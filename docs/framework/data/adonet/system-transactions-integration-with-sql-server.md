---
title: SQL Server と System.Transactions の統合
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b555544e-7abb-4814-859b-ab9cdd7d8716
ms.openlocfilehash: 42007dafbdc9f61b9fc0776e0aaa2987551b704a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174239"
---
# <a name="systemtransactions-integration-with-sql-server"></a><span data-ttu-id="a114c-102">SQL Server と System.Transactions の統合</span><span class="sxs-lookup"><span data-stu-id="a114c-102">System.Transactions Integration with SQL Server</span></span>
<span data-ttu-id="a114c-103">NET Framework バージョン 2.0 では、名前空間を介してアクセスできる<xref:System.Transactions>トランザクション フレームワークが導入されました。</span><span class="sxs-lookup"><span data-stu-id="a114c-103">The .NET Framework version 2.0 introduced a transaction framework that can be accessed through the <xref:System.Transactions> namespace.</span></span> <span data-ttu-id="a114c-104">このフレームワークは、ADO.NETを含む .NET Framework に完全に統合された方法でトランザクションを公開します。</span><span class="sxs-lookup"><span data-stu-id="a114c-104">This framework exposes transactions in a way that is fully integrated in the .NET Framework, including ADO.NET.</span></span>  
  
 <span data-ttu-id="a114c-105">プログラミング機能の強化に加えて、ADO.NET<xref:System.Transactions>連携してトランザクションを操作するときに最適化を調整できます。</span><span class="sxs-lookup"><span data-stu-id="a114c-105">In addition to the programmability enhancements, <xref:System.Transactions> and ADO.NET can work together to coordinate optimizations when you work with transactions.</span></span> <span data-ttu-id="a114c-106">昇格可能なトランザクションとは、必要に応じて完全な分散トランザクションに自動的に昇格する、軽量の (ローカル) トランザクションです。</span><span class="sxs-lookup"><span data-stu-id="a114c-106">A promotable transaction is a lightweight (local) transaction that can be automatically promoted to a fully distributed transaction on an as-needed basis.</span></span>  
  
 <span data-ttu-id="a114c-107">ADO.NET 2.0 以降<xref:System.Data.SqlClient>では、SQL Server で作業する場合の昇格可能なトランザクションがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="a114c-107">Starting with ADO.NET 2.0, <xref:System.Data.SqlClient> supports promotable transactions when you work with SQL Server.</span></span> <span data-ttu-id="a114c-108">昇格可能なトランザクションは、必要な場合以外、分散トランザクションのオーバーヘッドの増加を引き起こすことはありません。</span><span class="sxs-lookup"><span data-stu-id="a114c-108">A promotable transaction does not invoke the added overhead of a distributed transaction unless the added overhead is required.</span></span> <span data-ttu-id="a114c-109">昇格可能なトランザクションは自動的に行われ、開発者の介入は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="a114c-109">Promotable transactions are automatic and require no intervention from the developer.</span></span>  
  
 <span data-ttu-id="a114c-110">昇格可能なトランザクションは、SQL Server の .NET Framework データ プロバイダ`SqlClient`( ) を SQL Server で使用する場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a114c-110">Promotable transactions are only available when you use the .NET Framework Data Provider for SQL Server (`SqlClient`) with SQL Server.</span></span>  
  
