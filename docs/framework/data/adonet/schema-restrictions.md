---
title: スキーマの制限
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
ms.openlocfilehash: d0250e573dc24bfcad97a2f2606cb2e6c8e520da
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782760"
---
# <a name="schema-restrictions"></a><span data-ttu-id="d668b-102">スキーマの制限</span><span class="sxs-lookup"><span data-stu-id="d668b-102">Schema Restrictions</span></span>
<span data-ttu-id="d668b-103">**Getschema**メソッドの2番目の省略可能なパラメーターは、返されるスキーマ情報の量を制限するために使用される制限です。これは、文字列の配列として**getschema**メソッドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="d668b-103">The second optional parameter of the **GetSchema** method is the restrictions that are used to limit the amount of schema information returned, and it is passed to the **GetSchema** method as an array of strings.</span></span> <span data-ttu-id="d668b-104">配列での位置により、渡すことができる値が決定します。これは、制限の番号に相当します。</span><span class="sxs-lookup"><span data-stu-id="d668b-104">The position in the array determines the values that you can pass, and this is equivalent to the restriction number.</span></span>  
  
 <span data-ttu-id="d668b-105">たとえば、次の表は、.NET Framework Data Provider for SQL Server を使用して、"Tables" スキーマ コレクションによりサポートされる制限を示しています。</span><span class="sxs-lookup"><span data-stu-id="d668b-105">For example, the following table describes the restrictions supported by the "Tables" schema collection using the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="d668b-106">SQL Server スキーマ コレクションの追加の制限をこのトピックの終わりに示します。</span><span class="sxs-lookup"><span data-stu-id="d668b-106">Additional restrictions for SQL Server schema collections are listed at the end of this topic.</span></span>  
  
|<span data-ttu-id="d668b-107">制限の名前</span><span class="sxs-lookup"><span data-stu-id="d668b-107">Restriction Name</span></span>|<span data-ttu-id="d668b-108">[パラメーター名]</span><span class="sxs-lookup"><span data-stu-id="d668b-108">Parameter Name</span></span>|<span data-ttu-id="d668b-109">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="d668b-109">Restriction Default</span></span>|<span data-ttu-id="d668b-110">制限の番号</span><span class="sxs-lookup"><span data-stu-id="d668b-110">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d668b-111">Catalog</span><span class="sxs-lookup"><span data-stu-id="d668b-111">Catalog</span></span>|@Catalog|<span data-ttu-id="d668b-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d668b-112">TABLE_CATALOG</span></span>|<span data-ttu-id="d668b-113">1</span><span class="sxs-lookup"><span data-stu-id="d668b-113">1</span></span>|  
|<span data-ttu-id="d668b-114">Owner</span><span class="sxs-lookup"><span data-stu-id="d668b-114">Owner</span></span>|@Owner|<span data-ttu-id="d668b-115">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d668b-115">TABLE_SCHEMA</span></span>|<span data-ttu-id="d668b-116">2</span><span class="sxs-lookup"><span data-stu-id="d668b-116">2</span></span>|  
|<span data-ttu-id="d668b-117">テーブル</span><span class="sxs-lookup"><span data-stu-id="d668b-117">Table</span></span>|@Name|<span data-ttu-id="d668b-118">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d668b-118">TABLE_NAME</span></span>|<span data-ttu-id="d668b-119">3</span><span class="sxs-lookup"><span data-stu-id="d668b-119">3</span></span>|  
|<span data-ttu-id="d668b-120">TableType</span><span class="sxs-lookup"><span data-stu-id="d668b-120">TableType</span></span>|@TableType|<span data-ttu-id="d668b-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d668b-121">TABLE_TYPE</span></span>|<span data-ttu-id="d668b-122">4</span><span class="sxs-lookup"><span data-stu-id="d668b-122">4</span></span>|  
  
