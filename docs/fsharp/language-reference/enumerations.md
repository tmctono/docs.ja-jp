---
title: 列挙
description: リテラルの代わりにF#列挙を使用して、コードを読みやすく、保守しやすくする方法について説明します。
ms.date: 05/16/2016
ms.openlocfilehash: 784cd9612b199e4648bb64432d3b4422ad35f649
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630344"
---
# <a name="enumerations"></a><span data-ttu-id="fa1d6-103">列挙</span><span class="sxs-lookup"><span data-stu-id="fa1d6-103">Enumerations</span></span>

<span data-ttu-id="fa1d6-104">列挙*型とも*呼ばれる*列挙体*は、値のサブセットにラベルが割り当てられる整数型です。</span><span class="sxs-lookup"><span data-stu-id="fa1d6-104">*Enumerations*, also known as *enums*, , are integral types where labels are assigned to a subset of the values.</span></span> <span data-ttu-id="fa1d6-105">リテラルの代わりに使用すると、コードの読み取りおよび保守が容易になります。</span><span class="sxs-lookup"><span data-stu-id="fa1d6-105">You can use them in place of literals to make code more readable and maintainable.</span></span>

## <a name="syntax"></a><span data-ttu-id="fa1d6-106">構文</span><span class="sxs-lookup"><span data-stu-id="fa1d6-106">Syntax</span></span>

```fsharp
type enum-name =
| value1 = integer-literal1
| value2 = integer-literal2
...
```

## <a name="remarks"></a><span data-ttu-id="fa1d6-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="fa1d6-107">Remarks</span></span>

<span data-ttu-id="fa1d6-108">列挙体は、値を指定できる点を除いて、単純な値を持つ判別共用体とよく似ています。</span><span class="sxs-lookup"><span data-stu-id="fa1d6-108">An enumeration looks much like a discriminated union that has simple values, except that the values can be specified.</span></span> <span data-ttu-id="fa1d6-109">値は通常、0または1から始まる整数、またはビット位置を表す整数です。</span><span class="sxs-lookup"><span data-stu-id="fa1d6-109">The values are typically integers that start at 0 or 1, or integers that represent bit positions.</span></span> <span data-ttu-id="fa1d6-110">列挙体がビット位置を表すことを目的としている場合は、 [Flags](xref:System.FlagsAttribute)属性も使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa1d6-110">If an enumeration is intended to represent bit positions, you should also use the [Flags](xref:System.FlagsAttribute) attribute.</span></span>

<span data-ttu-id="fa1d6-111">列挙型の基になる型は、使用されるリテラルから決定されます。したがって、たとえば`1u`、、 `2u`などのサフィックスでリテラルを使用して、符号なし整数 (`uint32`) 型にすることができます。</span><span class="sxs-lookup"><span data-stu-id="fa1d6-111">The underlying type of the enumeration is determined from the literal that is used, so that, for example, you can use literals with a suffix, such as `1u`, `2u`, and so on, for an unsigned integer (`uint32`) type.</span></span>

<span data-ttu-id="fa1d6-112">名前付きの値を参照する場合は、列挙型自体の名前を修飾子として使用する必要があり`enum-name.value1`ます。これ`value1`は、だけではありません。</span><span class="sxs-lookup"><span data-stu-id="fa1d6-112">When you refer to the named values, you must use the name of the enumeration type itself as a qualifier, that is, `enum-name.value1`, not just `value1`.</span></span> <span data-ttu-id="fa1d6-113">この動作は、判別共用体の動作とは異なります。</span><span class="sxs-lookup"><span data-stu-id="fa1d6-113">This behavior differs from that of discriminated unions.</span></span> <span data-ttu-id="fa1d6-114">これは、列挙体には常に[RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15)属性が含まれているためです。</span><span class="sxs-lookup"><span data-stu-id="fa1d6-114">This is because enumerations always have the [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) attribute.</span></span>

<span data-ttu-id="fa1d6-115">次のコードは、列挙体の宣言と使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="fa1d6-115">The following code shows the declaration and use of an enumeration.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2101.fs)]

