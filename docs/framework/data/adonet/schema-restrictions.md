---
title: スキーマの制限
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
ms.openlocfilehash: 1a2c32d133799ee5338c18d0f51bced49cb3dc4b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963183"
---
# <a name="schema-restrictions"></a><span data-ttu-id="d6378-102">スキーマの制限</span><span class="sxs-lookup"><span data-stu-id="d6378-102">Schema Restrictions</span></span>
<span data-ttu-id="d6378-103">**Getschema**メソッドの2番目の省略可能なパラメーターは、返されるスキーマ情報の量を制限するために使用される制限です。これは、文字列の配列として**getschema**メソッドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="d6378-103">The second optional parameter of the **GetSchema** method is the restrictions that are used to limit the amount of schema information returned, and it is passed to the **GetSchema** method as an array of strings.</span></span> <span data-ttu-id="d6378-104">配列での位置により、渡すことができる値が決定します。これは、制限の番号に相当します。</span><span class="sxs-lookup"><span data-stu-id="d6378-104">The position in the array determines the values that you can pass, and this is equivalent to the restriction number.</span></span>  
  
 <span data-ttu-id="d6378-105">たとえば、次の表は、.NET Framework Data Provider for SQL Server を使用して、"Tables" スキーマ コレクションによりサポートされる制限を示しています。</span><span class="sxs-lookup"><span data-stu-id="d6378-105">For example, the following table describes the restrictions supported by the "Tables" schema collection using the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="d6378-106">SQL Server スキーマ コレクションの追加の制限をこのトピックの終わりに示します。</span><span class="sxs-lookup"><span data-stu-id="d6378-106">Additional restrictions for SQL Server schema collections are listed at the end of this topic.</span></span>  
  
|<span data-ttu-id="d6378-107">制限の名前</span><span class="sxs-lookup"><span data-stu-id="d6378-107">Restriction Name</span></span>|<span data-ttu-id="d6378-108">[パラメーター名]</span><span class="sxs-lookup"><span data-stu-id="d6378-108">Parameter Name</span></span>|<span data-ttu-id="d6378-109">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="d6378-109">Restriction Default</span></span>|<span data-ttu-id="d6378-110">制限の番号</span><span class="sxs-lookup"><span data-stu-id="d6378-110">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d6378-111">Catalog</span><span class="sxs-lookup"><span data-stu-id="d6378-111">Catalog</span></span>|@Catalog|<span data-ttu-id="d6378-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d6378-112">TABLE_CATALOG</span></span>|<span data-ttu-id="d6378-113">1</span><span class="sxs-lookup"><span data-stu-id="d6378-113">1</span></span>|  
|<span data-ttu-id="d6378-114">Owner</span><span class="sxs-lookup"><span data-stu-id="d6378-114">Owner</span></span>|@Owner|<span data-ttu-id="d6378-115">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d6378-115">TABLE_SCHEMA</span></span>|<span data-ttu-id="d6378-116">2</span><span class="sxs-lookup"><span data-stu-id="d6378-116">2</span></span>|  
|<span data-ttu-id="d6378-117">テーブル</span><span class="sxs-lookup"><span data-stu-id="d6378-117">Table</span></span>|@Name|<span data-ttu-id="d6378-118">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d6378-118">TABLE_NAME</span></span>|<span data-ttu-id="d6378-119">3</span><span class="sxs-lookup"><span data-stu-id="d6378-119">3</span></span>|  
|<span data-ttu-id="d6378-120">TableType</span><span class="sxs-lookup"><span data-stu-id="d6378-120">TableType</span></span>|@TableType|<span data-ttu-id="d6378-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d6378-121">TABLE_TYPE</span></span>|<span data-ttu-id="d6378-122">4</span><span class="sxs-lookup"><span data-stu-id="d6378-122">4</span></span>|  
  
