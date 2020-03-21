---
title: ContextMenu の概要
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], ContextMenu
- ContextMenu controls [WPF], about ContextMenu controls
ms.assetid: 16909c42-799a-4561-91e0-7d69dcfeea91
ms.openlocfilehash: 4d2d8db0f614b5240705146dbe91432b96b46dd6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185909"
---
# <a name="contextmenu-overview"></a><span data-ttu-id="b090b-102">ContextMenu の概要</span><span class="sxs-lookup"><span data-stu-id="b090b-102">ContextMenu Overview</span></span>
<span data-ttu-id="b090b-103">この<xref:System.Windows.Controls.ContextMenu>クラスは、コンテキスト固有<xref:System.Windows.Controls.Menu>の を使用して機能を公開する要素を表します。</span><span class="sxs-lookup"><span data-stu-id="b090b-103">The <xref:System.Windows.Controls.ContextMenu> class represents the element that exposes functionality by using a context-specific <xref:System.Windows.Controls.Menu>.</span></span> <span data-ttu-id="b090b-104">通常、ユーザーはマウス ボタン<xref:System.Windows.Controls.ContextMenu>を右[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]クリックして で を公開します。</span><span class="sxs-lookup"><span data-stu-id="b090b-104">Typically, a user exposes the <xref:System.Windows.Controls.ContextMenu> in the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] by right-clicking the mouse button.</span></span> <span data-ttu-id="b090b-105">このトピックでは、<xref:System.Windows.Controls.ContextMenu>要素を紹介し、その使用方法[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]とコードの例を示します。</span><span class="sxs-lookup"><span data-stu-id="b090b-105">This topic introduces the <xref:System.Windows.Controls.ContextMenu> element and provides examples of how to use it in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] and code.</span></span>  

<a name="contextmenu_control"></a>
## <a name="contextmenu-control"></a><span data-ttu-id="b090b-106">ContextMenu コントロール</span><span class="sxs-lookup"><span data-stu-id="b090b-106">ContextMenu Control</span></span>  
 <span data-ttu-id="b090b-107">A<xref:System.Windows.Controls.ContextMenu>は特定のコントロールにアタッチされます。</span><span class="sxs-lookup"><span data-stu-id="b090b-107">A <xref:System.Windows.Controls.ContextMenu> is attached to a specific control.</span></span> <span data-ttu-id="b090b-108">要素<xref:System.Windows.Controls.ContextMenu>を使用すると、特定のコントロールに関連付けられているコマンドやオプションを指定する項目のリストをユーザーに<xref:System.Windows.Controls.Button>表示できます。</span><span class="sxs-lookup"><span data-stu-id="b090b-108">The <xref:System.Windows.Controls.ContextMenu> element enables you to present users with a list of items that specify commands or options that are associated with a particular control, for example, a <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="b090b-109">ユーザーがコントロールを右クリックすると、メニューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b090b-109">Users right-click the control to make the menu appear.</span></span> <span data-ttu-id="b090b-110">通常、をクリック<xref:System.Windows.Controls.MenuItem>するとサブメニューが開き、アプリケーションがコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b090b-110">Typically, clicking a <xref:System.Windows.Controls.MenuItem> opens a submenu or causes an application to carry out a command.</span></span>  
  
