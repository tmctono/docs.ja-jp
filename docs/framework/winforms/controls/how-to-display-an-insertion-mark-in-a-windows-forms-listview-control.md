---
title: '方法: Windows フォーム ListView コントロールに挿入マークを表示する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ListView control [Windows Forms], drag operations
- graphics [Windows Forms], insertion marks
- drop and drag [Windows Forms], insertion marks
- insertion marks
ms.assetid: 88d0a15b-25fd-4dc3-a685-297351311940
ms.openlocfilehash: f5de00fd41b24fc1a7f1ff4484c3a126e98952a1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967833"
---
# <a name="how-to-display-an-insertion-mark-in-a-windows-forms-listview-control"></a><span data-ttu-id="99598-102">方法: Windows フォーム ListView コントロールに挿入マークを表示する</span><span class="sxs-lookup"><span data-stu-id="99598-102">How to: Display an Insertion Mark in a Windows Forms ListView Control</span></span>
<span data-ttu-id="99598-103"><xref:System.Windows.Forms.ListView> コントロールの挿入マークは、ドラッグされた項目の挿入先となるポイントをユーザーに表示します。</span><span class="sxs-lookup"><span data-stu-id="99598-103">The insertion mark in the <xref:System.Windows.Forms.ListView> control shows users the point where dragged items will be inserted.</span></span> <span data-ttu-id="99598-104">ユーザーが項目をその他の 2 つの項目の間のポイントにドラッグすると、項目の予期される新しい場所に挿入マークが表示されます。</span><span class="sxs-lookup"><span data-stu-id="99598-104">When a user drags an item to a point between two other items, the insertion mark shows the item's expected new location.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="99598-105">挿入マーク機能は、アプリケーションから <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> メソッドを呼び出した場合に、[!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="99598-105">The insertion mark feature is available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="99598-106">以前のオペレーティング システムでは、挿入マークに関連するすべてのコードは効果がなく、挿入マークは表示されません。</span><span class="sxs-lookup"><span data-stu-id="99598-106">On earlier operating systems, any code relating to the insertion mark has no effect and the insertion mark will not appear.</span></span> <span data-ttu-id="99598-107">詳細については、「 <xref:System.Windows.Forms.ListViewInsertionMark> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99598-107">For more information, see <xref:System.Windows.Forms.ListViewInsertionMark>.</span></span>  
  
 <span data-ttu-id="99598-108">次の図は、挿入マークを示しています。</span><span class="sxs-lookup"><span data-stu-id="99598-108">The following image shows an insertion mark:</span></span>  
  
 <span data-ttu-id="99598-109">![ListView 挿入マークを示すスクリーンショット。](./media/how-to-display-an-insertion-mark-in-a-windows-forms-listview-control/listview-insertion-mark.gif "ListViewInsertion")</span><span class="sxs-lookup"><span data-stu-id="99598-109">![Screenshot that shows a ListView insertion mark.](./media/how-to-display-an-insertion-mark-in-a-windows-forms-listview-control/listview-insertion-mark.gif "ListViewInsertion")</span></span>  
  
 <span data-ttu-id="99598-110">この機能の使用方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="99598-110">The following code example demonstrates how to use this feature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99598-111">例</span><span class="sxs-lookup"><span data-stu-id="99598-111">Example</span></span>  
 [!code-cpp[System.Windows.Forms.ListView.InsertionMark#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/CPP/listviewinsertionmarkexample.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListView.InsertionMark#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/CS/listviewinsertionmarkexample.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.InsertionMark#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/VB/listviewinsertionmarkexample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="99598-112">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="99598-112">Compiling the Code</span></span>  
 <span data-ttu-id="99598-113">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="99598-113">This example requires:</span></span>  
  
- <span data-ttu-id="99598-114">System アセンブリおよび System.Windows.Forms アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="99598-114">References to the System and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99598-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="99598-115">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.InsertionMark%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewInsertionMark>
- [<span data-ttu-id="99598-116">ListView コントロール</span><span class="sxs-lookup"><span data-stu-id="99598-116">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="99598-117">ListView コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="99598-117">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="99598-118">チュートリアル: Windows フォームでのドラッグアンドドロップ操作の実行</span><span class="sxs-lookup"><span data-stu-id="99598-118">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>](../advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md)
