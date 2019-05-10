---
title: WPF のコンテンツ モデル
ms.date: 03/30/2017
helpviewer_keywords:
- UIElement class [WPF], displaying content
- content model [WPF], controls
- controls [WPF], displaying text
- content display [WPF], controls
- controls [WPF], formatting text
- displaying content [WPF]
- arbitrary content classes [WPF], content model
- ContentControl class [WPF], displaying content
ms.assetid: 214da5ef-547a-4cf8-9b07-4aa8a0e52cdd
ms.openlocfilehash: 652a8b831d29c8da8dc651558351a5bd4ff5ce84
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665153"
---
# <a name="wpf-content-model"></a><span data-ttu-id="a1037-102">WPF のコンテンツ モデル</span><span class="sxs-lookup"><span data-stu-id="a1037-102">WPF Content Model</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="a1037-103">は、多くのコントロールやコントロールのような型を提供する表示プラットフォームで、その主な目的は、異なる種類のコンテンツを表示することです。</span><span class="sxs-lookup"><span data-stu-id="a1037-103">is a presentation platform that provides many controls and control-like types whose primary purpose is to display different types of content.</span></span> <span data-ttu-id="a1037-104">使用するコントロールまたは派生元のコントロールを判断するには、特定のコントロールが最適に表示できるオブジェクトの種類を理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1037-104">To determine which control to use or which control to derive from, you should understand the kinds of objects a particular control can best display.</span></span>  
  
 <span data-ttu-id="a1037-105">このトピックは、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] コントロールとコントロールのような型に関するコンテンツ モデルのまとめです。</span><span class="sxs-lookup"><span data-stu-id="a1037-105">This topic summarizes the content model for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control and control-like types.</span></span> <span data-ttu-id="a1037-106">コンテンツ モデルは、どのようなコンテンツをコントロールで使用できるかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a1037-106">The content model describes what content can be used in a control.</span></span> <span data-ttu-id="a1037-107">このトピックは、各コンテンツ モデルのコンテンツのプロパティもリストします。</span><span class="sxs-lookup"><span data-stu-id="a1037-107">This topic also lists the content properties for each content model.</span></span> <span data-ttu-id="a1037-108">コンテンツのプロパティは、オブジェクトのコンテンツの格納に使用されるプロパティです。</span><span class="sxs-lookup"><span data-stu-id="a1037-108">A content property is a property that is used to store the content of the object.</span></span>  

<a name="classes_that_contain_arbitrary_content"></a>   
## <a name="classes-that-contain-arbitrary-content"></a><span data-ttu-id="a1037-109">任意のコンテンツを含むクラス</span><span class="sxs-lookup"><span data-stu-id="a1037-109">Classes That Contain Arbitrary Content</span></span>  
 <span data-ttu-id="a1037-110">一部のコントロールは、文字列などの任意の型のオブジェクトを含めることができます、<xref:System.DateTime>オブジェクト、または<xref:System.Windows.UIElement>追加項目のコンテナーであります。</span><span class="sxs-lookup"><span data-stu-id="a1037-110">Some controls can contain an object of any type, such as a string, a <xref:System.DateTime> object, or a <xref:System.Windows.UIElement> that is a container for additional items.</span></span> <span data-ttu-id="a1037-111">たとえば、<xref:System.Windows.Controls.Button>イメージと任意のテキストに含めることができます、<xref:System.Windows.Controls.CheckBox>の値を含めることができます<xref:System.DateTime.Now%2A?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="a1037-111">For example, a <xref:System.Windows.Controls.Button> can contain an image and some text; or a <xref:System.Windows.Controls.CheckBox> can contain the value of <xref:System.DateTime.Now%2A?displayProperty=nameWithType>.</span></span>  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="a1037-112">には、任意のコンテンツを含めることができる 4 つのクラスがあります。</span><span class="sxs-lookup"><span data-stu-id="a1037-112">has four classes that can contain arbitrary content.</span></span> <span data-ttu-id="a1037-113">次の表から継承するクラス、<xref:System.Windows.Controls.Control>します。</span><span class="sxs-lookup"><span data-stu-id="a1037-113">The following table lists the classes, which inherit from <xref:System.Windows.Controls.Control>.</span></span>  
  
