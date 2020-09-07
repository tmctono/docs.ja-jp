---
ms.openlocfilehash: 8c8477ae3719cfcc2060459ba85bcc9e76f11c41
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496818"
---
### <a name="xslt-forward-compat-now-works"></a><span data-ttu-id="ea339-101">XSLT 上位互換が機能するようになった</span><span class="sxs-lookup"><span data-stu-id="ea339-101">XSLT forward compat now works</span></span>

#### <a name="details"></a><span data-ttu-id="ea339-102">説明</span><span class="sxs-lookup"><span data-stu-id="ea339-102">Details</span></span>

<span data-ttu-id="ea339-103">.NET Framework 4 では、XSLT 1.0 の上位互換性に、次の問題がありました。</span><span class="sxs-lookup"><span data-stu-id="ea339-103">In the .NET Framework 4, XSLT 1.0 forward compatibility had the following issues:</span></span><ul><li><span data-ttu-id="ea339-104">バージョンが 2.0 に設定されているときに、パーサーが認識できない XSLT 1.0 コンストラクトに遭遇すると、スタイル シートの読み込みが失敗していました。</span><span class="sxs-lookup"><span data-stu-id="ea339-104">Loading a style sheet failed if its version was set to 2.0 and the parser encountered an unrecognized XSLT 1.0 construct.</span></span></li><li><span data-ttu-id="ea339-105">スタイル シートのバージョンが 1.1 に設定されている場合、<code>xsl:sort</code> コンストラクトでデータを並べ替えることができませんでした。</span><span class="sxs-lookup"><span data-stu-id="ea339-105">The <code>xsl:sort</code> construct failed to sort data if the style sheet version was set to 1.1.</span></span></li></ul><span data-ttu-id="ea339-106">.NET Framework 4.5 では、これらの問題は修正され、XSLT 1.0 の上位互換モードが正常に機能するようになりました。</span><span class="sxs-lookup"><span data-stu-id="ea339-106">In the .NET Framework 4.5, these issues have been fixed, and XSLT 1.0 forward compatibility mode works properly.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ea339-107">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="ea339-107">Suggestion</span></span>

<span data-ttu-id="ea339-108">ほとんどのアプリには影響しませんが、xsl:sort が優先される場合は異なる方法でデータが並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="ea339-108">Most apps should be unaffected, however data will be sorted differently in some cases now that xsl:sort is respected.</span></span> <span data-ttu-id="ea339-109"><code>xsl:sort</code> が 1.1 スタイル シートで使用されている場合は、アプリが並べ替えられていないデータの順序に依存していないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ea339-109">If <code>xsl:sort</code> is used in 1.1 style sheets, confirm that apps were not depending on the unsorted order of data.</span></span> <span data-ttu-id="ea339-110">アプリが 4.0 の並べ替え動作に依存している場合は、スタイル シートから <code>xsl:sort</code> を削除してください。</span><span class="sxs-lookup"><span data-stu-id="ea339-110">If apps rely on the 4.0 sorting behavior, remove <code>xsl:sort</code> from the style sheet.</span></span>

| <span data-ttu-id="ea339-111">名前</span><span class="sxs-lookup"><span data-stu-id="ea339-111">Name</span></span>    | <span data-ttu-id="ea339-112">[値]</span><span class="sxs-lookup"><span data-stu-id="ea339-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ea339-113">スコープ</span><span class="sxs-lookup"><span data-stu-id="ea339-113">Scope</span></span>   |<span data-ttu-id="ea339-114">エッジ</span><span class="sxs-lookup"><span data-stu-id="ea339-114">Edge</span></span>|
|<span data-ttu-id="ea339-115">バージョン</span><span class="sxs-lookup"><span data-stu-id="ea339-115">Version</span></span>|<span data-ttu-id="ea339-116">4.5</span><span class="sxs-lookup"><span data-stu-id="ea339-116">4.5</span></span>|
|<span data-ttu-id="ea339-117">種類</span><span class="sxs-lookup"><span data-stu-id="ea339-117">Type</span></span>|<span data-ttu-id="ea339-118">ランタイム</span><span class="sxs-lookup"><span data-stu-id="ea339-118">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="ea339-119">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="ea339-119">Affected APIs</span></span>

- <xref:System.Xml.Xsl.XslCompiledTransform?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Xml.Xsl.XslCompiledTransform`

-->
