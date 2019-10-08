---
title: パフォーマンスの最適化:アプリケーション リソース
ms.date: 03/30/2017
helpviewer_keywords:
- application resources [WPF], performance
- resources [WPF], performance
- static resources [WPF]
- sharing resources [WPF]
- brushes [WPF], performance
- sharing brushes without copying [WPF]
ms.assetid: 62b88488-c08e-4804-b7de-a1c34fbe929c
ms.openlocfilehash: 759d02afe1934d2ace4ed226d5d911db2d676d98
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005042"
---
# <a name="optimizing-performance-application-resources"></a><span data-ttu-id="5a872-102">パフォーマンスの最適化:アプリケーション リソース</span><span class="sxs-lookup"><span data-stu-id="5a872-102">Optimizing Performance: Application Resources</span></span>
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="5a872-103">を使用すると、類似した型の要素全体で一貫した外観や動作をサポートできるように、アプリケーションリソースを共有できます。</span><span class="sxs-lookup"><span data-stu-id="5a872-103">allows you to share application resources so that you can support a consistent look or behavior across similar-typed elements.</span></span> <span data-ttu-id="5a872-104">このトピックでは、アプリケーションのパフォーマンスを向上させるために役立ついくつかの推奨事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a872-104">This topic provides a few recommendations in this area that can help you improve the performance of your applications.</span></span>  
  
 <span data-ttu-id="5a872-105">リソースについて詳しくは、「[XAML リソース](xaml-resources.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5a872-105">For more information on resources, see [XAML Resources](xaml-resources.md).</span></span>  
  
## <a name="sharing-resources"></a><span data-ttu-id="5a872-106">リソースの共有</span><span class="sxs-lookup"><span data-stu-id="5a872-106">Sharing resources</span></span>  
 <span data-ttu-id="5a872-107">アプリケーションでカスタムコントロールを使用して <xref:System.Windows.ResourceDictionary> (または XAML リソース) ノードでリソースを定義する場合は、リソースを <xref:System.Windows.Application> または @no__t 2 のオブジェクトレベルで定義するか、カスタムコントロールの既定のテーマで定義することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5a872-107">If your application uses custom controls and defines resources in a <xref:System.Windows.ResourceDictionary> (or XAML Resources node), it is recommended that you either define the resources at the <xref:System.Windows.Application> or <xref:System.Windows.Window> object level, or define them in the default theme for the custom controls.</span></span> <span data-ttu-id="5a872-108">カスタムコントロールの @no__t にリソースを定義すると、そのコントロールのすべてのインスタンスのパフォーマンスに影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="5a872-108">Defining resources in a custom control's <xref:System.Windows.ResourceDictionary> imposes a performance impact for every instance of that control.</span></span> <span data-ttu-id="5a872-109">たとえば、カスタムコントロールのリソース定義の一部として定義されているパフォーマンスを集中的に使用するブラシ操作と、カスタムコントロールの多くのインスタンスがある場合、アプリケーションのワーキングセットは大幅に増加します。</span><span class="sxs-lookup"><span data-stu-id="5a872-109">For example, if you have performance-intensive brush operations defined as part of the resource definition of a custom control and many instances of the custom control, the application's working set will increase significantly.</span></span>  
  
 <span data-ttu-id="5a872-110">この点を説明するために、次の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="5a872-110">To illustrate this point, consider the following.</span></span> <span data-ttu-id="5a872-111">たとえば、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] を使用してカードゲームを開発しているとします。</span><span class="sxs-lookup"><span data-stu-id="5a872-111">Let's say you are developing a card game using [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="5a872-112">ほとんどのカードゲームでは、52の異なる顔を持つ52カードが必要です。</span><span class="sxs-lookup"><span data-stu-id="5a872-112">For most card games, you need 52 cards with 52 different faces.</span></span> <span data-ttu-id="5a872-113">カードのカスタムコントロールを実装し、カードのカスタムコントロールのリソースに52のブラシ (それぞれカードの表面を表す) を定義します。</span><span class="sxs-lookup"><span data-stu-id="5a872-113">You decide to implement a card custom control and you define 52 brushes (each representing a card face) in the resources of your card custom control.</span></span> <span data-ttu-id="5a872-114">メインアプリケーションでは、最初にこのカードカスタムコントロールの52インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="5a872-114">In your main application, you initially create 52 instances of this card custom control.</span></span> <span data-ttu-id="5a872-115">カードのカスタムコントロールの各インスタンスは @no__t 0 オブジェクトの52インスタンスを生成します。これにより、アプリケーションで合計 52 \* 52 @no__t オブジェクトが得られます。</span><span class="sxs-lookup"><span data-stu-id="5a872-115">Each instance of the card custom control generates 52 instances of <xref:System.Windows.Media.Brush> objects, which gives you a total of 52 \* 52 <xref:System.Windows.Media.Brush> objects in your application.</span></span> <span data-ttu-id="5a872-116">ブラシをカードのカスタムコントロールリソースから @no__t 0 または <xref:System.Windows.Window> のオブジェクトレベルに移動したり、カスタムコントロールの既定のテーマで定義したりすることにより、52のブラシを52で共有するため、アプリケーションのワーキングセットを減らすことができます。カードコントロールのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="5a872-116">By moving the brushes out of the card custom control resources to the <xref:System.Windows.Application> or <xref:System.Windows.Window> object level, or defining them in the default theme for the custom control, you reduce the working set of the application, since you are now sharing the 52 brushes among 52 instances of the card control.</span></span>  
  
