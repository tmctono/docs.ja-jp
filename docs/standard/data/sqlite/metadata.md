---
title: メタデータ
ms.date: 12/13/2019
description: データベースに関するメタデータを取得する方法について説明します。
ms.openlocfilehash: b2f2704a748627d9943943fa2fa7b1b7e9f3007f
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450430"
---
# <a name="metadata"></a><span data-ttu-id="062ba-103">メタデータ</span><span class="sxs-lookup"><span data-stu-id="062ba-103">Metadata</span></span>

<span data-ttu-id="062ba-104">ADO.NET のメタデータを取得するための Api は2つあります。</span><span class="sxs-lookup"><span data-stu-id="062ba-104">There are two APIs for retrieving metadata in ADO.NET.</span></span> <span data-ttu-id="062ba-105">1つは、クエリ結果に関するメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="062ba-105">One retrieves metadata about query results.</span></span> <span data-ttu-id="062ba-106">もう1つは、データベーススキーマに関するメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="062ba-106">The other retrieves metadata about the database schema.</span></span>

## <a name="query-result-metadata"></a><span data-ttu-id="062ba-107">クエリ結果のメタデータ</span><span class="sxs-lookup"><span data-stu-id="062ba-107">Query result metadata</span></span>

<span data-ttu-id="062ba-108">`SqliteDataReader`の <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> メソッドを使用して、クエリの結果に関するメタデータを取得できます。</span><span class="sxs-lookup"><span data-stu-id="062ba-108">You can retrieve metadata about the results of a query using the <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> method on `SqliteDataReader`.</span></span> <span data-ttu-id="062ba-109">返される <xref:System.Data.DataTable> には、次の列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="062ba-109">The returned <xref:System.Data.DataTable> contains the following columns:</span></span>

