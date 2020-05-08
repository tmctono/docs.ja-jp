---
title: スキーマの制限
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
ms.openlocfilehash: 17c42c5131252993d1f16e4a2f7a6450f0984d11
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149012"
---
# <a name="schema-restrictions"></a><span data-ttu-id="0e775-102">スキーマの制限</span><span class="sxs-lookup"><span data-stu-id="0e775-102">Schema Restrictions</span></span>
<span data-ttu-id="0e775-103">**GetSchema** メソッドの 2 番目のオプション パラメーターは、返されるスキーマ情報の量を制限するために使用される制限で、文字列の配列として **GetSchema** メソッドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="0e775-103">The second optional parameter of the **GetSchema** method is the restrictions that are used to limit the amount of schema information returned, and it is passed to the **GetSchema** method as an array of strings.</span></span> <span data-ttu-id="0e775-104">配列での位置により、渡すことができる値が決定します。これは、制限の番号に相当します。</span><span class="sxs-lookup"><span data-stu-id="0e775-104">The position in the array determines the values that you can pass, and this is equivalent to the restriction number.</span></span>  
  
 <span data-ttu-id="0e775-105">たとえば、次の表は、.NET Framework Data Provider for SQL Server を使用して、"Tables" スキーマ コレクションによりサポートされる制限を示しています。</span><span class="sxs-lookup"><span data-stu-id="0e775-105">For example, the following table describes the restrictions supported by the "Tables" schema collection using the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="0e775-106">SQL Server スキーマ コレクションの追加の制限をこのトピックの終わりに示します。</span><span class="sxs-lookup"><span data-stu-id="0e775-106">Additional restrictions for SQL Server schema collections are listed at the end of this topic.</span></span>  
  
|<span data-ttu-id="0e775-107">制限の名前</span><span class="sxs-lookup"><span data-stu-id="0e775-107">Restriction Name</span></span>|<span data-ttu-id="0e775-108">パラメーター名</span><span class="sxs-lookup"><span data-stu-id="0e775-108">Parameter Name</span></span>|<span data-ttu-id="0e775-109">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="0e775-109">Restriction Default</span></span>|<span data-ttu-id="0e775-110">制限の番号</span><span class="sxs-lookup"><span data-stu-id="0e775-110">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="0e775-111">Catalog</span><span class="sxs-lookup"><span data-stu-id="0e775-111">Catalog</span></span>|@Catalog|<span data-ttu-id="0e775-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0e775-112">TABLE_CATALOG</span></span>|<span data-ttu-id="0e775-113">1</span><span class="sxs-lookup"><span data-stu-id="0e775-113">1</span></span>|  
|<span data-ttu-id="0e775-114">Owner</span><span class="sxs-lookup"><span data-stu-id="0e775-114">Owner</span></span>|@Owner|<span data-ttu-id="0e775-115">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0e775-115">TABLE_SCHEMA</span></span>|<span data-ttu-id="0e775-116">2</span><span class="sxs-lookup"><span data-stu-id="0e775-116">2</span></span>|  
|<span data-ttu-id="0e775-117">テーブル</span><span class="sxs-lookup"><span data-stu-id="0e775-117">Table</span></span>|@Name|<span data-ttu-id="0e775-118">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0e775-118">TABLE_NAME</span></span>|<span data-ttu-id="0e775-119">3</span><span class="sxs-lookup"><span data-stu-id="0e775-119">3</span></span>|  
|<span data-ttu-id="0e775-120">TableType</span><span class="sxs-lookup"><span data-stu-id="0e775-120">TableType</span></span>|@TableType|<span data-ttu-id="0e775-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="0e775-121">TABLE_TYPE</span></span>|<span data-ttu-id="0e775-122">4</span><span class="sxs-lookup"><span data-stu-id="0e775-122">4</span></span>|  
  
