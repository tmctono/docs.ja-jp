---
title: bool 型 - C# リファレンス
ms.date: 11/26/2019
f1_keywords:
- bool
- bool_CSharpKeyword
helpviewer_keywords:
- bool data type [C#]
- Boolean [C#]
ms.assetid: 551cfe35-2632-4343-af49-33ad12da08e2
ms.openlocfilehash: 2ba2e54a6b0f24402fc3728dfe19b548a2368830
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "78846446"
---
# <a name="bool-c-reference"></a><span data-ttu-id="8da5a-102">bool (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="8da5a-102">bool (C# reference)</span></span>

<span data-ttu-id="8da5a-103">`bool` 型キーワードは、ブール値 (<xref:System.Boolean?displayProperty=nameWithType> または `true` のいずれか) を表す .NET `false` 構造体型のエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="8da5a-103">The `bool` type keyword is an alias for the .NET <xref:System.Boolean?displayProperty=nameWithType> structure type that represents a Boolean value, which can be either `true` or `false`.</span></span>

<span data-ttu-id="8da5a-104">`bool` 型の値を使って論理演算を実行するには、[ブール論理](../operators/boolean-logical-operators.md)演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="8da5a-104">To perform logical operations with values of the `bool` type, use [Boolean logical](../operators/boolean-logical-operators.md) operators.</span></span> <span data-ttu-id="8da5a-105">`bool` 型は、[比較](../operators/comparison-operators.md)および[等値](../operators/equality-operators.md)演算子の結果の型です。</span><span class="sxs-lookup"><span data-stu-id="8da5a-105">The `bool` type is the result type of [comparison](../operators/comparison-operators.md) and [equality](../operators/equality-operators.md) operators.</span></span> <span data-ttu-id="8da5a-106">`bool` 式は、[if](../keywords/if-else.md)、[do](../keywords/do.md)、[while](../keywords/while.md)、および [for](../keywords/for.md) ステートメントおよび[条件演算子 `?:`](../operators/conditional-operator.md) で制御条件式にすることができます。</span><span class="sxs-lookup"><span data-stu-id="8da5a-106">A `bool` expression can be a controlling conditional expression in the [if](../keywords/if-else.md), [do](../keywords/do.md), [while](../keywords/while.md), and [for](../keywords/for.md) statements and in the [conditional operator `?:`](../operators/conditional-operator.md).</span></span>

<span data-ttu-id="8da5a-107">`bool` 型の既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="8da5a-107">The default value of the `bool` type is `false`.</span></span>

## <a name="literals"></a><span data-ttu-id="8da5a-108">リテラル</span><span class="sxs-lookup"><span data-stu-id="8da5a-108">Literals</span></span>

<span data-ttu-id="8da5a-109">`true` および `false` リテラルを使用して、`bool` 変数を初期化したり、`bool` 値を渡したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="8da5a-109">You can use the `true` and `false` literals to initialize a `bool` variable or to pass a `bool` value:</span></span>

[!code-csharp-interactive[bool literals](snippets/BoolType.cs#Literals)]

## <a name="three-valued-boolean-logic"></a><span data-ttu-id="8da5a-110">3 値ブール型ロジック</span><span class="sxs-lookup"><span data-stu-id="8da5a-110">Three-valued Boolean logic</span></span>

<span data-ttu-id="8da5a-111">3 値ロジックをサポートする必要がある場合は、null 許容型の `bool?` を使用します。たとえば、3 値ブール型をサポートするデータベースを操作する場合などです。</span><span class="sxs-lookup"><span data-stu-id="8da5a-111">Use the nullable `bool?` type, if you need to support the three-valued logic, for example, when you work with databases that support a three-valued Boolean type.</span></span> <span data-ttu-id="8da5a-112">`bool?` オペランドの場合、定義済みの `&` 演算子と `|` 演算子は 3 値ロジックをサポートします。</span><span class="sxs-lookup"><span data-stu-id="8da5a-112">For the `bool?` operands, the predefined `&` and `|` operators support the three-valued logic.</span></span> <span data-ttu-id="8da5a-113">詳細については、「[Boolean logical operators (ブール論理演算子)](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators)」記事の「[Nullable Boolean logical operators (null 許容論理演算子)](../operators/boolean-logical-operators.md)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8da5a-113">For more information, see the [Nullable Boolean logical operators](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) section of the [Boolean logical operators](../operators/boolean-logical-operators.md) article.</span></span>

<span data-ttu-id="8da5a-114">null 許容値型の詳細については、「[null 許容値型](nullable-value-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8da5a-114">For more information about nullable value types, see [Nullable value types](nullable-value-types.md).</span></span>

## <a name="conversions"></a><span data-ttu-id="8da5a-115">コンバージョン</span><span class="sxs-lookup"><span data-stu-id="8da5a-115">Conversions</span></span>

<span data-ttu-id="8da5a-116">C# には、`bool` 型が関係する変換が 2 つのみ用意されています。</span><span class="sxs-lookup"><span data-stu-id="8da5a-116">C# provides only two conversions that involve the `bool` type.</span></span> <span data-ttu-id="8da5a-117">対応する null 許容型の `bool?` への暗黙的な変換と、`bool?` 型からの明示的な変換です。</span><span class="sxs-lookup"><span data-stu-id="8da5a-117">Those are an implicit conversion to the corresponding nullable `bool?` type and an explicit conversion from the `bool?` type.</span></span> <span data-ttu-id="8da5a-118">ただし、.NET には、`bool` 型との間の変換に使用できる追加のメソッドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="8da5a-118">However, .NET provides additional methods that you can use to convert to or from the `bool` type.</span></span> <span data-ttu-id="8da5a-119">詳細については、[ API リファレンス ページの「](/dotnet/api/system.boolean#converting-to-and-from-boolean-values)ブール値との間の変換<xref:System.Boolean?displayProperty=nameWithType>」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8da5a-119">For more information, see the [Converting to and from Boolean values](/dotnet/api/system.boolean#converting-to-and-from-boolean-values) section of the <xref:System.Boolean?displayProperty=nameWithType> API reference page.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="8da5a-120">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="8da5a-120">C# language specification</span></span>

<span data-ttu-id="8da5a-121">詳細については、[C# 言語仕様](~/_csharplang/spec/types.md#the-bool-type)の「[Bool 型](~/_csharplang/spec/introduction.md)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8da5a-121">For more information, see [The bool type](~/_csharplang/spec/types.md#the-bool-type) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8da5a-122">参照</span><span class="sxs-lookup"><span data-stu-id="8da5a-122">See also</span></span>

- [<span data-ttu-id="8da5a-123">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="8da5a-123">C# reference</span></span>](../index.md)
- [<span data-ttu-id="8da5a-124">値型</span><span class="sxs-lookup"><span data-stu-id="8da5a-124">Value types</span></span>](value-types.md)
- [<span data-ttu-id="8da5a-125">True および False 演算子</span><span class="sxs-lookup"><span data-stu-id="8da5a-125">true and false operators</span></span>](../operators/true-false-operators.md)