## <a name="creating-promotable-transactions"></a><span data-ttu-id="a114c-111">昇格可能なトランザクションの作成</span><span class="sxs-lookup"><span data-stu-id="a114c-111">Creating Promotable Transactions</span></span>  
 <span data-ttu-id="a114c-112">SQL Server の .NET フレームワーク プロバイダーは、.NET Framework<xref:System.Transactions>名前空間のクラスを通じて処理される、昇格可能なトランザクションのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="a114c-112">The .NET Framework Provider for SQL Server provides support for promotable transactions, which are handled through the classes in the .NET Framework <xref:System.Transactions> namespace.</span></span> <span data-ttu-id="a114c-113">昇格可能なトランザクションでは、必要が生じるまで分散トランザクションの作成を延期することで、分散トランザクションが最適化されます。</span><span class="sxs-lookup"><span data-stu-id="a114c-113">Promotable transactions optimize distributed transactions by deferring creating a distributed transaction until it is needed.</span></span> <span data-ttu-id="a114c-114">必要なリソース マネージャーが 1 つだけである場合は、分散トランザクションは発生しません。</span><span class="sxs-lookup"><span data-stu-id="a114c-114">If only one resource manager is required, no distributed transaction occurs.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a114c-115">部分信頼のシナリオで分散トランザクションに昇格するには、 <xref:System.Transactions.DistributedTransactionPermission> が必要です。</span><span class="sxs-lookup"><span data-stu-id="a114c-115">In a partially trusted scenario, the <xref:System.Transactions.DistributedTransactionPermission> is required when a transaction is promoted to a distributed transaction.</span></span>  
  
## <a name="promotable-transaction-scenarios"></a><span data-ttu-id="a114c-116">昇格可能なトランザクションのシナリオ</span><span class="sxs-lookup"><span data-stu-id="a114c-116">Promotable Transaction Scenarios</span></span>  
 <span data-ttu-id="a114c-117">分散トランザクションは一般的にシステム リソースを大量に消費するため、トランザクションでアクセスされるすべてのリソース マネージャーを統合する、Microsoft Distributed Transaction Coordinator (MS DTC) で管理されます。</span><span class="sxs-lookup"><span data-stu-id="a114c-117">Distributed transactions typically consume significant system resources, being managed by Microsoft Distributed Transaction Coordinator (MS DTC), which integrates all the resource managers accessed in the transaction.</span></span> <span data-ttu-id="a114c-118">昇格可能なトランザクションは、作業を<xref:System.Transactions>単純な SQL Server トランザクションに効果的に委任する特殊な形式のトランザクションです。</span><span class="sxs-lookup"><span data-stu-id="a114c-118">A promotable transaction is a special form of a <xref:System.Transactions> transaction that effectively delegates the work to a simple SQL Server transaction.</span></span> <span data-ttu-id="a114c-119"><xref:System.Transactions>、、<xref:System.Data.SqlClient>および SQL Server は、トランザクションの処理に関連する作業を調整し、必要に応じてトランザクションを完全な分散トランザクションに昇格させます。</span><span class="sxs-lookup"><span data-stu-id="a114c-119"><xref:System.Transactions>, <xref:System.Data.SqlClient>, and SQL Server coordinate the work involved in handling the transaction, promoting it to a full distributed transaction as needed.</span></span>  
  
 <span data-ttu-id="a114c-120">昇格可能なトランザクションを使用する利点は、アクティブな <xref:System.Transactions.TransactionScope> トランザクションによって接続が開かれ、その他の接続が開いていない場合に、完全な分散トランザクションによるオーバーヘッドが生じることなく、トランザクションが軽量なトランザクションとしてコミットされることです。</span><span class="sxs-lookup"><span data-stu-id="a114c-120">The benefit of using promotable transactions is that when a connection is opened by using an active <xref:System.Transactions.TransactionScope> transaction, and no other connections are opened, the transaction commits as a lightweight transaction, instead of incurring the additional overhead of a full distributed transaction.</span></span>  
  
