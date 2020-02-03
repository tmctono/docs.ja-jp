---
title: DataGridView コントロールにデータをバインドする
ms.date: 02/08/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [Windows Forms], grids
- data binding [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 1660f69c-5711-45d2-abc1-e25bc6779124
ms.openlocfilehash: e2762bf363a469abf8c1e57b851d351c1cb41b62
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745076"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control"></a><span data-ttu-id="57b8e-102">方法: Windows フォーム DataGridView コントロールにデータをバインドする</span><span class="sxs-lookup"><span data-stu-id="57b8e-102">How to: Bind data to the Windows Forms DataGridView control</span></span>

<span data-ttu-id="57b8e-103"><xref:System.Windows.Forms.DataGridView> コントロールでは、標準の Windows フォームデータバインディングモデルがサポートされているため、さまざまなデータソースにバインドできます。</span><span class="sxs-lookup"><span data-stu-id="57b8e-103">The <xref:System.Windows.Forms.DataGridView> control supports the standard Windows Forms data binding model, so it can bind to a variety of data sources.</span></span> <span data-ttu-id="57b8e-104">通常、データソースとの対話を管理する <xref:System.Windows.Forms.BindingSource> にバインドします。</span><span class="sxs-lookup"><span data-stu-id="57b8e-104">Usually, you bind to a <xref:System.Windows.Forms.BindingSource> that manages the interaction with the data source.</span></span> <span data-ttu-id="57b8e-105"><xref:System.Windows.Forms.BindingSource> には任意の Windows フォームデータソースを指定できます。これにより、データの場所を選択または変更する際の柔軟性が向上します。</span><span class="sxs-lookup"><span data-stu-id="57b8e-105">The <xref:System.Windows.Forms.BindingSource> can be any Windows Forms data source, which gives you great flexibility when choosing or modifying your data's location.</span></span> <span data-ttu-id="57b8e-106"><xref:System.Windows.Forms.DataGridView> コントロールでサポートされているデータソースの詳細については、「 [DataGridView コントロールの概要](datagridview-control-overview-windows-forms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57b8e-106">For more information about data sources the <xref:System.Windows.Forms.DataGridView> control supports, see the [DataGridView control overview](datagridview-control-overview-windows-forms.md).</span></span>  

<span data-ttu-id="57b8e-107">Visual Studio では、DataGridView コントロールへのデータバインドが広範囲にサポートされています。</span><span class="sxs-lookup"><span data-stu-id="57b8e-107">Visual Studio has extensive support for data binding to the DataGridView control.</span></span> <span data-ttu-id="57b8e-108">詳細については、「[方法: デザイナーを使用してデータを Windows フォーム DataGridView コントロールにバインド](bind-data-to-the-datagrid-using-the-designer.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57b8e-108">For more information, see [How to: Bind data to the Windows Forms DataGridView control using the Designer](bind-data-to-the-datagrid-using-the-designer.md).</span></span>  

<span data-ttu-id="57b8e-109">DataGridView コントロールをデータに接続するには:</span><span class="sxs-lookup"><span data-stu-id="57b8e-109">To connect a DataGridView control to data:</span></span>

1. <span data-ttu-id="57b8e-110">データの取得の詳細を処理するメソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="57b8e-110">Implement a method to handle the details of retrieving the data.</span></span> <span data-ttu-id="57b8e-111">次のコード例では、<xref:System.Data.SqlClient.SqlDataAdapter>を初期化し、それを使用して <xref:System.Data.DataTable>を設定する `GetData` メソッドを実装しています。</span><span class="sxs-lookup"><span data-stu-id="57b8e-111">The following code example implements a `GetData` method that initializes a <xref:System.Data.SqlClient.SqlDataAdapter>, and uses it to populate a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="57b8e-112">次に、<xref:System.Data.DataTable> を <xref:System.Windows.Forms.BindingSource>にバインドします。</span><span class="sxs-lookup"><span data-stu-id="57b8e-112">It then binds the <xref:System.Data.DataTable> to the <xref:System.Windows.Forms.BindingSource>.</span></span> 

2. <span data-ttu-id="57b8e-113">フォームの <xref:System.Windows.Forms.Form.Load> イベントハンドラーで、<xref:System.Windows.Forms.DataGridView> コントロールを <xref:System.Windows.Forms.BindingSource>にバインドし、`GetData` メソッドを呼び出してデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="57b8e-113">In the form's <xref:System.Windows.Forms.Form.Load> event handler, bind the <xref:System.Windows.Forms.DataGridView> control to the <xref:System.Windows.Forms.BindingSource>, and call the `GetData` method to retrieve the data.</span></span>  

## <a name="example"></a><span data-ttu-id="57b8e-114">例</span><span class="sxs-lookup"><span data-stu-id="57b8e-114">Example</span></span>

<span data-ttu-id="57b8e-115">この完全なコード例では、データベースからデータを取得して、Windows フォームに DataGridView コントロールを設定します。</span><span class="sxs-lookup"><span data-stu-id="57b8e-115">This complete code example retrieves data from a database to populate a DataGridView control in a Windows form.</span></span> <span data-ttu-id="57b8e-116">フォームには、データを再読み込みし、変更をデータベースに送信するためのボタンもあります。</span><span class="sxs-lookup"><span data-stu-id="57b8e-116">The form also has buttons to reload data and submit changes to the database.</span></span>  

<span data-ttu-id="57b8e-117">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="57b8e-117">This example requires:</span></span> 

- <span data-ttu-id="57b8e-118">Northwind SQL Server サンプルデータベースへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="57b8e-118">Access to a Northwind SQL Server sample database.</span></span> <span data-ttu-id="57b8e-119">Northwind サンプルデータベースのインストールの詳細については、「 [ADO.NET コードサンプルのサンプルデータベースの取得](../../data/adonet/sql/linq/downloading-sample-databases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57b8e-119">For more information about installing the Northwind sample database, see [Get the sample databases for ADO.NET code samples](../../data/adonet/sql/linq/downloading-sample-databases.md).</span></span> 

- <span data-ttu-id="57b8e-120">システム、System.xml、System.xml、および System.xml の各アセンブリへの参照です。</span><span class="sxs-lookup"><span data-stu-id="57b8e-120">References to the System, System.Windows.Forms, System.Data, and System.Xml assemblies.</span></span>  

<span data-ttu-id="57b8e-121">この例をビルドして実行するには、新しい Windows フォームプロジェクトの*Form1*コードファイルにコードを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="57b8e-121">To build and run this example, paste the code into the *Form1* code file in a new Windows Forms project.</span></span> <span data-ttu-id="57b8e-122">C#または Visual Basic コマンドラインからのビルドの詳細については、「 [csc.exe を使用したコマンドライン](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)からのビルド」または「[コマンドラインからのビルド](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57b8e-122">For information about building from the C# or Visual Basic command line, see [Command-line building with csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) or [Build from the command line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span>  
  
<span data-ttu-id="57b8e-123">Northwind SQL Server サンプルデータベース接続の値を使用して、例の `connectionString` 変数を設定します。</span><span class="sxs-lookup"><span data-stu-id="57b8e-123">Populate the `connectionString` variable in the example with the values for your Northwind SQL Server sample database connection.</span></span> <span data-ttu-id="57b8e-124">Windows 認証 (統合セキュリティとも呼ばれます) は、接続文字列にパスワードを格納するよりも、データベースに接続するより安全な方法です。</span><span class="sxs-lookup"><span data-stu-id="57b8e-124">Windows Authentication, also called integrated security, is a more secure way to connect to the database than storing a password in the connection string.</span></span> <span data-ttu-id="57b8e-125">接続のセキュリティの詳細については、「[接続情報の保護](../../data/adonet/protecting-connection-information.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57b8e-125">For more information about connection security, see [Protect connection information](../../data/adonet/protecting-connection-information.md).</span></span>  

[!code-csharp[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs)]
[!code-vb[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="57b8e-126">参照</span><span class="sxs-lookup"><span data-stu-id="57b8e-126">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="57b8e-127">Windows フォーム DataGridView コントロールにデータを表示する</span><span class="sxs-lookup"><span data-stu-id="57b8e-127">Display data in the Windows Forms DataGridView control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="57b8e-128">接続情報の保護</span><span class="sxs-lookup"><span data-stu-id="57b8e-128">Protect connection information</span></span>](../../data/adonet/protecting-connection-information.md)