<a name="creating_contextmenus"></a>
## <a name="creating-contextmenus"></a><span data-ttu-id="b090b-111">ContextMenu の作成</span><span class="sxs-lookup"><span data-stu-id="b090b-111">Creating ContextMenus</span></span>  
 <span data-ttu-id="b090b-112">次の例は、サブメニューを<xref:System.Windows.Controls.ContextMenu>使用して を作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b090b-112">The following examples show how to create a <xref:System.Windows.Controls.ContextMenu> with submenus.</span></span> <span data-ttu-id="b090b-113">コントロール<xref:System.Windows.Controls.ContextMenu>はボタン コントロールにアタッチされます。</span><span class="sxs-lookup"><span data-stu-id="b090b-113">The <xref:System.Windows.Controls.ContextMenu> controls are attached to button controls.</span></span>  
  
 [!code-xaml[ContextMenu#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml#1)]  
  
 [!code-csharp[ContextMenu#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ContextMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ContextMenu/VisualBasic/Pane1.xaml.vb#2)]  
  
<a name="applying_styles_to_contextmenu"></a>
## <a name="applying-styles-to-a-contextmenu"></a><span data-ttu-id="b090b-114">ContextMenu へのスタイルの適用</span><span class="sxs-lookup"><span data-stu-id="b090b-114">Applying Styles to a ContextMenu</span></span>  
 <span data-ttu-id="b090b-115">コントロール を使用<xref:System.Windows.Style>すると、カスタム コントロールを記述せずに、外観や動作<xref:System.Windows.Controls.ContextMenu>を大幅に変更できます。</span><span class="sxs-lookup"><span data-stu-id="b090b-115">By using a control <xref:System.Windows.Style>, you can dramatically change the appearance and behavior of a <xref:System.Windows.Controls.ContextMenu> without writing a custom control.</span></span> <span data-ttu-id="b090b-116">視覚プロパティの設定に加えて、コントロールの一部にスタイルを適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="b090b-116">In addition to setting visual properties, you can also apply styles to parts of a control.</span></span> <span data-ttu-id="b090b-117">たとえば、プロパティを使用してコントロールの一部の動作を変更したり、パーツを追加したり、レイアウトを変更したりできます<xref:System.Windows.Controls.ContextMenu>。</span><span class="sxs-lookup"><span data-stu-id="b090b-117">For example, you can change the behavior of parts of the control by using properties, or you can add parts to, or change the layout of, a <xref:System.Windows.Controls.ContextMenu>.</span></span> <span data-ttu-id="b090b-118">次の例は、コントロールにスタイルを追加<xref:System.Windows.Controls.ContextMenu>するいくつかの方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b090b-118">The following examples show several ways to add styles to <xref:System.Windows.Controls.ContextMenu> controls.</span></span>  
  
 <span data-ttu-id="b090b-119">最初の例では、`SimpleSysResources` という名前のスタイルを定義し、スタイルで現在のシステム設定を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b090b-119">The first example defines a style called `SimpleSysResources`, which shows how to use the current system settings in your style.</span></span> <span data-ttu-id="b090b-120">この例では、<xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A><xref:System.Windows.Controls.Control.Background%2A>色として、および<xref:System.Windows.SystemColors.MenuTextBrushKey%2A><xref:System.Windows.Controls.ContextMenu>の<xref:System.Windows.Controls.Control.Foreground%2A>色として割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b090b-120">The example assigns <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> as the <xref:System.Windows.Controls.Control.Background%2A> color and <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> as the <xref:System.Windows.Controls.Control.Foreground%2A> color of the <xref:System.Windows.Controls.ContextMenu>.</span></span>  
  
```xaml  
<Style x:Key="SimpleSysResources" TargetType="{x:Type MenuItem}">  
  <Setter Property = "Background" Value=
    "{DynamicResource {x:Static SystemColors.MenuHighlightBrushKey}}"/>  
  <Setter Property = "Foreground" Value=
    "{DynamicResource {x:Static SystemColors.MenuTextBrushKey}}"/>  
</Style>  
```  
  
 <span data-ttu-id="b090b-121">次の例では、<xref:System.Windows.Trigger>要素を使用して、 で<xref:System.Windows.Controls.Menu>発生したイベントに対する in<xref:System.Windows.Controls.ContextMenu>の外観を変更します。</span><span class="sxs-lookup"><span data-stu-id="b090b-121">The following example uses the <xref:System.Windows.Trigger> element to change the appearance of a <xref:System.Windows.Controls.Menu> in response to events that are raised on the <xref:System.Windows.Controls.ContextMenu>.</span></span> <span data-ttu-id="b090b-122">ユーザーがメニュー上にマウスを移動すると、項目の外観が<xref:System.Windows.Controls.ContextMenu>変わります。</span><span class="sxs-lookup"><span data-stu-id="b090b-122">When a user moves the mouse over the menu, the appearance of the <xref:System.Windows.Controls.ContextMenu> items changes.</span></span>  
  
```xaml  
<Style x:Key="Triggers" TargetType="{x:Type MenuItem}">  
  <Style.Triggers>  
    <Trigger Property="MenuItem.IsMouseOver" Value="true">  
      <Setter Property = "FontSize" Value="16"/>  
      <Setter Property = "FontStyle" Value="Italic"/>  
      <Setter Property = "Foreground" Value="Red"/>  
    </Trigger>  
  </Style.Triggers>  
</Style>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b090b-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="b090b-123">See also</span></span>

- <xref:System.Windows.Controls.ContextMenu>
- <xref:System.Windows.Style>
- <xref:System.Windows.Controls.Menu>
- <xref:System.Windows.Controls.MenuItem>
- [<span data-ttu-id="b090b-124">Contextmenu</span><span class="sxs-lookup"><span data-stu-id="b090b-124">ContextMenu</span></span>](contextmenu.md)
- [<span data-ttu-id="b090b-125">ContextMenu のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="b090b-125">ContextMenu Styles and Templates</span></span>](contextmenu-styles-and-templates.md)
- [<span data-ttu-id="b090b-126">WPF コントロール ギャラリーのサンプル</span><span class="sxs-lookup"><span data-stu-id="b090b-126">WPF Controls Gallery Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)
