---
title: ユーザー定義関数
ms.date: 12/13/2019
description: ユーザー定義のスカラー関数と集計関数を作成する方法について説明します。
ms.openlocfilehash: 9ee3fbac73215353c8dc82199203b0d25e580cdb
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450412"
---
# <a name="user-defined-functions"></a><span data-ttu-id="d7589-103">ユーザー定義関数</span><span class="sxs-lookup"><span data-stu-id="d7589-103">User-defined functions</span></span>

<span data-ttu-id="d7589-104">ほとんどのデータベースには、独自の関数を定義するために使用できる SQL の手続き型の言語が用意されています。</span><span class="sxs-lookup"><span data-stu-id="d7589-104">Most databases have a procedural dialect of SQL that you can use to define your own functions.</span></span> <span data-ttu-id="d7589-105">ただし、SQLite はアプリでインプロセスで実行されます。</span><span class="sxs-lookup"><span data-stu-id="d7589-105">SQLite however, runs in-process with your app.</span></span> <span data-ttu-id="d7589-106">SQL の新しい言語を習得する代わりに、アプリのプログラミング言語を使用するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="d7589-106">Instead of having to learn a new dialect of SQL, you can just use the programming language of your app.</span></span>

## <a name="scalar-functions"></a><span data-ttu-id="d7589-107">スカラー関数</span><span class="sxs-lookup"><span data-stu-id="d7589-107">Scalar functions</span></span>

<span data-ttu-id="d7589-108">スカラー関数は、クエリ内の行ごとに1つのスカラー値を返します。</span><span class="sxs-lookup"><span data-stu-id="d7589-108">Scalar functions return a single, scalar value for each row in a query.</span></span> <span data-ttu-id="d7589-109">新しいスカラー関数を定義し、<xref:Microsoft.Data.Sqlite.SqliteConnection.CreateFunction%2A>を使用して組み込みの関数をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="d7589-109">Define new scalar functions and override the built-in ones using <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateFunction%2A>.</span></span>

