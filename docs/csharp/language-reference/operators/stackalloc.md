---
title: stackalloc 式 - C# リファレンス
ms.date: 03/13/2020
f1_keywords:
- stackalloc_CSharpKeyword
helpviewer_keywords:
- stackalloc expression [C#]
ms.openlocfilehash: 2e99ce8b1e44dfa040c1acac799a3a55b375bd91
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2020
ms.locfileid: "79546602"
---
# <a name="stackalloc-expression-c-reference"></a><span data-ttu-id="81a74-102">stackalloc 式 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="81a74-102">stackalloc expression (C# reference)</span></span>

<span data-ttu-id="81a74-103">`stackalloc` 式を使用すると、スタックにメモリ ブロックを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="81a74-103">A `stackalloc` expression allocates a block of memory on the stack.</span></span> <span data-ttu-id="81a74-104">メソッドの実行中に作成された、スタックに割り当てられたメモリ ブロックは、そのメソッドが戻るときに自動的に破棄されます。</span><span class="sxs-lookup"><span data-stu-id="81a74-104">A stack allocated memory block created during the method execution is automatically discarded when that method returns.</span></span> <span data-ttu-id="81a74-105">`stackalloc` を使用して割り当てられたメモリを明示的に開放することはできません。</span><span class="sxs-lookup"><span data-stu-id="81a74-105">You cannot explicitly free the memory allocated with `stackalloc`.</span></span> <span data-ttu-id="81a74-106">スタックに割り当てられたメモリ ブロックは、[ガベージ コレクション](../../../standard/garbage-collection/index.md)の対象外であり、[`fixed` ステートメント](../keywords/fixed-statement.md)を使用してピン留めする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="81a74-106">A stack allocated memory block is not subject to [garbage collection](../../../standard/garbage-collection/index.md) and doesn't have to be pinned with a [`fixed` statement](../keywords/fixed-statement.md).</span></span>

<span data-ttu-id="81a74-107">`stackalloc` 式の結果を、次のいずれかの型の変数に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="81a74-107">You can assign the result of a `stackalloc` expression to a variable of one of the following types:</span></span>

- <span data-ttu-id="81a74-108">C# 7.2 以降では <xref:System.Span%601?displayProperty=nameWithType> または <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="81a74-108">Beginning with C# 7.2, <xref:System.Span%601?displayProperty=nameWithType> or <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, as the following example shows:</span></span>

  [!code-csharp[stackalloc span](snippets/StackallocOperator.cs#AssignToSpan)]

  <span data-ttu-id="81a74-109">スタックに割り当てられたメモリ ブロックを <xref:System.Span%601> 変数または <xref:System.ReadOnlySpan%601> 変数に割り当てるときに、[unsafe](../keywords/unsafe.md) コンテキストを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="81a74-109">You don't have to use an [unsafe](../keywords/unsafe.md) context when you assign a stack allocated memory block to a <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> variable.</span></span>

  <span data-ttu-id="81a74-110">これらの型を操作するときに、次の例に示すように、[条件](conditional-operator.md)式または代入式の中で `stackalloc` 式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="81a74-110">When you work with those types, you can use a `stackalloc` expression in [conditional](conditional-operator.md) or assignment expressions, as the following example shows:</span></span>

  [!code-csharp[stackalloc expression](snippets/StackallocOperator.cs#AsExpression)]

  <span data-ttu-id="81a74-111">C# 8.0 以降では、次の例のように、<xref:System.Span%601> または <xref:System.ReadOnlySpan%601> の変数が許可されるところでは、他の式の中で `stackalloc` 式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="81a74-111">Beginning with C# 8.0, you can use a `stackalloc` expression inside other expressions whenever a <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> variable is allowed, as the following example shows:</span></span>

  [!code-csharp[stackalloc in nested expressions](snippets/StackallocOperator.cs#Nested)]

  > [!NOTE]
  > <span data-ttu-id="81a74-112">スタックに割り当てられたメモリを操作するときは、できるだけ <xref:System.Span%601> 型または <xref:System.ReadOnlySpan%601> 型を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="81a74-112">We recommend using <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> types to work with stack allocated memory whenever possible.</span></span>

- <span data-ttu-id="81a74-113">[ポインター型](../../programming-guide/unsafe-code-pointers/pointer-types.md)。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="81a74-113">A [pointer type](../../programming-guide/unsafe-code-pointers/pointer-types.md), as the following example shows:</span></span>

  [!code-csharp[stackalloc pointer](snippets/StackallocOperator.cs#AssignToPointer)]

  <span data-ttu-id="81a74-114">前の例に示したように、ポインター型を操作するときは、`unsafe` コンテキストを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81a74-114">As the preceding example shows, you must use an `unsafe` context when you work with pointer types.</span></span>

  <span data-ttu-id="81a74-115">ポインター型の場合、ローカル変数宣言でのみ `stackalloc` 式を使用し、変数を初期化できます。</span><span class="sxs-lookup"><span data-stu-id="81a74-115">In the case of pointer types, you can use a `stackalloc` expression only in a local variable declaration to initialize the variable.</span></span>

<span data-ttu-id="81a74-116">スタックで使用可能なメモリ容量は制限されています。</span><span class="sxs-lookup"><span data-stu-id="81a74-116">The amount of memory available on the stack is limited.</span></span> <span data-ttu-id="81a74-117">スタックに割り当てたメモリが多すぎると、<xref:System.StackOverflowException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="81a74-117">If you allocate too much memory on the stack, a <xref:System.StackOverflowException> is thrown.</span></span> <span data-ttu-id="81a74-118">これを回避するために、次の規則に従ってください。</span><span class="sxs-lookup"><span data-stu-id="81a74-118">To avoid that, follow the rules below:</span></span>

- <span data-ttu-id="81a74-119">`stackalloc` を使って割り当てるメモリ容量を制限する:</span><span class="sxs-lookup"><span data-stu-id="81a74-119">Limit the amount of memory you allocate with `stackalloc`:</span></span>

  [!code-csharp[limit stackalloc](snippets/StackallocOperator.cs#LimitStackalloc)]

  <span data-ttu-id="81a74-120">スタックで使用可能なメモリ容量はコードが実行される環境によって異なるため、実際の制限値は控えめに定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81a74-120">Because the amount of memory available on the stack depends on the environment in which the code is executed, be conservative when you define the actual limit value.</span></span>

- <span data-ttu-id="81a74-121">ループ内での `stackalloc` の使用を避ける。</span><span class="sxs-lookup"><span data-stu-id="81a74-121">Avoid using `stackalloc` inside loops.</span></span> <span data-ttu-id="81a74-122">ループの外側でメモリ ブロックを割り当て、それをループ内で再利用してください。</span><span class="sxs-lookup"><span data-stu-id="81a74-122">Allocate the memory block outside a loop and reuse it inside the loop.</span></span>

<span data-ttu-id="81a74-123">新しく割り当てられたメモリの内容は未定義です。</span><span class="sxs-lookup"><span data-stu-id="81a74-123">The content of the newly allocated memory is undefined.</span></span> <span data-ttu-id="81a74-124">これは、使用する前に初期化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81a74-124">You should initialize it before the use.</span></span> <span data-ttu-id="81a74-125">たとえば、すべての項目を `T` 型の既定値に設定する <xref:System.Span%601.Clear%2A?displayProperty=nameWithType> メソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="81a74-125">For example, you can use the <xref:System.Span%601.Clear%2A?displayProperty=nameWithType> method that sets all the items to the default value of type `T`.</span></span>

<span data-ttu-id="81a74-126">C# 7.3 以降、配列初期化子構文を使用して、新しく割り当てられたメモリの内容を定義できます。</span><span class="sxs-lookup"><span data-stu-id="81a74-126">Beginning with C# 7.3, you can use array initializer syntax to define the content of the newly allocated memory.</span></span> <span data-ttu-id="81a74-127">これを実行するさまざまな方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="81a74-127">The following example demonstrates various ways to do that:</span></span>

[!code-csharp[stackalloc initialization](snippets/StackallocOperator.cs#StackallocInit)]

<span data-ttu-id="81a74-128">式 `stackalloc T[E]` では、`T` は[アンマネージド型](../builtin-types/unmanaged-types.md)である必要があり、`E` は負でない [int](../builtin-types/integral-numeric-types.md) 値に評価される必要があります。</span><span class="sxs-lookup"><span data-stu-id="81a74-128">In expression `stackalloc T[E]`, `T` must be an [unmanaged type](../builtin-types/unmanaged-types.md) and `E` must evaluate to a non-negative [int](../builtin-types/integral-numeric-types.md) value.</span></span>

## <a name="security"></a><span data-ttu-id="81a74-129">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="81a74-129">Security</span></span>

<span data-ttu-id="81a74-130">`stackalloc` を使用すると、共通言語ランタイム (CLR) のバッファー オーバーラン検出機能が自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="81a74-130">The use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="81a74-131">バッファー オーバーランが検出されると、悪意のあるコードが実行される可能性を最小限に抑えるために、プロセスはできる限り迅速に終了されます。</span><span class="sxs-lookup"><span data-stu-id="81a74-131">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="81a74-132">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="81a74-132">C# language specification</span></span>

<span data-ttu-id="81a74-133">詳細については、[C# 言語仕様](~/_csharplang/spec/introduction.md)に関するページの「[スタック割り当て](~/_csharplang/spec/unsafe-code.md#stack-allocation)」セクションと、[入れ子になった `stackalloc` の許可](~/_csharplang/proposals/csharp-8.0/nested-stackalloc.md)に関する機能提案メモをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="81a74-133">For more information, see the [Stack allocation](~/_csharplang/spec/unsafe-code.md#stack-allocation) section of the [C# language specification](~/_csharplang/spec/introduction.md) and the [Permit `stackalloc` in nested contexts](~/_csharplang/proposals/csharp-8.0/nested-stackalloc.md) feature proposal note.</span></span>

## <a name="see-also"></a><span data-ttu-id="81a74-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="81a74-134">See also</span></span>

- [<span data-ttu-id="81a74-135">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="81a74-135">C# reference</span></span>](../index.md)
- [<span data-ttu-id="81a74-136">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="81a74-136">C# operators</span></span>](index.md)
- [<span data-ttu-id="81a74-137">ポインターに関連する演算子</span><span class="sxs-lookup"><span data-stu-id="81a74-137">Pointer related operators</span></span>](pointer-related-operators.md)
- [<span data-ttu-id="81a74-138">ポインター型</span><span class="sxs-lookup"><span data-stu-id="81a74-138">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="81a74-139">メモリおよびスパンに関連する型</span><span class="sxs-lookup"><span data-stu-id="81a74-139">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
- [<span data-ttu-id="81a74-140">stackalloc の注意事項</span><span class="sxs-lookup"><span data-stu-id="81a74-140">Dos and Don'ts of stackalloc</span></span>](https://vcsjones.dev/2020/02/24/stackalloc/)