<span data-ttu-id="fa1d6-116">次のコードに示すように、適切な演算子を使用して、列挙型を基になる型に簡単に変換できます。</span><span class="sxs-lookup"><span data-stu-id="fa1d6-116">You can easily convert enumerations to the underlying type by using the appropriate operator, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2102.fs)]

<span data-ttu-id="fa1d6-117">列挙`sbyte`型は`byte` 、、`char`、 `uint16` 、`int32` 、、`uint32`、、、、およびのいずれかの基になる型を持つことができます。 `int64` `int16` `uint16` `uint64`</span><span class="sxs-lookup"><span data-stu-id="fa1d6-117">Enumerated types can have one of the following underlying types: `sbyte`, `byte`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint16`, `uint64`, and `char`.</span></span> <span data-ttu-id="fa1d6-118">列挙型は、から`System.Enum`継承される型として .NET Framework で表されます。これは、から`System.ValueType`継承されます。</span><span class="sxs-lookup"><span data-stu-id="fa1d6-118">Enumeration types are represented in the .NET Framework as types that are inherited from `System.Enum`, which in turn is inherited from `System.ValueType`.</span></span> <span data-ttu-id="fa1d6-119">したがって、これらは、スタックに配置されている値型、または親オブジェクトのインラインにある値型であり、基になる型の値は列挙体の有効な値です。</span><span class="sxs-lookup"><span data-stu-id="fa1d6-119">Thus, they are value types that are located on the stack or inline in the containing object, and any value of the underlying type is a valid value of the enumeration.</span></span> <span data-ttu-id="fa1d6-120">これは、名前のない値をキャッチするパターンを指定する必要があるため、列挙値でパターンマッチングを行う場合に非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="fa1d6-120">This is significant when pattern matching on enumeration values, because you have to provide a pattern that catches the unnamed values.</span></span>

<span data-ttu-id="fa1d6-121">`enum`関数の F# ライブラリで使用できます、定義済みの以外の値も、列挙値を生成する名前付きの値。</span><span class="sxs-lookup"><span data-stu-id="fa1d6-121">The `enum` function in the F# library can be used to generate an enumeration value, even a value other than one of the predefined, named values.</span></span> <span data-ttu-id="fa1d6-122">関数は次`enum`のように使用します。</span><span class="sxs-lookup"><span data-stu-id="fa1d6-122">You use the `enum` function as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2103.fs)]

<span data-ttu-id="fa1d6-123">既定`enum`の関数は、型`int32`で動作します。</span><span class="sxs-lookup"><span data-stu-id="fa1d6-123">The default `enum` function works with type `int32`.</span></span> <span data-ttu-id="fa1d6-124">そのため、基になるその他の型を持つ列挙型では使用できません。</span><span class="sxs-lookup"><span data-stu-id="fa1d6-124">Therefore, it cannot be used with enumeration types that have other underlying types.</span></span> <span data-ttu-id="fa1d6-125">代わりに、次のものを使用します。</span><span class="sxs-lookup"><span data-stu-id="fa1d6-125">Instead, use the following.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2104.fs)]

<span data-ttu-id="fa1d6-126">さらに、列挙型のケースは常`public`にとして出力されます。</span><span class="sxs-lookup"><span data-stu-id="fa1d6-126">Additionally, cases for enums are always emitted as `public`.</span></span> <span data-ttu-id="fa1d6-127">これは、とその他のC# .net プラットフォームとの連携を行うためのものです。</span><span class="sxs-lookup"><span data-stu-id="fa1d6-127">This is so that they align with C# and the rest of the .NET platform.</span></span>

## <a name="see-also"></a><span data-ttu-id="fa1d6-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="fa1d6-128">See also</span></span>

- [<span data-ttu-id="fa1d6-129">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="fa1d6-129">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="fa1d6-130">キャストと変換</span><span class="sxs-lookup"><span data-stu-id="fa1d6-130">Casting and Conversions</span></span>](casting-and-conversions.md)
