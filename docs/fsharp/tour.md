---
title: F# のツアー
description: このツアーのF#プログラミング言語の主な機能のいくつかを、コードサンプルで確認します。
ms.date: 11/06/2018
ms.openlocfilehash: cfea2827dcec65f9e3606e8528179029e1f2db84
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423805"
---
# <a name="tour-of-f"></a><span data-ttu-id="ca276-103">F\# のツアー</span><span class="sxs-lookup"><span data-stu-id="ca276-103">Tour of F\#</span></span>

<span data-ttu-id="ca276-104">F# について学習する最善の方法は、F# コードを読み書きすることです。</span><span class="sxs-lookup"><span data-stu-id="ca276-104">The best way to learn about F# is to read and write F# code.</span></span> <span data-ttu-id="ca276-105">この記事は、F# 言語のいくつかの主な機能の手引きとしての役割を果たし、コンピューターで実行できるいくつかのコード スニペットを示します。</span><span class="sxs-lookup"><span data-stu-id="ca276-105">This article will act as a tour through some of the key features of the F# language and give you some code snippets that you can execute on your machine.</span></span> <span data-ttu-id="ca276-106">開発環境を設定する方法については、[Getting Started](get-started/index.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca276-106">To learn about setting up a development environment, check out [Getting Started](get-started/index.md).</span></span>

<span data-ttu-id="ca276-107">には、関数と型F#という2つの主要な概念があります。</span><span class="sxs-lookup"><span data-stu-id="ca276-107">There are two primary concepts in F#: functions and types.</span></span>  <span data-ttu-id="ca276-108">このツアーでは、この2つの概念に分類される言語の機能に重点を置いています。</span><span class="sxs-lookup"><span data-stu-id="ca276-108">This tour will emphasize features of the language which fall into these two concepts.</span></span>

## <a name="executing-the-code-online"></a><span data-ttu-id="ca276-109">コードをオンラインで実行する</span><span class="sxs-lookup"><span data-stu-id="ca276-109">Executing the code online</span></span>

<span data-ttu-id="ca276-110">コンピューターに F# がインストールされていない場合は、[WebAssembly におけるF# の使用](https://tryfsharp.fsbolero.io/) をブラウザーですべてのサンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="ca276-110">If you don't have F# installed on your machine, you can execute all of the samples in your browser with [Try F# on WebAssembly](https://tryfsharp.fsbolero.io/).</span></span> <span data-ttu-id="ca276-111">Fable は、ブラウザーで直接実行されるF# の言語です。</span><span class="sxs-lookup"><span data-stu-id="ca276-111">Fable is a dialect of F# that executes directly in your browser.</span></span> <span data-ttu-id="ca276-112">REPL の後に続くサンプルを確認するには、Fable REPL の左側のメニューバーにある  **サンプル> 学習 > F＃のツアー** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca276-112">To view the samples that follow in the REPL, check out **Samples > Learn > Tour of F#** in the left-hand menu bar of the Fable REPL.</span></span>

## <a name="functions-and-modules"></a><span data-ttu-id="ca276-113">関数とモジュール</span><span class="sxs-lookup"><span data-stu-id="ca276-113">Functions and Modules</span></span>

<span data-ttu-id="ca276-114">任意の F# プログラムの最も基本的な部分が***関数***編成***モジュール***します。</span><span class="sxs-lookup"><span data-stu-id="ca276-114">The most fundamental pieces of any F# program are ***functions*** organized into ***modules***.</span></span>  <span data-ttu-id="ca276-115">[関数](./language-reference/functions/index.md)出力を生成する入力に作業を実行し、で構成される[モジュール](./language-reference/modules.md)、F# でグループ化する主な方法であります。</span><span class="sxs-lookup"><span data-stu-id="ca276-115">[Functions](./language-reference/functions/index.md) perform work on inputs to produce outputs, and they are organized under [Modules](./language-reference/modules.md), which are the primary way you group things in F#.</span></span>  <span data-ttu-id="ca276-116">これらは[`let` バインディング](./language-reference/functions/let-bindings.md)を使用して定義されます。これにより、関数に名前を付け、引数を定義します。</span><span class="sxs-lookup"><span data-stu-id="ca276-116">They are defined using the [`let` binding](./language-reference/functions/let-bindings.md), which give the function a name and define its arguments.</span></span>

