---
title: エクスパンダーのスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], Expander
- ControlTemplate [WPF], Expander
- templates [WPF], Expander
- Expander [WPF], styles and templates
- states [WPF], Expander
- parts [WPF], Expander
ms.assetid: da2e5a1c-5230-4c21-98a5-59c7895facd7
ms.openlocfilehash: 39f81aacb24b0b68b550da622b1e3038eb9eac9b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283521"
---
# <a name="expander-styles-and-templates"></a><span data-ttu-id="bc46e-102">エクスパンダーのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="bc46e-102">Expander Styles and Templates</span></span>
<span data-ttu-id="bc46e-103">このトピックでは、<xref:System.Windows.Controls.Expander> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="bc46e-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Expander> control.</span></span> <span data-ttu-id="bc46e-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="bc46e-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="bc46e-105">詳細については、「[コントロールのテンプレートを作成する](../../../desktop-wpf/themes/how-to-create-apply-template.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc46e-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="expander-parts"></a><span data-ttu-id="bc46e-106">エキスパンダーパーツ</span><span class="sxs-lookup"><span data-stu-id="bc46e-106">Expander Parts</span></span>  
 <span data-ttu-id="bc46e-107"><xref:System.Windows.Controls.Expander> コントロールには、名前付きの部分がありません。</span><span class="sxs-lookup"><span data-stu-id="bc46e-107">The <xref:System.Windows.Controls.Expander> control does not have any named parts.</span></span>  
  
## <a name="expander-states"></a><span data-ttu-id="bc46e-108">展開の状態</span><span class="sxs-lookup"><span data-stu-id="bc46e-108">Expander States</span></span>  
 <span data-ttu-id="bc46e-109">次の表は、<xref:System.Windows.Controls.Expander> コントロールの表示状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="bc46e-109">The following table lists the visual states for the <xref:System.Windows.Controls.Expander> control.</span></span>  
  
