---
title: コード クォート
description: 言語機能を生成し、プログラムで F# コード式を処理することができますが、F# コード クォートについて説明します。
ms.date: 05/16/2016
ms.openlocfilehash: 30fd5b575fa59d78c3e70c1a94cd921a6a655ace
ms.sourcegitcommit: bab17fd81bab7886449217356084bf4881d6e7c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2019
ms.locfileid: "67402129"
---
# <a name="code-quotations"></a><span data-ttu-id="e5b64-103">コード クォート</span><span class="sxs-lookup"><span data-stu-id="e5b64-103">Code Quotations</span></span>

> [!NOTE]
> <span data-ttu-id="e5b64-104">API リファレンスのリンクをクリックすると MSDN に移動します。</span><span class="sxs-lookup"><span data-stu-id="e5b64-104">The API reference link will take you to MSDN.</span></span>  <span data-ttu-id="e5b64-105">docs.microsoft.com API リファレンスは完全ではありません。</span><span class="sxs-lookup"><span data-stu-id="e5b64-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="e5b64-106">このトピックで説明*コード クォート*、言語機能を生成し、プログラムで F# コード式を処理することができます。</span><span class="sxs-lookup"><span data-stu-id="e5b64-106">This topic describes *code quotations*, a language feature that enables you to generate and work with F# code expressions programmatically.</span></span> <span data-ttu-id="e5b64-107">この機能を使用して、F# コードを表す抽象構文ツリーを生成できます。</span><span class="sxs-lookup"><span data-stu-id="e5b64-107">This feature lets you generate an abstract syntax tree that represents F# code.</span></span> <span data-ttu-id="e5b64-108">抽象構文ツリーを走査し、アプリケーションのニーズに合わせて処理します。</span><span class="sxs-lookup"><span data-stu-id="e5b64-108">The abstract syntax tree can then be traversed and processed according to the needs of your application.</span></span> <span data-ttu-id="e5b64-109">たとえば、F# コードを生成または他の言語でコードを生成するツリーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e5b64-109">For example, you can use the tree to generate F# code or generate code in some other language.</span></span>

## <a name="quoted-expressions"></a><span data-ttu-id="e5b64-110">引用符で囲まれた式</span><span class="sxs-lookup"><span data-stu-id="e5b64-110">Quoted Expressions</span></span>

<span data-ttu-id="e5b64-111">A*式を引用符で囲まれた*F# 式では、プログラムの一部としてコンパイルされていない方法で区切られますが、代わりに、F# の式を表すオブジェクトにコンパイルするコードです。</span><span class="sxs-lookup"><span data-stu-id="e5b64-111">A *quoted expression* is an F# expression in your code that is delimited in such a way that it is not compiled as part of your program, but instead is compiled into an object that represents an F# expression.</span></span> <span data-ttu-id="e5b64-112">2 つの方法のいずれかで引用符で囲まれた式をマークすることができます。 型情報、または、型情報のいずれか。</span><span class="sxs-lookup"><span data-stu-id="e5b64-112">You can mark a quoted expression in one of two ways: either with type information or without type information.</span></span> <span data-ttu-id="e5b64-113">記号を使用する型情報を含める場合は、`<@`と`@>`を引用符で囲まれた式を区切るためにします。</span><span class="sxs-lookup"><span data-stu-id="e5b64-113">If you want to include type information, you use the symbols `<@` and `@>` to delimit the quoted expression.</span></span> <span data-ttu-id="e5b64-114">記号を使用する場合、型情報を使用する必要はありません、`<@@`と`@@>`します。</span><span class="sxs-lookup"><span data-stu-id="e5b64-114">If you do not need type information, you use the symbols `<@@` and `@@>`.</span></span> <span data-ttu-id="e5b64-115">次のコードでは、型指定された、型指定されていない見積を示します。</span><span class="sxs-lookup"><span data-stu-id="e5b64-115">The following code shows typed and untyped quotations.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet501.fs)]

