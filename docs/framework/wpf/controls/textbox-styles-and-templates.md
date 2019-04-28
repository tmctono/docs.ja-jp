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
ms.openlocfilehash: ccc89e0e0c8977398ed162b246ff6cdede3b8351
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790872"
---
# <a name="textbox-styles-and-templates"></a><span data-ttu-id="bcfae-102">TextBox のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="bcfae-102">TextBox Styles and Templates</span></span>
<span data-ttu-id="bcfae-103">このトピックでは、スタイルとテンプレートについて説明します、<xref:System.Windows.Controls.TextBox>コントロール。</span><span class="sxs-lookup"><span data-stu-id="bcfae-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.TextBox> control.</span></span> <span data-ttu-id="bcfae-104">既定値を変更する<xref:System.Windows.Controls.ControlTemplate>固有の外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="bcfae-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="bcfae-105">詳細については、「[ControlTemplate の作成による既存のコントロールの外観のカスタマイズ](customizing-the-appearance-of-an-existing-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcfae-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="textbox-parts"></a><span data-ttu-id="bcfae-106">テキスト ボックス部分</span><span class="sxs-lookup"><span data-stu-id="bcfae-106">TextBox Parts</span></span>  
 <span data-ttu-id="bcfae-107">次の表に、名前付きパーツ、<xref:System.Windows.Controls.TextBox>コントロール。</span><span class="sxs-lookup"><span data-stu-id="bcfae-107">The following table lists the named parts for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="bcfae-108">パーツ</span><span class="sxs-lookup"><span data-stu-id="bcfae-108">Part</span></span>|<span data-ttu-id="bcfae-109">型</span><span class="sxs-lookup"><span data-stu-id="bcfae-109">Type</span></span>|<span data-ttu-id="bcfae-110">説明</span><span class="sxs-lookup"><span data-stu-id="bcfae-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="bcfae-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="bcfae-111">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="bcfae-112">ビジュアル要素を含めることができます、<xref:System.Windows.FrameworkElement>します。</span><span class="sxs-lookup"><span data-stu-id="bcfae-112">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="bcfae-113">テキスト、<xref:System.Windows.Controls.TextBox>がこの要素に表示されます。</span><span class="sxs-lookup"><span data-stu-id="bcfae-113">The text of the <xref:System.Windows.Controls.TextBox> is displayed in this element.</span></span>|  
  
## <a name="textbox-states"></a><span data-ttu-id="bcfae-114">テキスト ボックスの状態</span><span class="sxs-lookup"><span data-stu-id="bcfae-114">TextBox States</span></span>  
 <span data-ttu-id="bcfae-115">次の表のビジュアルの状態、<xref:System.Windows.Controls.TextBox>コントロール。</span><span class="sxs-lookup"><span data-stu-id="bcfae-115">The following table lists the visual states for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="bcfae-116">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="bcfae-116">VisualState Name</span></span>|<span data-ttu-id="bcfae-117">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="bcfae-117">VisualStateGroup Name</span></span>|<span data-ttu-id="bcfae-118">説明</span><span class="sxs-lookup"><span data-stu-id="bcfae-118">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="bcfae-119">標準</span><span class="sxs-lookup"><span data-stu-id="bcfae-119">Normal</span></span>|<span data-ttu-id="bcfae-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="bcfae-120">CommonStates</span></span>|<span data-ttu-id="bcfae-121">既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="bcfae-121">The default state.</span></span>|  
|<span data-ttu-id="bcfae-122">MouseOver</span><span class="sxs-lookup"><span data-stu-id="bcfae-122">MouseOver</span></span>|<span data-ttu-id="bcfae-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="bcfae-123">CommonStates</span></span>|<span data-ttu-id="bcfae-124">マウス ポインターがコントロール上に配置されます。</span><span class="sxs-lookup"><span data-stu-id="bcfae-124">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="bcfae-125">無効</span><span class="sxs-lookup"><span data-stu-id="bcfae-125">Disabled</span></span>|<span data-ttu-id="bcfae-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="bcfae-126">CommonStates</span></span>|<span data-ttu-id="bcfae-127">コントロールが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="bcfae-127">The control is disabled.</span></span>|  
|<span data-ttu-id="bcfae-128">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="bcfae-128">ReadOnly</span></span>|<span data-ttu-id="bcfae-129">CommonStates</span><span class="sxs-lookup"><span data-stu-id="bcfae-129">CommonStates</span></span>|<span data-ttu-id="bcfae-130">内のテキストを変更することはできません、ユーザー、<xref:System.Windows.Controls.TextBox>します。</span><span class="sxs-lookup"><span data-stu-id="bcfae-130">The user cannot change the text in the <xref:System.Windows.Controls.TextBox>.</span></span>|  
|<span data-ttu-id="bcfae-131">フォーカスされている</span><span class="sxs-lookup"><span data-stu-id="bcfae-131">Focused</span></span>|<span data-ttu-id="bcfae-132">FocusStates</span><span class="sxs-lookup"><span data-stu-id="bcfae-132">FocusStates</span></span>|<span data-ttu-id="bcfae-133">コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="bcfae-133">The control has focus.</span></span>|  
|<span data-ttu-id="bcfae-134">フォーカスされていない</span><span class="sxs-lookup"><span data-stu-id="bcfae-134">Unfocused</span></span>|<span data-ttu-id="bcfae-135">FocusStates</span><span class="sxs-lookup"><span data-stu-id="bcfae-135">FocusStates</span></span>|<span data-ttu-id="bcfae-136">コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="bcfae-136">The control does not have focus.</span></span>|  
|<span data-ttu-id="bcfae-137">有効</span><span class="sxs-lookup"><span data-stu-id="bcfae-137">Valid</span></span>|<span data-ttu-id="bcfae-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="bcfae-138">ValidationStates</span></span>|<span data-ttu-id="bcfae-139">コントロールを使用して、<xref:System.Windows.Controls.Validation>クラスおよび<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`false`します。</span><span class="sxs-lookup"><span data-stu-id="bcfae-139">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="bcfae-140">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="bcfae-140">InvalidFocused</span></span>|<span data-ttu-id="bcfae-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="bcfae-141">ValidationStates</span></span>|<span data-ttu-id="bcfae-142"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="bcfae-142">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="bcfae-143">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="bcfae-143">InvalidUnfocused</span></span>|<span data-ttu-id="bcfae-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="bcfae-144">ValidationStates</span></span>|<span data-ttu-id="bcfae-145"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスがないです。</span><span class="sxs-lookup"><span data-stu-id="bcfae-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="textbox-controltemplate-example"></a><span data-ttu-id="bcfae-146">テキスト ボックスの ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="bcfae-146">TextBox ControlTemplate Example</span></span>  
 <span data-ttu-id="bcfae-147">次の例は、定義する方法を示します、<xref:System.Windows.Controls.ControlTemplate>の<xref:System.Windows.Controls.TextBox>コントロール。</span><span class="sxs-lookup"><span data-stu-id="bcfae-147">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#TextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#textbox)]  
  
 <span data-ttu-id="bcfae-148">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="bcfae-148">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="bcfae-149">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcfae-149">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcfae-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="bcfae-150">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="bcfae-151">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="bcfae-151">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="bcfae-152">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="bcfae-152">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="bcfae-153">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="bcfae-153">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="bcfae-154">ControlTemplate の作成による既存のコントロールの外観のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="bcfae-154">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