## <a name="specifying-restriction-values"></a><span data-ttu-id="0e775-123">制限値の指定</span><span class="sxs-lookup"><span data-stu-id="0e775-123">Specifying Restriction Values</span></span>  
 <span data-ttu-id="0e775-124">"Tables" スキーマ コレクションの制限の 1 つを使用するには、4 つの要素を使って文字列の配列を作成してから、制限の番号と一致する要素内に値を配置します。</span><span class="sxs-lookup"><span data-stu-id="0e775-124">To use one of the restrictions of the "Tables" schema collection, simply create an array of strings with four elements, then place a value in the element that matches the restriction number.</span></span> <span data-ttu-id="0e775-125">たとえば、**GetSchema** メソッドにより返されるテーブルを、"Sales" スキーマ内のテーブルのみに制限するには、**GetSchema** メソッドに渡す前に、配列の 2 番目の要素を "Sales" に設定します。</span><span class="sxs-lookup"><span data-stu-id="0e775-125">For example, to restrict the tables returned by the **GetSchema** method to only those tables in the "Sales" schema, set the second element of the array to "Sales" before passing it to the **GetSchema** method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0e775-126">`SqlClient` と `OracleClient` の制限のコレクションには、追加の `ParameterName` 列があります。</span><span class="sxs-lookup"><span data-stu-id="0e775-126">The restrictions collections for `SqlClient` and `OracleClient` have an additional `ParameterName` column.</span></span> <span data-ttu-id="0e775-127">制限の既定の列は、下位互換性のために存在してはいますが、現在は無視されています。</span><span class="sxs-lookup"><span data-stu-id="0e775-127">The restriction default column is still there for backwards compatibility, but is currently ignored.</span></span> <span data-ttu-id="0e775-128">制限の値を指定する場合、文字列置換ではなく、パラメーター付きのクエリを使って、SQL への注入攻撃のリスクを最小限にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e775-128">Parameterized queries rather than string replacement should be used to minimize the risk of an SQL injection attack when specifying restriction values.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0e775-129">配列内の要素数は、指定したスキーマ コレクションでサポートされる制限数以下にする必要があります。そうでない場合、<xref:System.ArgumentException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="0e775-129">The number of elements in the array must be less than or equal to the number of restrictions supported for the specified schema collection else an <xref:System.ArgumentException> will be thrown.</span></span> <span data-ttu-id="0e775-130">制限は最大数よりも小さい場合があります。</span><span class="sxs-lookup"><span data-stu-id="0e775-130">There can be fewer than the maximum number of restrictions.</span></span> <span data-ttu-id="0e775-131">指定されていない制限は、null (無制限) と見なされます。</span><span class="sxs-lookup"><span data-stu-id="0e775-131">The missing restrictions are assumed to be null (unrestricted).</span></span>  
  
 <span data-ttu-id="0e775-132">.NET Framework マネージド プロバイダーでは、"Restrictions" という制限のスキーマ コレクションの名前を指定して **GetSchema** メソッドを呼び出すことにより、サポートされる制限の一覧を特定します。</span><span class="sxs-lookup"><span data-stu-id="0e775-132">You can query a .NET Framework managed provider to determine the list of supported restrictions by calling the **GetSchema** method with the name of the restrictions schema collection, which is "Restrictions".</span></span> <span data-ttu-id="0e775-133">これにより、コレクション名の一覧、制限の名前、既定の制限値、および制限の番号と共に、<xref:System.Data.DataTable> が返されます。</span><span class="sxs-lookup"><span data-stu-id="0e775-133">This will return a <xref:System.Data.DataTable> with a list of the collection names, the restriction names, the default restriction values, and the restriction numbers.</span></span>  
  
### <a name="example"></a><span data-ttu-id="0e775-134">例</span><span class="sxs-lookup"><span data-stu-id="0e775-134">Example</span></span>  
 <span data-ttu-id="0e775-135">.NET Framework Data Provider for the SQL Server の <xref:System.Data.SqlClient.SqlConnection> クラスの <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> メソッドを使用して、**AdventureWorks** サンプル データベースに含まれるすべてのテーブルに関するスキーマ情報を取得し、返される情報を "Sales" スキーマ内のテーブルのみに制限する方法について、いくつかの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0e775-135">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database, and to restrict the information returned to only those tables in the "Sales" schema:</span></span>  
  
```vb  
Imports System.Data.SqlClient  
  
Module Module1  
Sub Main()  
  Dim connectionString As String = _  
    "Data Source=(local);Database=AdventureWorks;" & _  
       "Integrated Security=true;";  
  
  Dim restrictions(3) As String  
  Using connection As New SqlConnection(connectionString)  
    connection.Open()  
  
    'Specify the restrictions.  
    restrictions(1) = "Sales"  
    Dim table As DataTable = connection.GetSchema("Tables", _  
       restrictions)  
  
    ' Display the contents of the table.  
      For Each row As DataRow In table.Rows  
         For Each col As DataColumn In table.Columns  
            Console.WriteLine("{0} = {1}", col.ColumnName, row(col))  
         Next  
         Console.WriteLine("============================")  
      Next  
    Console.WriteLine("Press any key to continue.")  
    Console.ReadKey()  
  End Using  
End Sub  
End Module  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlClient;  
  
class Program  
{  
  static void Main()  
  {  
    string connectionString =
       "Data Source=(local);Database=AdventureWorks;" +  
       "Integrated Security=true;";  
    using (SqlConnection connection =  
       new SqlConnection(connectionString))  
    {  
        connection.Open();  
  
        // Specify the restrictions.  
        string[] restrictions = new string[4];  
        restrictions[1] = "Sales";  
        System.Data.DataTable table = connection.GetSchema(  
          "Tables", restrictions);  
  
        // Display the contents of the table.  
        foreach (System.Data.DataRow row in table.Rows)  
        {  
            foreach (System.Data.DataColumn col in table.Columns)  
            {  
                Console.WriteLine("{0} = {1}",
                  col.ColumnName, row[col]);  
            }  
            Console.WriteLine("============================");  
        }  
        Console.WriteLine("Press any key to continue.");  
        Console.ReadKey();  
    }  
  }  
  
  private static string GetConnectionString()  
  {  
     // To avoid storing the connection string in your code,  
     // you can retrieve it from a configuration file.  
     return "Data Source=(local);Database=AdventureWorks;" +  
        "Integrated Security=true;";  
  }  
  
  private static void DisplayData(System.Data.DataTable table)  
  {  
     foreach (System.Data.DataRow row in table.Rows)  
     {  
        foreach (System.Data.DataColumn col in table.Columns)  
        {  
           Console.WriteLine("{0} = {1}", col.ColumnName, row[col]);  
        }  
     Console.WriteLine("============================");  
     }  
  }  
}  
```  
  
