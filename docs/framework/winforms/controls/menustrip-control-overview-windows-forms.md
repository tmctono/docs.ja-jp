---
title: MenuStrip コントロールの概要
ms.date: 03/30/2017
f1_keywords:
- MenuStrip
helpviewer_keywords:
- MenuStrip control [Windows Forms], about MenuStrip control
- menus [Windows Forms], creating
ms.assetid: f45516e5-bf01-4468-b851-d45f4c33c055
ms.openlocfilehash: a536d13cb7be3f4e4e4a085e1a4da1b0899b3a0c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734470"
---
# <a name="menustrip-control-overview-windows-forms"></a><span data-ttu-id="b934b-102">MenuStrip コントロールの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="b934b-102">MenuStrip Control Overview (Windows Forms)</span></span>
<span data-ttu-id="b934b-103">メニューは、共通のテーマによってグループ化されたコマンドを保持することによって、ユーザーに機能を公開します。</span><span class="sxs-lookup"><span data-stu-id="b934b-103">Menus expose functionality to your users by holding commands that are grouped by a common theme.</span></span>  
  
 <span data-ttu-id="b934b-104"><xref:System.Windows.Forms.MenuStrip> コントロールは、.NET Framework のバージョン2.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b934b-104">The <xref:System.Windows.Forms.MenuStrip> control was introduced in version 2.0 of the .NET Framework.</span></span> <span data-ttu-id="b934b-105"><xref:System.Windows.Forms.MenuStrip> コントロールを使用すると、Microsoft Office にあるようなメニューを簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="b934b-105">With the <xref:System.Windows.Forms.MenuStrip> control, you can easily create menus like those found in Microsoft Office.</span></span>  
  
 <span data-ttu-id="b934b-106"><xref:System.Windows.Forms.MenuStrip> コントロールでは、マルチドキュメントインターフェイス (MDI) とメニューのマージ、ツールヒント、およびオーバーフローがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b934b-106">The <xref:System.Windows.Forms.MenuStrip> control supports the multiple-document interface (MDI) and menu merging, tool tips, and overflow.</span></span> <span data-ttu-id="b934b-107">アクセスキー、ショートカットキー、チェックマーク、画像、および区分線を追加することで、メニューの使いやすさと読みやすさを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="b934b-107">You can enhance the usability and readability of your menus by adding access keys, shortcut keys, check marks, images, and separator bars.</span></span>  
  
 <span data-ttu-id="b934b-108"><xref:System.Windows.Forms.MenuStrip> コントロールは、<xref:System.Windows.Forms.MainMenu> コントロールに置き換えられ、機能が追加されます。ただし、<xref:System.Windows.Forms.MainMenu> コントロールは、旧バージョンとの互換性を維持するために残されています。</span><span class="sxs-lookup"><span data-stu-id="b934b-108">The <xref:System.Windows.Forms.MenuStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.MainMenu> control; however, the <xref:System.Windows.Forms.MainMenu> control is retained for backward compatibility and future use if you choose.</span></span>  
  
## <a name="ways-to-use-the-menustrip-control"></a><span data-ttu-id="b934b-109">MenuStrip コントロールを使用する方法</span><span class="sxs-lookup"><span data-stu-id="b934b-109">Ways to Use the MenuStrip Control</span></span>  
 <span data-ttu-id="b934b-110"><xref:System.Windows.Forms.MenuStrip> コントロールを使用して次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b934b-110">Use the <xref:System.Windows.Forms.MenuStrip> control to:</span></span>  
  
- <span data-ttu-id="b934b-111">テキストとイメージの順序付けと配置、ドラッグアンドドロップ操作、MDI、オーバーフロー、メニューコマンドにアクセスするための代替モードなど、高度なユーザーインターフェイスとレイアウト機能をサポートする、カスタマイズされた、一般的に使用されるメニューを作成します。</span><span class="sxs-lookup"><span data-stu-id="b934b-111">Create easily customized, commonly employed menus that support advanced user interface and layout features, such as text and image ordering and alignment, drag-and-drop operations, MDI, overflow, and alternate modes of accessing menu commands.</span></span>  
  
- <span data-ttu-id="b934b-112">オペレーティングシステムの一般的な外観と動作をサポートします。</span><span class="sxs-lookup"><span data-stu-id="b934b-112">Support the typical appearance and behavior of the operating system.</span></span>  
  
- <span data-ttu-id="b934b-113">他のコントロールのイベントを処理するのと同じ方法で、すべてのコンテナーと含まれる項目に対して一貫したイベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="b934b-113">Handle events consistently for all containers and contained items, in the same way you handle events for other controls.</span></span>  
  
 <span data-ttu-id="b934b-114">次の表は、<xref:System.Windows.Forms.MenuStrip> と関連クラスのいくつかの重要なプロパティを示しています。</span><span class="sxs-lookup"><span data-stu-id="b934b-114">The following table shows some particularly important properties of <xref:System.Windows.Forms.MenuStrip> and associated classes.</span></span>  
  
