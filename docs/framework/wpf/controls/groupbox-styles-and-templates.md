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
ms.openlocfilehash: 0835c106ffbda86bca8e01bc61adebfc1ab0c2cb
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459644"
---
# <a name="groupbox-styles-and-templates"></a><span data-ttu-id="6c7f4-102">GroupBox のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="6c7f4-102">GroupBox Styles and Templates</span></span>
<a name="introduction"></a><span data-ttu-id="6c7f4-103">このトピックでは、<xref:System.Windows.Controls.GroupBox> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6c7f4-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.GroupBox> control.</span></span> <span data-ttu-id="6c7f4-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="6c7f4-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="6c7f4-105">詳細については、「[Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c7f4-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
<a name="groupbox_parts"></a>   
## <a name="groupbox-parts"></a><span data-ttu-id="6c7f4-106">GroupBox パーツ</span><span class="sxs-lookup"><span data-stu-id="6c7f4-106">GroupBox Parts</span></span>  
 <span data-ttu-id="6c7f4-107"><xref:System.Windows.Controls.GroupBox> コントロールには、名前付きの部分がありません。</span><span class="sxs-lookup"><span data-stu-id="6c7f4-107">The <xref:System.Windows.Controls.GroupBox> control does not have any named parts.</span></span>  
  
<a name="groupbox_states"></a>   
## <a name="groupbox-states"></a><span data-ttu-id="6c7f4-108">GroupBox の状態</span><span class="sxs-lookup"><span data-stu-id="6c7f4-108">GroupBox States</span></span>  
 <span data-ttu-id="6c7f4-109">次の表は、<xref:System.Windows.Controls.GroupBox> コントロールの表示状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="6c7f4-109">The following table lists the visual states for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
|<span data-ttu-id="6c7f4-110">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="6c7f4-110">VisualState Name</span></span>|<span data-ttu-id="6c7f4-111">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="6c7f4-111">VisualStateGroup Name</span></span>|<span data-ttu-id="6c7f4-112">説明</span><span class="sxs-lookup"><span data-stu-id="6c7f4-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="6c7f4-113">有効</span><span class="sxs-lookup"><span data-stu-id="6c7f4-113">Valid</span></span>|<span data-ttu-id="6c7f4-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6c7f4-114">ValidationStates</span></span>|<span data-ttu-id="6c7f4-115">コントロールは <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false`ます。</span><span class="sxs-lookup"><span data-stu-id="6c7f4-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="6c7f4-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="6c7f4-116">InvalidFocused</span></span>|<span data-ttu-id="6c7f4-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6c7f4-117">ValidationStates</span></span>|<span data-ttu-id="6c7f4-118"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがある `true` です。</span><span class="sxs-lookup"><span data-stu-id="6c7f4-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="6c7f4-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="6c7f4-119">InvalidUnfocused</span></span>|<span data-ttu-id="6c7f4-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6c7f4-120">ValidationStates</span></span>|<span data-ttu-id="6c7f4-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがない `true` です。</span><span class="sxs-lookup"><span data-stu-id="6c7f4-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
<a name="groupbox_controltemplate_example"></a>   
## <a name="groupbox-controltemplate-example"></a><span data-ttu-id="6c7f4-122">GroupBox ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="6c7f4-122">GroupBox ControlTemplate Example</span></span>  
 <span data-ttu-id="6c7f4-123">次の例は、<xref:System.Windows.Controls.GroupBox> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="6c7f4-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#GroupBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/groupbox.xaml#groupbox)]  
  
 <span data-ttu-id="6c7f4-124"><xref:System.Windows.Controls.ControlTemplate> では、次のリソースの1つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="6c7f4-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="6c7f4-125">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c7f4-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c7f4-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="6c7f4-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="6c7f4-127">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="6c7f4-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="6c7f4-128">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="6c7f4-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="6c7f4-129">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="6c7f4-129">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="6c7f4-130">ControlTemplate の作成による既存のコントロールの外観のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="6c7f4-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
