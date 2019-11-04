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
ms.openlocfilehash: 981a487b9935a86595a9caca03b4371326924642
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458221"
---
# <a name="togglebutton-styles-and-templates"></a><span data-ttu-id="c9879-102">ToggleButton のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="c9879-102">ToggleButton Styles and Templates</span></span>

<span data-ttu-id="c9879-103">このトピックでは、<xref:System.Windows.Controls.Primitives.ToggleButton> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c9879-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span> <span data-ttu-id="c9879-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="c9879-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="c9879-105">詳細については、「[Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9879-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>

## <a name="togglebutton-parts"></a><span data-ttu-id="c9879-106">ToggleButton の部分</span><span class="sxs-lookup"><span data-stu-id="c9879-106">ToggleButton Parts</span></span>

<span data-ttu-id="c9879-107"><xref:System.Windows.Controls.Primitives.ToggleButton> コントロールには、名前付きの部分がありません。</span><span class="sxs-lookup"><span data-stu-id="c9879-107">The <xref:System.Windows.Controls.Primitives.ToggleButton> control does not have any named parts.</span></span>

## <a name="togglebutton-states"></a><span data-ttu-id="c9879-108">ToggleButton の状態</span><span class="sxs-lookup"><span data-stu-id="c9879-108">ToggleButton States</span></span>

<span data-ttu-id="c9879-109">次の表は、<xref:System.Windows.Controls.Primitives.ToggleButton> コントロールの表示状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="c9879-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>

|<span data-ttu-id="c9879-110">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="c9879-110">VisualState Name</span></span>|<span data-ttu-id="c9879-111">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="c9879-111">VisualStateGroup Name</span></span>|<span data-ttu-id="c9879-112">説明</span><span class="sxs-lookup"><span data-stu-id="c9879-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="c9879-113">標準</span><span class="sxs-lookup"><span data-stu-id="c9879-113">Normal</span></span>|<span data-ttu-id="c9879-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="c9879-114">CommonStates</span></span>|<span data-ttu-id="c9879-115">既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="c9879-115">The default state.</span></span>|
|<span data-ttu-id="c9879-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="c9879-116">MouseOver</span></span>|<span data-ttu-id="c9879-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="c9879-117">CommonStates</span></span>|<span data-ttu-id="c9879-118">マウス ポインターがコントロール上に配置されます。</span><span class="sxs-lookup"><span data-stu-id="c9879-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="c9879-119">押されている</span><span class="sxs-lookup"><span data-stu-id="c9879-119">Pressed</span></span>|<span data-ttu-id="c9879-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="c9879-120">CommonStates</span></span>|<span data-ttu-id="c9879-121">コントロールが押されています。</span><span class="sxs-lookup"><span data-stu-id="c9879-121">The control is pressed.</span></span>|
|<span data-ttu-id="c9879-122">Disabled</span><span class="sxs-lookup"><span data-stu-id="c9879-122">Disabled</span></span>|<span data-ttu-id="c9879-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="c9879-123">CommonStates</span></span>|<span data-ttu-id="c9879-124">コントロールが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="c9879-124">The control is disabled.</span></span>|
|<span data-ttu-id="c9879-125">フォーカスされている</span><span class="sxs-lookup"><span data-stu-id="c9879-125">Focused</span></span>|<span data-ttu-id="c9879-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="c9879-126">FocusStates</span></span>|<span data-ttu-id="c9879-127">コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="c9879-127">The control has focus.</span></span>|
|<span data-ttu-id="c9879-128">フォーカスされていない</span><span class="sxs-lookup"><span data-stu-id="c9879-128">Unfocused</span></span>|<span data-ttu-id="c9879-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="c9879-129">FocusStates</span></span>|<span data-ttu-id="c9879-130">コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="c9879-130">The control does not have focus.</span></span>|
|<span data-ttu-id="c9879-131">チェック済み</span><span class="sxs-lookup"><span data-stu-id="c9879-131">Checked</span></span>|<span data-ttu-id="c9879-132">CheckStates</span><span class="sxs-lookup"><span data-stu-id="c9879-132">CheckStates</span></span>|<span data-ttu-id="c9879-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> が `true` です。</span><span class="sxs-lookup"><span data-stu-id="c9879-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.</span></span>|
|<span data-ttu-id="c9879-134">再帰</span><span class="sxs-lookup"><span data-stu-id="c9879-134">Unchecked</span></span>|<span data-ttu-id="c9879-135">CheckStates</span><span class="sxs-lookup"><span data-stu-id="c9879-135">CheckStates</span></span>|<span data-ttu-id="c9879-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> が `false` です。</span><span class="sxs-lookup"><span data-stu-id="c9879-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.</span></span>|
|<span data-ttu-id="c9879-137">確定</span><span class="sxs-lookup"><span data-stu-id="c9879-137">Indeterminate</span></span>|<span data-ttu-id="c9879-138">CheckStates</span><span class="sxs-lookup"><span data-stu-id="c9879-138">CheckStates</span></span>|<span data-ttu-id="c9879-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> が `true` で、<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> が `null` です。</span><span class="sxs-lookup"><span data-stu-id="c9879-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|
|<span data-ttu-id="c9879-140">有効</span><span class="sxs-lookup"><span data-stu-id="c9879-140">Valid</span></span>|<span data-ttu-id="c9879-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="c9879-141">ValidationStates</span></span>|<span data-ttu-id="c9879-142">コントロールは <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false`ます。</span><span class="sxs-lookup"><span data-stu-id="c9879-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="c9879-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="c9879-143">InvalidFocused</span></span>|<span data-ttu-id="c9879-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="c9879-144">ValidationStates</span></span>|<span data-ttu-id="c9879-145"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがある `true` です。</span><span class="sxs-lookup"><span data-stu-id="c9879-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="c9879-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="c9879-146">InvalidUnfocused</span></span>|<span data-ttu-id="c9879-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="c9879-147">ValidationStates</span></span>|<span data-ttu-id="c9879-148"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがない `true` です。</span><span class="sxs-lookup"><span data-stu-id="c9879-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

> [!NOTE]
> <span data-ttu-id="c9879-149">未確定の表示状態がコントロールテンプレートに存在しない場合、チェックを行わない状態は既定のビジュアル状態として使用されます。</span><span class="sxs-lookup"><span data-stu-id="c9879-149">If the Indeterminate visual state does not exist in your control template, then the Unchecked visual state will be used as default visual state.</span></span>

## <a name="togglebutton-controltemplate-example"></a><span data-ttu-id="c9879-150">ToggleButton ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="c9879-150">ToggleButton ControlTemplate Example</span></span>

<span data-ttu-id="c9879-151">次の例は、<xref:System.Windows.Controls.Primitives.ToggleButton> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="c9879-151">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>

[!code-xaml[ControlTemplateExamples#ToggleButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#togglebutton)]

<span data-ttu-id="c9879-152">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="c9879-152">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="c9879-153">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9879-153">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="c9879-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="c9879-154">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="c9879-155">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="c9879-155">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="c9879-156">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="c9879-156">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="c9879-157">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="c9879-157">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="c9879-158">ControlTemplate の作成による既存のコントロールの外観のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="c9879-158">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
