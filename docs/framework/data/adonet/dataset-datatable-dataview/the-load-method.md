---
title: Load メソッド
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: e22e5812-89c6-41f0-9302-bb899a46dbff
ms.openlocfilehash: f1c819333225c22efb85946001a1fc8340d57989
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150728"
---
# <a name="the-load-method"></a><span data-ttu-id="e3f5a-102">Load メソッド</span><span class="sxs-lookup"><span data-stu-id="e3f5a-102">The Load Method</span></span>
<span data-ttu-id="e3f5a-103"><xref:System.Data.DataTable.Load%2A> メソッドを使用して、データ ソースの行を <xref:System.Data.DataTable> に読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="e3f5a-103">You can use the <xref:System.Data.DataTable.Load%2A> method to load a <xref:System.Data.DataTable> with rows from a data source.</span></span> <span data-ttu-id="e3f5a-104">これは、最も単純な形式で、単一のパラメーター **DataReader**を受け取るオーバーロードされたメソッドです。</span><span class="sxs-lookup"><span data-stu-id="e3f5a-104">This is an overloaded method which, in its simplest form, accepts a single parameter, a **DataReader**.</span></span> <span data-ttu-id="e3f5a-105">このフォームでは、単に行を**含む DataTable を**読み込みます。</span><span class="sxs-lookup"><span data-stu-id="e3f5a-105">In this form, it simply loads the **DataTable** with rows.</span></span> <span data-ttu-id="e3f5a-106">必要に応じて、データを**DataTable**に追加する方法を制御する**LoadOption**パラメーターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e3f5a-106">Optionally, you can specify the **LoadOption** parameter to control how data is added to the **DataTable**.</span></span>  
  
 <span data-ttu-id="e3f5a-107">**LoadOption**パラメーターは、データ ソースからの入力データとテーブル内の既存のデータを結合する方法を記述するため **、DataTable**に既にデータ行が含まれている場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="e3f5a-107">The **LoadOption** parameter is particularly useful in cases where the **DataTable** already contains rows of data, because it describes how incoming data from the data source will be combined with the data already in the table.</span></span> <span data-ttu-id="e3f5a-108">たとえば **、PreserveCurrentValues** (既定値) では、行が**DataTable**で**追加**済みとしてマークされている場合、**元**の値または各列がデータ ソースの一致する行の内容に設定されるように指定します。</span><span class="sxs-lookup"><span data-stu-id="e3f5a-108">For example, **PreserveCurrentValues** (the default) specifies that in cases where a row is marked as **Added** in the **DataTable**, the **Original** value or each column is set to the contents of the matching row from the data source.</span></span> <span data-ttu-id="e3f5a-109">**Current**値は、行が追加されたときに割り当てられた値を保持し、行の**RowState**が**変更**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="e3f5a-109">The **Current** value will retain the values assigned when the row was added, and the **RowState** of the row will be set to **Changed**.</span></span>  
  
 <span data-ttu-id="e3f5a-110"><xref:System.Data.LoadOption> 列挙値の簡単な説明を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="e3f5a-110">The following table gives a short description of the <xref:System.Data.LoadOption> enumeration values.</span></span>  
  