### <a name="connection-string-keywords"></a><span data-ttu-id="a114c-121">接続文字列キーワード</span><span class="sxs-lookup"><span data-stu-id="a114c-121">Connection String Keywords</span></span>  
 <span data-ttu-id="a114c-122"><xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> プロパティではキーワード `Enlist`がサポートされており、 <xref:System.Data.SqlClient> によってトランザクションのコンテキストが検出され、分散トランザクションに接続が自動的に参加するかどうかが示されます。</span><span class="sxs-lookup"><span data-stu-id="a114c-122">The <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> property supports a keyword, `Enlist`, which indicates whether <xref:System.Data.SqlClient> will detect transactional contexts and automatically enlist the connection in a distributed transaction.</span></span> <span data-ttu-id="a114c-123">`Enlist=true`である場合は、開いているスレッドの現在のトランザクション コンテキストに接続が自動的に参加します。</span><span class="sxs-lookup"><span data-stu-id="a114c-123">If `Enlist=true`, the connection is automatically enlisted in the opening thread's current transaction context.</span></span> <span data-ttu-id="a114c-124">`Enlist=false`である場合、 `SqlClient` 接続は分散トランザクションとは対話しません。</span><span class="sxs-lookup"><span data-stu-id="a114c-124">If `Enlist=false`, the `SqlClient` connection does not interact with a distributed transaction.</span></span> <span data-ttu-id="a114c-125">`Enlist` の既定値は true です。</span><span class="sxs-lookup"><span data-stu-id="a114c-125">The default value for `Enlist` is true.</span></span> <span data-ttu-id="a114c-126">`Enlist` が接続文字列で指定されていない場合、接続が開いたときに分散トランザクションがあればそれに自動的に参加します。</span><span class="sxs-lookup"><span data-stu-id="a114c-126">If `Enlist` is not specified in the connection string, the connection is automatically enlisted in a distributed transaction if one is detected when the connection is opened.</span></span>  
  
 <span data-ttu-id="a114c-127">参加する `Transaction Binding` トランザクションと接続の関連付けは、 <xref:System.Data.SqlClient.SqlConnection> 接続文字列の `System.Transactions` キーワードによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="a114c-127">The `Transaction Binding` keywords in a <xref:System.Data.SqlClient.SqlConnection> connection string control the connection's association with an enlisted `System.Transactions` transaction.</span></span> <span data-ttu-id="a114c-128"><xref:System.Data.SqlClient.SqlConnectionStringBuilder.TransactionBinding%2A> の <xref:System.Data.SqlClient.SqlConnectionStringBuilder>プロパティを介して利用することもできます。</span><span class="sxs-lookup"><span data-stu-id="a114c-128">It is also available through the <xref:System.Data.SqlClient.SqlConnectionStringBuilder.TransactionBinding%2A> property of a <xref:System.Data.SqlClient.SqlConnectionStringBuilder>.</span></span>  
  
 <span data-ttu-id="a114c-129">次の表で使用可能な値について説明します。</span><span class="sxs-lookup"><span data-stu-id="a114c-129">The following table describes the possible values.</span></span>  
  
|<span data-ttu-id="a114c-130">Keyword</span><span class="sxs-lookup"><span data-stu-id="a114c-130">Keyword</span></span>|<span data-ttu-id="a114c-131">説明</span><span class="sxs-lookup"><span data-stu-id="a114c-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a114c-132">Implicit Unbind</span><span class="sxs-lookup"><span data-stu-id="a114c-132">Implicit Unbind</span></span>|<span data-ttu-id="a114c-133">これが既定値です。</span><span class="sxs-lookup"><span data-stu-id="a114c-133">The default.</span></span> <span data-ttu-id="a114c-134">完了時に接続がトランザクションからデタッチされ、自動コミット モードに切り替わります。</span><span class="sxs-lookup"><span data-stu-id="a114c-134">The connection detaches from the transaction when it ends, switching back to autocommit mode.</span></span>|  
|<span data-ttu-id="a114c-135">Explicit Unbind</span><span class="sxs-lookup"><span data-stu-id="a114c-135">Explicit Unbind</span></span>|<span data-ttu-id="a114c-136">トランザクションが閉じられるまで、接続がトランザクションにアタッチされたままになります。</span><span class="sxs-lookup"><span data-stu-id="a114c-136">The connection remains attached to the transaction until the transaction is closed.</span></span> <span data-ttu-id="a114c-137">関連付けられているトランザクションがアクティブでない場合や、 <xref:System.Transactions.Transaction.Current%2A>と一致しない場合、接続は失敗します。</span><span class="sxs-lookup"><span data-stu-id="a114c-137">The connection will fail if the associated transaction is not active or does not match <xref:System.Transactions.Transaction.Current%2A>.</span></span>|  
  
