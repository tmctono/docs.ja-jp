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
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283521"
---
# <a name="expander-styles-and-templates"></a><span data-ttu-id="be669-102">エクスパンダーのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="be669-102">Expander Styles and Templates</span></span>
<span data-ttu-id="be669-103">このトピックでは、<xref:System.Windows.Controls.Expander> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="be669-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Expander> control.</span></span> <span data-ttu-id="be669-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="be669-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="be669-105">詳細については、「[コントロールのためにテンプレートを作成する](../../../desktop-wpf/themes/how-to-create-apply-template.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="be669-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="expander-parts"></a><span data-ttu-id="be669-106">Expander のパーツ</span><span class="sxs-lookup"><span data-stu-id="be669-106">Expander Parts</span></span>  
 <span data-ttu-id="be669-107"><xref:System.Windows.Controls.Expander> コントロールに名前付きパーツはありません。</span><span class="sxs-lookup"><span data-stu-id="be669-107">The <xref:System.Windows.Controls.Expander> control does not have any named parts.</span></span>  
  
## <a name="expander-states"></a><span data-ttu-id="be669-108">Expander の状態</span><span class="sxs-lookup"><span data-stu-id="be669-108">Expander States</span></span>  
 <span data-ttu-id="be669-109">次の表は、<xref:System.Windows.Controls.Expander> コントロールの表示状態の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="be669-109">The following table lists the visual states for the <xref:System.Windows.Controls.Expander> control.</span></span>  
  
|<span data-ttu-id="be669-110">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="be669-110">VisualState Name</span></span>|<span data-ttu-id="be669-111">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="be669-111">VisualStateGroup Name</span></span>|<span data-ttu-id="be669-112">説明</span><span class="sxs-lookup"><span data-stu-id="be669-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="be669-113">標準</span><span class="sxs-lookup"><span data-stu-id="be669-113">Normal</span></span>|<span data-ttu-id="be669-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="be669-114">CommonStates</span></span>|<span data-ttu-id="be669-115">既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="be669-115">The default state.</span></span>|  
|<span data-ttu-id="be669-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="be669-116">MouseOver</span></span>|<span data-ttu-id="be669-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="be669-117">CommonStates</span></span>|<span data-ttu-id="be669-118">マウス ポインターがコントロール上に配置されます。</span><span class="sxs-lookup"><span data-stu-id="be669-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="be669-119">無効</span><span class="sxs-lookup"><span data-stu-id="be669-119">Disabled</span></span>|<span data-ttu-id="be669-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="be669-120">CommonStates</span></span>|<span data-ttu-id="be669-121">コントロールが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="be669-121">The control is disabled.</span></span>|  
|<span data-ttu-id="be669-122">フォーカスされている</span><span class="sxs-lookup"><span data-stu-id="be669-122">Focused</span></span>|<span data-ttu-id="be669-123">FocusStates</span><span class="sxs-lookup"><span data-stu-id="be669-123">FocusStates</span></span>|<span data-ttu-id="be669-124">コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="be669-124">The control has focus.</span></span>|  
|<span data-ttu-id="be669-125">フォーカスされていない</span><span class="sxs-lookup"><span data-stu-id="be669-125">Unfocused</span></span>|<span data-ttu-id="be669-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="be669-126">FocusStates</span></span>|<span data-ttu-id="be669-127">コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="be669-127">The control does not have focus.</span></span>|  
|<span data-ttu-id="be669-128">[展開済み]</span><span class="sxs-lookup"><span data-stu-id="be669-128">Expanded</span></span>|<span data-ttu-id="be669-129">ExpansionStates</span><span class="sxs-lookup"><span data-stu-id="be669-129">ExpansionStates</span></span>|<span data-ttu-id="be669-130">コントロールが展開されています。</span><span class="sxs-lookup"><span data-stu-id="be669-130">The control is expanded.</span></span>|  
|<span data-ttu-id="be669-131">Collapsed</span><span class="sxs-lookup"><span data-stu-id="be669-131">Collapsed</span></span>|<span data-ttu-id="be669-132">ExpansionStates</span><span class="sxs-lookup"><span data-stu-id="be669-132">ExpansionStates</span></span>|<span data-ttu-id="be669-133">コントロールが展開されていません。</span><span class="sxs-lookup"><span data-stu-id="be669-133">The control is not expanded.</span></span>|  
|<span data-ttu-id="be669-134">ExpandDown</span><span class="sxs-lookup"><span data-stu-id="be669-134">ExpandDown</span></span>|<span data-ttu-id="be669-135">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="be669-135">ExpandDirectionStates</span></span>|<span data-ttu-id="be669-136">コントロールが下方向に展開しています。</span><span class="sxs-lookup"><span data-stu-id="be669-136">The control expands down.</span></span>|  
|<span data-ttu-id="be669-137">ExpandUp</span><span class="sxs-lookup"><span data-stu-id="be669-137">ExpandUp</span></span>|<span data-ttu-id="be669-138">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="be669-138">ExpandDirectionStates</span></span>|<span data-ttu-id="be669-139">コントロールが上方向に展開しています。</span><span class="sxs-lookup"><span data-stu-id="be669-139">The control expands up.</span></span>|  
|<span data-ttu-id="be669-140">ExpandLeft</span><span class="sxs-lookup"><span data-stu-id="be669-140">ExpandLeft</span></span>|<span data-ttu-id="be669-141">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="be669-141">ExpandDirectionStates</span></span>|<span data-ttu-id="be669-142">コントロールが左方向に展開しています。</span><span class="sxs-lookup"><span data-stu-id="be669-142">The control expands left.</span></span>|  
|<span data-ttu-id="be669-143">ExpandRight</span><span class="sxs-lookup"><span data-stu-id="be669-143">ExpandRight</span></span>|<span data-ttu-id="be669-144">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="be669-144">ExpandDirectionStates</span></span>|<span data-ttu-id="be669-145">コントロールが右方向に展開しています。</span><span class="sxs-lookup"><span data-stu-id="be669-145">The control expands right.</span></span>|  
|<span data-ttu-id="be669-146">有効</span><span class="sxs-lookup"><span data-stu-id="be669-146">Valid</span></span>|<span data-ttu-id="be669-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="be669-147">ValidationStates</span></span>|<span data-ttu-id="be669-148">このコントロールで <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false` です。</span><span class="sxs-lookup"><span data-stu-id="be669-148">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="be669-149">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="be669-149">InvalidFocused</span></span>|<span data-ttu-id="be669-150">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="be669-150">ValidationStates</span></span>|<span data-ttu-id="be669-151"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがある `true` です。</span><span class="sxs-lookup"><span data-stu-id="be669-151">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="be669-152">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="be669-152">InvalidUnfocused</span></span>|<span data-ttu-id="be669-153">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="be669-153">ValidationStates</span></span>|<span data-ttu-id="be669-154"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがない `true` です。</span><span class="sxs-lookup"><span data-stu-id="be669-154">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="expander-controltemplate-example"></a><span data-ttu-id="be669-155">Expander の ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="be669-155">Expander ControlTemplate Example</span></span>  
 <span data-ttu-id="be669-156">次の例は、<xref:System.Windows.Controls.Expander> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="be669-156">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Expander> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Expander](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/expander.xaml#expander)]  
  
 <span data-ttu-id="be669-157">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="be669-157">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="be669-158">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be669-158">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be669-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="be669-159">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="be669-160">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="be669-160">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="be669-161">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="be669-161">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="be669-162">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="be669-162">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="be669-163">コントロールのためのテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="be669-163">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
