---
title: switch 式 - C# リファレンス
description: パターン マッチングとその他のデータ イントロスペクションに C# の switch 式を使用する方法について説明します
ms.date: 03/19/2020
ms.openlocfilehash: 9e609bcea0f92f492b5f9b07840e47f75c1b71e4
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249760"
---
# <a name="switch-expression-c-reference"></a><span data-ttu-id="e5848-103">switch 式 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="e5848-103">switch expression (C# reference)</span></span>

<span data-ttu-id="e5848-104">この記事では、C# 8.0 で導入された `switch` 式について説明します。</span><span class="sxs-lookup"><span data-stu-id="e5848-104">This article covers the `switch` expression, introduced in C# 8.0.</span></span> <span data-ttu-id="e5848-105">`switch` ステートメントについては、[ステートメント](../keywords/index.md)のセクションの [`switch` ステートメント](../keywords/switch.md)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5848-105">For information on the `switch` statement, see the article on the [`switch` statement](../keywords/switch.md) in the [statements](../keywords/index.md) section.</span></span>

## <a name="basic-example"></a><span data-ttu-id="e5848-106">基本的な例</span><span class="sxs-lookup"><span data-stu-id="e5848-106">Basic example</span></span>

<span data-ttu-id="e5848-107">`switch` 式では、式のコンテキストにおいて `switch` と同様のセマンティクスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="e5848-107">The `switch` expression provides for `switch`-like semantics in an expression context.</span></span> <span data-ttu-id="e5848-108">switch アームで値が生成されるときの簡潔な構文が提供されます。</span><span class="sxs-lookup"><span data-stu-id="e5848-108">It provides a concise syntax when the switch arms produce a value.</span></span> <span data-ttu-id="e5848-109">次の例では、switch 式の構造を示します。</span><span class="sxs-lookup"><span data-stu-id="e5848-109">The following example shows the structure of a switch expression.</span></span> <span data-ttu-id="e5848-110">オンライン マップでの視方向を表す `enum` の値が、対応する基本方位に変換されます。</span><span class="sxs-lookup"><span data-stu-id="e5848-110">It translates values from an `enum` representing visual directions in an online map to the corresponding cardinal direction:</span></span>

:::code language="csharp" source="snippets/SwitchExpressions.cs" id="SnippetBasicStructure":::

<span data-ttu-id="e5848-111">前のサンプルでは、switch 式の基本的な要素が示されています。</span><span class="sxs-lookup"><span data-stu-id="e5848-111">The preceding sample shows the basic elements of a switch expression:</span></span>

- <span data-ttu-id="e5848-112">"*範囲式*": 前の例では、変数 `direction` が範囲式として使用されています。</span><span class="sxs-lookup"><span data-stu-id="e5848-112">The *range expression*: The preceding example uses the variable `direction` as the range expression.</span></span>
- <span data-ttu-id="e5848-113">"*switch 式アーム*": 各 switch 式アームには、"*パターン*"、省略可能な "*ケース ガード*"、`=>` トークン、"*式*" が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e5848-113">The *switch expression arms*: Each switch expression arm contains a *pattern*, an optional *case guard*, the `=>` token, and an *expression*.</span></span>

<span data-ttu-id="e5848-114">"*switch 式の結果*" は、"*パターン*" が "*範囲式*" と一致し、"*ケース ガード*" が `true` と評価される (存在する場合)、最初の "*switch 式アーム*" の式の値です。</span><span class="sxs-lookup"><span data-stu-id="e5848-114">The result of the *switch expression* is the value of the expression of the first *switch expression arm* whose *pattern* matches the *range expression* and whose *cause guard*, if present, evaluates to `true`.</span></span> <span data-ttu-id="e5848-115">`=>` トークンの右側の "*式*" として、式ステートメントを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="e5848-115">The *expression* on the right of the `=>` token can't be an expression statement.</span></span>

<span data-ttu-id="e5848-116">"*switch 式アーム*" は、テキストの順番に評価されます。</span><span class="sxs-lookup"><span data-stu-id="e5848-116">The *switch expression arms* are evaluated in text order.</span></span> <span data-ttu-id="e5848-117">高い "*switch 式アーム*" がすべての値と一致するため、低い "*switch 式アーム*" を選択できない場合、コンパイラではエラーが発行されます。</span><span class="sxs-lookup"><span data-stu-id="e5848-117">The compiler issues an error when a lower *switch expression arm* can't be chosen because a higher *switch expression arm* matches all its values.</span></span>

## <a name="patterns-and-case-guards"></a><span data-ttu-id="e5848-118">パターンとケース ガード</span><span class="sxs-lookup"><span data-stu-id="e5848-118">Patterns and case guards</span></span>

<span data-ttu-id="e5848-119">switch 式アームでは、多くのパターンがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e5848-119">Many patterns are supported in switch expression arms.</span></span> <span data-ttu-id="e5848-120">前の例では、"*値パターン*" が使用されています。</span><span class="sxs-lookup"><span data-stu-id="e5848-120">The preceding example used a *value pattern*.</span></span> <span data-ttu-id="e5848-121">"*値パターン*" では、範囲式と値が比較されます。</span><span class="sxs-lookup"><span data-stu-id="e5848-121">A *value pattern* compares the range expression to a value.</span></span> <span data-ttu-id="e5848-122">その値は、コンパイル時定数である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5848-122">That value must be a compile time constant.</span></span> <span data-ttu-id="e5848-123">"*型パターン*" では、範囲式と既知の型が比較されます。</span><span class="sxs-lookup"><span data-stu-id="e5848-123">The *type pattern* compares the range expression to a known type.</span></span> <span data-ttu-id="e5848-124">次の例では、シーケンスから 3 番目の要素が取得されます。</span><span class="sxs-lookup"><span data-stu-id="e5848-124">The following example retrieves the third element from a sequence.</span></span> <span data-ttu-id="e5848-125">シーケンスの型に基づいて、異なるメソッドが使用されます。</span><span class="sxs-lookup"><span data-stu-id="e5848-125">It uses different methods based on the type of the sequence:</span></span>

