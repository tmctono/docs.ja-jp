---
title: Load メソッド
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: e22e5812-89c6-41f0-9302-bb899a46dbff
ms.openlocfilehash: f1c819333225c22efb85946001a1fc8340d57989
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150728"
---
# <a name="the-load-method"></a><span data-ttu-id="08771-102">Load メソッド</span><span class="sxs-lookup"><span data-stu-id="08771-102">The Load Method</span></span>
<span data-ttu-id="08771-103"><xref:System.Data.DataTable.Load%2A> メソッドを使用して、データ ソースの行を <xref:System.Data.DataTable> に読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="08771-103">You can use the <xref:System.Data.DataTable.Load%2A> method to load a <xref:System.Data.DataTable> with rows from a data source.</span></span> <span data-ttu-id="08771-104">これはオーバーロードされたメソッドで、最も単純な形式で単一の **DataReader** パラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="08771-104">This is an overloaded method which, in its simplest form, accepts a single parameter, a **DataReader**.</span></span> <span data-ttu-id="08771-105">この形式により、このメソッドでは **DataTable** に対する行の読み込みのみが行われます。</span><span class="sxs-lookup"><span data-stu-id="08771-105">In this form, it simply loads the **DataTable** with rows.</span></span> <span data-ttu-id="08771-106">または、**LoadOption** パラメーターを指定して **DataTable** へのデータの追加方法を制御することもできます。</span><span class="sxs-lookup"><span data-stu-id="08771-106">Optionally, you can specify the **LoadOption** parameter to control how data is added to the **DataTable**.</span></span>  
  
 <span data-ttu-id="08771-107">**LoadOption** パラメーターは、データ ソースからの受信データをテーブルに既に格納されているデータと組み合わせる方法が記述されているため、**DataTable** に既にデータ行が含まれている場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="08771-107">The **LoadOption** parameter is particularly useful in cases where the **DataTable** already contains rows of data, because it describes how incoming data from the data source will be combined with the data already in the table.</span></span> <span data-ttu-id="08771-108">たとえば、**PreserveCurrentValues** (既定値) は、**DataTable** の行が **Added** としてマークされ、データ ソースの行に一致する内容に対して **Original** 値または各列が設定されている場合に指定します。</span><span class="sxs-lookup"><span data-stu-id="08771-108">For example, **PreserveCurrentValues** (the default) specifies that in cases where a row is marked as **Added** in the **DataTable**, the **Original** value or each column is set to the contents of the matching row from the data source.</span></span> <span data-ttu-id="08771-109">**Current** 値は、行が追加されたときに割り当てられた値が保持され、その行の **RowState** は **Changed** に設定されます。</span><span class="sxs-lookup"><span data-stu-id="08771-109">The **Current** value will retain the values assigned when the row was added, and the **RowState** of the row will be set to **Changed**.</span></span>  
  
 <span data-ttu-id="08771-110"><xref:System.Data.LoadOption> 列挙値の簡単な説明を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="08771-110">The following table gives a short description of the <xref:System.Data.LoadOption> enumeration values.</span></span>  
  
