---
title: データベース エラー
ms.date: 12/13/2019
description: データベースのエラーと再試行がライブラリでどのように処理されるかについて説明します。
ms.openlocfilehash: 9a613b6f94a89dc40e627c14f46836be77080035
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450490"
---
# <a name="database-errors"></a><span data-ttu-id="c4437-103">データベース エラー</span><span class="sxs-lookup"><span data-stu-id="c4437-103">Database errors</span></span>

<span data-ttu-id="c4437-104">SQLite エラーが発生すると、<xref:Microsoft.Data.Sqlite.SqliteException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="c4437-104"><xref:Microsoft.Data.Sqlite.SqliteException> is thrown when a SQLite error is encountered.</span></span> <span data-ttu-id="c4437-105">メッセージは SQLite によって発行されます。</span><span class="sxs-lookup"><span data-stu-id="c4437-105">The message is provided by SQLite.</span></span> <span data-ttu-id="c4437-106">`SqliteErrorCode` と `SqliteExtendedErrorCode` プロパティには、エラーの SQLite [結果コード](https://www.sqlite.org/rescode.html)が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c4437-106">The `SqliteErrorCode` and `SqliteExtendedErrorCode` properties contain the SQLite [result code](https://www.sqlite.org/rescode.html) of the error.</span></span>

<span data-ttu-id="c4437-107">エラーが発生する可能性があるのは、Microsoft.Data.Sqlite でネイティブ SQLite ライブラリとの対話が行われているときです。</span><span class="sxs-lookup"><span data-stu-id="c4437-107">Errors may be encountered any time the Microsoft.Data.Sqlite interacts with the native SQLite library.</span></span> <span data-ttu-id="c4437-108">次の一覧に、エラーが発生する可能性がある一般的なシナリオを示します。</span><span class="sxs-lookup"><span data-stu-id="c4437-108">The following list shows the common scenarios where errors can occur:</span></span>

* <span data-ttu-id="c4437-109">接続のオープン。</span><span class="sxs-lookup"><span data-stu-id="c4437-109">Opening a connection.</span></span>
* <span data-ttu-id="c4437-110">トランザクションの開始。</span><span class="sxs-lookup"><span data-stu-id="c4437-110">Beginning a transaction.</span></span>
* <span data-ttu-id="c4437-111">コマンドの実行。</span><span class="sxs-lookup"><span data-stu-id="c4437-111">Executing a command.</span></span>
* <span data-ttu-id="c4437-112"><xref:Microsoft.Data.Sqlite.SqliteDataReader.NextResult%2A> の呼び出し</span><span class="sxs-lookup"><span data-stu-id="c4437-112">Calling <xref:Microsoft.Data.Sqlite.SqliteDataReader.NextResult%2A>.</span></span>

<span data-ttu-id="c4437-113">これらのエラーがアプリによってどのように処理されるかを慎重に検討してください。</span><span class="sxs-lookup"><span data-stu-id="c4437-113">Consider carefully how your app will handle these errors.</span></span>

## <a name="locking-retries-and-timeouts"></a><span data-ttu-id="c4437-114">ロック、再試行、タイムアウト</span><span class="sxs-lookup"><span data-stu-id="c4437-114">Locking, retries, and timeouts</span></span>

<span data-ttu-id="c4437-115">SQLite では、テーブルとデータベース ファイルのロックは積極的に行われます。</span><span class="sxs-lookup"><span data-stu-id="c4437-115">SQLite is aggressive when it comes to locking tables and database files.</span></span> <span data-ttu-id="c4437-116">アプリでデータベースへの同時アクセスが有効になっている場合、ビジー状態とロック状態のエラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c4437-116">If your app enables any concurrent database access, you'll likely encounter busy and locked errors.</span></span> <span data-ttu-id="c4437-117">[共有キャッシュ](connection-strings.md#cache) と[先行書き込みログ](async.md)を使用することで、エラーの多くを低減できます。</span><span class="sxs-lookup"><span data-stu-id="c4437-117">You can mitigate many errors by using a [shared cache](connection-strings.md#cache) and [write-ahead logging](async.md).</span></span>

<span data-ttu-id="c4437-118">Microsoft.Data.Sqlite では、ビジー状態またはロック状態のエラーが発生すると、成功するかコマンドがタイムアウトになるまで自動的に再試行されます。</span><span class="sxs-lookup"><span data-stu-id="c4437-118">Whenever Microsoft.Data.Sqlite encounters a busy or locked error, it will automatically retry until it succeeds or the command timeout is reached.</span></span>

<span data-ttu-id="c4437-119"><xref:Microsoft.Data.Sqlite.SqliteCommand.CommandTimeout%2A> を設定すると、コマンドのタイムアウトを延長できます。</span><span class="sxs-lookup"><span data-stu-id="c4437-119">You can increase the timeout of command by setting <xref:Microsoft.Data.Sqlite.SqliteCommand.CommandTimeout%2A>.</span></span> <span data-ttu-id="c4437-120">既定のタイムアウトは 30 秒です。</span><span class="sxs-lookup"><span data-stu-id="c4437-120">The default timeout is 30 seconds.</span></span> <span data-ttu-id="c4437-121">値 `0` は、タイムアウトがないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="c4437-121">A value of `0` means no timeout.</span></span>

```csharp
// Retry for 60 seconds while locked
command.CommandTimeout = 60;
```

<span data-ttu-id="c4437-122">Microsoft.Data.Sqlite では、暗黙的なコマンド オブジェクトの作成が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c4437-122">Microsoft.Data.Sqlite sometimes needs to create an implicit command object.</span></span> <span data-ttu-id="c4437-123">たとえば、BeginTransaction 中です。</span><span class="sxs-lookup"><span data-stu-id="c4437-123">For example, during BeginTransaction.</span></span> <span data-ttu-id="c4437-124">これらのコマンドのタイムアウトを設定するには、<xref:Microsoft.Data.Sqlite.SqliteConnection.DefaultTimeout%2A> を使用します。</span><span class="sxs-lookup"><span data-stu-id="c4437-124">To set the timeout for these commands, use <xref:Microsoft.Data.Sqlite.SqliteConnection.DefaultTimeout%2A>.</span></span>

```csharp
// Set the default timeout of all commands on this connection
connection.DefaultTimeout = 60;
```

## <a name="see-also"></a><span data-ttu-id="c4437-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="c4437-125">See also</span></span>

* [<span data-ttu-id="c4437-126">SQLite エラー コード</span><span class="sxs-lookup"><span data-stu-id="c4437-126">SQLite Error Codes</span></span>](https://www.sqlite.org/rescode.html)
* [<span data-ttu-id="c4437-127">SQLite でのファイルのロック</span><span class="sxs-lookup"><span data-stu-id="c4437-127">File Locking In SQLite</span></span>](https://www.sqlite.org/lockingv3.html)
* [<span data-ttu-id="c4437-128">共有キャッシュ モード</span><span class="sxs-lookup"><span data-stu-id="c4437-128">Shared-Cache Mode</span></span>](https://www.sqlite.org/sharedcache.html)
* [<span data-ttu-id="c4437-129">先行書き込みログ</span><span class="sxs-lookup"><span data-stu-id="c4437-129">Write-Ahead Logging</span></span>](https://www.sqlite.org/wal.html)
