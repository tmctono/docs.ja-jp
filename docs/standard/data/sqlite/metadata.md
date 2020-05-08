---
title: メタデータ
ms.date: 12/13/2019
description: データベースに関するメタデータを取得する方法について説明します。
ms.openlocfilehash: b2f2704a748627d9943943fa2fa7b1b7e9f3007f
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450430"
---
# <a name="metadata"></a><span data-ttu-id="2d7f2-103">メタデータ</span><span class="sxs-lookup"><span data-stu-id="2d7f2-103">Metadata</span></span>

<span data-ttu-id="2d7f2-104">ADO.NET でメタデータを取得するための API は 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="2d7f2-104">There are two APIs for retrieving metadata in ADO.NET.</span></span> <span data-ttu-id="2d7f2-105">1 つは、クエリ結果に関するメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="2d7f2-105">One retrieves metadata about query results.</span></span> <span data-ttu-id="2d7f2-106">もう 1 つは、データベース スキーマに関するメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="2d7f2-106">The other retrieves metadata about the database schema.</span></span>

## <a name="query-result-metadata"></a><span data-ttu-id="2d7f2-107">クエリ結果のメタデータ</span><span class="sxs-lookup"><span data-stu-id="2d7f2-107">Query result metadata</span></span>

<span data-ttu-id="2d7f2-108">`SqliteDataReader` の <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> メソッドを使用して、クエリの結果に関するメタデータを取得できます。</span><span class="sxs-lookup"><span data-stu-id="2d7f2-108">You can retrieve metadata about the results of a query using the <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> method on `SqliteDataReader`.</span></span> <span data-ttu-id="2d7f2-109">返される <xref:System.Data.DataTable> には次の列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2d7f2-109">The returned <xref:System.Data.DataTable> contains the following columns:</span></span>

