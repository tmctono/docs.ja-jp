---
title: ToolTip の概要
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolTip control [WPF], about ToolTip control
- controls [WPF], ToolTip
ms.assetid: f06c1603-e9cb-4809-8a62-234607fc52f7
ms.openlocfilehash: 0fec31b28a21c2e17986210c852b3d630087842d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181946"
---
# <a name="tooltip-overview"></a><span data-ttu-id="94560-102">ToolTip の概要</span><span class="sxs-lookup"><span data-stu-id="94560-102">ToolTip Overview</span></span>
<span data-ttu-id="94560-103">ツールヒントは、ユーザーが <xref:System.Windows.Controls.Button> などの要素の上にマウス ポインターを置いたときに表示される小さなポップアップ ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="94560-103">A tooltip is a small pop-up window that appears when a user pauses the mouse pointer over an element, such as over a <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="94560-104">このトピックでは、ツールヒントを紹介し、ツールヒントの内容を作成およびカスタマイズする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="94560-104">This topic introduces the tooltip and discusses how to create and customize tooltip content.</span></span>  

<a name="what_is_a_tooltip"></a>
## <a name="what-is-a-tooltip"></a><span data-ttu-id="94560-105">ツールヒントとは</span><span class="sxs-lookup"><span data-stu-id="94560-105">What Is a Tooltip?</span></span>  
 <span data-ttu-id="94560-106">ツールヒントを持つ要素の上にマウス ポインターを置くと、一定の時間、ツールヒントの内容 (たとえば、コントロールの機能を説明するテキスト コンテンツ) を含むウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="94560-106">When a user moves the mouse pointer over an element that has a tooltip, a window that contains tooltip content (for example, text content that describes the function of a control) appears for a specified amount of time.</span></span> <span data-ttu-id="94560-107">コントロールからマウス ポインターを移動すると、ツールヒントの内容がフォーカスを受け取ることができなくなるため、ウィンドウが消えます</span><span class="sxs-lookup"><span data-stu-id="94560-107">If the user moves the mouse pointer away from the control, the window disappears because the tooltip content cannot receive focus.</span></span>  
  
 <span data-ttu-id="94560-108">ツールヒントの内容は、1 行または複数行のテキスト、イメージ、図形などのビジュアル コンテンツを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="94560-108">The content of a tooltip can contain one or more lines of text, images, shapes, or other visual content.</span></span> <span data-ttu-id="94560-109">次のプロパティの 1 つをツールヒントの内容に設定することによって、コントロールのツールヒントを定義します。</span><span class="sxs-lookup"><span data-stu-id="94560-109">You define a tooltip for a control by setting one of the following properties to the tooltip content.</span></span>  
  
- <xref:System.Windows.FrameworkContentElement.ToolTip%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="94560-110">どのプロパティを使用するかは、ツールヒントを定義するコントロールが <xref:System.Windows.FrameworkContentElement> または <xref:System.Windows.FrameworkElement> のどちらのクラスを継承しているかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="94560-110">Which property you use depends on whether the control that defines the tooltip inherits from the <xref:System.Windows.FrameworkContentElement> or <xref:System.Windows.FrameworkElement> class.</span></span>  
  
