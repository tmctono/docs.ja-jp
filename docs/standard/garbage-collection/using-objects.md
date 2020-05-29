---
title: IDisposable を実装するオブジェクトの使用
ms.date: 05/13/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dispose method
- try/finally block
- garbage collection, encapsulating resources
ms.assetid: 81b2cdb5-c91a-4a31-9c83-eadc52da5cf0
ms.openlocfilehash: d0d55a9253fee1ffcfd5c10714a1118883f6c4ce
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396972"
---
# <a name="using-objects-that-implement-idisposable"></a><span data-ttu-id="c9076-102">IDisposable を実装するオブジェクトの使用</span><span class="sxs-lookup"><span data-stu-id="c9076-102">Using objects that implement IDisposable</span></span>

<span data-ttu-id="c9076-103">共通言語ランタイムのガベージ コレクターは、アンマネージド オブジェクトによって使用されているメモリを解放しますが、アンマネージ リソースを使用する型は、これらのアンマネージ リソースで必要なリソースが再利用されるように <xref:System.IDisposable> インターフェイスを実装しています。</span><span class="sxs-lookup"><span data-stu-id="c9076-103">The common language runtime's garbage collector reclaims the memory used by managed objects, but types that use unmanaged resources implement the <xref:System.IDisposable> interface to allow the resources needed by these unmanaged resources to be reclaimed.</span></span> <span data-ttu-id="c9076-104"><xref:System.IDisposable> を実装するオブジェクトを使い終わったら、オブジェクトの <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> の実装を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9076-104">When you finish using an object that implements <xref:System.IDisposable>, you should call the object's <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="c9076-105">2 つの方法のいずれかでこれを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c9076-105">You can do this in one of two ways:</span></span>

- <span data-ttu-id="c9076-106">C# の `using` ステートメント (Visual Basic の `Using`)。</span><span class="sxs-lookup"><span data-stu-id="c9076-106">With the C# `using` statement (`Using` in Visual Basic).</span></span>
- <span data-ttu-id="c9076-107">`try/finally` ブロックを実装し、`finally` で <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="c9076-107">By implementing a `try/finally` block, and calling the <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> in the `finally`.</span></span>

## <a name="the-using-statement"></a><span data-ttu-id="c9076-108">using ステートメント</span><span class="sxs-lookup"><span data-stu-id="c9076-108">The using statement</span></span>

<span data-ttu-id="c9076-109">C# の [`using` ステートメント](../../csharp/language-reference/keywords/using-statement.md)および Visual Basic の [`Using` ステートメント](../../visual-basic/language-reference/statements/using-statement.md)を使用すると、オブジェクトのクリーンアップ時に記述する必要のあるコードが簡略化されます。</span><span class="sxs-lookup"><span data-stu-id="c9076-109">The [`using` statement](../../csharp/language-reference/keywords/using-statement.md) in C# and the [`Using` statement](../../visual-basic/language-reference/statements/using-statement.md) in Visual Basic simplify the code that you must write to cleanup an object.</span></span> <span data-ttu-id="c9076-110">`using` ステートメントは、1 つ以上のリソースを取得し、指定されたステートメントを実行し、オブジェクトを自動的に破棄します。</span><span class="sxs-lookup"><span data-stu-id="c9076-110">The `using` statement obtains one or more resources, executes the statements that you specify, and automatically disposes of the object.</span></span> <span data-ttu-id="c9076-111">ただし、`using` ステートメントは、オブジェクトが構築されるメソッドのスコープ内で使用されるオブジェクトに対してのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="c9076-111">However, the `using` statement is useful only for objects that are used within the scope of the method in which they are constructed.</span></span>

<span data-ttu-id="c9076-112">次の例では、`using` ステートメントを使用して <xref:System.IO.StreamReader?displayProperty=nameWithType> オブジェクトを作成し解放します。</span><span class="sxs-lookup"><span data-stu-id="c9076-112">The following example uses the `using` statement to create and release a <xref:System.IO.StreamReader?displayProperty=nameWithType> object.</span></span>