## <a name="specifying-restriction-values"></a><span data-ttu-id="d6378-123">制限値の指定</span><span class="sxs-lookup"><span data-stu-id="d6378-123">Specifying Restriction Values</span></span>  
 <span data-ttu-id="d6378-124">"Tables" スキーマ コレクションの制限の 1 つを使用するには、4 つの要素を使って文字列の配列を作成してから、制限の番号と一致する要素内に値を配置します。</span><span class="sxs-lookup"><span data-stu-id="d6378-124">To use one of the restrictions of the "Tables" schema collection, simply create an array of strings with four elements, then place a value in the element that matches the restriction number.</span></span> <span data-ttu-id="d6378-125">たとえば、 **getschema**メソッドによって返されるテーブルを、"sales" スキーマ内のテーブルのみに制限するには、 **getschema**メソッドに渡す前に、配列の2番目の要素を "sales" に設定します。</span><span class="sxs-lookup"><span data-stu-id="d6378-125">For example, to restrict the tables returned by the **GetSchema** method to only those tables in the "Sales" schema, set the second element of the array to "Sales" before passing it to the **GetSchema** method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d6378-126">`SqlClient` と `OracleClient` の制限のコレクションには、追加の `ParameterName` 列があります。</span><span class="sxs-lookup"><span data-stu-id="d6378-126">The restrictions collections for `SqlClient` and `OracleClient` have an additional `ParameterName` column.</span></span> <span data-ttu-id="d6378-127">制限の既定の列は、下位互換性のために存在してはいますが、現在は無視されています。</span><span class="sxs-lookup"><span data-stu-id="d6378-127">The restriction default column is still there for backwards compatibility, but is currently ignored.</span></span> <span data-ttu-id="d6378-128">制限の値を指定する場合、文字列置換ではなく、パラメーター付きのクエリを使って、SQL への注入攻撃のリスクを最小限にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6378-128">Parameterized queries rather than string replacement should be used to minimize the risk of an SQL injection attack when specifying restriction values.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d6378-129">配列内の要素数は、指定したスキーマ コレクションでサポートされる制限数以下にする必要があります。そうでない場合、<xref:System.ArgumentException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="d6378-129">The number of elements in the array must be less than or equal to the number of restrictions supported for the specified schema collection else an <xref:System.ArgumentException> will be thrown.</span></span> <span data-ttu-id="d6378-130">制限は最大数よりも小さい場合があります。</span><span class="sxs-lookup"><span data-stu-id="d6378-130">There can be fewer than the maximum number of restrictions.</span></span> <span data-ttu-id="d6378-131">指定されていない制限は、null (無制限) と見なされます。</span><span class="sxs-lookup"><span data-stu-id="d6378-131">The missing restrictions are assumed to be null (unrestricted).</span></span>  
  
 <span data-ttu-id="d6378-132">制限スキーマコレクションの名前 ("制限") を指定して**GetSchema**メソッドを呼び出すことによって、.NET Framework マネージプロバイダーに照会して、サポートされている制限の一覧を特定できます。</span><span class="sxs-lookup"><span data-stu-id="d6378-132">You can query a .NET Framework managed provider to determine the list of supported restrictions by calling the **GetSchema** method with the name of the restrictions schema collection, which is "Restrictions".</span></span> <span data-ttu-id="d6378-133">これにより、コレクション名の一覧、制限の名前、既定の制限値、および制限の番号と共に、<xref:System.Data.DataTable> が返されます。</span><span class="sxs-lookup"><span data-stu-id="d6378-133">This will return a <xref:System.Data.DataTable> with a list of the collection names, the restriction names, the default restriction values, and the restriction numbers.</span></span>  
  
### <a name="example"></a><span data-ttu-id="d6378-134">例</span><span class="sxs-lookup"><span data-stu-id="d6378-134">Example</span></span>  
 <span data-ttu-id="d6378-135">次の例では、SQL Server <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> <xref:System.Data.SqlClient.SqlConnection>クラスの .NET Framework Data Provider のメソッドを使用して、 **AdventureWorks**サンプルデータベースに格納されているすべてのテーブルに関するスキーマ情報を取得する方法を示します。"Sales" スキーマ内のテーブルのみに返される情報を制限するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="d6378-135">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database, and to restrict the information returned to only those tables in the "Sales" schema:</span></span>  
  
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
  
## <a name="sql-server-schema-restrictions"></a><span data-ttu-id="d6378-136">SQL Server スキーマの制限</span><span class="sxs-lookup"><span data-stu-id="d6378-136">SQL Server Schema Restrictions</span></span>  
 <span data-ttu-id="d6378-137">次の表に、SQL Server スキーマ コレクションの制限を示します。</span><span class="sxs-lookup"><span data-stu-id="d6378-137">The following tables list the restrictions for SQL Server schema collections.</span></span>  
  
### <a name="users"></a><span data-ttu-id="d6378-138">Users</span><span class="sxs-lookup"><span data-stu-id="d6378-138">Users</span></span>  
  
|<span data-ttu-id="d6378-139">制限の名前</span><span class="sxs-lookup"><span data-stu-id="d6378-139">Restriction Name</span></span>|<span data-ttu-id="d6378-140">[パラメーター名]</span><span class="sxs-lookup"><span data-stu-id="d6378-140">Parameter Name</span></span>|<span data-ttu-id="d6378-141">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="d6378-141">Restriction Default</span></span>|<span data-ttu-id="d6378-142">制限の番号</span><span class="sxs-lookup"><span data-stu-id="d6378-142">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d6378-143">User_Name</span><span class="sxs-lookup"><span data-stu-id="d6378-143">User_Name</span></span>|@Name|<span data-ttu-id="d6378-144">name</span><span class="sxs-lookup"><span data-stu-id="d6378-144">name</span></span>|<span data-ttu-id="d6378-145">1</span><span class="sxs-lookup"><span data-stu-id="d6378-145">1</span></span>|  
  
### <a name="databases"></a><span data-ttu-id="d6378-146">データベース</span><span class="sxs-lookup"><span data-stu-id="d6378-146">Databases</span></span>  
  
