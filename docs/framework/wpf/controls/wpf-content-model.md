---
title: コンテンツ モデル
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
ms.openlocfilehash: ec4e96c0883489135b77f09a3c19f144cb4d30bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187405"
---
# <a name="wpf-content-model"></a><span data-ttu-id="dc54e-102">WPF のコンテンツ モデル</span><span class="sxs-lookup"><span data-stu-id="dc54e-102">WPF Content Model</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="dc54e-103">は、多くのコントロールやコントロールのような型を提供する表示プラットフォームで、その主な目的は、異なる種類のコンテンツを表示することです。</span><span class="sxs-lookup"><span data-stu-id="dc54e-103">is a presentation platform that provides many controls and control-like types whose primary purpose is to display different types of content.</span></span> <span data-ttu-id="dc54e-104">使用するコントロールまたは派生元のコントロールを判断するには、特定のコントロールが最適に表示できるオブジェクトの種類を理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc54e-104">To determine which control to use or which control to derive from, you should understand the kinds of objects a particular control can best display.</span></span>  
  
 <span data-ttu-id="dc54e-105">このトピックは、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] コントロールとコントロールのような型に関するコンテンツ モデルのまとめです。</span><span class="sxs-lookup"><span data-stu-id="dc54e-105">This topic summarizes the content model for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control and control-like types.</span></span> <span data-ttu-id="dc54e-106">コンテンツ モデルは、どのようなコンテンツをコントロールで使用できるかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="dc54e-106">The content model describes what content can be used in a control.</span></span> <span data-ttu-id="dc54e-107">このトピックは、各コンテンツ モデルのコンテンツのプロパティもリストします。</span><span class="sxs-lookup"><span data-stu-id="dc54e-107">This topic also lists the content properties for each content model.</span></span> <span data-ttu-id="dc54e-108">コンテンツのプロパティは、オブジェクトのコンテンツの格納に使用されるプロパティです。</span><span class="sxs-lookup"><span data-stu-id="dc54e-108">A content property is a property that is used to store the content of the object.</span></span>  

<a name="classes_that_contain_arbitrary_content"></a>
## <a name="classes-that-contain-arbitrary-content"></a><span data-ttu-id="dc54e-109">任意のコンテンツを含むクラス</span><span class="sxs-lookup"><span data-stu-id="dc54e-109">Classes That Contain Arbitrary Content</span></span>  
 <span data-ttu-id="dc54e-110">一部のコントロールには、文字列、<xref:System.DateTime>オブジェクト、追加<xref:System.Windows.UIElement>項目のコンテナーであるなど、任意の型のオブジェクトを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="dc54e-110">Some controls can contain an object of any type, such as a string, a <xref:System.DateTime> object, or a <xref:System.Windows.UIElement> that is a container for additional items.</span></span> <span data-ttu-id="dc54e-111">たとえば、 a<xref:System.Windows.Controls.Button>にはイメージとテキストを含めることができます。または、<xref:System.Windows.Controls.CheckBox>の値を含<xref:System.DateTime.Now%2A?displayProperty=nameWithType>めることができます。</span><span class="sxs-lookup"><span data-stu-id="dc54e-111">For example, a <xref:System.Windows.Controls.Button> can contain an image and some text; or a <xref:System.Windows.Controls.CheckBox> can contain the value of <xref:System.DateTime.Now%2A?displayProperty=nameWithType>.</span></span>  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="dc54e-112">には、任意のコンテンツを含めることができる 4 つのクラスがあります。</span><span class="sxs-lookup"><span data-stu-id="dc54e-112">has four classes that can contain arbitrary content.</span></span> <span data-ttu-id="dc54e-113">次の表は、から<xref:System.Windows.Controls.Control>継承するクラスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="dc54e-113">The following table lists the classes, which inherit from <xref:System.Windows.Controls.Control>.</span></span>  
  
