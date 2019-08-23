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
ms.openlocfilehash: 9e95c3623bf9bad8395f586392a0557ad1cde880
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912582"
---
# <a name="how-to-add-enhancements-to-toolstripmenuitems"></a><span data-ttu-id="095ff-102">方法: ToolStripMenuItems に拡張機能を追加する</span><span class="sxs-lookup"><span data-stu-id="095ff-102">How to: Add Enhancements to ToolStripMenuItems</span></span>
<span data-ttu-id="095ff-103">次の方法で、および<xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ContextMenuStrip>コントロールの使いやすさを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="095ff-103">You can enhance the usability of <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> controls in the following ways:</span></span>  
  
- <span data-ttu-id="095ff-104">チェックマークを追加して、機能を有効にするかどうかを指定します。たとえば、ワードプロセッシングアプリケーションの余白に沿ってルーラーを表示するかどうか、ファイルの一覧に表示されるファイル ( **[ウィンドウ]** メニューなど) を指定します。</span><span class="sxs-lookup"><span data-stu-id="095ff-104">Add check marks to designate whether a feature is turned on or off, such as whether a ruler is displayed along the margin of a word-processing application, or to indicate which file in a list of files is being displayed, such as on a **Window** menu.</span></span>  
  
- <span data-ttu-id="095ff-105">メニューコマンドを視覚的に表すイメージを追加します。</span><span class="sxs-lookup"><span data-stu-id="095ff-105">Add images that visually represent menu commands.</span></span>  
  
- <span data-ttu-id="095ff-106">ショートカットキーを表示して、コマンドを実行するためのキーボード代替手段をマウスに提供します。</span><span class="sxs-lookup"><span data-stu-id="095ff-106">Display shortcut keys to provide a keyboard alternative to the mouse for performing commands.</span></span> <span data-ttu-id="095ff-107">たとえば、CTRL キーを押しながら C キーを押すと、 **Copy**コマンドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="095ff-107">For example, pressing CTRL+C performs the **Copy** command.</span></span>  
  
- <span data-ttu-id="095ff-108">アクセスキーを表示して、メニューナビゲーション用のマウスの代わりにキーボードを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="095ff-108">Display access keys to provide a keyboard alternative to the mouse for menu navigation.</span></span> <span data-ttu-id="095ff-109">たとえば、ALT キーを押しながら F キーを押すと、 **[ファイル]** メニューが選択されます。</span><span class="sxs-lookup"><span data-stu-id="095ff-109">For example, pressing ALT+F chooses the **File** menu.</span></span>  
  
- <span data-ttu-id="095ff-110">区分線を表示して関連するコマンドをグループ化し、メニューを読みやすくします。</span><span class="sxs-lookup"><span data-stu-id="095ff-110">Show separator bars to group related commands and make menus more readable.</span></span>  
  
### <a name="to-display-a-check-mark-on-a-menu-command"></a><span data-ttu-id="095ff-111">メニューコマンドにチェックマークを表示するには</span><span class="sxs-lookup"><span data-stu-id="095ff-111">To display a check mark on a menu command</span></span>  
  
- <span data-ttu-id="095ff-112">プロパティをに`true`設定します。 <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A></span><span class="sxs-lookup"><span data-stu-id="095ff-112">Set its <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property to `true`.</span></span>  
  
     <span data-ttu-id="095ff-113">これにより、 <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A>プロパティも`true`に設定されます。</span><span class="sxs-lookup"><span data-stu-id="095ff-113">This also sets the <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> property to `true`.</span></span> <span data-ttu-id="095ff-114">この手順は、メニューコマンドが選択されているかどうかに関係なく、既定でオンになっている場合にのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="095ff-114">Use this procedure only if you want the menu command to appear as checked by default, regardless of whether it is selected.</span></span>  
  
### <a name="to-display-a-check-mark-that-changes-state-with-each-click"></a><span data-ttu-id="095ff-115">各クリックで状態を変更するチェックマークを表示するには</span><span class="sxs-lookup"><span data-stu-id="095ff-115">To display a check mark that changes state with each click</span></span>  
  
- <span data-ttu-id="095ff-116">メニューコマンドの<xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A>プロパティをに`true`設定します。</span><span class="sxs-lookup"><span data-stu-id="095ff-116">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property to `true`.</span></span>  
  
### <a name="to-add-an-image-to-a-menu-command"></a><span data-ttu-id="095ff-117">メニューコマンドにイメージを追加するには</span><span class="sxs-lookup"><span data-stu-id="095ff-117">To add an image to a menu command</span></span>  
  
- <span data-ttu-id="095ff-118">メニューコマンドの<xref:System.Windows.Forms.ToolStripItem.Image%2A>プロパティをイメージの名前に設定します。</span><span class="sxs-lookup"><span data-stu-id="095ff-118">Set the menu command's <xref:System.Windows.Forms.ToolStripItem.Image%2A> property to the name of the image.</span></span> <span data-ttu-id="095ff-119">このメニューコマンドの<xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> <xref:System.Windows.Forms.ToolStripItemDisplayStyle>プロパティがまたはに設定されている場合は、イメージを表示できません。</span><span class="sxs-lookup"><span data-stu-id="095ff-119">If the <xref:System.Windows.Forms.ToolStripItemDisplayStyle> property of this menu command is set to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> or <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>, the image cannot be displayed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="095ff-120">画像の余白では、選択した場合にチェックマークを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="095ff-120">The image margin can also show a check mark if you so choose.</span></span> <span data-ttu-id="095ff-121">また、イメージの<xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A>プロパティをに`true`設定すると、実行時にイメージがハッチ境界線で囲まれて表示されます。</span><span class="sxs-lookup"><span data-stu-id="095ff-121">Also, you can set the <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property of the image to `true`, and the image will appear with a hatched border around it at run time.</span></span>  
  