|<span data-ttu-id="d6378-147">制限の名前</span><span class="sxs-lookup"><span data-stu-id="d6378-147">Restriction Name</span></span>|<span data-ttu-id="d6378-148">[パラメーター名]</span><span class="sxs-lookup"><span data-stu-id="d6378-148">Parameter Name</span></span>|<span data-ttu-id="d6378-149">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="d6378-149">Restriction Default</span></span>|<span data-ttu-id="d6378-150">制限の番号</span><span class="sxs-lookup"><span data-stu-id="d6378-150">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d6378-151">Name</span><span class="sxs-lookup"><span data-stu-id="d6378-151">Name</span></span>|@Name|<span data-ttu-id="d6378-152">Name</span><span class="sxs-lookup"><span data-stu-id="d6378-152">Name</span></span>|<span data-ttu-id="d6378-153">1</span><span class="sxs-lookup"><span data-stu-id="d6378-153">1</span></span>|  
  
### <a name="tables"></a><span data-ttu-id="d6378-154">テーブル</span><span class="sxs-lookup"><span data-stu-id="d6378-154">Tables</span></span>  
  
|<span data-ttu-id="d6378-155">制限の名前</span><span class="sxs-lookup"><span data-stu-id="d6378-155">Restriction Name</span></span>|<span data-ttu-id="d6378-156">[パラメーター名]</span><span class="sxs-lookup"><span data-stu-id="d6378-156">Parameter Name</span></span>|<span data-ttu-id="d6378-157">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="d6378-157">Restriction Default</span></span>|<span data-ttu-id="d6378-158">制限の番号</span><span class="sxs-lookup"><span data-stu-id="d6378-158">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d6378-159">Catalog</span><span class="sxs-lookup"><span data-stu-id="d6378-159">Catalog</span></span>|@Catalog|<span data-ttu-id="d6378-160">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d6378-160">TABLE_CATALOG</span></span>|<span data-ttu-id="d6378-161">1</span><span class="sxs-lookup"><span data-stu-id="d6378-161">1</span></span>|  
|<span data-ttu-id="d6378-162">Owner</span><span class="sxs-lookup"><span data-stu-id="d6378-162">Owner</span></span>|@Owner|<span data-ttu-id="d6378-163">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d6378-163">TABLE_SCHEMA</span></span>|<span data-ttu-id="d6378-164">2</span><span class="sxs-lookup"><span data-stu-id="d6378-164">2</span></span>|  
|<span data-ttu-id="d6378-165">テーブル</span><span class="sxs-lookup"><span data-stu-id="d6378-165">Table</span></span>|@Name|<span data-ttu-id="d6378-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d6378-166">TABLE_NAME</span></span>|<span data-ttu-id="d6378-167">3</span><span class="sxs-lookup"><span data-stu-id="d6378-167">3</span></span>|  
|<span data-ttu-id="d6378-168">TableType</span><span class="sxs-lookup"><span data-stu-id="d6378-168">TableType</span></span>|@TableType|<span data-ttu-id="d6378-169">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d6378-169">TABLE_TYPE</span></span>|<span data-ttu-id="d6378-170">4</span><span class="sxs-lookup"><span data-stu-id="d6378-170">4</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="d6378-171">[列]</span><span class="sxs-lookup"><span data-stu-id="d6378-171">Columns</span></span>  
  
|<span data-ttu-id="d6378-172">制限の名前</span><span class="sxs-lookup"><span data-stu-id="d6378-172">Restriction Name</span></span>|<span data-ttu-id="d6378-173">[パラメーター名]</span><span class="sxs-lookup"><span data-stu-id="d6378-173">Parameter Name</span></span>|<span data-ttu-id="d6378-174">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="d6378-174">Restriction Default</span></span>|<span data-ttu-id="d6378-175">制限の番号</span><span class="sxs-lookup"><span data-stu-id="d6378-175">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d6378-176">Catalog</span><span class="sxs-lookup"><span data-stu-id="d6378-176">Catalog</span></span>|@Catalog|<span data-ttu-id="d6378-177">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d6378-177">TABLE_CATALOG</span></span>|<span data-ttu-id="d6378-178">1</span><span class="sxs-lookup"><span data-stu-id="d6378-178">1</span></span>|  
|<span data-ttu-id="d6378-179">Owner</span><span class="sxs-lookup"><span data-stu-id="d6378-179">Owner</span></span>|@Owner|<span data-ttu-id="d6378-180">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d6378-180">TABLE_SCHEMA</span></span>|<span data-ttu-id="d6378-181">2</span><span class="sxs-lookup"><span data-stu-id="d6378-181">2</span></span>|  
|<span data-ttu-id="d6378-182">テーブル</span><span class="sxs-lookup"><span data-stu-id="d6378-182">Table</span></span>|@Table|<span data-ttu-id="d6378-183">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d6378-183">TABLE_NAME</span></span>|<span data-ttu-id="d6378-184">3</span><span class="sxs-lookup"><span data-stu-id="d6378-184">3</span></span>|  
|<span data-ttu-id="d6378-185">[列]</span><span class="sxs-lookup"><span data-stu-id="d6378-185">Column</span></span>|@Column|<span data-ttu-id="d6378-186">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d6378-186">COLUMN_NAME</span></span>|<span data-ttu-id="d6378-187">4</span><span class="sxs-lookup"><span data-stu-id="d6378-187">4</span></span>|  
  
