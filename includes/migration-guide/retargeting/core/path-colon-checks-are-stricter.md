---
ms.openlocfilehash: 6af63c0a58a3273aa98fa70f22e3637b481806b4
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496630"
---
### <a name="path-colon-checks-are-stricter"></a><span data-ttu-id="d1bd7-101">パスのコロン確認が厳密化</span><span class="sxs-lookup"><span data-stu-id="d1bd7-101">Path colon checks are stricter</span></span>

#### <a name="details"></a><span data-ttu-id="d1bd7-102">説明</span><span class="sxs-lookup"><span data-stu-id="d1bd7-102">Details</span></span>

<span data-ttu-id="d1bd7-103">.NET Framework 4.6.2 では、以前はサポートされていなかったパスをサポートするために (長さと形式の両方で) 数多くの変更が加えられました。</span><span class="sxs-lookup"><span data-stu-id="d1bd7-103">In .NET Framework 4.6.2, a number of changes were made to support previously unsupported paths (both in length and format).</span></span> <span data-ttu-id="d1bd7-104">ドライブの区切り (コロン) 構文がより厳密に確認されるようになった結果、それ以前は許容されていた、選ばれた少数のパス API の一部の URI パスがブロックされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="d1bd7-104">Checks for proper drive separator (colon) syntax were made more correct, which had the side effect of blocking some URI paths in a few select Path APIs where they were previously tolerated.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d1bd7-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="d1bd7-105">Suggestion</span></span>

<span data-ttu-id="d1bd7-106">影響を受ける API に URI を渡す場合、まず、文字列を正規のパスに変更します。</span><span class="sxs-lookup"><span data-stu-id="d1bd7-106">If passing a URI to affected APIs, modify the string to be a legal path first.</span></span>

- <span data-ttu-id="d1bd7-107">URL から手動でスキームを削除します (たとえば、URL から `file://` を削除します)。</span><span class="sxs-lookup"><span data-stu-id="d1bd7-107">Remove the scheme from URLs manually (for example, remove `file://` from URLs).</span></span>

- <span data-ttu-id="d1bd7-108"><xref:System.Uri> クラスに URI を渡し、<xref:System.Uri.LocalPath> を使用します。</span><span class="sxs-lookup"><span data-stu-id="d1bd7-108">Pass the URI to the <xref:System.Uri> class and use <xref:System.Uri.LocalPath>.</span></span>

<span data-ttu-id="d1bd7-109">あるいは、`Switch.System.IO.UseLegacyPathHandling` AppContext スイッチを `true` に設定し、新しいパス正規化を無効にします。</span><span class="sxs-lookup"><span data-stu-id="d1bd7-109">Alternatively, you can opt out of the new path normalization by setting the `Switch.System.IO.UseLegacyPathHandling` AppContext switch to `true`.</span></span>

| <span data-ttu-id="d1bd7-110">名前</span><span class="sxs-lookup"><span data-stu-id="d1bd7-110">Name</span></span>    | <span data-ttu-id="d1bd7-111">[値]</span><span class="sxs-lookup"><span data-stu-id="d1bd7-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d1bd7-112">スコープ</span><span class="sxs-lookup"><span data-stu-id="d1bd7-112">Scope</span></span>   | <span data-ttu-id="d1bd7-113">エッジ</span><span class="sxs-lookup"><span data-stu-id="d1bd7-113">Edge</span></span>        |
| <span data-ttu-id="d1bd7-114">バージョン</span><span class="sxs-lookup"><span data-stu-id="d1bd7-114">Version</span></span> | <span data-ttu-id="d1bd7-115">4.6.2</span><span class="sxs-lookup"><span data-stu-id="d1bd7-115">4.6.2</span></span>       |
| <span data-ttu-id="d1bd7-116">種類</span><span class="sxs-lookup"><span data-stu-id="d1bd7-116">Type</span></span>    | <span data-ttu-id="d1bd7-117">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="d1bd7-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="d1bd7-118">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="d1bd7-118">Affected APIs</span></span>

- <xref:System.IO.Path.GetDirectoryName(System.String)?displayProperty=nameWithType>
- <xref:System.IO.Path.GetPathRoot(System.String)?displayProperty=nameWithType>
