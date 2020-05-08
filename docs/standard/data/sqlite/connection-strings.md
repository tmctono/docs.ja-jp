---
title: 接続文字列
ms.date: 12/13/2019
description: 接続文字列でサポートされているキーワードと値です。
ms.openlocfilehash: bb54d152bac62a86c2a49192cf678a745159164e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401197"
---
# <a name="connection-strings"></a><span data-ttu-id="558af-103">接続文字列</span><span class="sxs-lookup"><span data-stu-id="558af-103">Connection strings</span></span>

<span data-ttu-id="558af-104">接続文字列は、データベースへの接続方法を指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="558af-104">A connection string is used to specify how to connect to the database.</span></span> <span data-ttu-id="558af-105">Microsoft.Data.Sqlite の接続文字列は、セミコロンで区切られたキーワードと値のリストとして、標準の [ADO.NET 構文](../../../framework/data/adonet/connection-strings.md)に従っています。</span><span class="sxs-lookup"><span data-stu-id="558af-105">Connection strings in Microsoft.Data.Sqlite follow the standard [ADO.NET syntax](../../../framework/data/adonet/connection-strings.md) as a semicolon-separated list of keywords and values.</span></span>

## <a name="keywords"></a><span data-ttu-id="558af-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="558af-106">Keywords</span></span>

<span data-ttu-id="558af-107">Microsoft.Data.Sqlite では次の接続文字列キーワードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="558af-107">The following connection string keywords can be used with Microsoft.Data.Sqlite:</span></span>

### <a name="data-source"></a><span data-ttu-id="558af-108">データ ソース</span><span class="sxs-lookup"><span data-stu-id="558af-108">Data source</span></span>

<span data-ttu-id="558af-109">データベース ファイルのパス。</span><span class="sxs-lookup"><span data-stu-id="558af-109">The path to the database file.</span></span> <span data-ttu-id="558af-110">*DataSource* (スペースなし) と *Filename* はこのキーワードの別名です。</span><span class="sxs-lookup"><span data-stu-id="558af-110">*DataSource* (without a space) and *Filename* are aliases of this keyword.</span></span>

<span data-ttu-id="558af-111">SQLite では、パスは現在の作業ディレクトリからの相対パスとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="558af-111">SQLite treats paths relative to the current working directory.</span></span> <span data-ttu-id="558af-112">絶対パスも指定できます。</span><span class="sxs-lookup"><span data-stu-id="558af-112">Absolute paths can also be specified.</span></span>

<span data-ttu-id="558af-113">**空**の場合、一時的なディスク上のデータベースが作成されます。このデータベースは接続が閉じられるときに削除されます。</span><span class="sxs-lookup"><span data-stu-id="558af-113">If **empty**, SQLite creates a temporary on-disk database that's deleted when the connection is closed.</span></span>

