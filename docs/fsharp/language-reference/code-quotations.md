---
title: コード クォート
description: 言語機能を生成し、プログラムで F# コード式を処理することができますが、F# コード クォートについて説明します。
ms.date: 05/16/2016
ms.openlocfilehash: c6ec0078c685a6452f49edd289b01491dd62e3db
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630418"
---
# <a name="code-quotations"></a><span data-ttu-id="6af06-103">コード クォート</span><span class="sxs-lookup"><span data-stu-id="6af06-103">Code Quotations</span></span>

> [!NOTE]
> <span data-ttu-id="6af06-104">API リファレンスのリンクをクリックすると MSDN に移動します。</span><span class="sxs-lookup"><span data-stu-id="6af06-104">The API reference link will take you to MSDN.</span></span>  <span data-ttu-id="6af06-105">docs.microsoft.com API リファレンスは完全ではありません。</span><span class="sxs-lookup"><span data-stu-id="6af06-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="6af06-106">このトピックで説明*コード クォート*、言語機能を生成し、プログラムで F# コード式を処理することができます。</span><span class="sxs-lookup"><span data-stu-id="6af06-106">This topic describes *code quotations*, a language feature that enables you to generate and work with F# code expressions programmatically.</span></span> <span data-ttu-id="6af06-107">この機能を使用して、F# コードを表す抽象構文ツリーを生成できます。</span><span class="sxs-lookup"><span data-stu-id="6af06-107">This feature lets you generate an abstract syntax tree that represents F# code.</span></span> <span data-ttu-id="6af06-108">次に、アプリケーションのニーズに応じて、抽象構文ツリーを走査して処理できます。</span><span class="sxs-lookup"><span data-stu-id="6af06-108">The abstract syntax tree can then be traversed and processed according to the needs of your application.</span></span> <span data-ttu-id="6af06-109">たとえば、F# コードを生成または他の言語でコードを生成するツリーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6af06-109">For example, you can use the tree to generate F# code or generate code in some other language.</span></span>

## <a name="quoted-expressions"></a><span data-ttu-id="6af06-110">引用符で囲まれた式</span><span class="sxs-lookup"><span data-stu-id="6af06-110">Quoted Expressions</span></span>

<span data-ttu-id="6af06-111">A*式を引用符で囲まれた*F# 式では、プログラムの一部としてコンパイルされていない方法で区切られますが、代わりに、F# の式を表すオブジェクトにコンパイルするコードです。</span><span class="sxs-lookup"><span data-stu-id="6af06-111">A *quoted expression* is an F# expression in your code that is delimited in such a way that it is not compiled as part of your program, but instead is compiled into an object that represents an F# expression.</span></span> <span data-ttu-id="6af06-112">引用符で囲まれた式は、型情報を持つか、型情報のない2つの方法のいずれかでマークできます。</span><span class="sxs-lookup"><span data-stu-id="6af06-112">You can mark a quoted expression in one of two ways: either with type information or without type information.</span></span> <span data-ttu-id="6af06-113">型情報を含める場合は、記号`<@`と`@>`を使用して、引用符で囲まれた式を区切ります。</span><span class="sxs-lookup"><span data-stu-id="6af06-113">If you want to include type information, you use the symbols `<@` and `@>` to delimit the quoted expression.</span></span> <span data-ttu-id="6af06-114">型情報が不要な場合は、と`<@@` `@@>`の記号を使用します。</span><span class="sxs-lookup"><span data-stu-id="6af06-114">If you do not need type information, you use the symbols `<@@` and `@@>`.</span></span> <span data-ttu-id="6af06-115">次のコードは、型指定された型指定のない引用符を示しています。</span><span class="sxs-lookup"><span data-stu-id="6af06-115">The following code shows typed and untyped quotations.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet501.fs)]

