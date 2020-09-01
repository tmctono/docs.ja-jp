---
description: sizeof 演算子 - C# リファレンス
title: sizeof 演算子 - C# リファレンス
ms.date: 07/25/2019
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
helpviewer_keywords:
- sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
ms.openlocfilehash: f1358cbfb6cbc2942cef12e650f7bd362ba37a78
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89136877"
---
# <a name="sizeof-operator-c-reference"></a><span data-ttu-id="1980b-103">sizeof 演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="1980b-103">sizeof operator (C# reference)</span></span>

<span data-ttu-id="1980b-104">`sizeof` は、指定された型の変数が占有しているバイト数を返します。</span><span class="sxs-lookup"><span data-stu-id="1980b-104">The `sizeof` operator returns the number of bytes occupied by a variable of a given type.</span></span> <span data-ttu-id="1980b-105">`sizeof` 演算子への引数は、[アンマネージド型](../builtin-types/unmanaged-types.md)の名前、またはアンマネージド型に[制限される](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint)型パラメーターである必要があります。</span><span class="sxs-lookup"><span data-stu-id="1980b-105">The argument to the `sizeof` operator must be the name of an [unmanaged type](../builtin-types/unmanaged-types.md) or a type parameter that is [constrained](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) to be an unmanaged type.</span></span>

<span data-ttu-id="1980b-106">`sizeof` 演算子には [unsafe](../keywords/unsafe.md) コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="1980b-106">The `sizeof` operator requires an [unsafe](../keywords/unsafe.md) context.</span></span> <span data-ttu-id="1980b-107">ただし、次の表に示す式は、コンパイル時に対応する定数値に評価され、unsafe コンテキストを必要としません。</span><span class="sxs-lookup"><span data-stu-id="1980b-107">However, the expressions presented in the following table are evaluated in compile time to the corresponding constant values and don't require an unsafe context:</span></span>

|<span data-ttu-id="1980b-108">正規表現</span><span class="sxs-lookup"><span data-stu-id="1980b-108">Expression</span></span>|<span data-ttu-id="1980b-109">定数値</span><span class="sxs-lookup"><span data-stu-id="1980b-109">Constant value</span></span>|
|---------|---------------|
|`sizeof(sbyte)`|<span data-ttu-id="1980b-110">1</span><span class="sxs-lookup"><span data-stu-id="1980b-110">1</span></span>|
|`sizeof(byte)`|<span data-ttu-id="1980b-111">1</span><span class="sxs-lookup"><span data-stu-id="1980b-111">1</span></span>|
|`sizeof(short)`|<span data-ttu-id="1980b-112">2</span><span class="sxs-lookup"><span data-stu-id="1980b-112">2</span></span>|
|`sizeof(ushort)`|<span data-ttu-id="1980b-113">2</span><span class="sxs-lookup"><span data-stu-id="1980b-113">2</span></span>|
|`sizeof(int)`|<span data-ttu-id="1980b-114">4</span><span class="sxs-lookup"><span data-stu-id="1980b-114">4</span></span>|
|`sizeof(uint)`|<span data-ttu-id="1980b-115">4</span><span class="sxs-lookup"><span data-stu-id="1980b-115">4</span></span>|
|`sizeof(long)`|<span data-ttu-id="1980b-116">8</span><span class="sxs-lookup"><span data-stu-id="1980b-116">8</span></span>|
|`sizeof(ulong)`|<span data-ttu-id="1980b-117">8</span><span class="sxs-lookup"><span data-stu-id="1980b-117">8</span></span>|
|`sizeof(char)`|<span data-ttu-id="1980b-118">2</span><span class="sxs-lookup"><span data-stu-id="1980b-118">2</span></span>|
|`sizeof(float)`|<span data-ttu-id="1980b-119">4</span><span class="sxs-lookup"><span data-stu-id="1980b-119">4</span></span>|
|`sizeof(double)`|<span data-ttu-id="1980b-120">8</span><span class="sxs-lookup"><span data-stu-id="1980b-120">8</span></span>|
|`sizeof(decimal)`|<span data-ttu-id="1980b-121">16</span><span class="sxs-lookup"><span data-stu-id="1980b-121">16</span></span>|
|`sizeof(bool)`|<span data-ttu-id="1980b-122">1</span><span class="sxs-lookup"><span data-stu-id="1980b-122">1</span></span>|

<span data-ttu-id="1980b-123">`sizeof` 演算子のオペランドが[列挙](../builtin-types/enum.md)型の名前である場合も、unsafe コンテキストを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1980b-123">You also don't need to use an unsafe context when the operand of the `sizeof` operator is the name of an [enum](../builtin-types/enum.md) type.</span></span>

<span data-ttu-id="1980b-124">`sizeof` 演算子の使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="1980b-124">The following example demonstrates the usage of the `sizeof` operator:</span></span>

[!code-csharp[sizeof examples](snippets/shared/SizeOfOperator.cs)]

<span data-ttu-id="1980b-125">`sizeof` 演算子は、マネージド メモリ内の共通言語ランタイムによって割り当てられるバイト数を返します。</span><span class="sxs-lookup"><span data-stu-id="1980b-125">The `sizeof` operator returns a number of bytes that would be allocated by the common language runtime in managed memory.</span></span> <span data-ttu-id="1980b-126">[構造体](../builtin-types/struct.md)型の場合、前の例のように、その値に埋め込みが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1980b-126">For [struct](../builtin-types/struct.md) types, that value includes any padding, as the preceding example demonstrates.</span></span> <span data-ttu-id="1980b-127">`sizeof` 演算子の結果は、*アンマネージド* メモリの型のサイズを返す <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> メソッドの結果とは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1980b-127">The result of the `sizeof` operator might differ from the result of the <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> method, which returns the size of a type in *unmanaged* memory.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="1980b-128">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="1980b-128">C# language specification</span></span>

<span data-ttu-id="1980b-129">詳細については、[C# 言語仕様](~/_csharplang/spec/introduction.md)の [sizeof 演算子](~/_csharplang/spec/unsafe-code.md#the-sizeof-operator)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1980b-129">For more information, see [The sizeof operator](~/_csharplang/spec/unsafe-code.md#the-sizeof-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1980b-130">参照</span><span class="sxs-lookup"><span data-stu-id="1980b-130">See also</span></span>

- [<span data-ttu-id="1980b-131">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="1980b-131">C# reference</span></span>](../index.md)
- [<span data-ttu-id="1980b-132">C# の演算子と式</span><span class="sxs-lookup"><span data-stu-id="1980b-132">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="1980b-133">ポインターに関連する演算子</span><span class="sxs-lookup"><span data-stu-id="1980b-133">Pointer related operators</span></span>](pointer-related-operators.md)
- [<span data-ttu-id="1980b-134">ポインター型</span><span class="sxs-lookup"><span data-stu-id="1980b-134">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="1980b-135">メモリおよびスパンに関連する型</span><span class="sxs-lookup"><span data-stu-id="1980b-135">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
- [<span data-ttu-id="1980b-136">.NET のジェネリック</span><span class="sxs-lookup"><span data-stu-id="1980b-136">Generics in .NET</span></span>](../../../standard/generics/index.md)