|<span data-ttu-id="a1037-114">任意のコンテンツを含むクラス</span><span class="sxs-lookup"><span data-stu-id="a1037-114">Class that contains arbitrary content</span></span>|<span data-ttu-id="a1037-115">Content</span><span class="sxs-lookup"><span data-stu-id="a1037-115">Content</span></span>|  
|-------------------------------------------|-------------|  
|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="a1037-116">1 つの任意のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a1037-116">A single arbitrary object.</span></span>|  
|<xref:System.Windows.Controls.HeaderedContentControl>|<span data-ttu-id="a1037-117">ヘッダーと 1 つの項目。両方とも任意のオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="a1037-117">A header and a single item, both of which are arbitrary objects.</span></span>|  
|<xref:System.Windows.Controls.ItemsControl>|<span data-ttu-id="a1037-118">任意のオブジェクトのコレクション。</span><span class="sxs-lookup"><span data-stu-id="a1037-118">A collection of arbitrary objects.</span></span>|  
|<xref:System.Windows.Controls.HeaderedItemsControl>|<span data-ttu-id="a1037-119">ヘッダーと項目のコレクション。すべて任意のオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="a1037-119">A header and a collection of items, all of which are arbitrary objects.</span></span>|  
  
 <span data-ttu-id="a1037-120">これらのクラスから継承するコントロールは、同じ種類のコンテンツを格納でき、同じ方法でコンテンツを処理することができます。</span><span class="sxs-lookup"><span data-stu-id="a1037-120">Controls that inherit from these classes can contain the same type of content and treat the content in the same way.</span></span> <span data-ttu-id="a1037-121">次の図は、イメージを含む各コンテンツ モデルといくつかのテキストから 1 つのコントロールを示しています。</span><span class="sxs-lookup"><span data-stu-id="a1037-121">The following illustration shows one control from each content model that contains an image and some text:</span></span>  
  
 ![各コンテンツ モデルから 1 つ、4 つの異なるコントロールを示すスクリーン ショット。](./media/wpf-content-model/control-content-model-image-text.png)  
  
### <a name="controls-that-contain-a-single-arbitrary-object"></a><span data-ttu-id="a1037-123">任意の 1 つのオブジェクトを格納しているコントロール</span><span class="sxs-lookup"><span data-stu-id="a1037-123">Controls That Contain a Single Arbitrary Object</span></span>  
 <span data-ttu-id="a1037-124"><xref:System.Windows.Controls.ContentControl>クラスには、1 つ任意のコンテンツにはが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a1037-124">The <xref:System.Windows.Controls.ContentControl> class contains a single piece of arbitrary content.</span></span> <span data-ttu-id="a1037-125">コンテンツのプロパティは<xref:System.Windows.Controls.ContentControl.Content%2A>します。</span><span class="sxs-lookup"><span data-stu-id="a1037-125">Its content property is <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span> <span data-ttu-id="a1037-126">次のコントロールから継承<xref:System.Windows.Controls.ContentControl>とそのコンテンツ モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="a1037-126">The following controls inherit from <xref:System.Windows.Controls.ContentControl> and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.Button>  
  
- <xref:System.Windows.Controls.Primitives.ButtonBase>  
  
- <xref:System.Windows.Controls.CheckBox>  
  
- <xref:System.Windows.Controls.ComboBoxItem>  
  
- <xref:System.Windows.Controls.ContentControl>  
  
- <xref:System.Windows.Controls.Frame>  
  
- <xref:System.Windows.Controls.GridViewColumnHeader>  
  
- <xref:System.Windows.Controls.GroupItem>  
  
- <xref:System.Windows.Controls.Label>  
  
- <xref:System.Windows.Controls.ListBoxItem>  
  
- <xref:System.Windows.Controls.ListViewItem>  
  
- <xref:System.Windows.Navigation.NavigationWindow>  
  
- <xref:System.Windows.Controls.RadioButton>  
  
- <xref:System.Windows.Controls.Primitives.RepeatButton>  
  
- <xref:System.Windows.Controls.ScrollViewer>  
  
- <xref:System.Windows.Controls.Primitives.StatusBarItem>  
  
- <xref:System.Windows.Controls.Primitives.ToggleButton>  
  
- <xref:System.Windows.Controls.ToolTip>  
  
- <xref:System.Windows.Controls.UserControl>  
  
- <xref:System.Windows.Window>  
  
 <span data-ttu-id="a1037-127">次の図は 4 つのボタンが<xref:System.Windows.Controls.ContentControl.Content%2A>、文字列に設定されている、<xref:System.DateTime>オブジェクト、<xref:System.Windows.Shapes.Rectangle>と<xref:System.Windows.Controls.Panel>を格納している、<xref:System.Windows.Shapes.Ellipse>と<xref:System.Windows.Controls.TextBlock>:</span><span class="sxs-lookup"><span data-stu-id="a1037-127">The following illustration shows four buttons whose <xref:System.Windows.Controls.ContentControl.Content%2A> is set to a string, a <xref:System.DateTime> object, a <xref:System.Windows.Shapes.Rectangle>, and a <xref:System.Windows.Controls.Panel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>:</span></span>  
  
 ![さまざまなコンテンツ タイプの 4 つのボタンを示すスクリーン ショット。](./media/wpf-content-model/control-content-model-buttons.png)  
  
 <span data-ttu-id="a1037-129">設定する方法の例については、<xref:System.Windows.Controls.ContentControl.Content%2A>プロパティを参照してください<xref:System.Windows.Controls.ContentControl>します。</span><span class="sxs-lookup"><span data-stu-id="a1037-129">For an example of how to set the <xref:System.Windows.Controls.ContentControl.Content%2A> property, see <xref:System.Windows.Controls.ContentControl>.</span></span>  
  
