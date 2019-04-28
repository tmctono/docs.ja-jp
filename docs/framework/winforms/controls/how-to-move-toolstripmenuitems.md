---
title: '方法: ToolStripMenuItems を移動する'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], moving
- menus [Windows Forms], arranging items
- ToolStripMenuItems [Windows Forms], dragging and dropping
- menu items [Windows Forms], moving
- menu items [Windows Forms], cutting and pasting
- menu items [Windows Forms], dragging and dropping
- MenuStrip control [Windows Forms], arranging items
- ToolStripMenuItems [Windows Forms], cutting and pasting
ms.assetid: cab9e03e-4edd-4c25-b3e3-bd1edc602bd9
ms.openlocfilehash: 2203511e91254c270c59b5d298dd87a5b3737109
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61913628"
---
# <a name="how-to-move-toolstripmenuitems"></a><span data-ttu-id="eb0be-102">方法: ToolStripMenuItems を移動する</span><span class="sxs-lookup"><span data-stu-id="eb0be-102">How to: Move ToolStripMenuItems</span></span>
<span data-ttu-id="eb0be-103">デザイン時に移動できますトップレベル メニュー全体とそのメニュー項目を別の場所、<xref:System.Windows.Forms.MenuStrip>します。</span><span class="sxs-lookup"><span data-stu-id="eb0be-103">At design time, you can move entire top-level menus and their menu items to a different place on the <xref:System.Windows.Forms.MenuStrip>.</span></span> <span data-ttu-id="eb0be-104">トップレベル メニュー間で個々 のメニュー項目を移動またはメニュー内でのメニュー項目の位置を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="eb0be-104">You can also move individual menu items between top-level menus or change the position of menu items within a menu.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eb0be-105">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="eb0be-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="eb0be-106">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb0be-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="eb0be-107">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb0be-107">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-move-a-top-level-menu-and-its-menu-items-to-another-top-level-location"></a><span data-ttu-id="eb0be-108">トップレベル メニューとメニュー項目を最上位レベルの別の場所に移動するには</span><span class="sxs-lookup"><span data-stu-id="eb0be-108">To move a top-level menu and its menu items to another top-level location</span></span>  
  
1. <span data-ttu-id="eb0be-109">クリックして、移動するメニューにマウスの左ボタンを押したままにします。</span><span class="sxs-lookup"><span data-stu-id="eb0be-109">Click and hold down the left mouse button on the menu that you want to move.</span></span>  
  
2. <span data-ttu-id="eb0be-110">新しい場所の前にあるトップレベル メニューにカーソルをドラッグし、マウスの左ボタンを放します。</span><span class="sxs-lookup"><span data-stu-id="eb0be-110">Drag the insertion point to the top-level menu that is before the intended new location and release the left mouse button.</span></span>  
  
     <span data-ttu-id="eb0be-111">選択したメニューは、カーソルの右側に移動します。</span><span class="sxs-lookup"><span data-stu-id="eb0be-111">The selected menu moves to the right of the insertion point.</span></span>  
  
### <a name="to-move-a-top-level-menu-and-its-menu-items-to-a-drop-down-location"></a><span data-ttu-id="eb0be-112">トップレベル メニューとメニュー項目をドロップダウン リストの場所に移動するには</span><span class="sxs-lookup"><span data-stu-id="eb0be-112">To move a top-level menu and its menu items to a drop-down location</span></span>  
  
1. <span data-ttu-id="eb0be-113">移動、CTRL + X キーを押すとメニューを右クリックしてや選択するメニューを左クリックして**切り取り**ショートカット メニューから。</span><span class="sxs-lookup"><span data-stu-id="eb0be-113">Left-click the menu that you want to move and press CTRL+X, or right-click the menu and select **Cut** from the shortcut menu.</span></span>  
  
2. <span data-ttu-id="eb0be-114">宛先のトップレベル メニューで新しい場所の上のメニュー項目を左クリックし CTRL + V キーを押して新しい場所の上のメニュー項目を右クリックしてや選択**貼り付け**ショートカット メニューから。</span><span class="sxs-lookup"><span data-stu-id="eb0be-114">In the destination top-level menu, left-click the menu item above the intended new location and press CTRL+V, or right-click the menu item above the intended new location and select **Paste** from the shortcut menu.</span></span>  
  
     <span data-ttu-id="eb0be-115">切り取ったメニューは、選択したメニュー項目の後に挿入されます。</span><span class="sxs-lookup"><span data-stu-id="eb0be-115">The menu that you cut is inserted after the selected menu item.</span></span>  
  
