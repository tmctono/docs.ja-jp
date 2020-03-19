---
title: Connection strings
ms.date: 12/13/2019
description: サポートされている接続文字列のキーワードと値。
ms.openlocfilehash: bb54d152bac62a86c2a49192cf678a745159164e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401197"
---
# <a name="connection-strings"></a><span data-ttu-id="04dd8-103">Connection strings</span><span class="sxs-lookup"><span data-stu-id="04dd8-103">Connection strings</span></span>

<span data-ttu-id="04dd8-104">接続文字列を使用して、データベースへの接続方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="04dd8-104">A connection string is used to specify how to connect to the database.</span></span> <span data-ttu-id="04dd8-105">Microsoft.Data.Sqlite の接続文字列は、キーワードと値のセミコロン区切りのリストとして標準の[ADO.NET構文](../../../framework/data/adonet/connection-strings.md)に従います。</span><span class="sxs-lookup"><span data-stu-id="04dd8-105">Connection strings in Microsoft.Data.Sqlite follow the standard [ADO.NET syntax](../../../framework/data/adonet/connection-strings.md) as a semicolon-separated list of keywords and values.</span></span>

## <a name="keywords"></a><span data-ttu-id="04dd8-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="04dd8-106">Keywords</span></span>

<span data-ttu-id="04dd8-107">次の接続文字列キーワードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="04dd8-107">The following connection string keywords can be used with Microsoft.Data.Sqlite:</span></span>

### <a name="data-source"></a><span data-ttu-id="04dd8-108">データ ソース</span><span class="sxs-lookup"><span data-stu-id="04dd8-108">Data source</span></span>

<span data-ttu-id="04dd8-109">データベース ファイルのパス。</span><span class="sxs-lookup"><span data-stu-id="04dd8-109">The path to the database file.</span></span> <span data-ttu-id="04dd8-110">*データソース*(スペースなし) と*ファイル名*はこのキーワードのエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="04dd8-110">*DataSource* (without a space) and *Filename* are aliases of this keyword.</span></span>

<span data-ttu-id="04dd8-111">SQLite は、現在の作業ディレクトリに対する相対パスを扱います。</span><span class="sxs-lookup"><span data-stu-id="04dd8-111">SQLite treats paths relative to the current working directory.</span></span> <span data-ttu-id="04dd8-112">絶対パスも指定できます。</span><span class="sxs-lookup"><span data-stu-id="04dd8-112">Absolute paths can also be specified.</span></span>

<span data-ttu-id="04dd8-113">**空**の場合、SQLite は接続が閉じられたときに削除される一時的なディスク上のデータベースを作成します。</span><span class="sxs-lookup"><span data-stu-id="04dd8-113">If **empty**, SQLite creates a temporary on-disk database that's deleted when the connection is closed.</span></span>

