---
title: 行の検索
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5da300e2-74c0-4d13-9202-fc20ed8212d8
ms.openlocfilehash: 2ff2b6b6d00c854d07f36d37986268a388c7f31b
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203716"
---
# <a name="finding-rows"></a><span data-ttu-id="7f798-102">行の検索</span><span class="sxs-lookup"><span data-stu-id="7f798-102">Finding Rows</span></span>
<span data-ttu-id="7f798-103"><xref:System.Data.DataView.Find%2A> の <xref:System.Data.DataView.FindRows%2A> メソッドと <xref:System.Data.DataView> メソッドを使用すると、並べ替えキーの値に基づいて行を検索できます。</span><span class="sxs-lookup"><span data-stu-id="7f798-103">You can search for rows according to their sort key values by using the <xref:System.Data.DataView.Find%2A> and <xref:System.Data.DataView.FindRows%2A> methods of the <xref:System.Data.DataView>.</span></span> <span data-ttu-id="7f798-104">**Find**メソッドと**FindRows**メソッドの検索値の大文字と小文字の区別は、基になる<xref:System.Data.DataTable>の**CaseSensitive**プロパティによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="7f798-104">The case sensitivity of search values in the **Find** and **FindRows** methods is determined by the **CaseSensitive** property of the underlying <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="7f798-105">検索結果を返すには、検索値が既存の並べ替えキーの値と完全に一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f798-105">Search values must match existing sort key values in their entirety in order to return a result.</span></span>  
  
 <span data-ttu-id="7f798-106">**Find**メソッドは、検索条件に一致<xref:System.Data.DataRowView>するのインデックスを持つ整数を返します。</span><span class="sxs-lookup"><span data-stu-id="7f798-106">The **Find** method returns an integer with the index of the <xref:System.Data.DataRowView> that matches the search criteria.</span></span> <span data-ttu-id="7f798-107">複数の行が検索条件に一致する場合は、最初に一致した**DataRowView**のインデックスのみが返されます。</span><span class="sxs-lookup"><span data-stu-id="7f798-107">If more than one row matches the search criteria, only the index of the first matching **DataRowView** is returned.</span></span> <span data-ttu-id="7f798-108">一致するものが見つからない場合は、-1 が返されます。</span><span class="sxs-lookup"><span data-stu-id="7f798-108">If no matches are found, **Find** returns -1.</span></span>  
  
 <span data-ttu-id="7f798-109">複数の行に一致する検索結果を返すには、 **FindRows**メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="7f798-109">To return search results that match multiple rows, use the **FindRows** method.</span></span> <span data-ttu-id="7f798-110">**FindRows**は、**検索**メソッドと同様に機能しますが、 **DataView**内の一致するすべての行を参照する**DataRowView**配列を返す点が異なります。</span><span class="sxs-lookup"><span data-stu-id="7f798-110">**FindRows** works just like the **Find** method, except that it returns a **DataRowView** array that references all matching rows in the **DataView**.</span></span> <span data-ttu-id="7f798-111">一致するものが見つからない場合、 **DataRowView**配列は空になります。</span><span class="sxs-lookup"><span data-stu-id="7f798-111">If no matches are found, the **DataRowView** array will be empty.</span></span>  
  
 <span data-ttu-id="7f798-112">**Find**メソッドまたは**FindRows**メソッドを使用するには、 **applydefaultsort**を**true**に設定するか、 **sort**プロパティを使用して、並べ替え順序を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f798-112">To use the **Find** or **FindRows** methods you must specify a sort order either by setting **ApplyDefaultSort** to **true** or by using the **Sort** property.</span></span> <span data-ttu-id="7f798-113">並べ替え順序が指定されないと、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="7f798-113">If no sort order is specified, an exception is thrown.</span></span>  
  
 <span data-ttu-id="7f798-114">**Find**メソッドと**FindRows**メソッドは、並べ替え順序の列数と長さが一致する値の配列を入力として受け取ります。</span><span class="sxs-lookup"><span data-stu-id="7f798-114">The **Find** and **FindRows** methods take an array of values as input whose length matches the number of columns in the sort order.</span></span> <span data-ttu-id="7f798-115">1 つの列に基づく並べ替えの場合は、1 つの値を渡します。</span><span class="sxs-lookup"><span data-stu-id="7f798-115">In the case of a sort on a single column, you can pass a single value.</span></span> <span data-ttu-id="7f798-116">複数列に基づく並べ替えの場合は、オブジェクトの配列を渡します。</span><span class="sxs-lookup"><span data-stu-id="7f798-116">For sort orders containing multiple columns, you pass an array of objects.</span></span> <span data-ttu-id="7f798-117">複数の列の並べ替えでは、オブジェクト配列内の値が**DataView**の**sort**プロパティで指定された列の順序と一致する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7f798-117">Note that for a sort on multiple columns, the values in the object array must match the order of the columns specified in the **Sort** property of the **DataView**.</span></span>  
  
 <span data-ttu-id="7f798-118">次のコード例は、単一の列の並べ替え順序を持つ**DataView**に対して呼び出される**Find**メソッドを示しています。</span><span class="sxs-lookup"><span data-stu-id="7f798-118">The following code example shows the **Find** method being called against a **DataView** with a single column sort order.</span></span>  
  