## <a name="specifying-restriction-values"></a><span data-ttu-id="d668b-123">制限値の指定</span><span class="sxs-lookup"><span data-stu-id="d668b-123">Specifying Restriction Values</span></span>  
 <span data-ttu-id="d668b-124">"Tables" スキーマ コレクションの制限の 1 つを使用するには、4 つの要素を使って文字列の配列を作成してから、制限の番号と一致する要素内に値を配置します。</span><span class="sxs-lookup"><span data-stu-id="d668b-124">To use one of the restrictions of the "Tables" schema collection, simply create an array of strings with four elements, then place a value in the element that matches the restriction number.</span></span> <span data-ttu-id="d668b-125">たとえば、 **getschema**メソッドによって返されるテーブルを、"sales" スキーマ内のテーブルのみに制限するには、 **getschema**メソッドに渡す前に、配列の2番目の要素を "sales" に設定します。</span><span class="sxs-lookup"><span data-stu-id="d668b-125">For example, to restrict the tables returned by the **GetSchema** method to only those tables in the "Sales" schema, set the second element of the array to "Sales" before passing it to the **GetSchema** method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d668b-126">`SqlClient` と `OracleClient` の制限のコレクションには、追加の `ParameterName` 列があります。</span><span class="sxs-lookup"><span data-stu-id="d668b-126">The restrictions collections for `SqlClient` and `OracleClient` have an additional `ParameterName` column.</span></span> <span data-ttu-id="d668b-127">制限の既定の列は、下位互換性のために存在してはいますが、現在は無視されています。</span><span class="sxs-lookup"><span data-stu-id="d668b-127">The restriction default column is still there for backwards compatibility, but is currently ignored.</span></span> <span data-ttu-id="d668b-128">制限の値を指定する場合、文字列置換ではなく、パラメーター付きのクエリを使って、SQL への注入攻撃のリスクを最小限にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d668b-128">Parameterized queries rather than string replacement should be used to minimize the risk of an SQL injection attack when specifying restriction values.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d668b-129">配列内の要素数は、指定したスキーマ コレクションでサポートされる制限数以下にする必要があります。そうでない場合、<xref:System.ArgumentException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="d668b-129">The number of elements in the array must be less than or equal to the number of restrictions supported for the specified schema collection else an <xref:System.ArgumentException> will be thrown.</span></span> <span data-ttu-id="d668b-130">制限は最大数よりも小さい場合があります。</span><span class="sxs-lookup"><span data-stu-id="d668b-130">There can be fewer than the maximum number of restrictions.</span></span> <span data-ttu-id="d668b-131">指定されていない制限は、null (無制限) と見なされます。</span><span class="sxs-lookup"><span data-stu-id="d668b-131">The missing restrictions are assumed to be null (unrestricted).</span></span>  
  
 <span data-ttu-id="d668b-132">制限スキーマコレクションの名前 ("制限") を指定して**GetSchema**メソッドを呼び出すことによって、.NET Framework マネージプロバイダーに照会して、サポートされている制限の一覧を特定できます。</span><span class="sxs-lookup"><span data-stu-id="d668b-132">You can query a .NET Framework managed provider to determine the list of supported restrictions by calling the **GetSchema** method with the name of the restrictions schema collection, which is "Restrictions".</span></span> <span data-ttu-id="d668b-133">これにより、コレクション名の一覧、制限の名前、既定の制限値、および制限の番号と共に、<xref:System.Data.DataTable> が返されます。</span><span class="sxs-lookup"><span data-stu-id="d668b-133">This will return a <xref:System.Data.DataTable> with a list of the collection names, the restriction names, the default restriction values, and the restriction numbers.</span></span>  
  
### <a name="example"></a><span data-ttu-id="d668b-134">例</span><span class="sxs-lookup"><span data-stu-id="d668b-134">Example</span></span>  
 <span data-ttu-id="d668b-135">次の例では、SQL Server <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> <xref:System.Data.SqlClient.SqlConnection>クラスの .NET Framework Data Provider のメソッドを使用して、 **AdventureWorks**サンプルデータベースに格納されているすべてのテーブルに関するスキーマ情報を取得する方法を示します。"Sales" スキーマ内のテーブルのみに返される情報を制限するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="d668b-135">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database, and to restrict the information returned to only those tables in the "Sales" schema:</span></span>  
  
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
  
## <a name="sql-server-schema-restrictions"></a><span data-ttu-id="d668b-136">SQL Server スキーマの制限</span><span class="sxs-lookup"><span data-stu-id="d668b-136">SQL Server Schema Restrictions</span></span>  
 <span data-ttu-id="d668b-137">次の表に、SQL Server スキーマ コレクションの制限を示します。</span><span class="sxs-lookup"><span data-stu-id="d668b-137">The following tables list the restrictions for SQL Server schema collections.</span></span>  
  
### <a name="users"></a><span data-ttu-id="d668b-138">Users</span><span class="sxs-lookup"><span data-stu-id="d668b-138">Users</span></span>  
  
|<span data-ttu-id="d668b-139">制限の名前</span><span class="sxs-lookup"><span data-stu-id="d668b-139">Restriction Name</span></span>|<span data-ttu-id="d668b-140">[パラメーター名]</span><span class="sxs-lookup"><span data-stu-id="d668b-140">Parameter Name</span></span>|<span data-ttu-id="d668b-141">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="d668b-141">Restriction Default</span></span>|<span data-ttu-id="d668b-142">制限の番号</span><span class="sxs-lookup"><span data-stu-id="d668b-142">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d668b-143">User_Name</span><span class="sxs-lookup"><span data-stu-id="d668b-143">User_Name</span></span>|@Name|<span data-ttu-id="d668b-144">name</span><span class="sxs-lookup"><span data-stu-id="d668b-144">name</span></span>|<span data-ttu-id="d668b-145">1</span><span class="sxs-lookup"><span data-stu-id="d668b-145">1</span></span>|  
  
### <a name="databases"></a><span data-ttu-id="d668b-146">データベース</span><span class="sxs-lookup"><span data-stu-id="d668b-146">Databases</span></span>  
  
