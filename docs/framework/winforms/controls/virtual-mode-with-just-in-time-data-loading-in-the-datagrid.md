---
title: '方法: Windows フォーム DataGridView コントロールで Just-In-Time データ読み込みを使用して仮想モードを実装する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], just-in-time data loading
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- just-in-time data loading
- DataGridView control [Windows Forms], large data sets
- virtual mode [Windows Forms], just-in-time data loading
ms.assetid: 33825f92-7a22-40ee-86d9-9a2ed1ead7b7
ms.openlocfilehash: 6fdf2bd16297820026fa84bdaefe61cc495cea4f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61759961"
---
# <a name="how-to-implement-virtual-mode-with-just-in-time-data-loading-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="adbc5-102">方法: Windows フォーム DataGridView コントロールで Just-In-Time データ読み込みを使用して仮想モードを実装する</span><span class="sxs-lookup"><span data-stu-id="adbc5-102">How to: Implement Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="adbc5-103">次のコード例では、必要がある場合にのみ、サーバーからデータを読み込むデータ キャッシュを持つ <xref:System.Windows.Forms.DataGridView> コントロールで仮想モードを使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="adbc5-103">The following code example shows how to use virtual mode in the <xref:System.Windows.Forms.DataGridView> control with a data cache that loads data from a server only when it is needed.</span></span> <span data-ttu-id="adbc5-104">この例で詳しく説明は[Windows フォームの DataGridView コントロールで Just-In-Time データ読み込みで仮想モードの実装](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)します。</span><span class="sxs-lookup"><span data-stu-id="adbc5-104">This example is described in detail in [Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="adbc5-105">例</span><span class="sxs-lookup"><span data-stu-id="adbc5-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="adbc5-106">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="adbc5-106">Compiling the Code</span></span>  
 <span data-ttu-id="adbc5-107">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="adbc5-107">This example requires:</span></span>  
  
- <span data-ttu-id="adbc5-108">System、System.Data、System.Xml、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="adbc5-108">References to the System, System.Data, System.Xml, and System.Windows.Forms assemblies.</span></span>  
  
- <span data-ttu-id="adbc5-109">Northwind SQL Server サンプル データベースがインストールされているサーバーへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="adbc5-109">Access to a server with the Northwind SQL Server sample database installed.</span></span>  
  
 <span data-ttu-id="adbc5-110">Visual Basic または Visual C# からこの例をビルドする方法については、[コマンド ラインからのビルド](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)、または[csc.exe を使用したコマンド ラインからのビルド](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="adbc5-110">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="adbc5-111">新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="adbc5-111">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="adbc5-112">.NET Framework セキュリティ</span><span class="sxs-lookup"><span data-stu-id="adbc5-112">.NET Framework Security</span></span>  
 <span data-ttu-id="adbc5-113">接続文字列内に機密情報 (パスワードなど) を格納すると、アプリケーションのセキュリティに影響を及ぼすことがあります。</span><span class="sxs-lookup"><span data-stu-id="adbc5-113">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="adbc5-114">データベースへのアクセスを制御する方法としては、Windows 認証 (統合セキュリティとも呼ばれます) を使用する方が安全です。</span><span class="sxs-lookup"><span data-stu-id="adbc5-114">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="adbc5-115">詳細については、「[接続情報の保護](../../data/adonet/protecting-connection-information.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="adbc5-115">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adbc5-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="adbc5-116">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- <xref:System.Windows.Forms.DataGridView.CellValueNeeded>
- [<span data-ttu-id="adbc5-117">Windows フォーム DataGridView コントロールでの Just-In-Time データ読み込みによる仮想モードの実装</span><span class="sxs-lookup"><span data-stu-id="adbc5-117">Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)
- [<span data-ttu-id="adbc5-118">Windows フォーム DataGridView コントロールでのパフォーマンス チューニング</span><span class="sxs-lookup"><span data-stu-id="adbc5-118">Performance Tuning in the Windows Forms DataGridView Control</span></span>](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="adbc5-119">Windows フォーム DataGridView コントロールでの仮想モード</span><span class="sxs-lookup"><span data-stu-id="adbc5-119">Virtual Mode in the Windows Forms DataGridView Control</span></span>](virtual-mode-in-the-windows-forms-datagridview-control.md)
