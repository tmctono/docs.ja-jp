---
title: ボタンのスタイルとテンプレート
description: Windows Presentation Foundation の Button コントロールのスタイルとテンプレートについて学習します。 ControlTemplate を変更して、コントロールに固有の外観を指定します。
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], Button
- parts [WPF], Button
- styles [WPF], Button
- Button [WPF], styles and templates
- templates [WPF], Button
- ControlTemplate [WPF], Button
ms.assetid: e223c759-f8c4-4717-acfb-b1e40bdf5f3b
ms.openlocfilehash: 11509adeef397f26eb040e6e98d0edb333b2515f
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166267"
---
# <a name="button-styles-and-templates"></a><span data-ttu-id="7c697-104">ボタンのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="7c697-104">Button Styles and Templates</span></span>
<span data-ttu-id="7c697-105">このトピックでは、<xref:System.Windows.Controls.Button> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7c697-105">This topic describes the styles and templates for the <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="7c697-106"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="7c697-106">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="7c697-107">詳細については、「[コントロールのためにテンプレートを作成する](../../../desktop-wpf/themes/how-to-create-apply-template.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7c697-107">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="button-parts"></a><span data-ttu-id="7c697-108">Button のパーツ</span><span class="sxs-lookup"><span data-stu-id="7c697-108">Button Parts</span></span>  
 <span data-ttu-id="7c697-109"><xref:System.Windows.Controls.Button> コントロールに名前付きパーツはありません。</span><span class="sxs-lookup"><span data-stu-id="7c697-109">The <xref:System.Windows.Controls.Button> control does not have any named parts.</span></span>  
  
## <a name="button-states"></a><span data-ttu-id="7c697-110">Button の状態</span><span class="sxs-lookup"><span data-stu-id="7c697-110">Button States</span></span>  
 <span data-ttu-id="7c697-111">次の表は、<xref:System.Windows.Controls.Button> コントロールの表示状態の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="7c697-111">The following table lists the visual states for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
|<span data-ttu-id="7c697-112">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="7c697-112">VisualState Name</span></span>|<span data-ttu-id="7c697-113">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="7c697-113">VisualStateGroup Name</span></span>|<span data-ttu-id="7c697-114">説明</span><span class="sxs-lookup"><span data-stu-id="7c697-114">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="7c697-115">標準</span><span class="sxs-lookup"><span data-stu-id="7c697-115">Normal</span></span>|<span data-ttu-id="7c697-116">CommonStates</span><span class="sxs-lookup"><span data-stu-id="7c697-116">CommonStates</span></span>|<span data-ttu-id="7c697-117">既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="7c697-117">The default state.</span></span>|  
|<span data-ttu-id="7c697-118">MouseOver</span><span class="sxs-lookup"><span data-stu-id="7c697-118">MouseOver</span></span>|<span data-ttu-id="7c697-119">CommonStates</span><span class="sxs-lookup"><span data-stu-id="7c697-119">CommonStates</span></span>|<span data-ttu-id="7c697-120">マウス ポインターがコントロール上に配置されています。</span><span class="sxs-lookup"><span data-stu-id="7c697-120">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="7c697-121">押されている</span><span class="sxs-lookup"><span data-stu-id="7c697-121">Pressed</span></span>|<span data-ttu-id="7c697-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="7c697-122">CommonStates</span></span>|<span data-ttu-id="7c697-123">コントロールが押されています。</span><span class="sxs-lookup"><span data-stu-id="7c697-123">The control is pressed.</span></span>|  
|<span data-ttu-id="7c697-124">無効</span><span class="sxs-lookup"><span data-stu-id="7c697-124">Disabled</span></span>|<span data-ttu-id="7c697-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="7c697-125">CommonStates</span></span>|<span data-ttu-id="7c697-126">コントロールが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="7c697-126">The control is disabled.</span></span>|  
|<span data-ttu-id="7c697-127">フォーカスされている</span><span class="sxs-lookup"><span data-stu-id="7c697-127">Focused</span></span>|<span data-ttu-id="7c697-128">FocusStates</span><span class="sxs-lookup"><span data-stu-id="7c697-128">FocusStates</span></span>|<span data-ttu-id="7c697-129">コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="7c697-129">The control has focus.</span></span>|  
|<span data-ttu-id="7c697-130">フォーカスされていない</span><span class="sxs-lookup"><span data-stu-id="7c697-130">Unfocused</span></span>|<span data-ttu-id="7c697-131">FocusStates</span><span class="sxs-lookup"><span data-stu-id="7c697-131">FocusStates</span></span>|<span data-ttu-id="7c697-132">コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="7c697-132">The control does not have focus.</span></span>|  
|<span data-ttu-id="7c697-133">有効</span><span class="sxs-lookup"><span data-stu-id="7c697-133">Valid</span></span>|<span data-ttu-id="7c697-134">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="7c697-134">ValidationStates</span></span>|<span data-ttu-id="7c697-135">このコントロールで <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false` です。</span><span class="sxs-lookup"><span data-stu-id="7c697-135">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="7c697-136">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="7c697-136">InvalidFocused</span></span>|<span data-ttu-id="7c697-137">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="7c697-137">ValidationStates</span></span>|<span data-ttu-id="7c697-138"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `true` で、コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="7c697-138">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="7c697-139">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="7c697-139">InvalidUnfocused</span></span>|<span data-ttu-id="7c697-140">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="7c697-140">ValidationStates</span></span>|<span data-ttu-id="7c697-141"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `true` で、コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="7c697-141">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="button-controltemplate-example"></a><span data-ttu-id="7c697-142">Button の ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="7c697-142">Button ControlTemplate Example</span></span>  
 <span data-ttu-id="7c697-143">次の例は、<xref:System.Windows.Controls.Button> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="7c697-143">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Button](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#button)]  
  
 <span data-ttu-id="7c697-144">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="7c697-144">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="7c697-145">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c697-145">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c697-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="7c697-146">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="7c697-147">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="7c697-147">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="7c697-148">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="7c697-148">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="7c697-149">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="7c697-149">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="7c697-150">コントロールのためのテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="7c697-150">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
