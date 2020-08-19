---
title: コード クォート
description: 'F # コードの引用符について説明します。これは、プログラムで F # コード式を生成して操作できる言語機能です。'
ms.date: 08/13/2020
ms.openlocfilehash: 070e127397a5da7d70281d08ef7cafdb9b4f4fe5
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558336"
---
# <a name="code-quotations"></a><span data-ttu-id="c4f33-103">コード引用符</span><span class="sxs-lookup"><span data-stu-id="c4f33-103">Code quotations</span></span>

<span data-ttu-id="c4f33-104">この記事では、 *コードの引用符*について説明します。これは、プログラムによって F # コード式を生成して操作できる言語機能です。</span><span class="sxs-lookup"><span data-stu-id="c4f33-104">This article describes *code quotations*, a language feature that enables you to generate and work with F# code expressions programmatically.</span></span> <span data-ttu-id="c4f33-105">この機能を使用すると、F # コードを表す抽象構文ツリーを生成できます。</span><span class="sxs-lookup"><span data-stu-id="c4f33-105">This feature lets you generate an abstract syntax tree that represents F# code.</span></span> <span data-ttu-id="c4f33-106">次に、アプリケーションのニーズに応じて、抽象構文ツリーを走査して処理できます。</span><span class="sxs-lookup"><span data-stu-id="c4f33-106">The abstract syntax tree can then be traversed and processed according to the needs of your application.</span></span> <span data-ttu-id="c4f33-107">たとえば、ツリーを使用すると、F # コードを生成したり、他の言語でコードを生成したりできます。</span><span class="sxs-lookup"><span data-stu-id="c4f33-107">For example, you can use the tree to generate F# code or generate code in some other language.</span></span>

## <a name="quoted-expressions"></a><span data-ttu-id="c4f33-108">引用符で囲まれた式</span><span class="sxs-lookup"><span data-stu-id="c4f33-108">Quoted Expressions</span></span>

<span data-ttu-id="c4f33-109">*引用符で囲ま*れた式は、コード内の f # 式であり、プログラムの一部としてコンパイルされるのではなく、f # の式を表すオブジェクトにコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="c4f33-109">A *quoted expression* is an F# expression in your code that is delimited in such a way that it is not compiled as part of your program, but instead is compiled into an object that represents an F# expression.</span></span> <span data-ttu-id="c4f33-110">引用符で囲まれた式は、型情報を持つか、型情報のない2つの方法のいずれかでマークできます。</span><span class="sxs-lookup"><span data-stu-id="c4f33-110">You can mark a quoted expression in one of two ways: either with type information or without type information.</span></span> <span data-ttu-id="c4f33-111">型情報を含める場合は、記号とを使用して、引用符で囲まれた `<@` `@>` 式を区切ります。</span><span class="sxs-lookup"><span data-stu-id="c4f33-111">If you want to include type information, you use the symbols `<@` and `@>` to delimit the quoted expression.</span></span> <span data-ttu-id="c4f33-112">型情報が不要な場合は、との記号を使用し `<@@` `@@>` ます。</span><span class="sxs-lookup"><span data-stu-id="c4f33-112">If you do not need type information, you use the symbols `<@@` and `@@>`.</span></span> <span data-ttu-id="c4f33-113">次のコードは、型指定された型指定のない引用符を示しています。</span><span class="sxs-lookup"><span data-stu-id="c4f33-113">The following code shows typed and untyped quotations.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet501.fs)]

<span data-ttu-id="c4f33-114">型情報を含めないと、大きな式ツリーを走査する方が高速になります。</span><span class="sxs-lookup"><span data-stu-id="c4f33-114">Traversing a large expression tree is faster if you do not include type information.</span></span> <span data-ttu-id="c4f33-115">型指定された記号で囲まれた式の結果の型はです `Expr<'T>` 。ここで、型パラメーターには、F # コンパイラの型推論アルゴリズムによって決定される式の型があります。</span><span class="sxs-lookup"><span data-stu-id="c4f33-115">The resulting type of an expression quoted with the typed symbols is `Expr<'T>`, where the type parameter has the type of the expression as determined by the F# compiler's type inference algorithm.</span></span> <span data-ttu-id="c4f33-116">型情報を含まないコード引用符を使用する場合、引用符で囲まれた式の型は非ジェネリック型の [Expr](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-fsharpexpr.html)になります。</span><span class="sxs-lookup"><span data-stu-id="c4f33-116">When you use code quotations without type information, the type of the quoted expression is the non-generic type [Expr](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-fsharpexpr.html).</span></span> <span data-ttu-id="c4f33-117">型指定されたクラスで [Raw](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-fsharpexpr-1.html#Raw) プロパティを呼び出して、 `Expr` 型指定のないオブジェクトを取得でき `Expr` ます。</span><span class="sxs-lookup"><span data-stu-id="c4f33-117">You can call the [Raw](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-fsharpexpr-1.html#Raw) property on the typed `Expr` class to obtain the untyped `Expr` object.</span></span>

