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
ms.openlocfilehash: 9c6a8ad0a954d244fb693e25965ab52dda114068
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459852"
---
# <a name="repeatbutton-styles-and-templates"></a><span data-ttu-id="a5869-102">RepeatButton のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="a5869-102">RepeatButton Styles and Templates</span></span>

<span data-ttu-id="a5869-103">このトピックでは、<xref:System.Windows.Controls.Primitives.RepeatButton> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a5869-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span> <span data-ttu-id="a5869-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="a5869-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="a5869-105">詳細については、「[Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5869-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>

## <a name="repeatbutton-parts"></a><span data-ttu-id="a5869-106">RepeatButton パーツ</span><span class="sxs-lookup"><span data-stu-id="a5869-106">RepeatButton Parts</span></span>

<span data-ttu-id="a5869-107"><xref:System.Windows.Controls.Primitives.RepeatButton> コントロールには、名前付きの部分がありません。</span><span class="sxs-lookup"><span data-stu-id="a5869-107">The <xref:System.Windows.Controls.Primitives.RepeatButton> control does not have any named parts.</span></span>

## <a name="repeatbutton-states"></a><span data-ttu-id="a5869-108">RepeatButton の状態</span><span class="sxs-lookup"><span data-stu-id="a5869-108">RepeatButton States</span></span>

<span data-ttu-id="a5869-109">次の表は、<xref:System.Windows.Controls.Primitives.RepeatButton> コントロールの表示状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="a5869-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span>

|<span data-ttu-id="a5869-110">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="a5869-110">VisualState Name</span></span>|<span data-ttu-id="a5869-111">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="a5869-111">VisualStateGroup Name</span></span>|<span data-ttu-id="a5869-112">説明</span><span class="sxs-lookup"><span data-stu-id="a5869-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="a5869-113">標準</span><span class="sxs-lookup"><span data-stu-id="a5869-113">Normal</span></span>|<span data-ttu-id="a5869-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a5869-114">CommonStates</span></span>|<span data-ttu-id="a5869-115">既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="a5869-115">The default state.</span></span>|
|<span data-ttu-id="a5869-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="a5869-116">MouseOver</span></span>|<span data-ttu-id="a5869-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a5869-117">CommonStates</span></span>|<span data-ttu-id="a5869-118">マウス ポインターがコントロール上に配置されます。</span><span class="sxs-lookup"><span data-stu-id="a5869-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="a5869-119">押されている</span><span class="sxs-lookup"><span data-stu-id="a5869-119">Pressed</span></span>|<span data-ttu-id="a5869-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a5869-120">CommonStates</span></span>|<span data-ttu-id="a5869-121">コントロールが押されています。</span><span class="sxs-lookup"><span data-stu-id="a5869-121">The control is pressed.</span></span>|
|<span data-ttu-id="a5869-122">Disabled</span><span class="sxs-lookup"><span data-stu-id="a5869-122">Disabled</span></span>|<span data-ttu-id="a5869-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a5869-123">CommonStates</span></span>|<span data-ttu-id="a5869-124">コントロールが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="a5869-124">The control is disabled.</span></span>|
|<span data-ttu-id="a5869-125">フォーカスされている</span><span class="sxs-lookup"><span data-stu-id="a5869-125">Focused</span></span>|<span data-ttu-id="a5869-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="a5869-126">FocusStates</span></span>|<span data-ttu-id="a5869-127">コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="a5869-127">The control has focus.</span></span>|
|<span data-ttu-id="a5869-128">フォーカスされていない</span><span class="sxs-lookup"><span data-stu-id="a5869-128">Unfocused</span></span>|<span data-ttu-id="a5869-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="a5869-129">FocusStates</span></span>|<span data-ttu-id="a5869-130">コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="a5869-130">The control does not have focus.</span></span>|
|<span data-ttu-id="a5869-131">有効</span><span class="sxs-lookup"><span data-stu-id="a5869-131">Valid</span></span>|<span data-ttu-id="a5869-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a5869-132">ValidationStates</span></span>|<span data-ttu-id="a5869-133">コントロールは <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false`ます。</span><span class="sxs-lookup"><span data-stu-id="a5869-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="a5869-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="a5869-134">InvalidFocused</span></span>|<span data-ttu-id="a5869-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a5869-135">ValidationStates</span></span>|<span data-ttu-id="a5869-136"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがある `true` です。</span><span class="sxs-lookup"><span data-stu-id="a5869-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="a5869-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="a5869-137">InvalidUnfocused</span></span>|<span data-ttu-id="a5869-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a5869-138">ValidationStates</span></span>|<span data-ttu-id="a5869-139"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがない `true` です。</span><span class="sxs-lookup"><span data-stu-id="a5869-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="repeatbutton-controltemplate-example"></a><span data-ttu-id="a5869-140">RepeatButton ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="a5869-140">RepeatButton ControlTemplate Example</span></span>

<span data-ttu-id="a5869-141">次の例は、<xref:System.Windows.Controls.Primitives.RepeatButton> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a5869-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span>

[!code-xaml[ControlTemplateExamples#RepeatButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#repeatbutton)]

<span data-ttu-id="a5869-142">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="a5869-142">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="a5869-143">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5869-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="a5869-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="a5869-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="a5869-145">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="a5869-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="a5869-146">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="a5869-146">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="a5869-147">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="a5869-147">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="a5869-148">ControlTemplate の作成による既存のコントロールの外観のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="a5869-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
