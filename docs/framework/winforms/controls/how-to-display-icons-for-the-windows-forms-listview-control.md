---
title: '方法: Windows フォーム ListView コントロールのアイコンを表示する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], displaying icons
- icons [Windows Forms], displaying for ListView controls
- lists [Windows Forms], displaying icons
- ImageList component [Windows Forms], with ListView control
- list views [Windows Forms], displaying icons
ms.assetid: 9d577542-8595-429b-99e5-078770ec9d35
ms.openlocfilehash: 80a827a88ac92008c7fe2a642d1d4b59a18f89da
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2019
ms.locfileid: "65880403"
---
# <a name="how-to-display-icons-for-the-windows-forms-listview-control"></a><span data-ttu-id="ac483-102">方法: Windows フォーム ListView コントロールのアイコンを表示する</span><span class="sxs-lookup"><span data-stu-id="ac483-102">How to: Display Icons for the Windows Forms ListView Control</span></span>
<span data-ttu-id="ac483-103">Windows フォーム<xref:System.Windows.Forms.ListView>コントロールは、次の 3 つのイメージ リストのアイコンを表示できます。</span><span class="sxs-lookup"><span data-stu-id="ac483-103">The Windows Forms <xref:System.Windows.Forms.ListView> control can display icons from three image lists.</span></span> <span data-ttu-id="ac483-104">リスト、詳細、および SmallIcon ビューが指定されているイメージの一覧からイメージを表示、<xref:System.Windows.Forms.ListView.SmallImageList%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="ac483-104">The List, Details, and SmallIcon views display images from the image list specified in the <xref:System.Windows.Forms.ListView.SmallImageList%2A> property.</span></span> <span data-ttu-id="ac483-105">LargeIcon ビューが指定されているイメージの一覧の画像を表示、<xref:System.Windows.Forms.ListView.LargeImageList%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="ac483-105">The LargeIcon view displays images from the image list specified in the <xref:System.Windows.Forms.ListView.LargeImageList%2A> property.</span></span> <span data-ttu-id="ac483-106">リスト ビューは、追加で設定アイコンのセットを表示できます、<xref:System.Windows.Forms.ListView.StateImageList%2A>大きいアイコンまたは小さいアイコンの横にあるプロパティ。</span><span class="sxs-lookup"><span data-stu-id="ac483-106">A list view can also display an additional set of icons, set in the <xref:System.Windows.Forms.ListView.StateImageList%2A> property, next to the large or small icons.</span></span> <span data-ttu-id="ac483-107">イメージ リストの詳細については、次を参照してください。 [ImageList コンポーネント](imagelist-component-windows-forms.md)と[方法。追加または削除のイメージで、Windows フォームの ImageList コンポーネント](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)します。</span><span class="sxs-lookup"><span data-stu-id="ac483-107">For more information about image lists, see [ImageList Component](imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
### <a name="to-display-images-in-a-list-view"></a><span data-ttu-id="ac483-108">リスト ビューでイメージを表示するには</span><span class="sxs-lookup"><span data-stu-id="ac483-108">To display images in a list view</span></span>  
  
1. <span data-ttu-id="ac483-109">適切なプロパティを設定 —<xref:System.Windows.Forms.ListView.SmallImageList%2A>、 <xref:System.Windows.Forms.ListView.LargeImageList%2A>、または<xref:System.Windows.Forms.ListView.StateImageList%2A>— 既存<xref:System.Windows.Forms.ImageList>コンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="ac483-109">Set the appropriate property—<xref:System.Windows.Forms.ListView.SmallImageList%2A>, <xref:System.Windows.Forms.ListView.LargeImageList%2A>, or <xref:System.Windows.Forms.ListView.StateImageList%2A>—to the existing <xref:System.Windows.Forms.ImageList> component you wish to use.</span></span>  
  
     <span data-ttu-id="ac483-110">デザイナーの [プロパティ] ウィンドウまたはコードでは、これらのプロパティを設定できます。</span><span class="sxs-lookup"><span data-stu-id="ac483-110">These properties can be set in the designer with the Properties window, or in code.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#41)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#41)]  
  
2. <span data-ttu-id="ac483-111">設定、<xref:System.Windows.Forms.ListViewItem.ImageIndex%2A>または<xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A>アイコンが関連付けられている各リスト項目のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="ac483-111">Set the <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> or <xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A> property for each list item that has an associated icon.</span></span>  
  
     <span data-ttu-id="ac483-112">コードでは、または、これらのプロパティを設定できる、 **ListViewItem コレクション エディター**します。</span><span class="sxs-lookup"><span data-stu-id="ac483-112">These properties can be set in code, or within the **ListViewItem Collection Editor**.</span></span> <span data-ttu-id="ac483-113">開くには、 **ListViewItem コレクション エディター**、省略記号ボタンをクリックします (![. Visual Studio の [プロパティ] ウィンドウで、省略記号ボタン (…)](./media/visual-studio-ellipsis-button.png)) 横に、<xref:System.Windows.Forms.ListView.Items%2A>プロパティを**プロパティ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="ac483-113">To open the **ListViewItem Collection Editor**, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.ListView.Items%2A> property on the **Properties** window.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#42)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#42)]  
  
## <a name="see-also"></a><span data-ttu-id="ac483-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="ac483-114">See also</span></span>

- [<span data-ttu-id="ac483-115">ListView コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="ac483-115">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="ac483-116">方法: Windows フォーム ListView コントロールで項目追加および削除</span><span class="sxs-lookup"><span data-stu-id="ac483-116">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="ac483-117">方法: Windows フォーム ListView コントロールに列を追加します。</span><span class="sxs-lookup"><span data-stu-id="ac483-117">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [<span data-ttu-id="ac483-118">方法: TreeView コントロールまたは ListView コントロール (Windows フォーム) にカスタム情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="ac483-118">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [<span data-ttu-id="ac483-119">ImageList コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ac483-119">ImageList Component</span></span>](imagelist-component-windows-forms.md)