### <a name="to-display-a-shortcut-key-for-a-menu-command"></a><span data-ttu-id="095ff-122">メニューコマンドのショートカットキーを表示するには</span><span class="sxs-lookup"><span data-stu-id="095ff-122">To display a shortcut key for a menu command</span></span>  
  
- <span data-ttu-id="095ff-123">メニューコマンドの<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>プロパティを、[メニューを**開く**] コマンドの CTRL + O などの目的のキーボードの組み合わせに設定し<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> 、プロパティ`true`をに設定します。</span><span class="sxs-lookup"><span data-stu-id="095ff-123">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> property to the desired keyboard combination, such as CTRL+O for the **Open** menu command, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-custom-shortcut-keys-for-a-menu-command"></a><span data-ttu-id="095ff-124">メニューコマンドのカスタムショートカットキーを表示するには</span><span class="sxs-lookup"><span data-stu-id="095ff-124">To display custom shortcut keys for a menu command</span></span>  
  
- <span data-ttu-id="095ff-125">メニューコマンドの<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A>プロパティに、shift + CTRL + o ではなく、ctrl + shift + o などの目的のキーボードの組み合わせを設定し<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> 、プロパティ`true`をに設定します。</span><span class="sxs-lookup"><span data-stu-id="095ff-125">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> property to the desired keyboard combination, such as CTRL+SHIFT+O rather than SHIFT+CTRL+O, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-an-access-key-for-a-menu-command"></a><span data-ttu-id="095ff-126">メニューコマンドのアクセスキーを表示するには</span><span class="sxs-lookup"><span data-stu-id="095ff-126">To display an access key for a menu command</span></span>  
  
- <span data-ttu-id="095ff-127">メニューコマンドの<xref:System.Windows.Forms.ToolStripItem.Text%2A>プロパティを設定するときに、アクセスキーとして下線を付ける文字の前にアンパサンド (&) を入力します。</span><span class="sxs-lookup"><span data-stu-id="095ff-127">When you set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property for the menu command, enter an ampersand (&) before the letter you want to be underlined as the access key.</span></span> <span data-ttu-id="095ff-128">たとえば、メニュー項目`&Open`の<xref:System.Windows.Forms.ToolStripItem.Text%2A>プロパティとして「」と入力すると、メニューコマンドが<u>O</u>ペンとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="095ff-128">For example, typing `&Open` as the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of a menu item will result in a menu command that appears as <u>O</u>pen.</span></span>
  
     <span data-ttu-id="095ff-129">このメニューコマンドに移動するには<xref:System.Windows.Forms.MenuStrip>、ALT キーを押してにフォーカスを移し、メニュー名のアクセスキーを押します。</span><span class="sxs-lookup"><span data-stu-id="095ff-129">To navigate to this menu command, press ALT to give focus to the <xref:System.Windows.Forms.MenuStrip>, and press the access key of the menu name.</span></span> <span data-ttu-id="095ff-130">メニューが開き、アクセスキーを持つ項目が表示されたら、アクセスキーを押してメニューコマンドを選択するだけです。</span><span class="sxs-lookup"><span data-stu-id="095ff-130">When the menu opens and shows items with access keys, you only need to press the access key to select the menu command.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="095ff-131">同じメニューシステムで ALT + F を2回定義するなど、重複するアクセスキーを定義することは避けてください。</span><span class="sxs-lookup"><span data-stu-id="095ff-131">Avoid defining duplicate access keys, such as defining ALT+F twice in the same menu system.</span></span> <span data-ttu-id="095ff-132">重複するアクセスキーの選択順序を保証することはできません。</span><span class="sxs-lookup"><span data-stu-id="095ff-132">The selection order of duplicate access keys cannot be guaranteed.</span></span>  
  
### <a name="to-display-a-separator-bar-between-menu-commands"></a><span data-ttu-id="095ff-133">メニューコマンドの間に区切りバーを表示するには</span><span class="sxs-lookup"><span data-stu-id="095ff-133">To display a separator bar between menu commands</span></span>  
  
- <span data-ttu-id="095ff-134"><xref:System.Windows.Forms.MenuStrip>とそれに含まれる項目を定義したら、メソッド<xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A>または<xref:System.Windows.Forms.ToolStripItemCollection.Add%2A>メソッドを使用して、 <xref:System.Windows.Forms.MenuStrip>メニュー <xref:System.Windows.Forms.ToolStripSeparator>コマンドとコントロールを目的の順序でに追加します。</span><span class="sxs-lookup"><span data-stu-id="095ff-134">After you define your <xref:System.Windows.Forms.MenuStrip> and the items it will contain, use the <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> or <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> method to add the menu commands and <xref:System.Windows.Forms.ToolStripSeparator> controls to the <xref:System.Windows.Forms.MenuStrip> in the order you want.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="095ff-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="095ff-135">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="095ff-136">MenuStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="095ff-136">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
