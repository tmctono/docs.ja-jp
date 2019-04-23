---
title: ListView コントロール (Windows フォーム)
ms.date: 03/30/2017
helpviewer_keywords:
- lists
- checked list items [Windows Forms], Windows Forms controls
- user interface [Windows Forms], creating
- lists [Windows Forms], items with icons
- icons [Windows Forms], listing with items
- list views
- ListView control [Windows Forms]
- list controls [Windows Forms], List view
ms.assetid: 9f71cf5c-82da-488a-a04e-ef52c0817187
ms.openlocfilehash: d826fe0a64ad226db62e01259b0466f7f495f8e0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59200312"
---
# <a name="listview-control-windows-forms"></a><span data-ttu-id="7ec21-102">ListView コントロール (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="7ec21-102">ListView Control (Windows Forms)</span></span>
<span data-ttu-id="7ec21-103">Windows フォーム `ListView` コントロールにはアイコン表示で項目の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7ec21-103">The Windows Forms `ListView` control displays a list of items with icons.</span></span> <span data-ttu-id="7ec21-104">リスト ビューを使用すると、Windows エクスプローラーの右側のペインのようなユーザー インターフェイスを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="7ec21-104">You can use a list view to create a user interface like the right pane of Windows Explorer.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7ec21-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7ec21-105">In This Section</span></span>  
 [<span data-ttu-id="7ec21-106">ListView コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="7ec21-106">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)  
 <span data-ttu-id="7ec21-107">このコントロールの用途、主な機能、およびプロパティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7ec21-107">Describes this control and its key features and properties.</span></span>  
  
 [<span data-ttu-id="7ec21-108">方法: Windows フォーム ListView コントロールで項目追加および削除</span><span class="sxs-lookup"><span data-stu-id="7ec21-108">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)  
 <span data-ttu-id="7ec21-109">リスト ビューから項目を追加または削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7ec21-109">Describes how to add or remove items from a list view.</span></span>  
  
 [<span data-ttu-id="7ec21-110">方法: Windows フォーム ListView コントロールに列を追加します。</span><span class="sxs-lookup"><span data-stu-id="7ec21-110">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)  
 <span data-ttu-id="7ec21-111">各リスト項目に関する情報を表示するために列を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7ec21-111">Describes how to create columns in order to display information about each list item.</span></span>  
  
 [<span data-ttu-id="7ec21-112">方法: Windows フォーム ListView コントロールのアイコンを表示します。</span><span class="sxs-lookup"><span data-stu-id="7ec21-112">How to: Display Icons for the Windows Forms ListView Control</span></span>](how-to-display-icons-for-the-windows-forms-listview-control.md)  
 <span data-ttu-id="7ec21-113">大きいアイコンまたは小さいアイコンを表示するための適切なイメージ リストとリスト ビューを関連付ける方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7ec21-113">Describes how to associate a list view with an appropriate image list for displaying large or small icons.</span></span>  
  
 [<span data-ttu-id="7ec21-114">方法: Windows フォーム ListView コントロールでの列にサブ項目を表示</span><span class="sxs-lookup"><span data-stu-id="7ec21-114">How to: Display Subitems in Columns with the Windows Forms ListView Control</span></span>](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)  
 <span data-ttu-id="7ec21-115">列の各リスト項目に関する情報を表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7ec21-115">Describes how to display information about each list item in columns.</span></span>  
  
 [<span data-ttu-id="7ec21-116">方法: Windows フォーム ListView コントロールで項目を選択します。</span><span class="sxs-lookup"><span data-stu-id="7ec21-116">How to: Select an Item in the Windows Forms ListView Control</span></span>](how-to-select-an-item-in-the-windows-forms-listview-control.md)  
 <span data-ttu-id="7ec21-117">プログラムによって項目を選択する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7ec21-117">Describes how to programmatically select an item.</span></span>  
  
 [<span data-ttu-id="7ec21-118">方法: Windows フォーム ListView コントロールに項目をグループ化</span><span class="sxs-lookup"><span data-stu-id="7ec21-118">How to: Group Items in a Windows Forms ListView Control</span></span>](how-to-group-items-in-a-windows-forms-listview-control.md)  
 <span data-ttu-id="7ec21-119">カテゴリ別表示用のグループを作成して各グループに項目を割り当てる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7ec21-119">Describes how to create groups for categorized display and how to assign items to each group.</span></span>  
  
 <span data-ttu-id="7ec21-120">この機能は、[!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="7ec21-120">This feature is available only for [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)].</span></span>  
  
 [<span data-ttu-id="7ec21-121">方法: Windows フォーム ListView コントロールに並べて表示ビューを有効にします。</span><span class="sxs-lookup"><span data-stu-id="7ec21-121">How to: Enable Tile View in a Windows Forms ListView Control</span></span>](how-to-enable-tile-view-in-a-windows-forms-listview-control.md)  
 <span data-ttu-id="7ec21-122">大きいアイコンと複数行のテキストで構成される項目のタイル表示の方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7ec21-122">Describes how to display items as tiles, each of which is comprised of a large icon and multiple lines of text.</span></span>  
  
 <span data-ttu-id="7ec21-123">この機能は、[!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="7ec21-123">This feature is available only for [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)].</span></span>  
  
 [<span data-ttu-id="7ec21-124">方法: Windows フォーム ListView コントロールに挿入マークを表示します。</span><span class="sxs-lookup"><span data-stu-id="7ec21-124">How to: Display an Insertion Mark in a Windows Forms ListView Control</span></span>](how-to-display-an-insertion-mark-in-a-windows-forms-listview-control.md)  
 <span data-ttu-id="7ec21-125">挿入マークがマウス ポインターの位置ごとにドロップする場所を示す、ドラッグ アンド ドロップ操作のためのユーザー フィードバックを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7ec21-125">Describes how to implement user-feedback for drag-and-drop operations in which an insertion mark indicates the drop location for each mouse-pointer position.</span></span>  
  
 <span data-ttu-id="7ec21-126">この機能は、[!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="7ec21-126">This feature is available only for [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)].</span></span>  
  
 [<span data-ttu-id="7ec21-127">方法: ListView コントロールに検索機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="7ec21-127">How to: Add Search Capabilities to a ListView Control</span></span>](how-to-add-search-capabilities-to-a-listview-control.md)  
 <span data-ttu-id="7ec21-128">プログラムでいずれかのテキストの検索または画面座標を使用してアイテムを検索する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7ec21-128">Describes how to programmatically find an item using either text search or screen coordinates.</span></span>  
  
