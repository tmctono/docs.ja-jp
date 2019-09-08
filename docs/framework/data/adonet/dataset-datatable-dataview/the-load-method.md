---
title: Load メソッド
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: e22e5812-89c6-41f0-9302-bb899a46dbff
ms.openlocfilehash: da0695aff9447355b1fc44a033c1b4a1cc224435
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785886"
---
# <a name="the-load-method"></a><span data-ttu-id="7bbb3-102">Load メソッド</span><span class="sxs-lookup"><span data-stu-id="7bbb3-102">The Load Method</span></span>
<span data-ttu-id="7bbb3-103"><xref:System.Data.DataTable.Load%2A> メソッドを使用して、データ ソースの行を <xref:System.Data.DataTable> に読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="7bbb3-103">You can use the <xref:System.Data.DataTable.Load%2A> method to load a <xref:System.Data.DataTable> with rows from a data source.</span></span> <span data-ttu-id="7bbb3-104">これはオーバーロードされたメソッドであり、最も単純な形式で、1つのパラメーターである**DataReader**を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="7bbb3-104">This is an overloaded method which, in its simplest form, accepts a single parameter, a **DataReader**.</span></span> <span data-ttu-id="7bbb3-105">この形式では、単に行を含む**DataTable**が読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="7bbb3-105">In this form, it simply loads the **DataTable** with rows.</span></span> <span data-ttu-id="7bbb3-106">必要に応じて、 **LoadOption**パラメーターを指定して、データを**DataTable**に追加する方法を制御できます。</span><span class="sxs-lookup"><span data-stu-id="7bbb3-106">Optionally, you can specify the **LoadOption** parameter to control how data is added to the **DataTable**.</span></span>  
  
 <span data-ttu-id="7bbb3-107">**LoadOption**パラメーターは、 **DataTable**に既にデータ行が含まれている場合に特に便利です。これは、データソースからの受信データをテーブル内の既存のデータと結合する方法を記述するためです。</span><span class="sxs-lookup"><span data-stu-id="7bbb3-107">The **LoadOption** parameter is particularly useful in cases where the **DataTable** already contains rows of data, because it describes how incoming data from the data source will be combined with the data already in the table.</span></span> <span data-ttu-id="7bbb3-108">たとえば、 **PreserveCurrentValues** (既定値) は、行が**DataTable**に**追加さ**れたとしてマークされている場合に、**元**の値または各列がデータソースの一致する行の内容に設定されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="7bbb3-108">For example, **PreserveCurrentValues** (the default) specifies that in cases where a row is marked as **Added** in the **DataTable**, the **Original** value or each column is set to the contents of the matching row from the data source.</span></span> <span data-ttu-id="7bbb3-109">**現在**の値は、行が追加されたときに割り当てられた値を保持し、その行の**RowState**は**Changed**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="7bbb3-109">The **Current** value will retain the values assigned when the row was added, and the **RowState** of the row will be set to **Changed**.</span></span>  
  
 <span data-ttu-id="7bbb3-110"><xref:System.Data.LoadOption> 列挙値の簡単な説明を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="7bbb3-110">The following table gives a short description of the <xref:System.Data.LoadOption> enumeration values.</span></span>  
  
