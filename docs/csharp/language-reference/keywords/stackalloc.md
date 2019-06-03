---
title: stackalloc キーワード - C# リファレンス
ms.custom: seodec18
ms.date: 04/10/2019
f1_keywords:
- stackalloc_CSharpKeyword
- stackalloc
helpviewer_keywords:
- stackalloc keyword [C#]
ms.openlocfilehash: c72daa58d2fceb05d9cc9c388a9d2e5dbe062796
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422429"
---
# <a name="stackalloc-c-reference"></a><span data-ttu-id="87e00-102">stackalloc (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="87e00-102">stackalloc (C# Reference)</span></span>

<span data-ttu-id="87e00-103">`stackalloc` キーワードは、スタックにメモリ ブロックを割り当てるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="87e00-103">The `stackalloc` keyword is used to allocate a block of memory on the stack.</span></span>

```csharp
Span<int> block = stackalloc int[100];
```

<span data-ttu-id="87e00-104">割り当てられたブロックを `int*` ではなく <xref:System.Span%601?displayName=nameWithType> に割り当てると、安全なブロックでスタックを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="87e00-104">Assigning the allocated block to a <xref:System.Span%601?displayName=nameWithType> instead of an `int*` allows stack allocations in a safe block.</span></span> <span data-ttu-id="87e00-105">`unsafe` コンテキストは必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="87e00-105">The `unsafe` context is not required.</span></span>

## <a name="remarks"></a><span data-ttu-id="87e00-106">解説</span><span class="sxs-lookup"><span data-stu-id="87e00-106">Remarks</span></span>

<span data-ttu-id="87e00-107">このキーワードは、ローカル変数初期化子でのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="87e00-107">The keyword is valid only in local variable initializers.</span></span> <span data-ttu-id="87e00-108">次のコードはコンパイル エラーになります。</span><span class="sxs-lookup"><span data-stu-id="87e00-108">The following code causes compiler errors.</span></span>

```csharp
int* block;
// The following assignment statement causes compiler errors. You
// can use stackalloc only when declaring and initializing a local
// variable.
block = stackalloc int[100];
Span<int> span;
// The following assignment statement causes compiler errors. You
// can use stackalloc only when declaring and initializing a local
// variable.
span = stackalloc int[100];
```

<span data-ttu-id="87e00-109">C# 7.3 以降では、`stackalloc` 配列に対して配列初期化子構文を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="87e00-109">Beginning with C# 7.3, you can use array initializer syntax for `stackalloc` arrays.</span></span> <span data-ttu-id="87e00-110">次のすべての宣言では、値が整数 `1`、`2`、`3` である 3 つの要素を含む配列が宣言されています。</span><span class="sxs-lookup"><span data-stu-id="87e00-110">All the following declarations declare an array with three elements whose values are the integers `1`, `2`, and `3`.</span></span> <span data-ttu-id="87e00-111">2 回目の初期化でメモリを <xref:System.ReadOnlySpan%601> に割り当て、メモリを変更できないことを示します。</span><span class="sxs-lookup"><span data-stu-id="87e00-111">The second initialization assigns the memory to a <xref:System.ReadOnlySpan%601>, indicating that the memory cannot be modified.</span></span>

```csharp
// Valid starting with C# 7.3
Span<int> first = stackalloc int[3] { 1, 2, 3 };
ReadOnlySpan<int> second = stackalloc int[] { 1, 2, 3 };
Span<int> third = stackalloc[] { 1, 2, 3 };
```

<span data-ttu-id="87e00-112">ポインター型が使用される場合、`stackalloc` には [unsafe](unsafe.md) コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="87e00-112">When pointer types are involved, `stackalloc` requires an [unsafe](unsafe.md) context.</span></span> <span data-ttu-id="87e00-113">詳細については、「[アンセーフ コードとポインター](../../programming-guide/unsafe-code-pointers/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87e00-113">For more information, see [Unsafe Code and Pointers](../../programming-guide/unsafe-code-pointers/index.md).</span></span>

<span data-ttu-id="87e00-114">`stackalloc` は、C ランタイム ライブラリの [_alloca](/cpp/c-runtime-library/reference/alloca) に似ています。</span><span class="sxs-lookup"><span data-stu-id="87e00-114">`stackalloc` is like [_alloca](/cpp/c-runtime-library/reference/alloca) in the C run-time library.</span></span>

## <a name="examples"></a><span data-ttu-id="87e00-115">使用例</span><span class="sxs-lookup"><span data-stu-id="87e00-115">Examples</span></span>

<span data-ttu-id="87e00-116">次の例では、フィボナッチ数列の最初の 20 個の数値を計算して表示します。</span><span class="sxs-lookup"><span data-stu-id="87e00-116">The following example calculates and displays the first 20 numbers in the Fibonacci sequence.</span></span> <span data-ttu-id="87e00-117">それぞれの数値が、前の 2 つの数値の和になっています。</span><span class="sxs-lookup"><span data-stu-id="87e00-117">Each number is the sum of the previous two numbers.</span></span> <span data-ttu-id="87e00-118">このコードでは、`int` 型の要素を 20 個保持できるサイズのメモリ ブロックが、ヒープではなくスタックに割り当てられ、</span><span class="sxs-lookup"><span data-stu-id="87e00-118">In the code, a block of memory of sufficient size to contain 20 elements of type `int` is allocated on the stack, not the heap.</span></span> <span data-ttu-id="87e00-119">そのブロックのアドレスは `Span` `fib` に格納されます。</span><span class="sxs-lookup"><span data-stu-id="87e00-119">The address of the block is stored in the `Span` `fib`.</span></span> <span data-ttu-id="87e00-120">このメモリは、ガベージ コレクションの対象にはならないため、[fixed](fixed-statement.md) を使用して固定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="87e00-120">This memory is not subject to garbage collection and therefore does not have to be pinned (by using [fixed](fixed-statement.md)).</span></span> <span data-ttu-id="87e00-121">メモリ ブロックの有効期間は、そのブロックを定義するメソッドの有効期間に限定されます。</span><span class="sxs-lookup"><span data-stu-id="87e00-121">The lifetime of the memory block is limited to the lifetime of the method that defines it.</span></span> <span data-ttu-id="87e00-122">メソッドから制御が戻る前に、メモリを解放することはできません。</span><span class="sxs-lookup"><span data-stu-id="87e00-122">You cannot free the memory before the method returns.</span></span>

[!code-csharp[csrefKeywordsOperator#15](~/samples/snippets/csharp/keywords/StackAllocExamples.cs#1)]

<span data-ttu-id="87e00-123">次の例では、整数の `stackalloc` 配列を、要素ごとに 1 ビットが設定されているビット マスクに初期化しています。</span><span class="sxs-lookup"><span data-stu-id="87e00-123">The following example initializes a `stackalloc` array of integers to a bit mask with one bit set in each element.</span></span> <span data-ttu-id="87e00-124">これは、C# 7.3 以降で使用可能な新しい初期化子の構文を示しています。</span><span class="sxs-lookup"><span data-stu-id="87e00-124">This demonstrates the new initializer syntax available starting in C# 7.3:</span></span>

[!code-csharp[csrefKeywordsOperator#15](~/samples/snippets/csharp/keywords/StackAllocExamples.cs#2)]

## <a name="security"></a><span data-ttu-id="87e00-125">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="87e00-125">Security</span></span>

<span data-ttu-id="87e00-126">アンセーフ コードはセーフ コードよりも安全性が低いため、可能な限り <xref:System.Span%601> または <xref:System.ReadOnlySpan%601> を使用してください。</span><span class="sxs-lookup"><span data-stu-id="87e00-126">You should use <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> when possible because unsafe code is less secure than safe alternatives.</span></span> <span data-ttu-id="87e00-127">ポインターと共に使用したとしても、`stackalloc` を使用すると、共通言語ランタイム (CLR) のバッファー オーバーラン検出機能が自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="87e00-127">Even when used with pointers, the use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="87e00-128">バッファー オーバーランが検出されると、悪意のあるコードが実行される可能性を最小限に抑えるために、プロセスはできる限り迅速に終了されます。</span><span class="sxs-lookup"><span data-stu-id="87e00-128">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="87e00-129">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="87e00-129">C# language specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="87e00-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="87e00-130">See also</span></span>

- [<span data-ttu-id="87e00-131">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="87e00-131">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="87e00-132">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="87e00-132">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="87e00-133">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="87e00-133">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="87e00-134">アンセーフ コードとポインター</span><span class="sxs-lookup"><span data-stu-id="87e00-134">Unsafe Code and Pointers</span></span>](../../programming-guide/unsafe-code-pointers/index.md)