|<span data-ttu-id="08771-111">LoadOption の値</span><span class="sxs-lookup"><span data-stu-id="08771-111">LoadOption value</span></span>|<span data-ttu-id="08771-112">説明</span><span class="sxs-lookup"><span data-stu-id="08771-112">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="08771-113">**OverwriteRow**</span><span class="sxs-lookup"><span data-stu-id="08771-113">**OverwriteRow**</span></span>|<span data-ttu-id="08771-114">読み込まれる行と **DataTable** に既に存在する行で **PrimaryKey** 値が同じ場合、各列の **Original** 値と **Current** 値は読み込まれる行の値に置き換えられ、**RowState** プロパティは **Unchanged** に設定されます。</span><span class="sxs-lookup"><span data-stu-id="08771-114">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** and **Current** values of each column are replaced with the values in the incoming row, and the **RowState** property is set to **Unchanged**.</span></span><br /><br /> <span data-ttu-id="08771-115">**DataTable** に存在していなかった行がデータ ソースから読み込まれ、その行の **RowState** 値は **Unchanged** に設定されます。</span><span class="sxs-lookup"><span data-stu-id="08771-115">Rows from the data source that do not already exist in the **DataTable** are added with a **RowState** value of **Unchanged**.</span></span><br /><br /> <span data-ttu-id="08771-116">このオプションは **DataTable** の内容を更新して、データ ソースの内容と一致するようにします。</span><span class="sxs-lookup"><span data-stu-id="08771-116">This option in effect refreshes the contents of the **DataTable** so that it matches the contents of the data source.</span></span>|  
|<span data-ttu-id="08771-117">**PreserveCurrentValues (既定値)**</span><span class="sxs-lookup"><span data-stu-id="08771-117">**PreserveCurrentValues (default)**</span></span>|<span data-ttu-id="08771-118">読み込まれる行と **DataTable** に既に存在する行の **PrimaryKey** 値が同じ場合、**Original** 値には読み込まれる行の内容が設定されますが、**Current** 値は変更されません。</span><span class="sxs-lookup"><span data-stu-id="08771-118">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** value is set to the contents of the incoming row, and the **Current** value is not changed.</span></span><br /><br /> <span data-ttu-id="08771-119">**RowState** が **Added** または **Modified** の場合、この値は **Modified** に設定されます。</span><span class="sxs-lookup"><span data-stu-id="08771-119">If the **RowState** is **Added** or **Modified**, it is set to **Modified**.</span></span><br /><br /> <span data-ttu-id="08771-120">**RowState** が **Deleted** であった場合、この値は **Deleted** のままとなります。</span><span class="sxs-lookup"><span data-stu-id="08771-120">If the **RowState** was **Deleted**, it remains **Deleted**.</span></span><br /><br /> <span data-ttu-id="08771-121">**DataTable** に存在していなかった行がデータ ソースから読み込まれ、その行の **RowState** は **Unchanged** に設定されます。</span><span class="sxs-lookup"><span data-stu-id="08771-121">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Unchanged**.</span></span>|  
|<span data-ttu-id="08771-122">**UpdateCurrentValues**</span><span class="sxs-lookup"><span data-stu-id="08771-122">**UpdateCurrentValues**</span></span>|<span data-ttu-id="08771-123">読み込まれる行と **DataTable** に既に存在する行の **PrimaryKey** 値が同じ場合、**Current** 値が **Original** 値にコピーされ、**Current** 値には読み込まれる行の内容が設定されます。</span><span class="sxs-lookup"><span data-stu-id="08771-123">If incoming rows have the same **PrimaryKey** value as the row already in the **DataTable**, the **Current** value is copied to the **Original** value, and the **Current** value is then set to the contents of the incoming row.</span></span><br /><br /> <span data-ttu-id="08771-124">**DataTable** の **RowState** が **Added** の場合、**RowState** は **Added** のままとなります。</span><span class="sxs-lookup"><span data-stu-id="08771-124">If the **RowState** in the **DataTable** was **Added**, the **RowState** remains **Added**.</span></span> <span data-ttu-id="08771-125">**Modified** または **Deleted** としてマークされた行の **RowState** は **Modified** になります。</span><span class="sxs-lookup"><span data-stu-id="08771-125">For rows marked as **Modified** or **Deleted**, the **RowState** is **Modified**.</span></span><br /><br /> <span data-ttu-id="08771-126">**DataTable** に存在していなかった行がデータ ソースから読み込まれ、その行の **RowState** は **Added** に設定されます。</span><span class="sxs-lookup"><span data-stu-id="08771-126">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Added**.</span></span>|  
  
 <span data-ttu-id="08771-127">**Load** メソッドを使用して **Northwind** データベースに従業員の誕生日リストを表示する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="08771-127">The following sample uses the **Load** method to display a list of birthdays for the employees in the **Northwind** database.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="08771-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="08771-128">See also</span></span>

- [<span data-ttu-id="08771-129">DataTable 内のデータの操作</span><span class="sxs-lookup"><span data-stu-id="08771-129">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="08771-130">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="08771-130">ADO.NET Overview</span></span>](../ado-net-overview.md)