### <a name="controls-that-contain-a-header-and-a-single-arbitrary-object"></a><span data-ttu-id="a1037-130">ヘッダーと任意の 1 つのオブジェクトを格納しているコントロール</span><span class="sxs-lookup"><span data-stu-id="a1037-130">Controls That Contain a Header and a Single Arbitrary Object</span></span>  
 <span data-ttu-id="a1037-131"><xref:System.Windows.Controls.HeaderedContentControl>クラスから継承<xref:System.Windows.Controls.ContentControl>ヘッダーとコンテンツが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a1037-131">The <xref:System.Windows.Controls.HeaderedContentControl> class inherits from <xref:System.Windows.Controls.ContentControl> and displays content with a header.</span></span> <span data-ttu-id="a1037-132">コンテンツのプロパティを継承<xref:System.Windows.Controls.ContentControl.Content%2A>から<xref:System.Windows.Controls.ContentControl>を定義し、<xref:System.Windows.Controls.HeaderedContentControl.Header%2A>型のプロパティを<xref:System.Object>。 したがって、任意のオブジェクトはどちらもします。</span><span class="sxs-lookup"><span data-stu-id="a1037-132">It inherits the content property, <xref:System.Windows.Controls.ContentControl.Content%2A>, from <xref:System.Windows.Controls.ContentControl> and defines the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> property that is of type <xref:System.Object>; therefore, both can be an arbitrary object.</span></span>  
  
 <span data-ttu-id="a1037-133">次のコントロールから継承<xref:System.Windows.Controls.HeaderedContentControl>とそのコンテンツ モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="a1037-133">The following controls inherit from <xref:System.Windows.Controls.HeaderedContentControl> and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.Expander>  
  
- <xref:System.Windows.Controls.GroupBox>  
  
- <xref:System.Windows.Controls.TabItem>  
  
 <span data-ttu-id="a1037-134">次の図は 2 つ<xref:System.Windows.Controls.TabItem>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a1037-134">The following illustration shows two <xref:System.Windows.Controls.TabItem> objects.</span></span> <span data-ttu-id="a1037-135">最初の<xref:System.Windows.Controls.TabItem>が<xref:System.Windows.UIElement>としてオブジェクト、 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 、<xref:System.Windows.Controls.ContentControl.Content%2A>します。</span><span class="sxs-lookup"><span data-stu-id="a1037-135">The first <xref:System.Windows.Controls.TabItem> has <xref:System.Windows.UIElement> objects as the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and the <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span> <span data-ttu-id="a1037-136"><xref:System.Windows.Controls.HeaderedContentControl.Header%2A>に設定されている、<xref:System.Windows.Controls.StackPanel>を格納している、<xref:System.Windows.Shapes.Ellipse>と<xref:System.Windows.Controls.TextBlock>します。</span><span class="sxs-lookup"><span data-stu-id="a1037-136">The <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> is set to a <xref:System.Windows.Controls.StackPanel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="a1037-137"><xref:System.Windows.Controls.ContentControl.Content%2A>に設定されている、<xref:System.Windows.Controls.StackPanel>を格納している、<xref:System.Windows.Controls.TextBlock>と<xref:System.Windows.Controls.Label>します。</span><span class="sxs-lookup"><span data-stu-id="a1037-137">The <xref:System.Windows.Controls.ContentControl.Content%2A> is set to a <xref:System.Windows.Controls.StackPanel> that contains a <xref:System.Windows.Controls.TextBlock> and a <xref:System.Windows.Controls.Label>.</span></span> <span data-ttu-id="a1037-138">2 番目の<xref:System.Windows.Controls.TabItem>に文字列を持つ、<xref:System.Windows.Controls.HeaderedContentControl.Header%2A>と<xref:System.Windows.Controls.TextBlock>で、<xref:System.Windows.Controls.ContentControl.Content%2A>します。</span><span class="sxs-lookup"><span data-stu-id="a1037-138">The second <xref:System.Windows.Controls.TabItem> has a string in the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and a <xref:System.Windows.Controls.TextBlock> in the <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span>  
  
 ![ヘッダー プロパティにさまざまな種類を使用する TabControl します。](./media/wpf-content-model/control-content-model-tab.png)  
  
 <span data-ttu-id="a1037-140">作成する方法の例については<xref:System.Windows.Controls.TabItem>、オブジェクトを参照してください<xref:System.Windows.Controls.HeaderedContentControl>します。</span><span class="sxs-lookup"><span data-stu-id="a1037-140">For an example of how to create <xref:System.Windows.Controls.TabItem> objects, see <xref:System.Windows.Controls.HeaderedContentControl>.</span></span>  
  