|<span data-ttu-id="7bbb3-111">LoadOption の値</span><span class="sxs-lookup"><span data-stu-id="7bbb3-111">LoadOption value</span></span>|<span data-ttu-id="7bbb3-112">説明</span><span class="sxs-lookup"><span data-stu-id="7bbb3-112">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="7bbb3-113">**OverwriteRow**</span><span class="sxs-lookup"><span data-stu-id="7bbb3-113">**OverwriteRow**</span></span>|<span data-ttu-id="7bbb3-114">受信した行の**PrimaryKey**値が**DataTable**に既に存在する行と同じ場合、各列の**元**の値と**現在**の値は、受信した行の値に置き換えられ、 **RowState**プロパティはに設定されます。**変更なし**。</span><span class="sxs-lookup"><span data-stu-id="7bbb3-114">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** and **Current** values of each column are replaced with the values in the incoming row, and the **RowState** property is set to **Unchanged**.</span></span><br /><br /> <span data-ttu-id="7bbb3-115">**DataTable**にまだ存在しないデータソースからの行は、 **RowState**値が**Unchanged のまま**追加されます。</span><span class="sxs-lookup"><span data-stu-id="7bbb3-115">Rows from the data source that do not already exist in the **DataTable** are added with a **RowState** value of **Unchanged**.</span></span><br /><br /> <span data-ttu-id="7bbb3-116">このオプションを有効にすると、データソースの内容と一致するように**DataTable**の内容が更新されます。</span><span class="sxs-lookup"><span data-stu-id="7bbb3-116">This option in effect refreshes the contents of the **DataTable** so that it matches the contents of the data source.</span></span>|  
|<span data-ttu-id="7bbb3-117">**PreserveCurrentValues (既定値)**</span><span class="sxs-lookup"><span data-stu-id="7bbb3-117">**PreserveCurrentValues (default)**</span></span>|<span data-ttu-id="7bbb3-118">入力方向の行の**PrimaryKey**値が**DataTable**に既に存在する行と同じ場合、**元**の値は受信した行の内容に設定され、**現在**の値は変更されません。</span><span class="sxs-lookup"><span data-stu-id="7bbb3-118">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** value is set to the contents of the incoming row, and the **Current** value is not changed.</span></span><br /><br /> <span data-ttu-id="7bbb3-119">**RowState**が**追加**または**変更**されると、 **[変更済み]** に設定されます。</span><span class="sxs-lookup"><span data-stu-id="7bbb3-119">If the **RowState** is **Added** or **Modified**, it is set to **Modified**.</span></span><br /><br /> <span data-ttu-id="7bbb3-120">**RowState**が**削除**された場合、**削除**されたままになります。</span><span class="sxs-lookup"><span data-stu-id="7bbb3-120">If the **RowState** was **Deleted**, it remains **Deleted**.</span></span><br /><br /> <span data-ttu-id="7bbb3-121">**DataTable**にまだ存在しないデータソースからの行が追加され、 **RowState**は**Unchanged**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="7bbb3-121">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Unchanged**.</span></span>|  
|<span data-ttu-id="7bbb3-122">**UpdateCurrentValues**</span><span class="sxs-lookup"><span data-stu-id="7bbb3-122">**UpdateCurrentValues**</span></span>|<span data-ttu-id="7bbb3-123">受信した行の**PrimaryKey**値が**DataTable**内の既存の行と同じ場合、**現在**の値が**元**の値にコピーされ、**現在**の値が受信した行の内容に設定されます。</span><span class="sxs-lookup"><span data-stu-id="7bbb3-123">If incoming rows have the same **PrimaryKey** value as the row already in the **DataTable**, the **Current** value is copied to the **Original** value, and the **Current** value is then set to the contents of the incoming row.</span></span><br /><br /> <span data-ttu-id="7bbb3-124">**DataTable**の**RowState**が**追加**された場合、 **RowState**は**追加さ**れたままになります。</span><span class="sxs-lookup"><span data-stu-id="7bbb3-124">If the **RowState** in the **DataTable** was **Added**, the **RowState** remains **Added**.</span></span> <span data-ttu-id="7bbb3-125">**変更**または**削除済み**としてマークされた行については、 **RowState**が**変更**されます。</span><span class="sxs-lookup"><span data-stu-id="7bbb3-125">For rows marked as **Modified** or **Deleted**, the **RowState** is **Modified**.</span></span><br /><br /> <span data-ttu-id="7bbb3-126">**DataTable**に存在しないデータソースの行が追加され、 **RowState**が**追加**されるように設定されます。</span><span class="sxs-lookup"><span data-stu-id="7bbb3-126">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Added**.</span></span>|  
  
 <span data-ttu-id="7bbb3-127">次のサンプルでは、 **Load**メソッドを使用して、 **Northwind**データベース内の従業員の誕生日の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="7bbb3-127">The following sample uses the **Load** method to display a list of birthdays for the employees in the **Northwind** database.</span></span>  
  
```vb  
Private Sub LoadBirthdays(ByVal connectionString As String)  
    ' Assumes that connectionString is a valid connection string  
    ' to the Northwind database on SQL Server.  
    Dim queryString As String = _  
    "SELECT LastName, FirstName, BirthDate " & _  
      " FROM dbo.Employees " & _  
      "ORDER BY BirthDate, LastName, FirstName"  
  
    ' Open and fill a DataSet.   
    Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
        queryString, connectionString)  
    Dim employees As New DataSet  
    adapter.Fill(employees, "Employees")  
  
    ' Create a SqlDataReader for use with the Load Method.  
    Dim reader As DataTableReader = employees.GetDataReader()  
  
    ' Create an instance of DataTable and assign the first  
    ' DataTable in the DataSet.Tables collection to it.  
    Dim dataTableEmp As DataTable = employees.Tables(0)  
  
    ' Fill the DataTable with data by calling Load and  
    ' passing the SqlDataReader.  
    dataTableEmp.Load(reader, LoadOption.OverwriteRow)  
  
    ' Loop through the rows collection and display the values  
    ' in the console window.  
    Dim employeeRow As DataRow  
    For Each employeeRow In dataTableEmp.Rows  
        Console.WriteLine("{0:MM\\dd\\yyyy}" & ControlChars.Tab & _  
          "{1}, {2}", _  
          employeeRow("BirthDate"), _  
          employeeRow("LastName"), _  
          employeeRow("FirstName"))  
    Next employeeRow  
  
    ' Keep the window opened to view the contents.  
    Console.ReadLine()  
End Sub  
```  
  
## <a name="see-also"></a><span data-ttu-id="7bbb3-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="7bbb3-128">See also</span></span>

- [<span data-ttu-id="7bbb3-129">DataTable 内のデータの操作</span><span class="sxs-lookup"><span data-stu-id="7bbb3-129">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="7bbb3-130">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="7bbb3-130">ADO.NET Overview</span></span>](../ado-net-overview.md)
