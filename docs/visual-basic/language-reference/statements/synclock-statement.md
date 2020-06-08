---
title: SyncLock ステートメント
ms.date: 07/20/2015
f1_keywords:
- vb.SyncLock
- SyncLock
helpviewer_keywords:
- threading [Visual Basic], locks
- SyncLock statement [Visual Basic]
- locks, threads
ms.assetid: 14501703-298f-4d43-b139-c4b6366af176
ms.openlocfilehash: fd932a20af274faf2b56136a94675b28399989b8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404162"
---
# <a name="synclock-statement"></a><span data-ttu-id="02449-102">SyncLock ステートメント</span><span class="sxs-lookup"><span data-stu-id="02449-102">SyncLock Statement</span></span>
<span data-ttu-id="02449-103">ブロックを実行する前に、ステートメント ブロックの排他ロックを取得します。</span><span class="sxs-lookup"><span data-stu-id="02449-103">Acquires an exclusive lock for a statement block before executing the block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02449-104">構文</span><span class="sxs-lookup"><span data-stu-id="02449-104">Syntax</span></span>  
  
```vb  
SyncLock lockobject  
    [ block ]  
End SyncLock  
```  
  
## <a name="parts"></a><span data-ttu-id="02449-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="02449-105">Parts</span></span>  
 `lockobject`  
 <span data-ttu-id="02449-106">必須です。</span><span class="sxs-lookup"><span data-stu-id="02449-106">Required.</span></span> <span data-ttu-id="02449-107">オブジェクト参照として評価される式。</span><span class="sxs-lookup"><span data-stu-id="02449-107">Expression that evaluates to an object reference.</span></span>  
  
 `block`  
 <span data-ttu-id="02449-108">任意。</span><span class="sxs-lookup"><span data-stu-id="02449-108">Optional.</span></span> <span data-ttu-id="02449-109">ロックが取得されたときに実行されるステートメントのブロック。</span><span class="sxs-lookup"><span data-stu-id="02449-109">Block of statements that are to execute when the lock is acquired.</span></span>  
  
 `End SyncLock`  
 <span data-ttu-id="02449-110">`SyncLock` ブロックを終了します。</span><span class="sxs-lookup"><span data-stu-id="02449-110">Terminates a `SyncLock` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02449-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="02449-111">Remarks</span></span>  
 <span data-ttu-id="02449-112">`SyncLock` ステートメントは、複数のスレッドがステートメント ブロックを同時に実行しないようにします。</span><span class="sxs-lookup"><span data-stu-id="02449-112">The `SyncLock` statement ensures that multiple threads do not execute the statement block at the same time.</span></span> <span data-ttu-id="02449-113">`SyncLock` は、ブロックを実行する他のスレッドがなくなるまで、各スレッドがそのブロックに入らないようにします。</span><span class="sxs-lookup"><span data-stu-id="02449-113">`SyncLock` prevents each thread from entering the block until no other thread is executing it.</span></span>  
  
 <span data-ttu-id="02449-114">`SyncLock` の最も一般的な使用方法は、複数のスレッドによってデータが同時に更新されないようにすることです。</span><span class="sxs-lookup"><span data-stu-id="02449-114">The most common use of `SyncLock` is to protect data from being updated by more than one thread simultaneously.</span></span> <span data-ttu-id="02449-115">データを操作するステートメントが中断せずに完了する必要がある場合は、`SyncLock` ブロック内に配置します。</span><span class="sxs-lookup"><span data-stu-id="02449-115">If the statements that manipulate the data must go to completion without interruption, put them inside a `SyncLock` block.</span></span>  
  
 <span data-ttu-id="02449-116">排他ロックによって保護されているステートメント ブロックは、*クリティカル セクション*と呼ばれることもあります。</span><span class="sxs-lookup"><span data-stu-id="02449-116">A statement block protected by an exclusive lock is sometimes called a *critical section*.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="02449-117">ルール</span><span class="sxs-lookup"><span data-stu-id="02449-117">Rules</span></span>  
  
- <span data-ttu-id="02449-118">分岐。</span><span class="sxs-lookup"><span data-stu-id="02449-118">Branching.</span></span> <span data-ttu-id="02449-119">ブロック外から `SyncLock` ブロックに分岐することはできません。</span><span class="sxs-lookup"><span data-stu-id="02449-119">You cannot branch into a `SyncLock` block from outside the block.</span></span>  
  