## <a name="sql-server-schema-restrictions"></a><span data-ttu-id="0e775-136">SQL Server スキーマの制限</span><span class="sxs-lookup"><span data-stu-id="0e775-136">SQL Server Schema Restrictions</span></span>  
 <span data-ttu-id="0e775-137">次の表に、SQL Server スキーマ コレクションの制限を示します。</span><span class="sxs-lookup"><span data-stu-id="0e775-137">The following tables list the restrictions for SQL Server schema collections.</span></span>  
  
### <a name="users"></a><span data-ttu-id="0e775-138">Users</span><span class="sxs-lookup"><span data-stu-id="0e775-138">Users</span></span>  
  
|<span data-ttu-id="0e775-139">制限の名前</span><span class="sxs-lookup"><span data-stu-id="0e775-139">Restriction Name</span></span>|<span data-ttu-id="0e775-140">パラメーター名</span><span class="sxs-lookup"><span data-stu-id="0e775-140">Parameter Name</span></span>|<span data-ttu-id="0e775-141">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="0e775-141">Restriction Default</span></span>|<span data-ttu-id="0e775-142">制限の番号</span><span class="sxs-lookup"><span data-stu-id="0e775-142">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="0e775-143">User_Name</span><span class="sxs-lookup"><span data-stu-id="0e775-143">User_Name</span></span>|@Name|<span data-ttu-id="0e775-144">name</span><span class="sxs-lookup"><span data-stu-id="0e775-144">name</span></span>|<span data-ttu-id="0e775-145">1</span><span class="sxs-lookup"><span data-stu-id="0e775-145">1</span></span>|  
  
### <a name="databases"></a><span data-ttu-id="0e775-146">データベース</span><span class="sxs-lookup"><span data-stu-id="0e775-146">Databases</span></span>  
  
|<span data-ttu-id="0e775-147">制限の名前</span><span class="sxs-lookup"><span data-stu-id="0e775-147">Restriction Name</span></span>|<span data-ttu-id="0e775-148">パラメーター名</span><span class="sxs-lookup"><span data-stu-id="0e775-148">Parameter Name</span></span>|<span data-ttu-id="0e775-149">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="0e775-149">Restriction Default</span></span>|<span data-ttu-id="0e775-150">制限の番号</span><span class="sxs-lookup"><span data-stu-id="0e775-150">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="0e775-151">名前</span><span class="sxs-lookup"><span data-stu-id="0e775-151">Name</span></span>|@Name|<span data-ttu-id="0e775-152">名前</span><span class="sxs-lookup"><span data-stu-id="0e775-152">Name</span></span>|<span data-ttu-id="0e775-153">1</span><span class="sxs-lookup"><span data-stu-id="0e775-153">1</span></span>|  
  
### <a name="tables"></a><span data-ttu-id="0e775-154">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="0e775-154">Tables</span></span>  
  
|<span data-ttu-id="0e775-155">制限の名前</span><span class="sxs-lookup"><span data-stu-id="0e775-155">Restriction Name</span></span>|<span data-ttu-id="0e775-156">パラメーター名</span><span class="sxs-lookup"><span data-stu-id="0e775-156">Parameter Name</span></span>|<span data-ttu-id="0e775-157">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="0e775-157">Restriction Default</span></span>|<span data-ttu-id="0e775-158">制限の番号</span><span class="sxs-lookup"><span data-stu-id="0e775-158">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="0e775-159">Catalog</span><span class="sxs-lookup"><span data-stu-id="0e775-159">Catalog</span></span>|@Catalog|<span data-ttu-id="0e775-160">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0e775-160">TABLE_CATALOG</span></span>|<span data-ttu-id="0e775-161">1</span><span class="sxs-lookup"><span data-stu-id="0e775-161">1</span></span>|  
|<span data-ttu-id="0e775-162">Owner</span><span class="sxs-lookup"><span data-stu-id="0e775-162">Owner</span></span>|@Owner|<span data-ttu-id="0e775-163">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0e775-163">TABLE_SCHEMA</span></span>|<span data-ttu-id="0e775-164">2</span><span class="sxs-lookup"><span data-stu-id="0e775-164">2</span></span>|  
|<span data-ttu-id="0e775-165">テーブル</span><span class="sxs-lookup"><span data-stu-id="0e775-165">Table</span></span>|@Name|<span data-ttu-id="0e775-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0e775-166">TABLE_NAME</span></span>|<span data-ttu-id="0e775-167">3</span><span class="sxs-lookup"><span data-stu-id="0e775-167">3</span></span>|  
|<span data-ttu-id="0e775-168">TableType</span><span class="sxs-lookup"><span data-stu-id="0e775-168">TableType</span></span>|@TableType|<span data-ttu-id="0e775-169">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="0e775-169">TABLE_TYPE</span></span>|<span data-ttu-id="0e775-170">4</span><span class="sxs-lookup"><span data-stu-id="0e775-170">4</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="0e775-171">列</span><span class="sxs-lookup"><span data-stu-id="0e775-171">Columns</span></span>  
  