### <a name="structuredtypemembers"></a><span data-ttu-id="d6378-188">StructuredTypeMembers</span><span class="sxs-lookup"><span data-stu-id="d6378-188">StructuredTypeMembers</span></span>  
  
|<span data-ttu-id="d6378-189">制限の名前</span><span class="sxs-lookup"><span data-stu-id="d6378-189">Restriction Name</span></span>|<span data-ttu-id="d6378-190">[パラメーター名]</span><span class="sxs-lookup"><span data-stu-id="d6378-190">Parameter Name</span></span>|<span data-ttu-id="d6378-191">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="d6378-191">Restriction Default</span></span>|<span data-ttu-id="d6378-192">制限の番号</span><span class="sxs-lookup"><span data-stu-id="d6378-192">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d6378-193">Catalog</span><span class="sxs-lookup"><span data-stu-id="d6378-193">Catalog</span></span>|@Catalog|<span data-ttu-id="d6378-194">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d6378-194">TABLE_CATALOG</span></span>|<span data-ttu-id="d6378-195">1</span><span class="sxs-lookup"><span data-stu-id="d6378-195">1</span></span>|  
|<span data-ttu-id="d6378-196">Owner</span><span class="sxs-lookup"><span data-stu-id="d6378-196">Owner</span></span>|@Owner|<span data-ttu-id="d6378-197">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d6378-197">TABLE_SCHEMA</span></span>|<span data-ttu-id="d6378-198">2</span><span class="sxs-lookup"><span data-stu-id="d6378-198">2</span></span>|  
|<span data-ttu-id="d6378-199">テーブル</span><span class="sxs-lookup"><span data-stu-id="d6378-199">Table</span></span>|@Table|<span data-ttu-id="d6378-200">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d6378-200">TABLE_NAME</span></span>|<span data-ttu-id="d6378-201">3</span><span class="sxs-lookup"><span data-stu-id="d6378-201">3</span></span>|  
|<span data-ttu-id="d6378-202">[列]</span><span class="sxs-lookup"><span data-stu-id="d6378-202">Column</span></span>|@Column|<span data-ttu-id="d6378-203">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d6378-203">COLUMN_NAME</span></span>|<span data-ttu-id="d6378-204">4</span><span class="sxs-lookup"><span data-stu-id="d6378-204">4</span></span>|  
  
### <a name="views"></a><span data-ttu-id="d6378-205">Views</span><span class="sxs-lookup"><span data-stu-id="d6378-205">Views</span></span>  
  
|<span data-ttu-id="d6378-206">制限の名前</span><span class="sxs-lookup"><span data-stu-id="d6378-206">Restriction Name</span></span>|<span data-ttu-id="d6378-207">[パラメーター名]</span><span class="sxs-lookup"><span data-stu-id="d6378-207">Parameter Name</span></span>|<span data-ttu-id="d6378-208">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="d6378-208">Restriction Default</span></span>|<span data-ttu-id="d6378-209">制限の番号</span><span class="sxs-lookup"><span data-stu-id="d6378-209">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d6378-210">Catalog</span><span class="sxs-lookup"><span data-stu-id="d6378-210">Catalog</span></span>|@Catalog|<span data-ttu-id="d6378-211">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d6378-211">TABLE_CATALOG</span></span>|<span data-ttu-id="d6378-212">1</span><span class="sxs-lookup"><span data-stu-id="d6378-212">1</span></span>|  
|<span data-ttu-id="d6378-213">Owner</span><span class="sxs-lookup"><span data-stu-id="d6378-213">Owner</span></span>|@Owner|<span data-ttu-id="d6378-214">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d6378-214">TABLE_SCHEMA</span></span>|<span data-ttu-id="d6378-215">2</span><span class="sxs-lookup"><span data-stu-id="d6378-215">2</span></span>|  
|<span data-ttu-id="d6378-216">テーブル</span><span class="sxs-lookup"><span data-stu-id="d6378-216">Table</span></span>|@Table|<span data-ttu-id="d6378-217">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d6378-217">TABLE_NAME</span></span>|<span data-ttu-id="d6378-218">3</span><span class="sxs-lookup"><span data-stu-id="d6378-218">3</span></span>|  
  
### <a name="viewcolumns"></a><span data-ttu-id="d6378-219">ViewColumns</span><span class="sxs-lookup"><span data-stu-id="d6378-219">ViewColumns</span></span>  
  
