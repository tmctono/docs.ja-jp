---
title: CheckBox のスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], CheckBox
- templates [WPF], CheckBox
- parts [WPF], CheckBox
- ControlTemplate [WPF], CheckBox
- CheckBox [WPF], styles and templates
- styles [WPF], CheckBox
ms.assetid: bfdaec96-d101-4d3d-864d-c27e6b621d03
ms.openlocfilehash: b194b22c04ac586cbb10a021bac422bbb92a28f0
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356230"
---
# <a name="checkbox-styles-and-templates"></a><span data-ttu-id="4ae40-102">CheckBox のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="4ae40-102">CheckBox Styles and Templates</span></span>
<span data-ttu-id="4ae40-103">このトピックでは、スタイルとテンプレートについて説明します、<xref:System.Windows.Controls.CheckBox>コントロール。</span><span class="sxs-lookup"><span data-stu-id="4ae40-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.CheckBox> control.</span></span> <span data-ttu-id="4ae40-104">既定値を変更する<xref:System.Windows.Controls.ControlTemplate>固有の外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="4ae40-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="4ae40-105">詳細については、「[ControlTemplate の作成による既存のコントロールの外観のカスタマイズ](customizing-the-appearance-of-an-existing-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ae40-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="checkbox-parts"></a><span data-ttu-id="4ae40-106">チェック ボックス部分</span><span class="sxs-lookup"><span data-stu-id="4ae40-106">CheckBox Parts</span></span>  
 <span data-ttu-id="4ae40-107"><xref:System.Windows.Controls.CheckBox>コントロールには、名前付きパーツはありません。</span><span class="sxs-lookup"><span data-stu-id="4ae40-107">The <xref:System.Windows.Controls.CheckBox> control does not have any named parts.</span></span>  
  
## <a name="checkbox-states"></a><span data-ttu-id="4ae40-108">チェック ボックスをオンの状態</span><span class="sxs-lookup"><span data-stu-id="4ae40-108">CheckBox States</span></span>  
 <span data-ttu-id="4ae40-109">次の表のビジュアルの状態、<xref:System.Windows.Controls.CheckBox>コントロール。</span><span class="sxs-lookup"><span data-stu-id="4ae40-109">The following table lists the visual states for the <xref:System.Windows.Controls.CheckBox> control.</span></span>  
  
|<span data-ttu-id="4ae40-110">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="4ae40-110">VisualState Name</span></span>|<span data-ttu-id="4ae40-111">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="4ae40-111">VisualStateGroup Name</span></span>|<span data-ttu-id="4ae40-112">説明</span><span class="sxs-lookup"><span data-stu-id="4ae40-112">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="4ae40-113">標準</span><span class="sxs-lookup"><span data-stu-id="4ae40-113">Normal</span></span>|<span data-ttu-id="4ae40-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="4ae40-114">CommonStates</span></span>|<span data-ttu-id="4ae40-115">既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="4ae40-115">The default state.</span></span>|  
|<span data-ttu-id="4ae40-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="4ae40-116">MouseOver</span></span>|<span data-ttu-id="4ae40-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="4ae40-117">CommonStates</span></span>|<span data-ttu-id="4ae40-118">マウス ポインターがコントロール上に配置されています。</span><span class="sxs-lookup"><span data-stu-id="4ae40-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="4ae40-119">押されている</span><span class="sxs-lookup"><span data-stu-id="4ae40-119">Pressed</span></span>|<span data-ttu-id="4ae40-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="4ae40-120">CommonStates</span></span>|<span data-ttu-id="4ae40-121">コントロールが押されています。</span><span class="sxs-lookup"><span data-stu-id="4ae40-121">The control is pressed.</span></span>|  
|<span data-ttu-id="4ae40-122">無効</span><span class="sxs-lookup"><span data-stu-id="4ae40-122">Disabled</span></span>|<span data-ttu-id="4ae40-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="4ae40-123">CommonStates</span></span>|<span data-ttu-id="4ae40-124">コントロールが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="4ae40-124">The control is disabled.</span></span>|  
|<span data-ttu-id="4ae40-125">フォーカスされている</span><span class="sxs-lookup"><span data-stu-id="4ae40-125">Focused</span></span>|<span data-ttu-id="4ae40-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="4ae40-126">FocusStates</span></span>|<span data-ttu-id="4ae40-127">コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="4ae40-127">The control has focus.</span></span>|  
|<span data-ttu-id="4ae40-128">フォーカスされていない</span><span class="sxs-lookup"><span data-stu-id="4ae40-128">Unfocused</span></span>|<span data-ttu-id="4ae40-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="4ae40-129">FocusStates</span></span>|<span data-ttu-id="4ae40-130">コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="4ae40-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="4ae40-131">チェック済み</span><span class="sxs-lookup"><span data-stu-id="4ae40-131">Checked</span></span>|<span data-ttu-id="4ae40-132">CheckStates</span><span class="sxs-lookup"><span data-stu-id="4ae40-132">CheckStates</span></span>|<span data-ttu-id="4ae40-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> は `true` です。</span><span class="sxs-lookup"><span data-stu-id="4ae40-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.</span></span>|  
|<span data-ttu-id="4ae40-134">オフ</span><span class="sxs-lookup"><span data-stu-id="4ae40-134">Unchecked</span></span>|<span data-ttu-id="4ae40-135">CheckStates</span><span class="sxs-lookup"><span data-stu-id="4ae40-135">CheckStates</span></span>|<span data-ttu-id="4ae40-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> は `false` です。</span><span class="sxs-lookup"><span data-stu-id="4ae40-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.</span></span>|  
|<span data-ttu-id="4ae40-137">不確定です</span><span class="sxs-lookup"><span data-stu-id="4ae40-137">Indeterminate</span></span>|<span data-ttu-id="4ae40-138">CheckStates</span><span class="sxs-lookup"><span data-stu-id="4ae40-138">CheckStates</span></span>|<span data-ttu-id="4ae40-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> が `true` で、<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> が `null` です。</span><span class="sxs-lookup"><span data-stu-id="4ae40-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|  
|<span data-ttu-id="4ae40-140">有効</span><span class="sxs-lookup"><span data-stu-id="4ae40-140">Valid</span></span>|<span data-ttu-id="4ae40-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4ae40-141">ValidationStates</span></span>|<span data-ttu-id="4ae40-142">コントロールを使用して、<xref:System.Windows.Controls.Validation>クラスおよび<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`false`します。</span><span class="sxs-lookup"><span data-stu-id="4ae40-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="4ae40-143">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="4ae40-143">InvalidUnfocused</span></span>|<span data-ttu-id="4ae40-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4ae40-144">ValidationStates</span></span>|<span data-ttu-id="4ae40-145"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="4ae40-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="4ae40-146">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="4ae40-146">InvalidFocused</span></span>|<span data-ttu-id="4ae40-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4ae40-147">ValidationStates</span></span>|<span data-ttu-id="4ae40-148"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスがないです。</span><span class="sxs-lookup"><span data-stu-id="4ae40-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="checkbox-controltemplate-example"></a><span data-ttu-id="4ae40-149">チェック ボックスをオン ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="4ae40-149">CheckBox ControlTemplate Example</span></span>  
 <span data-ttu-id="4ae40-150">次の例は、定義する方法を示します、<xref:System.Windows.Controls.ControlTemplate>の<xref:System.Windows.Controls.CheckBox>コントロール。</span><span class="sxs-lookup"><span data-stu-id="4ae40-150">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.CheckBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#CheckBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/checkbox.xaml#checkbox)]  
  
 <span data-ttu-id="4ae40-151">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="4ae40-151">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="4ae40-152">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ae40-152">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ae40-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="4ae40-153">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="4ae40-154">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="4ae40-154">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="4ae40-155">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="4ae40-155">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="4ae40-156">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="4ae40-156">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="4ae40-157">ControlTemplate の作成による既存のコントロールの外観のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="4ae40-157">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
