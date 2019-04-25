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
ms.openlocfilehash: c5f805c251d3f6b256035e568798cd6d252ea9a4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61911736"
---
# <a name="expander-styles-and-templates"></a><span data-ttu-id="2053b-102">エクスパンダーのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="2053b-102">Expander Styles and Templates</span></span>
<span data-ttu-id="2053b-103">このトピックでは、スタイルとテンプレートについて説明します、<xref:System.Windows.Controls.Expander>コントロール。</span><span class="sxs-lookup"><span data-stu-id="2053b-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Expander> control.</span></span> <span data-ttu-id="2053b-104">既定値を変更する<xref:System.Windows.Controls.ControlTemplate>固有の外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="2053b-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="2053b-105">詳細については、「[ControlTemplate の作成による既存のコントロールの外観のカスタマイズ](customizing-the-appearance-of-an-existing-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2053b-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="expander-parts"></a><span data-ttu-id="2053b-106">展開コントロール パーツ</span><span class="sxs-lookup"><span data-stu-id="2053b-106">Expander Parts</span></span>  
 <span data-ttu-id="2053b-107"><xref:System.Windows.Controls.Expander>コントロールには、名前付きパーツはありません。</span><span class="sxs-lookup"><span data-stu-id="2053b-107">The <xref:System.Windows.Controls.Expander> control does not have any named parts.</span></span>  
  
## <a name="expander-states"></a><span data-ttu-id="2053b-108">エキスパンダーの状態</span><span class="sxs-lookup"><span data-stu-id="2053b-108">Expander States</span></span>  
 <span data-ttu-id="2053b-109">次の表のビジュアルの状態、<xref:System.Windows.Controls.Expander>コントロール。</span><span class="sxs-lookup"><span data-stu-id="2053b-109">The following table lists the visual states for the <xref:System.Windows.Controls.Expander> control.</span></span>  
  
|<span data-ttu-id="2053b-110">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="2053b-110">VisualState Name</span></span>|<span data-ttu-id="2053b-111">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="2053b-111">VisualStateGroup Name</span></span>|<span data-ttu-id="2053b-112">説明</span><span class="sxs-lookup"><span data-stu-id="2053b-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="2053b-113">標準</span><span class="sxs-lookup"><span data-stu-id="2053b-113">Normal</span></span>|<span data-ttu-id="2053b-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="2053b-114">CommonStates</span></span>|<span data-ttu-id="2053b-115">既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="2053b-115">The default state.</span></span>|  
|<span data-ttu-id="2053b-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="2053b-116">MouseOver</span></span>|<span data-ttu-id="2053b-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="2053b-117">CommonStates</span></span>|<span data-ttu-id="2053b-118">マウス ポインターがコントロール上に配置されます。</span><span class="sxs-lookup"><span data-stu-id="2053b-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="2053b-119">無効</span><span class="sxs-lookup"><span data-stu-id="2053b-119">Disabled</span></span>|<span data-ttu-id="2053b-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="2053b-120">CommonStates</span></span>|<span data-ttu-id="2053b-121">コントロールが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="2053b-121">The control is disabled.</span></span>|  
|<span data-ttu-id="2053b-122">フォーカスされている</span><span class="sxs-lookup"><span data-stu-id="2053b-122">Focused</span></span>|<span data-ttu-id="2053b-123">FocusStates</span><span class="sxs-lookup"><span data-stu-id="2053b-123">FocusStates</span></span>|<span data-ttu-id="2053b-124">コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="2053b-124">The control has focus.</span></span>|  
|<span data-ttu-id="2053b-125">フォーカスされていない</span><span class="sxs-lookup"><span data-stu-id="2053b-125">Unfocused</span></span>|<span data-ttu-id="2053b-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="2053b-126">FocusStates</span></span>|<span data-ttu-id="2053b-127">コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="2053b-127">The control does not have focus.</span></span>|  
|<span data-ttu-id="2053b-128">[展開済み]</span><span class="sxs-lookup"><span data-stu-id="2053b-128">Expanded</span></span>|<span data-ttu-id="2053b-129">ExpansionStates</span><span class="sxs-lookup"><span data-stu-id="2053b-129">ExpansionStates</span></span>|<span data-ttu-id="2053b-130">コントロールが展開されます。</span><span class="sxs-lookup"><span data-stu-id="2053b-130">The control is expanded.</span></span>|  
|<span data-ttu-id="2053b-131">Collapsed</span><span class="sxs-lookup"><span data-stu-id="2053b-131">Collapsed</span></span>|<span data-ttu-id="2053b-132">ExpansionStates</span><span class="sxs-lookup"><span data-stu-id="2053b-132">ExpansionStates</span></span>|<span data-ttu-id="2053b-133">コントロールは展開されません。</span><span class="sxs-lookup"><span data-stu-id="2053b-133">The control is not expanded.</span></span>|  
|<span data-ttu-id="2053b-134">ExpandDown</span><span class="sxs-lookup"><span data-stu-id="2053b-134">ExpandDown</span></span>|<span data-ttu-id="2053b-135">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="2053b-135">ExpandDirectionStates</span></span>|<span data-ttu-id="2053b-136">下のコントロールに展開します。</span><span class="sxs-lookup"><span data-stu-id="2053b-136">The control expands down.</span></span>|  
|<span data-ttu-id="2053b-137">ExpandUp</span><span class="sxs-lookup"><span data-stu-id="2053b-137">ExpandUp</span></span>|<span data-ttu-id="2053b-138">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="2053b-138">ExpandDirectionStates</span></span>|<span data-ttu-id="2053b-139">コントロールを展開します。</span><span class="sxs-lookup"><span data-stu-id="2053b-139">The control expands up.</span></span>|  
|<span data-ttu-id="2053b-140">ExpandLeft</span><span class="sxs-lookup"><span data-stu-id="2053b-140">ExpandLeft</span></span>|<span data-ttu-id="2053b-141">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="2053b-141">ExpandDirectionStates</span></span>|<span data-ttu-id="2053b-142">コントロールは左に展開します。</span><span class="sxs-lookup"><span data-stu-id="2053b-142">The control expands left.</span></span>|  
|<span data-ttu-id="2053b-143">ExpandRight</span><span class="sxs-lookup"><span data-stu-id="2053b-143">ExpandRight</span></span>|<span data-ttu-id="2053b-144">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="2053b-144">ExpandDirectionStates</span></span>|<span data-ttu-id="2053b-145">コントロールが右に展開します。</span><span class="sxs-lookup"><span data-stu-id="2053b-145">The control expands right.</span></span>|  
|<span data-ttu-id="2053b-146">有効</span><span class="sxs-lookup"><span data-stu-id="2053b-146">Valid</span></span>|<span data-ttu-id="2053b-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="2053b-147">ValidationStates</span></span>|<span data-ttu-id="2053b-148">コントロールを使用して、<xref:System.Windows.Controls.Validation>クラスおよび<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`false`します。</span><span class="sxs-lookup"><span data-stu-id="2053b-148">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="2053b-149">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="2053b-149">InvalidFocused</span></span>|<span data-ttu-id="2053b-150">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="2053b-150">ValidationStates</span></span>|<span data-ttu-id="2053b-151"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="2053b-151">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="2053b-152">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="2053b-152">InvalidUnfocused</span></span>|<span data-ttu-id="2053b-153">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="2053b-153">ValidationStates</span></span>|<span data-ttu-id="2053b-154"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスがないです。</span><span class="sxs-lookup"><span data-stu-id="2053b-154">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="expander-controltemplate-example"></a><span data-ttu-id="2053b-155">Expander ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="2053b-155">Expander ControlTemplate Example</span></span>  
 <span data-ttu-id="2053b-156">次の例は、定義する方法を示します、<xref:System.Windows.Controls.ControlTemplate>の<xref:System.Windows.Controls.Expander>コントロール。</span><span class="sxs-lookup"><span data-stu-id="2053b-156">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Expander> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Expander](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/expander.xaml#expander)]  
  
 <span data-ttu-id="2053b-157">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="2053b-157">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="2053b-158">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2053b-158">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2053b-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="2053b-159">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="2053b-160">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="2053b-160">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="2053b-161">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="2053b-161">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="2053b-162">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="2053b-162">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="2053b-163">ControlTemplate の作成による既存のコントロールの外観のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="2053b-163">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
