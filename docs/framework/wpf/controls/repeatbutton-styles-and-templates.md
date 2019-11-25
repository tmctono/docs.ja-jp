---
title: RepeatButton のスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatButton [WPF], styles and templates
- styles [WPF], RepeatButton
- templates [WPF], RepeatButton
- parts [WPF], RepeatButton
- ControlTemplate [WPF], RepeatButton
- states [WPF], RepeatButton
ms.assetid: fd340743-f44f-4990-9077-085301469670
ms.openlocfilehash: 8585e98536fd908daa11f21da395cab44924d612
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283426"
---
# <a name="repeatbutton-styles-and-templates"></a><span data-ttu-id="9674e-102">RepeatButton のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="9674e-102">RepeatButton Styles and Templates</span></span>

<span data-ttu-id="9674e-103">このトピックでは、<xref:System.Windows.Controls.Primitives.RepeatButton> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9674e-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span> <span data-ttu-id="9674e-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="9674e-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="9674e-105">詳細については、「[コントロールのテンプレートを作成する](../../../desktop-wpf/themes/how-to-create-apply-template.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9674e-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>

## <a name="repeatbutton-parts"></a><span data-ttu-id="9674e-106">RepeatButton パーツ</span><span class="sxs-lookup"><span data-stu-id="9674e-106">RepeatButton Parts</span></span>

<span data-ttu-id="9674e-107"><xref:System.Windows.Controls.Primitives.RepeatButton> コントロールには、名前付きの部分がありません。</span><span class="sxs-lookup"><span data-stu-id="9674e-107">The <xref:System.Windows.Controls.Primitives.RepeatButton> control does not have any named parts.</span></span>

## <a name="repeatbutton-states"></a><span data-ttu-id="9674e-108">RepeatButton の状態</span><span class="sxs-lookup"><span data-stu-id="9674e-108">RepeatButton States</span></span>

<span data-ttu-id="9674e-109">次の表は、<xref:System.Windows.Controls.Primitives.RepeatButton> コントロールの表示状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="9674e-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span>

|<span data-ttu-id="9674e-110">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="9674e-110">VisualState Name</span></span>|<span data-ttu-id="9674e-111">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="9674e-111">VisualStateGroup Name</span></span>|<span data-ttu-id="9674e-112">[説明]</span><span class="sxs-lookup"><span data-stu-id="9674e-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="9674e-113">標準</span><span class="sxs-lookup"><span data-stu-id="9674e-113">Normal</span></span>|<span data-ttu-id="9674e-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="9674e-114">CommonStates</span></span>|<span data-ttu-id="9674e-115">既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="9674e-115">The default state.</span></span>|
|<span data-ttu-id="9674e-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="9674e-116">MouseOver</span></span>|<span data-ttu-id="9674e-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="9674e-117">CommonStates</span></span>|<span data-ttu-id="9674e-118">マウス ポインターがコントロール上に配置されます。</span><span class="sxs-lookup"><span data-stu-id="9674e-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="9674e-119">押されている</span><span class="sxs-lookup"><span data-stu-id="9674e-119">Pressed</span></span>|<span data-ttu-id="9674e-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="9674e-120">CommonStates</span></span>|<span data-ttu-id="9674e-121">コントロールが押されています。</span><span class="sxs-lookup"><span data-stu-id="9674e-121">The control is pressed.</span></span>|
|<span data-ttu-id="9674e-122">Disabled</span><span class="sxs-lookup"><span data-stu-id="9674e-122">Disabled</span></span>|<span data-ttu-id="9674e-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="9674e-123">CommonStates</span></span>|<span data-ttu-id="9674e-124">コントロールが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="9674e-124">The control is disabled.</span></span>|
|<span data-ttu-id="9674e-125">フォーカスされている</span><span class="sxs-lookup"><span data-stu-id="9674e-125">Focused</span></span>|<span data-ttu-id="9674e-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="9674e-126">FocusStates</span></span>|<span data-ttu-id="9674e-127">コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="9674e-127">The control has focus.</span></span>|
|<span data-ttu-id="9674e-128">フォーカスされていない</span><span class="sxs-lookup"><span data-stu-id="9674e-128">Unfocused</span></span>|<span data-ttu-id="9674e-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="9674e-129">FocusStates</span></span>|<span data-ttu-id="9674e-130">コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="9674e-130">The control does not have focus.</span></span>|
|<span data-ttu-id="9674e-131">有効</span><span class="sxs-lookup"><span data-stu-id="9674e-131">Valid</span></span>|<span data-ttu-id="9674e-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9674e-132">ValidationStates</span></span>|<span data-ttu-id="9674e-133">コントロールは <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false`ます。</span><span class="sxs-lookup"><span data-stu-id="9674e-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="9674e-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="9674e-134">InvalidFocused</span></span>|<span data-ttu-id="9674e-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9674e-135">ValidationStates</span></span>|<span data-ttu-id="9674e-136"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがある `true` です。</span><span class="sxs-lookup"><span data-stu-id="9674e-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="9674e-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="9674e-137">InvalidUnfocused</span></span>|<span data-ttu-id="9674e-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9674e-138">ValidationStates</span></span>|<span data-ttu-id="9674e-139"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがない `true` です。</span><span class="sxs-lookup"><span data-stu-id="9674e-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="repeatbutton-controltemplate-example"></a><span data-ttu-id="9674e-140">RepeatButton ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="9674e-140">RepeatButton ControlTemplate Example</span></span>

<span data-ttu-id="9674e-141">次の例は、<xref:System.Windows.Controls.Primitives.RepeatButton> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="9674e-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span>

[!code-xaml[ControlTemplateExamples#RepeatButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#repeatbutton)]

<span data-ttu-id="9674e-142">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="9674e-142">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="9674e-143">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9674e-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="9674e-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="9674e-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="9674e-145">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="9674e-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="9674e-146">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="9674e-146">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="9674e-147">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="9674e-147">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="9674e-148">コントロールのテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="9674e-148">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
