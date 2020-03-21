---
title: メニューの概要
ms.date: 03/30/2017
helpviewer_keywords:
- Menu control [WPF]
- controls [WPF], Menu
ms.assetid: 67df6de5-db96-4c71-b752-af90729a6537
ms.openlocfilehash: 53bc8f10e61b6e4e9e1f3b9a484340d9e2ec2a85
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186971"
---
# <a name="menu-overview"></a><span data-ttu-id="734b0-102">メニューの概要</span><span class="sxs-lookup"><span data-stu-id="734b0-102">Menu Overview</span></span>
<span data-ttu-id="734b0-103">この<xref:System.Windows.Controls.Menu>クラスを使用すると、コマンドとイベント ハンドラーに関連付けられた要素を階層的な順序で整理できます。</span><span class="sxs-lookup"><span data-stu-id="734b0-103">The <xref:System.Windows.Controls.Menu> class enables you to organize elements associated with commands and event handlers in a hierarchical order.</span></span> <span data-ttu-id="734b0-104">各<xref:System.Windows.Controls.Menu>要素には、要素の<xref:System.Windows.Controls.MenuItem>コレクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="734b0-104">Each <xref:System.Windows.Controls.Menu> element contains a collection of <xref:System.Windows.Controls.MenuItem> elements.</span></span>  

<a name="menu_control"></a>
## <a name="menu-control"></a><span data-ttu-id="734b0-105">メニュー コントロール</span><span class="sxs-lookup"><span data-stu-id="734b0-105">Menu Control</span></span>  
 <span data-ttu-id="734b0-106">コントロール<xref:System.Windows.Controls.Menu>は、アプリケーションのコマンドまたはオプションを指定する項目のリストを表示します。</span><span class="sxs-lookup"><span data-stu-id="734b0-106">The <xref:System.Windows.Controls.Menu> control presents a list of items that specify commands or options for an application.</span></span> <span data-ttu-id="734b0-107">通常、をクリック<xref:System.Windows.Controls.MenuItem>するとサブメニューが開き、アプリケーションがコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="734b0-107">Typically, clicking a <xref:System.Windows.Controls.MenuItem> opens a submenu or causes an application to carry out a command.</span></span>  
  
