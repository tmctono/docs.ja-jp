---
title: '方法: Windows フォーム DataGrid コントロールに表示されるデータを実行時に変更する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DataGrid control [Windows Forms], dynamically changing at run time
- DataGrid control [Windows Forms], data binding
- cells [Windows Forms], changing DataGrid cell values
ms.assetid: 0c7a6d00-30de-416e-8223-0a81ddb4c1f8
ms.openlocfilehash: 60ba1e9304320346d505f3f73e1ba93ff6edab63
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59315856"
---
# <a name="how-to-change-displayed-data-at-run-time-in-the-windows-forms-datagrid-control"></a><span data-ttu-id="68c42-102">方法: Windows フォーム DataGrid コントロールに表示されるデータを実行時に変更する</span><span class="sxs-lookup"><span data-stu-id="68c42-102">How to: Change Displayed Data at Run Time in the Windows Forms DataGrid Control</span></span>
> [!NOTE]
>  <span data-ttu-id="68c42-103"><xref:System.Windows.Forms.DataGridView> コントロールは、<xref:System.Windows.Forms.DataGrid> コントロールに代わると共に追加の機能を提供します。ただし、<xref:System.Windows.Forms.DataGrid> コントロールは、下位互換性を保つ目的および将来使用する目的で保持されます。</span><span class="sxs-lookup"><span data-stu-id="68c42-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="68c42-104">詳細については、「[Windows フォームの DataGridView コントロールと DataGrid コントロールの違いについて](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68c42-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="68c42-105">Windows フォームを作成した後<xref:System.Windows.Forms.DataGrid>デザイン時機能を使用することも考えの要素を動的に変更する、<xref:System.Data.DataSet>実行時にグリッドのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="68c42-105">After you have created a Windows Forms <xref:System.Windows.Forms.DataGrid> using the design-time features, you may also wish to dynamically change elements of the <xref:System.Data.DataSet> object of the grid at run time.</span></span> <span data-ttu-id="68c42-106">これは、テーブルのいずれかの個別の値の変更を含めることができますかにバインドされているデータ ソースを変更する、<xref:System.Windows.Forms.DataGrid>コントロール。</span><span class="sxs-lookup"><span data-stu-id="68c42-106">This can include changes to either individual values of the table or changing which data source is bound to the <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="68c42-107">個々 の値への変更が完了したら、<xref:System.Data.DataSet>オブジェクトは、<xref:System.Windows.Forms.DataGrid>コントロール。</span><span class="sxs-lookup"><span data-stu-id="68c42-107">Changes to individual values are done through the <xref:System.Data.DataSet> object, not the <xref:System.Windows.Forms.DataGrid> control.</span></span>  
  
### <a name="to-change-data-programmatically"></a><span data-ttu-id="68c42-108">プログラムでデータを変更するには</span><span class="sxs-lookup"><span data-stu-id="68c42-108">To change data programmatically</span></span>  
  
