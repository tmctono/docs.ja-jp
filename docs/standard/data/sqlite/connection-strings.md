---
title: 接続文字列
ms.date: 12/13/2019
description: 接続文字列のサポートされているキーワードと値。
ms.openlocfilehash: bb54d152bac62a86c2a49192cf678a745159164e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450274"
---
# <a name="connection-strings"></a><span data-ttu-id="d8f54-103">接続文字列</span><span class="sxs-lookup"><span data-stu-id="d8f54-103">Connection strings</span></span>

<span data-ttu-id="d8f54-104">接続文字列は、データベースへの接続方法を指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d8f54-104">A connection string is used to specify how to connect to the database.</span></span> <span data-ttu-id="d8f54-105">ADO.NET の接続文字列は、キーワードと値をセミコロンで区切ったリストとして、標準の[構文](../../../framework/data/adonet/connection-strings.md)に従います。</span><span class="sxs-lookup"><span data-stu-id="d8f54-105">Connection strings in Microsoft.Data.Sqlite follow the standard [ADO.NET syntax](../../../framework/data/adonet/connection-strings.md) as a semicolon-separated list of keywords and values.</span></span>

## <a name="keywords"></a><span data-ttu-id="d8f54-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="d8f54-106">Keywords</span></span>

<span data-ttu-id="d8f54-107">次の接続文字列キーワードは、Microsoft. Data. Sqlite と共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="d8f54-107">The following connection string keywords can be used with Microsoft.Data.Sqlite:</span></span>

### <a name="data-source"></a><span data-ttu-id="d8f54-108">[データ ソース]</span><span class="sxs-lookup"><span data-stu-id="d8f54-108">Data source</span></span>

<span data-ttu-id="d8f54-109">データベース ファイルのパス。</span><span class="sxs-lookup"><span data-stu-id="d8f54-109">The path to the database file.</span></span> <span data-ttu-id="d8f54-110">*DataSource* (スペースなし) と*Filename*は、このキーワードのエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="d8f54-110">*DataSource* (without a space) and *Filename* are aliases of this keyword.</span></span>

<span data-ttu-id="d8f54-111">SQLite は、現在の作業ディレクトリを基準とした相対パスを扱います。</span><span class="sxs-lookup"><span data-stu-id="d8f54-111">SQLite treats paths relative to the current working directory.</span></span> <span data-ttu-id="d8f54-112">絶対パスを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="d8f54-112">Absolute paths can also be specified.</span></span>

<span data-ttu-id="d8f54-113">**空**の場合、SQLite は接続が閉じられたときに削除される一時的なディスク上のデータベースを作成します。</span><span class="sxs-lookup"><span data-stu-id="d8f54-113">If **empty**, SQLite creates a temporary on-disk database that's deleted when the connection is closed.</span></span>

