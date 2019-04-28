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
ms.openlocfilehash: 46fd7d07c3904ee752ae3f467f65af4b0c031c84
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790755"
---
# <a name="togglebutton-styles-and-templates"></a><span data-ttu-id="729ab-102">ToggleButton のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="729ab-102">ToggleButton Styles and Templates</span></span>

<span data-ttu-id="729ab-103">このトピックでは、スタイルとテンプレートについて説明します、<xref:System.Windows.Controls.Primitives.ToggleButton>コントロール。</span><span class="sxs-lookup"><span data-stu-id="729ab-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span> <span data-ttu-id="729ab-104">既定値を変更する<xref:System.Windows.Controls.ControlTemplate>固有の外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="729ab-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="729ab-105">詳細については、「[ControlTemplate の作成による既存のコントロールの外観のカスタマイズ](customizing-the-appearance-of-an-existing-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="729ab-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>

## <a name="togglebutton-parts"></a><span data-ttu-id="729ab-106">トグル ボタンのパーツ</span><span class="sxs-lookup"><span data-stu-id="729ab-106">ToggleButton Parts</span></span>

<span data-ttu-id="729ab-107"><xref:System.Windows.Controls.Primitives.ToggleButton>コントロールには、名前付きパーツはありません。</span><span class="sxs-lookup"><span data-stu-id="729ab-107">The <xref:System.Windows.Controls.Primitives.ToggleButton> control does not have any named parts.</span></span>

## <a name="togglebutton-states"></a><span data-ttu-id="729ab-108">トグル ボタンの状態</span><span class="sxs-lookup"><span data-stu-id="729ab-108">ToggleButton States</span></span>

<span data-ttu-id="729ab-109">次の表のビジュアルの状態、<xref:System.Windows.Controls.Primitives.ToggleButton>コントロール。</span><span class="sxs-lookup"><span data-stu-id="729ab-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>

|<span data-ttu-id="729ab-110">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="729ab-110">VisualState Name</span></span>|<span data-ttu-id="729ab-111">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="729ab-111">VisualStateGroup Name</span></span>|<span data-ttu-id="729ab-112">説明</span><span class="sxs-lookup"><span data-stu-id="729ab-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="729ab-113">標準</span><span class="sxs-lookup"><span data-stu-id="729ab-113">Normal</span></span>|<span data-ttu-id="729ab-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="729ab-114">CommonStates</span></span>|<span data-ttu-id="729ab-115">既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="729ab-115">The default state.</span></span>|
|<span data-ttu-id="729ab-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="729ab-116">MouseOver</span></span>|<span data-ttu-id="729ab-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="729ab-117">CommonStates</span></span>|<span data-ttu-id="729ab-118">マウス ポインターがコントロール上に配置されています。</span><span class="sxs-lookup"><span data-stu-id="729ab-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="729ab-119">押されている</span><span class="sxs-lookup"><span data-stu-id="729ab-119">Pressed</span></span>|<span data-ttu-id="729ab-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="729ab-120">CommonStates</span></span>|<span data-ttu-id="729ab-121">コントロールが押されています。</span><span class="sxs-lookup"><span data-stu-id="729ab-121">The control is pressed.</span></span>|
|<span data-ttu-id="729ab-122">無効</span><span class="sxs-lookup"><span data-stu-id="729ab-122">Disabled</span></span>|<span data-ttu-id="729ab-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="729ab-123">CommonStates</span></span>|<span data-ttu-id="729ab-124">コントロールが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="729ab-124">The control is disabled.</span></span>|
|<span data-ttu-id="729ab-125">フォーカスされている</span><span class="sxs-lookup"><span data-stu-id="729ab-125">Focused</span></span>|<span data-ttu-id="729ab-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="729ab-126">FocusStates</span></span>|<span data-ttu-id="729ab-127">コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="729ab-127">The control has focus.</span></span>|
|<span data-ttu-id="729ab-128">フォーカスされていない</span><span class="sxs-lookup"><span data-stu-id="729ab-128">Unfocused</span></span>|<span data-ttu-id="729ab-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="729ab-129">FocusStates</span></span>|<span data-ttu-id="729ab-130">コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="729ab-130">The control does not have focus.</span></span>|
|<span data-ttu-id="729ab-131">チェック済み</span><span class="sxs-lookup"><span data-stu-id="729ab-131">Checked</span></span>|<span data-ttu-id="729ab-132">CheckStates</span><span class="sxs-lookup"><span data-stu-id="729ab-132">CheckStates</span></span>|<span data-ttu-id="729ab-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> は `true`です。</span><span class="sxs-lookup"><span data-stu-id="729ab-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.</span></span>|
|<span data-ttu-id="729ab-134">オフ</span><span class="sxs-lookup"><span data-stu-id="729ab-134">Unchecked</span></span>|<span data-ttu-id="729ab-135">CheckStates</span><span class="sxs-lookup"><span data-stu-id="729ab-135">CheckStates</span></span>|<span data-ttu-id="729ab-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> は `false`です。</span><span class="sxs-lookup"><span data-stu-id="729ab-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.</span></span>|
|<span data-ttu-id="729ab-137">不確定です</span><span class="sxs-lookup"><span data-stu-id="729ab-137">Indeterminate</span></span>|<span data-ttu-id="729ab-138">CheckStates</span><span class="sxs-lookup"><span data-stu-id="729ab-138">CheckStates</span></span>|<span data-ttu-id="729ab-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> が `true` で、<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> が `null` です。</span><span class="sxs-lookup"><span data-stu-id="729ab-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|
|<span data-ttu-id="729ab-140">有効</span><span class="sxs-lookup"><span data-stu-id="729ab-140">Valid</span></span>|<span data-ttu-id="729ab-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="729ab-141">ValidationStates</span></span>|<span data-ttu-id="729ab-142">コントロールを使用して、<xref:System.Windows.Controls.Validation>クラスおよび<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`false`します。</span><span class="sxs-lookup"><span data-stu-id="729ab-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="729ab-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="729ab-143">InvalidFocused</span></span>|<span data-ttu-id="729ab-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="729ab-144">ValidationStates</span></span>|<span data-ttu-id="729ab-145"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="729ab-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="729ab-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="729ab-146">InvalidUnfocused</span></span>|<span data-ttu-id="729ab-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="729ab-147">ValidationStates</span></span>|<span data-ttu-id="729ab-148"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスがないです。</span><span class="sxs-lookup"><span data-stu-id="729ab-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

> [!NOTE]
> <span data-ttu-id="729ab-149">コントロール テンプレートで不確定な表示状態が存在しない場合、チェックを行わない表示状態は、既定の状態として使用します。</span><span class="sxs-lookup"><span data-stu-id="729ab-149">If the Indeterminate visual state does not exist in your control template, then the Unchecked visual state will be used as default visual state.</span></span>

## <a name="togglebutton-controltemplate-example"></a><span data-ttu-id="729ab-150">トグル ボタン ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="729ab-150">ToggleButton ControlTemplate Example</span></span>

<span data-ttu-id="729ab-151">次の例は、定義する方法を示します、<xref:System.Windows.Controls.ControlTemplate>の<xref:System.Windows.Controls.Primitives.ToggleButton>コントロール。</span><span class="sxs-lookup"><span data-stu-id="729ab-151">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>

[!code-xaml[ControlTemplateExamples#ToggleButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#togglebutton)]

<span data-ttu-id="729ab-152">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="729ab-152">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="729ab-153">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="729ab-153">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="729ab-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="729ab-154">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="729ab-155">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="729ab-155">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="729ab-156">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="729ab-156">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="729ab-157">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="729ab-157">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="729ab-158">ControlTemplate の作成による既存のコントロールの外観のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="729ab-158">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