|<span data-ttu-id="d668b-147">制限の名前</span><span class="sxs-lookup"><span data-stu-id="d668b-147">Restriction Name</span></span>|<span data-ttu-id="d668b-148">[パラメーター名]</span><span class="sxs-lookup"><span data-stu-id="d668b-148">Parameter Name</span></span>|<span data-ttu-id="d668b-149">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="d668b-149">Restriction Default</span></span>|<span data-ttu-id="d668b-150">制限の番号</span><span class="sxs-lookup"><span data-stu-id="d668b-150">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d668b-151">名前</span><span class="sxs-lookup"><span data-stu-id="d668b-151">Name</span></span>|@Name|<span data-ttu-id="d668b-152">名前</span><span class="sxs-lookup"><span data-stu-id="d668b-152">Name</span></span>|<span data-ttu-id="d668b-153">1</span><span class="sxs-lookup"><span data-stu-id="d668b-153">1</span></span>|  
  
### <a name="tables"></a><span data-ttu-id="d668b-154">テーブル</span><span class="sxs-lookup"><span data-stu-id="d668b-154">Tables</span></span>  
  
|<span data-ttu-id="d668b-155">制限の名前</span><span class="sxs-lookup"><span data-stu-id="d668b-155">Restriction Name</span></span>|<span data-ttu-id="d668b-156">[パラメーター名]</span><span class="sxs-lookup"><span data-stu-id="d668b-156">Parameter Name</span></span>|<span data-ttu-id="d668b-157">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="d668b-157">Restriction Default</span></span>|<span data-ttu-id="d668b-158">制限の番号</span><span class="sxs-lookup"><span data-stu-id="d668b-158">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d668b-159">Catalog</span><span class="sxs-lookup"><span data-stu-id="d668b-159">Catalog</span></span>|@Catalog|<span data-ttu-id="d668b-160">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d668b-160">TABLE_CATALOG</span></span>|<span data-ttu-id="d668b-161">1</span><span class="sxs-lookup"><span data-stu-id="d668b-161">1</span></span>|  
|<span data-ttu-id="d668b-162">Owner</span><span class="sxs-lookup"><span data-stu-id="d668b-162">Owner</span></span>|@Owner|<span data-ttu-id="d668b-163">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d668b-163">TABLE_SCHEMA</span></span>|<span data-ttu-id="d668b-164">2</span><span class="sxs-lookup"><span data-stu-id="d668b-164">2</span></span>|  
|<span data-ttu-id="d668b-165">テーブル</span><span class="sxs-lookup"><span data-stu-id="d668b-165">Table</span></span>|@Name|<span data-ttu-id="d668b-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d668b-166">TABLE_NAME</span></span>|<span data-ttu-id="d668b-167">3</span><span class="sxs-lookup"><span data-stu-id="d668b-167">3</span></span>|  
|<span data-ttu-id="d668b-168">TableType</span><span class="sxs-lookup"><span data-stu-id="d668b-168">TableType</span></span>|@TableType|<span data-ttu-id="d668b-169">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d668b-169">TABLE_TYPE</span></span>|<span data-ttu-id="d668b-170">4</span><span class="sxs-lookup"><span data-stu-id="d668b-170">4</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="d668b-171">[列]</span><span class="sxs-lookup"><span data-stu-id="d668b-171">Columns</span></span>  
  
|<span data-ttu-id="d668b-172">制限の名前</span><span class="sxs-lookup"><span data-stu-id="d668b-172">Restriction Name</span></span>|<span data-ttu-id="d668b-173">[パラメーター名]</span><span class="sxs-lookup"><span data-stu-id="d668b-173">Parameter Name</span></span>|<span data-ttu-id="d668b-174">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="d668b-174">Restriction Default</span></span>|<span data-ttu-id="d668b-175">制限の番号</span><span class="sxs-lookup"><span data-stu-id="d668b-175">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d668b-176">Catalog</span><span class="sxs-lookup"><span data-stu-id="d668b-176">Catalog</span></span>|@Catalog|<span data-ttu-id="d668b-177">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d668b-177">TABLE_CATALOG</span></span>|<span data-ttu-id="d668b-178">1</span><span class="sxs-lookup"><span data-stu-id="d668b-178">1</span></span>|  
|<span data-ttu-id="d668b-179">Owner</span><span class="sxs-lookup"><span data-stu-id="d668b-179">Owner</span></span>|@Owner|<span data-ttu-id="d668b-180">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d668b-180">TABLE_SCHEMA</span></span>|<span data-ttu-id="d668b-181">2</span><span class="sxs-lookup"><span data-stu-id="d668b-181">2</span></span>|  
|<span data-ttu-id="d668b-182">テーブル</span><span class="sxs-lookup"><span data-stu-id="d668b-182">Table</span></span>|@Table|<span data-ttu-id="d668b-183">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d668b-183">TABLE_NAME</span></span>|<span data-ttu-id="d668b-184">3</span><span class="sxs-lookup"><span data-stu-id="d668b-184">3</span></span>|  
|<span data-ttu-id="d668b-185">[列]</span><span class="sxs-lookup"><span data-stu-id="d668b-185">Column</span></span>|@Column|<span data-ttu-id="d668b-186">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d668b-186">COLUMN_NAME</span></span>|<span data-ttu-id="d668b-187">4</span><span class="sxs-lookup"><span data-stu-id="d668b-187">4</span></span>|  
  