1. <span data-ttu-id="68c42-109">目的のテーブルの指定、<xref:System.Data.DataSet>オブジェクトおよび必要な行しテーブルのフィールドし、セルを新しい値に設定します。</span><span class="sxs-lookup"><span data-stu-id="68c42-109">Specify the desired table from the <xref:System.Data.DataSet> object and the desired row and field from the table and set the cell equal to the new value.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="68c42-110">最初のテーブルを指定する、<xref:System.Data.DataSet>か、テーブルの最初の行は 0 を使用します。</span><span class="sxs-lookup"><span data-stu-id="68c42-110">To specify the first table of the <xref:System.Data.DataSet> or the first row of the table, use 0.</span></span>  
  
     <span data-ttu-id="68c42-111">次の例をクリックして、データセットの最初のテーブルの最初の行の 2 番目のエントリを変更する方法を示しています。`Button1`します。</span><span class="sxs-lookup"><span data-stu-id="68c42-111">The following example shows how to change the second entry of the first row of the first table of a dataset by clicking `Button1`.</span></span> <span data-ttu-id="68c42-112"><xref:System.Data.DataSet> (`ds`) とテーブル (`0`と`1`) 以前に作成されました。</span><span class="sxs-lookup"><span data-stu-id="68c42-112">The <xref:System.Data.DataSet> (`ds`) and Tables (`0` and `1`) were previously created.</span></span>  
  
    ```vb  
    Protected Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       ds.tables(0).rows(0)(1) = "NewEntry"  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       ds.Tables[0].Rows[0][1]="NewEntry";  
    }  
    ```  
  
    ```cpp  
    private:   
       void button1_Click(System::Object^ sender, System::EventArgs^ e)  
       {  
          dataSet1->Tables[0]->Rows[0][1] = "NewEntry";  
       }  
    ```  
  
     <span data-ttu-id="68c42-113">(Visual c#、 [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)])、イベント ハンドラーを登録するフォームのコンス トラクターで、次のコードを配置します。</span><span class="sxs-lookup"><span data-stu-id="68c42-113">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=  
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     <span data-ttu-id="68c42-114">実行時に使用することができます、<xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>にバインドするメソッド、<xref:System.Windows.Forms.DataGrid>別のデータ ソースを制御します。</span><span class="sxs-lookup"><span data-stu-id="68c42-114">At run time you can use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to bind the <xref:System.Windows.Forms.DataGrid> control to a different data source.</span></span> <span data-ttu-id="68c42-115">たとえば、いくつかする必要があります[!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]データ コントロールでは、それぞれ別のデータベースに接続します。</span><span class="sxs-lookup"><span data-stu-id="68c42-115">For example, you may have several [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] data controls, each connected to a different database.</span></span>  
  
### <a name="to-change-the-datasource-programmatically"></a><span data-ttu-id="68c42-116">データ ソースをプログラムで変更するには</span><span class="sxs-lookup"><span data-stu-id="68c42-116">To change the DataSource programmatically</span></span>  
  
1. <span data-ttu-id="68c42-117">設定、<xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>メソッドをデータ ソースにバインドするテーブルの名前。</span><span class="sxs-lookup"><span data-stu-id="68c42-117">Set the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to the name of the data source and table you want to bind to.</span></span>  
  
     <span data-ttu-id="68c42-118">次の例は、日付を使用してソースを変更する方法を示します、<xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>メソッドを[!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]Pubs データベースの Authors テーブルに接続されているデータ コントロール (adoPubsAuthors)。</span><span class="sxs-lookup"><span data-stu-id="68c42-118">The following example shows how to change the date source using the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to an [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] data control (adoPubsAuthors) that is connected to the Authors table in the Pubs database.</span></span>  
  
    ```vb  
    Private Sub ResetSource()  
       DataGrid1.SetDataBinding(adoPubsAuthors, "Authors")  
    End Sub  
    ```  
  
    ```csharp  
    private void ResetSource()  
    {  
       DataGrid1.SetDataBinding(adoPubsAuthors, "Authors");  
    }  
    ```  
  
    ```cpp  
    private:  
       void ResetSource()  
       {  
          dataGrid1->SetDataBinding(adoPubsAuthors, "Authors");  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="68c42-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="68c42-119">See also</span></span>

- [<span data-ttu-id="68c42-120">ADO.NET データセット</span><span class="sxs-lookup"><span data-stu-id="68c42-120">ADO.NET DataSets</span></span>](../../data/adonet/ado-net-datasets.md)
- [<span data-ttu-id="68c42-121">方法: 削除、または Windows フォームの DataGrid コントロール内の列を非表示にします。</span><span class="sxs-lookup"><span data-stu-id="68c42-121">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="68c42-122">方法: Windows フォームの DataGrid コントロールにテーブルと列を追加します。</span><span class="sxs-lookup"><span data-stu-id="68c42-122">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="68c42-123">方法: Windows フォームの DataGrid コントロールをデータ ソースにバインドします。</span><span class="sxs-lookup"><span data-stu-id="68c42-123">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
