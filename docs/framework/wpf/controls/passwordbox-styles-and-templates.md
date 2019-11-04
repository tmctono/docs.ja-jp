---
title: PasswordBox のスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], PasswordBox
- templates [WPF], PasswordBox
- ControlTemplate [WPF], PasswordBox
- states [WPF], PasswordBox
- PasswordBox [WPF], styles and templates
- parts [WPF], PasswordBox
ms.assetid: deb52107-959f-4a60-b303-d21a0a933060
ms.openlocfilehash: 227ccbda8d570868258508935a5d95f0f40663ab
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458841"
---
# <a name="passwordbox-styles-and-templates"></a><span data-ttu-id="f040d-102">PasswordBox のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="f040d-102">PasswordBox Styles and Templates</span></span>

<span data-ttu-id="f040d-103">このトピックでは、<xref:System.Windows.Controls.PasswordBox> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f040d-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.PasswordBox> control.</span></span> <span data-ttu-id="f040d-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="f040d-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="f040d-105">詳細については、「[Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f040d-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>

## <a name="passwordbox-parts"></a><span data-ttu-id="f040d-106">PasswordBox のパーツ</span><span class="sxs-lookup"><span data-stu-id="f040d-106">PasswordBox Parts</span></span>

<span data-ttu-id="f040d-107">次の表に、<xref:System.Windows.Controls.PasswordBox> コントロールの名前付きの部分を示します。</span><span class="sxs-lookup"><span data-stu-id="f040d-107">The following table lists the named parts for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

|<span data-ttu-id="f040d-108">パーツ</span><span class="sxs-lookup"><span data-stu-id="f040d-108">Part</span></span>|<span data-ttu-id="f040d-109">[種類]</span><span class="sxs-lookup"><span data-stu-id="f040d-109">Type</span></span>|<span data-ttu-id="f040d-110">説明</span><span class="sxs-lookup"><span data-stu-id="f040d-110">Description</span></span>|
|-|-|-|
|<span data-ttu-id="f040d-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="f040d-111">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="f040d-112"><xref:System.Windows.FrameworkElement>を含むことができるビジュアル要素。</span><span class="sxs-lookup"><span data-stu-id="f040d-112">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="f040d-113"><xref:System.Windows.Controls.PasswordBox> のテキストがこの要素に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f040d-113">The text of the <xref:System.Windows.Controls.PasswordBox> is displayed in this element.</span></span>|

## <a name="passwordbox-states"></a><span data-ttu-id="f040d-114">PasswordBox の状態</span><span class="sxs-lookup"><span data-stu-id="f040d-114">PasswordBox States</span></span>

<span data-ttu-id="f040d-115">次の表は、<xref:System.Windows.Controls.PasswordBox> コントロールの表示状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="f040d-115">The following table lists the visual states for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

|<span data-ttu-id="f040d-116">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="f040d-116">VisualState Name</span></span>|<span data-ttu-id="f040d-117">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="f040d-117">VisualStateGroup Name</span></span>|<span data-ttu-id="f040d-118">説明</span><span class="sxs-lookup"><span data-stu-id="f040d-118">Description</span></span>|
|-|-|-|
|<span data-ttu-id="f040d-119">標準</span><span class="sxs-lookup"><span data-stu-id="f040d-119">Normal</span></span>|<span data-ttu-id="f040d-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="f040d-120">CommonStates</span></span>|<span data-ttu-id="f040d-121">既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="f040d-121">The default state.</span></span>|
|<span data-ttu-id="f040d-122">MouseOver</span><span class="sxs-lookup"><span data-stu-id="f040d-122">MouseOver</span></span>|<span data-ttu-id="f040d-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="f040d-123">CommonStates</span></span>|<span data-ttu-id="f040d-124">マウス ポインターがコントロール上に配置されます。</span><span class="sxs-lookup"><span data-stu-id="f040d-124">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="f040d-125">Disabled</span><span class="sxs-lookup"><span data-stu-id="f040d-125">Disabled</span></span>|<span data-ttu-id="f040d-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="f040d-126">CommonStates</span></span>|<span data-ttu-id="f040d-127">コントロールが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="f040d-127">The control is disabled.</span></span>|
|<span data-ttu-id="f040d-128">フォーカスされている</span><span class="sxs-lookup"><span data-stu-id="f040d-128">Focused</span></span>|<span data-ttu-id="f040d-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="f040d-129">FocusStates</span></span>|<span data-ttu-id="f040d-130">コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="f040d-130">The control has focus.</span></span>|
|<span data-ttu-id="f040d-131">フォーカスされていない</span><span class="sxs-lookup"><span data-stu-id="f040d-131">Unfocused</span></span>|<span data-ttu-id="f040d-132">FocusStates</span><span class="sxs-lookup"><span data-stu-id="f040d-132">FocusStates</span></span>|<span data-ttu-id="f040d-133">コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="f040d-133">The control does not have focus.</span></span>|
|<span data-ttu-id="f040d-134">有効</span><span class="sxs-lookup"><span data-stu-id="f040d-134">Valid</span></span>|<span data-ttu-id="f040d-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f040d-135">ValidationStates</span></span>|<span data-ttu-id="f040d-136">コントロールは <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false`ます。</span><span class="sxs-lookup"><span data-stu-id="f040d-136">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="f040d-137">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="f040d-137">InvalidFocused</span></span>|<span data-ttu-id="f040d-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f040d-138">ValidationStates</span></span>|<span data-ttu-id="f040d-139"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがある `true` です。</span><span class="sxs-lookup"><span data-stu-id="f040d-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="f040d-140">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="f040d-140">InvalidUnfocused</span></span>|<span data-ttu-id="f040d-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f040d-141">ValidationStates</span></span>|<span data-ttu-id="f040d-142"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがない `true` です。</span><span class="sxs-lookup"><span data-stu-id="f040d-142">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="passwordbox-controltemplate-example"></a><span data-ttu-id="f040d-143">PasswordBox ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="f040d-143">PasswordBox ControlTemplate Example</span></span>

<span data-ttu-id="f040d-144">次の例は、<xref:System.Windows.Controls.PasswordBox> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f040d-144">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

[!code-xaml[ControlTemplateExamples#PasswordBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#passwordbox)]

<span data-ttu-id="f040d-145">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="f040d-145">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="f040d-146">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f040d-146">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="f040d-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="f040d-147">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="f040d-148">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="f040d-148">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="f040d-149">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="f040d-149">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="f040d-150">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="f040d-150">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="f040d-151">ControlTemplate の作成による既存のコントロールの外観のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="f040d-151">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