<span data-ttu-id="e5b64-116">大規模な式ツリーの走査は、高速は、型情報が含まれていない場合です。</span><span class="sxs-lookup"><span data-stu-id="e5b64-116">Traversing a large expression tree is faster if you do not include type information.</span></span> <span data-ttu-id="e5b64-117">型指定されたシンボルを使用した引用符で囲まれた式の結果の型が`Expr<'T>`、型パラメーターが F# コンパイラの型推論アルゴリズムによって決定される式の型。</span><span class="sxs-lookup"><span data-stu-id="e5b64-117">The resulting type of an expression quoted with the typed symbols is `Expr<'T>`, where the type parameter has the type of the expression as determined by the F# compiler's type inference algorithm.</span></span> <span data-ttu-id="e5b64-118">引用符で囲まれた式の型は、非ジェネリック型で型情報がないコード クォートを使用して、 [Expr](https://msdn.microsoft.com/library/ed6a2caf-69d4-45c2-ab97-e9b3be9bce65)します。</span><span class="sxs-lookup"><span data-stu-id="e5b64-118">When you use code quotations without type information, the type of the quoted expression is the non-generic type [Expr](https://msdn.microsoft.com/library/ed6a2caf-69d4-45c2-ab97-e9b3be9bce65).</span></span> <span data-ttu-id="e5b64-119">呼び出すことができます、 [Raw](https://msdn.microsoft.com/library/47fb94f1-e77f-4c68-aabc-2b0ba40d59c2)プロパティを型指定された`Expr`クラスを取得、型指定されていない`Expr`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="e5b64-119">You can call the [Raw](https://msdn.microsoft.com/library/47fb94f1-e77f-4c68-aabc-2b0ba40d59c2) property on the typed `Expr` class to obtain the untyped `Expr` object.</span></span>

<span data-ttu-id="e5b64-120">さまざまな F# の式オブジェクトでプログラムを生成するための静的メソッドがある、`Expr`クラスを使用せずに引用式。</span><span class="sxs-lookup"><span data-stu-id="e5b64-120">There are a variety of static methods that allow you to generate F# expression objects programmatically in the `Expr` class without using quoted expressions.</span></span>

<span data-ttu-id="e5b64-121">コード クォートが完全な式を含める必要がありますに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e5b64-121">Note that a code quotation must include a complete expression.</span></span> <span data-ttu-id="e5b64-122">`let`バインド、たとえば、する必要があるバインドの名前と、バインディングを使用する追加の式の両方の定義。</span><span class="sxs-lookup"><span data-stu-id="e5b64-122">For a `let` binding, for example, you need both the definition of the bound name and an additional expression that uses the binding.</span></span> <span data-ttu-id="e5b64-123">これに続く式である詳細な構文で、`in`キーワード。</span><span class="sxs-lookup"><span data-stu-id="e5b64-123">In verbose syntax, this is an expression that follows the `in` keyword.</span></span> <span data-ttu-id="e5b64-124">トップレベル モジュール内では、これは、モジュールの次の式だけですが、引用符内では明示的に必要です。</span><span class="sxs-lookup"><span data-stu-id="e5b64-124">At the top-level in a module, this is just the next expression in the module, but in a quotation, it is explicitly required.</span></span>

<span data-ttu-id="e5b64-125">そのため、次の式が無効です。</span><span class="sxs-lookup"><span data-stu-id="e5b64-125">Therefore, the following expression is not valid.</span></span>

```fsharp
// Not valid:
// <@ let f x = x + 1 @>
```

<span data-ttu-id="e5b64-126">次の式は無効です。</span><span class="sxs-lookup"><span data-stu-id="e5b64-126">But the following expressions are valid.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet502.fs)]

<span data-ttu-id="e5b64-127">評価するF#引用符で囲んでが使用する必要があります、 [ F#引用符エバリュエーター](https://github.com/fsprojects/FSharp.Quotations.Evaluator)します。</span><span class="sxs-lookup"><span data-stu-id="e5b64-127">To evaluate F# quotations, you must use the [F# Quotation Evaluator](https://github.com/fsprojects/FSharp.Quotations.Evaluator).</span></span> <span data-ttu-id="e5b64-128">評価して、実行のサポートを提供F#式オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="e5b64-128">It provides support for evaluating and executing F# expression objects.</span></span>

## <a name="expr-type"></a><span data-ttu-id="e5b64-129">Expr 型</span><span class="sxs-lookup"><span data-stu-id="e5b64-129">Expr Type</span></span>

