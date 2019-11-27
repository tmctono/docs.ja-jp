---
title: CheckBox のスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], CheckBox
- templates [WPF], CheckBox
- parts [WPF], CheckBox
- ControlTemplate [WPF], CheckBox
- CheckBox [WPF], styles and templates
- styles [WPF], CheckBox
ms.assetid: bfdaec96-d101-4d3d-864d-c27e6b621d03
ms.openlocfilehash: b9eee48c01f53e12bbe4a72f84c20eab68d5de23
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283811"
---
# <a name="checkbox-styles-and-templates"></a><span data-ttu-id="ca3b9-102">CheckBox のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="ca3b9-102">CheckBox Styles and Templates</span></span>
<span data-ttu-id="ca3b9-103">このトピックでは、<xref:System.Windows.Controls.CheckBox> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ca3b9-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.CheckBox> control.</span></span> <span data-ttu-id="ca3b9-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="ca3b9-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="ca3b9-105">詳細については、「[コントロールのテンプレートを作成する](../../../desktop-wpf/themes/how-to-create-apply-template.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca3b9-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="checkbox-parts"></a><span data-ttu-id="ca3b9-106">チェックボックスの部分</span><span class="sxs-lookup"><span data-stu-id="ca3b9-106">CheckBox Parts</span></span>  
 <span data-ttu-id="ca3b9-107"><xref:System.Windows.Controls.CheckBox> コントロールには、名前付きの部分がありません。</span><span class="sxs-lookup"><span data-stu-id="ca3b9-107">The <xref:System.Windows.Controls.CheckBox> control does not have any named parts.</span></span>  
  
## <a name="checkbox-states"></a><span data-ttu-id="ca3b9-108">チェックボックスの状態</span><span class="sxs-lookup"><span data-stu-id="ca3b9-108">CheckBox States</span></span>  
 <span data-ttu-id="ca3b9-109">次の表は、<xref:System.Windows.Controls.CheckBox> コントロールの表示状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="ca3b9-109">The following table lists the visual states for the <xref:System.Windows.Controls.CheckBox> control.</span></span>  
  
|<span data-ttu-id="ca3b9-110">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="ca3b9-110">VisualState Name</span></span>|<span data-ttu-id="ca3b9-111">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="ca3b9-111">VisualStateGroup Name</span></span>|<span data-ttu-id="ca3b9-112">説明</span><span class="sxs-lookup"><span data-stu-id="ca3b9-112">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="ca3b9-113">標準</span><span class="sxs-lookup"><span data-stu-id="ca3b9-113">Normal</span></span>|<span data-ttu-id="ca3b9-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ca3b9-114">CommonStates</span></span>|<span data-ttu-id="ca3b9-115">既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="ca3b9-115">The default state.</span></span>|  
|<span data-ttu-id="ca3b9-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="ca3b9-116">MouseOver</span></span>|<span data-ttu-id="ca3b9-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ca3b9-117">CommonStates</span></span>|<span data-ttu-id="ca3b9-118">マウス ポインターがコントロール上に配置されます。</span><span class="sxs-lookup"><span data-stu-id="ca3b9-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="ca3b9-119">押されている</span><span class="sxs-lookup"><span data-stu-id="ca3b9-119">Pressed</span></span>|<span data-ttu-id="ca3b9-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ca3b9-120">CommonStates</span></span>|<span data-ttu-id="ca3b9-121">コントロールが押されています。</span><span class="sxs-lookup"><span data-stu-id="ca3b9-121">The control is pressed.</span></span>|  
|<span data-ttu-id="ca3b9-122">無効</span><span class="sxs-lookup"><span data-stu-id="ca3b9-122">Disabled</span></span>|<span data-ttu-id="ca3b9-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ca3b9-123">CommonStates</span></span>|<span data-ttu-id="ca3b9-124">コントロールが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="ca3b9-124">The control is disabled.</span></span>|  
|<span data-ttu-id="ca3b9-125">フォーカスされている</span><span class="sxs-lookup"><span data-stu-id="ca3b9-125">Focused</span></span>|<span data-ttu-id="ca3b9-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="ca3b9-126">FocusStates</span></span>|<span data-ttu-id="ca3b9-127">コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="ca3b9-127">The control has focus.</span></span>|  
|<span data-ttu-id="ca3b9-128">フォーカスされていない</span><span class="sxs-lookup"><span data-stu-id="ca3b9-128">Unfocused</span></span>|<span data-ttu-id="ca3b9-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="ca3b9-129">FocusStates</span></span>|<span data-ttu-id="ca3b9-130">コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="ca3b9-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="ca3b9-131">チェック済み</span><span class="sxs-lookup"><span data-stu-id="ca3b9-131">Checked</span></span>|<span data-ttu-id="ca3b9-132">CheckStates</span><span class="sxs-lookup"><span data-stu-id="ca3b9-132">CheckStates</span></span>|<span data-ttu-id="ca3b9-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> は `true` です。</span><span class="sxs-lookup"><span data-stu-id="ca3b9-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.</span></span>|  
|<span data-ttu-id="ca3b9-134">再帰</span><span class="sxs-lookup"><span data-stu-id="ca3b9-134">Unchecked</span></span>|<span data-ttu-id="ca3b9-135">CheckStates</span><span class="sxs-lookup"><span data-stu-id="ca3b9-135">CheckStates</span></span>|<span data-ttu-id="ca3b9-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> は `false` です。</span><span class="sxs-lookup"><span data-stu-id="ca3b9-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.</span></span>|  
|<span data-ttu-id="ca3b9-137">確定</span><span class="sxs-lookup"><span data-stu-id="ca3b9-137">Indeterminate</span></span>|<span data-ttu-id="ca3b9-138">CheckStates</span><span class="sxs-lookup"><span data-stu-id="ca3b9-138">CheckStates</span></span>|<span data-ttu-id="ca3b9-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> が `true` で、<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> が `null` です。</span><span class="sxs-lookup"><span data-stu-id="ca3b9-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|  
|<span data-ttu-id="ca3b9-140">Valid</span><span class="sxs-lookup"><span data-stu-id="ca3b9-140">Valid</span></span>|<span data-ttu-id="ca3b9-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ca3b9-141">ValidationStates</span></span>|<span data-ttu-id="ca3b9-142">コントロールは <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false`ます。</span><span class="sxs-lookup"><span data-stu-id="ca3b9-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="ca3b9-143">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="ca3b9-143">InvalidUnfocused</span></span>|<span data-ttu-id="ca3b9-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ca3b9-144">ValidationStates</span></span>|<span data-ttu-id="ca3b9-145"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがある `true` です。</span><span class="sxs-lookup"><span data-stu-id="ca3b9-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="ca3b9-146">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="ca3b9-146">InvalidFocused</span></span>|<span data-ttu-id="ca3b9-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ca3b9-147">ValidationStates</span></span>|<span data-ttu-id="ca3b9-148"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがない `true` です。</span><span class="sxs-lookup"><span data-stu-id="ca3b9-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="checkbox-controltemplate-example"></a><span data-ttu-id="ca3b9-149">CheckBox ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="ca3b9-149">CheckBox ControlTemplate Example</span></span>  
 <span data-ttu-id="ca3b9-150">次の例は、<xref:System.Windows.Controls.CheckBox> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="ca3b9-150">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.CheckBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#CheckBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/checkbox.xaml#checkbox)]  
  
 <span data-ttu-id="ca3b9-151">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="ca3b9-151">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="ca3b9-152">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca3b9-152">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca3b9-153">参照</span><span class="sxs-lookup"><span data-stu-id="ca3b9-153">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="ca3b9-154">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="ca3b9-154">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="ca3b9-155">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="ca3b9-155">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="ca3b9-156">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="ca3b9-156">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="ca3b9-157">コントロールのテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="ca3b9-157">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