### <a name="controls-that-contain-a-collection-of-arbitrary-objects"></a><span data-ttu-id="a1037-141">任意のオブジェクトのコレクションを格納しているコントロール</span><span class="sxs-lookup"><span data-stu-id="a1037-141">Controls That Contain a Collection of Arbitrary Objects</span></span>  
 <span data-ttu-id="a1037-142"><xref:System.Windows.Controls.ItemsControl>クラスから継承<xref:System.Windows.Controls.Control>文字列、オブジェクト、またはその他の要素など、複数の項目を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a1037-142">The <xref:System.Windows.Controls.ItemsControl> class inherits from <xref:System.Windows.Controls.Control> and can contain multiple items, such as strings, objects, or other elements.</span></span> <span data-ttu-id="a1037-143">そのコンテンツのプロパティは<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>と<xref:System.Windows.Controls.ItemsControl.Items%2A>します。</span><span class="sxs-lookup"><span data-stu-id="a1037-143">Its content properties are <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> and <xref:System.Windows.Controls.ItemsControl.Items%2A>.</span></span> <span data-ttu-id="a1037-144"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 設定に通常使用、<xref:System.Windows.Controls.ItemsControl>データ コレクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="a1037-144"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> is typically used to populate the <xref:System.Windows.Controls.ItemsControl> with a data collection.</span></span> <span data-ttu-id="a1037-145">設定するコレクションを使用しないかどうか、<xref:System.Windows.Controls.ItemsControl>を使用して項目を追加することができます、<xref:System.Windows.Controls.ItemsControl.Items%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="a1037-145">If you do not want to use a collection to populate the <xref:System.Windows.Controls.ItemsControl>, you can add items by using the <xref:System.Windows.Controls.ItemsControl.Items%2A> property.</span></span>  
  
 <span data-ttu-id="a1037-146">次のコントロールから継承<xref:System.Windows.Controls.ItemsControl>とそのコンテンツ モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="a1037-146">The following controls inherit from <xref:System.Windows.Controls.ItemsControl> and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.Menu>  
  
- <xref:System.Windows.Controls.Primitives.MenuBase>  
  
- <xref:System.Windows.Controls.ContextMenu>  
  
- <xref:System.Windows.Controls.ComboBox>  
  
- <xref:System.Windows.Controls.ItemsControl>  
  
- <xref:System.Windows.Controls.ListBox>  
  
- <xref:System.Windows.Controls.ListView>  
  
- <xref:System.Windows.Controls.TabControl>  
  
- <xref:System.Windows.Controls.TreeView>  
  
- <xref:System.Windows.Controls.Primitives.Selector>  
  
- <xref:System.Windows.Controls.Primitives.StatusBar>  
  
 <span data-ttu-id="a1037-147">次の図は、<xref:System.Windows.Controls.ListBox>この種類のアイテムを格納しています。</span><span class="sxs-lookup"><span data-stu-id="a1037-147">The following illustration shows a <xref:System.Windows.Controls.ListBox> that contains these types of items:</span></span>  
  
- <span data-ttu-id="a1037-148">文字列。</span><span class="sxs-lookup"><span data-stu-id="a1037-148">A string.</span></span>  
  
- <span data-ttu-id="a1037-149"><xref:System.DateTime> オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a1037-149">A <xref:System.DateTime> object.</span></span>  
  
- <span data-ttu-id="a1037-150"><xref:System.Windows.UIElement>。</span><span class="sxs-lookup"><span data-stu-id="a1037-150">A <xref:System.Windows.UIElement>.</span></span>  
  
- <span data-ttu-id="a1037-151">A<xref:System.Windows.Controls.Panel>を格納している、<xref:System.Windows.Shapes.Ellipse>と<xref:System.Windows.Controls.TextBlock>します。</span><span class="sxs-lookup"><span data-stu-id="a1037-151">A <xref:System.Windows.Controls.Panel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 ![次の 4 つの種類のコンテンツがリスト ボックスを示すスクリーン ショット。](./media/wpf-content-model/control-content-model-listbox.png)  
  