<span data-ttu-id="d7589-110">`func` 引数のサポートされているパラメーターと戻り値の型の一覧については、「[データ型](types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7589-110">See [Data types](types.md) for a list of supported parameter and return types for the `func` argument.</span></span>

<span data-ttu-id="d7589-111">`state` 引数を指定すると、その値が関数のすべての呼び出しに渡されます。</span><span class="sxs-lookup"><span data-stu-id="d7589-111">Specifying the `state` argument will pass that value into every invocation of the function.</span></span> <span data-ttu-id="d7589-112">クロージャを回避するには、これを使用します。</span><span class="sxs-lookup"><span data-stu-id="d7589-112">Use this to avoid closures.</span></span>

<span data-ttu-id="d7589-113">クエリをコンパイルするときに SQLite で追加の最適化を使用できるようにするために、関数が決定的である場合は `isDeterministic` を指定します。</span><span class="sxs-lookup"><span data-stu-id="d7589-113">Specify `isDeterministic` if your function is deterministic to allow SQLite to use additional optimizations when compiling queries.</span></span>

<span data-ttu-id="d7589-114">次の例では、スカラー関数を追加して、円柱の半径を計算する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d7589-114">The following example shows how to add a scalar function to calculate the radius of a cylinder.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ScalarFunctionSample/Program.cs?name=snippet_CreateFunction)]

## <a name="operators"></a><span data-ttu-id="d7589-115">演算子</span><span class="sxs-lookup"><span data-stu-id="d7589-115">Operators</span></span>

<span data-ttu-id="d7589-116">次の SQLite 演算子は、対応するスカラー関数によって実装されます。</span><span class="sxs-lookup"><span data-stu-id="d7589-116">The following SQLite operators are implemented by corresponding scalar functions.</span></span> <span data-ttu-id="d7589-117">これらのスカラー関数をアプリに定義すると、これらの演算子の動作が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="d7589-117">Defining these scalar functions in your app will override the behavior of these operators.</span></span>

| <span data-ttu-id="d7589-118">演算子</span><span class="sxs-lookup"><span data-stu-id="d7589-118">Operator</span></span>          | <span data-ttu-id="d7589-119">関数</span><span class="sxs-lookup"><span data-stu-id="d7589-119">Function</span></span>      |
| ----------------- | ------------- |
| <span data-ttu-id="d7589-120">X GLOB Y</span><span class="sxs-lookup"><span data-stu-id="d7589-120">X GLOB Y</span></span>          | <span data-ttu-id="d7589-121">glob (Y, X)</span><span class="sxs-lookup"><span data-stu-id="d7589-121">glob(Y, X)</span></span>    |
| <span data-ttu-id="d7589-122">Y のような X</span><span class="sxs-lookup"><span data-stu-id="d7589-122">X LIKE Y</span></span>          | <span data-ttu-id="d7589-123">like (Y, X)</span><span class="sxs-lookup"><span data-stu-id="d7589-123">like(Y, X)</span></span>    |
| <span data-ttu-id="d7589-124">X のような Y エスケープ Z</span><span class="sxs-lookup"><span data-stu-id="d7589-124">X LIKE Y ESCAPE Z</span></span> | <span data-ttu-id="d7589-125">like (Y, X, Z)</span><span class="sxs-lookup"><span data-stu-id="d7589-125">like(Y, X, Z)</span></span> |
| <span data-ttu-id="d7589-126">X 一致 Y</span><span class="sxs-lookup"><span data-stu-id="d7589-126">X MATCH Y</span></span>         | <span data-ttu-id="d7589-127">一致 (Y, X)</span><span class="sxs-lookup"><span data-stu-id="d7589-127">match(Y, X)</span></span>   |
| <span data-ttu-id="d7589-128">X REGEXP (Y)</span><span class="sxs-lookup"><span data-stu-id="d7589-128">X REGEXP Y</span></span>        | <span data-ttu-id="d7589-129">regexp (Y, X)</span><span class="sxs-lookup"><span data-stu-id="d7589-129">regexp(Y, X)</span></span>  |

<span data-ttu-id="d7589-130">次の例では、対応する演算子を有効にするために regexp 関数を定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d7589-130">The following example shows how to define the regexp function to enable its corresponding operator.</span></span> <span data-ttu-id="d7589-131">SQLite には、regexp 関数の既定の実装は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="d7589-131">SQLite doesn't include a default implementation of the regexp function.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/RegularExpressionSample/Program.cs?name=snippet_Regex)]

## <a name="aggregate-functions"></a><span data-ttu-id="d7589-132">集計関数</span><span class="sxs-lookup"><span data-stu-id="d7589-132">Aggregate functions</span></span>

<span data-ttu-id="d7589-133">集計関数は、クエリ内のすべての行に対して1つの集計値を返します。</span><span class="sxs-lookup"><span data-stu-id="d7589-133">Aggregate functions return a single, aggregated value for all the rows in a query.</span></span> <span data-ttu-id="d7589-134"><xref:Microsoft.Data.Sqlite.SqliteConnection.CreateAggregate%2A>を使用して集計関数を定義およびオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="d7589-134">Define and override aggregate functions using <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateAggregate%2A>.</span></span>

<span data-ttu-id="d7589-135">`seed` 引数は、コンテキストの初期状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="d7589-135">The `seed` argument specifies the initial state of the context.</span></span> <span data-ttu-id="d7589-136">クロージャも使用しないようにします。</span><span class="sxs-lookup"><span data-stu-id="d7589-136">Use this to avoid closures also.</span></span>

<span data-ttu-id="d7589-137">`func` 引数は、行ごとに1回だけ呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d7589-137">The `func` argument is invoked once per row.</span></span> <span data-ttu-id="d7589-138">コンテキストを使用して、最終結果を累積します。</span><span class="sxs-lookup"><span data-stu-id="d7589-138">Use the context to accumulate a final result.</span></span> <span data-ttu-id="d7589-139">コンテキストを返します。</span><span class="sxs-lookup"><span data-stu-id="d7589-139">Return the context.</span></span> <span data-ttu-id="d7589-140">このパターンでは、コンテキストを値型にすることも、変更できないようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d7589-140">This pattern allows the context to be a value type or immutable.</span></span>

<span data-ttu-id="d7589-141">`resultSelector` が指定されていない場合、コンテキストの最終的な状態が結果として使用されます。</span><span class="sxs-lookup"><span data-stu-id="d7589-141">If no `resultSelector` is specified, the final state of the context is used as the result.</span></span> <span data-ttu-id="d7589-142">これにより、sum や count などの関数の定義が単純化され、行ごとに番号をインクリメントして返すだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="d7589-142">This can simplify the definition of functions like sum and count that only need to increment a number each row and return it.</span></span>

<span data-ttu-id="d7589-143">すべての行を反復処理した後、コンテキストから最終的な結果を計算するには、`resultSelector` を指定します。</span><span class="sxs-lookup"><span data-stu-id="d7589-143">Specify `resultSelector` to calculate the final result from the context after iterating through all the rows.</span></span>

<span data-ttu-id="d7589-144">`resultSelector`の `func` の引数と戻り値の型については、「[データ型](types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7589-144">See [Data types](types.md) for a list of supported parameter types for the `func` argument and return types for `resultSelector`.</span></span>

<span data-ttu-id="d7589-145">関数が決定的である場合は、`isDeterministic` を指定して、SQLite がクエリをコンパイルするときに追加の最適化を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="d7589-145">If your function is deterministic, specify `isDeterministic` to allow SQLite to use additional optimizations when compiling queries.</span></span>

<span data-ttu-id="d7589-146">次の例では、列の標準偏差を計算する集計関数を定義します。</span><span class="sxs-lookup"><span data-stu-id="d7589-146">The following example defines an aggregate function to calculate the standard deviation of a column.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/AggregateFunctionSample/Program.cs?name=snippet_CreateAggregate)]

