---
title: ユーザー定義の変換演算子 - C# リファレンス
description: C# でカスタムの暗黙的および明示的な型変換を定義する方法について説明します。
ms.date: 07/09/2019
f1_keywords:
- explicit_CSharpKeyword
- implicit_CSharpKeyword
helpviewer_keywords:
- explicit keyword [C#]
- implicit keyword [C#]
- conversion operator [C#]
- user-defined conversion [C#]
ms.openlocfilehash: 5d1882048b2af12c29a3771055cbeba9565b7dab
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67787398"
---
# <a name="user-defined-conversion-operators-c-reference"></a><span data-ttu-id="33611-103">ユーザー定義の変換演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="33611-103">User-defined conversion operators (C# reference)</span></span>

<span data-ttu-id="33611-104">ユーザー定義型では、別の型との間にカスタムの暗黙的または明示的な変換を定義できます。</span><span class="sxs-lookup"><span data-stu-id="33611-104">A user-defined type can define a custom implicit or explicit conversion from or to another type.</span></span>

<span data-ttu-id="33611-105">暗黙的変換では特別な構文を呼び出す必要はなく、代入やメソッド呼び出しなど、さまざまな状況で発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="33611-105">Implicit conversions don't require special syntax to be invoked and can occur in a variety of situations, for example, in assignments and methods invocations.</span></span> <span data-ttu-id="33611-106">事前に定義された C# の暗黙的な変換は常に成功し、例外がスローされたり、情報が失われたりすることはありません。</span><span class="sxs-lookup"><span data-stu-id="33611-106">Predefined C# implicit conversions always succeed and never throw an exception or lose information.</span></span> <span data-ttu-id="33611-107">ユーザー定義の暗黙的な変換も同様に動作します。</span><span class="sxs-lookup"><span data-stu-id="33611-107">User-defined implicit conversions should behave in that way as well.</span></span> <span data-ttu-id="33611-108">カスタムの変換によって例外がスローされたり情報が失われたりする可能性がある場合は、明示的な変換として定義します。</span><span class="sxs-lookup"><span data-stu-id="33611-108">If a custom conversion can throw an exception or lose information, define it as an explicit conversion.</span></span>

<span data-ttu-id="33611-109">ユーザー定義の変換は、[is](type-testing-and-conversion-operators.md#is-operator) および [as](type-testing-and-conversion-operators.md#as-operator) 演算子からは考慮されません。</span><span class="sxs-lookup"><span data-stu-id="33611-109">User-defined conversions are not considered by the [is](type-testing-and-conversion-operators.md#is-operator) and [as](type-testing-and-conversion-operators.md#as-operator) operators.</span></span> <span data-ttu-id="33611-110">ユーザー定義の明示的な変換を呼び出すには、[キャスト演算子 ()](type-testing-and-conversion-operators.md#cast-operator-) を使用します。</span><span class="sxs-lookup"><span data-stu-id="33611-110">Use the [cast operator ()](type-testing-and-conversion-operators.md#cast-operator-) to invoke a user-defined explicit conversion.</span></span>

<span data-ttu-id="33611-111">暗黙的または明示的な変換を定義するには、`operator` とそれぞれ `implicit` または `explicit` のキーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="33611-111">Use the `operator` and `implicit` or `explicit` keywords to define an implicit or explicit conversion, respectively.</span></span> <span data-ttu-id="33611-112">変換を定義する型は、その変換のソース型またはターゲット型のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="33611-112">The type that defines a conversion must be either a source type or a target type of that conversion.</span></span> <span data-ttu-id="33611-113">2 つのユーザー定義型間の変換は、2 つの型のどちらでも定義できます。</span><span class="sxs-lookup"><span data-stu-id="33611-113">A conversion between two user-defined types can be defined in either of the two types.</span></span>

<span data-ttu-id="33611-114">次の例は、暗黙的な変換と明示的な変換を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="33611-114">The following example demonstrates how to define an implicit and explicit conversion:</span></span>

[!code-csharp[implicit an explicit conversions](~/samples/csharp/language-reference/operators/UserDefinedConversions.cs)]

<span data-ttu-id="33611-115">また、事前に定義された C# 演算子をオーバーロードするには `operator` キーワードも使用します。</span><span class="sxs-lookup"><span data-stu-id="33611-115">You also use the `operator` keyword to overload a predefined C# operator.</span></span> <span data-ttu-id="33611-116">詳細については、「[演算子のオーバーロード](operator-overloading.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33611-116">For more information, see [Operator overloading](operator-overloading.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="33611-117">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="33611-117">C# language specification</span></span>

<span data-ttu-id="33611-118">詳細については、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="33611-118">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="33611-119">変換演算子</span><span class="sxs-lookup"><span data-stu-id="33611-119">Conversion operators</span></span>](~/_csharplang/spec/classes.md#conversion-operators)
- [<span data-ttu-id="33611-120">ユーザー定義の変換</span><span class="sxs-lookup"><span data-stu-id="33611-120">User-defined conversions</span></span>](~/_csharplang/spec/conversions.md#user-defined-conversions)
- [<span data-ttu-id="33611-121">暗黙的な変換</span><span class="sxs-lookup"><span data-stu-id="33611-121">Implicit conversions</span></span>](~/_csharplang/spec/conversions.md#implicit-conversions)
- [<span data-ttu-id="33611-122">明示的な変換</span><span class="sxs-lookup"><span data-stu-id="33611-122">Explicit conversions</span></span>](~/_csharplang/spec/conversions.md#explicit-conversions)

## <a name="see-also"></a><span data-ttu-id="33611-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="33611-123">See also</span></span>

- [<span data-ttu-id="33611-124">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="33611-124">C# reference</span></span>](../index.md)
- [<span data-ttu-id="33611-125">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="33611-125">C# operators</span></span>](index.md)
- [<span data-ttu-id="33611-126">演算子のオーバーロード</span><span class="sxs-lookup"><span data-stu-id="33611-126">Operator overloading</span></span>](operator-overloading.md)
- [<span data-ttu-id="33611-127">型テストおよび変換演算子</span><span class="sxs-lookup"><span data-stu-id="33611-127">Type-testing and conversion operators</span></span>](type-testing-and-conversion-operators.md)
- [<span data-ttu-id="33611-128">キャストと型変換</span><span class="sxs-lookup"><span data-stu-id="33611-128">Casting and type conversion</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
- <span data-ttu-id="33611-129">[Chained user-defined explicit conversions in C#](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/) (C# でのユーザー定義の明示的変換の連結)</span><span class="sxs-lookup"><span data-stu-id="33611-129">[Chained user-defined explicit conversions in C#](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)</span></span>
