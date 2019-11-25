---
title: F# の関数型プログラミングの概要
description: でF#の関数型プログラミングの基本について説明します。
ms.date: 10/29/2018
ms.openlocfilehash: e1a0edc61dbe13012c48e166d490e22ebc70d6a0
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424712"
---
# <a name="introduction-to-functional-programming-in-f"></a><span data-ttu-id="8f629-103">F\# での関数型プログラミングの概要</span><span class="sxs-lookup"><span data-stu-id="8f629-103">Introduction to Functional Programming in F\#</span></span>

<span data-ttu-id="8f629-104">関数型プログラミングは、関数と不変データの使用を重視するプログラミングのスタイルです。</span><span class="sxs-lookup"><span data-stu-id="8f629-104">Functional programming is a style of programming that emphasizes the use of functions and immutable data.</span></span> <span data-ttu-id="8f629-105">型指定された関数型プログラミングは、関数型プログラミングが、などF#の静的な型と結合される場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="8f629-105">Typed functional programming is when functional programming is combined with static types, such as with F#.</span></span> <span data-ttu-id="8f629-106">一般に、関数型プログラミングでは次の概念が強調されています。</span><span class="sxs-lookup"><span data-stu-id="8f629-106">In general, the following concepts are emphasized in functional programming:</span></span>

* <span data-ttu-id="8f629-107">使用する主なコンストラクトとしての関数</span><span class="sxs-lookup"><span data-stu-id="8f629-107">Functions as the primary constructs you use</span></span>
* <span data-ttu-id="8f629-108">ステートメントではなく式</span><span class="sxs-lookup"><span data-stu-id="8f629-108">Expressions instead of statements</span></span>
* <span data-ttu-id="8f629-109">変数に対する不変値</span><span class="sxs-lookup"><span data-stu-id="8f629-109">Immutable values over variables</span></span>
* <span data-ttu-id="8f629-110">命令型プログラミングに対する宣言型プログラミング</span><span class="sxs-lookup"><span data-stu-id="8f629-110">Declarative programming over imperative programming</span></span>

<span data-ttu-id="8f629-111">このシリーズでは、を使用して関数型プログラミングの概念F#とパターンについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8f629-111">Throughout this series, you'll explore concepts and patterns in functional programming using F#.</span></span> <span data-ttu-id="8f629-112">その過程でも学習F#します。</span><span class="sxs-lookup"><span data-stu-id="8f629-112">Along the way, you'll learn some F# too.</span></span>

## <a name="terminology"></a><span data-ttu-id="8f629-113">用語</span><span class="sxs-lookup"><span data-stu-id="8f629-113">Terminology</span></span>

<span data-ttu-id="8f629-114">他のプログラミングパラダイムと同様に関数型プログラミングには、最終的に学習する必要があるボキャブラリが付属しています。</span><span class="sxs-lookup"><span data-stu-id="8f629-114">Functional programming, like other programming paradigms, comes with a vocabulary that you will eventually need to learn.</span></span> <span data-ttu-id="8f629-115">ここでは、すべての一般的な用語について説明します。</span><span class="sxs-lookup"><span data-stu-id="8f629-115">Here are some common terms you'll see all of the time:</span></span>