- <span data-ttu-id="02449-120">ロック オブジェクトの値。</span><span class="sxs-lookup"><span data-stu-id="02449-120">Lock Object Value.</span></span> <span data-ttu-id="02449-121">`lockobject` の値を `Nothing` にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="02449-121">The value of `lockobject` cannot be `Nothing`.</span></span> <span data-ttu-id="02449-122">`SyncLock` ステートメントで使用する前に、ロック オブジェクトを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="02449-122">You must create the lock object before you use it in a `SyncLock` statement.</span></span>  
  
     <span data-ttu-id="02449-123">`SyncLock` ブロックの実行中に `lockobject` の値を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="02449-123">You cannot change the value of `lockobject` while executing a `SyncLock` block.</span></span> <span data-ttu-id="02449-124">このメカニズムでは、ロック オブジェクトが変更されないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="02449-124">The mechanism requires that the lock object remain unchanged.</span></span>  
  
- <span data-ttu-id="02449-125">`SyncLock` ブロックで [Await](../operators/await-operator.md) 演算子を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="02449-125">You can't use the [Await](../operators/await-operator.md) operator in a `SyncLock` block.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="02449-126">動作</span><span class="sxs-lookup"><span data-stu-id="02449-126">Behavior</span></span>  
  
- <span data-ttu-id="02449-127">メカニズム。</span><span class="sxs-lookup"><span data-stu-id="02449-127">Mechanism.</span></span> <span data-ttu-id="02449-128">スレッドが `SyncLock` ステートメントに達すると、`lockobject` 式が評価され、式によって返されたオブジェクトの排他ロックを取得するまで実行が中断されます。</span><span class="sxs-lookup"><span data-stu-id="02449-128">When a thread reaches the `SyncLock` statement, it evaluates the `lockobject` expression and suspends execution until it acquires an exclusive lock on the object returned by the expression.</span></span> <span data-ttu-id="02449-129">別のスレッドが `SyncLock` ステートメントに達すると、最初のスレッドが `End SyncLock` ステートメントを実行するまでロックは取得されません。</span><span class="sxs-lookup"><span data-stu-id="02449-129">When another thread reaches the `SyncLock` statement, it does not acquire a lock until the first thread executes the `End SyncLock` statement.</span></span>  
  
- <span data-ttu-id="02449-130">保護されたデータ。</span><span class="sxs-lookup"><span data-stu-id="02449-130">Protected Data.</span></span> <span data-ttu-id="02449-131">`lockobject` が `Shared` 変数の場合は、排他ロックによって、クラスのインスタンス内のスレッドが、他のスレッドが実行している間は `SyncLock` ブロックを実行できなくなります。</span><span class="sxs-lookup"><span data-stu-id="02449-131">If `lockobject` is a `Shared` variable, the exclusive lock prevents a thread in any instance of the class from executing the `SyncLock` block while any other thread is executing it.</span></span> <span data-ttu-id="02449-132">これにより、すべてのインスタンス間で共有されているデータが保護されます。</span><span class="sxs-lookup"><span data-stu-id="02449-132">This protects data that is shared among all the instances.</span></span>  
  
     <span data-ttu-id="02449-133">`lockobject` がインスタンス変数 (`Shared` ではなく) の場合は、ロックにより、現在のインスタンスで実行されているスレッドが、同じインスタンス内の別のスレッドと同時に `SyncLock` ブロックを実行できなくなります。</span><span class="sxs-lookup"><span data-stu-id="02449-133">If `lockobject` is an instance variable (not `Shared`), the lock prevents a thread running in the current instance from executing the `SyncLock` block at the same time as another thread in the same instance.</span></span> <span data-ttu-id="02449-134">これにより、個々のインスタンスによって保持されるデータが保護されます。</span><span class="sxs-lookup"><span data-stu-id="02449-134">This protects data maintained by the individual instance.</span></span>  
  
- <span data-ttu-id="02449-135">取得と解放。</span><span class="sxs-lookup"><span data-stu-id="02449-135">Acquisition and Release.</span></span> <span data-ttu-id="02449-136">`SyncLock` ブロックは、`Try` ブロックが `lockobject` に対して排他ロックを取得する `Try...Finally` コンストラクションと同様に動作し、`Finally` ブロックによって解放されます。</span><span class="sxs-lookup"><span data-stu-id="02449-136">A `SyncLock` block behaves like a `Try...Finally` construction in which the `Try` block acquires an exclusive lock on `lockobject` and the `Finally` block releases it.</span></span> <span data-ttu-id="02449-137">このため、`SyncLock` ブロックは、ブロックを終了する方法に関係なく、ロックの解放を保証します。</span><span class="sxs-lookup"><span data-stu-id="02449-137">Because of this, the `SyncLock` block guarantees release of the lock, no matter how you exit the block.</span></span> <span data-ttu-id="02449-138">これは、ハンドルされない例外が発生した場合でも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="02449-138">This is true even in the case of an unhandled exception.</span></span>  
  
