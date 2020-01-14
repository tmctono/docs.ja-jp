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
ms.openlocfilehash: 72a8dafdc5aa834a644e1e70a309cfc0827b5fdf
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352728"
---
# <a name="yield-statement-visual-basic"></a><span data-ttu-id="dadcd-102">Yield ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dadcd-102">Yield Statement (Visual Basic)</span></span>
<span data-ttu-id="dadcd-103">コレクションの次の要素を `For Each...Next` ステートメントに送信します。</span><span class="sxs-lookup"><span data-stu-id="dadcd-103">Sends the next element of a collection to a `For Each...Next` statement.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dadcd-104">構文</span><span class="sxs-lookup"><span data-stu-id="dadcd-104">Syntax</span></span>  
  
```vb  
Yield expression  
```  
  
## <a name="parameters"></a><span data-ttu-id="dadcd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dadcd-105">Parameters</span></span>  
  
|<span data-ttu-id="dadcd-106">用語</span><span class="sxs-lookup"><span data-stu-id="dadcd-106">Term</span></span>|<span data-ttu-id="dadcd-107">Definition</span><span class="sxs-lookup"><span data-stu-id="dadcd-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="dadcd-108">必須。</span><span class="sxs-lookup"><span data-stu-id="dadcd-108">Required.</span></span> <span data-ttu-id="dadcd-109">`Yield` ステートメントを含む反復子関数または `Get` アクセサーの型に暗黙的に変換できる式。</span><span class="sxs-lookup"><span data-stu-id="dadcd-109">An expression that is implicitly convertible to the type of the iterator function or `Get` accessor that contains the `Yield` statement.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dadcd-110">コメント</span><span class="sxs-lookup"><span data-stu-id="dadcd-110">Remarks</span></span>  
 <span data-ttu-id="dadcd-111">`Yield` ステートメントは、コレクションの1つの要素を一度に返します。</span><span class="sxs-lookup"><span data-stu-id="dadcd-111">The `Yield` statement returns one element of a collection at a time.</span></span> <span data-ttu-id="dadcd-112">`Yield` ステートメントは、コレクションに対してカスタムの反復処理を実行する反復子関数または `Get` アクセサーに含まれています。</span><span class="sxs-lookup"><span data-stu-id="dadcd-112">The `Yield` statement is included in an iterator function or `Get` accessor, which perform custom iterations over a collection.</span></span>  
  
 <span data-ttu-id="dadcd-113">For Each を使用して、iterator 関数を使用します。 [次のステートメント](../../../visual-basic/language-reference/statements/for-each-next-statement.md)または LINQ クエリ。</span><span class="sxs-lookup"><span data-stu-id="dadcd-113">You consume an iterator function by using a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md) or a LINQ query.</span></span> <span data-ttu-id="dadcd-114">`For Each` ループの各反復処理では、iterator 関数が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="dadcd-114">Each iteration of the `For Each` loop calls the iterator function.</span></span> <span data-ttu-id="dadcd-115">Iterator 関数で `Yield` ステートメントに到達すると、`expression` が返され、コード内の現在の場所が保持されます。</span><span class="sxs-lookup"><span data-stu-id="dadcd-115">When a `Yield` statement is reached in the iterator function, `expression` is returned, and the current location in code is retained.</span></span> <span data-ttu-id="dadcd-116">次回、反復子メソッドが呼び出されると、この位置から実行が再開されます。</span><span class="sxs-lookup"><span data-stu-id="dadcd-116">Execution is restarted from that location the next time that the iterator function is called.</span></span>  
  
 <span data-ttu-id="dadcd-117">`Yield` ステートメントの `expression` の型から反復子の戻り値の型への暗黙的な変換が存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dadcd-117">An implicit conversion must exist from the type of `expression` in the `Yield` statement to the return type of the iterator.</span></span>  
  
 <span data-ttu-id="dadcd-118">`Exit Function` または `Return` ステートメントを使用して、イテレーションを終了できます。</span><span class="sxs-lookup"><span data-stu-id="dadcd-118">You can use an `Exit Function` or `Return` statement to end the iteration.</span></span>  
  
 <span data-ttu-id="dadcd-119">"Yield" は予約語ではなく、`Iterator` 関数または `Get` アクセサーで使用される場合にのみ特別な意味を持ちます。</span><span class="sxs-lookup"><span data-stu-id="dadcd-119">"Yield" is not a reserved word and has special meaning only when it is used in an `Iterator` function or `Get` accessor.</span></span>  
  
 <span data-ttu-id="dadcd-120">反復子関数と `Get` アクセサーの詳細については、「[反復子](../../programming-guide/concepts/iterators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dadcd-120">For more information about iterator functions and `Get` accessors, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="iterator-functions-and-get-accessors"></a><span data-ttu-id="dadcd-121">反復子関数と Get アクセサー</span><span class="sxs-lookup"><span data-stu-id="dadcd-121">Iterator Functions and Get Accessors</span></span>  
 <span data-ttu-id="dadcd-122">反復子関数または `Get` アクセサーの宣言は、次の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dadcd-122">The declaration of an iterator function or `Get` accessor must meet the following requirements:</span></span>  
  
- <span data-ttu-id="dadcd-123">[反復子](../../../visual-basic/language-reference/modifiers/iterator.md)修飾子を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="dadcd-123">It must include an [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md) modifier.</span></span>  
  
- <span data-ttu-id="dadcd-124">戻り値の型は、<xref:System.Collections.IEnumerable>、<xref:System.Collections.Generic.IEnumerable%601>、<xref:System.Collections.IEnumerator>、または <xref:System.Collections.Generic.IEnumerator%601> であることが必要です。</span><span class="sxs-lookup"><span data-stu-id="dadcd-124">The return type must be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
- <span data-ttu-id="dadcd-125">`ByRef` パラメーターを持つことはできません。</span><span class="sxs-lookup"><span data-stu-id="dadcd-125">It cannot have any `ByRef` parameters.</span></span>  
  
 <span data-ttu-id="dadcd-126">反復子関数は、イベント、インスタンスコンストラクター、静的コンストラクター、または静的デストラクターでは実行できません。</span><span class="sxs-lookup"><span data-stu-id="dadcd-126">An iterator function cannot occur in an event, instance constructor, static constructor, or static destructor.</span></span>  
  
 <span data-ttu-id="dadcd-127">反復子関数は、匿名関数にすることができます。</span><span class="sxs-lookup"><span data-stu-id="dadcd-127">An iterator function can be an anonymous function.</span></span> <span data-ttu-id="dadcd-128">詳細については、「[反復子](../../programming-guide/concepts/iterators.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dadcd-128">For more information, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="exception-handling"></a><span data-ttu-id="dadcd-129">例外処理</span><span class="sxs-lookup"><span data-stu-id="dadcd-129">Exception Handling</span></span>  
 <span data-ttu-id="dadcd-130">`Yield` ステートメントは、Try の `Try` ブロック内にある場合があります.. [.キャッチ...Finally ステートメント](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="dadcd-130">A `Yield` statement can be inside a `Try` block of a [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span> <span data-ttu-id="dadcd-131">`Yield` ステートメントを持つ `Try` ブロックは `Catch` ブロックを持つことができ、`Finally` ブロックを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="dadcd-131">A `Try` block that has a `Yield` statement can have `Catch` blocks, and can have a `Finally` block.</span></span>  
  
 <span data-ttu-id="dadcd-132">`Yield` ステートメントを `Catch` ブロックまたは `Finally` ブロックの内部に指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="dadcd-132">A `Yield` statement cannot be inside a `Catch` block or a `Finally` block.</span></span>  
  
 <span data-ttu-id="dadcd-133">`For Each` 本体 (iterator 関数の外側) が例外をスローした場合、iterator 関数の `Catch` ブロックは実行されませんが、iterator 関数の `Finally` ブロックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="dadcd-133">If the `For Each` body (outside of the iterator function) throws an exception, a `Catch` block in the iterator function is not executed, but a `Finally` block in the iterator function is executed.</span></span> <span data-ttu-id="dadcd-134">Iterator 関数内の `Catch` ブロックは、iterator 関数内で発生した例外のみをキャッチします。</span><span class="sxs-lookup"><span data-stu-id="dadcd-134">A `Catch` block inside an iterator function catches only exceptions that occur inside the iterator function.</span></span>  
  
## <a name="technical-implementation"></a><span data-ttu-id="dadcd-135">技術的な実装</span><span class="sxs-lookup"><span data-stu-id="dadcd-135">Technical Implementation</span></span>  
 <span data-ttu-id="dadcd-136">次のコードは、iterator 関数から `IEnumerable (Of String)` を返し、`IEnumerable (Of String)`の要素を反復処理します。</span><span class="sxs-lookup"><span data-stu-id="dadcd-136">The following code returns an `IEnumerable (Of String)` from an iterator function and then iterates through the elements of the `IEnumerable (Of String)`.</span></span>  
  
```vb  
Dim elements As IEnumerable(Of String) = MyIteratorFunction()  
    …  
For Each element As String In elements  
Next  
```  
  
 <span data-ttu-id="dadcd-137">`MyIteratorFunction` の呼び出しでは、関数の本体は実行されません。</span><span class="sxs-lookup"><span data-stu-id="dadcd-137">The call to `MyIteratorFunction` doesn't execute the body of the function.</span></span> <span data-ttu-id="dadcd-138">この呼び出しでは、`IEnumerable(Of String)` が `elements` 変数に返されます。</span><span class="sxs-lookup"><span data-stu-id="dadcd-138">Instead the call returns an `IEnumerable(Of String)` into the `elements` variable.</span></span>  
  
 <span data-ttu-id="dadcd-139">`For Each` ループの反復処理では、<xref:System.Collections.IEnumerator.MoveNext%2A> について `elements` メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="dadcd-139">On an iteration of the `For Each` loop, the <xref:System.Collections.IEnumerator.MoveNext%2A> method is called for `elements`.</span></span> <span data-ttu-id="dadcd-140">この呼び出しでは、次の `MyIteratorFunction` ステートメントに到達するまで、`Yield` の本体が実行されます。</span><span class="sxs-lookup"><span data-stu-id="dadcd-140">This call executes the body of `MyIteratorFunction` until the next `Yield` statement is reached.</span></span> <span data-ttu-id="dadcd-141">`Yield` ステートメントは、ループ本体で使用する `element` 変数の値だけでなく、`IEnumerable (Of String)`である要素の <xref:System.Collections.Generic.IEnumerator%601.Current%2A> プロパティも決定する式を返します。</span><span class="sxs-lookup"><span data-stu-id="dadcd-141">The `Yield` statement returns an expression that determines not only the value of the `element` variable for consumption by the loop body but also the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property of elements, which is an `IEnumerable (Of String)`.</span></span>  
  
 <span data-ttu-id="dadcd-142">`For Each` ループの以降の各反復処理では、反復子本体の実行が中断した場所から続行し、`Yield` ステートメントに到達したときに再度停止します。</span><span class="sxs-lookup"><span data-stu-id="dadcd-142">On each subsequent iteration of the `For Each` loop, the execution of the iterator body continues from where it left off, again stopping when it reaches a `Yield` statement.</span></span> <span data-ttu-id="dadcd-143">反復子関数の末尾、または `Return` または `Exit Function` ステートメントに到達すると、`For Each` ループは完了します。</span><span class="sxs-lookup"><span data-stu-id="dadcd-143">The `For Each` loop completes when the end of the iterator function or a `Return` or `Exit Function` statement is reached.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dadcd-144">例</span><span class="sxs-lookup"><span data-stu-id="dadcd-144">Example</span></span>  
 <span data-ttu-id="dadcd-145">次の例では、For... の内部に `Yield` ステートメントがあります。 [次](../../../visual-basic/language-reference/statements/for-next-statement.md)のループ。</span><span class="sxs-lookup"><span data-stu-id="dadcd-145">The following example has a `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="dadcd-146">`Main` 内の[各](../../../visual-basic/language-reference/statements/for-each-next-statement.md)ステートメント本体の各反復処理では、`Power` iterator 関数の呼び出しが作成されます。</span><span class="sxs-lookup"><span data-stu-id="dadcd-146">Each iteration of the [For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement body in `Main` creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="dadcd-147">Iterator 関数を呼び出すごとに、`Yield` ステートメントの次の実行に進みます。これは、`For…Next` ループの次の反復処理で行われます。</span><span class="sxs-lookup"><span data-stu-id="dadcd-147">Each call to the iterator function proceeds to the next execution of the `Yield` statement, which occurs during the next iteration of the `For…Next` loop.</span></span>  
  
 <span data-ttu-id="dadcd-148">Iterator メソッドの戻り値の型は <xref:System.Collections.Generic.IEnumerable%601>であり、反復子インターフェイス型です。</span><span class="sxs-lookup"><span data-stu-id="dadcd-148">The return type of the iterator method is <xref:System.Collections.Generic.IEnumerable%601>, an iterator interface type.</span></span> <span data-ttu-id="dadcd-149">反復子メソッドが呼び出されると、数値の累乗を含む列挙可能なオブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="dadcd-149">When the iterator method is called, it returns an enumerable object that contains the powers of a number.</span></span>  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a><span data-ttu-id="dadcd-150">例</span><span class="sxs-lookup"><span data-stu-id="dadcd-150">Example</span></span>  
 <span data-ttu-id="dadcd-151">次の例は、反復子である `Get` アクセサーを示しています。</span><span class="sxs-lookup"><span data-stu-id="dadcd-151">The following example demonstrates a `Get` accessor that is an iterator.</span></span> <span data-ttu-id="dadcd-152">プロパティの宣言には、`Iterator` 修飾子が含まれています。</span><span class="sxs-lookup"><span data-stu-id="dadcd-152">The property declaration includes an `Iterator` modifier.</span></span>  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 <span data-ttu-id="dadcd-153">その他の例については、「[反復子](../../programming-guide/concepts/iterators.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dadcd-153">For additional examples, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dadcd-154">参照</span><span class="sxs-lookup"><span data-stu-id="dadcd-154">See also</span></span>

- [<span data-ttu-id="dadcd-155">ステートメント</span><span class="sxs-lookup"><span data-stu-id="dadcd-155">Statements</span></span>](../../../visual-basic/language-reference/statements/index.md)
