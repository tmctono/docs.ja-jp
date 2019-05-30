---
title: F# のツアー
description: 主な機能のいくつかを確認、F#プログラミング言語でこのツアーではコード サンプルを使用します。
ms.date: 11/06/2018
ms.openlocfilehash: 64394342777003b33dd77028739fb7209b9f3c86
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66301253"
---
# <a name="tour-of-f"></a><span data-ttu-id="8763a-103">F# のツアー\#</span><span class="sxs-lookup"><span data-stu-id="8763a-103">Tour of F\#</span></span>

<span data-ttu-id="8763a-104">F# について学習する最善の方法は、F# コードを読み書きすることです。</span><span class="sxs-lookup"><span data-stu-id="8763a-104">The best way to learn about F# is to read and write F# code.</span></span> <span data-ttu-id="8763a-105">この記事は、F# 言語のいくつかの主な機能の手引きとしての役割を果たし、コンピューターで実行できるいくつかのコード スニペットを示します。</span><span class="sxs-lookup"><span data-stu-id="8763a-105">This article will act as a tour through some of the key features of the F# language and give you some code snippets that you can execute on your machine.</span></span> <span data-ttu-id="8763a-106">開発環境を設定する方法については、[Getting Started](tutorials/getting-started/index.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8763a-106">To learn about setting up a development environment, check out [Getting Started](tutorials/getting-started/index.md).</span></span>

<span data-ttu-id="8763a-107">2 つの主要な概念があるF#: 関数と型。</span><span class="sxs-lookup"><span data-stu-id="8763a-107">There are two primary concepts in F#: functions and types.</span></span>  <span data-ttu-id="8763a-108">このツアーではこれら 2 つの概念には、言語の機能を強調します。</span><span class="sxs-lookup"><span data-stu-id="8763a-108">This tour will emphasize features of the language which fall into these two concepts.</span></span>

## <a name="executing-the-code-online"></a><span data-ttu-id="8763a-109">オンラインでのコードを実行します。</span><span class="sxs-lookup"><span data-stu-id="8763a-109">Executing the code online</span></span>

<span data-ttu-id="8763a-110">いない場合F#コンピューターにインストールされている、ことができますを実行するすべてのサンプルと共にブラウザーに[お試しくださいF#WebAssembly で](https://tryfsharp.fsbolero.io/)します。</span><span class="sxs-lookup"><span data-stu-id="8763a-110">If you don't have F# installed on your machine, you can execute all of the samples in your browser with [Try F# on WebAssembly](https://tryfsharp.fsbolero.io/).</span></span> <span data-ttu-id="8763a-111">Fable は言語にF#お使いのブラウザーで直接実行します。</span><span class="sxs-lookup"><span data-stu-id="8763a-111">Fable is a dialect of F# that executes directly in your browser.</span></span> <span data-ttu-id="8763a-112">REPL で次のサンプルを表示するチェック アウト**サンプル > 学習 > のツアー F#**  Fable レプリケーションの左側のメニュー バーに</span><span class="sxs-lookup"><span data-stu-id="8763a-112">To view the samples that follow in the REPL, check out **Samples > Learn > Tour of F#** in the left-hand menu bar of the Fable REPL.</span></span>

## <a name="functions-and-modules"></a><span data-ttu-id="8763a-113">関数、およびモジュール</span><span class="sxs-lookup"><span data-stu-id="8763a-113">Functions and Modules</span></span>

<span data-ttu-id="8763a-114">任意の F# プログラムの最も基本的な部分が***関数***編成***モジュール***します。</span><span class="sxs-lookup"><span data-stu-id="8763a-114">The most fundamental pieces of any F# program are ***functions*** organized into ***modules***.</span></span>  <span data-ttu-id="8763a-115">[関数](language-reference/functions/index.md)出力を生成する入力に作業を実行し、で構成される[モジュール](language-reference/modules.md)、F# でグループ化する主な方法であります。</span><span class="sxs-lookup"><span data-stu-id="8763a-115">[Functions](language-reference/functions/index.md) perform work on inputs to produce outputs, and they are organized under [Modules](language-reference/modules.md), which are the primary way you group things in F#.</span></span>  <span data-ttu-id="8763a-116">使用して定義されている、 [ `let`バインド](language-reference/functions/let-bindings.md)関数の名前し、その引数を定義します。</span><span class="sxs-lookup"><span data-stu-id="8763a-116">They are defined using the [`let` binding](language-reference/functions/let-bindings.md), which give the function a name and define its arguments.</span></span>