* <span data-ttu-id="8f629-116">**関数** - 関数とは指定した入力から出力を生成する構成要素です。</span><span class="sxs-lookup"><span data-stu-id="8f629-116">**Function** - A function is a construct that will produce an output when given an input.</span></span> <span data-ttu-id="8f629-117">正式には、ある集合を別の集合へ _マッピング_ するものです。この定式化は様々な方法に適用されます。</span><span class="sxs-lookup"><span data-stu-id="8f629-117">More formally, it _maps_ an item from one set to another set.</span></span> <span data-ttu-id="8f629-118">特にデータのコレクションを操作する関数を扱うような場合に有効です。</span><span class="sxs-lookup"><span data-stu-id="8f629-118">This formalism is lifted into the concrete in many ways, especially when using functions that operate on collections of data.</span></span> <span data-ttu-id="8f629-119">これは、関数型プログラミングで最も基本的な (かつ重要な) 概念です。</span><span class="sxs-lookup"><span data-stu-id="8f629-119">It is the most basic (and important) concept in functional programming.</span></span>
* <span data-ttu-id="8f629-120">**式** - 式は、値を生成するコード要素です。</span><span class="sxs-lookup"><span data-stu-id="8f629-120">**Expression** - An expression is a construct in code that produces a value.</span></span> <span data-ttu-id="8f629-121">F#では、この値はバインドされるかまたは明示的に無視されます。</span><span class="sxs-lookup"><span data-stu-id="8f629-121">In F#, this value must be bound or explicitly ignored.</span></span> <span data-ttu-id="8f629-122">式は、関数呼び出しで簡単に置き換える事ができます。</span><span class="sxs-lookup"><span data-stu-id="8f629-122">An expression can be trivially replaced by a function call.</span></span>
* <span data-ttu-id="8f629-123">**純粋性** - 純粋性とは同じ引数に対して戻り値は常に同じであり、その評価には副作用がないという関数の性質です。</span><span class="sxs-lookup"><span data-stu-id="8f629-123">**Purity** - Purity is a property of a function such that its return value is always the same for the same arguments, and that its evaluation has no side effects.</span></span> <span data-ttu-id="8f629-124">純粋関数はその引数に完全に依存します。</span><span class="sxs-lookup"><span data-stu-id="8f629-124">A pure function depends entirely on its arguments.</span></span>
* <span data-ttu-id="8f629-125">**参照透過性** - 参照透過性とはプログラムの動作に影響を与えずにその出力を交換できるような式の性質です。</span><span class="sxs-lookup"><span data-stu-id="8f629-125">**Referential Transparency** - Referential Transparency is a property of expressions such that they can be replaced with their output without affecting a program's behavior.</span></span>
* <span data-ttu-id="8f629-126">**不変性** - 不変性とは、値をその場で変更できないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="8f629-126">**Immutability** - Immutability means that a value cannot be changed in-place.</span></span> <span data-ttu-id="8f629-127">これは、その場で変化する可能性のある変数とは対照的です。</span><span class="sxs-lookup"><span data-stu-id="8f629-127">This is in contrast with variables, which can change in place.</span></span>

## <a name="examples"></a><span data-ttu-id="8f629-128">使用例</span><span class="sxs-lookup"><span data-stu-id="8f629-128">Examples</span></span>

<span data-ttu-id="8f629-129">次の例は、これらの主要な概念を示しています。</span><span class="sxs-lookup"><span data-stu-id="8f629-129">The following examples demonstrate these core concepts.</span></span>

### <a name="functions"></a><span data-ttu-id="8f629-130">関数</span><span class="sxs-lookup"><span data-stu-id="8f629-130">Functions</span></span>

<span data-ttu-id="8f629-131">関数型プログラミングの最も一般的で基本的な構成要素は、関数です。</span><span class="sxs-lookup"><span data-stu-id="8f629-131">The most common and fundamental construct in functional programming is the function.</span></span> <span data-ttu-id="8f629-132">次に示すのは、整数に1を加算する単純な関数です。</span><span class="sxs-lookup"><span data-stu-id="8f629-132">Here's a simple function that adds 1 to an integer:</span></span>

```fsharp
let addOne x = x + 1
```

<span data-ttu-id="8f629-133">その型シグネチャは次の通りです。</span><span class="sxs-lookup"><span data-stu-id="8f629-133">Its type signature is as follows:</span></span>

```fsharp
val addOne: x:int -> int
```

<span data-ttu-id="8f629-134">署名は、"`x` という名前の `int` を受け取り、`int`を生成する" として読み取ることができ`addOne` ます。</span><span class="sxs-lookup"><span data-stu-id="8f629-134">The signature can be read as, "`addOne` accepts an `int` named `x` and will produce an `int`".</span></span> <span data-ttu-id="8f629-135">より正式には、整数のセットの値を整数のセットに_マップ_する `addOne` ます。</span><span class="sxs-lookup"><span data-stu-id="8f629-135">More formally, `addOne` is _mapping_ a value from the set of integers to the set of integers.</span></span> <span data-ttu-id="8f629-136">`->` トークンはこのマッピングを意味します。</span><span class="sxs-lookup"><span data-stu-id="8f629-136">The `->` token signifies this mapping.</span></span> <span data-ttu-id="8f629-137">でF#は、通常、関数のシグネチャを調べて、その動作についての理解を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="8f629-137">In F#, you can usually look at the function signature to get a sense for what it does.</span></span>