<span data-ttu-id="04dd8-114">の`:memory:`場合、インメモリ データベースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="04dd8-114">If `:memory:`, an in-memory database is used.</span></span> <span data-ttu-id="04dd8-115">詳細については、「[インメモリ データベース](in-memory-databases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04dd8-115">For more information, see [In-Memory databases](in-memory-databases.md).</span></span>

<span data-ttu-id="04dd8-116">`|DataDirectory|`置換文字列で始まるパスは、相対パスと同じように扱われます。</span><span class="sxs-lookup"><span data-stu-id="04dd8-116">Paths that start with the `|DataDirectory|` substitution string are treated the same as relative paths.</span></span> <span data-ttu-id="04dd8-117">設定すると、パスは DataDirectory アプリケーション ドメイン プロパティの値に対して相対的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="04dd8-117">If set, paths are made relative to the DataDirectory application domain property value.</span></span>

<span data-ttu-id="04dd8-118">このキーワードは[、URI ファイル名](https://www.sqlite.org/uri.html)もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="04dd8-118">This keyword also supports [URI Filenames](https://www.sqlite.org/uri.html).</span></span>

### <a name="mode"></a><span data-ttu-id="04dd8-119">モード</span><span class="sxs-lookup"><span data-stu-id="04dd8-119">Mode</span></span>

<span data-ttu-id="04dd8-120">接続モード。</span><span class="sxs-lookup"><span data-stu-id="04dd8-120">The connection mode.</span></span>

| <span data-ttu-id="04dd8-121">Value</span><span class="sxs-lookup"><span data-stu-id="04dd8-121">Value</span></span>           | <span data-ttu-id="04dd8-122">説明</span><span class="sxs-lookup"><span data-stu-id="04dd8-122">Description</span></span>                                                                                        |
| --------------- | -------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="04dd8-123">書き込み書き込み作成</span><span class="sxs-lookup"><span data-stu-id="04dd8-123">ReadWriteCreate</span></span> | <span data-ttu-id="04dd8-124">データベースを読み書き用に開き、存在しない場合は作成します。</span><span class="sxs-lookup"><span data-stu-id="04dd8-124">Opens the database for reading and writing, and creates it if it doesn't exist.</span></span> <span data-ttu-id="04dd8-125">これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="04dd8-125">This is the default.</span></span> |
| <span data-ttu-id="04dd8-126">ReadWrite</span><span class="sxs-lookup"><span data-stu-id="04dd8-126">ReadWrite</span></span>       | <span data-ttu-id="04dd8-127">データベースを読み書き用に開きます。</span><span class="sxs-lookup"><span data-stu-id="04dd8-127">Opens the database for reading and writing.</span></span>                                                        |
| <span data-ttu-id="04dd8-128">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="04dd8-128">ReadOnly</span></span>        | <span data-ttu-id="04dd8-129">データベースを読み取り専用モードで開きます。</span><span class="sxs-lookup"><span data-stu-id="04dd8-129">Opens the database in read-only mode.</span></span>                                                              |
| <span data-ttu-id="04dd8-130">メモリ</span><span class="sxs-lookup"><span data-stu-id="04dd8-130">Memory</span></span>          | <span data-ttu-id="04dd8-131">インメモリ データベースを開きます。</span><span class="sxs-lookup"><span data-stu-id="04dd8-131">Opens an in-memory database.</span></span>                                                                       |

### <a name="cache"></a><span data-ttu-id="04dd8-132">キャッシュ</span><span class="sxs-lookup"><span data-stu-id="04dd8-132">Cache</span></span>

<span data-ttu-id="04dd8-133">接続で使用されるキャッシュ モード。</span><span class="sxs-lookup"><span data-stu-id="04dd8-133">The caching mode used by the connection.</span></span>

| <span data-ttu-id="04dd8-134">Value</span><span class="sxs-lookup"><span data-stu-id="04dd8-134">Value</span></span>   | <span data-ttu-id="04dd8-135">説明</span><span class="sxs-lookup"><span data-stu-id="04dd8-135">Description</span></span>                                                                                    |
| ------- | ---------------------------------------------------------------------------------------------- |
| <span data-ttu-id="04dd8-136">Default</span><span class="sxs-lookup"><span data-stu-id="04dd8-136">Default</span></span> | <span data-ttu-id="04dd8-137">基になる SQLite ライブラリの既定のモードを使用します。</span><span class="sxs-lookup"><span data-stu-id="04dd8-137">Uses the default mode of the underlying SQLite library.</span></span> <span data-ttu-id="04dd8-138">これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="04dd8-138">This is the default.</span></span>                   |
| <span data-ttu-id="04dd8-139">プライベート</span><span class="sxs-lookup"><span data-stu-id="04dd8-139">Private</span></span> | <span data-ttu-id="04dd8-140">各接続はプライベート キャッシュを使用します。</span><span class="sxs-lookup"><span data-stu-id="04dd8-140">Each connection uses a private cache.</span></span>                                                          |
| <span data-ttu-id="04dd8-141">共有</span><span class="sxs-lookup"><span data-stu-id="04dd8-141">Shared</span></span>  | <span data-ttu-id="04dd8-142">接続はキャッシュを共有します。</span><span class="sxs-lookup"><span data-stu-id="04dd8-142">Connections share a cache.</span></span> <span data-ttu-id="04dd8-143">このモードは、トランザクションとテーブルロックの動作を変更できます。</span><span class="sxs-lookup"><span data-stu-id="04dd8-143">This mode can change the behavior of transaction and table locking.</span></span> |

### <a name="password"></a><span data-ttu-id="04dd8-144">Password</span><span class="sxs-lookup"><span data-stu-id="04dd8-144">Password</span></span>

<span data-ttu-id="04dd8-145">暗号化キー。</span><span class="sxs-lookup"><span data-stu-id="04dd8-145">The encryption key.</span></span> <span data-ttu-id="04dd8-146">指定すると、`PRAGMA key`接続を開いた直後に送信されます。</span><span class="sxs-lookup"><span data-stu-id="04dd8-146">When specified, `PRAGMA key` is sent immediately after opening the connection.</span></span>

> [!WARNING]
> <span data-ttu-id="04dd8-147">パスワードは、暗号化がネイティブの SQLite ライブラリでサポートされていない場合には無効です。</span><span class="sxs-lookup"><span data-stu-id="04dd8-147">Password has no effect when encryption isn't supported by the native SQLite library.</span></span>

### <a name="foreign-keys"></a><span data-ttu-id="04dd8-148">外部キー</span><span class="sxs-lookup"><span data-stu-id="04dd8-148">Foreign Keys</span></span>

<span data-ttu-id="04dd8-149">外部キー制約を有効にするかどうかを示す値。</span><span class="sxs-lookup"><span data-stu-id="04dd8-149">A value indicating whether to enable foreign key constraints.</span></span>

| <span data-ttu-id="04dd8-150">Value</span><span class="sxs-lookup"><span data-stu-id="04dd8-150">Value</span></span>   | <span data-ttu-id="04dd8-151">説明</span><span class="sxs-lookup"><span data-stu-id="04dd8-151">Description</span></span>
| ------- | --- |
| <span data-ttu-id="04dd8-152">True</span><span class="sxs-lookup"><span data-stu-id="04dd8-152">True</span></span>    | <span data-ttu-id="04dd8-153">接続`PRAGMA foreign_keys = 1`を開いた直後に送信します。</span><span class="sxs-lookup"><span data-stu-id="04dd8-153">Sends `PRAGMA foreign_keys = 1` immediately after opening the connection.</span></span>
| <span data-ttu-id="04dd8-154">False</span><span class="sxs-lookup"><span data-stu-id="04dd8-154">False</span></span>   | <span data-ttu-id="04dd8-155">接続`PRAGMA foreign_keys = 0`を開いた直後に送信します。</span><span class="sxs-lookup"><span data-stu-id="04dd8-155">Sends `PRAGMA foreign_keys = 0` immediately after opening the connection.</span></span>
| <span data-ttu-id="04dd8-156">(空)</span><span class="sxs-lookup"><span data-stu-id="04dd8-156">(empty)</span></span> | <span data-ttu-id="04dd8-157">を送信`PRAGMA foreign_keys`しません。</span><span class="sxs-lookup"><span data-stu-id="04dd8-157">Doesn't send `PRAGMA foreign_keys`.</span></span> <span data-ttu-id="04dd8-158">これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="04dd8-158">This is the default.</span></span> |

<span data-ttu-id="04dd8-159">ネイティブ SQLite ライブラリのコンパイルに使用SQLITE_DEFAULT_FOREIGN_KEYS、e_sqlite3のように、外部キーを有効にする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="04dd8-159">There's no need enable foreign keys if, like in e_sqlite3, SQLITE_DEFAULT_FOREIGN_KEYS was used to compile the native SQLite library.</span></span>

### <a name="recursive-triggers"></a><span data-ttu-id="04dd8-160">再帰的トリガー</span><span class="sxs-lookup"><span data-stu-id="04dd8-160">Recursive triggers</span></span>

<span data-ttu-id="04dd8-161">再帰的なトリガーを有効にするかどうかを示す値。</span><span class="sxs-lookup"><span data-stu-id="04dd8-161">A value that indicates whether to enable recursive triggers.</span></span>

| <span data-ttu-id="04dd8-162">Value</span><span class="sxs-lookup"><span data-stu-id="04dd8-162">Value</span></span> | <span data-ttu-id="04dd8-163">説明</span><span class="sxs-lookup"><span data-stu-id="04dd8-163">Description</span></span>                                                                 |
| ----- | --------------------------------------------------------------------------- |
| <span data-ttu-id="04dd8-164">True</span><span class="sxs-lookup"><span data-stu-id="04dd8-164">True</span></span>  | <span data-ttu-id="04dd8-165">接続`PRAGMA recursive_triggers`を開いた直後に送信します。</span><span class="sxs-lookup"><span data-stu-id="04dd8-165">Sends `PRAGMA recursive_triggers` immediately after opening the connection.</span></span> |
| <span data-ttu-id="04dd8-166">False</span><span class="sxs-lookup"><span data-stu-id="04dd8-166">False</span></span> | <span data-ttu-id="04dd8-167">を送信`PRAGMA recursive_triggers`しません。</span><span class="sxs-lookup"><span data-stu-id="04dd8-167">Doesn't send `PRAGMA recursive_triggers`.</span></span> <span data-ttu-id="04dd8-168">これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="04dd8-168">This is the default.</span></span>              |

## <a name="connection-string-builder"></a><span data-ttu-id="04dd8-169">接続文字列ビルダ</span><span class="sxs-lookup"><span data-stu-id="04dd8-169">Connection string builder</span></span>

<span data-ttu-id="04dd8-170">接続文字列を作成<xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder>する厳密に型指定された方法として使用できます。</span><span class="sxs-lookup"><span data-stu-id="04dd8-170">You can use <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> as a strongly typed way of creating connection strings.</span></span> <span data-ttu-id="04dd8-171">また、接続文字列の挿入攻撃を防ぐためにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="04dd8-171">It can also be used to prevent connection string injection attacks.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="examples"></a><span data-ttu-id="04dd8-172">例</span><span class="sxs-lookup"><span data-stu-id="04dd8-172">Examples</span></span>

### <a name="basic"></a><span data-ttu-id="04dd8-173">Basic</span><span class="sxs-lookup"><span data-stu-id="04dd8-173">Basic</span></span>

<span data-ttu-id="04dd8-174">同時実行性を向上させる共有キャッシュを持つ基本的な接続文字列。</span><span class="sxs-lookup"><span data-stu-id="04dd8-174">A basic connection string with a shared cache for improved concurrency.</span></span>

```ConnectionString
Data Source=Application.db;Cache=Shared
```

### <a name="encrypted"></a><span data-ttu-id="04dd8-175">Encrypted</span><span class="sxs-lookup"><span data-stu-id="04dd8-175">Encrypted</span></span>

<span data-ttu-id="04dd8-176">暗号化されたデータベース。</span><span class="sxs-lookup"><span data-stu-id="04dd8-176">An encrypted database.</span></span>

```ConnectionString
Data Source=Encrypted.db;Password=MyEncryptionKey
```

### <a name="read-only"></a><span data-ttu-id="04dd8-177">読み取り専用</span><span class="sxs-lookup"><span data-stu-id="04dd8-177">Read-only</span></span>

<span data-ttu-id="04dd8-178">アプリで変更できない読み取り専用データベース。</span><span class="sxs-lookup"><span data-stu-id="04dd8-178">A read-only database that cannot be modified by the app.</span></span>

```ConnectionString
Data Source=Reference.db;Mode=ReadOnly
```

### <a name="in-memory"></a><span data-ttu-id="04dd8-179">メモリ内</span><span class="sxs-lookup"><span data-stu-id="04dd8-179">In-memory</span></span>

<span data-ttu-id="04dd8-180">プライベートなメモリ内データベース。</span><span class="sxs-lookup"><span data-stu-id="04dd8-180">A private, in-memory database.</span></span>

```ConnectionString
Data Source=:memory:
```

### <a name="sharable-in-memory"></a><span data-ttu-id="04dd8-181">メモリ内で共有可能</span><span class="sxs-lookup"><span data-stu-id="04dd8-181">Sharable in-memory</span></span>

<span data-ttu-id="04dd8-182">名前で識別される共有可能なインメモリ データベース*で、*</span><span class="sxs-lookup"><span data-stu-id="04dd8-182">A sharable, in-memory database identified by the name *Sharable*.</span></span>

```ConnectionString
Data Source=Sharable;Mode=Memory;Cache=Shared
```

## <a name="see-also"></a><span data-ttu-id="04dd8-183">関連項目</span><span class="sxs-lookup"><span data-stu-id="04dd8-183">See also</span></span>

* [<span data-ttu-id="04dd8-184">ADO.NET での接続文字列</span><span class="sxs-lookup"><span data-stu-id="04dd8-184">Connection Strings in ADO.NET</span></span>](../../../framework/data/adonet/connection-strings.md)
* [<span data-ttu-id="04dd8-185">インメモリ データベース</span><span class="sxs-lookup"><span data-stu-id="04dd8-185">In-Memory databases</span></span>](in-memory-databases.md)
* [<span data-ttu-id="04dd8-186">トランザクション</span><span class="sxs-lookup"><span data-stu-id="04dd8-186">Transactions</span></span>](transactions.md)
