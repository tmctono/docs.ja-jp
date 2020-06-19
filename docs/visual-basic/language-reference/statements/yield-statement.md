---
title: Yield ステートメント
ms.date: 07/20/2015
f1_keywords:
- vb.Yield
helpviewer_keywords:
- iterators, Yield statement [Visual Basic]
- iterators [Visual Basic]
- Yield statement [Visual Basic]
ms.assetid: f33126c5-d7c4-43e2-8e36-4ae3f0703d97
ms.openlocfilehash: cc89e6f9bc2ccb4fff9a9fe12cd190a6b2d212dc
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401369"
---
# <a name="yield-statement-visual-basic"></a><span data-ttu-id="b2de7-102">Yield ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b2de7-102">Yield Statement (Visual Basic)</span></span>
<span data-ttu-id="b2de7-103">コレクションの次の要素を `For Each...Next` ステートメントに送ります。</span><span class="sxs-lookup"><span data-stu-id="b2de7-103">Sends the next element of a collection to a `For Each...Next` statement.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2de7-104">構文</span><span class="sxs-lookup"><span data-stu-id="b2de7-104">Syntax</span></span>  
  
```vb  
Yield expression  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2de7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b2de7-105">Parameters</span></span>  
  
|<span data-ttu-id="b2de7-106">用語</span><span class="sxs-lookup"><span data-stu-id="b2de7-106">Term</span></span>|<span data-ttu-id="b2de7-107">定義</span><span class="sxs-lookup"><span data-stu-id="b2de7-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="b2de7-108">必須です。</span><span class="sxs-lookup"><span data-stu-id="b2de7-108">Required.</span></span> <span data-ttu-id="b2de7-109">`Yield` ステートメントを含む iterator 関数または `Get` アクセサーの型に暗黙的に変換可能な式。</span><span class="sxs-lookup"><span data-stu-id="b2de7-109">An expression that is implicitly convertible to the type of the iterator function or `Get` accessor that contains the `Yield` statement.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2de7-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="b2de7-110">Remarks</span></span>  
 <span data-ttu-id="b2de7-111">`Yield` ステートメントでは、コレクションの要素を一度に 1 つずつ返します。</span><span class="sxs-lookup"><span data-stu-id="b2de7-111">The `Yield` statement returns one element of a collection at a time.</span></span> <span data-ttu-id="b2de7-112">`Yield` ステートメントは、コレクションに対してカスタムの反復を実行する iterator 関数または `Get` アクセサーに含まれます。</span><span class="sxs-lookup"><span data-stu-id="b2de7-112">The `Yield` statement is included in an iterator function or `Get` accessor, which perform custom iterations over a collection.</span></span>  
  
 <span data-ttu-id="b2de7-113">iterator 関数を使用するには、[For Each...Next ステートメント](for-each-next-statement.md)または LINQ クエリを使用します。</span><span class="sxs-lookup"><span data-stu-id="b2de7-113">You consume an iterator function by using a [For Each...Next Statement](for-each-next-statement.md) or a LINQ query.</span></span> <span data-ttu-id="b2de7-114">`For Each` ループの各反復は、iterator 関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b2de7-114">Each iteration of the `For Each` loop calls the iterator function.</span></span> <span data-ttu-id="b2de7-115">`Yield` ステートメントが iterator 関数に到達すると、`expression` が返され、コードの現在の位置が保持されます。</span><span class="sxs-lookup"><span data-stu-id="b2de7-115">When a `Yield` statement is reached in the iterator function, `expression` is returned, and the current location in code is retained.</span></span> <span data-ttu-id="b2de7-116">次回、Iterator 関数が呼び出されると、この位置から実行が再開されます。</span><span class="sxs-lookup"><span data-stu-id="b2de7-116">Execution is restarted from that location the next time that the iterator function is called.</span></span>  
  
 <span data-ttu-id="b2de7-117">`Yield` ステートメント内の `expression` の型から、iterator の戻り値の型への暗黙的な変換が存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2de7-117">An implicit conversion must exist from the type of `expression` in the `Yield` statement to the return type of the iterator.</span></span>  
  
 <span data-ttu-id="b2de7-118">`Exit Function` または `Return` ステートメントを使用すると、反復を終了できます。</span><span class="sxs-lookup"><span data-stu-id="b2de7-118">You can use an `Exit Function` or `Return` statement to end the iteration.</span></span>  
  
 <span data-ttu-id="b2de7-119">"Yield" は予約語ではなく、`Iterator` 関数または `Get` アクセサーで使用される場合にのみ特別な意味を持ちます。</span><span class="sxs-lookup"><span data-stu-id="b2de7-119">"Yield" is not a reserved word and has special meaning only when it is used in an `Iterator` function or `Get` accessor.</span></span>  
  
 <span data-ttu-id="b2de7-120">iterator 関数と `Get` アクセサーの詳細については、「[反復子](../../programming-guide/concepts/iterators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2de7-120">For more information about iterator functions and `Get` accessors, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="iterator-functions-and-get-accessors"></a><span data-ttu-id="b2de7-121">iterator 関数と Get アクセサー</span><span class="sxs-lookup"><span data-stu-id="b2de7-121">Iterator Functions and Get Accessors</span></span>  
 <span data-ttu-id="b2de7-122">iterator 関数または `Get` アクセサーの宣言では、次の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2de7-122">The declaration of an iterator function or `Get` accessor must meet the following requirements:</span></span>  
  
- <span data-ttu-id="b2de7-123">[Iterator](../modifiers/iterator.md) 修飾子を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2de7-123">It must include an [Iterator](../modifiers/iterator.md) modifier.</span></span>  
  
- <span data-ttu-id="b2de7-124">戻り値の型は、<xref:System.Collections.IEnumerable>、<xref:System.Collections.Generic.IEnumerable%601>、<xref:System.Collections.IEnumerator>、または <xref:System.Collections.Generic.IEnumerator%601> であることが必要です。</span><span class="sxs-lookup"><span data-stu-id="b2de7-124">The return type must be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
- <span data-ttu-id="b2de7-125">`ByRef` パラメーターを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="b2de7-125">It cannot have any `ByRef` parameters.</span></span>  
  
 <span data-ttu-id="b2de7-126">iterator 関数を、イベント、インスタンス コンストラクター、静的コンストラクター、静的デストラクターで指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="b2de7-126">An iterator function cannot occur in an event, instance constructor, static constructor, or static destructor.</span></span>  
  
 <span data-ttu-id="b2de7-127">iterator 関数は、匿名関数にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b2de7-127">An iterator function can be an anonymous function.</span></span> <span data-ttu-id="b2de7-128">詳細については、「 [反復子](../../programming-guide/concepts/iterators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2de7-128">For more information, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="exception-handling"></a><span data-ttu-id="b2de7-129">例外処理</span><span class="sxs-lookup"><span data-stu-id="b2de7-129">Exception Handling</span></span>  
 <span data-ttu-id="b2de7-130">`Yield` ステートメントは [Try...Catch...Finally ステートメント](try-catch-finally-statement.md)の `Try` ブロック内に指定できます。</span><span class="sxs-lookup"><span data-stu-id="b2de7-130">A `Yield` statement can be inside a `Try` block of a [Try...Catch...Finally Statement](try-catch-finally-statement.md).</span></span> <span data-ttu-id="b2de7-131">`Yield` ステートメントがある `Try` ブロックには、`Catch` ブロックと `Finally` ブロックを記述することができます。</span><span class="sxs-lookup"><span data-stu-id="b2de7-131">A `Try` block that has a `Yield` statement can have `Catch` blocks, and can have a `Finally` block.</span></span>  
  
 <span data-ttu-id="b2de7-132">`Yield` ステートメントを `Catch` ブロックや `Finally` ブロックに記述することはできません。</span><span class="sxs-lookup"><span data-stu-id="b2de7-132">A `Yield` statement cannot be inside a `Catch` block or a `Finally` block.</span></span>  
  
 <span data-ttu-id="b2de7-133">(iterator 関数の外部の) `For Each` 本体で例外がスローされた場合、iterator 関数の `Catch` ブロックは実行されず、iterator 関数の `Finally` ブロックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="b2de7-133">If the `For Each` body (outside of the iterator function) throws an exception, a `Catch` block in the iterator function is not executed, but a `Finally` block in the iterator function is executed.</span></span> <span data-ttu-id="b2de7-134">iterator 関数内の `Catch` ブロックでキャッチされるのは、iterator 関数内で発生した例外だけです。</span><span class="sxs-lookup"><span data-stu-id="b2de7-134">A `Catch` block inside an iterator function catches only exceptions that occur inside the iterator function.</span></span>  
  
## <a name="technical-implementation"></a><span data-ttu-id="b2de7-135">技術的な実装</span><span class="sxs-lookup"><span data-stu-id="b2de7-135">Technical Implementation</span></span>  
 <span data-ttu-id="b2de7-136">次のコードでは、iterator 関数から `IEnumerable (Of String)` を返した後、`IEnumerable (Of String)` の要素を反復処理しています。</span><span class="sxs-lookup"><span data-stu-id="b2de7-136">The following code returns an `IEnumerable (Of String)` from an iterator function and then iterates through the elements of the `IEnumerable (Of String)`.</span></span>  
  
```vb  
Dim elements As IEnumerable(Of String) = MyIteratorFunction()  
    …  
