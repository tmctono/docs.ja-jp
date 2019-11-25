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
ms.openlocfilehash: 4ba90182468466773644c7375059f0cc01675b33
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283458"
---
# <a name="passwordbox-styles-and-templates"></a><span data-ttu-id="6f56b-102">PasswordBox のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="6f56b-102">PasswordBox Styles and Templates</span></span>

<span data-ttu-id="6f56b-103">このトピックでは、<xref:System.Windows.Controls.PasswordBox> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6f56b-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.PasswordBox> control.</span></span> <span data-ttu-id="6f56b-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="6f56b-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="6f56b-105">詳細については、「[コントロールのテンプレートを作成する](../../../desktop-wpf/themes/how-to-create-apply-template.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f56b-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>

## <a name="passwordbox-parts"></a><span data-ttu-id="6f56b-106">PasswordBox のパーツ</span><span class="sxs-lookup"><span data-stu-id="6f56b-106">PasswordBox Parts</span></span>

<span data-ttu-id="6f56b-107">次の表に、<xref:System.Windows.Controls.PasswordBox> コントロールの名前付きの部分を示します。</span><span class="sxs-lookup"><span data-stu-id="6f56b-107">The following table lists the named parts for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

|<span data-ttu-id="6f56b-108">パーツ</span><span class="sxs-lookup"><span data-stu-id="6f56b-108">Part</span></span>|<span data-ttu-id="6f56b-109">[種類]</span><span class="sxs-lookup"><span data-stu-id="6f56b-109">Type</span></span>|<span data-ttu-id="6f56b-110">[説明]</span><span class="sxs-lookup"><span data-stu-id="6f56b-110">Description</span></span>|
|-|-|-|
|<span data-ttu-id="6f56b-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="6f56b-111">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="6f56b-112"><xref:System.Windows.FrameworkElement>を含むことができるビジュアル要素。</span><span class="sxs-lookup"><span data-stu-id="6f56b-112">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="6f56b-113"><xref:System.Windows.Controls.PasswordBox> のテキストがこの要素に表示されます。</span><span class="sxs-lookup"><span data-stu-id="6f56b-113">The text of the <xref:System.Windows.Controls.PasswordBox> is displayed in this element.</span></span>|

## <a name="passwordbox-states"></a><span data-ttu-id="6f56b-114">PasswordBox の状態</span><span class="sxs-lookup"><span data-stu-id="6f56b-114">PasswordBox States</span></span>

<span data-ttu-id="6f56b-115">次の表は、<xref:System.Windows.Controls.PasswordBox> コントロールの表示状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="6f56b-115">The following table lists the visual states for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

|<span data-ttu-id="6f56b-116">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="6f56b-116">VisualState Name</span></span>|<span data-ttu-id="6f56b-117">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="6f56b-117">VisualStateGroup Name</span></span>|<span data-ttu-id="6f56b-118">[説明]</span><span class="sxs-lookup"><span data-stu-id="6f56b-118">Description</span></span>|
|-|-|-|
|<span data-ttu-id="6f56b-119">標準</span><span class="sxs-lookup"><span data-stu-id="6f56b-119">Normal</span></span>|<span data-ttu-id="6f56b-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="6f56b-120">CommonStates</span></span>|<span data-ttu-id="6f56b-121">既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="6f56b-121">The default state.</span></span>|
|<span data-ttu-id="6f56b-122">MouseOver</span><span class="sxs-lookup"><span data-stu-id="6f56b-122">MouseOver</span></span>|<span data-ttu-id="6f56b-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="6f56b-123">CommonStates</span></span>|<span data-ttu-id="6f56b-124">マウス ポインターがコントロール上に配置されます。</span><span class="sxs-lookup"><span data-stu-id="6f56b-124">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="6f56b-125">Disabled</span><span class="sxs-lookup"><span data-stu-id="6f56b-125">Disabled</span></span>|<span data-ttu-id="6f56b-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="6f56b-126">CommonStates</span></span>|<span data-ttu-id="6f56b-127">コントロールが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="6f56b-127">The control is disabled.</span></span>|
|<span data-ttu-id="6f56b-128">フォーカスされている</span><span class="sxs-lookup"><span data-stu-id="6f56b-128">Focused</span></span>|<span data-ttu-id="6f56b-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="6f56b-129">FocusStates</span></span>|<span data-ttu-id="6f56b-130">コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="6f56b-130">The control has focus.</span></span>|
|<span data-ttu-id="6f56b-131">フォーカスされていない</span><span class="sxs-lookup"><span data-stu-id="6f56b-131">Unfocused</span></span>|<span data-ttu-id="6f56b-132">FocusStates</span><span class="sxs-lookup"><span data-stu-id="6f56b-132">FocusStates</span></span>|<span data-ttu-id="6f56b-133">コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="6f56b-133">The control does not have focus.</span></span>|
|<span data-ttu-id="6f56b-134">有効</span><span class="sxs-lookup"><span data-stu-id="6f56b-134">Valid</span></span>|<span data-ttu-id="6f56b-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6f56b-135">ValidationStates</span></span>|<span data-ttu-id="6f56b-136">コントロールは <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false`ます。</span><span class="sxs-lookup"><span data-stu-id="6f56b-136">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="6f56b-137">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="6f56b-137">InvalidFocused</span></span>|<span data-ttu-id="6f56b-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6f56b-138">ValidationStates</span></span>|<span data-ttu-id="6f56b-139"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがある `true` です。</span><span class="sxs-lookup"><span data-stu-id="6f56b-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="6f56b-140">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="6f56b-140">InvalidUnfocused</span></span>|<span data-ttu-id="6f56b-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6f56b-141">ValidationStates</span></span>|<span data-ttu-id="6f56b-142"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがない `true` です。</span><span class="sxs-lookup"><span data-stu-id="6f56b-142">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="passwordbox-controltemplate-example"></a><span data-ttu-id="6f56b-143">PasswordBox ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="6f56b-143">PasswordBox ControlTemplate Example</span></span>

<span data-ttu-id="6f56b-144">次の例は、<xref:System.Windows.Controls.PasswordBox> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="6f56b-144">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

[!code-xaml[ControlTemplateExamples#PasswordBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#passwordbox)]

<span data-ttu-id="6f56b-145">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="6f56b-145">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="6f56b-146">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f56b-146">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="6f56b-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="6f56b-147">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="6f56b-148">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="6f56b-148">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="6f56b-149">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="6f56b-149">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="6f56b-150">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="6f56b-150">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="6f56b-151">コントロールのテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="6f56b-151">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
