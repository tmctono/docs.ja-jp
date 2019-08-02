---
title: MenuStrip コントロールの概要 (Windows フォーム)
ms.date: 03/30/2017
f1_keywords:
- MenuStrip
helpviewer_keywords:
- MenuStrip control [Windows Forms], about MenuStrip control
- menus [Windows Forms], creating
ms.assetid: f45516e5-bf01-4468-b851-d45f4c33c055
ms.openlocfilehash: 46a3a25415db77ee261f5fb1c3bf114b2275a2d4
ms.sourcegitcommit: 8c6426a3d2adff5fbcbe1fed0f28eda718c15351
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2019
ms.locfileid: "68733455"
---
# <a name="menustrip-control-overview-windows-forms"></a><span data-ttu-id="17a0c-102">MenuStrip コントロールの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="17a0c-102">MenuStrip Control Overview (Windows Forms)</span></span>
<span data-ttu-id="17a0c-103">メニューは、共通のテーマによってグループ化されたコマンドを保持することによって、ユーザーに機能を公開します。</span><span class="sxs-lookup"><span data-stu-id="17a0c-103">Menus expose functionality to your users by holding commands that are grouped by a common theme.</span></span>  
  
 <span data-ttu-id="17a0c-104">コントロール<xref:System.Windows.Forms.MenuStrip>は、.NET Framework のバージョン2.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="17a0c-104">The <xref:System.Windows.Forms.MenuStrip> control was introduced in version 2.0 of the .NET Framework.</span></span> <span data-ttu-id="17a0c-105"><xref:System.Windows.Forms.MenuStrip>コントロールを使用すると、Microsoft Office にあるようなメニューを簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="17a0c-105">With the <xref:System.Windows.Forms.MenuStrip> control, you can easily create menus like those found in Microsoft Office.</span></span>  
  
 <span data-ttu-id="17a0c-106">コントロール<xref:System.Windows.Forms.MenuStrip>では、マルチドキュメントインターフェイス (MDI) とメニューのマージ、ツールヒント、およびオーバーフローがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="17a0c-106">The <xref:System.Windows.Forms.MenuStrip> control supports the multiple-document interface (MDI) and menu merging, tool tips, and overflow.</span></span> <span data-ttu-id="17a0c-107">アクセスキー、ショートカットキー、チェックマーク、画像、および区分線を追加することで、メニューの使いやすさと読みやすさを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="17a0c-107">You can enhance the usability and readability of your menus by adding access keys, shortcut keys, check marks, images, and separator bars.</span></span>  
  
 <span data-ttu-id="17a0c-108">コントロールは、コントロール<xref:System.Windows.Forms.MainMenu>に置き換えられ、機能が追加さ<xref:System.Windows.Forms.MainMenu>れます。ただし、コントロールは旧バージョンとの互換性を維持するために残されています。 <xref:System.Windows.Forms.MenuStrip></span><span class="sxs-lookup"><span data-stu-id="17a0c-108">The <xref:System.Windows.Forms.MenuStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.MainMenu> control; however, the <xref:System.Windows.Forms.MainMenu> control is retained for backward compatibility and future use if you choose.</span></span>  
  
## <a name="ways-to-use-the-menustrip-control"></a><span data-ttu-id="17a0c-109">MenuStrip コントロールを使用する方法</span><span class="sxs-lookup"><span data-stu-id="17a0c-109">Ways to Use the MenuStrip Control</span></span>  
 <span data-ttu-id="17a0c-110">コントロールを<xref:System.Windows.Forms.MenuStrip>使用して次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="17a0c-110">Use the <xref:System.Windows.Forms.MenuStrip> control to:</span></span>  
  
- <span data-ttu-id="17a0c-111">テキストとイメージの順序付けと配置、ドラッグアンドドロップ操作、MDI、オーバーフロー、メニューコマンドにアクセスするための代替モードなど、高度なユーザーインターフェイスとレイアウト機能をサポートする、カスタマイズされた、一般的に使用されるメニューを作成します。</span><span class="sxs-lookup"><span data-stu-id="17a0c-111">Create easily customized, commonly employed menus that support advanced user interface and layout features, such as text and image ordering and alignment, drag-and-drop operations, MDI, overflow, and alternate modes of accessing menu commands.</span></span>  
  
- <span data-ttu-id="17a0c-112">オペレーティングシステムの一般的な外観と動作をサポートします。</span><span class="sxs-lookup"><span data-stu-id="17a0c-112">Support the typical appearance and behavior of the operating system.</span></span>  
  
- <span data-ttu-id="17a0c-113">他のコントロールのイベントを処理するのと同じ方法で、すべてのコンテナーと含まれる項目に対して一貫したイベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="17a0c-113">Handle events consistently for all containers and contained items, in the same way you handle events for other controls.</span></span>  
  
 <span data-ttu-id="17a0c-114">次の表は、および関連クラスの<xref:System.Windows.Forms.MenuStrip>いくつかの重要なプロパティを示しています。</span><span class="sxs-lookup"><span data-stu-id="17a0c-114">The following table shows some particularly important properties of <xref:System.Windows.Forms.MenuStrip> and associated classes.</span></span>  
  