|<span data-ttu-id="0e775-172">制限の名前</span><span class="sxs-lookup"><span data-stu-id="0e775-172">Restriction Name</span></span>|<span data-ttu-id="0e775-173">パラメーター名</span><span class="sxs-lookup"><span data-stu-id="0e775-173">Parameter Name</span></span>|<span data-ttu-id="0e775-174">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="0e775-174">Restriction Default</span></span>|<span data-ttu-id="0e775-175">制限の番号</span><span class="sxs-lookup"><span data-stu-id="0e775-175">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="0e775-176">Catalog</span><span class="sxs-lookup"><span data-stu-id="0e775-176">Catalog</span></span>|@Catalog|<span data-ttu-id="0e775-177">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0e775-177">TABLE_CATALOG</span></span>|<span data-ttu-id="0e775-178">1</span><span class="sxs-lookup"><span data-stu-id="0e775-178">1</span></span>|  
|<span data-ttu-id="0e775-179">Owner</span><span class="sxs-lookup"><span data-stu-id="0e775-179">Owner</span></span>|@Owner|<span data-ttu-id="0e775-180">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0e775-180">TABLE_SCHEMA</span></span>|<span data-ttu-id="0e775-181">2</span><span class="sxs-lookup"><span data-stu-id="0e775-181">2</span></span>|  
|<span data-ttu-id="0e775-182">テーブル</span><span class="sxs-lookup"><span data-stu-id="0e775-182">Table</span></span>|@Table|<span data-ttu-id="0e775-183">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0e775-183">TABLE_NAME</span></span>|<span data-ttu-id="0e775-184">3</span><span class="sxs-lookup"><span data-stu-id="0e775-184">3</span></span>|  
|<span data-ttu-id="0e775-185">Column</span><span class="sxs-lookup"><span data-stu-id="0e775-185">Column</span></span>|@Column|<span data-ttu-id="0e775-186">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="0e775-186">COLUMN_NAME</span></span>|<span data-ttu-id="0e775-187">4</span><span class="sxs-lookup"><span data-stu-id="0e775-187">4</span></span>|  
  
### <a name="structuredtypemembers"></a><span data-ttu-id="0e775-188">StructuredTypeMembers</span><span class="sxs-lookup"><span data-stu-id="0e775-188">StructuredTypeMembers</span></span>  
  
|<span data-ttu-id="0e775-189">制限の名前</span><span class="sxs-lookup"><span data-stu-id="0e775-189">Restriction Name</span></span>|<span data-ttu-id="0e775-190">パラメーター名</span><span class="sxs-lookup"><span data-stu-id="0e775-190">Parameter Name</span></span>|<span data-ttu-id="0e775-191">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="0e775-191">Restriction Default</span></span>|<span data-ttu-id="0e775-192">制限の番号</span><span class="sxs-lookup"><span data-stu-id="0e775-192">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="0e775-193">Catalog</span><span class="sxs-lookup"><span data-stu-id="0e775-193">Catalog</span></span>|@Catalog|<span data-ttu-id="0e775-194">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0e775-194">TABLE_CATALOG</span></span>|<span data-ttu-id="0e775-195">1</span><span class="sxs-lookup"><span data-stu-id="0e775-195">1</span></span>|  
|<span data-ttu-id="0e775-196">Owner</span><span class="sxs-lookup"><span data-stu-id="0e775-196">Owner</span></span>|@Owner|<span data-ttu-id="0e775-197">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0e775-197">TABLE_SCHEMA</span></span>|<span data-ttu-id="0e775-198">2</span><span class="sxs-lookup"><span data-stu-id="0e775-198">2</span></span>|  
|<span data-ttu-id="0e775-199">テーブル</span><span class="sxs-lookup"><span data-stu-id="0e775-199">Table</span></span>|@Table|<span data-ttu-id="0e775-200">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0e775-200">TABLE_NAME</span></span>|<span data-ttu-id="0e775-201">3</span><span class="sxs-lookup"><span data-stu-id="0e775-201">3</span></span>|  
|<span data-ttu-id="0e775-202">Column</span><span class="sxs-lookup"><span data-stu-id="0e775-202">Column</span></span>|@Column|<span data-ttu-id="0e775-203">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="0e775-203">COLUMN_NAME</span></span>|<span data-ttu-id="0e775-204">4</span><span class="sxs-lookup"><span data-stu-id="0e775-204">4</span></span>|  
  
### <a name="views"></a><span data-ttu-id="0e775-205">Views</span><span class="sxs-lookup"><span data-stu-id="0e775-205">Views</span></span>  
  
|<span data-ttu-id="0e775-206">制限の名前</span><span class="sxs-lookup"><span data-stu-id="0e775-206">Restriction Name</span></span>|<span data-ttu-id="0e775-207">パラメーター名</span><span class="sxs-lookup"><span data-stu-id="0e775-207">Parameter Name</span></span>|<span data-ttu-id="0e775-208">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="0e775-208">Restriction Default</span></span>|<span data-ttu-id="0e775-209">制限の番号</span><span class="sxs-lookup"><span data-stu-id="0e775-209">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="0e775-210">Catalog</span><span class="sxs-lookup"><span data-stu-id="0e775-210">Catalog</span></span>|@Catalog|<span data-ttu-id="0e775-211">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0e775-211">TABLE_CATALOG</span></span>|<span data-ttu-id="0e775-212">1</span><span class="sxs-lookup"><span data-stu-id="0e775-212">1</span></span>|  
|<span data-ttu-id="0e775-213">Owner</span><span class="sxs-lookup"><span data-stu-id="0e775-213">Owner</span></span>|@Owner|<span data-ttu-id="0e775-214">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0e775-214">TABLE_SCHEMA</span></span>|<span data-ttu-id="0e775-215">2</span><span class="sxs-lookup"><span data-stu-id="0e775-215">2</span></span>|  
|<span data-ttu-id="0e775-216">テーブル</span><span class="sxs-lookup"><span data-stu-id="0e775-216">Table</span></span>|@Table|<span data-ttu-id="0e775-217">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0e775-217">TABLE_NAME</span></span>|<span data-ttu-id="0e775-218">3</span><span class="sxs-lookup"><span data-stu-id="0e775-218">3</span></span>|  
  
