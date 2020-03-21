---
title: '方法 : ToolStripMenuItems に拡張機能を追加する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- commands [Windows Forms], grouping on menus
- check marks [Windows Forms], adding to menus
- ToolStripMenuItems [Windows Forms], displaying access keys
- menus [Windows Forms], grouping commands
- menu items [Windows Forms], displaying shortcut keys
- ToolStripMenuItems
- separators [Windows Forms], displaying on menus
- menu items [Windows Forms], showing separators
- menu items [Windows Forms], adding check marks
- ToolStripMenuItems [Windows Forms], adding check marks
- menu items [Windows Forms], adding images
- ToolStripSeparators [Windows Forms], displaying on MenuStrips
- menu items [Windows Forms], displaying access keys
- ToolStripMenuItems [Windows Forms], displaying shortcut keys
- ToolStripMenuItems [Windows Forms], adding images
- keyboard shortcuts [Windows Forms], displaying on menus
- images [Windows Forms], adding to menus
- ToolStripMenuItems [Windows Forms], showing separator bars
ms.assetid: aa5f19bb-b545-4378-bfa6-36ba592f0d7c
ms.openlocfilehash: 61a79b9bbe101d7bf694240bdffdecee5187adf2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182321"
---
# <a name="how-to-add-enhancements-to-toolstripmenuitems"></a><span data-ttu-id="19dc3-102">方法 : ToolStripMenuItems に拡張機能を追加する</span><span class="sxs-lookup"><span data-stu-id="19dc3-102">How to: Add Enhancements to ToolStripMenuItems</span></span>
<span data-ttu-id="19dc3-103">以下の方法で、コントロールと<xref:System.Windows.Forms.MenuStrip><xref:System.Windows.Forms.ContextMenuStrip>コントロールの操作性を向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="19dc3-103">You can enhance the usability of <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> controls in the following ways:</span></span>  
  
- <span data-ttu-id="19dc3-104">ワープロ アプリケーションの余白にルーラーを表示するかどうか、またはウィンドウ**メニューなど**、ファイルの一覧のどのファイルを表示するかを示すなど、機能をオンまたはオフにするかどうかを指定するチェック マークを追加します。</span><span class="sxs-lookup"><span data-stu-id="19dc3-104">Add check marks to designate whether a feature is turned on or off, such as whether a ruler is displayed along the margin of a word-processing application, or to indicate which file in a list of files is being displayed, such as on a **Window** menu.</span></span>  
  
- <span data-ttu-id="19dc3-105">メニュー コマンドを視覚的に表すイメージを追加します。</span><span class="sxs-lookup"><span data-stu-id="19dc3-105">Add images that visually represent menu commands.</span></span>  
  
- <span data-ttu-id="19dc3-106">ショートカット キーを表示して、コマンドを実行するためのマウスの代わりにキーボードを提供します。</span><span class="sxs-lookup"><span data-stu-id="19dc3-106">Display shortcut keys to provide a keyboard alternative to the mouse for performing commands.</span></span> <span data-ttu-id="19dc3-107">たとえば、Ctrl キーを押しながら C キーを押すと **、コピー**コマンドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="19dc3-107">For example, pressing CTRL+C performs the **Copy** command.</span></span>  
  
- <span data-ttu-id="19dc3-108">アクセス キーを表示して、メニュー ナビゲーション用のマウスに代わるキーボードを提供します。</span><span class="sxs-lookup"><span data-stu-id="19dc3-108">Display access keys to provide a keyboard alternative to the mouse for menu navigation.</span></span> <span data-ttu-id="19dc3-109">たとえば、Alt キーを押しながら F キーを押すと、[**ファイル]** メニューが選択されます。</span><span class="sxs-lookup"><span data-stu-id="19dc3-109">For example, pressing ALT+F chooses the **File** menu.</span></span>  
  
- <span data-ttu-id="19dc3-110">関連するコマンドをグループ化し、メニューを読みやすくする区切りバーを表示します。</span><span class="sxs-lookup"><span data-stu-id="19dc3-110">Show separator bars to group related commands and make menus more readable.</span></span>  
  
### <a name="to-display-a-check-mark-on-a-menu-command"></a><span data-ttu-id="19dc3-111">メニュー コマンドにチェック マークを表示するには</span><span class="sxs-lookup"><span data-stu-id="19dc3-111">To display a check mark on a menu command</span></span>  
  
