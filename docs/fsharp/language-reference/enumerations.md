---
title: 列挙
description: 'リテラルの代わりに F # の列挙を使用して、コードを読みやすく、保守しやすくする方法について説明します。'
ms.date: 08/15/2020
ms.openlocfilehash: 5f298691ce48a06c203930c7742cf007c819dc33
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812108"
---
# <a name="enumerations"></a><span data-ttu-id="a76b8-103">列挙</span><span class="sxs-lookup"><span data-stu-id="a76b8-103">Enumerations</span></span>

<span data-ttu-id="a76b8-104">列挙型とも呼ばれる*列挙体\*\*は、値*のサブセットにラベルが割り当てられる整数型です。</span><span class="sxs-lookup"><span data-stu-id="a76b8-104">*Enumerations*, also known as *enums*, , are integral types where labels are assigned to a subset of the values.</span></span> <span data-ttu-id="a76b8-105">リテラルの代わりに使用すると、コードの読み取りおよび保守が容易になります。</span><span class="sxs-lookup"><span data-stu-id="a76b8-105">You can use them in place of literals to make code more readable and maintainable.</span></span>

## <a name="syntax"></a><span data-ttu-id="a76b8-106">構文</span><span class="sxs-lookup"><span data-stu-id="a76b8-106">Syntax</span></span>

```fsharp
type enum-name =
| value1 = integer-literal1
| value2 = integer-literal2
...
```

## <a name="remarks"></a><span data-ttu-id="a76b8-107">解説</span><span class="sxs-lookup"><span data-stu-id="a76b8-107">Remarks</span></span>

<span data-ttu-id="a76b8-108">列挙体は、値を指定できる点を除いて、単純な値を持つ判別共用体とよく似ています。</span><span class="sxs-lookup"><span data-stu-id="a76b8-108">An enumeration looks much like a discriminated union that has simple values, except that the values can be specified.</span></span> <span data-ttu-id="a76b8-109">値は通常、0または1から始まる整数、またはビット位置を表す整数です。</span><span class="sxs-lookup"><span data-stu-id="a76b8-109">The values are typically integers that start at 0 or 1, or integers that represent bit positions.</span></span> <span data-ttu-id="a76b8-110">列挙体がビット位置を表すことを目的としている場合は、 [Flags](xref:System.FlagsAttribute) 属性も使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a76b8-110">If an enumeration is intended to represent bit positions, you should also use the [Flags](xref:System.FlagsAttribute) attribute.</span></span>

<span data-ttu-id="a76b8-111">列挙型の基になる型は、使用されるリテラルから決定されます。したがって、たとえば、、などのサフィックスでリテラルを使用して、 `1u` `2u` 符号なし整数 () 型にすることができ `uint32` ます。</span><span class="sxs-lookup"><span data-stu-id="a76b8-111">The underlying type of the enumeration is determined from the literal that is used, so that, for example, you can use literals with a suffix, such as `1u`, `2u`, and so on, for an unsigned integer (`uint32`) type.</span></span>

<span data-ttu-id="a76b8-112">名前付きの値を参照する場合は、列挙型自体の名前を修飾子として使用する必要があり `enum-name.value1` ます。これは、だけではありません `value1` 。</span><span class="sxs-lookup"><span data-stu-id="a76b8-112">When you refer to the named values, you must use the name of the enumeration type itself as a qualifier, that is, `enum-name.value1`, not just `value1`.</span></span> <span data-ttu-id="a76b8-113">この動作は、判別共用体の動作とは異なります。</span><span class="sxs-lookup"><span data-stu-id="a76b8-113">This behavior differs from that of discriminated unions.</span></span> <span data-ttu-id="a76b8-114">これは、列挙体には常に [RequireQualifiedAccess](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-requirequalifiedaccessattribute.html) 属性が含まれているためです。</span><span class="sxs-lookup"><span data-stu-id="a76b8-114">This is because enumerations always have the [RequireQualifiedAccess](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-requirequalifiedaccessattribute.html) attribute.</span></span>