## <a name="using-transactionscope"></a><span data-ttu-id="a114c-138">TransactionScope の使用</span><span class="sxs-lookup"><span data-stu-id="a114c-138">Using TransactionScope</span></span>  
 <span data-ttu-id="a114c-139"><xref:System.Transactions.TransactionScope> クラスは、接続を分散トランザクションに暗黙に参加させることで、コード ブロックをトランザクション対応にします。</span><span class="sxs-lookup"><span data-stu-id="a114c-139">The <xref:System.Transactions.TransactionScope> class makes a code block transactional by implicitly enlisting connections in a distributed transaction.</span></span> <span data-ttu-id="a114c-140"><xref:System.Transactions.TransactionScope.Complete%2A> ブロックの末尾では、終了する前に <xref:System.Transactions.TransactionScope> メソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="a114c-140">You must call the <xref:System.Transactions.TransactionScope.Complete%2A> method at the end of the <xref:System.Transactions.TransactionScope> block before leaving it.</span></span> <span data-ttu-id="a114c-141">ブロックを終了すると、 <xref:System.Transactions.TransactionScope.Dispose%2A> メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="a114c-141">Leaving the block invokes the <xref:System.Transactions.TransactionScope.Dispose%2A> method.</span></span> <span data-ttu-id="a114c-142">例外がスローされてコードがスコープから外れている場合は、トランザクションがアボートされたと見なされます。</span><span class="sxs-lookup"><span data-stu-id="a114c-142">If an exception has been thrown that causes the code to leave scope, the transaction is considered aborted.</span></span>  
  
 <span data-ttu-id="a114c-143">使用中のブロックを終了したときに `using` オブジェクトで <xref:System.Transactions.TransactionScope.Dispose%2A> が呼び出されるように、 <xref:System.Transactions.TransactionScope> ブロックを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a114c-143">We recommend that you use a `using` block to make sure that <xref:System.Transactions.TransactionScope.Dispose%2A> is called on the <xref:System.Transactions.TransactionScope> object when the using block is exited.</span></span> <span data-ttu-id="a114c-144">保留中のトランザクションのコミットまたはロールバックに失敗すると、 <xref:System.Transactions.TransactionScope> の既定のタイムアウトが 1 分であるため、パフォーマンスが大幅に低下する場合があります。</span><span class="sxs-lookup"><span data-stu-id="a114c-144">Failure to commit or roll back pending transactions can significantly damage performance because the default time-out for the <xref:System.Transactions.TransactionScope> is one minute.</span></span> <span data-ttu-id="a114c-145">`using` ステートメントを使用しない場合は、`Try` ブロック内のすべての処理を実行し、<xref:System.Transactions.TransactionScope.Dispose%2A> ブロックで `Finally` メソッドを明示的に呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="a114c-145">If you do not use a `using` statement, you must perform all work in a `Try` block and explicitly call the <xref:System.Transactions.TransactionScope.Dispose%2A> method in the `Finally` block.</span></span>  
  
 <span data-ttu-id="a114c-146"><xref:System.Transactions.TransactionScope>内で例外が発生した場合、そのトランザクションは矛盾しているとしてマークされ、破棄されます。</span><span class="sxs-lookup"><span data-stu-id="a114c-146">If an exception occurs in the <xref:System.Transactions.TransactionScope>, the transaction is marked as inconsistent and is abandoned.</span></span> <span data-ttu-id="a114c-147">トランザクションは、 <xref:System.Transactions.TransactionScope> が破棄されるとロールバックされます。</span><span class="sxs-lookup"><span data-stu-id="a114c-147">It will be rolled back when the <xref:System.Transactions.TransactionScope> is disposed.</span></span> <span data-ttu-id="a114c-148">例外が発生しなければ、参加しているトランザクションがコミットされます。</span><span class="sxs-lookup"><span data-stu-id="a114c-148">If no exception occurs, participating transactions commit.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a114c-149">既定では、`TransactionScope` クラスは、<xref:System.Transactions.Transaction.IsolationLevel%2A> が `Serializable` であるトランザクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="a114c-149">The `TransactionScope` class creates a transaction with a <xref:System.Transactions.Transaction.IsolationLevel%2A> of `Serializable` by default.</span></span> <span data-ttu-id="a114c-150">アプリケーションによっては、分離レベルを低くして、アプリケーション内の競合を回避することを検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a114c-150">Depending on your application, you might want to consider lowering the isolation level to avoid high contention in your application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a114c-151">データベース リソースを大量に消費するため、分散トランザクション内で実行するのは更新、挿入、削除だけにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a114c-151">We recommend that you perform only updates, inserts, and deletes within distributed transactions because they consume significant database resources.</span></span> <span data-ttu-id="a114c-152">Select ステートメントを使用すると、データベース リソースが不必要にロックされることがあり、シナリオによっては選択にトランザクションを使用する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="a114c-152">Select statements may lock database resources unnecessarily, and in some scenarios, you may have to use transactions for selects.</span></span> <span data-ttu-id="a114c-153">処理済みのその他のリソース マネージャーに関係する場合以外、データベース以外の処理はトランザクションのスコープ外で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a114c-153">Any non-database work should be done outside the scope of the transaction, unless it involves other transacted resource managers.</span></span> <span data-ttu-id="a114c-154">トランザクションのスコープ内で例外が発生するとトランザクションのコミットが防止されますが、 <xref:System.Transactions.TransactionScope> クラスでは、作成したコードによってトランザクションのスコープ外で行われた変更はロールバックされません。</span><span class="sxs-lookup"><span data-stu-id="a114c-154">Although an exception in the scope of the transaction prevents the transaction from committing, the <xref:System.Transactions.TransactionScope> class has no provision for rolling back any changes your code has made outside the scope of the transaction itself.</span></span> <span data-ttu-id="a114c-155">トランザクションがロールバックされたときに何らかの動作を行うようにする場合は、 <xref:System.Transactions.IEnlistmentNotification> インターフェイスを独自に実装し、トランザクションに明示的に参加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a114c-155">If you have to take some action when the transaction is rolled back, you must write your own implementation of the <xref:System.Transactions.IEnlistmentNotification> interface and explicitly enlist in the transaction.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a114c-156">例</span><span class="sxs-lookup"><span data-stu-id="a114c-156">Example</span></span>  
 <span data-ttu-id="a114c-157"><xref:System.Transactions> を使用する場合は、System.Transactions.dll への参照が必要になります。</span><span class="sxs-lookup"><span data-stu-id="a114c-157">Working with <xref:System.Transactions> requires that you have a reference to System.Transactions.dll.</span></span>  
  
 <span data-ttu-id="a114c-158">次の関数は、 <xref:System.Data.SqlClient.SqlConnection> ブロックでラップされている、異なる 2 つの <xref:System.Transactions.TransactionScope> オブジェクトで表された異なる 2 つの SQL Server インスタンスに対する、昇格可能なトランザクションを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a114c-158">The following function demonstrates how to create a promotable transaction against two different SQL Server instances, represented by two different <xref:System.Data.SqlClient.SqlConnection> objects, which are wrapped in a <xref:System.Transactions.TransactionScope> block.</span></span> <span data-ttu-id="a114c-159">このコードにより、 <xref:System.Transactions.TransactionScope> ステートメントを持つ `using` ブロックが作成され、最初の接続が開き、 <xref:System.Transactions.TransactionScope>に自動的に参加します。</span><span class="sxs-lookup"><span data-stu-id="a114c-159">The code creates the <xref:System.Transactions.TransactionScope> block with a `using` statement and opens the first connection, which automatically enlists it in the <xref:System.Transactions.TransactionScope>.</span></span> <span data-ttu-id="a114c-160">最初、トランザクションは完全な分散トランザクションではなく、軽量トランザクションとして参加します。</span><span class="sxs-lookup"><span data-stu-id="a114c-160">The transaction is initially enlisted as a lightweight transaction, not a full distributed transaction.</span></span> <span data-ttu-id="a114c-161">2 つ目の接続は、1 つ目の接続のコマンドで例外がスローされなかった場合にのみ、 <xref:System.Transactions.TransactionScope> に参加します。</span><span class="sxs-lookup"><span data-stu-id="a114c-161">The second connection is enlisted in the <xref:System.Transactions.TransactionScope> only if the command in the first connection does not throw an exception.</span></span> <span data-ttu-id="a114c-162">2 つ目の接続が開かれると、トランザクションが完全な分散トランザクションに自動的に昇格されます。</span><span class="sxs-lookup"><span data-stu-id="a114c-162">When the second connection is opened, the transaction is automatically promoted to a full distributed transaction.</span></span> <span data-ttu-id="a114c-163"><xref:System.Transactions.TransactionScope.Complete%2A> メソッドが呼び出され、例外がスローされなかった場合にのみ、トランザクションがコミットされます。</span><span class="sxs-lookup"><span data-stu-id="a114c-163">The <xref:System.Transactions.TransactionScope.Complete%2A> method is invoked, which commits the transaction only if no exceptions have been thrown.</span></span> <span data-ttu-id="a114c-164"><xref:System.Transactions.TransactionScope> ブロックの任意の場所で例外がスローされると、 `Complete` が呼び出されず、 <xref:System.Transactions.TransactionScope> ブロックの最後で `using` が破棄されたときに分散トランザクションがロールバックされます。</span><span class="sxs-lookup"><span data-stu-id="a114c-164">If an exception has been thrown at any point in the <xref:System.Transactions.TransactionScope> block, `Complete` will not be called, and the distributed transaction will roll back when the <xref:System.Transactions.TransactionScope> is disposed at the end of its `using` block.</span></span>  
  
