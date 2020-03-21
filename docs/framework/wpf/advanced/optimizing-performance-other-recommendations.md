---
title: 'パフォーマンスの最適化 : その他の推奨事項'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Terminal Services rendering [WPF]
- opacity [WPF]
- hit-test objects [WPF]
- ScrollBarVisibility enumeration [WPF]
- brushes [WPF], performance
ms.assetid: d028cc65-7e97-4a4f-9859-929734eaf40d
ms.openlocfilehash: 727331adb41251460209f157d1804ff455bcf473
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186302"
---
# <a name="optimizing-performance-other-recommendations"></a><span data-ttu-id="c11b7-102">パフォーマンスの最適化 : その他の推奨事項</span><span class="sxs-lookup"><span data-stu-id="c11b7-102">Optimizing Performance: Other Recommendations</span></span>
<a name="introduction"></a> <span data-ttu-id="c11b7-103">このトピックでは、「[WPF アプリケーションのパフォーマンスの最適化](optimizing-wpf-application-performance.md)」セクションのトピックで説明されている推奨事項を補足するパフォーマンスに関する推奨事項について取り上げます。</span><span class="sxs-lookup"><span data-stu-id="c11b7-103">This topic provides performance recommendations in addition to the ones covered by the topics in the [Optimizing WPF Application Performance](optimizing-wpf-application-performance.md) section.</span></span>  
  
 <span data-ttu-id="c11b7-104">このトピックには、次のセクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c11b7-104">This topic contains the following sections:</span></span>  
  