<span data-ttu-id="8f629-138">では、なぜ署名が重要なのでしょうか。</span><span class="sxs-lookup"><span data-stu-id="8f629-138">So, why is the signature important?</span></span> <span data-ttu-id="8f629-139">型指定された関数型プログラミングでは、多くの場合、関数の実装は実際の型シグネチャよりも重要度が低くなります。</span><span class="sxs-lookup"><span data-stu-id="8f629-139">In typed functional programming, the implementation of a function is often less important than the actual type signature!</span></span> <span data-ttu-id="8f629-140">値1を整数に追加 `addOne` と、実行時には興味深いことになりますが、プログラムを構築するときには、この関数を実際に使用する方法を通知するために、`int` を受け入れることになります。</span><span class="sxs-lookup"><span data-stu-id="8f629-140">The fact that `addOne` adds the value 1 to an integer is interesting at runtime, but when you are constructing a program, the fact that it accepts and returns an `int` is what informs how you will actually use this function.</span></span> <span data-ttu-id="8f629-141">さらに、(型シグネチャに関して) この関数を正しく使用すると、問題の診断は `addOne` 関数の本体内でのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="8f629-141">Furthermore, once you use this function correctly (with respect to its type signature), diagnosing any problems can be done only within the body of the `addOne` function.</span></span> <span data-ttu-id="8f629-142">これは、型指定された関数型プログラミングの背後にある望むです。</span><span class="sxs-lookup"><span data-stu-id="8f629-142">This is the impetus behind typed functional programming.</span></span>

### <a name="expressions"></a><span data-ttu-id="8f629-143">式</span><span class="sxs-lookup"><span data-stu-id="8f629-143">Expressions</span></span>

<span data-ttu-id="8f629-144">式は、値に評価されるコンストラクトです。</span><span class="sxs-lookup"><span data-stu-id="8f629-144">Expressions are constructs that evaluate to a value.</span></span> <span data-ttu-id="8f629-145">アクションを実行するステートメントとは対照的に、式は値を返すアクションを実行すると考えることができます。</span><span class="sxs-lookup"><span data-stu-id="8f629-145">In contrast to statements, which perform an action, expressions can be thought of performing an action that gives back a value.</span></span> <span data-ttu-id="8f629-146">式は、関数型プログラミングのステートメントを優先するためにほとんど常に使用されます。</span><span class="sxs-lookup"><span data-stu-id="8f629-146">Expressions are almost always used in favor of statements in functional programming.</span></span>

<span data-ttu-id="8f629-147">前の関数 `addOne`を考えてみます。</span><span class="sxs-lookup"><span data-stu-id="8f629-147">Consider the previous function, `addOne`.</span></span> <span data-ttu-id="8f629-148">`addOne` の本体は式です。</span><span class="sxs-lookup"><span data-stu-id="8f629-148">The body of `addOne` is an expression:</span></span>

```fsharp
// 'x + 1' is an expression!
let addOne x = x + 1
```

<span data-ttu-id="8f629-149">これは、`addOne` 関数の結果の型を定義する、この式の結果です。</span><span class="sxs-lookup"><span data-stu-id="8f629-149">It is the result of this expression that defines the result type of the `addOne` function.</span></span> <span data-ttu-id="8f629-150">たとえば、この関数を構成する式を、`string`などの別の型に変更することができます。</span><span class="sxs-lookup"><span data-stu-id="8f629-150">For example, the expression that makes up this function could be changed to be a different type, such as a `string`:</span></span>

```fsharp
let addOne x = x.ToString() + "1"
```

<span data-ttu-id="8f629-151">関数のシグネチャは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8f629-151">The signature of the function is now:</span></span>