```csharp  
// This function takes arguments for the 2 connection strings and commands in order  
// to create a transaction involving two SQL Servers. It returns a value > 0 if the  
// transaction committed, 0 if the transaction rolled back. To test this code, you can
// connect to two different databases on the same server by altering the connection string,  
// or to another RDBMS such as Oracle by altering the code in the connection2 code block.  
static public int CreateTransactionScope(  
    string connectString1, string connectString2,  
    string commandText1, string commandText2)  
{  
    // Initialize the return value to zero and create a StringWriter to display results.  
    int returnValue = 0;  
    System.IO.StringWriter writer = new System.IO.StringWriter();  
  
    // Create the TransactionScope in which to execute the commands, guaranteeing  
    // that both commands will commit or roll back as a single unit of work.  
    using (TransactionScope scope = new TransactionScope())  
    {  
        using (SqlConnection connection1 = new SqlConnection(connectString1))  
        {  
            try  
            {  
                // Opening the connection automatically enlists it in the
                // TransactionScope as a lightweight transaction.  
                connection1.Open();  
  
                // Create the SqlCommand object and execute the first command.  
                SqlCommand command1 = new SqlCommand(commandText1, connection1);  
                returnValue = command1.ExecuteNonQuery();  
                writer.WriteLine("Rows to be affected by command1: {0}", returnValue);  
  
                // if you get here, this means that command1 succeeded. By nesting  
                // the using block for connection2 inside that of connection1, you  
                // conserve server and network resources by opening connection2
                // only when there is a chance that the transaction can commit.
                using (SqlConnection connection2 = new SqlConnection(connectString2))  
                    try  
                    {  
                        // The transaction is promoted to a full distributed  
                        // transaction when connection2 is opened.  
                        connection2.Open();  
  
                        // Execute the second command in the second database.  
                        returnValue = 0;  
                        SqlCommand command2 = new SqlCommand(commandText2, connection2);  
                        returnValue = command2.ExecuteNonQuery();  
                        writer.WriteLine("Rows to be affected by command2: {0}", returnValue);  
                    }  
                    catch (Exception ex)  
                    {  
                        // Display information that command2 failed.  
                        writer.WriteLine("returnValue for command2: {0}", returnValue);  
                        writer.WriteLine("Exception Message2: {0}", ex.Message);  
                    }  
            }  
            catch (Exception ex)  
            {  
                // Display information that command1 failed.  
                writer.WriteLine("returnValue for command1: {0}", returnValue);  
                writer.WriteLine("Exception Message1: {0}", ex.Message);  
            }  
        }  
  
        // If an exception has been thrown, Complete will not
        // be called and the transaction is rolled back.  
        scope.Complete();  
    }  
  
    // The returnValue is greater than 0 if the transaction committed.  
    if (returnValue > 0)  
    {  
        writer.WriteLine("Transaction was committed.");  
    }  
    else  
    {  
        // You could write additional business logic here, notify the caller by  
        // throwing a TransactionAbortedException, or log the failure.  
        writer.WriteLine("Transaction rolled back.");  
    }  
  
    // Display messages.  
    Console.WriteLine(writer.ToString());  
  
    return returnValue;  
}  
```  
  