### <a name="structuredtypemembers"></a><span data-ttu-id="d668b-188">StructuredTypeMembers</span><span class="sxs-lookup"><span data-stu-id="d668b-188">StructuredTypeMembers</span></span>  
  
|<span data-ttu-id="d668b-189">制限の名前</span><span class="sxs-lookup"><span data-stu-id="d668b-189">Restriction Name</span></span>|<span data-ttu-id="d668b-190">[パラメーター名]</span><span class="sxs-lookup"><span data-stu-id="d668b-190">Parameter Name</span></span>|<span data-ttu-id="d668b-191">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="d668b-191">Restriction Default</span></span>|<span data-ttu-id="d668b-192">制限の番号</span><span class="sxs-lookup"><span data-stu-id="d668b-192">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d668b-193">Catalog</span><span class="sxs-lookup"><span data-stu-id="d668b-193">Catalog</span></span>|@Catalog|<span data-ttu-id="d668b-194">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d668b-194">TABLE_CATALOG</span></span>|<span data-ttu-id="d668b-195">1</span><span class="sxs-lookup"><span data-stu-id="d668b-195">1</span></span>|  
|<span data-ttu-id="d668b-196">Owner</span><span class="sxs-lookup"><span data-stu-id="d668b-196">Owner</span></span>|@Owner|<span data-ttu-id="d668b-197">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d668b-197">TABLE_SCHEMA</span></span>|<span data-ttu-id="d668b-198">2</span><span class="sxs-lookup"><span data-stu-id="d668b-198">2</span></span>|  
|<span data-ttu-id="d668b-199">テーブル</span><span class="sxs-lookup"><span data-stu-id="d668b-199">Table</span></span>|@Table|<span data-ttu-id="d668b-200">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d668b-200">TABLE_NAME</span></span>|<span data-ttu-id="d668b-201">3</span><span class="sxs-lookup"><span data-stu-id="d668b-201">3</span></span>|  
|<span data-ttu-id="d668b-202">[列]</span><span class="sxs-lookup"><span data-stu-id="d668b-202">Column</span></span>|@Column|<span data-ttu-id="d668b-203">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d668b-203">COLUMN_NAME</span></span>|<span data-ttu-id="d668b-204">4</span><span class="sxs-lookup"><span data-stu-id="d668b-204">4</span></span>|  
  
### <a name="views"></a><span data-ttu-id="d668b-205">Views</span><span class="sxs-lookup"><span data-stu-id="d668b-205">Views</span></span>  
  
|<span data-ttu-id="d668b-206">制限の名前</span><span class="sxs-lookup"><span data-stu-id="d668b-206">Restriction Name</span></span>|<span data-ttu-id="d668b-207">[パラメーター名]</span><span class="sxs-lookup"><span data-stu-id="d668b-207">Parameter Name</span></span>|<span data-ttu-id="d668b-208">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="d668b-208">Restriction Default</span></span>|<span data-ttu-id="d668b-209">制限の番号</span><span class="sxs-lookup"><span data-stu-id="d668b-209">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d668b-210">Catalog</span><span class="sxs-lookup"><span data-stu-id="d668b-210">Catalog</span></span>|@Catalog|<span data-ttu-id="d668b-211">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d668b-211">TABLE_CATALOG</span></span>|<span data-ttu-id="d668b-212">1</span><span class="sxs-lookup"><span data-stu-id="d668b-212">1</span></span>|  
|<span data-ttu-id="d668b-213">Owner</span><span class="sxs-lookup"><span data-stu-id="d668b-213">Owner</span></span>|@Owner|<span data-ttu-id="d668b-214">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d668b-214">TABLE_SCHEMA</span></span>|<span data-ttu-id="d668b-215">2</span><span class="sxs-lookup"><span data-stu-id="d668b-215">2</span></span>|  
|<span data-ttu-id="d668b-216">テーブル</span><span class="sxs-lookup"><span data-stu-id="d668b-216">Table</span></span>|@Table|<span data-ttu-id="d668b-217">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d668b-217">TABLE_NAME</span></span>|<span data-ttu-id="d668b-218">3</span><span class="sxs-lookup"><span data-stu-id="d668b-218">3</span></span>|  
  
### <a name="viewcolumns"></a><span data-ttu-id="d668b-219">ViewColumns</span><span class="sxs-lookup"><span data-stu-id="d668b-219">ViewColumns</span></span>  
  
