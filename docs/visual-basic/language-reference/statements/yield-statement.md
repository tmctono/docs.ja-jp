---
title: Yield ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Yield
helpviewer_keywords:
- iterators, Yield statement [Visual Basic]
- iterators [Visual Basic]
- Yield statement [Visual Basic]
ms.assetid: f33126c5-d7c4-43e2-8e36-4ae3f0703d97
ms.openlocfilehash: 645b8c4908095bc8d38c47836658325c9b47a569
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64615063"
---
# <a name="yield-statement-visual-basic"></a><span data-ttu-id="e3bd9-102">Yield ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e3bd9-102">Yield Statement (Visual Basic)</span></span>
<span data-ttu-id="e3bd9-103">コレクションの次の要素の送信、`For Each...Next`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="e3bd9-103">Sends the next element of a collection to a `For Each...Next` statement.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3bd9-104">構文</span><span class="sxs-lookup"><span data-stu-id="e3bd9-104">Syntax</span></span>  
  
```  
Yield expression  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3bd9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e3bd9-105">Parameters</span></span>  
  
|<span data-ttu-id="e3bd9-106">用語</span><span class="sxs-lookup"><span data-stu-id="e3bd9-106">Term</span></span>|<span data-ttu-id="e3bd9-107">定義</span><span class="sxs-lookup"><span data-stu-id="e3bd9-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="e3bd9-108">必須。</span><span class="sxs-lookup"><span data-stu-id="e3bd9-108">Required.</span></span> <span data-ttu-id="e3bd9-109">反復子関数の型に暗黙的に変換される式または`Get`アクセサーを含む、`Yield`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="e3bd9-109">An expression that is implicitly convertible to the type of the iterator function or `Get` accessor that contains the `Yield` statement.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e3bd9-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="e3bd9-110">Remarks</span></span>  
 <span data-ttu-id="e3bd9-111">`Yield`ステートメントは、一度にコレクションの 1 つの要素を返します。</span><span class="sxs-lookup"><span data-stu-id="e3bd9-111">The `Yield` statement returns one element of a collection at a time.</span></span> <span data-ttu-id="e3bd9-112">`Yield`ステートメントを反復子関数に含めるまたは`Get`アクセサーをコレクションに対するカスタム イテレーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="e3bd9-112">The `Yield` statement is included in an iterator function or `Get` accessor, which perform custom iterations over a collection.</span></span>  
  
 <span data-ttu-id="e3bd9-113">使用して、反復子関数を使用する、[ごとにしています.次のステートメントの](../../../visual-basic/language-reference/statements/for-each-next-statement.md)または LINQ クエリ。</span><span class="sxs-lookup"><span data-stu-id="e3bd9-113">You consume an iterator function by using a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md) or a LINQ query.</span></span> <span data-ttu-id="e3bd9-114">各反復処理、`For Each`ループが反復子関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e3bd9-114">Each iteration of the `For Each` loop calls the iterator function.</span></span> <span data-ttu-id="e3bd9-115">ときに、 `Yield` 、反復子関数のステートメントに達する`expression`返されるとコードの現在位置が保持されます。</span><span class="sxs-lookup"><span data-stu-id="e3bd9-115">When a `Yield` statement is reached in the iterator function, `expression` is returned, and the current location in code is retained.</span></span> <span data-ttu-id="e3bd9-116">次回、Iterator 関数が呼び出されると、この位置から実行が再開されます。</span><span class="sxs-lookup"><span data-stu-id="e3bd9-116">Execution is restarted from that location the next time that the iterator function is called.</span></span>  
  
 <span data-ttu-id="e3bd9-117">型からの暗黙的な変換が存在する必要があります`expression`で、`Yield`ステートメントを反復子の戻り値の型。</span><span class="sxs-lookup"><span data-stu-id="e3bd9-117">An implicit conversion must exist from the type of `expression` in the `Yield` statement to the return type of the iterator.</span></span>  
  
 <span data-ttu-id="e3bd9-118">使用することができます、`Exit Function`または`Return`ステートメント、反復を終了します。</span><span class="sxs-lookup"><span data-stu-id="e3bd9-118">You can use an `Exit Function` or `Return` statement to end the iteration.</span></span>  
  
 <span data-ttu-id="e3bd9-119">"Yield"予約語ではないで使用されている場合にのみ、特別な意味を持つ、`Iterator`関数または`Get`アクセサー。</span><span class="sxs-lookup"><span data-stu-id="e3bd9-119">"Yield" is not a reserved word and has special meaning only when it is used in an `Iterator` function or `Get` accessor.</span></span>  
  
 <span data-ttu-id="e3bd9-120">反復子関数の詳細については、`Get`アクセサーを参照してください[反復子](../../programming-guide/concepts/iterators.md)します。</span><span class="sxs-lookup"><span data-stu-id="e3bd9-120">For more information about iterator functions and `Get` accessors, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="iterator-functions-and-get-accessors"></a><span data-ttu-id="e3bd9-121">反復子関数と Get アクセサー</span><span class="sxs-lookup"><span data-stu-id="e3bd9-121">Iterator Functions and Get Accessors</span></span>  
 <span data-ttu-id="e3bd9-122">反復子関数の宣言または`Get`アクセサーは、次の要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3bd9-122">The declaration of an iterator function or `Get` accessor must meet the following requirements:</span></span>  
  
- <span data-ttu-id="e3bd9-123">含める必要があります、[反復子](../../../visual-basic/language-reference/modifiers/iterator.md)修飾子。</span><span class="sxs-lookup"><span data-stu-id="e3bd9-123">It must include an [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md) modifier.</span></span>  
  
- <span data-ttu-id="e3bd9-124">戻り値の型は、<xref:System.Collections.IEnumerable>、<xref:System.Collections.Generic.IEnumerable%601>、<xref:System.Collections.IEnumerator>、または <xref:System.Collections.Generic.IEnumerator%601> であることが必要です。</span><span class="sxs-lookup"><span data-stu-id="e3bd9-124">The return type must be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
- <span data-ttu-id="e3bd9-125">いずれかを持つことはできません`ByRef`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="e3bd9-125">It cannot have any `ByRef` parameters.</span></span>  
  
 <span data-ttu-id="e3bd9-126">反復子関数は、イベント、インスタンス コンス トラクター、静的コンス トラクターまたは静的デストラクターで発生することはできません。</span><span class="sxs-lookup"><span data-stu-id="e3bd9-126">An iterator function cannot occur in an event, instance constructor, static constructor, or static destructor.</span></span>  
  
 <span data-ttu-id="e3bd9-127">反復子関数では、匿名関数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e3bd9-127">An iterator function can be an anonymous function.</span></span> <span data-ttu-id="e3bd9-128">詳細については、「 [反復子](../../programming-guide/concepts/iterators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3bd9-128">For more information, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="exception-handling"></a><span data-ttu-id="e3bd9-129">例外処理</span><span class="sxs-lookup"><span data-stu-id="e3bd9-129">Exception Handling</span></span>  
 <span data-ttu-id="e3bd9-130">A`Yield`内でステートメントを使用できます、`Try`のブロックを[お試しください.キャッチしてください.Finally ステートメント](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="e3bd9-130">A `Yield` statement can be inside a `Try` block of a [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span> <span data-ttu-id="e3bd9-131">A`Try`を持つブロックを`Yield`ステートメントを持つことができます`Catch`ブロック、および、持つことができます、`Finally`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="e3bd9-131">A `Try` block that has a `Yield` statement can have `Catch` blocks, and can have a `Finally` block.</span></span>  
  
 <span data-ttu-id="e3bd9-132">A`Yield`内でステートメントを使用できない、`Catch`ブロックまたは`Finally`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="e3bd9-132">A `Yield` statement cannot be inside a `Catch` block or a `Finally` block.</span></span>  
  
 <span data-ttu-id="e3bd9-133">場合、`For Each`本体 (関数の外側で、反復子)、例外がスロー、`Catch`反復子関数のブロックは実行されませんが、`Finally`反復子関数でのブロックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="e3bd9-133">If the `For Each` body (outside of the iterator function) throws an exception, a `Catch` block in the iterator function is not executed, but a `Finally` block in the iterator function is executed.</span></span> <span data-ttu-id="e3bd9-134">A`Catch`反復子関数の内側のブロックは、反復子関数内で発生する例外のみをキャッチします。</span><span class="sxs-lookup"><span data-stu-id="e3bd9-134">A `Catch` block inside an iterator function catches only exceptions that occur inside the iterator function.</span></span>  
  
## <a name="technical-implementation"></a><span data-ttu-id="e3bd9-135">技術的な実装</span><span class="sxs-lookup"><span data-stu-id="e3bd9-135">Technical Implementation</span></span>  
 <span data-ttu-id="e3bd9-136">次のコードを返します、`IEnumerable (Of String)`を反復子関数からの要素を反復処理し、`IEnumerable (Of String)`します。</span><span class="sxs-lookup"><span data-stu-id="e3bd9-136">The following code returns an `IEnumerable (Of String)` from an iterator function and then iterates through the elements of the `IEnumerable (Of String)`.</span></span>  
  
```vb  
Dim elements As IEnumerable(Of String) = MyIteratorFunction()  
    …  
