---
title: '方法: オブジェクトを Windows フォーム DataGridView コントロールにバインドする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], object binding
- data grids [Windows Forms], object binding
- object binding [Windows Forms], DataGridView control
ms.assetid: cb8f29fa-577e-4e2b-883f-3a01c6189b9c
ms.openlocfilehash: e1fef71de799f9f906c956a0441c92e027173a1c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64612342"
---
# <a name="how-to-bind-objects-to-windows-forms-datagridview-controls"></a><span data-ttu-id="a136a-102">方法: オブジェクトを Windows フォーム DataGridView コントロールにバインドする</span><span class="sxs-lookup"><span data-stu-id="a136a-102">How to: Bind Objects to Windows Forms DataGridView Controls</span></span>
<span data-ttu-id="a136a-103">各オブジェクトが別々の行として表示されるように <xref:System.Windows.Forms.DataGridView> コントロールにオブジェクトのコレクションをバインドする方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="a136a-103">The following code example demonstrates how to bind a collection of objects to a <xref:System.Windows.Forms.DataGridView> control so that each object displays as a separate row.</span></span> <span data-ttu-id="a136a-104">また、この例では、<xref:System.Windows.Forms.DataGridViewComboBoxColumn> にプロパティとして列挙型を表示し、コンボ ボックスのドロップダウン リストに列挙値が含まれるようにする方法も示されています。</span><span class="sxs-lookup"><span data-stu-id="a136a-104">This example also illustrates how to display a property with an enumeration type in a <xref:System.Windows.Forms.DataGridViewComboBoxColumn> so that the combo box drop-down list contains the enumeration values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a136a-105">例</span><span class="sxs-lookup"><span data-stu-id="a136a-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridView._CollectionBound#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView._CollectionBound/CS/collectionbound.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView._CollectionBound#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView._CollectionBound/VB/collectionbound.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a136a-106">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="a136a-106">Compiling the Code</span></span>  
 <span data-ttu-id="a136a-107">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a136a-107">This example requires:</span></span>  
  
- <span data-ttu-id="a136a-108">System アセンブリおよび System.Windows.Forms アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="a136a-108">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="a136a-109">コマンドラインからこの例を Visual Basic または Visual C# の構築方法の詳細については、[、コマンドラインからビルドする](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)または[コマンド ライン ビルドで csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a136a-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="a136a-110">新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="a136a-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a136a-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="a136a-111">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="a136a-112">Windows フォーム DataGridView コントロールでのデータの表示</span><span class="sxs-lookup"><span data-stu-id="a136a-112">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="a136a-113">方法: Windows フォーム DataGridView 行にバインドされたオブジェクトへのアクセス</span><span class="sxs-lookup"><span data-stu-id="a136a-113">How to: Access Objects Bound to Windows Forms DataGridView Rows</span></span>](how-to-access-objects-bound-to-windows-forms-datagridview-rows.md)
