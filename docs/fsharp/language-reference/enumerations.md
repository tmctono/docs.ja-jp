---
title: 列挙
description: 使用する方法について説明しますF#読みやすく、保守しやすいコードにするためのリテラルの代わりに列挙体。
ms.date: 05/16/2016
ms.openlocfilehash: 7ff62b1c0a6ab0fda58a30de9387acbb547f6b81
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645547"
---
# <a name="enumerations"></a><span data-ttu-id="7a3bb-103">列挙</span><span class="sxs-lookup"><span data-stu-id="7a3bb-103">Enumerations</span></span>

<span data-ttu-id="7a3bb-104">*列挙体*とも呼ばれます*列挙型*、および整数型は、ラベルが割り当てられ、値のサブセットにします。</span><span class="sxs-lookup"><span data-stu-id="7a3bb-104">*Enumerations*, also known as *enums*, , are integral types where labels are assigned to a subset of the values.</span></span> <span data-ttu-id="7a3bb-105">リテラルの代わりに使用すると、コードの読み取りおよび保守が容易になります。</span><span class="sxs-lookup"><span data-stu-id="7a3bb-105">You can use them in place of literals to make code more readable and maintainable.</span></span>

## <a name="syntax"></a><span data-ttu-id="7a3bb-106">構文</span><span class="sxs-lookup"><span data-stu-id="7a3bb-106">Syntax</span></span>

```fsharp
type enum-name =
| value1 = integer-literal1
| value2 = integer-literal2
...
```

## <a name="remarks"></a><span data-ttu-id="7a3bb-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="7a3bb-107">Remarks</span></span>

<span data-ttu-id="7a3bb-108">値を指定する点を除いてを単純な値を持つ判別共用体と同様、列挙型を検索します。</span><span class="sxs-lookup"><span data-stu-id="7a3bb-108">An enumeration looks much like a discriminated union that has simple values, except that the values can be specified.</span></span> <span data-ttu-id="7a3bb-109">通常、値は、0 または 1 から始まる整数またはビット位置を表す整数です。</span><span class="sxs-lookup"><span data-stu-id="7a3bb-109">The values are typically integers that start at 0 or 1, or integers that represent bit positions.</span></span> <span data-ttu-id="7a3bb-110">またを使用する必要がある列挙体のビット位置を表す場合は、[フラグ](xref:System.FlagsAttribute)属性。</span><span class="sxs-lookup"><span data-stu-id="7a3bb-110">If an enumeration is intended to represent bit positions, you should also use the [Flags](xref:System.FlagsAttribute) attribute.</span></span>

<span data-ttu-id="7a3bb-111">、たとえば、を使用できるようにリテラル、サフィックスを持つように、使用されるリテラルから列挙体の基になる型が決定されます`1u`、 `2u`、で、符号なし整数 (`uint32`) 型。</span><span class="sxs-lookup"><span data-stu-id="7a3bb-111">The underlying type of the enumeration is determined from the literal that is used, so that, for example, you can use literals with a suffix, such as `1u`, `2u`, and so on, for an unsigned integer (`uint32`) type.</span></span>

<span data-ttu-id="7a3bb-112">名前付きの値を参照するときにする必要がありますとして使用する列挙型自体の名前、修飾子は、`enum-name.value1`だけでなく、`value1`します。</span><span class="sxs-lookup"><span data-stu-id="7a3bb-112">When you refer to the named values, you must use the name of the enumeration type itself as a qualifier, that is, `enum-name.value1`, not just `value1`.</span></span> <span data-ttu-id="7a3bb-113">この動作は、判別共用体の動作とは異なります。</span><span class="sxs-lookup"><span data-stu-id="7a3bb-113">This behavior differs from that of discriminated unions.</span></span> <span data-ttu-id="7a3bb-114">これは、列挙型が常にあるため、 [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15)属性。</span><span class="sxs-lookup"><span data-stu-id="7a3bb-114">This is because enumerations always have the [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) attribute.</span></span>

<span data-ttu-id="7a3bb-115">次のコードでは、宣言と列挙型の使用を示します。</span><span class="sxs-lookup"><span data-stu-id="7a3bb-115">The following code shows the declaration and use of an enumeration.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2101.fs)]

