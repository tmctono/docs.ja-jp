---
title: ProgressBar のスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], ProgressBar
- ProgressBar [WPF], styles and templates
- styles [WPF], ProgressBar
- ControlTemplate [WPF], ProgressBar
- templates [WPF], ProgressBar
- states [WPF], ProgressBar
ms.assetid: 935aa600-16e6-4947-a905-37a189a583dd
ms.openlocfilehash: 3a1bea39ba9b6d2cff9937a3fee1d1de41daf16b
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459871"
---
# <a name="progressbar-styles-and-templates"></a><span data-ttu-id="cf465-102">ProgressBar のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="cf465-102">ProgressBar Styles and Templates</span></span>
<span data-ttu-id="cf465-103">このトピックでは、<xref:System.Windows.Controls.ProgressBar> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="cf465-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ProgressBar> control.</span></span> <span data-ttu-id="cf465-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="cf465-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="cf465-105">詳細については、「[Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf465-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="progressbar-parts"></a><span data-ttu-id="cf465-106">ProgressBar のパーツ</span><span class="sxs-lookup"><span data-stu-id="cf465-106">ProgressBar Parts</span></span>  
 <span data-ttu-id="cf465-107">次の表に、<xref:System.Windows.Controls.ProgressBar> コントロールの名前付きの部分を示します。</span><span class="sxs-lookup"><span data-stu-id="cf465-107">The following table lists the named parts for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="cf465-108">パーツ</span><span class="sxs-lookup"><span data-stu-id="cf465-108">Part</span></span>|<span data-ttu-id="cf465-109">[種類]</span><span class="sxs-lookup"><span data-stu-id="cf465-109">Type</span></span>|<span data-ttu-id="cf465-110">説明</span><span class="sxs-lookup"><span data-stu-id="cf465-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="cf465-111">PART_Indicator</span><span class="sxs-lookup"><span data-stu-id="cf465-111">PART_Indicator</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="cf465-112">進行状況を示すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="cf465-112">The object that indicates progress.</span></span>|  
|<span data-ttu-id="cf465-113">PART_Track</span><span class="sxs-lookup"><span data-stu-id="cf465-113">PART_Track</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="cf465-114">進行状況インジケーターのパスを定義するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="cf465-114">The object that defines the path of the progress indicator.</span></span>|  
|<span data-ttu-id="cf465-115">PART_GlowRect</span><span class="sxs-lookup"><span data-stu-id="cf465-115">PART_GlowRect</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="cf465-116">プログレスバーを embellishes するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="cf465-116">An object that embellishes the progress bar.</span></span>|  
  
## <a name="progressbar-states"></a><span data-ttu-id="cf465-117">ProgressBar の状態</span><span class="sxs-lookup"><span data-stu-id="cf465-117">ProgressBar States</span></span>  
 <span data-ttu-id="cf465-118">次の表は、<xref:System.Windows.Controls.ProgressBar> コントロールの表示状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="cf465-118">The following table lists the visual states for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="cf465-119">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="cf465-119">VisualState Name</span></span>|<span data-ttu-id="cf465-120">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="cf465-120">VisualStateGroup Name</span></span>|<span data-ttu-id="cf465-121">説明</span><span class="sxs-lookup"><span data-stu-id="cf465-121">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="cf465-122">一定</span><span class="sxs-lookup"><span data-stu-id="cf465-122">Determinate</span></span>|<span data-ttu-id="cf465-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="cf465-123">CommonStates</span></span>|<span data-ttu-id="cf465-124"><xref:System.Windows.Controls.ProgressBar> は、<xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> プロパティに基づいて進行状況をレポートします。</span><span class="sxs-lookup"><span data-stu-id="cf465-124"><xref:System.Windows.Controls.ProgressBar> reports progress based on the <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> property.</span></span>|  
|<span data-ttu-id="cf465-125">確定</span><span class="sxs-lookup"><span data-stu-id="cf465-125">Indeterminate</span></span>|<span data-ttu-id="cf465-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="cf465-126">CommonStates</span></span>|<span data-ttu-id="cf465-127"><xref:System.Windows.Controls.ProgressBar> は、繰り返しパターンを使用して一般的な進行状況を報告します。</span><span class="sxs-lookup"><span data-stu-id="cf465-127"><xref:System.Windows.Controls.ProgressBar> reports generic progress with a repeating pattern.</span></span>|  
|<span data-ttu-id="cf465-128">有効</span><span class="sxs-lookup"><span data-stu-id="cf465-128">Valid</span></span>|<span data-ttu-id="cf465-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="cf465-129">ValidationStates</span></span>|<span data-ttu-id="cf465-130">コントロールは <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false`ます。</span><span class="sxs-lookup"><span data-stu-id="cf465-130">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="cf465-131">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="cf465-131">InvalidFocused</span></span>|<span data-ttu-id="cf465-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="cf465-132">ValidationStates</span></span>|<span data-ttu-id="cf465-133"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがある `true` です。</span><span class="sxs-lookup"><span data-stu-id="cf465-133">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="cf465-134">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="cf465-134">InvalidUnfocused</span></span>|<span data-ttu-id="cf465-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="cf465-135">ValidationStates</span></span>|<span data-ttu-id="cf465-136"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがない `true` です。</span><span class="sxs-lookup"><span data-stu-id="cf465-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="progressbar-controltemplate-example"></a><span data-ttu-id="cf465-137">ProgressBar ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="cf465-137">ProgressBar ControlTemplate Example</span></span>  
 <span data-ttu-id="cf465-138">次の例は、<xref:System.Windows.Controls.ProgressBar> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="cf465-138">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ProgressBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/progressbar.xaml#progressbar)]  
  
 <span data-ttu-id="cf465-139">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="cf465-139">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="cf465-140">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf465-140">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf465-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf465-141">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="cf465-142">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="cf465-142">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="cf465-143">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="cf465-143">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="cf465-144">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="cf465-144">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="cf465-145">ControlTemplate の作成による既存のコントロールの外観のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="cf465-145">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
