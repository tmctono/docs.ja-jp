---
title: '方法: Windows フォームの DataGrid コントロールを使用して入力データを検証する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid control [Windows Forms], examples
- user input [Windows Forms], validating
- examples [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], validating input
- validation [Windows Forms], user input
ms.assetid: f1e9c3a0-d0a1-4893-a615-b4b0db046c63
ms.openlocfilehash: dc8c8f157e6673c1bddc68bfb511683e6d2b99be
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796475"
---
# <a name="how-to-validate-input-with-the-windows-forms-datagrid-control"></a><span data-ttu-id="c5942-102">方法: Windows フォームの DataGrid コントロールを使用して入力データを検証する</span><span class="sxs-lookup"><span data-stu-id="c5942-102">How to: Validate Input with the Windows Forms DataGrid Control</span></span>

> [!NOTE]
> <span data-ttu-id="c5942-103"><xref:System.Windows.Forms.DataGridView> コントロールは、<xref:System.Windows.Forms.DataGrid> コントロールに代わると共に追加の機能を提供します。ただし、<xref:System.Windows.Forms.DataGrid> コントロールは、下位互換性を保つ目的および将来使用する目的で保持されます。</span><span class="sxs-lookup"><span data-stu-id="c5942-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="c5942-104">詳細については、「[Windows フォームの DataGridView コントロールと DataGrid コントロールの違いについて](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5942-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>

<span data-ttu-id="c5942-105">Windows フォームの使用可能な 2 種類の入力の検証は<xref:System.Windows.Forms.DataGrid>コントロール。</span><span class="sxs-lookup"><span data-stu-id="c5942-105">There are two types of input validation available for the Windows Forms <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="c5942-106">ユーザーがセル、整数、文字列などの許容できないデータ型の値を入力する場合は、古い値を持つ新しい無効な値が置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="c5942-106">If the user attempts to enter a value that is of an unacceptable data type for the cell, for example a string into an integer, the new invalid value is replaced with the old value.</span></span> <span data-ttu-id="c5942-107">この種類の入力の検証は、自動的には行われ、カスタマイズすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c5942-107">This kind of input validation is done automatically and cannot be customized.</span></span>

<span data-ttu-id="c5942-108">以上の値を 1、または不適切な文字列にする必要があるフィールドの値が 0 など、あらゆる許容できないデータを拒否する他の種類の入力の検証を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c5942-108">The other type of input validation can be used to reject any unacceptable data, for example a 0 value in a field that must be greater than or equal to 1, or an inappropriate string.</span></span> <span data-ttu-id="c5942-109">これは、データセット内のイベント ハンドラーを記述することで、<xref:System.Data.DataTable.ColumnChanging>または<xref:System.Data.DataTable.RowChanging>イベント。</span><span class="sxs-lookup"><span data-stu-id="c5942-109">This is done in the dataset by writing an event handler for the <xref:System.Data.DataTable.ColumnChanging> or <xref:System.Data.DataTable.RowChanging> event.</span></span> <span data-ttu-id="c5942-110">使用して次の例、<xref:System.Data.DataTable.ColumnChanging>イベント不正な値が"Product"列の具体的には許可されていないためです。</span><span class="sxs-lookup"><span data-stu-id="c5942-110">The example below uses the <xref:System.Data.DataTable.ColumnChanging> event because the unacceptable value is disallowed for the "Product" column in particular.</span></span> <span data-ttu-id="c5942-111">使用する場合があります、 <xref:System.Data.DataTable.RowChanging> 「終了日」の列の値が同じ行の「開始日」の列より後であるかを確認するためのイベント。</span><span class="sxs-lookup"><span data-stu-id="c5942-111">You might use the <xref:System.Data.DataTable.RowChanging> event for checking that the value of an "End Date" column is later than the "Start Date" column in the same row.</span></span>

## <a name="to-validate-user-input"></a><span data-ttu-id="c5942-112">ユーザー入力を検証するには</span><span class="sxs-lookup"><span data-stu-id="c5942-112">To validate user input</span></span>

1. <span data-ttu-id="c5942-113">処理するコードを記述、<xref:System.Data.DataTable.ColumnChanging>イベントを該当するテーブル。</span><span class="sxs-lookup"><span data-stu-id="c5942-113">Write code to handle the <xref:System.Data.DataTable.ColumnChanging> event for the appropriate table.</span></span> <span data-ttu-id="c5942-114">不適切な入力が検出されたときに呼び出す、<xref:System.Data.DataRow.SetColumnError%2A>のメソッド、<xref:System.Data.DataRow>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c5942-114">When inappropriate input is detected, call the <xref:System.Data.DataRow.SetColumnError%2A> method of the <xref:System.Data.DataRow> object.</span></span>

    ```vb
    Private Sub Customers_ColumnChanging(ByVal sender As Object, _
    ByVal e As System.Data.DataColumnChangeEventArgs)
       ' Only check for errors in the Product column
       If (e.Column.ColumnName.Equals("Product")) Then
          ' Do not allow "Automobile" as a product.
          If CType(e.ProposedValue, String) = "Automobile" Then
             Dim badValue As Object = e.ProposedValue
             e.ProposedValue = "Bad Data"
             e.Row.RowError = "The Product column contains an error"
             e.Row.SetColumnError(e.Column, "Product cannot be " & _
             CType(badValue, String))
          End If
       End If
    End Sub
    ```

    ```csharp
    //Handle column changing events on the Customers table
    private void Customers_ColumnChanging(object sender, System.Data.DataColumnChangeEventArgs e) {

       //Only check for errors in the Product column
       if (e.Column.ColumnName.Equals("Product")) {

          //Do not allow "Automobile" as a product
          if (e.ProposedValue.Equals("Automobile")) {
             object badValue = e.ProposedValue;
             e.ProposedValue = "Bad Data";
             e.Row.RowError = "The Product column contains an error";
             e.Row.SetColumnError(e.Column, "Product cannot be " + badValue);
          }
       }
    }
    ```

2. <span data-ttu-id="c5942-115">イベントにイベント ハンドラーを接続します。</span><span class="sxs-lookup"><span data-stu-id="c5942-115">Connect the event handler to the event.</span></span>

    <span data-ttu-id="c5942-116">フォームのコード内で、次の場所<xref:System.Windows.Forms.Form.Load>イベントまたはそのコンス トラクター。</span><span class="sxs-lookup"><span data-stu-id="c5942-116">Place the following code within either the form's <xref:System.Windows.Forms.Form.Load> event or its constructor.</span></span>

    ```vb
    ' Assumes the grid is bound to a dataset called customersDataSet1
    ' with a table called Customers.
    ' Put this code in the form's Load event or its constructor.
    AddHandler customersDataSet1.Tables("Customers").ColumnChanging, AddressOf Customers_ColumnChanging
    ```

    ```csharp
    // Assumes the grid is bound to a dataset called customersDataSet1
    // with a table called Customers.
    // Put this code in the form's Load event or its constructor.
    customersDataSet1.Tables["Customers"].ColumnChanging += new DataColumnChangeEventHandler(this.Customers_ColumnChanging);
    ```

## <a name="see-also"></a><span data-ttu-id="c5942-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="c5942-117">See also</span></span>

- <xref:System.Windows.Forms.DataGrid>
- <xref:System.Data.DataTable.ColumnChanging>
- <xref:System.Data.DataRow.SetColumnError%2A>
- [<span data-ttu-id="c5942-118">DataGrid コントロール</span><span class="sxs-lookup"><span data-stu-id="c5942-118">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