<span data-ttu-id="6af06-116">型情報を含めないと、大きな式ツリーを走査する方が高速になります。</span><span class="sxs-lookup"><span data-stu-id="6af06-116">Traversing a large expression tree is faster if you do not include type information.</span></span> <span data-ttu-id="6af06-117">型指定されたシンボルを使用した引用符で囲まれた式の結果の型が`Expr<'T>`、型パラメーターが F# コンパイラの型推論アルゴリズムによって決定される式の型。</span><span class="sxs-lookup"><span data-stu-id="6af06-117">The resulting type of an expression quoted with the typed symbols is `Expr<'T>`, where the type parameter has the type of the expression as determined by the F# compiler's type inference algorithm.</span></span> <span data-ttu-id="6af06-118">型情報を含まないコード引用符を使用する場合、引用符で囲まれた式の型は非ジェネリック型の[Expr](https://msdn.microsoft.com/library/ed6a2caf-69d4-45c2-ab97-e9b3be9bce65)になります。</span><span class="sxs-lookup"><span data-stu-id="6af06-118">When you use code quotations without type information, the type of the quoted expression is the non-generic type [Expr](https://msdn.microsoft.com/library/ed6a2caf-69d4-45c2-ab97-e9b3be9bce65).</span></span> <span data-ttu-id="6af06-119">型指定されたクラスで[Raw](https://msdn.microsoft.com/library/47fb94f1-e77f-4c68-aabc-2b0ba40d59c2)プロパティ`Expr`を呼び出して、型`Expr`指定のないオブジェクトを取得できます。</span><span class="sxs-lookup"><span data-stu-id="6af06-119">You can call the [Raw](https://msdn.microsoft.com/library/47fb94f1-e77f-4c68-aabc-2b0ba40d59c2) property on the typed `Expr` class to obtain the untyped `Expr` object.</span></span>

<span data-ttu-id="6af06-120">さまざまな F# の式オブジェクトでプログラムを生成するための静的メソッドがある、`Expr`クラスを使用せずに引用式。</span><span class="sxs-lookup"><span data-stu-id="6af06-120">There are a variety of static methods that allow you to generate F# expression objects programmatically in the `Expr` class without using quoted expressions.</span></span>

<span data-ttu-id="6af06-121">コード引用符には完全な式を含める必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6af06-121">Note that a code quotation must include a complete expression.</span></span> <span data-ttu-id="6af06-122">`let`たとえば、バインドの場合、バインドされた名前の定義とバインドを使用する追加の式の両方が必要です。</span><span class="sxs-lookup"><span data-stu-id="6af06-122">For a `let` binding, for example, you need both the definition of the bound name and an additional expression that uses the binding.</span></span> <span data-ttu-id="6af06-123">Verbose 構文では、これは`in`キーワードに続く式です。</span><span class="sxs-lookup"><span data-stu-id="6af06-123">In verbose syntax, this is an expression that follows the `in` keyword.</span></span> <span data-ttu-id="6af06-124">モジュールの最上位レベルでは、これはモジュール内の次の式にすぎませんが、引用符で囲まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6af06-124">At the top-level in a module, this is just the next expression in the module, but in a quotation, it is explicitly required.</span></span>

<span data-ttu-id="6af06-125">したがって、次の式は無効です。</span><span class="sxs-lookup"><span data-stu-id="6af06-125">Therefore, the following expression is not valid.</span></span>

```fsharp
// Not valid:
// <@ let f x = x + 1 @>
```

<span data-ttu-id="6af06-126">ただし、次の式は有効です。</span><span class="sxs-lookup"><span data-stu-id="6af06-126">But the following expressions are valid.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet502.fs)]

<span data-ttu-id="6af06-127">見積もりをF#評価するには、 [ F#見積もりエバリュエーター](https://github.com/fsprojects/FSharp.Quotations.Evaluator)を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6af06-127">To evaluate F# quotations, you must use the [F# Quotation Evaluator](https://github.com/fsprojects/FSharp.Quotations.Evaluator).</span></span> <span data-ttu-id="6af06-128">式オブジェクトの評価と実行F#のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="6af06-128">It provides support for evaluating and executing F# expression objects.</span></span>

## <a name="expr-type"></a><span data-ttu-id="6af06-129">Expr 型</span><span class="sxs-lookup"><span data-stu-id="6af06-129">Expr Type</span></span>

