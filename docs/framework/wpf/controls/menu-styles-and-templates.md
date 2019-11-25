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
ms.openlocfilehash: 3ce0be1fdeeee1465c2facb414cc7a081b268eb5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283473"
---
# <a name="menu-styles-and-templates"></a><span data-ttu-id="b93cd-102">メニューのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="b93cd-102">Menu Styles and Templates</span></span>
<span data-ttu-id="b93cd-103">このトピックでは、<xref:System.Windows.Controls.Menu> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b93cd-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Menu> control.</span></span> <span data-ttu-id="b93cd-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="b93cd-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="b93cd-105">詳細については、「[コントロールのテンプレートを作成する](../../../desktop-wpf/themes/how-to-create-apply-template.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b93cd-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="menu-parts"></a><span data-ttu-id="b93cd-106">メニューパーツ</span><span class="sxs-lookup"><span data-stu-id="b93cd-106">Menu Parts</span></span>  
 <span data-ttu-id="b93cd-107"><xref:System.Windows.Controls.Menu> コントロールには、名前付きの部分がありません。</span><span class="sxs-lookup"><span data-stu-id="b93cd-107">The <xref:System.Windows.Controls.Menu> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="b93cd-108"><xref:System.Windows.Controls.Menu>の <xref:System.Windows.Controls.ControlTemplate> を作成する場合、テンプレートに <xref:System.Windows.Controls.ScrollViewer>内の <xref:System.Windows.Controls.ItemsPresenter> が含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b93cd-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.Menu>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="b93cd-109">(<xref:System.Windows.Controls.ItemsPresenter> には、<xref:System.Windows.Controls.Menu>内の各項目が表示されます。 <xref:System.Windows.Controls.ScrollViewer> では、コントロール内でのスクロールが有効になります)。</span><span class="sxs-lookup"><span data-stu-id="b93cd-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.Menu>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="b93cd-110"><xref:System.Windows.Controls.ItemsPresenter> が <xref:System.Windows.Controls.ScrollViewer>の直接の子でない場合は、<xref:System.Windows.Controls.ItemsPresenter> の名前を `ItemsPresenter`に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b93cd-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="menu-states"></a><span data-ttu-id="b93cd-111">メニューの状態</span><span class="sxs-lookup"><span data-stu-id="b93cd-111">Menu States</span></span>  
 <span data-ttu-id="b93cd-112">次の表は、<xref:System.Windows.Controls.Menu> コントロールの表示状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="b93cd-112">The following table lists the visual states for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
|<span data-ttu-id="b93cd-113">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="b93cd-113">VisualState Name</span></span>|<span data-ttu-id="b93cd-114">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="b93cd-114">VisualStateGroup Name</span></span>|<span data-ttu-id="b93cd-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="b93cd-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="b93cd-116">有効</span><span class="sxs-lookup"><span data-stu-id="b93cd-116">Valid</span></span>|<span data-ttu-id="b93cd-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b93cd-117">ValidationStates</span></span>|<span data-ttu-id="b93cd-118">コントロールは <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false`ます。</span><span class="sxs-lookup"><span data-stu-id="b93cd-118">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="b93cd-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="b93cd-119">InvalidFocused</span></span>|<span data-ttu-id="b93cd-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b93cd-120">ValidationStates</span></span>|<span data-ttu-id="b93cd-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがある `true` です。</span><span class="sxs-lookup"><span data-stu-id="b93cd-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="b93cd-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="b93cd-122">InvalidUnfocused</span></span>|<span data-ttu-id="b93cd-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b93cd-123">ValidationStates</span></span>|<span data-ttu-id="b93cd-124"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがない `true` です。</span><span class="sxs-lookup"><span data-stu-id="b93cd-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="menuitem-parts"></a><span data-ttu-id="b93cd-125">MenuItem パーツ</span><span class="sxs-lookup"><span data-stu-id="b93cd-125">MenuItem Parts</span></span>  
 <span data-ttu-id="b93cd-126">次の表に、<xref:System.Windows.Controls.Menu> コントロールの名前付きの部分を示します。</span><span class="sxs-lookup"><span data-stu-id="b93cd-126">The following table lists the named parts for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
|<span data-ttu-id="b93cd-127">パーツ</span><span class="sxs-lookup"><span data-stu-id="b93cd-127">Part</span></span>|<span data-ttu-id="b93cd-128">[種類]</span><span class="sxs-lookup"><span data-stu-id="b93cd-128">Type</span></span>|<span data-ttu-id="b93cd-129">[説明]</span><span class="sxs-lookup"><span data-stu-id="b93cd-129">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="b93cd-130">PART_Popup</span><span class="sxs-lookup"><span data-stu-id="b93cd-130">PART_Popup</span></span>|<xref:System.Windows.Controls.Primitives.Popup>|<span data-ttu-id="b93cd-131">サブメニューの領域。</span><span class="sxs-lookup"><span data-stu-id="b93cd-131">The area for the submenu.</span></span>|  
  
 <span data-ttu-id="b93cd-132"><xref:System.Windows.Controls.MenuItem>の <xref:System.Windows.Controls.ControlTemplate> を作成する場合、テンプレートに <xref:System.Windows.Controls.ScrollViewer>内の <xref:System.Windows.Controls.ItemsPresenter> が含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b93cd-132">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.MenuItem>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="b93cd-133">(<xref:System.Windows.Controls.ItemsPresenter> には、<xref:System.Windows.Controls.MenuItem>内の各項目が表示されます。 <xref:System.Windows.Controls.ScrollViewer> では、コントロール内でのスクロールが有効になります)。</span><span class="sxs-lookup"><span data-stu-id="b93cd-133">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.MenuItem>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="b93cd-134"><xref:System.Windows.Controls.ItemsPresenter> が <xref:System.Windows.Controls.ScrollViewer>の直接の子でない場合は、<xref:System.Windows.Controls.ItemsPresenter> の名前を `ItemsPresenter`に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b93cd-134">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="menuitem-states"></a><span data-ttu-id="b93cd-135">MenuItem の状態</span><span class="sxs-lookup"><span data-stu-id="b93cd-135">MenuItem States</span></span>  
 <span data-ttu-id="b93cd-136">次の表は、<xref:System.Windows.Controls.MenuItem> コントロールの表示状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="b93cd-136">The following table lists the visual states for the <xref:System.Windows.Controls.MenuItem> control.</span></span>  
  
|<span data-ttu-id="b93cd-137">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="b93cd-137">VisualState Name</span></span>|<span data-ttu-id="b93cd-138">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="b93cd-138">VisualStateGroup Name</span></span>|<span data-ttu-id="b93cd-139">[説明]</span><span class="sxs-lookup"><span data-stu-id="b93cd-139">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="b93cd-140">有効</span><span class="sxs-lookup"><span data-stu-id="b93cd-140">Valid</span></span>|<span data-ttu-id="b93cd-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b93cd-141">ValidationStates</span></span>|<span data-ttu-id="b93cd-142">コントロールは <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false`ます。</span><span class="sxs-lookup"><span data-stu-id="b93cd-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="b93cd-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="b93cd-143">InvalidFocused</span></span>|<span data-ttu-id="b93cd-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b93cd-144">ValidationStates</span></span>|<span data-ttu-id="b93cd-145"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがある `true` です。</span><span class="sxs-lookup"><span data-stu-id="b93cd-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="b93cd-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="b93cd-146">InvalidUnfocused</span></span>|<span data-ttu-id="b93cd-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b93cd-147">ValidationStates</span></span>|<span data-ttu-id="b93cd-148"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがない `true` です。</span><span class="sxs-lookup"><span data-stu-id="b93cd-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="menu-and-menuitem-controltemplate-example"></a><span data-ttu-id="b93cd-149">Menu と MenuItem ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="b93cd-149">Menu and MenuItem ControlTemplate Example</span></span>  
 <span data-ttu-id="b93cd-150">次の例は、<xref:System.Windows.Controls.Menu> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b93cd-150">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Menu](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menu)]  
  
 <span data-ttu-id="b93cd-151">次の例は、<xref:System.Windows.Controls.MenuItem> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b93cd-151">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.MenuItem> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#MenuItem](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menuitem)]  
  
 <span data-ttu-id="b93cd-152">次の例では、前の例で使用した `MenuScrollViewer`を定義します。</span><span class="sxs-lookup"><span data-stu-id="b93cd-152">The following example defines the `MenuScrollViewer`, which is used in the previous example.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#MenuScrollViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menuscrollviewer)]  
  
 <span data-ttu-id="b93cd-153"><xref:System.Windows.Controls.ControlTemplate> の例では、次のリソースの1つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="b93cd-153">The <xref:System.Windows.Controls.ControlTemplate> examples use one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="b93cd-154">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b93cd-154">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b93cd-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="b93cd-155">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="b93cd-156">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="b93cd-156">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="b93cd-157">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="b93cd-157">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="b93cd-158">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="b93cd-158">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="b93cd-159">コントロールのテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="b93cd-159">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
