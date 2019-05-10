---
title: '方法: 連結されていない Windows フォーム DataGridView コントロールを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], unbound data
- DataGridView control [Windows Forms], displaying data without binding to a data source
- data [Windows Forms], unbound
ms.assetid: b5d4b47d-9a28-4d88-9dba-0a3c90fba71d
ms.openlocfilehash: 193e5228df8587dfc384d8ed97ee5e4e6c005215
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64611992"
---
# <a name="how-to-create-an-unbound-windows-forms-datagridview-control"></a><span data-ttu-id="8a6c2-102">方法: 連結されていない Windows フォーム DataGridView コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="8a6c2-102">How to: Create an Unbound Windows Forms DataGridView Control</span></span>
<span data-ttu-id="8a6c2-103"><xref:System.Windows.Forms.DataGridView> コントロールをデータ ソースにバインドせずに、プログラムでデータを設定する方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="8a6c2-103">The following code example demonstrates how to populate a <xref:System.Windows.Forms.DataGridView> control programmatically without binding it to a data source.</span></span> <span data-ttu-id="8a6c2-104">これは、少量のデータを表形式で表示する必要がある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="8a6c2-104">This is useful when you have a small amount of data that you want to display in a table format.</span></span>  
  
 <span data-ttu-id="8a6c2-105">このコード例の詳細については、次を参照してください。[チュートリアル。作成、バインドされていない Windows フォーム DataGridView コントロール](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)します。</span><span class="sxs-lookup"><span data-stu-id="8a6c2-105">For a complete explanation of this code example, see [Walkthrough: Creating an Unbound Windows Forms DataGridView Control](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a6c2-106">例</span><span class="sxs-lookup"><span data-stu-id="8a6c2-106">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8a6c2-107">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="8a6c2-107">Compiling the Code</span></span>  
 <span data-ttu-id="8a6c2-108">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8a6c2-108">This example requires:</span></span>  
  
- <span data-ttu-id="8a6c2-109">System、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="8a6c2-109">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="8a6c2-110">コマンドラインからこの例を Visual Basic または Visual C# の構築方法の詳細については、[、コマンドラインからビルドする](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)または[コマンド ライン ビルドで csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a6c2-110">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="8a6c2-111">新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="8a6c2-111">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  

## <a name="see-also"></a><span data-ttu-id="8a6c2-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="8a6c2-112">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="8a6c2-113">チュートリアル: 作成、バインドされていない Windows フォーム DataGridView コントロール</span><span class="sxs-lookup"><span data-stu-id="8a6c2-113">Walkthrough: Creating an Unbound Windows Forms DataGridView Control</span></span>](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)
- [<span data-ttu-id="8a6c2-114">Windows フォーム DataGridView コントロールでのデータの表示</span><span class="sxs-lookup"><span data-stu-id="8a6c2-114">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="8a6c2-115">Windows フォーム DataGridView コントロールでのデータ表示モード</span><span class="sxs-lookup"><span data-stu-id="8a6c2-115">Data Display Modes in the Windows Forms DataGridView Control</span></span>](data-display-modes-in-the-windows-forms-datagridview-control.md)
