---
title: '方法: ToolStripMenuItems に拡張機能を追加する'
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
ms.openlocfilehash: 458347df7e17aabc1e9e21d66ad1b5a96200fe28
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59198557"
---
# <a name="how-to-add-enhancements-to-toolstripmenuitems"></a><span data-ttu-id="0ed50-102">方法: ToolStripMenuItems に拡張機能を追加する</span><span class="sxs-lookup"><span data-stu-id="0ed50-102">How to: Add Enhancements to ToolStripMenuItems</span></span>
<span data-ttu-id="0ed50-103">使いやすさを強化する<xref:System.Windows.Forms.MenuStrip>と<xref:System.Windows.Forms.ContextMenuStrip>次の方法でコントロール。</span><span class="sxs-lookup"><span data-stu-id="0ed50-103">You can enhance the usability of <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> controls in the following ways:</span></span>  
  
-   <span data-ttu-id="0ed50-104">ワード プロセッシング アプリケーションでは、余白に、ルーラーを表示するかどうかなど、オンまたはオフ、機能を有効になっているかどうかを指定する、またはファイルの一覧で、どのファイルが表示されてこのようなのかを示すチェック マークを追加、**ウィンドウ**メニュー。</span><span class="sxs-lookup"><span data-stu-id="0ed50-104">Add check marks to designate whether a feature is turned on or off, such as whether a ruler is displayed along the margin of a word-processing application, or to indicate which file in a list of files is being displayed, such as on a **Window** menu.</span></span>  
  
-   <span data-ttu-id="0ed50-105">視覚的にメニュー コマンドを表すイメージを追加します。</span><span class="sxs-lookup"><span data-stu-id="0ed50-105">Add images that visually represent menu commands.</span></span>  
  
-   <span data-ttu-id="0ed50-106">コマンドを実行するために、マウスの代わりにキーボードを提供するショートカット キーを表示します。</span><span class="sxs-lookup"><span data-stu-id="0ed50-106">Display shortcut keys to provide a keyboard alternative to the mouse for performing commands.</span></span> <span data-ttu-id="0ed50-107">たとえば、実行 CTRL + C キーを押して、**コピー**コマンド。</span><span class="sxs-lookup"><span data-stu-id="0ed50-107">For example, pressing CTRL+C performs the **Copy** command.</span></span>  
  
-   <span data-ttu-id="0ed50-108">メニュー ナビゲーションのマウス、キーボードの代わりを提供するアクセス キーを表示します。</span><span class="sxs-lookup"><span data-stu-id="0ed50-108">Display access keys to provide a keyboard alternative to the mouse for menu navigation.</span></span> <span data-ttu-id="0ed50-109">たとえば、alt キーを押しながら F キーを押してが選択、**ファイル**メニュー。</span><span class="sxs-lookup"><span data-stu-id="0ed50-109">For example, pressing ALT+F chooses the **File** menu.</span></span>  
  
-   <span data-ttu-id="0ed50-110">関連するコマンドをグループ化し、メニューを読みやすくのセパレーター バーを表示します。</span><span class="sxs-lookup"><span data-stu-id="0ed50-110">Show separator bars to group related commands and make menus more readable.</span></span>  
  
### <a name="to-display-a-check-mark-on-a-menu-command"></a><span data-ttu-id="0ed50-111">メニュー コマンドにチェック マークを表示するには</span><span class="sxs-lookup"><span data-stu-id="0ed50-111">To display a check mark on a menu command</span></span>  
  
-   <span data-ttu-id="0ed50-112">設定の<xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A>プロパティを`true`します。</span><span class="sxs-lookup"><span data-stu-id="0ed50-112">Set its <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property to `true`.</span></span>  
  
     <span data-ttu-id="0ed50-113">これも設定、<xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A>プロパティを`true`します。</span><span class="sxs-lookup"><span data-stu-id="0ed50-113">This also sets the <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> property to `true`.</span></span> <span data-ttu-id="0ed50-114">メニュー コマンドが選択されているかどうかに関係なく、既定でチェック マークを付けて表示をする場合にのみ、この手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="0ed50-114">Use this procedure only if you want the menu command to appear as checked by default, regardless of whether it is selected.</span></span>  
  
### <a name="to-display-a-check-mark-that-changes-state-with-each-click"></a><span data-ttu-id="0ed50-115">クリックするたびに状態を変更するチェック マークを表示するには</span><span class="sxs-lookup"><span data-stu-id="0ed50-115">To display a check mark that changes state with each click</span></span>  
  
-   <span data-ttu-id="0ed50-116">設定、メニュー コマンドの<xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A>プロパティを`true`します。</span><span class="sxs-lookup"><span data-stu-id="0ed50-116">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property to `true`.</span></span>  
  
### <a name="to-add-an-image-to-a-menu-command"></a><span data-ttu-id="0ed50-117">メニュー コマンドにイメージを追加するには</span><span class="sxs-lookup"><span data-stu-id="0ed50-117">To add an image to a menu command</span></span>  
  
