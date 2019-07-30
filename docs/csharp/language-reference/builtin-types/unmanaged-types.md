---
title: アンマネージド型 - C# リファレンス
ms.date: 07/23/2019
helpviewer_keywords:
- unmanaged type [C#]
ms.openlocfilehash: 2b675be5dbc61006725549f4b69284326650401d
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512072"
---
# <a name="unmanaged-types-c-reference"></a><span data-ttu-id="b4886-102">アンマネージド型 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="b4886-102">Unmanaged types (C# reference)</span></span>

<span data-ttu-id="b4886-103">**アンマネージド型**は、参照型または構築型 (少なくとも 1 つの型引数を含む型) ではない型であり、入れ子のどのレベルにも参照型または構築型のフィールドが含まれていません。</span><span class="sxs-lookup"><span data-stu-id="b4886-103">An **unmanaged type** is any type that isn't a reference type or constructed type (a type that includes at least one type argument), and doesn't contain reference type or constructed type fields at any level of nesting.</span></span> <span data-ttu-id="b4886-104">つまり、アンマネージド型は次のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="b4886-104">In other words, an unmanaged type is one of the following:</span></span>

- <span data-ttu-id="b4886-105">`sbyte`、`byte`、`short`、`ushort`、`int`、`uint`、`long`、`ulong`、`char`、`float`、`double`、`decimal`、または `bool`</span><span class="sxs-lookup"><span data-stu-id="b4886-105">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal`, or `bool`</span></span>
- <span data-ttu-id="b4886-106">すべての[列挙](../keywords/enum.md)型</span><span class="sxs-lookup"><span data-stu-id="b4886-106">Any [enum](../keywords/enum.md) type</span></span>
- <span data-ttu-id="b4886-107">すべての[ポインター](../../programming-guide/unsafe-code-pointers/pointer-types.md) 型</span><span class="sxs-lookup"><span data-stu-id="b4886-107">Any [pointer](../../programming-guide/unsafe-code-pointers/pointer-types.md) type</span></span>
- <span data-ttu-id="b4886-108">構築型以外の、アンマネージ型のフィールドのみを含む、ユーザー定義のすべての[構造体](../keywords/struct.md)型</span><span class="sxs-lookup"><span data-stu-id="b4886-108">Any user-defined [struct](../keywords/struct.md) type that is not a constructed type and contains fields of unmanaged types only</span></span>

<span data-ttu-id="b4886-109">C# 7.3 以降、[`unmanaged` 制約](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint)を使用して、型パラメーターが非ポインターのアンマネージド型であることを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b4886-109">Beginning with C# 7.3, you can use the [`unmanaged` constraint](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) to specify that a type parameter is a non-pointer unmanaged type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="b4886-110">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="b4886-110">C# language specification</span></span>

<span data-ttu-id="b4886-111">詳しくは、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の「[ポインター型](~/_csharplang/spec/unsafe-code.md#pointer-types)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b4886-111">For more information, see the [Pointer types](~/_csharplang/spec/unsafe-code.md#pointer-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b4886-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="b4886-112">See also</span></span>

- [<span data-ttu-id="b4886-113">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="b4886-113">C# reference</span></span>](../index.md)
- [<span data-ttu-id="b4886-114">ポインター型</span><span class="sxs-lookup"><span data-stu-id="b4886-114">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="b4886-115">メモリおよびスパンに関連する型</span><span class="sxs-lookup"><span data-stu-id="b4886-115">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
- [<span data-ttu-id="b4886-116">sizeof 演算子</span><span class="sxs-lookup"><span data-stu-id="b4886-116">sizeof operator</span></span>](../operators/sizeof.md)
- [<span data-ttu-id="b4886-117">stackalloc 演算子</span><span class="sxs-lookup"><span data-stu-id="b4886-117">stackalloc operator</span></span>](../operators/stackalloc.md)