- [<span data-ttu-id="c11b7-105">ブラシの Opacity と要素の Opacity</span><span class="sxs-lookup"><span data-stu-id="c11b7-105">Opacity on Brushes Versus Opacity on Elements</span></span>](#Opacity)  
  
- [<span data-ttu-id="c11b7-106">オブジェクトへの移動</span><span class="sxs-lookup"><span data-stu-id="c11b7-106">Navigation to Object</span></span>](#Navigation_Objects)  
  
- [<span data-ttu-id="c11b7-107">大きな 3D サーフェイスのヒット テスト</span><span class="sxs-lookup"><span data-stu-id="c11b7-107">Hit Testing on Large 3D Surfaces</span></span>](#Hit_Testing)  
  
- [<span data-ttu-id="c11b7-108">CompositionTarget.Rendering イベント</span><span class="sxs-lookup"><span data-stu-id="c11b7-108">CompositionTarget.Rendering Event</span></span>](#CompositionTarget_Rendering_Event)  
  
- [<span data-ttu-id="c11b7-109">ScrollBarVisibility=Auto は使用しない</span><span class="sxs-lookup"><span data-stu-id="c11b7-109">Avoid Using ScrollBarVisibility=Auto</span></span>](#Avoid_Using_ScrollBarVisibility)  
  
- [<span data-ttu-id="c11b7-110">Font Cache サービスの構成による起動時間の短縮</span><span class="sxs-lookup"><span data-stu-id="c11b7-110">Configure Font Cache Service to Reduce Start-up Time</span></span>](#FontCache)  
  
<a name="Opacity"></a>
## <a name="opacity-on-brushes-versus-opacity-on-elements"></a><span data-ttu-id="c11b7-111">ブラシの Opacity と要素の Opacity</span><span class="sxs-lookup"><span data-stu-id="c11b7-111">Opacity on Brushes Versus Opacity on Elements</span></span>  
 <span data-ttu-id="c11b7-112">を<xref:System.Windows.Media.Brush>使用して 要素の<xref:System.Windows.Shapes.Shape.Fill%2A>を<xref:System.Windows.Shapes.Shape.Stroke%2A>設定する場合は、要素の<xref:System.Windows.Media.Brush.Opacity%2A?displayProperty=nameWithType><xref:System.Windows.UIElement.Opacity%2A>プロパティを設定するよりも、値を設定することをおし。</span><span class="sxs-lookup"><span data-stu-id="c11b7-112">When you use a <xref:System.Windows.Media.Brush> to set the <xref:System.Windows.Shapes.Shape.Fill%2A> or <xref:System.Windows.Shapes.Shape.Stroke%2A> of an element, it is better to set the <xref:System.Windows.Media.Brush.Opacity%2A?displayProperty=nameWithType> value rather than the setting the element's <xref:System.Windows.UIElement.Opacity%2A> property.</span></span> <span data-ttu-id="c11b7-113">要素の<xref:System.Windows.UIElement.Opacity%2A>プロパティを変更すると、一時的[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]なサーフェスが作成される場合があります。</span><span class="sxs-lookup"><span data-stu-id="c11b7-113">Modifying an element's <xref:System.Windows.UIElement.Opacity%2A> property can cause [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] to create a temporary surface.</span></span>  
  
<a name="Navigation_Objects"></a>
## <a name="navigation-to-object"></a><span data-ttu-id="c11b7-114">オブジェクトへの移動</span><span class="sxs-lookup"><span data-stu-id="c11b7-114">Navigation to Object</span></span>  
 <span data-ttu-id="c11b7-115">オブジェクト<xref:System.Windows.Navigation.NavigationWindow>は、主に<xref:System.Windows.Window>集約とジャーナルによって、コンテンツ ナビゲーションのサポートを使用してオブジェクトを<xref:System.Windows.Navigation.NavigationService>派生および拡張します。</span><span class="sxs-lookup"><span data-stu-id="c11b7-115">The <xref:System.Windows.Navigation.NavigationWindow> object derives from <xref:System.Windows.Window> and extends it with content navigation support, primarily by aggregating <xref:System.Windows.Navigation.NavigationService> and the journal.</span></span> <span data-ttu-id="c11b7-116">のクライアント領域は、統一<xref:System.Windows.Navigation.NavigationWindow>リソース識別子 (URI) またはオブジェクトのいずれかを指定して更新できます。</span><span class="sxs-lookup"><span data-stu-id="c11b7-116">You can update the client area of <xref:System.Windows.Navigation.NavigationWindow> by specifying either a uniform resource identifier (URI) or an object.</span></span> <span data-ttu-id="c11b7-117">この両方の方法を次のサンプルに示します。</span><span class="sxs-lookup"><span data-stu-id="c11b7-117">The following sample shows both methods:</span></span>  
  
 [!code-csharp[Performance#PerformanceSnippet14](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/TestNavigation.xaml.cs#performancesnippet14)]
 [!code-vb[Performance#PerformanceSnippet14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/testnavigation.xaml.vb#performancesnippet14)]  
  
 <span data-ttu-id="c11b7-118">各<xref:System.Windows.Navigation.NavigationWindow>オブジェクトには、そのウィンドウにユーザーのナビゲーション履歴を記録するジャーナルがあります。</span><span class="sxs-lookup"><span data-stu-id="c11b7-118">Each <xref:System.Windows.Navigation.NavigationWindow> object has a journal that records the user's navigation history in that window.</span></span> <span data-ttu-id="c11b7-119">履歴の目的の 1 つは、ユーザーが自分の来た道を戻れるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="c11b7-119">One of the purposes of the journal is to allow users to retrace their steps.</span></span>  
  
 <span data-ttu-id="c11b7-120">統一リソース識別子 (URI) を使用してナビゲートする場合、ジャーナルは統一リソース識別子 (URI) 参照のみを格納します。</span><span class="sxs-lookup"><span data-stu-id="c11b7-120">When you navigate using a uniform resource identifier (URI), the journal stores only the uniform resource identifier (URI) reference.</span></span> <span data-ttu-id="c11b7-121">したがって、ページに戻るたびにそのページが動的に再構築されることになり、ページの複雑さによってはかなりの時間がかかることもあります。</span><span class="sxs-lookup"><span data-stu-id="c11b7-121">This means that each time you revisit the page, it is dynamically reconstructed, which may be time consuming depending on the complexity of the page.</span></span> <span data-ttu-id="c11b7-122">この場合、履歴の格納の負荷は低い反面、ページの再構築にかかる時間が長くなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c11b7-122">In this case, the journal storage cost is low, but the time to reconstitute the page is potentially high.</span></span>  
  
 <span data-ttu-id="c11b7-123">オブジェクトを使用して移動した場合は、オブジェクトのビジュアル ツリー全体が履歴に格納されます。</span><span class="sxs-lookup"><span data-stu-id="c11b7-123">When you navigate using an object, the journal stores the entire visual tree of the object.</span></span> <span data-ttu-id="c11b7-124">したがって、ページに戻るたびにページを再構築する必要はなく、ページがすぐに描画されます。</span><span class="sxs-lookup"><span data-stu-id="c11b7-124">This means that each time you revisit the page, it renders immediately without having to be reconstructed.</span></span> <span data-ttu-id="c11b7-125">この場合、履歴の格納の負荷は高くなりますが、ページの再構築にかかる時間は短くて済みます。</span><span class="sxs-lookup"><span data-stu-id="c11b7-125">In this case, the journal storage cost is high, but the time to reconstitute the page is low.</span></span>  
  
 <span data-ttu-id="c11b7-126">オブジェクトを<xref:System.Windows.Navigation.NavigationWindow>使用する場合は、ジャーナリング・サポートがアプリケーションのパフォーマンスにどのような影響を与えるのかを念頭に置く必要があります。</span><span class="sxs-lookup"><span data-stu-id="c11b7-126">When you use the <xref:System.Windows.Navigation.NavigationWindow> object, you will need to keep in mind how the journaling support impacts your application's performance.</span></span> <span data-ttu-id="c11b7-127">詳細については、「ナビゲーションの[概要](../app-development/navigation-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c11b7-127">For more information, see [Navigation Overview](../app-development/navigation-overview.md).</span></span>  
  
<a name="Hit_Testing"></a>
## <a name="hit-testing-on-large-3d-surfaces"></a><span data-ttu-id="c11b7-128">大きな 3D サーフェイスのヒット テスト</span><span class="sxs-lookup"><span data-stu-id="c11b7-128">Hit Testing on Large 3D Surfaces</span></span>  
 <span data-ttu-id="c11b7-129">大きな 3D サーフェイスのヒット テストは、CPU 消費の面でパフォーマンスへの影響が非常に大きくなります。</span><span class="sxs-lookup"><span data-stu-id="c11b7-129">Hit testing on large 3D surfaces is a very performance intensive operation in terms of CPU consumption.</span></span> <span data-ttu-id="c11b7-130">3D サーフェイスがアニメーション化されている場合には特にその傾向が強くなります。</span><span class="sxs-lookup"><span data-stu-id="c11b7-130">This is especially true when the 3D surface is animating.</span></span> <span data-ttu-id="c11b7-131">そのようなサーフェイスでヒット テストを行う必要がない場合は、ヒット テストを無効にしてください。</span><span class="sxs-lookup"><span data-stu-id="c11b7-131">If you do not require hit testing on these surfaces, then disable hit testing.</span></span> <span data-ttu-id="c11b7-132">から<xref:System.Windows.UIElement>派生したオブジェクトは、プロパティを に設定することで<xref:System.Windows.UIElement.IsHitTestVisible%2A>ヒット`false`テストを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c11b7-132">Objects that are derived from <xref:System.Windows.UIElement> can disable hit testing by setting the <xref:System.Windows.UIElement.IsHitTestVisible%2A> property to `false`.</span></span>  
  
<a name="CompositionTarget_Rendering_Event"></a>
## <a name="compositiontargetrendering-event"></a><span data-ttu-id="c11b7-133">CompositionTarget.Rendering イベント</span><span class="sxs-lookup"><span data-stu-id="c11b7-133">CompositionTarget.Rendering Event</span></span>  
 <span data-ttu-id="c11b7-134">イベント<xref:System.Windows.Media.CompositionTarget.Rendering?displayProperty=nameWithType>が連続[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]的にアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="c11b7-134">The <xref:System.Windows.Media.CompositionTarget.Rendering?displayProperty=nameWithType> event causes [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] to continuously animate.</span></span> <span data-ttu-id="c11b7-135">このイベントを使用する場合は、毎回デタッチしてください。</span><span class="sxs-lookup"><span data-stu-id="c11b7-135">If you use this event, detach it at every opportunity.</span></span>  
  
<a name="Avoid_Using_ScrollBarVisibility"></a>
## <a name="avoid-using-scrollbarvisibilityauto"></a><span data-ttu-id="c11b7-136">ScrollBarVisibility=Auto は使用しない</span><span class="sxs-lookup"><span data-stu-id="c11b7-136">Avoid Using ScrollBarVisibility=Auto</span></span>  
 <span data-ttu-id="c11b7-137">可能な限り、<xref:System.Windows.Controls.ScrollBarVisibility.Auto?displayProperty=nameWithType>`HorizontalScrollBarVisibility`プロパティの値を`VerticalScrollBarVisibility`使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="c11b7-137">Whenever possible, avoid using the <xref:System.Windows.Controls.ScrollBarVisibility.Auto?displayProperty=nameWithType> value for the `HorizontalScrollBarVisibility` and `VerticalScrollBarVisibility` properties.</span></span> <span data-ttu-id="c11b7-138">これらのプロパティは、<xref:System.Windows.Controls.RichTextBox>および<xref:System.Windows.Controls.ScrollViewer>オブジェクト<xref:System.Windows.Controls.TextBox>に対して定義され、オブジェクトの添付<xref:System.Windows.Controls.ListBox>プロパティとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="c11b7-138">These properties are defined for <xref:System.Windows.Controls.RichTextBox>, <xref:System.Windows.Controls.ScrollViewer>, and <xref:System.Windows.Controls.TextBox> objects, and as an attached property for the <xref:System.Windows.Controls.ListBox> object.</span></span> <span data-ttu-id="c11b7-139">代わりに、 <xref:System.Windows.Controls.ScrollBarVisibility> <xref:System.Windows.Controls.ScrollBarVisibility.Disabled>、 <xref:System.Windows.Controls.ScrollBarVisibility.Hidden>、<xref:System.Windows.Controls.ScrollBarVisibility.Visible>または に設定します。</span><span class="sxs-lookup"><span data-stu-id="c11b7-139">Instead, set <xref:System.Windows.Controls.ScrollBarVisibility> to <xref:System.Windows.Controls.ScrollBarVisibility.Disabled>, <xref:System.Windows.Controls.ScrollBarVisibility.Hidden>, or <xref:System.Windows.Controls.ScrollBarVisibility.Visible>.</span></span>  
  
 <span data-ttu-id="c11b7-140">この<xref:System.Windows.Controls.ScrollBarVisibility.Auto>値は、スペースが限られており、必要な場合にのみスクロールバーを表示する必要がある場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c11b7-140">The <xref:System.Windows.Controls.ScrollBarVisibility.Auto> value is intended for cases when space is limited and scrollbars should only be displayed when necessary.</span></span> <span data-ttu-id="c11b7-141">たとえば、数百行のテキストを<xref:System.Windows.Controls.ScrollBarVisibility><xref:System.Windows.Controls.ListBox><xref:System.Windows.Controls.TextBox>含むのとは対照的に、この値を 30 項目の 1 つの値で使用すると便利です。</span><span class="sxs-lookup"><span data-stu-id="c11b7-141">For example, it may be useful to use this <xref:System.Windows.Controls.ScrollBarVisibility> value with a <xref:System.Windows.Controls.ListBox> of 30 items as opposed to a <xref:System.Windows.Controls.TextBox> with hundreds of lines of text.</span></span>  
  
<a name="FontCache"></a>
## <a name="configure-font-cache-service-to-reduce-start-up-time"></a><span data-ttu-id="c11b7-142">Font Cache サービスの構成による起動時間の短縮</span><span class="sxs-lookup"><span data-stu-id="c11b7-142">Configure Font Cache Service to Reduce Start-up Time</span></span>  
 <span data-ttu-id="c11b7-143">WPF フォント キャッシュ サービスは、WPF アプリケーション間でフォント データを共有します。</span><span class="sxs-lookup"><span data-stu-id="c11b7-143">The WPF Font Cache service shares font data between WPF applications.</span></span> <span data-ttu-id="c11b7-144">最初に実行する WPF アプリケーションは、サービスがまだ実行されていない場合に、このサービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="c11b7-144">The first WPF application you run starts this service if the service is not already running.</span></span> <span data-ttu-id="c11b7-145">Windows Vista を使用している場合は、"Windows プレゼンテーション基盤 (WPF) フォント キャッシュ 3.0.0.0" サービスを "手動" (既定) から "自動 (遅延開始)" に設定して、WPF アプリケーションの初期起動時間を短縮できます。</span><span class="sxs-lookup"><span data-stu-id="c11b7-145">If you are using Windows Vista, you can set the "Windows Presentation Foundation (WPF) Font Cache 3.0.0.0" service from "Manual" (the default) to "Automatic (Delayed Start)" to reduce the initial start-up time of WPF applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c11b7-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="c11b7-146">See also</span></span>

- [<span data-ttu-id="c11b7-147">アプリケーション パフォーマンスの計画</span><span class="sxs-lookup"><span data-stu-id="c11b7-147">Planning for Application Performance</span></span>](planning-for-application-performance.md)
- [<span data-ttu-id="c11b7-148">ハードウェアの活用</span><span class="sxs-lookup"><span data-stu-id="c11b7-148">Taking Advantage of Hardware</span></span>](optimizing-performance-taking-advantage-of-hardware.md)
- [<span data-ttu-id="c11b7-149">レイアウトとデザイン</span><span class="sxs-lookup"><span data-stu-id="c11b7-149">Layout and Design</span></span>](optimizing-performance-layout-and-design.md)
- [<span data-ttu-id="c11b7-150">2D グラフィックスとイメージング</span><span class="sxs-lookup"><span data-stu-id="c11b7-150">2D Graphics and Imaging</span></span>](optimizing-performance-2d-graphics-and-imaging.md)
- [<span data-ttu-id="c11b7-151">オブジェクトの動作</span><span class="sxs-lookup"><span data-stu-id="c11b7-151">Object Behavior</span></span>](optimizing-performance-object-behavior.md)
- [<span data-ttu-id="c11b7-152">アプリケーション リソース</span><span class="sxs-lookup"><span data-stu-id="c11b7-152">Application Resources</span></span>](optimizing-performance-application-resources.md)
- [<span data-ttu-id="c11b7-153">テキスト</span><span class="sxs-lookup"><span data-stu-id="c11b7-153">Text</span></span>](optimizing-performance-text.md)
- [<span data-ttu-id="c11b7-154">データ バインディング</span><span class="sxs-lookup"><span data-stu-id="c11b7-154">Data Binding</span></span>](optimizing-performance-data-binding.md)
- [<span data-ttu-id="c11b7-155">アニメーションのヒントとテクニック</span><span class="sxs-lookup"><span data-stu-id="c11b7-155">Animation Tips and Tricks</span></span>](../graphics-multimedia/animation-tips-and-tricks.md)
