---
title: 接続文字列
ms.date: 12/13/2019
description: 接続文字列でサポートされているキーワードと値です。
ms.openlocfilehash: 3c50b31689abf6d47aa8f83a6f6f755bcfec0ea3
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555394"
---
# <a name="connection-strings"></a><span data-ttu-id="56e2b-103">接続文字列</span><span class="sxs-lookup"><span data-stu-id="56e2b-103">Connection strings</span></span>

<span data-ttu-id="56e2b-104">接続文字列は、データベースへの接続方法を指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="56e2b-104">A connection string is used to specify how to connect to the database.</span></span> <span data-ttu-id="56e2b-105">Microsoft.Data.Sqlite の接続文字列は、セミコロンで区切られたキーワードと値のリストとして、標準の [ADO.NET 構文](../../../framework/data/adonet/connection-strings.md)に従っています。</span><span class="sxs-lookup"><span data-stu-id="56e2b-105">Connection strings in Microsoft.Data.Sqlite follow the standard [ADO.NET syntax](../../../framework/data/adonet/connection-strings.md) as a semicolon-separated list of keywords and values.</span></span>

## <a name="keywords"></a><span data-ttu-id="56e2b-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="56e2b-106">Keywords</span></span>

<span data-ttu-id="56e2b-107">Microsoft.Data.Sqlite では次の接続文字列キーワードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="56e2b-107">The following connection string keywords can be used with Microsoft.Data.Sqlite:</span></span>

### <a name="data-source"></a><span data-ttu-id="56e2b-108">データ ソース</span><span class="sxs-lookup"><span data-stu-id="56e2b-108">Data source</span></span>

<span data-ttu-id="56e2b-109">データベース ファイルのパス。</span><span class="sxs-lookup"><span data-stu-id="56e2b-109">The path to the database file.</span></span> <span data-ttu-id="56e2b-110">*DataSource* (スペースなし) と *Filename* はこのキーワードの別名です。</span><span class="sxs-lookup"><span data-stu-id="56e2b-110">*DataSource* (without a space) and *Filename* are aliases of this keyword.</span></span>

<span data-ttu-id="56e2b-111">SQLite では、パスは現在の作業ディレクトリからの相対パスとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="56e2b-111">SQLite treats paths relative to the current working directory.</span></span> <span data-ttu-id="56e2b-112">絶対パスも指定できます。</span><span class="sxs-lookup"><span data-stu-id="56e2b-112">Absolute paths can also be specified.</span></span>

<span data-ttu-id="56e2b-113">**空**の場合、一時的なディスク上のデータベースが作成されます。このデータベースは接続が閉じられるときに削除されます。</span><span class="sxs-lookup"><span data-stu-id="56e2b-113">If **empty**, SQLite creates a temporary on-disk database that's deleted when the connection is closed.</span></span>

