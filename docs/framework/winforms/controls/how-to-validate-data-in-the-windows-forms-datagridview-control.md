---
title: '方法: Windows フォーム DataGridView コントロールのデータを検証する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [Windows Forms], validation
- DataGridView control [Windows Forms], data validation
- data grids [Windows Forms], validating data
- data validation [Windows Forms], Windows Forms
ms.assetid: d10aef35-701e-4a3c-a684-2a2ed1aeaca6
ms.openlocfilehash: dae254c14790841b37162fca9f998be429006125
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61785737"
---
# <a name="how-to-validate-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="c4f90-102">方法: Windows フォーム DataGridView コントロールのデータを検証する</span><span class="sxs-lookup"><span data-stu-id="c4f90-102">How to: Validate Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="c4f90-103">ユーザーによって <xref:System.Windows.Forms.DataGridView> コントロールに入力されたデータを検証する方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="c4f90-103">The following code example demonstrates how to validate data entered by a user into a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="c4f90-104">この例では、<xref:System.Windows.Forms.DataGridView> には、Northwind サンプル データベースの `Customers` テーブルの行が読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="c4f90-104">In this example, the <xref:System.Windows.Forms.DataGridView> is populated with rows from the `Customers` table of the Northwind sample database.</span></span> <span data-ttu-id="c4f90-105">ユーザーが `CompanyName` 列内のセルを編集すると、値の有効性をテストするために、空ではないことが確認されます。</span><span class="sxs-lookup"><span data-stu-id="c4f90-105">When the user edits a cell in the `CompanyName` column, its value is tested for validity by checking that it is not empty.</span></span> <span data-ttu-id="c4f90-106"><xref:System.Windows.Forms.DataGridView.CellValidating> イベントのイベント ハンドラーによって値が空の文字列であることが検出されると、<xref:System.Windows.Forms.DataGridView> では、ユーザーが空ではない文字列を入力するまでそのセルから移動できなくなります。</span><span class="sxs-lookup"><span data-stu-id="c4f90-106">If the event handler for the <xref:System.Windows.Forms.DataGridView.CellValidating> event finds that the value is an empty string, the <xref:System.Windows.Forms.DataGridView> prevents the user from exiting the cell until a non-empty string is entered.</span></span>  
  
 <span data-ttu-id="c4f90-107">このコード例の詳細については、次を参照してください。[チュートリアル。フォームの DataGridView コントロールを Windows のデータの検証](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)です。</span><span class="sxs-lookup"><span data-stu-id="c4f90-107">For a complete explanation of this code example, see [Walkthrough: Validating Data in the Windows Forms DataGridView Control](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4f90-108">例</span><span class="sxs-lookup"><span data-stu-id="c4f90-108">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewDataValidation#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c4f90-109">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="c4f90-109">Compiling the Code</span></span>  
 <span data-ttu-id="c4f90-110">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c4f90-110">This example requires:</span></span>  
  
- <span data-ttu-id="c4f90-111">System、System.Data、System.Windows.Forms、および System.XML の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="c4f90-111">References to the System, System.Data, System.Windows.Forms and System.XML assemblies.</span></span>  
  
 <span data-ttu-id="c4f90-112">Visual Basic または Visual C# からこの例をビルドする方法については、[コマンド ラインからのビルド](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)、または[csc.exe を使用したコマンド ラインからのビルド](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4f90-112">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="c4f90-113">新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="c4f90-113">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="c4f90-114">.NET Framework セキュリティ</span><span class="sxs-lookup"><span data-stu-id="c4f90-114">.NET Framework Security</span></span>  
 <span data-ttu-id="c4f90-115">接続文字列内に機密情報 (パスワードなど) を格納すると、アプリケーションのセキュリティに影響を及ぼすことがあります。</span><span class="sxs-lookup"><span data-stu-id="c4f90-115">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="c4f90-116">データベースへのアクセスを制御する方法としては、Windows 認証 (統合セキュリティとも呼ばれます) を使用する方が安全です。</span><span class="sxs-lookup"><span data-stu-id="c4f90-116">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="c4f90-117">詳細については、「[接続情報の保護](../../data/adonet/protecting-connection-information.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4f90-117">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4f90-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="c4f90-118">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="c4f90-119">チュートリアル: Windows フォームの DataGridView コントロールのデータの検証</span><span class="sxs-lookup"><span data-stu-id="c4f90-119">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="c4f90-120">Windows フォーム DataGridView コントロールでのデータ入力</span><span class="sxs-lookup"><span data-stu-id="c4f90-120">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="c4f90-121">チュートリアル: Windows フォームの DataGridView コントロールでのデータ入力中に発生したエラーの処理</span><span class="sxs-lookup"><span data-stu-id="c4f90-121">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [<span data-ttu-id="c4f90-122">接続情報の保護</span><span class="sxs-lookup"><span data-stu-id="c4f90-122">Protecting Connection Information</span></span>](../../data/adonet/protecting-connection-information.md)
