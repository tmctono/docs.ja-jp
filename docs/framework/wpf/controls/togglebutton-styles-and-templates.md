---
title: ToggleButton のスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], ToggleButton
- ToggleButton [WPF], styles and templates
- ControlTemplate [WPF], ToggleButton
- styles [WPF], ToggleButton
- templates [WPF], ToggleButton
- parts [WPF], ToggleButton
ms.assetid: 54f23f30-4bcb-4f09-8ce4-376a13a255a1
ms.openlocfilehash: e055dcbd557f9b90eb2fe99ad15a05b6f229fd28
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805913"
---
# <a name="togglebutton-styles-and-templates"></a><span data-ttu-id="ba634-102">ToggleButton のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="ba634-102">ToggleButton Styles and Templates</span></span>

<span data-ttu-id="ba634-103">このトピックでは、コントロールのスタイルとテンプレートについて<xref:System.Windows.Controls.Primitives.ToggleButton>説明します。</span><span class="sxs-lookup"><span data-stu-id="ba634-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span> <span data-ttu-id="ba634-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="ba634-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="ba634-105">詳細については、「[コントロールのテンプレートを作成する」を](../../../desktop-wpf/themes/how-to-create-apply-template.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba634-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>

## <a name="togglebutton-parts"></a><span data-ttu-id="ba634-106">トグルボタンパーツ</span><span class="sxs-lookup"><span data-stu-id="ba634-106">ToggleButton Parts</span></span>

<span data-ttu-id="ba634-107"><xref:System.Windows.Controls.Primitives.ToggleButton>コントロールには名前付きパーツがありません。</span><span class="sxs-lookup"><span data-stu-id="ba634-107">The <xref:System.Windows.Controls.Primitives.ToggleButton> control does not have any named parts.</span></span>

## <a name="togglebutton-states"></a><span data-ttu-id="ba634-108">トグルボタンの状態</span><span class="sxs-lookup"><span data-stu-id="ba634-108">ToggleButton States</span></span>

<span data-ttu-id="ba634-109">次の表に、コントロールの表示状態<xref:System.Windows.Controls.Primitives.ToggleButton>を示します。</span><span class="sxs-lookup"><span data-stu-id="ba634-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>

