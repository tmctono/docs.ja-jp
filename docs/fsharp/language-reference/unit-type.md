---
title: Unit 型
description: 値はありませんが必要なまたは必要なときに言語の構文で値が必要な場所、場所を保持するために F# 'unit' の型を使用する多くの場合について説明します。
ms.date: 05/16/2016
ms.openlocfilehash: f1866ff12f36f4f8d3eaa1275551c42fc4ade216
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61982528"
---
# <a name="unit-type"></a><span data-ttu-id="21d0d-103">Unit 型</span><span class="sxs-lookup"><span data-stu-id="21d0d-103">Unit Type</span></span>

<span data-ttu-id="21d0d-104">`unit`型は、特定の値がないことを示す型、`unit`型のみ 1 つの値を持つ、その他の値はありませんが存在するか、必要なときに、プレース ホルダーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="21d0d-104">The `unit` type is a type that indicates the absence of a specific value; the `unit` type has only a single value, which acts as a placeholder when no other value exists or is needed.</span></span>

## <a name="syntax"></a><span data-ttu-id="21d0d-105">構文</span><span class="sxs-lookup"><span data-stu-id="21d0d-105">Syntax</span></span>

```fsharp
// The value of the unit type.
()
```

## <a name="remarks"></a><span data-ttu-id="21d0d-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="21d0d-106">Remarks</span></span>

<span data-ttu-id="21d0d-107">すべての F# の式は、値に評価される必要があります。</span><span class="sxs-lookup"><span data-stu-id="21d0d-107">Every F# expression must evaluate to a value.</span></span> <span data-ttu-id="21d0d-108">型の値、目的の値を生成しない式の`unit`使用されます。</span><span class="sxs-lookup"><span data-stu-id="21d0d-108">For expressions that do not generate a value that is of interest, the value of type `unit` is used.</span></span> <span data-ttu-id="21d0d-109">`unit`型に似ています、 `void` c# および C++ などの言語での型。</span><span class="sxs-lookup"><span data-stu-id="21d0d-109">The `unit` type resembles the `void` type in languages such as C# and C++.</span></span>

<span data-ttu-id="21d0d-110">`unit`型が 1 つの値とその値は、トークンで示される`()`します。</span><span class="sxs-lookup"><span data-stu-id="21d0d-110">The `unit` type has a single value, and that value is indicated by the token `()`.</span></span>

<span data-ttu-id="21d0d-111">値、`unit`型が F# 言語の構文で、値が必要な場合は、値はありませんが必要なまたは必要なときに、場所を保持するためにプログラミングでよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="21d0d-111">The value of the `unit` type is often used in F# programming to hold the place where a value is required by the language syntax, but when no value is needed or desired.</span></span> <span data-ttu-id="21d0d-112">例の戻り値があります、`printf`関数。</span><span class="sxs-lookup"><span data-stu-id="21d0d-112">An example might be the return value of a `printf` function.</span></span> <span data-ttu-id="21d0d-113">の重要なアクション、`printf`操作が、関数で発生する関数が実際の値を返す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="21d0d-113">Because the important actions of the `printf` operation occur in the function, the function does not have to return an actual value.</span></span> <span data-ttu-id="21d0d-114">そのため、戻り値が型`unit`します。</span><span class="sxs-lookup"><span data-stu-id="21d0d-114">Therefore, the return value is of type `unit`.</span></span>

<span data-ttu-id="21d0d-115">一部のコンストラクトの期待を`unit`値。</span><span class="sxs-lookup"><span data-stu-id="21d0d-115">Some constructs expect a `unit` value.</span></span> <span data-ttu-id="21d0d-116">たとえば、`do`バインドまたはモジュールの最上位レベルで、コードを評価する予定を`unit`値。</span><span class="sxs-lookup"><span data-stu-id="21d0d-116">For example, a `do` binding or any code at the top level of a module is expected to evaluate to a `unit` value.</span></span> <span data-ttu-id="21d0d-117">コンパイラ警告を報告するときに、`do`バインドまたはコード モジュールの最上位レベル以外の結果を生成、`unit`使用されていない、次の例に示すように値。</span><span class="sxs-lookup"><span data-stu-id="21d0d-117">The compiler reports a warning when a `do` binding or code at the top level of a module produces a result other than the `unit` value that is not used, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet901.fs)]

<span data-ttu-id="21d0d-118">この警告は、関数型プログラミングの特性その他の .NET プログラミング言語では表示されません。</span><span class="sxs-lookup"><span data-stu-id="21d0d-118">This warning is a characteristic of functional programming; it does not appear in other .NET programming languages.</span></span> <span data-ttu-id="21d0d-119">副作用は関数がない、純粋に機能するプログラムでは、最終的な戻り値は、関数呼び出しの結果だけが。</span><span class="sxs-lookup"><span data-stu-id="21d0d-119">In a purely functional program, in which functions do not have any side effects, the final return value is the only result of a function call.</span></span> <span data-ttu-id="21d0d-120">そのため、結果を無視すると、可能性のあるプログラミング エラーです。</span><span class="sxs-lookup"><span data-stu-id="21d0d-120">Therefore, when the result is ignored, it is a possible programming error.</span></span> <span data-ttu-id="21d0d-121">F#が純粋に機能していないプログラミング言語、機能のプログラミング スタイル可能な場合に従うことをお勧めが。</span><span class="sxs-lookup"><span data-stu-id="21d0d-121">Although F# is not a purely functional programming language, it is a good practice to follow functional programming style whenever possible.</span></span>

## <a name="see-also"></a><span data-ttu-id="21d0d-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="21d0d-122">See also</span></span>

- [<span data-ttu-id="21d0d-123">プリミティブ</span><span class="sxs-lookup"><span data-stu-id="21d0d-123">Primitive</span></span>](primitive-types.md)
- [<span data-ttu-id="21d0d-124">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="21d0d-124">F# Language Reference</span></span>](index.md)