<span data-ttu-id="558af-114">`:memory:` の場合、インメモリ データベースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="558af-114">If `:memory:`, an in-memory database is used.</span></span> <span data-ttu-id="558af-115">詳細については、「[インメモリ データベース](in-memory-databases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="558af-115">For more information, see [In-Memory databases](in-memory-databases.md).</span></span>

<span data-ttu-id="558af-116">`|DataDirectory|` 置換文字列で始まるパスは、相対パスと同じように扱われます。</span><span class="sxs-lookup"><span data-stu-id="558af-116">Paths that start with the `|DataDirectory|` substitution string are treated the same as relative paths.</span></span> <span data-ttu-id="558af-117">設定すると、パスは DataDirectory アプリケーション ドメイン プロパティ値を基準とした相対パスになります。</span><span class="sxs-lookup"><span data-stu-id="558af-117">If set, paths are made relative to the DataDirectory application domain property value.</span></span>

<span data-ttu-id="558af-118">このキーワードでは、[URI ファイル名](https://www.sqlite.org/uri.html)もサポートされます。</span><span class="sxs-lookup"><span data-stu-id="558af-118">This keyword also supports [URI Filenames](https://www.sqlite.org/uri.html).</span></span>

### <a name="mode"></a><span data-ttu-id="558af-119">モード</span><span class="sxs-lookup"><span data-stu-id="558af-119">Mode</span></span>

<span data-ttu-id="558af-120">接続モード。</span><span class="sxs-lookup"><span data-stu-id="558af-120">The connection mode.</span></span>

| <span data-ttu-id="558af-121">[値]</span><span class="sxs-lookup"><span data-stu-id="558af-121">Value</span></span>           | <span data-ttu-id="558af-122">説明</span><span class="sxs-lookup"><span data-stu-id="558af-122">Description</span></span>                                                                                        |
| --------------- | -------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="558af-123">ReadWriteCreate</span><span class="sxs-lookup"><span data-stu-id="558af-123">ReadWriteCreate</span></span> | <span data-ttu-id="558af-124">読み取りと書き込みを行うデータベースを開きます。データベースが存在しない場合は作成します。</span><span class="sxs-lookup"><span data-stu-id="558af-124">Opens the database for reading and writing, and creates it if it doesn't exist.</span></span> <span data-ttu-id="558af-125">既定値です。</span><span class="sxs-lookup"><span data-stu-id="558af-125">This is the default.</span></span> |
| <span data-ttu-id="558af-126">ReadWrite</span><span class="sxs-lookup"><span data-stu-id="558af-126">ReadWrite</span></span>       | <span data-ttu-id="558af-127">読み取りと書き込みを行うデータベースを開きます。</span><span class="sxs-lookup"><span data-stu-id="558af-127">Opens the database for reading and writing.</span></span>                                                        |
| <span data-ttu-id="558af-128">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="558af-128">ReadOnly</span></span>        | <span data-ttu-id="558af-129">データベースを読み取り専用モードで開きます。</span><span class="sxs-lookup"><span data-stu-id="558af-129">Opens the database in read-only mode.</span></span>                                                              |
| <span data-ttu-id="558af-130">メモリ</span><span class="sxs-lookup"><span data-stu-id="558af-130">Memory</span></span>          | <span data-ttu-id="558af-131">インメモリ データベースを開きます。</span><span class="sxs-lookup"><span data-stu-id="558af-131">Opens an in-memory database.</span></span>                                                                       |

### <a name="cache"></a><span data-ttu-id="558af-132">キャッシュ</span><span class="sxs-lookup"><span data-stu-id="558af-132">Cache</span></span>

<span data-ttu-id="558af-133">接続で使用されるキャッシュ モード。</span><span class="sxs-lookup"><span data-stu-id="558af-133">The caching mode used by the connection.</span></span>

| <span data-ttu-id="558af-134">[値]</span><span class="sxs-lookup"><span data-stu-id="558af-134">Value</span></span>   | <span data-ttu-id="558af-135">説明</span><span class="sxs-lookup"><span data-stu-id="558af-135">Description</span></span>                                                                                    |
| ------- | ---------------------------------------------------------------------------------------------- |
| <span data-ttu-id="558af-136">Default</span><span class="sxs-lookup"><span data-stu-id="558af-136">Default</span></span> | <span data-ttu-id="558af-137">基になる SQLite ライブラリの既定のモードを使用します。</span><span class="sxs-lookup"><span data-stu-id="558af-137">Uses the default mode of the underlying SQLite library.</span></span> <span data-ttu-id="558af-138">既定値です。</span><span class="sxs-lookup"><span data-stu-id="558af-138">This is the default.</span></span>                   |
| <span data-ttu-id="558af-139">Private</span><span class="sxs-lookup"><span data-stu-id="558af-139">Private</span></span> | <span data-ttu-id="558af-140">各接続で、プライベート キャッシュを使用します。</span><span class="sxs-lookup"><span data-stu-id="558af-140">Each connection uses a private cache.</span></span>                                                          |
| <span data-ttu-id="558af-141">Shared</span><span class="sxs-lookup"><span data-stu-id="558af-141">Shared</span></span>  | <span data-ttu-id="558af-142">接続でキャッシュを共有します。</span><span class="sxs-lookup"><span data-stu-id="558af-142">Connections share a cache.</span></span> <span data-ttu-id="558af-143">このモードでは、トランザクションとテーブル ロックの動作が変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="558af-143">This mode can change the behavior of transaction and table locking.</span></span> |

### <a name="password"></a><span data-ttu-id="558af-144">パスワード</span><span class="sxs-lookup"><span data-stu-id="558af-144">Password</span></span>

<span data-ttu-id="558af-145">暗号化キー。</span><span class="sxs-lookup"><span data-stu-id="558af-145">The encryption key.</span></span> <span data-ttu-id="558af-146">指定した場合、接続を開いた直後に `PRAGMA key` が送信されます。</span><span class="sxs-lookup"><span data-stu-id="558af-146">When specified, `PRAGMA key` is sent immediately after opening the connection.</span></span>

> [!WARNING]
> <span data-ttu-id="558af-147">暗号化がネイティブ SQLite ライブラリでサポートされていない場合、パスワードの効果はありません。</span><span class="sxs-lookup"><span data-stu-id="558af-147">Password has no effect when encryption isn't supported by the native SQLite library.</span></span>

### <a name="foreign-keys"></a><span data-ttu-id="558af-148">外部キー</span><span class="sxs-lookup"><span data-stu-id="558af-148">Foreign Keys</span></span>

<span data-ttu-id="558af-149">外部キー制約を有効にするかどうかを示す値です。</span><span class="sxs-lookup"><span data-stu-id="558af-149">A value indicating whether to enable foreign key constraints.</span></span>

| <span data-ttu-id="558af-150">[値]</span><span class="sxs-lookup"><span data-stu-id="558af-150">Value</span></span>   | <span data-ttu-id="558af-151">説明</span><span class="sxs-lookup"><span data-stu-id="558af-151">Description</span></span>
| ------- | --- |
| <span data-ttu-id="558af-152">True</span><span class="sxs-lookup"><span data-stu-id="558af-152">True</span></span>    | <span data-ttu-id="558af-153">接続を開いた直後に `PRAGMA foreign_keys = 1` を送信します。</span><span class="sxs-lookup"><span data-stu-id="558af-153">Sends `PRAGMA foreign_keys = 1` immediately after opening the connection.</span></span>
| <span data-ttu-id="558af-154">False</span><span class="sxs-lookup"><span data-stu-id="558af-154">False</span></span>   | <span data-ttu-id="558af-155">接続を開いた直後に `PRAGMA foreign_keys = 0` を送信します。</span><span class="sxs-lookup"><span data-stu-id="558af-155">Sends `PRAGMA foreign_keys = 0` immediately after opening the connection.</span></span>
| <span data-ttu-id="558af-156">(空)</span><span class="sxs-lookup"><span data-stu-id="558af-156">(empty)</span></span> | <span data-ttu-id="558af-157">`PRAGMA foreign_keys` を送信しません。</span><span class="sxs-lookup"><span data-stu-id="558af-157">Doesn't send `PRAGMA foreign_keys`.</span></span> <span data-ttu-id="558af-158">既定値です。</span><span class="sxs-lookup"><span data-stu-id="558af-158">This is the default.</span></span> |

<span data-ttu-id="558af-159">e_sqlite3 の場合のように、ネイティブ SQLite ライブラリをコンパイルするために SQLITE_DEFAULT_FOREIGN_KEYS が使用された場合は、外部キーを有効にする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="558af-159">There's no need enable foreign keys if, like in e_sqlite3, SQLITE_DEFAULT_FOREIGN_KEYS was used to compile the native SQLite library.</span></span>

### <a name="recursive-triggers"></a><span data-ttu-id="558af-160">再帰トリガー</span><span class="sxs-lookup"><span data-stu-id="558af-160">Recursive triggers</span></span>

<span data-ttu-id="558af-161">再帰トリガーを有効にするかどうかを示す値です。</span><span class="sxs-lookup"><span data-stu-id="558af-161">A value that indicates whether to enable recursive triggers.</span></span>

| <span data-ttu-id="558af-162">[値]</span><span class="sxs-lookup"><span data-stu-id="558af-162">Value</span></span> | <span data-ttu-id="558af-163">説明</span><span class="sxs-lookup"><span data-stu-id="558af-163">Description</span></span>                                                                 |
| ----- | --------------------------------------------------------------------------- |
| <span data-ttu-id="558af-164">True</span><span class="sxs-lookup"><span data-stu-id="558af-164">True</span></span>  | <span data-ttu-id="558af-165">接続を開いた直後に `PRAGMA recursive_triggers` を送信します。</span><span class="sxs-lookup"><span data-stu-id="558af-165">Sends `PRAGMA recursive_triggers` immediately after opening the connection.</span></span> |
| <span data-ttu-id="558af-166">False</span><span class="sxs-lookup"><span data-stu-id="558af-166">False</span></span> | <span data-ttu-id="558af-167">`PRAGMA recursive_triggers` を送信しません。</span><span class="sxs-lookup"><span data-stu-id="558af-167">Doesn't send `PRAGMA recursive_triggers`.</span></span> <span data-ttu-id="558af-168">既定値です。</span><span class="sxs-lookup"><span data-stu-id="558af-168">This is the default.</span></span>              |

## <a name="connection-string-builder"></a><span data-ttu-id="558af-169">接続文字列ビルダー</span><span class="sxs-lookup"><span data-stu-id="558af-169">Connection string builder</span></span>

<span data-ttu-id="558af-170"><xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> は、厳密に型指定された方法で接続文字列を作成する際に使用できます。</span><span class="sxs-lookup"><span data-stu-id="558af-170">You can use <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> as a strongly typed way of creating connection strings.</span></span> <span data-ttu-id="558af-171">接続文字列のインジェクション攻撃を防止するためにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="558af-171">It can also be used to prevent connection string injection attacks.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="examples"></a><span data-ttu-id="558af-172">使用例</span><span class="sxs-lookup"><span data-stu-id="558af-172">Examples</span></span>

### <a name="basic"></a><span data-ttu-id="558af-173">Basic</span><span class="sxs-lookup"><span data-stu-id="558af-173">Basic</span></span>

<span data-ttu-id="558af-174">コンカレンシーを向上させるために共有キャッシュを使用する基本的な接続文字列。</span><span class="sxs-lookup"><span data-stu-id="558af-174">A basic connection string with a shared cache for improved concurrency.</span></span>

```ConnectionString
Data Source=Application.db;Cache=Shared
```

### <a name="encrypted"></a><span data-ttu-id="558af-175">Encrypted</span><span class="sxs-lookup"><span data-stu-id="558af-175">Encrypted</span></span>

<span data-ttu-id="558af-176">暗号化されたデータベース。</span><span class="sxs-lookup"><span data-stu-id="558af-176">An encrypted database.</span></span>

```ConnectionString
Data Source=Encrypted.db;Password=MyEncryptionKey
```

### <a name="read-only"></a><span data-ttu-id="558af-177">読み取り専用</span><span class="sxs-lookup"><span data-stu-id="558af-177">Read-only</span></span>

<span data-ttu-id="558af-178">アプリによって変更できない読み取り専用のデータベース。</span><span class="sxs-lookup"><span data-stu-id="558af-178">A read-only database that cannot be modified by the app.</span></span>

```ConnectionString
Data Source=Reference.db;Mode=ReadOnly
```

### <a name="in-memory"></a><span data-ttu-id="558af-179">メモリ内</span><span class="sxs-lookup"><span data-stu-id="558af-179">In-memory</span></span>

<span data-ttu-id="558af-180">非公開のインメモリ データベース。</span><span class="sxs-lookup"><span data-stu-id="558af-180">A private, in-memory database.</span></span>

```ConnectionString
Data Source=:memory:
```

### <a name="sharable-in-memory"></a><span data-ttu-id="558af-181">共有可能なインメモリ</span><span class="sxs-lookup"><span data-stu-id="558af-181">Sharable in-memory</span></span>

<span data-ttu-id="558af-182">*Sharable* という名前で識別される、共有可能なインメモリ データベース。</span><span class="sxs-lookup"><span data-stu-id="558af-182">A sharable, in-memory database identified by the name *Sharable*.</span></span>

```ConnectionString
Data Source=Sharable;Mode=Memory;Cache=Shared
```

## <a name="see-also"></a><span data-ttu-id="558af-183">関連項目</span><span class="sxs-lookup"><span data-stu-id="558af-183">See also</span></span>

* [<span data-ttu-id="558af-184">ADO.NET での接続文字列</span><span class="sxs-lookup"><span data-stu-id="558af-184">Connection Strings in ADO.NET</span></span>](../../../framework/data/adonet/connection-strings.md)
* [<span data-ttu-id="558af-185">インメモリ データベース</span><span class="sxs-lookup"><span data-stu-id="558af-185">In-Memory databases</span></span>](in-memory-databases.md)
* [<span data-ttu-id="558af-186">トランザクション</span><span class="sxs-lookup"><span data-stu-id="558af-186">Transactions</span></span>](transactions.md)