|<span data-ttu-id="d668b-220">制限の名前</span><span class="sxs-lookup"><span data-stu-id="d668b-220">Restriction Name</span></span>|<span data-ttu-id="d668b-221">[パラメーター名]</span><span class="sxs-lookup"><span data-stu-id="d668b-221">Parameter Name</span></span>|<span data-ttu-id="d668b-222">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="d668b-222">Restriction Default</span></span>|<span data-ttu-id="d668b-223">制限の番号</span><span class="sxs-lookup"><span data-stu-id="d668b-223">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d668b-224">Catalog</span><span class="sxs-lookup"><span data-stu-id="d668b-224">Catalog</span></span>|@Catalog|<span data-ttu-id="d668b-225">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d668b-225">VIEW_CATALOG</span></span>|<span data-ttu-id="d668b-226">1</span><span class="sxs-lookup"><span data-stu-id="d668b-226">1</span></span>|  
|<span data-ttu-id="d668b-227">Owner</span><span class="sxs-lookup"><span data-stu-id="d668b-227">Owner</span></span>|@Owner|<span data-ttu-id="d668b-228">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d668b-228">VIEW_SCHEMA</span></span>|<span data-ttu-id="d668b-229">2</span><span class="sxs-lookup"><span data-stu-id="d668b-229">2</span></span>|  
|<span data-ttu-id="d668b-230">テーブル</span><span class="sxs-lookup"><span data-stu-id="d668b-230">Table</span></span>|@Table|<span data-ttu-id="d668b-231">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="d668b-231">VIEW_NAME</span></span>|<span data-ttu-id="d668b-232">3</span><span class="sxs-lookup"><span data-stu-id="d668b-232">3</span></span>|  
|<span data-ttu-id="d668b-233">[列]</span><span class="sxs-lookup"><span data-stu-id="d668b-233">Column</span></span>|@Column|<span data-ttu-id="d668b-234">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d668b-234">COLUMN_NAME</span></span>|<span data-ttu-id="d668b-235">4</span><span class="sxs-lookup"><span data-stu-id="d668b-235">4</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="d668b-236">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="d668b-236">ProcedureParameters</span></span>  
  
|<span data-ttu-id="d668b-237">制限の名前</span><span class="sxs-lookup"><span data-stu-id="d668b-237">Restriction Name</span></span>|<span data-ttu-id="d668b-238">[パラメーター名]</span><span class="sxs-lookup"><span data-stu-id="d668b-238">Parameter Name</span></span>|<span data-ttu-id="d668b-239">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="d668b-239">Restriction Default</span></span>|<span data-ttu-id="d668b-240">制限の番号</span><span class="sxs-lookup"><span data-stu-id="d668b-240">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d668b-241">Catalog</span><span class="sxs-lookup"><span data-stu-id="d668b-241">Catalog</span></span>|@Catalog|<span data-ttu-id="d668b-242">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d668b-242">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="d668b-243">1</span><span class="sxs-lookup"><span data-stu-id="d668b-243">1</span></span>|  
|<span data-ttu-id="d668b-244">Owner</span><span class="sxs-lookup"><span data-stu-id="d668b-244">Owner</span></span>|@Owner|<span data-ttu-id="d668b-245">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d668b-245">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="d668b-246">2</span><span class="sxs-lookup"><span data-stu-id="d668b-246">2</span></span>|  
|<span data-ttu-id="d668b-247">名前</span><span class="sxs-lookup"><span data-stu-id="d668b-247">Name</span></span>|@Name|<span data-ttu-id="d668b-248">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="d668b-248">SPECIFIC_NAME</span></span>|<span data-ttu-id="d668b-249">3</span><span class="sxs-lookup"><span data-stu-id="d668b-249">3</span></span>|  
|<span data-ttu-id="d668b-250">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d668b-250">Parameter</span></span>|@Parameter|<span data-ttu-id="d668b-251">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="d668b-251">PARAMETER_NAME</span></span>|<span data-ttu-id="d668b-252">4</span><span class="sxs-lookup"><span data-stu-id="d668b-252">4</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="d668b-253">手順</span><span class="sxs-lookup"><span data-stu-id="d668b-253">Procedures</span></span>  
  
|<span data-ttu-id="d668b-254">制限の名前</span><span class="sxs-lookup"><span data-stu-id="d668b-254">Restriction Name</span></span>|<span data-ttu-id="d668b-255">[パラメーター名]</span><span class="sxs-lookup"><span data-stu-id="d668b-255">Parameter Name</span></span>|<span data-ttu-id="d668b-256">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="d668b-256">Restriction Default</span></span>|<span data-ttu-id="d668b-257">制限の番号</span><span class="sxs-lookup"><span data-stu-id="d668b-257">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d668b-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="d668b-258">Catalog</span></span>|@Catalog|<span data-ttu-id="d668b-259">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d668b-259">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="d668b-260">1</span><span class="sxs-lookup"><span data-stu-id="d668b-260">1</span></span>|  
|<span data-ttu-id="d668b-261">Owner</span><span class="sxs-lookup"><span data-stu-id="d668b-261">Owner</span></span>|@Owner|<span data-ttu-id="d668b-262">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d668b-262">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="d668b-263">2</span><span class="sxs-lookup"><span data-stu-id="d668b-263">2</span></span>|  
|<span data-ttu-id="d668b-264">Name</span><span class="sxs-lookup"><span data-stu-id="d668b-264">Name</span></span>|@Name|<span data-ttu-id="d668b-265">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="d668b-265">SPECIFIC_NAME</span></span>|<span data-ttu-id="d668b-266">3</span><span class="sxs-lookup"><span data-stu-id="d668b-266">3</span></span>|  
|<span data-ttu-id="d668b-267">種類</span><span class="sxs-lookup"><span data-stu-id="d668b-267">Type</span></span>|@Type|<span data-ttu-id="d668b-268">ROUTINE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d668b-268">ROUTINE_TYPE</span></span>|<span data-ttu-id="d668b-269">4</span><span class="sxs-lookup"><span data-stu-id="d668b-269">4</span></span>|  
  