|<span data-ttu-id="d6378-220">制限の名前</span><span class="sxs-lookup"><span data-stu-id="d6378-220">Restriction Name</span></span>|<span data-ttu-id="d6378-221">[パラメーター名]</span><span class="sxs-lookup"><span data-stu-id="d6378-221">Parameter Name</span></span>|<span data-ttu-id="d6378-222">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="d6378-222">Restriction Default</span></span>|<span data-ttu-id="d6378-223">制限の番号</span><span class="sxs-lookup"><span data-stu-id="d6378-223">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d6378-224">Catalog</span><span class="sxs-lookup"><span data-stu-id="d6378-224">Catalog</span></span>|@Catalog|<span data-ttu-id="d6378-225">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d6378-225">VIEW_CATALOG</span></span>|<span data-ttu-id="d6378-226">1</span><span class="sxs-lookup"><span data-stu-id="d6378-226">1</span></span>|  
|<span data-ttu-id="d6378-227">Owner</span><span class="sxs-lookup"><span data-stu-id="d6378-227">Owner</span></span>|@Owner|<span data-ttu-id="d6378-228">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d6378-228">VIEW_SCHEMA</span></span>|<span data-ttu-id="d6378-229">2</span><span class="sxs-lookup"><span data-stu-id="d6378-229">2</span></span>|  
|<span data-ttu-id="d6378-230">テーブル</span><span class="sxs-lookup"><span data-stu-id="d6378-230">Table</span></span>|@Table|<span data-ttu-id="d6378-231">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="d6378-231">VIEW_NAME</span></span>|<span data-ttu-id="d6378-232">3</span><span class="sxs-lookup"><span data-stu-id="d6378-232">3</span></span>|  
|<span data-ttu-id="d6378-233">[列]</span><span class="sxs-lookup"><span data-stu-id="d6378-233">Column</span></span>|@Column|<span data-ttu-id="d6378-234">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d6378-234">COLUMN_NAME</span></span>|<span data-ttu-id="d6378-235">4</span><span class="sxs-lookup"><span data-stu-id="d6378-235">4</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="d6378-236">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="d6378-236">ProcedureParameters</span></span>  
  
|<span data-ttu-id="d6378-237">制限の名前</span><span class="sxs-lookup"><span data-stu-id="d6378-237">Restriction Name</span></span>|<span data-ttu-id="d6378-238">[パラメーター名]</span><span class="sxs-lookup"><span data-stu-id="d6378-238">Parameter Name</span></span>|<span data-ttu-id="d6378-239">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="d6378-239">Restriction Default</span></span>|<span data-ttu-id="d6378-240">制限の番号</span><span class="sxs-lookup"><span data-stu-id="d6378-240">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d6378-241">Catalog</span><span class="sxs-lookup"><span data-stu-id="d6378-241">Catalog</span></span>|@Catalog|<span data-ttu-id="d6378-242">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d6378-242">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="d6378-243">1</span><span class="sxs-lookup"><span data-stu-id="d6378-243">1</span></span>|  
|<span data-ttu-id="d6378-244">Owner</span><span class="sxs-lookup"><span data-stu-id="d6378-244">Owner</span></span>|@Owner|<span data-ttu-id="d6378-245">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d6378-245">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="d6378-246">2</span><span class="sxs-lookup"><span data-stu-id="d6378-246">2</span></span>|  
|<span data-ttu-id="d6378-247">Name</span><span class="sxs-lookup"><span data-stu-id="d6378-247">Name</span></span>|@Name|<span data-ttu-id="d6378-248">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="d6378-248">SPECIFIC_NAME</span></span>|<span data-ttu-id="d6378-249">3</span><span class="sxs-lookup"><span data-stu-id="d6378-249">3</span></span>|  
|<span data-ttu-id="d6378-250">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d6378-250">Parameter</span></span>|@Parameter|<span data-ttu-id="d6378-251">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="d6378-251">PARAMETER_NAME</span></span>|<span data-ttu-id="d6378-252">4</span><span class="sxs-lookup"><span data-stu-id="d6378-252">4</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="d6378-253">手順</span><span class="sxs-lookup"><span data-stu-id="d6378-253">Procedures</span></span>  
  
|<span data-ttu-id="d6378-254">制限の名前</span><span class="sxs-lookup"><span data-stu-id="d6378-254">Restriction Name</span></span>|<span data-ttu-id="d6378-255">[パラメーター名]</span><span class="sxs-lookup"><span data-stu-id="d6378-255">Parameter Name</span></span>|<span data-ttu-id="d6378-256">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="d6378-256">Restriction Default</span></span>|<span data-ttu-id="d6378-257">制限の番号</span><span class="sxs-lookup"><span data-stu-id="d6378-257">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d6378-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="d6378-258">Catalog</span></span>|@Catalog|<span data-ttu-id="d6378-259">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d6378-259">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="d6378-260">1</span><span class="sxs-lookup"><span data-stu-id="d6378-260">1</span></span>|  
|<span data-ttu-id="d6378-261">Owner</span><span class="sxs-lookup"><span data-stu-id="d6378-261">Owner</span></span>|@Owner|<span data-ttu-id="d6378-262">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d6378-262">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="d6378-263">2</span><span class="sxs-lookup"><span data-stu-id="d6378-263">2</span></span>|  
|<span data-ttu-id="d6378-264">名前</span><span class="sxs-lookup"><span data-stu-id="d6378-264">Name</span></span>|@Name|<span data-ttu-id="d6378-265">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="d6378-265">SPECIFIC_NAME</span></span>|<span data-ttu-id="d6378-266">3</span><span class="sxs-lookup"><span data-stu-id="d6378-266">3</span></span>|  
|<span data-ttu-id="d6378-267">種類</span><span class="sxs-lookup"><span data-stu-id="d6378-267">Type</span></span>|@Type|<span data-ttu-id="d6378-268">ROUTINE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d6378-268">ROUTINE_TYPE</span></span>|<span data-ttu-id="d6378-269">4</span><span class="sxs-lookup"><span data-stu-id="d6378-269">4</span></span>|  
  
