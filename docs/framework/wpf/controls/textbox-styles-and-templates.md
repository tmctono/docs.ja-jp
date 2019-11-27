---
title: TextBox のスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], TextBox
- parts [WPF], TextBox
- states [WPF], TextBox
- styles [WPF], TextBox
- templates [WPF], TextBox
- TextBox [WPF], styles and templates
ms.assetid: aa99130c-43a1-450f-9b46-c40ae0db0cca
ms.openlocfilehash: 41e390c261836909240cc146a48729d48c4a410e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283697"
---
# <a name="textbox-styles-and-templates"></a><span data-ttu-id="62107-102">TextBox のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="62107-102">TextBox Styles and Templates</span></span>
<span data-ttu-id="62107-103">このトピックでは、<xref:System.Windows.Controls.TextBox> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="62107-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.TextBox> control.</span></span> <span data-ttu-id="62107-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="62107-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="62107-105">詳細については、「[コントロールのテンプレートを作成する](../../../desktop-wpf/themes/how-to-create-apply-template.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62107-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="textbox-parts"></a><span data-ttu-id="62107-106">TextBox の部分</span><span class="sxs-lookup"><span data-stu-id="62107-106">TextBox Parts</span></span>  
 <span data-ttu-id="62107-107">次の表に、<xref:System.Windows.Controls.TextBox> コントロールの名前付きの部分を示します。</span><span class="sxs-lookup"><span data-stu-id="62107-107">The following table lists the named parts for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="62107-108">要素</span><span class="sxs-lookup"><span data-stu-id="62107-108">Part</span></span>|<span data-ttu-id="62107-109">種類</span><span class="sxs-lookup"><span data-stu-id="62107-109">Type</span></span>|<span data-ttu-id="62107-110">説明</span><span class="sxs-lookup"><span data-stu-id="62107-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="62107-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="62107-111">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="62107-112"><xref:System.Windows.FrameworkElement>を含むことができるビジュアル要素。</span><span class="sxs-lookup"><span data-stu-id="62107-112">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="62107-113"><xref:System.Windows.Controls.TextBox> のテキストがこの要素に表示されます。</span><span class="sxs-lookup"><span data-stu-id="62107-113">The text of the <xref:System.Windows.Controls.TextBox> is displayed in this element.</span></span>|  
  
## <a name="textbox-states"></a><span data-ttu-id="62107-114">テキストボックスの状態</span><span class="sxs-lookup"><span data-stu-id="62107-114">TextBox States</span></span>  
 <span data-ttu-id="62107-115">次の表は、<xref:System.Windows.Controls.TextBox> コントロールの表示状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="62107-115">The following table lists the visual states for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="62107-116">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="62107-116">VisualState Name</span></span>|<span data-ttu-id="62107-117">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="62107-117">VisualStateGroup Name</span></span>|<span data-ttu-id="62107-118">説明</span><span class="sxs-lookup"><span data-stu-id="62107-118">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="62107-119">標準</span><span class="sxs-lookup"><span data-stu-id="62107-119">Normal</span></span>|<span data-ttu-id="62107-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="62107-120">CommonStates</span></span>|<span data-ttu-id="62107-121">既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="62107-121">The default state.</span></span>|  
|<span data-ttu-id="62107-122">MouseOver</span><span class="sxs-lookup"><span data-stu-id="62107-122">MouseOver</span></span>|<span data-ttu-id="62107-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="62107-123">CommonStates</span></span>|<span data-ttu-id="62107-124">マウス ポインターがコントロール上に配置されます。</span><span class="sxs-lookup"><span data-stu-id="62107-124">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="62107-125">無効</span><span class="sxs-lookup"><span data-stu-id="62107-125">Disabled</span></span>|<span data-ttu-id="62107-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="62107-126">CommonStates</span></span>|<span data-ttu-id="62107-127">コントロールが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="62107-127">The control is disabled.</span></span>|  
|<span data-ttu-id="62107-128">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="62107-128">ReadOnly</span></span>|<span data-ttu-id="62107-129">CommonStates</span><span class="sxs-lookup"><span data-stu-id="62107-129">CommonStates</span></span>|<span data-ttu-id="62107-130">ユーザーは、<xref:System.Windows.Controls.TextBox>内のテキストを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="62107-130">The user cannot change the text in the <xref:System.Windows.Controls.TextBox>.</span></span>|  
|<span data-ttu-id="62107-131">フォーカスされている</span><span class="sxs-lookup"><span data-stu-id="62107-131">Focused</span></span>|<span data-ttu-id="62107-132">FocusStates</span><span class="sxs-lookup"><span data-stu-id="62107-132">FocusStates</span></span>|<span data-ttu-id="62107-133">コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="62107-133">The control has focus.</span></span>|  
|<span data-ttu-id="62107-134">フォーカスされていない</span><span class="sxs-lookup"><span data-stu-id="62107-134">Unfocused</span></span>|<span data-ttu-id="62107-135">FocusStates</span><span class="sxs-lookup"><span data-stu-id="62107-135">FocusStates</span></span>|<span data-ttu-id="62107-136">コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="62107-136">The control does not have focus.</span></span>|  
|<span data-ttu-id="62107-137">Valid</span><span class="sxs-lookup"><span data-stu-id="62107-137">Valid</span></span>|<span data-ttu-id="62107-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="62107-138">ValidationStates</span></span>|<span data-ttu-id="62107-139">コントロールは <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false`ます。</span><span class="sxs-lookup"><span data-stu-id="62107-139">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="62107-140">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="62107-140">InvalidFocused</span></span>|<span data-ttu-id="62107-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="62107-141">ValidationStates</span></span>|<span data-ttu-id="62107-142"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがある `true` です。</span><span class="sxs-lookup"><span data-stu-id="62107-142">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="62107-143">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="62107-143">InvalidUnfocused</span></span>|<span data-ttu-id="62107-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="62107-144">ValidationStates</span></span>|<span data-ttu-id="62107-145"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがない `true` です。</span><span class="sxs-lookup"><span data-stu-id="62107-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="textbox-controltemplate-example"></a><span data-ttu-id="62107-146">TextBox ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="62107-146">TextBox ControlTemplate Example</span></span>  
 <span data-ttu-id="62107-147">次の例は、<xref:System.Windows.Controls.TextBox> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="62107-147">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#TextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#textbox)]  
  
 <span data-ttu-id="62107-148">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="62107-148">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="62107-149">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62107-149">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62107-150">参照</span><span class="sxs-lookup"><span data-stu-id="62107-150">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="62107-151">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="62107-151">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="62107-152">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="62107-152">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="62107-153">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="62107-153">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="62107-154">コントロールのテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="62107-154">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