<span data-ttu-id="6af06-130">インスタンス、`Expr`型が F# の式を表します。</span><span class="sxs-lookup"><span data-stu-id="6af06-130">An instance of the `Expr` type represents an F# expression.</span></span> <span data-ttu-id="6af06-131">ジェネリックと非ジェネリック`Expr`型が F# ライブラリのドキュメントに記載されています。</span><span class="sxs-lookup"><span data-stu-id="6af06-131">Both the generic and the non-generic `Expr` types are documented in the F# library documentation.</span></span> <span data-ttu-id="6af06-132">詳細については、「 [Fsharp.core 名前空間](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.quotations-namespace-%5bfsharp%5d)と[引用クラス](https://msdn.microsoft.com/visualfsharpdocs/conceptual/quotations.expr-class-%5bfsharp%5d)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6af06-132">For more information, see [Microsoft.FSharp.Quotations Namespace](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.quotations-namespace-%5bfsharp%5d) and [Quotations.Expr Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/quotations.expr-class-%5bfsharp%5d).</span></span>

## <a name="splicing-operators"></a><span data-ttu-id="6af06-133">スプライス演算子</span><span class="sxs-lookup"><span data-stu-id="6af06-133">Splicing Operators</span></span>

<span data-ttu-id="6af06-134">スプライスを使用すると、リテラルコードの引用符を、プログラムまたは別のコード引用符から作成した式と組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="6af06-134">Splicing enables you to combine literal code quotations with expressions that you have created programmatically or from another code quotation.</span></span> <span data-ttu-id="6af06-135">`%`と`%%`演算子を使用すると、コード クォートに F# の式オブジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="6af06-135">The `%` and `%%` operators enable you to add an F# expression object into a code quotation.</span></span> <span data-ttu-id="6af06-136">型指定さ`%`れた式オブジェクトを型指定された引用符に挿入するに`%%`は、演算子を使用します。型指定されていない式オブジェクトを型指定された引用符に挿入するには、演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="6af06-136">You use the `%` operator to insert a typed expression object into a typed quotation; you use the `%%` operator to insert an untyped expression object into an untyped quotation.</span></span> <span data-ttu-id="6af06-137">どちらの演算子も、単項前置演算子です。</span><span class="sxs-lookup"><span data-stu-id="6af06-137">Both operators are unary prefix operators.</span></span> <span data-ttu-id="6af06-138">このため`expr` 、が型の型`Expr`指定されていない式である場合、次のコードは有効です。</span><span class="sxs-lookup"><span data-stu-id="6af06-138">Thus if `expr` is an untyped expression of type `Expr`, the following code is valid.</span></span>

```fsharp
<@@ 1 + %%expr @@>
```

<span data-ttu-id="6af06-139">また、 `expr`が型の型`Expr<int>`指定された引用符である場合、次のコードが有効です。</span><span class="sxs-lookup"><span data-stu-id="6af06-139">And if `expr` is a typed quotation of type `Expr<int>`, the following code is valid.</span></span>

```fsharp
<@ 1 + %expr @>
```

## <a name="example"></a><span data-ttu-id="6af06-140">例</span><span class="sxs-lookup"><span data-stu-id="6af06-140">Example</span></span>

### <a name="description"></a><span data-ttu-id="6af06-141">説明</span><span class="sxs-lookup"><span data-stu-id="6af06-141">Description</span></span>

