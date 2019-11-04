---
title: つまみのスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], Thumb
- styles [WPF], Thumb
- templates [WPF], Thumb
- Thumb [WPF], styles and templates
- ControlTemplate [WPF], Thumb
- parts [WPF], Thumb
ms.assetid: 86a49235-62d9-414e-923e-53126e3f930a
ms.openlocfilehash: c2114a02016db96d898a394b6892b6d3042d81ff
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458240"
---
# <a name="thumb-styles-and-templates"></a><span data-ttu-id="22124-102">つまみのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="22124-102">Thumb Styles and Templates</span></span>

<span data-ttu-id="22124-103">このトピックでは、<xref:System.Windows.Controls.Primitives.Thumb> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="22124-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span> <span data-ttu-id="22124-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="22124-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="22124-105">詳細については、「[Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22124-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>

## <a name="thumb-parts"></a><span data-ttu-id="22124-106">Thumb パーツ</span><span class="sxs-lookup"><span data-stu-id="22124-106">Thumb Parts</span></span>

<span data-ttu-id="22124-107"><xref:System.Windows.Controls.Primitives.Thumb> コントロールには、名前付きの部分がありません。</span><span class="sxs-lookup"><span data-stu-id="22124-107">The <xref:System.Windows.Controls.Primitives.Thumb> control does not have any named parts.</span></span>

## <a name="thumb-states"></a><span data-ttu-id="22124-108">Thumb の状態</span><span class="sxs-lookup"><span data-stu-id="22124-108">Thumb States</span></span>

<span data-ttu-id="22124-109">次の表は、<xref:System.Windows.Controls.Primitives.Thumb> コントロールの表示状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="22124-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span>

|<span data-ttu-id="22124-110">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="22124-110">VisualState Name</span></span>|<span data-ttu-id="22124-111">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="22124-111">VisualStateGroup Name</span></span>|<span data-ttu-id="22124-112">説明</span><span class="sxs-lookup"><span data-stu-id="22124-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="22124-113">標準</span><span class="sxs-lookup"><span data-stu-id="22124-113">Normal</span></span>|<span data-ttu-id="22124-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="22124-114">CommonStates</span></span>|<span data-ttu-id="22124-115">既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="22124-115">The default state.</span></span>|
|<span data-ttu-id="22124-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="22124-116">MouseOver</span></span>|<span data-ttu-id="22124-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="22124-117">CommonStates</span></span>|<span data-ttu-id="22124-118">マウス ポインターがコントロール上に配置されます。</span><span class="sxs-lookup"><span data-stu-id="22124-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="22124-119">押されている</span><span class="sxs-lookup"><span data-stu-id="22124-119">Pressed</span></span>|<span data-ttu-id="22124-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="22124-120">CommonStates</span></span>|<span data-ttu-id="22124-121">コントロールが押されています。</span><span class="sxs-lookup"><span data-stu-id="22124-121">The control is pressed.</span></span>|
|<span data-ttu-id="22124-122">Disabled</span><span class="sxs-lookup"><span data-stu-id="22124-122">Disabled</span></span>|<span data-ttu-id="22124-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="22124-123">CommonStates</span></span>|<span data-ttu-id="22124-124">コントロールが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="22124-124">The control is disabled.</span></span>|
|<span data-ttu-id="22124-125">フォーカスされている</span><span class="sxs-lookup"><span data-stu-id="22124-125">Focused</span></span>|<span data-ttu-id="22124-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="22124-126">FocusStates</span></span>|<span data-ttu-id="22124-127">コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="22124-127">The control has focus.</span></span>|
|<span data-ttu-id="22124-128">フォーカスされていない</span><span class="sxs-lookup"><span data-stu-id="22124-128">Unfocused</span></span>|<span data-ttu-id="22124-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="22124-129">FocusStates</span></span>|<span data-ttu-id="22124-130">コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="22124-130">The control does not have focus.</span></span>|
|<span data-ttu-id="22124-131">有効</span><span class="sxs-lookup"><span data-stu-id="22124-131">Valid</span></span>|<span data-ttu-id="22124-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="22124-132">ValidationStates</span></span>|<span data-ttu-id="22124-133">コントロールは <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false`ます。</span><span class="sxs-lookup"><span data-stu-id="22124-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="22124-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="22124-134">InvalidFocused</span></span>|<span data-ttu-id="22124-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="22124-135">ValidationStates</span></span>|<span data-ttu-id="22124-136"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがある `true` です。</span><span class="sxs-lookup"><span data-stu-id="22124-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="22124-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="22124-137">InvalidUnfocused</span></span>|<span data-ttu-id="22124-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="22124-138">ValidationStates</span></span>|<span data-ttu-id="22124-139"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがない `true` です。</span><span class="sxs-lookup"><span data-stu-id="22124-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="thumb-controltemplate-example"></a><span data-ttu-id="22124-140">Thumb ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="22124-140">Thumb ControlTemplate Example</span></span>

<span data-ttu-id="22124-141">次の例は、<xref:System.Windows.Controls.Primitives.Thumb> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="22124-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span>

[!code-xaml[ControlTemplateExamples#Thumb](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/slider.xaml#thumb)]

<span data-ttu-id="22124-142">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="22124-142">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="22124-143">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22124-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="22124-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="22124-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="22124-145">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="22124-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="22124-146">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="22124-146">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="22124-147">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="22124-147">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="22124-148">ControlTemplate の作成による既存のコントロールの外観のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="22124-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
