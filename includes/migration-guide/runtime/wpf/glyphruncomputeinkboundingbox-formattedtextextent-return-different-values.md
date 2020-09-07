---
ms.openlocfilehash: d9e1624bbeb91db63bc284b8eb52643938eb42e5
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496326"
---
### <a name="glyphruncomputeinkboundingbox-and-formattedtextextent-return-different-values-beginning-in-net-framework-45"></a><span data-ttu-id="8f1ae-101">GlyphRun.ComputeInkBoundingBox() と FormattedText.Extent が、.NET Framework 4.5 以降では、異なる値を返す</span><span class="sxs-lookup"><span data-stu-id="8f1ae-101">GlyphRun.ComputeInkBoundingBox() and FormattedText.Extent return different values beginning in .NET Framework 4.5</span></span>

#### <a name="details"></a><span data-ttu-id="8f1ae-102">説明</span><span class="sxs-lookup"><span data-stu-id="8f1ae-102">Details</span></span>

<span data-ttu-id="8f1ae-103">.NET Framework 4.5 では、<xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox> と <xref:System.Windows.Media.FormattedText.Extent> が改善され、場合によっては含まれるグリフに対してボックスが小さすぎるという .NET Framework 4.0 での問題に対応しました。</span><span class="sxs-lookup"><span data-stu-id="8f1ae-103">Improvements were made to <xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox> and <xref:System.Windows.Media.FormattedText.Extent> in the .NET Framework 4.5 to address issues where the boxes were too small for the contained glyphs in some cases in the .NET Framework 4.0.</span></span> <span data-ttu-id="8f1ae-104">この結果、.NET Framework 4.5 以降では、いくつかの境界ボックスが大きくなり、UI のレイアウトにわずかな違いが生じます。</span><span class="sxs-lookup"><span data-stu-id="8f1ae-104">As a result of this, some bounding boxes will be larger beginning in the .NET Framework 4.5, resulting in subtle differences in UI layout.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="8f1ae-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="8f1ae-105">Suggestion</span></span>

<span data-ttu-id="8f1ae-106">いくつかのグリフの境界ボックスのサイズが大きくなったことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8f1ae-106">Be aware that some glyph bounding box sizes have increased.</span></span> <span data-ttu-id="8f1ae-107">このような変更は、通常、プレゼンテーションおよびヒット ボックス テストを向上させますが、以前の (.NET 4.5 より前の) 動作が望ましい場合は、次のエントリをアプリの構成ファイルに追加することによって実現できます。</span><span class="sxs-lookup"><span data-stu-id="8f1ae-107">These changes will usually improve presentation and hit box testing, but if the older (pre-.NET 4.5) behavior is desired, it can be opted into by adding the following entry to the app.config file:</span></span><pre><code class="lang-xml">&lt;appsettings&gt;&#13;&#10;&lt;add key=&quot;IncludeAllInkInBoundingBox&quot; value=&quot;false&quot;&gt;&#13;&#10;&lt;/appsettings&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="8f1ae-108">名前</span><span class="sxs-lookup"><span data-stu-id="8f1ae-108">Name</span></span>    | <span data-ttu-id="8f1ae-109">[値]</span><span class="sxs-lookup"><span data-stu-id="8f1ae-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="8f1ae-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="8f1ae-110">Scope</span></span>   |<span data-ttu-id="8f1ae-111">エッジ</span><span class="sxs-lookup"><span data-stu-id="8f1ae-111">Edge</span></span>|
|<span data-ttu-id="8f1ae-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="8f1ae-112">Version</span></span>|<span data-ttu-id="8f1ae-113">4.5</span><span class="sxs-lookup"><span data-stu-id="8f1ae-113">4.5</span></span>|
|<span data-ttu-id="8f1ae-114">種類</span><span class="sxs-lookup"><span data-stu-id="8f1ae-114">Type</span></span>|<span data-ttu-id="8f1ae-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="8f1ae-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="8f1ae-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="8f1ae-116">Affected APIs</span></span>

- <xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox?displayProperty=nameWithType>
- <xref:System.Windows.Media.FormattedText.Extent?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Windows.Media.GlyphRun.ComputeInkBoundingBox`
- `P:System.Windows.Media.FormattedText.Extent`

-->