| <span data-ttu-id="062ba-110">[列 ]</span><span class="sxs-lookup"><span data-stu-id="062ba-110">Column</span></span>             | <span data-ttu-id="062ba-111">の型</span><span class="sxs-lookup"><span data-stu-id="062ba-111">Type</span></span>    | <span data-ttu-id="062ba-112">説明</span><span class="sxs-lookup"><span data-stu-id="062ba-112">Description</span></span>                                                               |
| ------------------ | ------- | ------------------------------------------------------------------------- |
| `AllowDBNull`      | <span data-ttu-id="062ba-113">Boolean</span><span class="sxs-lookup"><span data-stu-id="062ba-113">Boolean</span></span> | <span data-ttu-id="062ba-114">Origin 列が NULL である場合は True を指定します。</span><span class="sxs-lookup"><span data-stu-id="062ba-114">True if the origin column may be NULL.</span></span>                                    |
| `BaseCatalogName`  | <span data-ttu-id="062ba-115">文字列型</span><span class="sxs-lookup"><span data-stu-id="062ba-115">String</span></span>  | <span data-ttu-id="062ba-116">元の列のデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="062ba-116">The name of the origin column's database.</span></span> <span data-ttu-id="062ba-117">式の場合は常に NULL です。</span><span class="sxs-lookup"><span data-stu-id="062ba-117">Always NULL for expressions.</span></span>    |
| `BaseColumnName`   | <span data-ttu-id="062ba-118">文字列型</span><span class="sxs-lookup"><span data-stu-id="062ba-118">String</span></span>  | <span data-ttu-id="062ba-119">元の列のエイリアス解除された名前。</span><span class="sxs-lookup"><span data-stu-id="062ba-119">The unaliased name of the origin column.</span></span> <span data-ttu-id="062ba-120">式の場合は常に NULL です。</span><span class="sxs-lookup"><span data-stu-id="062ba-120">Always NULL for expressions.</span></span>    |
| `BaseSchemaName`   | <span data-ttu-id="062ba-121">文字列型</span><span class="sxs-lookup"><span data-stu-id="062ba-121">String</span></span>  | <span data-ttu-id="062ba-122">常に NULL です。</span><span class="sxs-lookup"><span data-stu-id="062ba-122">Always NULL.</span></span> <span data-ttu-id="062ba-123">SQLite はスキーマをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="062ba-123">SQLite doesn't support schemas.</span></span>                              |
| `BaseServerName`   | <span data-ttu-id="062ba-124">文字列型</span><span class="sxs-lookup"><span data-stu-id="062ba-124">String</span></span>  | <span data-ttu-id="062ba-125">接続文字列で指定されたデータベースファイルへのパスです。</span><span class="sxs-lookup"><span data-stu-id="062ba-125">The path to the database file specified in the connection string.</span></span>         |
| `BaseTableName`    | <span data-ttu-id="062ba-126">文字列型</span><span class="sxs-lookup"><span data-stu-id="062ba-126">String</span></span>  | <span data-ttu-id="062ba-127">元の列のテーブルの名前。</span><span class="sxs-lookup"><span data-stu-id="062ba-127">The name of the origin column's table.</span></span> <span data-ttu-id="062ba-128">式の場合は常に NULL です。</span><span class="sxs-lookup"><span data-stu-id="062ba-128">Always NULL for expressions.</span></span>       |
| `ColumnName`       | <span data-ttu-id="062ba-129">文字列型</span><span class="sxs-lookup"><span data-stu-id="062ba-129">String</span></span>  | <span data-ttu-id="062ba-130">結果セット内の列の名前または別名。</span><span class="sxs-lookup"><span data-stu-id="062ba-130">The name or alias of the column in the result set.</span></span>                        |
| `ColumnOrdinal`    | <span data-ttu-id="062ba-131">Int32</span><span class="sxs-lookup"><span data-stu-id="062ba-131">Int32</span></span>   | <span data-ttu-id="062ba-132">結果セット内の列の序数。</span><span class="sxs-lookup"><span data-stu-id="062ba-132">The ordinal of the column in the result set.</span></span>                              |
| `ColumnSize`       | <span data-ttu-id="062ba-133">Int32</span><span class="sxs-lookup"><span data-stu-id="062ba-133">Int32</span></span>   | <span data-ttu-id="062ba-134">常に-1 です。</span><span class="sxs-lookup"><span data-stu-id="062ba-134">Always -1.</span></span> <span data-ttu-id="062ba-135">これは、`Microsoft.Data.Sqlite`の将来のバージョンで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="062ba-135">This may change in future versions of `Microsoft.Data.Sqlite`.</span></span>   |
| `DataType`         | <span data-ttu-id="062ba-136">の型</span><span class="sxs-lookup"><span data-stu-id="062ba-136">Type</span></span>    | <span data-ttu-id="062ba-137">列の既定の .NET データ型。</span><span class="sxs-lookup"><span data-stu-id="062ba-137">The default .NET data type of the column.</span></span>                                 |
| `DataTypeName`     | <span data-ttu-id="062ba-138">文字列型</span><span class="sxs-lookup"><span data-stu-id="062ba-138">String</span></span>  | <span data-ttu-id="062ba-139">列の SQLite データ型。</span><span class="sxs-lookup"><span data-stu-id="062ba-139">The SQLite data type of the column.</span></span>                                       |
| `IsAliased`        | <span data-ttu-id="062ba-140">Boolean</span><span class="sxs-lookup"><span data-stu-id="062ba-140">Boolean</span></span> | <span data-ttu-id="062ba-141">列名が結果セットに含まれる場合は True を指定します。</span><span class="sxs-lookup"><span data-stu-id="062ba-141">True if the column name is aliased in the result set.</span></span>                     |
| `IsAutoIncrement`  | <span data-ttu-id="062ba-142">Boolean</span><span class="sxs-lookup"><span data-stu-id="062ba-142">Boolean</span></span> | <span data-ttu-id="062ba-143">Origin 列が AUTOINCREMENT キーワードを使用して作成された場合は True。</span><span class="sxs-lookup"><span data-stu-id="062ba-143">True if the origin column was created with the AUTOINCREMENT keyword.</span></span>     |
| `IsExpression`     | <span data-ttu-id="062ba-144">Boolean</span><span class="sxs-lookup"><span data-stu-id="062ba-144">Boolean</span></span> | <span data-ttu-id="062ba-145">列がクエリ内の式から生成される場合は True を指定します。</span><span class="sxs-lookup"><span data-stu-id="062ba-145">True if the column originates from an expression in the query.</span></span>            |
| `IsKey`            | <span data-ttu-id="062ba-146">Boolean</span><span class="sxs-lookup"><span data-stu-id="062ba-146">Boolean</span></span> | <span data-ttu-id="062ba-147">Origin 列が主キーの一部である場合は True。</span><span class="sxs-lookup"><span data-stu-id="062ba-147">True if the origin column is part of the PRIMARY KEY.</span></span>                     |
| `IsUnique`         | <span data-ttu-id="062ba-148">Boolean</span><span class="sxs-lookup"><span data-stu-id="062ba-148">Boolean</span></span> | <span data-ttu-id="062ba-149">Origin 列が一意である場合は True を示します。</span><span class="sxs-lookup"><span data-stu-id="062ba-149">True if the origin column is UNIQUE.</span></span>                                      |
| `NumericPrecision` | <span data-ttu-id="062ba-150">Int16</span><span class="sxs-lookup"><span data-stu-id="062ba-150">Int16</span></span>   | <span data-ttu-id="062ba-151">常に NULL です。</span><span class="sxs-lookup"><span data-stu-id="062ba-151">Always NULL.</span></span> <span data-ttu-id="062ba-152">これは、`Microsoft.Data.Sqlite`の将来のバージョンで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="062ba-152">This may change in future versions of `Microsoft.Data.Sqlite`.</span></span> |
| `NumericScale`     | <span data-ttu-id="062ba-153">Int16</span><span class="sxs-lookup"><span data-stu-id="062ba-153">Int16</span></span>   | <span data-ttu-id="062ba-154">常に NULL です。</span><span class="sxs-lookup"><span data-stu-id="062ba-154">Always NULL.</span></span> <span data-ttu-id="062ba-155">これは、`Microsoft.Data.Sqlite`の将来のバージョンで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="062ba-155">This may change in future versions of `Microsoft.Data.Sqlite`.</span></span> |