-   <span data-ttu-id="0ed50-118">設定、メニュー コマンドの<xref:System.Windows.Forms.ToolStripItem.Image%2A>プロパティをイメージの名前にします。</span><span class="sxs-lookup"><span data-stu-id="0ed50-118">Set the menu command's <xref:System.Windows.Forms.ToolStripItem.Image%2A> property to the name of the image.</span></span> <span data-ttu-id="0ed50-119">場合、<xref:System.Windows.Forms.ToolStripItemDisplayStyle>このメニュー コマンドのプロパティに設定されて<xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>または<xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>イメージを表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="0ed50-119">If the <xref:System.Windows.Forms.ToolStripItemDisplayStyle> property of this menu command is set to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> or <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>, the image cannot be displayed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ed50-120">イメージの余白も表示できます、チェック マークできます。</span><span class="sxs-lookup"><span data-stu-id="0ed50-120">The image margin can also show a check mark if you so choose.</span></span> <span data-ttu-id="0ed50-121">また、設定、<xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A>するイメージのプロパティ`true`、およびイメージは、実行時にハッチ境界線と共に表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ed50-121">Also, you can set the <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property of the image to `true`, and the image will appear with a hatched border around it at run time.</span></span>  
  
### <a name="to-display-a-shortcut-key-for-a-menu-command"></a><span data-ttu-id="0ed50-122">メニュー コマンドのショートカット キーを表示するには</span><span class="sxs-lookup"><span data-stu-id="0ed50-122">To display a shortcut key for a menu command</span></span>  
  
-   <span data-ttu-id="0ed50-123">設定、メニュー コマンドの<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>プロパティの CTRL + O など、目的のキーボードの組み合わせを**オープン**メニュー コマンド、およびセット、<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>プロパティを`true`します。</span><span class="sxs-lookup"><span data-stu-id="0ed50-123">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> property to the desired keyboard combination, such as CTRL+O for the **Open** menu command, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-custom-shortcut-keys-for-a-menu-command"></a><span data-ttu-id="0ed50-124">メニュー コマンドのカスタム ショートカット キーを表示するには</span><span class="sxs-lookup"><span data-stu-id="0ed50-124">To display custom shortcut keys for a menu command</span></span>  
  
-   <span data-ttu-id="0ed50-125">設定、メニュー コマンドの<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A>プロパティ SHIFT + CTRL + O とセットではなく、CTRL + SHIFT + O など、目的のキーボードの組み合わせを<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>プロパティを`true`します。</span><span class="sxs-lookup"><span data-stu-id="0ed50-125">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> property to the desired keyboard combination, such as CTRL+SHIFT+O rather than SHIFT+CTRL+O, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-an-access-key-for-a-menu-command"></a><span data-ttu-id="0ed50-126">メニュー コマンドのアクセス キーを表示するには</span><span class="sxs-lookup"><span data-stu-id="0ed50-126">To display an access key for a menu command</span></span>  
  
-   <span data-ttu-id="0ed50-127">設定すると、<xref:System.Windows.Forms.ToolStripItem.Text%2A>メニュー コマンドは、プロパティは、アンパサンドを入力します。 (&) は、アクセス キーと下線付きで表示する文字の前にします。</span><span class="sxs-lookup"><span data-stu-id="0ed50-127">When you set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property for the menu command, enter an ampersand (&) before the letter you want to be underlined as the access key.</span></span> <span data-ttu-id="0ed50-128">たとえば、入力`&Open`として、<xref:System.Windows.Forms.ToolStripItem.Text%2A>として表示されるメニュー コマンドとメニュー項目のプロパティ、 <u>O</u>ペン。</span><span class="sxs-lookup"><span data-stu-id="0ed50-128">For example, typing `&Open` as the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of a menu item will result in a menu command that appears as <u>O</u>pen.</span></span>
  
     <span data-ttu-id="0ed50-129">このメニュー コマンドに移動する、フォーカスを移す ALT キーを押し、<xref:System.Windows.Forms.MenuStrip>メニュー名のアクセス キーを押します。</span><span class="sxs-lookup"><span data-stu-id="0ed50-129">To navigate to this menu command, press ALT to give focus to the <xref:System.Windows.Forms.MenuStrip>, and press the access key of the menu name.</span></span> <span data-ttu-id="0ed50-130">メニューが開きアクセス キーを持つ項目が表示されます、ときにのみ、メニュー コマンドを選択するアクセス キーを押す必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ed50-130">When the menu opens and shows items with access keys, you only need to press the access key to select the menu command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ed50-131">同じメニュー システムで 2 回 ALT キーを押しながら F キーを定義するなどの重複するアクセス キーを定義しないでください。</span><span class="sxs-lookup"><span data-stu-id="0ed50-131">Avoid defining duplicate access keys, such as defining ALT+F twice in the same menu system.</span></span> <span data-ttu-id="0ed50-132">重複するアクセス キーの選択順序を保証できません。</span><span class="sxs-lookup"><span data-stu-id="0ed50-132">The selection order of duplicate access keys cannot be guaranteed.</span></span>  
  
### <a name="to-display-a-separator-bar-between-menu-commands"></a><span data-ttu-id="0ed50-133">メニュー コマンドの間の区切り線を表示するには</span><span class="sxs-lookup"><span data-stu-id="0ed50-133">To display a separator bar between menu commands</span></span>  
  
-   <span data-ttu-id="0ed50-134">定義した後、<xref:System.Windows.Forms.MenuStrip>と項目が含まれます使用して、<xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A>または<xref:System.Windows.Forms.ToolStripItemCollection.Add%2A>メニュー コマンドを追加するメソッドをおよび<xref:System.Windows.Forms.ToolStripSeparator>にコントロールを<xref:System.Windows.Forms.MenuStrip>順序で。</span><span class="sxs-lookup"><span data-stu-id="0ed50-134">After you define your <xref:System.Windows.Forms.MenuStrip> and the items it will contain, use the <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> or <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> method to add the menu commands and <xref:System.Windows.Forms.ToolStripSeparator> controls to the <xref:System.Windows.Forms.MenuStrip> in the order you want.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0ed50-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="0ed50-135">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="0ed50-136">MenuStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="0ed50-136">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