<span data-ttu-id="d8f54-114">`:memory:`すると、メモリ内データベースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="d8f54-114">If `:memory:`, an in-memory database is used.</span></span> <span data-ttu-id="d8f54-115">詳細については、「[メモリ内データベース](in-memory-databases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8f54-115">For more information, see [In-Memory databases](in-memory-databases.md).</span></span>

<span data-ttu-id="d8f54-116">`|DataDirectory|` 置換文字列で始まるパスは、相対パスと同じように扱われます。</span><span class="sxs-lookup"><span data-stu-id="d8f54-116">Paths that start with the `|DataDirectory|` substitution string are treated the same as relative paths.</span></span> <span data-ttu-id="d8f54-117">設定すると、DataDirectory アプリケーションドメインプロパティ値を基準とした相対パスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d8f54-117">If set, paths are made relative to the DataDirectory application domain property value.</span></span>

<span data-ttu-id="d8f54-118">このキーワードは[URI ファイル名](https://www.sqlite.org/uri.html)もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d8f54-118">This keyword also supports [URI Filenames](https://www.sqlite.org/uri.html).</span></span>

### <a name="mode"></a><span data-ttu-id="d8f54-119">モード</span><span class="sxs-lookup"><span data-stu-id="d8f54-119">Mode</span></span>

<span data-ttu-id="d8f54-120">接続モード。</span><span class="sxs-lookup"><span data-stu-id="d8f54-120">The connection mode.</span></span>

| <span data-ttu-id="d8f54-121">Value</span><span class="sxs-lookup"><span data-stu-id="d8f54-121">Value</span></span>           | <span data-ttu-id="d8f54-122">説明</span><span class="sxs-lookup"><span data-stu-id="d8f54-122">Description</span></span>                                                                                        |
| --------------- | -------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="d8f54-123">ReadWriteCreate</span><span class="sxs-lookup"><span data-stu-id="d8f54-123">ReadWriteCreate</span></span> | <span data-ttu-id="d8f54-124">読み取りと書き込みのためにデータベースを開き、存在しない場合は作成します。</span><span class="sxs-lookup"><span data-stu-id="d8f54-124">Opens the database for reading and writing, and creates it if it doesn't exist.</span></span> <span data-ttu-id="d8f54-125">これは既定です。</span><span class="sxs-lookup"><span data-stu-id="d8f54-125">This is the default.</span></span> |
| <span data-ttu-id="d8f54-126">ReadWrite</span><span class="sxs-lookup"><span data-stu-id="d8f54-126">ReadWrite</span></span>       | <span data-ttu-id="d8f54-127">読み取りと書き込みのためにデータベースを開きます。</span><span class="sxs-lookup"><span data-stu-id="d8f54-127">Opens the database for reading and writing.</span></span>                                                        |
| <span data-ttu-id="d8f54-128">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="d8f54-128">ReadOnly</span></span>        | <span data-ttu-id="d8f54-129">データベースを読み取り専用モードで開きます。</span><span class="sxs-lookup"><span data-stu-id="d8f54-129">Opens the database in read-only mode.</span></span>                                                              |
| <span data-ttu-id="d8f54-130">メモリ</span><span class="sxs-lookup"><span data-stu-id="d8f54-130">Memory</span></span>          | <span data-ttu-id="d8f54-131">メモリ内データベースを開きます。</span><span class="sxs-lookup"><span data-stu-id="d8f54-131">Opens an in-memory database.</span></span>                                                                       |

### <a name="cache"></a><span data-ttu-id="d8f54-132">キャッシュ</span><span class="sxs-lookup"><span data-stu-id="d8f54-132">Cache</span></span>

<span data-ttu-id="d8f54-133">接続で使用されるキャッシュモード。</span><span class="sxs-lookup"><span data-stu-id="d8f54-133">The caching mode used by the connection.</span></span>

| <span data-ttu-id="d8f54-134">Value</span><span class="sxs-lookup"><span data-stu-id="d8f54-134">Value</span></span>   | <span data-ttu-id="d8f54-135">説明</span><span class="sxs-lookup"><span data-stu-id="d8f54-135">Description</span></span>                                                                                    |
| ------- | ---------------------------------------------------------------------------------------------- |
| <span data-ttu-id="d8f54-136">[既定値]</span><span class="sxs-lookup"><span data-stu-id="d8f54-136">Default</span></span> | <span data-ttu-id="d8f54-137">は、基になる SQLite ライブラリの既定のモードを使用します。</span><span class="sxs-lookup"><span data-stu-id="d8f54-137">Uses the default mode of the underlying SQLite library.</span></span> <span data-ttu-id="d8f54-138">これは既定です。</span><span class="sxs-lookup"><span data-stu-id="d8f54-138">This is the default.</span></span>                   |
| <span data-ttu-id="d8f54-139">Private</span><span class="sxs-lookup"><span data-stu-id="d8f54-139">Private</span></span> | <span data-ttu-id="d8f54-140">各接続は、プライベートキャッシュを使用します。</span><span class="sxs-lookup"><span data-stu-id="d8f54-140">Each connection uses a private cache.</span></span>                                                          |
| <span data-ttu-id="d8f54-141">[共有]</span><span class="sxs-lookup"><span data-stu-id="d8f54-141">Shared</span></span>  | <span data-ttu-id="d8f54-142">接続はキャッシュを共有します。</span><span class="sxs-lookup"><span data-stu-id="d8f54-142">Connections share a cache.</span></span> <span data-ttu-id="d8f54-143">このモードでは、トランザクションおよびテーブルロックの動作を変更できます。</span><span class="sxs-lookup"><span data-stu-id="d8f54-143">This mode can change the behavior of transaction and table locking.</span></span> |

### <a name="password"></a><span data-ttu-id="d8f54-144">Password</span><span class="sxs-lookup"><span data-stu-id="d8f54-144">Password</span></span>

<span data-ttu-id="d8f54-145">暗号化キー。</span><span class="sxs-lookup"><span data-stu-id="d8f54-145">The encryption key.</span></span> <span data-ttu-id="d8f54-146">指定した場合、接続を開いた直後に `PRAGMA key` が送信されます。</span><span class="sxs-lookup"><span data-stu-id="d8f54-146">When specified, `PRAGMA key` is sent immediately after opening the connection.</span></span>

> [!WARNING]
> <span data-ttu-id="d8f54-147">ネイティブ SQLite ライブラリで暗号化がサポートされていない場合、パスワードは無効です。</span><span class="sxs-lookup"><span data-stu-id="d8f54-147">Password has no effect when encryption isn't supported by the native SQLite library.</span></span>

### <a name="foreign-keys"></a><span data-ttu-id="d8f54-148">外部キー</span><span class="sxs-lookup"><span data-stu-id="d8f54-148">Foreign Keys</span></span>

<span data-ttu-id="d8f54-149">Foreign key 制約を有効にするかどうかを示す値です。</span><span class="sxs-lookup"><span data-stu-id="d8f54-149">A value indicating whether to enable foreign key constraints.</span></span>

| <span data-ttu-id="d8f54-150">Value</span><span class="sxs-lookup"><span data-stu-id="d8f54-150">Value</span></span>   | <span data-ttu-id="d8f54-151">説明</span><span class="sxs-lookup"><span data-stu-id="d8f54-151">Description</span></span>
| ------- | --- |
| <span data-ttu-id="d8f54-152">True</span><span class="sxs-lookup"><span data-stu-id="d8f54-152">True</span></span>    | <span data-ttu-id="d8f54-153">接続を開いた直後に `PRAGMA foreign_keys = 1` を送信します。</span><span class="sxs-lookup"><span data-stu-id="d8f54-153">Sends `PRAGMA foreign_keys = 1` immediately after opening the connection.</span></span>
| <span data-ttu-id="d8f54-154">[False]</span><span class="sxs-lookup"><span data-stu-id="d8f54-154">False</span></span>   | <span data-ttu-id="d8f54-155">接続を開いた直後に `PRAGMA foreign_keys = 0` を送信します。</span><span class="sxs-lookup"><span data-stu-id="d8f54-155">Sends `PRAGMA foreign_keys = 0` immediately after opening the connection.</span></span>
| <span data-ttu-id="d8f54-156">(空)</span><span class="sxs-lookup"><span data-stu-id="d8f54-156">(empty)</span></span> | <span data-ttu-id="d8f54-157">`PRAGMA foreign_keys`を送信しません。</span><span class="sxs-lookup"><span data-stu-id="d8f54-157">Doesn't send `PRAGMA foreign_keys`.</span></span> <span data-ttu-id="d8f54-158">これは既定です。</span><span class="sxs-lookup"><span data-stu-id="d8f54-158">This is the default.</span></span> |

<span data-ttu-id="d8f54-159">E_sqlite3 のように、ネイティブ SQLite ライブラリをコンパイルするために SQLITE_DEFAULT_FOREIGN_KEYS を使用した場合、外部キーを有効にする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d8f54-159">There's no need enable foreign keys if, like in e_sqlite3, SQLITE_DEFAULT_FOREIGN_KEYS was used to compile the native SQLite library.</span></span>

### <a name="recursive-triggers"></a><span data-ttu-id="d8f54-160">再帰トリガー</span><span class="sxs-lookup"><span data-stu-id="d8f54-160">Recursive triggers</span></span>

<span data-ttu-id="d8f54-161">再帰トリガーを有効にするかどうかを示す値です。</span><span class="sxs-lookup"><span data-stu-id="d8f54-161">A value that indicates whether to enable recursive triggers.</span></span>

| <span data-ttu-id="d8f54-162">Value</span><span class="sxs-lookup"><span data-stu-id="d8f54-162">Value</span></span> | <span data-ttu-id="d8f54-163">説明</span><span class="sxs-lookup"><span data-stu-id="d8f54-163">Description</span></span>                                                                 |
| ----- | --------------------------------------------------------------------------- |
| <span data-ttu-id="d8f54-164">True</span><span class="sxs-lookup"><span data-stu-id="d8f54-164">True</span></span>  | <span data-ttu-id="d8f54-165">接続を開いた直後に `PRAGMA recursive_triggers` を送信します。</span><span class="sxs-lookup"><span data-stu-id="d8f54-165">Sends `PRAGMA recursive_triggers` immediately after opening the connection.</span></span> |
| <span data-ttu-id="d8f54-166">[False]</span><span class="sxs-lookup"><span data-stu-id="d8f54-166">False</span></span> | <span data-ttu-id="d8f54-167">`PRAGMA recursive_triggers`を送信しません。</span><span class="sxs-lookup"><span data-stu-id="d8f54-167">Doesn't send `PRAGMA recursive_triggers`.</span></span> <span data-ttu-id="d8f54-168">これは既定です。</span><span class="sxs-lookup"><span data-stu-id="d8f54-168">This is the default.</span></span>              |

## <a name="connection-string-builder"></a><span data-ttu-id="d8f54-169">接続文字列ビルダー</span><span class="sxs-lookup"><span data-stu-id="d8f54-169">Connection string builder</span></span>

<span data-ttu-id="d8f54-170"><xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> は、厳密に型指定された接続文字列の作成方法として使用できます。</span><span class="sxs-lookup"><span data-stu-id="d8f54-170">You can use <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> as a strongly typed way of creating connection strings.</span></span> <span data-ttu-id="d8f54-171">また、接続文字列のインジェクション攻撃を防ぐためにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="d8f54-171">It can also be used to prevent connection string injection attacks.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="examples"></a><span data-ttu-id="d8f54-172">使用例</span><span class="sxs-lookup"><span data-stu-id="d8f54-172">Examples</span></span>

### <a name="basic"></a><span data-ttu-id="d8f54-173">Basic</span><span class="sxs-lookup"><span data-stu-id="d8f54-173">Basic</span></span>

<span data-ttu-id="d8f54-174">同時実行性を向上させるための共有キャッシュを備えた基本的な接続文字列。</span><span class="sxs-lookup"><span data-stu-id="d8f54-174">A basic connection string with a shared cache for improved concurrency.</span></span>

```ConnectionString
Data Source=Application.db;Cache=Shared
```

### <a name="encrypted"></a><span data-ttu-id="d8f54-175">暗号化</span><span class="sxs-lookup"><span data-stu-id="d8f54-175">Encrypted</span></span>

<span data-ttu-id="d8f54-176">暗号化されたデータベース。</span><span class="sxs-lookup"><span data-stu-id="d8f54-176">An encrypted database.</span></span>

```ConnectionString
Data Source=Encrypted.db;Password=MyEncryptionKey
```

### <a name="read-only"></a><span data-ttu-id="d8f54-177">読み取り専用</span><span class="sxs-lookup"><span data-stu-id="d8f54-177">Read-only</span></span>

<span data-ttu-id="d8f54-178">アプリによって変更できない読み取り専用のデータベース。</span><span class="sxs-lookup"><span data-stu-id="d8f54-178">A read-only database that cannot be modified by the app.</span></span>

```ConnectionString
Data Source=Reference.db;Mode=ReadOnly
```

### <a name="in-memory"></a><span data-ttu-id="d8f54-179">メモリ内</span><span class="sxs-lookup"><span data-stu-id="d8f54-179">In-memory</span></span>

<span data-ttu-id="d8f54-180">プライベートなメモリ内データベース。</span><span class="sxs-lookup"><span data-stu-id="d8f54-180">A private, in-memory database.</span></span>

```ConnectionString
Data Source=:memory:
```

### <a name="sharable-in-memory"></a><span data-ttu-id="d8f54-181">メモリ内で共有可能</span><span class="sxs-lookup"><span data-stu-id="d8f54-181">Sharable in-memory</span></span>

<span data-ttu-id="d8f54-182">*共有可能な名前で*識別される、共有可能なメモリ内のデータベース。</span><span class="sxs-lookup"><span data-stu-id="d8f54-182">A sharable, in-memory database identified by the name *Sharable*.</span></span>

```ConnectionString
Data Source=Sharable;Mode=Memory;Cache=Shared
```

## <a name="see-also"></a><span data-ttu-id="d8f54-183">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8f54-183">See also</span></span>

* [<span data-ttu-id="d8f54-184">ADO.NET の接続文字列</span><span class="sxs-lookup"><span data-stu-id="d8f54-184">Connection Strings in ADO.NET</span></span>](../../../framework/data/adonet/connection-strings.md)
* [<span data-ttu-id="d8f54-185">インメモリデータベース</span><span class="sxs-lookup"><span data-stu-id="d8f54-185">In-Memory databases</span></span>](in-memory-databases.md)
* [<span data-ttu-id="d8f54-186">トランザクション</span><span class="sxs-lookup"><span data-stu-id="d8f54-186">Transactions</span></span>](transactions.md)