### <a name="controls-that-contain-a-header-and-a-collection-of-arbitrary-objects"></a><span data-ttu-id="a1037-153">ヘッダーと任意のオブジェクトのコレクションを含むコントロール</span><span class="sxs-lookup"><span data-stu-id="a1037-153">Controls That Contain a Header and a Collection of Arbitrary Objects</span></span>  
 <span data-ttu-id="a1037-154"><xref:System.Windows.Controls.HeaderedItemsControl>クラスから継承<xref:System.Windows.Controls.ItemsControl>文字列、オブジェクト、または他の要素やヘッダーなど、複数の項目を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a1037-154">The <xref:System.Windows.Controls.HeaderedItemsControl> class inherits from <xref:System.Windows.Controls.ItemsControl> and can contain multiple items, such as strings, objects, or other elements, and a header.</span></span> <span data-ttu-id="a1037-155">継承、<xref:System.Windows.Controls.ItemsControl>コンテンツのプロパティを<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>と<xref:System.Windows.Controls.ItemsControl.Items%2A>、し、定義、<xref:System.Windows.Controls.HeaderedItemsControl.Header%2A>ことができる任意のオブジェクト プロパティです。</span><span class="sxs-lookup"><span data-stu-id="a1037-155">It inherits the <xref:System.Windows.Controls.ItemsControl> content properties, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>, and <xref:System.Windows.Controls.ItemsControl.Items%2A>, and it defines the <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> property that can be an arbitrary object.</span></span>  
  
 <span data-ttu-id="a1037-156">次のコントロールから継承<xref:System.Windows.Controls.HeaderedItemsControl>とそのコンテンツ モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="a1037-156">The following controls inherit from <xref:System.Windows.Controls.HeaderedItemsControl> and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.MenuItem>  
  
- <xref:System.Windows.Controls.ToolBar>  
  
- <xref:System.Windows.Controls.TreeViewItem>  
  
<a name="classes_that_contain_a_collection_of_uielement_objects"></a>   
## <a name="classes-that-contain-a-collection-of-uielement-objects"></a><span data-ttu-id="a1037-157">UIElement オブジェクトのコレクションを含むクラス</span><span class="sxs-lookup"><span data-stu-id="a1037-157">Classes That Contain a Collection of UIElement Objects</span></span>  
 <span data-ttu-id="a1037-158"><xref:System.Windows.Controls.Panel>クラスを配置し、子を整列<xref:System.Windows.UIElement>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a1037-158">The <xref:System.Windows.Controls.Panel> class positions and arranges child <xref:System.Windows.UIElement> objects.</span></span> <span data-ttu-id="a1037-159">コンテンツのプロパティは<xref:System.Windows.Controls.Panel.Children%2A>します。</span><span class="sxs-lookup"><span data-stu-id="a1037-159">Its content property is <xref:System.Windows.Controls.Panel.Children%2A>.</span></span>  
  
 <span data-ttu-id="a1037-160">次のクラスから継承、<xref:System.Windows.Controls.Panel>クラスし、そのコンテンツ モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="a1037-160">The following classes inherit from the <xref:System.Windows.Controls.Panel> class and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.Canvas>  
  
- <xref:System.Windows.Controls.DockPanel>  
  
- <xref:System.Windows.Controls.Grid>  
  
- <xref:System.Windows.Controls.Primitives.TabPanel>  
  
- <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>  
  
- <xref:System.Windows.Controls.Primitives.ToolBarPanel>  
  
- <xref:System.Windows.Controls.Primitives.UniformGrid>  
  
- <xref:System.Windows.Controls.StackPanel>  
  
- <xref:System.Windows.Controls.VirtualizingPanel>  
  
- <xref:System.Windows.Controls.VirtualizingStackPanel>  
  