### <a name="to-move-a-menu-item-within-a-menu-using-the-items-collection-editor"></a><span data-ttu-id="eb0be-116">項目コレクション エディターを使用してメニュー内のメニュー項目を移動するには</span><span class="sxs-lookup"><span data-stu-id="eb0be-116">To move a menu item within a menu using the Items Collection Editor</span></span>  
  
1. <span data-ttu-id="eb0be-117">移動するメニュー項目を含むメニューを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="eb0be-117">Right-click the menu that contains the menu item you want to move.</span></span>  
  
2. <span data-ttu-id="eb0be-118">ショートカット メニューの**編集ドロップダウン項目です**します。</span><span class="sxs-lookup"><span data-stu-id="eb0be-118">From the shortcut menu, choose **Edit DropDownItems**.</span></span>  
  
3. <span data-ttu-id="eb0be-119">**Items コレクション エディター**、移動するメニュー項目を左クリックします。</span><span class="sxs-lookup"><span data-stu-id="eb0be-119">In the **Items Collection Editor**, left-click the menu item you want to move.</span></span>  
  
4. <span data-ttu-id="eb0be-120">メニュー内のメニュー項目を移動する、上下矢印キーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb0be-120">Click the UP and DOWN ARROW keys to move the menu item within the menu.</span></span>  
  
5. <span data-ttu-id="eb0be-121">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb0be-121">Click **OK**.</span></span>  
  
### <a name="to-move-a-menu-item-within-a-menu-using-the-keyboard"></a><span data-ttu-id="eb0be-122">キーボードを使用してメニュー内のメニュー項目を移動するには</span><span class="sxs-lookup"><span data-stu-id="eb0be-122">To move a menu item within a menu using the keyboard</span></span>  
  
1. <span data-ttu-id="eb0be-123">キーを押して、ALT キーを押したままにします。</span><span class="sxs-lookup"><span data-stu-id="eb0be-123">Press and hold down the ALT key.</span></span>  
  
2. <span data-ttu-id="eb0be-124">移動するメニュー項目をマウスの左ボタンを押したままにします。</span><span class="sxs-lookup"><span data-stu-id="eb0be-124">Click and hold the left mouse button on the menu item that you want to move.</span></span>  
  
3. <span data-ttu-id="eb0be-125">メニュー項目を新しい場所にドラッグし、マウスの左ボタンを離します。</span><span class="sxs-lookup"><span data-stu-id="eb0be-125">Drag the menu item to the new location and release the left mouse button.</span></span>  
  
### <a name="to-move-a-menu-item-to-another-menu"></a><span data-ttu-id="eb0be-126">別のメニューにメニュー項目を移動するには</span><span class="sxs-lookup"><span data-stu-id="eb0be-126">To move a menu item to another menu</span></span>  
  
1. <span data-ttu-id="eb0be-127">移動、CTRL + X キーを押すとメニュー項目を右クリックしてや選択するメニュー項目を左クリックして**切り取り**ショートカット メニューから。</span><span class="sxs-lookup"><span data-stu-id="eb0be-127">Left-click the menu item that you want to move and press CTRL+X, or right-click the menu item and choose **Cut** from the shortcut menu.</span></span>  
  
2. <span data-ttu-id="eb0be-128">切り取りメニュー項目を含むメニューをクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb0be-128">Left-click the menu that will contain the menu item that you cut.</span></span>  
  
3. <span data-ttu-id="eb0be-129">新しい場所の前にあるメニュー項目を左クリックし、ctrl キーを押しながら V キーを押してまたはクリックし、新しい場所の前にあるメニュー項目を右クリックして**貼り付け**ショートカット メニューから。</span><span class="sxs-lookup"><span data-stu-id="eb0be-129">Left-click the menu item that is before the intended new location and press CTRL+V, or right-click the menu item that is before the intended new location and select **Paste** from the shortcut menu.</span></span>  
  
     <span data-ttu-id="eb0be-130">切り取りメニュー項目が選択されているメニュー項目の後に挿入されます。</span><span class="sxs-lookup"><span data-stu-id="eb0be-130">The menu item that you cut is inserted after the selected menu item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb0be-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="eb0be-131">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="eb0be-132">MenuStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="eb0be-132">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