|<span data-ttu-id="bc46e-110">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="bc46e-110">VisualState Name</span></span>|<span data-ttu-id="bc46e-111">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="bc46e-111">VisualStateGroup Name</span></span>|<span data-ttu-id="bc46e-112">説明</span><span class="sxs-lookup"><span data-stu-id="bc46e-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="bc46e-113">標準</span><span class="sxs-lookup"><span data-stu-id="bc46e-113">Normal</span></span>|<span data-ttu-id="bc46e-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="bc46e-114">CommonStates</span></span>|<span data-ttu-id="bc46e-115">既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="bc46e-115">The default state.</span></span>|  
|<span data-ttu-id="bc46e-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="bc46e-116">MouseOver</span></span>|<span data-ttu-id="bc46e-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="bc46e-117">CommonStates</span></span>|<span data-ttu-id="bc46e-118">マウス ポインターがコントロール上に配置されます。</span><span class="sxs-lookup"><span data-stu-id="bc46e-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="bc46e-119">Disabled</span><span class="sxs-lookup"><span data-stu-id="bc46e-119">Disabled</span></span>|<span data-ttu-id="bc46e-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="bc46e-120">CommonStates</span></span>|<span data-ttu-id="bc46e-121">コントロールが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="bc46e-121">The control is disabled.</span></span>|  
|<span data-ttu-id="bc46e-122">フォーカスされている</span><span class="sxs-lookup"><span data-stu-id="bc46e-122">Focused</span></span>|<span data-ttu-id="bc46e-123">FocusStates</span><span class="sxs-lookup"><span data-stu-id="bc46e-123">FocusStates</span></span>|<span data-ttu-id="bc46e-124">コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="bc46e-124">The control has focus.</span></span>|  
|<span data-ttu-id="bc46e-125">フォーカスされていない</span><span class="sxs-lookup"><span data-stu-id="bc46e-125">Unfocused</span></span>|<span data-ttu-id="bc46e-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="bc46e-126">FocusStates</span></span>|<span data-ttu-id="bc46e-127">コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="bc46e-127">The control does not have focus.</span></span>|  
|<span data-ttu-id="bc46e-128">[展開済み]</span><span class="sxs-lookup"><span data-stu-id="bc46e-128">Expanded</span></span>|<span data-ttu-id="bc46e-129">すべての状態</span><span class="sxs-lookup"><span data-stu-id="bc46e-129">ExpansionStates</span></span>|<span data-ttu-id="bc46e-130">コントロールが展開されます。</span><span class="sxs-lookup"><span data-stu-id="bc46e-130">The control is expanded.</span></span>|  
|<span data-ttu-id="bc46e-131">Collapsed</span><span class="sxs-lookup"><span data-stu-id="bc46e-131">Collapsed</span></span>|<span data-ttu-id="bc46e-132">すべての状態</span><span class="sxs-lookup"><span data-stu-id="bc46e-132">ExpansionStates</span></span>|<span data-ttu-id="bc46e-133">コントロールが展開されていません。</span><span class="sxs-lookup"><span data-stu-id="bc46e-133">The control is not expanded.</span></span>|  
|<span data-ttu-id="bc46e-134">ExpandDown</span><span class="sxs-lookup"><span data-stu-id="bc46e-134">ExpandDown</span></span>|<span data-ttu-id="bc46e-135">Expanddirection の状態</span><span class="sxs-lookup"><span data-stu-id="bc46e-135">ExpandDirectionStates</span></span>|<span data-ttu-id="bc46e-136">コントロールが下方向に拡張されます。</span><span class="sxs-lookup"><span data-stu-id="bc46e-136">The control expands down.</span></span>|  
|<span data-ttu-id="bc46e-137">ExpandUp</span><span class="sxs-lookup"><span data-stu-id="bc46e-137">ExpandUp</span></span>|<span data-ttu-id="bc46e-138">Expanddirection の状態</span><span class="sxs-lookup"><span data-stu-id="bc46e-138">ExpandDirectionStates</span></span>|<span data-ttu-id="bc46e-139">コントロールが拡張されます。</span><span class="sxs-lookup"><span data-stu-id="bc46e-139">The control expands up.</span></span>|  
|<span data-ttu-id="bc46e-140">ExpandLeft</span><span class="sxs-lookup"><span data-stu-id="bc46e-140">ExpandLeft</span></span>|<span data-ttu-id="bc46e-141">Expanddirection の状態</span><span class="sxs-lookup"><span data-stu-id="bc46e-141">ExpandDirectionStates</span></span>|<span data-ttu-id="bc46e-142">コントロールが左に展開されます。</span><span class="sxs-lookup"><span data-stu-id="bc46e-142">The control expands left.</span></span>|  
|<span data-ttu-id="bc46e-143">ExpandRight</span><span class="sxs-lookup"><span data-stu-id="bc46e-143">ExpandRight</span></span>|<span data-ttu-id="bc46e-144">Expanddirection の状態</span><span class="sxs-lookup"><span data-stu-id="bc46e-144">ExpandDirectionStates</span></span>|<span data-ttu-id="bc46e-145">コントロールが右に展開されます。</span><span class="sxs-lookup"><span data-stu-id="bc46e-145">The control expands right.</span></span>|  
|<span data-ttu-id="bc46e-146">Valid</span><span class="sxs-lookup"><span data-stu-id="bc46e-146">Valid</span></span>|<span data-ttu-id="bc46e-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="bc46e-147">ValidationStates</span></span>|<span data-ttu-id="bc46e-148">コントロールは <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false`ます。</span><span class="sxs-lookup"><span data-stu-id="bc46e-148">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="bc46e-149">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="bc46e-149">InvalidFocused</span></span>|<span data-ttu-id="bc46e-150">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="bc46e-150">ValidationStates</span></span>|<span data-ttu-id="bc46e-151"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがある `true` です。</span><span class="sxs-lookup"><span data-stu-id="bc46e-151">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="bc46e-152">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="bc46e-152">InvalidUnfocused</span></span>|<span data-ttu-id="bc46e-153">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="bc46e-153">ValidationStates</span></span>|<span data-ttu-id="bc46e-154"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがない `true` です。</span><span class="sxs-lookup"><span data-stu-id="bc46e-154">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="expander-controltemplate-example"></a><span data-ttu-id="bc46e-155">エキスパンダー ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="bc46e-155">Expander ControlTemplate Example</span></span>  
 <span data-ttu-id="bc46e-156">次の例は、<xref:System.Windows.Controls.Expander> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="bc46e-156">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Expander> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Expander](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/expander.xaml#expander)]  
  
 <span data-ttu-id="bc46e-157">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="bc46e-157">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="bc46e-158">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc46e-158">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc46e-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="bc46e-159">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="bc46e-160">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="bc46e-160">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="bc46e-161">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="bc46e-161">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="bc46e-162">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="bc46e-162">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="bc46e-163">コントロールのテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="bc46e-163">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