```fsharp
val addOne: x:'a -> string
```

<span data-ttu-id="8f629-152">のF#型には `ToString()` を呼び出すことができるため、`x` の型はジェネリック ([自動汎](../language-reference/generics/automatic-generalization.md)化と呼ばれます) になり、結果の型は `string`になります。</span><span class="sxs-lookup"><span data-stu-id="8f629-152">Since any type in F# can have `ToString()` called on it, the type of `x` has been made generic (called [Automatic Generalization](../language-reference/generics/automatic-generalization.md)), and the resultant type is a `string`.</span></span>

<span data-ttu-id="8f629-153">式は関数本体だけにあるものではありません。</span><span class="sxs-lookup"><span data-stu-id="8f629-153">Expressions are not just the bodies of functions.</span></span> <span data-ttu-id="8f629-154">他の場所で使用する値を生成する式を作成できます。</span><span class="sxs-lookup"><span data-stu-id="8f629-154">You can have expressions that produce a value you use elsewhere.</span></span> <span data-ttu-id="8f629-155">一般的なものは `if`次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8f629-155">A common one is `if`:</span></span>

```fsharp
// Checks if 'x' is odd by using the mod operator
let isOdd x = x % 2 <> 0

let addOneIfOdd input =
    let result =
        if isOdd input then
            input + 1
        else
            input

    result
```

<span data-ttu-id="8f629-156">`if` 式では `result`という値が生成されます。</span><span class="sxs-lookup"><span data-stu-id="8f629-156">The `if` expression produces a value called `result`.</span></span> <span data-ttu-id="8f629-157">`result` を完全に省略し、`if` 式を `addOneIfOdd` 関数の本体にすることができることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8f629-157">Note that you could omit `result` entirely, making the `if` expression the body of the `addOneIfOdd` function.</span></span> <span data-ttu-id="8f629-158">式について覚えておくべき重要な点は、値を生成することです。</span><span class="sxs-lookup"><span data-stu-id="8f629-158">The key thing to remember about expressions is that they produce a value.</span></span>

<span data-ttu-id="8f629-159">返されるものがない場合に使用される特殊な型 `unit`があります。</span><span class="sxs-lookup"><span data-stu-id="8f629-159">There is a special type, `unit`, that is used when there is nothing to return.</span></span> <span data-ttu-id="8f629-160">たとえば、次の単純な関数を考えてみます。</span><span class="sxs-lookup"><span data-stu-id="8f629-160">For example, consider this simple function:</span></span>

```fsharp
let printString (str: string) =
    printfn "String is: %s" str
```

<span data-ttu-id="8f629-161">署名は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8f629-161">The signature looks like this:</span></span>

```fsharp
val printString: str:string -> unit
```

<span data-ttu-id="8f629-162">`unit` 型は、返される実際の値がないことを示します。</span><span class="sxs-lookup"><span data-stu-id="8f629-162">The `unit` type indicates that there is no actual value being returned.</span></span> <span data-ttu-id="8f629-163">これは、その作業の結果として返す値がない場合でも、"処理を行う必要がある" ルーチンがある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="8f629-163">This is useful when you have a routine that must "do work" despite having no value to return as a result of that work.</span></span>

<span data-ttu-id="8f629-164">これは、命令型プログラミングとは対照的です。これは、同等の `if` コンストラクトがステートメントであり、多くの場合、変数の変化によって値を生成することです。</span><span class="sxs-lookup"><span data-stu-id="8f629-164">This is in sharp contrast to imperative programming, where the equivalent `if` construct is a statement, and producing values is often done with mutating variables.</span></span> <span data-ttu-id="8f629-165">たとえば、でC#は、次のようなコードが記述されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8f629-165">For example, in C#, the code might be written like this:</span></span>

```csharp
bool IsOdd(int x) => x % 2 != 0;

int AddOneIfOdd(int input)
{
    var result = input;

    if (IsOdd(input))
    {
        result = input + 1;
    }

    return result;
}
```

