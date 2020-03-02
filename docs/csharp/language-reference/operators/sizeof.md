---
title: sizeof 演算子 - C# リファレンス
ms.date: 07/25/2019
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
helpviewer_keywords:
- sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
ms.openlocfilehash: 8e4518718d0975f8b4a65870f15d8c52d692c2f5
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2020
ms.locfileid: "77625736"
---
# <a name="sizeof-operator-c-reference"></a><span data-ttu-id="04d01-102">sizeof 演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="04d01-102">sizeof operator (C# reference)</span></span>

<span data-ttu-id="04d01-103">`sizeof` は、指定された型の変数が占有しているバイト数を返します。</span><span class="sxs-lookup"><span data-stu-id="04d01-103">The `sizeof` operator returns the number of bytes occupied by a variable of a given type.</span></span> <span data-ttu-id="04d01-104">`sizeof` 演算子への引数は、[アンマネージド型](../builtin-types/unmanaged-types.md)の名前、またはアンマネージド型に[制限される](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint)型パラメーターである必要があります。</span><span class="sxs-lookup"><span data-stu-id="04d01-104">The argument to the `sizeof` operator must be the name of an [unmanaged type](../builtin-types/unmanaged-types.md) or a type parameter that is [constrained](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) to be an unmanaged type.</span></span>

<span data-ttu-id="04d01-105">`sizeof` 演算子には [unsafe](../keywords/unsafe.md) コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="04d01-105">The `sizeof` operator requires an [unsafe](../keywords/unsafe.md) context.</span></span> <span data-ttu-id="04d01-106">ただし、次の表に示す式は、コンパイル時に対応する定数値に評価され、unsafe コンテキストを必要としません。</span><span class="sxs-lookup"><span data-stu-id="04d01-106">However, the expressions presented in the following table are evaluated in compile time to the corresponding constant values and don't require an unsafe context:</span></span>

|<span data-ttu-id="04d01-107">正規表現</span><span class="sxs-lookup"><span data-stu-id="04d01-107">Expression</span></span>|<span data-ttu-id="04d01-108">定数値</span><span class="sxs-lookup"><span data-stu-id="04d01-108">Constant value</span></span>|
|---------|---------------|
|`sizeof(sbyte)`|<span data-ttu-id="04d01-109">1</span><span class="sxs-lookup"><span data-stu-id="04d01-109">1</span></span>|
|`sizeof(byte)`|<span data-ttu-id="04d01-110">1</span><span class="sxs-lookup"><span data-stu-id="04d01-110">1</span></span>|
|`sizeof(short)`|<span data-ttu-id="04d01-111">2</span><span class="sxs-lookup"><span data-stu-id="04d01-111">2</span></span>|
|`sizeof(ushort)`|<span data-ttu-id="04d01-112">2</span><span class="sxs-lookup"><span data-stu-id="04d01-112">2</span></span>|
|`sizeof(int)`|<span data-ttu-id="04d01-113">4</span><span class="sxs-lookup"><span data-stu-id="04d01-113">4</span></span>|
|`sizeof(uint)`|<span data-ttu-id="04d01-114">4</span><span class="sxs-lookup"><span data-stu-id="04d01-114">4</span></span>|
|`sizeof(long)`|<span data-ttu-id="04d01-115">8</span><span class="sxs-lookup"><span data-stu-id="04d01-115">8</span></span>|
|`sizeof(ulong)`|<span data-ttu-id="04d01-116">8</span><span class="sxs-lookup"><span data-stu-id="04d01-116">8</span></span>|
|`sizeof(char)`|<span data-ttu-id="04d01-117">2</span><span class="sxs-lookup"><span data-stu-id="04d01-117">2</span></span>|
|`sizeof(float)`|<span data-ttu-id="04d01-118">4</span><span class="sxs-lookup"><span data-stu-id="04d01-118">4</span></span>|
|`sizeof(double)`|<span data-ttu-id="04d01-119">8</span><span class="sxs-lookup"><span data-stu-id="04d01-119">8</span></span>|
|`sizeof(decimal)`|<span data-ttu-id="04d01-120">16</span><span class="sxs-lookup"><span data-stu-id="04d01-120">16</span></span>|
|`sizeof(bool)`|<span data-ttu-id="04d01-121">1</span><span class="sxs-lookup"><span data-stu-id="04d01-121">1</span></span>|

<span data-ttu-id="04d01-122">`sizeof` 演算子のオペランドが[列挙](../builtin-types/enum.md)型の名前である場合も、unsafe コンテキストを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="04d01-122">You also don't need to use an unsafe context when the operand of the `sizeof` operator is the name of an [enum](../builtin-types/enum.md) type.</span></span>

<span data-ttu-id="04d01-123">`sizeof` 演算子の使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="04d01-123">The following example demonstrates the usage of the `sizeof` operator:</span></span>

[!code-csharp[sizeof examples](~/samples/csharp/language-reference/operators/SizeOfOperator.cs)]

<span data-ttu-id="04d01-124">`sizeof` 演算子は、マネージド メモリ内の共通言語ランタイムによって割り当てられるバイト数を返します。</span><span class="sxs-lookup"><span data-stu-id="04d01-124">The `sizeof` operator returns a number of bytes that would be allocated by the common language runtime in managed memory.</span></span> <span data-ttu-id="04d01-125">[構造体](../builtin-types/struct.md)型の場合、前の例のように、その値に埋め込みが含まれます。</span><span class="sxs-lookup"><span data-stu-id="04d01-125">For [struct](../builtin-types/struct.md) types, that value includes any padding, as the preceding example demonstrates.</span></span> <span data-ttu-id="04d01-126">`sizeof` 演算子の結果は、*アンマネージド* メモリの型のサイズを返す <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> メソッドの結果とは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="04d01-126">The result of the `sizeof` operator might differ from the result of the <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> method, which returns the size of a type in *unmanaged* memory.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="04d01-127">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="04d01-127">C# language specification</span></span>

<span data-ttu-id="04d01-128">詳細については、[C# 言語仕様](~/_csharplang/spec/introduction.md)の [sizeof 演算子](~/_csharplang/spec/unsafe-code.md#the-sizeof-operator)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="04d01-128">For more information, see [The sizeof operator](~/_csharplang/spec/unsafe-code.md#the-sizeof-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="04d01-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="04d01-129">See also</span></span>

- [<span data-ttu-id="04d01-130">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="04d01-130">C# reference</span></span>](../index.md)
- [<span data-ttu-id="04d01-131">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="04d01-131">C# operators</span></span>](index.md)
- [<span data-ttu-id="04d01-132">ポインターに関連する演算子</span><span class="sxs-lookup"><span data-stu-id="04d01-132">Pointer related operators</span></span>](pointer-related-operators.md)
- [<span data-ttu-id="04d01-133">ポインター型</span><span class="sxs-lookup"><span data-stu-id="04d01-133">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="04d01-134">メモリおよびスパンに関連する型</span><span class="sxs-lookup"><span data-stu-id="04d01-134">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
- [<span data-ttu-id="04d01-135">.NET のジェネリック</span><span class="sxs-lookup"><span data-stu-id="04d01-135">Generics in .NET</span></span>](../../../standard/generics/index.md)