[!code-fsharp[BasicFunctions](~/samples/snippets/fsharp/tour.fs#L101-L133)]

<span data-ttu-id="ca276-117">`let` バインドは、他の言語の変数と同様に、値を名前にバインドする方法でもあります。</span><span class="sxs-lookup"><span data-stu-id="ca276-117">`let` bindings are also how you bind a value to a name, similar to a variable in other languages.</span></span>  <span data-ttu-id="ca276-118">`let` バインディングは、既定で***は変更でき***ません。つまり、値または関数が名前にバインドされると、その代わりに変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="ca276-118">`let` bindings are ***immutable*** by default, which means that once a value or function is bound to a name, it cannot be changed in-place.</span></span>  <span data-ttu-id="ca276-119">これは、変更可能な他の言語の変数と***は対照的***です。つまり、値は任意の時点で変更できます。</span><span class="sxs-lookup"><span data-stu-id="ca276-119">This is in contrast to variables in other languages, which are ***mutable***, meaning their values can be changed at any point in time.</span></span>  <span data-ttu-id="ca276-120">変更可能なバインドが必要な場合は、`let mutable ...` 構文を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ca276-120">If you require a mutable binding, you can use `let mutable ...` syntax.</span></span>

[!code-fsharp[Immutability](~/samples/snippets/fsharp/tour.fs#L75-L94)]

## <a name="numbers-booleans-and-strings"></a><span data-ttu-id="ca276-121">数値、ブール値、および文字列</span><span class="sxs-lookup"><span data-stu-id="ca276-121">Numbers, Booleans, and Strings</span></span>

<span data-ttu-id="ca276-122">.NET 言語として F# をサポートしています、同じ基になる[プリミティブ型](language-reference/basic-types.md).NET 内に存在します。</span><span class="sxs-lookup"><span data-stu-id="ca276-122">As a .NET language, F# supports the same underlying [primitive types](language-reference/basic-types.md) that exist in .NET.</span></span>

<span data-ttu-id="ca276-123">さまざまな数値型は F# で表されます。 次に示します。</span><span class="sxs-lookup"><span data-stu-id="ca276-123">Here is how various numeric types are represented in F#:</span></span>

[!code-fsharp[Numbers](~/samples/snippets/fsharp/tour.fs#L49-L68)]

<span data-ttu-id="ca276-124">次に、ブール値と基本的な条件ロジックの実行例を示します。</span><span class="sxs-lookup"><span data-stu-id="ca276-124">Here's what Boolean values and performing basic conditional logic looks like:</span></span>

[!code-fsharp[Bools](~/samples/snippets/fsharp/tour.fs#L142-L152)]

<span data-ttu-id="ca276-125">基本的な[文字列](./language-reference/strings.md)操作は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="ca276-125">And here's what basic [string](./language-reference/strings.md) manipulation looks like:</span></span>

[!code-fsharp[Strings](~/samples/snippets/fsharp/tour.fs#L158-L180)]

## <a name="tuples"></a><span data-ttu-id="ca276-126">タプル</span><span class="sxs-lookup"><span data-stu-id="ca276-126">Tuples</span></span>

<span data-ttu-id="ca276-127">[タプル](./language-reference/tuples.md)は F# の大きな問題です。</span><span class="sxs-lookup"><span data-stu-id="ca276-127">[Tuples](./language-reference/tuples.md) are a big deal in F#.</span></span>  <span data-ttu-id="ca276-128">これらは名前のない、順序付けされた値をグループ化したもので、値自体として扱うことができます。</span><span class="sxs-lookup"><span data-stu-id="ca276-128">They are a grouping of unnamed, but ordered values, that can be treated as values themselves.</span></span>  <span data-ttu-id="ca276-129">これらは、他の値から集計された値と考えることができます。</span><span class="sxs-lookup"><span data-stu-id="ca276-129">Think of them as values which are aggregated from other values.</span></span>  <span data-ttu-id="ca276-130">多くの用途があります。たとえば、関数から複数の値を返すことができるようにしたり、特別な便宜を行うために値をグループ化したりします。</span><span class="sxs-lookup"><span data-stu-id="ca276-130">They have many uses, such as conveniently returning multiple values from a function, or grouping values for some ad-hoc convenience.</span></span>

[!code-fsharp[Tuples](~/samples/snippets/fsharp/tour.fs#L186-L203)]

<span data-ttu-id="ca276-131">4\.1 のF#ように、`struct` 組を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="ca276-131">As of F# 4.1, you can also create `struct` tuples.</span></span>  <span data-ttu-id="ca276-132">これらは、C# 7/Visual Basic 15 組で完全に相互運用することもできます。タプルも `struct` ます。</span><span class="sxs-lookup"><span data-stu-id="ca276-132">These also interoperate fully with C#7/Visual Basic 15 tuples, which are also `struct` tuples:</span></span>

[!code-fsharp[Tuples](~/samples/snippets/fsharp/tour.fs#L205-L218)]

<span data-ttu-id="ca276-133">`struct` 組は値型であるため、暗黙的に参照タプルに変換することはできず、その逆も可能であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ca276-133">It's important to note that because `struct` tuples are value types, they cannot be implicitly converted to reference tuples, or vice versa.</span></span>  <span data-ttu-id="ca276-134">参照と構造体の組の間で明示的に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca276-134">You must explicitly convert between a reference and struct tuple.</span></span>

## <a name="pipelines-and-composition"></a><span data-ttu-id="ca276-135">パイプラインとコンポジション</span><span class="sxs-lookup"><span data-stu-id="ca276-135">Pipelines and Composition</span></span>

<span data-ttu-id="ca276-136">などの演算子をパイプ`|>`F# でのデータを処理するときに広く使用されます。</span><span class="sxs-lookup"><span data-stu-id="ca276-136">Pipe operators such as `|>` are used extensively when processing data in F#.</span></span> <span data-ttu-id="ca276-137">これらの演算子は、関数の "パイプライン" を柔軟な方法で確立できるようにする関数です。</span><span class="sxs-lookup"><span data-stu-id="ca276-137">These operators are functions that allow you to establish "pipelines" of functions in a flexible manner.</span></span> <span data-ttu-id="ca276-138">次の例では、これらの演算子を利用して単純な機能パイプラインを構築する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca276-138">The following example walks through how you can take advantage of these operators to build a simple functional pipeline:</span></span>

[!code-fsharp[Pipelines](~/samples/snippets/fsharp/tour.fs#L227-L282)]

<span data-ttu-id="ca276-139">行われる前のサンプルの F# では、リスト処理関数をファーストクラスの関数を含む多くの機能の使用と[部分適用](./language-reference/functions/index.md#partial-application-of-arguments)します。</span><span class="sxs-lookup"><span data-stu-id="ca276-139">The previous sample made use of many features of F#, including list processing functions, first-class functions, and [partial application](./language-reference/functions/index.md#partial-application-of-arguments).</span></span> <span data-ttu-id="ca276-140">これらの概念を深く理解することは少し高度になる可能性がありますが、パイプラインを構築するときに、簡単に関数を使用してデータを処理する方法を明確にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca276-140">Although a deep understanding of each of those concepts can become somewhat advanced, it should be clear how easily functions can be used to process data when building pipelines.</span></span>

## <a name="lists-arrays-and-sequences"></a><span data-ttu-id="ca276-141">リスト、配列、およびシーケンス</span><span class="sxs-lookup"><span data-stu-id="ca276-141">Lists, Arrays, and Sequences</span></span>

<span data-ttu-id="ca276-142">リスト、配列、およびシーケンスは、F# コア ライブラリの次の 3 つのプライマリ コレクション型です。</span><span class="sxs-lookup"><span data-stu-id="ca276-142">Lists, Arrays, and Sequences are three primary collection types in the F# core library.</span></span>

<span data-ttu-id="ca276-143">[リスト](./language-reference/lists.md)は、同じ型の要素の順序付けられ、変更できないコレクションです。</span><span class="sxs-lookup"><span data-stu-id="ca276-143">[Lists](./language-reference/lists.md) are ordered, immutable collections of elements of the same type.</span></span>  <span data-ttu-id="ca276-144">これらはシングルリンクリストです。つまり、列挙型であることを意味しますが、サイズが大きい場合はランダムアクセスと連結には適していません。</span><span class="sxs-lookup"><span data-stu-id="ca276-144">They are singly-linked lists, which means they are meant for enumeration, but a poor choice for random access and concatenation if they're large.</span></span>  <span data-ttu-id="ca276-145">これは、一般的には、リストを表すために単一リンクリストを使用しない他の一般的な言語の一覧とは対照的です。</span><span class="sxs-lookup"><span data-stu-id="ca276-145">This in contrast to Lists in other popular languages, which typically do not use a singly-linked list to represent Lists.</span></span>

[!code-fsharp[Lists](~/samples/snippets/fsharp/tour.fs#L309-L359)]

<span data-ttu-id="ca276-146">[配列](./language-reference/arrays.md)は、同じ型の要素の固定*サイズの変更可能なコレクションです*。</span><span class="sxs-lookup"><span data-stu-id="ca276-146">[Arrays](./language-reference/arrays.md) are fixed-size, *mutable* collections of elements of the same type.</span></span>  <span data-ttu-id="ca276-147">要素の高速なランダム アクセスをサポートし、F# リストのメモリ ブロックが連続するだけであるためよりも高速化されます。</span><span class="sxs-lookup"><span data-stu-id="ca276-147">They support fast random access of elements, and are faster than F# lists because they are just contiguous blocks of memory.</span></span>

[!code-fsharp[Arrays](~/samples/snippets/fsharp/tour.fs#L368-L407)]

<span data-ttu-id="ca276-148">[シーケンス](./language-reference/sequences.md)は、すべて同じ型の論理的な一連の要素です。</span><span class="sxs-lookup"><span data-stu-id="ca276-148">[Sequences](./language-reference/sequences.md) are a logical series of elements, all of the same type.</span></span>  <span data-ttu-id="ca276-149">これらは、リストや配列よりも一般的な型であり、任意の論理シリーズの要素に "表示" できるようになっています。</span><span class="sxs-lookup"><span data-stu-id="ca276-149">These are a more general type than Lists and Arrays, capable of being your "view" into any logical series of elements.</span></span>  <span data-ttu-id="ca276-150">また、***遅延***がある可能性があるため、このような場合もあります。これは、要素が必要な場合にのみ計算できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="ca276-150">They also stand out because they can be ***lazy***, which means that elements can be computed only when they are needed.</span></span>

[!code-fsharp[Sequences](~/samples/snippets/fsharp/tour.fs#L418-L452)]

## <a name="recursive-functions"></a><span data-ttu-id="ca276-151">再帰関数</span><span class="sxs-lookup"><span data-stu-id="ca276-151">Recursive Functions</span></span>

<span data-ttu-id="ca276-152">コレクションまたは要素のシーケンス処理で通常実行[再帰](./language-reference/functions/index.md#recursive-functions)F# でします。</span><span class="sxs-lookup"><span data-stu-id="ca276-152">Processing collections or sequences of elements is typically done with [recursion](./language-reference/functions/index.md#recursive-functions) in F#.</span></span>  <span data-ttu-id="ca276-153">にF#はループと命令型プログラミングがサポートされていますが、正確性を保証するのが簡単であるため、再帰が推奨されています。</span><span class="sxs-lookup"><span data-stu-id="ca276-153">Although F# has support for loops and imperative programming, recursion is preferred because it is easier to guarantee correctness.</span></span>

> [!NOTE]
> <span data-ttu-id="ca276-154">次の例では、`match` 式を使用してパターンマッチングを使用します。</span><span class="sxs-lookup"><span data-stu-id="ca276-154">The following example makes use of the pattern matching via the `match` expression.</span></span>  <span data-ttu-id="ca276-155">この基本的な構成要素については、この記事の後半で説明します。</span><span class="sxs-lookup"><span data-stu-id="ca276-155">This fundamental construct is covered later in this article.</span></span>

[!code-fsharp[RecursiveFunctions](~/samples/snippets/fsharp/tour.fs#L461-L500)]

<span data-ttu-id="ca276-156">F#では、末尾呼び出しの最適化も完全にサポートされています。これは、再帰呼び出しを最適化してループ構造と同じ速度にすることができるようにするための方法です。</span><span class="sxs-lookup"><span data-stu-id="ca276-156">F# also has full support for Tail Call Optimization, which is a way to optimize recursive calls so that they are just as fast as a loop construct.</span></span>

## <a name="record-and-discriminated-union-types"></a><span data-ttu-id="ca276-157">レコードと判別共用体型</span><span class="sxs-lookup"><span data-stu-id="ca276-157">Record and Discriminated Union Types</span></span>

<span data-ttu-id="ca276-158">レコード、共用体の型は、F# コードで使用される 2 つの基本的なデータ型を一般に、F# プログラムでデータを表現する最善の方法は。</span><span class="sxs-lookup"><span data-stu-id="ca276-158">Record and Union types are two fundamental data types used in F# code, and are generally the best way to represent data in an F# program.</span></span>  <span data-ttu-id="ca276-159">これは他の言語のクラスと似ていますが、主な違いの1つは、構造上の等価性があることです。</span><span class="sxs-lookup"><span data-stu-id="ca276-159">Although this makes them similar to classes in other languages, one of their primary differences is that they have structural equality semantics.</span></span>  <span data-ttu-id="ca276-160">つまり、これらは "ネイティブな" 比較可能であり、等価性が簡単であることを意味します。一方が等しいかどうかを確認するだけです。</span><span class="sxs-lookup"><span data-stu-id="ca276-160">This means that they are "natively" comparable and equality is straightforward - just check if one is equal to the other.</span></span>

<span data-ttu-id="ca276-161">[レコード](./language-reference/records.md)は、名前付きの値の集合であり、オプションのメンバー (メソッドなど) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ca276-161">[Records](./language-reference/records.md) are an aggregate of named values, with optional members (such as methods).</span></span>  <span data-ttu-id="ca276-162">C#または Java に慣れている場合、これらは、構造的な等価性が少なく、手続きが少ない、pocos または pojo に似ています。</span><span class="sxs-lookup"><span data-stu-id="ca276-162">If you're familiar with C# or Java, then these should feel similar to POCOs or POJOs - just with structural equality and less ceremony.</span></span>

[!code-fsharp[Records](~/samples/snippets/fsharp/tour.fs#L507-L559)]

<span data-ttu-id="ca276-163">4\.1 のF#ように、レコードを `struct`s として表すこともできます。</span><span class="sxs-lookup"><span data-stu-id="ca276-163">As of F# 4.1, you can also represent Records as `struct`s.</span></span>  <span data-ttu-id="ca276-164">これは、`[<Struct>]` 属性を使用して行います。</span><span class="sxs-lookup"><span data-stu-id="ca276-164">This is done with the `[<Struct>]` attribute:</span></span>

[!code-fsharp[Records](~/samples/snippets/fsharp/tour.fs#L561-L568)]

<span data-ttu-id="ca276-165">[判別共用体 (du)](./language-reference/discriminated-unions.md)は、多数の名前付きフォームまたはケースである可能性がある値です。</span><span class="sxs-lookup"><span data-stu-id="ca276-165">[Discriminated Unions (DUs)](./language-reference/discriminated-unions.md) are values which could be a number of named forms or cases.</span></span>  <span data-ttu-id="ca276-166">型に格納されるデータは、複数の個別の値のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="ca276-166">Data stored in the type can be one of several distinct values.</span></span>

[!code-fsharp[Unions](~/samples/snippets/fsharp/tour.fs#L575-L631)]

<span data-ttu-id="ca276-167">また、Du を*シングルケース判別共用体*として使用して、プリミティブ型に対するドメインモデリングを支援することもできます。</span><span class="sxs-lookup"><span data-stu-id="ca276-167">You can also use DUs as *Single-Case Discriminated Unions*, to help with domain modeling over primitive types.</span></span>  <span data-ttu-id="ca276-168">多くの場合、文字列やその他のプリミティブ型を使用して何かを表しているため、特定の意味が与えられます。</span><span class="sxs-lookup"><span data-stu-id="ca276-168">Often times, strings and other primitive types are used to represent something, and are thus given a particular meaning.</span></span>  <span data-ttu-id="ca276-169">ただし、データのプリミティブ表現のみを使用すると、誤った値が誤って割り当てられる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ca276-169">However, using only the primitive representation of the data can result in mistakenly assigning an incorrect value!</span></span>  <span data-ttu-id="ca276-170">このシナリオでは、各種類の情報を個別の単一ケース共用体として表すことができます。</span><span class="sxs-lookup"><span data-stu-id="ca276-170">Representing each type of information as a distinct single-case union can enforce correctness in this scenario.</span></span>

[!code-fsharp[Unions](~/samples/snippets/fsharp/tour.fs#L633-L654)]

<span data-ttu-id="ca276-171">上の例で示すように、単一ケースの判別共用体の基になる値を取得するには、明示的にラップ解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca276-171">As the above sample demonstrates, to get the underlying value in a single-case Discriminated Union, you must explicitly unwrap it.</span></span>

<span data-ttu-id="ca276-172">また、Du は再帰的な定義もサポートしているので、ツリーや本質的に再帰的なデータを簡単に表すことができます。</span><span class="sxs-lookup"><span data-stu-id="ca276-172">Additionally, DUs also support recursive definitions, allowing you to easily represent trees and inherently recursive data.</span></span>  <span data-ttu-id="ca276-173">たとえば、`exists` と `insert` 関数を含むバイナリ検索ツリーを表現する方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ca276-173">For example, here's how you can represent a Binary Search Tree with `exists` and `insert` functions.</span></span>

[!code-fsharp[Unions](~/samples/snippets/fsharp/tour.fs#L656-L683)]

<span data-ttu-id="ca276-174">Du では、データ型のツリーの再帰構造を表すことができるため、この再帰構造での操作は簡単で、正確性が保証されます。</span><span class="sxs-lookup"><span data-stu-id="ca276-174">Because DUs allow you to represent the recursive structure of the tree in the data type, operating on this recursive structure is straightforward and guarantees correctness.</span></span>  <span data-ttu-id="ca276-175">次に示すように、パターンマッチングでもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ca276-175">It is also supported in pattern matching, as shown below.</span></span>

<span data-ttu-id="ca276-176">また、`[<Struct>]` 属性を使用して、`struct`s として Du を表すことができます。</span><span class="sxs-lookup"><span data-stu-id="ca276-176">Additionally, you can represent DUs as `struct`s with the `[<Struct>]` attribute:</span></span>

[!code-fsharp[Unions](~/samples/snippets/fsharp/tour.fs#L685-L696)]

<span data-ttu-id="ca276-177">ただし、その場合は、次の2つの点に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca276-177">However, there are two key things to keep in mind when doing so:</span></span>

1. <span data-ttu-id="ca276-178">Struct DU を再帰的に定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="ca276-178">A struct DU cannot be recursively-defined.</span></span>
2. <span data-ttu-id="ca276-179">Struct DU は、それぞれのケースに対して一意の名前を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca276-179">A struct DU must have unique names for each of its cases.</span></span>

<span data-ttu-id="ca276-180">上記に従わないと、コンパイルエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="ca276-180">Failure to follow the above will result in a compilation error.</span></span>

## <a name="pattern-matching"></a><span data-ttu-id="ca276-181">パターン マッチ</span><span class="sxs-lookup"><span data-stu-id="ca276-181">Pattern Matching</span></span>

<span data-ttu-id="ca276-182">[パターン照合](./language-reference/pattern-matching.md)により、F# の型に対する操作のための正確性が F# 言語機能です。</span><span class="sxs-lookup"><span data-stu-id="ca276-182">[Pattern Matching](./language-reference/pattern-matching.md) is the F# language feature which enables correctness for operating on F# types.</span></span>  <span data-ttu-id="ca276-183">上記のサンプルでは、`match x with ...` 構文が非常に複雑であることに気付きます。</span><span class="sxs-lookup"><span data-stu-id="ca276-183">In the above samples, you probably noticed quite a bit of `match x with ...` syntax.</span></span>  <span data-ttu-id="ca276-184">このコンストラクトを使用すると、コンパイラはデータ型の "形状" を理解でき、完全なパターンマッチングとして知られているデータ型を使用する場合に、すべてのケースを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca276-184">This construct allows the compiler, which can understand the "shape" of data types, to force you to account for all possible cases when using a data type through what is known as Exhaustive Pattern Matching.</span></span>  <span data-ttu-id="ca276-185">これは、正確さを実現するために非常に強力であり、通常はランタイムの問題としてコンパイル時に巧妙を "リフト" するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="ca276-185">This is incredibly powerful for correctness, and can be cleverly used to "lift" what would normally be a runtime concern into compile-time.</span></span>

[!code-fsharp[PatternMatching](~/samples/snippets/fsharp/tour.fs#L705-L742)]

<span data-ttu-id="ca276-186">ご存知かもしれませんが、`_` パターンを使用しています。</span><span class="sxs-lookup"><span data-stu-id="ca276-186">Something you may have noticed is the use of the `_` pattern.</span></span>  <span data-ttu-id="ca276-187">これは、[ワイルドカードパターン](./language-reference/pattern-matching.md#wildcard-pattern)と呼ばれます。これは、"何が何であるかを気にしない" と言うことができます。</span><span class="sxs-lookup"><span data-stu-id="ca276-187">This is known as the [Wildcard Pattern](./language-reference/pattern-matching.md#wildcard-pattern), which is a way of saying "I don't care what something is".</span></span>  <span data-ttu-id="ca276-188">便利ですが、`_`を使用することに注意していない場合は、完全なパターンマッチングを誤ってバイパスし、コンパイル時の実施からメリットを得られなくなりました。</span><span class="sxs-lookup"><span data-stu-id="ca276-188">Although convenient, you can accidentally bypass Exhaustive Pattern Matching and no longer benefit from compile-time enforcements if you aren't careful in using `_`.</span></span>  <span data-ttu-id="ca276-189">パターンマッチングの際に分解された型の特定の部分を気にしない場合、またはパターン一致式ですべての意味のあるケースを列挙した場合は final 句を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ca276-189">It is best used when you don't care about certain pieces of a decomposed type when pattern matching, or the final clause when you have enumerated all meaningful cases in a pattern matching expression.</span></span>

<span data-ttu-id="ca276-190">[アクティブパターン](./language-reference/active-patterns.md)は、パターンマッチングで使用するもう1つの強力な構成要素です。</span><span class="sxs-lookup"><span data-stu-id="ca276-190">[Active Patterns](./language-reference/active-patterns.md) are another powerful construct to use with pattern matching.</span></span>  <span data-ttu-id="ca276-191">これにより、入力データをカスタムフォームに分割し、パターンマッチ呼び出しサイトで分解することができます。</span><span class="sxs-lookup"><span data-stu-id="ca276-191">They allow you to partition input data into custom forms, decomposing them at the pattern match call site.</span></span>  <span data-ttu-id="ca276-192">また、パラメーター化して、がパーティションを関数として定義できるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="ca276-192">They can also be parameterized, thus allowing to define the partition as a function.</span></span>  <span data-ttu-id="ca276-193">アクティブなパターンをサポートするために前の例を拡張すると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="ca276-193">Expanding the previous example to support Active Patterns looks something like this:</span></span>

[!code-fsharp[ActivePatterns](~/samples/snippets/fsharp/tour.fs#L764-L786)]

## <a name="optional-types"></a><span data-ttu-id="ca276-194">省略可能な型</span><span class="sxs-lookup"><span data-stu-id="ca276-194">Optional Types</span></span>

<span data-ttu-id="ca276-195">判別共用体の型の 1 つの特殊なケースは非常に役立つ、F# コア ライブラリの一部であるあるオプションの種類です。</span><span class="sxs-lookup"><span data-stu-id="ca276-195">One special case of Discriminated Union types is the Option Type, which is so useful that it's a part of the F# core library.</span></span>

<span data-ttu-id="ca276-196">[オプションの種類](./language-reference/options.md)は、値または nothing の2つのケースのいずれかを表す型です。</span><span class="sxs-lookup"><span data-stu-id="ca276-196">[The Option Type](./language-reference/options.md) is a type which represents one of two cases: a value, or nothing at all.</span></span>  <span data-ttu-id="ca276-197">このメソッドは、特定の操作の結果として値が異なる可能性がある場合に、どのようなシナリオでも使用されます。</span><span class="sxs-lookup"><span data-stu-id="ca276-197">It is used in any scenario where a value may or may not result from a particular operation.</span></span>  <span data-ttu-id="ca276-198">これにより、実行時の問題ではなく、コンパイル時の問題になるように、両方のケースを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca276-198">This then forces you to account for both cases, making it a compile-time concern rather than a runtime concern.</span></span>  <span data-ttu-id="ca276-199">これらは多くの場合、`null` が "nothing" を表すために使用される Api で使用されるため、多くの状況で `NullReferenceException` を気にする必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="ca276-199">These are often used in APIs where `null` is used to represent "nothing" instead, thus eliminating the need to worry about `NullReferenceException` in many circumstances.</span></span>

[!code-fsharp[Options](~/samples/snippets/fsharp/tour.fs#L789-L814)]

## <a name="units-of-measure"></a><span data-ttu-id="ca276-200">測定単位</span><span class="sxs-lookup"><span data-stu-id="ca276-200">Units of Measure</span></span>

<span data-ttu-id="ca276-201">F# の型システムの固有の機能を 1 つの単位を数値リテラルのコンテキストを提供する機能があります。</span><span class="sxs-lookup"><span data-stu-id="ca276-201">One unique feature of F#'s type system is the ability to provide context for numeric literals through Units of Measure.</span></span>

<span data-ttu-id="ca276-202">[測定単位](./language-reference/units-of-measure.md)を使用すると、数値型をメートル単位に関連付けることができます。また、関数は数値リテラルではなく単位で作業を実行します。</span><span class="sxs-lookup"><span data-stu-id="ca276-202">[Units of Measure](./language-reference/units-of-measure.md) allow you to associate a numeric type to a unit, such as Meters, and have functions perform work on units rather than numeric literals.</span></span>  <span data-ttu-id="ca276-203">これにより、コンパイラは、渡された数値リテラルの型が特定のコンテキストで意味を持つかどうかを検証できるため、そのような作業に関連するランタイムエラーを回避できます。</span><span class="sxs-lookup"><span data-stu-id="ca276-203">This enables the compiler to verify that the types of numeric literals passed in make sense under a certain context, thus eliminating runtime errors associated with that kind of work.</span></span>

[!code-fsharp[UnitsOfMeasure](~/samples/snippets/fsharp/tour.fs#L817-L842)]

<span data-ttu-id="ca276-204">コアF#ライブラリでは、さまざまな SI 単位の型と単位の変換が定義されています。</span><span class="sxs-lookup"><span data-stu-id="ca276-204">The F# Core library defines many SI unit types and unit conversions.</span></span>  <span data-ttu-id="ca276-205">詳細については、 [Microsoft.FSharp.Data.UnitSystems.SI 名前空間](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.data.unitsystems.si-namespace-%5bfsharp%5d)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="ca276-205">To learn more, check out the [Microsoft.FSharp.Data.UnitSystems.SI Namespace](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.data.unitsystems.si-namespace-%5bfsharp%5d).</span></span>

## <a name="classes-and-interfaces"></a><span data-ttu-id="ca276-206">クラスとインターフェイス</span><span class="sxs-lookup"><span data-stu-id="ca276-206">Classes and Interfaces</span></span>

<span data-ttu-id="ca276-207">F#では、.NET クラス、[インターフェイス](./language-reference/interfaces.md)、[抽象クラス](./language-reference/abstract-classes.md)、[継承](./language-reference/inheritance.md)なども完全にサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ca276-207">F# also has full support for .NET classes, [Interfaces](./language-reference/interfaces.md), [Abstract Classes](./language-reference/abstract-classes.md), [Inheritance](./language-reference/inheritance.md), and so on.</span></span>

<span data-ttu-id="ca276-208">[クラス](./language-reference/classes.md)は、プロパティ、メソッド、およびイベントを[メンバー](./language-reference/members/index.md)として持つことができる .net オブジェクトを表す型です。</span><span class="sxs-lookup"><span data-stu-id="ca276-208">[Classes](./language-reference/classes.md) are types that represent .NET objects, which can have properties, methods, and events as its [Members](./language-reference/members/index.md).</span></span>

[!code-fsharp[Classes](~/samples/snippets/fsharp/tour.fs#L845-L880)]

<span data-ttu-id="ca276-209">ジェネリッククラスを定義することも、非常に簡単です。</span><span class="sxs-lookup"><span data-stu-id="ca276-209">Defining generic classes is also very straightforward.</span></span>

[!code-fsharp[Classes](~/samples/snippets/fsharp/tour.fs#L883-L908)]

<span data-ttu-id="ca276-210">インターフェイスを実装するには、`interface ... with` 構文または[オブジェクト式](./language-reference/object-expressions.md)のいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ca276-210">To implement an Interface, you can use either `interface ... with` syntax or an [Object Expression](./language-reference/object-expressions.md).</span></span>

[!code-fsharp[Classes](~/samples/snippets/fsharp/tour.fs#L911-L934)]

## <a name="which-types-to-use"></a><span data-ttu-id="ca276-211">使用する型</span><span class="sxs-lookup"><span data-stu-id="ca276-211">Which Types to Use</span></span>

<span data-ttu-id="ca276-212">クラス、レコード、判別共用体、および組が存在すると、重要な質問につながります。</span><span class="sxs-lookup"><span data-stu-id="ca276-212">The presence of Classes, Records, Discriminated Unions, and Tuples leads to an important question: which should you use?</span></span>  <span data-ttu-id="ca276-213">多くの場合、その答えは状況によって異なります。</span><span class="sxs-lookup"><span data-stu-id="ca276-213">Like most everything in life, the answer depends on your circumstances.</span></span>

<span data-ttu-id="ca276-214">組は、関数から複数の値を返す場合や、値のアドホック集計を値自体として使用する場合に適しています。</span><span class="sxs-lookup"><span data-stu-id="ca276-214">Tuples are great for returning multiple values from a function, and using an ad-hoc aggregate of values as a value itself.</span></span>

<span data-ttu-id="ca276-215">レコードは組からの "ステップアップ" であり、名前付きラベルとオプションメンバーのサポートがあります。</span><span class="sxs-lookup"><span data-stu-id="ca276-215">Records are a "step up" from Tuples, having named labels and support for optional members.</span></span>  <span data-ttu-id="ca276-216">プログラムを通じて転送中のデータをより詳細に表現する場合に適しています。</span><span class="sxs-lookup"><span data-stu-id="ca276-216">They are great for a low-ceremony representation of data in-transit through your program.</span></span>  <span data-ttu-id="ca276-217">これらは構造的に等価であるため、比較で簡単に使用できます。</span><span class="sxs-lookup"><span data-stu-id="ca276-217">Because they have structural equality, they are easy to use with comparison.</span></span>

<span data-ttu-id="ca276-218">判別共用体には多くの用途がありますが、主な利点は、データに含まれる可能性のあるすべての "形状" を考慮して、それらをパターンマッチングと組み合わせて使用できることです。</span><span class="sxs-lookup"><span data-stu-id="ca276-218">Discriminated Unions have many uses, but the core benefit is to be able to utilize them in conjunction with Pattern Matching to account for all possible "shapes" that a data can have.</span></span>  

<span data-ttu-id="ca276-219">クラスは、情報を表す必要がある場合や、その情報を機能に関連付けている場合など、膨大な数の理由で非常に優れています。</span><span class="sxs-lookup"><span data-stu-id="ca276-219">Classes are great for a huge number of reasons, such as when you need to represent information and also tie that information to functionality.</span></span>  <span data-ttu-id="ca276-220">経験則として、概念的に一部のデータに関連付けられている機能がある場合は、クラスとオブジェクト指向プログラミングの原則を使用することが大きな利点です。</span><span class="sxs-lookup"><span data-stu-id="ca276-220">As a rule of thumb, when you have functionality which is conceptually tied to some data, using Classes and the principles of Object-Oriented Programming is a big benefit.</span></span>  <span data-ttu-id="ca276-221">これらの言語はほぼすべての言語でクラスC#を使用するため、および Visual Basic と相互運用する場合は、クラスも推奨されるデータ型です。</span><span class="sxs-lookup"><span data-stu-id="ca276-221">Classes are also the preferred data type when interoperating with C# and Visual Basic, as these languages use classes for nearly everything.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ca276-222">次のステップ</span><span class="sxs-lookup"><span data-stu-id="ca276-222">Next Steps</span></span>

<span data-ttu-id="ca276-223">言語の主な機能のいくつかを確認したらには、最初の F# プログラムを作成できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca276-223">Now that you've seen some of the primary features of the language, you should be ready to write your first F# programs!</span></span>  <span data-ttu-id="ca276-224">開発環境を設定してコードを記述する方法については、[はじめに](get-started/index.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca276-224">Check out [Getting Started](get-started/index.md) to learn how to set up your development environment and write some code.</span></span>

<span data-ttu-id="ca276-225">さらに学習するための次の手順は任意のものにすることができますが、コア関数型プログラミングの概念を理解するために、[のF#関数型プログラミングの概要](./introduction-to-functional-programming/index.md)をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ca276-225">The next steps for learning more can be whatever you like, but we recommend [Introduction to Functional Programming in F#](./introduction-to-functional-programming/index.md) to get comfortable with core Functional Programming concepts.</span></span>  <span data-ttu-id="ca276-226">これらは、F# で堅牢なアプリケーションの構築に不可欠になります。</span><span class="sxs-lookup"><span data-stu-id="ca276-226">These will be essential in building robust programs in F#.</span></span>

<span data-ttu-id="ca276-227">また、チェック アウト、 [F# 言語リファレンス](./language-reference/index.md)を F# の概念的なコンテンツの包括的なコレクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca276-227">Also, check out the [F# Language Reference](./language-reference/index.md) to see a comprehensive collection of conceptual content on F#.</span></span>
