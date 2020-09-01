---
description: コンテキスト キーワード yield - C# リファレンス
title: コンテキスト キーワード yield - C# リファレンス
ms.date: 07/20/2015
f1_keywords:
- yield
- yield_CSharpKeyword
helpviewer_keywords:
- yield keyword [C#]
ms.assetid: 1089194f-9e53-46a2-8642-53ccbe9d414d
ms.openlocfilehash: c8caf7e34397faf9f7085d6634287cffcb37eb08
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89141882"
---
# <a name="yield-c-reference"></a><span data-ttu-id="e44da-103">yield (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="e44da-103">yield (C# Reference)</span></span>

<span data-ttu-id="e44da-104">ステートメントで `yield` [コンテキスト キーワード](index.md#contextual-keywords)を使用した場合、メソッド、演算子、または `get` アクセサーが反復子であることを示します。</span><span class="sxs-lookup"><span data-stu-id="e44da-104">When you use the `yield` [contextual keyword](index.md#contextual-keywords) in a statement, you indicate that the method, operator, or `get` accessor in which it appears is an iterator.</span></span> <span data-ttu-id="e44da-105">`yield` を使用して反復子を定義すると、カスタム コレクション型の <xref:System.Collections.Generic.IEnumerator%601> および <xref:System.Collections.IEnumerable> パターンを実装するときに明示的な余分なクラス (列挙の状態を保持するクラス。たとえば <xref:System.Collections.IEnumerator> を参照) が不要になります。</span><span class="sxs-lookup"><span data-stu-id="e44da-105">Using `yield` to define an iterator removes the need for an explicit extra class (the class that holds the state for an enumeration, see <xref:System.Collections.Generic.IEnumerator%601> for an example) when you implement the <xref:System.Collections.IEnumerable> and <xref:System.Collections.IEnumerator> pattern for a custom collection type.</span></span>

<span data-ttu-id="e44da-106">`yield` ステートメントの 2 つの形式を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="e44da-106">The following example shows the two forms of the `yield` statement.</span></span>

```csharp
yield return <expression>;
yield break;
```

## <a name="remarks"></a><span data-ttu-id="e44da-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="e44da-107">Remarks</span></span>

<span data-ttu-id="e44da-108">各要素を 1 つずつ返すには、`yield return` ステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="e44da-108">You use a `yield return` statement to return each element one at a time.</span></span>

<span data-ttu-id="e44da-109">Iterator メソッドから返されるシーケンスを、[foreach](foreach-in.md) ステートメントまたは LINQ クエリを使って使用することができます。</span><span class="sxs-lookup"><span data-stu-id="e44da-109">The sequence returned from an iterator method can be consumed by using a [foreach](foreach-in.md) statement or LINQ query.</span></span> <span data-ttu-id="e44da-110">`foreach` ループの各イテレーションは、Iterator メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e44da-110">Each iteration of the `foreach` loop calls the iterator method.</span></span> <span data-ttu-id="e44da-111">`yield return` ステートメントが Iterator メソッドに到達すると、`expression` が返され、コードの現在の位置が保持されます。</span><span class="sxs-lookup"><span data-stu-id="e44da-111">When a `yield return` statement is reached in the iterator method, `expression` is returned, and the current location in code is retained.</span></span> <span data-ttu-id="e44da-112">次回、Iterator 関数が呼び出されると、この位置から実行が再開されます。</span><span class="sxs-lookup"><span data-stu-id="e44da-112">Execution is restarted from that location the next time that the iterator function is called.</span></span>

<span data-ttu-id="e44da-113">`yield break` ステートメントを使用すると、反復を終了できます。</span><span class="sxs-lookup"><span data-stu-id="e44da-113">You can use a `yield break` statement to end the iteration.</span></span>

<span data-ttu-id="e44da-114">反復子について詳しくは、「[Iterators](../../iterators.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e44da-114">For more information about iterators, see [Iterators](../../iterators.md).</span></span>

## <a name="iterator-methods-and-get-accessors"></a><span data-ttu-id="e44da-115">Iterator メソッドと get アクセサー</span><span class="sxs-lookup"><span data-stu-id="e44da-115">Iterator methods and get accessors</span></span>

<span data-ttu-id="e44da-116">反復子の宣言は、次の要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="e44da-116">The declaration of an iterator must meet the following requirements:</span></span>

- <span data-ttu-id="e44da-117">戻り値の型は、<xref:System.Collections.IEnumerable>、<xref:System.Collections.Generic.IEnumerable%601>、<xref:System.Collections.IEnumerator>、または <xref:System.Collections.Generic.IEnumerator%601> であることが必要です。</span><span class="sxs-lookup"><span data-stu-id="e44da-117">The return type must be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>

- <span data-ttu-id="e44da-118">この宣言には、[in](in-parameter-modifier.md)、[ref](ref.md)、または [out](out-parameter-modifier.md) パラメーターを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="e44da-118">The declaration can't have any [in](in-parameter-modifier.md) [ref](ref.md) or [out](out-parameter-modifier.md) parameters.</span></span>

<span data-ttu-id="e44da-119">`yield` または <xref:System.Collections.IEnumerable> を返す反復子の <xref:System.Collections.IEnumerator> 型は `object` です。</span><span class="sxs-lookup"><span data-stu-id="e44da-119">The `yield` type of an iterator that returns <xref:System.Collections.IEnumerable> or <xref:System.Collections.IEnumerator> is `object`.</span></span>  <span data-ttu-id="e44da-120">反復子が <xref:System.Collections.Generic.IEnumerable%601> または <xref:System.Collections.Generic.IEnumerator%601> を返す場合、`yield return` ステートメント内の式の型から、ジェネリック型パラメーターへの暗黙的な変換が存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e44da-120">If the iterator returns <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Collections.Generic.IEnumerator%601>, there must be an implicit conversion from the type of the expression in the `yield return` statement to the generic type parameter .</span></span>

<span data-ttu-id="e44da-121">`yield return` または `yield break` ステートメントを以下に含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="e44da-121">You can't include a `yield return` or `yield break` statement in:</span></span>

- <span data-ttu-id="e44da-122">[ラムダ式](../operators/lambda-expressions.md)および[匿名メソッド](../operators/delegate-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="e44da-122">[Lambda expressions](../operators/lambda-expressions.md) and [anonymous methods](../operators/delegate-operator.md).</span></span>

- <span data-ttu-id="e44da-123">unsafe ブロックを含むメソッド。</span><span class="sxs-lookup"><span data-stu-id="e44da-123">Methods that contain unsafe blocks.</span></span> <span data-ttu-id="e44da-124">詳しくは、「[unsafe](unsafe.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e44da-124">For more information, see [unsafe](unsafe.md).</span></span>

## <a name="exception-handling"></a><span data-ttu-id="e44da-125">例外処理</span><span class="sxs-lookup"><span data-stu-id="e44da-125">Exception handling</span></span>

<span data-ttu-id="e44da-126">`yield return` ステートメントは、try-catch ブロックに配置することはできません。</span><span class="sxs-lookup"><span data-stu-id="e44da-126">A `yield return` statement can't be located in a try-catch block.</span></span> <span data-ttu-id="e44da-127">`yield return` ステートメントは、try-finally ステートメントの try ブロックに配置できます。</span><span class="sxs-lookup"><span data-stu-id="e44da-127">A `yield return` statement can be located in the try block of a try-finally statement.</span></span>

<span data-ttu-id="e44da-128">`yield break` ステートメントは、try ブロックまたは catch ブロックには配置できますが、finally ブロックには配置できません。</span><span class="sxs-lookup"><span data-stu-id="e44da-128">A `yield break` statement can be located in a try block or a catch block but not a finally block.</span></span>

<span data-ttu-id="e44da-129">`foreach` 本体 (Iterator メソッドの外部) で例外がスローされた場合、Iterator メソッドの `finally` ブロックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="e44da-129">If the `foreach` body (outside of the iterator method) throws an exception, a `finally` block in the iterator method is executed.</span></span>

## <a name="technical-implementation"></a><span data-ttu-id="e44da-130">技術的な実装</span><span class="sxs-lookup"><span data-stu-id="e44da-130">Technical implementation</span></span>

<span data-ttu-id="e44da-131">次のコードは、iterator メソッドから `IEnumerable<string>` を返した後、要素を反復処理します。</span><span class="sxs-lookup"><span data-stu-id="e44da-131">The following code returns an `IEnumerable<string>` from an iterator method and then iterates through its elements.</span></span>

```csharp
IEnumerable<string> elements = MyIteratorMethod();
foreach (string element in elements)
{
   ...
}
```

<span data-ttu-id="e44da-132">`MyIteratorMethod` への呼び出しでは、メソッドの本体は実行されません。</span><span class="sxs-lookup"><span data-stu-id="e44da-132">The call to `MyIteratorMethod` doesn't execute the body of the method.</span></span> <span data-ttu-id="e44da-133">この呼び出しでは、`IEnumerable<string>` が `elements` 変数に返されます。</span><span class="sxs-lookup"><span data-stu-id="e44da-133">Instead the call returns an `IEnumerable<string>` into the `elements` variable.</span></span>

<span data-ttu-id="e44da-134">`foreach` ループの反復処理では、<xref:System.Collections.IEnumerator.MoveNext%2A> について `elements` メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e44da-134">On an iteration of the `foreach` loop, the <xref:System.Collections.IEnumerator.MoveNext%2A> method is called for `elements`.</span></span> <span data-ttu-id="e44da-135">この呼び出しでは、次の `MyIteratorMethod` ステートメントに到達するまで、`yield return` の本体が実行されます。</span><span class="sxs-lookup"><span data-stu-id="e44da-135">This call executes the body of `MyIteratorMethod` until the next `yield return` statement is reached.</span></span> <span data-ttu-id="e44da-136">`yield return` ステートメントによって返される式は、ループ本体による処理に対する `element` 変数の値だけでなく、`IEnumerable<string>` である、`elements` の <xref:System.Collections.Generic.IEnumerator%601.Current%2A> プロパティも決定します。</span><span class="sxs-lookup"><span data-stu-id="e44da-136">The expression returned by the `yield return` statement determines not only the value of the `element` variable for consumption by the loop body but also the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property of `elements`, which is an `IEnumerable<string>`.</span></span>

<span data-ttu-id="e44da-137">`foreach` ループの以降の各反復処理では、反復子本体の実行が中断した場所から続行し、`yield return` ステートメントに到達したときに再度停止します。</span><span class="sxs-lookup"><span data-stu-id="e44da-137">On each subsequent iteration of the `foreach` loop, the execution of the iterator body continues from where it left off, again stopping when it reaches a `yield return` statement.</span></span> <span data-ttu-id="e44da-138">iterator メソッドまたは `foreach` ステートメントの最後に到達すると、`yield break` ループは完了します。</span><span class="sxs-lookup"><span data-stu-id="e44da-138">The `foreach` loop completes when the end of the iterator method or a `yield break` statement is reached.</span></span>

## <a name="example"></a><span data-ttu-id="e44da-139">例</span><span class="sxs-lookup"><span data-stu-id="e44da-139">Example</span></span>

<span data-ttu-id="e44da-140">次の例では、`yield return` ループ内に `for` ステートメントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e44da-140">The following example has a `yield return` statement that's inside a `for` loop.</span></span> <span data-ttu-id="e44da-141">`Main` メソッド内の `foreach` ステートメント本体の各反復処理では、`Power` Iterator 関数が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e44da-141">Each iteration of the `foreach` statement body in the `Main` method creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="e44da-142">Iterator 関数を呼び出すごとに、`yield return` ステートメントの次の実行に進みます。これは、`for` ループの次の反復処理で行われます。</span><span class="sxs-lookup"><span data-stu-id="e44da-142">Each call to the iterator function proceeds to the next execution of the `yield return` statement, which occurs during the next iteration of the `for` loop.</span></span>

<span data-ttu-id="e44da-143">Iterator メソッドの戻り値の型は <xref:System.Collections.IEnumerable> であり、これは反復子インターフェイス型です。</span><span class="sxs-lookup"><span data-stu-id="e44da-143">The return type of the iterator method is <xref:System.Collections.IEnumerable>, which is an iterator interface type.</span></span> <span data-ttu-id="e44da-144">Iterator メソッドが呼び出されると、数値の累乗を含む列挙可能なオブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="e44da-144">When the iterator method is called, it returns an enumerable object that contains the powers of a number.</span></span>

[!code-csharp[csrefKeywordsContextual#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#5)]

## <a name="example"></a><span data-ttu-id="e44da-145">例</span><span class="sxs-lookup"><span data-stu-id="e44da-145">Example</span></span>

<span data-ttu-id="e44da-146">次の例は、反復子である `get` アクセサーを示しています。</span><span class="sxs-lookup"><span data-stu-id="e44da-146">The following example demonstrates a `get` accessor that is an iterator.</span></span> <span data-ttu-id="e44da-147">この例では、各 `yield return` ステートメントがユーザー定義クラスのインスタンスを返します。</span><span class="sxs-lookup"><span data-stu-id="e44da-147">In the example, each `yield return` statement returns an instance of a user-defined class.</span></span>

[!code-csharp[csrefKeywordsContextual#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#21)]

## <a name="c-language-specification"></a><span data-ttu-id="e44da-148">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="e44da-148">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="e44da-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="e44da-149">See also</span></span>

- [<span data-ttu-id="e44da-150">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="e44da-150">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e44da-151">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="e44da-151">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e44da-152">foreach、in</span><span class="sxs-lookup"><span data-stu-id="e44da-152">foreach, in</span></span>](foreach-in.md)
- [<span data-ttu-id="e44da-153">反復子</span><span class="sxs-lookup"><span data-stu-id="e44da-153">Iterators</span></span>](../../iterators.md)
