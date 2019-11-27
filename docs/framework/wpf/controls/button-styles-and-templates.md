---
title: ボタンのスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], Button
- parts [WPF], Button
- styles [WPF], Button
- Button [WPF], styles and templates
- templates [WPF], Button
- ControlTemplate [WPF], Button
ms.assetid: e223c759-f8c4-4717-acfb-b1e40bdf5f3b
ms.openlocfilehash: ef9f85848ebdda9dc4ae15d0f54847eacd46e24d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283578"
---
# <a name="button-styles-and-templates"></a><span data-ttu-id="a5bf1-102">ボタンのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="a5bf1-102">Button Styles and Templates</span></span>
<span data-ttu-id="a5bf1-103">このトピックでは、<xref:System.Windows.Controls.Button> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="a5bf1-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="a5bf1-105">詳細については、「[コントロールのテンプレートを作成する](../../../desktop-wpf/themes/how-to-create-apply-template.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="button-parts"></a><span data-ttu-id="a5bf1-106">ボタン部分</span><span class="sxs-lookup"><span data-stu-id="a5bf1-106">Button Parts</span></span>  
 <span data-ttu-id="a5bf1-107"><xref:System.Windows.Controls.Button> コントロールには、名前付きの部分がありません。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-107">The <xref:System.Windows.Controls.Button> control does not have any named parts.</span></span>  
  
## <a name="button-states"></a><span data-ttu-id="a5bf1-108">ボタンの状態</span><span class="sxs-lookup"><span data-stu-id="a5bf1-108">Button States</span></span>  
 <span data-ttu-id="a5bf1-109">次の表は、<xref:System.Windows.Controls.Button> コントロールの表示状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-109">The following table lists the visual states for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
|<span data-ttu-id="a5bf1-110">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="a5bf1-110">VisualState Name</span></span>|<span data-ttu-id="a5bf1-111">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="a5bf1-111">VisualStateGroup Name</span></span>|<span data-ttu-id="a5bf1-112">説明</span><span class="sxs-lookup"><span data-stu-id="a5bf1-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="a5bf1-113">標準</span><span class="sxs-lookup"><span data-stu-id="a5bf1-113">Normal</span></span>|<span data-ttu-id="a5bf1-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a5bf1-114">CommonStates</span></span>|<span data-ttu-id="a5bf1-115">既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-115">The default state.</span></span>|  
|<span data-ttu-id="a5bf1-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="a5bf1-116">MouseOver</span></span>|<span data-ttu-id="a5bf1-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a5bf1-117">CommonStates</span></span>|<span data-ttu-id="a5bf1-118">マウス ポインターがコントロール上に配置されます。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="a5bf1-119">押されている</span><span class="sxs-lookup"><span data-stu-id="a5bf1-119">Pressed</span></span>|<span data-ttu-id="a5bf1-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a5bf1-120">CommonStates</span></span>|<span data-ttu-id="a5bf1-121">コントロールが押されています。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-121">The control is pressed.</span></span>|  
|<span data-ttu-id="a5bf1-122">無効</span><span class="sxs-lookup"><span data-stu-id="a5bf1-122">Disabled</span></span>|<span data-ttu-id="a5bf1-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a5bf1-123">CommonStates</span></span>|<span data-ttu-id="a5bf1-124">コントロールが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-124">The control is disabled.</span></span>|  
|<span data-ttu-id="a5bf1-125">フォーカスされている</span><span class="sxs-lookup"><span data-stu-id="a5bf1-125">Focused</span></span>|<span data-ttu-id="a5bf1-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="a5bf1-126">FocusStates</span></span>|<span data-ttu-id="a5bf1-127">コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-127">The control has focus.</span></span>|  
|<span data-ttu-id="a5bf1-128">フォーカスされていない</span><span class="sxs-lookup"><span data-stu-id="a5bf1-128">Unfocused</span></span>|<span data-ttu-id="a5bf1-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="a5bf1-129">FocusStates</span></span>|<span data-ttu-id="a5bf1-130">コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="a5bf1-131">Valid</span><span class="sxs-lookup"><span data-stu-id="a5bf1-131">Valid</span></span>|<span data-ttu-id="a5bf1-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a5bf1-132">ValidationStates</span></span>|<span data-ttu-id="a5bf1-133">コントロールは <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false`ます。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="a5bf1-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="a5bf1-134">InvalidFocused</span></span>|<span data-ttu-id="a5bf1-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a5bf1-135">ValidationStates</span></span>|<span data-ttu-id="a5bf1-136"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティが `true`、コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="a5bf1-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="a5bf1-137">InvalidUnfocused</span></span>|<span data-ttu-id="a5bf1-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a5bf1-138">ValidationStates</span></span>|<span data-ttu-id="a5bf1-139"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティが `true`、コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="button-controltemplate-example"></a><span data-ttu-id="a5bf1-140">Button ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="a5bf1-140">Button ControlTemplate Example</span></span>  
 <span data-ttu-id="a5bf1-141">次の例は、<xref:System.Windows.Controls.Button> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Button](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#button)]  
  
 <span data-ttu-id="a5bf1-142">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-142">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="a5bf1-143">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5bf1-144">参照</span><span class="sxs-lookup"><span data-stu-id="a5bf1-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="a5bf1-145">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="a5bf1-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="a5bf1-146">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="a5bf1-146">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="a5bf1-147">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="a5bf1-147">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="a5bf1-148">コントロールのテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="a5bf1-148">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