<span data-ttu-id="8f629-166">また、他の C C#スタイルの言語では、式ベースの条件付きプログラミングを可能にする[三項式](../../csharp/language-reference/operators/conditional-operator.md)がサポートされていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8f629-166">It's worth noting that C# and other C-style languages do support the [ternary expression](../../csharp/language-reference/operators/conditional-operator.md), which allows for expression-based conditional programming.</span></span>

<span data-ttu-id="8f629-167">関数型プログラミングでは、ステートメントを使用して値を変化させることはめったにありません。</span><span class="sxs-lookup"><span data-stu-id="8f629-167">In functional programming, it is rare to mutate values with statements.</span></span> <span data-ttu-id="8f629-168">一部の機能言語では、ステートメントと変異がサポートされていますが、関数型プログラミングでこれらの概念を使用するのは一般的ではありません。</span><span class="sxs-lookup"><span data-stu-id="8f629-168">Although some functional languages support statements and mutation, it is not common to use these concepts in functional programming.</span></span>

### <a name="pure-functions"></a><span data-ttu-id="8f629-169">純粋関数</span><span class="sxs-lookup"><span data-stu-id="8f629-169">Pure functions</span></span>

<span data-ttu-id="8f629-170">前述のように、純粋関数は次のような機能を備えています。</span><span class="sxs-lookup"><span data-stu-id="8f629-170">As previously mentioned, pure functions are functions that:</span></span>

* <span data-ttu-id="8f629-171">同じ入力に対して常に同じ値に評価されます。</span><span class="sxs-lookup"><span data-stu-id="8f629-171">Always evaluate to the same value for the same input.</span></span>
* <span data-ttu-id="8f629-172">副作用はありません。</span><span class="sxs-lookup"><span data-stu-id="8f629-172">Have no side effects.</span></span>

<span data-ttu-id="8f629-173">このコンテキストでは、数学関数を考えると便利です。</span><span class="sxs-lookup"><span data-stu-id="8f629-173">It is helpful to think of mathematical functions in this context.</span></span> <span data-ttu-id="8f629-174">数学では、関数は引数だけに依存しており、副作用はありません。</span><span class="sxs-lookup"><span data-stu-id="8f629-174">In mathematics, functions depend only on their arguments and do not have any side effects.</span></span> <span data-ttu-id="8f629-175">数学関数 `f(x) = x + 1`では、`f(x)` の値は `x`の値にのみ依存します。</span><span class="sxs-lookup"><span data-stu-id="8f629-175">In the mathematical function `f(x) = x + 1`, the value of `f(x)` depends only on the value of `x`.</span></span> <span data-ttu-id="8f629-176">関数型プログラミングの純粋関数は同じように機能します。</span><span class="sxs-lookup"><span data-stu-id="8f629-176">Pure functions in functional programming are the same way.</span></span>

<span data-ttu-id="8f629-177">純粋関数を記述する場合、関数はその引数にのみ依存し、副作用が発生するアクションを実行しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f629-177">When writing a pure function, the function must depend only on its arguments and not perform any action that results in a side effect.</span></span>

<span data-ttu-id="8f629-178">次に、非純粋関数の例を示します。これは、グローバルで変更可能な状態に依存しているためです。</span><span class="sxs-lookup"><span data-stu-id="8f629-178">Here is an example of a non-pure function because it depends on global, mutable state:</span></span>

```fsharp
let mutable value = 1

let addOneToValue x = x + value
```

<span data-ttu-id="8f629-179">`addOneToValue` 関数は明確に純粋でないます。 `value` は、いつでも1以外の値に変更できます。</span><span class="sxs-lookup"><span data-stu-id="8f629-179">The `addOneToValue` function is clearly impure, because `value` could be changed at any time to have a different value than 1.</span></span> <span data-ttu-id="8f629-180">グローバル値に応じたこのパターンは、関数型プログラミングでは回避することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8f629-180">This pattern of depending on a global value is to be avoided in functional programming.</span></span>

<span data-ttu-id="8f629-181">次に、非純粋関数のもう1つの例を示します。副作用が実行されるためです。</span><span class="sxs-lookup"><span data-stu-id="8f629-181">Here is another example of a non-pure function, because it performs a side effect:</span></span>

