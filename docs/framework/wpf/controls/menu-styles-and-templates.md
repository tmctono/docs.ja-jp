---
title: メニューのスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], Menu
- ControlTemplate [WPF], Menu
- Menu [WPF], styles and templates
- states [WPF], Menu
- templates [WPF], Menu
- parts [WPF], Menu
ms.assetid: b89da183-9b87-42c6-ac53-731a42c7b09e
ms.openlocfilehash: 6818be4ac92dbdd7de0c6c6fa65109e21eadc2f5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942104"
---
# <a name="menu-styles-and-templates"></a><span data-ttu-id="d86ba-102">メニューのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="d86ba-102">Menu Styles and Templates</span></span>
<span data-ttu-id="d86ba-103">このトピックでは、スタイルとテンプレートについて説明します、<xref:System.Windows.Controls.Menu>コントロール。</span><span class="sxs-lookup"><span data-stu-id="d86ba-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Menu> control.</span></span> <span data-ttu-id="d86ba-104">既定値を変更する<xref:System.Windows.Controls.ControlTemplate>固有の外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="d86ba-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="d86ba-105">詳細については、「[ControlTemplate の作成による既存のコントロールの外観のカスタマイズ](customizing-the-appearance-of-an-existing-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d86ba-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="menu-parts"></a><span data-ttu-id="d86ba-106">メニューの部品</span><span class="sxs-lookup"><span data-stu-id="d86ba-106">Menu Parts</span></span>  
 <span data-ttu-id="d86ba-107"><xref:System.Windows.Controls.Menu>コントロールには、名前付きパーツはありません。</span><span class="sxs-lookup"><span data-stu-id="d86ba-107">The <xref:System.Windows.Controls.Menu> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="d86ba-108">作成するときに、<xref:System.Windows.Controls.ControlTemplate>の<xref:System.Windows.Controls.Menu>、テンプレートが含まれます、<xref:System.Windows.Controls.ItemsPresenter>内、 <xref:System.Windows.Controls.ScrollViewer>。</span><span class="sxs-lookup"><span data-stu-id="d86ba-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.Menu>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="d86ba-109">(、<xref:System.Windows.Controls.ItemsPresenter>内の各項目が表示されます、 <xref:System.Windows.Controls.Menu>、<xref:System.Windows.Controls.ScrollViewer>コントロール内でスクロールできます)。</span><span class="sxs-lookup"><span data-stu-id="d86ba-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.Menu>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="d86ba-110">場合、<xref:System.Windows.Controls.ItemsPresenter>の直接の子ではない、<xref:System.Windows.Controls.ScrollViewer>を付ける必要があります、<xref:System.Windows.Controls.ItemsPresenter>名、`ItemsPresenter`します。</span><span class="sxs-lookup"><span data-stu-id="d86ba-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="menu-states"></a><span data-ttu-id="d86ba-111">メニューの状態</span><span class="sxs-lookup"><span data-stu-id="d86ba-111">Menu States</span></span>  
 <span data-ttu-id="d86ba-112">次の表のビジュアルの状態、<xref:System.Windows.Controls.Menu>コントロール。</span><span class="sxs-lookup"><span data-stu-id="d86ba-112">The following table lists the visual states for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
|<span data-ttu-id="d86ba-113">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="d86ba-113">VisualState Name</span></span>|<span data-ttu-id="d86ba-114">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="d86ba-114">VisualStateGroup Name</span></span>|<span data-ttu-id="d86ba-115">説明</span><span class="sxs-lookup"><span data-stu-id="d86ba-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="d86ba-116">有効</span><span class="sxs-lookup"><span data-stu-id="d86ba-116">Valid</span></span>|<span data-ttu-id="d86ba-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d86ba-117">ValidationStates</span></span>|<span data-ttu-id="d86ba-118">コントロールを使用して、<xref:System.Windows.Controls.Validation>クラスおよび<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`false`します。</span><span class="sxs-lookup"><span data-stu-id="d86ba-118">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="d86ba-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="d86ba-119">InvalidFocused</span></span>|<span data-ttu-id="d86ba-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d86ba-120">ValidationStates</span></span>|<span data-ttu-id="d86ba-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="d86ba-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="d86ba-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="d86ba-122">InvalidUnfocused</span></span>|<span data-ttu-id="d86ba-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d86ba-123">ValidationStates</span></span>|<span data-ttu-id="d86ba-124"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスがないです。</span><span class="sxs-lookup"><span data-stu-id="d86ba-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="menuitem-parts"></a><span data-ttu-id="d86ba-125">MenuItem のパーツ</span><span class="sxs-lookup"><span data-stu-id="d86ba-125">MenuItem Parts</span></span>  
 <span data-ttu-id="d86ba-126">次の表に、名前付きパーツ、<xref:System.Windows.Controls.Menu>コントロール。</span><span class="sxs-lookup"><span data-stu-id="d86ba-126">The following table lists the named parts for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
|<span data-ttu-id="d86ba-127">パーツ</span><span class="sxs-lookup"><span data-stu-id="d86ba-127">Part</span></span>|<span data-ttu-id="d86ba-128">型</span><span class="sxs-lookup"><span data-stu-id="d86ba-128">Type</span></span>|<span data-ttu-id="d86ba-129">説明</span><span class="sxs-lookup"><span data-stu-id="d86ba-129">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="d86ba-130">PART_Popup</span><span class="sxs-lookup"><span data-stu-id="d86ba-130">PART_Popup</span></span>|<xref:System.Windows.Controls.Primitives.Popup>|<span data-ttu-id="d86ba-131">サブメニューの領域。</span><span class="sxs-lookup"><span data-stu-id="d86ba-131">The area for the submenu.</span></span>|  
  
 <span data-ttu-id="d86ba-132">作成するときに、<xref:System.Windows.Controls.ControlTemplate>の<xref:System.Windows.Controls.MenuItem>、テンプレートが含まれます、<xref:System.Windows.Controls.ItemsPresenter>内、 <xref:System.Windows.Controls.ScrollViewer>。</span><span class="sxs-lookup"><span data-stu-id="d86ba-132">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.MenuItem>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="d86ba-133">(、<xref:System.Windows.Controls.ItemsPresenter>内の各項目が表示されます、 <xref:System.Windows.Controls.MenuItem>、<xref:System.Windows.Controls.ScrollViewer>コントロール内でスクロールできます)。</span><span class="sxs-lookup"><span data-stu-id="d86ba-133">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.MenuItem>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="d86ba-134">場合、<xref:System.Windows.Controls.ItemsPresenter>の直接の子ではない、<xref:System.Windows.Controls.ScrollViewer>を付ける必要があります、<xref:System.Windows.Controls.ItemsPresenter>名、`ItemsPresenter`します。</span><span class="sxs-lookup"><span data-stu-id="d86ba-134">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="menuitem-states"></a><span data-ttu-id="d86ba-135">MenuItem の状態</span><span class="sxs-lookup"><span data-stu-id="d86ba-135">MenuItem States</span></span>  
 <span data-ttu-id="d86ba-136">次の表のビジュアルの状態、<xref:System.Windows.Controls.MenuItem>コントロール。</span><span class="sxs-lookup"><span data-stu-id="d86ba-136">The following table lists the visual states for the <xref:System.Windows.Controls.MenuItem> control.</span></span>  
  
|<span data-ttu-id="d86ba-137">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="d86ba-137">VisualState Name</span></span>|<span data-ttu-id="d86ba-138">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="d86ba-138">VisualStateGroup Name</span></span>|<span data-ttu-id="d86ba-139">説明</span><span class="sxs-lookup"><span data-stu-id="d86ba-139">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="d86ba-140">有効</span><span class="sxs-lookup"><span data-stu-id="d86ba-140">Valid</span></span>|<span data-ttu-id="d86ba-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d86ba-141">ValidationStates</span></span>|<span data-ttu-id="d86ba-142">コントロールを使用して、<xref:System.Windows.Controls.Validation>クラスおよび<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`false`します。</span><span class="sxs-lookup"><span data-stu-id="d86ba-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="d86ba-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="d86ba-143">InvalidFocused</span></span>|<span data-ttu-id="d86ba-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d86ba-144">ValidationStates</span></span>|<span data-ttu-id="d86ba-145"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="d86ba-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="d86ba-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="d86ba-146">InvalidUnfocused</span></span>|<span data-ttu-id="d86ba-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d86ba-147">ValidationStates</span></span>|<span data-ttu-id="d86ba-148"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスがないです。</span><span class="sxs-lookup"><span data-stu-id="d86ba-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="menu-and-menuitem-controltemplate-example"></a><span data-ttu-id="d86ba-149">メニューおよび MenuItem ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="d86ba-149">Menu and MenuItem ControlTemplate Example</span></span>  
 <span data-ttu-id="d86ba-150">次の例は、定義する方法を示します、<xref:System.Windows.Controls.ControlTemplate>の<xref:System.Windows.Controls.Menu>コントロール。</span><span class="sxs-lookup"><span data-stu-id="d86ba-150">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Menu](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menu)]  
  
 <span data-ttu-id="d86ba-151">次の例は、定義する方法を示します、<xref:System.Windows.Controls.ControlTemplate>の<xref:System.Windows.Controls.MenuItem>コントロール。</span><span class="sxs-lookup"><span data-stu-id="d86ba-151">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.MenuItem> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#MenuItem](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menuitem)]  
  
 <span data-ttu-id="d86ba-152">次の例では、定義、 `MenuScrollViewer`、前の例で使用されます。</span><span class="sxs-lookup"><span data-stu-id="d86ba-152">The following example defines the `MenuScrollViewer`, which is used in the previous example.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#MenuScrollViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menuscrollviewer)]  
  
 <span data-ttu-id="d86ba-153"><xref:System.Windows.Controls.ControlTemplate>例は、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="d86ba-153">The <xref:System.Windows.Controls.ControlTemplate> examples use one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="d86ba-154">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d86ba-154">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d86ba-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="d86ba-155">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="d86ba-156">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="d86ba-156">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="d86ba-157">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="d86ba-157">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="d86ba-158">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="d86ba-158">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="d86ba-159">ControlTemplate の作成による既存のコントロールの外観のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="d86ba-159">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
