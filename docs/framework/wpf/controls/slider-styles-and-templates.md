---
title: スライダーのスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], Slider
- states [WPF], Slider
- Slider [WPF], styles and templates
- styles [WPF], Slider
- templates [WPF], Slider
- ControlTemplate [WPF], Slider
ms.assetid: d89aa97b-075a-4752-9c41-9679df65c491
ms.openlocfilehash: 334cb4a44788980262110eadac3305283bb61a92
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458393"
---
# <a name="slider-styles-and-templates"></a><span data-ttu-id="ba66a-102">スライダーのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="ba66a-102">Slider Styles and Templates</span></span>
<span data-ttu-id="ba66a-103">このトピックでは、<xref:System.Windows.Controls.Slider> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ba66a-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Slider> control.</span></span> <span data-ttu-id="ba66a-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="ba66a-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="ba66a-105">詳細については、「[Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba66a-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="slider-parts"></a><span data-ttu-id="ba66a-106">スライダーの部分</span><span class="sxs-lookup"><span data-stu-id="ba66a-106">Slider Parts</span></span>  
 <span data-ttu-id="ba66a-107">次の表に、<xref:System.Windows.Controls.Slider> コントロールの名前付きの部分を示します。</span><span class="sxs-lookup"><span data-stu-id="ba66a-107">The following table lists the named parts for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
|<span data-ttu-id="ba66a-108">パーツ</span><span class="sxs-lookup"><span data-stu-id="ba66a-108">Part</span></span>|<span data-ttu-id="ba66a-109">[種類]</span><span class="sxs-lookup"><span data-stu-id="ba66a-109">Type</span></span>|<span data-ttu-id="ba66a-110">説明</span><span class="sxs-lookup"><span data-stu-id="ba66a-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="ba66a-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="ba66a-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="ba66a-112"><xref:System.Windows.Controls.Slider>の位置を示す要素のコンテナー。</span><span class="sxs-lookup"><span data-stu-id="ba66a-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Slider>.</span></span>|  
|<span data-ttu-id="ba66a-113">PART_SelectionRange</span><span class="sxs-lookup"><span data-stu-id="ba66a-113">PART_SelectionRange</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="ba66a-114"><xref:System.Windows.Controls.Slider>に沿って選択範囲を表示する要素。</span><span class="sxs-lookup"><span data-stu-id="ba66a-114">The element that displays a selection range along the <xref:System.Windows.Controls.Slider>.</span></span>  <span data-ttu-id="ba66a-115">選択範囲は、<xref:System.Windows.Controls.Slider.IsSelectionRangeEnabled%2A> プロパティが `true`場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="ba66a-115">The selection range is visible only if the <xref:System.Windows.Controls.Slider.IsSelectionRangeEnabled%2A> property is `true`.</span></span>|  
  
## <a name="slider-states"></a><span data-ttu-id="ba66a-116">スライダーの状態</span><span class="sxs-lookup"><span data-stu-id="ba66a-116">Slider States</span></span>  
 <span data-ttu-id="ba66a-117">次の表は、<xref:System.Windows.Controls.Slider> コントロールの表示状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="ba66a-117">The following table lists the visual states for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
|<span data-ttu-id="ba66a-118">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="ba66a-118">VisualState Name</span></span>|<span data-ttu-id="ba66a-119">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="ba66a-119">VisualStateGroup Name</span></span>|<span data-ttu-id="ba66a-120">説明</span><span class="sxs-lookup"><span data-stu-id="ba66a-120">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="ba66a-121">標準</span><span class="sxs-lookup"><span data-stu-id="ba66a-121">Normal</span></span>|<span data-ttu-id="ba66a-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ba66a-122">CommonStates</span></span>|<span data-ttu-id="ba66a-123">既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="ba66a-123">The default state.</span></span>|  
|<span data-ttu-id="ba66a-124">MouseOver</span><span class="sxs-lookup"><span data-stu-id="ba66a-124">MouseOver</span></span>|<span data-ttu-id="ba66a-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ba66a-125">CommonStates</span></span>|<span data-ttu-id="ba66a-126">マウス ポインターがコントロール上に配置されます。</span><span class="sxs-lookup"><span data-stu-id="ba66a-126">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="ba66a-127">Disabled</span><span class="sxs-lookup"><span data-stu-id="ba66a-127">Disabled</span></span>|<span data-ttu-id="ba66a-128">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ba66a-128">CommonStates</span></span>|<span data-ttu-id="ba66a-129">コントロールが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="ba66a-129">The control is disabled.</span></span>|  
|<span data-ttu-id="ba66a-130">フォーカスされている</span><span class="sxs-lookup"><span data-stu-id="ba66a-130">Focused</span></span>|<span data-ttu-id="ba66a-131">FocusStates</span><span class="sxs-lookup"><span data-stu-id="ba66a-131">FocusStates</span></span>|<span data-ttu-id="ba66a-132">コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="ba66a-132">The control has focus.</span></span>|  
|<span data-ttu-id="ba66a-133">フォーカスされていない</span><span class="sxs-lookup"><span data-stu-id="ba66a-133">Unfocused</span></span>|<span data-ttu-id="ba66a-134">FocusStates</span><span class="sxs-lookup"><span data-stu-id="ba66a-134">FocusStates</span></span>|<span data-ttu-id="ba66a-135">コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="ba66a-135">The control does not have focus.</span></span>|  
|<span data-ttu-id="ba66a-136">有効</span><span class="sxs-lookup"><span data-stu-id="ba66a-136">Valid</span></span>|<span data-ttu-id="ba66a-137">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ba66a-137">ValidationStates</span></span>|<span data-ttu-id="ba66a-138">コントロールは <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false`ます。</span><span class="sxs-lookup"><span data-stu-id="ba66a-138">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="ba66a-139">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="ba66a-139">InvalidFocused</span></span>|<span data-ttu-id="ba66a-140">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ba66a-140">ValidationStates</span></span>|<span data-ttu-id="ba66a-141"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがある `true` です。</span><span class="sxs-lookup"><span data-stu-id="ba66a-141">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="ba66a-142">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="ba66a-142">InvalidUnfocused</span></span>|<span data-ttu-id="ba66a-143">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ba66a-143">ValidationStates</span></span>|<span data-ttu-id="ba66a-144"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがない `true` です。</span><span class="sxs-lookup"><span data-stu-id="ba66a-144">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="slider-controltemplate-example"></a><span data-ttu-id="ba66a-145">Slider ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="ba66a-145">Slider ControlTemplate Example</span></span>  
 <span data-ttu-id="ba66a-146">次の例は、<xref:System.Windows.Controls.Slider> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="ba66a-146">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Slider](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/slider.xaml#slider)]  
  
 <span data-ttu-id="ba66a-147">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="ba66a-147">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="ba66a-148">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba66a-148">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba66a-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="ba66a-149">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="ba66a-150">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="ba66a-150">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="ba66a-151">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="ba66a-151">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="ba66a-152">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="ba66a-152">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="ba66a-153">ControlTemplate の作成による既存のコントロールの外観のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="ba66a-153">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