|<span data-ttu-id="e3f5a-111">LoadOption の値</span><span class="sxs-lookup"><span data-stu-id="e3f5a-111">LoadOption value</span></span>|<span data-ttu-id="e3f5a-112">説明</span><span class="sxs-lookup"><span data-stu-id="e3f5a-112">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="e3f5a-113">**OverwriteRow**</span><span class="sxs-lookup"><span data-stu-id="e3f5a-113">**OverwriteRow**</span></span>|<span data-ttu-id="e3f5a-114">受信行が**DataTable**内の行と同じ**主キー**値を持つ場合、各列の**元**の値と**現在**の値は、入力行の値に置き換えられ **、RowState**プロパティは**Unchanged**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="e3f5a-114">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** and **Current** values of each column are replaced with the values in the incoming row, and the **RowState** property is set to **Unchanged**.</span></span><br /><br /> <span data-ttu-id="e3f5a-115">データ ソースの行のうち、**データ テーブル**に存在しない行は **、RowState**値が **[未変更]** の値で追加されます。</span><span class="sxs-lookup"><span data-stu-id="e3f5a-115">Rows from the data source that do not already exist in the **DataTable** are added with a **RowState** value of **Unchanged**.</span></span><br /><br /> <span data-ttu-id="e3f5a-116">このオプションは、データ ソースの内容と一致するように**DataTable**の内容を更新します。</span><span class="sxs-lookup"><span data-stu-id="e3f5a-116">This option in effect refreshes the contents of the **DataTable** so that it matches the contents of the data source.</span></span>|  
|<span data-ttu-id="e3f5a-117">**PreserveCurrentValues (既定値)**</span><span class="sxs-lookup"><span data-stu-id="e3f5a-117">**PreserveCurrentValues (default)**</span></span>|<span data-ttu-id="e3f5a-118">受信行が**DataTable**内の行と同じ**主キー**値を持つ場合、**元**の値は受信行の内容に設定され、**現在**の値は変更されません。</span><span class="sxs-lookup"><span data-stu-id="e3f5a-118">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** value is set to the contents of the incoming row, and the **Current** value is not changed.</span></span><br /><br /> <span data-ttu-id="e3f5a-119">**RowState**が **[追加]** または **[変更済み**] の場合は、**変更済**みに設定されます。</span><span class="sxs-lookup"><span data-stu-id="e3f5a-119">If the **RowState** is **Added** or **Modified**, it is set to **Modified**.</span></span><br /><br /> <span data-ttu-id="e3f5a-120">**RowState**が**削除された**場合は、**削除された**ままになります。</span><span class="sxs-lookup"><span data-stu-id="e3f5a-120">If the **RowState** was **Deleted**, it remains **Deleted**.</span></span><br /><br /> <span data-ttu-id="e3f5a-121">データ ソースの行が追加され、**データ テーブル**に存在しない行が追加され **、RowState**が**未変更**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="e3f5a-121">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Unchanged**.</span></span>|  
|<span data-ttu-id="e3f5a-122">**UpdateCurrentValues**</span><span class="sxs-lookup"><span data-stu-id="e3f5a-122">**UpdateCurrentValues**</span></span>|<span data-ttu-id="e3f5a-123">受信行が**DataTable**内の既に存在する行と同じ**主キー**値を持つ場合 **、現在**の値は**元**の値にコピーされ、**現在**の値は、受信行の内容に設定されます。</span><span class="sxs-lookup"><span data-stu-id="e3f5a-123">If incoming rows have the same **PrimaryKey** value as the row already in the **DataTable**, the **Current** value is copied to the **Original** value, and the **Current** value is then set to the contents of the incoming row.</span></span><br /><br /> <span data-ttu-id="e3f5a-124">**データ テーブル**の**RowState**が**追加**された場合 **、RowState**は**追加された**ままになります。</span><span class="sxs-lookup"><span data-stu-id="e3f5a-124">If the **RowState** in the **DataTable** was **Added**, the **RowState** remains **Added**.</span></span> <span data-ttu-id="e3f5a-125">**更新または\*\*\*\*削除済**みとしてマークされた行の**場合、RowState**は**変更済み**になります。</span><span class="sxs-lookup"><span data-stu-id="e3f5a-125">For rows marked as **Modified** or **Deleted**, the **RowState** is **Modified**.</span></span><br /><br /> <span data-ttu-id="e3f5a-126">データ ソースの行が追加され、**データ テーブル**に存在しない、 **RowState**が**追加に**設定されます。</span><span class="sxs-lookup"><span data-stu-id="e3f5a-126">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Added**.</span></span>|  
  
 <span data-ttu-id="e3f5a-127">次のサンプルでは **、Load**メソッドを使用して **、Northwind**データベース内の従業員の誕生日の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="e3f5a-127">The following sample uses the **Load** method to display a list of birthdays for the employees in the **Northwind** database.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e3f5a-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="e3f5a-128">See also</span></span>

- [<span data-ttu-id="e3f5a-129">DataTable 内のデータの操作</span><span class="sxs-lookup"><span data-stu-id="e3f5a-129">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="e3f5a-130">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="e3f5a-130">ADO.NET Overview</span></span>](../ado-net-overview.md)