### <a name="indexcolumns"></a><span data-ttu-id="d668b-270">IndexColumns</span><span class="sxs-lookup"><span data-stu-id="d668b-270">IndexColumns</span></span>  
  
|<span data-ttu-id="d668b-271">制限の名前</span><span class="sxs-lookup"><span data-stu-id="d668b-271">Restriction Name</span></span>|<span data-ttu-id="d668b-272">[パラメーター名]</span><span class="sxs-lookup"><span data-stu-id="d668b-272">Parameter Name</span></span>|<span data-ttu-id="d668b-273">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="d668b-273">Restriction Default</span></span>|<span data-ttu-id="d668b-274">制限の番号</span><span class="sxs-lookup"><span data-stu-id="d668b-274">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d668b-275">Catalog</span><span class="sxs-lookup"><span data-stu-id="d668b-275">Catalog</span></span>|@Catalog|<span data-ttu-id="d668b-276">db_name()</span><span class="sxs-lookup"><span data-stu-id="d668b-276">db_name()</span></span>|<span data-ttu-id="d668b-277">1</span><span class="sxs-lookup"><span data-stu-id="d668b-277">1</span></span>|  
|<span data-ttu-id="d668b-278">Owner</span><span class="sxs-lookup"><span data-stu-id="d668b-278">Owner</span></span>|@Owner|<span data-ttu-id="d668b-279">user_name()</span><span class="sxs-lookup"><span data-stu-id="d668b-279">user_name()</span></span>|<span data-ttu-id="d668b-280">2</span><span class="sxs-lookup"><span data-stu-id="d668b-280">2</span></span>|  
|<span data-ttu-id="d668b-281">テーブル</span><span class="sxs-lookup"><span data-stu-id="d668b-281">Table</span></span>|@Table|<span data-ttu-id="d668b-282">o.name</span><span class="sxs-lookup"><span data-stu-id="d668b-282">o.name</span></span>|<span data-ttu-id="d668b-283">3</span><span class="sxs-lookup"><span data-stu-id="d668b-283">3</span></span>|  
|<span data-ttu-id="d668b-284">ConstraintName</span><span class="sxs-lookup"><span data-stu-id="d668b-284">ConstraintName</span></span>|@ConstraintName|<span data-ttu-id="d668b-285">x.name</span><span class="sxs-lookup"><span data-stu-id="d668b-285">x.name</span></span>|<span data-ttu-id="d668b-286">4</span><span class="sxs-lookup"><span data-stu-id="d668b-286">4</span></span>|  
|<span data-ttu-id="d668b-287">[列]</span><span class="sxs-lookup"><span data-stu-id="d668b-287">Column</span></span>|@Column|<span data-ttu-id="d668b-288">c.name</span><span class="sxs-lookup"><span data-stu-id="d668b-288">c.name</span></span>|<span data-ttu-id="d668b-289">5</span><span class="sxs-lookup"><span data-stu-id="d668b-289">5</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="d668b-290">インデックス</span><span class="sxs-lookup"><span data-stu-id="d668b-290">Indexes</span></span>  
  
|<span data-ttu-id="d668b-291">制限の名前</span><span class="sxs-lookup"><span data-stu-id="d668b-291">Restriction Name</span></span>|<span data-ttu-id="d668b-292">[パラメーター名]</span><span class="sxs-lookup"><span data-stu-id="d668b-292">Parameter Name</span></span>|<span data-ttu-id="d668b-293">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="d668b-293">Restriction Default</span></span>|<span data-ttu-id="d668b-294">制限の番号</span><span class="sxs-lookup"><span data-stu-id="d668b-294">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d668b-295">Catalog</span><span class="sxs-lookup"><span data-stu-id="d668b-295">Catalog</span></span>|@Catalog|<span data-ttu-id="d668b-296">db_name()</span><span class="sxs-lookup"><span data-stu-id="d668b-296">db_name()</span></span>|<span data-ttu-id="d668b-297">1</span><span class="sxs-lookup"><span data-stu-id="d668b-297">1</span></span>|  
|<span data-ttu-id="d668b-298">Owner</span><span class="sxs-lookup"><span data-stu-id="d668b-298">Owner</span></span>|@Owner|<span data-ttu-id="d668b-299">user_name()</span><span class="sxs-lookup"><span data-stu-id="d668b-299">user_name()</span></span>|<span data-ttu-id="d668b-300">2</span><span class="sxs-lookup"><span data-stu-id="d668b-300">2</span></span>|  
|<span data-ttu-id="d668b-301">テーブル</span><span class="sxs-lookup"><span data-stu-id="d668b-301">Table</span></span>|@Table|<span data-ttu-id="d668b-302">o.name</span><span class="sxs-lookup"><span data-stu-id="d668b-302">o.name</span></span>|<span data-ttu-id="d668b-303">3</span><span class="sxs-lookup"><span data-stu-id="d668b-303">3</span></span>|  
  