[!code-csharp[Conceptual.Disposable#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using1.cs#1)]
[!code-vb[Conceptual.Disposable#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using1.vb#1)]

<span data-ttu-id="c9076-113"><xref:System.IO.StreamReader> クラスは <xref:System.IDisposable> インターフェイスを実装し、これはアンマネージ リソースを使用することを示していますが、例では <xref:System.IO.StreamReader.Dispose%2A?displayProperty=nameWithType> メソッドを明示的に呼び出していません。</span><span class="sxs-lookup"><span data-stu-id="c9076-113">Although the <xref:System.IO.StreamReader> class implements the <xref:System.IDisposable> interface, which indicates that it uses an unmanaged resource, the example doesn't explicitly call the <xref:System.IO.StreamReader.Dispose%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="c9076-114">C# または Visual Basic コンパイラが `using` ステートメントを見つけると、明示的に `try/finally` ブロックを含む次のコードと同等の中間言語 (IL) を生成します。</span><span class="sxs-lookup"><span data-stu-id="c9076-114">When the C# or Visual Basic compiler encounters the `using` statement, it emits intermediate language (IL) that is equivalent to the following code that explicitly contains a `try/finally` block.</span></span>

[!code-csharp[Conceptual.Disposable#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using3.cs#3)]
[!code-vb[Conceptual.Disposable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using3.vb#3)]

<span data-ttu-id="c9076-115">また、C# の `using` ステートメントでは、単一のステートメントで複数のリソースを取得できます。そのようなステートメントは、内部的には複数の `using` ステートメントを入れ子にした場合と同等です。</span><span class="sxs-lookup"><span data-stu-id="c9076-115">The C# `using` statement also allows you to acquire multiple resources in a single statement, which is internally equivalent to nested `using` statements.</span></span> <span data-ttu-id="c9076-116">次の例では、2 つの異なるファイルの内容を読み取るために、<xref:System.IO.StreamReader> の 2 つのオブジェクトをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="c9076-116">The following example instantiates two <xref:System.IO.StreamReader> objects to read the contents of two different files.</span></span>

[!code-csharp[Conceptual.Disposable#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using4.cs#4)]

## <a name="tryfinally-block"></a><span data-ttu-id="c9076-117">Try/Finally ブロック</span><span class="sxs-lookup"><span data-stu-id="c9076-117">Try/finally block</span></span>

<span data-ttu-id="c9076-118">`using` ステートメントで `try/finally` ブロックをラップする代わりに、`try/finally` ブロックを直接実装することもできます。</span><span class="sxs-lookup"><span data-stu-id="c9076-118">Instead of wrapping a `try/finally` block in a `using` statement, you may choose to implement the `try/finally` block directly.</span></span> <span data-ttu-id="c9076-119">これは、個人のコーディング スタイルであることも、次のいずれかの理由からそうすることもあります。</span><span class="sxs-lookup"><span data-stu-id="c9076-119">It may be your personal coding style, or you might want to do this for one of the following reasons:</span></span>

- <span data-ttu-id="c9076-120">`catch` ブロックでスローされた例外を処理する `try` ブロックを含めるため。</span><span class="sxs-lookup"><span data-stu-id="c9076-120">To include a `catch` block to handle exceptions thrown in the `try` block.</span></span> <span data-ttu-id="c9076-121">それ以外の場合、`using` ステートメント内でスローされた例外は処理されません。</span><span class="sxs-lookup"><span data-stu-id="c9076-121">Otherwise, any exceptions thrown within the `using` statement are unhandled.</span></span>

- <span data-ttu-id="c9076-122">宣言されたブロックに対してスコープがローカルでない <xref:System.IDisposable> を実装するオブジェクトをインスタンス化するため。</span><span class="sxs-lookup"><span data-stu-id="c9076-122">To instantiate an object that implements <xref:System.IDisposable> whose scope is not local to the block within which it is declared.</span></span>

<span data-ttu-id="c9076-123">次の例は前の例に似ていますが、`try/catch/finally` ブロックを使用して、<xref:System.IO.StreamReader> オブジェクトのインスタンス化、使用、破棄を実行し、<xref:System.IO.StreamReader> コンストラクターと <xref:System.IO.StreamReader.ReadToEnd%2A> メソッドによってスローされた例外を処理しています。</span><span class="sxs-lookup"><span data-stu-id="c9076-123">The following example is similar to the previous example, except that it uses a `try/catch/finally` block to instantiate, use, and dispose of a <xref:System.IO.StreamReader> object, and to handle any exceptions thrown by the <xref:System.IO.StreamReader> constructor and its <xref:System.IO.StreamReader.ReadToEnd%2A> method.</span></span> <span data-ttu-id="c9076-124">`finally` メソッドを呼び出す前に <xref:System.IDisposable> を実装するオブジェクトが `null` でないことを <xref:System.IDisposable.Dispose%2A> ブロックのコードがチェックします。</span><span class="sxs-lookup"><span data-stu-id="c9076-124">The code in the `finally` block checks that the object that implements <xref:System.IDisposable> isn't `null` before it calls the <xref:System.IDisposable.Dispose%2A> method.</span></span> <span data-ttu-id="c9076-125">これを行わない場合、実行時に <xref:System.NullReferenceException> 例外が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c9076-125">Failure to do this can result in a <xref:System.NullReferenceException> exception at run time.</span></span>

[!code-csharp[Conceptual.Disposable#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using5.cs#6)]
[!code-vb[Conceptual.Disposable#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using5.vb#6)]

<span data-ttu-id="c9076-126">この基本パターンを利用できるのは、プログラミング言語で `using` ステートメントがサポートされていないが、<xref:System.IDisposable.Dispose%2A> メソッドを直接呼び出すことはできるため、`try/finally` ブロックの実装を選択した場合、または実装する必要がある場合です。</span><span class="sxs-lookup"><span data-stu-id="c9076-126">You can follow this basic pattern if you choose to implement or must implement a `try/finally` block, because your programming language doesn't support a `using` statement but does allow direct calls to the <xref:System.IDisposable.Dispose%2A> method.</span></span>

## <a name="idisposable-instance-members"></a><span data-ttu-id="c9076-127">IDisposable インスタンス メンバー</span><span class="sxs-lookup"><span data-stu-id="c9076-127">IDisposable instance members</span></span>

<span data-ttu-id="c9076-128">クラスがインスタンス メンバーとして <xref:System.IDisposable> の実装 (フィールドまたはプロパティ) を保持している場合、クラスも <xref:System.IDisposable> を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9076-128">If a class holds an <xref:System.IDisposable> implementation as an instance member, either a field or a property, the class should also implement <xref:System.IDisposable>.</span></span> <span data-ttu-id="c9076-129">詳細については、[カスケード破棄の実装に関する記事](implementing-dispose.md#cascade-dispose-calls)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9076-129">For more information, see [implement a cascade dispose](implementing-dispose.md#cascade-dispose-calls).</span></span>

## <a name="see-also"></a><span data-ttu-id="c9076-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="c9076-130">See also</span></span>

- [<span data-ttu-id="c9076-131">アンマネージ リソースのクリーンアップ</span><span class="sxs-lookup"><span data-stu-id="c9076-131">Cleaning up unmanaged resources</span></span>](../../../docs/standard/garbage-collection/unmanaged.md)
- [<span data-ttu-id="c9076-132">using ステートメント (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="c9076-132">using Statement (C# Reference)</span></span>](../../csharp/language-reference/keywords/using-statement.md)
- [<span data-ttu-id="c9076-133">Using ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c9076-133">Using Statement (Visual Basic)</span></span>](../../visual-basic/language-reference/statements/using-statement.md)
