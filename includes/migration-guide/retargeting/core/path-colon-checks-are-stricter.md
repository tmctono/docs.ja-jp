---
ms.openlocfilehash: 3e4a5936bbac4e77efc5f7e68b55ddf49bae5d43
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614720"
---
### <a name="path-colon-checks-are-stricter"></a><span data-ttu-id="da104-101">パスのコロン確認が厳密化</span><span class="sxs-lookup"><span data-stu-id="da104-101">Path colon checks are stricter</span></span>

#### <a name="details"></a><span data-ttu-id="da104-102">説明</span><span class="sxs-lookup"><span data-stu-id="da104-102">Details</span></span>

<span data-ttu-id="da104-103">.NET Framework 4.6.2 では、以前はサポートされていなかったパスをサポートするために (長さと形式の両方で) 数多くの変更が加えられました。</span><span class="sxs-lookup"><span data-stu-id="da104-103">In .NET Framework 4.6.2, a number of changes were made to support previously unsupported paths (both in length and format).</span></span> <span data-ttu-id="da104-104">適切なドライブ区切り (コロン) 構文の確認がより正確に行われました。その結果、それ以前は許容されていた、ごく少数のパス API の一部の URI パスがブロックされました。</span><span class="sxs-lookup"><span data-stu-id="da104-104">Checks for proper drive separator (colon) syntax were made more correct, which had the side effect of blocking some URI paths in a few select Path APIs where they used to be tolerated.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="da104-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="da104-105">Suggestion</span></span>

<span data-ttu-id="da104-106">影響を受ける API に URI を渡す場合、まず、文字列を正規のパスに変更します。</span><span class="sxs-lookup"><span data-stu-id="da104-106">If passing a URI to affected APIs, modify the string to be a legal path first.</span></span><ul><li><span data-ttu-id="da104-107">URL から手動でスキームを削除します (たとえば、URL から `file://` を削除します)。</span><span class="sxs-lookup"><span data-stu-id="da104-107">Remove the scheme from URLs manually (e.g. remove `file://` from URLs)</span></span>

- <span data-ttu-id="da104-108"><xref:System.Uri> クラスに URI を渡し、<xref:System.Uri.LocalPath> を使用します。</span><span class="sxs-lookup"><span data-stu-id="da104-108">Pass the URI to the <xref:System.Uri> class and use <xref:System.Uri.LocalPath></span></span>

<span data-ttu-id="da104-109">あるいは、`Switch.System.IO.UseLegacyPathHandling` AppContext スイッチを true に設定し、新しいパス正規化を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="da104-109">Alternatively, you can opt out of the new path normalization by setting the `Switch.System.IO.UseLegacyPathHandling` AppContext switch to true.</span></span>

| <span data-ttu-id="da104-110">名前</span><span class="sxs-lookup"><span data-stu-id="da104-110">Name</span></span>    | <span data-ttu-id="da104-111">値</span><span class="sxs-lookup"><span data-stu-id="da104-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="da104-112">スコープ</span><span class="sxs-lookup"><span data-stu-id="da104-112">Scope</span></span>   | <span data-ttu-id="da104-113">エッジ</span><span class="sxs-lookup"><span data-stu-id="da104-113">Edge</span></span>        |
| <span data-ttu-id="da104-114">バージョン</span><span class="sxs-lookup"><span data-stu-id="da104-114">Version</span></span> | <span data-ttu-id="da104-115">4.6.2</span><span class="sxs-lookup"><span data-stu-id="da104-115">4.6.2</span></span>       |
| <span data-ttu-id="da104-116">種類</span><span class="sxs-lookup"><span data-stu-id="da104-116">Type</span></span>    | <span data-ttu-id="da104-117">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="da104-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="da104-118">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="da104-118">Affected APIs</span></span>

- <xref:System.IO.Path.GetDirectoryName(System.String)?displayProperty=nameWithType>
- <xref:System.IO.Path.GetPathRoot(System.String)?displayProperty=nameWithType>
