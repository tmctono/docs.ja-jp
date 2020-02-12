---
title: メニューの概要
ms.date: 03/30/2017
helpviewer_keywords:
- Menu control [WPF]
- controls [WPF], Menu
ms.assetid: 67df6de5-db96-4c71-b752-af90729a6537
ms.openlocfilehash: 3d5cfba0734e684349f7d73b7242f4b69089b94d
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124651"
---
# <a name="menu-overview"></a><span data-ttu-id="19585-102">メニューの概要</span><span class="sxs-lookup"><span data-stu-id="19585-102">Menu Overview</span></span>
<span data-ttu-id="19585-103"><xref:System.Windows.Controls.Menu> クラスを使用すると、コマンドおよびイベントハンドラーに関連付けられている要素を階層順に整理できます。</span><span class="sxs-lookup"><span data-stu-id="19585-103">The <xref:System.Windows.Controls.Menu> class enables you to organize elements associated with commands and event handlers in a hierarchical order.</span></span> <span data-ttu-id="19585-104">各 <xref:System.Windows.Controls.Menu> 要素には、<xref:System.Windows.Controls.MenuItem> 要素のコレクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="19585-104">Each <xref:System.Windows.Controls.Menu> element contains a collection of <xref:System.Windows.Controls.MenuItem> elements.</span></span>  

<a name="menu_control"></a>   
## <a name="menu-control"></a><span data-ttu-id="19585-105">メニュー コントロール</span><span class="sxs-lookup"><span data-stu-id="19585-105">Menu Control</span></span>  
 <span data-ttu-id="19585-106"><xref:System.Windows.Controls.Menu> コントロールには、アプリケーションのコマンドまたはオプションを指定する項目の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="19585-106">The <xref:System.Windows.Controls.Menu> control presents a list of items that specify commands or options for an application.</span></span> <span data-ttu-id="19585-107">通常、<xref:System.Windows.Controls.MenuItem> をクリックするとサブメニューが表示され、アプリケーションはコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="19585-107">Typically, clicking a <xref:System.Windows.Controls.MenuItem> opens a submenu or causes an application to carry out a command.</span></span>  
  
