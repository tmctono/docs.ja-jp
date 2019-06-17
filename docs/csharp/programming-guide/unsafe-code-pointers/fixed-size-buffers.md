---
title: 固定サイズ バッファー - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 04/20/2018
helpviewer_keywords:
- fixed size buffers [C#]
- unsafe buffers [C#]
- unsafe code [C#], fixed size buffers
ms.openlocfilehash: 5bfd9f3f559e4780b910a2e5a3430b08a2183ee3
ms.sourcegitcommit: 34593b4d0be779699d38a9949d6aec11561657ec
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2019
ms.locfileid: "66833497"
---
# <a name="fixed-size-buffers-c-programming-guide"></a><span data-ttu-id="ceda6-102">固定サイズ バッファー (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="ceda6-102">Fixed Size Buffers (C# Programming Guide)</span></span>

<span data-ttu-id="ceda6-103">C# では、[fixed](../../language-reference/keywords/fixed-statement.md) ステートメントを使って、データの構造体に固定サイズの配列を持ったバッファーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="ceda6-103">In C#, you can use the [fixed](../../language-reference/keywords/fixed-statement.md) statement to create a buffer with a fixed size array in a data structure.</span></span> <span data-ttu-id="ceda6-104">固定サイズのバッファーは、他の言語またはプラットフォームのデータ ソースと相互運用するメソッドを作成するときに便利です。</span><span class="sxs-lookup"><span data-stu-id="ceda6-104">Fixed size buffers are useful when you write methods that interop with data sources from other languages or platforms.</span></span> <span data-ttu-id="ceda6-105">この固定配列には、標準的な構造体メンバーで許容されている属性または修飾子であれば、何でも適用することができます。</span><span class="sxs-lookup"><span data-stu-id="ceda6-105">The fixed array can take any attributes or modifiers that are allowed for regular struct members.</span></span> <span data-ttu-id="ceda6-106">ただし配列の型は `bool`、`byte`、`char`、`short`、`int`、`long`、`sbyte`、`ushort`、`uint`、`ulong`、`float`、`double` のいずれかに該当する必要があり、それが唯一の制限となります。</span><span class="sxs-lookup"><span data-stu-id="ceda6-106">The only restriction is that the array type must be `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float`, or `double`.</span></span>

```csharp
private fixed char name[30];
```

## <a name="remarks"></a><span data-ttu-id="ceda6-107">コメント</span><span class="sxs-lookup"><span data-stu-id="ceda6-107">Remarks</span></span>

<span data-ttu-id="ceda6-108">セーフ コードでは、配列を含む C# 構造体に配列要素が含まれません。</span><span class="sxs-lookup"><span data-stu-id="ceda6-108">In safe code, a C# struct that contains an array does not contain the array elements.</span></span> <span data-ttu-id="ceda6-109">この場合、構造体には、配列の要素ではなく、その参照が格納されます。</span><span class="sxs-lookup"><span data-stu-id="ceda6-109">Instead, the struct contains a reference to the elements.</span></span> <span data-ttu-id="ceda6-110">[unsafe](../../language-reference/keywords/unsafe.md) のコード ブロックで使われている [struct](../../language-reference/keywords/struct.md) に、固定サイズの配列を埋め込むことができます。</span><span class="sxs-lookup"><span data-stu-id="ceda6-110">You can embed an array of fixed size in a [struct](../../language-reference/keywords/struct.md) when it is used in an [unsafe](../../language-reference/keywords/unsafe.md) code block.</span></span>

<span data-ttu-id="ceda6-111">次の `struct` のサイズは 8 バイトです。</span><span class="sxs-lookup"><span data-stu-id="ceda6-111">The following `struct` is 8 bytes in size.</span></span> <span data-ttu-id="ceda6-112">`pathName` 配列は参照です。</span><span class="sxs-lookup"><span data-stu-id="ceda6-112">The `pathName` array is a reference:</span></span>

[!code-csharp[Struct with embedded array](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#6)]

<span data-ttu-id="ceda6-113">アンセーフ コードでは、`struct` に埋め込み配列を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="ceda6-113">A `struct` can contain an embedded array in unsafe code.</span></span> <span data-ttu-id="ceda6-114">以下の例の `fixedBuffer` 配列は固定サイズです。</span><span class="sxs-lookup"><span data-stu-id="ceda6-114">In the following example, the `fixedBuffer` array has a fixed size.</span></span> <span data-ttu-id="ceda6-115">`fixed` ステートメントを使用して、先頭要素へのポインターを確立します。</span><span class="sxs-lookup"><span data-stu-id="ceda6-115">You use a `fixed` statement to establish a pointer to the first element.</span></span> <span data-ttu-id="ceda6-116">このポインターを使用して配列の要素にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="ceda6-116">You access the elements of the array through this pointer.</span></span> <span data-ttu-id="ceda6-117">`fixed` ステートメントによって、`fixedBuffer` インスタンス フィールドがメモリ内の特定の位置に固定されます。</span><span class="sxs-lookup"><span data-stu-id="ceda6-117">The `fixed` statement pins the `fixedBuffer` instance field to a specific location in memory.</span></span>

[!code-csharp[Struct with embedded inline array](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#7)]

<span data-ttu-id="ceda6-118">要素数 128 の `char` 配列のサイズは 256 バイトです。</span><span class="sxs-lookup"><span data-stu-id="ceda6-118">The size of the 128 element `char` array is 256 bytes.</span></span> <span data-ttu-id="ceda6-119">固定サイズの [char](../../language-reference/keywords/char.md) 型バッファーは、エンコーディングに関係なく常に、1 文字あたり 2 バイトを消費します。</span><span class="sxs-lookup"><span data-stu-id="ceda6-119">Fixed size [char](../../language-reference/keywords/char.md) buffers always take two bytes per character, regardless of the encoding.</span></span> <span data-ttu-id="ceda6-120">これは、char 型のバッファーが、`CharSet = CharSet.Auto` または `CharSet = CharSet.Ansi` で API メソッドや構造体にマーシャリングされたときにも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="ceda6-120">This is true even when char buffers are marshaled to API methods or structs with `CharSet = CharSet.Auto` or `CharSet = CharSet.Ansi`.</span></span> <span data-ttu-id="ceda6-121">詳細については、「<xref:System.Runtime.InteropServices.CharSet>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ceda6-121">For more information, see <xref:System.Runtime.InteropServices.CharSet>.</span></span>

<span data-ttu-id="ceda6-122">上記の例は、固定せずに `fixed` フィールドにアクセスする方法を示しています。この方法は C# 7.3 以降から使用できます。</span><span class="sxs-lookup"><span data-stu-id="ceda6-122">The  preceding example demonstrates accessing `fixed` fields without pinning, which is available starting with C# 7.3.</span></span>

<span data-ttu-id="ceda6-123">一般的な固定サイズの配列としては、他にも [bool](../../language-reference/keywords/bool.md) 配列があります。</span><span class="sxs-lookup"><span data-stu-id="ceda6-123">Another common fixed-size array is the [bool](../../language-reference/keywords/bool.md) array.</span></span> <span data-ttu-id="ceda6-124">`bool` 配列内の要素のサイズは常に 1 バイトです。</span><span class="sxs-lookup"><span data-stu-id="ceda6-124">The elements in a `bool` array are always one byte in size.</span></span> <span data-ttu-id="ceda6-125">`bool` 配列は、ビット配列やバッファーの作成には適していません。</span><span class="sxs-lookup"><span data-stu-id="ceda6-125">`bool` arrays are not appropriate for creating bit arrays or buffers.</span></span>

> [!NOTE]
> <span data-ttu-id="ceda6-126">C# コンパイラおよび共通言語ランタイム (CLR) は、[stackalloc](../../language-reference/operators/stackalloc.md) を使って作成されたメモリを除き、バッファー オーバーランのセキュリティ チェックを実行しません。</span><span class="sxs-lookup"><span data-stu-id="ceda6-126">Except for memory created by using [stackalloc](../../language-reference/operators/stackalloc.md), the C# compiler and the common language runtime (CLR) do not perform any security buffer overrun checks.</span></span> <span data-ttu-id="ceda6-127">その他のアンセーフ コードと同様、十分な注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="ceda6-127">As with all unsafe code, use caution.</span></span>

<span data-ttu-id="ceda6-128">アンセーフ バッファーは、次の点で通常の配列とは異なります。</span><span class="sxs-lookup"><span data-stu-id="ceda6-128">Unsafe buffers differ from regular arrays in the following ways:</span></span>

- <span data-ttu-id="ceda6-129">アンセーフ バッファーの使用は、unsafe コンテキストに限られます。</span><span class="sxs-lookup"><span data-stu-id="ceda6-129">You can only use unsafe buffers in an unsafe context.</span></span>
- <span data-ttu-id="ceda6-130">アンセーフ バッファーは常にベクタ (1 次元配列) です。</span><span class="sxs-lookup"><span data-stu-id="ceda6-130">Unsafe buffers are always vectors, or one-dimensional arrays.</span></span>
- <span data-ttu-id="ceda6-131">配列の宣言には要素数を指定する必要があります (例: `char id[8]`)。</span><span class="sxs-lookup"><span data-stu-id="ceda6-131">The declaration of the array should include a count, such as `char id[8]`.</span></span> <span data-ttu-id="ceda6-132">`char id[]` は使用できません。</span><span class="sxs-lookup"><span data-stu-id="ceda6-132">You cannot use `char id[]`.</span></span>
- <span data-ttu-id="ceda6-133">アンセーフ バッファーは、unsafe コンテキストで構造体のインスタンス フィールドとしてのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="ceda6-133">Unsafe buffers can only be instance fields of structs in an unsafe context.</span></span>

## <a name="see-also"></a><span data-ttu-id="ceda6-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="ceda6-134">See also</span></span>

- [<span data-ttu-id="ceda6-135">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="ceda6-135">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="ceda6-136">アンセーフ コードとポインター</span><span class="sxs-lookup"><span data-stu-id="ceda6-136">Unsafe Code and Pointers</span></span>](index.md)
- [<span data-ttu-id="ceda6-137">fixed ステートメント</span><span class="sxs-lookup"><span data-stu-id="ceda6-137">fixed Statement</span></span>](../../language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="ceda6-138">相互運用性</span><span class="sxs-lookup"><span data-stu-id="ceda6-138">Interoperability</span></span>](../interop/index.md)
