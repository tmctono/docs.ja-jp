---
title: ListView コントロールに列を追加する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
- list views [Windows Forms], adding columns
ms.assetid: 79174274-12ee-4a5d-80db-6ec02976d010
ms.openlocfilehash: dd438ffbadddfc37ec9eb15e59a908bb58472a45
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744582"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control"></a><span data-ttu-id="ed04e-102">方法 : Windows フォーム ListView コントロールに列を追加する</span><span class="sxs-lookup"><span data-stu-id="ed04e-102">How to: Add Columns to the Windows Forms ListView Control</span></span>
<span data-ttu-id="ed04e-103">詳細ビューでは、<xref:System.Windows.Forms.ListView> コントロールは、各リスト項目に対して複数の列を表示できます。</span><span class="sxs-lookup"><span data-stu-id="ed04e-103">In the Details view, the <xref:System.Windows.Forms.ListView> control can display multiple columns for each list item.</span></span> <span data-ttu-id="ed04e-104">列を使用して、各リスト項目に関するいくつかの種類の情報をユーザーに表示できます。</span><span class="sxs-lookup"><span data-stu-id="ed04e-104">You can use the columns to display to the user several types of information about each list item.</span></span> <span data-ttu-id="ed04e-105">たとえば、ファイルの一覧には、ファイル名、ファイルの種類、サイズ、ファイルが最後に変更された日付が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ed04e-105">For example, a list of files could display the file name, file type, size, and date the file was last modified.</span></span> <span data-ttu-id="ed04e-106">作成後に列を設定する方法の詳細については、「[方法: Windows フォーム ListView コントロールを使用して列にサブ項目を表示する](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed04e-106">For information about populating the columns after they are created, see [How to: Display Subitems in Columns with the Windows Forms ListView Control](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).</span></span>  
  
### <a name="to-add-columns-programmatically"></a><span data-ttu-id="ed04e-107">プログラムによって列を追加するには</span><span class="sxs-lookup"><span data-stu-id="ed04e-107">To add columns programmatically</span></span>  
  
1. <span data-ttu-id="ed04e-108">コントロールの <xref:System.Windows.Forms.ListView.View%2A> プロパティを <xref:System.Windows.Forms.View.Details>に設定します。</span><span class="sxs-lookup"><span data-stu-id="ed04e-108">Set the control's <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Details>.</span></span>  
  
2. <span data-ttu-id="ed04e-109">リストビューの <xref:System.Windows.Forms.ListView.Columns%2A> プロパティの <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="ed04e-109">Use the <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> method of the list view's <xref:System.Windows.Forms.ListView.Columns%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="ed04e-110">参照</span><span class="sxs-lookup"><span data-stu-id="ed04e-110">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- [<span data-ttu-id="ed04e-111">ListView コントロール</span><span class="sxs-lookup"><span data-stu-id="ed04e-111">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="ed04e-112">ListView コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="ed04e-112">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
