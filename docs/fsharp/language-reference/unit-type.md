---
title: Unit 型
description: 値はありませんが必要なまたは必要なときに言語の構文で値が必要な場所、場所を保持するために F# 'unit' の型を使用する多くの場合について説明します。
ms.date: 05/16/2016
ms.openlocfilehash: 4e586702324565b8dcd4f6c7e11a0e1754f89c58
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630174"
---
# <a name="unit-type"></a><span data-ttu-id="36fdc-103">Unit 型</span><span class="sxs-lookup"><span data-stu-id="36fdc-103">Unit Type</span></span>

<span data-ttu-id="36fdc-104">この型は、特定の値がないことを示す型です`unit` 。型には1つの値しかありません。これは、他の値が存在しない場合や必要な場合にプレースホルダーとして機能します。 `unit`</span><span class="sxs-lookup"><span data-stu-id="36fdc-104">The `unit` type is a type that indicates the absence of a specific value; the `unit` type has only a single value, which acts as a placeholder when no other value exists or is needed.</span></span>

## <a name="syntax"></a><span data-ttu-id="36fdc-105">構文</span><span class="sxs-lookup"><span data-stu-id="36fdc-105">Syntax</span></span>

```fsharp
// The value of the unit type.
()
```

## <a name="remarks"></a><span data-ttu-id="36fdc-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="36fdc-106">Remarks</span></span>

<span data-ttu-id="36fdc-107">すべての F# の式は、値に評価される必要があります。</span><span class="sxs-lookup"><span data-stu-id="36fdc-107">Every F# expression must evaluate to a value.</span></span> <span data-ttu-id="36fdc-108">対象となる値を生成しない式の場合は、型`unit`の値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="36fdc-108">For expressions that do not generate a value that is of interest, the value of type `unit` is used.</span></span> <span data-ttu-id="36fdc-109">型`unit`は、や`void` C++などC#の言語の型に似ています。</span><span class="sxs-lookup"><span data-stu-id="36fdc-109">The `unit` type resembles the `void` type in languages such as C# and C++.</span></span>

<span data-ttu-id="36fdc-110">型には1つの値があり、その値はトークン`()`によって示されます。 `unit`</span><span class="sxs-lookup"><span data-stu-id="36fdc-110">The `unit` type has a single value, and that value is indicated by the token `()`.</span></span>

<span data-ttu-id="36fdc-111">値、`unit`型が F# 言語の構文で、値が必要な場合は、値はありませんが必要なまたは必要なときに、場所を保持するためにプログラミングでよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="36fdc-111">The value of the `unit` type is often used in F# programming to hold the place where a value is required by the language syntax, but when no value is needed or desired.</span></span> <span data-ttu-id="36fdc-112">例として、 `printf`関数の戻り値が挙げられます。</span><span class="sxs-lookup"><span data-stu-id="36fdc-112">An example might be the return value of a `printf` function.</span></span> <span data-ttu-id="36fdc-113">関数では`printf`操作の重要なアクションが発生するため、関数は実際の値を返す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="36fdc-113">Because the important actions of the `printf` operation occur in the function, the function does not have to return an actual value.</span></span> <span data-ttu-id="36fdc-114">したがって、戻り値の型`unit`はです。</span><span class="sxs-lookup"><span data-stu-id="36fdc-114">Therefore, the return value is of type `unit`.</span></span>

<span data-ttu-id="36fdc-115">一部のコンストラクトで`unit`は値が想定されています。</span><span class="sxs-lookup"><span data-stu-id="36fdc-115">Some constructs expect a `unit` value.</span></span> <span data-ttu-id="36fdc-116">たとえば、モジュールの`do`最上位レベルにあるバインドまたはコードは、 `unit`値に評価される必要があります。</span><span class="sxs-lookup"><span data-stu-id="36fdc-116">For example, a `do` binding or any code at the top level of a module is expected to evaluate to a `unit` value.</span></span> <span data-ttu-id="36fdc-117">コンパイラは、次の例に`do`示すように、モジュールの最上位レベルのバインディングまたはコードが、 `unit`使用されていない値以外の結果を生成した場合に警告を報告します。</span><span class="sxs-lookup"><span data-stu-id="36fdc-117">The compiler reports a warning when a `do` binding or code at the top level of a module produces a result other than the `unit` value that is not used, as shown in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet901.fs)]

<span data-ttu-id="36fdc-118">この警告は、関数型プログラミングの特性です。他の .NET プログラミング言語では表示されません。</span><span class="sxs-lookup"><span data-stu-id="36fdc-118">This warning is a characteristic of functional programming; it does not appear in other .NET programming languages.</span></span> <span data-ttu-id="36fdc-119">純粋関数型プログラムでは、どの関数にも副作用がない場合、最終的な戻り値は関数呼び出しの唯一の結果になります。</span><span class="sxs-lookup"><span data-stu-id="36fdc-119">In a purely functional program, in which functions do not have any side effects, the final return value is the only result of a function call.</span></span> <span data-ttu-id="36fdc-120">したがって、結果が無視された場合は、プログラミングエラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="36fdc-120">Therefore, when the result is ignored, it is a possible programming error.</span></span> <span data-ttu-id="36fdc-121">F#は純粋関数型プログラミング言語ではありませんが、可能な限り関数型プログラミングスタイルに従うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="36fdc-121">Although F# is not a purely functional programming language, it is a good practice to follow functional programming style whenever possible.</span></span>

## <a name="see-also"></a><span data-ttu-id="36fdc-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="36fdc-122">See also</span></span>

- [<span data-ttu-id="36fdc-123">プリミティブ</span><span class="sxs-lookup"><span data-stu-id="36fdc-123">Primitive</span></span>](primitive-types.md)
- [<span data-ttu-id="36fdc-124">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="36fdc-124">F# Language Reference</span></span>](index.md)
