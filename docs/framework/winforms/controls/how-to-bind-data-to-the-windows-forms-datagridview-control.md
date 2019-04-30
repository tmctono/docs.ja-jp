---
title: '方法: Windows フォーム DataGridView コントロールにデータをバインドします。'
ms.date: 02/08/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [Windows Forms], grids
- data binding [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 1660f69c-5711-45d2-abc1-e25bc6779124
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e147109a64687177f201ad1e312fab56ea61d604
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62010931"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control"></a><span data-ttu-id="d0478-102">方法: Windows フォーム DataGridView コントロールにデータをバインドします。</span><span class="sxs-lookup"><span data-stu-id="d0478-102">How to: Bind data to the Windows Forms DataGridView control</span></span>

<span data-ttu-id="d0478-103"><xref:System.Windows.Forms.DataGridView>コントロールは、さまざまなデータ ソースにバインドできるように、標準 Windows フォーム データ バインディング モデルをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d0478-103">The <xref:System.Windows.Forms.DataGridView> control supports the standard Windows Forms data binding model, so it can bind to a variety of data sources.</span></span> <span data-ttu-id="d0478-104">バインドする、通常、<xref:System.Windows.Forms.BindingSource>データ ソースとの相互作用を管理します。</span><span class="sxs-lookup"><span data-stu-id="d0478-104">Usually, you bind to a <xref:System.Windows.Forms.BindingSource> that manages the interaction with the data source.</span></span> <span data-ttu-id="d0478-105"><xref:System.Windows.Forms.BindingSource>を選択するか、データの場所を変更するときに、優れた柔軟性を提供する Windows フォームのデータ ソースを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d0478-105">The <xref:System.Windows.Forms.BindingSource> can be any Windows Forms data source, which gives you great flexibility when choosing or modifying your data's location.</span></span> <span data-ttu-id="d0478-106">データ ソースの詳細については、<xref:System.Windows.Forms.DataGridView>サポートを制御しを参照してください、 [DataGridView コントロールの概要](datagridview-control-overview-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="d0478-106">For more information about data sources the <xref:System.Windows.Forms.DataGridView> control supports, see the [DataGridView control overview](datagridview-control-overview-windows-forms.md).</span></span>  

<span data-ttu-id="d0478-107">Visual Studio は広範なデータ バインド DataGridView コントロールをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d0478-107">Visual Studio has extensive support for data binding to the DataGridView control.</span></span> <span data-ttu-id="d0478-108">詳細については、「[方法 :データ デザイナーを使用して Windows フォームの DataGridView コントロールをバインド](bind-data-to-the-datagrid-using-the-designer.md)します。</span><span class="sxs-lookup"><span data-stu-id="d0478-108">For more information, see [How to: Bind data to the Windows Forms DataGridView control using the Designer](bind-data-to-the-datagrid-using-the-designer.md).</span></span>  

<span data-ttu-id="d0478-109">DataGridView コントロールをデータに接続します。</span><span class="sxs-lookup"><span data-stu-id="d0478-109">To connect a DataGridView control to data:</span></span>

1. <span data-ttu-id="d0478-110">データの取得の詳細を処理するメソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="d0478-110">Implement a method to handle the details of retrieving the data.</span></span> <span data-ttu-id="d0478-111">次のコード例の実装を`GetData`を初期化するメソッド、 <xref:System.Data.SqlClient.SqlDataAdapter>、設定を使用して、<xref:System.Data.DataTable>します。</span><span class="sxs-lookup"><span data-stu-id="d0478-111">The following code example implements a `GetData` method that initializes a <xref:System.Data.SqlClient.SqlDataAdapter>, and uses it to populate a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="d0478-112">バインドし、<xref:System.Data.DataTable>を<xref:System.Windows.Forms.BindingSource>します。</span><span class="sxs-lookup"><span data-stu-id="d0478-112">It then binds the <xref:System.Data.DataTable> to the <xref:System.Windows.Forms.BindingSource>.</span></span> 

2. <span data-ttu-id="d0478-113">フォームの<xref:System.Windows.Forms.Form.Load>イベント ハンドラー、バインド、<xref:System.Windows.Forms.DataGridView>への制御、<xref:System.Windows.Forms.BindingSource>を呼び出すと、`GetData`データを取得します。</span><span class="sxs-lookup"><span data-stu-id="d0478-113">In the form's <xref:System.Windows.Forms.Form.Load> event handler, bind the <xref:System.Windows.Forms.DataGridView> control to the <xref:System.Windows.Forms.BindingSource>, and call the `GetData` method to retrieve the data.</span></span>  

## <a name="example"></a><span data-ttu-id="d0478-114">例</span><span class="sxs-lookup"><span data-stu-id="d0478-114">Example</span></span>

<span data-ttu-id="d0478-115">この完全なコード例では、Windows フォーム DataGridView コントロールを作成するデータベースからデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="d0478-115">This complete code example retrieves data from a database to populate a DataGridView control in a Windows form.</span></span> <span data-ttu-id="d0478-116">フォームでは、データを再読み込みし、データベースへの変更を送信するボタンもあります。</span><span class="sxs-lookup"><span data-stu-id="d0478-116">The form also has buttons to reload data and submit changes to the database.</span></span>  

<span data-ttu-id="d0478-117">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d0478-117">This example requires:</span></span> 

- <span data-ttu-id="d0478-118">SQL Server の Northwind サンプル データベースへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="d0478-118">Access to a Northwind SQL Server sample database.</span></span> <span data-ttu-id="d0478-119">Northwind サンプル データベースのインストールの詳細については、次を参照してください。 [ADO.NET コード サンプルについては、サンプル データベースを取得](../../data/adonet/sql/linq/downloading-sample-databases.md)します。</span><span class="sxs-lookup"><span data-stu-id="d0478-119">For more information about installing the Northwind sample database, see [Get the sample databases for ADO.NET code samples](../../data/adonet/sql/linq/downloading-sample-databases.md).</span></span> 

- <span data-ttu-id="d0478-120">System、System.Windows.Forms、System.Data、および System.Xml アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="d0478-120">References to the System, System.Windows.Forms, System.Data, and System.Xml assemblies.</span></span>  

<span data-ttu-id="d0478-121">ビルドし、この例を実行するにコードを貼り付ける、 *Form1*新しい Windows フォーム プロジェクトでコード ファイル。</span><span class="sxs-lookup"><span data-stu-id="d0478-121">To build and run this example, paste the code into the *Form1* code file in a new Windows Forms project.</span></span> <span data-ttu-id="d0478-122">ビルドについては、C#または Visual Basic のコマンド ラインで、「 [csc.exe を](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)または[コマンドラインからビルド](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)します。</span><span class="sxs-lookup"><span data-stu-id="d0478-122">For information about building from the C# or Visual Basic command line, see [Command-line building with csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) or [Build from the command line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span>  
  
<span data-ttu-id="d0478-123">設定、`connectionString`例では、SQL Server の Northwind サンプル データベース接続の値を持つ変数です。</span><span class="sxs-lookup"><span data-stu-id="d0478-123">Populate the `connectionString` variable in the example with the values for your Northwind SQL Server sample database connection.</span></span> <span data-ttu-id="d0478-124">Windows 認証、統合のセキュリティとも呼ばれます。 は、接続文字列にパスワードを格納するよりもデータベースに接続するより安全な方法です。</span><span class="sxs-lookup"><span data-stu-id="d0478-124">Windows Authentication, also called integrated security, is a more secure way to connect to the database than storing a password in the connection string.</span></span> <span data-ttu-id="d0478-125">接続セキュリティの詳細については、次を参照してください。[接続情報を保護する](../../data/adonet/protecting-connection-information.md)します。</span><span class="sxs-lookup"><span data-stu-id="d0478-125">For more information about connection security, see [Protect connection information](../../data/adonet/protecting-connection-information.md).</span></span>  

[!code-csharp[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs)]
[!code-vb[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d0478-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="d0478-126">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="d0478-127">Windows フォーム DataGridView コントロールでデータを表示</span><span class="sxs-lookup"><span data-stu-id="d0478-127">Display data in the Windows Forms DataGridView control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="d0478-128">接続情報を保護します。</span><span class="sxs-lookup"><span data-stu-id="d0478-128">Protect connection information</span></span>](../../data/adonet/protecting-connection-information.md)
