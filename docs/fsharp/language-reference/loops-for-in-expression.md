---
title: 'ループ: for...in 式'
description: 参照してください方法 F# for….. 式で列挙可能なコレクション内のパターンの一致を反復処理するループ コンストラクトが使用されます。
ms.date: 05/16/2016
ms.openlocfilehash: adaf448a49cf53c63c41f9156d40ee5d1ad3caeb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62024444"
---
# <a name="loops-forin-expression"></a><span data-ttu-id="ad38a-103">ループ: for...in 式</span><span class="sxs-lookup"><span data-stu-id="ad38a-103">Loops: for...in Expression</span></span>

<span data-ttu-id="ad38a-104">このループの構造は、範囲表現、シーケンス、リスト、配列、または列挙型をサポートするその他の構成要素などの列挙可能なコレクション内のパターンの一致を反復処理に使用されます。</span><span class="sxs-lookup"><span data-stu-id="ad38a-104">This looping construct is used to iterate over the matches of a pattern in an enumerable collection such as a range expression, sequence, list, array, or other construct that supports enumeration.</span></span>

## <a name="syntax"></a><span data-ttu-id="ad38a-105">構文</span><span class="sxs-lookup"><span data-stu-id="ad38a-105">Syntax</span></span>

```fsharp
for pattern in enumerable-expression do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="ad38a-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="ad38a-106">Remarks</span></span>

<span data-ttu-id="ad38a-107">`for...in`に式を比較できるように、`for each`他の .NET 言語でステートメントをループ処理する列挙可能なコレクション内の値に使用されています。</span><span class="sxs-lookup"><span data-stu-id="ad38a-107">The `for...in` expression can be compared to the `for each` statement in other .NET languages because it is used to loop over the values in an enumerable collection.</span></span> <span data-ttu-id="ad38a-108">ただし、`for...in`も全体のコレクションを反復処理だけではなくコレクションに対する一致パターンをサポートします。</span><span class="sxs-lookup"><span data-stu-id="ad38a-108">However, `for...in` also supports pattern matching over the collection instead of just iteration over the whole collection.</span></span>

<span data-ttu-id="ad38a-109">列挙可能なコレクションとして、またはを使用して、列挙可能な式を指定することができます、`..`整数型の範囲として、演算子。</span><span class="sxs-lookup"><span data-stu-id="ad38a-109">The enumerable expression can be specified as an enumerable collection or, by using the `..` operator, as a range on an integral type.</span></span> <span data-ttu-id="ad38a-110">列挙可能なコレクションには、リスト、シーケンス、配列、セット、マップ、およびなどが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ad38a-110">Enumerable collections include lists, sequences, arrays, sets, maps, and so on.</span></span> <span data-ttu-id="ad38a-111">実装する任意の型`System.Collections.IEnumerable`ことができます。</span><span class="sxs-lookup"><span data-stu-id="ad38a-111">Any type that implements `System.Collections.IEnumerable` can be used.</span></span>

<span data-ttu-id="ad38a-112">使用して範囲を表現するときに、`..`オペレーターは、次の構文を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="ad38a-112">When you express a range by using the `..` operator, you can use the following syntax.</span></span>

<span data-ttu-id="ad38a-113">*開始*.</span><span class="sxs-lookup"><span data-stu-id="ad38a-113">*start* ..</span></span> <span data-ttu-id="ad38a-114">*[完了] します。*</span><span class="sxs-lookup"><span data-stu-id="ad38a-114">*finish*</span></span>

<span data-ttu-id="ad38a-115">呼ばれる、インクリメントを含むバージョンを使用することもできます、*スキップ*次のコードのようにします。</span><span class="sxs-lookup"><span data-stu-id="ad38a-115">You can also use a version that includes an increment called the *skip*, as in the following code.</span></span>

<span data-ttu-id="ad38a-116">*開始*.</span><span class="sxs-lookup"><span data-stu-id="ad38a-116">*start* ..</span></span> <span data-ttu-id="ad38a-117">*スキップ*.</span><span class="sxs-lookup"><span data-stu-id="ad38a-117">*skip* ..</span></span> <span data-ttu-id="ad38a-118">*[完了] します。*</span><span class="sxs-lookup"><span data-stu-id="ad38a-118">*finish*</span></span>

<span data-ttu-id="ad38a-119">反復処理ごとに、1 つのカウンター変数をインクリメントする通常の動作は、パターンとして整数の範囲と単純なカウンター変数を使用する場合が、カウンターは skip 値が代わりにインクリメントされます範囲には、skip 値が含まれている場合。</span><span class="sxs-lookup"><span data-stu-id="ad38a-119">When you use integral ranges and a simple counter variable as a pattern, the typical behavior is to increment the counter variable by 1 on each iteration, but if the range includes a skip value, the counter is incremented by the skip value instead.</span></span>

<span data-ttu-id="ad38a-120">パターンに一致した値は、式の本体でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="ad38a-120">Values matched in the pattern can also be used in the body expression.</span></span>

<span data-ttu-id="ad38a-121">次のコード例は、の使用を示しています、`for...in`式。</span><span class="sxs-lookup"><span data-stu-id="ad38a-121">The following code examples illustrate the use of the `for...in` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5201.fs)]

<span data-ttu-id="ad38a-122">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ad38a-122">The output is as follows.</span></span>

```
1
5
100
450
788
```

<span data-ttu-id="ad38a-123">次の例では、単純な変数ではなくタプル パターンを使用する方法と、シーケンス全体をループする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ad38a-123">The following example shows how to loop over a sequence, and how to use a tuple pattern instead of a simple variable.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5202.fs)]

<span data-ttu-id="ad38a-124">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ad38a-124">The output is as follows.</span></span>

```
1 squared is 1
2 squared is 4
3 squared is 9
4 squared is 16
5 squared is 25
6 squared is 36
7 squared is 49
8 squared is 64
9 squared is 81
10 squared is 100
```

<span data-ttu-id="ad38a-125">次の例では、単純な整数の範囲をループする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ad38a-125">The following example shows how to loop over a simple integer range.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5203.fs)]

<span data-ttu-id="ad38a-126">Function1 の出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ad38a-126">The output of function1 is as follows.</span></span>

```
1 2 3 4 5 6 7 8 9 10
```

<span data-ttu-id="ad38a-127">次の例では、範囲の他のすべての要素を含む、2 のスキップを含む範囲をループする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ad38a-127">The following example shows how to loop over a range with a skip of 2, which includes every other element of the range.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5204.fs)]

<span data-ttu-id="ad38a-128">出力`function2`のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ad38a-128">The output of `function2` is as follows.</span></span>

```
1 3 5 7 9
```

<span data-ttu-id="ad38a-129">次の例では、文字の範囲を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ad38a-129">The following example shows how to use a character range.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5205.fs)]

<span data-ttu-id="ad38a-130">出力`function3`のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ad38a-130">The output of `function3` is as follows.</span></span>

```
a b c d e f g h i j k l m n o p q r s t u v w x y z
```

<span data-ttu-id="ad38a-131">次の例では、逆順イテレーションの負の値のスキップの値を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ad38a-131">The following example shows how to use a negative skip value for a reverse iteration.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5208.fs)]

<span data-ttu-id="ad38a-132">出力`function4`のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ad38a-132">The output of `function4` is as follows.</span></span>

```
10 9 8 7 6 5 4 3 2 1 ... Lift off!
```

<span data-ttu-id="ad38a-133">先頭と範囲の終了には、次のコードのように、関数などの式ことができます。</span><span class="sxs-lookup"><span data-stu-id="ad38a-133">The beginning and ending of the range can also be expressions, such as functions, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5206.fs)]

<span data-ttu-id="ad38a-134">出力`function5`この入力は次のようにします。</span><span class="sxs-lookup"><span data-stu-id="ad38a-134">The output of `function5` with this input is as follows.</span></span>

```
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