- <span data-ttu-id="02449-139">フレームワークの呼び出し。</span><span class="sxs-lookup"><span data-stu-id="02449-139">Framework Calls.</span></span> <span data-ttu-id="02449-140">`SyncLock` ブロックは、<xref:System.Threading> 名前空間の `Monitor` クラスの `Enter` および `Exit` メソッドを呼び出すことによって、排他ロックを取得したり解放したりします。</span><span class="sxs-lookup"><span data-stu-id="02449-140">The `SyncLock` block acquires and releases the exclusive lock by calling the `Enter` and `Exit` methods of the `Monitor` class in the <xref:System.Threading> namespace.</span></span>  
  
## <a name="programming-practices"></a><span data-ttu-id="02449-141">プログラミング プラクティス</span><span class="sxs-lookup"><span data-stu-id="02449-141">Programming Practices</span></span>  
 <span data-ttu-id="02449-142">`lockobject` 式は、常に、クラスに排他的に属しているオブジェクトに評価される必要があります。</span><span class="sxs-lookup"><span data-stu-id="02449-142">The `lockobject` expression should always evaluate to an object that belongs exclusively to your class.</span></span> <span data-ttu-id="02449-143">現在のインスタンスに属するデータを保護するには `Private` オブジェクト変数を宣言し、すべてのインスタンスに共通のデータを保護するには `Private Shared` オブジェクト変数を宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="02449-143">You should declare a `Private` object variable to protect data belonging to the current instance, or a `Private Shared` object variable to protect data common to all instances.</span></span>  
  
 <span data-ttu-id="02449-144">インスタンス データ用のロック オブジェクトを指定するために、`Me` キーワードを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="02449-144">You should not use the `Me` keyword to provide a lock object for instance data.</span></span> <span data-ttu-id="02449-145">クラスの外部のコードにクラスのインスタンスへの参照が含まれている場合、その参照を、ユーザーのものとはまったく異なる `SyncLock` ブロックのロック オブジェクトとして使用して、さまざまなデータを保護することができます。</span><span class="sxs-lookup"><span data-stu-id="02449-145">If code external to your class has a reference to an instance of your class, it could use that reference as a lock object for a `SyncLock` block completely different from yours, protecting different data.</span></span> <span data-ttu-id="02449-146">このようにして、ユーザーのクラスとその他のクラスは、関連付けられていない `SyncLock` ブロックの実行を互いにブロックできます。</span><span class="sxs-lookup"><span data-stu-id="02449-146">In this way, your class and the other class could block each other from executing their unrelated `SyncLock` blocks.</span></span> <span data-ttu-id="02449-147">同様に、文字列のロックも問題になる可能性があります。同じ文字列を使用するコードがプロセス内に他にも存在した場合、そのコードも同じロックを共有するためです。</span><span class="sxs-lookup"><span data-stu-id="02449-147">Similarly locking on a string can be problematic since any other code in the process using the same string will share the same lock.</span></span>  
  
 <span data-ttu-id="02449-148">また、共有データのロック オブジェクトを指定するために、`Me.GetType` メソッドを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="02449-148">You should also not use the `Me.GetType` method to provide a lock object for shared data.</span></span> <span data-ttu-id="02449-149">これは、`GetType` は常に、指定されたクラス名に対して同じ `Type` オブジェクトを返すためです。</span><span class="sxs-lookup"><span data-stu-id="02449-149">This is because `GetType` always returns the same `Type` object for a given class name.</span></span> <span data-ttu-id="02449-150">外部コードは、クラスで `GetType` を呼び出し、使用しているものと同じロック オブジェクトを取得することができます。</span><span class="sxs-lookup"><span data-stu-id="02449-150">External code could call `GetType` on your class and obtain the same lock object you are using.</span></span> <span data-ttu-id="02449-151">これにより、2 つのクラスが `SyncLock` ブロックから互いにブロックされることになります。</span><span class="sxs-lookup"><span data-stu-id="02449-151">This would result in the two classes blocking each other from their `SyncLock` blocks.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="02449-152">使用例</span><span class="sxs-lookup"><span data-stu-id="02449-152">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="02449-153">説明</span><span class="sxs-lookup"><span data-stu-id="02449-153">Description</span></span>  
 <span data-ttu-id="02449-154">次の例では、メッセージの単純なリストを保持するクラスを示します。</span><span class="sxs-lookup"><span data-stu-id="02449-154">The following example shows a class that maintains a simple list of messages.</span></span> <span data-ttu-id="02449-155">これは、メッセージを配列内に保持し、その配列の最後に使用された要素を変数に保持します。</span><span class="sxs-lookup"><span data-stu-id="02449-155">It holds the messages in an array and the last used element of that array in a variable.</span></span> <span data-ttu-id="02449-156">`addAnotherMessage` プロシージャは、最後の要素をインクリメントし、新しいメッセージを格納します。</span><span class="sxs-lookup"><span data-stu-id="02449-156">The `addAnotherMessage` procedure increments the last element and stores the new message.</span></span> <span data-ttu-id="02449-157">これら 2 つの操作は、`SyncLock` および `End SyncLock` ステートメントによって保護されます。最後の要素がインクリメントされた後、他のすべてのスレッドが最後の要素を再度インクリメントできるようになる前に、新しいメッセージが格納される必要があるためです。</span><span class="sxs-lookup"><span data-stu-id="02449-157">Those two operations are protected by the `SyncLock` and `End SyncLock` statements, because once the last element has been incremented, the new message must be stored before any other thread can increment the last element again.</span></span>  
  
 <span data-ttu-id="02449-158">`simpleMessageList` クラスがそのすべてのインスタンス間で 1 つのメッセージ リストを共有している場合、変数 `messagesList` および `messagesLast` は `Shared` として宣言されます。</span><span class="sxs-lookup"><span data-stu-id="02449-158">If the `simpleMessageList` class shared one list of messages among all its instances, the variables `messagesList` and `messagesLast` would be declared as `Shared`.</span></span> <span data-ttu-id="02449-159">この場合、変数 `messagesLock` も `Shared` にして、すべてのインスタンスで 1 つのロック オブジェクトが使用されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="02449-159">In this case, the variable `messagesLock` should also be `Shared`, so that there would be a single lock object used by every instance.</span></span>  
  
