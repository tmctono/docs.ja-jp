---
title: リソースの管理:Use キーワード
description: については、F#キーワード 'use' と 'using' の関数は、初期化とリソースの解放を制御できます。
ms.date: 05/16/2016
ms.openlocfilehash: 3389f84713ec7cf5459dd0132249970f0e2ef3e0
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641704"
---
# <a name="resource-management-the-use-keyword"></a><span data-ttu-id="a5e43-103">リソースの管理:Use キーワード</span><span class="sxs-lookup"><span data-stu-id="a5e43-103">Resource Management: The use Keyword</span></span>

<span data-ttu-id="a5e43-104">このトピックで説明、キーワード`use`と`using`関数で、初期化とリソースの解放を制御できます。</span><span class="sxs-lookup"><span data-stu-id="a5e43-104">This topic describes the keyword `use` and the `using` function, which can control the initialization and release of resources.</span></span>

## <a name="resources"></a><span data-ttu-id="a5e43-105">リソース</span><span class="sxs-lookup"><span data-stu-id="a5e43-105">Resources</span></span>

<span data-ttu-id="a5e43-106">用語*リソース*は、複数の方法で使用されます。</span><span class="sxs-lookup"><span data-stu-id="a5e43-106">The term *resource* is used in more than one way.</span></span> <span data-ttu-id="a5e43-107">はい、リソースが文字列、グラフィックス、like などが、このコンテキストで、アプリケーションが使用するデータを指定できます*リソース*グラフィックス デバイス コンテキスト、ファイル ハンドル、ネットワークなどのソフトウェアやオペレーティング システムのリソースへの参照データベースの接続、待機ハンドルなどの同時実行オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a5e43-107">Yes, resources can be data that an application uses, such as strings, graphics, and the like, but in this context, *resources* refers to software or operating system resources, such as graphics device contexts, file handles, network and database connections, concurrency objects such as wait handles, and so on.</span></span> <span data-ttu-id="a5e43-108">アプリケーションがこれらのリソースの使用には、オペレーティング システムまたは別のアプリケーションに提供するようにプールに、リソースの今後のリリースを続けて、その他のリソース プロバイダーからリソースの取得が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a5e43-108">The use of these resources by applications involves the acquisition of the resource from the operating system or other resource provider, followed by the later release of the resource to the pool so that it can be provided to another application.</span></span> <span data-ttu-id="a5e43-109">アプリケーションが共通のプールに戻すリソースを解放しないと、問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="a5e43-109">Problems occur when applications do not release resources back to the common pool.</span></span>

## <a name="managing-resources"></a><span data-ttu-id="a5e43-110">リソースの管理</span><span class="sxs-lookup"><span data-stu-id="a5e43-110">Managing Resources</span></span>

<span data-ttu-id="a5e43-111">をアプリケーション内のリソースを効率的に責任を持って管理するには、を予測可能な方法で迅速にリソースを解放する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5e43-111">To efficiently and responsibly manage resources in an application, you must release resources promptly and in a predictable manner.</span></span> <span data-ttu-id="a5e43-112">.NET Framework では、このことで実行できます。、`System.IDisposable`インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="a5e43-112">The .NET Framework helps you do this by providing the `System.IDisposable` interface.</span></span> <span data-ttu-id="a5e43-113">実装する型`System.IDisposable`が、`System.IDisposable.Dispose`メソッドで、誤ってリソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="a5e43-113">A type that implements `System.IDisposable` has the `System.IDisposable.Dispose` method, which correctly frees resources.</span></span> <span data-ttu-id="a5e43-114">適切に記述されたアプリケーションを保証する`System.IDisposable.Dispose`限られたリソースを保持する任意のオブジェクトが不要になったときに迅速に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="a5e43-114">Well-written applications guarantee that `System.IDisposable.Dispose` is called promptly when any object that holds a limited resource is no longer needed.</span></span> <span data-ttu-id="a5e43-115">さいわい、ほとんどの .NET 言語が、簡単に確認するサポートを提供し、F# には例外はありません。</span><span class="sxs-lookup"><span data-stu-id="a5e43-115">Fortunately, most .NET languages provide support to make this easier, and F# is no exception.</span></span> <span data-ttu-id="a5e43-116">Dispose パターンをサポートする 2 つの便利な言語構造がある:`use`バインドと`using`関数。</span><span class="sxs-lookup"><span data-stu-id="a5e43-116">There are two useful language constructs that support the dispose pattern: the `use` binding and the `using` function.</span></span>

## <a name="use-binding"></a><span data-ttu-id="a5e43-117">バインディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="a5e43-117">use Binding</span></span>

<span data-ttu-id="a5e43-118">`use`キーワードには、フォームのような`let`バインド。</span><span class="sxs-lookup"><span data-stu-id="a5e43-118">The `use` keyword has a form that resembles that of the `let` binding:</span></span>

<span data-ttu-id="a5e43-119">使用して、*値* = *式*</span><span class="sxs-lookup"><span data-stu-id="a5e43-119">use *value* = *expression*</span></span>

<span data-ttu-id="a5e43-120">同じ機能を提供します、`let`バインドしますが、への呼び出しを追加します`Dispose`値がスコープ外になる値。</span><span class="sxs-lookup"><span data-stu-id="a5e43-120">It provides the same functionality as a `let` binding but adds a call to `Dispose` on the value when the value goes out of scope.</span></span> <span data-ttu-id="a5e43-121">場合に、値は、コンパイラは、値の null チェックを挿入します。 注`null`、への呼び出し`Dispose`は行われません。</span><span class="sxs-lookup"><span data-stu-id="a5e43-121">Note that the compiler inserts a null check on the value, so that if the value is `null`, the call to `Dispose` is not attempted.</span></span>

