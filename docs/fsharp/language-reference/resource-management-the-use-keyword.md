---
title: リソース管理:Use キーワード
description: F#キーワード ' use ' と ' using ' 関数について説明します。この関数は、リソースの初期化と解放を制御できます。
ms.date: 05/16/2016
ms.openlocfilehash: 5e0838401bee02050343b2f6dcc646a8dc8b4dc0
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627255"
---
# <a name="resource-management-the-use-keyword"></a><span data-ttu-id="965a4-103">リソース管理:Use キーワード</span><span class="sxs-lookup"><span data-stu-id="965a4-103">Resource Management: The use Keyword</span></span>

<span data-ttu-id="965a4-104">このトピック`use` `using`では、リソースの初期化と解放を制御できるキーワードと関数について説明します。</span><span class="sxs-lookup"><span data-stu-id="965a4-104">This topic describes the keyword `use` and the `using` function, which can control the initialization and release of resources.</span></span>

## <a name="resources"></a><span data-ttu-id="965a4-105">リソース</span><span class="sxs-lookup"><span data-stu-id="965a4-105">Resources</span></span>

<span data-ttu-id="965a4-106">*リソース*という用語は、複数の方法で使用されます。</span><span class="sxs-lookup"><span data-stu-id="965a4-106">The term *resource* is used in more than one way.</span></span> <span data-ttu-id="965a4-107">はい。リソースは、文字列やグラフィックスなど、アプリケーションで使用されるデータにすることができますが、このコンテキストでは、*リソース*とは、グラフィックスデバイスコンテキスト、ファイルハンドル、ネットワーク、データベースなどのソフトウェアまたはオペレーティングシステムのリソースを指します。接続、待機ハンドルなどの同時実行オブジェクトなど。</span><span class="sxs-lookup"><span data-stu-id="965a4-107">Yes, resources can be data that an application uses, such as strings, graphics, and the like, but in this context, *resources* refers to software or operating system resources, such as graphics device contexts, file handles, network and database connections, concurrency objects such as wait handles, and so on.</span></span> <span data-ttu-id="965a4-108">これらのリソースをアプリケーションで使用するには、オペレーティングシステムまたは他のリソースプロバイダーからリソースを取得した後、リソースの新しいリリースをプールに渡して、別のアプリケーションに提供できるようにします。</span><span class="sxs-lookup"><span data-stu-id="965a4-108">The use of these resources by applications involves the acquisition of the resource from the operating system or other resource provider, followed by the later release of the resource to the pool so that it can be provided to another application.</span></span> <span data-ttu-id="965a4-109">アプリケーションがリソースを共通プールに解放しないと、問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="965a4-109">Problems occur when applications do not release resources back to the common pool.</span></span>

## <a name="managing-resources"></a><span data-ttu-id="965a4-110">リソースの管理</span><span class="sxs-lookup"><span data-stu-id="965a4-110">Managing Resources</span></span>

<span data-ttu-id="965a4-111">アプリケーションのリソースを効率的かつ確実に管理するには、リソースを迅速かつ予測可能な方法で解放する必要があります。</span><span class="sxs-lookup"><span data-stu-id="965a4-111">To efficiently and responsibly manage resources in an application, you must release resources promptly and in a predictable manner.</span></span> <span data-ttu-id="965a4-112">.NET Framework を使用すると、 `System.IDisposable`インターフェイスを提供してこれを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="965a4-112">The .NET Framework helps you do this by providing the `System.IDisposable` interface.</span></span> <span data-ttu-id="965a4-113">を実装`System.IDisposable`する型に`System.IDisposable.Dispose`は、リソースを正しく解放するメソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="965a4-113">A type that implements `System.IDisposable` has the `System.IDisposable.Dispose` method, which correctly frees resources.</span></span> <span data-ttu-id="965a4-114">適切に記述された`System.IDisposable.Dispose`アプリケーションは、リソースが制限されているオブジェクトが不要になったときに、すぐに呼び出されることを保証します。</span><span class="sxs-lookup"><span data-stu-id="965a4-114">Well-written applications guarantee that `System.IDisposable.Dispose` is called promptly when any object that holds a limited resource is no longer needed.</span></span> <span data-ttu-id="965a4-115">さいわい、ほとんどの .NET 言語が、簡単に確認するサポートを提供し、F# には例外はありません。</span><span class="sxs-lookup"><span data-stu-id="965a4-115">Fortunately, most .NET languages provide support to make this easier, and F# is no exception.</span></span> <span data-ttu-id="965a4-116">Dispose パターンをサポートする便利な言語構成要素`use` `using`として、バインディングと関数の2つがあります。</span><span class="sxs-lookup"><span data-stu-id="965a4-116">There are two useful language constructs that support the dispose pattern: the `use` binding and the `using` function.</span></span>

## <a name="use-binding"></a><span data-ttu-id="965a4-117">バインドを使用する</span><span class="sxs-lookup"><span data-stu-id="965a4-117">use Binding</span></span>

<span data-ttu-id="965a4-118">キーワードには、 `let`バインドの形式に似た形式があります。 `use`</span><span class="sxs-lookup"><span data-stu-id="965a4-118">The `use` keyword has a form that resembles that of the `let` binding:</span></span>

<span data-ttu-id="965a4-119">*値* = *式*を使用する</span><span class="sxs-lookup"><span data-stu-id="965a4-119">use *value* = *expression*</span></span>