<a name="create_tooltip"></a>
## <a name="creating-a-tooltip"></a><span data-ttu-id="94560-111">ツールヒントの作成</span><span class="sxs-lookup"><span data-stu-id="94560-111">Creating a ToolTip</span></span>  
 <span data-ttu-id="94560-112">次の例では、<xref:System.Windows.Controls.Button> コントロールの <xref:System.Windows.FrameworkElement.ToolTip%2A> プロパティにテキスト文字列を設定することにより、簡単なツールヒントを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="94560-112">The following example shows how to create a simple tooltip by setting the <xref:System.Windows.FrameworkElement.ToolTip%2A> property for a <xref:System.Windows.Controls.Button> control to a text string.</span></span>  
  
 [!code-xaml[GroupBoxSnippet#ToolTipString](~/samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#tooltipstring)]  
  
 <span data-ttu-id="94560-113">また、ツールヒントを <xref:System.Windows.Controls.ToolTip> オブジェクトとして定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="94560-113">You can also define a tooltip as a <xref:System.Windows.Controls.ToolTip> object.</span></span> <span data-ttu-id="94560-114">次の例では、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] を使用して、<xref:System.Windows.Controls.TextBox> 要素のツールヒントとして <xref:System.Windows.Controls.ToolTip> オブジェクトを指定しています。</span><span class="sxs-lookup"><span data-stu-id="94560-114">The following example uses [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] to specify a <xref:System.Windows.Controls.ToolTip> object as the tooltip of a <xref:System.Windows.Controls.TextBox> element.</span></span> <span data-ttu-id="94560-115">この例では、<xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=nameWithType> プロパティを設定することにより <xref:System.Windows.Controls.ToolTip> を指定していることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="94560-115">Note that the example specifies the <xref:System.Windows.Controls.ToolTip> by setting the <xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=nameWithType> property.</span></span>  
  
 [!code-xaml[ToolTipSimple#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml#tooltip)]  
  
 <span data-ttu-id="94560-116">次の例では、コードを使用して <xref:System.Windows.Controls.ToolTip> オブジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="94560-116">The following example uses code to generate a <xref:System.Windows.Controls.ToolTip> object.</span></span> <span data-ttu-id="94560-117">この例では、<xref:System.Windows.Controls.ToolTip> (`tt`) を作成し、それを <xref:System.Windows.Controls.Button> に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="94560-117">The example creates a <xref:System.Windows.Controls.ToolTip> (`tt`) and associates it with a <xref:System.Windows.Controls.Button>.</span></span>  
  
 [!code-csharp[ToolTipSimple#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ToolTipSimple#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipSimple/VisualBasic/Window1.xaml.vb#2)]  
  
 <span data-ttu-id="94560-118"><xref:System.Windows.Controls.DockPanel> などのレイアウト要素でツールヒントの内容を囲むことにより、<xref:System.Windows.Controls.ToolTip> オブジェクトとして定義されていないツールヒントの内容を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="94560-118">You can also create tooltip content that is not defined as a <xref:System.Windows.Controls.ToolTip> object by enclosing the tooltip content in a layout element, such as a <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="94560-119">次の例では、<xref:System.Windows.Controls.DockPanel> コントロールで囲まれたコンテンツを、<xref:System.Windows.Controls.TextBox> の <xref:System.Windows.FrameworkElement.ToolTip%2A> プロパティに設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="94560-119">The following example shows how to set the <xref:System.Windows.FrameworkElement.ToolTip%2A> property of a <xref:System.Windows.Controls.TextBox> to content that is enclosed in a <xref:System.Windows.Controls.DockPanel> control.</span></span>  
  
 [!code-xaml[GroupBoxSnippet#ToolTipDockPanel](~/samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#tooltipdockpanel)]  
  
<a name="Using_the_ToolTip_and_ToolTipService_Properties"></a>
## <a name="using-the-properties-of-the-tooltip-and-tooltipservice-classes"></a><span data-ttu-id="94560-120">ToolTip クラスおよび ToolTipService クラスのプロパティの使用</span><span class="sxs-lookup"><span data-stu-id="94560-120">Using the Properties of the ToolTip and ToolTipService Classes</span></span>  
 <span data-ttu-id="94560-121">ビジュアル プロパティを設定し、スタイルを適用して、ツールヒントの内容をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="94560-121">You can customize tooltip content by setting visual properties and applying styles.</span></span> <span data-ttu-id="94560-122">ツールヒントの内容を <xref:System.Windows.Controls.ToolTip> オブジェクトとして定義した場合は、<xref:System.Windows.Controls.ToolTip> オブジェクトのビジュアル プロパティを設定できます。</span><span class="sxs-lookup"><span data-stu-id="94560-122">If you define the tooltip content as a <xref:System.Windows.Controls.ToolTip> object, you can set the visual properties of the <xref:System.Windows.Controls.ToolTip> object.</span></span> <span data-ttu-id="94560-123">それ以外の場合は、<xref:System.Windows.Controls.ToolTipService> クラスで同等の添付プロパティを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94560-123">Otherwise, you must set equivalent attached properties on the <xref:System.Windows.Controls.ToolTipService> class.</span></span>  
  
 <span data-ttu-id="94560-124">ツールヒントの内容の位置を指定するために、<xref:System.Windows.Controls.ToolTip> および <xref:System.Windows.Controls.ToolTipService> プロパティを設定する方法の例については、「[ToolTip を配置する](how-to-position-a-tooltip.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94560-124">For an example of how to set properties in order to specify the position of tooltip content by using the <xref:System.Windows.Controls.ToolTip> and <xref:System.Windows.Controls.ToolTipService> properties, see [Position a ToolTip](how-to-position-a-tooltip.md).</span></span>  
  
<a name="StylingToolTip"></a>
## <a name="styling-a-tooltip"></a><span data-ttu-id="94560-125">ツールヒントのスタイル設定</span><span class="sxs-lookup"><span data-stu-id="94560-125">Styling a ToolTip</span></span>  
 <span data-ttu-id="94560-126">カスタム <xref:System.Windows.Style> を定義することで、<xref:System.Windows.Controls.ToolTip> のスタイルを設定できます。</span><span class="sxs-lookup"><span data-stu-id="94560-126">You can style a <xref:System.Windows.Controls.ToolTip> by defining a custom <xref:System.Windows.Style>.</span></span> <span data-ttu-id="94560-127">次の例では、<xref:System.Windows.Controls.Control.Background%2A>、<xref:System.Windows.Controls.Control.Foreground%2A>、<xref:System.Windows.Controls.Control.FontSize%2A>、<xref:System.Windows.Controls.Control.FontWeight%2A> を設定することによって、<xref:System.Windows.Controls.ToolTip> の配置をオフセットし、その外観を変更する方法を示す、`Simple` という名前の <xref:System.Windows.Style> を定義します。</span><span class="sxs-lookup"><span data-stu-id="94560-127">The following example defines a <xref:System.Windows.Style> called `Simple` that shows how to offset the placement of the <xref:System.Windows.Controls.ToolTip> and change its appearance by setting the <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>, <xref:System.Windows.Controls.Control.FontSize%2A>, and <xref:System.Windows.Controls.Control.FontWeight%2A>.</span></span>  
  
 [!code-xaml[ToolTipSimple#Style](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml#style)]  
  
<a name="UsingtheToolTipServiceTimeIntervalProperties"></a>
## <a name="using-the-time-interval-properties-of-tooltipservice"></a><span data-ttu-id="94560-128">ToolTipService の時間間隔プロパティの使用</span><span class="sxs-lookup"><span data-stu-id="94560-128">Using the Time Interval Properties of ToolTipService</span></span>  
 <span data-ttu-id="94560-129"><xref:System.Windows.Controls.ToolTipService> クラスでは、ツールヒントの表示時間を設定するために、<xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A>、<xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A>、<xref:System.Windows.Controls.ToolTipService.ShowDuration%2A> プロパティが提供されています。</span><span class="sxs-lookup"><span data-stu-id="94560-129">The <xref:System.Windows.Controls.ToolTipService> class provides the following properties for you to set tooltip display times: <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A>, <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A>, and <xref:System.Windows.Controls.ToolTipService.ShowDuration%2A>.</span></span>  
  
 <span data-ttu-id="94560-130"><xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> プロパティと <xref:System.Windows.Controls.ToolTipService.ShowDuration%2A> プロパティを使用して、<xref:System.Windows.Controls.ToolTip> が表示される前の遅延 (通常は短い時間) を指定します。また、<xref:System.Windows.Controls.ToolTip> を表示し続ける時間も指定できます。</span><span class="sxs-lookup"><span data-stu-id="94560-130">Use the <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> and <xref:System.Windows.Controls.ToolTipService.ShowDuration%2A> properties to specify a delay, typically brief, before a <xref:System.Windows.Controls.ToolTip> appears and also to specify how long a <xref:System.Windows.Controls.ToolTip> remains visible.</span></span> <span data-ttu-id="94560-131">詳細については、[ツールヒントの表示を遅らせる方法](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms747264(v=vs.90))に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="94560-131">For more information, see [How to: Delay the Display of a ToolTip](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms747264(v=vs.90)).</span></span>  
  
 <span data-ttu-id="94560-132"><xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> プロパティでは、コントロール間でマウス ポインターをすばやく移動するときに、コントロールのツールヒントを初期遅延なしで表示するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="94560-132">The <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> property determines if tooltips for different controls appear without an initial delay when you move the mouse pointer quickly between them.</span></span> <span data-ttu-id="94560-133"><xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> プロパティの詳細については、「[BetweenShowDelay プロパティを使用する](how-to-use-the-betweenshowdelay-property.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94560-133">For more information about the <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> property, see [Use the BetweenShowDelay Property](how-to-use-the-betweenshowdelay-property.md).</span></span>  
  
 <span data-ttu-id="94560-134">次の例では、ツールヒントのこれらのプロパティを設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="94560-134">The following example shows how to set these properties for a tooltip.</span></span>  
  
 [!code-xaml[ToolTipService#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
## <a name="see-also"></a><span data-ttu-id="94560-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="94560-135">See also</span></span>

- <xref:System.Windows.Controls.ToolTipService>
- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipEventArgs>
- <xref:System.Windows.Controls.ToolTipEventHandler>
- [<span data-ttu-id="94560-136">方法トピック</span><span class="sxs-lookup"><span data-stu-id="94560-136">How-to Topics</span></span>](tooltip-how-to-topics.md)
