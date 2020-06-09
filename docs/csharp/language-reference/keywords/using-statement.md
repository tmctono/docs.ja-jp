---
title: using ステートメント - C# リファレンス
ms.date: 05/29/2020
helpviewer_keywords:
- using statement [C#]
ms.assetid: afc355e6-f0b9-4240-94dd-0d93f17d9fc3
ms.openlocfilehash: b889d2fcbdf854dbe8948744810f9b74e9f0dac2
ms.sourcegitcommit: 5280b2aef60a1ed99002dba44e4b9e7f6c830604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2020
ms.locfileid: "84307047"
---
# <a name="using-statement-c-reference"></a><span data-ttu-id="ccdad-102">using ステートメント (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="ccdad-102">using statement (C# Reference)</span></span>

<span data-ttu-id="ccdad-103"><xref:System.IDisposable> オブジェクトの正しい使用を保証する簡易構文を提供します。</span><span class="sxs-lookup"><span data-stu-id="ccdad-103">Provides a convenient syntax that ensures the correct use of <xref:System.IDisposable> objects.</span></span> <span data-ttu-id="ccdad-104">C# 8.0 以降は、`using` ステートメントによって <xref:System.IAsyncDisposable> オブジェクトが適切に使用されるようになります。</span><span class="sxs-lookup"><span data-stu-id="ccdad-104">Beginning in C# 8.0, the `using` statement ensures the correct use of <xref:System.IAsyncDisposable> objects.</span></span>

## <a name="example"></a><span data-ttu-id="ccdad-105">例</span><span class="sxs-lookup"><span data-stu-id="ccdad-105">Example</span></span>

<span data-ttu-id="ccdad-106">`using` ステートメントを使用する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ccdad-106">The following example shows how to use the `using` statement.</span></span>

:::code language="csharp" source="snippets/usings.cs" id="SnippetFirstExample":::

<span data-ttu-id="ccdad-107">C# 8.0 以降では、中かっこを必要としない `using` ステートメントに次の代替構文を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ccdad-107">Beginning with C# 8.0, you can use the following alternative syntax for the `using` statement that doesn't require braces:</span></span>

:::code language="csharp" source="snippets/usings.cs" id="SnippetModernUsing":::

## <a name="remarks"></a><span data-ttu-id="ccdad-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="ccdad-108">Remarks</span></span>

<span data-ttu-id="ccdad-109"><xref:System.IO.File> と <xref:System.Drawing.Font> は、アンマネージド リソース (この場合はファイル ハンドルとデバイス コンテキスト) にアクセスするマネージド型の例です。</span><span class="sxs-lookup"><span data-stu-id="ccdad-109"><xref:System.IO.File> and <xref:System.Drawing.Font> are examples of managed types that access unmanaged resources (in this case file handles and device contexts).</span></span> <span data-ttu-id="ccdad-110">アンマネージ リソースや、それをカプセル化するクラス ライブラリ型は他にもたくさんあります。</span><span class="sxs-lookup"><span data-stu-id="ccdad-110">There are many other kinds of unmanaged resources and class library types that encapsulate them.</span></span> <span data-ttu-id="ccdad-111">このようなすべての型は、<xref:System.IDisposable> インターフェイスまたは <xref:System.IAsyncDisposable> インターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccdad-111">All such types must implement the <xref:System.IDisposable> interface, or the <xref:System.IAsyncDisposable> interface.</span></span>

<span data-ttu-id="ccdad-112">`IDisposable` オブジェクトの有効期間が 1 つのメソッドに限定されているとき、それを `using` ステートメントで宣言し、インスタンス化してください。</span><span class="sxs-lookup"><span data-stu-id="ccdad-112">When the lifetime of an `IDisposable` object is limited to a single method, you should declare and instantiate it in the `using` statement.</span></span> <span data-ttu-id="ccdad-113">`using` ステートメントは、オブジェクトで正しく <xref:System.IDisposable.Dispose%2A> メソッドを呼び出します。(前述のようにこのステートメントを使用する場合) <xref:System.IDisposable.Dispose%2A> が呼び出されるとすぐに、オブジェクト自体がスコープの外側に出されます。</span><span class="sxs-lookup"><span data-stu-id="ccdad-113">The `using` statement calls the <xref:System.IDisposable.Dispose%2A> method on the object in the correct way, and (when you use it as shown earlier) it also causes the object itself to go out of scope as soon as <xref:System.IDisposable.Dispose%2A> is called.</span></span> <span data-ttu-id="ccdad-114">オブジェクトは、`using` ブロック内では読み取り専用です。変更したり再割り当てしたりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ccdad-114">Within the `using` block, the object is read-only and can't be modified or reassigned.</span></span> <span data-ttu-id="ccdad-115">オブジェクトに `IDisposable` ではなく `IAsyncDisposable` が実装されている場合、`using` ステートメントからは <xref:System.IAsyncDisposable.DisposeAsync%2A> が呼び出され、返される <xref:System.Threading.Tasks.ValueTask> の `awaits` を行います。</span><span class="sxs-lookup"><span data-stu-id="ccdad-115">If the object implements `IAsyncDisposable` instead of `IDisposable`, the `using` statement calls the <xref:System.IAsyncDisposable.DisposeAsync%2A> and `awaits` the returned <xref:System.Threading.Tasks.ValueTask>.</span></span> <span data-ttu-id="ccdad-116"><xref:System.IAsyncDisposable> の詳細については、「[DisposeAsync メソッドの実装](../../../standard/garbage-collection/implementing-disposeasync.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ccdad-116">For more information on <xref:System.IAsyncDisposable>, see [Implement a DisposeAsync method](../../../standard/garbage-collection/implementing-disposeasync.md).</span></span>

<span data-ttu-id="ccdad-117">`using` ステートメントにより、`using` ブロック内で例外が発生した場合でも必ず <xref:System.IDisposable.Dispose%2A> (または <xref:System.IAsyncDisposable.DisposeAsync%2A>) が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="ccdad-117">The `using` statement ensures that <xref:System.IDisposable.Dispose%2A> (or <xref:System.IAsyncDisposable.DisposeAsync%2A>) is called even if an exception occurs within the `using` block.</span></span> <span data-ttu-id="ccdad-118">オブジェクトを `try` ブロックに配置し、`finally` ブロック内で <xref:System.IDisposable.Dispose%2A> (または <xref:System.IAsyncDisposable.DisposeAsync%2A>) を呼び出しても、同じ結果が得られます。実際には、コンパイラによって `using` ステートメントがこのように変換されます。</span><span class="sxs-lookup"><span data-stu-id="ccdad-118">You can achieve the same result by putting the object inside a `try` block and then calling <xref:System.IDisposable.Dispose%2A> (or <xref:System.IAsyncDisposable.DisposeAsync%2A>) in a `finally` block; in fact, this is how the `using` statement is translated by the compiler.</span></span> <span data-ttu-id="ccdad-119">前のコード例は、コンパイル時に次のコードに展開されます (オブジェクトのスコープ制限を定義する中かっこが加えられていることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="ccdad-119">The code example earlier expands to the following code at compile time (note the extra curly braces to create the limited scope for the object):</span></span>

:::code language="csharp" source="snippets/usings.cs" id="SnippetTryFinallyExample":::

<span data-ttu-id="ccdad-120">新しい `using` ステートメントの構文は似たコードに変換されます。</span><span class="sxs-lookup"><span data-stu-id="ccdad-120">The newer `using` statement syntax translates to similar code.</span></span> <span data-ttu-id="ccdad-121">変数が宣言されている場所で `try` ブロックが開きます。</span><span class="sxs-lookup"><span data-stu-id="ccdad-121">The `try` block opens where the variable is declared.</span></span> <span data-ttu-id="ccdad-122">`finally` ブロックは、囲んでいるブロックの終わり、通常はメソッドの最後に追加されます。</span><span class="sxs-lookup"><span data-stu-id="ccdad-122">The `finally` block is added at the close of the enclosing block, typically at the end of a method.</span></span>

<span data-ttu-id="ccdad-123">`try`-`finally` ステートメントの詳細については、「[try-finally](try-finally.md)」の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ccdad-123">For more information about the `try`-`finally` statement, see the [try-finally](try-finally.md) article.</span></span>

<span data-ttu-id="ccdad-124">次の例のように、1 つの `using` ステートメントで型の複数のインスタンスを宣言できます。</span><span class="sxs-lookup"><span data-stu-id="ccdad-124">Multiple instances of a type can be declared in a single `using` statement, as shown in the following example.</span></span> <span data-ttu-id="ccdad-125">1 つのステートメントで複数の変数を宣言する場合、暗黙的に型指定された変数 (`var`) を使用できないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ccdad-125">Notice that you can't use implicitly typed variables (`var`) when you declare multiple variables in a single statement:</span></span>

:::code language="csharp" source="snippets/usings.cs" id="SnippetDeclareMultipleVariables":::

<span data-ttu-id="ccdad-126">次の例に示すように、C# 8 で導入された新しい構文を使用して、同じ型の複数の宣言を組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="ccdad-126">You can combine multiple declarations of the same type using the new syntax introduced with C# 8 as well, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/usings.cs" id="SnippetModernMultipleVariables":::

<span data-ttu-id="ccdad-127">リソース オブジェクトをインスタンス化してから、変数を `using` ステートメントに渡すことはできますが、これはベスト プラクティスではありません。</span><span class="sxs-lookup"><span data-stu-id="ccdad-127">You can instantiate the resource object and then pass the variable to the `using` statement, but this isn't a best practice.</span></span> <span data-ttu-id="ccdad-128">この場合、アンマネージド リソースへのアクセスがなくなっている可能性が高いのにもかかわらず、制御が `using` ブロックを離れた後もオブジェクトはスコープ内に残ります。</span><span class="sxs-lookup"><span data-stu-id="ccdad-128">In this case, after control leaves the `using` block, the object remains in scope but probably has no access to its unmanaged resources.</span></span> <span data-ttu-id="ccdad-129">つまり、完全に初期化されることはなくなります。</span><span class="sxs-lookup"><span data-stu-id="ccdad-129">In other words, it's not fully initialized anymore.</span></span> <span data-ttu-id="ccdad-130">`using` ブロックの外側でオブジェクトを使用しようとすると、例外がスローされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ccdad-130">If you try to use the object outside the `using` block, you risk causing an exception to be thrown.</span></span> <span data-ttu-id="ccdad-131">このため、オブジェクトを `using` ステートメントでインスタンス化して、そのスコープを `using` ブロックに制限することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ccdad-131">For this reason, it's better to instantiate the object in the `using` statement and limit its scope to the `using` block.</span></span>

:::code language="csharp" source="snippets/usings.cs" id="SnippetDeclareBeforeUsing":::

<span data-ttu-id="ccdad-132">`IDisposable` オブジェクトの破棄に関する詳細については、「[IDisposable を実装するオブジェクトの使用](../../../standard/garbage-collection/using-objects.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ccdad-132">For more information about disposing of `IDisposable` objects, see [Using objects that implement IDisposable](../../../standard/garbage-collection/using-objects.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="ccdad-133">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="ccdad-133">C# language specification</span></span>

<span data-ttu-id="ccdad-134">詳細については、[C# 言語仕様](/dotnet/csharp/language-reference/language-specification/introduction)に関するページの [using ステートメント](~/_csharplang/spec/statements.md#the-using-statement)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ccdad-134">For more information, see [The using statement](~/_csharplang/spec/statements.md#the-using-statement) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="ccdad-135">言語仕様は、C# の構文と使用法に関する信頼性のある情報源です。</span><span class="sxs-lookup"><span data-stu-id="ccdad-135">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="ccdad-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="ccdad-136">See also</span></span>

- [<span data-ttu-id="ccdad-137">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="ccdad-137">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="ccdad-138">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="ccdad-138">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="ccdad-139">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="ccdad-139">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="ccdad-140">using ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="ccdad-140">using Directive</span></span>](using-directive.md)
- [<span data-ttu-id="ccdad-141">ガベージ コレクション</span><span class="sxs-lookup"><span data-stu-id="ccdad-141">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="ccdad-142">IDisposable を実装するオブジェクトの使用</span><span class="sxs-lookup"><span data-stu-id="ccdad-142">Using objects that implement IDisposable</span></span>](../../../standard/garbage-collection/using-objects.md)
- [<span data-ttu-id="ccdad-143">IDisposable インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ccdad-143">IDisposable interface</span></span>](xref:System.IDisposable)
- [<span data-ttu-id="ccdad-144">C# 8.0 の using ステートメント</span><span class="sxs-lookup"><span data-stu-id="ccdad-144">using statement in C# 8.0</span></span>](~/_csharplang/proposals/csharp-8.0/using.md)
