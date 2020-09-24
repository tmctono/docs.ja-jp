---
title: トランザクション
ms.date: 09/08/2020
description: トランザクションの使用方法について説明します。
ms.openlocfilehash: 50c4cd1023eac892cafc3ae4395e9168bd8e9f36
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2020
ms.locfileid: "90678863"
---
# <a name="transactions"></a><span data-ttu-id="1ead1-103">トランザクション</span><span class="sxs-lookup"><span data-stu-id="1ead1-103">Transactions</span></span>

<span data-ttu-id="1ead1-104">トランザクションを使用すると、複数の SQL ステートメントを 1 つの作業単位にまとめて、1 つのアトミック単位としてデータベースにコミットできます。</span><span class="sxs-lookup"><span data-stu-id="1ead1-104">Transactions let you group multiple SQL statements into a single unit of work that is committed to the database as one atomic unit.</span></span> <span data-ttu-id="1ead1-105">トランザクション内のいずれかのステートメントが失敗した場合は、前のステートメントによって行われた変更をロールバックできます。</span><span class="sxs-lookup"><span data-stu-id="1ead1-105">If any statement in the transaction fails, changes made by the previous statements can be rolled back.</span></span> <span data-ttu-id="1ead1-106">トランザクションが開始されたときのデータベースの初期状態は保持されます。</span><span class="sxs-lookup"><span data-stu-id="1ead1-106">The initial state of the database when the transaction was started is preserved.</span></span> <span data-ttu-id="1ead1-107">トランザクションを使用すると、データベースに多数の変更を一度に加えるときの SQLite でのパフォーマンスを向上させることもできます。</span><span class="sxs-lookup"><span data-stu-id="1ead1-107">Using a transaction can also improve performance on SQLite when making numerous changes to the database at once.</span></span>

## <a name="concurrency"></a><span data-ttu-id="1ead1-108">コンカレンシー</span><span class="sxs-lookup"><span data-stu-id="1ead1-108">Concurrency</span></span>

<span data-ttu-id="1ead1-109">SQLite では、一度に 1 つのトランザクションだけがデータベース内で変更を保留にすることができます。</span><span class="sxs-lookup"><span data-stu-id="1ead1-109">In SQLite, only one transaction is allowed to have changes pending in the database at a time.</span></span> <span data-ttu-id="1ead1-110">このため、別のトランザクションの完了に時間がかかりすぎると、<xref:Microsoft.Data.Sqlite.SqliteCommand> の <xref:Microsoft.Data.Sqlite.SqliteConnection.BeginTransaction%2A> メソッドと `Execute` メソッドの呼び出しがタイムアウトになる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1ead1-110">Because of this, calls to <xref:Microsoft.Data.Sqlite.SqliteConnection.BeginTransaction%2A> and the `Execute` methods on <xref:Microsoft.Data.Sqlite.SqliteCommand> may time out if another transaction takes too long to complete.</span></span>

