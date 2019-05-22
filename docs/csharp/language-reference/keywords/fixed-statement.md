---
title: fixed ステートメント - C# リファレンス
ms.custom: seodec18
ms.date: 05/10/2018
f1_keywords:
- fixed_CSharpKeyword
- fixed
helpviewer_keywords:
- fixed keyword [C#]
ms.openlocfilehash: a852f36c05075365ced8ec39457b15601ca3c3fb
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2019
ms.locfileid: "65877085"
---
# <a name="fixed-statement-c-reference"></a><span data-ttu-id="b07c1-102">fixed ステートメント (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="b07c1-102">fixed Statement (C# Reference)</span></span>

<span data-ttu-id="b07c1-103">`fixed` ステートメントは、移動可能な変数がガベージ コレクターにより再配置されることを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="b07c1-103">The `fixed` statement prevents the garbage collector from relocating a movable variable.</span></span> <span data-ttu-id="b07c1-104">`fixed` ステートメントは、[unsafe](unsafe.md) コンテキストでのみ許可されます。</span><span class="sxs-lookup"><span data-stu-id="b07c1-104">The `fixed` statement is only permitted in an [unsafe](unsafe.md) context.</span></span> <span data-ttu-id="b07c1-105">`fixed` キーワードは、[固定サイズ バッファー](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md)の作成にも使うことができます。</span><span class="sxs-lookup"><span data-stu-id="b07c1-105">You can also use the `fixed` keyword to create [fixed size buffers](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span></span>

<span data-ttu-id="b07c1-106">`fixed` ステートメントは、マネージド変数へのポインターを設定し、ステートメントの実行中にその変数を "固定" します。</span><span class="sxs-lookup"><span data-stu-id="b07c1-106">The `fixed` statement sets a pointer to a managed variable and "pins" that variable during the execution of the statement.</span></span> <span data-ttu-id="b07c1-107">移動可能なマネージド変数へのポインターは、`fixed` コンテキストでのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="b07c1-107">Pointers to movable managed variables are useful only in a `fixed` context.</span></span> <span data-ttu-id="b07c1-108">`fixed` コンテキストがない場合、ガベージ コレクションによって変数が予期せず再配置される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b07c1-108">Without a `fixed` context, garbage collection could relocate the variables unpredictably.</span></span> <span data-ttu-id="b07c1-109">C# コンパイラでは、`fixed` ステートメントでマネージド変数へのポインターを割り当てることだけができます。</span><span class="sxs-lookup"><span data-stu-id="b07c1-109">The C# compiler only lets you assign a pointer to a managed variable in a `fixed` statement.</span></span>

[!code-csharp[Accessing fixed memory](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#1)]

<span data-ttu-id="b07c1-110">配列、文字列、固定サイズ バッファー、または変数のアドレスを使って、ポインターを初期化できます。</span><span class="sxs-lookup"><span data-stu-id="b07c1-110">You can initialize a pointer by using an array, a string, a fixed-size buffer, or the address of a variable.</span></span> <span data-ttu-id="b07c1-111">次の例では、変数のアドレス、配列、および文字列の使い方を示します。</span><span class="sxs-lookup"><span data-stu-id="b07c1-111">The following example illustrates the use of variable addresses, arrays, and strings:</span></span>

[!code-csharp[Initializing fixed size buffers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#2)]

<span data-ttu-id="b07c1-112">C# 7.3 以降では、`fixed` ステートメントは、配列、文字列、固定サイズ バッファー、アンマネージド型変数以外の型でも動作します。</span><span class="sxs-lookup"><span data-stu-id="b07c1-112">Starting with C# 7.3, the `fixed` statement operates on additional types beyond arrays, strings, fixed-size buffers, or unmanaged variables.</span></span> <span data-ttu-id="b07c1-113">`GetPinnableReference` という名前のメソッドを実装する型はピン留めできます。</span><span class="sxs-lookup"><span data-stu-id="b07c1-113">Any type that implements a method named `GetPinnableReference` can be pinned.</span></span> <span data-ttu-id="b07c1-114">`GetPinnableReference` は `ref` 変数をアンマネージド型にして返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="b07c1-114">The `GetPinnableReference` must return a `ref` variable to an unmanaged type.</span></span> <span data-ttu-id="b07c1-115">詳しくは、「[ポインター型](../../programming-guide/unsafe-code-pointers/pointer-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b07c1-115">See the topic on [pointer types](../../programming-guide/unsafe-code-pointers/pointer-types.md) for more information.</span></span> <span data-ttu-id="b07c1-116">.NET Core 2.0 で導入された .NET 型 <xref:System.Span%601?displayProperty=nameWithType> と <xref:System.ReadOnlySpan%601?displayProperty=nameWithType> はこのパターンを活用し、ピン留めできます。</span><span class="sxs-lookup"><span data-stu-id="b07c1-116">The .NET types <xref:System.Span%601?displayProperty=nameWithType> and <xref:System.ReadOnlySpan%601?displayProperty=nameWithType> introduced in .NET Core 2.0 make use of this pattern and can be pinned.</span></span> <span data-ttu-id="b07c1-117">以下の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b07c1-117">This is shown in the following example:</span></span>

[!code-csharp[Accessing fixed memory](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#FixedSpan)]

<span data-ttu-id="b07c1-118">このパターンに参加する必要のある型を作成する場合は、パターンの実装の例について、「<xref:System.Span%601.GetPinnableReference?displayProperty=nameWithType>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b07c1-118">If you are creating types that should participate in this pattern, see <xref:System.Span%601.GetPinnableReference?displayProperty=nameWithType> for an example of implementing the pattern.</span></span>

<span data-ttu-id="b07c1-119">複数のポインターは、すべて同じ型の場合、1 つのステートメントで初期化できます。</span><span class="sxs-lookup"><span data-stu-id="b07c1-119">Multiple pointers can be initialized in one statement if they are all the same type:</span></span>

```csharp
fixed (byte* ps = srcarray, pd = dstarray) {...}
```

<span data-ttu-id="b07c1-120">異なる型のポインターを初期化するには、次の例で示すように、`fixed` ステートメントを入れ子にします。</span><span class="sxs-lookup"><span data-stu-id="b07c1-120">To initialize pointers of different types, simply nest `fixed` statements, as shown in the following example.</span></span>

[!code-csharp[Initializing multiple pointers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#3)]

<span data-ttu-id="b07c1-121">ステートメント内のコードの実行が済むと、固定された変数は固定を解除されて、ガベージ コレクションの対象になります。</span><span class="sxs-lookup"><span data-stu-id="b07c1-121">After the code in the statement is executed, any pinned variables are unpinned and subject to garbage collection.</span></span> <span data-ttu-id="b07c1-122">そのため、`fixed` ステートメントの外側ではこれらの変数を参照しないでください。</span><span class="sxs-lookup"><span data-stu-id="b07c1-122">Therefore, do not point to those variables outside the `fixed` statement.</span></span> <span data-ttu-id="b07c1-123">`fixed` ステートメントで宣言された変数は、そのステートメントにスコープされるので、この処理が簡単になります。</span><span class="sxs-lookup"><span data-stu-id="b07c1-123">The variables declared in the `fixed` statement are scoped to that statement, making this easier:</span></span>

```csharp
fixed (byte* ps = srcarray, pd = dstarray)
{
   ...
}
// ps and pd are no longer in scope here.
```

<span data-ttu-id="b07c1-124">`fixed` ステートメントで初期化されたポインターは読み取り専用変数です。</span><span class="sxs-lookup"><span data-stu-id="b07c1-124">Pointers initialized in `fixed` statements are readonly variables.</span></span> <span data-ttu-id="b07c1-125">ポインター値を変更するには、2 つ目のポインター変数を宣言し、それを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b07c1-125">If you want to modify the pointer value, you must declare a second pointer variable, and modify that.</span></span> <span data-ttu-id="b07c1-126">`fixed` ステートメントで宣言された変数は変更できません。</span><span class="sxs-lookup"><span data-stu-id="b07c1-126">The variable declared in the `fixed` statement cannot be modified:</span></span>

```csharp
fixed (byte* ps = srcarray, pd = dstarray)
{
    byte* pSourceCopy = ps;
    pSourceCopy++; // point to the next element.
    ps++; // invalid: cannot modify ps, as it is declared in the fixed statement.
}
```

<span data-ttu-id="b07c1-127">スタックにメモリを割り当てることができ、スタックはガベージ コレクションの対象にならないので、固定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b07c1-127">You can allocate memory on the stack, where it is not subject to garbage collection and therefore does not need to be pinned.</span></span> <span data-ttu-id="b07c1-128">詳しくは、「[stackalloc](stackalloc.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b07c1-128">For more information, see [stackalloc](stackalloc.md).</span></span>

[!code-csharp[Initializing multiple pointers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="b07c1-129">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="b07c1-129">C# Language Specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="b07c1-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="b07c1-130">See also</span></span>

- [<span data-ttu-id="b07c1-131">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="b07c1-131">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b07c1-132">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="b07c1-132">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b07c1-133">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="b07c1-133">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="b07c1-134">unsafe</span><span class="sxs-lookup"><span data-stu-id="b07c1-134">unsafe</span></span>](unsafe.md)
- [<span data-ttu-id="b07c1-135">固定サイズ バッファー</span><span class="sxs-lookup"><span data-stu-id="b07c1-135">Fixed Size Buffers</span></span>](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
