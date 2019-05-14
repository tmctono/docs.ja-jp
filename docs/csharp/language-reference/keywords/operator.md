---
title: operator キーワード - C# リファレンス
ms.custom: seodec18
description: 組み込みの C# 演算子をオーバー ロードする方法を学習する
ms.date: 08/27/2018
f1_keywords:
- operator_CSharpKeyword
- operator
helpviewer_keywords:
- operator keyword [C#]
ms.assetid: 59218cce-e90e-42f6-a6bb-30300981b86a
ms.openlocfilehash: 47ce91c343092ac2f7555c1edf3418527776e131
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64754761"
---
# <a name="operator-c-reference"></a><span data-ttu-id="8d2d1-103">演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="8d2d1-103">operator (C# Reference)</span></span>

<span data-ttu-id="8d2d1-104">`operator` キーワードを使用して、組み込みの演算子をオーバーロードしたり、クラスまたは構造体宣言内でユーザー定義の変換を行ったりすることができます。</span><span class="sxs-lookup"><span data-stu-id="8d2d1-104">Use the `operator` keyword to overload a built-in operator or to provide a user-defined conversion in a class or struct declaration.</span></span>

<span data-ttu-id="8d2d1-105">カスタム クラスまたは構造体上で演算子をオーバー ロードするには、対応する型で演算子の宣言を作成します。</span><span class="sxs-lookup"><span data-stu-id="8d2d1-105">To overload an operator on a custom class or struct, you create an operator declaration in the corresponding type.</span></span> <span data-ttu-id="8d2d1-106">組み込みの C# 演算子をオーバーロードする演算子宣言は、次の規則を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d2d1-106">The operator declaration that overloads a built-in C# operator must satisfy the following rules:</span></span>

- <span data-ttu-id="8d2d1-107">これには、`public` と `static` 修飾子の両方が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8d2d1-107">It includes both a `public` and a `static` modifier.</span></span>
- <span data-ttu-id="8d2d1-108">これには `operator X` が含まれています。ここで、`X` は、オーバーロードされる演算子の名前またはシンボルです。</span><span class="sxs-lookup"><span data-stu-id="8d2d1-108">It includes `operator X` where `X` is the name or symbol of the operator being overloaded.</span></span>
- <span data-ttu-id="8d2d1-109">単項演算子にはパラメーターが 1 つ、2 項演算子にはパラメーターが 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="8d2d1-109">Unary operators have one parameter, and binary operators have two parameters.</span></span> <span data-ttu-id="8d2d1-110">いずれの場合も、少なくとも 1 つのパラメーターが演算子を宣言するクラスまたは構造体と同じ型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d2d1-110">In each case, at least one parameter must be the same type as the class or struct that declares the operator.</span></span>

<span data-ttu-id="8d2d1-111">変換演算子を定義する方法については、[明示的なキーワード](explicit.md)と[暗黙的なキーワード](implicit.md)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d2d1-111">For information about how to define conversion operators, see the [explicit](explicit.md) and [implicit](implicit.md) keyword articles.</span></span>

<span data-ttu-id="8d2d1-112">オーバーロードできる C# 演算子の概要については、[オーバーロード可能な演算子](../../programming-guide/statements-expressions-operators/overloadable-operators.md)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d2d1-112">For an overview of the C# operators that can be overloaded, see the [Overloadable operators](../../programming-guide/statements-expressions-operators/overloadable-operators.md) article.</span></span>

## <a name="example"></a><span data-ttu-id="8d2d1-113">例</span><span class="sxs-lookup"><span data-stu-id="8d2d1-113">Example</span></span>

<span data-ttu-id="8d2d1-114">次の例では、小数部を表す `Fraction` 型が定義されています。</span><span class="sxs-lookup"><span data-stu-id="8d2d1-114">The following example defines a `Fraction` type that represents fractional numbers.</span></span> <span data-ttu-id="8d2d1-115">このクラスは、小数の加算および乗算を実行するために `+` 演算子および `*` 演算子をオーバーロードします。また、`Fraction` 型を `double` 型に変換する変換演算子も提供します。</span><span class="sxs-lookup"><span data-stu-id="8d2d1-115">It overloads the `+` and `*` operators to perform fractional addition and multiplication, and also provides a conversion operator that converts a `Fraction` type to a `double` type.</span></span>

[!code-csharp[csrefKeywordsConversion#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#6)]

## <a name="c-language-specification"></a><span data-ttu-id="8d2d1-116">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="8d2d1-116">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="8d2d1-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="8d2d1-117">See also</span></span>

- [<span data-ttu-id="8d2d1-118">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="8d2d1-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="8d2d1-119">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="8d2d1-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="8d2d1-120">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="8d2d1-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="8d2d1-121">implicit</span><span class="sxs-lookup"><span data-stu-id="8d2d1-121">implicit</span></span>](implicit.md)
- [<span data-ttu-id="8d2d1-122">explicit</span><span class="sxs-lookup"><span data-stu-id="8d2d1-122">explicit</span></span>](explicit.md)
- [<span data-ttu-id="8d2d1-123">オーバーロード可能な演算子</span><span class="sxs-lookup"><span data-stu-id="8d2d1-123">Overloadable operators</span></span>](../../programming-guide/statements-expressions-operators/overloadable-operators.md)
- [<span data-ttu-id="8d2d1-124">方法: 構造体間にユーザー定義の変換を実装する</span><span class="sxs-lookup"><span data-stu-id="8d2d1-124">How to: Implement User-Defined Conversions Between Structs</span></span>](../../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
