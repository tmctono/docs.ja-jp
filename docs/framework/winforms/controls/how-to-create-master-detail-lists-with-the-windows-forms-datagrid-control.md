---
title: DataGrid コントロールを使用してマスター/詳細リストを作成する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 20388c6a-94f9-4d96-be18-8c200491247f
ms.openlocfilehash: e8ab63d52d97a8a6e6f60da741186e3937350e1e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76730990"
---
# <a name="how-to-create-masterdetail-lists-with-the-windows-forms-datagrid-control"></a><span data-ttu-id="4c6c5-102">方法 : Windows フォーム DataGrid コントロールを使用してマスター/詳細リストを作成する</span><span class="sxs-lookup"><span data-stu-id="4c6c5-102">How to: Create Master/Detail Lists with the Windows Forms DataGrid Control</span></span>
> [!NOTE]
> <span data-ttu-id="4c6c5-103"><xref:System.Windows.Forms.DataGridView> コントロールは、<xref:System.Windows.Forms.DataGrid> コントロールに代わると共に追加の機能を提供します。ただし、<xref:System.Windows.Forms.DataGrid> コントロールは、下位互換性を保つ目的および将来使用する目的で保持されます。</span><span class="sxs-lookup"><span data-stu-id="4c6c5-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="4c6c5-104">詳細については、「[Windows フォームの DataGridView コントロールと DataGrid コントロールの違いについて](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c6c5-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="4c6c5-105"><xref:System.Data.DataSet> に一連の関連テーブルが含まれている場合は、2つの <xref:System.Windows.Forms.DataGrid> コントロールを使用して、マスター/詳細形式でデータを表示できます。</span><span class="sxs-lookup"><span data-stu-id="4c6c5-105">If your <xref:System.Data.DataSet> contains a series of related tables, you can use two <xref:System.Windows.Forms.DataGrid> controls to display the data in a master/detail format.</span></span> <span data-ttu-id="4c6c5-106">1つの <xref:System.Windows.Forms.DataGrid> はマスターグリッドとして指定され、2つ目は詳細グリッドとして指定されます。</span><span class="sxs-lookup"><span data-stu-id="4c6c5-106">One <xref:System.Windows.Forms.DataGrid> is designated to be the master grid, and the second is designated to be the details grid.</span></span> <span data-ttu-id="4c6c5-107">マスターリストでエントリを選択すると、関連するすべての子エントリが詳細一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="4c6c5-107">When you select an entry in the master list, all of the related child entries are shown in the details list.</span></span> <span data-ttu-id="4c6c5-108">たとえば、<xref:System.Data.DataSet> に Customers テーブルと関連する Orders テーブルが含まれている場合は、Customers テーブルをマスターグリッドに指定し、Orders テーブルを詳細グリッドとして指定します。</span><span class="sxs-lookup"><span data-stu-id="4c6c5-108">For example, if your <xref:System.Data.DataSet> contains a Customers table and a related Orders table, you would specify the Customers table to be the master grid and the Orders table to be the details grid.</span></span> <span data-ttu-id="4c6c5-109">マスターグリッドから顧客を選択すると、Orders テーブル内のその顧客に関連付けられているすべての注文が詳細グリッドに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4c6c5-109">When a customer is selected from the master grid, all of the orders associated with that customer in the Orders table would be displayed in the details grid.</span></span>  
  
### <a name="to-set-a-masterdetail-relationship-programmatically"></a><span data-ttu-id="4c6c5-110">マスター/詳細関係をプログラムによって設定するには</span><span class="sxs-lookup"><span data-stu-id="4c6c5-110">To set a master/detail relationship programmatically</span></span>  
  
1. <span data-ttu-id="4c6c5-111">2つの新しい <xref:System.Windows.Forms.DataGrid> コントロールを作成し、それらのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="4c6c5-111">Create two new <xref:System.Windows.Forms.DataGrid> controls and set their properties.</span></span>  
  
