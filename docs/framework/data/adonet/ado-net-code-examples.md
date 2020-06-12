---
title: コード例
description: これらの例では、.NET Framework プログラマに対して、ADO.NET データ プロバイダーと ADO.NET Entity Framework を使用してデータベースからデータを取得する方法が示されます。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c119657a-9ce6-4940-91e4-ac1d5f0d9584
ms.openlocfilehash: 54df0e253716c970cf23446434d96b104b8e9b03
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287169"
---
# <a name="adonet-code-examples"></a><span data-ttu-id="e709b-103">ADO.NET のコード例</span><span class="sxs-lookup"><span data-stu-id="e709b-103">ADO.NET code examples</span></span>

<span data-ttu-id="e709b-104">このページのコード リストでは、次の ADO.NET テクノロジを使用してデータベースからデータを取得する方法が示されています。</span><span class="sxs-lookup"><span data-stu-id="e709b-104">The code listings on this page demonstrate how to retrieve data from a database by using the following ADO.NET technologies:</span></span>

- <span data-ttu-id="e709b-105">ADO.NET データ プロバイダー:</span><span class="sxs-lookup"><span data-stu-id="e709b-105">ADO.NET data providers:</span></span>

  - <span data-ttu-id="e709b-106">[SqlClient](#sqlclient) (`System.Data.SqlClient`)</span><span class="sxs-lookup"><span data-stu-id="e709b-106">[SqlClient](#sqlclient) (`System.Data.SqlClient`)</span></span>

  - <span data-ttu-id="e709b-107">[OleDb](#oledb) (`System.Data.OleDb`)</span><span class="sxs-lookup"><span data-stu-id="e709b-107">[OleDb](#oledb) (`System.Data.OleDb`)</span></span>

  - <span data-ttu-id="e709b-108">[Odbc](#odbc) (`System.Data.Odbc`)</span><span class="sxs-lookup"><span data-stu-id="e709b-108">[Odbc](#odbc) (`System.Data.Odbc`)</span></span>

  - <span data-ttu-id="e709b-109">[OracleClient](#oracleclient) (`System.Data.OracleClient`)</span><span class="sxs-lookup"><span data-stu-id="e709b-109">[OracleClient](#oracleclient) (`System.Data.OracleClient`)</span></span>

- <span data-ttu-id="e709b-110">ADO.NET Entity Framework:</span><span class="sxs-lookup"><span data-stu-id="e709b-110">ADO.NET Entity Framework:</span></span>

  - [<span data-ttu-id="e709b-111">LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="e709b-111">LINQ to Entities</span></span>](#linq-to-entities)

  - [<span data-ttu-id="e709b-112">型指定された ObjectQuery</span><span class="sxs-lookup"><span data-stu-id="e709b-112">Typed ObjectQuery</span></span>](#typed-objectquery)

  - <span data-ttu-id="e709b-113">[EntityClient](#entityclient) (`System.Data.EntityClient`)</span><span class="sxs-lookup"><span data-stu-id="e709b-113">[EntityClient](#entityclient) (`System.Data.EntityClient`)</span></span>

- [<span data-ttu-id="e709b-114">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="e709b-114">LINQ to SQL</span></span>](#linq-to-sql)

## <a name="adonet-data-provider-examples"></a><span data-ttu-id="e709b-115">ADO.NET データ プロバイダーの例</span><span class="sxs-lookup"><span data-stu-id="e709b-115">ADO.NET data provider examples</span></span>
<span data-ttu-id="e709b-116">以下に示した各コードは、ADO.NET データ プロバイダーを使用してデータベースからデータを取得する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e709b-116">The following code listings demonstrate how to retrieve data from a database using ADO.NET data providers.</span></span> <span data-ttu-id="e709b-117">データは `DataReader` で返されます。</span><span class="sxs-lookup"><span data-stu-id="e709b-117">The data is returned in a `DataReader`.</span></span> <span data-ttu-id="e709b-118">詳しくは、「[DataReader によるデータの取得](retrieving-data-using-a-datareader.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e709b-118">For more information, see [Retrieving Data Using a DataReader](retrieving-data-using-a-datareader.md).</span></span>

### <a name="sqlclient"></a><span data-ttu-id="e709b-119">SqlClient</span><span class="sxs-lookup"><span data-stu-id="e709b-119">SqlClient</span></span>
<span data-ttu-id="e709b-120">このコード例では、Microsoft SQL Server の `Northwind` サンプル データベースに接続できることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="e709b-120">The code in this example assumes that you can connect to the `Northwind` sample database on Microsoft SQL Server.</span></span> <span data-ttu-id="e709b-121">このコードは <xref:System.Data.SqlClient.SqlCommand> を作成してProducts テーブルから行を選択し、<xref:System.Data.SqlClient.SqlParameter> を追加して、結果を指定したパラメーター値 (この場合は 5) よりも大きな UnitPrice を持つ行に制限します。</span><span class="sxs-lookup"><span data-stu-id="e709b-121">The code creates a <xref:System.Data.SqlClient.SqlCommand> to select rows from the Products table, adding a <xref:System.Data.SqlClient.SqlParameter> to restrict the results to rows with a UnitPrice greater than the specified parameter value, in this case 5.</span></span> <span data-ttu-id="e709b-122"><xref:System.Data.SqlClient.SqlConnection> は `using` ブロック内で開かれ、これによってコードが終了したときにリソースが閉じられ破棄されます。</span><span class="sxs-lookup"><span data-stu-id="e709b-122">The <xref:System.Data.SqlClient.SqlConnection> is opened inside a `using` block, which ensures that resources are closed and disposed when the code exits.</span></span> <span data-ttu-id="e709b-123">コードは <xref:System.Data.SqlClient.SqlDataReader> を使用してコマンドを実行し、コンソール ウィンドウに結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="e709b-123">The code executes the command by using a <xref:System.Data.SqlClient.SqlDataReader>, and displays the results in the console window.</span></span>

 [!code-csharp[DataWorks SampleApp.SqlClient#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.SqlClient/CS/source.cs#1)]
 [!code-vb[DataWorks SampleApp.SqlClient#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.SqlClient/VB/source.vb#1)]

### <a name="oledb"></a><span data-ttu-id="e709b-124">OleDb</span><span class="sxs-lookup"><span data-stu-id="e709b-124">OleDb</span></span>
<span data-ttu-id="e709b-125">このコード例は、Microsoft Access の Northwind サンプル データベースに接続できることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="e709b-125">The code in this example assumes that you can connect to the Microsoft Access Northwind sample database.</span></span> <span data-ttu-id="e709b-126">このコードは <xref:System.Data.OleDb.OleDbCommand> を作成してProducts テーブルから行を選択し、<xref:System.Data.OleDb.OleDbParameter> を追加して、結果を指定したパラメーター値 (この場合は 5) よりも大きな UnitPrice を持つ行に制限します。</span><span class="sxs-lookup"><span data-stu-id="e709b-126">The code creates a <xref:System.Data.OleDb.OleDbCommand> to select rows from the Products table, adding a <xref:System.Data.OleDb.OleDbParameter> to restrict the results to rows with a UnitPrice greater than the specified parameter value, in this case 5.</span></span> <span data-ttu-id="e709b-127"><xref:System.Data.OleDb.OleDbConnection> は `using` ブロック内に開かれ、これによってコードが終了したときにリソースが閉じられ破棄されます。</span><span class="sxs-lookup"><span data-stu-id="e709b-127">The <xref:System.Data.OleDb.OleDbConnection> is opened inside of a `using` block, which ensures that resources are closed and disposed when the code exits.</span></span> <span data-ttu-id="e709b-128">コードは <xref:System.Data.OleDb.OleDbDataReader> を使用してコマンドを実行し、コンソール ウィンドウに結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="e709b-128">The code executes the command by using a <xref:System.Data.OleDb.OleDbDataReader>, and displays the results in the console window.</span></span>

 [!code-csharp[DataWorks SampleApp.OleDb#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.OleDb/CS/source.cs#1)]
 [!code-vb[DataWorks SampleApp.OleDb#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.OleDb/VB/source.vb#1)]

### <a name="odbc"></a><span data-ttu-id="e709b-129">Odbc</span><span class="sxs-lookup"><span data-stu-id="e709b-129">Odbc</span></span>
<span data-ttu-id="e709b-130">このコード例は、Microsoft Access の Northwind サンプル データベースに接続できることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="e709b-130">The code in this example assumes that you can connect to the Microsoft Access Northwind sample database.</span></span> <span data-ttu-id="e709b-131">このコードは <xref:System.Data.Odbc.OdbcCommand> を作成してProducts テーブルから行を選択し、<xref:System.Data.Odbc.OdbcParameter> を追加して、結果を指定したパラメーター値 (この場合は 5) よりも大きな UnitPrice を持つ行に制限します。</span><span class="sxs-lookup"><span data-stu-id="e709b-131">The code creates a <xref:System.Data.Odbc.OdbcCommand> to select rows from the Products table, adding a <xref:System.Data.Odbc.OdbcParameter> to restrict the results to rows with a UnitPrice greater than the specified parameter value, in this case 5.</span></span> <span data-ttu-id="e709b-132"><xref:System.Data.Odbc.OdbcConnection> は `using` ブロック内で開かれ、これによってコードが終了したときにリソースが閉じられ破棄されます。</span><span class="sxs-lookup"><span data-stu-id="e709b-132">The <xref:System.Data.Odbc.OdbcConnection> is opened inside a `using` block, which ensures that resources are closed and disposed when the code exits.</span></span> <span data-ttu-id="e709b-133">コードは <xref:System.Data.Odbc.OdbcDataReader> を使用してコマンドを実行し、コンソール ウィンドウに結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="e709b-133">The code executes the command by using a <xref:System.Data.Odbc.OdbcDataReader>, and displays the results in the console window.</span></span>

[!code-csharp[DataWorks SampleApp.Odbc#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.Odbc/CS/source.cs#1)]
[!code-vb[DataWorks SampleApp.Odbc#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.Odbc/VB/source.vb#1)]

### <a name="oracleclient"></a><span data-ttu-id="e709b-134">OracleClient</span><span class="sxs-lookup"><span data-stu-id="e709b-134">OracleClient</span></span>
<span data-ttu-id="e709b-135">このコード例では、Oracle サーバー上の DEMO.CUSTOMER との接続を前提としています。</span><span class="sxs-lookup"><span data-stu-id="e709b-135">The code in this example assumes a connection to DEMO.CUSTOMER on an Oracle server.</span></span> <span data-ttu-id="e709b-136">また、System.Data.OracleClient.dll への参照を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e709b-136">You must also add a reference to the System.Data.OracleClient.dll.</span></span> <span data-ttu-id="e709b-137">このコードは、データを <xref:System.Data.OracleClient.OracleDataReader> で返します。</span><span class="sxs-lookup"><span data-stu-id="e709b-137">The code returns the data in an <xref:System.Data.OracleClient.OracleDataReader>.</span></span>

 [!code-csharp[DataWorks SampleApp.Oracle#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.Oracle/CS/source.cs#1)]
 [!code-vb[DataWorks SampleApp.Oracle#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.Oracle/VB/source.vb#1)]

## <a name="entity-framework-examples"></a><span data-ttu-id="e709b-138">Entity Framework の例</span><span class="sxs-lookup"><span data-stu-id="e709b-138">Entity Framework examples</span></span>
<span data-ttu-id="e709b-139">以下に示した各コードは、エンティティ データ モデル (EDM) のエンティティを照会して、データ ソースからデータを取得する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e709b-139">The following code listings demonstrate how to retrieve data from a data source by querying entities in an Entity Data Model (EDM).</span></span> <span data-ttu-id="e709b-140">これらの例では、Northwind サンプル データベースに基づくモデルが使用されています。</span><span class="sxs-lookup"><span data-stu-id="e709b-140">These examples use a model based on the Northwind sample database.</span></span> <span data-ttu-id="e709b-141">Entity Framework について詳しくは、「[Entity Framework の概要](./ef/overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e709b-141">For more information about Entity Framework, see [Entity Framework Overview](./ef/overview.md).</span></span>

### <a name="linq-to-entities"></a><span data-ttu-id="e709b-142">LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="e709b-142">LINQ to Entities</span></span>
<span data-ttu-id="e709b-143">この例のコードは LINQ クエリを使用してデータをカテゴリ オブジェクトとして返します。これは、CategoryID および CategoryName プロパティのみを含んでいる匿名型として射影されます。</span><span class="sxs-lookup"><span data-stu-id="e709b-143">The code in this example uses a LINQ query to return data as Categories objects, which are projected as an anonymous type that contains only the CategoryID and CategoryName properties.</span></span> <span data-ttu-id="e709b-144">詳しくは、「[LINQ to Entities の概要](./ef/language-reference/linq-to-entities.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e709b-144">For more information, see [LINQ to Entities Overview](./ef/language-reference/linq-to-entities.md).</span></span>

```csharp
using System;
using System.Linq;
using System.Data.Objects;
using NorthwindModel;

class LinqSample
{
    public static void ExecuteQuery()
    {
        using (NorthwindEntities context = new NorthwindEntities())
        {
            try
            {
                var query = from category in context.Categories
                            select new
                            {
                                categoryID = category.CategoryID,
                                categoryName = category.CategoryName
                            };

                foreach (var categoryInfo in query)
                {
                    Console.WriteLine("\t{0}\t{1}",
                        categoryInfo.categoryID, categoryInfo.categoryName);
                }
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex.Message);
            }
        }
    }
}
```

```vb
Option Explicit On
Option Strict On

Imports System.Linq
Imports System.Data.Objects
Imports NorthwindModel

Class LinqSample
    Public Shared Sub ExecuteQuery()
        Using context As NorthwindEntities = New NorthwindEntities()
            Try
                Dim query = From category In context.Categories _
                            Select New With _
                            { _
                                .categoryID = category.CategoryID, _
                                .categoryName = category.CategoryName _
                            }

                For Each categoryInfo In query
                    Console.WriteLine(vbTab & "{0}" & vbTab & "{1}", _
                        categoryInfo.categoryID, categoryInfo.categoryName)
                Next
            Catch ex As Exception
                Console.WriteLine(ex.Message)
            End Try
        End Using
    End Sub
End Class
```

### <a name="typed-objectquery"></a><span data-ttu-id="e709b-145">型指定された ObjectQuery</span><span class="sxs-lookup"><span data-stu-id="e709b-145">Typed ObjectQuery</span></span>
<span data-ttu-id="e709b-146">この例のコードは <xref:System.Data.Objects.ObjectQuery%601> を使用し、カテゴリ オブジェクトとしてデータを返します。</span><span class="sxs-lookup"><span data-stu-id="e709b-146">The code in this example uses an <xref:System.Data.Objects.ObjectQuery%601> to return data as Categories objects.</span></span> <span data-ttu-id="e709b-147">詳しくは、「[オブジェクト クエリ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896241(v=vs.100))」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e709b-147">For more information, see [Object Queries](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896241(v=vs.100)).</span></span>

```csharp
using System;
using System.Data.Objects;
using NorthwindModel;

class ObjectQuerySample
{
    public static void ExecuteQuery()
    {
        using (NorthwindEntities context = new NorthwindEntities())
        {
            ObjectQuery<Categories> categoryQuery = context.Categories;

            foreach (Categories category in
                categoryQuery.Execute(MergeOption.AppendOnly))
            {
                Console.WriteLine("\t{0}\t{1}",
                    category.CategoryID, category.CategoryName);
            }
        }
    }
}
```

```vb
Option Explicit On
Option Strict On

Imports System.Data.Objects
Imports NorthwindModel

Class ObjectQuerySample
    Public Shared Sub ExecuteQuery()
        Using context As NorthwindEntities = New NorthwindEntities()
            Dim categoryQuery As ObjectQuery(Of Categories) = context.Categories

            For Each category As Categories In _
                categoryQuery.Execute(MergeOption.AppendOnly)
                Console.WriteLine(vbTab & "{0}" & vbTab & "{1}", _
                    category.CategoryID, category.CategoryName)
            Next
        End Using
    End Sub
End Class
```

### <a name="entityclient"></a><span data-ttu-id="e709b-148">EntityClient</span><span class="sxs-lookup"><span data-stu-id="e709b-148">EntityClient</span></span>
<span data-ttu-id="e709b-149">この例のコードは <xref:System.Data.EntityClient.EntityCommand> を使用し、Entity SQL クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="e709b-149">The code in this example uses an <xref:System.Data.EntityClient.EntityCommand> to execute an Entity SQL query.</span></span> <span data-ttu-id="e709b-150">このクエリは、カテゴリ エンティティ型のインスタンスを示すレコードのリストを返します。</span><span class="sxs-lookup"><span data-stu-id="e709b-150">This query returns a list of records that represent instances of the Categories entity type.</span></span> <span data-ttu-id="e709b-151"><xref:System.Data.EntityClient.EntityDataReader> を使用して、結果セットのデータ レコードにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="e709b-151">An <xref:System.Data.EntityClient.EntityDataReader> is used to access data records in the result set.</span></span> <span data-ttu-id="e709b-152">詳細については、「 [Entity Framework 用の EntityClient プロバイダー](./ef/entityclient-provider-for-the-entity-framework.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e709b-152">For more information, see [EntityClient Provider for the Entity Framework](./ef/entityclient-provider-for-the-entity-framework.md).</span></span>

```csharp
using System;
using System.Data;
using System.Data.Common;
using System.Data.EntityClient;
using NorthwindModel;

class EntityClientSample
{
    public static void ExecuteQuery()
    {
        string queryString =
            @"SELECT c.CategoryID, c.CategoryName
                FROM NorthwindEntities.Categories AS c";

        using (EntityConnection conn =
            new EntityConnection("name=NorthwindEntities"))
        {
            try
            {
                conn.Open();
                using (EntityCommand query = new EntityCommand(queryString, conn))
                {
                    using (DbDataReader rdr =
                        query.ExecuteReader(CommandBehavior.SequentialAccess))
                    {
                        while (rdr.Read())
                        {
                            Console.WriteLine("\t{0}\t{1}", rdr[0], rdr[1]);
                        }
                    }
                }
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex.Message);
            }
        }
    }
}
```

```vb
Option Explicit On
Option Strict On

Imports System.Data
Imports System.Data.Common
Imports System.Data.EntityClient
Imports NorthwindModel

Class EntityClientSample
    Public Shared Sub ExecuteQuery()
        Dim queryString As String = _
            "SELECT c.CategoryID, c.CategoryName " & _
                "FROM NorthwindEntities.Categories AS c"

        Using conn As EntityConnection = _
            New EntityConnection("name=NorthwindEntities")

            Try
                conn.Open()
                Using query As EntityCommand = _
                New EntityCommand(queryString, conn)
                    Using rdr As DbDataReader = _
                        query.ExecuteReader(CommandBehavior.SequentialAccess)
                        While rdr.Read()
                            Console.WriteLine(vbTab & "{0}" & vbTab & "{1}", _
                                              rdr(0), rdr(1))
                        End While
                    End Using
                End Using
            Catch ex As Exception
                Console.WriteLine(ex.Message)
            End Try
        End Using
    End Sub
End Class
```

## <a name="linq-to-sql"></a><span data-ttu-id="e709b-153">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="e709b-153">LINQ to SQL</span></span>
<span data-ttu-id="e709b-154">この例のコードは LINQ クエリを使用してデータをカテゴリ オブジェクトとして返します。これは、CategoryID および CategoryName プロパティのみを含んでいる匿名型として射影されます。</span><span class="sxs-lookup"><span data-stu-id="e709b-154">The code in this example uses a LINQ query to return data as Categories objects, which are projected as an anonymous type that contains only the CategoryID and CategoryName properties.</span></span> <span data-ttu-id="e709b-155">この例は Northwind データ コンテキストを基にしています。</span><span class="sxs-lookup"><span data-stu-id="e709b-155">This example is based on the Northwind data context.</span></span> <span data-ttu-id="e709b-156">詳細については、[概要](./sql/linq/getting-started.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e709b-156">For more information, see [Getting Started](./sql/linq/getting-started.md).</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using Northwind;

    class LinqSqlSample
    {
        public static void ExecuteQuery()
        {
            using (NorthwindDataContext db = new NorthwindDataContext())
            {
                try
                {
                    var query = from category in db.Categories
                                select new
                                {
                                    categoryID = category.CategoryID,
                                    categoryName = category.CategoryName
                                };

                    foreach (var categoryInfo in query)
                    {
                        Console.WriteLine("vbTab {0} vbTab {1}",
                            categoryInfo.categoryID, categoryInfo.categoryName);
                    }
                }
                catch (Exception ex)
                {
                    Console.WriteLine(ex.Message);
                }
            }
        }
    }
```

```vb
Option Explicit On
Option Strict On

Imports System.Collections.Generic
Imports System.Linq
Imports System.Text
Imports Northwind

Class LinqSqlSample
    Public Shared Sub ExecuteQuery()
        Using db As NorthwindDataContext = New NorthwindDataContext()
            Try
                Dim query = From category In db.Categories _
                                Select New With _
                                { _
                                    .categoryID = category.CategoryID, _
                                    .categoryName = category.CategoryName _
                                }

                For Each categoryInfo In query
                    Console.WriteLine(vbTab & "{0}" & vbTab & "{1}", _
                            categoryInfo.categoryID, categoryInfo.categoryName)
                Next
            Catch ex As Exception
                Console.WriteLine(ex.Message)
            End Try
            End Using
    End Sub
End Class
```

## <a name="see-also"></a><span data-ttu-id="e709b-157">関連項目</span><span class="sxs-lookup"><span data-stu-id="e709b-157">See also</span></span>

- [<span data-ttu-id="e709b-158">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="e709b-158">ADO.NET Overview</span></span>](ado-net-overview.md)
- [<span data-ttu-id="e709b-159">ADO.NET でのデータの取得および変更</span><span class="sxs-lookup"><span data-stu-id="e709b-159">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- <span data-ttu-id="e709b-160">[データ アプリケーションの作成](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/h0y4a0f6(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="e709b-160">[Creating Data Applications](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/h0y4a0f6(v=vs.120))</span></span>
- <span data-ttu-id="e709b-161">[Entity Data Model のクエリ (Entity Framework タスク)](https://docs.microsoft.com/previous-versions/bb738455(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="e709b-161">[Querying an Entity Data Model (Entity Framework Tasks)](https://docs.microsoft.com/previous-versions/bb738455(v=vs.90))</span></span>
- <span data-ttu-id="e709b-162">[方法: 匿名型のコレクションを返すクエリを実行する](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738512(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="e709b-162">[How to: Execute a Query that Returns Anonymous Type Objects](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738512(v=vs.100))</span></span>