|<span data-ttu-id="dc54e-114">任意のコンテンツを含むクラス</span><span class="sxs-lookup"><span data-stu-id="dc54e-114">Class that contains arbitrary content</span></span>|<span data-ttu-id="dc54e-115">コンテンツ</span><span class="sxs-lookup"><span data-stu-id="dc54e-115">Content</span></span>|  
|-------------------------------------------|-------------|  
|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="dc54e-116">1 つの任意のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="dc54e-116">A single arbitrary object.</span></span>|  
|<xref:System.Windows.Controls.HeaderedContentControl>|<span data-ttu-id="dc54e-117">ヘッダーと 1 つの項目。両方とも任意のオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="dc54e-117">A header and a single item, both of which are arbitrary objects.</span></span>|  
|<xref:System.Windows.Controls.ItemsControl>|<span data-ttu-id="dc54e-118">任意のオブジェクトのコレクション。</span><span class="sxs-lookup"><span data-stu-id="dc54e-118">A collection of arbitrary objects.</span></span>|  
|<xref:System.Windows.Controls.HeaderedItemsControl>|<span data-ttu-id="dc54e-119">ヘッダーと項目のコレクション。すべて任意のオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="dc54e-119">A header and a collection of items, all of which are arbitrary objects.</span></span>|  
  
 <span data-ttu-id="dc54e-120">これらのクラスから継承するコントロールは、同じ種類のコンテンツを格納でき、同じ方法でコンテンツを処理することができます。</span><span class="sxs-lookup"><span data-stu-id="dc54e-120">Controls that inherit from these classes can contain the same type of content and treat the content in the same way.</span></span> <span data-ttu-id="dc54e-121">次の図は、イメージとテキストを含む各コンテンツ モデルのコントロールを示しています。</span><span class="sxs-lookup"><span data-stu-id="dc54e-121">The following illustration shows one control from each content model that contains an image and some text:</span></span>  
  
 ![各コンテンツ モデルから 1 つずつ、4 つの異なるコントロールを示すスクリーンショット。](./media/wpf-content-model/control-content-model-image-text.png)  
  
### <a name="controls-that-contain-a-single-arbitrary-object"></a><span data-ttu-id="dc54e-123">任意の 1 つのオブジェクトを格納しているコントロール</span><span class="sxs-lookup"><span data-stu-id="dc54e-123">Controls That Contain a Single Arbitrary Object</span></span>  
 <span data-ttu-id="dc54e-124">この<xref:System.Windows.Controls.ContentControl>クラスには、任意のコンテンツが 1 つ含まれています。</span><span class="sxs-lookup"><span data-stu-id="dc54e-124">The <xref:System.Windows.Controls.ContentControl> class contains a single piece of arbitrary content.</span></span> <span data-ttu-id="dc54e-125">そのコンテンツ プロパティ<xref:System.Windows.Controls.ContentControl.Content%2A>は です。</span><span class="sxs-lookup"><span data-stu-id="dc54e-125">Its content property is <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span> <span data-ttu-id="dc54e-126">次のコントロールは、<xref:System.Windows.Controls.ContentControl>そのコンテンツ モデルから継承して使用します。</span><span class="sxs-lookup"><span data-stu-id="dc54e-126">The following controls inherit from <xref:System.Windows.Controls.ContentControl> and use its content model:</span></span>  
  
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
  
 <span data-ttu-id="dc54e-127">次の<xref:System.Windows.Controls.ContentControl.Content%2A>図は、文字列、<xref:System.DateTime>オブジェクト、および を含む<xref:System.Windows.Shapes.Rectangle>の 4 つの<xref:System.Windows.Controls.Panel>ボタン、<xref:System.Windows.Shapes.Ellipse>および<xref:System.Windows.Controls.TextBlock>を含む を示しています。</span><span class="sxs-lookup"><span data-stu-id="dc54e-127">The following illustration shows four buttons whose <xref:System.Windows.Controls.ContentControl.Content%2A> is set to a string, a <xref:System.DateTime> object, a <xref:System.Windows.Shapes.Rectangle>, and a <xref:System.Windows.Controls.Panel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>:</span></span>  
  
 ![コンテンツ タイプが異なる 4 つのボタンを示すスクリーンショット。](./media/wpf-content-model/control-content-model-buttons.png)  
  
 <span data-ttu-id="dc54e-129"><xref:System.Windows.Controls.ContentControl.Content%2A>プロパティの設定方法の例については、「」を参照<xref:System.Windows.Controls.ContentControl>してください。</span><span class="sxs-lookup"><span data-stu-id="dc54e-129">For an example of how to set the <xref:System.Windows.Controls.ContentControl.Content%2A> property, see <xref:System.Windows.Controls.ContentControl>.</span></span>  
  
