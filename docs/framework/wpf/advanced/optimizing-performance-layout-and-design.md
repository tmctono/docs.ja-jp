---
title: パフォーマンスの最適化:レイアウトとデザイン
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- layout [WPF], optimizing performance
- design considerations [WPF]
- layout pass [WPF]
ms.assetid: 005f4cda-a849-448b-916b-38d14d9a96fe
ms.openlocfilehash: a18cc364d625cc98f77e63b0f361980ef574e8a5
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64611891"
---
# <a name="optimizing-performance-layout-and-design"></a><span data-ttu-id="47aa8-102">パフォーマンスの最適化:レイアウトとデザイン</span><span class="sxs-lookup"><span data-stu-id="47aa8-102">Optimizing Performance: Layout and Design</span></span>
<span data-ttu-id="47aa8-103">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] アプリケーションの設計によっては、レイアウトの計算やオブジェクト参照の検証で不要なオーバーヘッドが発生して、パフォーマンスに影響が及ぶことがあります。</span><span class="sxs-lookup"><span data-stu-id="47aa8-103">The design of your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application can impact its performance by creating unnecessary overhead in calculating layout and validating object references.</span></span> <span data-ttu-id="47aa8-104">オブジェクトの作成 (特に実行時の作成) はアプリケーションのパフォーマンス特性に影響する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="47aa8-104">The construction of objects, particularly at run time, can affect the performance characteristics of your application.</span></span>  
  
 <span data-ttu-id="47aa8-105">このトピックでは、このようなパフォーマンスに関する推奨事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="47aa8-105">This topic provides performance recommendations in these areas.</span></span>  
  
## <a name="layout"></a><span data-ttu-id="47aa8-106">レイアウト</span><span class="sxs-lookup"><span data-stu-id="47aa8-106">Layout</span></span>  
 <span data-ttu-id="47aa8-107">「レイアウト パス」という用語が測定および配置のメンバーのプロセスについて説明します、 <xref:System.Windows.Controls.Panel>-派生したオブジェクトのコレクションの子、およびそれらの画面を描画します。</span><span class="sxs-lookup"><span data-stu-id="47aa8-107">The term "layout pass" describes the process of measuring and arranging the members of a <xref:System.Windows.Controls.Panel>-derived object's collection of children, and then drawing them onscreen.</span></span> <span data-ttu-id="47aa8-108">レイアウト パスは数学的に増大するプロセスで、コレクション内の子の数が多くなれば、必要な計算の数も多くなります。</span><span class="sxs-lookup"><span data-stu-id="47aa8-108">The layout pass is a mathematically-intensive process—the larger the number of children in the collection, the greater the number of calculations required.</span></span> <span data-ttu-id="47aa8-109">たとえば、たびに、子<xref:System.Windows.UIElement>コレクション内のオブジェクトがその位置を変更、レイアウト システムによる新しいパスをトリガーする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="47aa8-109">For example, each time a child <xref:System.Windows.UIElement> object in the collection changes its position, it has the potential to trigger a new pass by the layout system.</span></span> <span data-ttu-id="47aa8-110">オブジェクトの特性とレイアウトの動作の間には密接な関係があるため、レイアウト システムを呼び出すことができるイベントの種類を把握することが重要です。</span><span class="sxs-lookup"><span data-stu-id="47aa8-110">Because of the close relationship between object characteristics and layout behavior, it's important to understand the type of events that can invoke the layout system.</span></span> <span data-ttu-id="47aa8-111">レイアウト パスの不要な呼び出しをできるだけ減らすことで、アプリケーションのパフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="47aa8-111">Your application will perform better by reducing as much as possible any unnecessary invocations of the layout pass.</span></span>  
  
 <span data-ttu-id="47aa8-112">レイアウト システムは、コレクションの子メンバーごとに、測定パスと配置パスという 2 つのパスを実行します。</span><span class="sxs-lookup"><span data-stu-id="47aa8-112">The layout system completes two passes for each child member in a collection: a measure pass, and an arrange pass.</span></span> <span data-ttu-id="47aa8-113">各子オブジェクトのオーバーライドされた実装を提供する、<xref:System.Windows.UIElement.Measure%2A>と<xref:System.Windows.UIElement.Arrange%2A>メソッドは独自の特定のレイアウト動作を提供するためにします。</span><span class="sxs-lookup"><span data-stu-id="47aa8-113">Each child object provides its own overridden implementation of the <xref:System.Windows.UIElement.Measure%2A> and <xref:System.Windows.UIElement.Arrange%2A> methods in order to provide its own specific layout behavior.</span></span> <span data-ttu-id="47aa8-114">簡単に言うと、レイアウトは、要素のサイズ測定、配置、画面上への描画を繰り返す再帰的なシステムです。</span><span class="sxs-lookup"><span data-stu-id="47aa8-114">At its simplest, layout is a recursive system that leads to an element being sized, positioned, and drawn onscreen.</span></span>  
  
