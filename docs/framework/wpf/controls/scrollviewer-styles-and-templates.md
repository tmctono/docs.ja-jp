---
title: ScrollViewer のスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], ScrollViewer
- states [WPF], ScrollViewer
- styles [WPF], ScrollViewer
- templates [WPF], ScrollViewer
- ControlTemplate [WPF], ScrollViewer
- ScrollViewer [WPF], styles and templates
ms.assetid: dffdd822-ae69-4946-abaf-710860cd65b2
ms.openlocfilehash: b54dcacf55a750d7c1253db20147d18de47d027e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283405"
---
# <a name="scrollviewer-styles-and-templates"></a><span data-ttu-id="e94e0-102">ScrollViewer のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="e94e0-102">ScrollViewer Styles and Templates</span></span>
<span data-ttu-id="e94e0-103">このトピックでは、<xref:System.Windows.Controls.ScrollViewer> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e94e0-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span> <span data-ttu-id="e94e0-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="e94e0-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="e94e0-105">詳細については、「[コントロールのためにテンプレートを作成する](../../../desktop-wpf/themes/how-to-create-apply-template.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e94e0-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="scrollviewer-parts"></a><span data-ttu-id="e94e0-106">ScrollViewer のパーツ</span><span class="sxs-lookup"><span data-stu-id="e94e0-106">ScrollViewer Parts</span></span>  
 <span data-ttu-id="e94e0-107">次の表は、<xref:System.Windows.Controls.ScrollViewer> コントロールの名前付きパーツの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="e94e0-107">The following table lists the named parts for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="e94e0-108">パーツ</span><span class="sxs-lookup"><span data-stu-id="e94e0-108">Part</span></span>|<span data-ttu-id="e94e0-109">種類</span><span class="sxs-lookup"><span data-stu-id="e94e0-109">Type</span></span>|<span data-ttu-id="e94e0-110">説明</span><span class="sxs-lookup"><span data-stu-id="e94e0-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="e94e0-111">PART_ScrollContentPresenter</span><span class="sxs-lookup"><span data-stu-id="e94e0-111">PART_ScrollContentPresenter</span></span>|<xref:System.Windows.Controls.ScrollContentPresenter>|<span data-ttu-id="e94e0-112"><xref:System.Windows.Controls.ScrollViewer> のコンテンツのプレースホルダー。</span><span class="sxs-lookup"><span data-stu-id="e94e0-112">The placeholder for content in the <xref:System.Windows.Controls.ScrollViewer>.</span></span>|  
|<span data-ttu-id="e94e0-113">PART_HorizontalScrollBar</span><span class="sxs-lookup"><span data-stu-id="e94e0-113">PART_HorizontalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="e94e0-114">コンテンツを水平方向にスクロールするために使用する <xref:System.Windows.Controls.Primitives.ScrollBar>。</span><span class="sxs-lookup"><span data-stu-id="e94e0-114">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content horizontally.</span></span>|  
|<span data-ttu-id="e94e0-115">PART_VerticalScrollBar</span><span class="sxs-lookup"><span data-stu-id="e94e0-115">PART_VerticalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="e94e0-116">コンテンツを垂直方向にスクロールするために使用する <xref:System.Windows.Controls.Primitives.ScrollBar>。</span><span class="sxs-lookup"><span data-stu-id="e94e0-116">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content vertically.</span></span>|  
  
## <a name="scrollviewer-states"></a><span data-ttu-id="e94e0-117">ScrollViewer の状態</span><span class="sxs-lookup"><span data-stu-id="e94e0-117">ScrollViewer States</span></span>  
 <span data-ttu-id="e94e0-118">次の表は、<xref:System.Windows.Controls.ScrollViewer> コントロールの表示状態の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="e94e0-118">The following table lists the visual states for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="e94e0-119">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="e94e0-119">VisualState Name</span></span>|<span data-ttu-id="e94e0-120">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="e94e0-120">VisualStateGroup Name</span></span>|<span data-ttu-id="e94e0-121">説明</span><span class="sxs-lookup"><span data-stu-id="e94e0-121">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="e94e0-122">有効</span><span class="sxs-lookup"><span data-stu-id="e94e0-122">Valid</span></span>|<span data-ttu-id="e94e0-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e94e0-123">ValidationStates</span></span>|<span data-ttu-id="e94e0-124">このコントロールで <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false` です。</span><span class="sxs-lookup"><span data-stu-id="e94e0-124">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="e94e0-125">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="e94e0-125">InvalidFocused</span></span>|<span data-ttu-id="e94e0-126">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e94e0-126">ValidationStates</span></span>|<span data-ttu-id="e94e0-127"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがある `true` です。</span><span class="sxs-lookup"><span data-stu-id="e94e0-127">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="e94e0-128">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="e94e0-128">InvalidUnfocused</span></span>|<span data-ttu-id="e94e0-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e94e0-129">ValidationStates</span></span>|<span data-ttu-id="e94e0-130"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがない `true` です。</span><span class="sxs-lookup"><span data-stu-id="e94e0-130">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="scrollviewer-controltemplate-example"></a><span data-ttu-id="e94e0-131">ScrollViewer の ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="e94e0-131">ScrollViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="e94e0-132">次の例は、<xref:System.Windows.Controls.ScrollViewer> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e94e0-132">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollviewer.xaml#scrollviewer)]  
  
 <span data-ttu-id="e94e0-133">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="e94e0-133">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="e94e0-134">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e94e0-134">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e94e0-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="e94e0-135">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="e94e0-136">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="e94e0-136">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="e94e0-137">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="e94e0-137">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="e94e0-138">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="e94e0-138">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="e94e0-139">コントロールのためのテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="e94e0-139">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
