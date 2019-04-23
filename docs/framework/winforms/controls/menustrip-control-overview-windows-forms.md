---
title: MenuStrip コントロールの概要 (Windows フォーム)
ms.date: 03/30/2017
f1_keywords:
- MenuStrip
helpviewer_keywords:
- MenuStrip control [Windows Forms], about MenuStrip control
- menus [Windows Forms], creating
ms.assetid: f45516e5-bf01-4468-b851-d45f4c33c055
ms.openlocfilehash: 7cd761697a09205294727043efc6cf73816803ce
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "59975599"
---
# <a name="menustrip-control-overview-windows-forms"></a><span data-ttu-id="d4b10-102">MenuStrip コントロールの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="d4b10-102">MenuStrip Control Overview (Windows Forms)</span></span>
<span data-ttu-id="d4b10-103">メニューは、共通のテーマでグループ化されているコマンドを保持して、ユーザーに機能を公開します。</span><span class="sxs-lookup"><span data-stu-id="d4b10-103">Menus expose functionality to your users by holding commands that are grouped by a common theme.</span></span>  
  
 <span data-ttu-id="d4b10-104"><xref:System.Windows.Forms.MenuStrip>コントロールはこのバージョンの Visual Studio および .NET Framework で新しく導入されます。</span><span class="sxs-lookup"><span data-stu-id="d4b10-104">The <xref:System.Windows.Forms.MenuStrip> control is new to this version of Visual Studio and the .NET Framework.</span></span> <span data-ttu-id="d4b10-105">コントロールで、Microsoft Office で見られるようなメニューを簡単に作成することができます。</span><span class="sxs-lookup"><span data-stu-id="d4b10-105">With the control, you can easily create menus like those found in Microsoft Office.</span></span>  
  
 <span data-ttu-id="d4b10-106"><xref:System.Windows.Forms.MenuStrip>マルチ ドキュメント インターフェイス (MDI) とメニューのマージ、ツール ヒント、およびオーバーフロー コントロールをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d4b10-106">The <xref:System.Windows.Forms.MenuStrip> control supports the multiple-document interface (MDI) and menu merging, tool tips, and overflow.</span></span> <span data-ttu-id="d4b10-107">アクセス キー、ショートカット キー、チェック マーク、イメージ、および区分線を追加することで、メニューの読みやすさと使いやすさを強化できます。</span><span class="sxs-lookup"><span data-stu-id="d4b10-107">You can enhance the usability and readability of your menus by adding access keys, shortcut keys, check marks, images, and separator bars.</span></span>  
  
 <span data-ttu-id="d4b10-108"><xref:System.Windows.Forms.MenuStrip>コントロールが置換および機能を追加、<xref:System.Windows.Forms.MainMenu>制御します。 ただし、、<xref:System.Windows.Forms.MainMenu>を選択した場合、下位互換性と将来の使用のコントロールは保持されます。</span><span class="sxs-lookup"><span data-stu-id="d4b10-108">The <xref:System.Windows.Forms.MenuStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.MainMenu> control; however, the <xref:System.Windows.Forms.MainMenu> control is retained for backward compatibility and future use if you choose.</span></span>  
  
## <a name="ways-to-use-the-menustrip-control"></a><span data-ttu-id="d4b10-109">MenuStrip コントロールを使用する方法</span><span class="sxs-lookup"><span data-stu-id="d4b10-109">Ways to Use the MenuStrip Control</span></span>  
 <span data-ttu-id="d4b10-110">使用して、<xref:System.Windows.Forms.MenuStrip>を制御します。</span><span class="sxs-lookup"><span data-stu-id="d4b10-110">Use the <xref:System.Windows.Forms.MenuStrip> control to:</span></span>  
  
-   <span data-ttu-id="d4b10-111">簡単にカスタマイズされた作成をサポートする、一般的に使用されるメニューなどの拡張ユーザー インターフェイスとレイアウト機能、テキストとイメージの並べ替えとアラインメント、ドラッグ アンド ドロップ操作、MDI、オーバーフロー、およびメニュー コマンドにアクセスするのに代替のモード。</span><span class="sxs-lookup"><span data-stu-id="d4b10-111">Create easily customized, commonly employed menus that support advanced user interface and layout features, such as text and image ordering and alignment, drag-and-drop operations, MDI, overflow, and alternate modes of accessing menu commands.</span></span>  
  
-   <span data-ttu-id="d4b10-112">オペレーティング システムの動作と標準的な外観をサポートします。</span><span class="sxs-lookup"><span data-stu-id="d4b10-112">Support the typical appearance and behavior of the operating system.</span></span>  
  
-   <span data-ttu-id="d4b10-113">同様に他のコントロールのイベントを処理するには、すべてのコンテナーと含まれる項目を一貫してイベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="d4b10-113">Handle events consistently for all containers and contained items, in the same way you handle events for other controls.</span></span>  
  
 <span data-ttu-id="d4b10-114">次の表には、いくつか特に重要なプロパティが表示されます。<xref:System.Windows.Forms.MenuStrip>および関連するクラス。</span><span class="sxs-lookup"><span data-stu-id="d4b10-114">The following table shows some particularly important properties of <xref:System.Windows.Forms.MenuStrip> and associated classes.</span></span>  
  