:::code language="csharp" source="snippets/SwitchExpressions.cs" id="SnippetTypePattern":::

<span data-ttu-id="e5848-126">パターンは再帰的にすることができます。パターンで型をテストし、その型が一致する場合、そのパターンは範囲式の 1 つまたは複数のプロパティ値と一致します。</span><span class="sxs-lookup"><span data-stu-id="e5848-126">Patterns can be recursive, where a pattern tests a type, and if that type matches, the pattern matches one or more property values on the range expression.</span></span> <span data-ttu-id="e5848-127">再帰パターンを使用して、前の例を拡張できます。</span><span class="sxs-lookup"><span data-stu-id="e5848-127">You can use recursive patterns to extend the preceding example.</span></span> <span data-ttu-id="e5848-128">要素数が 3 未満の配列に対する switch 式アームを追加します。</span><span class="sxs-lookup"><span data-stu-id="e5848-128">You add switch expression arms for arrays that have fewer than 3 elements.</span></span> <span data-ttu-id="e5848-129">再帰パターンを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="e5848-129">Recursive patterns are shown in the following example:</span></span>

:::code language="csharp" source="snippets/SwitchExpressions.cs" id="SnippetRecursivePattern":::

<span data-ttu-id="e5848-130">再帰パターンでは、範囲式のプロパティを調べることはできますが、任意のコードを実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="e5848-130">Recursive patterns can examine properties of the range expression, but can't execute arbitrary code.</span></span> <span data-ttu-id="e5848-131">`when` 句で指定する "*ケース ガード*" を使用して、他のシーケンス型と同様のチェックを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e5848-131">You can use a *case guard*, specified in a `when` clause, to provide similar checks for other sequence types:</span></span>

:::code language="csharp" source="snippets/SwitchExpressions.cs" id="SnippetGuardCase":::

<span data-ttu-id="e5848-132">最後に、`_` パターンと `null` パターンを追加して、他のどの switch 式アームによっても処理されない引数をキャッチすることができます。</span><span class="sxs-lookup"><span data-stu-id="e5848-132">Finally, you can add the `_` pattern and the `null` pattern to catch arguments that aren't processed by any other switch expression arm.</span></span> <span data-ttu-id="e5848-133">そのようにすると、switch 式が "*網羅的*" になります。これは、範囲式で可能性のあるすべての値が処理されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="e5848-133">That makes the switch expression *exhaustive*, meaning any possible value of the range expression is handled.</span></span> <span data-ttu-id="e5848-134">次の例では、そのような式アームを追加しています。</span><span class="sxs-lookup"><span data-stu-id="e5848-134">The following example adds those expression arms:</span></span>

:::code language="csharp" source="snippets/SwitchExpressions.cs" id="SnippetExhaustive":::

<span data-ttu-id="e5848-135">前の例では、`null` パターンが追加され、`IEnumerable<T>` 型パターンが `_` パターンに変更されています。</span><span class="sxs-lookup"><span data-stu-id="e5848-135">The preceding example adds a `null` pattern, and changes the `IEnumerable<T>` type pattern to a `_` pattern.</span></span> <span data-ttu-id="e5848-136">`null` パターンでは、switch 式アームとして null チェックが提供されます。</span><span class="sxs-lookup"><span data-stu-id="e5848-136">The `null` pattern provides a null check as a switch expression arm.</span></span> <span data-ttu-id="e5848-137">そのアームの式によって、<xref:System.ArgumentNullException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="e5848-137">The expression for that arm throws an <xref:System.ArgumentNullException>.</span></span> <span data-ttu-id="e5848-138">`_` パターンは、それより前にあるアームで一致していないすべての入力と一致します。</span><span class="sxs-lookup"><span data-stu-id="e5848-138">The `_` pattern matches all inputs that haven't been matched by previous arms.</span></span> <span data-ttu-id="e5848-139">`null` チェックの後で指定する必要があります。そうしないと、`null` 入力と一致します。</span><span class="sxs-lookup"><span data-stu-id="e5848-139">It must come after the `null` check, or it would match `null` inputs.</span></span>

<span data-ttu-id="e5848-140">[再帰パターン](~/_csharplang/proposals/csharp-8.0/patterns.md#switch-expression)に関する C# 言語仕様の提案について詳しくは、こちらをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e5848-140">You can read more in the C# language spec proposal for [recursive patterns](~/_csharplang/proposals/csharp-8.0/patterns.md#switch-expression).</span></span>

## <a name="see-also"></a><span data-ttu-id="e5848-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5848-141">See also</span></span>

- [<span data-ttu-id="e5848-142">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="e5848-142">C# reference</span></span>](../index.md)
- [<span data-ttu-id="e5848-143">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="e5848-143">C# operators</span></span>](index.md)
- [<span data-ttu-id="e5848-144">パターン マッチング</span><span class="sxs-lookup"><span data-stu-id="e5848-144">Pattern matching</span></span>](../../pattern-matching.md)
