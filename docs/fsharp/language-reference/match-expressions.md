---
title: Match 式
description: について説明しますが、どのようにF#match 式が式のパターンのセットとの比較に基づいている分岐を制御を提供します。
ms.date: 04/19/2018
ms.openlocfilehash: 69ff8de1617e6b55d112d310bfcd8b2f967b6e8a
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645198"
---
# <a name="match-expressions"></a><span data-ttu-id="7e604-103">Match 式</span><span class="sxs-lookup"><span data-stu-id="7e604-103">Match expressions</span></span>

<span data-ttu-id="7e604-104">`match`式が式のパターンのセットとの比較に基づいている分岐を制御を提供します。</span><span class="sxs-lookup"><span data-stu-id="7e604-104">The `match` expression provides branching control that is based on the comparison of an expression with a set of patterns.</span></span>

## <a name="syntax"></a><span data-ttu-id="7e604-105">構文</span><span class="sxs-lookup"><span data-stu-id="7e604-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="7e604-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="7e604-106">Remarks</span></span>

<span data-ttu-id="7e604-107">パターン マッチング式は、複雑なパターンのセットとテスト式の比較に基づく、分岐の許可されます。</span><span class="sxs-lookup"><span data-stu-id="7e604-107">The pattern matching expressions allow for complex branching based on the comparison of a test expression with a set of patterns.</span></span> <span data-ttu-id="7e604-108">`match`式、*テスト式*でを有効にして、対応する一致が見つかった場合は、各パターンと比較されます*結果式*評価は、結果として得られる値はmatch 式の値として返されます。</span><span class="sxs-lookup"><span data-stu-id="7e604-108">In the `match` expression, the *test-expression* is compared with each pattern in turn, and when a match is found, the corresponding *result-expression* is evaluated and the resulting value is returned as the value of the match expression.</span></span>

<span data-ttu-id="7e604-109">前の構文に示すように関数を一致するパターンは、パターン マッチが行われますすぐに、引数にラムダ式です。</span><span class="sxs-lookup"><span data-stu-id="7e604-109">The pattern matching function shown in the previous syntax is a lambda expression in which pattern matching is performed immediately on the argument.</span></span> <span data-ttu-id="7e604-110">前の構文に示すように関数を一致するパターンは、次のと同じです。</span><span class="sxs-lookup"><span data-stu-id="7e604-110">The pattern matching function shown in the previous syntax is equivalent to the following.</span></span>

```fsharp
fun arg ->
    match arg with
    | pattern1 [ when condition ] -> result-expression1
    | pattern2 [ when condition ] -> result-expression2
    | ...
```

<span data-ttu-id="7e604-111">ラムダ式の詳細については、次を参照してください。[ラムダ式。`fun`キーワード](functions/lambda-expressions-the-fun-keyword.md)します。</span><span class="sxs-lookup"><span data-stu-id="7e604-111">For more information about lambda expressions, see [Lambda Expressions: The `fun` Keyword](functions/lambda-expressions-the-fun-keyword.md).</span></span>

<span data-ttu-id="7e604-112">パターンのセット全体には、入力変数の考えられるすべての一致する必要がありますについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7e604-112">The whole set of patterns should cover all the possible matches of the input variable.</span></span> <span data-ttu-id="7e604-113">ワイルドカード パターンを使用する多くの場合、(`_`)、比類のない以前の入力値と一致する最後のパターンとして。</span><span class="sxs-lookup"><span data-stu-id="7e604-113">Frequently, you use the wildcard pattern (`_`) as the last pattern to match any previously unmatched input values.</span></span>

<span data-ttu-id="7e604-114">次のコードはいくつかの方法を示しています、`match`式を使用します。</span><span class="sxs-lookup"><span data-stu-id="7e604-114">The following code illustrates some of the ways in which the `match` expression is used.</span></span> <span data-ttu-id="7e604-115">参照および使用できるすべてのパターンの例では、「[パターン マッチング](pattern-matching.md)します。</span><span class="sxs-lookup"><span data-stu-id="7e604-115">For a reference and examples of all the possible patterns that can be used, see [Pattern Matching](pattern-matching.md).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4601.fs)]

## <a name="guards-on-patterns"></a><span data-ttu-id="7e604-116">パターンのガード</span><span class="sxs-lookup"><span data-stu-id="7e604-116">Guards on patterns</span></span>

<span data-ttu-id="7e604-117">使用することができます、`when`がパターンに一致する変数が満たす必要がある追加の条件を指定する句。</span><span class="sxs-lookup"><span data-stu-id="7e604-117">You can use a `when` clause to specify an additional condition that the variable must satisfy to match a pattern.</span></span> <span data-ttu-id="7e604-118">このような句として参照されます、*ガード*します。</span><span class="sxs-lookup"><span data-stu-id="7e604-118">Such a clause is referred to as a *guard*.</span></span> <span data-ttu-id="7e604-119">続く式、`when`警備員に関連付けられているパターンに一致が行われた場合を除き、キーワードは評価されません。</span><span class="sxs-lookup"><span data-stu-id="7e604-119">The expression following the `when` keyword is not evaluated unless a match is made to the pattern associated with that guard.</span></span>

<span data-ttu-id="7e604-120">次の例では、変数パターンの数値範囲を指定するガードの使用を示します。</span><span class="sxs-lookup"><span data-stu-id="7e604-120">The following example illustrates the use of a guard to specify a numeric range for a variable pattern.</span></span> <span data-ttu-id="7e604-121">ブール演算子を使用して複数の条件がまとめられることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7e604-121">Note that multiple conditions are combined by using Boolean operators.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4602.fs)]

<span data-ttu-id="7e604-122">パターンのリテラル以外の値を使用することはできません、する必要がありますを使用することに注意してください、`when`句の値に対する入力の一部を比較した場合。</span><span class="sxs-lookup"><span data-stu-id="7e604-122">Note that because values other than literals cannot be used in the pattern, you must use a `when` clause if you have to compare some part of the input against a value.</span></span> <span data-ttu-id="7e604-123">これは、次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="7e604-123">This is shown in the following code:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4603.fs)]

<span data-ttu-id="7e604-124">共用体パターンは、ガードでカバーされる、ときに、保護に適用されることに注意してください。**すべて**最後の 1 つだけでなく、パターンの。</span><span class="sxs-lookup"><span data-stu-id="7e604-124">Note that when a union pattern is covered by a guard, the guard applies to **all** of the patterns, not just the last one.</span></span> <span data-ttu-id="7e604-125">たとえば、次のコードでは、ガードを与える`when a > 12`両方に適用されます`A a`と`B a`:</span><span class="sxs-lookup"><span data-stu-id="7e604-125">For example, given the following code, the guard `when a > 12` applies to both `A a` and `B a`:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="7e604-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="7e604-126">See also</span></span>

- [<span data-ttu-id="7e604-127">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="7e604-127">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="7e604-128">アクティブ パターン</span><span class="sxs-lookup"><span data-stu-id="7e604-128">Active Patterns</span></span>](active-patterns.md)
- [<span data-ttu-id="7e604-129">パターン一致</span><span class="sxs-lookup"><span data-stu-id="7e604-129">Pattern Matching</span></span>](pattern-matching.md)