### <a name="controls-that-contain-a-header-and-a-single-arbitrary-object"></a><span data-ttu-id="dc54e-130">ヘッダーと任意の 1 つのオブジェクトを格納しているコントロール</span><span class="sxs-lookup"><span data-stu-id="dc54e-130">Controls That Contain a Header and a Single Arbitrary Object</span></span>  
 <span data-ttu-id="dc54e-131">この<xref:System.Windows.Controls.HeaderedContentControl>クラスは、ヘッダー<xref:System.Windows.Controls.ContentControl>を持つコンテンツを継承し、表示します。</span><span class="sxs-lookup"><span data-stu-id="dc54e-131">The <xref:System.Windows.Controls.HeaderedContentControl> class inherits from <xref:System.Windows.Controls.ContentControl> and displays content with a header.</span></span> <span data-ttu-id="dc54e-132">content プロパティ<xref:System.Windows.Controls.ContentControl.Content%2A>を継承<xref:System.Windows.Controls.ContentControl>し、型<xref:System.Windows.Controls.HeaderedContentControl.Header%2A><xref:System.Object>のプロパティを定義します。したがって、両方とも任意のオブジェクトにすることができます。</span><span class="sxs-lookup"><span data-stu-id="dc54e-132">It inherits the content property, <xref:System.Windows.Controls.ContentControl.Content%2A>, from <xref:System.Windows.Controls.ContentControl> and defines the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> property that is of type <xref:System.Object>; therefore, both can be an arbitrary object.</span></span>  
  
 <span data-ttu-id="dc54e-133">次のコントロールは、<xref:System.Windows.Controls.HeaderedContentControl>そのコンテンツ モデルから継承して使用します。</span><span class="sxs-lookup"><span data-stu-id="dc54e-133">The following controls inherit from <xref:System.Windows.Controls.HeaderedContentControl> and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.Expander>  
  
- <xref:System.Windows.Controls.GroupBox>  
  
- <xref:System.Windows.Controls.TabItem>  
  
 <span data-ttu-id="dc54e-134">次の図は、2 つのオブジェクトを<xref:System.Windows.Controls.TabItem>示しています。</span><span class="sxs-lookup"><span data-stu-id="dc54e-134">The following illustration shows two <xref:System.Windows.Controls.TabItem> objects.</span></span> <span data-ttu-id="dc54e-135">最初<xref:System.Windows.Controls.TabItem>のオブジェクト<xref:System.Windows.UIElement>は、<xref:System.Windows.Controls.HeaderedContentControl.Header%2A>および<xref:System.Windows.Controls.ContentControl.Content%2A>として.</span><span class="sxs-lookup"><span data-stu-id="dc54e-135">The first <xref:System.Windows.Controls.TabItem> has <xref:System.Windows.UIElement> objects as the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and the <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span> <span data-ttu-id="dc54e-136">は<xref:System.Windows.Controls.HeaderedContentControl.Header%2A>、<xref:System.Windows.Controls.StackPanel><xref:System.Windows.Shapes.Ellipse>と を含む に<xref:System.Windows.Controls.TextBlock>設定されます。</span><span class="sxs-lookup"><span data-stu-id="dc54e-136">The <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> is set to a <xref:System.Windows.Controls.StackPanel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="dc54e-137">は<xref:System.Windows.Controls.ContentControl.Content%2A>、<xref:System.Windows.Controls.StackPanel><xref:System.Windows.Controls.TextBlock>と を含む に<xref:System.Windows.Controls.Label>設定されます。</span><span class="sxs-lookup"><span data-stu-id="dc54e-137">The <xref:System.Windows.Controls.ContentControl.Content%2A> is set to a <xref:System.Windows.Controls.StackPanel> that contains a <xref:System.Windows.Controls.TextBlock> and a <xref:System.Windows.Controls.Label>.</span></span> <span data-ttu-id="dc54e-138">2<xref:System.Windows.Controls.TabItem>つ目の場合は<xref:System.Windows.Controls.HeaderedContentControl.Header%2A>、<xref:System.Windows.Controls.TextBlock>に文字列<xref:System.Windows.Controls.ContentControl.Content%2A>が含まれ、 に a が含まれます。</span><span class="sxs-lookup"><span data-stu-id="dc54e-138">The second <xref:System.Windows.Controls.TabItem> has a string in the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and a <xref:System.Windows.Controls.TextBlock> in the <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span>  
  
 ![プロパティ内の異なる型を使用するタブ コントロール。](./media/wpf-content-model/control-content-model-tab.png)  
  
 <span data-ttu-id="dc54e-140">オブジェクトの作成<xref:System.Windows.Controls.TabItem>方法の例については、を参照<xref:System.Windows.Controls.HeaderedContentControl>してください。</span><span class="sxs-lookup"><span data-stu-id="dc54e-140">For an example of how to create <xref:System.Windows.Controls.TabItem> objects, see <xref:System.Windows.Controls.HeaderedContentControl>.</span></span>  
  
