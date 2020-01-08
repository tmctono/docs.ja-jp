---
title: トランザクション
ms.date: 12/13/2019
description: トランザクションの使用方法について説明します。
ms.openlocfilehash: 4b72a1573a560ffd1bfd0f54d46ab3b135280976
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450382"
---
# <a name="transactions"></a><span data-ttu-id="a3639-103">トランザクション</span><span class="sxs-lookup"><span data-stu-id="a3639-103">Transactions</span></span>

<span data-ttu-id="a3639-104">トランザクションを使用すると、複数の SQL ステートメントをグループ化し、1つのアトミックユニットとしてデータベースにコミットされる1つの作業単位にすることができます。</span><span class="sxs-lookup"><span data-stu-id="a3639-104">Transactions let you group multiple SQL statements into a single unit of work that is committed to the database as one atomic unit.</span></span> <span data-ttu-id="a3639-105">トランザクション内のいずれかのステートメントが失敗した場合は、前のステートメントによって行われた変更をロールバックできます。</span><span class="sxs-lookup"><span data-stu-id="a3639-105">If any statement in the transaction fails, changes made by the previous statements can be rolled back.</span></span> <span data-ttu-id="a3639-106">トランザクションが開始されたときのデータベースの初期状態は保持されます。</span><span class="sxs-lookup"><span data-stu-id="a3639-106">The initial state of the database when the transaction was started is preserved.</span></span> <span data-ttu-id="a3639-107">トランザクションを使用すると、一度にデータベースに多数の変更を加えたときに SQLite のパフォーマンスを向上させることもできます。</span><span class="sxs-lookup"><span data-stu-id="a3639-107">Using a transaction can also improve performance on SQLite when making numerous changes to the database at once.</span></span>

## <a name="concurrency"></a><span data-ttu-id="a3639-108">コンカレンシー</span><span class="sxs-lookup"><span data-stu-id="a3639-108">Concurrency</span></span>

<span data-ttu-id="a3639-109">SQLite では、一度に1つのトランザクションだけがデータベースで保留中の変更を保持できます。</span><span class="sxs-lookup"><span data-stu-id="a3639-109">In SQLite, only one transaction is allowed to have changes pending in the database at a time.</span></span> <span data-ttu-id="a3639-110">このため、別のトランザクションの完了に時間がかかりすぎると、<xref:Microsoft.Data.Sqlite.SqliteConnection.BeginTransaction%2A> と <xref:Microsoft.Data.Sqlite.SqliteCommand> の `Execute` メソッドの呼び出しがタイムアウトする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a3639-110">Because of this, calls to <xref:Microsoft.Data.Sqlite.SqliteConnection.BeginTransaction%2A> and the `Execute` methods on <xref:Microsoft.Data.Sqlite.SqliteCommand> may time out if another transaction takes too long to complete.</span></span>

<span data-ttu-id="a3639-111">ロック、再試行、タイムアウトの詳細については、「[データベースエラー](database-errors.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3639-111">For more information about locking, retries, and timeouts, see [Database errors](database-errors.md).</span></span>

## <a name="isolation-levels"></a><span data-ttu-id="a3639-112">分離レベル</span><span class="sxs-lookup"><span data-stu-id="a3639-112">Isolation levels</span></span>

<span data-ttu-id="a3639-113">SQLite では、トランザクションは既定で**シリアル化**可能です。</span><span class="sxs-lookup"><span data-stu-id="a3639-113">Transactions are **serializable** by default in SQLite.</span></span> <span data-ttu-id="a3639-114">この分離レベルは、トランザクション内で行われたすべての変更が完全に分離されることを保証します。</span><span class="sxs-lookup"><span data-stu-id="a3639-114">This isolation level guarantees that any changes made within a transaction are completely isolated.</span></span> <span data-ttu-id="a3639-115">トランザクションの外部で実行される他のステートメントは、トランザクションの変更の影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="a3639-115">Other statements executed outside of the transaction aren't affected by the transaction's changes.</span></span>

<span data-ttu-id="a3639-116">SQLite は、共有キャッシュを使用しているときに、 **read 未確定**をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a3639-116">SQLite also supports **read uncommitted** when using a shared cache.</span></span> <span data-ttu-id="a3639-117">このレベルでは、ダーティリード、反復不能読み取り、およびファントムが許可されます。</span><span class="sxs-lookup"><span data-stu-id="a3639-117">This level allows dirty reads, nonrepeatable reads, and phantoms:</span></span>

- <span data-ttu-id="a3639-118">*ダーティリード*は、あるトランザクションで保留中の変更がトランザクションの外部のクエリによって返されたが、トランザクションの変更がロールバックされた場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="a3639-118">A *dirty read* occurs when changes pending in one transaction are returned by a query outside of the transaction, but the changes in the transaction are rolled back.</span></span> <span data-ttu-id="a3639-119">結果には、実際にはデータベースにコミットされていないデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a3639-119">The results contain data that was never actually committed to the database.</span></span>

- <span data-ttu-id="a3639-120">*反復不能読み取り*は、トランザクションが同じ行を2回クエリする場合に発生しますが、結果が異なるのは、2つのクエリの間で別のトランザクションによって変更されたためです。</span><span class="sxs-lookup"><span data-stu-id="a3639-120">A *nonrepeatable read* occurs when a transaction queries same row twice, but the results are different because it was changed between the two queries by another transaction.</span></span>

- <span data-ttu-id="a3639-121">*ファントム*は、トランザクション中にクエリの where 句を満たすために変更または追加される行です。</span><span class="sxs-lookup"><span data-stu-id="a3639-121">*Phantoms* are rows that get changed or added to meet the where clause of a query during a transaction.</span></span> <span data-ttu-id="a3639-122">許可されている場合、同じクエリで同じトランザクション内で2回実行すると、異なる行が返される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a3639-122">If allowed, the same query could return different rows when executed twice in the same transaction.</span></span>

<span data-ttu-id="a3639-123"><xref:Microsoft.Data.Sqlite.SqliteConnection.BeginTransaction%2A> に渡される IsolationLevel は、最小レベルとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="a3639-123">Microsoft.Data.Sqlite treats the IsolationLevel passed to <xref:Microsoft.Data.Sqlite.SqliteConnection.BeginTransaction%2A> as a minimum level.</span></span> <span data-ttu-id="a3639-124">実際の分離レベルは、read 未確定または serializable に昇格されます。</span><span class="sxs-lookup"><span data-stu-id="a3639-124">The actual isolation level will be promoted to either read uncommitted or serializable.</span></span>

<span data-ttu-id="a3639-125">次のコードは、ダーティリードをシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="a3639-125">The following code simulates a dirty read.</span></span> <span data-ttu-id="a3639-126">接続文字列には `Cache=Shared`を含める必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a3639-126">Note, the connection string must include `Cache=Shared`.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DirtyReadSample/Program.cs?name=snippet_DirtyRead)]