### <a name="indexcolumns"></a><span data-ttu-id="d6378-270">IndexColumns</span><span class="sxs-lookup"><span data-stu-id="d6378-270">IndexColumns</span></span>  
  
|<span data-ttu-id="d6378-271">制限の名前</span><span class="sxs-lookup"><span data-stu-id="d6378-271">Restriction Name</span></span>|<span data-ttu-id="d6378-272">[パラメーター名]</span><span class="sxs-lookup"><span data-stu-id="d6378-272">Parameter Name</span></span>|<span data-ttu-id="d6378-273">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="d6378-273">Restriction Default</span></span>|<span data-ttu-id="d6378-274">制限の番号</span><span class="sxs-lookup"><span data-stu-id="d6378-274">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d6378-275">Catalog</span><span class="sxs-lookup"><span data-stu-id="d6378-275">Catalog</span></span>|@Catalog|<span data-ttu-id="d6378-276">db_name()</span><span class="sxs-lookup"><span data-stu-id="d6378-276">db_name()</span></span>|<span data-ttu-id="d6378-277">1</span><span class="sxs-lookup"><span data-stu-id="d6378-277">1</span></span>|  
|<span data-ttu-id="d6378-278">Owner</span><span class="sxs-lookup"><span data-stu-id="d6378-278">Owner</span></span>|@Owner|<span data-ttu-id="d6378-279">user_name()</span><span class="sxs-lookup"><span data-stu-id="d6378-279">user_name()</span></span>|<span data-ttu-id="d6378-280">2</span><span class="sxs-lookup"><span data-stu-id="d6378-280">2</span></span>|  
|<span data-ttu-id="d6378-281">テーブル</span><span class="sxs-lookup"><span data-stu-id="d6378-281">Table</span></span>|@Table|<span data-ttu-id="d6378-282">o.name</span><span class="sxs-lookup"><span data-stu-id="d6378-282">o.name</span></span>|<span data-ttu-id="d6378-283">3</span><span class="sxs-lookup"><span data-stu-id="d6378-283">3</span></span>|  
|<span data-ttu-id="d6378-284">ConstraintName</span><span class="sxs-lookup"><span data-stu-id="d6378-284">ConstraintName</span></span>|@ConstraintName|<span data-ttu-id="d6378-285">x.name</span><span class="sxs-lookup"><span data-stu-id="d6378-285">x.name</span></span>|<span data-ttu-id="d6378-286">4</span><span class="sxs-lookup"><span data-stu-id="d6378-286">4</span></span>|  
|<span data-ttu-id="d6378-287">[列]</span><span class="sxs-lookup"><span data-stu-id="d6378-287">Column</span></span>|@Column|<span data-ttu-id="d6378-288">c.name</span><span class="sxs-lookup"><span data-stu-id="d6378-288">c.name</span></span>|<span data-ttu-id="d6378-289">5</span><span class="sxs-lookup"><span data-stu-id="d6378-289">5</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="d6378-290">インデックス</span><span class="sxs-lookup"><span data-stu-id="d6378-290">Indexes</span></span>  
  
|<span data-ttu-id="d6378-291">制限の名前</span><span class="sxs-lookup"><span data-stu-id="d6378-291">Restriction Name</span></span>|<span data-ttu-id="d6378-292">[パラメーター名]</span><span class="sxs-lookup"><span data-stu-id="d6378-292">Parameter Name</span></span>|<span data-ttu-id="d6378-293">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="d6378-293">Restriction Default</span></span>|<span data-ttu-id="d6378-294">制限の番号</span><span class="sxs-lookup"><span data-stu-id="d6378-294">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d6378-295">Catalog</span><span class="sxs-lookup"><span data-stu-id="d6378-295">Catalog</span></span>|@Catalog|<span data-ttu-id="d6378-296">db_name()</span><span class="sxs-lookup"><span data-stu-id="d6378-296">db_name()</span></span>|<span data-ttu-id="d6378-297">1</span><span class="sxs-lookup"><span data-stu-id="d6378-297">1</span></span>|  
|<span data-ttu-id="d6378-298">Owner</span><span class="sxs-lookup"><span data-stu-id="d6378-298">Owner</span></span>|@Owner|<span data-ttu-id="d6378-299">user_name()</span><span class="sxs-lookup"><span data-stu-id="d6378-299">user_name()</span></span>|<span data-ttu-id="d6378-300">2</span><span class="sxs-lookup"><span data-stu-id="d6378-300">2</span></span>|  
|<span data-ttu-id="d6378-301">テーブル</span><span class="sxs-lookup"><span data-stu-id="d6378-301">Table</span></span>|@Table|<span data-ttu-id="d6378-302">o.name</span><span class="sxs-lookup"><span data-stu-id="d6378-302">o.name</span></span>|<span data-ttu-id="d6378-303">3</span><span class="sxs-lookup"><span data-stu-id="d6378-303">3</span></span>|  
  
