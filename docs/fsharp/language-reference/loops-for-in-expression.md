---
title: 'ループ: for...in 式'
description: 参照してください方法 F# for….. 式で列挙可能なコレクション内のパターンの一致を反復処理するループ コンストラクトが使用されます。
ms.date: 05/16/2016
ms.openlocfilehash: 640b0f91f6c641f3b49a99dc67abe7e4c31911ea
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630721"
---
# <a name="loops-forin-expression"></a><span data-ttu-id="4c97c-103">ループ: for...in 式</span><span class="sxs-lookup"><span data-stu-id="4c97c-103">Loops: for...in Expression</span></span>

<span data-ttu-id="4c97c-104">このループ構造は、列挙可能なコレクション内のパターンの一致を反復処理するために使用されます。たとえば、範囲式、シーケンス、リスト、配列、または列挙をサポートするその他の構造体です。</span><span class="sxs-lookup"><span data-stu-id="4c97c-104">This looping construct is used to iterate over the matches of a pattern in an enumerable collection such as a range expression, sequence, list, array, or other construct that supports enumeration.</span></span>

## <a name="syntax"></a><span data-ttu-id="4c97c-105">構文</span><span class="sxs-lookup"><span data-stu-id="4c97c-105">Syntax</span></span>

```fsharp
for pattern in enumerable-expression do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="4c97c-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="4c97c-106">Remarks</span></span>

<span data-ttu-id="4c97c-107">式は、他の .net 言語`for each`のステートメントと比較できます。これは、列挙可能なコレクションの値をループ処理するために使用されるためです。 `for...in`</span><span class="sxs-lookup"><span data-stu-id="4c97c-107">The `for...in` expression can be compared to the `for each` statement in other .NET languages because it is used to loop over the values in an enumerable collection.</span></span> <span data-ttu-id="4c97c-108">ただし、 `for...in`では、コレクション全体に対して反復処理を行うのではなく、コレクションに対するパターンマッチングもサポートしています。</span><span class="sxs-lookup"><span data-stu-id="4c97c-108">However, `for...in` also supports pattern matching over the collection instead of just iteration over the whole collection.</span></span>

<span data-ttu-id="4c97c-109">列挙可能な式は、整数型の範囲として、列挙`..`可能なコレクションとして指定することも、演算子を使用して指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="4c97c-109">The enumerable expression can be specified as an enumerable collection or, by using the `..` operator, as a range on an integral type.</span></span> <span data-ttu-id="4c97c-110">列挙可能なコレクションには、リスト、シーケンス、配列、セット、マップなどがあります。</span><span class="sxs-lookup"><span data-stu-id="4c97c-110">Enumerable collections include lists, sequences, arrays, sets, maps, and so on.</span></span> <span data-ttu-id="4c97c-111">を実装`System.Collections.IEnumerable`する任意の型を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4c97c-111">Any type that implements `System.Collections.IEnumerable` can be used.</span></span>

<span data-ttu-id="4c97c-112">`..`演算子を使用して範囲を表現する場合は、次の構文を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4c97c-112">When you express a range by using the `..` operator, you can use the following syntax.</span></span>

<span data-ttu-id="4c97c-113">*開始*...</span><span class="sxs-lookup"><span data-stu-id="4c97c-113">*start* ..</span></span> <span data-ttu-id="4c97c-114">*終わっ*</span><span class="sxs-lookup"><span data-stu-id="4c97c-114">*finish*</span></span>

<span data-ttu-id="4c97c-115">次のコードのように、 *skip*と呼ばれるインクリメントを含むバージョンを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="4c97c-115">You can also use a version that includes an increment called the *skip*, as in the following code.</span></span>

<span data-ttu-id="4c97c-116">*開始*...</span><span class="sxs-lookup"><span data-stu-id="4c97c-116">*start* ..</span></span> <span data-ttu-id="4c97c-117">*スキップ*..</span><span class="sxs-lookup"><span data-stu-id="4c97c-117">*skip* ..</span></span> <span data-ttu-id="4c97c-118">*終わっ*</span><span class="sxs-lookup"><span data-stu-id="4c97c-118">*finish*</span></span>

<span data-ttu-id="4c97c-119">整数の範囲と単純なカウンター変数をパターンとして使用する場合の一般的な動作は、各反復処理でカウンター変数を1ずつインクリメントすることですが、範囲に skip 値が含まれている場合は、代わりに skip 値によってカウンターがインクリメントされます。</span><span class="sxs-lookup"><span data-stu-id="4c97c-119">When you use integral ranges and a simple counter variable as a pattern, the typical behavior is to increment the counter variable by 1 on each iteration, but if the range includes a skip value, the counter is incremented by the skip value instead.</span></span>

<span data-ttu-id="4c97c-120">パターンに一致した値は、本文の式でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="4c97c-120">Values matched in the pattern can also be used in the body expression.</span></span>

<span data-ttu-id="4c97c-121">次のコード例は、 `for...in`式の使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="4c97c-121">The following code examples illustrate the use of the `for...in` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5201.fs)]

<span data-ttu-id="4c97c-122">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4c97c-122">The output is as follows.</span></span>

```
1
5
100
450
788
```

<span data-ttu-id="4c97c-123">次の例は、シーケンスをループ処理する方法と、単純な変数の代わりに組パターンを使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="4c97c-123">The following example shows how to loop over a sequence, and how to use a tuple pattern instead of a simple variable.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5202.fs)]

<span data-ttu-id="4c97c-124">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4c97c-124">The output is as follows.</span></span>

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

<span data-ttu-id="4c97c-125">次の例は、単純な整数範囲をループ処理する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="4c97c-125">The following example shows how to loop over a simple integer range.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5203.fs)]

<span data-ttu-id="4c97c-126">Function1 の出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="4c97c-126">The output of function1 is as follows.</span></span>

```
1 2 3 4 5 6 7 8 9 10
```

<span data-ttu-id="4c97c-127">次の例では、範囲の他のすべての要素を含む、skip が2の範囲をループ処理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4c97c-127">The following example shows how to loop over a range with a skip of 2, which includes every other element of the range.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5204.fs)]

<span data-ttu-id="4c97c-128">の出力は`function2`次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4c97c-128">The output of `function2` is as follows.</span></span>

```
1 3 5 7 9
```

<span data-ttu-id="4c97c-129">文字範囲を使用する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="4c97c-129">The following example shows how to use a character range.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5205.fs)]

<span data-ttu-id="4c97c-130">の出力は`function3`次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4c97c-130">The output of `function3` is as follows.</span></span>

```
a b c d e f g h i j k l m n o p q r s t u v w x y z
```

<span data-ttu-id="4c97c-131">次の例では、逆の反復処理で負の skip 値を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4c97c-131">The following example shows how to use a negative skip value for a reverse iteration.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5208.fs)]

<span data-ttu-id="4c97c-132">の出力は`function4`次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4c97c-132">The output of `function4` is as follows.</span></span>

```
10 9 8 7 6 5 4 3 2 1 ... Lift off!
```

<span data-ttu-id="4c97c-133">次のコードのように、範囲の先頭と末尾には、関数などの式を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="4c97c-133">The beginning and ending of the range can also be expressions, such as functions, as in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5206.fs)]

<span data-ttu-id="4c97c-134">この入力に`function5`よるの出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4c97c-134">The output of `function5` with this input is as follows.</span></span>

```
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