### <a name="userdefinedtypes"></a><span data-ttu-id="d668b-304">UserDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="d668b-304">UserDefinedTypes</span></span>  
  
|<span data-ttu-id="d668b-305">制限の名前</span><span class="sxs-lookup"><span data-stu-id="d668b-305">Restriction Name</span></span>|<span data-ttu-id="d668b-306">[パラメーター名]</span><span class="sxs-lookup"><span data-stu-id="d668b-306">Parameter Name</span></span>|<span data-ttu-id="d668b-307">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="d668b-307">Restriction Default</span></span>|<span data-ttu-id="d668b-308">制限の番号</span><span class="sxs-lookup"><span data-stu-id="d668b-308">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d668b-309">assembly_name</span><span class="sxs-lookup"><span data-stu-id="d668b-309">assembly_name</span></span>|@AssemblyName|<span data-ttu-id="d668b-310">assemblies.name</span><span class="sxs-lookup"><span data-stu-id="d668b-310">assemblies.name</span></span>|<span data-ttu-id="d668b-311">1</span><span class="sxs-lookup"><span data-stu-id="d668b-311">1</span></span>|  
|<span data-ttu-id="d668b-312">udt_name</span><span class="sxs-lookup"><span data-stu-id="d668b-312">udt_name</span></span>|@UDTName|<span data-ttu-id="d668b-313">types.assembly_class</span><span class="sxs-lookup"><span data-stu-id="d668b-313">types.assembly_class</span></span>|<span data-ttu-id="d668b-314">2</span><span class="sxs-lookup"><span data-stu-id="d668b-314">2</span></span>|  
  
### <a name="foreignkeys"></a><span data-ttu-id="d668b-315">ForeignKeys</span><span class="sxs-lookup"><span data-stu-id="d668b-315">ForeignKeys</span></span>  
  
|<span data-ttu-id="d668b-316">制限の名前</span><span class="sxs-lookup"><span data-stu-id="d668b-316">Restriction Name</span></span>|<span data-ttu-id="d668b-317">[パラメーター名]</span><span class="sxs-lookup"><span data-stu-id="d668b-317">Parameter Name</span></span>|<span data-ttu-id="d668b-318">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="d668b-318">Restriction Default</span></span>|<span data-ttu-id="d668b-319">制限の番号</span><span class="sxs-lookup"><span data-stu-id="d668b-319">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d668b-320">Catalog</span><span class="sxs-lookup"><span data-stu-id="d668b-320">Catalog</span></span>|@Catalog|<span data-ttu-id="d668b-321">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d668b-321">CONSTRAINT_CATALOG</span></span>|<span data-ttu-id="d668b-322">1</span><span class="sxs-lookup"><span data-stu-id="d668b-322">1</span></span>|  
|<span data-ttu-id="d668b-323">Owner</span><span class="sxs-lookup"><span data-stu-id="d668b-323">Owner</span></span>|@Owner|<span data-ttu-id="d668b-324">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d668b-324">CONSTRAINT_SCHEMA</span></span>|<span data-ttu-id="d668b-325">2</span><span class="sxs-lookup"><span data-stu-id="d668b-325">2</span></span>|  
|<span data-ttu-id="d668b-326">テーブル</span><span class="sxs-lookup"><span data-stu-id="d668b-326">Table</span></span>|@Table|<span data-ttu-id="d668b-327">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d668b-327">TABLE_NAME</span></span>|<span data-ttu-id="d668b-328">3</span><span class="sxs-lookup"><span data-stu-id="d668b-328">3</span></span>|  
|<span data-ttu-id="d668b-329">名前</span><span class="sxs-lookup"><span data-stu-id="d668b-329">Name</span></span>|@Name|<span data-ttu-id="d668b-330">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="d668b-330">CONSTRAINT_NAME</span></span>|<span data-ttu-id="d668b-331">4</span><span class="sxs-lookup"><span data-stu-id="d668b-331">4</span></span>|  
  