<span data-ttu-id="c4f33-118">クラスでは、 `Expr` 引用符で囲まれた式を使用せずに、プログラムによって F # 式オブジェクトを生成できるようにする静的メソッドがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="c4f33-118">There are a variety of static methods that allow you to generate F# expression objects programmatically in the `Expr` class without using quoted expressions.</span></span>

<span data-ttu-id="c4f33-119">コード引用符には完全な式を含める必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c4f33-119">Note that a code quotation must include a complete expression.</span></span> <span data-ttu-id="c4f33-120">たとえば、バインドの場合、バインドされた `let` 名前の定義とバインドを使用する追加の式の両方が必要です。</span><span class="sxs-lookup"><span data-stu-id="c4f33-120">For a `let` binding, for example, you need both the definition of the bound name and an additional expression that uses the binding.</span></span> <span data-ttu-id="c4f33-121">Verbose 構文では、これはキーワードに続く式です `in` 。</span><span class="sxs-lookup"><span data-stu-id="c4f33-121">In verbose syntax, this is an expression that follows the `in` keyword.</span></span> <span data-ttu-id="c4f33-122">モジュールの最上位レベルでは、これはモジュール内の次の式にすぎませんが、引用符で囲まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4f33-122">At the top-level in a module, this is just the next expression in the module, but in a quotation, it is explicitly required.</span></span>

<span data-ttu-id="c4f33-123">したがって、次の式は無効です。</span><span class="sxs-lookup"><span data-stu-id="c4f33-123">Therefore, the following expression is not valid.</span></span>

```fsharp
// Not valid:
// <@ let f x = x + 1 @>
```

<span data-ttu-id="c4f33-124">ただし、次の式は有効です。</span><span class="sxs-lookup"><span data-stu-id="c4f33-124">But the following expressions are valid.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet502.fs)]

<span data-ttu-id="c4f33-125">F # の引用符を評価するには、 [f # の引用符](https://github.com/fsprojects/FSharp.Quotations.Evaluator)を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4f33-125">To evaluate F# quotations, you must use the [F# Quotation Evaluator](https://github.com/fsprojects/FSharp.Quotations.Evaluator).</span></span> <span data-ttu-id="c4f33-126">F # expression オブジェクトの評価と実行のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="c4f33-126">It provides support for evaluating and executing F# expression objects.</span></span>

## <a name="expr-type"></a><span data-ttu-id="c4f33-127">Expr 型</span><span class="sxs-lookup"><span data-stu-id="c4f33-127">Expr Type</span></span>

<span data-ttu-id="c4f33-128">型のインスタンスは `Expr` F # の式を表します。</span><span class="sxs-lookup"><span data-stu-id="c4f33-128">An instance of the `Expr` type represents an F# expression.</span></span> <span data-ttu-id="c4f33-129">ジェネリック型と非ジェネリック型の両方 `Expr` が、F # ライブラリのドキュメントに記載されています。</span><span class="sxs-lookup"><span data-stu-id="c4f33-129">Both the generic and the non-generic `Expr` types are documented in the F# library documentation.</span></span> <span data-ttu-id="c4f33-130">詳細については、「 [Fsharp.core 名前空間](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations.html) と [引用クラス](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-fsharpexpr.html)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4f33-130">For more information, see [FSharp.Quotations Namespace](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations.html) and [Quotations.Expr Class](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-fsharpexpr.html).</span></span>

## <a name="splicing-operators"></a><span data-ttu-id="c4f33-131">スプライス演算子</span><span class="sxs-lookup"><span data-stu-id="c4f33-131">Splicing Operators</span></span>

<span data-ttu-id="c4f33-132">スプライスを使用すると、リテラルコードの引用符を、プログラムまたは別のコード引用符から作成した式と組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="c4f33-132">Splicing enables you to combine literal code quotations with expressions that you have created programmatically or from another code quotation.</span></span> <span data-ttu-id="c4f33-133">`%`演算子と演算子を使用すると、 `%%` F # 式オブジェクトをコード引用符に追加できます。</span><span class="sxs-lookup"><span data-stu-id="c4f33-133">The `%` and `%%` operators enable you to add an F# expression object into a code quotation.</span></span> <span data-ttu-id="c4f33-134">型指定さ `%` れた式オブジェクトを型指定された引用符に挿入するには、演算子を使用します。型指定されていない式オブジェクトを型指定された引用符に挿入するには、演算子を使用し `%%` ます。</span><span class="sxs-lookup"><span data-stu-id="c4f33-134">You use the `%` operator to insert a typed expression object into a typed quotation; you use the `%%` operator to insert an untyped expression object into an untyped quotation.</span></span> <span data-ttu-id="c4f33-135">どちらの演算子も、単項前置演算子です。</span><span class="sxs-lookup"><span data-stu-id="c4f33-135">Both operators are unary prefix operators.</span></span> <span data-ttu-id="c4f33-136">このため `expr` 、が型の型指定されていない式である場合 `Expr` 、次のコードは有効です。</span><span class="sxs-lookup"><span data-stu-id="c4f33-136">Thus if `expr` is an untyped expression of type `Expr`, the following code is valid.</span></span>