```vb  
Dim custView As DataView = _  
  New DataView(custDS.Tables("Customers"), "", _  
  "CompanyName", DataViewRowState.CurrentRows)  
  
Dim rowIndex As Integer = custView.Find("The Cracker Box")  
  
If rowIndex = -1 Then  
  Console.WriteLine("No match found.")  
Else  
  Console.WriteLine("{0}, {1}", _  
    custView(rowIndex)("CustomerID").ToString(), _  
    custView(rowIndex)("CompanyName").ToString())  
End If  
```  
  
```csharp  
DataView custView = new DataView(custDS.Tables["Customers"], "",   
  "CompanyName", DataViewRowState.CurrentRows);  
  
int rowIndex = custView.Find("The Cracker Box");  
  
if (rowIndex == -1)  
  Console.WriteLine("No match found.");  
else  
  Console.WriteLine("{0}, {1}",  
    custView[rowIndex]["CustomerID"].ToString(),  
    custView[rowIndex]["CompanyName"].ToString());  
```  
  
 <span data-ttu-id="7f798-119">**Sort**プロパティで複数の列を指定する場合は、次のコード例のように、 **sort**プロパティで指定された順序で各列の検索値を含むオブジェクト配列を渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f798-119">If your **Sort** property specifies multiple columns, you must pass an object array with the search values for each column in the order specified by the **Sort** property, as in the following code example.</span></span>  
  
```vb  
Dim custView As DataView = _  
  New DataView(custDS.Tables("Customers"), "", _  
  "CompanyName, ContactName", _  
  DataViewRowState.CurrentRows)  
  
Dim foundRows() As DataRowView = _  
  custView.FindRows(New object() {"The Cracker Box", "Liu Wong"})  
  
If foundRows.Length = 0 Then  
  Console.WriteLine("No match found.")  
Else  
  Dim myDRV As DataRowView  
  For Each myDRV In foundRows  
    Console.WriteLine("{0}, {1}", _  
      myDRV("CompanyName").ToString(), myDRV("ContactName").ToString())  
  Next  
End If  
```  
  
```csharp  
DataView custView = new DataView(custDS.Tables["Customers"], "",  
  "CompanyName, ContactName",  
  DataViewRowState.CurrentRows);  
  
DataRowView[] foundRows =   
  custView.FindRows(new object[] {"The Cracker Box", "Liu Wong"});  
  
if (foundRows.Length == 0)  
  Console.WriteLine("No match found.");  
else  
  foreach (DataRowView myDRV in foundRows)  
    Console.WriteLine("{0}, {1}", myDRV["CompanyName"].ToString(),   
      myDRV["ContactName"].ToString());  
```  
  
## <a name="see-also"></a><span data-ttu-id="7f798-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="7f798-120">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [<span data-ttu-id="7f798-121">DataViews</span><span class="sxs-lookup"><span data-stu-id="7f798-121">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="7f798-122">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="7f798-122">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
