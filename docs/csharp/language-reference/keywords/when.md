---
title: コンテキスト キーワード when - C# リファレンス
ms.date: 03/07/2017
f1_keywords:
- when_CSharpKeyword
- when
helpviewer_keywords:
- when keyword [C#]
ms.assetid: dd543335-ae37-48ac-9560-bd5f047b9aea
ms.openlocfilehash: 2b041ca3a821f45dd63ce3f6bee7a920eb495651
ms.sourcegitcommit: 32f0d6f4c01ddc6ca78767c3a30e3305f8cd032c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2020
ms.locfileid: "87426996"
---
# <a name="when-c-reference"></a><span data-ttu-id="c127e-102">when (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="c127e-102">when (C# Reference)</span></span>

<span data-ttu-id="c127e-103">コンテキスト キーワード `when` は、次のコンテキストでフィルター条件を指定するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="c127e-103">You can use the `when` contextual keyword to specify a filter condition in the following contexts:</span></span>

- <span data-ttu-id="c127e-104">[try/catch](try-catch.md) または [try/catch/finally](try-catch-finally.md) ブロックの `catch` ステートメント。</span><span class="sxs-lookup"><span data-stu-id="c127e-104">In the `catch` statement of a [try/catch](try-catch.md) or [try/catch/finally](try-catch-finally.md) block.</span></span>
- <span data-ttu-id="c127e-105">[switch](switch.md) ステートメントの `case` ラベル。</span><span class="sxs-lookup"><span data-stu-id="c127e-105">In the `case` label of a [switch](switch.md) statement.</span></span>
- <span data-ttu-id="c127e-106">[`switch` 式](../operators/switch-expression.md)。</span><span class="sxs-lookup"><span data-stu-id="c127e-106">In the [`switch` expression](../operators/switch-expression.md).</span></span>

## <a name="when-in-a-catch-statement"></a><span data-ttu-id="c127e-107">`catch` ステートメントでの `when`</span><span class="sxs-lookup"><span data-stu-id="c127e-107">`when` in a `catch` statement</span></span>

<span data-ttu-id="c127e-108">C# 6 から、`when` を `catch` ステートメントで使用して、特定の例外のハンドラーを実行するために true になる必要がある条件を指定できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="c127e-108">Starting with C# 6, `when` can be used in a `catch` statement to specify a condition that must be true for the handler for a specific exception to execute.</span></span> <span data-ttu-id="c127e-109">構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c127e-109">Its syntax is:</span></span>

```csharp
catch (ExceptionType [e]) when (expr)
```

<span data-ttu-id="c127e-110">*expr* の箇所には、ブール値に評価される式を指定します。</span><span class="sxs-lookup"><span data-stu-id="c127e-110">where *expr* is an expression that evaluates to a Boolean value.</span></span> <span data-ttu-id="c127e-111">`true` が返された場合は、例外ハンドラーが実行されます。`false` の場合は実行されません。</span><span class="sxs-lookup"><span data-stu-id="c127e-111">If it returns `true`, the exception handler executes; if `false`, it does not.</span></span>

<span data-ttu-id="c127e-112">次の例では、`when` キーワードを使用し、例外メッセージのテキストに応じて、<xref:System.Net.Http.HttpRequestException> のハンドラーが条件付きで実行されるようにしています。</span><span class="sxs-lookup"><span data-stu-id="c127e-112">The following example uses the `when` keyword to conditionally execute handlers for an <xref:System.Net.Http.HttpRequestException> depending on the text of the exception message.</span></span>

[!code-csharp[when-with-catch](~/samples/snippets/csharp/language-reference/keywords/when/catch.cs)]

## <a name="when-in-a-switch-statement"></a><span data-ttu-id="c127e-113">`switch` ステートメントでの `when`</span><span class="sxs-lookup"><span data-stu-id="c127e-113">`when` in a `switch` statement</span></span>

<span data-ttu-id="c127e-114">C# 7.0 以降では、`case` ラベルが相互に排他的である必要がなくなり、`switch` ステートメントでの `case` ラベルの表示順序によって、実行される switch ブロックを決定できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="c127e-114">Starting with C# 7.0, `case` labels no longer need be mutually exclusive, and the order in which `case` labels appear in a `switch` statement can determine which switch block executes.</span></span> <span data-ttu-id="c127e-115">`when` キーワードを使用すると、フィルター条件が true である場合にのみ、関連付けられた case ラベルも true になるフィルター条件を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c127e-115">The `when` keyword can be used to specify a filter condition that causes its associated case label to be true only if the filter condition is also true.</span></span> <span data-ttu-id="c127e-116">構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c127e-116">Its syntax is:</span></span>

```csharp
case (expr) when (when-condition):
```

<span data-ttu-id="c127e-117">*expr* の箇所には、match 式と比較される定数パターンまたは型パターンを指定し、*when-condition* の箇所には、任意のブール式を指定します。</span><span class="sxs-lookup"><span data-stu-id="c127e-117">where *expr* is a constant pattern or type pattern that is compared to the match expression, and *when-condition* is any Boolean expression.</span></span>

<span data-ttu-id="c127e-118">次の例では、`when` キーワードを使用して、面積が 0 の `Shape` オブジェクトに対するテストと、面積が 0 より大きい各種の `Shape` オブジェクトに対するテストを実行しています。</span><span class="sxs-lookup"><span data-stu-id="c127e-118">The following example uses the `when` keyword to test for `Shape` objects that have an area of zero, as well as to test for a variety of `Shape` objects that have an area greater than zero.</span></span>

[!code-csharp[when-with-case#1](~/samples/snippets/csharp/language-reference/keywords/when/when.cs#1)]

## <a name="see-also"></a><span data-ttu-id="c127e-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="c127e-119">See also</span></span>

- [<span data-ttu-id="c127e-120">switch ステートメント</span><span class="sxs-lookup"><span data-stu-id="c127e-120">switch statement</span></span>](switch.md)
- [<span data-ttu-id="c127e-121">try/catch ステートメント</span><span class="sxs-lookup"><span data-stu-id="c127e-121">try/catch statement</span></span>](try-catch.md)
- [<span data-ttu-id="c127e-122">try/catch/finally ステートメント</span><span class="sxs-lookup"><span data-stu-id="c127e-122">try/catch/finally statement</span></span>](try-catch-finally.md)