-   [<span data-ttu-id="7ec21-129">方法: デザイナーを使用して Windows フォーム ListView コントロールの並べて表示ビューを有効にします。</span><span class="sxs-lookup"><span data-stu-id="7ec21-129">How to: Enable Tile View in a Windows Forms ListView Control Using the Designer</span></span>](enable-tile-view-in-a-wf-listview-control-using-the-designer.md)  
  
-   [<span data-ttu-id="7ec21-130">方法: デザイナーを使用して Windows フォーム ListView コントロールで項目追加および削除</span><span class="sxs-lookup"><span data-stu-id="7ec21-130">How to: Add and Remove Items with the Windows Forms ListView Control Using the Designer</span></span>](add-and-remove-items-with-wf-listview-control-using-the-designer.md)  
  
-   [<span data-ttu-id="7ec21-131">方法: デザイナーを使用して Windows フォーム ListView コントロールに列を追加します。</span><span class="sxs-lookup"><span data-stu-id="7ec21-131">How to: Add Columns to the Windows Forms ListView Control Using the Designer</span></span>](how-to-add-columns-to-the-windows-forms-listview-control-using-the-designer.md)  
  
-   [<span data-ttu-id="7ec21-132">方法: デザイナーを使用して Windows フォーム ListView コントロールの項目をグループ化</span><span class="sxs-lookup"><span data-stu-id="7ec21-132">How to: Group Items in a Windows Forms ListView Control Using the Designer</span></span>](how-to-group-items-in-a-windows-forms-listview-control-using-the-designer.md)  
  
-   [<span data-ttu-id="7ec21-133">チュートリアル: ListView とデザイナーを使用して TreeView コントロールでエクスプ ローラー スタイルのインターフェイスを作成します。</span><span class="sxs-lookup"><span data-stu-id="7ec21-133">Walkthrough: Creating an Explorer Style Interface with the ListView and TreeView Controls Using the Designer</span></span>](creating-an-explorer-style-interface-with-the-listview-and-treeview.md)  
  
## <a name="reference"></a><span data-ttu-id="7ec21-134">参照</span><span class="sxs-lookup"><span data-stu-id="7ec21-134">Reference</span></span>  
 <span data-ttu-id="7ec21-135"><xref:System.Windows.Forms.ListView> クラス</span><span class="sxs-lookup"><span data-stu-id="7ec21-135"><xref:System.Windows.Forms.ListView> class</span></span>  
 <span data-ttu-id="7ec21-136">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="7ec21-136">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7ec21-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="7ec21-137">Related Sections</span></span>  
 [<span data-ttu-id="7ec21-138">方法: TreeView コントロールまたは ListView コントロール (Windows フォーム) にカスタム情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="7ec21-138">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)  
 <span data-ttu-id="7ec21-139">リスト ビュー内のアイテムまたはツリー ビュー内のノードから継承して、必要なフィールド、メソッド、またはコンストラクターを追加するための手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="7ec21-139">Describes how to inherit from an item in a list view or a node in a tree view in order to add any fields, methods, or constructors you need.</span></span>  
  
 [<span data-ttu-id="7ec21-140">ImageList コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7ec21-140">ImageList Component</span></span>](imagelist-component-windows-forms.md)  
 <span data-ttu-id="7ec21-141">イメージ リストの用途、主な機能、およびプロパティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7ec21-141">Explains what an image list is and its key features and properties.</span></span>  
  
 [<span data-ttu-id="7ec21-142">方法: Windows フォームでマルチペイン ユーザー インターフェイスを作成します。</span><span class="sxs-lookup"><span data-stu-id="7ec21-142">How to: Create a Multipane User Interface with Windows Forms</span></span>](how-to-create-a-multipane-user-interface-with-windows-forms.md)  
 <span data-ttu-id="7ec21-143">複数のペインで Windows フォームのレイアウトを設定するための方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="7ec21-143">Gives instructions for laying out a Windows Form with multiple panes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ec21-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="7ec21-144">See also</span></span>

- [<span data-ttu-id="7ec21-145">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="7ec21-145">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
