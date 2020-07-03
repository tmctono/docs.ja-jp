---
title: CommittableTransaction を使用した明示的なトランザクションの実装
description: .NET で CommittableTransaction を使用した明示的なトランザクションを実装します。 このクラスによって、アプリケーションでトランザクションを使用する明示的な方法が提供されました。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 29efe5e5-897b-46c2-a35f-e599a273acc8
ms.openlocfilehash: 40001422e665a7dda3fb938c8d57860909525404
ms.sourcegitcommit: 6219b1e1feccb16d88656444210fed3297f5611e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/22/2020
ms.locfileid: "85141992"
---
# <a name="implementing-an-explicit-transaction-using-committabletransaction"></a><span data-ttu-id="7b662-104">CommittableTransaction を使用した明示的なトランザクションの実装</span><span class="sxs-lookup"><span data-stu-id="7b662-104">Implementing an Explicit Transaction using CommittableTransaction</span></span>
<span data-ttu-id="7b662-105"><xref:System.Transactions.CommittableTransaction> クラスは、<xref:System.Transactions.TransactionScope> クラスが暗黙的に使用されるのと対照的に、アプリケーションがトランザクションを明示的に使用する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="7b662-105">The <xref:System.Transactions.CommittableTransaction> class provides an explicit way for applications to use a transaction, as opposed to using the <xref:System.Transactions.TransactionScope> class implicitly.</span></span> <span data-ttu-id="7b662-106">これは、複数の関数呼び出しまたは複数のスレッド呼び出しで同じトランザクションを使用するアプリケーションで役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7b662-106">It is useful for applications that want to use the same transaction across multiple function calls or multiple thread calls.</span></span> <span data-ttu-id="7b662-107"><xref:System.Transactions.TransactionScope> クラスとは異なり、アプリケーション作成者はトランザクションをコミットまたは中止するために、具体的に <xref:System.Transactions.CommittableTransaction.Commit%2A> メソッドまたは <xref:System.Transactions.Transaction.Rollback%2A> メソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b662-107">Unlike the <xref:System.Transactions.TransactionScope> class, the application writer needs to specifically call the <xref:System.Transactions.CommittableTransaction.Commit%2A> and <xref:System.Transactions.Transaction.Rollback%2A> methods in order to commit or abort the transaction.</span></span>  
  
## <a name="overview-of-the-committabletransaction-class"></a><span data-ttu-id="7b662-108">CommittableTransaction クラスの概要</span><span class="sxs-lookup"><span data-stu-id="7b662-108">Overview of the CommittableTransaction class</span></span>  
 <span data-ttu-id="7b662-109"><xref:System.Transactions.CommittableTransaction> クラスは、<xref:System.Transactions.Transaction> クラスから派生するため、後者のすべての機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="7b662-109">The <xref:System.Transactions.CommittableTransaction> class derives from the <xref:System.Transactions.Transaction> class, therefore providing all the functionality of the latter.</span></span> <span data-ttu-id="7b662-110">特に有用なのは、<xref:System.Transactions.Transaction.Rollback%2A> クラスの <xref:System.Transactions.Transaction> メソッドで、これは <xref:System.Transactions.CommittableTransaction> オブジェクトのロールバックにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="7b662-110">Specifically useful is the <xref:System.Transactions.Transaction.Rollback%2A> method on the <xref:System.Transactions.Transaction> class that can also be used to rollback a <xref:System.Transactions.CommittableTransaction> object.</span></span>  
  
 <span data-ttu-id="7b662-111"><xref:System.Transactions.Transaction> クラスは <xref:System.Transactions.CommittableTransaction> クラスに類似していますが、`Commit` メソッドは提供しません。</span><span class="sxs-lookup"><span data-stu-id="7b662-111">The  <xref:System.Transactions.Transaction> class is similar to the <xref:System.Transactions.CommittableTransaction> class but does not offer a `Commit` method.</span></span> <span data-ttu-id="7b662-112">これにより、トランザクションのコミット時に制御を継続しながら、トランザクション オブジェクト (またはその複製) を他のメソッド (他のスレッド上に存在する可能性もあり) に渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="7b662-112">This enables you to pass the transaction object (or clones of it) to other methods (potentially on other threads) while still controlling when the transaction is committed.</span></span> <span data-ttu-id="7b662-113">呼び出されたコードでは、トランザクションの参加や処理の選択を行えますが、トランザクションをコミットできるのは <xref:System.Transactions.CommittableTransaction> オブジェクトの作成者のみです。</span><span class="sxs-lookup"><span data-stu-id="7b662-113">The called code is able to enlist and vote on the transaction, but only the creator of the <xref:System.Transactions.CommittableTransaction> object has the ability to commit the transaction.</span></span>  
  
 <span data-ttu-id="7b662-114"><xref:System.Transactions.CommittableTransaction> クラスを使用する場合には、次のことに注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b662-114">You should note the followings when working with the <xref:System.Transactions.CommittableTransaction> class,</span></span>  
  
