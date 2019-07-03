---
title: C# 7.0 の新機能 - C# ガイド
description: C# 言語のバージョン 7.0 での新機能の概要を説明します。
ms.date: 02/20/2019
ms.assetid: fd41596d-d0c2-4816-b94d-c4d00a5d0243
ms.openlocfilehash: c3fdee2bdb974640b56bfab3af4be57133ad2f7a
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/21/2019
ms.locfileid: "67307149"
---
# <a name="whats-new-in-c-70"></a><span data-ttu-id="8252b-103">C# 7.0 の新機能</span><span class="sxs-lookup"><span data-stu-id="8252b-103">What's new in C# 7.0</span></span>

<span data-ttu-id="8252b-104">C# 7.0 では、C# 言語に多くの新機能が追加されます。</span><span class="sxs-lookup"><span data-stu-id="8252b-104">C# 7.0 adds a number of new features to the C# language:</span></span>
* [<span data-ttu-id="8252b-105">`out` 変数</span><span class="sxs-lookup"><span data-stu-id="8252b-105">`out` variables</span></span>](#out-variables)
  - <span data-ttu-id="8252b-106">`out` の値は、それが使用されるメソッドの引数としてインラインで宣言できます。</span><span class="sxs-lookup"><span data-stu-id="8252b-106">You can declare `out` values inline as arguments to the method where they're used.</span></span>
* [<span data-ttu-id="8252b-107">タプル</span><span class="sxs-lookup"><span data-stu-id="8252b-107">Tuples</span></span>](#tuples)
  - <span data-ttu-id="8252b-108">複数のパブリック フィールドを含む、軽量で名前のない型を作成できます。</span><span class="sxs-lookup"><span data-stu-id="8252b-108">You can create lightweight, unnamed types that contain multiple public fields.</span></span> <span data-ttu-id="8252b-109">コンパイラおよび IDE ツールでは、このような型のセマンティクスが認識されます。</span><span class="sxs-lookup"><span data-stu-id="8252b-109">Compilers and IDE tools understand the semantics of these types.</span></span>
* [<span data-ttu-id="8252b-110">破棄</span><span class="sxs-lookup"><span data-stu-id="8252b-110">Discards</span></span>](#discards)
  - <span data-ttu-id="8252b-111">破棄は、割り当てられた値を考慮しない場合に割り当てで使用された、一時的な書き込み専用の値です。</span><span class="sxs-lookup"><span data-stu-id="8252b-111">Discards are temporary, write-only variables used in assignments when you don't care about the value assigned.</span></span> <span data-ttu-id="8252b-112">タプルおよびユーザー定義の型を分解する場合や、メソッドを `out` パラメーターを使用して呼び出す場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="8252b-112">They're most useful when deconstructing tuples and user-defined types, as well as when calling methods with `out` parameters.</span></span>
* [<span data-ttu-id="8252b-113">パターン一致</span><span class="sxs-lookup"><span data-stu-id="8252b-113">Pattern Matching</span></span>](#pattern-matching)
  - <span data-ttu-id="8252b-114">これらの型のメンバーの任意の型と値に基づいて、分岐ロジックを作成できます。</span><span class="sxs-lookup"><span data-stu-id="8252b-114">You can create branching logic based on arbitrary types and values of the members of those types.</span></span>
* [<span data-ttu-id="8252b-115">`ref` ローカル変数と戻り値</span><span class="sxs-lookup"><span data-stu-id="8252b-115">`ref` locals and returns</span></span>](#ref-locals-and-returns)
  - <span data-ttu-id="8252b-116">メソッドのローカル変数と戻り値は、他のストレージへの参照になります。</span><span class="sxs-lookup"><span data-stu-id="8252b-116">Method local variables and return values can be references to other storage.</span></span>
* [<span data-ttu-id="8252b-117">ローカル関数</span><span class="sxs-lookup"><span data-stu-id="8252b-117">Local Functions</span></span>](#local-functions)
  - <span data-ttu-id="8252b-118">関数を他の関数の中に入れ子にして、関数のスコープと可視性を制限することができます。</span><span class="sxs-lookup"><span data-stu-id="8252b-118">You can nest functions inside other functions to limit their scope and visibility.</span></span>
* [<span data-ttu-id="8252b-119">式形式のメンバーの追加</span><span class="sxs-lookup"><span data-stu-id="8252b-119">More expression-bodied members</span></span>](#more-expression-bodied-members)
  - <span data-ttu-id="8252b-120">式を使用して作成できるメンバーが増加しました。</span><span class="sxs-lookup"><span data-stu-id="8252b-120">The list of members that can be authored using expressions has grown.</span></span>
* [<span data-ttu-id="8252b-121">`throw` 式</span><span class="sxs-lookup"><span data-stu-id="8252b-121">`throw` Expressions</span></span>](#throw-expressions)
  - <span data-ttu-id="8252b-122">`throw` がステートメントだったためにこれまで許可されなかったコード コンストラクトで例外をスローできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="8252b-122">You can throw exceptions in code constructs that previously weren't allowed because `throw` was a statement.</span></span>
* [<span data-ttu-id="8252b-123">一般化された async の戻り値の型</span><span class="sxs-lookup"><span data-stu-id="8252b-123">Generalized async return types</span></span>](#generalized-async-return-types)
  - <span data-ttu-id="8252b-124">`async` 修飾子を使って宣言したメソッドは、`Task` と `Task<T>` に加えて他の型を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="8252b-124">Methods declared with the `async` modifier can return other types in addition to `Task` and `Task<T>`.</span></span>
* [<span data-ttu-id="8252b-125">数値リテラルの構文の改善</span><span class="sxs-lookup"><span data-stu-id="8252b-125">Numeric literal syntax improvements</span></span>](#numeric-literal-syntax-improvements)
  - <span data-ttu-id="8252b-126">新しいトークンにより、数値定数の読みやすさが向上します。</span><span class="sxs-lookup"><span data-stu-id="8252b-126">New tokens improve readability for numeric constants.</span></span>

<span data-ttu-id="8252b-127">この記事の残りでは、各機能の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="8252b-127">The remainder of this article provides an overview of each feature.</span></span> <span data-ttu-id="8252b-128">機能ごとに、その背後にある論拠のほか、</span><span class="sxs-lookup"><span data-stu-id="8252b-128">For each feature, you'll learn the reasoning behind it.</span></span> <span data-ttu-id="8252b-129">構文についても説明します。</span><span class="sxs-lookup"><span data-stu-id="8252b-129">You'll learn the syntax.</span></span> <span data-ttu-id="8252b-130">これらの機能については、Microsoft の[対話型の探索](../tutorials/exploration/csharp-7.yml)で詳しく学習できます。</span><span class="sxs-lookup"><span data-stu-id="8252b-130">You can explore these features in our [interactive exploration](../tutorials/exploration/csharp-7.yml) of these features.</span></span>

## <a name="out-variables"></a><span data-ttu-id="8252b-131">`out` 変数</span><span class="sxs-lookup"><span data-stu-id="8252b-131">`out` variables</span></span>

<span data-ttu-id="8252b-132">`out` パラメーターをサポートする既存の構文は、このバージョンで改良されました。</span><span class="sxs-lookup"><span data-stu-id="8252b-132">The existing syntax that supports `out` parameters has been improved in this version.</span></span> <span data-ttu-id="8252b-133">現在は、別の宣言ステートメントを記述するのではなく、メソッド呼び出しの引数リストで `out` 変数を宣言できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="8252b-133">You can now declare `out` variables in the argument list of a method call, rather than writing a separate declaration statement:</span></span>

[!code-csharp[OutVariableDeclarations](~/samples/snippets/csharp/new-in-7/program.cs#OutVariableDeclarations "Out variable declarations")]

<span data-ttu-id="8252b-134">上記のように、わかりやすくするために `out` 変数の型を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="8252b-134">You may want to specify the type of the `out` variable for clarity, as shown above.</span></span> <span data-ttu-id="8252b-135">ただし、この言語では、次のように暗黙的に型指定されたローカル変数を使用できます。</span><span class="sxs-lookup"><span data-stu-id="8252b-135">However, the language does support using an implicitly typed local variable:</span></span>

[!code-csharp[OutVarVariableDeclarations](~/samples/snippets/csharp/new-in-7/program.cs#OutVarVariableDeclarations "Implicitly typed Out variable")]

* <span data-ttu-id="8252b-136">コードが読みやすくなる。</span><span class="sxs-lookup"><span data-stu-id="8252b-136">The code is easier to read.</span></span>
  - <span data-ttu-id="8252b-137">out 変数は、使用する場所で宣言します。その場所より上にある別の行で宣言しません。</span><span class="sxs-lookup"><span data-stu-id="8252b-137">You declare the out variable where you use it, not on another line above.</span></span>
* <span data-ttu-id="8252b-138">初期値を割り当てる必要がない。</span><span class="sxs-lookup"><span data-stu-id="8252b-138">No need to assign an initial value.</span></span>
  - <span data-ttu-id="8252b-139">`out` 変数は、メソッド呼び出し内の使用場所で宣言することにより、割り当てる前に誤って使用することがなくなります。</span><span class="sxs-lookup"><span data-stu-id="8252b-139">By declaring the `out` variable where it's used in a method call, you can't accidentally use it before it is assigned.</span></span>

## <a name="tuples"></a><span data-ttu-id="8252b-140">タプル</span><span class="sxs-lookup"><span data-stu-id="8252b-140">Tuples</span></span>

<span data-ttu-id="8252b-141">C# には、設計の意図を説明するために使用される、クラスと構造体の豊富な構文が用意されています。</span><span class="sxs-lookup"><span data-stu-id="8252b-141">C# provides a rich syntax for classes and structs that is used to explain your design intent.</span></span> <span data-ttu-id="8252b-142">ところが、場合によっては、その豊富な構文を使用するために、余分な作業が必要になることがあります。この場合、メリットはごくわずかです。</span><span class="sxs-lookup"><span data-stu-id="8252b-142">But sometimes that rich syntax requires extra work with minimal benefit.</span></span> <span data-ttu-id="8252b-143">複数のデータ要素を含む単純な構造を必要とするメソッドを記述することはよくあります。</span><span class="sxs-lookup"><span data-stu-id="8252b-143">You may often write methods that need a simple structure containing more than one data element.</span></span> <span data-ttu-id="8252b-144">このようなシナリオをサポートするために、C# には "*タプル*" が追加されました。</span><span class="sxs-lookup"><span data-stu-id="8252b-144">To support these scenarios *tuples* were added to C#.</span></span> <span data-ttu-id="8252b-145">タプルとは、データ メンバーを表す複数のフィールドを含む軽量なデータ構造です。</span><span class="sxs-lookup"><span data-stu-id="8252b-145">Tuples are lightweight data structures that contain multiple fields to represent the data members.</span></span>
<span data-ttu-id="8252b-146">フィールドは検証されず、独自のメソッドを定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="8252b-146">The fields aren't validated, and you can't define your own methods</span></span>

> [!NOTE]
> <span data-ttu-id="8252b-147">タプルは C# 7.0 より前で使用できましたが、効率的でなく、言語サポートがありませんでした。</span><span class="sxs-lookup"><span data-stu-id="8252b-147">Tuples were available before C# 7.0, but they were inefficient and had no language support.</span></span>
> <span data-ttu-id="8252b-148">これは、タプル要素が `Item1` や `Item2` などとしてのみ参照できることを意味しました。</span><span class="sxs-lookup"><span data-stu-id="8252b-148">This meant that tuple elements could only be referenced as `Item1`, `Item2` and so on.</span></span> <span data-ttu-id="8252b-149">C# 7.0 では、タプルの言語サポートが導入されたことで、新しい、より効率的なタプル型を使用するフィールドのセマンティック名が有効になります。</span><span class="sxs-lookup"><span data-stu-id="8252b-149">C# 7.0 introduces language support for tuples, which enables semantic names for the fields of a tuple using new, more efficient tuple types.</span></span>

<span data-ttu-id="8252b-150">各メンバーに値を割り当て、任意でタプルの各メンバーにセマンティック名を付けることでタプルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="8252b-150">You can create a tuple by assigning a value to each member, and optionally providing semantic names to each of the members of the tuple:</span></span>

[!code-csharp[NamedTuple](~/samples/snippets/csharp/new-in-7/program.cs#NamedTuple "Named tuple")]

<span data-ttu-id="8252b-151">`namedLetters` タプルには、`Alpha` と `Beta` と呼ばれるフィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8252b-151">The `namedLetters` tuple contains fields referred to as `Alpha` and `Beta`.</span></span> <span data-ttu-id="8252b-152">これらの名前は、コンパイル時にのみ存在し、実行時にリフレクションを使用してタプルを検査するときなどには保持されません。</span><span class="sxs-lookup"><span data-stu-id="8252b-152">Those names exist only at compile time and aren't preserved, for example when inspecting the tuple using reflection at runtime.</span></span>

<span data-ttu-id="8252b-153">タプルの割り当てでは、代入の右辺でフィールドの名前を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="8252b-153">In a tuple assignment, you can also specify the names of the fields on the right-hand side of the assignment:</span></span>

[!code-csharp[ImplicitNamedTuple](~/samples/snippets/csharp/new-in-7/program.cs#ImplicitNamedTuple "Implicitly named tuple")]

<span data-ttu-id="8252b-154">状況によっては、メソッドから返されたタプルのメンバーをばらすことが必要になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="8252b-154">There may be times when you want to unpackage the members of a tuple that were returned from a method.</span></span>  <span data-ttu-id="8252b-155">そのためには、タプル内のそれぞれの値に対して別個の変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="8252b-155">You can do that by declaring separate variables for each of the values in the tuple.</span></span> <span data-ttu-id="8252b-156">このばらす行為は、タプルの*分解*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="8252b-156">This unpackaging is called *deconstructing* the tuple:</span></span>

[!code-csharp[CallingWithDeconstructor](~/samples/snippets/csharp/new-in-7/program.cs#CallingWithDeconstructor "Deconstructing a tuple")]

<span data-ttu-id="8252b-157">.NET でも任意の型に同様の分解を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="8252b-157">You can also provide a similar deconstruction for any type in .NET.</span></span> <span data-ttu-id="8252b-158">クラスのメンバーとして `Deconstruct` メソッドを記述します。</span><span class="sxs-lookup"><span data-stu-id="8252b-158">You write a `Deconstruct` method as a member of the class.</span></span> <span data-ttu-id="8252b-159">その `Deconstruct` メソッドは、抽出する各プロパティ用に一連の `out` 引数を提供します。</span><span class="sxs-lookup"><span data-stu-id="8252b-159">That `Deconstruct` method provides a set of `out` arguments for each of the properties you want to extract.</span></span> <span data-ttu-id="8252b-160">次の `Point` クラスを考えてみましょう。このクラスは、`X` 座標と `Y` 座標を抽出するデコンストラクター メソッドを指定しています。</span><span class="sxs-lookup"><span data-stu-id="8252b-160">Consider this `Point` class that provides a deconstructor method that extracts the `X` and `Y` coordinates:</span></span>

[!code-csharp[PointWithDeconstruction](~/samples/snippets/csharp/new-in-7/point.cs#PointWithDeconstruction "Point with deconstruction method")]

<span data-ttu-id="8252b-161">`Point` をタプルに割り当てて、個々のフィールドを抽出できます。</span><span class="sxs-lookup"><span data-stu-id="8252b-161">You can extract the individual fields by assigning a `Point` to a tuple:</span></span>

[!code-csharp[DeconstructPoint](~/samples/snippets/csharp/new-in-7/program.cs#DeconstructPoint "Deconstruct a point")]

<span data-ttu-id="8252b-162">タプルの詳細については、[タプルに関する記事](../tuples.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8252b-162">You can learn more in depth about tuples in the [tuples article](../tuples.md).</span></span>

## <a name="discards"></a><span data-ttu-id="8252b-163">破棄</span><span class="sxs-lookup"><span data-stu-id="8252b-163">Discards</span></span>

<span data-ttu-id="8252b-164">`out` パラメーターを使用してタプルを分解したりメソッドを呼び出したりする場合に、使用する予定がなく、考慮にも入れない値の変数の定義を強制されることが多くあります。</span><span class="sxs-lookup"><span data-stu-id="8252b-164">Often when deconstructing a tuple or calling a method with `out` parameters, you're forced to define a variable whose value you don't care about and don't intend to use.</span></span> <span data-ttu-id="8252b-165">C# ではこのシナリオを処理するために*破棄*のサポートを追加しています。</span><span class="sxs-lookup"><span data-stu-id="8252b-165">C# adds support for *discards* to handle this scenario.</span></span> <span data-ttu-id="8252b-166">破棄は名前が `_` (アンダースコア (_) 文字) の書き込み専用の変数で、破棄するすべての値をこの 1 つの変数に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="8252b-166">A discard is a write-only variable whose name is `_` (the underscore character); you can assign all of the values that you intend to discard to the single variable.</span></span> <span data-ttu-id="8252b-167">破棄は未割り当ての変数に似ています。代入ステートメントとは異なり、破棄はコードで使用できません。</span><span class="sxs-lookup"><span data-stu-id="8252b-167">A discard is like an unassigned variable; apart from the assignment statement, the discard can't be used in code.</span></span>

<span data-ttu-id="8252b-168">次のシナリオでは破棄はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="8252b-168">Discards are supported in the following scenarios:</span></span>

* <span data-ttu-id="8252b-169">タプルまたはユーザー定義の型を分解する場合。</span><span class="sxs-lookup"><span data-stu-id="8252b-169">When deconstructing tuples or user-defined types.</span></span>
* <span data-ttu-id="8252b-170">[out](../language-reference/keywords/out-parameter-modifier.md) パラメーターを使用してメソッドを呼び出す場合。</span><span class="sxs-lookup"><span data-stu-id="8252b-170">When calling methods with [out](../language-reference/keywords/out-parameter-modifier.md) parameters.</span></span>
* <span data-ttu-id="8252b-171">[is](../language-reference/keywords/is.md) および [switch](../language-reference/keywords/switch.md) ステートメントによるパターン マッチング操作。</span><span class="sxs-lookup"><span data-stu-id="8252b-171">In a pattern matching operation with the [is](../language-reference/keywords/is.md) and [switch](../language-reference/keywords/switch.md) statements.</span></span>
* <span data-ttu-id="8252b-172">割り当ての値を破棄として明示的に識別する必要がある場合の、スタンドアロン識別子。</span><span class="sxs-lookup"><span data-stu-id="8252b-172">As a standalone identifier when you want to explicitly identify the value of an assignment as a discard.</span></span>

<span data-ttu-id="8252b-173">次の例では、ある都市の 2 つの異なる年度のデータを含む 6 つのタプルを戻す `QueryCityDataForYears` メソッドを定義しています。</span><span class="sxs-lookup"><span data-stu-id="8252b-173">The following example defines a `QueryCityDataForYears` method that returns a 6-tuple that contains data for a city for two different years.</span></span> <span data-ttu-id="8252b-174">この例のメソッド呼び出しでは、メソッドによって戻された 2 つの人口の値のみが考慮されているため、タプルの残りの値はタプルの分解時に破棄として扱われます。</span><span class="sxs-lookup"><span data-stu-id="8252b-174">The method call in the example is concerned only with the two population values returned by the method and so treats the remaining values in the tuple as discards when it deconstructs the tuple.</span></span>

[!code-csharp[Tuple-discard](~/samples/snippets/csharp/programming-guide/deconstructing-tuples/discard-tuple1.cs)]

<span data-ttu-id="8252b-175">詳細については、[破棄](../discards.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8252b-175">For more information, see [Discards](../discards.md).</span></span>

## <a name="pattern-matching"></a><span data-ttu-id="8252b-176">パターン マッチング</span><span class="sxs-lookup"><span data-stu-id="8252b-176">Pattern matching</span></span>

<span data-ttu-id="8252b-177">"*パターン マッチング*" は、オブジェクトの型以外のプロパティでメソッドのディスパッチを実装できるようにする機能です。</span><span class="sxs-lookup"><span data-stu-id="8252b-177">*Pattern matching* is a feature that allows you to implement method dispatch on properties other than the type of an object.</span></span> <span data-ttu-id="8252b-178">オブジェクトの型に基づいたメソッドのディスパッチに慣れている方も多いはずです。</span><span class="sxs-lookup"><span data-stu-id="8252b-178">You're probably already familiar with method dispatch based on the type of an object.</span></span> <span data-ttu-id="8252b-179">オブジェクト指向プログラミングでは、仮想メソッドとオーバーライド メソッドには、オブジェクトの型に基づくメソッドのディスパッチを実装するための言語構文が用意されています。</span><span class="sxs-lookup"><span data-stu-id="8252b-179">In object-oriented programming, virtual and override methods provide language syntax to implement method dispatching based on an object's type.</span></span> <span data-ttu-id="8252b-180">基底クラスと派生クラスは異なる実装を提供します。</span><span class="sxs-lookup"><span data-stu-id="8252b-180">Base and Derived classes provide different implementations.</span></span>
<span data-ttu-id="8252b-181">パターン マッチング式により、この概念が拡張されたため、継承階層を介して関連していない型やデータ要素に同様のディスパッチ パターンを簡単に実装できるようになります。</span><span class="sxs-lookup"><span data-stu-id="8252b-181">Pattern matching expressions extend this concept so that you can easily implement similar dispatch patterns for types and data elements that aren't related through an inheritance hierarchy.</span></span>

<span data-ttu-id="8252b-182">パターン マッチングでは、`is` 式と `switch` 式がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8252b-182">Pattern matching supports `is` expressions and `switch` expressions.</span></span> <span data-ttu-id="8252b-183">どちらの式でも、オブジェクトとそのプロパティを検査して、そのオブジェクトが必要なパターンを満たしているかどうかを判定できます。</span><span class="sxs-lookup"><span data-stu-id="8252b-183">Each enables inspecting an object and its properties to determine if that object satisfies the sought pattern.</span></span> <span data-ttu-id="8252b-184">パターンに追加の規則を指定するには、`when` キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="8252b-184">You use the `when` keyword to specify additional rules to the pattern.</span></span>

<span data-ttu-id="8252b-185">`is` パターン式を使用すると、使い慣れた [`is` 演算子](../language-reference/keywords/is.md#pattern-matching-with-is)を拡張し、その型を超えてオブジェクトを照会したり、1 つの命令で結果を割り当てたりできます。</span><span class="sxs-lookup"><span data-stu-id="8252b-185">The `is` pattern expression extends the familiar [`is` operator](../language-reference/keywords/is.md#pattern-matching-with-is) to query an object about its type and assign the result in one instruction.</span></span> <span data-ttu-id="8252b-186">次のコードでは、変数が `int` であるかどうかが確認されます。int の場合、現在の合計に追加されます。</span><span class="sxs-lookup"><span data-stu-id="8252b-186">The following code checks if a variable is an `int`, and if so, adds it to the current sum:</span></span>

```csharp
if (input is int count)
    sum += count;
```

<span data-ttu-id="8252b-187">先の小さな例では、`is` 式の拡張が示されています。</span><span class="sxs-lookup"><span data-stu-id="8252b-187">The preceding small example demonstrates the enhancements to the `is` expression.</span></span> <span data-ttu-id="8252b-188">値の型や参照型に対してテストしたり、正しい型の新しい変数に成功した結果を割り当てたりできます。</span><span class="sxs-lookup"><span data-stu-id="8252b-188">You can test against value types as well as reference types, and you can assign the successful result to a new variable of the correct type.</span></span>

<span data-ttu-id="8252b-189">switch 一致式には、既に C# 言語に含まれている `switch` ステートメントに基づいた、使い慣れた構文があります。</span><span class="sxs-lookup"><span data-stu-id="8252b-189">The switch match expression has a familiar syntax, based on the `switch` statement already part of the C# language.</span></span> <span data-ttu-id="8252b-190">更新された switch 式には新しいコンストラクトがいくつか含まれます。</span><span class="sxs-lookup"><span data-stu-id="8252b-190">The updated switch statement has several new constructs:</span></span>

- <span data-ttu-id="8252b-191">`switch` 式を制御する型は、整数型、`Enum` 型、`string`、あるいはそれらの型のいずれかに対応する null 許容型に制限されなくなります。</span><span class="sxs-lookup"><span data-stu-id="8252b-191">The governing type of a `switch` expression is no longer restricted to integral types, `Enum` types, `string`, or a nullable type corresponding to one of those types.</span></span> <span data-ttu-id="8252b-192">任意の型を使用できます。</span><span class="sxs-lookup"><span data-stu-id="8252b-192">Any type may be used.</span></span>
- <span data-ttu-id="8252b-193">各 `case` ラベルで `switch` 式の型をテストできます。</span><span class="sxs-lookup"><span data-stu-id="8252b-193">You can test the type of the `switch` expression in each `case` label.</span></span> <span data-ttu-id="8252b-194">`is` 式と同様に、その型に新しい変数を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="8252b-194">As with the `is` expression, you may assign a new variable to that type.</span></span>
- <span data-ttu-id="8252b-195">`when` 句を追加し、その変数で条件をさらにテストできます。</span><span class="sxs-lookup"><span data-stu-id="8252b-195">You may add a `when` clause to further test conditions on that variable.</span></span>
- <span data-ttu-id="8252b-196">`case` ラベルの順序が重要になります。</span><span class="sxs-lookup"><span data-stu-id="8252b-196">The order of `case` labels is now important.</span></span> <span data-ttu-id="8252b-197">一致する最初の分岐が実行されます。他の分岐はスキップされます。</span><span class="sxs-lookup"><span data-stu-id="8252b-197">The first branch to match is executed; others are skipped.</span></span>

<span data-ttu-id="8252b-198">次のコードでこれらの新しい機能を確認できます。</span><span class="sxs-lookup"><span data-stu-id="8252b-198">The following code demonstrates these new features:</span></span>

```csharp
public static int SumPositiveNumbers(IEnumerable<object> sequence)
{
    int sum = 0;
    foreach (var i in sequence)
    {
        switch (i)
        {
            case 0:
                break;
            case IEnumerable<int> childSequence:
            {
                foreach(var item in childSequence)
                    sum += (item > 0) ? item : 0;
                break;
            }
            case int n when n > 0:
                sum += n;
                break;
            case null:
                throw new NullReferenceException("Null found in sequence");
            default:
                throw new InvalidOperationException("Unrecognized type");
        }
    }
    return sum;
}
```

- <span data-ttu-id="8252b-199">`case 0:` はおなじみの定数パターンです。</span><span class="sxs-lookup"><span data-stu-id="8252b-199">`case 0:` is the familiar constant pattern.</span></span>
- <span data-ttu-id="8252b-200">`case IEnumerable<int> childSequence:` は型パターンです。</span><span class="sxs-lookup"><span data-stu-id="8252b-200">`case IEnumerable<int> childSequence:` is a type pattern.</span></span>
- <span data-ttu-id="8252b-201">`case int n when n > 0:` は `when` 条件が追加された型パターンです。</span><span class="sxs-lookup"><span data-stu-id="8252b-201">`case int n when n > 0:` is a type pattern with an additional `when` condition.</span></span>
- <span data-ttu-id="8252b-202">`case null:` は null パターンです。</span><span class="sxs-lookup"><span data-stu-id="8252b-202">`case null:` is the null pattern.</span></span>
- <span data-ttu-id="8252b-203">`default:` はおなじみの既定ケースです。</span><span class="sxs-lookup"><span data-stu-id="8252b-203">`default:` is the familiar default case.</span></span>

<span data-ttu-id="8252b-204">パターン マッチングの詳細については、[C# のパターン マッチング](../pattern-matching.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8252b-204">You can learn more about pattern matching in [Pattern Matching in C#](../pattern-matching.md).</span></span>

## <a name="ref-locals-and-returns"></a><span data-ttu-id="8252b-205">ref ローカル変数と戻り値</span><span class="sxs-lookup"><span data-stu-id="8252b-205">Ref locals and returns</span></span>

<span data-ttu-id="8252b-206">この機能により、他の場所に定義されている変数への参照を使用したり返したりするアルゴリズムが実現します。</span><span class="sxs-lookup"><span data-stu-id="8252b-206">This feature enables algorithms that use and return references to variables defined elsewhere.</span></span> <span data-ttu-id="8252b-207">1 つの例として、大規模なマトリックスを使用していて、特定の特性を持つ 1 つの場所を探します。</span><span class="sxs-lookup"><span data-stu-id="8252b-207">One example is working with large matrices, and finding a single location with certain characteristics.</span></span> <span data-ttu-id="8252b-208">次のメソッドでは、マトリックスのそのストレージに**参照**が返されます。</span><span class="sxs-lookup"><span data-stu-id="8252b-208">The following method returns a **reference** to that storage in the matrix:</span></span>

[!code-csharp[FindReturningRef](~/samples/snippets/csharp/new-in-7/MatrixSearch.cs#FindReturningRef "Find returning by reference")]

<span data-ttu-id="8252b-209">戻り値を `ref` として宣言し、次のコードのように、マトリックスでその値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="8252b-209">You can declare the return value as a `ref` and modify that value in the matrix, as shown in the following code:</span></span>

[!code-csharp[AssignRefReturn](~/samples/snippets/csharp/new-in-7/Program.cs#AssignRefReturn "Assign ref return")]

<span data-ttu-id="8252b-210">C# 言語には、`ref` ローカル変数と戻り値の誤用を防ぐ規則がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="8252b-210">The C# language has several rules that protect you from misusing the `ref` locals and returns:</span></span>

* <span data-ttu-id="8252b-211">メソッド シグネチャと、メソッド内のすべての `return` ステートメントに `ref` キーワードを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8252b-211">You must add the `ref` keyword to the method signature and to all `return` statements in a method.</span></span>
  - <span data-ttu-id="8252b-212">それにより、メソッド全体でメソッドは参照渡しで返すことになります。</span><span class="sxs-lookup"><span data-stu-id="8252b-212">That makes it clear the method returns by reference throughout the method.</span></span>
* <span data-ttu-id="8252b-213">`ref return` は値の変数か `ref` 変数に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="8252b-213">A `ref return` may be assigned to a value variable, or a `ref` variable.</span></span>
  - <span data-ttu-id="8252b-214">呼び出し元により、戻り値がコピーされるかどうかが制御されます。</span><span class="sxs-lookup"><span data-stu-id="8252b-214">The caller controls whether the return value is copied or not.</span></span> <span data-ttu-id="8252b-215">戻り値を割り当てるとき、`ref` 修飾子を省略すると、呼び出し元はストレージの参照ではなく、値のコピーを求めることになります。</span><span class="sxs-lookup"><span data-stu-id="8252b-215">Omitting the `ref` modifier when assigning the return value indicates that the caller wants a copy of the value, not a reference to the storage.</span></span>
* <span data-ttu-id="8252b-216">標準的なメソッドの戻り値を `ref` ローカル変数に割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="8252b-216">You can't assign a standard method return value to a `ref` local variable.</span></span>
  - <span data-ttu-id="8252b-217">したがって、`ref int i = sequence.Count();` のようなステートメントは使用できません。</span><span class="sxs-lookup"><span data-stu-id="8252b-217">That disallows statements like `ref int i = sequence.Count();`</span></span>
* <span data-ttu-id="8252b-218">有効期間がメソッドの実行期間を超えない変数に `ref` を返すことはできません。</span><span class="sxs-lookup"><span data-stu-id="8252b-218">You can't return a `ref` to a variable whose lifetime doesn't extend beyond the execution of the method.</span></span>
  - <span data-ttu-id="8252b-219">つまり、ローカル変数または類似のスコープの変数への参照を返すことはできません。</span><span class="sxs-lookup"><span data-stu-id="8252b-219">That means you can't return a reference to a local variable or a variable with a similar scope.</span></span>
* <span data-ttu-id="8252b-220">`ref` ローカル変数と戻り値は、非同期メソッドと共に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="8252b-220">`ref` locals and returns can't be used with async methods.</span></span>
  - <span data-ttu-id="8252b-221">コンパイラは、非同期メソッドが戻るときに、参照先の変数が、最終的な値に設定されているかどうかを認識できません。</span><span class="sxs-lookup"><span data-stu-id="8252b-221">The compiler can't know if the referenced variable has been set to its final value when the async method returns.</span></span>

<span data-ttu-id="8252b-222">ref ローカル変数および ref 戻り値の追加により、値のコピーを回避したり、逆参照操作を複数回実行したりすることで、より効率的なアルゴリズムを実現できます。</span><span class="sxs-lookup"><span data-stu-id="8252b-222">The addition of ref locals and ref returns enables algorithms that are more efficient by avoiding copying values, or performing dereferencing operations multiple times.</span></span>

<span data-ttu-id="8252b-223">戻り値に `ref` を追加することは、[ソース互換性がある変更](version-update-considerations.md#source-compatible-changes)です。</span><span class="sxs-lookup"><span data-stu-id="8252b-223">Adding `ref` to the return value is a [source compatible change](version-update-considerations.md#source-compatible-changes).</span></span> <span data-ttu-id="8252b-224">既存のコードはコンパイルされますが、参照戻り値は割り当て時にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="8252b-224">Existing code compiles, but the ref return value is copied when assigned.</span></span> <span data-ttu-id="8252b-225">呼び出し元は、戻り値を参照として格納するために、戻り値の記憶域を `ref` ローカル変数に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8252b-225">Callers must update the storage for the return value to a `ref` local variable to store the return as a reference.</span></span>

<span data-ttu-id="8252b-226">詳しくは、[ref](../language-reference/keywords/ref.md) キーワードに関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8252b-226">For more information, see the [ref keyword](../language-reference/keywords/ref.md) article.</span></span>

## <a name="local-functions"></a><span data-ttu-id="8252b-227">ローカル関数</span><span class="sxs-lookup"><span data-stu-id="8252b-227">Local functions</span></span>

<span data-ttu-id="8252b-228">クラスの多くの設計には、1 つの場所からのみ呼び出されるメソッドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8252b-228">Many designs for classes include methods that are called from only one location.</span></span> <span data-ttu-id="8252b-229">このような追加のプライベート メソッドを使用することで、各メソッドのサイズを小さくし、その焦点を絞ることができます。</span><span class="sxs-lookup"><span data-stu-id="8252b-229">These additional private methods keep each method small and focused.</span></span> <span data-ttu-id="8252b-230">*ローカル関数*を使用すると、別のメソッドのコンテキスト内でメソッドを宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="8252b-230">*Local functions* enable you to declare methods inside the context of another method.</span></span> <span data-ttu-id="8252b-231">ローカル関数のおかげで、クラスを読み取る際に、ローカル メソッドはそれ自体が宣言されているコンテキストからしか呼び出されないことが、簡単にわかります。</span><span class="sxs-lookup"><span data-stu-id="8252b-231">Local functions make it easier for readers of the class to see that the local method is only called from the context in which it is declared.</span></span>

<span data-ttu-id="8252b-232">ローカル関数には、パブリック反復子メソッドとパブリック非同期メソッドという 2 つの一般的なユース ケースがあります。</span><span class="sxs-lookup"><span data-stu-id="8252b-232">There are two common use cases for local functions: public iterator methods and public async methods.</span></span> <span data-ttu-id="8252b-233">どちらの種類のメソッドも、プログラマーが期待するよりも遅くエラーを報告するコードを生成します。</span><span class="sxs-lookup"><span data-stu-id="8252b-233">Both types of methods generate code that reports errors later than programmers might expect.</span></span> <span data-ttu-id="8252b-234">反復子メソッドの場合、例外が検出されるのは、返されたシーケンスを列挙するコードを呼び出した場合のみです。</span><span class="sxs-lookup"><span data-stu-id="8252b-234">In iterator methods, any exceptions are observed only when calling code that enumerates the returned sequence.</span></span> <span data-ttu-id="8252b-235">非同期メソッドの場合、例外が検出されるのは、返された `Task` が待機状態になったときのみです。</span><span class="sxs-lookup"><span data-stu-id="8252b-235">In async methods, any exceptions are only observed when the returned `Task` is awaited.</span></span> <span data-ttu-id="8252b-236">次の例では、ローカル関数を使用し、反復子の実装からパラメーター検証を分ける動作を確認できます。</span><span class="sxs-lookup"><span data-stu-id="8252b-236">The following example demonstrates separating parameter validation from the iterator implementation using a local function:</span></span>

[!code-csharp[22_IteratorMethodLocal](~/samples/snippets/csharp/new-in-7/Iterator.cs#IteratorMethodLocal "Iterator method with local function")]

<span data-ttu-id="8252b-237">同じ手法を `async` メソッドで使用すると、引数の検証で発生する例外が非同期操作の開始前にスローされることを保証できます。</span><span class="sxs-lookup"><span data-stu-id="8252b-237">The same technique can be employed with `async` methods to ensure that exceptions arising from argument validation are thrown before the asynchronous work begins:</span></span>

[!code-csharp[TaskExample](~/samples/snippets/csharp/new-in-7/AsyncWork.cs#TaskExample "Task returning method with local function")]

> [!NOTE]
> <span data-ttu-id="8252b-238">ローカル関数によってサポートされる設計の中には、"*ラムダ式*" を使用して実現できるものもあります。</span><span class="sxs-lookup"><span data-stu-id="8252b-238">Some of the designs that are supported by local functions could also be accomplished using *lambda expressions*.</span></span> <span data-ttu-id="8252b-239">興味のある方は、[その違いの詳細を確認してください](../local-functions-vs-lambdas.md)。</span><span class="sxs-lookup"><span data-stu-id="8252b-239">Those interested can [read more about the differences](../local-functions-vs-lambdas.md)</span></span>

## <a name="more-expression-bodied-members"></a><span data-ttu-id="8252b-240">式形式のメンバーの追加</span><span class="sxs-lookup"><span data-stu-id="8252b-240">More expression-bodied members</span></span>

<span data-ttu-id="8252b-241">C# 6 では、メンバー関数の[式形式のメンバー](csharp-6.md#expression-bodied-function-members)と読み取り専用プロパティが導入されました。</span><span class="sxs-lookup"><span data-stu-id="8252b-241">C# 6 introduced [expression-bodied members](csharp-6.md#expression-bodied-function-members) for member functions, and read-only properties.</span></span> <span data-ttu-id="8252b-242">C# 7.0 では、式として実装できる許可されたメンバーが拡張されます。</span><span class="sxs-lookup"><span data-stu-id="8252b-242">C# 7.0 expands the allowed members that can be implemented as expressions.</span></span> <span data-ttu-id="8252b-243">C# 7.0 では、"*コンストラクター*"、"*ファイナライザー*"、`get` アクセサー、および `set` アクセサーを "*プロパティ*" と "*インデクサー*" に実装できます。</span><span class="sxs-lookup"><span data-stu-id="8252b-243">In C# 7.0, you can implement *constructors*, *finalizers*, and `get` and `set` accessors on *properties* and *indexers*.</span></span> <span data-ttu-id="8252b-244">それぞれの例を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="8252b-244">The following code shows examples of each:</span></span>

[!code-csharp[ExpressionBodiedMembers](~/samples/snippets/csharp/new-in-7/expressionmembers.cs#ExpressionBodiedEverything "new expression-bodied members")]

> [!NOTE]
> <span data-ttu-id="8252b-245">この例ではファイナライザーは必要ありませんが、その構文を紹介するために示しています。</span><span class="sxs-lookup"><span data-stu-id="8252b-245">This example does not need a finalizer, but it is shown to demonstrate the syntax.</span></span> <span data-ttu-id="8252b-246">アンマネージ リソースを解放する必要がない限り、クラスにファイナライザーを実装しないでください。</span><span class="sxs-lookup"><span data-stu-id="8252b-246">You should not implement a finalizer in your class unless it is necessary to  release unmanaged resources.</span></span> <span data-ttu-id="8252b-247">また、アンマネージ リソースを直接管理する代わりに、<xref:System.Runtime.InteropServices.SafeHandle> クラスの使用を検討する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="8252b-247">You should also consider using the <xref:System.Runtime.InteropServices.SafeHandle> class instead of managing unmanaged resources directly.</span></span>

<span data-ttu-id="8252b-248">式形式のメンバー用のこれらの新しい場所は、C# 言語の重要なマイルストーンです。これらの機能は、オープン ソースの [Roslyn](https://github.com/dotnet/Roslyn) プロジェクトに関わるコミュニティ メンバーによって実装されました。</span><span class="sxs-lookup"><span data-stu-id="8252b-248">These new locations for expression-bodied members represent an important milestone for the C# language: These features were implemented by community members working on the open-source [Roslyn](https://github.com/dotnet/Roslyn) project.</span></span>

<span data-ttu-id="8252b-249">メソッドを式のようなメンバーに変更することは、[バイナリ互換性がある変更](version-update-considerations.md#binary-compatible-changes)です。</span><span class="sxs-lookup"><span data-stu-id="8252b-249">Changing a method to an expression bodied member is a [binary compatible change](version-update-considerations.md#binary-compatible-changes).</span></span>

## <a name="throw-expressions"></a><span data-ttu-id="8252b-250">throw 式</span><span class="sxs-lookup"><span data-stu-id="8252b-250">Throw expressions</span></span>

<span data-ttu-id="8252b-251">C# では、`throw` は常にステートメントでした。</span><span class="sxs-lookup"><span data-stu-id="8252b-251">In C#, `throw` has always been a statement.</span></span> <span data-ttu-id="8252b-252">`throw` は式ではなくステートメントであるため、使用できない C# コンストラクトがありました。</span><span class="sxs-lookup"><span data-stu-id="8252b-252">Because `throw` is a statement, not an expression, there were C# constructs where you couldn't use it.</span></span> <span data-ttu-id="8252b-253">これには、条件式、null 結合式、および一部のラムダ式が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8252b-253">These included conditional expressions, null coalescing expressions, and some lambda expressions.</span></span> <span data-ttu-id="8252b-254">式形式のメンバーが追加されたことにより、さらに多くの場所で `throw` 式が役に立つようになりました。</span><span class="sxs-lookup"><span data-stu-id="8252b-254">The addition of expression-bodied members adds more locations where `throw` expressions would be useful.</span></span> <span data-ttu-id="8252b-255">C# 7.0 では、このようなコンストラクトを記述できるように、[*throw 式*](../language-reference/keywords/throw.md#the-throw-expression)が導入されています。</span><span class="sxs-lookup"><span data-stu-id="8252b-255">So that you can write any of these constructs, C# 7.0 introduces [*throw expressions*](../language-reference/keywords/throw.md#the-throw-expression).</span></span>

<span data-ttu-id="8252b-256">この導入により、式ベースのコードをたくさん記述することが簡単になります。</span><span class="sxs-lookup"><span data-stu-id="8252b-256">This addition makes it easier to write more expression-based code.</span></span> <span data-ttu-id="8252b-257">エラー チェックのためにステートメントを追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8252b-257">You don't need additional statements for error checking.</span></span>

## <a name="generalized-async-return-types"></a><span data-ttu-id="8252b-258">一般化された async の戻り値の型</span><span class="sxs-lookup"><span data-stu-id="8252b-258">Generalized async return types</span></span>

<span data-ttu-id="8252b-259">非同期メソッドから `Task` オブジェクトを返すと、特定のパスでパフォーマンスのボトルネックが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8252b-259">Returning a `Task` object from async methods can introduce performance bottlenecks in certain paths.</span></span> <span data-ttu-id="8252b-260">`Task` は参照型です。したがって、これを使うことは、オブジェクトを割り当てることを意味します。</span><span class="sxs-lookup"><span data-stu-id="8252b-260">`Task` is a reference type, so using it means allocating an object.</span></span> <span data-ttu-id="8252b-261">`async` 修飾子で宣言されたメソッドがキャッシュされた結果を返すか、同期的に完了する場合、追加の割り当ては、コードのパフォーマンスが重要なセクションにおいて大きな時間コストにつながります。</span><span class="sxs-lookup"><span data-stu-id="8252b-261">In cases where a method declared with the `async` modifier returns a cached result, or completes synchronously, the extra allocations can become a significant time cost in performance critical sections of code.</span></span> <span data-ttu-id="8252b-262">厳密なループ処理でこのような割り当てが発生した場合、コストがかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8252b-262">It can become costly if those allocations occur in tight loops.</span></span>

<span data-ttu-id="8252b-263">新しい言語機能では、非同期メソッドの戻り値の型が `Task`、`Task<T>`、`void` に限定されません。</span><span class="sxs-lookup"><span data-stu-id="8252b-263">The new language feature means that async method return types aren't limited to `Task`, `Task<T>`, and `void`.</span></span> <span data-ttu-id="8252b-264">返される型は引き続き非同期パターンを満たす必要があります。つまり、`GetAwaiter` メソッドはアクセス可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8252b-264">The returned type must still satisfy the async pattern, meaning a `GetAwaiter` method must be accessible.</span></span> <span data-ttu-id="8252b-265">1 つの具体的な例として、この新しい言語機能を使用するために .NET Framework に `ValueTask` 型が追加されました。</span><span class="sxs-lookup"><span data-stu-id="8252b-265">As one concrete example, the `ValueTask` type has been added to the .NET framework to make use of this new language feature:</span></span>

[!code-csharp[UsingValueTask](~/samples/snippets/csharp/new-in-7/AsyncWork.cs#UsingValueTask "Using ValueTask")]

> [!NOTE]
> <span data-ttu-id="8252b-266"><xref:System.Threading.Tasks.ValueTask%601> 型を使用するには、NuGet パッケージ [`System.Threading.Tasks.Extensions`](https://www.nuget.org/packages/System.Threading.Tasks.Extensions/) を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8252b-266">You need to add the NuGet package [`System.Threading.Tasks.Extensions`](https://www.nuget.org/packages/System.Threading.Tasks.Extensions/) in order to use the <xref:System.Threading.Tasks.ValueTask%601> type.</span></span>

<span data-ttu-id="8252b-267">この機能強化は、ライブラリの作成時、パフォーマンス クリティカルなコードに `Task` を割り当てることを回避する目的で非常に便利です。</span><span class="sxs-lookup"><span data-stu-id="8252b-267">This enhancement is most useful for library authors to avoid allocating a `Task` in performance critical code.</span></span>

## <a name="numeric-literal-syntax-improvements"></a><span data-ttu-id="8252b-268">数値リテラルの構文の改善</span><span class="sxs-lookup"><span data-stu-id="8252b-268">Numeric literal syntax improvements</span></span>

<span data-ttu-id="8252b-269">数値定数を読み間違えると、コードを初めて読むときにコードを理解するのが難しくなる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8252b-269">Misreading numeric constants can make it harder to understand code when reading it for the first time.</span></span> <span data-ttu-id="8252b-270">ビット マスクやその他の記号を用いた値では誤解を招きやすくなります。</span><span class="sxs-lookup"><span data-stu-id="8252b-270">Bit masks or other symbolic values are prone to misunderstanding.</span></span> <span data-ttu-id="8252b-271">C# 7.0 では、使用目的に応じて最も読みやすい形式で数値を記述しできるように、*バイナリ リテラル*と*桁区切り文字*という 2 つの新機能が導入されました。</span><span class="sxs-lookup"><span data-stu-id="8252b-271">C# 7.0 includes two new features to write numbers in the most readable fashion for the intended use: *binary literals*, and *digit separators*.</span></span>

<span data-ttu-id="8252b-272">ビット マスクを作成しているときや、数値をバイナリで表現するとコードが最も読みやすくなる場合は、数字をバイナリで記述します。</span><span class="sxs-lookup"><span data-stu-id="8252b-272">For those times when you're creating bit masks, or whenever a binary representation of a number makes the most readable code, write that number in binary:</span></span>

[!code-csharp[ThousandSeparators](~/samples/snippets/csharp/new-in-7/Program.cs#ThousandSeparators "Thousands separators")]

<span data-ttu-id="8252b-273">定数の先頭にある `0b` は、数値が 2 進数として記述されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="8252b-273">The `0b` at the beginning of the constant indicates that the number is written as a binary number.</span></span> <span data-ttu-id="8252b-274">バイナリ数値は非常に長くなる場合があるため、ビット パターンが見やすくなるように、桁区切り記号として `_` が導入されました。上の画像のバイナリ定数で確認できます。</span><span class="sxs-lookup"><span data-stu-id="8252b-274">Binary numbers can get long, so it's often easier to see the bit patterns by introducing the `_` as a digit separator, as shown above in the binary constant.</span></span> <span data-ttu-id="8252b-275">桁区切り記号は定数のどこにでも置くことができます。</span><span class="sxs-lookup"><span data-stu-id="8252b-275">The digit separator can appear anywhere in the constant.</span></span> <span data-ttu-id="8252b-276">10 進数の場合は、3 桁の区切り記号として使用するのが一般的です。</span><span class="sxs-lookup"><span data-stu-id="8252b-276">For base 10 numbers, it is common to use it as a thousands separator:</span></span>

[!code-csharp[LargeIntegers](~/samples/snippets/csharp/new-in-7/Program.cs#LargeIntegers "Large integer")]

<span data-ttu-id="8252b-277">桁区切り記号は、`decimal` 型、`float` 型、`double` 型でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="8252b-277">The digit separator can be used with `decimal`, `float`, and `double` types as well:</span></span>

[!code-csharp[OtherConstants](~/samples/snippets/csharp/new-in-7/Program.cs#OtherConstants "non-integral constants")]

<span data-ttu-id="8252b-278">これらをまとめると、数値定数をさらに見やすい状態で宣言できます。</span><span class="sxs-lookup"><span data-stu-id="8252b-278">Taken together, you can declare numeric constants with much more readability.</span></span>