<span data-ttu-id="062ba-156">次の例は、`GetSchemaTable` を使用して、結果に関するメタデータを示すデバッグ文字列を作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="062ba-156">The following example shows how to use `GetSchemaTable` to create a debug string that shows metadata about a result:</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ResultMetadataSample/Program.cs?name=snippet_ResultMetadata)]

<span data-ttu-id="062ba-157">たとえば、次のクエリでは、次のデバッグ文字列が生成されます。</span><span class="sxs-lookup"><span data-stu-id="062ba-157">For example, this query would produce the following debug string:</span></span>

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

## <a name="schema-metadata"></a><span data-ttu-id="062ba-158">スキーマメタデータ</span><span class="sxs-lookup"><span data-stu-id="062ba-158">Schema metadata</span></span>

<span data-ttu-id="062ba-159">DbConnection には、GetSchema メソッドが実装されていません。</span><span class="sxs-lookup"><span data-stu-id="062ba-159">Microsoft.Data.Sqlite doesn't implement the GetSchema method on DbConnection.</span></span> <span data-ttu-id="062ba-160">代わりに、 [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema)テーブルと、 [table_info](https://www.sqlite.org/pragma.html#pragma_table_info)や[foreign_key_list](https://www.sqlite.org/pragma.html#pragma_foreign_key_list)などのプラグマステートメントを使用して、スキーマ情報を直接照会することができます。</span><span class="sxs-lookup"><span data-stu-id="062ba-160">Instead, you can query directly for schema information using the [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) table and PRAGMA statements like [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) and [foreign_key_list](https://www.sqlite.org/pragma.html#pragma_foreign_key_list).</span></span>

<span data-ttu-id="062ba-161">たとえば、次のクエリでは、データベース内のすべての列に関するメタデータが取得されます。</span><span class="sxs-lookup"><span data-stu-id="062ba-161">For example, this query will retrieve metadata about all the columns in the database.</span></span>

```sql
SELECT t.name AS tbl_name, c.name, c.type, c.notnull, c.dflt_value, c.pk
FROM sqlite_master AS t,
     pragma_table_info(t.name) AS c
WHERE t.type = 'table';
```

## <a name="see-also"></a><span data-ttu-id="062ba-162">関連項目</span><span class="sxs-lookup"><span data-stu-id="062ba-162">See also</span></span>

* [<span data-ttu-id="062ba-163">SQL Database スキーマの格納</span><span class="sxs-lookup"><span data-stu-id="062ba-163">Storage of the SQL Database Schema</span></span>](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema)
* [<span data-ttu-id="062ba-164">PRAGMA ステートメント</span><span class="sxs-lookup"><span data-stu-id="062ba-164">PRAGMA Statements</span></span>](https://www.sqlite.org/pragma.html)
* [<span data-ttu-id="062ba-165">データ型</span><span class="sxs-lookup"><span data-stu-id="062ba-165">Data types</span></span>](types.md)