<span data-ttu-id="1ead1-111">ロック、再試行、タイムアウトの詳細については、「[データベース エラー](database-errors.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ead1-111">For more information about locking, retries, and timeouts, see [Database errors](database-errors.md).</span></span>

## <a name="isolation-levels"></a><span data-ttu-id="1ead1-112">分離レベル</span><span class="sxs-lookup"><span data-stu-id="1ead1-112">Isolation levels</span></span>

<span data-ttu-id="1ead1-113">SQLite では、トランザクションは既定で **serializable** です。</span><span class="sxs-lookup"><span data-stu-id="1ead1-113">Transactions are **serializable** by default in SQLite.</span></span> <span data-ttu-id="1ead1-114">この分離レベルを使用すると、トランザクション内で行われたすべての変更が完全に分離されることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="1ead1-114">This isolation level guarantees that any changes made within a transaction are completely isolated.</span></span> <span data-ttu-id="1ead1-115">トランザクションの外部で実行される他のステートメントは、そのトランザクションの変更の影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="1ead1-115">Other statements executed outside of the transaction aren't affected by the transaction's changes.</span></span>

<span data-ttu-id="1ead1-116">SQLite では、共有キャッシュの使用時には、**read uncommitted** もサポートされます。</span><span class="sxs-lookup"><span data-stu-id="1ead1-116">SQLite also supports **read uncommitted** when using a shared cache.</span></span> <span data-ttu-id="1ead1-117">このレベルでは、ダーティ リード、反復不能読み取り、ファントムが可能です。</span><span class="sxs-lookup"><span data-stu-id="1ead1-117">This level allows dirty reads, nonrepeatable reads, and phantoms:</span></span>

- <span data-ttu-id="1ead1-118">"*ダーティ リード*" は、1 つのトランザクション内で保留中の変更がそのトランザクションの外部でクエリによって返される一方で、そのトランザクション内の変更がロールバックされるときに生じます。</span><span class="sxs-lookup"><span data-stu-id="1ead1-118">A *dirty read* occurs when changes pending in one transaction are returned by a query outside of the transaction, but the changes in the transaction are rolled back.</span></span> <span data-ttu-id="1ead1-119">結果には、実際にはデータベースにコミットされなかったデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1ead1-119">The results contain data that was never actually committed to the database.</span></span>

- <span data-ttu-id="1ead1-120">"*反復不能読み取り*" は、トランザクションで同じ行に 2 回クエリが実行され、一方、、その 2 回のクエリの間に別のトランザクションによってその行が変更されたことが原因で、結果が異なっているときに生じます。</span><span class="sxs-lookup"><span data-stu-id="1ead1-120">A *nonrepeatable read* occurs when a transaction queries same row twice, but the results are different because it was changed between the two queries by another transaction.</span></span>

- <span data-ttu-id="1ead1-121">"*ファントム*" は、トランザクション中にクエリの where 句に合わせて変更または追加された行です。</span><span class="sxs-lookup"><span data-stu-id="1ead1-121">*Phantoms* are rows that get changed or added to meet the where clause of a query during a transaction.</span></span> <span data-ttu-id="1ead1-122">同じクエリが同じトランザクション内で 2 回実行されることが許可されている場合、そのようなクエリで異なる行が返されることがあります。</span><span class="sxs-lookup"><span data-stu-id="1ead1-122">If allowed, the same query could return different rows when executed twice in the same transaction.</span></span>

<span data-ttu-id="1ead1-123">Microsoft.Data.Sqlite では、<xref:Microsoft.Data.Sqlite.SqliteConnection.BeginTransaction%2A> に渡される IsolationLevel は最小レベルとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="1ead1-123">Microsoft.Data.Sqlite treats the IsolationLevel passed to <xref:Microsoft.Data.Sqlite.SqliteConnection.BeginTransaction%2A> as a minimum level.</span></span> <span data-ttu-id="1ead1-124">実際の分離レベルは、read uncommitted または serializable に昇格されます。</span><span class="sxs-lookup"><span data-stu-id="1ead1-124">The actual isolation level will be promoted to either read uncommitted or serializable.</span></span>

<span data-ttu-id="1ead1-125">次のコードは、ダーティ リードをシミュレートしています。</span><span class="sxs-lookup"><span data-stu-id="1ead1-125">The following code simulates a dirty read.</span></span> <span data-ttu-id="1ead1-126">接続文字列には `Cache=Shared` を含める必要があるので注意してください。</span><span class="sxs-lookup"><span data-stu-id="1ead1-126">Note, the connection string must include `Cache=Shared`.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DirtyReadSample/Program.cs?name=snippet_DirtyRead)]

## <a name="deferred-transactions"></a><span data-ttu-id="1ead1-127">遅延トランザクション</span><span class="sxs-lookup"><span data-stu-id="1ead1-127">Deferred transactions</span></span>

<span data-ttu-id="1ead1-128">Microsoft. Data. Sqlite バージョン 5.0 以降では、トランザクションを遅延させることができます。</span><span class="sxs-lookup"><span data-stu-id="1ead1-128">Starting with Microsoft.Data.Sqlite version 5.0, transactions can be deferred.</span></span> <span data-ttu-id="1ead1-129">これにより、最初のコマンドが実行されるまで、データベース内の実際のトランザクションの作成が遅延されます。</span><span class="sxs-lookup"><span data-stu-id="1ead1-129">This defers the creation of the actual transaction in the database until the first command is executed.</span></span> <span data-ttu-id="1ead1-130">また、必要に応じて、トランザクションがそのコマンドによって、読み取りトランザクションから書き込みトランザクションに徐々にアップグレードされるようにします。</span><span class="sxs-lookup"><span data-stu-id="1ead1-130">It also causes the transaction to gradually upgrade from a read transaction to a write transaction as needed by its commands.</span></span> <span data-ttu-id="1ead1-131">これは、トランザクション中にデータベースへの同時アクセスを有効にする場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="1ead1-131">This can be useful for enabling concurrent access to the database during the transaction.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DeferredTransactionSample/Program.cs?name=snippet_DeferredTransaction)]

> [!WARNING]
> <span data-ttu-id="1ead1-132">データベースがロックされているときに、遅延トランザクション内のコマンドによって、トランザクションが読み取りトランザクションから書き込みトランザクションにアップグレードされると、そのコマンドは失敗することがあります。</span><span class="sxs-lookup"><span data-stu-id="1ead1-132">Commands inside a deferred transaction can fail if they cause the transaction to be upgraded from a read transaction to a write transaction while the database is locked.</span></span> <span data-ttu-id="1ead1-133">この場合、アプリケーションで、トランザクション全体の再試行を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ead1-133">When this happens, the application will need to retry the entire transaction.</span></span>