<span data-ttu-id="965a4-120">`let`バインディングと同じ機能を提供しますが、値がスコープ`Dispose`外になったときにの呼び出しを値に追加します。</span><span class="sxs-lookup"><span data-stu-id="965a4-120">It provides the same functionality as a `let` binding but adds a call to `Dispose` on the value when the value goes out of scope.</span></span> <span data-ttu-id="965a4-121">コンパイラは値に null チェックを挿入するため、値が`null`の場合、へ`Dispose`の呼び出しは試行されません。</span><span class="sxs-lookup"><span data-stu-id="965a4-121">Note that the compiler inserts a null check on the value, so that if the value is `null`, the call to `Dispose` is not attempted.</span></span>

<span data-ttu-id="965a4-122">次の例は、 `use`キーワードを使用してファイルを自動的に閉じる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="965a4-122">The following example shows how to close a file automatically by using the `use` keyword.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6301.fs)]

> [!NOTE]
> <span data-ttu-id="965a4-123">コンピュテーション式で`use`を使用できます。この場合、 `use`式のカスタマイズされたバージョンが使用されます。</span><span class="sxs-lookup"><span data-stu-id="965a4-123">You can use `use` in computation expressions, in which case a customized version of the `use` expression is used.</span></span> <span data-ttu-id="965a4-124">詳細については、「[シーケンス](sequences.md)、[非同期ワークフロー](asynchronous-workflows.md)、および[コンピュテーション式](computation-expressions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="965a4-124">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>

## <a name="using-function"></a><span data-ttu-id="965a4-125">関数の使用</span><span class="sxs-lookup"><span data-stu-id="965a4-125">using Function</span></span>

<span data-ttu-id="965a4-126">関数`using`の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="965a4-126">The `using` function has the following form:</span></span>

<span data-ttu-id="965a4-127">`using`(*expression1*)*関数または-ラムダ*</span><span class="sxs-lookup"><span data-stu-id="965a4-127">`using` (*expression1*) *function-or-lambda*</span></span>

<span data-ttu-id="965a4-128">式では、expression1 は、破棄する必要があるオブジェクトを作成します。 `using`</span><span class="sxs-lookup"><span data-stu-id="965a4-128">In a `using` expression, *expression1* creates the object that must be disposed.</span></span> <span data-ttu-id="965a4-129">*Expression1* (破棄する必要があるオブジェクト) の結果は、引数、*値*、*またはラムダ*になります。これは、によって*生成される値に一致する型の1つの残りの引数を期待する関数です。expression1*、またはその型の引数を予期するラムダ式。</span><span class="sxs-lookup"><span data-stu-id="965a4-129">The result of *expression1* (the object that must be disposed) becomes an argument, *value*, to *function-or-lambda*, which is either a function that expects a single remaining argument of a type that matches the value produced by *expression1*, or a lambda expression that expects an argument of that type.</span></span> <span data-ttu-id="965a4-130">関数の実行が終了すると、ランタイムはリソースを呼び出し`Dispose` 、解放します (値が`null`の場合を除きます。この場合、Dispose への呼び出しは試行されません)。</span><span class="sxs-lookup"><span data-stu-id="965a4-130">At the end of the execution of the function, the runtime calls `Dispose` and frees the resources (unless the value is `null`, in which case the call to Dispose is not attempted).</span></span>

<span data-ttu-id="965a4-131">次の例では`using` 、ラムダ式を含む式を示します。</span><span class="sxs-lookup"><span data-stu-id="965a4-131">The following example demonstrates the `using` expression with a lambda expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6302.fs)]

<span data-ttu-id="965a4-132">次の例は、 `using`関数を使用した式を示しています。</span><span class="sxs-lookup"><span data-stu-id="965a4-132">The next example shows the `using` expression with a function.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6303.fs)]

<span data-ttu-id="965a4-133">関数は、いくつかの引数が既に適用されている関数である可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="965a4-133">Note that the function could be a function that has some arguments applied already.</span></span> <span data-ttu-id="965a4-134">次のコード例はこの処理方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="965a4-134">The following code example demonstrates this.</span></span> <span data-ttu-id="965a4-135">この例では、文字列`XYZ`を含むファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="965a4-135">It creates a file that contains the string `XYZ`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6304.fs)]

<span data-ttu-id="965a4-136">`using` 関数`use`とバインディングは、同じことを実現するためのほぼ同じ方法です。</span><span class="sxs-lookup"><span data-stu-id="965a4-136">The `using` function and the `use` binding are nearly equivalent ways to accomplish the same thing.</span></span> <span data-ttu-id="965a4-137">キーワード`using`を使用すると、が`Dispose`呼び出されるタイミングをより細かく制御できます。</span><span class="sxs-lookup"><span data-stu-id="965a4-137">The `using` keyword provides more control over when `Dispose` is called.</span></span> <span data-ttu-id="965a4-138">を使用`using`すると`Dispose` 、関数またはラムダ式の末尾でが呼び出され`use`ます。キーワードを使用する`Dispose`と、が格納されているコードブロックの末尾でが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="965a4-138">When you use `using`, `Dispose` is called at the end of the function or lambda expression; when you use the `use` keyword, `Dispose` is called at the end of the containing code block.</span></span> <span data-ttu-id="965a4-139">一般に、 `using`関数の代わりにを`use`使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="965a4-139">In general, you should prefer to use `use` instead of the `using` function.</span></span>

## <a name="see-also"></a><span data-ttu-id="965a4-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="965a4-140">See also</span></span>

- [<span data-ttu-id="965a4-141">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="965a4-141">F# Language Reference</span></span>](index.md)