```fsharp
<@@ 1 + %%expr @@>
```

<span data-ttu-id="c4f33-137">また、 `expr` が型の型指定された引用符である場合 `Expr<int>` 、次のコードが有効です。</span><span class="sxs-lookup"><span data-stu-id="c4f33-137">And if `expr` is a typed quotation of type `Expr<int>`, the following code is valid.</span></span>

```fsharp
<@ 1 + %expr @>
```

## <a name="example"></a><span data-ttu-id="c4f33-138">例</span><span class="sxs-lookup"><span data-stu-id="c4f33-138">Example</span></span>

### <a name="description"></a><span data-ttu-id="c4f33-139">説明</span><span class="sxs-lookup"><span data-stu-id="c4f33-139">Description</span></span>

<span data-ttu-id="c4f33-140">次の例では、コード引用符を使用して F # コードを式オブジェクトに配置し、式を表す F # コードを出力する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c4f33-140">The following example illustrates the use of code quotations to put F# code into an expression object and then print the F# code that represents the expression.</span></span> <span data-ttu-id="c4f33-141">`println` `print` F # expression オブジェクト (型 `Expr` ) をわかりやすい形式で表示する再帰関数を含む関数が定義されています。</span><span class="sxs-lookup"><span data-stu-id="c4f33-141">A function `println` is defined that contains a recursive function `print` that displays an F# expression object (of type `Expr`) in a friendly format.</span></span> <span data-ttu-id="c4f33-142">[Fsharp.core](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-patternsmodule.html)および[fsharp.core](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-derivedpatternsmodule.html)モジュールには、式オブジェクトの分析に使用できるアクティブなパターンがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="c4f33-142">There are several active patterns in the [FSharp.Quotations.Patterns](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-patternsmodule.html) and [FSharp.Quotations.DerivedPatterns](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-derivedpatternsmodule.html) modules that can be used to analyze expression objects.</span></span> <span data-ttu-id="c4f33-143">この例には、F # 式に出現する可能性のあるすべてのパターンが含まれているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="c4f33-143">This example does not include all the possible patterns that might appear in an F# expression.</span></span> <span data-ttu-id="c4f33-144">認識されていないパターンは、ワイルドカードパターン () との一致をトリガーし、メソッドを使用して `_` 表示します。このメソッドを使用すると、 `ToString` `Expr` 一致式に追加するアクティブパターンを知ることができます。</span><span class="sxs-lookup"><span data-stu-id="c4f33-144">Any unrecognized pattern triggers a match to the wildcard pattern (`_`) and is rendered by using the `ToString` method, which, on the `Expr` type, lets you know the active pattern to add to your match expression.</span></span>

### <a name="code"></a><span data-ttu-id="c4f33-145">コード</span><span class="sxs-lookup"><span data-stu-id="c4f33-145">Code</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet601.fs)]

### <a name="output"></a><span data-ttu-id="c4f33-146">出力</span><span class="sxs-lookup"><span data-stu-id="c4f33-146">Output</span></span>

```fsharp
fun (x:System.Int32) -> x + 1
a + 1
let f = fun (x:System.Int32) -> x + 10 in f 10
```

## <a name="example"></a><span data-ttu-id="c4f33-147">例</span><span class="sxs-lookup"><span data-stu-id="c4f33-147">Example</span></span>

### <a name="description"></a><span data-ttu-id="c4f33-148">説明</span><span class="sxs-lookup"><span data-stu-id="c4f33-148">Description</span></span>

