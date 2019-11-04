---
title: StatusBar のスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], StatusBar
- styles [WPF], StatusBar
- templates [WPF], StatusBar
- states [WPF], StatusBar
- parts [WPF], StatusBar
- StatusBar [WPF], styles and templates
ms.assetid: 9f5e1c25-81eb-4756-a0ac-d9e1fbe33ee2
ms.openlocfilehash: b1dd575d58571b845fc849ca432ad440d1ce3ec4
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458258"
---
# <a name="statusbar-styles-and-templates"></a><span data-ttu-id="38deb-102">StatusBar のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="38deb-102">StatusBar Styles and Templates</span></span>
<span data-ttu-id="38deb-103">このトピックでは、<xref:System.Windows.Controls.Primitives.StatusBar> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="38deb-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span> <span data-ttu-id="38deb-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="38deb-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="38deb-105">詳細については、「[Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38deb-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="statusbar-parts"></a><span data-ttu-id="38deb-106">StatusBar パーツ</span><span class="sxs-lookup"><span data-stu-id="38deb-106">StatusBar Parts</span></span>  
 <span data-ttu-id="38deb-107"><xref:System.Windows.Controls.Primitives.StatusBar> コントロールには、名前付きの部分がありません。</span><span class="sxs-lookup"><span data-stu-id="38deb-107">The <xref:System.Windows.Controls.Primitives.StatusBar> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="38deb-108">ステータスバーの状態</span><span class="sxs-lookup"><span data-stu-id="38deb-108">StatusBar States</span></span>  
 <span data-ttu-id="38deb-109">次の表は、<xref:System.Windows.Controls.Primitives.StatusBar> コントロールの表示状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="38deb-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
|<span data-ttu-id="38deb-110">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="38deb-110">VisualState Name</span></span>|<span data-ttu-id="38deb-111">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="38deb-111">VisualStateGroup Name</span></span>|<span data-ttu-id="38deb-112">説明</span><span class="sxs-lookup"><span data-stu-id="38deb-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="38deb-113">有効</span><span class="sxs-lookup"><span data-stu-id="38deb-113">Valid</span></span>|<span data-ttu-id="38deb-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="38deb-114">ValidationStates</span></span>|<span data-ttu-id="38deb-115">コントロールは <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false`ます。</span><span class="sxs-lookup"><span data-stu-id="38deb-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="38deb-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="38deb-116">InvalidFocused</span></span>|<span data-ttu-id="38deb-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="38deb-117">ValidationStates</span></span>|<span data-ttu-id="38deb-118"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがある `true` です。</span><span class="sxs-lookup"><span data-stu-id="38deb-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="38deb-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="38deb-119">InvalidUnfocused</span></span>|<span data-ttu-id="38deb-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="38deb-120">ValidationStates</span></span>|<span data-ttu-id="38deb-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがない `true` です。</span><span class="sxs-lookup"><span data-stu-id="38deb-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbaritem-parts"></a><span data-ttu-id="38deb-122">StatusBarItem パーツ</span><span class="sxs-lookup"><span data-stu-id="38deb-122">StatusBarItem Parts</span></span>  
 <span data-ttu-id="38deb-123"><xref:System.Windows.Controls.Primitives.StatusBarItem> コントロールには、名前付きの部分がありません。</span><span class="sxs-lookup"><span data-stu-id="38deb-123">The <xref:System.Windows.Controls.Primitives.StatusBarItem> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="38deb-124">ステータスバーの状態</span><span class="sxs-lookup"><span data-stu-id="38deb-124">StatusBar States</span></span>  
 <span data-ttu-id="38deb-125">次の表は、<xref:System.Windows.Controls.Primitives.StatusBarItem> コントロールの表示状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="38deb-125">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBarItem> control.</span></span>  
  
|<span data-ttu-id="38deb-126">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="38deb-126">VisualState Name</span></span>|<span data-ttu-id="38deb-127">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="38deb-127">VisualStateGroup Name</span></span>|<span data-ttu-id="38deb-128">説明</span><span class="sxs-lookup"><span data-stu-id="38deb-128">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="38deb-129">有効</span><span class="sxs-lookup"><span data-stu-id="38deb-129">Valid</span></span>|<span data-ttu-id="38deb-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="38deb-130">ValidationStates</span></span>|<span data-ttu-id="38deb-131">コントロールは <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false`ます。</span><span class="sxs-lookup"><span data-stu-id="38deb-131">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="38deb-132">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="38deb-132">InvalidFocused</span></span>|<span data-ttu-id="38deb-133">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="38deb-133">ValidationStates</span></span>|<span data-ttu-id="38deb-134"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがある `true` です。</span><span class="sxs-lookup"><span data-stu-id="38deb-134">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="38deb-135">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="38deb-135">InvalidUnfocused</span></span>|<span data-ttu-id="38deb-136">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="38deb-136">ValidationStates</span></span>|<span data-ttu-id="38deb-137"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがない `true` です。</span><span class="sxs-lookup"><span data-stu-id="38deb-137">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbar-controltemplate-example"></a><span data-ttu-id="38deb-138">StatusBar ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="38deb-138">StatusBar ControlTemplate Example</span></span>  
 <span data-ttu-id="38deb-139">次の例は、<xref:System.Windows.Controls.Primitives.StatusBar> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="38deb-139">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#StatusBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/statusbar.xaml#statusbar)]  
  
 <span data-ttu-id="38deb-140"><xref:System.Windows.Controls.ControlTemplate> では、次のリソースの1つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="38deb-140">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="38deb-141">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38deb-141">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38deb-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="38deb-142">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="38deb-143">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="38deb-143">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="38deb-144">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="38deb-144">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="38deb-145">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="38deb-145">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="38deb-146">ControlTemplate の作成による既存のコントロールの外観のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="38deb-146">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
