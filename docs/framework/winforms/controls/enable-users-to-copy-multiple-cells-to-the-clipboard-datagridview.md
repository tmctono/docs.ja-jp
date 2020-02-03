---
title: ユーザーが DataGridView コントロールからクリップボードに複数のセルをコピーできるようにする
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], copying to Clipboard
- DataGridView control [Windows Forms], copying multiple cells
- data grids [Windows Forms], copying multiple cells
- Clipboard [Windows Forms], copying multiple cells
ms.assetid: fd0403b2-d0e3-4ae0-839c-0f737e1eb4a9
ms.openlocfilehash: 2bb74a1f0c59b28ab496ce9c89c1c1b5f9d8147b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745774"
---
# <a name="how-to-enable-users-to-copy-multiple-cells-to-the-clipboard-from-the-windows-forms-datagridview-control"></a><span data-ttu-id="5a1c6-102">方法 : ユーザーが、Windows フォーム DataGridView コントロールからクリップボードに複数のセルをコピーできるようにする</span><span class="sxs-lookup"><span data-stu-id="5a1c6-102">How to: Enable Users to Copy Multiple Cells to the Clipboard from the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="5a1c6-103">セルのコピーを有効にすると、<xref:System.Windows.Forms.DataGridView> コントロール内のデータを <xref:System.Windows.Forms.Clipboard> 経由で他のアプリケーションが簡単に利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="5a1c6-103">When you enable cell copying, you make the data in your <xref:System.Windows.Forms.DataGridView> control easily accessible to other applications through the <xref:System.Windows.Forms.Clipboard>.</span></span> <span data-ttu-id="5a1c6-104">選択したセルの値は文字列に変換されてクリップボードに追加され、メモ帳や Excel などのアプリケーションにはタブ区切りのテキスト値として貼り付けられ、Word などのアプリケーションには HTML 形式のテーブルとして貼り付けられます。</span><span class="sxs-lookup"><span data-stu-id="5a1c6-104">The values of the selected cells are converted to strings and added to the Clipboard as tab-delimited text values for pasting into applications like Notepad and Excel, and as an HTML-formatted table for pasting into applications like Word.</span></span>  
  
 <span data-ttu-id="5a1c6-105">セルのコピーは、セル値のみをコピーするか、行と列のヘッダー テキストをクリップボード データに含めるか、またはユーザーが行または列全体を選択したときのみヘッダー テキストを含めるように設定できます。</span><span class="sxs-lookup"><span data-stu-id="5a1c6-105">You can configure cell copying to copy cell values only, to include row and column header text in the Clipboard data, or to include header text only when users select entire rows or columns.</span></span>  
  
 <span data-ttu-id="5a1c6-106">選択モードによっては、ユーザーは、連続しない複数のセル グループを選択できます。</span><span class="sxs-lookup"><span data-stu-id="5a1c6-106">Depending on the selection mode, users can select multiple disconnected groups of cells.</span></span> <span data-ttu-id="5a1c6-107">ユーザーがセルをクリップボードにコピーする際、セルが選択されていない行と列はコピーされません。</span><span class="sxs-lookup"><span data-stu-id="5a1c6-107">When a user copies cells to the Clipboard, rows and columns with no selected cells are not copied.</span></span> <span data-ttu-id="5a1c6-108">その他の行と列はすべて、クリップボードにコピーされたデータのテーブル内の行と列になります。</span><span class="sxs-lookup"><span data-stu-id="5a1c6-108">All other rows or columns become rows and columns in the table of data copied to the Clipboard.</span></span> <span data-ttu-id="5a1c6-109">これらの行や列で選択されていないセルは、空白のプレースホルダーとしてクリップボードにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="5a1c6-109">Unselected cells in these rows or columns are copied as blank placeholders to the Clipboard.</span></span>  
  
### <a name="to-enable-cell-copying"></a><span data-ttu-id="5a1c6-110">セルのコピーを有効にするには</span><span class="sxs-lookup"><span data-stu-id="5a1c6-110">To enable cell copying</span></span>  
  
- <span data-ttu-id="5a1c6-111"><xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A?displayProperty=nameWithType> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="5a1c6-111">Set the <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#15](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#15)]
     [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#15](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#15)]  
  
## <a name="example"></a><span data-ttu-id="5a1c6-112">例</span><span class="sxs-lookup"><span data-stu-id="5a1c6-112">Example</span></span>  
 <span data-ttu-id="5a1c6-113">セルをクリップボードにコピーする完全なコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5a1c6-113">The following complete code example demonstrates how cells are copied to the Clipboard.</span></span> <span data-ttu-id="5a1c6-114">この例には、<xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A?displayProperty=nameWithType> メソッドを使用して、選択したセルをクリップボードにコピーし、クリップボードの内容をテキスト ボックスに表示するボタンが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5a1c6-114">This example includes a button that copies the selected cells to the Clipboard using the <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A?displayProperty=nameWithType> method and displays the Clipboard contents in a text box.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5a1c6-115">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="5a1c6-115">Compiling the Code</span></span>  
 <span data-ttu-id="5a1c6-116">このコードには、次のものが必要です。</span><span class="sxs-lookup"><span data-stu-id="5a1c6-116">This code requires:</span></span>  
  
- <span data-ttu-id="5a1c6-117">N:System アセンブリおよび N:System.Windows.Forms アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="5a1c6-117">References to the N:System and N:System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a1c6-118">参照</span><span class="sxs-lookup"><span data-stu-id="5a1c6-118">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>
- <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A>
- [<span data-ttu-id="5a1c6-119">Windows フォーム DataGridView コントロールでの選択およびクリップボードの使用</span><span class="sxs-lookup"><span data-stu-id="5a1c6-119">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