|<span data-ttu-id="d4b10-115">プロパティ</span><span class="sxs-lookup"><span data-stu-id="d4b10-115">Property</span></span>|<span data-ttu-id="d4b10-116">説明</span><span class="sxs-lookup"><span data-stu-id="d4b10-116">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>|<span data-ttu-id="d4b10-117">取得または設定します、 <xref:System.Windows.Forms.ToolStripMenuItem> MDI 子フォームの一覧を表示するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d4b10-117">Gets or sets the <xref:System.Windows.Forms.ToolStripMenuItem> that is used to display a list of MDI child forms.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem.MergeAction%2A?displayProperty=nameWithType>|<span data-ttu-id="d4b10-118">取得または子メニューが MDI アプリケーションで親メニューにマージされる方法を設定します。</span><span class="sxs-lookup"><span data-stu-id="d4b10-118">Gets or sets how child menus are merged with parent menus in MDI applications.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A?displayProperty=nameWithType>|<span data-ttu-id="d4b10-119">取得または MDI アプリケーションでメニュー内でマージされた項目の位置を設定します。</span><span class="sxs-lookup"><span data-stu-id="d4b10-119">Gets or sets the position of a merged item within a menu in MDI applications.</span></span>|  
|<xref:System.Windows.Forms.Form.IsMdiContainer%2A?displayProperty=nameWithType>|<span data-ttu-id="d4b10-120">取得またはフォームが MDI 子フォームのコンテナーであるかどうかを示す値を設定します。</span><span class="sxs-lookup"><span data-stu-id="d4b10-120">Gets or sets a value indicating whether the form is a container for MDI child forms.</span></span>|  
|<xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A>|<span data-ttu-id="d4b10-121">取得または設定のツール ヒントを表示するかどうかを示す値、<xref:System.Windows.Forms.MenuStrip>します。</span><span class="sxs-lookup"><span data-stu-id="d4b10-121">Gets or sets a value indicating whether tool tips are shown for the <xref:System.Windows.Forms.MenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.MenuStrip.CanOverflow%2A>|<span data-ttu-id="d4b10-122"><xref:System.Windows.Forms.MenuStrip> がオーバーフロー機能をサポートするかどうかを示す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="d4b10-122">Gets or sets a value indicating whether the <xref:System.Windows.Forms.MenuStrip> supports overflow functionality.</span></span>|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>|<span data-ttu-id="d4b10-123">取得または設定に関連付けられているショートカット キー、<xref:System.Windows.Forms.ToolStripMenuItem>します。</span><span class="sxs-lookup"><span data-stu-id="d4b10-123">Gets or sets the shortcut keys associated with the <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>|<span data-ttu-id="d4b10-124">関連付けられたショートカット キーをかどうかを示す値を取得または設定、<xref:System.Windows.Forms.ToolStripMenuItem>横に表示する、<xref:System.Windows.Forms.ToolStripMenuItem>します。</span><span class="sxs-lookup"><span data-stu-id="d4b10-124">Gets or sets a value indicating whether the shortcut keys that are associated with the <xref:System.Windows.Forms.ToolStripMenuItem> are displayed next to the <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>|  
  
 <span data-ttu-id="d4b10-125">次の表は、重要な<xref:System.Windows.Forms.MenuStrip>コンパニオン クラス。</span><span class="sxs-lookup"><span data-stu-id="d4b10-125">The following table shows the important <xref:System.Windows.Forms.MenuStrip> companion classes.</span></span>  
  
|<span data-ttu-id="d4b10-126">クラス</span><span class="sxs-lookup"><span data-stu-id="d4b10-126">Class</span></span>|<span data-ttu-id="d4b10-127">説明</span><span class="sxs-lookup"><span data-stu-id="d4b10-127">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|<span data-ttu-id="d4b10-128">表示される選択可能なオプションを表す、<xref:System.Windows.Forms.MenuStrip>または<xref:System.Windows.Forms.ContextMenuStrip>します。</span><span class="sxs-lookup"><span data-stu-id="d4b10-128">Represents a selectable option displayed on a <xref:System.Windows.Forms.MenuStrip> or <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.ContextMenuStrip>|<span data-ttu-id="d4b10-129">ショートカット メニューを表します。</span><span class="sxs-lookup"><span data-stu-id="d4b10-129">Represents a shortcut menu.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDown>|<span data-ttu-id="d4b10-130">ユーザーは、ユーザーがクリックしたときに表示される一覧から 1 つの項目を選択できるようにするコントロール表します、<xref:System.Windows.Forms.ToolStripDropDownButton>または上位レベルのメニュー項目。</span><span class="sxs-lookup"><span data-stu-id="d4b10-130">Represents a control that allows the user to select a single item from a list that is displayed when the user clicks a <xref:System.Windows.Forms.ToolStripDropDownButton> or a higher-level menu item.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|<span data-ttu-id="d4b10-131">派生したコントロールの基本的な機能を提供します<xref:System.Windows.Forms.ToolStripItem>クリックされたときにドロップダウン リストの項目を表示します。</span><span class="sxs-lookup"><span data-stu-id="d4b10-131">Provides basic functionality for controls derived from <xref:System.Windows.Forms.ToolStripItem> that display drop-down items when clicked.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d4b10-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="d4b10-132">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