- <span data-ttu-id="47aa8-115">子<xref:System.Windows.UIElement>オブジェクトは最初そのコア プロパティを測定することで、レイアウト プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="47aa8-115">A child <xref:System.Windows.UIElement> object begins the layout process by first having its core properties measured.</span></span>  
  
- <span data-ttu-id="47aa8-116">オブジェクトの<xref:System.Windows.FrameworkElement>など、サイズに関連したプロパティ<xref:System.Windows.FrameworkElement.Width%2A>、 <xref:System.Windows.FrameworkElement.Height%2A>、および<xref:System.Windows.FrameworkElement.Margin%2A>、評価されます。</span><span class="sxs-lookup"><span data-stu-id="47aa8-116">The object's <xref:System.Windows.FrameworkElement> properties that are related to size, such as <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.Height%2A>, and <xref:System.Windows.FrameworkElement.Margin%2A>, are evaluated.</span></span>  
  
- <span data-ttu-id="47aa8-117"><xref:System.Windows.Controls.Panel>-など特定のロジックが適用される、<xref:System.Windows.Controls.DockPanel.Dock%2A>のプロパティ、 <xref:System.Windows.Controls.DockPanel>、または<xref:System.Windows.Controls.StackPanel.Orientation%2A>のプロパティ、<xref:System.Windows.Controls.StackPanel>します。</span><span class="sxs-lookup"><span data-stu-id="47aa8-117"><xref:System.Windows.Controls.Panel>-specific logic is applied, such as the <xref:System.Windows.Controls.DockPanel.Dock%2A> property of the <xref:System.Windows.Controls.DockPanel>, or the <xref:System.Windows.Controls.StackPanel.Orientation%2A> property of the <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
- <span data-ttu-id="47aa8-118">すべての子オブジェクトが測定された後、コンテンツが配置されます。</span><span class="sxs-lookup"><span data-stu-id="47aa8-118">Content is arranged, or positioned, after all child objects have been measured.</span></span>  
  
- <span data-ttu-id="47aa8-119">子オブジェクトのコレクションが画面に描画されます。</span><span class="sxs-lookup"><span data-stu-id="47aa8-119">The collection of child objects is drawn to the screen.</span></span>  
  
 <span data-ttu-id="47aa8-120">以下のアクションが発生すると、再びレイアウト パス プロセスが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="47aa8-120">The layout pass process is invoked again if any of the following actions occur:</span></span>  
  
- <span data-ttu-id="47aa8-121">子オブジェクトがコレクションに追加された場合。</span><span class="sxs-lookup"><span data-stu-id="47aa8-121">A child object is added to the collection.</span></span>  
  
- <span data-ttu-id="47aa8-122">A<xref:System.Windows.FrameworkElement.LayoutTransform%2A>子オブジェクトに適用されます。</span><span class="sxs-lookup"><span data-stu-id="47aa8-122">A <xref:System.Windows.FrameworkElement.LayoutTransform%2A> is applied to the child object.</span></span>  
  
- <span data-ttu-id="47aa8-123"><xref:System.Windows.UIElement.UpdateLayout%2A>子オブジェクトのメソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="47aa8-123">The <xref:System.Windows.UIElement.UpdateLayout%2A> method is called for the child object.</span></span>  
  
- <span data-ttu-id="47aa8-124">測定パスや配置パスに影響を与えるものとしてメタデータでマークされている依存関係プロパティの値が変更された場合。</span><span class="sxs-lookup"><span data-stu-id="47aa8-124">When a change occurs to the value of a dependency property that is marked with metadata affecting the measure or arrange passes.</span></span>  
  
