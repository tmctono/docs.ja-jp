---
title: アンマネージド型 - C# リファレンス
ms.date: 09/06/2019
helpviewer_keywords:
- unmanaged type [C#]
ms.openlocfilehash: 8a4599514115aa21f17c32848ce203fea704072e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "78846466"
---
# <a name="unmanaged-types-c-reference"></a><span data-ttu-id="5084e-102">アンマネージド型 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="5084e-102">Unmanaged types (C# reference)</span></span>

<span data-ttu-id="5084e-103">型は、次のいずれかの型である場合、**アンマネージド型**です。</span><span class="sxs-lookup"><span data-stu-id="5084e-103">A type is an **unmanaged type** if it's any of the following types:</span></span>

- <span data-ttu-id="5084e-104">`sbyte`、`byte`、`short`、`ushort`、`int`、`uint`、`long`、`ulong`、`char`、`float`、`double`、`decimal`、または `bool`</span><span class="sxs-lookup"><span data-stu-id="5084e-104">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal`, or `bool`</span></span>
- <span data-ttu-id="5084e-105">すべての[列挙](enum.md)型</span><span class="sxs-lookup"><span data-stu-id="5084e-105">Any [enum](enum.md) type</span></span>
- <span data-ttu-id="5084e-106">すべての[ポインター](../../programming-guide/unsafe-code-pointers/pointer-types.md) 型</span><span class="sxs-lookup"><span data-stu-id="5084e-106">Any [pointer](../../programming-guide/unsafe-code-pointers/pointer-types.md) type</span></span>
- <span data-ttu-id="5084e-107">アンマネージド型のフィールドのみが含まれるすべてのユーザー定義の[構造体](struct.md)型で、かつ C# 7.3 以前の場合は、構築された型 (1 つ以上の型引数が含まれる型) でない</span><span class="sxs-lookup"><span data-stu-id="5084e-107">Any user-defined [struct](struct.md) type that contains fields of unmanaged types only and, in C# 7.3 and earlier, is not a constructed type (a type that includes at least one type argument)</span></span>

<span data-ttu-id="5084e-108">C# 7.3 以降、[`unmanaged` 制約](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint)を使用して、型パラメーターが非ポインターで、null 非許容で、アンマネージド型であることを指定できます。</span><span class="sxs-lookup"><span data-stu-id="5084e-108">Beginning with C# 7.3, you can use the [`unmanaged` constraint](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) to specify that a type parameter is a non-pointer, non-nullable unmanaged type.</span></span>

<span data-ttu-id="5084e-109">C# 8.0 以降では、次の例に示すように、アンマネージド型のフィールドのみが含まれる "*構築された*" 構造体型もアンマネージド型になります。</span><span class="sxs-lookup"><span data-stu-id="5084e-109">Beginning with C# 8.0, a *constructed* struct type that contains fields of unmanaged types only is also unmanaged, as the following example shows:</span></span>

[!code-csharp[unmanaged constructed types](snippets/UnmanagedTypes.cs#ProgramExample)]

<span data-ttu-id="5084e-110">ジェネリック構造体は、構築されたアンマネージド型およびアンマネージドでない型の両方のソースになる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5084e-110">A generic struct may be the source of both unmanaged and not unmanaged constructed types.</span></span> <span data-ttu-id="5084e-111">前の例では、ジェネリック構造体 `Coords<T>` を定義し、構築されたアンマネージド型の例を示します。</span><span class="sxs-lookup"><span data-stu-id="5084e-111">The preceding example defines a generic struct `Coords<T>` and presents the examples of unmanaged constructed types.</span></span> <span data-ttu-id="5084e-112">アンマネージド型でない例は `Coords<object>` です。</span><span class="sxs-lookup"><span data-stu-id="5084e-112">The example of not an unmanaged type is `Coords<object>`.</span></span> <span data-ttu-id="5084e-113">アンマネージドでない `object` 型のフィールドがあるため、これはアンマネージドではありません。</span><span class="sxs-lookup"><span data-stu-id="5084e-113">It's not unmanaged because it has the fields of the `object` type, which is not unmanaged.</span></span> <span data-ttu-id="5084e-114">構築された "*すべての*" 型をアンマネージド型にする場合は、ジェネリック構造体の定義で `unmanaged` 制約を使用します。</span><span class="sxs-lookup"><span data-stu-id="5084e-114">If you want *all* constructed types to be unmanaged types, use the `unmanaged` constraint in the definition of a generic struct:</span></span>

[!code-csharp[unmanaged constraint in type definition](snippets/UnmanagedTypes.cs#AlwaysUnmanaged)]

## <a name="c-language-specification"></a><span data-ttu-id="5084e-115">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="5084e-115">C# language specification</span></span>

<span data-ttu-id="5084e-116">詳しくは、「[C# 言語仕様](~/_csharplang/spec/unsafe-code.md#pointer-types)」の「[ポインター型](~/_csharplang/spec/introduction.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5084e-116">For more information, see the [Pointer types](~/_csharplang/spec/unsafe-code.md#pointer-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5084e-117">参照</span><span class="sxs-lookup"><span data-stu-id="5084e-117">See also</span></span>

- [<span data-ttu-id="5084e-118">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="5084e-118">C# reference</span></span>](../index.md)
- [<span data-ttu-id="5084e-119">ポインター型</span><span class="sxs-lookup"><span data-stu-id="5084e-119">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="5084e-120">メモリおよびスパンに関連する型</span><span class="sxs-lookup"><span data-stu-id="5084e-120">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
- [<span data-ttu-id="5084e-121">sizeof 演算子</span><span class="sxs-lookup"><span data-stu-id="5084e-121">sizeof operator</span></span>](../operators/sizeof.md)
- [<span data-ttu-id="5084e-122">stackalloc 演算子</span><span class="sxs-lookup"><span data-stu-id="5084e-122">stackalloc operator</span></span>](../operators/stackalloc.md)