2. <span data-ttu-id="4c6c5-112">テーブルをデータセットに追加します。</span><span class="sxs-lookup"><span data-stu-id="4c6c5-112">Add tables to the dataset.</span></span>  
  
3. <span data-ttu-id="4c6c5-113">作成するリレーションシップを表す <xref:System.Data.DataRelation> 型の変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="4c6c5-113">Declare a variable of type <xref:System.Data.DataRelation> to represent the relation you want to create.</span></span>  
  
4. <span data-ttu-id="4c6c5-114">リレーションシップの名前を指定し、2つのテーブルを関連付けるテーブル、列、およびアイテムを指定して、リレーションシップをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="4c6c5-114">Instantiate the relationship by specifying a name for the relationship and specifying the table, column, and item that will tie the two tables.</span></span>  
  
5. <span data-ttu-id="4c6c5-115"><xref:System.Data.DataSet> オブジェクトの <xref:System.Data.DataSet.Relations%2A> コレクションにリレーションシップを追加します。</span><span class="sxs-lookup"><span data-stu-id="4c6c5-115">Add the relationship to the <xref:System.Data.DataSet> object's <xref:System.Data.DataSet.Relations%2A> collection.</span></span>  
  
6. <span data-ttu-id="4c6c5-116"><xref:System.Windows.Forms.DataGrid> の <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> メソッドを使用して、各グリッドを <xref:System.Data.DataSet>にバインドします。</span><span class="sxs-lookup"><span data-stu-id="4c6c5-116">Use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method of the <xref:System.Windows.Forms.DataGrid> to bind each of the grids to the <xref:System.Data.DataSet>.</span></span>  
  
     <span data-ttu-id="4c6c5-117">次の例では、以前に生成された <xref:System.Data.DataSet> (`ds`) の Customers テーブルと Orders テーブルの間にマスター/詳細リレーションシップを設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4c6c5-117">The following example shows how to set a master/detail relationship between the Customers and Orders tables in a previously generated <xref:System.Data.DataSet> (`ds`).</span></span>  
  
    ```vb  
    Dim myDataRelation As DataRelation  
    myDataRelation = New DataRelation _  
       ("CustOrd", ds.Tables("Customers").Columns("CustomerID"), _  
       ds.Tables("Orders").Columns("CustomerID"))  
    ' Add the relation to the DataSet.  
    ds.Relations.Add(myDataRelation)  
    GridOrders.SetDataBinding(ds, "Customers")  
    GridDetails.SetDataBinding(ds, "Customers.CustOrd")  
    ```  
  
    ```csharp  
    DataRelation myDataRelation;  
    myDataRelation = new DataRelation("CustOrd", ds.Tables["Customers"].Columns["CustomerID"], ds.Tables["Orders"].Columns["CustomerID"]);  
    // Add the relation to the DataSet.  
    ds.Relations.Add(myDataRelation);  
    GridOrders.SetDataBinding(ds,"Customers");  
    GridDetails.SetDataBinding(ds,"Customers.CustOrd");  
    ```  
  
    ```cpp  
    DataRelation^ myDataRelation;  
    myDataRelation = gcnew DataRelation("CustOrd",  
       ds->Tables["Customers"]->Columns["CustomerID"],  
       ds->Tables["Orders"]->Columns["CustomerID"]);  
    // Add the relation to the DataSet.  
    ds->Relations->Add(myDataRelation);  
    GridOrders->SetDataBinding(ds, "Customers");  
    GridDetails->SetDataBinding(ds, "Customers.CustOrd");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4c6c5-118">参照</span><span class="sxs-lookup"><span data-stu-id="4c6c5-118">See also</span></span>

- [<span data-ttu-id="4c6c5-119">DataGrid コントロール</span><span class="sxs-lookup"><span data-stu-id="4c6c5-119">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
- [<span data-ttu-id="4c6c5-120">DataGrid コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="4c6c5-120">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)
- [<span data-ttu-id="4c6c5-121">方法: データ ソースに Windows フォーム DataGrid コントロールをバインドする</span><span class="sxs-lookup"><span data-stu-id="4c6c5-121">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