### <a name="viewcolumns"></a><span data-ttu-id="0e775-219">ViewColumns</span><span class="sxs-lookup"><span data-stu-id="0e775-219">ViewColumns</span></span>  
  
|<span data-ttu-id="0e775-220">制限の名前</span><span class="sxs-lookup"><span data-stu-id="0e775-220">Restriction Name</span></span>|<span data-ttu-id="0e775-221">パラメーター名</span><span class="sxs-lookup"><span data-stu-id="0e775-221">Parameter Name</span></span>|<span data-ttu-id="0e775-222">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="0e775-222">Restriction Default</span></span>|<span data-ttu-id="0e775-223">制限の番号</span><span class="sxs-lookup"><span data-stu-id="0e775-223">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="0e775-224">Catalog</span><span class="sxs-lookup"><span data-stu-id="0e775-224">Catalog</span></span>|@Catalog|<span data-ttu-id="0e775-225">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0e775-225">VIEW_CATALOG</span></span>|<span data-ttu-id="0e775-226">1</span><span class="sxs-lookup"><span data-stu-id="0e775-226">1</span></span>|  
|<span data-ttu-id="0e775-227">Owner</span><span class="sxs-lookup"><span data-stu-id="0e775-227">Owner</span></span>|@Owner|<span data-ttu-id="0e775-228">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0e775-228">VIEW_SCHEMA</span></span>|<span data-ttu-id="0e775-229">2</span><span class="sxs-lookup"><span data-stu-id="0e775-229">2</span></span>|  
|<span data-ttu-id="0e775-230">テーブル</span><span class="sxs-lookup"><span data-stu-id="0e775-230">Table</span></span>|@Table|<span data-ttu-id="0e775-231">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="0e775-231">VIEW_NAME</span></span>|<span data-ttu-id="0e775-232">3</span><span class="sxs-lookup"><span data-stu-id="0e775-232">3</span></span>|  
|<span data-ttu-id="0e775-233">Column</span><span class="sxs-lookup"><span data-stu-id="0e775-233">Column</span></span>|@Column|<span data-ttu-id="0e775-234">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="0e775-234">COLUMN_NAME</span></span>|<span data-ttu-id="0e775-235">4</span><span class="sxs-lookup"><span data-stu-id="0e775-235">4</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="0e775-236">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="0e775-236">ProcedureParameters</span></span>  
  
|<span data-ttu-id="0e775-237">制限の名前</span><span class="sxs-lookup"><span data-stu-id="0e775-237">Restriction Name</span></span>|<span data-ttu-id="0e775-238">パラメーター名</span><span class="sxs-lookup"><span data-stu-id="0e775-238">Parameter Name</span></span>|<span data-ttu-id="0e775-239">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="0e775-239">Restriction Default</span></span>|<span data-ttu-id="0e775-240">制限の番号</span><span class="sxs-lookup"><span data-stu-id="0e775-240">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="0e775-241">Catalog</span><span class="sxs-lookup"><span data-stu-id="0e775-241">Catalog</span></span>|@Catalog|<span data-ttu-id="0e775-242">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0e775-242">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="0e775-243">1</span><span class="sxs-lookup"><span data-stu-id="0e775-243">1</span></span>|  
|<span data-ttu-id="0e775-244">Owner</span><span class="sxs-lookup"><span data-stu-id="0e775-244">Owner</span></span>|@Owner|<span data-ttu-id="0e775-245">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0e775-245">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="0e775-246">2</span><span class="sxs-lookup"><span data-stu-id="0e775-246">2</span></span>|  
|<span data-ttu-id="0e775-247">名前</span><span class="sxs-lookup"><span data-stu-id="0e775-247">Name</span></span>|@Name|<span data-ttu-id="0e775-248">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="0e775-248">SPECIFIC_NAME</span></span>|<span data-ttu-id="0e775-249">3</span><span class="sxs-lookup"><span data-stu-id="0e775-249">3</span></span>|  
|<span data-ttu-id="0e775-250">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0e775-250">Parameter</span></span>|@Parameter|<span data-ttu-id="0e775-251">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="0e775-251">PARAMETER_NAME</span></span>|<span data-ttu-id="0e775-252">4</span><span class="sxs-lookup"><span data-stu-id="0e775-252">4</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="0e775-253">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="0e775-253">Procedures</span></span>  
  