## <a name="sql-server-2008-schema-restrictions"></a><span data-ttu-id="d668b-332">SQL Server 2008 スキーマの制限</span><span class="sxs-lookup"><span data-stu-id="d668b-332">SQL Server 2008 Schema Restrictions</span></span>  
 <span data-ttu-id="d668b-333">次の表に、SQL Server 2008 スキーマ コレクションの制限を示します。</span><span class="sxs-lookup"><span data-stu-id="d668b-333">The following tables list the restrictions for SQL Server 2008 schema collections.</span></span> <span data-ttu-id="d668b-334">これらの制限は、.NET Framework 3.5 SP1 および SQL Server 2008 以降で有効です。</span><span class="sxs-lookup"><span data-stu-id="d668b-334">These restrictions are valid beginning with version 3.5 SP1 of the .NET Framework and SQL Server 2008.</span></span> <span data-ttu-id="d668b-335">これらの制限は、以前のバージョンの .NET Framework および SQL Server ではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="d668b-335">They are not supported in earlier versions of the .NET Framework and SQL Server.</span></span>  
  
### <a name="columnsetcolumns"></a><span data-ttu-id="d668b-336">ColumnSetColumns</span><span class="sxs-lookup"><span data-stu-id="d668b-336">ColumnSetColumns</span></span>  
  
|<span data-ttu-id="d668b-337">制限の名前</span><span class="sxs-lookup"><span data-stu-id="d668b-337">Restriction Name</span></span>|<span data-ttu-id="d668b-338">[パラメーター名]</span><span class="sxs-lookup"><span data-stu-id="d668b-338">Parameter Name</span></span>|<span data-ttu-id="d668b-339">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="d668b-339">Restriction Default</span></span>|<span data-ttu-id="d668b-340">制限の番号</span><span class="sxs-lookup"><span data-stu-id="d668b-340">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d668b-341">Catalog</span><span class="sxs-lookup"><span data-stu-id="d668b-341">Catalog</span></span>|@Catalog|<span data-ttu-id="d668b-342">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d668b-342">TABLE_CATALOG</span></span>|<span data-ttu-id="d668b-343">1</span><span class="sxs-lookup"><span data-stu-id="d668b-343">1</span></span>|  
|<span data-ttu-id="d668b-344">Owner</span><span class="sxs-lookup"><span data-stu-id="d668b-344">Owner</span></span>|@Owner|<span data-ttu-id="d668b-345">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d668b-345">TABLE_SCHEMA</span></span>|<span data-ttu-id="d668b-346">2</span><span class="sxs-lookup"><span data-stu-id="d668b-346">2</span></span>|  
|<span data-ttu-id="d668b-347">テーブル</span><span class="sxs-lookup"><span data-stu-id="d668b-347">Table</span></span>|@Table|<span data-ttu-id="d668b-348">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d668b-348">TABLE_NAME</span></span>|<span data-ttu-id="d668b-349">3</span><span class="sxs-lookup"><span data-stu-id="d668b-349">3</span></span>|  
  
### <a name="allcolumns"></a><span data-ttu-id="d668b-350">AllColumns</span><span class="sxs-lookup"><span data-stu-id="d668b-350">AllColumns</span></span>  
  
|<span data-ttu-id="d668b-351">制限の名前</span><span class="sxs-lookup"><span data-stu-id="d668b-351">Restriction Name</span></span>|<span data-ttu-id="d668b-352">[パラメーター名]</span><span class="sxs-lookup"><span data-stu-id="d668b-352">Parameter Name</span></span>|<span data-ttu-id="d668b-353">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="d668b-353">Restriction Default</span></span>|<span data-ttu-id="d668b-354">制限の番号</span><span class="sxs-lookup"><span data-stu-id="d668b-354">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d668b-355">Catalog</span><span class="sxs-lookup"><span data-stu-id="d668b-355">Catalog</span></span>|@Catalog|<span data-ttu-id="d668b-356">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d668b-356">TABLE_CATALOG</span></span>|<span data-ttu-id="d668b-357">1</span><span class="sxs-lookup"><span data-stu-id="d668b-357">1</span></span>|  
|<span data-ttu-id="d668b-358">Owner</span><span class="sxs-lookup"><span data-stu-id="d668b-358">Owner</span></span>|@Owner|<span data-ttu-id="d668b-359">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d668b-359">TABLE_SCHEMA</span></span>|<span data-ttu-id="d668b-360">2</span><span class="sxs-lookup"><span data-stu-id="d668b-360">2</span></span>|  
|<span data-ttu-id="d668b-361">テーブル</span><span class="sxs-lookup"><span data-stu-id="d668b-361">Table</span></span>|@Table|<span data-ttu-id="d668b-362">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d668b-362">TABLE_NAME</span></span>|<span data-ttu-id="d668b-363">3</span><span class="sxs-lookup"><span data-stu-id="d668b-363">3</span></span>|  
|<span data-ttu-id="d668b-364">[列]</span><span class="sxs-lookup"><span data-stu-id="d668b-364">Column</span></span>|@Column|<span data-ttu-id="d668b-365">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d668b-365">COLUMN_NAME</span></span>|<span data-ttu-id="d668b-366">4</span><span class="sxs-lookup"><span data-stu-id="d668b-366">4</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d668b-367">関連項目</span><span class="sxs-lookup"><span data-stu-id="d668b-367">See also</span></span>

- [<span data-ttu-id="d668b-368">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="d668b-368">ADO.NET Overview</span></span>](ado-net-overview.md)
