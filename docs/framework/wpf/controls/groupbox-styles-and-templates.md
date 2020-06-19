---
title: GroupBox のスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], GroupBox
- parts [WPF], GroupBox
- GroupBox [WPF], styles and templates
- states [WPF], GroupBox
- styles [WPF], GroupBox
- templates [WPF], GroupBox
ms.assetid: 33df7037-0a1b-476f-b9d0-41566a777699
ms.openlocfilehash: 474cda0abc6a18c015836c749c78f4d33aa5abd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187477"
---
# <a name="groupbox-styles-and-templates"></a><span data-ttu-id="fc05c-102">GroupBox のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="fc05c-102">GroupBox Styles and Templates</span></span>
<a name="introduction"></a> <span data-ttu-id="fc05c-103">このトピックでは、<xref:System.Windows.Controls.GroupBox> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="fc05c-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.GroupBox> control.</span></span> <span data-ttu-id="fc05c-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="fc05c-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="fc05c-105">詳細については、「[コントロールのためにテンプレートを作成する](../../../desktop-wpf/themes/how-to-create-apply-template.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fc05c-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
<a name="groupbox_parts"></a>
## <a name="groupbox-parts"></a><span data-ttu-id="fc05c-106">GroupBox のパーツ</span><span class="sxs-lookup"><span data-stu-id="fc05c-106">GroupBox Parts</span></span>  
 <span data-ttu-id="fc05c-107"><xref:System.Windows.Controls.GroupBox> コントロールに名前付きパーツはありません。</span><span class="sxs-lookup"><span data-stu-id="fc05c-107">The <xref:System.Windows.Controls.GroupBox> control does not have any named parts.</span></span>  
  
<a name="groupbox_states"></a>
## <a name="groupbox-states"></a><span data-ttu-id="fc05c-108">GroupBox の状態</span><span class="sxs-lookup"><span data-stu-id="fc05c-108">GroupBox States</span></span>  
 <span data-ttu-id="fc05c-109">次の表は、<xref:System.Windows.Controls.GroupBox> コントロールの表示状態の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="fc05c-109">The following table lists the visual states for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
|<span data-ttu-id="fc05c-110">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="fc05c-110">VisualState Name</span></span>|<span data-ttu-id="fc05c-111">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="fc05c-111">VisualStateGroup Name</span></span>|<span data-ttu-id="fc05c-112">説明</span><span class="sxs-lookup"><span data-stu-id="fc05c-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="fc05c-113">有効</span><span class="sxs-lookup"><span data-stu-id="fc05c-113">Valid</span></span>|<span data-ttu-id="fc05c-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fc05c-114">ValidationStates</span></span>|<span data-ttu-id="fc05c-115">コントロールでは <xref:System.Windows.Controls.Validation> クラスが使用されていて、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false` です。</span><span class="sxs-lookup"><span data-stu-id="fc05c-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="fc05c-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="fc05c-116">InvalidFocused</span></span>|<span data-ttu-id="fc05c-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fc05c-117">ValidationStates</span></span>|<span data-ttu-id="fc05c-118"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `true` で、コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="fc05c-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="fc05c-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="fc05c-119">InvalidUnfocused</span></span>|<span data-ttu-id="fc05c-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fc05c-120">ValidationStates</span></span>|<span data-ttu-id="fc05c-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `true` で、コントロールにフォーカスはありません。</span><span class="sxs-lookup"><span data-stu-id="fc05c-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
<a name="groupbox_controltemplate_example"></a>
## <a name="groupbox-controltemplate-example"></a><span data-ttu-id="fc05c-122">GroupBox の ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="fc05c-122">GroupBox ControlTemplate Example</span></span>  
 <span data-ttu-id="fc05c-123">次の例は、<xref:System.Windows.Controls.GroupBox> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="fc05c-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#GroupBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/groupbox.xaml#groupbox)]  
  
 <span data-ttu-id="fc05c-124"><xref:System.Windows.Controls.ControlTemplate> では、次のリソースを 1 つ以上使用します。</span><span class="sxs-lookup"><span data-stu-id="fc05c-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="fc05c-125">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc05c-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc05c-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="fc05c-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="fc05c-127">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="fc05c-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="fc05c-128">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="fc05c-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="fc05c-129">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="fc05c-129">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="fc05c-130">コントロールのためのテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="fc05c-130">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
