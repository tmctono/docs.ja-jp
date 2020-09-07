---
ms.openlocfilehash: d23d7821e19b9d7f2db13a6bfdf868a8414cf721
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496162"
---
### <a name="item-scrolling-a-flat-list-with-items-of-different-pixel-height"></a><span data-ttu-id="deeb4-101">ピクセルの高さが異なる項目を含むフラット リストでの項目スクロール</span><span class="sxs-lookup"><span data-stu-id="deeb4-101">Item-scrolling a flat list with items of different pixel-height</span></span>

#### <a name="details"></a><span data-ttu-id="deeb4-102">説明</span><span class="sxs-lookup"><span data-stu-id="deeb4-102">Details</span></span>

<span data-ttu-id="deeb4-103"><xref:System.Windows.Controls.ItemsControl?displayProperty=fullName> に仮想化 (<code>IsVirtualizing=true</code>) と項目スクロール (<code>ScrollUnit=Item</code>) を使うコレクションが表示される場合、およびコントロールがスクロールされ、近隣項目と異なる高さ (ピクセル単位) の項目が表示される場合、<xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName> ではコレクション内のすべての項目に対してイテレーションが行われます。</span><span class="sxs-lookup"><span data-stu-id="deeb4-103">When an <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName> displays a collection using virtualization (<code>IsVirtualizing=true</code>) and item- scrolling (<code>ScrollUnit=Item</code>), and when the control scrolls to display an item whose height in pixels differs from its neighbors, the <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName> iterates over all items in the collection.</span></span> <span data-ttu-id="deeb4-104">このイテレーション中に UI は応答しません。コレクションのサイズが大きい場合、ハングとして認識される場合があります。</span><span class="sxs-lookup"><span data-stu-id="deeb4-104">The UI is unresponsive during this iteration; if the collection is large, this can be perceived as a hang.</span></span> <span data-ttu-id="deeb4-105">.NET Framework の以前のリリースであっても、このようなイテレーションは他の状況で発生します。</span><span class="sxs-lookup"><span data-stu-id="deeb4-105">The iteration occurs in other circumstances, even in previous .NET Framework releases.</span></span> <span data-ttu-id="deeb4-106">たとえば、これは、ピクセル スクロール (<code>ScrollUnit=Pixel</code>) が高さの異なる項目 (ピクセル単位) を検出した場合、および階層データの項目スクロール (<xref:System.Windows.Controls.TreeView?displayProperty=fullName> や、グループ化が有効になっている <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName> など) が近隣項目と異なる数の子項目を持つ項目を検出した場合に発生します。項目スクロールと高さが異なる (ピクセル単位) 場合の対処方として、階層データのレイアウトのバグを修正できるようイテレーションが .NET Framework 4.6.1 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="deeb4-106">For example, it occurs when pixel-scrolling (<code>ScrollUnit=Pixel</code>) upon encountering an item with different pixel height, and when item-scrolling hierarchical data (such as a <xref:System.Windows.Controls.TreeView?displayProperty=fullName> or an <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName> with grouping enabled) upon encountering an item with a different number of descendant items than its neighbors.For the case of item-scrolling and different pixel height, the iteration was introduced in .NET Framework 4.6.1 to fix bugs in the layout of hierarchical data.</span></span>  <span data-ttu-id="deeb4-107">データがフラットである場合 (階層がない場合) は必要ないため、そのような状況では .NET Framework 4.6.2 はイテレーションを行いません。</span><span class="sxs-lookup"><span data-stu-id="deeb4-107">It is not needed if the data is flat (no hierarchy), and .NET Framework 4.6.2 does not do it in that case.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="deeb4-108">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="deeb4-108">Suggestion</span></span>

<span data-ttu-id="deeb4-109">.NET Framework 4.6.1 でイテレーションが発生し、以前のリリースでは発生しない場合、つまり <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName> が異なる高さの (ピクセル単位) の項目を含むフラットなリストを項目スクロールしている場合、実行できる対応策は以下の 2 つです。</span><span class="sxs-lookup"><span data-stu-id="deeb4-109">If the iteration occurs in .NET Framework 4.6.1 but not in earlier releases - that is, if the <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName> is item- scrolling a flat list with items of different pixel height - there are two remedies:</span></span><ol><li><span data-ttu-id="deeb4-110">.NET Framework 4.6.2 をインストールします。</span><span class="sxs-lookup"><span data-stu-id="deeb4-110">Install .NET Framework 4.6.2.</span></span></li><li><span data-ttu-id="deeb4-111">.NET Framework 4.6.1 の修正プログラム HR 1605 をインストールします。</span><span class="sxs-lookup"><span data-stu-id="deeb4-111">Install hotfix HR 1605 for .NET Framework 4.6.1.</span></span></li></ol>

| <span data-ttu-id="deeb4-112">名前</span><span class="sxs-lookup"><span data-stu-id="deeb4-112">Name</span></span>    | <span data-ttu-id="deeb4-113">[値]</span><span class="sxs-lookup"><span data-stu-id="deeb4-113">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="deeb4-114">スコープ</span><span class="sxs-lookup"><span data-stu-id="deeb4-114">Scope</span></span>   |<span data-ttu-id="deeb4-115">マイナー</span><span class="sxs-lookup"><span data-stu-id="deeb4-115">Minor</span></span>|
|<span data-ttu-id="deeb4-116">バージョン</span><span class="sxs-lookup"><span data-stu-id="deeb4-116">Version</span></span>|<span data-ttu-id="deeb4-117">4.6.1</span><span class="sxs-lookup"><span data-stu-id="deeb4-117">4.6.1</span></span>|
|<span data-ttu-id="deeb4-118">種類</span><span class="sxs-lookup"><span data-stu-id="deeb4-118">Type</span></span>|<span data-ttu-id="deeb4-119">ランタイム</span><span class="sxs-lookup"><span data-stu-id="deeb4-119">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="deeb4-120">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="deeb4-120">Affected APIs</span></span>

- <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Windows.Controls.VirtualizingStackPanel`

-->