[!code-fsharp[BasicFunctions](../../samples/snippets/fsharp/tour.fs#L101-L133)]

<span data-ttu-id="8763a-117">`let` バインディングでは、値を他の言語での変数のような名前にバインドする方法も。</span><span class="sxs-lookup"><span data-stu-id="8763a-117">`let` bindings are also how you bind a value to a name, similar to a variable in other languages.</span></span>  <span data-ttu-id="8763a-118">`let` バインドは***不変***既定では、値または関数の名前をバインドしたら、変更できないことを意味する、インプレースします。</span><span class="sxs-lookup"><span data-stu-id="8763a-118">`let` bindings are ***immutable*** by default, which means that once a value or function is bound to a name, it cannot be changed in-place.</span></span>  <span data-ttu-id="8763a-119">これは、他の言語での変数とは対照的***変更可能な***時間で任意の時点でその値の意味を変更できます。</span><span class="sxs-lookup"><span data-stu-id="8763a-119">This is in contrast to variables in other languages, which are ***mutable***, meaning their values can be changed at any point in time.</span></span>  <span data-ttu-id="8763a-120">変更可能なバインディングを必要とする場合は使用できます`let mutable ...`構文。</span><span class="sxs-lookup"><span data-stu-id="8763a-120">If you require a mutable binding, you can use `let mutable ...` syntax.</span></span>

[!code-fsharp[Immutability](../../samples/snippets/fsharp/tour.fs#L75-L94)]

## <a name="numbers-booleans-and-strings"></a><span data-ttu-id="8763a-121">数値、ブール値、および文字列</span><span class="sxs-lookup"><span data-stu-id="8763a-121">Numbers, Booleans, and Strings</span></span>

<span data-ttu-id="8763a-122">.NET 言語として F# をサポートしています、同じ基になる[プリミティブ型](language-reference/primitive-types.md).NET 内に存在します。</span><span class="sxs-lookup"><span data-stu-id="8763a-122">As a .NET language, F# supports the same underlying [primitive types](language-reference/primitive-types.md) that exist in .NET.</span></span>

<span data-ttu-id="8763a-123">さまざまな数値型は F# で表されます。 次に示します。</span><span class="sxs-lookup"><span data-stu-id="8763a-123">Here is how various numeric types are represented in F#:</span></span>

[!code-fsharp[Numbers](../../samples/snippets/fsharp/tour.fs#L49-L68)]

<span data-ttu-id="8763a-124">どのようなブール値を次に示し、基本的な条件付きロジックを実行するようになります。</span><span class="sxs-lookup"><span data-stu-id="8763a-124">Here's what Boolean values and performing basic conditional logic looks like:</span></span>

[!code-fsharp[Bools](../../samples/snippets/fsharp/tour.fs#L142-L152)]

<span data-ttu-id="8763a-125">ここでは、どのような basic と[文字列](language-reference/strings.md)操作のようになります。</span><span class="sxs-lookup"><span data-stu-id="8763a-125">And here's what basic [string](language-reference/strings.md) manipulation looks like:</span></span>

[!code-fsharp[Strings](../../samples/snippets/fsharp/tour.fs#L158-L180)]

## <a name="tuples"></a><span data-ttu-id="8763a-126">タプル</span><span class="sxs-lookup"><span data-stu-id="8763a-126">Tuples</span></span>

<span data-ttu-id="8763a-127">[タプル](language-reference/tuples.md)は F# の大きな問題です。</span><span class="sxs-lookup"><span data-stu-id="8763a-127">[Tuples](language-reference/tuples.md) are a big deal in F#.</span></span>  <span data-ttu-id="8763a-128">これらは、値自体として扱うことができますが、名前のない、順序付けされた値のグループです。</span><span class="sxs-lookup"><span data-stu-id="8763a-128">They are a grouping of unnamed, but ordered values, that can be treated as values themselves.</span></span>  <span data-ttu-id="8763a-129">それらの他の値からごとに集計値として考えます。</span><span class="sxs-lookup"><span data-stu-id="8763a-129">Think of them as values which are aggregated from other values.</span></span>  <span data-ttu-id="8763a-130">簡単に、関数から複数の値を返すまたはアドホック便宜上いくつかの値をグループ化など、数多くの用途があります。</span><span class="sxs-lookup"><span data-stu-id="8763a-130">They have many uses, such as conveniently returning multiple values from a function, or grouping values for some ad-hoc convenience.</span></span>

[!code-fsharp[Tuples](../../samples/snippets/fsharp/tour.fs#L186-L203)]

<span data-ttu-id="8763a-131">F# 4.1、作成することも`struct`組。</span><span class="sxs-lookup"><span data-stu-id="8763a-131">As of F# 4.1, you can also create `struct` tuples.</span></span>  <span data-ttu-id="8763a-132">これらも相互運用完全にも、C# 7/Visual Basic 15 タプル`struct`組。</span><span class="sxs-lookup"><span data-stu-id="8763a-132">These also interoperate fully with C#7/Visual Basic 15 tuples, which are also `struct` tuples:</span></span>

[!code-fsharp[Tuples](../../samples/snippets/fsharp/tour.fs#L205-L218)]

<span data-ttu-id="8763a-133">ため、注意することが重要`struct`タプルが値型、タプルを参照する暗黙的に変換することはできませんまたはその逆です。</span><span class="sxs-lookup"><span data-stu-id="8763a-133">It's important to note that because `struct` tuples are value types, they cannot be implicitly converted to reference tuples, or vice versa.</span></span>  <span data-ttu-id="8763a-134">参照と構造体のタプルの間で明示的に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8763a-134">You must explicitly convert between a reference and struct tuple.</span></span>

## <a name="pipelines-and-composition"></a><span data-ttu-id="8763a-135">パイプラインと合成</span><span class="sxs-lookup"><span data-stu-id="8763a-135">Pipelines and Composition</span></span>

<span data-ttu-id="8763a-136">などの演算子をパイプ`|>`F# でのデータを処理するときに広く使用されます。</span><span class="sxs-lookup"><span data-stu-id="8763a-136">Pipe operators such as `|>` are used extensively when processing data in F#.</span></span> <span data-ttu-id="8763a-137">これらの演算子は、柔軟な方法で関数の「パイプライン」を確立するための関数です。</span><span class="sxs-lookup"><span data-stu-id="8763a-137">These operators are functions that allow you to establish "pipelines" of functions in a flexible manner.</span></span> <span data-ttu-id="8763a-138">次の例では、方法を利用する機能の単純なパイプラインを構築するこれらの演算子の説明します。</span><span class="sxs-lookup"><span data-stu-id="8763a-138">The following example walks through how you can take advantage of these operators to build a simple functional pipeline:</span></span>

[!code-fsharp[Pipelines](../../samples/snippets/fsharp/tour.fs#L227-L282)]

<span data-ttu-id="8763a-139">行われる前のサンプルの F# では、リスト処理関数をファーストクラスの関数を含む多くの機能の使用と[部分適用](language-reference/functions/index.md#partial-application-of-arguments)します。</span><span class="sxs-lookup"><span data-stu-id="8763a-139">The previous sample made use of many features of F#, including list processing functions, first-class functions, and [partial application](language-reference/functions/index.md#partial-application-of-arguments).</span></span> <span data-ttu-id="8763a-140">これらの概念のそれぞれの深い理解がやや高度なことができますになる、する必要がありますがクリア関数を使用してパイプラインを構築するときにデータを処理する方法を簡単にします。</span><span class="sxs-lookup"><span data-stu-id="8763a-140">Although a deep understanding of each of those concepts can become somewhat advanced, it should be clear how easily functions can be used to process data when building pipelines.</span></span>

## <a name="lists-arrays-and-sequences"></a><span data-ttu-id="8763a-141">リスト、配列、およびシーケンス</span><span class="sxs-lookup"><span data-stu-id="8763a-141">Lists, Arrays, and Sequences</span></span>

<span data-ttu-id="8763a-142">リスト、配列、およびシーケンスは、F# コア ライブラリの次の 3 つのプライマリ コレクション型です。</span><span class="sxs-lookup"><span data-stu-id="8763a-142">Lists, Arrays, and Sequences are three primary collection types in the F# core library.</span></span>

<span data-ttu-id="8763a-143">[一覧表示](language-reference/lists.md)は同じ型の要素の順序付けられた、変更できないコレクションです。</span><span class="sxs-lookup"><span data-stu-id="8763a-143">[Lists](language-reference/lists.md) are ordered, immutable collections of elements of the same type.</span></span>  <span data-ttu-id="8763a-144">シングル リンク リスト、つまり、大規模な場合、列挙がランダム アクセスと連結するにはあまり適して本来は。</span><span class="sxs-lookup"><span data-stu-id="8763a-144">They are singly-linked lists, which means they are meant for enumeration, but a poor choice for random access and concatenation if they're large.</span></span>  <span data-ttu-id="8763a-145">これは通常のリストを表すシングル リンク リストを使用しないでください、人気のある他の言語のリストとは対照的です。</span><span class="sxs-lookup"><span data-stu-id="8763a-145">This in contrast to Lists in other popular languages, which typically do not use a singly-linked list to represent Lists.</span></span>

[!code-fsharp[Lists](../../samples/snippets/fsharp/tour.fs#L309-L359)]

<span data-ttu-id="8763a-146">[配列](language-reference/arrays.md)が固定サイズ*変更可能な*同じ型の要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="8763a-146">[Arrays](language-reference/arrays.md) are fixed-size, *mutable* collections of elements of the same type.</span></span>  <span data-ttu-id="8763a-147">要素の高速なランダム アクセスをサポートし、F# リストのメモリ ブロックが連続するだけであるためよりも高速化されます。</span><span class="sxs-lookup"><span data-stu-id="8763a-147">They support fast random access of elements, and are faster than F# lists because they are just contiguous blocks of memory.</span></span>

[!code-fsharp[Arrays](../../samples/snippets/fsharp/tour.fs#L368-L407)]

<span data-ttu-id="8763a-148">[シーケンス](language-reference/sequences.md)は論理的な一連の同じ型のすべての要素。</span><span class="sxs-lookup"><span data-stu-id="8763a-148">[Sequences](language-reference/sequences.md) are a logical series of elements, all of the same type.</span></span>  <span data-ttu-id="8763a-149">これらは、リストと配列を論理的な一連の要素に、"view"をすることのできるより一般的な型です。</span><span class="sxs-lookup"><span data-stu-id="8763a-149">These are a more general type than Lists and Arrays, capable of being your "view" into any logical series of elements.</span></span>  <span data-ttu-id="8763a-150">これらも目立つことができるので***遅延***、つまり、必要な場合にのみ要素を計算することができます。</span><span class="sxs-lookup"><span data-stu-id="8763a-150">They also stand out because they can be ***lazy***, which means that elements can be computed only when they are needed.</span></span>

[!code-fsharp[Sequences](../../samples/snippets/fsharp/tour.fs#L418-L452)]

## <a name="recursive-functions"></a><span data-ttu-id="8763a-151">再帰関数</span><span class="sxs-lookup"><span data-stu-id="8763a-151">Recursive Functions</span></span>

<span data-ttu-id="8763a-152">コレクションまたは要素のシーケンス処理で通常実行[再帰](language-reference/functions/index.md#recursive-functions)F# でします。</span><span class="sxs-lookup"><span data-stu-id="8763a-152">Processing collections or sequences of elements is typically done with [recursion](language-reference/functions/index.md#recursive-functions) in F#.</span></span>  <span data-ttu-id="8763a-153">F#サポートが for ループおよび命令型プログラミングでは、再帰をお勧めの正確性を保証するために簡単だからです。</span><span class="sxs-lookup"><span data-stu-id="8763a-153">Although F# has support for loops and imperative programming, recursion is preferred because it is easier to guarantee correctness.</span></span>

> [!NOTE]
> <span data-ttu-id="8763a-154">次の例を使用してパターン マッチングの利用、`match`式。</span><span class="sxs-lookup"><span data-stu-id="8763a-154">The following example makes use of the pattern matching via the `match` expression.</span></span>  <span data-ttu-id="8763a-155">この基本的な構成要素はこの記事の後半で説明します。</span><span class="sxs-lookup"><span data-stu-id="8763a-155">This fundamental construct is covered later in this article.</span></span>

[!code-fsharp[RecursiveFunctions](../../samples/snippets/fsharp/tour.fs#L461-L500)]

<span data-ttu-id="8763a-156">F#これは、ループ コンストラクトと同じ速度ように再帰呼び出しを最適化する方法、末尾呼び出し最適化を完全にサポートがあります。</span><span class="sxs-lookup"><span data-stu-id="8763a-156">F# also has full support for Tail Call Optimization, which is a way to optimize recursive calls so that they are just as fast as a loop construct.</span></span>

## <a name="record-and-discriminated-union-types"></a><span data-ttu-id="8763a-157">レコードと判別された共用体型</span><span class="sxs-lookup"><span data-stu-id="8763a-157">Record and Discriminated Union Types</span></span>

<span data-ttu-id="8763a-158">レコード、共用体の型は、F# コードで使用される 2 つの基本的なデータ型を一般に、F# プログラムでデータを表現する最善の方法は。</span><span class="sxs-lookup"><span data-stu-id="8763a-158">Record and Union types are two fundamental data types used in F# code, and are generally the best way to represent data in an F# program.</span></span>  <span data-ttu-id="8763a-159">これにより、そのクラスのような他の言語は、構造的等値セマンティクスを備えることの主な違いの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="8763a-159">Although this makes them similar to classes in other languages, one of their primary differences is that they have structural equality semantics.</span></span>  <span data-ttu-id="8763a-160">つまり、「ネイティブ」の比較が等しいかどうかは簡単です - チェックのいずれかが、他と等しいかどうかだけです。</span><span class="sxs-lookup"><span data-stu-id="8763a-160">This means that they are "natively" comparable and equality is straightforward - just check if one is equal to the other.</span></span>

<span data-ttu-id="8763a-161">[レコード](language-reference/records.md)は省略可能なメンバー (メソッドなど) と、名前付きの値の集計。</span><span class="sxs-lookup"><span data-stu-id="8763a-161">[Records](language-reference/records.md) are an aggregate of named values, with optional members (such as methods).</span></span>  <span data-ttu-id="8763a-162">C# または Java に詳しい場合は、し、これらように思われる Poco または Pojo - と同様に構造的等値と式だけです。</span><span class="sxs-lookup"><span data-stu-id="8763a-162">If you're familiar with C# or Java, then these should feel similar to POCOs or POJOs - just with structural equality and less ceremony.</span></span>

[!code-fsharp[Records](../../samples/snippets/fsharp/tour.fs#L507-L559)]

<span data-ttu-id="8763a-163">F# 4.1、レコードとしても表現できます`struct`秒。</span><span class="sxs-lookup"><span data-stu-id="8763a-163">As of F# 4.1, you can also represent Records as `struct`s.</span></span>  <span data-ttu-id="8763a-164">これは、`[<Struct>]`属性。</span><span class="sxs-lookup"><span data-stu-id="8763a-164">This is done with the `[<Struct>]` attribute:</span></span>

[!code-fsharp[Records](../../samples/snippets/fsharp/tour.fs#L561-L568)]

<span data-ttu-id="8763a-165">[判別共用体 (Du)](language-reference/discriminated-unions.md)は値の名前付きのフォームまたはケースの数である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8763a-165">[Discriminated Unions (DUs)](language-reference/discriminated-unions.md) are values which could be a number of named forms or cases.</span></span>  <span data-ttu-id="8763a-166">型に格納されたデータには、いくつかの個別の値のいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="8763a-166">Data stored in the type can be one of several distinct values.</span></span>

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L575-L631)]

<span data-ttu-id="8763a-167">Du として使用することもできます。*単一ケースの判別共用体*、ドメイン モデリングのプリミティブ型を支援します。</span><span class="sxs-lookup"><span data-stu-id="8763a-167">You can also use DUs as *Single-Case Discriminated Unions*, to help with domain modeling over primitive types.</span></span>  <span data-ttu-id="8763a-168">多くの場合、文字列およびその他のプリミティブ型を表すもの、使用されはそのため、特定の意味が与えられます。</span><span class="sxs-lookup"><span data-stu-id="8763a-168">Often times, strings and other primitive types are used to represent something, and are thus given a particular meaning.</span></span>  <span data-ttu-id="8763a-169">ただし、データのプリミティブの表現のみを使用しては、誤って正しくない値を割り当てることになることができます!</span><span class="sxs-lookup"><span data-stu-id="8763a-169">However, using only the primitive representation of the data can result in mistakenly assigning an incorrect value!</span></span>  <span data-ttu-id="8763a-170">個別の単一ケース共用体として情報の各型を表すと、このシナリオでは正確性を適用できます。</span><span class="sxs-lookup"><span data-stu-id="8763a-170">Representing each type of information as a distinct single-case union can enforce correctness in this scenario.</span></span>

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L633-L654)]

<span data-ttu-id="8763a-171">単一ケース判別された共用体、基になる値を取得する、上記のサンプルに示すように明示的に unwrap する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8763a-171">As the above sample demonstrates, to get the underlying value in a single-case Discriminated Union, you must explicitly unwrap it.</span></span>

<span data-ttu-id="8763a-172">また、Du もサポート再帰的な定義では、ツリーと本質的に再帰型データを簡単に記述することができます。</span><span class="sxs-lookup"><span data-stu-id="8763a-172">Additionally, DUs also support recursive definitions, allowing you to easily represent trees and inherently recursive data.</span></span>  <span data-ttu-id="8763a-173">たとえば、ここではどのでバイナリ検索ツリーを表すことができます`exists`と`insert`関数。</span><span class="sxs-lookup"><span data-stu-id="8763a-173">For example, here's how you can represent a Binary Search Tree with `exists` and `insert` functions.</span></span>

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L656-L683)]

<span data-ttu-id="8763a-174">Du するデータ型にツリーを再帰的な構造を表すため、この再帰構造で動作しているは簡単で、正確性が保証されます。</span><span class="sxs-lookup"><span data-stu-id="8763a-174">Because DUs allow you to represent the recursive structure of the tree in the data type, operating on this recursive structure is straightforward and guarantees correctness.</span></span>  <span data-ttu-id="8763a-175">次に示すパターン マッチングでもサポートされます。</span><span class="sxs-lookup"><span data-stu-id="8763a-175">It is also supported in pattern matching, as shown below.</span></span>

<span data-ttu-id="8763a-176">さらに、として Du を表すことができます`struct`を`[<Struct>]`属性。</span><span class="sxs-lookup"><span data-stu-id="8763a-176">Additionally, you can represent DUs as `struct`s with the `[<Struct>]` attribute:</span></span>

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L685-L696)]

<span data-ttu-id="8763a-177">ただし、その際に留意する 2 つの重要事項があります。</span><span class="sxs-lookup"><span data-stu-id="8763a-177">However, there are two key things to keep in mind when doing so:</span></span>

1. <span data-ttu-id="8763a-178">DU 構造体は、再帰的に定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="8763a-178">A struct DU cannot be recursively-defined.</span></span>
2. <span data-ttu-id="8763a-179">DU 構造体には、そのケースのそれぞれに一意の名前が必要です。</span><span class="sxs-lookup"><span data-stu-id="8763a-179">A struct DU must have unique names for each of its cases.</span></span>

<span data-ttu-id="8763a-180">上記に従わないは、コンパイル エラーになります。</span><span class="sxs-lookup"><span data-stu-id="8763a-180">Failure to follow the above will result in a compilation error.</span></span>

## <a name="pattern-matching"></a><span data-ttu-id="8763a-181">パターン マッチ</span><span class="sxs-lookup"><span data-stu-id="8763a-181">Pattern Matching</span></span>

<span data-ttu-id="8763a-182">[パターン照合](language-reference/pattern-matching.md)により、F# の型に対する操作のための正確性が F# 言語機能です。</span><span class="sxs-lookup"><span data-stu-id="8763a-182">[Pattern Matching](language-reference/pattern-matching.md) is the F# language feature which enables correctness for operating on F# types.</span></span>  <span data-ttu-id="8763a-183">上記のサンプルのことに気付いたのかなり`match x with ...`構文。</span><span class="sxs-lookup"><span data-stu-id="8763a-183">In the above samples, you probably noticed quite a bit of `match x with ...` syntax.</span></span>  <span data-ttu-id="8763a-184">このコンス トラクターにより、コンパイラを強制すると、パターンの完全一致として呼ばれるものを通じて、データ型を使用する場合は、すべての可能なケースのアカウントに、データ型の「形状」を理解することができます。</span><span class="sxs-lookup"><span data-stu-id="8763a-184">This construct allows the compiler, which can understand the "shape" of data types, to force you to account for all possible cases when using a data type through what is known as Exhaustive Pattern Matching.</span></span>  <span data-ttu-id="8763a-185">これは正しいかどうか、非常に強力な巧妙にどのようなコンパイル時にランタイムの問題は、通常「リフト」使用できます。</span><span class="sxs-lookup"><span data-stu-id="8763a-185">This is incredibly powerful for correctness, and can be cleverly used to "lift" what would normally be a runtime concern into compile-time.</span></span>

[!code-fsharp[PatternMatching](../../samples/snippets/fsharp/tour.fs#L705-L742)]

<span data-ttu-id="8763a-186">使用は、何かお気付き、`_`パターン。</span><span class="sxs-lookup"><span data-stu-id="8763a-186">Something you may have noticed is the use of the `_` pattern.</span></span>  <span data-ttu-id="8763a-187">これと呼ばれますが、[ワイルドカード パターン](language-reference/pattern-matching.md#wildcard-pattern)、「気にしません何かが」と答えるのですが。</span><span class="sxs-lookup"><span data-stu-id="8763a-187">This is known as the [Wildcard Pattern](language-reference/pattern-matching.md#wildcard-pattern), which is a way of saying "I don't care what something is".</span></span>  <span data-ttu-id="8763a-188">、便利ですが誤ってバイパス徹底的なパターンに一致して不要になったコンパイル時の実施メリットを使用して注意が必要ない場合は`_`します。</span><span class="sxs-lookup"><span data-stu-id="8763a-188">Although convenient, you can accidentally bypass Exhaustive Pattern Matching and no longer benefit from compile-time enforcements if you aren't careful in using `_`.</span></span>  <span data-ttu-id="8763a-189">分解された型の特定の情報が必要ない場合に最適な使用パターン マッチ式内のすべての意味のあるケースを列挙するときと一致する、または最後の句のパターンします。</span><span class="sxs-lookup"><span data-stu-id="8763a-189">It is best used when you don't care about certain pieces of a decomposed type when pattern matching, or the final clause when you have enumerated all meaningful cases in a pattern matching expression.</span></span>

<span data-ttu-id="8763a-190">[アクティブ パターン](language-reference/active-patterns.md)はパターン マッチングで使用する別の強力なコンストラクトです。</span><span class="sxs-lookup"><span data-stu-id="8763a-190">[Active Patterns](language-reference/active-patterns.md) are another powerful construct to use with pattern matching.</span></span>  <span data-ttu-id="8763a-191">それらの分解パターン一致の呼び出しサイトでカスタムのフォームに入力データをパーティション化できます。</span><span class="sxs-lookup"><span data-stu-id="8763a-191">They allow you to partition input data into custom forms, decomposing them at the pattern match call site.</span></span>  <span data-ttu-id="8763a-192">これらもパラメーター化できる、ため関数として、パーティションを定義することができます。</span><span class="sxs-lookup"><span data-stu-id="8763a-192">They can also be parameterized, thus allowing to define the partition as a function.</span></span>  <span data-ttu-id="8763a-193">アクティブ パターンをサポートするために、前の例を展開するようになります。</span><span class="sxs-lookup"><span data-stu-id="8763a-193">Expanding the previous example to support Active Patterns looks something like this:</span></span>

[!code-fsharp[ActivePatterns](../../samples/snippets/fsharp/tour.fs#L764-L786)]

## <a name="optional-types"></a><span data-ttu-id="8763a-194">省略可能な型</span><span class="sxs-lookup"><span data-stu-id="8763a-194">Optional Types</span></span>

<span data-ttu-id="8763a-195">判別共用体の型の 1 つの特殊なケースは非常に役立つ、F# コア ライブラリの一部であるあるオプションの種類です。</span><span class="sxs-lookup"><span data-stu-id="8763a-195">One special case of Discriminated Union types is the Option Type, which is so useful that it's a part of the F# core library.</span></span>

<span data-ttu-id="8763a-196">[オプションの種類](language-reference/options.md)は 2 つのケースのいずれかを表す型です: 値、またはまったくありません。</span><span class="sxs-lookup"><span data-stu-id="8763a-196">[The Option Type](language-reference/options.md) is a type which represents one of two cases: a value, or nothing at all.</span></span>  <span data-ttu-id="8763a-197">値が場合がありますか、特定の操作からならない可能性がありますのシナリオで使用されます。</span><span class="sxs-lookup"><span data-stu-id="8763a-197">It is used in any scenario where a value may or may not result from a particular operation.</span></span>  <span data-ttu-id="8763a-198">どちらの場合も、ランタイムの問題ではなく、コンパイル時の問題のためのアカウントに、必然です。</span><span class="sxs-lookup"><span data-stu-id="8763a-198">This then forces you to account for both cases, making it a compile-time concern rather than a runtime concern.</span></span>  <span data-ttu-id="8763a-199">Api でよく使用されます、`null`を代わりに、"nothing"を表す使用について心配する必要がなくなります`NullReferenceException`多くの場合。</span><span class="sxs-lookup"><span data-stu-id="8763a-199">These are often used in APIs where `null` is used to represent "nothing" instead, thus eliminating the need to worry about `NullReferenceException` in many circumstances.</span></span>

[!code-fsharp[Options](../../samples/snippets/fsharp/tour.fs#L789-L814)]

## <a name="units-of-measure"></a><span data-ttu-id="8763a-200">測定単位</span><span class="sxs-lookup"><span data-stu-id="8763a-200">Units of Measure</span></span>

<span data-ttu-id="8763a-201">F# の型システムの固有の機能を 1 つの単位を数値リテラルのコンテキストを提供する機能があります。</span><span class="sxs-lookup"><span data-stu-id="8763a-201">One unique feature of F#'s type system is the ability to provide context for numeric literals through Units of Measure.</span></span>

<span data-ttu-id="8763a-202">[測定単位](language-reference/units-of-measure.md)を使用すると、メートル単位などの単位に数値の種類の関連付けが関数を実行したり作業数値リテラルではなく、単位。</span><span class="sxs-lookup"><span data-stu-id="8763a-202">[Units of Measure](language-reference/units-of-measure.md) allow you to associate a numeric type to a unit, such as Meters, and have functions perform work on units rather than numeric literals.</span></span>  <span data-ttu-id="8763a-203">これにより、コンパイラに渡された数値リテラルの型によって、特定のコンテキストで意味が、これにより、ランタイム エラー、その種の作業に関連付けられていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="8763a-203">This enables the compiler to verify that the types of numeric literals passed in make sense under a certain context, thus eliminating runtime errors associated with that kind of work.</span></span>

[!code-fsharp[UnitsOfMeasure](../../samples/snippets/fsharp/tour.fs#L817-L842)]

<span data-ttu-id="8763a-204">F#コア ライブラリは、多くの SI 単位の種類および単位の変換を定義します。</span><span class="sxs-lookup"><span data-stu-id="8763a-204">The F# Core library defines many SI unit types and unit conversions.</span></span>  <span data-ttu-id="8763a-205">詳細についてにチェック アウト、 [Microsoft.FSharp.Data.UnitSystems.SI Namespace](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.data.unitsystems.si-namespace-%5bfsharp%5d)します。</span><span class="sxs-lookup"><span data-stu-id="8763a-205">To learn more, check out the [Microsoft.FSharp.Data.UnitSystems.SI Namespace](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.data.unitsystems.si-namespace-%5bfsharp%5d).</span></span>

## <a name="classes-and-interfaces"></a><span data-ttu-id="8763a-206">クラスとインターフェイス</span><span class="sxs-lookup"><span data-stu-id="8763a-206">Classes and Interfaces</span></span>

<span data-ttu-id="8763a-207">F#.NET のクラスの完全なサポートがあります[インターフェイス](language-reference/interfaces.md)、[抽象クラス](language-reference/abstract-classes.md)、[継承](language-reference/inheritance.md)など。</span><span class="sxs-lookup"><span data-stu-id="8763a-207">F# also has full support for .NET classes, [Interfaces](language-reference/interfaces.md), [Abstract Classes](language-reference/abstract-classes.md), [Inheritance](language-reference/inheritance.md), and so on.</span></span>

<span data-ttu-id="8763a-208">[クラス](language-reference/classes.md)は、.NET オブジェクトを表す型がプロパティ、メソッド、およびイベントであることができます、[メンバー](language-reference/members/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="8763a-208">[Classes](language-reference/classes.md) are types that represent .NET objects, which can have properties, methods, and events as its [Members](language-reference/members/index.md).</span></span>

[!code-fsharp[Classes](../../samples/snippets/fsharp/tour.fs#L845-L880)]

<span data-ttu-id="8763a-209">ジェネリック クラスの定義も非常に簡単です。</span><span class="sxs-lookup"><span data-stu-id="8763a-209">Defining generic classes is also very straightforward.</span></span>

[!code-fsharp[Classes](../../samples/snippets/fsharp/tour.fs#L883-L908)]

<span data-ttu-id="8763a-210">インターフェイスを実装する、いずれかを使用できる`interface ... with`構文または[オブジェクト式](language-reference/object-expressions.md)します。</span><span class="sxs-lookup"><span data-stu-id="8763a-210">To implement an Interface, you can use either `interface ... with` syntax or an [Object Expression](language-reference/object-expressions.md).</span></span>

[!code-fsharp[Classes](../../samples/snippets/fsharp/tour.fs#L911-L934)]

## <a name="which-types-to-use"></a><span data-ttu-id="8763a-211">使用する型</span><span class="sxs-lookup"><span data-stu-id="8763a-211">Which Types to Use</span></span>

<span data-ttu-id="8763a-212">クラス、レコード、判別共用体、およびタプルの存在が重要な質問につながります。 使用すべきでしょうか。</span><span class="sxs-lookup"><span data-stu-id="8763a-212">The presence of Classes, Records, Discriminated Unions, and Tuples leads to an important question: which should you use?</span></span>  <span data-ttu-id="8763a-213">ほとんどライフで、すべてのように、答えは、状況によって異なります。</span><span class="sxs-lookup"><span data-stu-id="8763a-213">Like most everything in life, the answer depends on your circumstances.</span></span>

<span data-ttu-id="8763a-214">タプルは、関数から複数の値を返すおよびアドホック集計値の集計を使用して、自体の値として適しています。</span><span class="sxs-lookup"><span data-stu-id="8763a-214">Tuples are great for returning multiple values from a function, and using an ad-hoc aggregate of values as a value itself.</span></span>

<span data-ttu-id="8763a-215">レコードは、"からのステップ アップ"組、ラベルと省略可能なメンバーのサポートということです。</span><span class="sxs-lookup"><span data-stu-id="8763a-215">Records are a "step up" from Tuples, having named labels and support for optional members.</span></span>  <span data-ttu-id="8763a-216">データ転送中のプログラムを儀礼的表現に適しています。</span><span class="sxs-lookup"><span data-stu-id="8763a-216">They are great for a low-ceremony representation of data in-transit through your program.</span></span>  <span data-ttu-id="8763a-217">構造の等値があるため比較で簡単に使用されます。</span><span class="sxs-lookup"><span data-stu-id="8763a-217">Because they have structural equality, they are easy to use with comparison.</span></span>

<span data-ttu-id="8763a-218">判別共用体は数多くの用途がコア特典がアカウントのすべての可能な「図形」ことができるデータに一致するパターンと組み合わせて利用するため可能になります。</span><span class="sxs-lookup"><span data-stu-id="8763a-218">Discriminated Unions have many uses, but the core benefit is to be able to utilize them in conjunction with Pattern Matching to account for all possible "shapes" that a data can have.</span></span>  

<span data-ttu-id="8763a-219">クラスは、情報を表すしても機能するには、その情報を関連付ける必要がある場合などの理由の数が膨大に適しています。</span><span class="sxs-lookup"><span data-stu-id="8763a-219">Classes are great for a huge number of reasons, such as when you need to represent information and also tie that information to functionality.</span></span>  <span data-ttu-id="8763a-220">ルールの一般的に、概念的には、一部のデータに関連する機能がある場合は、大きな利点にはクラスとオブジェクト指向プログラミングの原則を使用してます。</span><span class="sxs-lookup"><span data-stu-id="8763a-220">As a rule of thumb, when you have functionality which is conceptually tied to some data, using Classes and the principles of Object-Oriented Programming is a big benefit.</span></span>  <span data-ttu-id="8763a-221">クラスも優先されるデータ型 c# と Visual Basic での相互運用するときにこれらの言語では、ほぼすべてのクラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="8763a-221">Classes are also the preferred data type when interoperating with C# and Visual Basic, as these languages use classes for nearly everything.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8763a-222">次の手順</span><span class="sxs-lookup"><span data-stu-id="8763a-222">Next Steps</span></span>

<span data-ttu-id="8763a-223">言語の主な機能のいくつかを確認したらには、最初の F# プログラムを作成できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8763a-223">Now that you've seen some of the primary features of the language, you should be ready to write your first F# programs!</span></span>  <span data-ttu-id="8763a-224">チェック アウト[Getting Started](tutorials/getting-started/index.md)に開発環境を設定して、コードを記述する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8763a-224">Check out [Getting Started](tutorials/getting-started/index.md) to learn how to set up your development environment and write some code.</span></span>

<span data-ttu-id="8763a-225">詳細は次の手順は任意できますが、お勧めします[で関数型プログラミングの概要F#](introduction-to-functional-programming/index.md)コア関数型プログラミングの概念に慣れるにします。</span><span class="sxs-lookup"><span data-stu-id="8763a-225">The next steps for learning more can be whatever you like, but we recommend [Introduction to Functional Programming in F#](introduction-to-functional-programming/index.md) to get comfortable with core Functional Programming concepts.</span></span>  <span data-ttu-id="8763a-226">これらは、F# で堅牢なアプリケーションの構築に不可欠になります。</span><span class="sxs-lookup"><span data-stu-id="8763a-226">These will be essential in building robust programs in F#.</span></span>

<span data-ttu-id="8763a-227">また、チェック アウト、 [F# 言語リファレンス](language-reference/index.md)を F# の概念的なコンテンツの包括的なコレクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8763a-227">Also, check out the [F# Language Reference](language-reference/index.md) to see a comprehensive collection of conceptual content on F#.</span></span>