- <span data-ttu-id="7b662-115"><xref:System.Transactions.CommittableTransaction> トランザクションを作成しても、アンビエント トランザクションは設定されません。</span><span class="sxs-lookup"><span data-stu-id="7b662-115">Creating a <xref:System.Transactions.CommittableTransaction> transaction does not set the ambient transaction.</span></span> <span data-ttu-id="7b662-116">リソース マネージャーが必要に応じて正しいトランザクション コンテキストで動作することを保証するには、アンビエント トランザクションを具体的に設定およびリセットする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b662-116">You need to specifically set and reset the ambient transaction, to ensure that resource managers operate under the right transaction context when appropriate.</span></span> <span data-ttu-id="7b662-117">現在のアンビエント トランザクションを設定するには、グローバルな <xref:System.Transactions.Transaction.Current%2A> オブジェクトの静的な <xref:System.Transactions.Transaction> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="7b662-117">The way to set the current ambient transaction is by setting the static <xref:System.Transactions.Transaction.Current%2A> property on the global <xref:System.Transactions.Transaction> object.</span></span>  
  
- <span data-ttu-id="7b662-118"><xref:System.Transactions.CommittableTransaction> オブジェクトは再利用できません。</span><span class="sxs-lookup"><span data-stu-id="7b662-118">A <xref:System.Transactions.CommittableTransaction> object cannot be reused.</span></span> <span data-ttu-id="7b662-119"><xref:System.Transactions.CommittableTransaction> オブジェクトがコミットまたはロールバックされると、トランザクションで再び使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="7b662-119">Once a <xref:System.Transactions.CommittableTransaction> object has been committed or rolled back, it cannot be used again in a transaction.</span></span> <span data-ttu-id="7b662-120">つまり、現在のアンビエント トランザクション コンテキストとして設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="7b662-120">That is, it cannot be set as the current ambient transaction context.</span></span>  
  
