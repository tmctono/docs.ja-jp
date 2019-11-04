---
title: ボタンのスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], Button
- parts [WPF], Button
- styles [WPF], Button
- Button [WPF], styles and templates
- templates [WPF], Button
- ControlTemplate [WPF], Button
ms.assetid: e223c759-f8c4-4717-acfb-b1e40bdf5f3b
ms.openlocfilehash: 64764d43191d30c191c5d6519982b16cfc86d26e
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460957"
---
# <a name="button-styles-and-templates"></a><span data-ttu-id="ac30f-102">ボタンのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="ac30f-102">Button Styles and Templates</span></span>
<span data-ttu-id="ac30f-103">このトピックでは、<xref:System.Windows.Controls.Button> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ac30f-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="ac30f-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="ac30f-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="ac30f-105">詳細については、「[Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac30f-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="button-parts"></a><span data-ttu-id="ac30f-106">ボタン部分</span><span class="sxs-lookup"><span data-stu-id="ac30f-106">Button Parts</span></span>  
 <span data-ttu-id="ac30f-107"><xref:System.Windows.Controls.Button> コントロールには、名前付きの部分がありません。</span><span class="sxs-lookup"><span data-stu-id="ac30f-107">The <xref:System.Windows.Controls.Button> control does not have any named parts.</span></span>  
  
## <a name="button-states"></a><span data-ttu-id="ac30f-108">ボタンの状態</span><span class="sxs-lookup"><span data-stu-id="ac30f-108">Button States</span></span>  
 <span data-ttu-id="ac30f-109">次の表は、<xref:System.Windows.Controls.Button> コントロールの表示状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="ac30f-109">The following table lists the visual states for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
|<span data-ttu-id="ac30f-110">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="ac30f-110">VisualState Name</span></span>|<span data-ttu-id="ac30f-111">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="ac30f-111">VisualStateGroup Name</span></span>|<span data-ttu-id="ac30f-112">説明</span><span class="sxs-lookup"><span data-stu-id="ac30f-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="ac30f-113">標準</span><span class="sxs-lookup"><span data-stu-id="ac30f-113">Normal</span></span>|<span data-ttu-id="ac30f-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ac30f-114">CommonStates</span></span>|<span data-ttu-id="ac30f-115">既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="ac30f-115">The default state.</span></span>|  
|<span data-ttu-id="ac30f-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="ac30f-116">MouseOver</span></span>|<span data-ttu-id="ac30f-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ac30f-117">CommonStates</span></span>|<span data-ttu-id="ac30f-118">マウス ポインターがコントロール上に配置されます。</span><span class="sxs-lookup"><span data-stu-id="ac30f-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="ac30f-119">押されている</span><span class="sxs-lookup"><span data-stu-id="ac30f-119">Pressed</span></span>|<span data-ttu-id="ac30f-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ac30f-120">CommonStates</span></span>|<span data-ttu-id="ac30f-121">コントロールが押されています。</span><span class="sxs-lookup"><span data-stu-id="ac30f-121">The control is pressed.</span></span>|  
|<span data-ttu-id="ac30f-122">Disabled</span><span class="sxs-lookup"><span data-stu-id="ac30f-122">Disabled</span></span>|<span data-ttu-id="ac30f-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ac30f-123">CommonStates</span></span>|<span data-ttu-id="ac30f-124">コントロールが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="ac30f-124">The control is disabled.</span></span>|  
|<span data-ttu-id="ac30f-125">フォーカスされている</span><span class="sxs-lookup"><span data-stu-id="ac30f-125">Focused</span></span>|<span data-ttu-id="ac30f-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="ac30f-126">FocusStates</span></span>|<span data-ttu-id="ac30f-127">コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="ac30f-127">The control has focus.</span></span>|  
|<span data-ttu-id="ac30f-128">フォーカスされていない</span><span class="sxs-lookup"><span data-stu-id="ac30f-128">Unfocused</span></span>|<span data-ttu-id="ac30f-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="ac30f-129">FocusStates</span></span>|<span data-ttu-id="ac30f-130">コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="ac30f-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="ac30f-131">有効</span><span class="sxs-lookup"><span data-stu-id="ac30f-131">Valid</span></span>|<span data-ttu-id="ac30f-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ac30f-132">ValidationStates</span></span>|<span data-ttu-id="ac30f-133">コントロールは <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false`ます。</span><span class="sxs-lookup"><span data-stu-id="ac30f-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="ac30f-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="ac30f-134">InvalidFocused</span></span>|<span data-ttu-id="ac30f-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ac30f-135">ValidationStates</span></span>|<span data-ttu-id="ac30f-136"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティが `true`、コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="ac30f-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="ac30f-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="ac30f-137">InvalidUnfocused</span></span>|<span data-ttu-id="ac30f-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ac30f-138">ValidationStates</span></span>|<span data-ttu-id="ac30f-139"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティが `true`、コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="ac30f-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="button-controltemplate-example"></a><span data-ttu-id="ac30f-140">Button ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="ac30f-140">Button ControlTemplate Example</span></span>  
 <span data-ttu-id="ac30f-141">次の例は、<xref:System.Windows.Controls.Button> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="ac30f-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Button](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#button)]  
  
 <span data-ttu-id="ac30f-142">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="ac30f-142">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="ac30f-143">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac30f-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac30f-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="ac30f-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="ac30f-145">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="ac30f-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="ac30f-146">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="ac30f-146">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="ac30f-147">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="ac30f-147">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="ac30f-148">ControlTemplate の作成による既存のコントロールの外観のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="ac30f-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
