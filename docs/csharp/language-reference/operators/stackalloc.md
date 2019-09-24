---
title: stackalloc 演算子 - C# リファレンス
ms.custom: seodec18
ms.date: 09/20/2019
f1_keywords:
- stackalloc_CSharpKeyword
helpviewer_keywords:
- stackalloc operator [C#]
ms.openlocfilehash: 9ef5f98f2b4973c5873417ecc9a71c187e7299b9
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2019
ms.locfileid: "71182419"
---
# <a name="stackalloc-operator-c-reference"></a><span data-ttu-id="12722-102">stackalloc 演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="12722-102">stackalloc operator (C# reference)</span></span>

<span data-ttu-id="12722-103">`stackalloc` 演算子は、スタックにメモリ ブロックを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="12722-103">The `stackalloc` operator allocates a block of memory on the stack.</span></span> <span data-ttu-id="12722-104">メソッドの実行中に作成された、スタックに割り当てられたメモリ ブロックは、そのメソッドが戻るときに自動的に破棄されます。</span><span class="sxs-lookup"><span data-stu-id="12722-104">A stack allocated memory block created during the method execution is automatically discarded when that method returns.</span></span> <span data-ttu-id="12722-105">`stackalloc` 演算子を使用して割り当てられたメモリを明示的に開放することはできません。</span><span class="sxs-lookup"><span data-stu-id="12722-105">You cannot explicitly free memory allocated with the `stackalloc` operator.</span></span> <span data-ttu-id="12722-106">スタックに割り当てられたメモリ ブロックは、[ガベージ コレクション](../../../standard/garbage-collection/index.md)の対象外であり、[`fixed` ステートメント](../keywords/fixed-statement.md)を使用してピン留めする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="12722-106">A stack allocated memory block is not subject to [garbage collection](../../../standard/garbage-collection/index.md) and doesn't have to be pinned with the [`fixed` statement](../keywords/fixed-statement.md).</span></span>

<span data-ttu-id="12722-107">`stackalloc T[E]` の式では、`T` が[アンマネージド型](../builtin-types/unmanaged-types.md)であり、`E` は型 `int` の式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="12722-107">In expression `stackalloc T[E]`, `T` must be an [unmanaged type](../builtin-types/unmanaged-types.md) and `E` must be an expression of type `int`.</span></span>

<span data-ttu-id="12722-108">`stackalloc` 演算子の結果を、次のいずれかの型の変数に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="12722-108">You can assign the result of the `stackalloc` operator to a variable of one of the following types:</span></span>

- <span data-ttu-id="12722-109">C# 7.2 以降では <xref:System.Span%601?displayProperty=nameWithType> または <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="12722-109">Starting with C# 7.2, <xref:System.Span%601?displayProperty=nameWithType> or <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, as the following example shows:</span></span>

  [!code-csharp[stackalloc span](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AssignToSpan)]

  <span data-ttu-id="12722-110">スタックに割り当てられたメモリ ブロックを <xref:System.Span%601> 変数または <xref:System.ReadOnlySpan%601> 変数に割り当てるときに、[unsafe](../keywords/unsafe.md) コンテキストを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="12722-110">You don't have to use an [unsafe](../keywords/unsafe.md) context when you assign a stack allocated memory block to a <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> variable.</span></span>

  <span data-ttu-id="12722-111">これらの型を操作するときに、次の例に示すように、[条件](conditional-operator.md)式または代入式の中で `stackalloc` 式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="12722-111">When you work with those types, you can use a `stackalloc` expression in [conditional](conditional-operator.md) or assignment expressions, as the following example shows:</span></span>

  [!code-csharp[stackalloc expression](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AsExpression)]

  <span data-ttu-id="12722-112">C# 8.0 以降、次の例のように、<xref:System.Span%601> または <xref:System.ReadOnlySpan%601> 式が許可されるところでは、他の式の中で `stackalloc` 式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="12722-112">Starting with C# 8.0, you can use a `stackalloc` expression inside other expressions whenever a <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> variable is allowed, as the following example shows:</span></span>

  [!code-csharp[stackalloc in nested expressions](~/samples/csharp/language-reference/operators/StackallocOperator.cs#Nested)]

  > [!NOTE]
  > <span data-ttu-id="12722-113">スタックに割り当てられたメモリを操作するときは、できるだけ <xref:System.Span%601> 型または <xref:System.ReadOnlySpan%601> 型を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="12722-113">We recommend using <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> types to work with stack allocated memory whenever possible.</span></span>

- <span data-ttu-id="12722-114">[ポインター型](../../programming-guide/unsafe-code-pointers/pointer-types.md)。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="12722-114">A [pointer type](../../programming-guide/unsafe-code-pointers/pointer-types.md), as the following example shows:</span></span>

  [!code-csharp[stackalloc pointer](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AssignToPointer)]

  <span data-ttu-id="12722-115">前の例に示したように、ポインター型を操作するときは、`unsafe` コンテキストを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="12722-115">As the preceding example shows, you must use an `unsafe` context when you work with pointer types.</span></span>

  <span data-ttu-id="12722-116">ポインター型の場合、ローカル変数宣言でのみ `stackalloc` 式を使用し、変数を初期化できます。</span><span class="sxs-lookup"><span data-stu-id="12722-116">In the case of pointer types, you can use a `stackalloc` expression only in a local variable declaration to initialize the variable.</span></span>

<span data-ttu-id="12722-117">新しく割り当てられたメモリの内容は未定義です。</span><span class="sxs-lookup"><span data-stu-id="12722-117">The content of the newly allocated memory is undefined.</span></span> <span data-ttu-id="12722-118">C# 7.3 以降、配列初期化子構文を使用して、新しく割り当てられたメモリの内容を定義できます。</span><span class="sxs-lookup"><span data-stu-id="12722-118">Starting with C# 7.3, you can use array initializer syntax to define the content of the newly allocated memory.</span></span> <span data-ttu-id="12722-119">これを実行するさまざまな方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="12722-119">The following example demonstrates various ways to do that:</span></span>

[!code-csharp[stackalloc initialization](~/samples/csharp/language-reference/operators/StackallocOperator.cs#StackallocInit)]

## <a name="security"></a><span data-ttu-id="12722-120">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="12722-120">Security</span></span>

<span data-ttu-id="12722-121">`stackalloc` を使用すると、共通言語ランタイム (CLR) のバッファー オーバーラン検出機能が自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="12722-121">The use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="12722-122">バッファー オーバーランが検出されると、悪意のあるコードが実行される可能性を最小限に抑えるために、プロセスはできる限り迅速に終了されます。</span><span class="sxs-lookup"><span data-stu-id="12722-122">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="12722-123">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="12722-123">C# language specification</span></span>

<span data-ttu-id="12722-124">詳細については、[C# 言語仕様](~/_csharplang/spec/introduction.md)に関するページの「[Stack allocation (スタック割り当て)](~/_csharplang/spec/unsafe-code.md#stack-allocation)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="12722-124">For more information, see the [Stack allocation](~/_csharplang/spec/unsafe-code.md#stack-allocation) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="12722-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="12722-125">See also</span></span>

- [<span data-ttu-id="12722-126">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="12722-126">C# reference</span></span>](../index.md)
- [<span data-ttu-id="12722-127">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="12722-127">C# operators</span></span>](index.md)
- [<span data-ttu-id="12722-128">ポインターに関連する演算子</span><span class="sxs-lookup"><span data-stu-id="12722-128">Pointer related operators</span></span>](pointer-related-operators.md)
- [<span data-ttu-id="12722-129">ポインター型</span><span class="sxs-lookup"><span data-stu-id="12722-129">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="12722-130">メモリおよびスパンに関連する型</span><span class="sxs-lookup"><span data-stu-id="12722-130">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