```fsharp
let addOneToValue x =
    printfn "x is %d" x
    x + 1
```

<span data-ttu-id="8f629-182">この関数はグローバル値に依存しませんが、`x` の値をプログラムの出力に書き込みます。</span><span class="sxs-lookup"><span data-stu-id="8f629-182">Although this function does not depend on a global value, it writes the value of `x` to the output of the program.</span></span> <span data-ttu-id="8f629-183">これを行うには本質的に問題はありませんが、関数が純粋でないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="8f629-183">Although there is nothing inherently wrong with doing this, it does mean that the function is not pure.</span></span> <span data-ttu-id="8f629-184">プログラムの別の部分が、出力バッファーなどのプログラムの外部に依存している場合、この関数を呼び出すと、プログラムの他の部分に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8f629-184">If another part of your program depends on something external to the program, such as the output buffer, then calling this function can affect that other part of your program.</span></span>

<span data-ttu-id="8f629-185">`printfn` ステートメントを削除すると、関数が純粋になります。</span><span class="sxs-lookup"><span data-stu-id="8f629-185">Removing the `printfn` statement makes the function pure:</span></span>

```fsharp
let addOneToValue x = x + 1
```

<span data-ttu-id="8f629-186">この関数は、`printfn` ステートメントを使用した以前のバージョンよりも本質的に_優れ_ているわけではありませんが、この関数がすべての値を返すことを保証します。</span><span class="sxs-lookup"><span data-stu-id="8f629-186">Although this function is not inherently _better_ than the previous version with the `printfn` statement, it does guarantee that all this function does is return a value.</span></span> <span data-ttu-id="8f629-187">この関数を何度も呼び出すと、同じ結果が生成されます。値が生成されるだけです。</span><span class="sxs-lookup"><span data-stu-id="8f629-187">Calling this function any number of times produces the same result: it just produces a value.</span></span> <span data-ttu-id="8f629-188">純度によって得られる予測可能性は、多くの機能プログラマが追求しています。</span><span class="sxs-lookup"><span data-stu-id="8f629-188">The predictability given by purity is something many functional programmers strive for.</span></span>

### <a name="immutability"></a><span data-ttu-id="8f629-189">不変性</span><span class="sxs-lookup"><span data-stu-id="8f629-189">Immutability</span></span>

<span data-ttu-id="8f629-190">最後に、型指定された関数型プログラミングの最も基本的な概念の1つは不変です。</span><span class="sxs-lookup"><span data-stu-id="8f629-190">Finally, one of the most fundamental concepts of typed functional programming is immutability.</span></span> <span data-ttu-id="8f629-191">でF#は、既定ですべての値が不変です。</span><span class="sxs-lookup"><span data-stu-id="8f629-191">In F#, all values are immutable by default.</span></span> <span data-ttu-id="8f629-192">つまり、明示的に変更可能としてマークしない限り、これらの変換をインプレースで行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="8f629-192">That means they cannot be mutated in-place unless you explicitly mark them as mutable.</span></span>

<span data-ttu-id="8f629-193">実際には、変更できない値を使用することは、"何かを変更する必要があります"、"新しい値を生成する必要があります" のようにプログラミングにアプローチを変更することを意味します。</span><span class="sxs-lookup"><span data-stu-id="8f629-193">In practice, working with immutable values means that you change your approach to programming from, "I need to change something", to "I need to produce a new value".</span></span>

<span data-ttu-id="8f629-194">たとえば、値に1を追加すると、新しい値が生成され、既存の値が変更されることはありません。</span><span class="sxs-lookup"><span data-stu-id="8f629-194">For example, adding 1 to a value means producing a new value, not mutating the existing one:</span></span>

```fsharp
let value = 1
let secondValue = value + 1
```

<span data-ttu-id="8f629-195">でF#は、次のコードは `value` 関数を変化**させません**。代わりに、等価性のチェックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="8f629-195">In F#, the following code does **not** mutate the `value` function; instead, it performs an equality check:</span></span>

