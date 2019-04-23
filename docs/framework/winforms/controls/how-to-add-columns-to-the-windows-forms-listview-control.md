---
title: '方法: Windows フォーム ListView コントロールに列を追加する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
- list views [Windows Forms], adding columns
ms.assetid: 79174274-12ee-4a5d-80db-6ec02976d010
ms.openlocfilehash: 5c87d43513f2125945145445c61f689cdd9d2aaf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59345743"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control"></a><span data-ttu-id="d43c4-102">方法: Windows フォーム ListView コントロールに列を追加する</span><span class="sxs-lookup"><span data-stu-id="d43c4-102">How to: Add Columns to the Windows Forms ListView Control</span></span>
<span data-ttu-id="d43c4-103">詳細ビューで、<xref:System.Windows.Forms.ListView>コントロールは、各リスト項目の複数の列を表示できます。</span><span class="sxs-lookup"><span data-stu-id="d43c4-103">In the Details view, the <xref:System.Windows.Forms.ListView> control can display multiple columns for each list item.</span></span> <span data-ttu-id="d43c4-104">いくつかの種類の各リスト項目に関する情報をユーザーに表示するのに列を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="d43c4-104">You can use the columns to display to the user several types of information about each list item.</span></span> <span data-ttu-id="d43c4-105">たとえば、ファイルの一覧には、ファイル名、ファイルの種類、サイズ、およびファイルの最終更新日を表示できます。</span><span class="sxs-lookup"><span data-stu-id="d43c4-105">For example, a list of files could display the file name, file type, size, and date the file was last modified.</span></span> <span data-ttu-id="d43c4-106">作成した後、列の設定方法の詳細については、次を参照してください。[方法。Windows での列にサブ項目を表示フォーム ListView コントロール](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)します。</span><span class="sxs-lookup"><span data-stu-id="d43c4-106">For information about populating the columns after they are created, see [How to: Display Subitems in Columns with the Windows Forms ListView Control](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).</span></span>  
  
### <a name="to-add-columns-programmatically"></a><span data-ttu-id="d43c4-107">プログラムで列を追加するには</span><span class="sxs-lookup"><span data-stu-id="d43c4-107">To add columns programmatically</span></span>  
  
1. <span data-ttu-id="d43c4-108">コントロールの設定<xref:System.Windows.Forms.ListView.View%2A>プロパティを<xref:System.Windows.Forms.View.Details>します。</span><span class="sxs-lookup"><span data-stu-id="d43c4-108">Set the control's <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Details>.</span></span>  
  
2. <span data-ttu-id="d43c4-109">使用して、<xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A>メソッドのリスト ビューの<xref:System.Windows.Forms.ListView.Columns%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="d43c4-109">Use the <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> method of the list view's <xref:System.Windows.Forms.ListView.Columns%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="d43c4-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="d43c4-110">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- [<span data-ttu-id="d43c4-111">ListView コントロール</span><span class="sxs-lookup"><span data-stu-id="d43c4-111">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="d43c4-112">ListView コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="d43c4-112">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