|<span data-ttu-id="0e775-254">制限の名前</span><span class="sxs-lookup"><span data-stu-id="0e775-254">Restriction Name</span></span>|<span data-ttu-id="0e775-255">パラメーター名</span><span class="sxs-lookup"><span data-stu-id="0e775-255">Parameter Name</span></span>|<span data-ttu-id="0e775-256">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="0e775-256">Restriction Default</span></span>|<span data-ttu-id="0e775-257">制限の番号</span><span class="sxs-lookup"><span data-stu-id="0e775-257">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="0e775-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="0e775-258">Catalog</span></span>|@Catalog|<span data-ttu-id="0e775-259">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0e775-259">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="0e775-260">1</span><span class="sxs-lookup"><span data-stu-id="0e775-260">1</span></span>|  
|<span data-ttu-id="0e775-261">Owner</span><span class="sxs-lookup"><span data-stu-id="0e775-261">Owner</span></span>|@Owner|<span data-ttu-id="0e775-262">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0e775-262">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="0e775-263">2</span><span class="sxs-lookup"><span data-stu-id="0e775-263">2</span></span>|  
|<span data-ttu-id="0e775-264">名前</span><span class="sxs-lookup"><span data-stu-id="0e775-264">Name</span></span>|@Name|<span data-ttu-id="0e775-265">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="0e775-265">SPECIFIC_NAME</span></span>|<span data-ttu-id="0e775-266">3</span><span class="sxs-lookup"><span data-stu-id="0e775-266">3</span></span>|  
|<span data-ttu-id="0e775-267">種類</span><span class="sxs-lookup"><span data-stu-id="0e775-267">Type</span></span>|@Type|<span data-ttu-id="0e775-268">ROUTINE_TYPE</span><span class="sxs-lookup"><span data-stu-id="0e775-268">ROUTINE_TYPE</span></span>|<span data-ttu-id="0e775-269">4</span><span class="sxs-lookup"><span data-stu-id="0e775-269">4</span></span>|  
  
### <a name="indexcolumns"></a><span data-ttu-id="0e775-270">IndexColumns</span><span class="sxs-lookup"><span data-stu-id="0e775-270">IndexColumns</span></span>  
  
|<span data-ttu-id="0e775-271">制限の名前</span><span class="sxs-lookup"><span data-stu-id="0e775-271">Restriction Name</span></span>|<span data-ttu-id="0e775-272">パラメーター名</span><span class="sxs-lookup"><span data-stu-id="0e775-272">Parameter Name</span></span>|<span data-ttu-id="0e775-273">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="0e775-273">Restriction Default</span></span>|<span data-ttu-id="0e775-274">制限の番号</span><span class="sxs-lookup"><span data-stu-id="0e775-274">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="0e775-275">Catalog</span><span class="sxs-lookup"><span data-stu-id="0e775-275">Catalog</span></span>|@Catalog|<span data-ttu-id="0e775-276">db_name()</span><span class="sxs-lookup"><span data-stu-id="0e775-276">db_name()</span></span>|<span data-ttu-id="0e775-277">1</span><span class="sxs-lookup"><span data-stu-id="0e775-277">1</span></span>|  
|<span data-ttu-id="0e775-278">Owner</span><span class="sxs-lookup"><span data-stu-id="0e775-278">Owner</span></span>|@Owner|<span data-ttu-id="0e775-279">user_name()</span><span class="sxs-lookup"><span data-stu-id="0e775-279">user_name()</span></span>|<span data-ttu-id="0e775-280">2</span><span class="sxs-lookup"><span data-stu-id="0e775-280">2</span></span>|  
|<span data-ttu-id="0e775-281">テーブル</span><span class="sxs-lookup"><span data-stu-id="0e775-281">Table</span></span>|@Table|<span data-ttu-id="0e775-282">o.name</span><span class="sxs-lookup"><span data-stu-id="0e775-282">o.name</span></span>|<span data-ttu-id="0e775-283">3</span><span class="sxs-lookup"><span data-stu-id="0e775-283">3</span></span>|  
|<span data-ttu-id="0e775-284">ConstraintName</span><span class="sxs-lookup"><span data-stu-id="0e775-284">ConstraintName</span></span>|@ConstraintName|<span data-ttu-id="0e775-285">x.name</span><span class="sxs-lookup"><span data-stu-id="0e775-285">x.name</span></span>|<span data-ttu-id="0e775-286">4</span><span class="sxs-lookup"><span data-stu-id="0e775-286">4</span></span>|  
|<span data-ttu-id="0e775-287">Column</span><span class="sxs-lookup"><span data-stu-id="0e775-287">Column</span></span>|@Column|<span data-ttu-id="0e775-288">c.name</span><span class="sxs-lookup"><span data-stu-id="0e775-288">c.name</span></span>|<span data-ttu-id="0e775-289">5</span><span class="sxs-lookup"><span data-stu-id="0e775-289">5</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="0e775-290">Indexes</span><span class="sxs-lookup"><span data-stu-id="0e775-290">Indexes</span></span>  
  