```fsharp
let value = 1
value = value + 1 // Produces a 'bool' value!
```

<span data-ttu-id="8f629-196">一部の関数型プログラミング言語では、変化を一切サポートしていません。</span><span class="sxs-lookup"><span data-stu-id="8f629-196">Some functional programming languages do not support mutation at all.</span></span> <span data-ttu-id="8f629-197">でF#はサポートされていますが、値の既定の動作ではありません。</span><span class="sxs-lookup"><span data-stu-id="8f629-197">In F#, it is supported, but it is not the default behavior for values.</span></span>

<span data-ttu-id="8f629-198">この概念は、さらにデータ構造に拡張されます。</span><span class="sxs-lookup"><span data-stu-id="8f629-198">This concept extends even further to data structures.</span></span> <span data-ttu-id="8f629-199">関数型プログラミング言語では、集合 (およびその他のデータ) といった不変データ構造の実装は、最初の予想とは異なります。</span><span class="sxs-lookup"><span data-stu-id="8f629-199">In functional programming, immutable data structures such as sets (and many more) have a different implementation than you might initially expect.</span></span> <span data-ttu-id="8f629-200">たとえば、セットに項目を追加しても、セットを変更しないと、_新しい_セットが生成され、値が追加されます。</span><span class="sxs-lookup"><span data-stu-id="8f629-200">Conceptually, something like adding an item to a set does not change the set, it produces a _new_ set with the added value.</span></span> <span data-ttu-id="8f629-201">内部的には、これは多くの場合、データの適切な表現を結果として得られるように、値を効率的に追跡できるようにする別のデータ構造によって実現されます。</span><span class="sxs-lookup"><span data-stu-id="8f629-201">Under the covers, this is often accomplished by a different data structure that allows for efficiently tracking a value so that the appropriate representation of the data can be given as a result.</span></span>

<span data-ttu-id="8f629-202">値とデータ構造体を操作するこのスタイルは、新しいバージョンを作成する場合と同様に変更する操作を強制するため、非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="8f629-202">This style of working with values and data structures is critical, as it forces you to treat any operation that modifies something as if it creates a new version of that thing.</span></span> <span data-ttu-id="8f629-203">これにより、プログラムで等価性や比較可能性などを一貫して扱う事ができます。</span><span class="sxs-lookup"><span data-stu-id="8f629-203">This allows for things like equality and comparability to be consistent in your programs.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8f629-204">次のステップ</span><span class="sxs-lookup"><span data-stu-id="8f629-204">Next steps</span></span>

<span data-ttu-id="8f629-205">次のセクションでは、関数を徹底的に取り上げ、関数型プログラミングにおける様々な扱い方を探ります。</span><span class="sxs-lookup"><span data-stu-id="8f629-205">The next section will thoroughly cover functions, exploring different ways you can use them in functional programming.</span></span>

<span data-ttu-id="8f629-206">[ファーストクラス関数](first-class-functions.md)は関数を深く様々なコンテキストで使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8f629-206">[First-class functions](first-class-functions.md) explores functions deeply, showing how you can use them in various contexts.</span></span>

## <a name="further-reading"></a><span data-ttu-id="8f629-207">関連項目</span><span class="sxs-lookup"><span data-stu-id="8f629-207">Further reading</span></span>

<span data-ttu-id="8f629-208">[Thinking Functionally](https://fsharpforfunandprofit.com/posts/thinking-functionally-intro/) シリーズは、F# を使用した関数型プログラミングについて学ぶためのもう一つの優れたリソースです。</span><span class="sxs-lookup"><span data-stu-id="8f629-208">The [Thinking Functionally](https://fsharpforfunandprofit.com/posts/thinking-functionally-intro/) series is another great resource to learn about functional programming with F#.</span></span> <span data-ttu-id="8f629-209">機能を使用してF#概念を説明する、実用的で読みやすい方法での関数型プログラミングの基礎について説明します。</span><span class="sxs-lookup"><span data-stu-id="8f629-209">It covers fundamentals of functional programming in a pragmatic and easy-to-read way, using F# features to illustrate the concepts.</span></span>