<a name="creating_menus"></a>
## <a name="creating-menus"></a><span data-ttu-id="734b0-108">メニューの作成</span><span class="sxs-lookup"><span data-stu-id="734b0-108">Creating Menus</span></span>  
 <span data-ttu-id="734b0-109">次の例では、<xref:System.Windows.Controls.Menu>のテキストを操作<xref:System.Windows.Controls.TextBox>する を作成します。</span><span class="sxs-lookup"><span data-stu-id="734b0-109">The following example creates a <xref:System.Windows.Controls.Menu> to manipulate text in a <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="734b0-110">には<xref:System.Windows.Controls.Menu><xref:System.Windows.Controls.MenuItem.Command%2A>、 、 、 <xref:System.Windows.Controls.MenuItem.IsCheckable%2A>、 <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> 、 、 <xref:System.Windows.Controls.MenuItem.Checked> <xref:System.Windows.Controls.MenuItem.Unchecked>、および<xref:System.Windows.Controls.MenuItem.Click>イベントを使用するオブジェクトが含まれます<xref:System.Windows.Controls.MenuItem>。</span><span class="sxs-lookup"><span data-stu-id="734b0-110">The <xref:System.Windows.Controls.Menu> contains <xref:System.Windows.Controls.MenuItem> objects that use the <xref:System.Windows.Controls.MenuItem.Command%2A>, <xref:System.Windows.Controls.MenuItem.IsCheckable%2A>, and <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> properties and the <xref:System.Windows.Controls.MenuItem.Checked>, <xref:System.Windows.Controls.MenuItem.Unchecked>, and <xref:System.Windows.Controls.MenuItem.Click> events.</span></span>  
  
 [!code-xaml[MenuItemCommandsAndEvents#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml#1)]  
  
 [!code-csharp[MenuItemCommandsAndEvents#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml.cs#2)]
 [!code-vb[MenuItemCommandsAndEvents#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandsAndEvents/VisualBasic/Window1.xaml.vb#2)]  
  
<a name="menus_with_shortcutkeys"></a>
## <a name="menuitems-with-keyboard-shortcuts"></a><span data-ttu-id="734b0-111">キーボード ショートカット付きのメニュー項目</span><span class="sxs-lookup"><span data-stu-id="734b0-111">MenuItems with Keyboard Shortcuts</span></span>  
 <span data-ttu-id="734b0-112">キーボード ショートカットは、コマンドを呼び出すために<xref:System.Windows.Controls.Menu>キーボードと入力できる文字の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="734b0-112">Keyboard shortcuts are character combinations that can be entered with the keyboard to invoke <xref:System.Windows.Controls.Menu> commands.</span></span> <span data-ttu-id="734b0-113">たとえば、**コピー**のショートカットは CTRL+C です。</span><span class="sxs-lookup"><span data-stu-id="734b0-113">For example, the shortcut for **Copy** is CTRL+C.</span></span> <span data-ttu-id="734b0-114">キーボード ショートカットとメニュー項目<xref:System.Windows.Controls.MenuItem.InputGestureText%2A>には 2 つのプロパティがあります。 <xref:System.Windows.Controls.MenuItem.Command%2A></span><span class="sxs-lookup"><span data-stu-id="734b0-114">There are two properties to use with keyboard shortcuts and menu items —<xref:System.Windows.Controls.MenuItem.InputGestureText%2A> or <xref:System.Windows.Controls.MenuItem.Command%2A>.</span></span>  
  
<a name="menus_inputgesturetext"></a>
### <a name="inputgesturetext"></a><span data-ttu-id="734b0-115">InputGestureText</span><span class="sxs-lookup"><span data-stu-id="734b0-115">InputGestureText</span></span>  
 <span data-ttu-id="734b0-116"><xref:System.Windows.Controls.MenuItem.InputGestureText%2A>次の例は、プロパティを使用してコントロールにキーボード ショートカット<xref:System.Windows.Controls.MenuItem>テキストを割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="734b0-116">The following example shows how to use the <xref:System.Windows.Controls.MenuItem.InputGestureText%2A> property to assign keyboard shortcut text to <xref:System.Windows.Controls.MenuItem> controls.</span></span> <span data-ttu-id="734b0-117">これは、キーボード ショートカットをメニュー項目に配置するだけです。</span><span class="sxs-lookup"><span data-stu-id="734b0-117">This only places the keyboard shortcut in the menu item.</span></span>  <span data-ttu-id="734b0-118">コマンドは<xref:System.Windows.Controls.MenuItem>.</span><span class="sxs-lookup"><span data-stu-id="734b0-118">It does not associate the command with the <xref:System.Windows.Controls.MenuItem>.</span></span> <span data-ttu-id="734b0-119">アプリケーションでは、アクションを実行するために、ユーザーの入力を処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="734b0-119">The application must handle the user's input to carry out the action.</span></span>  
  
 [!code-xaml[MenuEvent#6](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#6)]  
  
<a name="menus_commands"></a>
### <a name="command"></a><span data-ttu-id="734b0-120">command</span><span class="sxs-lookup"><span data-stu-id="734b0-120">Command</span></span>  
 <span data-ttu-id="734b0-121">次の例は、プロパティを使用<xref:System.Windows.Controls.MenuItem.Command%2A>して **、Open**コマンドと**Save** <xref:System.Windows.Controls.MenuItem>コマンドをコントロールに関連付ける方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="734b0-121">The following example shows how to use the <xref:System.Windows.Controls.MenuItem.Command%2A> property to associate the **Open** and **Save** commands with <xref:System.Windows.Controls.MenuItem> controls.</span></span> <span data-ttu-id="734b0-122">コマンド プロパティは、コマンドを<xref:System.Windows.Controls.MenuItem>に関連付けるだけでなく、ショートカットとして使用する入力ジェスチャ テキストも提供します。</span><span class="sxs-lookup"><span data-stu-id="734b0-122">Not only does the command property associate a command with a <xref:System.Windows.Controls.MenuItem>, but it also supplies the input gesture text to use as a shortcut.</span></span>  
  
 [!code-xaml[MenuEvent#8](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#8)]  
  
 <span data-ttu-id="734b0-123">この<xref:System.Windows.Controls.MenuItem>クラスには、コマンド<xref:System.Windows.Controls.MenuItem.CommandTarget%2A>が発生する要素を指定するプロパティもあります。</span><span class="sxs-lookup"><span data-stu-id="734b0-123">The <xref:System.Windows.Controls.MenuItem> class also has a <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> property, which specifies the element where the command occurs.</span></span> <span data-ttu-id="734b0-124">設定<xref:System.Windows.Controls.MenuItem.CommandTarget%2A>されていない場合、キーボード フォーカスを持つ要素がコマンドを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="734b0-124">If <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> is not set, the element that has keyboard focus receives the command.</span></span> <span data-ttu-id="734b0-125">コマンドの詳細については、[Commanding Overview](../advanced/commanding-overview.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="734b0-125">For more information about commands, see [Commanding Overview](../advanced/commanding-overview.md).</span></span>  
  
<a name="menu_styling"></a>
## <a name="menu-styling"></a><span data-ttu-id="734b0-126">メニューのスタイル指定</span><span class="sxs-lookup"><span data-stu-id="734b0-126">Menu Styling</span></span>  
 <span data-ttu-id="734b0-127">コントロールのスタイル設定を使用すると、カスタム コントロールを記述しなくても<xref:System.Windows.Controls.Menu>、コントロールの外観や動作を大幅に変更できます。</span><span class="sxs-lookup"><span data-stu-id="734b0-127">With control styling, you can dramatically change the appearance and behavior of <xref:System.Windows.Controls.Menu> controls without having to write a custom control.</span></span> <span data-ttu-id="734b0-128">表示プロパティの設定に加えて、コントロールの個々の<xref:System.Windows.Style>部分に a を適用したり、プロパティを使用してコントロールの一部の動作を変更したり、追加パーツを追加したり、コントロールのレイアウトを変更したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="734b0-128">In addition to setting visual properties, you can also apply a <xref:System.Windows.Style> to individual parts of a control, change the behavior of parts of the control through properties, or add additional parts or change the layout of a control.</span></span> <span data-ttu-id="734b0-129">次の例は、コントロールにを<xref:System.Windows.Style>追加するいくつかの方法<xref:System.Windows.Controls.Menu>を示しています。</span><span class="sxs-lookup"><span data-stu-id="734b0-129">The following examples demonstrate several ways to add a <xref:System.Windows.Style> to a <xref:System.Windows.Controls.Menu> control.</span></span>  
  
 <span data-ttu-id="734b0-130">最初のコード例では、<xref:System.Windows.Style>現在`Simple`のシステム設定をスタイルで使用する方法を示す呼び出しを定義します。</span><span class="sxs-lookup"><span data-stu-id="734b0-130">The first code example defines a <xref:System.Windows.Style> called `Simple` that shows how to use the current system settings in your style.</span></span> <span data-ttu-id="734b0-131">このコードは、`MenuHighlightBrush`の色をメニューの背景色として、 `MenuTextBrush`の色をメニューの前景色として割り当てます。</span><span class="sxs-lookup"><span data-stu-id="734b0-131">The code assigns the color of the `MenuHighlightBrush` as the menu's background color and the `MenuTextBrush` as the menu's foreground color.</span></span> <span data-ttu-id="734b0-132">ブラシを割り当てるには、リソース キーを使用することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="734b0-132">Notice that you use resource keys to assign the brushes.</span></span>  
  
 [!code-xaml[MenuStylesSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#1)]  
  
 <span data-ttu-id="734b0-133">次のサンプルでは<xref:System.Windows.Trigger>、で発生したイベントに応答して、<xref:System.Windows.Controls.MenuItem>の外観を変更できる要素を<xref:System.Windows.Controls.Menu>使用します。</span><span class="sxs-lookup"><span data-stu-id="734b0-133">The following sample uses <xref:System.Windows.Trigger> elements that enable you to change the appearance of a <xref:System.Windows.Controls.MenuItem> in response to events that occur on the <xref:System.Windows.Controls.Menu>.</span></span> <span data-ttu-id="734b0-134"><xref:System.Windows.Controls.Menu>上にマウスを移動すると、前景色とメニュー項目のフォント特性が変わります。</span><span class="sxs-lookup"><span data-stu-id="734b0-134">When you move the mouse over the <xref:System.Windows.Controls.Menu>, the foreground color and the font characteristics of the menu items change.</span></span>  
  
 [!code-xaml[MenuStylesSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#2)]  
  
## <a name="see-also"></a><span data-ttu-id="734b0-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="734b0-135">See also</span></span>

- [<span data-ttu-id="734b0-136">WPF コントロール ギャラリーのサンプル</span><span class="sxs-lookup"><span data-stu-id="734b0-136">WPF Controls Gallery Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)