For Each element As String In elements  
Next  
```  
  
 <span data-ttu-id="e3bd9-137">呼び出し`MyIteratorFunction`関数の本体は実行されません。</span><span class="sxs-lookup"><span data-stu-id="e3bd9-137">The call to `MyIteratorFunction` doesn't execute the body of the function.</span></span> <span data-ttu-id="e3bd9-138">この呼び出しでは、`IEnumerable(Of String)` が `elements` 変数に返されます。</span><span class="sxs-lookup"><span data-stu-id="e3bd9-138">Instead the call returns an `IEnumerable(Of String)` into the `elements` variable.</span></span>  
  
 <span data-ttu-id="e3bd9-139">`For Each` ループの反復処理では、<xref:System.Collections.IEnumerator.MoveNext%2A> について `elements` メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e3bd9-139">On an iteration of the `For Each` loop, the <xref:System.Collections.IEnumerator.MoveNext%2A> method is called for `elements`.</span></span> <span data-ttu-id="e3bd9-140">この呼び出しでは、次の `MyIteratorFunction` ステートメントに到達するまで、`Yield` の本体が実行されます。</span><span class="sxs-lookup"><span data-stu-id="e3bd9-140">This call executes the body of `MyIteratorFunction` until the next `Yield` statement is reached.</span></span> <span data-ttu-id="e3bd9-141">`Yield`ステートメントだけでなくの値を決定する式を返します、`element`ループの本体で使用するための変数も、<xref:System.Collections.Generic.IEnumerator%601.Current%2A>これは、要素のプロパティ、`IEnumerable (Of String)`します。</span><span class="sxs-lookup"><span data-stu-id="e3bd9-141">The `Yield` statement returns an expression that determines not only the value of the `element` variable for consumption by the loop body but also the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property of elements, which is an `IEnumerable (Of String)`.</span></span>  
  
 <span data-ttu-id="e3bd9-142">`For Each` ループの以降の各反復処理では、反復子本体の実行が中断した場所から続行し、`Yield` ステートメントに到達したときに再度停止します。</span><span class="sxs-lookup"><span data-stu-id="e3bd9-142">On each subsequent iteration of the `For Each` loop, the execution of the iterator body continues from where it left off, again stopping when it reaches a `Yield` statement.</span></span> <span data-ttu-id="e3bd9-143">`For Each`ループが完了するときに、反復子関数の末尾または`Return`または`Exit Function`ステートメントに達する。</span><span class="sxs-lookup"><span data-stu-id="e3bd9-143">The `For Each` loop completes when the end of the iterator function or a `Return` or `Exit Function` statement is reached.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e3bd9-144">例</span><span class="sxs-lookup"><span data-stu-id="e3bd9-144">Example</span></span>  
 <span data-ttu-id="e3bd9-145">次の例は、`Yield`内にあるステートメント、[をしています.[次へ]](../../../visual-basic/language-reference/statements/for-next-statement.md)ループします。</span><span class="sxs-lookup"><span data-stu-id="e3bd9-145">The following example has a `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="e3bd9-146">各反復処理、[各](../../../visual-basic/language-reference/statements/for-each-next-statement.md)ステートメント本体で`Main`への呼び出しを作成、 `Power` iterator 関数。</span><span class="sxs-lookup"><span data-stu-id="e3bd9-146">Each iteration of the [For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement body in `Main` creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="e3bd9-147">Iterator 関数を呼び出すごとに、`Yield` ステートメントの次の実行に進みます。これは、`For…Next` ループの次の反復処理で行われます。</span><span class="sxs-lookup"><span data-stu-id="e3bd9-147">Each call to the iterator function proceeds to the next execution of the `Yield` statement, which occurs during the next iteration of the `For…Next` loop.</span></span>  
  
 <span data-ttu-id="e3bd9-148">Iterator メソッドの戻り値の型は<xref:System.Collections.Generic.IEnumerable%601>、反復子インターフェイス型。</span><span class="sxs-lookup"><span data-stu-id="e3bd9-148">The return type of the iterator method is <xref:System.Collections.Generic.IEnumerable%601>, an iterator interface type.</span></span> <span data-ttu-id="e3bd9-149">Iterator メソッドが呼び出されると、数値の累乗を含む列挙可能なオブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="e3bd9-149">When the iterator method is called, it returns an enumerable object that contains the powers of a number.</span></span>  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a><span data-ttu-id="e3bd9-150">例</span><span class="sxs-lookup"><span data-stu-id="e3bd9-150">Example</span></span>  
 <span data-ttu-id="e3bd9-151">次の例は、反復子である `Get` アクセサーを示しています。</span><span class="sxs-lookup"><span data-stu-id="e3bd9-151">The following example demonstrates a `Get` accessor that is an iterator.</span></span> <span data-ttu-id="e3bd9-152">プロパティ宣言が含まれる、`Iterator`修飾子。</span><span class="sxs-lookup"><span data-stu-id="e3bd9-152">The property declaration includes an `Iterator` modifier.</span></span>  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 <span data-ttu-id="e3bd9-153">その他の例では、次を参照してください。[反復子](../../programming-guide/concepts/iterators.md)します。</span><span class="sxs-lookup"><span data-stu-id="e3bd9-153">For additional examples, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3bd9-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="e3bd9-154">See also</span></span>

- [<span data-ttu-id="e3bd9-155">ステートメント</span><span class="sxs-lookup"><span data-stu-id="e3bd9-155">Statements</span></span>](../../../visual-basic/language-reference/statements/index.md)
