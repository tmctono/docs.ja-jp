---
title: () 演算子 - C# リファレンス
ms.custom: seodec18
ms.date: 01/15/2019
f1_keywords:
- ()_CSharpKeyword
helpviewer_keywords:
- type conversion [C#], () operator
- cast operator [C#]
- () operator [C#]
ms.assetid: 846e1f94-8a8c-42fc-a42c-fbd38e70d8cc
ms.openlocfilehash: 8f7382a49c81b6fd8e104b864ffc2f70db7fe4a6
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758114"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="41197-102">() 演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="41197-102">() operator (C# Reference)</span></span>

<span data-ttu-id="41197-103">通常、かっこ (`()`) は、メソッドまたはデリゲートの呼び出し、またはキャスト式内で使用されます。</span><span class="sxs-lookup"><span data-stu-id="41197-103">Parentheses, `()`, are typically used for method or delegate invocation or in cast expressions.</span></span>

<span data-ttu-id="41197-104">式に含まれる演算を評価する順序を指定する場合にもかっこを使用します。</span><span class="sxs-lookup"><span data-stu-id="41197-104">You also use parentheses to specify the order in which to evaluate operations in an expression.</span></span> <span data-ttu-id="41197-105">詳細については、「[演算子](../../programming-guide/statements-expressions-operators/operators.md)」記事の「[かっこの追加](../../programming-guide/statements-expressions-operators/operators.md#adding-parentheses)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="41197-105">For more information, see the [Adding parentheses](../../programming-guide/statements-expressions-operators/operators.md#adding-parentheses) section of the [Operators](../../programming-guide/statements-expressions-operators/operators.md) article.</span></span> <span data-ttu-id="41197-106">優先順位順に並べられた演算子の一覧については、「[C# 演算子](index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41197-106">For the list of operators ordered by precedence level, see [C# operators](index.md).</span></span>

## <a name="method-invocation"></a><span data-ttu-id="41197-107">メソッドの呼び出し</span><span class="sxs-lookup"><span data-stu-id="41197-107">Method invocation</span></span>

<span data-ttu-id="41197-108">メソッド (引数を指定した場合と指定しない場合) とデリゲートを呼び出す方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="41197-108">The following example demonstrates how to invoke a method, with or without arguments, and a delegate:</span></span>

[!code-csharp-interactive[use for invocation](~/samples/csharp/language-reference/operators/InvocationOperatorExamples.cs#Invocation)]

<span data-ttu-id="41197-109">かっこは、[`new`](../keywords/new-operator.md) 演算子を使用して[コンストラクター](../../programming-guide/classes-and-structs/constructors.md)を呼び出すときにも使用します。</span><span class="sxs-lookup"><span data-stu-id="41197-109">You also use parentheses when you invoke a [constructor](../../programming-guide/classes-and-structs/constructors.md) with a [`new`](../keywords/new-operator.md) operator.</span></span>

<span data-ttu-id="41197-110">メソッドの詳細については、「[メソッド](../../programming-guide/classes-and-structs/methods.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41197-110">For more information about methods, see [Methods](../../programming-guide/classes-and-structs/methods.md).</span></span> <span data-ttu-id="41197-111">デリゲートの詳細については、「[デリゲート](../../programming-guide/delegates/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41197-111">For more information about delegates, see [Delegates](../../programming-guide/delegates/index.md).</span></span>

## <a name="cast-expression"></a><span data-ttu-id="41197-112">キャスト式</span><span class="sxs-lookup"><span data-stu-id="41197-112">Cast expression</span></span>

<span data-ttu-id="41197-113">`(T)E` という形式のキャスト式で、変換演算子が呼び出され、式 `E` の値が型 `T` に変換されます。</span><span class="sxs-lookup"><span data-stu-id="41197-113">A cast expression of the form `(T)E` invokes a conversion operator to convert the value of expression `E` to type `T`.</span></span> <span data-ttu-id="41197-114">型 `E` から型 `T` への明示的な変換が存在しない場合は、コンパイル時エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="41197-114">If no explicit conversion exists from the type of `E` to type `T`, a compile-time error occurs.</span></span> <span data-ttu-id="41197-115">変換演算子を定義する方法については、[明示的なキーワード](../keywords/explicit.md)と[暗黙的なキーワード](../keywords/implicit.md)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41197-115">For information about how to define a conversion operator, see the [explicit](../keywords/explicit.md) and [implicit](../keywords/implicit.md) keyword articles.</span></span>

<span data-ttu-id="41197-116">数値間の型変換の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="41197-116">The following example demonstrates type conversion between numeric types:</span></span>

[!code-csharp-interactive[use for cast](~/samples/csharp/language-reference/operators/InvocationOperatorExamples.cs#Cast)]

<span data-ttu-id="41197-117">数値型間の事前に定義された明示的な変換については、「[明示的な数値変換の一覧表](../keywords/explicit-numeric-conversions-table.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41197-117">For more information about predefined explicit conversions between numeric types, see [Explicit numeric conversions table](../keywords/explicit-numeric-conversions-table.md).</span></span>

<span data-ttu-id="41197-118">詳細については、「[キャストと型変換](../../programming-guide/types/casting-and-type-conversions.md)」と「[変換演算子](../../programming-guide/statements-expressions-operators/conversion-operators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41197-118">For more information, see [Casting and type conversions](../../programming-guide/types/casting-and-type-conversions.md) and [Conversion operators](../../programming-guide/statements-expressions-operators/conversion-operators.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="41197-119">演算子のオーバーロード可/不可</span><span class="sxs-lookup"><span data-stu-id="41197-119">Operator overloadability</span></span>

<span data-ttu-id="41197-120">`()` 演算子はオーバーロードできません。</span><span class="sxs-lookup"><span data-stu-id="41197-120">The operator `()` cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="41197-121">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="41197-121">C# language specification</span></span>

<span data-ttu-id="41197-122">詳細については、「[C# 言語仕様](../language-specification/index.md)」の「[Invocation 式](~/_csharplang/spec/expressions.md#invocation-expressions)」セクションと「[キャスト式](~/_csharplang/spec/expressions.md#cast-expressions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41197-122">For more information, see the [Invocation expressions](~/_csharplang/spec/expressions.md#invocation-expressions) and [Cast expressions](~/_csharplang/spec/expressions.md#cast-expressions) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="41197-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="41197-123">See also</span></span>

- [<span data-ttu-id="41197-124">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="41197-124">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="41197-125">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="41197-125">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="41197-126">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="41197-126">C# Operators</span></span>](index.md)
