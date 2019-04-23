---
title: '方法: データ ソースに Windows フォーム DataGrid コントロールをバインドする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- datasets [Windows Forms], binding to DataGrid control
- data binding [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], data binding
- bound controls [Windows Forms], DataGrid control
- Windows Forms controls, data binding
- bound controls [Windows Forms]
- data-bound controls [Windows Forms], DataGrid
ms.assetid: 128cdb07-dfd3-4d60-9d6a-902847667c36
ms.openlocfilehash: 920a93894cc126f85bc6b618efbe6e9cedea4881
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59332574"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source"></a><span data-ttu-id="64ebf-102">方法: データ ソースに Windows フォーム DataGrid コントロールをバインドする</span><span class="sxs-lookup"><span data-stu-id="64ebf-102">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>
> [!NOTE]
>  <span data-ttu-id="64ebf-103"><xref:System.Windows.Forms.DataGridView> コントロールは、<xref:System.Windows.Forms.DataGrid> コントロールに代わると共に追加の機能を提供します。ただし、<xref:System.Windows.Forms.DataGrid> コントロールは、下位互換性を保つ目的および将来使用する目的で保持されます。</span><span class="sxs-lookup"><span data-stu-id="64ebf-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="64ebf-104">詳細については、「[Windows フォームの DataGridView コントロールと DataGrid コントロールの違いについて](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64ebf-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="64ebf-105">Windows フォーム<xref:System.Windows.Forms.DataGrid>コントロールが具体的には、データ ソースから情報を表示するように設計します。</span><span class="sxs-lookup"><span data-stu-id="64ebf-105">The Windows Forms <xref:System.Windows.Forms.DataGrid> control is specifically designed to display information from a data source.</span></span> <span data-ttu-id="64ebf-106">実行時に呼び出すことによって、コントロールをバインドする、<xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="64ebf-106">You bind the control at run time by calling the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span> <span data-ttu-id="64ebf-107">さまざまなデータ ソースからデータを表示できますが、最も一般的なソース、データセットとデータのビューです。</span><span class="sxs-lookup"><span data-stu-id="64ebf-107">Although you can display data from a variety of data sources, the most typical sources are datasets and data views.</span></span>  
  
### <a name="to-data-bind-the-datagrid-control-programmatically"></a><span data-ttu-id="64ebf-108">DataGrid コントロールをプログラムでデータ バインドする</span><span class="sxs-lookup"><span data-stu-id="64ebf-108">To data-bind the DataGrid control programmatically</span></span>  
  
1. <span data-ttu-id="64ebf-109">データセットを挿入するコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="64ebf-109">Write code to fill the dataset.</span></span>  
  
     <span data-ttu-id="64ebf-110">データ ソースがデータセットまたはデータセットのテーブルに基づくデータ ビューの場合は、データセットを挿入するためのフォームにコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="64ebf-110">If the data source is a dataset or a data view based on a dataset table, add code to the form to fill the dataset.</span></span>  
  
     <span data-ttu-id="64ebf-111">実際に使用するコードは、データセットがデータを取得する場所に依存します。</span><span class="sxs-lookup"><span data-stu-id="64ebf-111">The exact code you use depends on where the dataset is getting data.</span></span> <span data-ttu-id="64ebf-112">通常、呼び出す場合は、データセットをデータベースから直接登録されている、`Fill`メソッドという名前のデータセットを設定します次の例のように、データ アダプターの`DsCategories1`:。</span><span class="sxs-lookup"><span data-stu-id="64ebf-112">If the dataset is being populated directly from a database, you typically call the `Fill` method of a data adapter, as in the following example, which populates a dataset called `DsCategories1`:</span></span>  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
     <span data-ttu-id="64ebf-113">XML Web サービス、データセットが指定されている場合、通常コードで、サービスのインスタンスを作成し、データセットを返すメソッドのいずれかを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="64ebf-113">If the dataset is being filled from an XML Web service, you typically create an instance of the service in your code and then call one of its methods to return a dataset.</span></span> <span data-ttu-id="64ebf-114">その後、XML Web サービスからのデータセットは、ローカルのデータセットにマージします。</span><span class="sxs-lookup"><span data-stu-id="64ebf-114">You then merge the dataset from the XML Web service into your local dataset.</span></span> <span data-ttu-id="64ebf-115">次の例と呼ばれる XML Web サービスのインスタンスを作成する方法を示しています`CategoriesService`、呼び出すその`GetCategories`メソッド、およびローカルのデータセットに結果のデータセットと呼ばれるマージ`DsCategories1`:。</span><span class="sxs-lookup"><span data-stu-id="64ebf-115">The following example shows how you can create an instance of an XML Web service called `CategoriesService`, call its `GetCategories` method, and merge the resulting dataset into a local dataset called `DsCategories1`:</span></span>  
  
    ```vb  
    Dim ws As New MyProject.localhost.CategoriesService()  
    ws.Credentials = System.Net.CredentialCache.DefaultCredentials  
    DsCategories1.Merge(ws.GetCategories())  
    ```  
  
    ```csharp  
    MyProject.localhost.CategoriesService ws = new MyProject.localhost.CategoriesService();  
    ws.Credentials = System.Net.CredentialCache.DefaultCredentials;  
    DsCategories1.Merge(ws.GetCategories());  
    ```  
  
    ```cpp  
    MyProject::localhost::CategoriesService^ ws =   
       new MyProject::localhost::CategoriesService();  
    ws->Credentials = System::Net::CredentialCache::DefaultCredentials;  
    dsCategories1->Merge(ws->GetCategories());  
    ```  
  
