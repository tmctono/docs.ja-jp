---
title: ADO.NET の制限事項
ms.date: 12/13/2019
description: 発生する可能性がある ADO.NET の制限事項について説明します。
ms.openlocfilehash: b58fd3a9ea324e9c17ad21479e53e45f5982db9d
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450340"
---
# <a name="adonet-limitations"></a><span data-ttu-id="35ecf-103">ADO.NET の制限事項</span><span class="sxs-lookup"><span data-stu-id="35ecf-103">ADO.NET limitations</span></span>

<span data-ttu-id="35ecf-104">ADO.NET には、多くの抽象化が実装されていますが、いくつかの制限があります。</span><span class="sxs-lookup"><span data-stu-id="35ecf-104">Microsoft.Data.Sqlite provides implementations of many of the ADO.NET abstractions, but there are some limitations.</span></span>

## <a name="database-schema-information"></a><span data-ttu-id="35ecf-105">データベーススキーマ情報</span><span class="sxs-lookup"><span data-stu-id="35ecf-105">Database schema information</span></span>

<span data-ttu-id="35ecf-106">クエリ結果に関するメタデータは、<xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> メソッドを使用して取得できます。</span><span class="sxs-lookup"><span data-stu-id="35ecf-106">Metadata about query results is available using the <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> method.</span></span>

<span data-ttu-id="35ecf-107">`DbConnection.GetSchema()` は実装されていません。</span><span class="sxs-lookup"><span data-stu-id="35ecf-107">`DbConnection.GetSchema()` isn't implemented.</span></span> <span data-ttu-id="35ecf-108">この API は明確に定義されていないため、 [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema)テーブルや[table_info](https://www.sqlite.org/pragma.html#pragma_table_info)プラグマなどの標準の SQLite api を使用して、データベースのメタデータを直接取得することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="35ecf-108">This API isn't well-defined, so we recommend retrieving database metadata directly using standard SQLite APIs like the [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) table and the [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) PRAGMA.</span></span>

<span data-ttu-id="35ecf-109">詳細については、「[メタデータ](metadata.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35ecf-109">For more information, see [Metadata](metadata.md).</span></span>

## <a name="systemtransactions"></a><span data-ttu-id="35ecf-110">System.Transactions</span><span class="sxs-lookup"><span data-stu-id="35ecf-110">System.Transactions</span></span>

<span data-ttu-id="35ecf-111">Microsoft Data Sqlite では、まだ system.string はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="35ecf-111">Microsoft.Data.Sqlite doesn't yet support System.Transactions.</span></span> <span data-ttu-id="35ecf-112">代わりに ADO.NET トランザクションを使用してください。</span><span class="sxs-lookup"><span data-stu-id="35ecf-112">Use ADO.NET transactions instead.</span></span> <span data-ttu-id="35ecf-113">詳細については、「[トランザクション](transactions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35ecf-113">For more information, see [Transactions](transactions.md).</span></span>

<span data-ttu-id="35ecf-114">問題[#13825](https://github.com/aspnet/EntityFrameworkCore/issues/13825)でのシステムトランザクションのサポート不足に関するフィードバックを提供します。</span><span class="sxs-lookup"><span data-stu-id="35ecf-114">Provide feedback about the lack of support for System.Transactions on issue [#13825](https://github.com/aspnet/EntityFrameworkCore/issues/13825).</span></span>

## <a name="data-adapters"></a><span data-ttu-id="35ecf-115">データアダプター</span><span class="sxs-lookup"><span data-stu-id="35ecf-115">Data adapters</span></span>

<span data-ttu-id="35ecf-116">`DbDataAdapter` は、まだ Microsoft. Sqlite によって実装されていません。</span><span class="sxs-lookup"><span data-stu-id="35ecf-116">`DbDataAdapter` isn't yet implemented by Microsoft.Data.Sqlite.</span></span> <span data-ttu-id="35ecf-117">つまり、ADO.NET `DataTable` `DataSet` のみを使用してデータを読み込み、更新することはできません。</span><span class="sxs-lookup"><span data-stu-id="35ecf-117">This means you can only use ADO.NET `DataSet` and `DataTable` to load data and not update it.</span></span>

<span data-ttu-id="35ecf-118">問題[#13838](https://github.com/aspnet/EntityFrameworkCore/issues/13838)を使用して、`DbDataAdapter`の実装に関するフィードバックを提供します。</span><span class="sxs-lookup"><span data-stu-id="35ecf-118">Use issue [#13838](https://github.com/aspnet/EntityFrameworkCore/issues/13838) to provide feedback about implementing `DbDataAdapter`.</span></span>

## <a name="output-parameters"></a><span data-ttu-id="35ecf-119">出力パラメーター</span><span class="sxs-lookup"><span data-stu-id="35ecf-119">Output parameters</span></span>

<span data-ttu-id="35ecf-120">SQLite では、出力パラメーターはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="35ecf-120">SQLite doesn't support output parameters.</span></span>

## <a name="positional-parameters"></a><span data-ttu-id="35ecf-121">位置指定パラメーター</span><span class="sxs-lookup"><span data-stu-id="35ecf-121">Positional parameters</span></span>

<span data-ttu-id="35ecf-122">Microsoft では、名前付き[パラメーター](parameters.md)のみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="35ecf-122">Microsoft.Data.Sqlite only supports named [parameters](parameters.md).</span></span> <span data-ttu-id="35ecf-123">位置指定パラメーターはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="35ecf-123">Positional parameters aren't supported.</span></span>

## <a name="stored-procedures"></a><span data-ttu-id="35ecf-124">ストアド プロシージャ</span><span class="sxs-lookup"><span data-stu-id="35ecf-124">Stored procedures</span></span>

<span data-ttu-id="35ecf-125">SQLite はストアドプロシージャをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="35ecf-125">SQLite doesn't support stored procedures.</span></span>

## <a name="isolation-levels"></a><span data-ttu-id="35ecf-126">分離レベル</span><span class="sxs-lookup"><span data-stu-id="35ecf-126">Isolation levels</span></span>

<span data-ttu-id="35ecf-127">`Chaos` および `Snapshot` の分離レベルは、SQLite トランザクションではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="35ecf-127">The `Chaos` and `Snapshot` isolation levels aren't supported in SQLite transactions.</span></span>

## <a name="see-also"></a><span data-ttu-id="35ecf-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="35ecf-128">See also</span></span>

* [<span data-ttu-id="35ecf-129">非同期の制限事項</span><span class="sxs-lookup"><span data-stu-id="35ecf-129">Async limitations</span></span>](async.md)
* [<span data-ttu-id="35ecf-130">データ型</span><span class="sxs-lookup"><span data-stu-id="35ecf-130">Data types</span></span>](types.md)
* [<span data-ttu-id="35ecf-131">トランザクション</span><span class="sxs-lookup"><span data-stu-id="35ecf-131">Transactions</span></span>](transactions.md)