### <a name="controls-that-contain-a-collection-of-arbitrary-objects"></a><span data-ttu-id="dc54e-141">任意のオブジェクトのコレクションを格納しているコントロール</span><span class="sxs-lookup"><span data-stu-id="dc54e-141">Controls That Contain a Collection of Arbitrary Objects</span></span>  
 <span data-ttu-id="dc54e-142">この<xref:System.Windows.Controls.ItemsControl>クラスは、文字列<xref:System.Windows.Controls.Control>、オブジェクト、その他の要素など、複数の項目を継承し、含めることができます。</span><span class="sxs-lookup"><span data-stu-id="dc54e-142">The <xref:System.Windows.Controls.ItemsControl> class inherits from <xref:System.Windows.Controls.Control> and can contain multiple items, such as strings, objects, or other elements.</span></span> <span data-ttu-id="dc54e-143">そのコンテンツ プロパティ<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>は<xref:System.Windows.Controls.ItemsControl.Items%2A>、 および です。</span><span class="sxs-lookup"><span data-stu-id="dc54e-143">Its content properties are <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> and <xref:System.Windows.Controls.ItemsControl.Items%2A>.</span></span> <span data-ttu-id="dc54e-144"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>は通常、データ コレクション<xref:System.Windows.Controls.ItemsControl>を設定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="dc54e-144"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> is typically used to populate the <xref:System.Windows.Controls.ItemsControl> with a data collection.</span></span> <span data-ttu-id="dc54e-145">コレクションを使用して を設定しない場合は<xref:System.Windows.Controls.ItemsControl>、 プロパティを使用して項目を<xref:System.Windows.Controls.ItemsControl.Items%2A>追加できます。</span><span class="sxs-lookup"><span data-stu-id="dc54e-145">If you do not want to use a collection to populate the <xref:System.Windows.Controls.ItemsControl>, you can add items by using the <xref:System.Windows.Controls.ItemsControl.Items%2A> property.</span></span>  
  
 <span data-ttu-id="dc54e-146">次のコントロールは、<xref:System.Windows.Controls.ItemsControl>そのコンテンツ モデルから継承して使用します。</span><span class="sxs-lookup"><span data-stu-id="dc54e-146">The following controls inherit from <xref:System.Windows.Controls.ItemsControl> and use its content model:</span></span>  
  
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
  
 <span data-ttu-id="dc54e-147">次の図は、<xref:System.Windows.Controls.ListBox>次の種類のアイテムを含むを示しています。</span><span class="sxs-lookup"><span data-stu-id="dc54e-147">The following illustration shows a <xref:System.Windows.Controls.ListBox> that contains these types of items:</span></span>  
  
- <span data-ttu-id="dc54e-148">文字列。</span><span class="sxs-lookup"><span data-stu-id="dc54e-148">A string.</span></span>  
  
- <span data-ttu-id="dc54e-149"><xref:System.DateTime> オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="dc54e-149">A <xref:System.DateTime> object.</span></span>  
  
- <span data-ttu-id="dc54e-150"><xref:System.Windows.UIElement> です。</span><span class="sxs-lookup"><span data-stu-id="dc54e-150">A <xref:System.Windows.UIElement>.</span></span>  
  
- <span data-ttu-id="dc54e-151">と<xref:System.Windows.Controls.Panel>を<xref:System.Windows.Shapes.Ellipse>含む<xref:System.Windows.Controls.TextBlock>。</span><span class="sxs-lookup"><span data-stu-id="dc54e-151">A <xref:System.Windows.Controls.Panel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 ![4 種類のコンテンツを含む ListBox を示すスクリーンショット。](./media/wpf-content-model/control-content-model-listbox.png)  
  
### <a name="controls-that-contain-a-header-and-a-collection-of-arbitrary-objects"></a><span data-ttu-id="dc54e-153">ヘッダーと任意のオブジェクトのコレクションを含むコントロール</span><span class="sxs-lookup"><span data-stu-id="dc54e-153">Controls That Contain a Header and a Collection of Arbitrary Objects</span></span>  
 <span data-ttu-id="dc54e-154">この<xref:System.Windows.Controls.HeaderedItemsControl>クラスは、文字列<xref:System.Windows.Controls.ItemsControl>、オブジェクト、その他の要素、ヘッダーなど、複数の項目を継承し、含めることができます。</span><span class="sxs-lookup"><span data-stu-id="dc54e-154">The <xref:System.Windows.Controls.HeaderedItemsControl> class inherits from <xref:System.Windows.Controls.ItemsControl> and can contain multiple items, such as strings, objects, or other elements, and a header.</span></span> <span data-ttu-id="dc54e-155">このクラスは、<xref:System.Windows.Controls.ItemsControl>コンテンツ プロパティ<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>、 <xref:System.Windows.Controls.ItemsControl.Items%2A>、および を<xref:System.Windows.Controls.HeaderedItemsControl.Header%2A>継承し、任意のオブジェクトにできるプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="dc54e-155">It inherits the <xref:System.Windows.Controls.ItemsControl> content properties, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>, and <xref:System.Windows.Controls.ItemsControl.Items%2A>, and it defines the <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> property that can be an arbitrary object.</span></span>  
  
 <span data-ttu-id="dc54e-156">次のコントロールは、<xref:System.Windows.Controls.HeaderedItemsControl>そのコンテンツ モデルから継承して使用します。</span><span class="sxs-lookup"><span data-stu-id="dc54e-156">The following controls inherit from <xref:System.Windows.Controls.HeaderedItemsControl> and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.MenuItem>  
  