For Each element As String In elements  
Next  
```  
  
 <span data-ttu-id="b2de7-137">`MyIteratorFunction` への呼び出しでは、関数の本体は実行されません。</span><span class="sxs-lookup"><span data-stu-id="b2de7-137">The call to `MyIteratorFunction` doesn't execute the body of the function.</span></span> <span data-ttu-id="b2de7-138">この呼び出しでは、`IEnumerable(Of String)` が `elements` 変数に返されます。</span><span class="sxs-lookup"><span data-stu-id="b2de7-138">Instead the call returns an `IEnumerable(Of String)` into the `elements` variable.</span></span>  
  
 <span data-ttu-id="b2de7-139">`For Each` ループの反復処理では、<xref:System.Collections.IEnumerator.MoveNext%2A> について `elements` メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="b2de7-139">On an iteration of the `For Each` loop, the <xref:System.Collections.IEnumerator.MoveNext%2A> method is called for `elements`.</span></span> <span data-ttu-id="b2de7-140">この呼び出しでは、次の `MyIteratorFunction` ステートメントに到達するまで、`Yield` の本体が実行されます。</span><span class="sxs-lookup"><span data-stu-id="b2de7-140">This call executes the body of `MyIteratorFunction` until the next `Yield` statement is reached.</span></span> <span data-ttu-id="b2de7-141">`Yield` ステートメントによって、ループ本体で使用するための `element` 変数の値だけでなく、`IEnumerable (Of String)` である要素の <xref:System.Collections.Generic.IEnumerator%601.Current%2A> プロパティも判断する式が返されます。</span><span class="sxs-lookup"><span data-stu-id="b2de7-141">The `Yield` statement returns an expression that determines not only the value of the `element` variable for consumption by the loop body but also the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property of elements, which is an `IEnumerable (Of String)`.</span></span>  
  
 <span data-ttu-id="b2de7-142">`For Each` ループの以降の各反復処理では、反復子本体の実行が中断した場所から続行し、`Yield` ステートメントに到達したときに再度停止します。</span><span class="sxs-lookup"><span data-stu-id="b2de7-142">On each subsequent iteration of the `For Each` loop, the execution of the iterator body continues from where it left off, again stopping when it reaches a `Yield` statement.</span></span> <span data-ttu-id="b2de7-143">iterator 関数または `Return` または `Exit Function` ステートメントの最後に到達すると、`For Each` ループは完了します。</span><span class="sxs-lookup"><span data-stu-id="b2de7-143">The `For Each` loop completes when the end of the iterator function or a `Return` or `Exit Function` statement is reached.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2de7-144">例</span><span class="sxs-lookup"><span data-stu-id="b2de7-144">Example</span></span>  
 <span data-ttu-id="b2de7-145">次の例では、[For…Next](for-next-statement.md) ループ内に `Yield` ステートメントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b2de7-145">The following example has a `Yield` statement that is inside a [For…Next](for-next-statement.md) loop.</span></span> <span data-ttu-id="b2de7-146">`Main` 内の [For Each](for-each-next-statement.md) ステートメント本体の各反復処理では、`Power` Iterator 関数が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="b2de7-146">Each iteration of the [For Each](for-each-next-statement.md) statement body in `Main` creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="b2de7-147">Iterator 関数を呼び出すごとに、`Yield` ステートメントの次の実行に進みます。これは、`For…Next` ループの次の反復処理で行われます。</span><span class="sxs-lookup"><span data-stu-id="b2de7-147">Each call to the iterator function proceeds to the next execution of the `Yield` statement, which occurs during the next iteration of the `For…Next` loop.</span></span>  
  
 <span data-ttu-id="b2de7-148">Iterator メソッドの戻り値の型は、反復子インターフェイス型の <xref:System.Collections.Generic.IEnumerable%601> です。</span><span class="sxs-lookup"><span data-stu-id="b2de7-148">The return type of the iterator method is <xref:System.Collections.Generic.IEnumerable%601>, an iterator interface type.</span></span> <span data-ttu-id="b2de7-149">Iterator メソッドが呼び出されると、数値の累乗を含む列挙可能なオブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="b2de7-149">When the iterator method is called, it returns an enumerable object that contains the powers of a number.</span></span>  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a><span data-ttu-id="b2de7-150">例</span><span class="sxs-lookup"><span data-stu-id="b2de7-150">Example</span></span>  
 <span data-ttu-id="b2de7-151">次の例は、反復子である `Get` アクセサーを示しています。</span><span class="sxs-lookup"><span data-stu-id="b2de7-151">The following example demonstrates a `Get` accessor that is an iterator.</span></span> <span data-ttu-id="b2de7-152">プロパティの宣言には、`Iterator` 修飾子が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b2de7-152">The property declaration includes an `Iterator` modifier.</span></span>  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 <span data-ttu-id="b2de7-153">その他の例については、「[反復子](../../programming-guide/concepts/iterators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2de7-153">For additional examples, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2de7-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="b2de7-154">See also</span></span>

- [<span data-ttu-id="b2de7-155">ステートメント</span><span class="sxs-lookup"><span data-stu-id="b2de7-155">Statements</span></span>](index.md)