### <a name="userdefinedtypes"></a><span data-ttu-id="d6378-304">UserDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="d6378-304">UserDefinedTypes</span></span>  
  
|<span data-ttu-id="d6378-305">制限の名前</span><span class="sxs-lookup"><span data-stu-id="d6378-305">Restriction Name</span></span>|<span data-ttu-id="d6378-306">[パラメーター名]</span><span class="sxs-lookup"><span data-stu-id="d6378-306">Parameter Name</span></span>|<span data-ttu-id="d6378-307">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="d6378-307">Restriction Default</span></span>|<span data-ttu-id="d6378-308">制限の番号</span><span class="sxs-lookup"><span data-stu-id="d6378-308">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d6378-309">assembly_name</span><span class="sxs-lookup"><span data-stu-id="d6378-309">assembly_name</span></span>|@AssemblyName|<span data-ttu-id="d6378-310">assemblies.name</span><span class="sxs-lookup"><span data-stu-id="d6378-310">assemblies.name</span></span>|<span data-ttu-id="d6378-311">1</span><span class="sxs-lookup"><span data-stu-id="d6378-311">1</span></span>|  
|<span data-ttu-id="d6378-312">udt_name</span><span class="sxs-lookup"><span data-stu-id="d6378-312">udt_name</span></span>|@UDTName|<span data-ttu-id="d6378-313">types.assembly_class</span><span class="sxs-lookup"><span data-stu-id="d6378-313">types.assembly_class</span></span>|<span data-ttu-id="d6378-314">2</span><span class="sxs-lookup"><span data-stu-id="d6378-314">2</span></span>|  
  
### <a name="foreignkeys"></a><span data-ttu-id="d6378-315">ForeignKeys</span><span class="sxs-lookup"><span data-stu-id="d6378-315">ForeignKeys</span></span>  
  
|<span data-ttu-id="d6378-316">制限の名前</span><span class="sxs-lookup"><span data-stu-id="d6378-316">Restriction Name</span></span>|<span data-ttu-id="d6378-317">[パラメーター名]</span><span class="sxs-lookup"><span data-stu-id="d6378-317">Parameter Name</span></span>|<span data-ttu-id="d6378-318">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="d6378-318">Restriction Default</span></span>|<span data-ttu-id="d6378-319">制限の番号</span><span class="sxs-lookup"><span data-stu-id="d6378-319">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d6378-320">Catalog</span><span class="sxs-lookup"><span data-stu-id="d6378-320">Catalog</span></span>|@Catalog|<span data-ttu-id="d6378-321">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d6378-321">CONSTRAINT_CATALOG</span></span>|<span data-ttu-id="d6378-322">1</span><span class="sxs-lookup"><span data-stu-id="d6378-322">1</span></span>|  
|<span data-ttu-id="d6378-323">Owner</span><span class="sxs-lookup"><span data-stu-id="d6378-323">Owner</span></span>|@Owner|<span data-ttu-id="d6378-324">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d6378-324">CONSTRAINT_SCHEMA</span></span>|<span data-ttu-id="d6378-325">2</span><span class="sxs-lookup"><span data-stu-id="d6378-325">2</span></span>|  
|<span data-ttu-id="d6378-326">テーブル</span><span class="sxs-lookup"><span data-stu-id="d6378-326">Table</span></span>|@Table|<span data-ttu-id="d6378-327">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d6378-327">TABLE_NAME</span></span>|<span data-ttu-id="d6378-328">3</span><span class="sxs-lookup"><span data-stu-id="d6378-328">3</span></span>|  
|<span data-ttu-id="d6378-329">名前</span><span class="sxs-lookup"><span data-stu-id="d6378-329">Name</span></span>|@Name|<span data-ttu-id="d6378-330">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="d6378-330">CONSTRAINT_NAME</span></span>|<span data-ttu-id="d6378-331">4</span><span class="sxs-lookup"><span data-stu-id="d6378-331">4</span></span>|  
  