- <xref:System.Windows.Controls.WrapPanel>  
  
 <span data-ttu-id="a1037-161">詳細については、「[Panels Overview](panels-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1037-161">For more information, see [Panels Overview](panels-overview.md).</span></span>  
  
<a name="classes_that_affects_the_appearance_of_a_uielement"></a>   
## <a name="classes-that-affect-the-appearance-of-a-uielement"></a><span data-ttu-id="a1037-162">UIElement の外観に影響を与えるクラス</span><span class="sxs-lookup"><span data-stu-id="a1037-162">Classes That Affect the Appearance of a UIElement</span></span>  
 <span data-ttu-id="a1037-163"><xref:System.Windows.Controls.Decorator>クラスまたは 1 つの子の周囲に視覚効果を適用する<xref:System.Windows.UIElement>します。</span><span class="sxs-lookup"><span data-stu-id="a1037-163">The <xref:System.Windows.Controls.Decorator> class applies visual effects onto or around a single child <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="a1037-164">コンテンツのプロパティは<xref:System.Windows.Controls.Decorator.Child%2A>します。</span><span class="sxs-lookup"><span data-stu-id="a1037-164">Its content property is <xref:System.Windows.Controls.Decorator.Child%2A>.</span></span> <span data-ttu-id="a1037-165">次のクラスから継承<xref:System.Windows.Controls.Decorator>とそのコンテンツ モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="a1037-165">The following classes inherit from <xref:System.Windows.Controls.Decorator> and use its content model:</span></span>  
  
- <xref:System.Windows.Documents.AdornerDecorator>  
  
- <xref:System.Windows.Controls.Border>  
  
- <xref:System.Windows.Controls.Primitives.BulletDecorator>  
  
- <xref:Microsoft.Windows.Themes.ButtonChrome>  
  
- <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>  
  
- <xref:System.Windows.Controls.InkPresenter>  
  
- <xref:Microsoft.Windows.Themes.ListBoxChrome>  
  
- <xref:Microsoft.Windows.Themes.SystemDropShadowChrome>  
  
- <xref:System.Windows.Controls.Viewbox>  
  
 <span data-ttu-id="a1037-166">次の図は、<xref:System.Windows.Controls.TextBox>を持つ (で装飾が)、<xref:System.Windows.Controls.Border>周囲します。</span><span class="sxs-lookup"><span data-stu-id="a1037-166">The following illustration shows a <xref:System.Windows.Controls.TextBox> that has (is decorated with) a <xref:System.Windows.Controls.Border> around it.</span></span>  
  
 <span data-ttu-id="a1037-167">![境界線が黒の TextBox](./media/layout-border-around-textbox.png "Layout_Border_around_TextBox")</span><span class="sxs-lookup"><span data-stu-id="a1037-167">![TextBox with black border](./media/layout-border-around-textbox.png "Layout_Border_around_TextBox")</span></span>  
<span data-ttu-id="a1037-168">境界がある TextBlock</span><span class="sxs-lookup"><span data-stu-id="a1037-168">TextBlock that has a Border</span></span>  
  
<a name="classes_that_provides_visual_feedback_about_a_uielement"></a>   
## <a name="classes-that-provide-visual-feedback-about-a-uielement"></a><span data-ttu-id="a1037-169">UIElement についての視覚的なフィードバックを提供するクラス</span><span class="sxs-lookup"><span data-stu-id="a1037-169">Classes That Provide Visual Feedback About a UIElement</span></span>  
 <span data-ttu-id="a1037-170"><xref:System.Windows.Documents.Adorner>クラスは、ユーザーに視覚的な手掛かりを提供します。</span><span class="sxs-lookup"><span data-stu-id="a1037-170">The <xref:System.Windows.Documents.Adorner> class provides visual cues to a user.</span></span> <span data-ttu-id="a1037-171">たとえば、使用して、<xref:System.Windows.Documents.Adorner>要素に機能ハンドルを追加またはコントロールに関する状態情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="a1037-171">For example, use an <xref:System.Windows.Documents.Adorner> to add functional handles to elements or provide state information about a control.</span></span> <span data-ttu-id="a1037-172"><xref:System.Windows.Documents.Adorner>クラスは、独自の装飾を作成できるようにするフレームワークを提供します。</span><span class="sxs-lookup"><span data-stu-id="a1037-172">The <xref:System.Windows.Documents.Adorner> class provides a framework so that you can create your own adorners.</span></span> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="a1037-173">は実装された装飾は提供しません。</span><span class="sxs-lookup"><span data-stu-id="a1037-173">does not provide any implemented adorners.</span></span> <span data-ttu-id="a1037-174">詳しくは、[Adorners Overview](adorners-overview.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a1037-174">For more information, see [Adorners Overview](adorners-overview.md).</span></span>  
  
<a name="classes_that_enable_users_to_enter_text"></a>   
## <a name="classes-that-enable-users-to-enter-text"></a><span data-ttu-id="a1037-175">ユーザーがテキストを入力できるようにするクラス</span><span class="sxs-lookup"><span data-stu-id="a1037-175">Classes That Enable Users to Enter Text</span></span>  
 <span data-ttu-id="a1037-176">WPF は、ユーザーがテキストを入力できるようにする 3 つの主なコントロールを提供します。</span><span class="sxs-lookup"><span data-stu-id="a1037-176">WPF provides three primary controls that enable users to enter text.</span></span> <span data-ttu-id="a1037-177">各コントロールは、異なる方法で、テキストを表示します。</span><span class="sxs-lookup"><span data-stu-id="a1037-177">Each control displays the text differently.</span></span> <span data-ttu-id="a1037-178">次の表は、これら 3 つのテキスト関連のコントロール、テキストを表示するときのそれぞれの機能、およびコントロールのテキストを格納するそれぞれのプロパティの一覧です。</span><span class="sxs-lookup"><span data-stu-id="a1037-178">The following table lists these three text-related controls, their capabilities when they display text, and their properties that contain the control's text.</span></span>  
  
|<span data-ttu-id="a1037-179">コントロール</span><span class="sxs-lookup"><span data-stu-id="a1037-179">Control</span></span>|<span data-ttu-id="a1037-180">テキストの表示形態</span><span class="sxs-lookup"><span data-stu-id="a1037-180">Text is displayed as</span></span>|<span data-ttu-id="a1037-181">コンテンツのプロパティ</span><span class="sxs-lookup"><span data-stu-id="a1037-181">Content property</span></span>|  
|-------------|--------------------------|----------------------|  
|<xref:System.Windows.Controls.TextBox>|<span data-ttu-id="a1037-182">プレーンテキスト</span><span class="sxs-lookup"><span data-stu-id="a1037-182">Plain text</span></span>|<xref:System.Windows.Controls.TextBox.Text%2A>|  
|<xref:System.Windows.Controls.RichTextBox>|<span data-ttu-id="a1037-183">書式付きテキスト</span><span class="sxs-lookup"><span data-stu-id="a1037-183">Formatted text</span></span>|<xref:System.Windows.Controls.RichTextBox.Document%2A>|  
|<xref:System.Windows.Controls.PasswordBox>|<span data-ttu-id="a1037-184">非表示のテキスト (文字はマスクされます)</span><span class="sxs-lookup"><span data-stu-id="a1037-184">Hidden text (characters are masked)</span></span>|<xref:System.Windows.Controls.PasswordBox.Password%2A>|  
  
<a name="classes_that_display_text"></a>   
## <a name="classes-that-display-your-text"></a><span data-ttu-id="a1037-185">テキストを表示するクラス</span><span class="sxs-lookup"><span data-stu-id="a1037-185">Classes That Display Your Text</span></span>  
 <span data-ttu-id="a1037-186">いくつかのクラスを使用して、プレーン テキストまたは書式設定されたテキストを表示できます。</span><span class="sxs-lookup"><span data-stu-id="a1037-186">Several classes can be used to display plain or formatted text.</span></span> <span data-ttu-id="a1037-187">使用することができます<xref:System.Windows.Controls.TextBlock>少量のテキストを表示します。</span><span class="sxs-lookup"><span data-stu-id="a1037-187">You can use <xref:System.Windows.Controls.TextBlock> to display small amounts of text.</span></span> <span data-ttu-id="a1037-188">大量のテキストを表示する場合は、使用、 <xref:System.Windows.Controls.FlowDocumentReader>、 <xref:System.Windows.Controls.FlowDocumentPageViewer>、または<xref:System.Windows.Controls.FlowDocumentScrollViewer>コントロール。</span><span class="sxs-lookup"><span data-stu-id="a1037-188">If you want to display large amounts of text, use the <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, or <xref:System.Windows.Controls.FlowDocumentScrollViewer> controls.</span></span>  
  
 <span data-ttu-id="a1037-189"><xref:System.Windows.Controls.TextBlock>は 2 つのコンテンツ プロパティがあります:<xref:System.Windows.Controls.TextBlock.Text%2A>と<xref:System.Windows.Controls.TextBlock.Inlines%2A>します。</span><span class="sxs-lookup"><span data-stu-id="a1037-189">The <xref:System.Windows.Controls.TextBlock> has two content properties: <xref:System.Windows.Controls.TextBlock.Text%2A> and <xref:System.Windows.Controls.TextBlock.Inlines%2A>.</span></span> <span data-ttu-id="a1037-190">一貫した書式設定を使用するテキストを表示するときに、<xref:System.Windows.Controls.TextBlock.Text%2A>プロパティは、多くの場合、最適な選択肢です。</span><span class="sxs-lookup"><span data-stu-id="a1037-190">When you want to display text that uses consistent formatting, the <xref:System.Windows.Controls.TextBlock.Text%2A> property is often your best choice.</span></span> <span data-ttu-id="a1037-191">テキスト全体でさまざまな書式設定を使用する場合を使用して、<xref:System.Windows.Controls.TextBlock.Inlines%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="a1037-191">If you plan to use different formatting throughout the text, use the <xref:System.Windows.Controls.TextBlock.Inlines%2A> property.</span></span> <span data-ttu-id="a1037-192"><xref:System.Windows.Controls.TextBlock.Inlines%2A>プロパティのコレクションである<xref:System.Windows.Documents.Inline>オブジェクトで、テキストの書式設定する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="a1037-192">The <xref:System.Windows.Controls.TextBlock.Inlines%2A> property is a collection of <xref:System.Windows.Documents.Inline> objects, which specify how to format text.</span></span>  
  
 <span data-ttu-id="a1037-193">次の表に、コンテンツのプロパティの<xref:System.Windows.Controls.FlowDocumentReader>、 <xref:System.Windows.Controls.FlowDocumentPageViewer>、および<xref:System.Windows.Controls.FlowDocumentScrollViewer>クラス。</span><span class="sxs-lookup"><span data-stu-id="a1037-193">The following table lists the content property for <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, and <xref:System.Windows.Controls.FlowDocumentScrollViewer> classes.</span></span>  
  
|<span data-ttu-id="a1037-194">コントロール</span><span class="sxs-lookup"><span data-stu-id="a1037-194">Control</span></span>|<span data-ttu-id="a1037-195">コンテンツのプロパティ</span><span class="sxs-lookup"><span data-stu-id="a1037-195">Content property</span></span>|<span data-ttu-id="a1037-196">コンテンツのプロパティの型</span><span class="sxs-lookup"><span data-stu-id="a1037-196">Content property type</span></span>|  
|-------------|----------------------|---------------------------|  
|<xref:System.Windows.Controls.FlowDocumentPageViewer>|<span data-ttu-id="a1037-197">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="a1037-197">Document</span></span>|<xref:System.Windows.Documents.IDocumentPaginatorSource>|  
|<xref:System.Windows.Controls.FlowDocumentReader>|<span data-ttu-id="a1037-198">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="a1037-198">Document</span></span>|<xref:System.Windows.Documents.FlowDocument>|  
|<xref:System.Windows.Controls.FlowDocumentScrollViewer>|<span data-ttu-id="a1037-199">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="a1037-199">Document</span></span>|<xref:System.Windows.Documents.FlowDocument>|  
  
 <span data-ttu-id="a1037-200"><xref:System.Windows.Documents.FlowDocument>実装、<xref:System.Windows.Documents.IDocumentPaginatorSource>インターフェイス。 したがって、3 つすべてのクラスがかかることができます、<xref:System.Windows.Documents.FlowDocument>コンテンツとして。</span><span class="sxs-lookup"><span data-stu-id="a1037-200">The <xref:System.Windows.Documents.FlowDocument> implements the <xref:System.Windows.Documents.IDocumentPaginatorSource> interface; therefore, all three classes can take a <xref:System.Windows.Documents.FlowDocument> as content.</span></span>  
  
<a name="classes_that_format_text"></a>   
## <a name="classes-that-format-your-text"></a><span data-ttu-id="a1037-201">テキストを書式設定するクラス</span><span class="sxs-lookup"><span data-stu-id="a1037-201">Classes That Format Your Text</span></span>  
 <span data-ttu-id="a1037-202"><xref:System.Windows.Documents.TextElement> およびその関連クラスは、テキストの書式設定できます。</span><span class="sxs-lookup"><span data-stu-id="a1037-202"><xref:System.Windows.Documents.TextElement> and its related classes allow you to format text.</span></span> <span data-ttu-id="a1037-203"><xref:System.Windows.Documents.TextElement> オブジェクトが含まれてし、に書式を<xref:System.Windows.Controls.TextBlock>と<xref:System.Windows.Documents.FlowDocument>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a1037-203"><xref:System.Windows.Documents.TextElement> objects contain and format text in <xref:System.Windows.Controls.TextBlock> and <xref:System.Windows.Documents.FlowDocument> objects.</span></span> <span data-ttu-id="a1037-204">2 つの主な種類の<xref:System.Windows.Documents.TextElement>オブジェクトが<xref:System.Windows.Documents.Block>要素と<xref:System.Windows.Documents.Inline>要素。</span><span class="sxs-lookup"><span data-stu-id="a1037-204">The two primary types of <xref:System.Windows.Documents.TextElement> objects are <xref:System.Windows.Documents.Block> elements and <xref:System.Windows.Documents.Inline> elements.</span></span> <span data-ttu-id="a1037-205">A<xref:System.Windows.Documents.Block>要素は、段落やリストなどのテキストのブロックを表します。</span><span class="sxs-lookup"><span data-stu-id="a1037-205">A <xref:System.Windows.Documents.Block> element represents a block of text, such as a paragraph or list.</span></span> <span data-ttu-id="a1037-206"><xref:System.Windows.Documents.Inline>要素ブロック内のテキストの一部を表します。</span><span class="sxs-lookup"><span data-stu-id="a1037-206">An <xref:System.Windows.Documents.Inline> element represents a portion of text in a block.</span></span> <span data-ttu-id="a1037-207">多く<xref:System.Windows.Documents.Inline>クラスは、適用先のテキストの書式を指定します。</span><span class="sxs-lookup"><span data-stu-id="a1037-207">Many <xref:System.Windows.Documents.Inline> classes specify formatting for the text to which they are applied.</span></span> <span data-ttu-id="a1037-208">各<xref:System.Windows.Documents.TextElement>独自のコンテンツ モデルがあります。</span><span class="sxs-lookup"><span data-stu-id="a1037-208">Each <xref:System.Windows.Documents.TextElement> has its own content model.</span></span> <span data-ttu-id="a1037-209">詳細については、「[TextElement Content Model Overview](../advanced/textelement-content-model-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1037-209">For more information, see the [TextElement Content Model Overview](../advanced/textelement-content-model-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1037-210">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1037-210">See also</span></span>

- [<span data-ttu-id="a1037-211">詳細設定</span><span class="sxs-lookup"><span data-stu-id="a1037-211">Advanced</span></span>](../advanced/index.md)
