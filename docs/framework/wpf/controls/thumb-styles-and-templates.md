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
ms.openlocfilehash: 0d0d88e3b527beacfa5f879027e696aa75b18147
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283688"
---
# <a name="thumb-styles-and-templates"></a><span data-ttu-id="5bdd2-102">つまみのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="5bdd2-102">Thumb Styles and Templates</span></span>

<span data-ttu-id="5bdd2-103">このトピックでは、<xref:System.Windows.Controls.Primitives.Thumb> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5bdd2-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span> <span data-ttu-id="5bdd2-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="5bdd2-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="5bdd2-105">詳細については、「[コントロールのためにテンプレートを作成する](../../../desktop-wpf/themes/how-to-create-apply-template.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5bdd2-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>

## <a name="thumb-parts"></a><span data-ttu-id="5bdd2-106">Thumb のパーツ</span><span class="sxs-lookup"><span data-stu-id="5bdd2-106">Thumb Parts</span></span>

<span data-ttu-id="5bdd2-107"><xref:System.Windows.Controls.Primitives.Thumb> コントロールに名前付きパーツはありません。</span><span class="sxs-lookup"><span data-stu-id="5bdd2-107">The <xref:System.Windows.Controls.Primitives.Thumb> control does not have any named parts.</span></span>

## <a name="thumb-states"></a><span data-ttu-id="5bdd2-108">Thumb の状態</span><span class="sxs-lookup"><span data-stu-id="5bdd2-108">Thumb States</span></span>

<span data-ttu-id="5bdd2-109">次の表は、<xref:System.Windows.Controls.Primitives.Thumb> コントロールの表示状態の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="5bdd2-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span>

|<span data-ttu-id="5bdd2-110">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="5bdd2-110">VisualState Name</span></span>|<span data-ttu-id="5bdd2-111">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="5bdd2-111">VisualStateGroup Name</span></span>|<span data-ttu-id="5bdd2-112">説明</span><span class="sxs-lookup"><span data-stu-id="5bdd2-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="5bdd2-113">標準</span><span class="sxs-lookup"><span data-stu-id="5bdd2-113">Normal</span></span>|<span data-ttu-id="5bdd2-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="5bdd2-114">CommonStates</span></span>|<span data-ttu-id="5bdd2-115">既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="5bdd2-115">The default state.</span></span>|
|<span data-ttu-id="5bdd2-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="5bdd2-116">MouseOver</span></span>|<span data-ttu-id="5bdd2-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="5bdd2-117">CommonStates</span></span>|<span data-ttu-id="5bdd2-118">マウス ポインターがコントロール上に配置されています。</span><span class="sxs-lookup"><span data-stu-id="5bdd2-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="5bdd2-119">押されている</span><span class="sxs-lookup"><span data-stu-id="5bdd2-119">Pressed</span></span>|<span data-ttu-id="5bdd2-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="5bdd2-120">CommonStates</span></span>|<span data-ttu-id="5bdd2-121">コントロールが押されています。</span><span class="sxs-lookup"><span data-stu-id="5bdd2-121">The control is pressed.</span></span>|
|<span data-ttu-id="5bdd2-122">無効</span><span class="sxs-lookup"><span data-stu-id="5bdd2-122">Disabled</span></span>|<span data-ttu-id="5bdd2-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="5bdd2-123">CommonStates</span></span>|<span data-ttu-id="5bdd2-124">コントロールが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="5bdd2-124">The control is disabled.</span></span>|
|<span data-ttu-id="5bdd2-125">フォーカスされている</span><span class="sxs-lookup"><span data-stu-id="5bdd2-125">Focused</span></span>|<span data-ttu-id="5bdd2-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="5bdd2-126">FocusStates</span></span>|<span data-ttu-id="5bdd2-127">コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="5bdd2-127">The control has focus.</span></span>|
|<span data-ttu-id="5bdd2-128">フォーカスされていない</span><span class="sxs-lookup"><span data-stu-id="5bdd2-128">Unfocused</span></span>|<span data-ttu-id="5bdd2-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="5bdd2-129">FocusStates</span></span>|<span data-ttu-id="5bdd2-130">コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="5bdd2-130">The control does not have focus.</span></span>|
|<span data-ttu-id="5bdd2-131">有効</span><span class="sxs-lookup"><span data-stu-id="5bdd2-131">Valid</span></span>|<span data-ttu-id="5bdd2-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5bdd2-132">ValidationStates</span></span>|<span data-ttu-id="5bdd2-133">このコントロールで <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false` です。</span><span class="sxs-lookup"><span data-stu-id="5bdd2-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="5bdd2-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="5bdd2-134">InvalidFocused</span></span>|<span data-ttu-id="5bdd2-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5bdd2-135">ValidationStates</span></span>|<span data-ttu-id="5bdd2-136"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがある `true` です。</span><span class="sxs-lookup"><span data-stu-id="5bdd2-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="5bdd2-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="5bdd2-137">InvalidUnfocused</span></span>|<span data-ttu-id="5bdd2-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5bdd2-138">ValidationStates</span></span>|<span data-ttu-id="5bdd2-139"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがない `true` です。</span><span class="sxs-lookup"><span data-stu-id="5bdd2-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="thumb-controltemplate-example"></a><span data-ttu-id="5bdd2-140">Thumb の ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="5bdd2-140">Thumb ControlTemplate Example</span></span>

<span data-ttu-id="5bdd2-141">次の例は、<xref:System.Windows.Controls.Primitives.Thumb> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="5bdd2-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span>

[!code-xaml[ControlTemplateExamples#Thumb](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/slider.xaml#thumb)]

<span data-ttu-id="5bdd2-142">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="5bdd2-142">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="5bdd2-143">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5bdd2-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="5bdd2-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="5bdd2-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="5bdd2-145">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="5bdd2-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="5bdd2-146">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="5bdd2-146">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="5bdd2-147">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="5bdd2-147">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="5bdd2-148">コントロールのためのテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="5bdd2-148">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