2. <span data-ttu-id="64ebf-116">呼び出す、<xref:System.Windows.Forms.DataGrid>コントロールの<xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>メソッド、データ ソースとデータ メンバーに渡します。</span><span class="sxs-lookup"><span data-stu-id="64ebf-116">Call the <xref:System.Windows.Forms.DataGrid> control's <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method, passing it the data source and a data member.</span></span> <span data-ttu-id="64ebf-117">データ メンバーを明示的に渡す必要がない場合は、空の文字列を渡します。</span><span class="sxs-lookup"><span data-stu-id="64ebf-117">If you do not need to explicitly pass a data member, pass an empty string.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="64ebf-118">最初に、グリッドをバインドする場合は、コントロールを設定できます<xref:System.Windows.Forms.DataGrid.DataSource%2A>と<xref:System.Windows.Forms.DataGrid.DataMember%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="64ebf-118">If you are binding the grid for the first time, you can set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties.</span></span> <span data-ttu-id="64ebf-119">ただし、設定されていると、これらのプロパティをリセットできません。</span><span class="sxs-lookup"><span data-stu-id="64ebf-119">However, you cannot reset these properties once they have been set.</span></span> <span data-ttu-id="64ebf-120">そのため、お勧め必ず使用すること、<xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="64ebf-120">Therefore, it is recommended that you always use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span>  
  
     <span data-ttu-id="64ebf-121">次の例は、プログラムによってという名前のデータセット内の Customers テーブルにバインドする方法を示しています`DsCustomers1`:。</span><span class="sxs-lookup"><span data-stu-id="64ebf-121">The following example shows how you can programmatically bind to the Customers table in a dataset called `DsCustomers1`:</span></span>  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "Customers");  
    ```  
  
     <span data-ttu-id="64ebf-122">Customers テーブルがデータセット内の唯一のテーブルの場合は、でしたまたはグリッドを連結するこの方法。</span><span class="sxs-lookup"><span data-stu-id="64ebf-122">If the Customers table is the only table in the dataset, you could alternatively bind the grid this way:</span></span>  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "");  
    ```  
  
3. <span data-ttu-id="64ebf-123">(省略可能)グリッドに適切なテーブルのスタイルおよび列のスタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="64ebf-123">(Optional) Add the appropriate table styles and column styles to the grid.</span></span> <span data-ttu-id="64ebf-124">テーブル スタイルがない場合は、テーブルが表示されますが、最低限の書式と表示されているすべての列。</span><span class="sxs-lookup"><span data-stu-id="64ebf-124">If there are no table styles, you will see the table, but with minimal formatting and with all columns visible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64ebf-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="64ebf-125">See also</span></span>

- [<span data-ttu-id="64ebf-126">DataGrid コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="64ebf-126">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)
- [<span data-ttu-id="64ebf-127">方法: Windows フォームの DataGrid コントロールにテーブルと列を追加します。</span><span class="sxs-lookup"><span data-stu-id="64ebf-127">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="64ebf-128">DataGrid コントロール</span><span class="sxs-lookup"><span data-stu-id="64ebf-128">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
- [<span data-ttu-id="64ebf-129">Windows フォームでのデータ バインディング</span><span class="sxs-lookup"><span data-stu-id="64ebf-129">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
