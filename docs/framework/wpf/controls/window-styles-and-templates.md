---
title: ウィンドウのスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], Window
- templates [WPF], Window
- styles [WPF], Window
- ControlTemplate [WPF], Window
- Window [WPF], styles and templates
- states [WPF], Window
ms.assetid: 2dfdf025-347b-4342-bf28-95206c273f35
ms.openlocfilehash: 01233c5d0179e1a6f9bed651cd1f18058bfac168
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283612"
---
# <a name="window-styles-and-templates"></a><span data-ttu-id="e09ba-102">ウィンドウのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="e09ba-102">Window Styles and Templates</span></span>
<span data-ttu-id="e09ba-103">このトピックでは、<xref:System.Windows.Window> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e09ba-103">This topic describes the styles and templates for the <xref:System.Windows.Window> control.</span></span> <span data-ttu-id="e09ba-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="e09ba-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="e09ba-105">詳細については、「[コントロールのテンプレートを作成する](../../../desktop-wpf/themes/how-to-create-apply-template.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e09ba-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="window-parts"></a><span data-ttu-id="e09ba-106">ウィンドウ部分</span><span class="sxs-lookup"><span data-stu-id="e09ba-106">Window Parts</span></span>  
 <span data-ttu-id="e09ba-107"><xref:System.Windows.Window> コントロールには、名前付きの部分がありません。</span><span class="sxs-lookup"><span data-stu-id="e09ba-107">The <xref:System.Windows.Window> control does not have any named parts.</span></span>  
  
## <a name="window-states"></a><span data-ttu-id="e09ba-108">ウィンドウの状態</span><span class="sxs-lookup"><span data-stu-id="e09ba-108">Window States</span></span>  
 <span data-ttu-id="e09ba-109">次の表は、<xref:System.Windows.Window> コントロールの表示状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="e09ba-109">The following table lists the visual states for the <xref:System.Windows.Window> control.</span></span>  
  
|<span data-ttu-id="e09ba-110">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="e09ba-110">VisualState Name</span></span>|<span data-ttu-id="e09ba-111">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="e09ba-111">VisualStateGroup Name</span></span>|<span data-ttu-id="e09ba-112">[説明]</span><span class="sxs-lookup"><span data-stu-id="e09ba-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="e09ba-113">有効</span><span class="sxs-lookup"><span data-stu-id="e09ba-113">Valid</span></span>|<span data-ttu-id="e09ba-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e09ba-114">ValidationStates</span></span>|<span data-ttu-id="e09ba-115">コントロールは <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false`ます。</span><span class="sxs-lookup"><span data-stu-id="e09ba-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="e09ba-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="e09ba-116">InvalidFocused</span></span>|<span data-ttu-id="e09ba-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e09ba-117">ValidationStates</span></span>|<span data-ttu-id="e09ba-118"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがある `true` です。</span><span class="sxs-lookup"><span data-stu-id="e09ba-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="e09ba-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="e09ba-119">InvalidUnfocused</span></span>|<span data-ttu-id="e09ba-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e09ba-120">ValidationStates</span></span>|<span data-ttu-id="e09ba-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがない `true` です。</span><span class="sxs-lookup"><span data-stu-id="e09ba-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="window-controltemplate-example"></a><span data-ttu-id="e09ba-122">Window ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="e09ba-122">Window ControlTemplate Example</span></span>  
 <span data-ttu-id="e09ba-123">次の例は、<xref:System.Windows.Window> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e09ba-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Window> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Window](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/window.xaml#window)]  
  
 <span data-ttu-id="e09ba-124"><xref:System.Windows.Controls.ControlTemplate> では、次のリソースの1つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="e09ba-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="e09ba-125">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e09ba-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e09ba-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="e09ba-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="e09ba-127">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="e09ba-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="e09ba-128">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="e09ba-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="e09ba-129">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="e09ba-129">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="e09ba-130">コントロールのテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="e09ba-130">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