| <span data-ttu-id="2d7f2-110">Column</span><span class="sxs-lookup"><span data-stu-id="2d7f2-110">Column</span></span>             | <span data-ttu-id="2d7f2-111">種類</span><span class="sxs-lookup"><span data-stu-id="2d7f2-111">Type</span></span>    | <span data-ttu-id="2d7f2-112">説明</span><span class="sxs-lookup"><span data-stu-id="2d7f2-112">Description</span></span>                                                               |
| ------------------ | ------- | ------------------------------------------------------------------------- |
| `AllowDBNull`      | <span data-ttu-id="2d7f2-113">ブール型</span><span class="sxs-lookup"><span data-stu-id="2d7f2-113">Boolean</span></span> | <span data-ttu-id="2d7f2-114">元の列で NULL が許容される場合は true。</span><span class="sxs-lookup"><span data-stu-id="2d7f2-114">True if the origin column may be NULL.</span></span>                                    |
| `BaseCatalogName`  | <span data-ttu-id="2d7f2-115">String</span><span class="sxs-lookup"><span data-stu-id="2d7f2-115">String</span></span>  | <span data-ttu-id="2d7f2-116">元の列のデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="2d7f2-116">The name of the origin column's database.</span></span> <span data-ttu-id="2d7f2-117">式では常に NULL です。</span><span class="sxs-lookup"><span data-stu-id="2d7f2-117">Always NULL for expressions.</span></span>    |
| `BaseColumnName`   | <span data-ttu-id="2d7f2-118">String</span><span class="sxs-lookup"><span data-stu-id="2d7f2-118">String</span></span>  | <span data-ttu-id="2d7f2-119">元の列の (別名ではない) 名前。</span><span class="sxs-lookup"><span data-stu-id="2d7f2-119">The unaliased name of the origin column.</span></span> <span data-ttu-id="2d7f2-120">式では常に NULL です。</span><span class="sxs-lookup"><span data-stu-id="2d7f2-120">Always NULL for expressions.</span></span>    |
| `BaseSchemaName`   | <span data-ttu-id="2d7f2-121">String</span><span class="sxs-lookup"><span data-stu-id="2d7f2-121">String</span></span>  | <span data-ttu-id="2d7f2-122">常に NULL です。</span><span class="sxs-lookup"><span data-stu-id="2d7f2-122">Always NULL.</span></span> <span data-ttu-id="2d7f2-123">SQLite ではスキーマはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="2d7f2-123">SQLite doesn't support schemas.</span></span>                              |
| `BaseServerName`   | <span data-ttu-id="2d7f2-124">String</span><span class="sxs-lookup"><span data-stu-id="2d7f2-124">String</span></span>  | <span data-ttu-id="2d7f2-125">接続文字列の中で指定されたデータベース ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="2d7f2-125">The path to the database file specified in the connection string.</span></span>         |
| `BaseTableName`    | <span data-ttu-id="2d7f2-126">String</span><span class="sxs-lookup"><span data-stu-id="2d7f2-126">String</span></span>  | <span data-ttu-id="2d7f2-127">元の列のテーブルの名前。</span><span class="sxs-lookup"><span data-stu-id="2d7f2-127">The name of the origin column's table.</span></span> <span data-ttu-id="2d7f2-128">式では常に NULL です。</span><span class="sxs-lookup"><span data-stu-id="2d7f2-128">Always NULL for expressions.</span></span>       |
| `ColumnName`       | <span data-ttu-id="2d7f2-129">String</span><span class="sxs-lookup"><span data-stu-id="2d7f2-129">String</span></span>  | <span data-ttu-id="2d7f2-130">結果セット内の列の名前または別名。</span><span class="sxs-lookup"><span data-stu-id="2d7f2-130">The name or alias of the column in the result set.</span></span>                        |
| `ColumnOrdinal`    | <span data-ttu-id="2d7f2-131">Int32</span><span class="sxs-lookup"><span data-stu-id="2d7f2-131">Int32</span></span>   | <span data-ttu-id="2d7f2-132">結果セット内の列の序数。</span><span class="sxs-lookup"><span data-stu-id="2d7f2-132">The ordinal of the column in the result set.</span></span>                              |
| `ColumnSize`       | <span data-ttu-id="2d7f2-133">Int32</span><span class="sxs-lookup"><span data-stu-id="2d7f2-133">Int32</span></span>   | <span data-ttu-id="2d7f2-134">常に -1 です。</span><span class="sxs-lookup"><span data-stu-id="2d7f2-134">Always -1.</span></span> <span data-ttu-id="2d7f2-135">これは、将来のバージョンの `Microsoft.Data.Sqlite` では変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2d7f2-135">This may change in future versions of `Microsoft.Data.Sqlite`.</span></span>   |
| `DataType`         | <span data-ttu-id="2d7f2-136">種類</span><span class="sxs-lookup"><span data-stu-id="2d7f2-136">Type</span></span>    | <span data-ttu-id="2d7f2-137">列の既定の .NET データ型。</span><span class="sxs-lookup"><span data-stu-id="2d7f2-137">The default .NET data type of the column.</span></span>                                 |
| `DataTypeName`     | <span data-ttu-id="2d7f2-138">String</span><span class="sxs-lookup"><span data-stu-id="2d7f2-138">String</span></span>  | <span data-ttu-id="2d7f2-139">列の SQLite データ型。</span><span class="sxs-lookup"><span data-stu-id="2d7f2-139">The SQLite data type of the column.</span></span>                                       |
| `IsAliased`        | <span data-ttu-id="2d7f2-140">ブール型</span><span class="sxs-lookup"><span data-stu-id="2d7f2-140">Boolean</span></span> | <span data-ttu-id="2d7f2-141">結果セット内で列名に別名を使用する場合は true。</span><span class="sxs-lookup"><span data-stu-id="2d7f2-141">True if the column name is aliased in the result set.</span></span>                     |
| `IsAutoIncrement`  | <span data-ttu-id="2d7f2-142">ブール型</span><span class="sxs-lookup"><span data-stu-id="2d7f2-142">Boolean</span></span> | <span data-ttu-id="2d7f2-143">元の列が AUTOINCREMENT キーワードを使用して作成された場合は true。</span><span class="sxs-lookup"><span data-stu-id="2d7f2-143">True if the origin column was created with the AUTOINCREMENT keyword.</span></span>     |
| `IsExpression`     | <span data-ttu-id="2d7f2-144">ブール型</span><span class="sxs-lookup"><span data-stu-id="2d7f2-144">Boolean</span></span> | <span data-ttu-id="2d7f2-145">列がクエリ内の式から生成される場合は true。</span><span class="sxs-lookup"><span data-stu-id="2d7f2-145">True if the column originates from an expression in the query.</span></span>            |
| `IsKey`            | <span data-ttu-id="2d7f2-146">ブール型</span><span class="sxs-lookup"><span data-stu-id="2d7f2-146">Boolean</span></span> | <span data-ttu-id="2d7f2-147">元の列が PRIMARY KEY の一部である場合は true。</span><span class="sxs-lookup"><span data-stu-id="2d7f2-147">True if the origin column is part of the PRIMARY KEY.</span></span>                     |
| `IsUnique`         | <span data-ttu-id="2d7f2-148">ブール型</span><span class="sxs-lookup"><span data-stu-id="2d7f2-148">Boolean</span></span> | <span data-ttu-id="2d7f2-149">元の列が UNIQUE の場合は true。</span><span class="sxs-lookup"><span data-stu-id="2d7f2-149">True if the origin column is UNIQUE.</span></span>                                      |
| `NumericPrecision` | <span data-ttu-id="2d7f2-150">Int16</span><span class="sxs-lookup"><span data-stu-id="2d7f2-150">Int16</span></span>   | <span data-ttu-id="2d7f2-151">常に NULL です。</span><span class="sxs-lookup"><span data-stu-id="2d7f2-151">Always NULL.</span></span> <span data-ttu-id="2d7f2-152">これは、将来のバージョンの `Microsoft.Data.Sqlite` では変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2d7f2-152">This may change in future versions of `Microsoft.Data.Sqlite`.</span></span> |
| `NumericScale`     | <span data-ttu-id="2d7f2-153">Int16</span><span class="sxs-lookup"><span data-stu-id="2d7f2-153">Int16</span></span>   | <span data-ttu-id="2d7f2-154">常に NULL です。</span><span class="sxs-lookup"><span data-stu-id="2d7f2-154">Always NULL.</span></span> <span data-ttu-id="2d7f2-155">これは、将来のバージョンの `Microsoft.Data.Sqlite` では変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2d7f2-155">This may change in future versions of `Microsoft.Data.Sqlite`.</span></span> |