- <span data-ttu-id="19dc3-112">プロパティを<xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A>に`true`設定します。</span><span class="sxs-lookup"><span data-stu-id="19dc3-112">Set its <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property to `true`.</span></span>  
  
     <span data-ttu-id="19dc3-113">このプロパティもに<xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A>設定`true`されます。</span><span class="sxs-lookup"><span data-stu-id="19dc3-113">This also sets the <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> property to `true`.</span></span> <span data-ttu-id="19dc3-114">この手順は、メニュー コマンドが選択されているかどうかに関係なく、既定でオンに表示される場合にのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="19dc3-114">Use this procedure only if you want the menu command to appear as checked by default, regardless of whether it is selected.</span></span>  
  
### <a name="to-display-a-check-mark-that-changes-state-with-each-click"></a><span data-ttu-id="19dc3-115">クリックするたびに状態が変化するチェック マークを表示するには</span><span class="sxs-lookup"><span data-stu-id="19dc3-115">To display a check mark that changes state with each click</span></span>  
  
- <span data-ttu-id="19dc3-116">メニュー コマンドの<xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A>プロパティを に`true`設定します。</span><span class="sxs-lookup"><span data-stu-id="19dc3-116">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property to `true`.</span></span>  
  
### <a name="to-add-an-image-to-a-menu-command"></a><span data-ttu-id="19dc3-117">メニュー コマンドにイメージを追加するには</span><span class="sxs-lookup"><span data-stu-id="19dc3-117">To add an image to a menu command</span></span>  
  
- <span data-ttu-id="19dc3-118">メニュー コマンドの<xref:System.Windows.Forms.ToolStripItem.Image%2A>プロパティをイメージの名前に設定します。</span><span class="sxs-lookup"><span data-stu-id="19dc3-118">Set the menu command's <xref:System.Windows.Forms.ToolStripItem.Image%2A> property to the name of the image.</span></span> <span data-ttu-id="19dc3-119">このメニュー<xref:System.Windows.Forms.ToolStripItemDisplayStyle>コマンドのプロパティが or<xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text><xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>に設定されている場合、イメージを表示できません。</span><span class="sxs-lookup"><span data-stu-id="19dc3-119">If the <xref:System.Windows.Forms.ToolStripItemDisplayStyle> property of this menu command is set to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> or <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>, the image cannot be displayed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="19dc3-120">選択した場合、画像の余白にもチェック マークを表示できます。</span><span class="sxs-lookup"><span data-stu-id="19dc3-120">The image margin can also show a check mark if you so choose.</span></span> <span data-ttu-id="19dc3-121">また、イメージの<xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A>プロパティを に`true`設定すると、実行時に画像の周囲にハッチング境界が表示されます。</span><span class="sxs-lookup"><span data-stu-id="19dc3-121">Also, you can set the <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property of the image to `true`, and the image will appear with a hatched border around it at run time.</span></span>  
  
### <a name="to-display-a-shortcut-key-for-a-menu-command"></a><span data-ttu-id="19dc3-122">メニュー コマンドのショートカット キーを表示するには</span><span class="sxs-lookup"><span data-stu-id="19dc3-122">To display a shortcut key for a menu command</span></span>  
  
- <span data-ttu-id="19dc3-123">メニュー<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>コマンドのプロパティを、目的のキーボードの組み合わせ ([**開く**] メニュー コマンドの<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>Ctrl+ `true`O など) に設定し、プロパティを に設定します。</span><span class="sxs-lookup"><span data-stu-id="19dc3-123">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> property to the desired keyboard combination, such as CTRL+O for the **Open** menu command, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-custom-shortcut-keys-for-a-menu-command"></a><span data-ttu-id="19dc3-124">メニュー コマンドのカスタム ショートカット キーを表示するには</span><span class="sxs-lookup"><span data-stu-id="19dc3-124">To display custom shortcut keys for a menu command</span></span>  
  
- <span data-ttu-id="19dc3-125">メニュー コマンドの<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A>プロパティを、Shift キーを押しながら Ctrl キーを押しながら O キーを押すのではなく、Ctrl キー<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>を押`true`しながら Shift キーを押しながら O キーを押すなどのキーボードの組み合わせを設定し、プロパティを に設定します。</span><span class="sxs-lookup"><span data-stu-id="19dc3-125">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> property to the desired keyboard combination, such as CTRL+SHIFT+O rather than SHIFT+CTRL+O, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-an-access-key-for-a-menu-command"></a><span data-ttu-id="19dc3-126">メニュー コマンドのアクセス キーを表示するには</span><span class="sxs-lookup"><span data-stu-id="19dc3-126">To display an access key for a menu command</span></span>  
  
