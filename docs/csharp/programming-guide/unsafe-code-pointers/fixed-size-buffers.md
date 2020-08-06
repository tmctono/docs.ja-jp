---
title: 固定サイズ バッファー - C# プログラミング ガイド
description: 固定サイズ バッファーについて説明します。 固定サイズ バッファーは、他の言語のデータ ソースと相互運用するメソッドを作成するために使用します。
ms.date: 04/23/2020
helpviewer_keywords:
- fixed size buffers [C#]
- unsafe buffers [C#]
- unsafe code [C#], fixed size buffers
ms.openlocfilehash: 1d4f5068121cdc98976954f2d99f4ac020c3b2a8
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381243"
---
# <a name="fixed-size-buffers-c-programming-guide"></a><span data-ttu-id="5824e-104">固定サイズ バッファー (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="5824e-104">Fixed Size Buffers (C# Programming Guide)</span></span>

<span data-ttu-id="5824e-105">C# では、[fixed](../../language-reference/keywords/fixed-statement.md) ステートメントを使って、データの構造体に固定サイズの配列を持ったバッファーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="5824e-105">In C#, you can use the [fixed](../../language-reference/keywords/fixed-statement.md) statement to create a buffer with a fixed size array in a data structure.</span></span> <span data-ttu-id="5824e-106">固定サイズのバッファーは、他の言語またはプラットフォームのデータ ソースと相互運用するメソッドを作成するときに便利です。</span><span class="sxs-lookup"><span data-stu-id="5824e-106">Fixed size buffers are useful when you write methods that interop with data sources from other languages or platforms.</span></span> <span data-ttu-id="5824e-107">この固定配列には、標準的な構造体メンバーで許容されている属性または修飾子であれば、何でも適用することができます。</span><span class="sxs-lookup"><span data-stu-id="5824e-107">The fixed array can take any attributes or modifiers that are allowed for regular struct members.</span></span> <span data-ttu-id="5824e-108">ただし配列の型は `bool`、`byte`、`char`、`short`、`int`、`long`、`sbyte`、`ushort`、`uint`、`ulong`、`float`、`double` のいずれかに該当する必要があり、それが唯一の制限となります。</span><span class="sxs-lookup"><span data-stu-id="5824e-108">The only restriction is that the array type must be `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float`, or `double`.</span></span>

```csharp
private fixed char name[30];
```

## <a name="remarks"></a><span data-ttu-id="5824e-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="5824e-109">Remarks</span></span>

<span data-ttu-id="5824e-110">セーフ コードでは、配列を含む C# 構造体に配列要素が含まれません。</span><span class="sxs-lookup"><span data-stu-id="5824e-110">In safe code, a C# struct that contains an array does not contain the array elements.</span></span> <span data-ttu-id="5824e-111">この場合、構造体には、配列の要素ではなく、その参照が格納されます。</span><span class="sxs-lookup"><span data-stu-id="5824e-111">Instead, the struct contains a reference to the elements.</span></span> <span data-ttu-id="5824e-112">[unsafe](../../language-reference/keywords/unsafe.md) のコード ブロックで使われている [struct](../../language-reference/builtin-types/struct.md) に、固定サイズの配列を埋め込むことができます。</span><span class="sxs-lookup"><span data-stu-id="5824e-112">You can embed an array of fixed size in a [struct](../../language-reference/builtin-types/struct.md) when it is used in an [unsafe](../../language-reference/keywords/unsafe.md) code block.</span></span>

<span data-ttu-id="5824e-113">`struct` が参照であるため、次の `pathName` のサイズは配列内の要素の数に依存しません。</span><span class="sxs-lookup"><span data-stu-id="5824e-113">Size of the following `struct` doesn't depend on the number of elements in the array, since `pathName` is a reference:</span></span>

[!code-csharp[Struct with embedded array](snippets/FixedKeywordExamples.cs#6)]

<span data-ttu-id="5824e-114">アンセーフ コードでは、`struct` に埋め込み配列を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="5824e-114">A `struct` can contain an embedded array in unsafe code.</span></span> <span data-ttu-id="5824e-115">以下の例の `fixedBuffer` 配列は固定サイズです。</span><span class="sxs-lookup"><span data-stu-id="5824e-115">In the following example, the `fixedBuffer` array has a fixed size.</span></span> <span data-ttu-id="5824e-116">`fixed` ステートメントを使用して、先頭要素へのポインターを確立します。</span><span class="sxs-lookup"><span data-stu-id="5824e-116">You use a `fixed` statement to establish a pointer to the first element.</span></span> <span data-ttu-id="5824e-117">このポインターを使用して配列の要素にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="5824e-117">You access the elements of the array through this pointer.</span></span> <span data-ttu-id="5824e-118">`fixed` ステートメントによって、`fixedBuffer` インスタンス フィールドがメモリ内の特定の位置に固定されます。</span><span class="sxs-lookup"><span data-stu-id="5824e-118">The `fixed` statement pins the `fixedBuffer` instance field to a specific location in memory.</span></span>

[!code-csharp[Struct with embedded inline array](snippets/FixedKeywordExamples.cs#7)]

<span data-ttu-id="5824e-119">要素数 128 の `char` 配列のサイズは 256 バイトです。</span><span class="sxs-lookup"><span data-stu-id="5824e-119">The size of the 128 element `char` array is 256 bytes.</span></span> <span data-ttu-id="5824e-120">固定サイズの [char](../../language-reference/builtin-types/char.md) 型バッファーは、エンコーディングに関係なく常に、1 文字あたり 2 バイトを消費します。</span><span class="sxs-lookup"><span data-stu-id="5824e-120">Fixed size [char](../../language-reference/builtin-types/char.md) buffers always take two bytes per character, regardless of the encoding.</span></span> <span data-ttu-id="5824e-121">これは、char 型のバッファーが、`CharSet = CharSet.Auto` または `CharSet = CharSet.Ansi` で API メソッドや構造体にマーシャリングされたときにも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="5824e-121">This is true even when char buffers are marshaled to API methods or structs with `CharSet = CharSet.Auto` or `CharSet = CharSet.Ansi`.</span></span> <span data-ttu-id="5824e-122">詳細については、「<xref:System.Runtime.InteropServices.CharSet>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5824e-122">For more information, see <xref:System.Runtime.InteropServices.CharSet>.</span></span>

<span data-ttu-id="5824e-123">上記の例は、固定せずに `fixed` フィールドにアクセスする方法を示しています。この方法は C# 7.3 以降から使用できます。</span><span class="sxs-lookup"><span data-stu-id="5824e-123">The  preceding example demonstrates accessing `fixed` fields without pinning, which is available starting with C# 7.3.</span></span>

<span data-ttu-id="5824e-124">一般的な固定サイズの配列としては、他にも [bool](../../language-reference/builtin-types/bool.md) 配列があります。</span><span class="sxs-lookup"><span data-stu-id="5824e-124">Another common fixed-size array is the [bool](../../language-reference/builtin-types/bool.md) array.</span></span> <span data-ttu-id="5824e-125">`bool` 配列内の要素のサイズは常に 1 バイトです。</span><span class="sxs-lookup"><span data-stu-id="5824e-125">The elements in a `bool` array are always one byte in size.</span></span> <span data-ttu-id="5824e-126">`bool` 配列は、ビット配列やバッファーの作成には適していません。</span><span class="sxs-lookup"><span data-stu-id="5824e-126">`bool` arrays are not appropriate for creating bit arrays or buffers.</span></span>

<span data-ttu-id="5824e-127">固定サイズ バッファーは <xref:System.Runtime.CompilerServices.UnsafeValueTypeAttribute?displayProperty=nameWithType>を使用してコンパイルされます。これにより、オーバーフローする可能性があるアンマネージド配列が型に含まれていることが共通言語ランタイム (CLR) に指示されます。</span><span class="sxs-lookup"><span data-stu-id="5824e-127">Fixed size buffers are compiled with the <xref:System.Runtime.CompilerServices.UnsafeValueTypeAttribute?displayProperty=nameWithType>, which instructs the common language runtime (CLR) that a type contains an unmanaged array that can potentially overflow.</span></span> <span data-ttu-id="5824e-128">これは [stackalloc](../../language-reference/operators/stackalloc.md) を使用して作成されたメモリに似ています。これにより、CLR 内でバッファー オーバーラン検出機能が自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="5824e-128">This is similar to memory created using [stackalloc](../../language-reference/operators/stackalloc.md), which automatically enables buffer overrun detection features in the CLR.</span></span> <span data-ttu-id="5824e-129">前の例では、`unsafe struct` に固定サイズ バッファーがどのようにして存在できるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="5824e-129">The previous example shows how a fixed size buffer could exist in an `unsafe struct`.</span></span>

```csharp
internal unsafe struct Buffer
{
    public fixed char fixedBuffer[128];
}
```

<span data-ttu-id="5824e-130">`Buffer` 用にコンパイラで生成された C# は、次のように属性が付けられます。</span><span class="sxs-lookup"><span data-stu-id="5824e-130">The compiler generated C# for `Buffer`, is attributed as follows:</span></span>

```csharp
internal struct Buffer
{
    [StructLayout(LayoutKind.Sequential, Size = 256)]
    [CompilerGenerated]
    [UnsafeValueType]
    public struct <fixedBuffer>e__FixedBuffer
    {
        public char FixedElementField;
    }

    [FixedBuffer(typeof(char), 128)]
    public <fixedBuffer>e__FixedBuffer fixedBuffer;
}
```

<span data-ttu-id="5824e-131">固定サイズ バッファーは、次の点で通常の配列とは異なります。</span><span class="sxs-lookup"><span data-stu-id="5824e-131">Fixed size buffers differ from regular arrays in the following ways:</span></span>

- <span data-ttu-id="5824e-132">[unsafe](../../language-reference/keywords/unsafe.md) のコンテキストでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="5824e-132">May only be used in an [unsafe](../../language-reference/keywords/unsafe.md) context.</span></span>
- <span data-ttu-id="5824e-133">構造体のインスタンス フィールドのみを指定できます。</span><span class="sxs-lookup"><span data-stu-id="5824e-133">May only be instance fields of structs.</span></span>
- <span data-ttu-id="5824e-134">これらは常にベクター (1 次元配列) です。</span><span class="sxs-lookup"><span data-stu-id="5824e-134">They're always vectors, or one-dimensional arrays.</span></span>
- <span data-ttu-id="5824e-135">宣言には、`fixed char id[8]` などの長さを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="5824e-135">The declaration should include the length, such as `fixed char id[8]`.</span></span> <span data-ttu-id="5824e-136">`fixed char id[]` は使用できません。</span><span class="sxs-lookup"><span data-stu-id="5824e-136">You cannot use `fixed char id[]`.</span></span>

## <a name="see-also"></a><span data-ttu-id="5824e-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="5824e-137">See also</span></span>

- [<span data-ttu-id="5824e-138">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="5824e-138">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="5824e-139">アンセーフ コードとポインター</span><span class="sxs-lookup"><span data-stu-id="5824e-139">Unsafe Code and Pointers</span></span>](index.md)
- [<span data-ttu-id="5824e-140">fixed ステートメント</span><span class="sxs-lookup"><span data-stu-id="5824e-140">fixed Statement</span></span>](../../language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="5824e-141">相互運用性</span><span class="sxs-lookup"><span data-stu-id="5824e-141">Interoperability</span></span>](../interop/index.md)