<span data-ttu-id="a76b8-115">次のコードは、列挙体の宣言と使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a76b8-115">The following code shows the declaration and use of an enumeration.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2101.fs)]

<span data-ttu-id="a76b8-116">次のコードに示すように、適切な演算子を使用して、列挙型を基になる型に簡単に変換できます。</span><span class="sxs-lookup"><span data-stu-id="a76b8-116">You can easily convert enumerations to the underlying type by using the appropriate operator, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2102.fs)]

<span data-ttu-id="a76b8-117">列挙型は、、、、、、、、、、およびのいずれかの基になる型を持つことができます `sbyte` `byte` `int16` `uint16` `int32` `uint32` `int64` `uint16` `uint64` `char` 。</span><span class="sxs-lookup"><span data-stu-id="a76b8-117">Enumerated types can have one of the following underlying types: `sbyte`, `byte`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint16`, `uint64`, and `char`.</span></span> <span data-ttu-id="a76b8-118">列挙型は、から継承される型として .NET Framework で表され `System.Enum` ます。これは、から継承され `System.ValueType` ます。</span><span class="sxs-lookup"><span data-stu-id="a76b8-118">Enumeration types are represented in the .NET Framework as types that are inherited from `System.Enum`, which in turn is inherited from `System.ValueType`.</span></span> <span data-ttu-id="a76b8-119">したがって、これらは、スタックに配置されている値型、または親オブジェクトのインラインにある値型であり、基になる型の値は列挙体の有効な値です。</span><span class="sxs-lookup"><span data-stu-id="a76b8-119">Thus, they are value types that are located on the stack or inline in the containing object, and any value of the underlying type is a valid value of the enumeration.</span></span> <span data-ttu-id="a76b8-120">これは、名前のない値をキャッチするパターンを指定する必要があるため、列挙値でパターンマッチングを行う場合に非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="a76b8-120">This is significant when pattern matching on enumeration values, because you have to provide a pattern that catches the unnamed values.</span></span>

<span data-ttu-id="a76b8-121">`enum`F # ライブラリの関数は、定義済みの名前付きの値の1つ以外の値であっても、列挙値を生成するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="a76b8-121">The `enum` function in the F# library can be used to generate an enumeration value, even a value other than one of the predefined, named values.</span></span> <span data-ttu-id="a76b8-122">関数は次のように使用し `enum` ます。</span><span class="sxs-lookup"><span data-stu-id="a76b8-122">You use the `enum` function as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2103.fs)]

<span data-ttu-id="a76b8-123">既定の `enum` 関数は、型で動作し `int32` ます。</span><span class="sxs-lookup"><span data-stu-id="a76b8-123">The default `enum` function works with type `int32`.</span></span> <span data-ttu-id="a76b8-124">そのため、基になるその他の型を持つ列挙型では使用できません。</span><span class="sxs-lookup"><span data-stu-id="a76b8-124">Therefore, it cannot be used with enumeration types that have other underlying types.</span></span> <span data-ttu-id="a76b8-125">代わりに、次のものを使用します。</span><span class="sxs-lookup"><span data-stu-id="a76b8-125">Instead, use the following.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2104.fs)]

<span data-ttu-id="a76b8-126">さらに、列挙型のケースは常にとして出力され `public` ます。</span><span class="sxs-lookup"><span data-stu-id="a76b8-126">Additionally, cases for enums are always emitted as `public`.</span></span> <span data-ttu-id="a76b8-127">これは、C# およびその他の .NET プラットフォームと一致するようにするためです。</span><span class="sxs-lookup"><span data-stu-id="a76b8-127">This is so that they align with C# and the rest of the .NET platform.</span></span>

## <a name="see-also"></a><span data-ttu-id="a76b8-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="a76b8-128">See also</span></span>

- [<span data-ttu-id="a76b8-129">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="a76b8-129">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="a76b8-130">キャストと変換</span><span class="sxs-lookup"><span data-stu-id="a76b8-130">Casting and Conversions</span></span>](casting-and-conversions.md)
