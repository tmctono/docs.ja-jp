---
title: '方法: Windows フォーム DataGrid コントロールでマスター/詳細リストを作成します。'
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
ms.openlocfilehash: 92b4a7d9513ce0ec9b7c02f57c23fa4267fb26ad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052171"
---
# <a name="how-to-create-masterdetail-lists-with-the-windows-forms-datagrid-control"></a><span data-ttu-id="bfdda-102">方法: Windows フォーム DataGrid コントロールを使用してマスター/詳細リストを作成する</span><span class="sxs-lookup"><span data-stu-id="bfdda-102">How to: Create Master/Detail Lists with the Windows Forms DataGrid Control</span></span>
> [!NOTE]
>  <span data-ttu-id="bfdda-103"><xref:System.Windows.Forms.DataGridView> コントロールは、<xref:System.Windows.Forms.DataGrid> コントロールに代わると共に追加の機能を提供します。ただし、<xref:System.Windows.Forms.DataGrid> コントロールは、下位互換性を保つ目的および将来使用する目的で保持されます。</span><span class="sxs-lookup"><span data-stu-id="bfdda-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="bfdda-104">詳細については、「[Windows フォームの DataGridView コントロールと DataGrid コントロールの違いについて](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfdda-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="bfdda-105">場合、<xref:System.Data.DataSet>は一連の関連テーブルの 2 つ使用できます<xref:System.Windows.Forms.DataGrid>マスター/詳細形式でデータを表示するコントロール。</span><span class="sxs-lookup"><span data-stu-id="bfdda-105">If your <xref:System.Data.DataSet> contains a series of related tables, you can use two <xref:System.Windows.Forms.DataGrid> controls to display the data in a master/detail format.</span></span> <span data-ttu-id="bfdda-106">1 つ<xref:System.Windows.Forms.DataGrid>マスター グリッドに指定し、2 つ目は詳細グリッドに指定します。</span><span class="sxs-lookup"><span data-stu-id="bfdda-106">One <xref:System.Windows.Forms.DataGrid> is designated to be the master grid, and the second is designated to be the details grid.</span></span> <span data-ttu-id="bfdda-107">マスター リストのエントリを選択すると、すべての関連する子エントリ、詳細の一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="bfdda-107">When you select an entry in the master list, all of the related child entries are shown in the details list.</span></span> <span data-ttu-id="bfdda-108">たとえば場合、 <xref:System.Data.DataSet> Customers テーブルと関連する Orders テーブルを含むマスター グリッドに Customers テーブルと Orders テーブル詳細グリッドに指定します。</span><span class="sxs-lookup"><span data-stu-id="bfdda-108">For example, if your <xref:System.Data.DataSet> contains a Customers table and a related Orders table, you would specify the Customers table to be the master grid and the Orders table to be the details grid.</span></span> <span data-ttu-id="bfdda-109">マスター グリッドから顧客を選択すると、すべての Orders テーブルでは、その顧客に関連付けられている注文の詳細グリッドで表示されます。</span><span class="sxs-lookup"><span data-stu-id="bfdda-109">When a customer is selected from the master grid, all of the orders associated with that customer in the Orders table would be displayed in the details grid.</span></span>  
  
### <a name="to-set-a-masterdetail-relationship-programmatically"></a><span data-ttu-id="bfdda-110">プログラムでマスター/詳細リレーションシップを設定するには</span><span class="sxs-lookup"><span data-stu-id="bfdda-110">To set a master/detail relationship programmatically</span></span>  
  
1. <span data-ttu-id="bfdda-111">新しい 2 つ作成<xref:System.Windows.Forms.DataGrid>を制御し、そのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="bfdda-111">Create two new <xref:System.Windows.Forms.DataGrid> controls and set their properties.</span></span>  
  
2. <span data-ttu-id="bfdda-112">データセットにテーブルを追加します。</span><span class="sxs-lookup"><span data-stu-id="bfdda-112">Add tables to the dataset.</span></span>  
  
3. <span data-ttu-id="bfdda-113">型の変数を宣言<xref:System.Data.DataRelation>を作成するリレーションシップを表します。</span><span class="sxs-lookup"><span data-stu-id="bfdda-113">Declare a variable of type <xref:System.Data.DataRelation> to represent the relation you want to create.</span></span>  
  
4. <span data-ttu-id="bfdda-114">リレーションシップの名前を指定して、テーブル、列、および 2 つのテーブルに関連付けられるアイテムを指定することによって、リレーションシップをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="bfdda-114">Instantiate the relationship by specifying a name for the relationship and specifying the table, column, and item that will tie the two tables.</span></span>  
  
5. <span data-ttu-id="bfdda-115">リレーションシップを追加、<xref:System.Data.DataSet>オブジェクトの<xref:System.Data.DataSet.Relations%2A>コレクション。</span><span class="sxs-lookup"><span data-stu-id="bfdda-115">Add the relationship to the <xref:System.Data.DataSet> object's <xref:System.Data.DataSet.Relations%2A> collection.</span></span>  
  
6. <span data-ttu-id="bfdda-116">使用して、<xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>のメソッド、<xref:System.Windows.Forms.DataGrid>のグリッドの各バインドに、<xref:System.Data.DataSet>します。</span><span class="sxs-lookup"><span data-stu-id="bfdda-116">Use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method of the <xref:System.Windows.Forms.DataGrid> to bind each of the grids to the <xref:System.Data.DataSet>.</span></span>  
  
     <span data-ttu-id="bfdda-117">次の例は、以前に生成されたで顧客と注文テーブル間のマスター/詳細リレーションシップを設定する方法を示します<xref:System.Data.DataSet>(`ds`)。</span><span class="sxs-lookup"><span data-stu-id="bfdda-117">The following example shows how to set a master/detail relationship between the Customers and Orders tables in a previously generated <xref:System.Data.DataSet> (`ds`).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bfdda-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="bfdda-118">See also</span></span>

- [<span data-ttu-id="bfdda-119">DataGrid コントロール</span><span class="sxs-lookup"><span data-stu-id="bfdda-119">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
- [<span data-ttu-id="bfdda-120">DataGrid コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="bfdda-120">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)
- [<span data-ttu-id="bfdda-121">方法: Windows フォームの DataGrid コントロールをデータ ソースにバインドします。</span><span class="sxs-lookup"><span data-stu-id="bfdda-121">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
