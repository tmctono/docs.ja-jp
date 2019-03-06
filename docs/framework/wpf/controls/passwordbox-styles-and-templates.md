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
ms.openlocfilehash: 7783330dd56ec5b2759e783a6935761eb3587978
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57509531"
---
# <a name="passwordbox-styles-and-templates"></a><span data-ttu-id="528a9-102">PasswordBox のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="528a9-102">PasswordBox Styles and Templates</span></span>

<span data-ttu-id="528a9-103">このトピックでは、スタイルとテンプレートについて説明します、<xref:System.Windows.Controls.PasswordBox>コントロール。</span><span class="sxs-lookup"><span data-stu-id="528a9-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.PasswordBox> control.</span></span> <span data-ttu-id="528a9-104">既定値を変更する<xref:System.Windows.Controls.ControlTemplate>固有の外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="528a9-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="528a9-105">詳細については、「[ControlTemplate の作成による既存のコントロールの外観のカスタマイズ](customizing-the-appearance-of-an-existing-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="528a9-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>

## <a name="passwordbox-parts"></a><span data-ttu-id="528a9-106">PasswordBox のパーツ</span><span class="sxs-lookup"><span data-stu-id="528a9-106">PasswordBox Parts</span></span>

<span data-ttu-id="528a9-107">次の表に、名前付きパーツ、<xref:System.Windows.Controls.PasswordBox>コントロール。</span><span class="sxs-lookup"><span data-stu-id="528a9-107">The following table lists the named parts for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

|<span data-ttu-id="528a9-108">パーツ</span><span class="sxs-lookup"><span data-stu-id="528a9-108">Part</span></span>|<span data-ttu-id="528a9-109">型</span><span class="sxs-lookup"><span data-stu-id="528a9-109">Type</span></span>|<span data-ttu-id="528a9-110">説明</span><span class="sxs-lookup"><span data-stu-id="528a9-110">Description</span></span>|
|-|-|-|
|<span data-ttu-id="528a9-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="528a9-111">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="528a9-112">ビジュアル要素を含めることができます、<xref:System.Windows.FrameworkElement>します。</span><span class="sxs-lookup"><span data-stu-id="528a9-112">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="528a9-113">テキスト、<xref:System.Windows.Controls.PasswordBox>がこの要素に表示されます。</span><span class="sxs-lookup"><span data-stu-id="528a9-113">The text of the <xref:System.Windows.Controls.PasswordBox> is displayed in this element.</span></span>|

## <a name="passwordbox-states"></a><span data-ttu-id="528a9-114">PasswordBox の状態</span><span class="sxs-lookup"><span data-stu-id="528a9-114">PasswordBox States</span></span>

<span data-ttu-id="528a9-115">次の表のビジュアルの状態、<xref:System.Windows.Controls.PasswordBox>コントロール。</span><span class="sxs-lookup"><span data-stu-id="528a9-115">The following table lists the visual states for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

|<span data-ttu-id="528a9-116">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="528a9-116">VisualState Name</span></span>|<span data-ttu-id="528a9-117">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="528a9-117">VisualStateGroup Name</span></span>|<span data-ttu-id="528a9-118">説明</span><span class="sxs-lookup"><span data-stu-id="528a9-118">Description</span></span>|
|-|-|-|
|<span data-ttu-id="528a9-119">標準</span><span class="sxs-lookup"><span data-stu-id="528a9-119">Normal</span></span>|<span data-ttu-id="528a9-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="528a9-120">CommonStates</span></span>|<span data-ttu-id="528a9-121">既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="528a9-121">The default state.</span></span>|
|<span data-ttu-id="528a9-122">MouseOver</span><span class="sxs-lookup"><span data-stu-id="528a9-122">MouseOver</span></span>|<span data-ttu-id="528a9-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="528a9-123">CommonStates</span></span>|<span data-ttu-id="528a9-124">マウス ポインターがコントロール上に配置されます。</span><span class="sxs-lookup"><span data-stu-id="528a9-124">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="528a9-125">無効</span><span class="sxs-lookup"><span data-stu-id="528a9-125">Disabled</span></span>|<span data-ttu-id="528a9-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="528a9-126">CommonStates</span></span>|<span data-ttu-id="528a9-127">コントロールが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="528a9-127">The control is disabled.</span></span>|
|<span data-ttu-id="528a9-128">フォーカスされている</span><span class="sxs-lookup"><span data-stu-id="528a9-128">Focused</span></span>|<span data-ttu-id="528a9-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="528a9-129">FocusStates</span></span>|<span data-ttu-id="528a9-130">コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="528a9-130">The control has focus.</span></span>|
|<span data-ttu-id="528a9-131">フォーカスされていない</span><span class="sxs-lookup"><span data-stu-id="528a9-131">Unfocused</span></span>|<span data-ttu-id="528a9-132">FocusStates</span><span class="sxs-lookup"><span data-stu-id="528a9-132">FocusStates</span></span>|<span data-ttu-id="528a9-133">コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="528a9-133">The control does not have focus.</span></span>|
|<span data-ttu-id="528a9-134">有効</span><span class="sxs-lookup"><span data-stu-id="528a9-134">Valid</span></span>|<span data-ttu-id="528a9-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="528a9-135">ValidationStates</span></span>|<span data-ttu-id="528a9-136">コントロールを使用して、<xref:System.Windows.Controls.Validation>クラスおよび<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`false`します。</span><span class="sxs-lookup"><span data-stu-id="528a9-136">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="528a9-137">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="528a9-137">InvalidFocused</span></span>|<span data-ttu-id="528a9-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="528a9-138">ValidationStates</span></span>|<span data-ttu-id="528a9-139"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="528a9-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="528a9-140">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="528a9-140">InvalidUnfocused</span></span>|<span data-ttu-id="528a9-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="528a9-141">ValidationStates</span></span>|<span data-ttu-id="528a9-142"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスがないです。</span><span class="sxs-lookup"><span data-stu-id="528a9-142">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="passwordbox-controltemplate-example"></a><span data-ttu-id="528a9-143">PasswordBox ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="528a9-143">PasswordBox ControlTemplate Example</span></span>

<span data-ttu-id="528a9-144">次の例は、定義する方法を示します、<xref:System.Windows.Controls.ControlTemplate>の<xref:System.Windows.Controls.PasswordBox>コントロール。</span><span class="sxs-lookup"><span data-stu-id="528a9-144">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

[!code-xaml[ControlTemplateExamples#PasswordBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#passwordbox)]

<span data-ttu-id="528a9-145">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="528a9-145">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="528a9-146">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="528a9-146">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="528a9-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="528a9-147">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="528a9-148">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="528a9-148">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="528a9-149">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="528a9-149">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="528a9-150">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="528a9-150">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="528a9-151">ControlTemplate の作成による既存のコントロールの外観のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="528a9-151">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