<span data-ttu-id="ad38a-135">次の例では、ワイルドカード文字の使用 (\_) 要素が、ループ内で必要ない場合。</span><span class="sxs-lookup"><span data-stu-id="ad38a-135">The next example shows the use of a wildcard character (\_) when the element is not needed in the loop.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5207.fs)]

<span data-ttu-id="ad38a-136">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ad38a-136">The output is as follows.</span></span>

```
Number of elements in list1: 5
```

<span data-ttu-id="ad38a-137">`Note` 使用することができます`for...in`シーケンス式とその他のコンピュテーション式で、カスタマイズされたバージョンの場合、`for...in`式を使用します。</span><span class="sxs-lookup"><span data-stu-id="ad38a-137">`Note` You can use `for...in` in sequence expressions and other computation expressions, in which case a customized version of the `for...in` expression is used.</span></span> <span data-ttu-id="ad38a-138">詳細については、次を参照してください。[シーケンス](sequences.md)、[非同期ワークフロー](asynchronous-workflows.md)、および[コンピュテーション式](computation-expressions.md)します。</span><span class="sxs-lookup"><span data-stu-id="ad38a-138">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ad38a-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="ad38a-139">See also</span></span>

- [<span data-ttu-id="ad38a-140">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="ad38a-140">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="ad38a-141">ループ:`for...to` 式</span><span class="sxs-lookup"><span data-stu-id="ad38a-141">Loops: `for...to` Expression</span></span>](loops-for-to-expression.md)
- [<span data-ttu-id="ad38a-142">ループ:`while...do` 式</span><span class="sxs-lookup"><span data-stu-id="ad38a-142">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)