### <a name="code"></a><span data-ttu-id="02449-160">コード</span><span class="sxs-lookup"><span data-stu-id="02449-160">Code</span></span>  
 [!code-vb[VbVbalrThreading#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrThreading/VB/Class1.vb#1)]  
  
### <a name="description"></a><span data-ttu-id="02449-161">説明</span><span class="sxs-lookup"><span data-stu-id="02449-161">Description</span></span>  
 <span data-ttu-id="02449-162">次の例では、スレッドと `SyncLock` を使用しています。</span><span class="sxs-lookup"><span data-stu-id="02449-162">The following example uses threads and `SyncLock`.</span></span> <span data-ttu-id="02449-163">`SyncLock` ステートメントが存在する限り、このステートメント ブロックはクリティカル セクションとなり、`balance` が負の数になることはありません。</span><span class="sxs-lookup"><span data-stu-id="02449-163">As long as the `SyncLock` statement is present, the statement block is a critical section and `balance` never becomes a negative number.</span></span> <span data-ttu-id="02449-164">`SyncLock` および `End SyncLock` ステートメントをコメント アウトして、`SyncLock` キーワードを残すことによる影響を確認できます。</span><span class="sxs-lookup"><span data-stu-id="02449-164">You can comment out the `SyncLock` and `End SyncLock` statements to see the effect of leaving out the `SyncLock` keyword.</span></span>  
  
### <a name="code"></a><span data-ttu-id="02449-165">コード</span><span class="sxs-lookup"><span data-stu-id="02449-165">Code</span></span>  
 [!code-vb[VbVbalrThreading#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrThreading/VB/class2.vb#21)]  
  
### <a name="comments"></a><span data-ttu-id="02449-166">コメント</span><span class="sxs-lookup"><span data-stu-id="02449-166">Comments</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02449-167">関連項目</span><span class="sxs-lookup"><span data-stu-id="02449-167">See also</span></span>

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.Interlocked?displayProperty=nameWithType>
- [<span data-ttu-id="02449-168">同期プリミティブの概要</span><span class="sxs-lookup"><span data-stu-id="02449-168">Overview of synchronization primitives</span></span>](../../../standard/threading/overview-of-synchronization-primitives.md)