- <span data-ttu-id="19dc3-127">メニュー コマンドの<xref:System.Windows.Forms.ToolStripItem.Text%2A>プロパティを設定する場合は、アクセス キーとして下線を付ける文字の前にアンパサンド (&) を入力します。</span><span class="sxs-lookup"><span data-stu-id="19dc3-127">When you set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property for the menu command, enter an ampersand (&) before the letter you want to be underlined as the access key.</span></span> <span data-ttu-id="19dc3-128">たとえば、メニュー項目`&Open`の<xref:System.Windows.Forms.ToolStripItem.Text%2A>プロパティとして入力すると、メニュー コマンドは<u>O</u>ペンとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="19dc3-128">For example, typing `&Open` as the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of a menu item will result in a menu command that appears as <u>O</u>pen.</span></span>
  
     <span data-ttu-id="19dc3-129">このメニュー コマンドに移動するには、 Alt キーを押<xref:System.Windows.Forms.MenuStrip>して にフォーカスを移動し、メニュー名のアクセス キーを押します。</span><span class="sxs-lookup"><span data-stu-id="19dc3-129">To navigate to this menu command, press ALT to give focus to the <xref:System.Windows.Forms.MenuStrip>, and press the access key of the menu name.</span></span> <span data-ttu-id="19dc3-130">メニューが開き、アクセスキーを持つ項目が表示されたら、アクセスキーを押してメニューコマンドを選択するだけです。</span><span class="sxs-lookup"><span data-stu-id="19dc3-130">When the menu opens and shows items with access keys, you only need to press the access key to select the menu command.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="19dc3-131">同じメニュー システムで Alt + F を 2 回定義するなど、重複するアクセス キーを定義しないようにします。</span><span class="sxs-lookup"><span data-stu-id="19dc3-131">Avoid defining duplicate access keys, such as defining ALT+F twice in the same menu system.</span></span> <span data-ttu-id="19dc3-132">重複アクセス キーの選択順序は保証できません。</span><span class="sxs-lookup"><span data-stu-id="19dc3-132">The selection order of duplicate access keys cannot be guaranteed.</span></span>  
  
### <a name="to-display-a-separator-bar-between-menu-commands"></a><span data-ttu-id="19dc3-133">メニュー コマンドの間に区切り線を表示するには</span><span class="sxs-lookup"><span data-stu-id="19dc3-133">To display a separator bar between menu commands</span></span>  
  
- <span data-ttu-id="19dc3-134"><xref:System.Windows.Forms.MenuStrip>を定義し、そのアイテムに含める項目を定義したら<xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A>、<xref:System.Windows.Forms.ToolStripItemCollection.Add%2A>または メソッドを使用して<xref:System.Windows.Forms.ToolStripSeparator>、メニュー<xref:System.Windows.Forms.MenuStrip>コマンドとコントロールを目的の順序で に追加します。</span><span class="sxs-lookup"><span data-stu-id="19dc3-134">After you define your <xref:System.Windows.Forms.MenuStrip> and the items it will contain, use the <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> or <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> method to add the menu commands and <xref:System.Windows.Forms.ToolStripSeparator> controls to the <xref:System.Windows.Forms.MenuStrip> in the order you want.</span></span>  
  
    ```vb  
    ' This code adds a top-level File menu to the MenuStrip.  
    Me.menuStrip1.Items.Add(New ToolStripMenuItem() _  
    {Me.fileToolStripMenuItem})  
  
    ' This code adds the New and Open menu commands, a separator bar,
    ' and the Save and Exit menu commands to the top-level File menu,
    ' in that order.  
    Me.fileToolStripMenuItem.DropDownItems.AddRange(New _  
    ToolStripMenuItem() {Me.newToolStripMenuItem, _  
    Me.openToolStripMenuItem, Me.toolStripSeparator1, _  
    Me.saveToolStripMenuItem, Me.exitToolStripMenuItem})  
    ```  
  
    ```csharp  
    // This code adds a top-level File menu to the MenuStrip.  
    this.menuStrip1.Items.Add(new ToolStripItem[]_  
    {this.fileToolStripMenuItem});  
  
    // This code adds the New and Open menu commands, a separator bar,
    // and the Save and Exit menu commands to the top-level File menu,
    // in that order.  
    this.fileToolStripMenuItem.DropDownItems.AddRange(new _  
    ToolStripItem[] {  
    this.newToolStripMenuItem,  
    this.openToolStripMenuItem,  
    this.toolStripSeparator1,  
    this.saveToolStripMenuItem,  
    this.exitToolStripMenuItem});  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="19dc3-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="19dc3-135">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="19dc3-136">MenuStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="19dc3-136">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