<a name="creating_menus"></a>   
## <a name="creating-menus"></a><span data-ttu-id="19585-108">メニューの作成</span><span class="sxs-lookup"><span data-stu-id="19585-108">Creating Menus</span></span>  
 <span data-ttu-id="19585-109">次の例では、<xref:System.Windows.Controls.TextBox>内のテキストを操作する <xref:System.Windows.Controls.Menu> を作成します。</span><span class="sxs-lookup"><span data-stu-id="19585-109">The following example creates a <xref:System.Windows.Controls.Menu> to manipulate text in a <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="19585-110"><xref:System.Windows.Controls.Menu> には、<xref:System.Windows.Controls.MenuItem.Command%2A>、<xref:System.Windows.Controls.MenuItem.IsCheckable%2A>、および <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> の各プロパティと、<xref:System.Windows.Controls.MenuItem.Checked>、<xref:System.Windows.Controls.MenuItem.Unchecked>、および <xref:System.Windows.Controls.MenuItem.Click> イベントを使用する <xref:System.Windows.Controls.MenuItem> オブジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="19585-110">The <xref:System.Windows.Controls.Menu> contains <xref:System.Windows.Controls.MenuItem> objects that use the <xref:System.Windows.Controls.MenuItem.Command%2A>, <xref:System.Windows.Controls.MenuItem.IsCheckable%2A>, and <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> properties and the <xref:System.Windows.Controls.MenuItem.Checked>, <xref:System.Windows.Controls.MenuItem.Unchecked>, and <xref:System.Windows.Controls.MenuItem.Click> events.</span></span>  
  
 [!code-xaml[MenuItemCommandsAndEvents#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml#1)]  
  
 [!code-csharp[MenuItemCommandsAndEvents#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml.cs#2)]
 [!code-vb[MenuItemCommandsAndEvents#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandsAndEvents/VisualBasic/Window1.xaml.vb#2)]  
  
<a name="menus_with_shortcutkeys"></a>   
## <a name="menuitems-with-keyboard-shortcuts"></a><span data-ttu-id="19585-111">キーボード ショートカット付きのメニュー項目</span><span class="sxs-lookup"><span data-stu-id="19585-111">MenuItems with Keyboard Shortcuts</span></span>  
 <span data-ttu-id="19585-112">キーボードショートカットは、<xref:System.Windows.Controls.Menu> のコマンドを呼び出すためにキーボードで入力できる文字の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="19585-112">Keyboard shortcuts are character combinations that can be entered with the keyboard to invoke <xref:System.Windows.Controls.Menu> commands.</span></span> <span data-ttu-id="19585-113">たとえば、**コピー**のショートカットは CTRL+C です。</span><span class="sxs-lookup"><span data-stu-id="19585-113">For example, the shortcut for **Copy** is CTRL+C.</span></span> <span data-ttu-id="19585-114">キーボードショートカットとメニュー項目で使用するプロパティには、<xref:System.Windows.Controls.MenuItem.InputGestureText%2A> または <xref:System.Windows.Controls.MenuItem.Command%2A>の2つがあります。</span><span class="sxs-lookup"><span data-stu-id="19585-114">There are two properties to use with keyboard shortcuts and menu items —<xref:System.Windows.Controls.MenuItem.InputGestureText%2A> or <xref:System.Windows.Controls.MenuItem.Command%2A>.</span></span>  
  
<a name="menus_inputgesturetext"></a>   
### <a name="inputgesturetext"></a><span data-ttu-id="19585-115">InputGestureText</span><span class="sxs-lookup"><span data-stu-id="19585-115">InputGestureText</span></span>  
 <span data-ttu-id="19585-116">次の例では、<xref:System.Windows.Controls.MenuItem.InputGestureText%2A> プロパティを使用して、<xref:System.Windows.Controls.MenuItem> コントロールにキーボードショートカットテキストを割り当てる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="19585-116">The following example shows how to use the <xref:System.Windows.Controls.MenuItem.InputGestureText%2A> property to assign keyboard shortcut text to <xref:System.Windows.Controls.MenuItem> controls.</span></span> <span data-ttu-id="19585-117">これは、キーボード ショートカットをメニュー項目に配置するだけです。</span><span class="sxs-lookup"><span data-stu-id="19585-117">This only places the keyboard shortcut in the menu item.</span></span>  <span data-ttu-id="19585-118">コマンドは <xref:System.Windows.Controls.MenuItem>に関連付けられません。</span><span class="sxs-lookup"><span data-stu-id="19585-118">It does not associate the command with the <xref:System.Windows.Controls.MenuItem>.</span></span> <span data-ttu-id="19585-119">アプリケーションでは、アクションを実行するために、ユーザーの入力を処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19585-119">The application must handle the user's input to carry out the action.</span></span>  
  
 [!code-xaml[MenuEvent#6](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#6)]  
  
<a name="menus_commands"></a>   
### <a name="command"></a><span data-ttu-id="19585-120">command</span><span class="sxs-lookup"><span data-stu-id="19585-120">Command</span></span>  
 <span data-ttu-id="19585-121">次の例は、<xref:System.Windows.Controls.MenuItem.Command%2A> プロパティを使用して、 **Open**コマンドと**Save**コマンドを <xref:System.Windows.Controls.MenuItem> コントロールに関連付ける方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="19585-121">The following example shows how to use the <xref:System.Windows.Controls.MenuItem.Command%2A> property to associate the **Open** and **Save** commands with <xref:System.Windows.Controls.MenuItem> controls.</span></span> <span data-ttu-id="19585-122">Command プロパティによってコマンドが <xref:System.Windows.Controls.MenuItem>に関連付けられるだけでなく、ショートカットとして使用する入力ジェスチャテキストも提供されます。</span><span class="sxs-lookup"><span data-stu-id="19585-122">Not only does the command property associate a command with a <xref:System.Windows.Controls.MenuItem>, but it also supplies the input gesture text to use as a shortcut.</span></span>  
  
 [!code-xaml[MenuEvent#8](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#8)]  
  
 <span data-ttu-id="19585-123"><xref:System.Windows.Controls.MenuItem> クラスには、コマンドが発生する要素を指定する <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> プロパティもあります。</span><span class="sxs-lookup"><span data-stu-id="19585-123">The <xref:System.Windows.Controls.MenuItem> class also has a <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> property, which specifies the element where the command occurs.</span></span> <span data-ttu-id="19585-124"><xref:System.Windows.Controls.MenuItem.CommandTarget%2A> が設定されていない場合、キーボードフォーカスを持つ要素はコマンドを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="19585-124">If <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> is not set, the element that has keyboard focus receives the command.</span></span> <span data-ttu-id="19585-125">コマンドの詳細については、[Commanding Overview](../advanced/commanding-overview.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19585-125">For more information about commands, see [Commanding Overview](../advanced/commanding-overview.md).</span></span>  
  
<a name="menu_styling"></a>   
## <a name="menu-styling"></a><span data-ttu-id="19585-126">メニューのスタイル指定</span><span class="sxs-lookup"><span data-stu-id="19585-126">Menu Styling</span></span>  
 <span data-ttu-id="19585-127">コントロールのスタイル設定を使用すると、カスタムコントロールを記述しなくても、<xref:System.Windows.Controls.Menu> コントロールの外観と動作を大幅に変更できます。</span><span class="sxs-lookup"><span data-stu-id="19585-127">With control styling, you can dramatically change the appearance and behavior of <xref:System.Windows.Controls.Menu> controls without having to write a custom control.</span></span> <span data-ttu-id="19585-128">ビジュアルプロパティの設定に加えて、コントロールの個々の部分に <xref:System.Windows.Style> を適用したり、プロパティを使用してコントロールの一部の動作を変更したり、パーツを追加したり、コントロールのレイアウトを変更したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="19585-128">In addition to setting visual properties, you can also apply a <xref:System.Windows.Style> to individual parts of a control, change the behavior of parts of the control through properties, or add additional parts or change the layout of a control.</span></span> <span data-ttu-id="19585-129">次の例では、<xref:System.Windows.Style> を <xref:System.Windows.Controls.Menu> コントロールに追加するいくつかの方法を示します。</span><span class="sxs-lookup"><span data-stu-id="19585-129">The following examples demonstrate several ways to add a <xref:System.Windows.Style> to a <xref:System.Windows.Controls.Menu> control.</span></span>  
  
 <span data-ttu-id="19585-130">最初のコード例では、スタイルで現在のシステム設定を使用する方法を示す `Simple` と呼ばれる <xref:System.Windows.Style> を定義します。</span><span class="sxs-lookup"><span data-stu-id="19585-130">The first code example defines a <xref:System.Windows.Style> called `Simple` that shows how to use the current system settings in your style.</span></span> <span data-ttu-id="19585-131">このコードは、`MenuHighlightBrush`の色をメニューの背景色として、 `MenuTextBrush`の色をメニューの前景色として割り当てます。</span><span class="sxs-lookup"><span data-stu-id="19585-131">The code assigns the color of the `MenuHighlightBrush` as the menu's background color and the `MenuTextBrush` as the menu's foreground color.</span></span> <span data-ttu-id="19585-132">ブラシを割り当てるには、リソース キーを使用することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="19585-132">Notice that you use resource keys to assign the brushes.</span></span>  
  
 [!code-xaml[MenuStylesSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#1)]  
  
 <span data-ttu-id="19585-133">次の例では <xref:System.Windows.Trigger> 要素を使用して、<xref:System.Windows.Controls.Menu>で発生するイベントに応答して <xref:System.Windows.Controls.MenuItem> の外観を変更できます。</span><span class="sxs-lookup"><span data-stu-id="19585-133">The following sample uses <xref:System.Windows.Trigger> elements that enable you to change the appearance of a <xref:System.Windows.Controls.MenuItem> in response to events that occur on the <xref:System.Windows.Controls.Menu>.</span></span> <span data-ttu-id="19585-134"><xref:System.Windows.Controls.Menu>上にマウスを移動すると、メニュー項目の前景色とフォント特性が変わります。</span><span class="sxs-lookup"><span data-stu-id="19585-134">When you move the mouse over the <xref:System.Windows.Controls.Menu>, the foreground color and the font characteristics of the menu items change.</span></span>  
  
 [!code-xaml[MenuStylesSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#2)]  
  
## <a name="see-also"></a><span data-ttu-id="19585-135">参照</span><span class="sxs-lookup"><span data-stu-id="19585-135">See also</span></span>

- [<span data-ttu-id="19585-136">WPF Controls Gallery Sample</span><span class="sxs-lookup"><span data-stu-id="19585-136">WPF Controls Gallery Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)