<span data-ttu-id="6af06-142">次の例では、式オブジェクトに F# コードを配置し、式を表す F# コードを印刷するコード クォートの使用を示します。</span><span class="sxs-lookup"><span data-stu-id="6af06-142">The following example illustrates the use of code quotations to put F# code into an expression object and then print the F# code that represents the expression.</span></span> <span data-ttu-id="6af06-143">関数`println`が定義されている再帰関数を格納している`print`F# の式オブジェクトを表示する (型の`Expr`) を見やすい形式でします。</span><span class="sxs-lookup"><span data-stu-id="6af06-143">A function `println` is defined that contains a recursive function `print` that displays an F# expression object (of type `Expr`) in a friendly format.</span></span> <span data-ttu-id="6af06-144">[Fsharp.core](https://msdn.microsoft.com/library/093944a9-c752-403a-8983-5fcd5dbf92a4)および[fsharp.core](https://msdn.microsoft.com/library/d2434a6e-ae7b-4f3d-b567-c162938bc9cd)モジュールには、式オブジェクトの分析に使用できるアクティブなパターンがいくつかありますが、これらはいくつか存在します。</span><span class="sxs-lookup"><span data-stu-id="6af06-144">There are several active patterns in the [Microsoft.FSharp.Quotations.Patterns](https://msdn.microsoft.com/library/093944a9-c752-403a-8983-5fcd5dbf92a4) and [Microsoft.FSharp.Quotations.DerivedPatterns](https://msdn.microsoft.com/library/d2434a6e-ae7b-4f3d-b567-c162938bc9cd) modules that can be used to analyze expression objects.</span></span> <span data-ttu-id="6af06-145">この例では、F# の式が表示されるすべてのパターンは含まれません。</span><span class="sxs-lookup"><span data-stu-id="6af06-145">This example does not include all the possible patterns that might appear in an F# expression.</span></span> <span data-ttu-id="6af06-146">認識されていないパターンは、ワイルドカード`_`パターン () との一致を`ToString`トリガーし、メソッドを使用`Expr`して表示します。このメソッドを使用すると、一致式に追加するアクティブパターンを知ることができます。</span><span class="sxs-lookup"><span data-stu-id="6af06-146">Any unrecognized pattern triggers a match to the wildcard pattern (`_`) and is rendered by using the `ToString` method, which, on the `Expr` type, lets you know the active pattern to add to your match expression.</span></span>

### <a name="code"></a><span data-ttu-id="6af06-147">コード</span><span class="sxs-lookup"><span data-stu-id="6af06-147">Code</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet601.fs)]

### <a name="output"></a><span data-ttu-id="6af06-148">出力</span><span class="sxs-lookup"><span data-stu-id="6af06-148">Output</span></span>

```fsharp
fun (x:System.Int32) -> x + 1
a + 1
let f = fun (x:System.Int32) -> x + 10 in f 10
```

## <a name="example"></a><span data-ttu-id="6af06-149">例</span><span class="sxs-lookup"><span data-stu-id="6af06-149">Example</span></span>

### <a name="description"></a><span data-ttu-id="6af06-150">説明</span><span class="sxs-lookup"><span data-stu-id="6af06-150">Description</span></span>

