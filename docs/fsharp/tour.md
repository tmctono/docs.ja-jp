---
title: F# のツアー
description: 'このツアーの F # プログラミング言語の主な機能のいくつかを、コードサンプルで確認します。'
ms.date: 08/14/2020
ms.openlocfilehash: b115317e1f47ef7e18333cae4145b99e11645579
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558596"
---
# <a name="tour-of-f"></a><span data-ttu-id="5d3c8-103">F のツアー\#</span><span class="sxs-lookup"><span data-stu-id="5d3c8-103">Tour of F\#</span></span>

<span data-ttu-id="5d3c8-104">F # について学習する最善の方法は、F # コードの読み取りと書き込みです。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-104">The best way to learn about F# is to read and write F# code.</span></span> <span data-ttu-id="5d3c8-105">この記事では、F # 言語の主な機能をいくつか紹介し、お使いのコンピューターで実行できるコードスニペットをいくつか紹介します。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-105">This article will act as a tour through some of the key features of the F# language and give you some code snippets that you can execute on your machine.</span></span> <span data-ttu-id="5d3c8-106">開発環境の設定の詳細については、「 [はじめに](get-started/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-106">To learn about setting up a development environment, check out [Getting Started](get-started/index.md).</span></span>

<span data-ttu-id="5d3c8-107">F # には、関数と型という2つの主要な概念があります。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-107">There are two primary concepts in F#: functions and types.</span></span>  <span data-ttu-id="5d3c8-108">このツアーでは、この2つの概念に分類される言語の機能に重点を置いています。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-108">This tour will emphasize features of the language which fall into these two concepts.</span></span>

## <a name="executing-the-code-online"></a><span data-ttu-id="5d3c8-109">コードをオンラインで実行する</span><span class="sxs-lookup"><span data-stu-id="5d3c8-109">Executing the code online</span></span>

<span data-ttu-id="5d3c8-110">コンピューターに F # がインストールされていない場合は、ブラウザーですべてのサンプルを実行し [てみてください](https://tryfsharp.fsbolero.io/)。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-110">If you don't have F# installed on your machine, you can execute all of the samples in your browser with [Try F# on WebAssembly](https://tryfsharp.fsbolero.io/).</span></span> <span data-ttu-id="5d3c8-111">Fable は、ブラウザーで直接実行される F # の言語です。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-111">Fable is a dialect of F# that executes directly in your browser.</span></span> <span data-ttu-id="5d3c8-112">REPL の後に続くサンプルを確認するには、Fable REPL の左側のメニューバーにある **F # の > ツアーの >** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-112">To view the samples that follow in the REPL, check out **Samples > Learn > Tour of F#** in the left-hand menu bar of the Fable REPL.</span></span>

## <a name="functions-and-modules"></a><span data-ttu-id="5d3c8-113">関数とモジュール</span><span class="sxs-lookup"><span data-stu-id="5d3c8-113">Functions and Modules</span></span>

<span data-ttu-id="5d3c8-114">F # プログラムの最も基本的な部分は、***モジュール***に編成された***関数***です。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-114">The most fundamental pieces of any F# program are ***functions*** organized into ***modules***.</span></span>  <span data-ttu-id="5d3c8-115">[関数](./language-reference/functions/index.md) は、入力に対する処理を実行して出力を生成し、モジュールの下に編成されます。 [モジュール](./language-reference/modules.md)は、F # で項目をグループ化する主な方法です。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-115">[Functions](./language-reference/functions/index.md) perform work on inputs to produce outputs, and they are organized under [Modules](./language-reference/modules.md), which are the primary way you group things in F#.</span></span>  <span data-ttu-id="5d3c8-116">これらは、 [ `let` バインディング](./language-reference/functions/let-bindings.md)を使用して定義されます。これにより、関数に名前を付け、引数を定義します。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-116">They are defined using the [`let` binding](./language-reference/functions/let-bindings.md), which give the function a name and define its arguments.</span></span>