## <a name="sql-server-2008-schema-restrictions"></a><span data-ttu-id="d6378-332">SQL Server 2008 スキーマの制限</span><span class="sxs-lookup"><span data-stu-id="d6378-332">SQL Server 2008 Schema Restrictions</span></span>  
 <span data-ttu-id="d6378-333">次の表に、SQL Server 2008 スキーマ コレクションの制限を示します。</span><span class="sxs-lookup"><span data-stu-id="d6378-333">The following tables list the restrictions for SQL Server 2008 schema collections.</span></span> <span data-ttu-id="d6378-334">これらの制限は、.NET Framework 3.5 SP1 および SQL Server 2008 以降で有効です。</span><span class="sxs-lookup"><span data-stu-id="d6378-334">These restrictions are valid beginning with version 3.5 SP1 of the .NET Framework and SQL Server 2008.</span></span> <span data-ttu-id="d6378-335">これらの制限は、以前のバージョンの .NET Framework および SQL Server ではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="d6378-335">They are not supported in earlier versions of the .NET Framework and SQL Server.</span></span>  
  
### <a name="columnsetcolumns"></a><span data-ttu-id="d6378-336">ColumnSetColumns</span><span class="sxs-lookup"><span data-stu-id="d6378-336">ColumnSetColumns</span></span>  
  
|<span data-ttu-id="d6378-337">制限の名前</span><span class="sxs-lookup"><span data-stu-id="d6378-337">Restriction Name</span></span>|<span data-ttu-id="d6378-338">[パラメーター名]</span><span class="sxs-lookup"><span data-stu-id="d6378-338">Parameter Name</span></span>|<span data-ttu-id="d6378-339">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="d6378-339">Restriction Default</span></span>|<span data-ttu-id="d6378-340">制限の番号</span><span class="sxs-lookup"><span data-stu-id="d6378-340">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d6378-341">Catalog</span><span class="sxs-lookup"><span data-stu-id="d6378-341">Catalog</span></span>|@Catalog|<span data-ttu-id="d6378-342">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d6378-342">TABLE_CATALOG</span></span>|<span data-ttu-id="d6378-343">1</span><span class="sxs-lookup"><span data-stu-id="d6378-343">1</span></span>|  
|<span data-ttu-id="d6378-344">Owner</span><span class="sxs-lookup"><span data-stu-id="d6378-344">Owner</span></span>|@Owner|<span data-ttu-id="d6378-345">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d6378-345">TABLE_SCHEMA</span></span>|<span data-ttu-id="d6378-346">2</span><span class="sxs-lookup"><span data-stu-id="d6378-346">2</span></span>|  
|<span data-ttu-id="d6378-347">テーブル</span><span class="sxs-lookup"><span data-stu-id="d6378-347">Table</span></span>|@Table|<span data-ttu-id="d6378-348">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d6378-348">TABLE_NAME</span></span>|<span data-ttu-id="d6378-349">3</span><span class="sxs-lookup"><span data-stu-id="d6378-349">3</span></span>|  
  
### <a name="allcolumns"></a><span data-ttu-id="d6378-350">AllColumns</span><span class="sxs-lookup"><span data-stu-id="d6378-350">AllColumns</span></span>  
  
|<span data-ttu-id="d6378-351">制限の名前</span><span class="sxs-lookup"><span data-stu-id="d6378-351">Restriction Name</span></span>|<span data-ttu-id="d6378-352">[パラメーター名]</span><span class="sxs-lookup"><span data-stu-id="d6378-352">Parameter Name</span></span>|<span data-ttu-id="d6378-353">制限の既定値</span><span class="sxs-lookup"><span data-stu-id="d6378-353">Restriction Default</span></span>|<span data-ttu-id="d6378-354">制限の番号</span><span class="sxs-lookup"><span data-stu-id="d6378-354">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d6378-355">Catalog</span><span class="sxs-lookup"><span data-stu-id="d6378-355">Catalog</span></span>|@Catalog|<span data-ttu-id="d6378-356">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d6378-356">TABLE_CATALOG</span></span>|<span data-ttu-id="d6378-357">1</span><span class="sxs-lookup"><span data-stu-id="d6378-357">1</span></span>|  
|<span data-ttu-id="d6378-358">Owner</span><span class="sxs-lookup"><span data-stu-id="d6378-358">Owner</span></span>|@Owner|<span data-ttu-id="d6378-359">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d6378-359">TABLE_SCHEMA</span></span>|<span data-ttu-id="d6378-360">2</span><span class="sxs-lookup"><span data-stu-id="d6378-360">2</span></span>|  
|<span data-ttu-id="d6378-361">テーブル</span><span class="sxs-lookup"><span data-stu-id="d6378-361">Table</span></span>|@Table|<span data-ttu-id="d6378-362">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d6378-362">TABLE_NAME</span></span>|<span data-ttu-id="d6378-363">3</span><span class="sxs-lookup"><span data-stu-id="d6378-363">3</span></span>|  
|<span data-ttu-id="d6378-364">[列]</span><span class="sxs-lookup"><span data-stu-id="d6378-364">Column</span></span>|@Column|<span data-ttu-id="d6378-365">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d6378-365">COLUMN_NAME</span></span>|<span data-ttu-id="d6378-366">4</span><span class="sxs-lookup"><span data-stu-id="d6378-366">4</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d6378-367">関連項目</span><span class="sxs-lookup"><span data-stu-id="d6378-367">See also</span></span>

- [<span data-ttu-id="d6378-368">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="d6378-368">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