### <a name="use-the-most-efficient-panel-where-possible"></a><span data-ttu-id="47aa8-125">可能な場合は最も効率的なパネルを使用する</span><span class="sxs-lookup"><span data-stu-id="47aa8-125">Use the Most Efficient Panel where Possible</span></span>  
 <span data-ttu-id="47aa8-126">レイアウト動作に直接基づくレイアウト プロセスの複雑さ、 <xref:System.Windows.Controls.Panel>-派生を使用する要素。</span><span class="sxs-lookup"><span data-stu-id="47aa8-126">The complexity of the layout process is directly based on the layout behavior of the <xref:System.Windows.Controls.Panel>-derived elements you use.</span></span> <span data-ttu-id="47aa8-127">たとえば、<xref:System.Windows.Controls.Grid>または<xref:System.Windows.Controls.StackPanel>コントロールよりも多くの機能を提供する、<xref:System.Windows.Controls.Canvas>コントロール。</span><span class="sxs-lookup"><span data-stu-id="47aa8-127">For example, a <xref:System.Windows.Controls.Grid> or <xref:System.Windows.Controls.StackPanel> control provides much more functionality than a <xref:System.Windows.Controls.Canvas> control.</span></span> <span data-ttu-id="47aa8-128">はるかに多くの機能が用意されていますが、その代償として、パフォーマンスへの負荷も高くなります。</span><span class="sxs-lookup"><span data-stu-id="47aa8-128">The price for this greater increase in functionality is a greater increase in performance costs.</span></span> <span data-ttu-id="47aa8-129">ただし、機能が必要としない場合、<xref:System.Windows.Controls.Grid>コントロールが提供するなどの低コストの代替手段を使用する必要があります、<xref:System.Windows.Controls.Canvas>やカスタム パネル。</span><span class="sxs-lookup"><span data-stu-id="47aa8-129">However, if you do not require the functionality that a <xref:System.Windows.Controls.Grid> control provides, you should use the less costly alternatives, such as a <xref:System.Windows.Controls.Canvas> or a custom panel.</span></span>  
  
 <span data-ttu-id="47aa8-130">詳細については、「[Panels Overview](../controls/panels-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47aa8-130">For more information, see [Panels Overview](../controls/panels-overview.md).</span></span>  
  
### <a name="update-rather-than-replace-a-rendertransform"></a><span data-ttu-id="47aa8-131">RenderTransform は置き換えずに更新する</span><span class="sxs-lookup"><span data-stu-id="47aa8-131">Update Rather than Replace a RenderTransform</span></span>  
 <span data-ttu-id="47aa8-132">更新することができます、<xref:System.Windows.Media.Transform>の値に置換することではなく、<xref:System.Windows.UIElement.RenderTransform%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="47aa8-132">You may be able to update a <xref:System.Windows.Media.Transform> rather than replacing it as the value of a <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span> <span data-ttu-id="47aa8-133">アニメーションを含むシナリオでは特にこれが当てはまります。</span><span class="sxs-lookup"><span data-stu-id="47aa8-133">This is particularly true in scenarios that involve animation.</span></span> <span data-ttu-id="47aa8-134">既存の更新によって<xref:System.Windows.Media.Transform>、不要なレイアウト計算を開始することを回避します。</span><span class="sxs-lookup"><span data-stu-id="47aa8-134">By updating an existing <xref:System.Windows.Media.Transform>, you avoid initiating an unnecessary layout calculation.</span></span>  
  
### <a name="build-your-tree-top-down"></a><span data-ttu-id="47aa8-135">ツリーはトップダウンで作成する</span><span class="sxs-lookup"><span data-stu-id="47aa8-135">Build Your Tree Top-Down</span></span>  
 <span data-ttu-id="47aa8-136">論理ツリーのノードが追加または削除されると、ノードの親とそのすべての子でプロパティの無効化が行われます。</span><span class="sxs-lookup"><span data-stu-id="47aa8-136">When a node is added or removed from the logical tree, property invalidations are raised on the node's parent and all its children.</span></span> <span data-ttu-id="47aa8-137">このため、常にトップダウンの作成パターンに従って、検証済みのノードで無駄に無効化が行われないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="47aa8-137">As a result, a top-down construction pattern should always be followed to avoid the cost of unnecessary invalidations on nodes that have already been validated.</span></span> <span data-ttu-id="47aa8-138">次の表は、ツリーを作成する場合とボトムアップ ツリーが 150 レベルの深さを 1 つを上から下への実行速度の違いを示しています。<xref:System.Windows.Controls.TextBlock>と<xref:System.Windows.Controls.DockPanel>各レベル。</span><span class="sxs-lookup"><span data-stu-id="47aa8-138">The following table shows the difference in execution speed between building a tree top-down versus bottom-up, where the tree is 150 levels deep with a single <xref:System.Windows.Controls.TextBlock> and <xref:System.Windows.Controls.DockPanel> at each level.</span></span>  
  
|<span data-ttu-id="47aa8-139">**動作**</span><span class="sxs-lookup"><span data-stu-id="47aa8-139">**Action**</span></span>|<span data-ttu-id="47aa8-140">**ツリーの作成 (ミリ秒)**</span><span class="sxs-lookup"><span data-stu-id="47aa8-140">**Tree building (in ms)**</span></span>|<span data-ttu-id="47aa8-141">**レンダリング-ツリーの作成を含む (ミリ秒)**</span><span class="sxs-lookup"><span data-stu-id="47aa8-141">**Render—includes tree building (in ms)**</span></span>|  
|----------------|---------------------------------|-------------------------------------------------|  
|<span data-ttu-id="47aa8-142">ボトムアップ</span><span class="sxs-lookup"><span data-stu-id="47aa8-142">Bottom-up</span></span>|<span data-ttu-id="47aa8-143">366</span><span class="sxs-lookup"><span data-stu-id="47aa8-143">366</span></span>|<span data-ttu-id="47aa8-144">454</span><span class="sxs-lookup"><span data-stu-id="47aa8-144">454</span></span>|  
|<span data-ttu-id="47aa8-145">トップダウン</span><span class="sxs-lookup"><span data-stu-id="47aa8-145">Top-down</span></span>|<span data-ttu-id="47aa8-146">11</span><span class="sxs-lookup"><span data-stu-id="47aa8-146">11</span></span>|<span data-ttu-id="47aa8-147">96</span><span class="sxs-lookup"><span data-stu-id="47aa8-147">96</span></span>|  
  
 <span data-ttu-id="47aa8-148">ツリーをトップダウンで作成する方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="47aa8-148">The following code example demonstrates how to create a tree top down.</span></span>  
  
 [!code-csharp[Performance#PerformanceSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet1)]
 [!code-vb[Performance#PerformanceSnippet1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet1)]  
  
 <span data-ttu-id="47aa8-149">論理ツリーについて詳しくは、「[WPF のツリー](trees-in-wpf.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="47aa8-149">For more information on the logical tree, see [Trees in WPF](trees-in-wpf.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47aa8-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="47aa8-150">See also</span></span>

- [<span data-ttu-id="47aa8-151">WPF アプリケーションのパフォーマンスの最適化</span><span class="sxs-lookup"><span data-stu-id="47aa8-151">Optimizing WPF Application Performance</span></span>](optimizing-wpf-application-performance.md)
- [<span data-ttu-id="47aa8-152">アプリケーション パフォーマンスの計画</span><span class="sxs-lookup"><span data-stu-id="47aa8-152">Planning for Application Performance</span></span>](planning-for-application-performance.md)
- [<span data-ttu-id="47aa8-153">ハードウェアの活用</span><span class="sxs-lookup"><span data-stu-id="47aa8-153">Taking Advantage of Hardware</span></span>](optimizing-performance-taking-advantage-of-hardware.md)
- [<span data-ttu-id="47aa8-154">2D グラフィックスとイメージング</span><span class="sxs-lookup"><span data-stu-id="47aa8-154">2D Graphics and Imaging</span></span>](optimizing-performance-2d-graphics-and-imaging.md)
- [<span data-ttu-id="47aa8-155">オブジェクトの動作</span><span class="sxs-lookup"><span data-stu-id="47aa8-155">Object Behavior</span></span>](optimizing-performance-object-behavior.md)
- [<span data-ttu-id="47aa8-156">アプリケーション リソース</span><span class="sxs-lookup"><span data-stu-id="47aa8-156">Application Resources</span></span>](optimizing-performance-application-resources.md)
- [<span data-ttu-id="47aa8-157">Text</span><span class="sxs-lookup"><span data-stu-id="47aa8-157">Text</span></span>](optimizing-performance-text.md)
- [<span data-ttu-id="47aa8-158">データ バインディング</span><span class="sxs-lookup"><span data-stu-id="47aa8-158">Data Binding</span></span>](optimizing-performance-data-binding.md)
- [<span data-ttu-id="47aa8-159">パフォーマンスに関するその他の推奨事項</span><span class="sxs-lookup"><span data-stu-id="47aa8-159">Other Performance Recommendations</span></span>](optimizing-performance-other-recommendations.md)
- [<span data-ttu-id="47aa8-160">レイアウト</span><span class="sxs-lookup"><span data-stu-id="47aa8-160">Layout</span></span>](layout.md)