- <xref:System.Windows.Controls.ToolBar>  
  
- <xref:System.Windows.Controls.TreeViewItem>  
  
<a name="classes_that_contain_a_collection_of_uielement_objects"></a>
## <a name="classes-that-contain-a-collection-of-uielement-objects"></a><span data-ttu-id="dc54e-157">UIElement オブジェクトのコレクションを含むクラス</span><span class="sxs-lookup"><span data-stu-id="dc54e-157">Classes That Contain a Collection of UIElement Objects</span></span>  
 <span data-ttu-id="dc54e-158">クラス<xref:System.Windows.Controls.Panel>は子<xref:System.Windows.UIElement>オブジェクトを配置し、配置します。</span><span class="sxs-lookup"><span data-stu-id="dc54e-158">The <xref:System.Windows.Controls.Panel> class positions and arranges child <xref:System.Windows.UIElement> objects.</span></span> <span data-ttu-id="dc54e-159">そのコンテンツ プロパティ<xref:System.Windows.Controls.Panel.Children%2A>は です。</span><span class="sxs-lookup"><span data-stu-id="dc54e-159">Its content property is <xref:System.Windows.Controls.Panel.Children%2A>.</span></span>  
  
 <span data-ttu-id="dc54e-160">次のクラスは<xref:System.Windows.Controls.Panel>クラスから継承され、そのコンテンツ モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="dc54e-160">The following classes inherit from the <xref:System.Windows.Controls.Panel> class and use its content model:</span></span>  
  
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
  
 <span data-ttu-id="dc54e-161">詳細については、「[Panels Overview](panels-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc54e-161">For more information, see [Panels Overview](panels-overview.md).</span></span>  
  
<a name="classes_that_affects_the_appearance_of_a_uielement"></a>
## <a name="classes-that-affect-the-appearance-of-a-uielement"></a><span data-ttu-id="dc54e-162">UIElement の外観に影響を与えるクラス</span><span class="sxs-lookup"><span data-stu-id="dc54e-162">Classes That Affect the Appearance of a UIElement</span></span>  
 <span data-ttu-id="dc54e-163">この<xref:System.Windows.Controls.Decorator>クラスは、視覚効果を 1 つの子<xref:System.Windows.UIElement>に適用するか、または 1 つの子の周囲に適用します。</span><span class="sxs-lookup"><span data-stu-id="dc54e-163">The <xref:System.Windows.Controls.Decorator> class applies visual effects onto or around a single child <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="dc54e-164">そのコンテンツ プロパティ<xref:System.Windows.Controls.Decorator.Child%2A>は です。</span><span class="sxs-lookup"><span data-stu-id="dc54e-164">Its content property is <xref:System.Windows.Controls.Decorator.Child%2A>.</span></span> <span data-ttu-id="dc54e-165">次のクラスは、<xref:System.Windows.Controls.Decorator>そのコンテンツ モデルから継承し、使用します。</span><span class="sxs-lookup"><span data-stu-id="dc54e-165">The following classes inherit from <xref:System.Windows.Controls.Decorator> and use its content model:</span></span>  
  
- <xref:System.Windows.Documents.AdornerDecorator>  
  
- <xref:System.Windows.Controls.Border>  
  
- <xref:System.Windows.Controls.Primitives.BulletDecorator>  
  
- <xref:Microsoft.Windows.Themes.ButtonChrome>  
  
- <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>  
  
- <xref:System.Windows.Controls.InkPresenter>  
  
- <xref:Microsoft.Windows.Themes.ListBoxChrome>  
  
- <xref:Microsoft.Windows.Themes.SystemDropShadowChrome>  
  
- <xref:System.Windows.Controls.Viewbox>  
  
 <span data-ttu-id="dc54e-166">次の図は<xref:System.Windows.Controls.TextBox>、周囲に a が付いている<xref:System.Windows.Controls.Border>(装飾されている) を示しています。</span><span class="sxs-lookup"><span data-stu-id="dc54e-166">The following illustration shows a <xref:System.Windows.Controls.TextBox> that has (is decorated with) a <xref:System.Windows.Controls.Border> around it.</span></span>  
  
 <span data-ttu-id="dc54e-167">![境界線が黒の TextBox](./media/layout-border-around-textbox.png "Layout_Border_around_TextBox")</span><span class="sxs-lookup"><span data-stu-id="dc54e-167">![TextBox with black border](./media/layout-border-around-textbox.png "Layout_Border_around_TextBox")</span></span>  
<span data-ttu-id="dc54e-168">境界がある TextBlock</span><span class="sxs-lookup"><span data-stu-id="dc54e-168">TextBlock that has a Border</span></span>  
  
<a name="classes_that_provides_visual_feedback_about_a_uielement"></a>
## <a name="classes-that-provide-visual-feedback-about-a-uielement"></a><span data-ttu-id="dc54e-169">UIElement についての視覚的なフィードバックを提供するクラス</span><span class="sxs-lookup"><span data-stu-id="dc54e-169">Classes That Provide Visual Feedback About a UIElement</span></span>  
 <span data-ttu-id="dc54e-170">クラス<xref:System.Windows.Documents.Adorner>は、ユーザーに視覚的な手掛かりを提供します。</span><span class="sxs-lookup"><span data-stu-id="dc54e-170">The <xref:System.Windows.Documents.Adorner> class provides visual cues to a user.</span></span> <span data-ttu-id="dc54e-171">たとえば、 を<xref:System.Windows.Documents.Adorner>使用して、要素に機能ハンドルを追加したり、コントロールに関する状態情報を提供したりできます。</span><span class="sxs-lookup"><span data-stu-id="dc54e-171">For example, use an <xref:System.Windows.Documents.Adorner> to add functional handles to elements or provide state information about a control.</span></span> <span data-ttu-id="dc54e-172">クラス<xref:System.Windows.Documents.Adorner>は、独自の装飾を作成できるようにフレームワークを提供します。</span><span class="sxs-lookup"><span data-stu-id="dc54e-172">The <xref:System.Windows.Documents.Adorner> class provides a framework so that you can create your own adorners.</span></span> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="dc54e-173">は実装された装飾は提供しません。</span><span class="sxs-lookup"><span data-stu-id="dc54e-173">does not provide any implemented adorners.</span></span> <span data-ttu-id="dc54e-174">詳しくは、[Adorners Overview](adorners-overview.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dc54e-174">For more information, see [Adorners Overview](adorners-overview.md).</span></span>  
  
<a name="classes_that_enable_users_to_enter_text"></a>
## <a name="classes-that-enable-users-to-enter-text"></a><span data-ttu-id="dc54e-175">ユーザーがテキストを入力できるようにするクラス</span><span class="sxs-lookup"><span data-stu-id="dc54e-175">Classes That Enable Users to Enter Text</span></span>  
 <span data-ttu-id="dc54e-176">WPF は、ユーザーがテキストを入力できるようにする 3 つの主なコントロールを提供します。</span><span class="sxs-lookup"><span data-stu-id="dc54e-176">WPF provides three primary controls that enable users to enter text.</span></span> <span data-ttu-id="dc54e-177">各コントロールは、異なる方法で、テキストを表示します。</span><span class="sxs-lookup"><span data-stu-id="dc54e-177">Each control displays the text differently.</span></span> <span data-ttu-id="dc54e-178">次の表は、これら 3 つのテキスト関連のコントロール、テキストを表示するときのそれぞれの機能、およびコントロールのテキストを格納するそれぞれのプロパティの一覧です。</span><span class="sxs-lookup"><span data-stu-id="dc54e-178">The following table lists these three text-related controls, their capabilities when they display text, and their properties that contain the control's text.</span></span>  
  
|<span data-ttu-id="dc54e-179">コントロール</span><span class="sxs-lookup"><span data-stu-id="dc54e-179">Control</span></span>|<span data-ttu-id="dc54e-180">テキストの表示形態</span><span class="sxs-lookup"><span data-stu-id="dc54e-180">Text is displayed as</span></span>|<span data-ttu-id="dc54e-181">コンテンツのプロパティ</span><span class="sxs-lookup"><span data-stu-id="dc54e-181">Content property</span></span>|  
|-------------|--------------------------|----------------------|  
|<xref:System.Windows.Controls.TextBox>|<span data-ttu-id="dc54e-182">プレーンテキスト ファイル</span><span class="sxs-lookup"><span data-stu-id="dc54e-182">Plain text</span></span>|<xref:System.Windows.Controls.TextBox.Text%2A>|  
|<xref:System.Windows.Controls.RichTextBox>|<span data-ttu-id="dc54e-183">書式付きテキスト</span><span class="sxs-lookup"><span data-stu-id="dc54e-183">Formatted text</span></span>|<xref:System.Windows.Controls.RichTextBox.Document%2A>|  
|<xref:System.Windows.Controls.PasswordBox>|<span data-ttu-id="dc54e-184">非表示のテキスト (文字はマスクされます)</span><span class="sxs-lookup"><span data-stu-id="dc54e-184">Hidden text (characters are masked)</span></span>|<xref:System.Windows.Controls.PasswordBox.Password%2A>|  
  
<a name="classes_that_display_text"></a>
## <a name="classes-that-display-your-text"></a><span data-ttu-id="dc54e-185">テキストを表示するクラス</span><span class="sxs-lookup"><span data-stu-id="dc54e-185">Classes That Display Your Text</span></span>  
 <span data-ttu-id="dc54e-186">いくつかのクラスを使用して、プレーン テキストまたは書式設定されたテキストを表示できます。</span><span class="sxs-lookup"><span data-stu-id="dc54e-186">Several classes can be used to display plain or formatted text.</span></span> <span data-ttu-id="dc54e-187">を使用<xref:System.Windows.Controls.TextBlock>して、少量のテキストを表示できます。</span><span class="sxs-lookup"><span data-stu-id="dc54e-187">You can use <xref:System.Windows.Controls.TextBlock> to display small amounts of text.</span></span> <span data-ttu-id="dc54e-188">大量のテキストを表示する場合は、 、<xref:System.Windows.Controls.FlowDocumentReader><xref:System.Windows.Controls.FlowDocumentPageViewer>または<xref:System.Windows.Controls.FlowDocumentScrollViewer>コントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="dc54e-188">If you want to display large amounts of text, use the <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, or <xref:System.Windows.Controls.FlowDocumentScrollViewer> controls.</span></span>  
  
 <span data-ttu-id="dc54e-189">には<xref:System.Windows.Controls.TextBlock>、 と の<xref:System.Windows.Controls.TextBlock.Text%2A><xref:System.Windows.Controls.TextBlock.Inlines%2A>2 つのコンテンツ プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="dc54e-189">The <xref:System.Windows.Controls.TextBlock> has two content properties: <xref:System.Windows.Controls.TextBlock.Text%2A> and <xref:System.Windows.Controls.TextBlock.Inlines%2A>.</span></span> <span data-ttu-id="dc54e-190">一貫性のある書式を使用するテキストを表示する場合<xref:System.Windows.Controls.TextBlock.Text%2A>、多くの場合、プロパティが最適な選択肢になります。</span><span class="sxs-lookup"><span data-stu-id="dc54e-190">When you want to display text that uses consistent formatting, the <xref:System.Windows.Controls.TextBlock.Text%2A> property is often your best choice.</span></span> <span data-ttu-id="dc54e-191">テキスト全体で異なる書式を使用する場合は、<xref:System.Windows.Controls.TextBlock.Inlines%2A>プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="dc54e-191">If you plan to use different formatting throughout the text, use the <xref:System.Windows.Controls.TextBlock.Inlines%2A> property.</span></span> <span data-ttu-id="dc54e-192">プロパティ<xref:System.Windows.Controls.TextBlock.Inlines%2A>は、テキストの書式設定<xref:System.Windows.Documents.Inline>方法を指定するオブジェクトのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="dc54e-192">The <xref:System.Windows.Controls.TextBlock.Inlines%2A> property is a collection of <xref:System.Windows.Documents.Inline> objects, which specify how to format text.</span></span>  
  
 <span data-ttu-id="dc54e-193">次の表は、 、 <xref:System.Windows.Controls.FlowDocumentReader>、<xref:System.Windows.Controls.FlowDocumentPageViewer>および<xref:System.Windows.Controls.FlowDocumentScrollViewer>クラスのコンテンツ プロパティの一覧です。</span><span class="sxs-lookup"><span data-stu-id="dc54e-193">The following table lists the content property for <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, and <xref:System.Windows.Controls.FlowDocumentScrollViewer> classes.</span></span>  
  
|<span data-ttu-id="dc54e-194">コントロール</span><span class="sxs-lookup"><span data-stu-id="dc54e-194">Control</span></span>|<span data-ttu-id="dc54e-195">コンテンツのプロパティ</span><span class="sxs-lookup"><span data-stu-id="dc54e-195">Content property</span></span>|<span data-ttu-id="dc54e-196">コンテンツのプロパティの型</span><span class="sxs-lookup"><span data-stu-id="dc54e-196">Content property type</span></span>|  
|-------------|----------------------|---------------------------|  
|<xref:System.Windows.Controls.FlowDocumentPageViewer>|<span data-ttu-id="dc54e-197">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="dc54e-197">Document</span></span>|<xref:System.Windows.Documents.IDocumentPaginatorSource>|  
|<xref:System.Windows.Controls.FlowDocumentReader>|<span data-ttu-id="dc54e-198">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="dc54e-198">Document</span></span>|<xref:System.Windows.Documents.FlowDocument>|  
|<xref:System.Windows.Controls.FlowDocumentScrollViewer>|<span data-ttu-id="dc54e-199">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="dc54e-199">Document</span></span>|<xref:System.Windows.Documents.FlowDocument>|  
  
 <span data-ttu-id="dc54e-200">は<xref:System.Windows.Documents.FlowDocument>インターフェイスを実装<xref:System.Windows.Documents.IDocumentPaginatorSource>します。したがって、3 つのクラスはすべてコンテンツ<xref:System.Windows.Documents.FlowDocument>として受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="dc54e-200">The <xref:System.Windows.Documents.FlowDocument> implements the <xref:System.Windows.Documents.IDocumentPaginatorSource> interface; therefore, all three classes can take a <xref:System.Windows.Documents.FlowDocument> as content.</span></span>  
  
<a name="classes_that_format_text"></a>
## <a name="classes-that-format-your-text"></a><span data-ttu-id="dc54e-201">テキストを書式設定するクラス</span><span class="sxs-lookup"><span data-stu-id="dc54e-201">Classes That Format Your Text</span></span>  
 <span data-ttu-id="dc54e-202"><xref:System.Windows.Documents.TextElement>また、関連するクラスを使用してテキストの書式を設定できます。</span><span class="sxs-lookup"><span data-stu-id="dc54e-202"><xref:System.Windows.Documents.TextElement> and its related classes allow you to format text.</span></span> <span data-ttu-id="dc54e-203"><xref:System.Windows.Documents.TextElement>オブジェクトには、テキストとオブジェクト<xref:System.Windows.Controls.TextBlock>が<xref:System.Windows.Documents.FlowDocument>含まれ、書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="dc54e-203"><xref:System.Windows.Documents.TextElement> objects contain and format text in <xref:System.Windows.Controls.TextBlock> and <xref:System.Windows.Documents.FlowDocument> objects.</span></span> <span data-ttu-id="dc54e-204">オブジェクトの<xref:System.Windows.Documents.TextElement>2 つの主要<xref:System.Windows.Documents.Block>な型<xref:System.Windows.Documents.Inline>は、要素と要素です。</span><span class="sxs-lookup"><span data-stu-id="dc54e-204">The two primary types of <xref:System.Windows.Documents.TextElement> objects are <xref:System.Windows.Documents.Block> elements and <xref:System.Windows.Documents.Inline> elements.</span></span> <span data-ttu-id="dc54e-205">要素<xref:System.Windows.Documents.Block>は、段落やリストなどのテキストのブロックを表します。</span><span class="sxs-lookup"><span data-stu-id="dc54e-205">A <xref:System.Windows.Documents.Block> element represents a block of text, such as a paragraph or list.</span></span> <span data-ttu-id="dc54e-206">要素<xref:System.Windows.Documents.Inline>は、ブロック内のテキストの一部を表します。</span><span class="sxs-lookup"><span data-stu-id="dc54e-206">An <xref:System.Windows.Documents.Inline> element represents a portion of text in a block.</span></span> <span data-ttu-id="dc54e-207">多<xref:System.Windows.Documents.Inline>くのクラスでは、適用するテキストの書式を指定します。</span><span class="sxs-lookup"><span data-stu-id="dc54e-207">Many <xref:System.Windows.Documents.Inline> classes specify formatting for the text to which they are applied.</span></span> <span data-ttu-id="dc54e-208">それぞれに<xref:System.Windows.Documents.TextElement>独自のコンテンツ モデルがあります。</span><span class="sxs-lookup"><span data-stu-id="dc54e-208">Each <xref:System.Windows.Documents.TextElement> has its own content model.</span></span> <span data-ttu-id="dc54e-209">詳細については、「[TextElement Content Model Overview](../advanced/textelement-content-model-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc54e-209">For more information, see the [TextElement Content Model Overview](../advanced/textelement-content-model-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc54e-210">関連項目</span><span class="sxs-lookup"><span data-stu-id="dc54e-210">See also</span></span>

- <span data-ttu-id="dc54e-211">[[詳細設定](../advanced/index.md)]</span><span class="sxs-lookup"><span data-stu-id="dc54e-211">[Advanced](../advanced/index.md)</span></span>
