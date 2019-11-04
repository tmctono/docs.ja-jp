---
title: RadioButton のスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], RadioButton
- RadioButton [WPF], styles and templates
- ControlTemplate [WPF], RadioButton
- states [WPF], RadioButton
- templates [WPF], RadioButton
- parts [WPF], RadioButton
ms.assetid: 9acf93f7-dd2f-4010-8ce0-1edd81c52ae2
ms.openlocfilehash: 892b4bead6ef6db3a6c007e34fb333ebf1e39850
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459865"
---
# <a name="radiobutton-styles-and-templates"></a><span data-ttu-id="14641-102">RadioButton のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="14641-102">RadioButton Styles and Templates</span></span>
<span data-ttu-id="14641-103">このトピックでは、<xref:System.Windows.Controls.RadioButton> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="14641-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.RadioButton> control.</span></span> <span data-ttu-id="14641-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="14641-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="14641-105">詳細については、「[Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14641-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="radiobutton-parts"></a><span data-ttu-id="14641-106">RadioButton の部分</span><span class="sxs-lookup"><span data-stu-id="14641-106">RadioButton Parts</span></span>  
 <span data-ttu-id="14641-107"><xref:System.Windows.Controls.RadioButton> コントロールには、名前付きの部分がありません。</span><span class="sxs-lookup"><span data-stu-id="14641-107">The <xref:System.Windows.Controls.RadioButton> control does not have any named parts.</span></span>  
  
## <a name="radiobutton-states"></a><span data-ttu-id="14641-108">RadioButton の状態</span><span class="sxs-lookup"><span data-stu-id="14641-108">RadioButton States</span></span>  
 <span data-ttu-id="14641-109">次の表は、<xref:System.Windows.Controls.RadioButton> コントロールの表示状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="14641-109">The following table lists the visual states for the <xref:System.Windows.Controls.RadioButton> control.</span></span>  
  
|<span data-ttu-id="14641-110">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="14641-110">VisualState Name</span></span>|<span data-ttu-id="14641-111">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="14641-111">VisualStateGroup Name</span></span>|<span data-ttu-id="14641-112">説明</span><span class="sxs-lookup"><span data-stu-id="14641-112">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="14641-113">標準</span><span class="sxs-lookup"><span data-stu-id="14641-113">Normal</span></span>|<span data-ttu-id="14641-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="14641-114">CommonStates</span></span>|<span data-ttu-id="14641-115">既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="14641-115">The default state.</span></span>|  
|<span data-ttu-id="14641-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="14641-116">MouseOver</span></span>|<span data-ttu-id="14641-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="14641-117">CommonStates</span></span>|<span data-ttu-id="14641-118">マウス ポインターがコントロール上に配置されます。</span><span class="sxs-lookup"><span data-stu-id="14641-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="14641-119">押されている</span><span class="sxs-lookup"><span data-stu-id="14641-119">Pressed</span></span>|<span data-ttu-id="14641-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="14641-120">CommonStates</span></span>|<span data-ttu-id="14641-121">コントロールが押されています。</span><span class="sxs-lookup"><span data-stu-id="14641-121">The control is pressed.</span></span>|  
|<span data-ttu-id="14641-122">Disabled</span><span class="sxs-lookup"><span data-stu-id="14641-122">Disabled</span></span>|<span data-ttu-id="14641-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="14641-123">CommonStates</span></span>|<span data-ttu-id="14641-124">コントロールが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="14641-124">The control is disabled.</span></span>|  
|<span data-ttu-id="14641-125">フォーカスされている</span><span class="sxs-lookup"><span data-stu-id="14641-125">Focused</span></span>|<span data-ttu-id="14641-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="14641-126">FocusStates</span></span>|<span data-ttu-id="14641-127">コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="14641-127">The control has focus.</span></span>|  
|<span data-ttu-id="14641-128">フォーカスされていない</span><span class="sxs-lookup"><span data-stu-id="14641-128">Unfocused</span></span>|<span data-ttu-id="14641-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="14641-129">FocusStates</span></span>|<span data-ttu-id="14641-130">コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="14641-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="14641-131">チェック済み</span><span class="sxs-lookup"><span data-stu-id="14641-131">Checked</span></span>|<span data-ttu-id="14641-132">CheckStates</span><span class="sxs-lookup"><span data-stu-id="14641-132">CheckStates</span></span>|<span data-ttu-id="14641-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> が `true` です。</span><span class="sxs-lookup"><span data-stu-id="14641-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.</span></span>|  
|<span data-ttu-id="14641-134">再帰</span><span class="sxs-lookup"><span data-stu-id="14641-134">Unchecked</span></span>|<span data-ttu-id="14641-135">CheckStates</span><span class="sxs-lookup"><span data-stu-id="14641-135">CheckStates</span></span>|<span data-ttu-id="14641-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> が `false` です。</span><span class="sxs-lookup"><span data-stu-id="14641-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.</span></span>|  
|<span data-ttu-id="14641-137">確定</span><span class="sxs-lookup"><span data-stu-id="14641-137">Indeterminate</span></span>|<span data-ttu-id="14641-138">CheckStates</span><span class="sxs-lookup"><span data-stu-id="14641-138">CheckStates</span></span>|<span data-ttu-id="14641-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> が `true` で、<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> が `null` です。</span><span class="sxs-lookup"><span data-stu-id="14641-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|  
|<span data-ttu-id="14641-140">有効</span><span class="sxs-lookup"><span data-stu-id="14641-140">Valid</span></span>|<span data-ttu-id="14641-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="14641-141">ValidationStates</span></span>|<span data-ttu-id="14641-142">コントロールは <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false`ます。</span><span class="sxs-lookup"><span data-stu-id="14641-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="14641-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="14641-143">InvalidFocused</span></span>|<span data-ttu-id="14641-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="14641-144">ValidationStates</span></span>|<span data-ttu-id="14641-145"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがある `true` です。</span><span class="sxs-lookup"><span data-stu-id="14641-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="14641-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="14641-146">InvalidUnfocused</span></span>|<span data-ttu-id="14641-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="14641-147">ValidationStates</span></span>|<span data-ttu-id="14641-148"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがない `true` です。</span><span class="sxs-lookup"><span data-stu-id="14641-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="radiobutton-controltemplate-example"></a><span data-ttu-id="14641-149">RadioButton ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="14641-149">RadioButton ControlTemplate Example</span></span>  
 <span data-ttu-id="14641-150">次の例は、<xref:System.Windows.Controls.RadioButton> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="14641-150">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.RadioButton> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#RadioButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/radiobutton.xaml#radiobutton)]  
  
 <span data-ttu-id="14641-151">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="14641-151">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="14641-152">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14641-152">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14641-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="14641-153">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="14641-154">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="14641-154">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="14641-155">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="14641-155">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="14641-156">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="14641-156">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="14641-157">ControlTemplate の作成による既存のコントロールの外観のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="14641-157">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
