---
title: トランザクション
ms.date: 12/13/2019
description: トランザクションの使用方法について説明します。
ms.openlocfilehash: 4b72a1573a560ffd1bfd0f54d46ab3b135280976
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450382"
---
# <a name="transactions"></a><span data-ttu-id="3d1d3-103">トランザクション</span><span class="sxs-lookup"><span data-stu-id="3d1d3-103">Transactions</span></span>

<span data-ttu-id="3d1d3-104">トランザクションを使用すると、複数の SQL ステートメントを 1 つの作業単位にまとめて、1 つのアトミック単位としてデータベースにコミットできます。</span><span class="sxs-lookup"><span data-stu-id="3d1d3-104">Transactions let you group multiple SQL statements into a single unit of work that is committed to the database as one atomic unit.</span></span> <span data-ttu-id="3d1d3-105">トランザクション内のいずれかのステートメントが失敗した場合は、前のステートメントによって行われた変更をロールバックできます。</span><span class="sxs-lookup"><span data-stu-id="3d1d3-105">If any statement in the transaction fails, changes made by the previous statements can be rolled back.</span></span> <span data-ttu-id="3d1d3-106">トランザクションが開始されたときのデータベースの初期状態は保持されます。</span><span class="sxs-lookup"><span data-stu-id="3d1d3-106">The initial state of the database when the transaction was started is preserved.</span></span> <span data-ttu-id="3d1d3-107">トランザクションを使用すると、データベースに多数の変更を一度に加えるときの SQLite でのパフォーマンスを向上させることもできます。</span><span class="sxs-lookup"><span data-stu-id="3d1d3-107">Using a transaction can also improve performance on SQLite when making numerous changes to the database at once.</span></span>

## <a name="concurrency"></a><span data-ttu-id="3d1d3-108">コンカレンシー</span><span class="sxs-lookup"><span data-stu-id="3d1d3-108">Concurrency</span></span>

<span data-ttu-id="3d1d3-109">SQLite では、一度に 1 つのトランザクションだけがデータベース内で変更を保留にすることができます。</span><span class="sxs-lookup"><span data-stu-id="3d1d3-109">In SQLite, only one transaction is allowed to have changes pending in the database at a time.</span></span> <span data-ttu-id="3d1d3-110">このため、別のトランザクションの完了に時間がかかりすぎると、<xref:Microsoft.Data.Sqlite.SqliteCommand> の <xref:Microsoft.Data.Sqlite.SqliteConnection.BeginTransaction%2A> メソッドと `Execute` メソッドの呼び出しがタイムアウトになる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3d1d3-110">Because of this, calls to <xref:Microsoft.Data.Sqlite.SqliteConnection.BeginTransaction%2A> and the `Execute` methods on <xref:Microsoft.Data.Sqlite.SqliteCommand> may time out if another transaction takes too long to complete.</span></span>

<span data-ttu-id="3d1d3-111">ロック、再試行、タイムアウトの詳細については、「[データベース エラー](database-errors.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d1d3-111">For more information about locking, retries, and timeouts, see [Database errors](database-errors.md).</span></span>

## <a name="isolation-levels"></a><span data-ttu-id="3d1d3-112">分離レベル</span><span class="sxs-lookup"><span data-stu-id="3d1d3-112">Isolation levels</span></span>

<span data-ttu-id="3d1d3-113">SQLite では、トランザクションは既定で **serializable** です。</span><span class="sxs-lookup"><span data-stu-id="3d1d3-113">Transactions are **serializable** by default in SQLite.</span></span> <span data-ttu-id="3d1d3-114">この分離レベルを使用すると、トランザクション内で行われたすべての変更が完全に分離されることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="3d1d3-114">This isolation level guarantees that any changes made within a transaction are completely isolated.</span></span> <span data-ttu-id="3d1d3-115">トランザクションの外部で実行される他のステートメントは、そのトランザクションの変更の影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="3d1d3-115">Other statements executed outside of the transaction aren't affected by the transaction's changes.</span></span>

<span data-ttu-id="3d1d3-116">SQLite では、共有キャッシュの使用時には、**read uncommitted** もサポートされます。</span><span class="sxs-lookup"><span data-stu-id="3d1d3-116">SQLite also supports **read uncommitted** when using a shared cache.</span></span> <span data-ttu-id="3d1d3-117">このレベルでは、ダーティ リード、反復不能読み取り、ファントムが可能です。</span><span class="sxs-lookup"><span data-stu-id="3d1d3-117">This level allows dirty reads, nonrepeatable reads, and phantoms:</span></span>

- <span data-ttu-id="3d1d3-118">"*ダーティ リード*" は、1 つのトランザクション内で保留中の変更がそのトランザクションの外部でクエリによって返される一方で、そのトランザクション内の変更がロールバックされるときに生じます。</span><span class="sxs-lookup"><span data-stu-id="3d1d3-118">A *dirty read* occurs when changes pending in one transaction are returned by a query outside of the transaction, but the changes in the transaction are rolled back.</span></span> <span data-ttu-id="3d1d3-119">結果には、実際にはデータベースにコミットされなかったデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3d1d3-119">The results contain data that was never actually committed to the database.</span></span>

- <span data-ttu-id="3d1d3-120">"*反復不能読み取り*" は、トランザクションで同じ行に 2 回クエリが実行され、一方、、その 2 回のクエリの間に別のトランザクションによってその行が変更されたことが原因で、結果が異なっているときに生じます。</span><span class="sxs-lookup"><span data-stu-id="3d1d3-120">A *nonrepeatable read* occurs when a transaction queries same row twice, but the results are different because it was changed between the two queries by another transaction.</span></span>

- <span data-ttu-id="3d1d3-121">"*ファントム*" は、トランザクション中にクエリの where 句に合わせて変更または追加された行です。</span><span class="sxs-lookup"><span data-stu-id="3d1d3-121">*Phantoms* are rows that get changed or added to meet the where clause of a query during a transaction.</span></span> <span data-ttu-id="3d1d3-122">同じクエリが同じトランザクション内で 2 回実行されることが許可されている場合、そのようなクエリで異なる行が返されることがあります。</span><span class="sxs-lookup"><span data-stu-id="3d1d3-122">If allowed, the same query could return different rows when executed twice in the same transaction.</span></span>

<span data-ttu-id="3d1d3-123">Microsoft.Data.Sqlite では、<xref:Microsoft.Data.Sqlite.SqliteConnection.BeginTransaction%2A> に渡される IsolationLevel は最小レベルとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="3d1d3-123">Microsoft.Data.Sqlite treats the IsolationLevel passed to <xref:Microsoft.Data.Sqlite.SqliteConnection.BeginTransaction%2A> as a minimum level.</span></span> <span data-ttu-id="3d1d3-124">実際の分離レベルは、read uncommitted または serializable に昇格されます。</span><span class="sxs-lookup"><span data-stu-id="3d1d3-124">The actual isolation level will be promoted to either read uncommitted or serializable.</span></span>

<span data-ttu-id="3d1d3-125">次のコードは、ダーティ リードをシミュレートしています。</span><span class="sxs-lookup"><span data-stu-id="3d1d3-125">The following code simulates a dirty read.</span></span> <span data-ttu-id="3d1d3-126">接続文字列には `Cache=Shared` を含める必要があるので注意してください。</span><span class="sxs-lookup"><span data-stu-id="3d1d3-126">Note, the connection string must include `Cache=Shared`.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DirtyReadSample/Program.cs?name=snippet_DirtyRead)]