<span data-ttu-id="e5b64-130">インスタンス、`Expr`型が F# の式を表します。</span><span class="sxs-lookup"><span data-stu-id="e5b64-130">An instance of the `Expr` type represents an F# expression.</span></span> <span data-ttu-id="e5b64-131">ジェネリックと非ジェネリック`Expr`型が F# ライブラリのドキュメントに記載されています。</span><span class="sxs-lookup"><span data-stu-id="e5b64-131">Both the generic and the non-generic `Expr` types are documented in the F# library documentation.</span></span> <span data-ttu-id="e5b64-132">詳細については、次を参照してください。 [Microsoft.FSharp.Quotations Namespace](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.quotations-namespace-%5bfsharp%5d)と[Quotations.Expr クラス](https://msdn.microsoft.com/visualfsharpdocs/conceptual/quotations.expr-class-%5bfsharp%5d)します。</span><span class="sxs-lookup"><span data-stu-id="e5b64-132">For more information, see [Microsoft.FSharp.Quotations Namespace](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.quotations-namespace-%5bfsharp%5d) and [Quotations.Expr Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/quotations.expr-class-%5bfsharp%5d).</span></span>

## <a name="splicing-operators"></a><span data-ttu-id="e5b64-133">演算子のスプライス</span><span class="sxs-lookup"><span data-stu-id="e5b64-133">Splicing Operators</span></span>

<span data-ttu-id="e5b64-134">スプライスするには、プログラムから、または別のコード クォートから作成した式のリテラル コード クォートを結合することができます。</span><span class="sxs-lookup"><span data-stu-id="e5b64-134">Splicing enables you to combine literal code quotations with expressions that you have created programmatically or from another code quotation.</span></span> <span data-ttu-id="e5b64-135">`%`と`%%`演算子を使用すると、コード クォートに F# の式オブジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="e5b64-135">The `%` and `%%` operators enable you to add an F# expression object into a code quotation.</span></span> <span data-ttu-id="e5b64-136">使用する、`%`型指定された引用符に型指定された式のオブジェクトを挿入する演算子です。 使用する、`%%`演算子に型指定されていないの引用符に型指定されていない式オブジェクトを挿入します。</span><span class="sxs-lookup"><span data-stu-id="e5b64-136">You use the `%` operator to insert a typed expression object into a typed quotation; you use the `%%` operator to insert an untyped expression object into an untyped quotation.</span></span> <span data-ttu-id="e5b64-137">両方の演算子は、単項前置演算子です。</span><span class="sxs-lookup"><span data-stu-id="e5b64-137">Both operators are unary prefix operators.</span></span> <span data-ttu-id="e5b64-138">そのため場合`expr`型指定されていない型の式は、 `Expr`、次のコードは無効です。</span><span class="sxs-lookup"><span data-stu-id="e5b64-138">Thus if `expr` is an untyped expression of type `Expr`, the following code is valid.</span></span>

```fsharp
<@@ 1 + %%expr @@>
```

<span data-ttu-id="e5b64-139">場合`expr`型の型指定された引用符が`Expr<int>`、次のコードは無効です。</span><span class="sxs-lookup"><span data-stu-id="e5b64-139">And if `expr` is a typed quotation of type `Expr<int>`, the following code is valid.</span></span>

```fsharp
<@ 1 + %expr @>
```

## <a name="example"></a><span data-ttu-id="e5b64-140">例</span><span class="sxs-lookup"><span data-stu-id="e5b64-140">Example</span></span>

### <a name="description"></a><span data-ttu-id="e5b64-141">説明</span><span class="sxs-lookup"><span data-stu-id="e5b64-141">Description</span></span>