|<span data-ttu-id="0e775-291">制限の名前</span><span class="sxs-lookup"><span data-stu-id="0e775-291">Restriction Name</span></span>|<span data-ttu-id="0e775-292">パラメーター名</span><span class="sxs-lookup"><span data-stu-id="0e775-292">Parameter Name</span></span>|<span data-ttu-id="0e775-293">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="0e775-293">Restriction Default</span></span>|<span data-ttu-id="0e775-294">制限の番号</span><span class="sxs-lookup"><span data-stu-id="0e775-294">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="0e775-295">Catalog</span><span class="sxs-lookup"><span data-stu-id="0e775-295">Catalog</span></span>|@Catalog|<span data-ttu-id="0e775-296">db_name()</span><span class="sxs-lookup"><span data-stu-id="0e775-296">db_name()</span></span>|<span data-ttu-id="0e775-297">1</span><span class="sxs-lookup"><span data-stu-id="0e775-297">1</span></span>|  
|<span data-ttu-id="0e775-298">Owner</span><span class="sxs-lookup"><span data-stu-id="0e775-298">Owner</span></span>|@Owner|<span data-ttu-id="0e775-299">user_name()</span><span class="sxs-lookup"><span data-stu-id="0e775-299">user_name()</span></span>|<span data-ttu-id="0e775-300">2</span><span class="sxs-lookup"><span data-stu-id="0e775-300">2</span></span>|  
|<span data-ttu-id="0e775-301">テーブル</span><span class="sxs-lookup"><span data-stu-id="0e775-301">Table</span></span>|@Table|<span data-ttu-id="0e775-302">o.name</span><span class="sxs-lookup"><span data-stu-id="0e775-302">o.name</span></span>|<span data-ttu-id="0e775-303">3</span><span class="sxs-lookup"><span data-stu-id="0e775-303">3</span></span>|  
  
### <a name="userdefinedtypes"></a><span data-ttu-id="0e775-304">UserDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="0e775-304">UserDefinedTypes</span></span>  
  
|<span data-ttu-id="0e775-305">制限の名前</span><span class="sxs-lookup"><span data-stu-id="0e775-305">Restriction Name</span></span>|<span data-ttu-id="0e775-306">パラメーター名</span><span class="sxs-lookup"><span data-stu-id="0e775-306">Parameter Name</span></span>|<span data-ttu-id="0e775-307">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="0e775-307">Restriction Default</span></span>|<span data-ttu-id="0e775-308">制限の番号</span><span class="sxs-lookup"><span data-stu-id="0e775-308">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="0e775-309">assembly_name</span><span class="sxs-lookup"><span data-stu-id="0e775-309">assembly_name</span></span>|@AssemblyName|<span data-ttu-id="0e775-310">assemblies.name</span><span class="sxs-lookup"><span data-stu-id="0e775-310">assemblies.name</span></span>|<span data-ttu-id="0e775-311">1</span><span class="sxs-lookup"><span data-stu-id="0e775-311">1</span></span>|  
|<span data-ttu-id="0e775-312">udt_name</span><span class="sxs-lookup"><span data-stu-id="0e775-312">udt_name</span></span>|@UDTName|<span data-ttu-id="0e775-313">types.assembly_class</span><span class="sxs-lookup"><span data-stu-id="0e775-313">types.assembly_class</span></span>|<span data-ttu-id="0e775-314">2</span><span class="sxs-lookup"><span data-stu-id="0e775-314">2</span></span>|  
  
### <a name="foreignkeys"></a><span data-ttu-id="0e775-315">ForeignKeys</span><span class="sxs-lookup"><span data-stu-id="0e775-315">ForeignKeys</span></span>  
  
|<span data-ttu-id="0e775-316">制限の名前</span><span class="sxs-lookup"><span data-stu-id="0e775-316">Restriction Name</span></span>|<span data-ttu-id="0e775-317">パラメーター名</span><span class="sxs-lookup"><span data-stu-id="0e775-317">Parameter Name</span></span>|<span data-ttu-id="0e775-318">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="0e775-318">Restriction Default</span></span>|<span data-ttu-id="0e775-319">制限の番号</span><span class="sxs-lookup"><span data-stu-id="0e775-319">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="0e775-320">Catalog</span><span class="sxs-lookup"><span data-stu-id="0e775-320">Catalog</span></span>|@Catalog|<span data-ttu-id="0e775-321">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0e775-321">CONSTRAINT_CATALOG</span></span>|<span data-ttu-id="0e775-322">1</span><span class="sxs-lookup"><span data-stu-id="0e775-322">1</span></span>|  
|<span data-ttu-id="0e775-323">Owner</span><span class="sxs-lookup"><span data-stu-id="0e775-323">Owner</span></span>|@Owner|<span data-ttu-id="0e775-324">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0e775-324">CONSTRAINT_SCHEMA</span></span>|<span data-ttu-id="0e775-325">2</span><span class="sxs-lookup"><span data-stu-id="0e775-325">2</span></span>|  
|<span data-ttu-id="0e775-326">テーブル</span><span class="sxs-lookup"><span data-stu-id="0e775-326">Table</span></span>|@Table|<span data-ttu-id="0e775-327">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0e775-327">TABLE_NAME</span></span>|<span data-ttu-id="0e775-328">3</span><span class="sxs-lookup"><span data-stu-id="0e775-328">3</span></span>|  
|<span data-ttu-id="0e775-329">名前</span><span class="sxs-lookup"><span data-stu-id="0e775-329">Name</span></span>|@Name|<span data-ttu-id="0e775-330">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="0e775-330">CONSTRAINT_NAME</span></span>|<span data-ttu-id="0e775-331">4</span><span class="sxs-lookup"><span data-stu-id="0e775-331">4</span></span>|  
  