<span data-ttu-id="7a3bb-116">適切な演算子を使用して基になる型には、次のコードに示すように、列挙型を変換できます簡単にします。</span><span class="sxs-lookup"><span data-stu-id="7a3bb-116">You can easily convert enumerations to the underlying type by using the appropriate operator, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2102.fs)]

<span data-ttu-id="7a3bb-117">列挙型は、次の基になる型のいずれかを指定できます: `sbyte`、 `byte`、 `int16`、 `uint16`、 `int32`、 `uint32`、 `int64`、 `uint16`、 `uint64`、および`char`します。</span><span class="sxs-lookup"><span data-stu-id="7a3bb-117">Enumerated types can have one of the following underlying types: `sbyte`, `byte`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint16`, `uint64`, and `char`.</span></span> <span data-ttu-id="7a3bb-118">列挙型は、.NET Framework でから継承された型として表されます。 `System.Enum`、から継承順番`System.ValueType`します。</span><span class="sxs-lookup"><span data-stu-id="7a3bb-118">Enumeration types are represented in the .NET Framework as types that are inherited from `System.Enum`, which in turn is inherited from `System.ValueType`.</span></span> <span data-ttu-id="7a3bb-119">したがって、スタックまたは親オブジェクトでのインラインに配置されている値型では、基になる型の任意の値が列挙体の有効な値。</span><span class="sxs-lookup"><span data-stu-id="7a3bb-119">Thus, they are value types that are located on the stack or inline in the containing object, and any value of the underlying type is a valid value of the enumeration.</span></span> <span data-ttu-id="7a3bb-120">これは重要な場合、パターン マッチに列挙値の名前のない値をキャッチするパターンを指定する必要があるためです。</span><span class="sxs-lookup"><span data-stu-id="7a3bb-120">This is significant when pattern matching on enumeration values, because you have to provide a pattern that catches the unnamed values.</span></span>

<span data-ttu-id="7a3bb-121">`enum`関数の F# ライブラリで使用できます、定義済みの以外の値も、列挙値を生成する名前付きの値。</span><span class="sxs-lookup"><span data-stu-id="7a3bb-121">The `enum` function in the F# library can be used to generate an enumeration value, even a value other than one of the predefined, named values.</span></span> <span data-ttu-id="7a3bb-122">使用する、`enum`次のように機能します。</span><span class="sxs-lookup"><span data-stu-id="7a3bb-122">You use the `enum` function as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2103.fs)]

<span data-ttu-id="7a3bb-123">既定の`enum`関数は型で機能`int32`します。</span><span class="sxs-lookup"><span data-stu-id="7a3bb-123">The default `enum` function works with type `int32`.</span></span> <span data-ttu-id="7a3bb-124">そのため、基になるその他の型を持つ列挙型で使用できません。</span><span class="sxs-lookup"><span data-stu-id="7a3bb-124">Therefore, it cannot be used with enumeration types that have other underlying types.</span></span> <span data-ttu-id="7a3bb-125">代わりに、次を使用します。</span><span class="sxs-lookup"><span data-stu-id="7a3bb-125">Instead, use the following.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2104.fs)]

<span data-ttu-id="7a3bb-126">さらに、ケースの列挙型として常に出力されます。`public`します。</span><span class="sxs-lookup"><span data-stu-id="7a3bb-126">Additionally, cases for enums are always emitted as `public`.</span></span> <span data-ttu-id="7a3bb-127">これは、c# および .NET プラットフォームの残りの部分に配置します。</span><span class="sxs-lookup"><span data-stu-id="7a3bb-127">This is so that they align with C# and the rest of the .NET platform.</span></span>

## <a name="see-also"></a><span data-ttu-id="7a3bb-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="7a3bb-128">See also</span></span>

- [<span data-ttu-id="7a3bb-129">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="7a3bb-129">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="7a3bb-130">キャストと変換</span><span class="sxs-lookup"><span data-stu-id="7a3bb-130">Casting and Conversions</span></span>](casting-and-conversions.md)
