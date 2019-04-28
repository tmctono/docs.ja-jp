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
ms.openlocfilehash: 24def466509c12eb69307de139e83dd5a1ed5ce4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790677"
---
# <a name="tooltip-styles-and-templates"></a><span data-ttu-id="f0376-102">ToolTip のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="f0376-102">ToolTip Styles and Templates</span></span>
<span data-ttu-id="f0376-103">このトピックでは、スタイルとテンプレートについて説明します、<xref:System.Windows.Controls.ToolTip>コントロール。</span><span class="sxs-lookup"><span data-stu-id="f0376-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ToolTip> control.</span></span> <span data-ttu-id="f0376-104">既定値を変更する<xref:System.Windows.Controls.ControlTemplate>固有の外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="f0376-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="f0376-105">詳細については、「[ControlTemplate の作成による既存のコントロールの外観のカスタマイズ](customizing-the-appearance-of-an-existing-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0376-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="tooltip-parts"></a><span data-ttu-id="f0376-106">ツールヒントの部品</span><span class="sxs-lookup"><span data-stu-id="f0376-106">ToolTip Parts</span></span>  
 <span data-ttu-id="f0376-107"><xref:System.Windows.Controls.ToolTip>コントロールには、名前付きパーツはありません。</span><span class="sxs-lookup"><span data-stu-id="f0376-107">The <xref:System.Windows.Controls.ToolTip> control does not have any named parts.</span></span>  
  
## <a name="tooltip-states"></a><span data-ttu-id="f0376-108">ツールヒントの状態</span><span class="sxs-lookup"><span data-stu-id="f0376-108">ToolTip States</span></span>  
 <span data-ttu-id="f0376-109">次の表のビジュアルの状態、<xref:System.Windows.Controls.ToolTip>コントロール。</span><span class="sxs-lookup"><span data-stu-id="f0376-109">The following table lists the visual states for the <xref:System.Windows.Controls.ToolTip> control.</span></span>  
  
|<span data-ttu-id="f0376-110">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="f0376-110">VisualState Name</span></span>|<span data-ttu-id="f0376-111">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="f0376-111">VisualStateGroup Name</span></span>|<span data-ttu-id="f0376-112">説明</span><span class="sxs-lookup"><span data-stu-id="f0376-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="f0376-113">Closed</span><span class="sxs-lookup"><span data-stu-id="f0376-113">Closed</span></span>|<span data-ttu-id="f0376-114">OpenStates</span><span class="sxs-lookup"><span data-stu-id="f0376-114">OpenStates</span></span>|<span data-ttu-id="f0376-115">既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="f0376-115">The default state.</span></span>|  
|<span data-ttu-id="f0376-116">開く</span><span class="sxs-lookup"><span data-stu-id="f0376-116">Open</span></span>|<span data-ttu-id="f0376-117">OpenStates</span><span class="sxs-lookup"><span data-stu-id="f0376-117">OpenStates</span></span>|<span data-ttu-id="f0376-118"><xref:System.Windows.Controls.ToolTip>を表示します。</span><span class="sxs-lookup"><span data-stu-id="f0376-118">The <xref:System.Windows.Controls.ToolTip> is visible.</span></span>|  
|<span data-ttu-id="f0376-119">有効</span><span class="sxs-lookup"><span data-stu-id="f0376-119">Valid</span></span>|<span data-ttu-id="f0376-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f0376-120">ValidationStates</span></span>|<span data-ttu-id="f0376-121">コントロールを使用して、<xref:System.Windows.Controls.Validation>クラスおよび<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`false`します。</span><span class="sxs-lookup"><span data-stu-id="f0376-121">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="f0376-122">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="f0376-122">InvalidFocused</span></span>|<span data-ttu-id="f0376-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f0376-123">ValidationStates</span></span>|<span data-ttu-id="f0376-124"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="f0376-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="f0376-125">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="f0376-125">InvalidUnfocused</span></span>|<span data-ttu-id="f0376-126">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f0376-126">ValidationStates</span></span>|<span data-ttu-id="f0376-127"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスがないです。</span><span class="sxs-lookup"><span data-stu-id="f0376-127">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="tooltip-controltemplate-example"></a><span data-ttu-id="f0376-128">ツールヒント ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="f0376-128">ToolTip ControlTemplate Example</span></span>  
 <span data-ttu-id="f0376-129">次の例は、定義する方法を示します、<xref:System.Windows.Controls.ControlTemplate>の<xref:System.Windows.Controls.ToolTip>コントロール。</span><span class="sxs-lookup"><span data-stu-id="f0376-129">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ToolTip> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/tooltip.xaml#tooltip)]  
  
 <span data-ttu-id="f0376-130">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="f0376-130">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="f0376-131">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0376-131">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0376-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="f0376-132">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="f0376-133">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="f0376-133">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="f0376-134">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="f0376-134">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="f0376-135">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="f0376-135">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="f0376-136">ControlTemplate の作成による既存のコントロールの外観のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="f0376-136">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