<span data-ttu-id="e5b64-142">次の例では、式オブジェクトに F# コードを配置し、式を表す F# コードを印刷するコード クォートの使用を示します。</span><span class="sxs-lookup"><span data-stu-id="e5b64-142">The following example illustrates the use of code quotations to put F# code into an expression object and then print the F# code that represents the expression.</span></span> <span data-ttu-id="e5b64-143">関数`println`が定義されている再帰関数を格納している`print`F# の式オブジェクトを表示する (型の`Expr`) を見やすい形式でします。</span><span class="sxs-lookup"><span data-stu-id="e5b64-143">A function `println` is defined that contains a recursive function `print` that displays an F# expression object (of type `Expr`) in a friendly format.</span></span> <span data-ttu-id="e5b64-144">いくつかのアクティブなパターンがない、 [Microsoft.FSharp.Quotations.Patterns](https://msdn.microsoft.com/library/093944a9-c752-403a-8983-5fcd5dbf92a4)と[Microsoft.FSharp.Quotations.DerivedPatterns](https://msdn.microsoft.com/library/d2434a6e-ae7b-4f3d-b567-c162938bc9cd)モジュール式オブジェクトを分析するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="e5b64-144">There are several active patterns in the [Microsoft.FSharp.Quotations.Patterns](https://msdn.microsoft.com/library/093944a9-c752-403a-8983-5fcd5dbf92a4) and [Microsoft.FSharp.Quotations.DerivedPatterns](https://msdn.microsoft.com/library/d2434a6e-ae7b-4f3d-b567-c162938bc9cd) modules that can be used to analyze expression objects.</span></span> <span data-ttu-id="e5b64-145">この例では、F# の式が表示されるすべてのパターンは含まれません。</span><span class="sxs-lookup"><span data-stu-id="e5b64-145">This example does not include all the possible patterns that might appear in an F# expression.</span></span> <span data-ttu-id="e5b64-146">ワイルドカード パターンに一致するものをトリガーするパターン認識されていないいずれか (`_`) を使用して表示されると、`ToString`メソッドであり、上、`Expr`型を match 式に追加するアクティブ パターンを確認できます。</span><span class="sxs-lookup"><span data-stu-id="e5b64-146">Any unrecognized pattern triggers a match to the wildcard pattern (`_`) and is rendered by using the `ToString` method, which, on the `Expr` type, lets you know the active pattern to add to your match expression.</span></span>

### <a name="code"></a><span data-ttu-id="e5b64-147">コード</span><span class="sxs-lookup"><span data-stu-id="e5b64-147">Code</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet601.fs)]

### <a name="output"></a><span data-ttu-id="e5b64-148">出力</span><span class="sxs-lookup"><span data-stu-id="e5b64-148">Output</span></span>

```fsharp
fun (x:System.Int32) -> x + 1
a + 1
let f = fun (x:System.Int32) -> x + 10 in f 10
```

## <a name="example"></a><span data-ttu-id="e5b64-149">例</span><span class="sxs-lookup"><span data-stu-id="e5b64-149">Example</span></span>

### <a name="description"></a><span data-ttu-id="e5b64-150">説明</span><span class="sxs-lookup"><span data-stu-id="e5b64-150">Description</span></span>