## <a name="sharing-a-brush-without-copying"></a><span data-ttu-id="5a872-117">コピーせずにブラシを共有する</span><span class="sxs-lookup"><span data-stu-id="5a872-117">Sharing a Brush without Copying</span></span>  
 <span data-ttu-id="5a872-118">同じ @no__t 0 オブジェクトを使用している複数の要素がある場合は、XAML でブラシをインラインで定義するのではなく、ブラシをリソースとして定義し、それを参照します。</span><span class="sxs-lookup"><span data-stu-id="5a872-118">If you have multiple elements using the same <xref:System.Windows.Media.Brush> object, define the brush as a resource and reference it, rather than defining the brush inline in XAML.</span></span> <span data-ttu-id="5a872-119">このメソッドは、1つのインスタンスを作成して再利用します。一方、XAML でブラシをインラインで定義すると、要素ごとに新しいインスタンスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="5a872-119">This method will create one instance and reuse it, whereas defining brushes inline in XAML creates a new instance for each element.</span></span>  
  
 <span data-ttu-id="5a872-120">次のマークアップサンプルは、この点を示しています。</span><span class="sxs-lookup"><span data-stu-id="5a872-120">The following markup sample illustrates this point:</span></span>  
  
 [!code-xaml[Performance#PerformanceSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/BrushResource.xaml#performancesnippet7)]  
  
## <a name="use-static-resources-when-possible"></a><span data-ttu-id="5a872-121">可能な場合は静的リソースを使用する</span><span class="sxs-lookup"><span data-stu-id="5a872-121">Use Static Resources when Possible</span></span>  
 <span data-ttu-id="5a872-122">静的リソースは、既に定義されているリソースへの参照を検索することによって、任意の XAML プロパティ属性の値を提供します。</span><span class="sxs-lookup"><span data-stu-id="5a872-122">A static resource provides a value for any XAML property attribute by looking up a reference to an already defined resource.</span></span> <span data-ttu-id="5a872-123">このリソースの参照動作は、コンパイル時の参照に似ています。</span><span class="sxs-lookup"><span data-stu-id="5a872-123">Lookup behavior for that resource is analogous to compile-time lookup.</span></span>  
  
 <span data-ttu-id="5a872-124">一方、動的リソースでは、初期コンパイル中に一時式が作成されます。そのため、オブジェクトを構築するために要求されたリソース値が実際に必要になるまで、リソースの参照を延期します。</span><span class="sxs-lookup"><span data-stu-id="5a872-124">A dynamic resource, on the other hand, will create a temporary expression during the initial compilation and thus defer lookup for resources until the requested resource value is actually required in order to construct an object.</span></span> <span data-ttu-id="5a872-125">そのリソースの参照動作は、実行時の検索に似ており、パフォーマンスに影響します。</span><span class="sxs-lookup"><span data-stu-id="5a872-125">Lookup behavior for that resource is analogous to run-time lookup, which imposes a performance impact.</span></span> <span data-ttu-id="5a872-126">必要な場合にのみ動的リソースを使用して、アプリケーションで可能な限り静的リソースを使用します。</span><span class="sxs-lookup"><span data-stu-id="5a872-126">Use static resources whenever possible in your application, using dynamic resources only when necessary.</span></span>  
  
 <span data-ttu-id="5a872-127">次のマークアップサンプルは、両方の種類のリソースの使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="5a872-127">The following markup sample shows the use of both types of resources:</span></span>  
  
 [!code-xaml[Performance#PerformanceSnippet8](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/DynamicResource.xaml#performancesnippet8)]  
  
## <a name="see-also"></a><span data-ttu-id="5a872-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a872-128">See also</span></span>

- [<span data-ttu-id="5a872-129">WPF アプリケーションのパフォーマンスの最適化</span><span class="sxs-lookup"><span data-stu-id="5a872-129">Optimizing WPF Application Performance</span></span>](optimizing-wpf-application-performance.md)
- [<span data-ttu-id="5a872-130">アプリケーション パフォーマンスの計画</span><span class="sxs-lookup"><span data-stu-id="5a872-130">Planning for Application Performance</span></span>](planning-for-application-performance.md)
- [<span data-ttu-id="5a872-131">ハードウェアの活用</span><span class="sxs-lookup"><span data-stu-id="5a872-131">Taking Advantage of Hardware</span></span>](optimizing-performance-taking-advantage-of-hardware.md)
- [<span data-ttu-id="5a872-132">レイアウトとデザイン</span><span class="sxs-lookup"><span data-stu-id="5a872-132">Layout and Design</span></span>](optimizing-performance-layout-and-design.md)
- [<span data-ttu-id="5a872-133">2D グラフィックスとイメージング</span><span class="sxs-lookup"><span data-stu-id="5a872-133">2D Graphics and Imaging</span></span>](optimizing-performance-2d-graphics-and-imaging.md)
- [<span data-ttu-id="5a872-134">オブジェクトの動作</span><span class="sxs-lookup"><span data-stu-id="5a872-134">Object Behavior</span></span>](optimizing-performance-object-behavior.md)
- [<span data-ttu-id="5a872-135">Text</span><span class="sxs-lookup"><span data-stu-id="5a872-135">Text</span></span>](optimizing-performance-text.md)
- [<span data-ttu-id="5a872-136">データ バインディング</span><span class="sxs-lookup"><span data-stu-id="5a872-136">Data Binding</span></span>](optimizing-performance-data-binding.md)
- [<span data-ttu-id="5a872-137">パフォーマンスに関するその他の推奨事項</span><span class="sxs-lookup"><span data-stu-id="5a872-137">Other Performance Recommendations</span></span>](optimizing-performance-other-recommendations.md)