## <a name="sql-server-2008-schema-restrictions"></a><span data-ttu-id="0e775-332">SQL Server 2008 スキーマの制限</span><span class="sxs-lookup"><span data-stu-id="0e775-332">SQL Server 2008 Schema Restrictions</span></span>  
 <span data-ttu-id="0e775-333">次の表に、SQL Server 2008 スキーマ コレクションの制限を示します。</span><span class="sxs-lookup"><span data-stu-id="0e775-333">The following tables list the restrictions for SQL Server 2008 schema collections.</span></span> <span data-ttu-id="0e775-334">これらの制限は、.NET Framework 3.5 SP1 および SQL Server 2008 以降で有効です。</span><span class="sxs-lookup"><span data-stu-id="0e775-334">These restrictions are valid beginning with version 3.5 SP1 of the .NET Framework and SQL Server 2008.</span></span> <span data-ttu-id="0e775-335">これらの制限は、以前のバージョンの .NET Framework および SQL Server ではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="0e775-335">They are not supported in earlier versions of the .NET Framework and SQL Server.</span></span>  
  
### <a name="columnsetcolumns"></a><span data-ttu-id="0e775-336">ColumnSetColumns</span><span class="sxs-lookup"><span data-stu-id="0e775-336">ColumnSetColumns</span></span>  
  
|<span data-ttu-id="0e775-337">制限の名前</span><span class="sxs-lookup"><span data-stu-id="0e775-337">Restriction Name</span></span>|<span data-ttu-id="0e775-338">パラメーター名</span><span class="sxs-lookup"><span data-stu-id="0e775-338">Parameter Name</span></span>|<span data-ttu-id="0e775-339">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="0e775-339">Restriction Default</span></span>|<span data-ttu-id="0e775-340">制限の番号</span><span class="sxs-lookup"><span data-stu-id="0e775-340">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="0e775-341">Catalog</span><span class="sxs-lookup"><span data-stu-id="0e775-341">Catalog</span></span>|@Catalog|<span data-ttu-id="0e775-342">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0e775-342">TABLE_CATALOG</span></span>|<span data-ttu-id="0e775-343">1</span><span class="sxs-lookup"><span data-stu-id="0e775-343">1</span></span>|  
|<span data-ttu-id="0e775-344">Owner</span><span class="sxs-lookup"><span data-stu-id="0e775-344">Owner</span></span>|@Owner|<span data-ttu-id="0e775-345">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0e775-345">TABLE_SCHEMA</span></span>|<span data-ttu-id="0e775-346">2</span><span class="sxs-lookup"><span data-stu-id="0e775-346">2</span></span>|  
|<span data-ttu-id="0e775-347">テーブル</span><span class="sxs-lookup"><span data-stu-id="0e775-347">Table</span></span>|@Table|<span data-ttu-id="0e775-348">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0e775-348">TABLE_NAME</span></span>|<span data-ttu-id="0e775-349">3</span><span class="sxs-lookup"><span data-stu-id="0e775-349">3</span></span>|  
  
### <a name="allcolumns"></a><span data-ttu-id="0e775-350">AllColumns</span><span class="sxs-lookup"><span data-stu-id="0e775-350">AllColumns</span></span>  
  
|<span data-ttu-id="0e775-351">制限の名前</span><span class="sxs-lookup"><span data-stu-id="0e775-351">Restriction Name</span></span>|<span data-ttu-id="0e775-352">パラメーター名</span><span class="sxs-lookup"><span data-stu-id="0e775-352">Parameter Name</span></span>|<span data-ttu-id="0e775-353">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="0e775-353">Restriction Default</span></span>|<span data-ttu-id="0e775-354">制限の番号</span><span class="sxs-lookup"><span data-stu-id="0e775-354">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="0e775-355">Catalog</span><span class="sxs-lookup"><span data-stu-id="0e775-355">Catalog</span></span>|@Catalog|<span data-ttu-id="0e775-356">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0e775-356">TABLE_CATALOG</span></span>|<span data-ttu-id="0e775-357">1</span><span class="sxs-lookup"><span data-stu-id="0e775-357">1</span></span>|  
|<span data-ttu-id="0e775-358">Owner</span><span class="sxs-lookup"><span data-stu-id="0e775-358">Owner</span></span>|@Owner|<span data-ttu-id="0e775-359">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0e775-359">TABLE_SCHEMA</span></span>|<span data-ttu-id="0e775-360">2</span><span class="sxs-lookup"><span data-stu-id="0e775-360">2</span></span>|  
|<span data-ttu-id="0e775-361">テーブル</span><span class="sxs-lookup"><span data-stu-id="0e775-361">Table</span></span>|@Table|<span data-ttu-id="0e775-362">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0e775-362">TABLE_NAME</span></span>|<span data-ttu-id="0e775-363">3</span><span class="sxs-lookup"><span data-stu-id="0e775-363">3</span></span>|  
|<span data-ttu-id="0e775-364">Column</span><span class="sxs-lookup"><span data-stu-id="0e775-364">Column</span></span>|@Column|<span data-ttu-id="0e775-365">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="0e775-365">COLUMN_NAME</span></span>|<span data-ttu-id="0e775-366">4</span><span class="sxs-lookup"><span data-stu-id="0e775-366">4</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0e775-367">関連項目</span><span class="sxs-lookup"><span data-stu-id="0e775-367">See also</span></span>

- [<span data-ttu-id="0e775-368">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="0e775-368">ADO.NET Overview</span></span>](ado-net-overview.md)