<span data-ttu-id="56e2b-114">`:memory:` の場合、インメモリ データベースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="56e2b-114">If `:memory:`, an in-memory database is used.</span></span> <span data-ttu-id="56e2b-115">詳細については、「[インメモリ データベース](in-memory-databases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56e2b-115">For more information, see [In-Memory databases](in-memory-databases.md).</span></span>

<span data-ttu-id="56e2b-116">`|DataDirectory|` 置換文字列で始まるパスは、相対パスと同じように扱われます。</span><span class="sxs-lookup"><span data-stu-id="56e2b-116">Paths that start with the `|DataDirectory|` substitution string are treated the same as relative paths.</span></span> <span data-ttu-id="56e2b-117">設定すると、パスは DataDirectory アプリケーション ドメイン プロパティ値を基準とした相対パスになります。</span><span class="sxs-lookup"><span data-stu-id="56e2b-117">If set, paths are made relative to the DataDirectory application domain property value.</span></span>

<span data-ttu-id="56e2b-118">このキーワードでは、[URI ファイル名](https://www.sqlite.org/uri.html)もサポートされます。</span><span class="sxs-lookup"><span data-stu-id="56e2b-118">This keyword also supports [URI Filenames](https://www.sqlite.org/uri.html).</span></span>

### <a name="mode"></a><span data-ttu-id="56e2b-119">モード</span><span class="sxs-lookup"><span data-stu-id="56e2b-119">Mode</span></span>

<span data-ttu-id="56e2b-120">接続モード。</span><span class="sxs-lookup"><span data-stu-id="56e2b-120">The connection mode.</span></span>

| <span data-ttu-id="56e2b-121">[値]</span><span class="sxs-lookup"><span data-stu-id="56e2b-121">Value</span></span>           | <span data-ttu-id="56e2b-122">説明</span><span class="sxs-lookup"><span data-stu-id="56e2b-122">Description</span></span>                                                                                        |
| --------------- | -------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="56e2b-123">ReadWriteCreate</span><span class="sxs-lookup"><span data-stu-id="56e2b-123">ReadWriteCreate</span></span> | <span data-ttu-id="56e2b-124">読み取りと書き込みを行うデータベースを開きます。データベースが存在しない場合は作成します。</span><span class="sxs-lookup"><span data-stu-id="56e2b-124">Opens the database for reading and writing, and creates it if it doesn't exist.</span></span> <span data-ttu-id="56e2b-125">既定値です。</span><span class="sxs-lookup"><span data-stu-id="56e2b-125">This is the default.</span></span> |
| <span data-ttu-id="56e2b-126">ReadWrite</span><span class="sxs-lookup"><span data-stu-id="56e2b-126">ReadWrite</span></span>       | <span data-ttu-id="56e2b-127">読み取りと書き込みを行うデータベースを開きます。</span><span class="sxs-lookup"><span data-stu-id="56e2b-127">Opens the database for reading and writing.</span></span>                                                        |
| <span data-ttu-id="56e2b-128">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="56e2b-128">ReadOnly</span></span>        | <span data-ttu-id="56e2b-129">データベースを読み取り専用モードで開きます。</span><span class="sxs-lookup"><span data-stu-id="56e2b-129">Opens the database in read-only mode.</span></span>                                                              |
| <span data-ttu-id="56e2b-130">メモリ</span><span class="sxs-lookup"><span data-stu-id="56e2b-130">Memory</span></span>          | <span data-ttu-id="56e2b-131">インメモリ データベースを開きます。</span><span class="sxs-lookup"><span data-stu-id="56e2b-131">Opens an in-memory database.</span></span>                                                                       |

### <a name="cache"></a><span data-ttu-id="56e2b-132">キャッシュ</span><span class="sxs-lookup"><span data-stu-id="56e2b-132">Cache</span></span>

<span data-ttu-id="56e2b-133">接続で使用されるキャッシュ モード。</span><span class="sxs-lookup"><span data-stu-id="56e2b-133">The caching mode used by the connection.</span></span>

| <span data-ttu-id="56e2b-134">[値]</span><span class="sxs-lookup"><span data-stu-id="56e2b-134">Value</span></span>   | <span data-ttu-id="56e2b-135">説明</span><span class="sxs-lookup"><span data-stu-id="56e2b-135">Description</span></span>                                                                                    |
| ------- | ---------------------------------------------------------------------------------------------- |
| <span data-ttu-id="56e2b-136">Default</span><span class="sxs-lookup"><span data-stu-id="56e2b-136">Default</span></span> | <span data-ttu-id="56e2b-137">基になる SQLite ライブラリの既定のモードを使用します。</span><span class="sxs-lookup"><span data-stu-id="56e2b-137">Uses the default mode of the underlying SQLite library.</span></span> <span data-ttu-id="56e2b-138">既定値です。</span><span class="sxs-lookup"><span data-stu-id="56e2b-138">This is the default.</span></span>                   |
| <span data-ttu-id="56e2b-139">Private</span><span class="sxs-lookup"><span data-stu-id="56e2b-139">Private</span></span> | <span data-ttu-id="56e2b-140">各接続で、プライベート キャッシュを使用します。</span><span class="sxs-lookup"><span data-stu-id="56e2b-140">Each connection uses a private cache.</span></span>                                                          |
| <span data-ttu-id="56e2b-141">Shared</span><span class="sxs-lookup"><span data-stu-id="56e2b-141">Shared</span></span>  | <span data-ttu-id="56e2b-142">接続でキャッシュを共有します。</span><span class="sxs-lookup"><span data-stu-id="56e2b-142">Connections share a cache.</span></span> <span data-ttu-id="56e2b-143">このモードでは、トランザクションとテーブル ロックの動作が変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="56e2b-143">This mode can change the behavior of transaction and table locking.</span></span> |

### <a name="password"></a><span data-ttu-id="56e2b-144">パスワード</span><span class="sxs-lookup"><span data-stu-id="56e2b-144">Password</span></span>

<span data-ttu-id="56e2b-145">暗号化キー。</span><span class="sxs-lookup"><span data-stu-id="56e2b-145">The encryption key.</span></span> <span data-ttu-id="56e2b-146">指定した場合、接続を開いた直後に `PRAGMA key` が送信されます。</span><span class="sxs-lookup"><span data-stu-id="56e2b-146">When specified, `PRAGMA key` is sent immediately after opening the connection.</span></span>

> [!WARNING]
> <span data-ttu-id="56e2b-147">暗号化がネイティブ SQLite ライブラリでサポートされていない場合、パスワードの効果はありません。</span><span class="sxs-lookup"><span data-stu-id="56e2b-147">Password has no effect when encryption isn't supported by the native SQLite library.</span></span>

### <a name="foreign-keys"></a><span data-ttu-id="56e2b-148">外部キー</span><span class="sxs-lookup"><span data-stu-id="56e2b-148">Foreign Keys</span></span>

<span data-ttu-id="56e2b-149">外部キー制約を有効にするかどうかを示す値です。</span><span class="sxs-lookup"><span data-stu-id="56e2b-149">A value indicating whether to enable foreign key constraints.</span></span>

| <span data-ttu-id="56e2b-150">[値]</span><span class="sxs-lookup"><span data-stu-id="56e2b-150">Value</span></span>   | <span data-ttu-id="56e2b-151">説明</span><span class="sxs-lookup"><span data-stu-id="56e2b-151">Description</span></span>
| ------- | --- |
| <span data-ttu-id="56e2b-152">True</span><span class="sxs-lookup"><span data-stu-id="56e2b-152">True</span></span>    | <span data-ttu-id="56e2b-153">接続を開いた直後に `PRAGMA foreign_keys = 1` を送信します。</span><span class="sxs-lookup"><span data-stu-id="56e2b-153">Sends `PRAGMA foreign_keys = 1` immediately after opening the connection.</span></span>
| <span data-ttu-id="56e2b-154">False</span><span class="sxs-lookup"><span data-stu-id="56e2b-154">False</span></span>   | <span data-ttu-id="56e2b-155">接続を開いた直後に `PRAGMA foreign_keys = 0` を送信します。</span><span class="sxs-lookup"><span data-stu-id="56e2b-155">Sends `PRAGMA foreign_keys = 0` immediately after opening the connection.</span></span>
| <span data-ttu-id="56e2b-156">(空)</span><span class="sxs-lookup"><span data-stu-id="56e2b-156">(empty)</span></span> | <span data-ttu-id="56e2b-157">`PRAGMA foreign_keys` を送信しません。</span><span class="sxs-lookup"><span data-stu-id="56e2b-157">Doesn't send `PRAGMA foreign_keys`.</span></span> <span data-ttu-id="56e2b-158">既定値です。</span><span class="sxs-lookup"><span data-stu-id="56e2b-158">This is the default.</span></span> |

<span data-ttu-id="56e2b-159">e_sqlite3 の場合のように、ネイティブ SQLite ライブラリをコンパイルするために SQLITE_DEFAULT_FOREIGN_KEYS が使用された場合は、外部キーを有効にする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="56e2b-159">There's no need enable foreign keys if, like in e_sqlite3, SQLITE_DEFAULT_FOREIGN_KEYS was used to compile the native SQLite library.</span></span>

### <a name="recursive-triggers"></a><span data-ttu-id="56e2b-160">再帰トリガー</span><span class="sxs-lookup"><span data-stu-id="56e2b-160">Recursive triggers</span></span>

<span data-ttu-id="56e2b-161">再帰トリガーを有効にするかどうかを示す値です。</span><span class="sxs-lookup"><span data-stu-id="56e2b-161">A value that indicates whether to enable recursive triggers.</span></span>

| <span data-ttu-id="56e2b-162">[値]</span><span class="sxs-lookup"><span data-stu-id="56e2b-162">Value</span></span> | <span data-ttu-id="56e2b-163">説明</span><span class="sxs-lookup"><span data-stu-id="56e2b-163">Description</span></span>                                                                 |
| ----- | --------------------------------------------------------------------------- |
| <span data-ttu-id="56e2b-164">True</span><span class="sxs-lookup"><span data-stu-id="56e2b-164">True</span></span>  | <span data-ttu-id="56e2b-165">接続を開いた直後に `PRAGMA recursive_triggers` を送信します。</span><span class="sxs-lookup"><span data-stu-id="56e2b-165">Sends `PRAGMA recursive_triggers` immediately after opening the connection.</span></span> |
| <span data-ttu-id="56e2b-166">False</span><span class="sxs-lookup"><span data-stu-id="56e2b-166">False</span></span> | <span data-ttu-id="56e2b-167">`PRAGMA recursive_triggers` を送信しません。</span><span class="sxs-lookup"><span data-stu-id="56e2b-167">Doesn't send `PRAGMA recursive_triggers`.</span></span> <span data-ttu-id="56e2b-168">既定値です。</span><span class="sxs-lookup"><span data-stu-id="56e2b-168">This is the default.</span></span>              |

## <a name="connection-string-builder"></a><span data-ttu-id="56e2b-169">接続文字列ビルダー</span><span class="sxs-lookup"><span data-stu-id="56e2b-169">Connection string builder</span></span>

<span data-ttu-id="56e2b-170"><xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> は、厳密に型指定された方法で接続文字列を作成する際に使用できます。</span><span class="sxs-lookup"><span data-stu-id="56e2b-170">You can use <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> as a strongly typed way of creating connection strings.</span></span> <span data-ttu-id="56e2b-171">接続文字列のインジェクション攻撃を防止するためにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="56e2b-171">It can also be used to prevent connection string injection attacks.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="examples"></a><span data-ttu-id="56e2b-172">使用例</span><span class="sxs-lookup"><span data-stu-id="56e2b-172">Examples</span></span>

### <a name="basic"></a><span data-ttu-id="56e2b-173">Basic</span><span class="sxs-lookup"><span data-stu-id="56e2b-173">Basic</span></span>

<span data-ttu-id="56e2b-174">コンカレンシーを向上させるために共有キャッシュを使用する基本的な接続文字列。</span><span class="sxs-lookup"><span data-stu-id="56e2b-174">A basic connection string with a shared cache for improved concurrency.</span></span>

```connectionstring
Data Source=Application.db;Cache=Shared
```

### <a name="encrypted"></a><span data-ttu-id="56e2b-175">Encrypted</span><span class="sxs-lookup"><span data-stu-id="56e2b-175">Encrypted</span></span>

<span data-ttu-id="56e2b-176">暗号化されたデータベース。</span><span class="sxs-lookup"><span data-stu-id="56e2b-176">An encrypted database.</span></span>

```connectionstring
Data Source=Encrypted.db;Password=MyEncryptionKey
```

### <a name="read-only"></a><span data-ttu-id="56e2b-177">読み取り専用</span><span class="sxs-lookup"><span data-stu-id="56e2b-177">Read-only</span></span>

<span data-ttu-id="56e2b-178">アプリによって変更できない読み取り専用のデータベース。</span><span class="sxs-lookup"><span data-stu-id="56e2b-178">A read-only database that cannot be modified by the app.</span></span>

```connectionstring
Data Source=Reference.db;Mode=ReadOnly
```

### <a name="in-memory"></a><span data-ttu-id="56e2b-179">メモリ内</span><span class="sxs-lookup"><span data-stu-id="56e2b-179">In-memory</span></span>

<span data-ttu-id="56e2b-180">非公開のインメモリ データベース。</span><span class="sxs-lookup"><span data-stu-id="56e2b-180">A private, in-memory database.</span></span>

```connectionstring
Data Source=:memory:
```

### <a name="sharable-in-memory"></a><span data-ttu-id="56e2b-181">共有可能なインメモリ</span><span class="sxs-lookup"><span data-stu-id="56e2b-181">Sharable in-memory</span></span>

<span data-ttu-id="56e2b-182">*Sharable* という名前で識別される、共有可能なインメモリ データベース。</span><span class="sxs-lookup"><span data-stu-id="56e2b-182">A sharable, in-memory database identified by the name *Sharable*.</span></span>

```connectionstring
Data Source=Sharable;Mode=Memory;Cache=Shared
```

## <a name="see-also"></a><span data-ttu-id="56e2b-183">関連項目</span><span class="sxs-lookup"><span data-stu-id="56e2b-183">See also</span></span>

* [<span data-ttu-id="56e2b-184">ADO.NET での接続文字列</span><span class="sxs-lookup"><span data-stu-id="56e2b-184">Connection Strings in ADO.NET</span></span>](../../../framework/data/adonet/connection-strings.md)
* [<span data-ttu-id="56e2b-185">インメモリ データベース</span><span class="sxs-lookup"><span data-stu-id="56e2b-185">In-Memory databases</span></span>](in-memory-databases.md)
* [<span data-ttu-id="56e2b-186">トランザクション</span><span class="sxs-lookup"><span data-stu-id="56e2b-186">Transactions</span></span>](transactions.md)
