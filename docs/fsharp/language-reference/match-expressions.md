---
title: 一致式
description: F#一致式を使用して、式と一連のパターンとの比較に基づく分岐コントロールを提供する方法について説明します。
ms.date: 04/19/2018
ms.openlocfilehash: 222cb0604300039d86ed0c80293651631d212eb6
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627611"
---
# <a name="match-expressions"></a><span data-ttu-id="b376f-103">一致式</span><span class="sxs-lookup"><span data-stu-id="b376f-103">Match expressions</span></span>

<span data-ttu-id="b376f-104">式`match`は、式と一連のパターンとの比較に基づいて分岐コントロールを提供します。</span><span class="sxs-lookup"><span data-stu-id="b376f-104">The `match` expression provides branching control that is based on the comparison of an expression with a set of patterns.</span></span>

## <a name="syntax"></a><span data-ttu-id="b376f-105">構文</span><span class="sxs-lookup"><span data-stu-id="b376f-105">Syntax</span></span>

```fsharp
// Match expression.
match test-expression with
| pattern1 [ when condition ] -> result-expression1
| pattern2 [ when condition ] -> result-expression2
| ...

// Pattern matching function.
function
| pattern1 [ when condition ] -> result-expression1
| pattern2 [ when condition ] -> result-expression2
| ...
```

## <a name="remarks"></a><span data-ttu-id="b376f-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="b376f-106">Remarks</span></span>

<span data-ttu-id="b376f-107">パターン一致式を使用すると、テスト式と一連のパターンとの比較に基づいて、複雑な分岐を実行できます。</span><span class="sxs-lookup"><span data-stu-id="b376f-107">The pattern matching expressions allow for complex branching based on the comparison of a test expression with a set of patterns.</span></span> <span data-ttu-id="b376f-108">この式では、各パターンと*テスト式*が比較され、一致が見つかると、対応する*結果式*が評価され、結果の値が match 式の値として返されます。 `match`</span><span class="sxs-lookup"><span data-stu-id="b376f-108">In the `match` expression, the *test-expression* is compared with each pattern in turn, and when a match is found, the corresponding *result-expression* is evaluated and the resulting value is returned as the value of the match expression.</span></span>

<span data-ttu-id="b376f-109">前の構文で示されているパターン一致関数は、引数でパターンマッチングがすぐに実行されるラムダ式です。</span><span class="sxs-lookup"><span data-stu-id="b376f-109">The pattern matching function shown in the previous syntax is a lambda expression in which pattern matching is performed immediately on the argument.</span></span> <span data-ttu-id="b376f-110">前の構文で示されているパターン一致関数は、次の関数と同じです。</span><span class="sxs-lookup"><span data-stu-id="b376f-110">The pattern matching function shown in the previous syntax is equivalent to the following.</span></span>

```fsharp
fun arg ->
    match arg with
    | pattern1 [ when condition ] -> result-expression1
    | pattern2 [ when condition ] -> result-expression2
    | ...
```

<span data-ttu-id="b376f-111">ラムダ式の詳細については[、次を参照してください。ラムダ式:`fun`キーワード](./functions/lambda-expressions-the-fun-keyword.md)します。</span><span class="sxs-lookup"><span data-stu-id="b376f-111">For more information about lambda expressions, see [Lambda Expressions: The `fun` Keyword](./functions/lambda-expressions-the-fun-keyword.md).</span></span>

<span data-ttu-id="b376f-112">パターンのセット全体で、入力変数のすべての一致候補をカバーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b376f-112">The whole set of patterns should cover all the possible matches of the input variable.</span></span> <span data-ttu-id="b376f-113">多くの場合、以前に一致し`_`ていない入力値と一致させるために、最後のパターンとしてワイルドカードパターン () を使用します。</span><span class="sxs-lookup"><span data-stu-id="b376f-113">Frequently, you use the wildcard pattern (`_`) as the last pattern to match any previously unmatched input values.</span></span>

<span data-ttu-id="b376f-114">次のコードは、 `match`式を使用するいくつかの方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b376f-114">The following code illustrates some of the ways in which the `match` expression is used.</span></span> <span data-ttu-id="b376f-115">使用可能なすべてのパターンのリファレンスと例については、「[パターン一致](pattern-matching.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b376f-115">For a reference and examples of all the possible patterns that can be used, see [Pattern Matching](pattern-matching.md).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4601.fs)]

## <a name="guards-on-patterns"></a><span data-ttu-id="b376f-116">パターンでのガード</span><span class="sxs-lookup"><span data-stu-id="b376f-116">Guards on patterns</span></span>

<span data-ttu-id="b376f-117">句を`when`使用して、変数がパターンに一致するために満たす必要のある追加条件を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b376f-117">You can use a `when` clause to specify an additional condition that the variable must satisfy to match a pattern.</span></span> <span data-ttu-id="b376f-118">このような句を*ガード*と呼びます。</span><span class="sxs-lookup"><span data-stu-id="b376f-118">Such a clause is referred to as a *guard*.</span></span> <span data-ttu-id="b376f-119">`when`キーワードに続く式は、そのガードに関連付けられているパターンが一致しない限り評価されません。</span><span class="sxs-lookup"><span data-stu-id="b376f-119">The expression following the `when` keyword is not evaluated unless a match is made to the pattern associated with that guard.</span></span>

<span data-ttu-id="b376f-120">次の例は、ガードを使用して、変数パターンの数値範囲を指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b376f-120">The following example illustrates the use of a guard to specify a numeric range for a variable pattern.</span></span> <span data-ttu-id="b376f-121">複数の条件は、ブール演算子を使用して結合されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b376f-121">Note that multiple conditions are combined by using Boolean operators.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4602.fs)]

<span data-ttu-id="b376f-122">リテラル以外の値はパターンで使用できないため、入力の一部を値と`when`比較する必要がある場合は、句を使用する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b376f-122">Note that because values other than literals cannot be used in the pattern, you must use a `when` clause if you have to compare some part of the input against a value.</span></span> <span data-ttu-id="b376f-123">これを次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="b376f-123">This is shown in the following code:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4603.fs)]

<span data-ttu-id="b376f-124">Union パターンがガードによってカバーされている場合、ガードは、最後のパターンだけでなく、**すべて**のパターンに適用されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b376f-124">Note that when a union pattern is covered by a guard, the guard applies to **all** of the patterns, not just the last one.</span></span> <span data-ttu-id="b376f-125">たとえば、次のコードがあるとします`when a > 12` 。ガードは`A a`と`B a`の両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="b376f-125">For example, given the following code, the guard `when a > 12` applies to both `A a` and `B a`:</span></span>

```fsharp
type Union =
    | A of int
    | B of int

let foo() =
    let test = A 42
    match test with
    | A a
    | B a when a > 41 -> a // the guard applies to both patterns
    | _ -> 1

foo() // returns 42
```

## <a name="see-also"></a><span data-ttu-id="b376f-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="b376f-126">See also</span></span>

- [<span data-ttu-id="b376f-127">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="b376f-127">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="b376f-128">アクティブ パターン</span><span class="sxs-lookup"><span data-stu-id="b376f-128">Active Patterns</span></span>](active-patterns.md)
- [<span data-ttu-id="b376f-129">パターン一致</span><span class="sxs-lookup"><span data-stu-id="b376f-129">Pattern Matching</span></span>](pattern-matching.md)
