---
title: ToolTip のスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], ToolTip
- styles [WPF], ToolTip
- states [WPF], ToolTip
- ToolTip [WPF], styles and templates
- ControlTemplate [WPF], ToolTip
- templates [WPF], ToolTip
ms.assetid: 405fe385-4de9-49ee-a448-d8f4d1f740dd
ms.openlocfilehash: c7a14034d665c124d01e8a4b43c5d42968241925
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283647"
---
# <a name="tooltip-styles-and-templates"></a><span data-ttu-id="929a0-102">ToolTip のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="929a0-102">ToolTip Styles and Templates</span></span>
<span data-ttu-id="929a0-103">このトピックでは、<xref:System.Windows.Controls.ToolTip> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="929a0-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ToolTip> control.</span></span> <span data-ttu-id="929a0-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="929a0-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="929a0-105">詳細については、「[コントロールのためにテンプレートを作成する](../../../desktop-wpf/themes/how-to-create-apply-template.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="929a0-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="tooltip-parts"></a><span data-ttu-id="929a0-106">ToolTip のパーツ</span><span class="sxs-lookup"><span data-stu-id="929a0-106">ToolTip Parts</span></span>  
 <span data-ttu-id="929a0-107"><xref:System.Windows.Controls.ToolTip> コントロールに名前付きパーツはありません。</span><span class="sxs-lookup"><span data-stu-id="929a0-107">The <xref:System.Windows.Controls.ToolTip> control does not have any named parts.</span></span>  
  
## <a name="tooltip-states"></a><span data-ttu-id="929a0-108">ToolTip の状態</span><span class="sxs-lookup"><span data-stu-id="929a0-108">ToolTip States</span></span>  
 <span data-ttu-id="929a0-109">次の表は、<xref:System.Windows.Controls.ToolTip> コントロールの表示状態の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="929a0-109">The following table lists the visual states for the <xref:System.Windows.Controls.ToolTip> control.</span></span>  
  
|<span data-ttu-id="929a0-110">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="929a0-110">VisualState Name</span></span>|<span data-ttu-id="929a0-111">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="929a0-111">VisualStateGroup Name</span></span>|<span data-ttu-id="929a0-112">説明</span><span class="sxs-lookup"><span data-stu-id="929a0-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="929a0-113">Closed</span><span class="sxs-lookup"><span data-stu-id="929a0-113">Closed</span></span>|<span data-ttu-id="929a0-114">OpenStates</span><span class="sxs-lookup"><span data-stu-id="929a0-114">OpenStates</span></span>|<span data-ttu-id="929a0-115">既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="929a0-115">The default state.</span></span>|  
|<span data-ttu-id="929a0-116">開く</span><span class="sxs-lookup"><span data-stu-id="929a0-116">Open</span></span>|<span data-ttu-id="929a0-117">OpenStates</span><span class="sxs-lookup"><span data-stu-id="929a0-117">OpenStates</span></span>|<span data-ttu-id="929a0-118"><xref:System.Windows.Controls.ToolTip> が表示されています。</span><span class="sxs-lookup"><span data-stu-id="929a0-118">The <xref:System.Windows.Controls.ToolTip> is visible.</span></span>|  
|<span data-ttu-id="929a0-119">有効</span><span class="sxs-lookup"><span data-stu-id="929a0-119">Valid</span></span>|<span data-ttu-id="929a0-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="929a0-120">ValidationStates</span></span>|<span data-ttu-id="929a0-121">このコントロールで <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false` です。</span><span class="sxs-lookup"><span data-stu-id="929a0-121">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="929a0-122">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="929a0-122">InvalidFocused</span></span>|<span data-ttu-id="929a0-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="929a0-123">ValidationStates</span></span>|<span data-ttu-id="929a0-124"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがある `true` です。</span><span class="sxs-lookup"><span data-stu-id="929a0-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="929a0-125">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="929a0-125">InvalidUnfocused</span></span>|<span data-ttu-id="929a0-126">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="929a0-126">ValidationStates</span></span>|<span data-ttu-id="929a0-127"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがない `true` です。</span><span class="sxs-lookup"><span data-stu-id="929a0-127">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="tooltip-controltemplate-example"></a><span data-ttu-id="929a0-128">ToolTip の ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="929a0-128">ToolTip ControlTemplate Example</span></span>  
 <span data-ttu-id="929a0-129">次の例は、<xref:System.Windows.Controls.ToolTip> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="929a0-129">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ToolTip> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/tooltip.xaml#tooltip)]  
  
 <span data-ttu-id="929a0-130">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="929a0-130">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="929a0-131">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="929a0-131">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="929a0-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="929a0-132">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="929a0-133">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="929a0-133">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="929a0-134">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="929a0-134">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="929a0-135">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="929a0-135">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="929a0-136">コントロールのためのテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="929a0-136">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
