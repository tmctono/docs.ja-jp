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
ms.openlocfilehash: 26989474f264161be12bcc14fed614fdc7f775b6
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460331"
---
# <a name="expander-styles-and-templates"></a><span data-ttu-id="a0ac9-102">エクスパンダーのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="a0ac9-102">Expander Styles and Templates</span></span>
<span data-ttu-id="a0ac9-103">このトピックでは、<xref:System.Windows.Controls.Expander> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a0ac9-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Expander> control.</span></span> <span data-ttu-id="a0ac9-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="a0ac9-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="a0ac9-105">詳細については、「[Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0ac9-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="expander-parts"></a><span data-ttu-id="a0ac9-106">エキスパンダーパーツ</span><span class="sxs-lookup"><span data-stu-id="a0ac9-106">Expander Parts</span></span>  
 <span data-ttu-id="a0ac9-107"><xref:System.Windows.Controls.Expander> コントロールには、名前付きの部分がありません。</span><span class="sxs-lookup"><span data-stu-id="a0ac9-107">The <xref:System.Windows.Controls.Expander> control does not have any named parts.</span></span>  
  
## <a name="expander-states"></a><span data-ttu-id="a0ac9-108">展開の状態</span><span class="sxs-lookup"><span data-stu-id="a0ac9-108">Expander States</span></span>  
 <span data-ttu-id="a0ac9-109">次の表は、<xref:System.Windows.Controls.Expander> コントロールの表示状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="a0ac9-109">The following table lists the visual states for the <xref:System.Windows.Controls.Expander> control.</span></span>  
  
|<span data-ttu-id="a0ac9-110">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="a0ac9-110">VisualState Name</span></span>|<span data-ttu-id="a0ac9-111">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="a0ac9-111">VisualStateGroup Name</span></span>|<span data-ttu-id="a0ac9-112">説明</span><span class="sxs-lookup"><span data-stu-id="a0ac9-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="a0ac9-113">標準</span><span class="sxs-lookup"><span data-stu-id="a0ac9-113">Normal</span></span>|<span data-ttu-id="a0ac9-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a0ac9-114">CommonStates</span></span>|<span data-ttu-id="a0ac9-115">既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="a0ac9-115">The default state.</span></span>|  
|<span data-ttu-id="a0ac9-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="a0ac9-116">MouseOver</span></span>|<span data-ttu-id="a0ac9-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a0ac9-117">CommonStates</span></span>|<span data-ttu-id="a0ac9-118">マウス ポインターがコントロール上に配置されます。</span><span class="sxs-lookup"><span data-stu-id="a0ac9-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="a0ac9-119">Disabled</span><span class="sxs-lookup"><span data-stu-id="a0ac9-119">Disabled</span></span>|<span data-ttu-id="a0ac9-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a0ac9-120">CommonStates</span></span>|<span data-ttu-id="a0ac9-121">コントロールが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="a0ac9-121">The control is disabled.</span></span>|  
|<span data-ttu-id="a0ac9-122">フォーカスされている</span><span class="sxs-lookup"><span data-stu-id="a0ac9-122">Focused</span></span>|<span data-ttu-id="a0ac9-123">FocusStates</span><span class="sxs-lookup"><span data-stu-id="a0ac9-123">FocusStates</span></span>|<span data-ttu-id="a0ac9-124">コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="a0ac9-124">The control has focus.</span></span>|  
|<span data-ttu-id="a0ac9-125">フォーカスされていない</span><span class="sxs-lookup"><span data-stu-id="a0ac9-125">Unfocused</span></span>|<span data-ttu-id="a0ac9-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="a0ac9-126">FocusStates</span></span>|<span data-ttu-id="a0ac9-127">コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="a0ac9-127">The control does not have focus.</span></span>|  
|<span data-ttu-id="a0ac9-128">[展開済み]</span><span class="sxs-lookup"><span data-stu-id="a0ac9-128">Expanded</span></span>|<span data-ttu-id="a0ac9-129">すべての状態</span><span class="sxs-lookup"><span data-stu-id="a0ac9-129">ExpansionStates</span></span>|<span data-ttu-id="a0ac9-130">コントロールが展開されます。</span><span class="sxs-lookup"><span data-stu-id="a0ac9-130">The control is expanded.</span></span>|  
|<span data-ttu-id="a0ac9-131">Collapsed</span><span class="sxs-lookup"><span data-stu-id="a0ac9-131">Collapsed</span></span>|<span data-ttu-id="a0ac9-132">すべての状態</span><span class="sxs-lookup"><span data-stu-id="a0ac9-132">ExpansionStates</span></span>|<span data-ttu-id="a0ac9-133">コントロールが展開されていません。</span><span class="sxs-lookup"><span data-stu-id="a0ac9-133">The control is not expanded.</span></span>|  
|<span data-ttu-id="a0ac9-134">ExpandDown</span><span class="sxs-lookup"><span data-stu-id="a0ac9-134">ExpandDown</span></span>|<span data-ttu-id="a0ac9-135">Expanddirection の状態</span><span class="sxs-lookup"><span data-stu-id="a0ac9-135">ExpandDirectionStates</span></span>|<span data-ttu-id="a0ac9-136">コントロールが下方向に拡張されます。</span><span class="sxs-lookup"><span data-stu-id="a0ac9-136">The control expands down.</span></span>|  
|<span data-ttu-id="a0ac9-137">ExpandUp</span><span class="sxs-lookup"><span data-stu-id="a0ac9-137">ExpandUp</span></span>|<span data-ttu-id="a0ac9-138">Expanddirection の状態</span><span class="sxs-lookup"><span data-stu-id="a0ac9-138">ExpandDirectionStates</span></span>|<span data-ttu-id="a0ac9-139">コントロールが拡張されます。</span><span class="sxs-lookup"><span data-stu-id="a0ac9-139">The control expands up.</span></span>|  
|<span data-ttu-id="a0ac9-140">ExpandLeft</span><span class="sxs-lookup"><span data-stu-id="a0ac9-140">ExpandLeft</span></span>|<span data-ttu-id="a0ac9-141">Expanddirection の状態</span><span class="sxs-lookup"><span data-stu-id="a0ac9-141">ExpandDirectionStates</span></span>|<span data-ttu-id="a0ac9-142">コントロールが左に展開されます。</span><span class="sxs-lookup"><span data-stu-id="a0ac9-142">The control expands left.</span></span>|  
|<span data-ttu-id="a0ac9-143">ExpandRight</span><span class="sxs-lookup"><span data-stu-id="a0ac9-143">ExpandRight</span></span>|<span data-ttu-id="a0ac9-144">Expanddirection の状態</span><span class="sxs-lookup"><span data-stu-id="a0ac9-144">ExpandDirectionStates</span></span>|<span data-ttu-id="a0ac9-145">コントロールが右に展開されます。</span><span class="sxs-lookup"><span data-stu-id="a0ac9-145">The control expands right.</span></span>|  
|<span data-ttu-id="a0ac9-146">有効</span><span class="sxs-lookup"><span data-stu-id="a0ac9-146">Valid</span></span>|<span data-ttu-id="a0ac9-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a0ac9-147">ValidationStates</span></span>|<span data-ttu-id="a0ac9-148">コントロールは <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false`ます。</span><span class="sxs-lookup"><span data-stu-id="a0ac9-148">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="a0ac9-149">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="a0ac9-149">InvalidFocused</span></span>|<span data-ttu-id="a0ac9-150">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a0ac9-150">ValidationStates</span></span>|<span data-ttu-id="a0ac9-151"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがある `true` です。</span><span class="sxs-lookup"><span data-stu-id="a0ac9-151">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="a0ac9-152">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="a0ac9-152">InvalidUnfocused</span></span>|<span data-ttu-id="a0ac9-153">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a0ac9-153">ValidationStates</span></span>|<span data-ttu-id="a0ac9-154"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがない `true` です。</span><span class="sxs-lookup"><span data-stu-id="a0ac9-154">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="expander-controltemplate-example"></a><span data-ttu-id="a0ac9-155">エキスパンダー ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="a0ac9-155">Expander ControlTemplate Example</span></span>  
 <span data-ttu-id="a0ac9-156">次の例は、<xref:System.Windows.Controls.Expander> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a0ac9-156">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Expander> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Expander](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/expander.xaml#expander)]  
  
 <span data-ttu-id="a0ac9-157">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="a0ac9-157">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="a0ac9-158">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0ac9-158">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0ac9-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="a0ac9-159">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="a0ac9-160">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="a0ac9-160">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="a0ac9-161">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="a0ac9-161">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="a0ac9-162">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="a0ac9-162">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="a0ac9-163">ControlTemplate の作成による既存のコントロールの外観のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="a0ac9-163">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
