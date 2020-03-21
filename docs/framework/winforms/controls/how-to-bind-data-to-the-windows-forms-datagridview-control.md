---
title: データをデータ グリッド ビュー コントロールにバインドする
ms.date: 02/08/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [Windows Forms], grids
- data binding [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 1660f69c-5711-45d2-abc1-e25bc6779124
ms.openlocfilehash: 643dcd37cd1bb3f8b5938fedff66c67cd68278ff
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182272"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control"></a><span data-ttu-id="1c0e8-102">方法 : データをバインドするコントロール</span><span class="sxs-lookup"><span data-stu-id="1c0e8-102">How to: Bind data to the Windows Forms DataGridView control</span></span>

<span data-ttu-id="1c0e8-103">コントロール<xref:System.Windows.Forms.DataGridView>は、標準の Windows フォーム データ バインディング モデルをサポートするため、さまざまなデータ ソースにバインドできます。</span><span class="sxs-lookup"><span data-stu-id="1c0e8-103">The <xref:System.Windows.Forms.DataGridView> control supports the standard Windows Forms data binding model, so it can bind to a variety of data sources.</span></span> <span data-ttu-id="1c0e8-104">通常は、データ ソース<xref:System.Windows.Forms.BindingSource>との対話を管理する にバインドします。</span><span class="sxs-lookup"><span data-stu-id="1c0e8-104">Usually, you bind to a <xref:System.Windows.Forms.BindingSource> that manages the interaction with the data source.</span></span> <span data-ttu-id="1c0e8-105">は<xref:System.Windows.Forms.BindingSource>、任意の Windows フォーム データ ソースを使用でき、データの場所を選択または変更する際に柔軟性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="1c0e8-105">The <xref:System.Windows.Forms.BindingSource> can be any Windows Forms data source, which gives you great flexibility when choosing or modifying your data's location.</span></span> <span data-ttu-id="1c0e8-106">コントロールがサポートするデータ ソース<xref:System.Windows.Forms.DataGridView>の詳細については、「 [DataGridView コントロールの概要](datagridview-control-overview-windows-forms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c0e8-106">For more information about data sources the <xref:System.Windows.Forms.DataGridView> control supports, see the [DataGridView control overview](datagridview-control-overview-windows-forms.md).</span></span>  

<span data-ttu-id="1c0e8-107">コントロールへのデータ バインディングに対する広範なサポートがあります。</span><span class="sxs-lookup"><span data-stu-id="1c0e8-107">Visual Studio has extensive support for data binding to the DataGridView control.</span></span> <span data-ttu-id="1c0e8-108">詳細については、「[方法 : デザイナーを使用して Windows フォーム DataGridView コントロールにデータをバインドする」を参照してください](bind-data-to-the-datagrid-using-the-designer.md)。</span><span class="sxs-lookup"><span data-stu-id="1c0e8-108">For more information, see [How to: Bind data to the Windows Forms DataGridView control using the Designer](bind-data-to-the-datagrid-using-the-designer.md).</span></span>  

<span data-ttu-id="1c0e8-109">コントロールをデータに接続するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1c0e8-109">To connect a DataGridView control to data:</span></span>

1. <span data-ttu-id="1c0e8-110">データの取得の詳細を処理するメソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="1c0e8-110">Implement a method to handle the details of retrieving the data.</span></span> <span data-ttu-id="1c0e8-111">を初期化し、それを使用して`GetData`を設定するメソッド<xref:System.Data.SqlClient.SqlDataAdapter>を実装するコード例を次<xref:System.Data.DataTable>に示します。</span><span class="sxs-lookup"><span data-stu-id="1c0e8-111">The following code example implements a `GetData` method that initializes a <xref:System.Data.SqlClient.SqlDataAdapter>, and uses it to populate a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="1c0e8-112">次に、 を<xref:System.Data.DataTable>に<xref:System.Windows.Forms.BindingSource>バインドします。</span><span class="sxs-lookup"><span data-stu-id="1c0e8-112">It then binds the <xref:System.Data.DataTable> to the <xref:System.Windows.Forms.BindingSource>.</span></span>

2. <span data-ttu-id="1c0e8-113">フォームの<xref:System.Windows.Forms.Form.Load>イベント ハンドラで、コントロールを<xref:System.Windows.Forms.DataGridView><xref:System.Windows.Forms.BindingSource>にバインドし、メソッドを`GetData`呼び出してデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="1c0e8-113">In the form's <xref:System.Windows.Forms.Form.Load> event handler, bind the <xref:System.Windows.Forms.DataGridView> control to the <xref:System.Windows.Forms.BindingSource>, and call the `GetData` method to retrieve the data.</span></span>  

## <a name="example"></a><span data-ttu-id="1c0e8-114">例</span><span class="sxs-lookup"><span data-stu-id="1c0e8-114">Example</span></span>

<span data-ttu-id="1c0e8-115">この完全なコード例では、データベースからデータを取得して、Windows フォームに DataGridView コントロールを設定します。</span><span class="sxs-lookup"><span data-stu-id="1c0e8-115">This complete code example retrieves data from a database to populate a DataGridView control in a Windows form.</span></span> <span data-ttu-id="1c0e8-116">フォームには、データを再読み込みし、データベースに変更を送信するためのボタンもあります。</span><span class="sxs-lookup"><span data-stu-id="1c0e8-116">The form also has buttons to reload data and submit changes to the database.</span></span>  

<span data-ttu-id="1c0e8-117">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1c0e8-117">This example requires:</span></span>

- <span data-ttu-id="1c0e8-118">ノースウィンド SQL サーバー サンプル データベースへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="1c0e8-118">Access to a Northwind SQL Server sample database.</span></span> <span data-ttu-id="1c0e8-119">Northwind サンプル データベースのインストールの詳細については[、「ADO.NETコード サンプルのサンプル データベースを取得する](../../data/adonet/sql/linq/downloading-sample-databases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c0e8-119">For more information about installing the Northwind sample database, see [Get the sample databases for ADO.NET code samples](../../data/adonet/sql/linq/downloading-sample-databases.md).</span></span>

- <span data-ttu-id="1c0e8-120">システム、システム.Windows.フォーム、システム.データ、およびシステム.Xml アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="1c0e8-120">References to the System, System.Windows.Forms, System.Data, and System.Xml assemblies.</span></span>  

<span data-ttu-id="1c0e8-121">この例をビルドして実行するには、新しい Windows フォーム プロジェクトの*Form1*コード ファイルにコードを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="1c0e8-121">To build and run this example, paste the code into the *Form1* code file in a new Windows Forms project.</span></span> <span data-ttu-id="1c0e8-122">C# または Visual Basic コマンド ラインからのビルドについては[、「csc.exe を使用したコマンド ラインのビルド](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)」または「[コマンド ラインからのビルド](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c0e8-122">For information about building from the C# or Visual Basic command line, see [Command-line building with csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) or [Build from the command line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span>  
  
<span data-ttu-id="1c0e8-123">例の`connectionString`変数に、ノースウィンド SQL Server サンプル データベース接続の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="1c0e8-123">Populate the `connectionString` variable in the example with the values for your Northwind SQL Server sample database connection.</span></span> <span data-ttu-id="1c0e8-124">Windows 認証は統合セキュリティとも呼ばれ、接続文字列にパスワードを格納するよりも、データベースに接続する方が安全な方法です。</span><span class="sxs-lookup"><span data-stu-id="1c0e8-124">Windows Authentication, also called integrated security, is a more secure way to connect to the database than storing a password in the connection string.</span></span> <span data-ttu-id="1c0e8-125">接続セキュリティの詳細については、[接続情報の保護](../../data/adonet/protecting-connection-information.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c0e8-125">For more information about connection security, see [Protect connection information](../../data/adonet/protecting-connection-information.md).</span></span>  

[!code-csharp[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs)]
[!code-vb[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="1c0e8-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="1c0e8-126">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="1c0e8-127">コントロールにデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="1c0e8-127">Display data in the Windows Forms DataGridView control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="1c0e8-128">接続情報を保護する</span><span class="sxs-lookup"><span data-stu-id="1c0e8-128">Protect connection information</span></span>](../../data/adonet/protecting-connection-information.md)