## <a name="creating-a-committabletransaction"></a><span data-ttu-id="7b662-121">CommittableTransaction の作成</span><span class="sxs-lookup"><span data-stu-id="7b662-121">Creating a CommittableTransaction</span></span>  
 <span data-ttu-id="7b662-122">新しい <xref:System.Transactions.CommittableTransaction> を作成してコミットする例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="7b662-122">The following sample creates a new <xref:System.Transactions.CommittableTransaction> and commits it.</span></span>  
  
 [!code-csharp[Tx_CommittableTx#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/tx_committabletx/cs/committabletxwithsql.cs#1)]
 [!code-vb[Tx_CommittableTx#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/tx_committabletx/vb/committabletxwithsql.vb#1)]  
  
 <span data-ttu-id="7b662-123"><xref:System.Transactions.CommittableTransaction> のインスタンスを作成しても、アンビエント トランザクション コンテキストは自動的に設定されません。</span><span class="sxs-lookup"><span data-stu-id="7b662-123">Creating an instance of <xref:System.Transactions.CommittableTransaction> does not automatically set the ambient transaction context.</span></span> <span data-ttu-id="7b662-124">したがって、リソース マネージャーに対する操作は、そのトランザクションの一部に含まれません。</span><span class="sxs-lookup"><span data-stu-id="7b662-124">Therefore, any operation on a resource manager is not part of that transaction.</span></span> <span data-ttu-id="7b662-125">アンビエント トランザクションを設定または取得するには、グローバル <xref:System.Transactions.Transaction.Current%2A> オブジェクトの静的な <xref:System.Transactions.Transaction> プロパティを使用します。アプリケーションでは、リソース マネージャーがトランザクションに参加できるようにするために、手動でこのプロパティを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b662-125">The static <xref:System.Transactions.Transaction.Current%2A> property on the global <xref:System.Transactions.Transaction> object is used to set or retrieve the ambient transaction and the application must manually set it to ensure that resource managers can participate in the transaction.</span></span> <span data-ttu-id="7b662-126">古いアンビエント トランザクションを保存し、<xref:System.Transactions.CommittableTransaction> オブジェクトの使用が終了したら復元することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7b662-126">It is also a good practice to save the old ambient transaction and restore it when you finish using the <xref:System.Transactions.CommittableTransaction> object.</span></span>  
  
 <span data-ttu-id="7b662-127">トランザクションをコミットするには、<xref:System.Transactions.CommittableTransaction.Commit%2A> メソッドを明示的に呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b662-127">To commit the transaction, you need to explicitly call the <xref:System.Transactions.CommittableTransaction.Commit%2A> method.</span></span> <span data-ttu-id="7b662-128">トランザクションをロールバックするには、<xref:System.Transactions.Transaction.Rollback%2A> メソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b662-128">For rolling back a transaction, you should call the <xref:System.Transactions.Transaction.Rollback%2A> method.</span></span> <span data-ttu-id="7b662-129"><xref:System.Transactions.CommittableTransaction> がコミットまたはロールバックされるまで、そのトランザクションに関連するすべてのリソースはロックされたままであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7b662-129">It is important to note that until a <xref:System.Transactions.CommittableTransaction> has been committed or rolled back, all the resources involved in that transaction are still locked.</span></span>  
  
 <span data-ttu-id="7b662-130"><xref:System.Transactions.CommittableTransaction> オブジェクトは、複数の関数呼び出しおよびスレッドにわたって使用できます。</span><span class="sxs-lookup"><span data-stu-id="7b662-130">A <xref:System.Transactions.CommittableTransaction> object can be used across function calls and threads.</span></span> <span data-ttu-id="7b662-131">ただし、例外を処理し、特に障害発生時に <xref:System.Transactions.Transaction.Rollback%28System.Exception%29> メソッドを呼び出すことはアプリケーション開発者の責任です。</span><span class="sxs-lookup"><span data-stu-id="7b662-131">However, it is up to the application developer to handle exceptions and specifically call the <xref:System.Transactions.Transaction.Rollback%28System.Exception%29> method in case of failures.</span></span>  
  
## <a name="asynchronous-commit"></a><span data-ttu-id="7b662-132">非同期コミット</span><span class="sxs-lookup"><span data-stu-id="7b662-132">Asynchronous Commit</span></span>  
 <span data-ttu-id="7b662-133"><xref:System.Transactions.CommittableTransaction> クラスは、トランザクションを非同期にコミットするための機構も提供します。</span><span class="sxs-lookup"><span data-stu-id="7b662-133">The <xref:System.Transactions.CommittableTransaction> class also provides a mechanism for committing a transaction asynchronously.</span></span> <span data-ttu-id="7b662-134">トランザクションのコミットは、複数回のデータベース アクセスや潜在的なネットワーク待機時間が含まれる場合、かなりの時間を要することがあります。</span><span class="sxs-lookup"><span data-stu-id="7b662-134">A transaction commit can take substantial time, as it might involve multiple database access and possible network latency.</span></span> <span data-ttu-id="7b662-135">高いスループットのアプリケーションでデッドロックを回避するため、非同期コミットを使用してできるだけ早期にトランザクションの処理を完了し、バックグラウンド タスクとしてコミット処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="7b662-135">When you want to avoid deadlocks in high throughput applications, you can use asynchronous commit to finish the transactional work as soon as possible, and run the commit operation as a background task.</span></span> <span data-ttu-id="7b662-136">このために、<xref:System.Transactions.CommittableTransaction.BeginCommit%2A> クラスの <xref:System.Transactions.CommittableTransaction.EndCommit%2A> メソッドおよび <xref:System.Transactions.CommittableTransaction> メソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7b662-136">The <xref:System.Transactions.CommittableTransaction.BeginCommit%2A> and <xref:System.Transactions.CommittableTransaction.EndCommit%2A> methods of the <xref:System.Transactions.CommittableTransaction> class allow you to do so.</span></span>  
  
 <span data-ttu-id="7b662-137"><xref:System.Transactions.CommittableTransaction.BeginCommit%2A> を呼び出すことで、スレッド プールからのスレッドにコミット ホールドアップをディスパッチできます。</span><span class="sxs-lookup"><span data-stu-id="7b662-137">You can call <xref:System.Transactions.CommittableTransaction.BeginCommit%2A> to dispatch the commit holdup to a thread from the thread pool.</span></span> <span data-ttu-id="7b662-138">また、<xref:System.Transactions.CommittableTransaction.EndCommit%2A> を呼び出して、トランザクションが実際にコミットされたかどうかを判断することもできます。</span><span class="sxs-lookup"><span data-stu-id="7b662-138">You can also call <xref:System.Transactions.CommittableTransaction.EndCommit%2A> to determine if the transaction has actually been committed.</span></span> <span data-ttu-id="7b662-139">なんらかの理由でトランザクションがコミットされなかった場合、<xref:System.Transactions.CommittableTransaction.EndCommit%2A> はトランザクションの例外を発生させます。</span><span class="sxs-lookup"><span data-stu-id="7b662-139">If the transaction failed to commit for whatever reason, <xref:System.Transactions.CommittableTransaction.EndCommit%2A> raises a transaction exception.</span></span> <span data-ttu-id="7b662-140"><xref:System.Transactions.CommittableTransaction.EndCommit%2A> が呼び出された時点でトランザクションがまだコミットされていない場合、トランザクションがコミットまたは中止されるまで、呼び出し元がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="7b662-140">If the transaction is not yet committed by the time <xref:System.Transactions.CommittableTransaction.EndCommit%2A> is called, the caller is blocked until the transaction is committed or aborted.</span></span>  
  
 <span data-ttu-id="7b662-141">非同期のコミットを行う最も簡単な方法は、コミットの完了時に呼び出されるコールバック メソッドを提供することです。</span><span class="sxs-lookup"><span data-stu-id="7b662-141">The easiest way to do an asynchronous commit is by providing a callback method, to be called when committing is finished.</span></span> <span data-ttu-id="7b662-142">ただし、呼び出しを実行するために使用する元の <xref:System.Transactions.CommittableTransaction.EndCommit%2A> オブジェクトに対して <xref:System.Transactions.CommittableTransaction> メソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b662-142">However, you must call the <xref:System.Transactions.CommittableTransaction.EndCommit%2A> method on the original <xref:System.Transactions.CommittableTransaction> object used to invoke the call.</span></span> <span data-ttu-id="7b662-143">そのオブジェクトを取得するには、コールバック メソッドの *IAsyncResult* パラメーターをダウンキャストできます。これは、<xref:System.Transactions.CommittableTransaction> クラスで <xref:System.IAsyncResult> クラスが実装されているためです。</span><span class="sxs-lookup"><span data-stu-id="7b662-143">To obtain that object, you can downcast the *IAsyncResult* parameter of the callback method, since the <xref:System.Transactions.CommittableTransaction> class implements <xref:System.IAsyncResult> class.</span></span>  
  
 <span data-ttu-id="7b662-144">次の例は、非同期コミットの実行方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="7b662-144">The following example shows how an asynchronous commit can be done.</span></span>  
  
```csharp  
public void DoTransactionalWork()  
{  
     Transaction oldAmbient = Transaction.Current;  
     CommittableTransaction committableTransaction = new CommittableTransaction();  
     Transaction.Current = committableTransaction;  
  
     try  
     {  
          /* Perform transactional work here */  
          // No errors - commit transaction asynchronously  
          committableTransaction.BeginCommit(OnCommitted,null);  
     }  
     finally  
     {  
          //Restore the ambient transaction
          Transaction.Current = oldAmbient;  
     }  
}  
void OnCommitted(IAsyncResult asyncResult)  
{  
     CommittableTransaction committableTransaction;  
     committableTransaction = asyncResult as CommittableTransaction;
     Debug.Assert(committableTransaction != null);  
     try  
     {  
          using(committableTransaction)  
          {  
               committableTransaction.EndCommit(asyncResult);  
          }  
     }  
     catch(TransactionException e)  
     {  
          //Handle the failure to commit  
     }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="7b662-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="7b662-145">See also</span></span>

- [<span data-ttu-id="7b662-146">トランザクション スコープを使用した暗黙的なトランザクションの実装</span><span class="sxs-lookup"><span data-stu-id="7b662-146">Implementing an Implicit Transaction using Transaction Scope</span></span>](implementing-an-implicit-transaction-using-transaction-scope.md)
- [<span data-ttu-id="7b662-147">トランザクション処理</span><span class="sxs-lookup"><span data-stu-id="7b662-147">Transaction Processing</span></span>](index.md)
