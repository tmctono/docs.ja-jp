---
title: Unit 型
description: 値が不要F#な場合や必要な場合に、言語の構文で値が必要とされる場所を保持するために、' unit ' 型がよく使用される方法について説明します。
ms.date: 05/16/2016
ms.openlocfilehash: a5960fb05af50486a78345d10a5ad913e65729e3
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424024"
---
# <a name="unit-type"></a><span data-ttu-id="d8985-103">Unit 型</span><span class="sxs-lookup"><span data-stu-id="d8985-103">Unit Type</span></span>

<span data-ttu-id="d8985-104">`unit` 型は、特定の値が存在しないことを示す型です。`unit` 型には、値が1つだけあります。これは、他の値が存在しない場合や必要な場合にプレースホルダーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="d8985-104">The `unit` type is a type that indicates the absence of a specific value; the `unit` type has only a single value, which acts as a placeholder when no other value exists or is needed.</span></span>

## <a name="syntax"></a><span data-ttu-id="d8985-105">構文</span><span class="sxs-lookup"><span data-stu-id="d8985-105">Syntax</span></span>

```fsharp
// The value of the unit type.
()
```

## <a name="remarks"></a><span data-ttu-id="d8985-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="d8985-106">Remarks</span></span>

<span data-ttu-id="d8985-107">すべてF#の式は、値に評価される必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8985-107">Every F# expression must evaluate to a value.</span></span> <span data-ttu-id="d8985-108">対象となる値を生成しない式の場合は、`unit` 型の値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="d8985-108">For expressions that do not generate a value that is of interest, the value of type `unit` is used.</span></span> <span data-ttu-id="d8985-109">`unit` 型は、やC# C++などの言語の `void` の型に似ています。</span><span class="sxs-lookup"><span data-stu-id="d8985-109">The `unit` type resembles the `void` type in languages such as C# and C++.</span></span>

<span data-ttu-id="d8985-110">`unit` 型には1つの値があり、その値はトークン `()`によって示されます。</span><span class="sxs-lookup"><span data-stu-id="d8985-110">The `unit` type has a single value, and that value is indicated by the token `()`.</span></span>

<span data-ttu-id="d8985-111">`unit` 型の値は、言語構文で値F#が必要な場所を保持するためにプログラミングで使用されることがよくありますが、値が不要な場合、または必要な場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="d8985-111">The value of the `unit` type is often used in F# programming to hold the place where a value is required by the language syntax, but when no value is needed or desired.</span></span> <span data-ttu-id="d8985-112">例としては、`printf` 関数の戻り値が考えられます。</span><span class="sxs-lookup"><span data-stu-id="d8985-112">An example might be the return value of a `printf` function.</span></span> <span data-ttu-id="d8985-113">関数では `printf` 操作の重要なアクションが発生するため、関数は実際の値を返す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d8985-113">Because the important actions of the `printf` operation occur in the function, the function does not have to return an actual value.</span></span> <span data-ttu-id="d8985-114">したがって、戻り値の型は `unit`です。</span><span class="sxs-lookup"><span data-stu-id="d8985-114">Therefore, the return value is of type `unit`.</span></span>

<span data-ttu-id="d8985-115">一部のコンストラクトでは、`unit` 値が想定されています。</span><span class="sxs-lookup"><span data-stu-id="d8985-115">Some constructs expect a `unit` value.</span></span> <span data-ttu-id="d8985-116">たとえば、`do` バインドまたはモジュールの最上位レベルのコードは、`unit` 値に評価される必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8985-116">For example, a `do` binding or any code at the top level of a module is expected to evaluate to a `unit` value.</span></span> <span data-ttu-id="d8985-117">コンパイラは、次の例に示すように、モジュールの最上位レベルにある `do` バインドまたはコードが、使用されていない `unit` 値以外の結果を生成した場合に、警告を報告します。</span><span class="sxs-lookup"><span data-stu-id="d8985-117">The compiler reports a warning when a `do` binding or code at the top level of a module produces a result other than the `unit` value that is not used, as shown in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet901.fs)]

<span data-ttu-id="d8985-118">この警告は、関数型プログラミングの特性です。他の .NET プログラミング言語では表示されません。</span><span class="sxs-lookup"><span data-stu-id="d8985-118">This warning is a characteristic of functional programming; it does not appear in other .NET programming languages.</span></span> <span data-ttu-id="d8985-119">純粋関数型プログラムでは、どの関数にも副作用がない場合、最終的な戻り値は関数呼び出しの唯一の結果になります。</span><span class="sxs-lookup"><span data-stu-id="d8985-119">In a purely functional program, in which functions do not have any side effects, the final return value is the only result of a function call.</span></span> <span data-ttu-id="d8985-120">したがって、結果が無視された場合は、プログラミングエラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d8985-120">Therefore, when the result is ignored, it is a possible programming error.</span></span> <span data-ttu-id="d8985-121">F#は純粋関数型プログラミング言語ではありませんが、可能な限り関数型プログラミングスタイルに従うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d8985-121">Although F# is not a purely functional programming language, it is a good practice to follow functional programming style whenever possible.</span></span>

## <a name="see-also"></a><span data-ttu-id="d8985-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8985-122">See also</span></span>

- [<span data-ttu-id="d8985-123">プリミティブ</span><span class="sxs-lookup"><span data-stu-id="d8985-123">Primitive</span></span>](basic-types.md)
- [<span data-ttu-id="d8985-124">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="d8985-124">F# Language Reference</span></span>](index.md)
