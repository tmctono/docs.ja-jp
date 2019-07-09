---
title: explicit キーワード - C# リファレンス
ms.custom: seodec18
ms.date: 08/24/2018
f1_keywords:
- explicit_CSharpKeyword
- explicit
helpviewer_keywords:
- explicit keyword [C#]
ms.assetid: cfb8f42a-e411-4db2-af9b-796b05644846
ms.openlocfilehash: a260c6f1ccac6e09770f1cb8f43d5d872b4b2650
ms.sourcegitcommit: eaa6d5cd0f4e7189dbe0bd756e9f53508b01989e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2019
ms.locfileid: "67610101"
---
# <a name="explicit-c-reference"></a><span data-ttu-id="07323-102">explicit (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="07323-102">explicit (C# Reference)</span></span>

<span data-ttu-id="07323-103">`explicit` キーワードは、キャストを使用して呼び出す必要があるユーザー定義型変換演算子を宣言します。</span><span class="sxs-lookup"><span data-stu-id="07323-103">The `explicit` keyword declares a user-defined type conversion operator that must be invoked with a cast.</span></span>

<span data-ttu-id="07323-104">次の例では、`Fahrenheit` クラスから `Celsius` クラスに変換される演算子が定義されます。</span><span class="sxs-lookup"><span data-stu-id="07323-104">The following example defines the operator that converts from a `Fahrenheit` class to a `Celsius` class.</span></span> <span data-ttu-id="07323-105">この演算子は、`Fahrenheit`クラス内または `Celsius` クラス内のいずれかで定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07323-105">The operator must be defined either inside a `Fahrenheit` class or a `Celsius` class:</span></span>

[!code-csharp[csrefKeywordsConversion#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#2)]

<span data-ttu-id="07323-106">次の例に示すように、定義された変換演算子はキャストを使用して呼び出します。</span><span class="sxs-lookup"><span data-stu-id="07323-106">You invoke the defined conversion operator with a cast, as the following example shows:</span></span>

[!code-csharp[csrefKeywordsConversion#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#3)]

<span data-ttu-id="07323-107">変換演算子は、ソースの型をターゲットの型に変換します。</span><span class="sxs-lookup"><span data-stu-id="07323-107">The conversion operator converts from a source type to a target type.</span></span> <span data-ttu-id="07323-108">変換演算子はソースの型によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="07323-108">The source type provides the conversion operator.</span></span> <span data-ttu-id="07323-109">暗黙的な変換とは異なり、変換演算子はキャストを使用して明示的に呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="07323-109">Unlike implicit conversion, explicit conversion operators must be invoked by means of a cast.</span></span> <span data-ttu-id="07323-110">変換操作によって例外が発生したり、情報が失われる可能性がある場合は、その操作を `explicit` としてマークする必要があります。</span><span class="sxs-lookup"><span data-stu-id="07323-110">If a conversion operation can cause exceptions or lose information, you should mark it `explicit`.</span></span> <span data-ttu-id="07323-111">これにより、予期しない結果をもたらす可能性がある変換操作がコンパイラによって暗黙的に呼び出されるのを防止できます。</span><span class="sxs-lookup"><span data-stu-id="07323-111">This prevents the compiler from silently invoking the conversion operation with possibly unforeseen consequences.</span></span>

<span data-ttu-id="07323-112">キャストを省略すると、コンパイル時エラー CS0266 が返されます。</span><span class="sxs-lookup"><span data-stu-id="07323-112">Omitting the cast results in compile-time error CS0266.</span></span>

<span data-ttu-id="07323-113">詳しくは、「[変換演算子の使用](../../programming-guide/statements-expressions-operators/using-conversion-operators.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="07323-113">For more information, see [Using Conversion Operators](../../programming-guide/statements-expressions-operators/using-conversion-operators.md).</span></span>

## <a name="example"></a><span data-ttu-id="07323-114">例</span><span class="sxs-lookup"><span data-stu-id="07323-114">Example</span></span>

<span data-ttu-id="07323-115">次のコードは、`Fahrenheit` クラスと `Celsius` クラスを提供する場合の例です。これらの各クラスは、他方のクラスへの明示的な変換演算子を提供します。</span><span class="sxs-lookup"><span data-stu-id="07323-115">The following example provides a `Fahrenheit` and a `Celsius` class, each of which provides an explicit conversion operator to the other class.</span></span>

[!code-csharp[csrefKeywordsConversion#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#1)]

## <a name="example"></a><span data-ttu-id="07323-116">例</span><span class="sxs-lookup"><span data-stu-id="07323-116">Example</span></span>

<span data-ttu-id="07323-117">次のコードは、単一の 10 進数を表す構造体 (`Digit`) を定義する場合の例です。</span><span class="sxs-lookup"><span data-stu-id="07323-117">The following example defines a struct, `Digit`, that represents a single decimal digit.</span></span> <span data-ttu-id="07323-118">`byte` を `Digit` に変換するための演算子が定義されていますが、すべてのバイトを `Digit` に変換できるとは限らないため、変換を explicit にしています。</span><span class="sxs-lookup"><span data-stu-id="07323-118">An operator is defined for conversions from `byte` to `Digit`, but because not all bytes can be converted to a `Digit`, the conversion is explicit.</span></span>

[!code-csharp[csrefKeywordsConversion#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="07323-119">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="07323-119">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="07323-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="07323-120">See also</span></span>

- [<span data-ttu-id="07323-121">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="07323-121">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="07323-122">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="07323-122">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="07323-123">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="07323-123">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="07323-124">implicit</span><span class="sxs-lookup"><span data-stu-id="07323-124">implicit</span></span>](implicit.md)
- [<span data-ttu-id="07323-125">演算子のオーバーロード</span><span class="sxs-lookup"><span data-stu-id="07323-125">Operator overloading</span></span>](../operators/operator-overloading.md)
- [<span data-ttu-id="07323-126">方法: 構造体間にユーザー定義の変換を実装する</span><span class="sxs-lookup"><span data-stu-id="07323-126">How to: Implement User-Defined Conversions Between Structs</span></span>](../../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
- <span data-ttu-id="07323-127">[Chained user-defined explicit conversions in C#](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/) (C# でのユーザー定義の明示的変換の連結)</span><span class="sxs-lookup"><span data-stu-id="07323-127">[Chained user-defined explicit conversions in C#](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)</span></span>
