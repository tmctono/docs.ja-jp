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
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805913"
---
# <a name="togglebutton-styles-and-templates"></a><span data-ttu-id="5eeca-102">ToggleButton のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="5eeca-102">ToggleButton Styles and Templates</span></span>

<span data-ttu-id="5eeca-103">このトピックでは、<xref:System.Windows.Controls.Primitives.ToggleButton> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5eeca-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span> <span data-ttu-id="5eeca-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="5eeca-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="5eeca-105">詳細については、「[コントロールのためにテンプレートを作成する](../../../desktop-wpf/themes/how-to-create-apply-template.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5eeca-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>

## <a name="togglebutton-parts"></a><span data-ttu-id="5eeca-106">ToggleButton のパーツ</span><span class="sxs-lookup"><span data-stu-id="5eeca-106">ToggleButton Parts</span></span>

<span data-ttu-id="5eeca-107"><xref:System.Windows.Controls.Primitives.ToggleButton> コントロールに名前付きパーツはありません。</span><span class="sxs-lookup"><span data-stu-id="5eeca-107">The <xref:System.Windows.Controls.Primitives.ToggleButton> control does not have any named parts.</span></span>

## <a name="togglebutton-states"></a><span data-ttu-id="5eeca-108">ToggleButton の状態</span><span class="sxs-lookup"><span data-stu-id="5eeca-108">ToggleButton States</span></span>

<span data-ttu-id="5eeca-109">次の表は、<xref:System.Windows.Controls.Primitives.ToggleButton> コントロールの表示状態の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="5eeca-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>

|<span data-ttu-id="5eeca-110">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="5eeca-110">VisualState Name</span></span>|<span data-ttu-id="5eeca-111">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="5eeca-111">VisualStateGroup Name</span></span>|<span data-ttu-id="5eeca-112">説明</span><span class="sxs-lookup"><span data-stu-id="5eeca-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="5eeca-113">標準</span><span class="sxs-lookup"><span data-stu-id="5eeca-113">Normal</span></span>|<span data-ttu-id="5eeca-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="5eeca-114">CommonStates</span></span>|<span data-ttu-id="5eeca-115">既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="5eeca-115">The default state.</span></span>|
|<span data-ttu-id="5eeca-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="5eeca-116">MouseOver</span></span>|<span data-ttu-id="5eeca-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="5eeca-117">CommonStates</span></span>|<span data-ttu-id="5eeca-118">マウス ポインターがコントロール上に配置されています。</span><span class="sxs-lookup"><span data-stu-id="5eeca-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="5eeca-119">押されている</span><span class="sxs-lookup"><span data-stu-id="5eeca-119">Pressed</span></span>|<span data-ttu-id="5eeca-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="5eeca-120">CommonStates</span></span>|<span data-ttu-id="5eeca-121">コントロールが押されています。</span><span class="sxs-lookup"><span data-stu-id="5eeca-121">The control is pressed.</span></span>|
|<span data-ttu-id="5eeca-122">無効</span><span class="sxs-lookup"><span data-stu-id="5eeca-122">Disabled</span></span>|<span data-ttu-id="5eeca-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="5eeca-123">CommonStates</span></span>|<span data-ttu-id="5eeca-124">コントロールが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="5eeca-124">The control is disabled.</span></span>|
|<span data-ttu-id="5eeca-125">フォーカスされている</span><span class="sxs-lookup"><span data-stu-id="5eeca-125">Focused</span></span>|<span data-ttu-id="5eeca-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="5eeca-126">FocusStates</span></span>|<span data-ttu-id="5eeca-127">コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="5eeca-127">The control has focus.</span></span>|
|<span data-ttu-id="5eeca-128">フォーカスされていない</span><span class="sxs-lookup"><span data-stu-id="5eeca-128">Unfocused</span></span>|<span data-ttu-id="5eeca-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="5eeca-129">FocusStates</span></span>|<span data-ttu-id="5eeca-130">コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="5eeca-130">The control does not have focus.</span></span>|
|<span data-ttu-id="5eeca-131">チェック済み</span><span class="sxs-lookup"><span data-stu-id="5eeca-131">Checked</span></span>|<span data-ttu-id="5eeca-132">CheckStates</span><span class="sxs-lookup"><span data-stu-id="5eeca-132">CheckStates</span></span>|<span data-ttu-id="5eeca-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> が `true`です。</span><span class="sxs-lookup"><span data-stu-id="5eeca-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.</span></span>|
|<span data-ttu-id="5eeca-134">オフ</span><span class="sxs-lookup"><span data-stu-id="5eeca-134">Unchecked</span></span>|<span data-ttu-id="5eeca-135">CheckStates</span><span class="sxs-lookup"><span data-stu-id="5eeca-135">CheckStates</span></span>|<span data-ttu-id="5eeca-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> が `false`です。</span><span class="sxs-lookup"><span data-stu-id="5eeca-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.</span></span>|
|<span data-ttu-id="5eeca-137">Indeterminate</span><span class="sxs-lookup"><span data-stu-id="5eeca-137">Indeterminate</span></span>|<span data-ttu-id="5eeca-138">CheckStates</span><span class="sxs-lookup"><span data-stu-id="5eeca-138">CheckStates</span></span>|<span data-ttu-id="5eeca-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> が `true` で、<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> が `null` です。</span><span class="sxs-lookup"><span data-stu-id="5eeca-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|
|<span data-ttu-id="5eeca-140">有効</span><span class="sxs-lookup"><span data-stu-id="5eeca-140">Valid</span></span>|<span data-ttu-id="5eeca-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5eeca-141">ValidationStates</span></span>|<span data-ttu-id="5eeca-142">コントロールでは <xref:System.Windows.Controls.Validation> クラスが使用されており、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false` です。</span><span class="sxs-lookup"><span data-stu-id="5eeca-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="5eeca-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="5eeca-143">InvalidFocused</span></span>|<span data-ttu-id="5eeca-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5eeca-144">ValidationStates</span></span>|<span data-ttu-id="5eeca-145"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `true` で、コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="5eeca-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|
|<span data-ttu-id="5eeca-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="5eeca-146">InvalidUnfocused</span></span>|<span data-ttu-id="5eeca-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5eeca-147">ValidationStates</span></span>|<span data-ttu-id="5eeca-148"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `true` で、コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="5eeca-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|

> [!NOTE]
> <span data-ttu-id="5eeca-149">Indeterminate 表示状態がコントロール テンプレートに存在しない場合、Unchecked 表示状態が既定の表示状態として使用されます。</span><span class="sxs-lookup"><span data-stu-id="5eeca-149">If the Indeterminate visual state does not exist in your control template, then the Unchecked visual state will be used as default visual state.</span></span>

## <a name="togglebutton-controltemplate-example"></a><span data-ttu-id="5eeca-150">ToggleButton の ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="5eeca-150">ToggleButton ControlTemplate Example</span></span>

<span data-ttu-id="5eeca-151">次の例は、<xref:System.Windows.Controls.Primitives.ToggleButton> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="5eeca-151">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>

[!code-xaml[ControlTemplateExamples#ToggleButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#togglebutton)]

<span data-ttu-id="5eeca-152">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="5eeca-152">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="5eeca-153">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5eeca-153">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="5eeca-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="5eeca-154">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="5eeca-155">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="5eeca-155">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="5eeca-156">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="5eeca-156">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="5eeca-157">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="5eeca-157">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="5eeca-158">コントロールのためのテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="5eeca-158">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