```vb  
' This function takes arguments for the 2 connection strings and commands in order  
' to create a transaction involving two SQL Servers. It returns a value > 0 if the  
' transaction committed, 0 if the transaction rolled back. To test this code, you can
' connect to two different databases on the same server by altering the connection string,  
' or to another RDBMS such as Oracle by altering the code in the connection2 code block.  
Public Function CreateTransactionScope( _  
  ByVal connectString1 As String, ByVal connectString2 As String, _  
  ByVal commandText1 As String, ByVal commandText2 As String) As Integer  
  
    ' Initialize the return value to zero and create a StringWriter to display results.  
    Dim returnValue As Integer = 0  
    Dim writer As System.IO.StringWriter = New System.IO.StringWriter  
  
    ' Create the TransactionScope in which to execute the commands, guaranteeing  
    ' that both commands will commit or roll back as a single unit of work.  
    Using scope As New TransactionScope()  
        Using connection1 As New SqlConnection(connectString1)  
            Try  
                ' Opening the connection automatically enlists it in the
                ' TransactionScope as a lightweight transaction.  
                connection1.Open()  
  
                ' Create the SqlCommand object and execute the first command.  
                Dim command1 As SqlCommand = New SqlCommand(commandText1, connection1)  
                returnValue = command1.ExecuteNonQuery()  
                writer.WriteLine("Rows to be affected by command1: {0}", returnValue)  
  
                ' If you get here, this means that command1 succeeded. By nesting  
                ' the Using block for connection2 inside that of connection1, you  
                ' conserve server and network resources by opening connection2
                ' only when there is a chance that the transaction can commit.
                Using connection2 As New SqlConnection(connectString2)  
                    Try  
                        ' The transaction is promoted to a full distributed  
                        ' transaction when connection2 is opened.  
                        connection2.Open()  
  
                        ' Execute the second command in the second database.  
                        returnValue = 0  
                        Dim command2 As SqlCommand = New SqlCommand(commandText2, connection2)  
                        returnValue = command2.ExecuteNonQuery()  
                        writer.WriteLine("Rows to be affected by command2: {0}", returnValue)  
  
                    Catch ex As Exception  
                        ' Display information that command2 failed.  
                        writer.WriteLine("returnValue for command2: {0}", returnValue)  
                        writer.WriteLine("Exception Message2: {0}", ex.Message)  
                    End Try  
                End Using  
  
            Catch ex As Exception  
                ' Display information that command1 failed.  
                writer.WriteLine("returnValue for command1: {0}", returnValue)  
                writer.WriteLine("Exception Message1: {0}", ex.Message)  
            End Try  
        End Using  
  
        ' If an exception has been thrown, Complete will
        ' not be called and the transaction is rolled back.  
        scope.Complete()  
    End Using  
  
    ' The returnValue is greater than 0 if the transaction committed.  
    If returnValue > 0 Then  
        writer.WriteLine("Transaction was committed.")  
    Else  
        ' You could write additional business logic here, notify the caller by  
        ' throwing a TransactionAbortedException, or log the failure.  
       writer.WriteLine("Transaction rolled back.")  
     End If  
  
    ' Display messages.  
    Console.WriteLine(writer.ToString())  
  
    Return returnValue  
End Function  
```  
  
## <a name="see-also"></a><span data-ttu-id="a114c-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="a114c-165">See also</span></span>

- [<span data-ttu-id="a114c-166">トランザクションとコンカレンシー</span><span class="sxs-lookup"><span data-stu-id="a114c-166">Transactions and Concurrency</span></span>](transactions-and-concurrency.md)
- [<span data-ttu-id="a114c-167">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="a114c-167">ADO.NET Overview</span></span>](ado-net-overview.md)