|<span data-ttu-id="b934b-115">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b934b-115">Property</span></span>|<span data-ttu-id="b934b-116">[説明]</span><span class="sxs-lookup"><span data-stu-id="b934b-116">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>|<span data-ttu-id="b934b-117">MDI 子フォームの一覧を表示するために使用される <xref:System.Windows.Forms.ToolStripMenuItem> を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="b934b-117">Gets or sets the <xref:System.Windows.Forms.ToolStripMenuItem> that is used to display a list of MDI child forms.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem.MergeAction%2A?displayProperty=nameWithType>|<span data-ttu-id="b934b-118">MDI アプリケーションの親メニューと子メニューをマージする方法を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="b934b-118">Gets or sets how child menus are merged with parent menus in MDI applications.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A?displayProperty=nameWithType>|<span data-ttu-id="b934b-119">MDI アプリケーションのメニュー内のマージされた項目の位置を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="b934b-119">Gets or sets the position of a merged item within a menu in MDI applications.</span></span>|  
|<xref:System.Windows.Forms.Form.IsMdiContainer%2A?displayProperty=nameWithType>|<span data-ttu-id="b934b-120">フォームが MDI 子フォームのコンテナーかどうかを示す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="b934b-120">Gets or sets a value indicating whether the form is a container for MDI child forms.</span></span>|  
|<xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A>|<span data-ttu-id="b934b-121"><xref:System.Windows.Forms.MenuStrip>にツールヒントを表示するかどうかを示す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="b934b-121">Gets or sets a value indicating whether tool tips are shown for the <xref:System.Windows.Forms.MenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.MenuStrip.CanOverflow%2A>|<span data-ttu-id="b934b-122"><xref:System.Windows.Forms.MenuStrip> がオーバーフロー機能をサポートするかどうかを示す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="b934b-122">Gets or sets a value indicating whether the <xref:System.Windows.Forms.MenuStrip> supports overflow functionality.</span></span>|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>|<span data-ttu-id="b934b-123"><xref:System.Windows.Forms.ToolStripMenuItem> に関連付けられたショートカット キーを取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="b934b-123">Gets or sets the shortcut keys associated with the <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>|<span data-ttu-id="b934b-124"><xref:System.Windows.Forms.ToolStripMenuItem> に関連付けられたショートカット キーを <xref:System.Windows.Forms.ToolStripMenuItem> の横に表示するかどうかを示す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="b934b-124">Gets or sets a value indicating whether the shortcut keys that are associated with the <xref:System.Windows.Forms.ToolStripMenuItem> are displayed next to the <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>|  
  
 <span data-ttu-id="b934b-125">次の表は、重要な <xref:System.Windows.Forms.MenuStrip> コンパニオンクラスを示しています。</span><span class="sxs-lookup"><span data-stu-id="b934b-125">The following table shows the important <xref:System.Windows.Forms.MenuStrip> companion classes.</span></span>  
  
|<span data-ttu-id="b934b-126">クラス</span><span class="sxs-lookup"><span data-stu-id="b934b-126">Class</span></span>|<span data-ttu-id="b934b-127">[説明]</span><span class="sxs-lookup"><span data-stu-id="b934b-127">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|<span data-ttu-id="b934b-128"><xref:System.Windows.Forms.MenuStrip> または <xref:System.Windows.Forms.ContextMenuStrip> に表示される選択可能なオプションを表します。</span><span class="sxs-lookup"><span data-stu-id="b934b-128">Represents a selectable option displayed on a <xref:System.Windows.Forms.MenuStrip> or <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.ContextMenuStrip>|<span data-ttu-id="b934b-129">ショートカット メニューを表します。</span><span class="sxs-lookup"><span data-stu-id="b934b-129">Represents a shortcut menu.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDown>|<span data-ttu-id="b934b-130">ユーザーが <xref:System.Windows.Forms.ToolStripDropDownButton> または上位レベルのメニュー項目をクリックしたときに表示される一覧から1つの項目を選択できるようにするコントロールを表します。</span><span class="sxs-lookup"><span data-stu-id="b934b-130">Represents a control that allows the user to select a single item from a list that is displayed when the user clicks a <xref:System.Windows.Forms.ToolStripDropDownButton> or a higher-level menu item.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|<span data-ttu-id="b934b-131">クリックしたときにドロップダウン項目を表示する <xref:System.Windows.Forms.ToolStripItem> から派生したコントロールの基本機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="b934b-131">Provides basic functionality for controls derived from <xref:System.Windows.Forms.ToolStripItem> that display drop-down items when clicked.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b934b-132">参照</span><span class="sxs-lookup"><span data-stu-id="b934b-132">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
