---
title: '方法: TextBox でカスタム コンテキスト メニューを使用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- context menus [WPF], custom
- menus [WPF], custom
- custom context menus [WPF]
- TextBox control [WPF], custom content menus
ms.assetid: 842d3cd5-6fa0-4be4-8d90-6c7466213b1c
ms.openlocfilehash: b0507c6fa37f0f51f9e12ebe5f908c39c25b50d9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61699176"
---
# <a name="how-to-use-a-custom-context-menu-with-a-textbox"></a><span data-ttu-id="30829-102">方法: TextBox でカスタム コンテキスト メニューを使用する</span><span class="sxs-lookup"><span data-stu-id="30829-102">How to: Use a Custom Context Menu with a TextBox</span></span>
<span data-ttu-id="30829-103">この例は、定義して、単純なカスタム コンテキスト メニューを実装する方法を示します、<xref:System.Windows.Controls.TextBox>します。</span><span class="sxs-lookup"><span data-stu-id="30829-103">This example shows how to define and implement a simple custom context menu for a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="30829-104">例</span><span class="sxs-lookup"><span data-stu-id="30829-104">Example</span></span>  
 <span data-ttu-id="30829-105">次[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]例、<xref:System.Windows.Controls.TextBox>コントロールをカスタム コンテキスト メニューが含まれています。</span><span class="sxs-lookup"><span data-stu-id="30829-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example defines a <xref:System.Windows.Controls.TextBox> control that includes a custom context menu.</span></span>  
  
 <span data-ttu-id="30829-106">使用して、コンテキスト メニューを定義、<xref:System.Windows.Controls.ContextMenu>要素。</span><span class="sxs-lookup"><span data-stu-id="30829-106">The context menu is defined using a <xref:System.Windows.Controls.ContextMenu> element.</span></span>  <span data-ttu-id="30829-107">自体のコンテキスト メニューから成る、一連の<xref:System.Windows.Controls.MenuItem>要素と<xref:System.Windows.Controls.Separator>要素。</span><span class="sxs-lookup"><span data-stu-id="30829-107">The context menu itself consists of a series of <xref:System.Windows.Controls.MenuItem> elements and <xref:System.Windows.Controls.Separator> elements.</span></span>  <span data-ttu-id="30829-108">各<xref:System.Windows.Controls.MenuItem>要素は、コンテキスト メニューのコマンドを定義、<xref:System.Windows.Controls.HeaderedItemsControl.Header%2A>属性は、メニュー コマンドの表示テキストを定義し、<xref:System.Windows.Controls.MenuItem.Click>属性は、各メニュー項目のハンドラー メソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="30829-108">Each <xref:System.Windows.Controls.MenuItem> element defines a command in the context menu; the <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> attribute defines the display text for the menu command, and the <xref:System.Windows.Controls.MenuItem.Click> attribute specifies a handler method for each menu item.</span></span>  <span data-ttu-id="30829-109"><xref:System.Windows.Controls.Separator>要素は、前と後のメニュー項目の間に表示される区切り線を単純に、します。</span><span class="sxs-lookup"><span data-stu-id="30829-109">The <xref:System.Windows.Controls.Separator> element simply causes a separating line to be rendered between the previous and subsequent menu items.</span></span>  
  
 [!code-xaml[TextBox_ContextMenu#_TextBox_ContextMenuXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml#_textbox_contextmenuxaml)]  
  
## <a name="example"></a><span data-ttu-id="30829-110">例</span><span class="sxs-lookup"><span data-stu-id="30829-110">Example</span></span>  
 <span data-ttu-id="30829-111">次の例では、前のコンテキスト メニューの定義の実装コードも有効にし、コンテキスト メニューを無効にするコードを示します。</span><span class="sxs-lookup"><span data-stu-id="30829-111">The following example shows the implementation code for the preceding context menu definition, as well as the code that enables and disables the context menu.</span></span>  <span data-ttu-id="30829-112"><xref:System.Windows.Controls.ContextMenu.Opened>イベントを使用して動的に有効またはの現在の状態に応じて、特定のコマンドを無効にするのには<xref:System.Windows.Controls.TextBox>します。</span><span class="sxs-lookup"><span data-stu-id="30829-112">The <xref:System.Windows.Controls.ContextMenu.Opened> event is used to dynamically enable or disable certain commands depending on the current state of the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
 <span data-ttu-id="30829-113">既定のショートカット メニューを復元するには、使用、<xref:System.Windows.DependencyObject.ClearValue%2A>の値をクリアする方法、<xref:System.Windows.FrameworkElement.ContextMenu%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="30829-113">To restore the default context menu, use the <xref:System.Windows.DependencyObject.ClearValue%2A> method to clear the value of the <xref:System.Windows.FrameworkElement.ContextMenu%2A> property.</span></span>  <span data-ttu-id="30829-114">コンテキスト メニューを完全に無効にするのには、設定、<xref:System.Windows.FrameworkElement.ContextMenu%2A>プロパティを null 参照 (`Nothing` Visual Basic で)。</span><span class="sxs-lookup"><span data-stu-id="30829-114">To disable the context menu altogether, set the <xref:System.Windows.FrameworkElement.ContextMenu%2A> property to a null reference (`Nothing` in Visual Basic).</span></span>  
  
 [!code-csharp[TextBox_ContextMenu#_TextBox_ContextMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml.cs#_textbox_contextmenu)]
 [!code-vb[TextBox_ContextMenu#_TextBox_ContextMenu](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_ContextMenu/VisualBasic/Window1.xaml.vb#_textbox_contextmenu)]  
  
## <a name="see-also"></a><span data-ttu-id="30829-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="30829-115">See also</span></span>

- [<span data-ttu-id="30829-116">コンテキスト メニューでスペル チェックを使用する</span><span class="sxs-lookup"><span data-stu-id="30829-116">Use Spell Checking with a Context Menu</span></span>](how-to-use-spell-checking-with-a-context-menu.md)
- [<span data-ttu-id="30829-117">TextBox の概要</span><span class="sxs-lookup"><span data-stu-id="30829-117">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="30829-118">RichTextBox の概要</span><span class="sxs-lookup"><span data-stu-id="30829-118">RichTextBox Overview</span></span>](richtextbox-overview.md)
