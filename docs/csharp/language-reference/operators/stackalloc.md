---
title: stackalloc 演算子 - C# リファレンス
ms.custom: seodec18
ms.date: 06/10/2019
f1_keywords:
- stackalloc_CSharpKeyword
helpviewer_keywords:
- stackalloc operator [C#]
ms.openlocfilehash: f211acaa8c47ab42a1f7f06cff6c35570cd22b75
ms.sourcegitcommit: 1e7ac70be1b4d89708c0d9552897515f2cbf52c4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68433825"
---
# <a name="stackalloc-operator-c-reference"></a><span data-ttu-id="06464-102">stackalloc 演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="06464-102">stackalloc operator (C# reference)</span></span>

<span data-ttu-id="06464-103">`stackalloc` 演算子は、スタックにメモリ ブロックを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="06464-103">The `stackalloc` operator allocates a block of memory on the stack.</span></span> <span data-ttu-id="06464-104">メソッドの実行中に作成された、スタックに割り当てられたメモリ ブロックは、そのメソッドが戻るときに自動的に破棄されます。</span><span class="sxs-lookup"><span data-stu-id="06464-104">A stack allocated memory block created during the method execution is automatically discarded when that method returns.</span></span> <span data-ttu-id="06464-105">`stackalloc` 演算子を使用して割り当てられたメモリを明示的に開放することはできません。</span><span class="sxs-lookup"><span data-stu-id="06464-105">You cannot explicitly free memory allocated with the `stackalloc` operator.</span></span> <span data-ttu-id="06464-106">スタックに割り当てられたメモリ ブロックは、[ガベージ コレクション](../../../standard/garbage-collection/index.md)の対象外であり、[`fixed` ステートメント](../keywords/fixed-statement.md)を使用してピン留めする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="06464-106">A stack allocated memory block is not subject to [garbage collection](../../../standard/garbage-collection/index.md) and doesn't have to be pinned with the [`fixed` statement](../keywords/fixed-statement.md).</span></span>

<span data-ttu-id="06464-107">`stackalloc T[E]` の式では、`T` が[アンマネージド型](../builtin-types/unmanaged-types.md)であり、`E` は型 `int` の式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="06464-107">In expression `stackalloc T[E]`, `T` must be an [unmanaged type](../builtin-types/unmanaged-types.md) and `E` must be an expression of type `int`.</span></span>

<span data-ttu-id="06464-108">`stackalloc` 演算子の結果を、次のいずれかの型の変数に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="06464-108">You can assign the result of the `stackalloc` operator to a variable of one of the following types:</span></span>

- <span data-ttu-id="06464-109">C# 7.2 以降では <xref:System.Span%601?displayProperty=nameWithType> または <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="06464-109">Starting with C# 7.2, <xref:System.Span%601?displayProperty=nameWithType> or <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, as the following example shows:</span></span>

  [!code-csharp[stackalloc span](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AssignToSpan)]

  <span data-ttu-id="06464-110">スタックに割り当てられたメモリ ブロックを <xref:System.Span%601> 変数または <xref:System.ReadOnlySpan%601> 変数に割り当てるときに、[unsafe](../keywords/unsafe.md) コンテキストを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="06464-110">You don't have to use an [unsafe](../keywords/unsafe.md) context when you assign a stack allocated memory block to a <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> variable.</span></span>

  <span data-ttu-id="06464-111">これらの型を操作するときに、次の例に示すように、[条件](conditional-operator.md)式または代入式の中で `stackalloc` 式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="06464-111">When you work with those types, you can use a `stackalloc` expression in [conditional](conditional-operator.md) or assignment expressions, as the following example shows:</span></span>

  [!code-csharp[stackalloc expression](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AsExpression)]

  > [!NOTE]
  > <span data-ttu-id="06464-112">スタックに割り当てられたメモリを操作するときは、できるだけ <xref:System.Span%601> 型または <xref:System.ReadOnlySpan%601> 型を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="06464-112">We recommend using <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> types to work with stack allocated memory whenever possible.</span></span>

- <span data-ttu-id="06464-113">[ポインター型](../../programming-guide/unsafe-code-pointers/pointer-types.md)。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="06464-113">A [pointer type](../../programming-guide/unsafe-code-pointers/pointer-types.md), as the following example shows:</span></span>

  [!code-csharp[stackalloc pointer](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AssignToPointer)]

  <span data-ttu-id="06464-114">前の例に示したように、ポインター型を操作するときは、`unsafe` コンテキストを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="06464-114">As the preceding example shows, you must use an `unsafe` context when you work with pointer types.</span></span>

<span data-ttu-id="06464-115">新しく割り当てられたメモリの内容は未定義です。</span><span class="sxs-lookup"><span data-stu-id="06464-115">The content of the newly allocated memory is undefined.</span></span> <span data-ttu-id="06464-116">C# 7.3 以降、配列初期化子構文を使用して、新しく割り当てられたメモリの内容を定義できます。</span><span class="sxs-lookup"><span data-stu-id="06464-116">Starting with C# 7.3, you can use array initializer syntax to define the content of the newly allocated memory.</span></span> <span data-ttu-id="06464-117">これを実行するさまざまな方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="06464-117">The following example demonstrates various ways to do that:</span></span>

[!code-csharp[stackalloc initialization](~/samples/csharp/language-reference/operators/StackallocOperator.cs#StackallocInit)]

## <a name="security"></a><span data-ttu-id="06464-118">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="06464-118">Security</span></span>

<span data-ttu-id="06464-119">`stackalloc` を使用すると、共通言語ランタイム (CLR) のバッファー オーバーラン検出機能が自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="06464-119">The use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="06464-120">バッファー オーバーランが検出されると、悪意のあるコードが実行される可能性を最小限に抑えるために、プロセスはできる限り迅速に終了されます。</span><span class="sxs-lookup"><span data-stu-id="06464-120">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="06464-121">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="06464-121">C# language specification</span></span>

<span data-ttu-id="06464-122">詳細については、[C# 言語仕様](~/_csharplang/spec/introduction.md)に関するページの「[Stack allocation (スタック割り当て)](~/_csharplang/spec/unsafe-code.md#stack-allocation)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="06464-122">For more information, see the [Stack allocation](~/_csharplang/spec/unsafe-code.md#stack-allocation) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="06464-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="06464-123">See also</span></span>

- [<span data-ttu-id="06464-124">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="06464-124">C# reference</span></span>](../index.md)
- [<span data-ttu-id="06464-125">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="06464-125">C# operators</span></span>](index.md)
- [<span data-ttu-id="06464-126">ポインターに関連する演算子</span><span class="sxs-lookup"><span data-stu-id="06464-126">Pointer related operators</span></span>](pointer-related-operators.md)
- [<span data-ttu-id="06464-127">ポインター型</span><span class="sxs-lookup"><span data-stu-id="06464-127">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="06464-128">メモリおよびスパンに関連する型</span><span class="sxs-lookup"><span data-stu-id="06464-128">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