|<span data-ttu-id="17a0c-115">プロパティ</span><span class="sxs-lookup"><span data-stu-id="17a0c-115">Property</span></span>|<span data-ttu-id="17a0c-116">説明</span><span class="sxs-lookup"><span data-stu-id="17a0c-116">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>|<span data-ttu-id="17a0c-117">MDI 子フォームの<xref:System.Windows.Forms.ToolStripMenuItem>一覧を表示するために使用されるを取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="17a0c-117">Gets or sets the <xref:System.Windows.Forms.ToolStripMenuItem> that is used to display a list of MDI child forms.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem.MergeAction%2A?displayProperty=nameWithType>|<span data-ttu-id="17a0c-118">MDI アプリケーションの親メニューと子メニューをマージする方法を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="17a0c-118">Gets or sets how child menus are merged with parent menus in MDI applications.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A?displayProperty=nameWithType>|<span data-ttu-id="17a0c-119">MDI アプリケーションのメニュー内のマージされた項目の位置を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="17a0c-119">Gets or sets the position of a merged item within a menu in MDI applications.</span></span>|  
|<xref:System.Windows.Forms.Form.IsMdiContainer%2A?displayProperty=nameWithType>|<span data-ttu-id="17a0c-120">フォームが MDI 子フォームのコンテナーかどうかを示す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="17a0c-120">Gets or sets a value indicating whether the form is a container for MDI child forms.</span></span>|  
|<xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A>|<span data-ttu-id="17a0c-121">にツールヒントを表示<xref:System.Windows.Forms.MenuStrip>するかどうかを示す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="17a0c-121">Gets or sets a value indicating whether tool tips are shown for the <xref:System.Windows.Forms.MenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.MenuStrip.CanOverflow%2A>|<span data-ttu-id="17a0c-122"><xref:System.Windows.Forms.MenuStrip> がオーバーフロー機能をサポートするかどうかを示す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="17a0c-122">Gets or sets a value indicating whether the <xref:System.Windows.Forms.MenuStrip> supports overflow functionality.</span></span>|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>|<span data-ttu-id="17a0c-123">に関連付けられているショートカット<xref:System.Windows.Forms.ToolStripMenuItem>キーを取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="17a0c-123">Gets or sets the shortcut keys associated with the <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>|<span data-ttu-id="17a0c-124">に関連付けら<xref:System.Windows.Forms.ToolStripMenuItem>れているショートカットキーをの<xref:System.Windows.Forms.ToolStripMenuItem>横に表示するかどうかを示す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="17a0c-124">Gets or sets a value indicating whether the shortcut keys that are associated with the <xref:System.Windows.Forms.ToolStripMenuItem> are displayed next to the <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>|  
  
 <span data-ttu-id="17a0c-125">次の表は、重要<xref:System.Windows.Forms.MenuStrip>な関連クラスを示しています。</span><span class="sxs-lookup"><span data-stu-id="17a0c-125">The following table shows the important <xref:System.Windows.Forms.MenuStrip> companion classes.</span></span>  
  
|<span data-ttu-id="17a0c-126">クラス</span><span class="sxs-lookup"><span data-stu-id="17a0c-126">Class</span></span>|<span data-ttu-id="17a0c-127">説明</span><span class="sxs-lookup"><span data-stu-id="17a0c-127">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|<span data-ttu-id="17a0c-128"><xref:System.Windows.Forms.MenuStrip>または<xref:System.Windows.Forms.ContextMenuStrip>に表示される選択可能なオプションを表します。</span><span class="sxs-lookup"><span data-stu-id="17a0c-128">Represents a selectable option displayed on a <xref:System.Windows.Forms.MenuStrip> or <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.ContextMenuStrip>|<span data-ttu-id="17a0c-129">ショートカット メニューを表します。</span><span class="sxs-lookup"><span data-stu-id="17a0c-129">Represents a shortcut menu.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDown>|<span data-ttu-id="17a0c-130">ユーザーが<xref:System.Windows.Forms.ToolStripDropDownButton>または上位レベルのメニュー項目をクリックしたときに表示される一覧から1つの項目を選択できるようにするコントロールを表します。</span><span class="sxs-lookup"><span data-stu-id="17a0c-130">Represents a control that allows the user to select a single item from a list that is displayed when the user clicks a <xref:System.Windows.Forms.ToolStripDropDownButton> or a higher-level menu item.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|<span data-ttu-id="17a0c-131">クリックしたときに表示さ<xref:System.Windows.Forms.ToolStripItem>れるドロップダウン項目から派生したコントロールの基本機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="17a0c-131">Provides basic functionality for controls derived from <xref:System.Windows.Forms.ToolStripItem> that display drop-down items when clicked.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="17a0c-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="17a0c-132">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