<span data-ttu-id="2d7f2-156">次の例は、`GetSchemaTable` を使用して、結果に関するメタデータを表示するデバッグ文字列を作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="2d7f2-156">The following example shows how to use `GetSchemaTable` to create a debug string that shows metadata about a result:</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ResultMetadataSample/Program.cs?name=snippet_ResultMetadata)]

<span data-ttu-id="2d7f2-157">たとえば、次のクエリでは、以下のデバッグ文字列が生成されます。</span><span class="sxs-lookup"><span data-stu-id="2d7f2-157">For example, this query would produce the following debug string:</span></span>

```sql
SELECT id AS post_id,
       title,
       body,
       random() AS random
FROM post
```

```output
post.id AS post_id INTEGER PRIMARY KEY AUTOINCREMENT
post.title TEXT NOT NULL UNIQUE
post.body TEXT
(expression) AS random BLOB
```

## <a name="schema-metadata"></a><span data-ttu-id="2d7f2-158">スキーマ メタデータ</span><span class="sxs-lookup"><span data-stu-id="2d7f2-158">Schema metadata</span></span>

<span data-ttu-id="2d7f2-159">Microsoft.Data.Sqlite では、DbConnection の GetSchema メソッドは実装していません。</span><span class="sxs-lookup"><span data-stu-id="2d7f2-159">Microsoft.Data.Sqlite doesn't implement the GetSchema method on DbConnection.</span></span> <span data-ttu-id="2d7f2-160">代わりに、[sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) テーブルと、[table_info](https://www.sqlite.org/pragma.html#pragma_table_info) や [foreign_key_list](https://www.sqlite.org/pragma.html#pragma_foreign_key_list) などの PRAGMA ステートメントを使用して、スキーマ情報のクエリを直接実行できます。</span><span class="sxs-lookup"><span data-stu-id="2d7f2-160">Instead, you can query directly for schema information using the [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) table and PRAGMA statements like [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) and [foreign_key_list](https://www.sqlite.org/pragma.html#pragma_foreign_key_list).</span></span>

<span data-ttu-id="2d7f2-161">たとえば、次のクエリでは、データベース内のすべての列に関するメタデータが取得されます。</span><span class="sxs-lookup"><span data-stu-id="2d7f2-161">For example, this query will retrieve metadata about all the columns in the database.</span></span>

```sql
SELECT t.name AS tbl_name, c.name, c.type, c.notnull, c.dflt_value, c.pk
FROM sqlite_master AS t,
     pragma_table_info(t.name) AS c
WHERE t.type = 'table';
```

## <a name="see-also"></a><span data-ttu-id="2d7f2-162">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d7f2-162">See also</span></span>

* [<span data-ttu-id="2d7f2-163">SQL Database スキーマの格納</span><span class="sxs-lookup"><span data-stu-id="2d7f2-163">Storage of the SQL Database Schema</span></span>](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema)
* [<span data-ttu-id="2d7f2-164">PRAGMA ステートメント</span><span class="sxs-lookup"><span data-stu-id="2d7f2-164">PRAGMA Statements</span></span>](https://www.sqlite.org/pragma.html)
* [<span data-ttu-id="2d7f2-165">データ型</span><span class="sxs-lookup"><span data-stu-id="2d7f2-165">Data types</span></span>](types.md)