## <a name="errors"></a><span data-ttu-id="d7589-147">エラー</span><span class="sxs-lookup"><span data-stu-id="d7589-147">Errors</span></span>

<span data-ttu-id="d7589-148">ユーザー定義関数が例外をスローした場合、メッセージは SQLite に返されます。</span><span class="sxs-lookup"><span data-stu-id="d7589-148">If a user-defined function throws an exception, the message is returned to SQLite.</span></span> <span data-ttu-id="d7589-149">SQLite によってエラーが発生し、SqliteException がスローされます。</span><span class="sxs-lookup"><span data-stu-id="d7589-149">SQLite will then raise an error and Microsoft.Data.Sqlite will throw a SqliteException.</span></span> <span data-ttu-id="d7589-150">詳細については、「[データベースエラー](database-errors.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7589-150">For more information, see [Database errors](database-errors.md).</span></span>

<span data-ttu-id="d7589-151">既定では、エラー SQLite エラーコードは SQLITE_ERROR (または 1) になります。</span><span class="sxs-lookup"><span data-stu-id="d7589-151">By default, the error SQLite error code will be SQLITE_ERROR (or 1).</span></span> <span data-ttu-id="d7589-152">ただし、必要な <xref:Microsoft.Data.Sqlite.SqliteException.SqliteErrorCode> を指定して関数内の <xref:Microsoft.Data.Sqlite.SqliteException> をスローすることによって変更できます。</span><span class="sxs-lookup"><span data-stu-id="d7589-152">You can, however, change it by throwing a <xref:Microsoft.Data.Sqlite.SqliteException> in your function with the desired <xref:Microsoft.Data.Sqlite.SqliteException.SqliteErrorCode> specified.</span></span>

## <a name="debugging"></a><span data-ttu-id="d7589-153">デバッグ</span><span class="sxs-lookup"><span data-stu-id="d7589-153">Debugging</span></span>

<span data-ttu-id="d7589-154">SQLite は、実装を直接呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d7589-154">SQLite calls your implementation directly.</span></span> <span data-ttu-id="d7589-155">これにより、SQLite がクエリを評価している間にトリガーされるブレークポイントを追加できます。</span><span class="sxs-lookup"><span data-stu-id="d7589-155">This lets you add breakpoints that trigger while SQLite is evaluating queries.</span></span> <span data-ttu-id="d7589-156">完全な .NET デバッグエクスペリエンスは、ユーザー定義関数の作成に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d7589-156">The full .NET debugging experience is available to help you create your user-defined functions.</span></span>

## <a name="see-also"></a><span data-ttu-id="d7589-157">参照</span><span class="sxs-lookup"><span data-stu-id="d7589-157">See also</span></span>

* [<span data-ttu-id="d7589-158">データ型</span><span class="sxs-lookup"><span data-stu-id="d7589-158">Data types</span></span>](types.md)
* [<span data-ttu-id="d7589-159">SQLite コア関数</span><span class="sxs-lookup"><span data-stu-id="d7589-159">SQLite Core functions</span></span>](https://www.sqlite.org/lang_corefunc.html)
* [<span data-ttu-id="d7589-160">SQLite 集計関数</span><span class="sxs-lookup"><span data-stu-id="d7589-160">SQLite Aggregate Functions</span></span>](https://www.sqlite.org/lang_aggfunc.html)