<span data-ttu-id="4c97c-135">次の例は、ループで要素が不要な\_場合に、ワイルドカード文字 () を使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="4c97c-135">The next example shows the use of a wildcard character (\_) when the element is not needed in the loop.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5207.fs)]

<span data-ttu-id="4c97c-136">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4c97c-136">The output is as follows.</span></span>

```
Number of elements in list1: 5
```

<span data-ttu-id="4c97c-137">`Note`は、シーケンス`for...in`式やその他のコンピュテーション式で使用できます。その場合は、 `for...in`式のカスタマイズされたバージョンが使用されます。</span><span class="sxs-lookup"><span data-stu-id="4c97c-137">`Note` You can use `for...in` in sequence expressions and other computation expressions, in which case a customized version of the `for...in` expression is used.</span></span> <span data-ttu-id="4c97c-138">詳細については、「[シーケンス](sequences.md)、[非同期ワークフロー](asynchronous-workflows.md)、および[コンピュテーション式](computation-expressions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c97c-138">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4c97c-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="4c97c-139">See also</span></span>

- [<span data-ttu-id="4c97c-140">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="4c97c-140">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="4c97c-141">For`for...to`条件</span><span class="sxs-lookup"><span data-stu-id="4c97c-141">Loops: `for...to` Expression</span></span>](loops-for-to-expression.md)
- [<span data-ttu-id="4c97c-142">For`while...do`条件</span><span class="sxs-lookup"><span data-stu-id="4c97c-142">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)