<span data-ttu-id="a5e43-122">次の例を使用してファイルを自動的に閉じる方法を示しています、`use`キーワード。</span><span class="sxs-lookup"><span data-stu-id="a5e43-122">The following example shows how to close a file automatically by using the `use` keyword.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6301.fs)]

> [!NOTE]
> <span data-ttu-id="a5e43-123">使用することができます`use`計算式で、カスタマイズされたバージョンの場合、`use`式を使用します。</span><span class="sxs-lookup"><span data-stu-id="a5e43-123">You can use `use` in computation expressions, in which case a customized version of the `use` expression is used.</span></span> <span data-ttu-id="a5e43-124">詳細については、次を参照してください。[シーケンス](sequences.md)、[非同期ワークフロー](asynchronous-workflows.md)、および[コンピュテーション式](computation-expressions.md)します。</span><span class="sxs-lookup"><span data-stu-id="a5e43-124">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>

## <a name="using-function"></a><span data-ttu-id="a5e43-125">関数を使用してください。</span><span class="sxs-lookup"><span data-stu-id="a5e43-125">using Function</span></span>

<span data-ttu-id="a5e43-126">`using`関数には、次の形式。</span><span class="sxs-lookup"><span data-stu-id="a5e43-126">The `using` function has the following form:</span></span>

<span data-ttu-id="a5e43-127">`using` (*expression1*) *function-or-lambda*</span><span class="sxs-lookup"><span data-stu-id="a5e43-127">`using` (*expression1*) *function-or-lambda*</span></span>

<span data-ttu-id="a5e43-128">`using`式、 *expression1*破棄する必要がありますオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="a5e43-128">In a `using` expression, *expression1* creates the object that must be disposed.</span></span> <span data-ttu-id="a5e43-129">結果*expression1* (破棄する必要がありますオブジェクト) が、引数*値*を*関数またはラムダ*、1 つが必要とする関数によって生成された値に一致する型の引数の残り*expression1*、またはその型の引数を受け取るラムダ式。</span><span class="sxs-lookup"><span data-stu-id="a5e43-129">The result of *expression1* (the object that must be disposed) becomes an argument, *value*, to *function-or-lambda*, which is either a function that expects a single remaining argument of a type that matches the value produced by *expression1*, or a lambda expression that expects an argument of that type.</span></span> <span data-ttu-id="a5e43-130">ランタイムが呼び出す関数の実行の最後に、`Dispose`リソースを解放し、(値がない限り`null`、後者 Dispose の呼び出しは行われません)。</span><span class="sxs-lookup"><span data-stu-id="a5e43-130">At the end of the execution of the function, the runtime calls `Dispose` and frees the resources (unless the value is `null`, in which case the call to Dispose is not attempted).</span></span>

<span data-ttu-id="a5e43-131">次の例で、`using`ラムダ式を持つ式。</span><span class="sxs-lookup"><span data-stu-id="a5e43-131">The following example demonstrates the `using` expression with a lambda expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6302.fs)]

<span data-ttu-id="a5e43-132">例を次に示します、`using`関数を使用した式。</span><span class="sxs-lookup"><span data-stu-id="a5e43-132">The next example shows the `using` expression with a function.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6303.fs)]

<span data-ttu-id="a5e43-133">関数は既に適用されるいくつかの引数を持つ関数である可能性がありますに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a5e43-133">Note that the function could be a function that has some arguments applied already.</span></span> <span data-ttu-id="a5e43-134">次のコード例はこの処理方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a5e43-134">The following code example demonstrates this.</span></span> <span data-ttu-id="a5e43-135">文字列を含むファイルが作成されます`XYZ`します。</span><span class="sxs-lookup"><span data-stu-id="a5e43-135">It creates a file that contains the string `XYZ`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6304.fs)]

<span data-ttu-id="a5e43-136">`using`関数と`use`バインディングは同じことを実現するほぼ同等の方法です。</span><span class="sxs-lookup"><span data-stu-id="a5e43-136">The `using` function and the `use` binding are nearly equivalent ways to accomplish the same thing.</span></span> <span data-ttu-id="a5e43-137">`using`キーワードは、時に詳細に制御を提供します。`Dispose`が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="a5e43-137">The `using` keyword provides more control over when `Dispose` is called.</span></span> <span data-ttu-id="a5e43-138">使用すると`using`、`Dispose`を使用するときに、関数またはラムダ式の最後に呼び出されますが、`use`キーワード、`Dispose`要素を含むコード ブロックの最後に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="a5e43-138">When you use `using`, `Dispose` is called at the end of the function or lambda expression; when you use the `use` keyword, `Dispose` is called at the end of the containing code block.</span></span> <span data-ttu-id="a5e43-139">一般に、使用を希望する必要があります`use`の代わりに、`using`関数。</span><span class="sxs-lookup"><span data-stu-id="a5e43-139">In general, you should prefer to use `use` instead of the `using` function.</span></span>

## <a name="see-also"></a><span data-ttu-id="a5e43-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="a5e43-140">See also</span></span>

- [<span data-ttu-id="a5e43-141">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="a5e43-141">F# Language Reference</span></span>](index.md)
