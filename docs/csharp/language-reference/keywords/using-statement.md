---
title: using ステートメント - C# リファレンス
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- using statement [C#]
ms.assetid: afc355e6-f0b9-4240-94dd-0d93f17d9fc3
ms.openlocfilehash: e1a1a960fa69be593ea01cab51be576b0055fd5e
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632896"
---
# <a name="using-statement-c-reference"></a><span data-ttu-id="1be4d-102">using ステートメント (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="1be4d-102">using statement (C# Reference)</span></span>

<span data-ttu-id="1be4d-103"><xref:System.IDisposable> オブジェクトの正しい使用を保証する簡易構文を提供します。</span><span class="sxs-lookup"><span data-stu-id="1be4d-103">Provides a convenient syntax that ensures the correct use of <xref:System.IDisposable> objects.</span></span>

## <a name="example"></a><span data-ttu-id="1be4d-104">例</span><span class="sxs-lookup"><span data-stu-id="1be4d-104">Example</span></span>

<span data-ttu-id="1be4d-105">`using` ステートメントを使用する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="1be4d-105">The following example shows how to use the `using` statement.</span></span>

[!code-csharp[csrefKeywordsNamespace#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#4)]

## <a name="remarks"></a><span data-ttu-id="1be4d-106">解説</span><span class="sxs-lookup"><span data-stu-id="1be4d-106">Remarks</span></span>

<span data-ttu-id="1be4d-107"><xref:System.IO.File> と <xref:System.Drawing.Font> は、アンマネージド リソース (この場合はファイル ハンドルとデバイス コンテキスト) にアクセスするマネージド型の例です。</span><span class="sxs-lookup"><span data-stu-id="1be4d-107"><xref:System.IO.File> and <xref:System.Drawing.Font> are examples of managed types that access unmanaged resources (in this case file handles and device contexts).</span></span> <span data-ttu-id="1be4d-108">アンマネージ リソースや、それをカプセル化するクラス ライブラリ型は他にもたくさんあります。</span><span class="sxs-lookup"><span data-stu-id="1be4d-108">There are many other kinds of unmanaged resources and class library types that encapsulate them.</span></span> <span data-ttu-id="1be4d-109">このような型はすべて、<xref:System.IDisposable> インターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1be4d-109">All such types must implement the <xref:System.IDisposable> interface.</span></span>

<span data-ttu-id="1be4d-110">`IDisposable` オブジェクトの有効期間が 1 つのメソッドに限定されているとき、それを `using` ステートメントで宣言し、インスタンス化してください。</span><span class="sxs-lookup"><span data-stu-id="1be4d-110">When the lifetime of an `IDisposable` object is limited to a single method, you should declare and instantiate it in the `using` statement.</span></span> <span data-ttu-id="1be4d-111">`using` ステートメントは、オブジェクトで正しく <xref:System.IDisposable.Dispose%2A> メソッドを呼び出します。(前述のようにこのステートメントを使用する場合) <xref:System.IDisposable.Dispose%2A> が呼び出されるとすぐに、オブジェクト自体がスコープの外側に出されます。</span><span class="sxs-lookup"><span data-stu-id="1be4d-111">The `using` statement calls the <xref:System.IDisposable.Dispose%2A> method on the object in the correct way, and (when you use it as shown earlier) it also causes the object itself to go out of scope as soon as <xref:System.IDisposable.Dispose%2A> is called.</span></span> <span data-ttu-id="1be4d-112">オブジェクトは、`using` ブロック内では読み取り専用です。変更したり再割り当てしたりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="1be4d-112">Within the `using` block, the object is read-only and cannot be modified or reassigned.</span></span>

<span data-ttu-id="1be4d-113">`using` ステートメントにより、`using` ブロックで例外が発生した場合でも必ず <xref:System.IDisposable.Dispose%2A> が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="1be4d-113">The `using` statement ensures that <xref:System.IDisposable.Dispose%2A> is called even if an exception occurs within the `using` block.</span></span> <span data-ttu-id="1be4d-114">オブジェクトを `try` ブロックに配置し、`finally` ブロックで <xref:System.IDisposable.Dispose%2A> を呼び出しても、同じ結果が得られます。実際には、コンパイラは `using` ステートメントをこのように変換します。</span><span class="sxs-lookup"><span data-stu-id="1be4d-114">You can achieve the same result by putting the object inside a `try` block and then calling <xref:System.IDisposable.Dispose%2A> in a `finally` block; in fact, this is how the `using` statement is translated by the compiler.</span></span> <span data-ttu-id="1be4d-115">前のコード例は、コンパイル時に次のコードに展開されます (オブジェクトのスコープ制限を定義する中かっこが加えられていることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="1be4d-115">The code example earlier expands to the following code at compile time (note the extra curly braces to create the limited scope for the object):</span></span>

[!code-csharp[csrefKeywordsNamespace#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#5)]

<span data-ttu-id="1be4d-116">`try`-`finally` ステートメントの詳細については、「[try-finally](try-finally.md)」のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1be4d-116">For more information about the `try`-`finally` statement, see the [try-finally](try-finally.md) topic.</span></span>

<span data-ttu-id="1be4d-117">次の例のように、`using` ステートメントでは型の複数のインスタンスを宣言できます。</span><span class="sxs-lookup"><span data-stu-id="1be4d-117">Multiple instances of a type can be declared in the `using` statement, as shown in the following example:</span></span>

[!code-csharp[csrefKeywordsNamespace#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#6)]

<span data-ttu-id="1be4d-118">リソース オブジェクトをインスタンス化してから、変数を `using` ステートメントに渡すことはできますが、これはベスト プラクティスではありません。</span><span class="sxs-lookup"><span data-stu-id="1be4d-118">You can instantiate the resource object and then pass the variable to the `using` statement, but this is not a best practice.</span></span> <span data-ttu-id="1be4d-119">この場合、アンマネージド リソースへのアクセスがなくなっている可能性が高いのにもかかわらず、制御が `using` ブロックを離れた後もオブジェクトはスコープ内に残ります。</span><span class="sxs-lookup"><span data-stu-id="1be4d-119">In this case, after control leaves the `using` block, the object remains in scope but probably has no access to its unmanaged resources.</span></span> <span data-ttu-id="1be4d-120">つまり、完全に初期化されることはなくなります。</span><span class="sxs-lookup"><span data-stu-id="1be4d-120">In other words, it's not fully initialized anymore.</span></span> <span data-ttu-id="1be4d-121">`using` ブロックの外側でオブジェクトを使用しようとすると、例外がスローされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1be4d-121">If you try to use the object outside the `using` block, you risk causing an exception to be thrown.</span></span> <span data-ttu-id="1be4d-122">このため、通常は、オブジェクトを `using` ステートメントでインスタンス化して、そのスコープを `using` ブロックに制限することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1be4d-122">For this reason, it's generally better to instantiate the object in the `using` statement and limit its scope to the `using` block.</span></span>

[!code-csharp[csrefKeywordsNamespace#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#7)]

<span data-ttu-id="1be4d-123">`IDisposable` オブジェクトの破棄に関する詳細については、「[IDisposable を実装するオブジェクトの使用](../../../standard/garbage-collection/using-objects.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1be4d-123">For more information about disposing of `IDisposable` objects, see [Using objects that implement IDisposable](../../../standard/garbage-collection/using-objects.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="1be4d-124">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="1be4d-124">C# language specification</span></span>

<span data-ttu-id="1be4d-125">詳細については、[C# 言語仕様](../language-specification/index.md)に関するページの [using ステートメント](~/_csharplang/spec/statements.md#the-using-statement)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1be4d-125">For more information, see [The using statement](~/_csharplang/spec/statements.md#the-using-statement) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="1be4d-126">言語仕様は、C# の構文と使用法に関する信頼性のある情報源です。</span><span class="sxs-lookup"><span data-stu-id="1be4d-126">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="1be4d-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="1be4d-127">See also</span></span>

- [<span data-ttu-id="1be4d-128">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="1be4d-128">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="1be4d-129">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="1be4d-129">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="1be4d-130">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="1be4d-130">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="1be4d-131">using ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="1be4d-131">using Directive</span></span>](using-directive.md)
- [<span data-ttu-id="1be4d-132">ガベージ コレクション</span><span class="sxs-lookup"><span data-stu-id="1be4d-132">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="1be4d-133">IDisposable を実装するオブジェクトの使用</span><span class="sxs-lookup"><span data-stu-id="1be4d-133">Using objects that implement IDisposable</span></span>](../../../standard/garbage-collection/using-objects.md)
- [<span data-ttu-id="1be4d-134">IDisposable インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1be4d-134">IDisposable interface</span></span>](xref:System.IDisposable)
