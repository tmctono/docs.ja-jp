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
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283811"
---
# <a name="checkbox-styles-and-templates"></a><span data-ttu-id="0448e-102">CheckBox のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="0448e-102">CheckBox Styles and Templates</span></span>
<span data-ttu-id="0448e-103">このトピックでは、<xref:System.Windows.Controls.CheckBox> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="0448e-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.CheckBox> control.</span></span> <span data-ttu-id="0448e-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="0448e-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="0448e-105">詳細については、「[コントロールのためにテンプレートを作成する](../../../desktop-wpf/themes/how-to-create-apply-template.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0448e-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="checkbox-parts"></a><span data-ttu-id="0448e-106">CheckBox のパーツ</span><span class="sxs-lookup"><span data-stu-id="0448e-106">CheckBox Parts</span></span>  
 <span data-ttu-id="0448e-107"><xref:System.Windows.Controls.CheckBox> コントロールに名前付きパーツはありません。</span><span class="sxs-lookup"><span data-stu-id="0448e-107">The <xref:System.Windows.Controls.CheckBox> control does not have any named parts.</span></span>  
  
## <a name="checkbox-states"></a><span data-ttu-id="0448e-108">CheckBox の状態</span><span class="sxs-lookup"><span data-stu-id="0448e-108">CheckBox States</span></span>  
 <span data-ttu-id="0448e-109">次の表は、<xref:System.Windows.Controls.CheckBox> コントロールの表示状態の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="0448e-109">The following table lists the visual states for the <xref:System.Windows.Controls.CheckBox> control.</span></span>  
  
|<span data-ttu-id="0448e-110">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="0448e-110">VisualState Name</span></span>|<span data-ttu-id="0448e-111">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="0448e-111">VisualStateGroup Name</span></span>|<span data-ttu-id="0448e-112">説明</span><span class="sxs-lookup"><span data-stu-id="0448e-112">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="0448e-113">標準</span><span class="sxs-lookup"><span data-stu-id="0448e-113">Normal</span></span>|<span data-ttu-id="0448e-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="0448e-114">CommonStates</span></span>|<span data-ttu-id="0448e-115">既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="0448e-115">The default state.</span></span>|  
|<span data-ttu-id="0448e-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="0448e-116">MouseOver</span></span>|<span data-ttu-id="0448e-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="0448e-117">CommonStates</span></span>|<span data-ttu-id="0448e-118">マウス ポインターがコントロール上に配置されています。</span><span class="sxs-lookup"><span data-stu-id="0448e-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="0448e-119">押されている</span><span class="sxs-lookup"><span data-stu-id="0448e-119">Pressed</span></span>|<span data-ttu-id="0448e-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="0448e-120">CommonStates</span></span>|<span data-ttu-id="0448e-121">コントロールが押されています。</span><span class="sxs-lookup"><span data-stu-id="0448e-121">The control is pressed.</span></span>|  
|<span data-ttu-id="0448e-122">無効</span><span class="sxs-lookup"><span data-stu-id="0448e-122">Disabled</span></span>|<span data-ttu-id="0448e-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="0448e-123">CommonStates</span></span>|<span data-ttu-id="0448e-124">コントロールが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="0448e-124">The control is disabled.</span></span>|  
|<span data-ttu-id="0448e-125">フォーカスされている</span><span class="sxs-lookup"><span data-stu-id="0448e-125">Focused</span></span>|<span data-ttu-id="0448e-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="0448e-126">FocusStates</span></span>|<span data-ttu-id="0448e-127">コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="0448e-127">The control has focus.</span></span>|  
|<span data-ttu-id="0448e-128">フォーカスされていない</span><span class="sxs-lookup"><span data-stu-id="0448e-128">Unfocused</span></span>|<span data-ttu-id="0448e-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="0448e-129">FocusStates</span></span>|<span data-ttu-id="0448e-130">コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="0448e-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="0448e-131">チェック済み</span><span class="sxs-lookup"><span data-stu-id="0448e-131">Checked</span></span>|<span data-ttu-id="0448e-132">CheckStates</span><span class="sxs-lookup"><span data-stu-id="0448e-132">CheckStates</span></span>|<span data-ttu-id="0448e-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> が `true`です。</span><span class="sxs-lookup"><span data-stu-id="0448e-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.</span></span>|  
|<span data-ttu-id="0448e-134">オフ</span><span class="sxs-lookup"><span data-stu-id="0448e-134">Unchecked</span></span>|<span data-ttu-id="0448e-135">CheckStates</span><span class="sxs-lookup"><span data-stu-id="0448e-135">CheckStates</span></span>|<span data-ttu-id="0448e-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> が `false`です。</span><span class="sxs-lookup"><span data-stu-id="0448e-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.</span></span>|  
|<span data-ttu-id="0448e-137">Indeterminate</span><span class="sxs-lookup"><span data-stu-id="0448e-137">Indeterminate</span></span>|<span data-ttu-id="0448e-138">CheckStates</span><span class="sxs-lookup"><span data-stu-id="0448e-138">CheckStates</span></span>|<span data-ttu-id="0448e-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> が `true` で、<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> が `null` です。</span><span class="sxs-lookup"><span data-stu-id="0448e-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|  
|<span data-ttu-id="0448e-140">有効</span><span class="sxs-lookup"><span data-stu-id="0448e-140">Valid</span></span>|<span data-ttu-id="0448e-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0448e-141">ValidationStates</span></span>|<span data-ttu-id="0448e-142">このコントロールで <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false` です。</span><span class="sxs-lookup"><span data-stu-id="0448e-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="0448e-143">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="0448e-143">InvalidUnfocused</span></span>|<span data-ttu-id="0448e-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0448e-144">ValidationStates</span></span>|<span data-ttu-id="0448e-145"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがある `true` です。</span><span class="sxs-lookup"><span data-stu-id="0448e-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="0448e-146">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="0448e-146">InvalidFocused</span></span>|<span data-ttu-id="0448e-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0448e-147">ValidationStates</span></span>|<span data-ttu-id="0448e-148"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがない `true` です。</span><span class="sxs-lookup"><span data-stu-id="0448e-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="checkbox-controltemplate-example"></a><span data-ttu-id="0448e-149">CheckBox の ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="0448e-149">CheckBox ControlTemplate Example</span></span>  
 <span data-ttu-id="0448e-150">次の例は、<xref:System.Windows.Controls.CheckBox> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="0448e-150">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.CheckBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#CheckBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/checkbox.xaml#checkbox)]  
  
 <span data-ttu-id="0448e-151">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="0448e-151">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="0448e-152">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0448e-152">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0448e-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="0448e-153">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="0448e-154">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="0448e-154">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="0448e-155">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="0448e-155">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="0448e-156">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="0448e-156">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="0448e-157">コントロールのためのテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="0448e-157">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