|<span data-ttu-id="ba634-110">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="ba634-110">VisualState Name</span></span>|<span data-ttu-id="ba634-111">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="ba634-111">VisualStateGroup Name</span></span>|<span data-ttu-id="ba634-112">説明</span><span class="sxs-lookup"><span data-stu-id="ba634-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="ba634-113">Normal</span><span class="sxs-lookup"><span data-stu-id="ba634-113">Normal</span></span>|<span data-ttu-id="ba634-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ba634-114">CommonStates</span></span>|<span data-ttu-id="ba634-115">既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="ba634-115">The default state.</span></span>|
|<span data-ttu-id="ba634-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="ba634-116">MouseOver</span></span>|<span data-ttu-id="ba634-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ba634-117">CommonStates</span></span>|<span data-ttu-id="ba634-118">マウス ポインターがコントロール上に配置されます。</span><span class="sxs-lookup"><span data-stu-id="ba634-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="ba634-119">押されている</span><span class="sxs-lookup"><span data-stu-id="ba634-119">Pressed</span></span>|<span data-ttu-id="ba634-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ba634-120">CommonStates</span></span>|<span data-ttu-id="ba634-121">コントロールが押されています。</span><span class="sxs-lookup"><span data-stu-id="ba634-121">The control is pressed.</span></span>|
|<span data-ttu-id="ba634-122">無効</span><span class="sxs-lookup"><span data-stu-id="ba634-122">Disabled</span></span>|<span data-ttu-id="ba634-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ba634-123">CommonStates</span></span>|<span data-ttu-id="ba634-124">コントロールが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="ba634-124">The control is disabled.</span></span>|
|<span data-ttu-id="ba634-125">フォーカスされている</span><span class="sxs-lookup"><span data-stu-id="ba634-125">Focused</span></span>|<span data-ttu-id="ba634-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="ba634-126">FocusStates</span></span>|<span data-ttu-id="ba634-127">コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="ba634-127">The control has focus.</span></span>|
|<span data-ttu-id="ba634-128">フォーカスされていない</span><span class="sxs-lookup"><span data-stu-id="ba634-128">Unfocused</span></span>|<span data-ttu-id="ba634-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="ba634-129">FocusStates</span></span>|<span data-ttu-id="ba634-130">コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="ba634-130">The control does not have focus.</span></span>|
|<span data-ttu-id="ba634-131">オン</span><span class="sxs-lookup"><span data-stu-id="ba634-131">Checked</span></span>|<span data-ttu-id="ba634-132">チェックステート</span><span class="sxs-lookup"><span data-stu-id="ba634-132">CheckStates</span></span>|<span data-ttu-id="ba634-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> は `true` です。</span><span class="sxs-lookup"><span data-stu-id="ba634-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.</span></span>|
|<span data-ttu-id="ba634-134">オフ</span><span class="sxs-lookup"><span data-stu-id="ba634-134">Unchecked</span></span>|<span data-ttu-id="ba634-135">チェックステート</span><span class="sxs-lookup"><span data-stu-id="ba634-135">CheckStates</span></span>|<span data-ttu-id="ba634-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> は `false` です。</span><span class="sxs-lookup"><span data-stu-id="ba634-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.</span></span>|
|<span data-ttu-id="ba634-137">不確定</span><span class="sxs-lookup"><span data-stu-id="ba634-137">Indeterminate</span></span>|<span data-ttu-id="ba634-138">チェックステート</span><span class="sxs-lookup"><span data-stu-id="ba634-138">CheckStates</span></span>|<span data-ttu-id="ba634-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> が `true` で、<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> が `null` です。</span><span class="sxs-lookup"><span data-stu-id="ba634-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|
|<span data-ttu-id="ba634-140">有効</span><span class="sxs-lookup"><span data-stu-id="ba634-140">Valid</span></span>|<span data-ttu-id="ba634-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ba634-141">ValidationStates</span></span>|<span data-ttu-id="ba634-142">コントロールはクラスを<xref:System.Windows.Controls.Validation>使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`false`です。</span><span class="sxs-lookup"><span data-stu-id="ba634-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="ba634-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="ba634-143">InvalidFocused</span></span>|<span data-ttu-id="ba634-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ba634-144">ValidationStates</span></span>|<span data-ttu-id="ba634-145"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`、コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="ba634-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|
|<span data-ttu-id="ba634-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="ba634-146">InvalidUnfocused</span></span>|<span data-ttu-id="ba634-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ba634-147">ValidationStates</span></span>|<span data-ttu-id="ba634-148"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティが`true`、コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="ba634-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|

> [!NOTE]
> <span data-ttu-id="ba634-149">Indeterminate 表示状態がコントロール テンプレートに存在しない場合、チェックされていない表示状態が既定の表示状態として使用されます。</span><span class="sxs-lookup"><span data-stu-id="ba634-149">If the Indeterminate visual state does not exist in your control template, then the Unchecked visual state will be used as default visual state.</span></span>

## <a name="togglebutton-controltemplate-example"></a><span data-ttu-id="ba634-150">トグルボタンコントロールテンプレートの例</span><span class="sxs-lookup"><span data-stu-id="ba634-150">ToggleButton ControlTemplate Example</span></span>

<span data-ttu-id="ba634-151">コントロールの を定義する方法を<xref:System.Windows.Controls.ControlTemplate>次の<xref:System.Windows.Controls.Primitives.ToggleButton>例に示します。</span><span class="sxs-lookup"><span data-stu-id="ba634-151">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>

[!code-xaml[ControlTemplateExamples#ToggleButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#togglebutton)]

<span data-ttu-id="ba634-152">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="ba634-152">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="ba634-153">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba634-153">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="ba634-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="ba634-154">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="ba634-155">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="ba634-155">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="ba634-156">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="ba634-156">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="ba634-157">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="ba634-157">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="ba634-158">コントロールのテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="ba634-158">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