[!code-fsharp[BasicFunctions](~/samples/snippets/fsharp/tour.fs#L101-L133)]

<span data-ttu-id="5d3c8-117">`let` バインドは、他の言語の変数と同様に、値を名前にバインドする方法でもあります。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-117">`let` bindings are also how you bind a value to a name, similar to a variable in other languages.</span></span>  <span data-ttu-id="5d3c8-118">`let` 既定では、バインドは変更できません。つまり、値または関数が名前に ***バインドされる*** と、その場で変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-118">`let` bindings are ***immutable*** by default, which means that once a value or function is bound to a name, it cannot be changed in-place.</span></span>  <span data-ttu-id="5d3c8-119">これは、変更可能な他の言語の変数と ***は対照的***です。つまり、値は任意の時点で変更できます。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-119">This is in contrast to variables in other languages, which are ***mutable***, meaning their values can be changed at any point in time.</span></span>  <span data-ttu-id="5d3c8-120">変更可能なバインドが必要な場合は、構文を使用でき `let mutable ...` ます。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-120">If you require a mutable binding, you can use `let mutable ...` syntax.</span></span>

[!code-fsharp[Immutability](~/samples/snippets/fsharp/tour.fs#L75-L94)]

## <a name="numbers-booleans-and-strings"></a><span data-ttu-id="5d3c8-121">数値、ブール値、および文字列</span><span class="sxs-lookup"><span data-stu-id="5d3c8-121">Numbers, Booleans, and Strings</span></span>

<span data-ttu-id="5d3c8-122">.NET 言語として、F # では .NET に存在する基になる [プリミティブ型](language-reference/basic-types.md) と同じものがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-122">As a .NET language, F# supports the same underlying [primitive types](language-reference/basic-types.md) that exist in .NET.</span></span>

<span data-ttu-id="5d3c8-123">F # では、さまざまな数値型がどのように表されるかを次に示します。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-123">Here is how various numeric types are represented in F#:</span></span>

[!code-fsharp[Numbers](~/samples/snippets/fsharp/tour.fs#L49-L68)]

<span data-ttu-id="5d3c8-124">次に、ブール値と基本的な条件ロジックの実行例を示します。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-124">Here's what Boolean values and performing basic conditional logic looks like:</span></span>

[!code-fsharp[Bools](~/samples/snippets/fsharp/tour.fs#L142-L152)]

<span data-ttu-id="5d3c8-125">基本的な [文字列](./language-reference/strings.md) 操作は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-125">And here's what basic [string](./language-reference/strings.md) manipulation looks like:</span></span>

[!code-fsharp[Strings](~/samples/snippets/fsharp/tour.fs#L158-L180)]

## <a name="tuples"></a><span data-ttu-id="5d3c8-126">タプル</span><span class="sxs-lookup"><span data-stu-id="5d3c8-126">Tuples</span></span>

<span data-ttu-id="5d3c8-127">F # では、[タプル](./language-reference/tuples.md)は大きな問題です。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-127">[Tuples](./language-reference/tuples.md) are a big deal in F#.</span></span>  <span data-ttu-id="5d3c8-128">これらは名前のない、順序付けされた値をグループ化したもので、値自体として扱うことができます。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-128">They are a grouping of unnamed, but ordered values, that can be treated as values themselves.</span></span>  <span data-ttu-id="5d3c8-129">これらは、他の値から集計された値と考えることができます。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-129">Think of them as values which are aggregated from other values.</span></span>  <span data-ttu-id="5d3c8-130">多くの用途があります。たとえば、関数から複数の値を返すことができるようにしたり、特別な便宜を行うために値をグループ化したりします。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-130">They have many uses, such as conveniently returning multiple values from a function, or grouping values for some ad-hoc convenience.</span></span>

[!code-fsharp[Tuples](~/samples/snippets/fsharp/tour.fs#L186-L203)]

<span data-ttu-id="5d3c8-131">組を作成することもでき `struct` ます。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-131">You can also create `struct` tuples.</span></span>  <span data-ttu-id="5d3c8-132">これらは、C# 7/Visual Basic 15 組 (タプル) と完全に相互運用することもでき `struct` ます。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-132">These also interoperate fully with C#7/Visual Basic 15 tuples, which are also `struct` tuples:</span></span>

[!code-fsharp[Tuples](~/samples/snippets/fsharp/tour.fs#L205-L218)]

<span data-ttu-id="5d3c8-133">`struct`タプルは値型であるため、暗黙的に参照タプルに変換することはできず、逆の場合もあります。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-133">It's important to note that because `struct` tuples are value types, they cannot be implicitly converted to reference tuples, or vice versa.</span></span>  <span data-ttu-id="5d3c8-134">参照と構造体の組の間で明示的に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-134">You must explicitly convert between a reference and struct tuple.</span></span>

## <a name="pipelines-and-composition"></a><span data-ttu-id="5d3c8-135">パイプラインとコンポジション</span><span class="sxs-lookup"><span data-stu-id="5d3c8-135">Pipelines and Composition</span></span>

<span data-ttu-id="5d3c8-136">などのパイプ演算子 `|>` は、F # でデータを処理するときに広く使用されます。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-136">Pipe operators such as `|>` are used extensively when processing data in F#.</span></span> <span data-ttu-id="5d3c8-137">これらの演算子は、関数の "パイプライン" を柔軟な方法で確立できるようにする関数です。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-137">These operators are functions that allow you to establish "pipelines" of functions in a flexible manner.</span></span> <span data-ttu-id="5d3c8-138">次の例では、これらの演算子を利用して単純な機能パイプラインを構築する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-138">The following example walks through how you can take advantage of these operators to build a simple functional pipeline:</span></span>

[!code-fsharp[Pipelines](~/samples/snippets/fsharp/tour.fs#L227-L282)]

<span data-ttu-id="5d3c8-139">前のサンプルでは、リスト処理関数、ファーストクラス関数、 [部分アプリケーション](./language-reference/functions/index.md#partial-application-of-arguments)など、F # の多くの機能が使用されていました。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-139">The previous sample made use of many features of F#, including list processing functions, first-class functions, and [partial application](./language-reference/functions/index.md#partial-application-of-arguments).</span></span> <span data-ttu-id="5d3c8-140">これらの概念を深く理解することは少し高度になる可能性がありますが、パイプラインを構築するときに、簡単に関数を使用してデータを処理する方法を明確にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-140">Although a deep understanding of each of those concepts can become somewhat advanced, it should be clear how easily functions can be used to process data when building pipelines.</span></span>

## <a name="lists-arrays-and-sequences"></a><span data-ttu-id="5d3c8-141">リスト、配列、およびシーケンス</span><span class="sxs-lookup"><span data-stu-id="5d3c8-141">Lists, Arrays, and Sequences</span></span>

<span data-ttu-id="5d3c8-142">リスト、配列、およびシーケンスは、F # コアライブラリの3つのプライマリコレクション型です。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-142">Lists, Arrays, and Sequences are three primary collection types in the F# core library.</span></span>

<span data-ttu-id="5d3c8-143">[リスト](./language-reference/lists.md) は、同じ型の要素の順序付けられ、変更できないコレクションです。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-143">[Lists](./language-reference/lists.md) are ordered, immutable collections of elements of the same type.</span></span>  <span data-ttu-id="5d3c8-144">これらはシングルリンクリストです。つまり、列挙型であることを意味しますが、サイズが大きい場合はランダムアクセスと連結には適していません。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-144">They are singly-linked lists, which means they are meant for enumeration, but a poor choice for random access and concatenation if they're large.</span></span>  <span data-ttu-id="5d3c8-145">これは、一般的には、リストを表すために単一リンクリストを使用しない他の一般的な言語の一覧とは対照的です。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-145">This in contrast to Lists in other popular languages, which typically do not use a singly-linked list to represent Lists.</span></span>

[!code-fsharp[Lists](~/samples/snippets/fsharp/tour.fs#L309-L359)]

<span data-ttu-id="5d3c8-146">[配列](./language-reference/arrays.md) は、同じ型の要素の固定 *サイズの変更可能なコレクションです* 。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-146">[Arrays](./language-reference/arrays.md) are fixed-size, *mutable* collections of elements of the same type.</span></span>  <span data-ttu-id="5d3c8-147">要素の高速なランダムアクセスをサポートしています。 F # リストは、連続したメモリブロックであるため、F # リストより高速です。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-147">They support fast random access of elements, and are faster than F# lists because they are just contiguous blocks of memory.</span></span>

[!code-fsharp[Arrays](~/samples/snippets/fsharp/tour.fs#L368-L407)]

<span data-ttu-id="5d3c8-148">[シーケンス](./language-reference/sequences.md) は、すべて同じ型の論理的な一連の要素です。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-148">[Sequences](./language-reference/sequences.md) are a logical series of elements, all of the same type.</span></span>  <span data-ttu-id="5d3c8-149">これらは、リストや配列よりも一般的な型であり、任意の論理シリーズの要素に "表示" できるようになっています。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-149">These are a more general type than Lists and Arrays, capable of being your "view" into any logical series of elements.</span></span>  <span data-ttu-id="5d3c8-150">また、 ***遅延***がある可能性があるため、このような場合もあります。これは、要素が必要な場合にのみ計算できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-150">They also stand out because they can be ***lazy***, which means that elements can be computed only when they are needed.</span></span>

[!code-fsharp[Sequences](~/samples/snippets/fsharp/tour.fs#L418-L452)]

## <a name="recursive-functions"></a><span data-ttu-id="5d3c8-151">再帰関数</span><span class="sxs-lookup"><span data-stu-id="5d3c8-151">Recursive Functions</span></span>

<span data-ttu-id="5d3c8-152">コレクションまたは要素のシーケンスの処理は、通常、F # の [再帰](./language-reference/functions/index.md#recursive-functions) を使用して行われます。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-152">Processing collections or sequences of elements is typically done with [recursion](./language-reference/functions/index.md#recursive-functions) in F#.</span></span>  <span data-ttu-id="5d3c8-153">F # では、ループと命令型プログラミングがサポートされていますが、正確性を保証するのが簡単であるため、再帰が推奨されています。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-153">Although F# has support for loops and imperative programming, recursion is preferred because it is easier to guarantee correctness.</span></span>

> [!NOTE]
> <span data-ttu-id="5d3c8-154">次の例では、式を使用してパターンマッチングを使用し `match` ます。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-154">The following example makes use of the pattern matching via the `match` expression.</span></span>  <span data-ttu-id="5d3c8-155">この基本的な構成要素については、この記事の後半で説明します。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-155">This fundamental construct is covered later in this article.</span></span>

[!code-fsharp[RecursiveFunctions](~/samples/snippets/fsharp/tour.fs#L461-L500)]

<span data-ttu-id="5d3c8-156">F # では、末尾呼び出しの最適化も完全にサポートされています。これは、再帰呼び出しを最適化して、ループ構造と同じ速度にすることができるようにするための方法です。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-156">F# also has full support for Tail Call Optimization, which is a way to optimize recursive calls so that they are just as fast as a loop construct.</span></span>

## <a name="record-and-discriminated-union-types"></a><span data-ttu-id="5d3c8-157">レコードと判別共用体型</span><span class="sxs-lookup"><span data-stu-id="5d3c8-157">Record and Discriminated Union Types</span></span>

<span data-ttu-id="5d3c8-158">レコード型と共用体型は、F # コードで使用される2つの基本データ型であり、一般に F # プログラムでデータを表現する最良の方法です。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-158">Record and Union types are two fundamental data types used in F# code, and are generally the best way to represent data in an F# program.</span></span>  <span data-ttu-id="5d3c8-159">これは他の言語のクラスと似ていますが、主な違いの1つは、構造上の等価性があることです。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-159">Although this makes them similar to classes in other languages, one of their primary differences is that they have structural equality semantics.</span></span>  <span data-ttu-id="5d3c8-160">つまり、これらは "ネイティブな" 比較可能であり、等価性が簡単であることを意味します。一方が等しいかどうかを確認するだけです。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-160">This means that they are "natively" comparable and equality is straightforward - just check if one is equal to the other.</span></span>

<span data-ttu-id="5d3c8-161">[レコード](./language-reference/records.md) は、名前付きの値の集合であり、オプションのメンバー (メソッドなど) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-161">[Records](./language-reference/records.md) are an aggregate of named values, with optional members (such as methods).</span></span>  <span data-ttu-id="5d3c8-162">C# または Java に慣れていれば、これらは、構造的な等価性と少ない手続きを持つ POCOs や Pojo に似ています。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-162">If you're familiar with C# or Java, then these should feel similar to POCOs or POJOs - just with structural equality and less ceremony.</span></span>

[!code-fsharp[Records](~/samples/snippets/fsharp/tour.fs#L507-L559)]

<span data-ttu-id="5d3c8-163">レコードを構造体として表すこともできます。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-163">You can also represent Records as structs.</span></span> <span data-ttu-id="5d3c8-164">これは、属性を使用して行い `[<Struct>]` ます。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-164">This is done with the `[<Struct>]` attribute:</span></span>

[!code-fsharp[Records](~/samples/snippets/fsharp/tour.fs#L561-L568)]

<span data-ttu-id="5d3c8-165">[判別共用体 (du)](./language-reference/discriminated-unions.md) は、多数の名前付きフォームまたはケースである可能性がある値です。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-165">[Discriminated Unions (DUs)](./language-reference/discriminated-unions.md) are values which could be a number of named forms or cases.</span></span>  <span data-ttu-id="5d3c8-166">型に格納されるデータは、複数の個別の値のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-166">Data stored in the type can be one of several distinct values.</span></span>

[!code-fsharp[Unions](~/samples/snippets/fsharp/tour.fs#L575-L631)]

<span data-ttu-id="5d3c8-167">また、Du を *シングルケース判別共用体*として使用して、プリミティブ型に対するドメインモデリングを支援することもできます。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-167">You can also use DUs as *Single-Case Discriminated Unions*, to help with domain modeling over primitive types.</span></span>  <span data-ttu-id="5d3c8-168">多くの場合、文字列やその他のプリミティブ型を使用して何かを表しているため、特定の意味が与えられます。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-168">Often times, strings and other primitive types are used to represent something, and are thus given a particular meaning.</span></span>  <span data-ttu-id="5d3c8-169">ただし、データのプリミティブ表現のみを使用すると、誤った値が誤って割り当てられる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-169">However, using only the primitive representation of the data can result in mistakenly assigning an incorrect value!</span></span>  <span data-ttu-id="5d3c8-170">このシナリオでは、各種類の情報を個別の単一ケース共用体として表すことができます。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-170">Representing each type of information as a distinct single-case union can enforce correctness in this scenario.</span></span>

[!code-fsharp[Unions](~/samples/snippets/fsharp/tour.fs#L633-L654)]

<span data-ttu-id="5d3c8-171">上の例で示すように、単一ケースの判別共用体の基になる値を取得するには、明示的にラップ解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-171">As the above sample demonstrates, to get the underlying value in a single-case Discriminated Union, you must explicitly unwrap it.</span></span>

<span data-ttu-id="5d3c8-172">また、Du は再帰的な定義もサポートしているので、ツリーや本質的に再帰的なデータを簡単に表すことができます。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-172">Additionally, DUs also support recursive definitions, allowing you to easily represent trees and inherently recursive data.</span></span>  <span data-ttu-id="5d3c8-173">たとえば、関数と関数を使用してバイナリ検索ツリーを表現する方法を次に示し `exists` `insert` ます。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-173">For example, here's how you can represent a Binary Search Tree with `exists` and `insert` functions.</span></span>

[!code-fsharp[Unions](~/samples/snippets/fsharp/tour.fs#L656-L683)]

<span data-ttu-id="5d3c8-174">Du では、データ型のツリーの再帰構造を表すことができるため、この再帰構造での操作は簡単で、正確性が保証されます。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-174">Because DUs allow you to represent the recursive structure of the tree in the data type, operating on this recursive structure is straightforward and guarantees correctness.</span></span>  <span data-ttu-id="5d3c8-175">次に示すように、パターンマッチングでもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-175">It is also supported in pattern matching, as shown below.</span></span>

<span data-ttu-id="5d3c8-176">また、次の属性を使用して、の Du をとして表すことができ `struct` `[<Struct>]` ます。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-176">Additionally, you can represent DUs as `struct`s with the `[<Struct>]` attribute:</span></span>

[!code-fsharp[Unions](~/samples/snippets/fsharp/tour.fs#L685-L696)]

<span data-ttu-id="5d3c8-177">ただし、その場合は、次の2つの点に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-177">However, there are two key things to keep in mind when doing so:</span></span>

1. <span data-ttu-id="5d3c8-178">Struct DU を再帰的に定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-178">A struct DU cannot be recursively-defined.</span></span>
2. <span data-ttu-id="5d3c8-179">Struct DU は、それぞれのケースに対して一意の名前を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-179">A struct DU must have unique names for each of its cases.</span></span>

<span data-ttu-id="5d3c8-180">上記に従わないと、コンパイルエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-180">Failure to follow the above will result in a compilation error.</span></span>

## <a name="pattern-matching"></a><span data-ttu-id="5d3c8-181">パターン マッチ</span><span class="sxs-lookup"><span data-stu-id="5d3c8-181">Pattern Matching</span></span>

<span data-ttu-id="5d3c8-182">[パターンマッチング](./language-reference/pattern-matching.md) は f # 言語機能で、f # の型を操作するための正確さを有効にします。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-182">[Pattern Matching](./language-reference/pattern-matching.md) is the F# language feature which enables correctness for operating on F# types.</span></span>  <span data-ttu-id="5d3c8-183">上記のサンプルでは、非常に多くの構文に気付き `match x with ...` ます。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-183">In the above samples, you probably noticed quite a bit of `match x with ...` syntax.</span></span>  <span data-ttu-id="5d3c8-184">このコンストラクトを使用すると、コンパイラはデータ型の "形状" を理解でき、完全なパターンマッチングとして知られているデータ型を使用する場合に、すべてのケースを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-184">This construct allows the compiler, which can understand the "shape" of data types, to force you to account for all possible cases when using a data type through what is known as Exhaustive Pattern Matching.</span></span>  <span data-ttu-id="5d3c8-185">これは、正確さを実現するために非常に強力であり、通常はランタイムの問題としてコンパイル時に巧妙を "リフト" するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-185">This is incredibly powerful for correctness, and can be cleverly used to "lift" what would normally be a runtime concern into compile-time.</span></span>

[!code-fsharp[PatternMatching](~/samples/snippets/fsharp/tour.fs#L705-L742)]

<span data-ttu-id="5d3c8-186">ご存知かもしれませんが、パターンを使用してい `_` ます。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-186">Something you may have noticed is the use of the `_` pattern.</span></span>  <span data-ttu-id="5d3c8-187">これは、 [ワイルドカードパターン](./language-reference/pattern-matching.md#wildcard-pattern)と呼ばれます。これは、"何が何であるかを気にしない" と言うことができます。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-187">This is known as the [Wildcard Pattern](./language-reference/pattern-matching.md#wildcard-pattern), which is a way of saying "I don't care what something is".</span></span>  <span data-ttu-id="5d3c8-188">便利ですが、を使用するのが十分でない場合は、完全なパターンマッチングを誤ってバイパスし、コンパイル時の実施の恩恵を受けることができなくなり `_` ます。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-188">Although convenient, you can accidentally bypass Exhaustive Pattern Matching and no longer benefit from compile-time enforcements if you aren't careful in using `_`.</span></span>  <span data-ttu-id="5d3c8-189">パターンマッチングの際に分解された型の特定の部分を気にしない場合、またはパターン一致式ですべての意味のあるケースを列挙した場合は final 句を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-189">It is best used when you don't care about certain pieces of a decomposed type when pattern matching, or the final clause when you have enumerated all meaningful cases in a pattern matching expression.</span></span>

<span data-ttu-id="5d3c8-190">次の例では、 `_` 解析操作が失敗したときにケースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-190">In the following example, the `_` case is used when a parse operation fails.</span></span>

[!code-fsharp[PatternMatching](~/samples/snippets/fsharp/tour.fs#L744-L762)]

<span data-ttu-id="5d3c8-191">[アクティブパターン](./language-reference/active-patterns.md) は、パターンマッチングで使用するもう1つの強力な構成要素です。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-191">[Active Patterns](./language-reference/active-patterns.md) are another powerful construct to use with pattern matching.</span></span>  <span data-ttu-id="5d3c8-192">これにより、入力データをカスタムフォームに分割し、パターンマッチ呼び出しサイトで分解することができます。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-192">They allow you to partition input data into custom forms, decomposing them at the pattern match call site.</span></span>  <span data-ttu-id="5d3c8-193">また、パラメーター化して、がパーティションを関数として定義できるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-193">They can also be parameterized, thus allowing to define the partition as a function.</span></span>  <span data-ttu-id="5d3c8-194">アクティブなパターンをサポートするために前の例を拡張すると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-194">Expanding the previous example to support Active Patterns looks something like this:</span></span>

[!code-fsharp[ActivePatterns](~/samples/snippets/fsharp/tour.fs#L764-L786)]

## <a name="optional-types"></a><span data-ttu-id="5d3c8-195">省略可能な型</span><span class="sxs-lookup"><span data-stu-id="5d3c8-195">Optional Types</span></span>

<span data-ttu-id="5d3c8-196">判別共用体型の1つの特殊なケースとして、オプションの型があります。これは、F # コアライブラリの一部であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-196">One special case of Discriminated Union types is the Option Type, which is so useful that it's a part of the F# core library.</span></span>

<span data-ttu-id="5d3c8-197">[オプションの種類](./language-reference/options.md) は、値または nothing の2つのケースのいずれかを表す型です。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-197">[The Option Type](./language-reference/options.md) is a type which represents one of two cases: a value, or nothing at all.</span></span>  <span data-ttu-id="5d3c8-198">このメソッドは、特定の操作の結果として値が異なる可能性がある場合に、どのようなシナリオでも使用されます。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-198">It is used in any scenario where a value may or may not result from a particular operation.</span></span>  <span data-ttu-id="5d3c8-199">これにより、実行時の問題ではなく、コンパイル時の問題になるように、両方のケースを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-199">This then forces you to account for both cases, making it a compile-time concern rather than a runtime concern.</span></span>  <span data-ttu-id="5d3c8-200">これらは多くの場合、 `null` が "nothing" を表すために使用される api で使用されるため、多くの状況では心配する必要があり `NullReferenceException` ません。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-200">These are often used in APIs where `null` is used to represent "nothing" instead, thus eliminating the need to worry about `NullReferenceException` in many circumstances.</span></span>

[!code-fsharp[Options](~/samples/snippets/fsharp/tour.fs#L789-L814)]

## <a name="units-of-measure"></a><span data-ttu-id="5d3c8-201">測定単位</span><span class="sxs-lookup"><span data-stu-id="5d3c8-201">Units of Measure</span></span>

<span data-ttu-id="5d3c8-202">F # の型システムの固有の機能の1つに、測定単位を使用して数値リテラルのコンテキストを提供する機能があります。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-202">One unique feature of F#'s type system is the ability to provide context for numeric literals through Units of Measure.</span></span>

<span data-ttu-id="5d3c8-203">[測定単位](./language-reference/units-of-measure.md) を使用すると、数値型をメートル単位に関連付けることができます。また、関数は数値リテラルではなく単位で作業を実行します。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-203">[Units of Measure](./language-reference/units-of-measure.md) allow you to associate a numeric type to a unit, such as Meters, and have functions perform work on units rather than numeric literals.</span></span>  <span data-ttu-id="5d3c8-204">これにより、コンパイラは、渡された数値リテラルの型が特定のコンテキストで意味を持つかどうかを検証できるため、そのような作業に関連するランタイムエラーを回避できます。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-204">This enables the compiler to verify that the types of numeric literals passed in make sense under a certain context, thus eliminating runtime errors associated with that kind of work.</span></span>

[!code-fsharp[UnitsOfMeasure](~/samples/snippets/fsharp/tour.fs#L817-L842)]

<span data-ttu-id="5d3c8-205">F # コアライブラリでは、さまざまな SI 単位の型と単位の変換が定義されています。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-205">The F# Core library defines many SI unit types and unit conversions.</span></span>  <span data-ttu-id="5d3c8-206">詳細については、 [Fsharp.core 名前空間](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-data-unitsystems-si-unitsymbols.html)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-206">To learn more, check out the [FSharp.Data.UnitSystems.SI.UnitSymbols Namespace](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-data-unitsystems-si-unitsymbols.html).</span></span>

## <a name="classes-and-interfaces"></a><span data-ttu-id="5d3c8-207">クラスとインターフェイス</span><span class="sxs-lookup"><span data-stu-id="5d3c8-207">Classes and Interfaces</span></span>

<span data-ttu-id="5d3c8-208">F # では、.NET クラス、 [インターフェイス](./language-reference/interfaces.md)、 [抽象クラス](./language-reference/abstract-classes.md)、 [継承](./language-reference/inheritance.md)なども完全にサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-208">F# also has full support for .NET classes, [Interfaces](./language-reference/interfaces.md), [Abstract Classes](./language-reference/abstract-classes.md), [Inheritance](./language-reference/inheritance.md), and so on.</span></span>

<span data-ttu-id="5d3c8-209">[クラス](./language-reference/classes.md) は、プロパティ、メソッド、およびイベントを [メンバー](./language-reference/members/index.md)として持つことができる .net オブジェクトを表す型です。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-209">[Classes](./language-reference/classes.md) are types that represent .NET objects, which can have properties, methods, and events as its [Members](./language-reference/members/index.md).</span></span>

[!code-fsharp[Classes](~/samples/snippets/fsharp/tour.fs#L845-L880)]

<span data-ttu-id="5d3c8-210">ジェネリッククラスを定義することも、非常に簡単です。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-210">Defining generic classes is also very straightforward.</span></span>

[!code-fsharp[Classes](~/samples/snippets/fsharp/tour.fs#L883-L908)]

<span data-ttu-id="5d3c8-211">インターフェイスを実装するには、 `interface ... with` 構文または [オブジェクト式](./language-reference/object-expressions.md)のいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-211">To implement an Interface, you can use either `interface ... with` syntax or an [Object Expression](./language-reference/object-expressions.md).</span></span>

[!code-fsharp[Classes](~/samples/snippets/fsharp/tour.fs#L911-L934)]

## <a name="which-types-to-use"></a><span data-ttu-id="5d3c8-212">使用する型</span><span class="sxs-lookup"><span data-stu-id="5d3c8-212">Which Types to Use</span></span>

<span data-ttu-id="5d3c8-213">クラス、レコード、判別共用体、および組が存在すると、重要な質問につながります。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-213">The presence of Classes, Records, Discriminated Unions, and Tuples leads to an important question: which should you use?</span></span>  <span data-ttu-id="5d3c8-214">多くの場合、その答えは状況によって異なります。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-214">Like most everything in life, the answer depends on your circumstances.</span></span>

<span data-ttu-id="5d3c8-215">組は、関数から複数の値を返す場合や、値のアドホック集計を値自体として使用する場合に適しています。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-215">Tuples are great for returning multiple values from a function, and using an ad-hoc aggregate of values as a value itself.</span></span>

<span data-ttu-id="5d3c8-216">レコードは組からの "ステップアップ" であり、名前付きラベルとオプションメンバーのサポートがあります。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-216">Records are a "step up" from Tuples, having named labels and support for optional members.</span></span>  <span data-ttu-id="5d3c8-217">プログラムを通じて転送中のデータをより詳細に表現する場合に適しています。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-217">They are great for a low-ceremony representation of data in-transit through your program.</span></span>  <span data-ttu-id="5d3c8-218">これらは構造的に等価であるため、比較で簡単に使用できます。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-218">Because they have structural equality, they are easy to use with comparison.</span></span>

<span data-ttu-id="5d3c8-219">判別共用体には多くの用途がありますが、主な利点は、データに含まれる可能性のあるすべての "形状" を考慮して、それらをパターンマッチングと組み合わせて使用できることです。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-219">Discriminated Unions have many uses, but the core benefit is to be able to utilize them in conjunction with Pattern Matching to account for all possible "shapes" that a data can have.</span></span>  

<span data-ttu-id="5d3c8-220">クラスは、情報を表す必要がある場合や、その情報を機能に関連付けている場合など、膨大な数の理由で非常に優れています。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-220">Classes are great for a huge number of reasons, such as when you need to represent information and also tie that information to functionality.</span></span>  <span data-ttu-id="5d3c8-221">経験則として、概念的に一部のデータに関連付けられている機能がある場合は、クラスとオブジェクト指向プログラミングの原則を使用することが大きな利点です。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-221">As a rule of thumb, when you have functionality which is conceptually tied to some data, using Classes and the principles of Object-Oriented Programming is a big benefit.</span></span>  <span data-ttu-id="5d3c8-222">クラスは C# および Visual Basic と相互運用する場合にも、ほぼすべての言語でクラスを使用するため、推奨されるデータ型です。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-222">Classes are also the preferred data type when interoperating with C# and Visual Basic, as these languages use classes for nearly everything.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5d3c8-223">次の手順</span><span class="sxs-lookup"><span data-stu-id="5d3c8-223">Next Steps</span></span>

<span data-ttu-id="5d3c8-224">言語の主な機能をいくつか紹介したので、最初の F # プログラムを作成する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-224">Now that you've seen some of the primary features of the language, you should be ready to write your first F# programs!</span></span>  <span data-ttu-id="5d3c8-225">開発環境を設定してコードを記述する方法については、 [はじめに](get-started/index.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-225">Check out [Getting Started](get-started/index.md) to learn how to set up your development environment and write some code.</span></span>

<span data-ttu-id="5d3c8-226">さらに学習するための次の手順は任意のものにすることができますが、コア関数型プログラミングの概念を理解するには、 [F # での関数型プログラミングの概要](./introduction-to-functional-programming/index.md) をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-226">The next steps for learning more can be whatever you like, but we recommend [Introduction to Functional Programming in F#](./introduction-to-functional-programming/index.md) to get comfortable with core Functional Programming concepts.</span></span>  <span data-ttu-id="5d3c8-227">これらは、F # で堅牢なプログラムを構築する際に不可欠です。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-227">These will be essential in building robust programs in F#.</span></span>

<span data-ttu-id="5d3c8-228">また、f # の概念コンテンツの包括的なコレクションを確認するには、 [f # 言語リファレンス](./language-reference/index.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d3c8-228">Also, check out the [F# Language Reference](./language-reference/index.md) to see a comprehensive collection of conceptual content on F#.</span></span>
