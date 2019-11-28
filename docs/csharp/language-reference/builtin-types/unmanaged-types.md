---
title: アンマネージド型 - C# リファレンス
ms.date: 09/06/2019
helpviewer_keywords:
- unmanaged type [C#]
ms.openlocfilehash: 81eef59ceb20bcae6c749dd59578ce35da253826
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2019
ms.locfileid: "74204470"
---
# <a name="unmanaged-types-c-reference"></a><span data-ttu-id="ca6af-102">アンマネージド型 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="ca6af-102">Unmanaged types (C# reference)</span></span>

<span data-ttu-id="ca6af-103">型は、次のいずれかの型である場合、**アンマネージド型**です。</span><span class="sxs-lookup"><span data-stu-id="ca6af-103">A type is an **unmanaged type** if it's any of the following types:</span></span>

- <span data-ttu-id="ca6af-104">`sbyte`、`byte`、`short`、`ushort`、`int`、`uint`、`long`、`ulong`、`char`、`float`、`double`、`decimal`、または `bool`</span><span class="sxs-lookup"><span data-stu-id="ca6af-104">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal`, or `bool`</span></span>
- <span data-ttu-id="ca6af-105">すべての[列挙](../keywords/enum.md)型</span><span class="sxs-lookup"><span data-stu-id="ca6af-105">Any [enum](../keywords/enum.md) type</span></span>
- <span data-ttu-id="ca6af-106">すべての[ポインター](../../programming-guide/unsafe-code-pointers/pointer-types.md) 型</span><span class="sxs-lookup"><span data-stu-id="ca6af-106">Any [pointer](../../programming-guide/unsafe-code-pointers/pointer-types.md) type</span></span>
- <span data-ttu-id="ca6af-107">アンマネージド型のフィールドのみが含まれるすべてのユーザー定義の[構造体](../keywords/struct.md)型で、かつ C# 7.3 以前の場合は、構築された型 (1 つ以上の型引数が含まれる型) でない</span><span class="sxs-lookup"><span data-stu-id="ca6af-107">Any user-defined [struct](../keywords/struct.md) type that contains fields of unmanaged types only and, in C# 7.3 and earlier, is not a constructed type (a type that includes at least one type argument)</span></span>

<span data-ttu-id="ca6af-108">C# 7.3 以降、[`unmanaged` 制約](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint)を使用して、型パラメーターが非ポインターで、null 非許容で、アンマネージド型であることを指定できます。</span><span class="sxs-lookup"><span data-stu-id="ca6af-108">Beginning with C# 7.3, you can use the [`unmanaged` constraint](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) to specify that a type parameter is a non-pointer, non-nullable unmanaged type.</span></span>

<span data-ttu-id="ca6af-109">C# 8.0 以降では、次の例に示すように、アンマネージド型のフィールドのみが含まれる "*構築された*" 構造体型もアンマネージド型になります。</span><span class="sxs-lookup"><span data-stu-id="ca6af-109">Beginning with C# 8.0, a *constructed* struct type that contains fields of unmanaged types only is also unmanaged, as the following example shows:</span></span>

[!code-csharp[unmanaged constructed types](~/samples/csharp/language-reference/builtin-types/UnmanagedTypes.cs#ProgramExample)]

<span data-ttu-id="ca6af-110">ジェネリック構造体は、構築されたアンマネージド型およびアンマネージドでない型の両方のソースになる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ca6af-110">A generic struct may be the source of both unmanaged and not unmanaged constructed types.</span></span> <span data-ttu-id="ca6af-111">前の例では、ジェネリック構造体 `Coords<T>` を定義し、構築されたアンマネージド型の例を示します。</span><span class="sxs-lookup"><span data-stu-id="ca6af-111">The preceding example defines a generic struct `Coords<T>` and presents the examples of unmanaged constructed types.</span></span> <span data-ttu-id="ca6af-112">アンマネージド型でない例は `Coords<object>` です。</span><span class="sxs-lookup"><span data-stu-id="ca6af-112">The example of not an unmanaged type is `Coords<object>`.</span></span> <span data-ttu-id="ca6af-113">アンマネージドでない `object` 型のフィールドがあるため、これはアンマネージドではありません。</span><span class="sxs-lookup"><span data-stu-id="ca6af-113">It's not unmanaged because it has the fields of the `object` type, which is not unmanaged.</span></span> <span data-ttu-id="ca6af-114">構築された "*すべての*" 型をアンマネージド型にする場合は、ジェネリック構造体の定義で `unmanaged` 制約を使用します。</span><span class="sxs-lookup"><span data-stu-id="ca6af-114">If you want *all* constructed types to be unmanaged types, use the `unmanaged` constraint in the definition of a generic struct:</span></span>

[!code-csharp[unmanaged constraint in type definition](~/samples/csharp/language-reference/builtin-types/UnmanagedTypes.cs#AlwaysUnmanaged)]

## <a name="c-language-specification"></a><span data-ttu-id="ca6af-115">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="ca6af-115">C# language specification</span></span>

<span data-ttu-id="ca6af-116">詳しくは、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の「[ポインター型](~/_csharplang/spec/unsafe-code.md#pointer-types)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ca6af-116">For more information, see the [Pointer types](~/_csharplang/spec/unsafe-code.md#pointer-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ca6af-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="ca6af-117">See also</span></span>

- [<span data-ttu-id="ca6af-118">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="ca6af-118">C# reference</span></span>](../index.md)
- [<span data-ttu-id="ca6af-119">ポインター型</span><span class="sxs-lookup"><span data-stu-id="ca6af-119">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="ca6af-120">メモリおよびスパンに関連する型</span><span class="sxs-lookup"><span data-stu-id="ca6af-120">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
- [<span data-ttu-id="ca6af-121">sizeof 演算子</span><span class="sxs-lookup"><span data-stu-id="ca6af-121">sizeof operator</span></span>](../operators/sizeof.md)
- [<span data-ttu-id="ca6af-122">stackalloc 演算子</span><span class="sxs-lookup"><span data-stu-id="ca6af-122">stackalloc operator</span></span>](../operators/stackalloc.md)