<span data-ttu-id="6af06-151">また、 [Exprshape モジュール](https://msdn.microsoft.com/library/7685150e-2432-4d39-9338-57292eff18de)内の3つのアクティブパターンを使用して、アクティブなパターンが少数の式ツリーを走査することもできます。</span><span class="sxs-lookup"><span data-stu-id="6af06-151">You can also use the three active patterns in the [ExprShape module](https://msdn.microsoft.com/library/7685150e-2432-4d39-9338-57292eff18de) to traverse expression trees with fewer active patterns.</span></span> <span data-ttu-id="6af06-152">これらのアクティブなパターンは、ツリーを走査するときに、ほとんどのノードの情報をすべて必要としない場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="6af06-152">These active patterns can be useful when you want to traverse a tree but you do not need all the information in most of the nodes.</span></span> <span data-ttu-id="6af06-153">これらのパターンを使用する場合は次の 3 つのパターンのいずれかの任意の F# の式と一致する:`ShapeVar`式が、変数の場合`ShapeLambda`場合は、式はラムダ式、または`ShapeCombination`式が何である場合。</span><span class="sxs-lookup"><span data-stu-id="6af06-153">When you use these patterns, any F# expression matches one of the following three patterns: `ShapeVar` if the expression is a variable, `ShapeLambda` if the expression is a lambda expression, or `ShapeCombination` if the expression is anything else.</span></span> <span data-ttu-id="6af06-154">前のコード例のようにアクティブ パターンを使用して式ツリーを走査する場合はすべて可能な F# 式の型を処理するために多くのより多くのパターンを使用する必要が、コードが複雑になります。</span><span class="sxs-lookup"><span data-stu-id="6af06-154">If you traverse an expression tree by using the active patterns as in the previous code example, you have to use many more patterns to handle all possible F# expression types, and your code will be more complex.</span></span> <span data-ttu-id="6af06-155">詳細については、「 [Exprshape. スナップショット&#124;&#124;](https://msdn.microsoft.com/visualfsharpdocs/conceptual/exprshape.shapevarhshapelambdahshapecombination-active-pattern-%5bfsharp%5d)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6af06-155">For more information, see [ExprShape.ShapeVar&#124;ShapeLambda&#124;ShapeCombination Active Pattern](https://msdn.microsoft.com/visualfsharpdocs/conceptual/exprshape.shapevarhshapelambdahshapecombination-active-pattern-%5bfsharp%5d).</span></span>

<span data-ttu-id="6af06-156">次のコード例は、より複雑なトラバーサルの基礎として使用できます。</span><span class="sxs-lookup"><span data-stu-id="6af06-156">The following code example can be used as a basis for more complex traversals.</span></span> <span data-ttu-id="6af06-157">このコードでは、関数呼び出し`add`を含む式に対して式ツリーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="6af06-157">In this code, an expression tree is created for an expression that involves a function call, `add`.</span></span> <span data-ttu-id="6af06-158">特定の[呼び出し](https://msdn.microsoft.com/library/05a77b21-20fe-4b9a-8e07-aa999538198d)のアクティブパターンは、式ツリー内の`add`への呼び出しを検出するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="6af06-158">The [SpecificCall](https://msdn.microsoft.com/library/05a77b21-20fe-4b9a-8e07-aa999538198d) active pattern is used to detect any call to `add` in the expression tree.</span></span> <span data-ttu-id="6af06-159">このアクティブパターンは、呼び出しの引数を`exprList`値に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6af06-159">This active pattern assigns the arguments of the call to the `exprList` value.</span></span> <span data-ttu-id="6af06-160">この場合は、2つしか存在しないため、これらの関数は引数に対して再帰的に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="6af06-160">In this case, there are only two, so these are pulled out and the function is called recursively on the arguments.</span></span> <span data-ttu-id="6af06-161">結果は、スプライス演算子 ( `mul` `%%`) を使用したへの呼び出しを表すコード引用符に挿入されます。</span><span class="sxs-lookup"><span data-stu-id="6af06-161">The results are inserted into a code quotation that represents a call to `mul` by using the splice operator (`%%`).</span></span> <span data-ttu-id="6af06-162">前の例の関数は、結果を表示するために使用されます。`println`</span><span class="sxs-lookup"><span data-stu-id="6af06-162">The `println` function from the previous example is used to display the results.</span></span>

<span data-ttu-id="6af06-163">もう一方のアクティブパターン分岐のコードは同じ式ツリーを再生成するだけなので、結果として得ら`add`れる`mul`式の変更はからに変更されるだけです。</span><span class="sxs-lookup"><span data-stu-id="6af06-163">The code in the other active pattern branches just regenerates the same expression tree, so the only change in the resulting expression is the change from `add` to `mul`.</span></span>

### <a name="code"></a><span data-ttu-id="6af06-164">コード</span><span class="sxs-lookup"><span data-stu-id="6af06-164">Code</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet701.fs)]

### <a name="output"></a><span data-ttu-id="6af06-165">Output</span><span class="sxs-lookup"><span data-stu-id="6af06-165">Output</span></span>

```fsharp
1 + Module1.add(2,Module1.add(3,4))
1 + Module1.mul(2,Module1.mul(3,4))
```

## <a name="see-also"></a><span data-ttu-id="6af06-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="6af06-166">See also</span></span>

- [<span data-ttu-id="6af06-167">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="6af06-167">F# Language Reference</span></span>](index.md)