<span data-ttu-id="e5b64-151">次の 3 つのアクティブなパターンを使用することもできます、 [ExprShape モジュール](https://msdn.microsoft.com/library/7685150e-2432-4d39-9338-57292eff18de)少ないアクティブ パターン式ツリーを走査します。</span><span class="sxs-lookup"><span data-stu-id="e5b64-151">You can also use the three active patterns in the [ExprShape module](https://msdn.microsoft.com/library/7685150e-2432-4d39-9338-57292eff18de) to traverse expression trees with fewer active patterns.</span></span> <span data-ttu-id="e5b64-152">これらのアクティブ パターンは、ツリーを走査したいが、ほとんどのノード内のすべての情報が不要な場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e5b64-152">These active patterns can be useful when you want to traverse a tree but you do not need all the information in most of the nodes.</span></span> <span data-ttu-id="e5b64-153">これらのパターンを使用する場合は次の 3 つのパターンのいずれかの任意の F# の式と一致する:`ShapeVar`式が、変数の場合`ShapeLambda`場合は、式はラムダ式、または`ShapeCombination`式が何である場合。</span><span class="sxs-lookup"><span data-stu-id="e5b64-153">When you use these patterns, any F# expression matches one of the following three patterns: `ShapeVar` if the expression is a variable, `ShapeLambda` if the expression is a lambda expression, or `ShapeCombination` if the expression is anything else.</span></span> <span data-ttu-id="e5b64-154">前のコード例のようにアクティブ パターンを使用して式ツリーを走査する場合はすべて可能な F# 式の型を処理するために多くのより多くのパターンを使用する必要が、コードが複雑になります。</span><span class="sxs-lookup"><span data-stu-id="e5b64-154">If you traverse an expression tree by using the active patterns as in the previous code example, you have to use many more patterns to handle all possible F# expression types, and your code will be more complex.</span></span> <span data-ttu-id="e5b64-155">詳細については、次を参照してください。 [ExprShape.ShapeVar&#124;ShapeLambda&#124;ShapeCombination アクティブ パターン](https://msdn.microsoft.com/visualfsharpdocs/conceptual/exprshape.shapevarhshapelambdahshapecombination-active-pattern-%5bfsharp%5d)します。</span><span class="sxs-lookup"><span data-stu-id="e5b64-155">For more information, see [ExprShape.ShapeVar&#124;ShapeLambda&#124;ShapeCombination Active Pattern](https://msdn.microsoft.com/visualfsharpdocs/conceptual/exprshape.shapevarhshapelambdahshapecombination-active-pattern-%5bfsharp%5d).</span></span>

<span data-ttu-id="e5b64-156">次のコード例より複雑なトラバーサルの基礎として使用できます。</span><span class="sxs-lookup"><span data-stu-id="e5b64-156">The following code example can be used as a basis for more complex traversals.</span></span> <span data-ttu-id="e5b64-157">このコードで式ツリーは、関数呼び出しを含む式の作成`add`です。</span><span class="sxs-lookup"><span data-stu-id="e5b64-157">In this code, an expression tree is created for an expression that involves a function call, `add`.</span></span> <span data-ttu-id="e5b64-158">[SpecificCall](https://msdn.microsoft.com/library/05a77b21-20fe-4b9a-8e07-aa999538198d)アクティブ パターンを使用して、任意の呼び出しを検出`add`式ツリー。</span><span class="sxs-lookup"><span data-stu-id="e5b64-158">The [SpecificCall](https://msdn.microsoft.com/library/05a77b21-20fe-4b9a-8e07-aa999538198d) active pattern is used to detect any call to `add` in the expression tree.</span></span> <span data-ttu-id="e5b64-159">このアクティブ パターンへの呼び出しの引数の代入、`exprList`値。</span><span class="sxs-lookup"><span data-stu-id="e5b64-159">This active pattern assigns the arguments of the call to the `exprList` value.</span></span> <span data-ttu-id="e5b64-160">この場合が 2 つだけため、これらが引き出されていると、関数には、引数に再帰的には呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e5b64-160">In this case, there are only two, so these are pulled out and the function is called recursively on the arguments.</span></span> <span data-ttu-id="e5b64-161">呼び出しを表すコード クォートに結果が挿入されます`mul`スプライス演算子を使用して (`%%`)。</span><span class="sxs-lookup"><span data-stu-id="e5b64-161">The results are inserted into a code quotation that represents a call to `mul` by using the splice operator (`%%`).</span></span> <span data-ttu-id="e5b64-162">`println`前の例の関数を使用して、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="e5b64-162">The `println` function from the previous example is used to display the results.</span></span>

<span data-ttu-id="e5b64-163">結果の式でのみ変更がから変更にアクティブ パターンの他の分岐でコードが、同じ式ツリーにだけ再生成`add`に`mul`します。</span><span class="sxs-lookup"><span data-stu-id="e5b64-163">The code in the other active pattern branches just regenerates the same expression tree, so the only change in the resulting expression is the change from `add` to `mul`.</span></span>

### <a name="code"></a><span data-ttu-id="e5b64-164">コード</span><span class="sxs-lookup"><span data-stu-id="e5b64-164">Code</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet701.fs)]

### <a name="output"></a><span data-ttu-id="e5b64-165">Output</span><span class="sxs-lookup"><span data-stu-id="e5b64-165">Output</span></span>

```fsharp
1 + Module1.add(2,Module1.add(3,4))
1 + Module1.mul(2,Module1.mul(3,4))
```

## <a name="see-also"></a><span data-ttu-id="e5b64-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5b64-166">See also</span></span>

- [<span data-ttu-id="e5b64-167">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="e5b64-167">F# Language Reference</span></span>](index.md)