<span data-ttu-id="c4f33-149">また、 [Exprshape モジュール](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-exprshapemodule.html) 内の3つのアクティブパターンを使用して、アクティブなパターンが少数の式ツリーを走査することもできます。</span><span class="sxs-lookup"><span data-stu-id="c4f33-149">You can also use the three active patterns in the [ExprShape module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-exprshapemodule.html) to traverse expression trees with fewer active patterns.</span></span> <span data-ttu-id="c4f33-150">これらのアクティブなパターンは、ツリーを走査するときに、ほとんどのノードの情報をすべて必要としない場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="c4f33-150">These active patterns can be useful when you want to traverse a tree but you do not need all the information in most of the nodes.</span></span> <span data-ttu-id="c4f33-151">これらのパターンを使用すると、F # の式は、次の3つのパターンのいずれかと一致します。式が `ShapeVar` 変数である場合、 `ShapeLambda` 式がラムダ式である場合、または `ShapeCombination` 式が他のものである場合は。</span><span class="sxs-lookup"><span data-stu-id="c4f33-151">When you use these patterns, any F# expression matches one of the following three patterns: `ShapeVar` if the expression is a variable, `ShapeLambda` if the expression is a lambda expression, or `ShapeCombination` if the expression is anything else.</span></span> <span data-ttu-id="c4f33-152">前のコード例のようにアクティブなパターンを使用して式ツリーを走査する場合は、使用可能な F # 式の型をすべて処理するために、さらに多くのパターンを使用する必要があります。また、コードがより複雑になります。</span><span class="sxs-lookup"><span data-stu-id="c4f33-152">If you traverse an expression tree by using the active patterns as in the previous code example, you have to use many more patterns to handle all possible F# expression types, and your code will be more complex.</span></span> <span data-ttu-id="c4f33-153">詳細については、「 [Exprshape. の&#124;&#124;](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-exprshapemodule.html#(%20|ShapeVar|ShapeLambda|ShapeCombination|%20))、「スナップショット」を参照してください。また、このパターンを使用します。</span><span class="sxs-lookup"><span data-stu-id="c4f33-153">For more information, see [ExprShape.ShapeVar&#124;ShapeLambda&#124;ShapeCombination Active Pattern](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-exprshapemodule.html#(%20|ShapeVar|ShapeLambda|ShapeCombination|%20)).</span></span>

<span data-ttu-id="c4f33-154">次のコード例は、より複雑なトラバーサルの基礎として使用できます。</span><span class="sxs-lookup"><span data-stu-id="c4f33-154">The following code example can be used as a basis for more complex traversals.</span></span> <span data-ttu-id="c4f33-155">このコードでは、関数呼び出しを含む式に対して式ツリーが作成され `add` ます。</span><span class="sxs-lookup"><span data-stu-id="c4f33-155">In this code, an expression tree is created for an expression that involves a function call, `add`.</span></span> <span data-ttu-id="c4f33-156">特定の [呼び出し](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-derivedpatternsmodule.html#(%20|SpecificCall|_|%20)) のアクティブパターンは、 `add` 式ツリー内のへの呼び出しを検出するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c4f33-156">The [SpecificCall](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-derivedpatternsmodule.html#(%20|SpecificCall|_|%20)) active pattern is used to detect any call to `add` in the expression tree.</span></span> <span data-ttu-id="c4f33-157">このアクティブパターンは、呼び出しの引数を値に割り当て `exprList` ます。</span><span class="sxs-lookup"><span data-stu-id="c4f33-157">This active pattern assigns the arguments of the call to the `exprList` value.</span></span> <span data-ttu-id="c4f33-158">この場合は、2つしか存在しないため、これらの関数は引数に対して再帰的に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c4f33-158">In this case, there are only two, so these are pulled out and the function is called recursively on the arguments.</span></span> <span data-ttu-id="c4f33-159">結果は、 `mul` スプライス演算子 () を使用したへの呼び出しを表すコード引用符に挿入され `%%` ます。</span><span class="sxs-lookup"><span data-stu-id="c4f33-159">The results are inserted into a code quotation that represents a call to `mul` by using the splice operator (`%%`).</span></span> <span data-ttu-id="c4f33-160">`println`前の例の関数は、結果を表示するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c4f33-160">The `println` function from the previous example is used to display the results.</span></span>

<span data-ttu-id="c4f33-161">もう一方のアクティブパターン分岐のコードは同じ式ツリーを再生成するだけなので、結果として得られる式の変更はからに変更されるだけです `add` `mul` 。</span><span class="sxs-lookup"><span data-stu-id="c4f33-161">The code in the other active pattern branches just regenerates the same expression tree, so the only change in the resulting expression is the change from `add` to `mul`.</span></span>

### <a name="code"></a><span data-ttu-id="c4f33-162">コード</span><span class="sxs-lookup"><span data-stu-id="c4f33-162">Code</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet701.fs)]

### <a name="output"></a><span data-ttu-id="c4f33-163">出力</span><span class="sxs-lookup"><span data-stu-id="c4f33-163">Output</span></span>

```fsharp
1 + Module1.add(2,Module1.add(3,4))
1 + Module1.mul(2,Module1.mul(3,4))
```

## <a name="see-also"></a><span data-ttu-id="c4f33-164">関連項目</span><span class="sxs-lookup"><span data-stu-id="c4f33-164">See also</span></span>

- [<span data-ttu-id="c4f33-165">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="c4f33-165">F# Language Reference</span></span>](index.md)
