---
title: F# コードのフォーマットに関するガイドライン
description: F# コードの書式設定に関するガイドラインを学習します。
ms.date: 11/04/2019
ms.openlocfilehash: b8be70dd29a04e71614308164e541b99a1724305
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739556"
---
# <a name="f-code-formatting-guidelines"></a><span data-ttu-id="e9d77-103">F# コードのフォーマットに関するガイドライン</span><span class="sxs-lookup"><span data-stu-id="e9d77-103">F# code formatting guidelines</span></span>

<span data-ttu-id="e9d77-104">この記事では、F# コードが次のコードになるようにコードを書式設定する方法のガイドラインを示します。</span><span class="sxs-lookup"><span data-stu-id="e9d77-104">This article offers guidelines for how to format your code so that your F# code is:</span></span>

* <span data-ttu-id="e9d77-105">より読みやすい</span><span class="sxs-lookup"><span data-stu-id="e9d77-105">More legible</span></span>
* <span data-ttu-id="e9d77-106">Visual Studio および他のエディターでツールを書式設定によって適用される規則に従って</span><span class="sxs-lookup"><span data-stu-id="e9d77-106">In accordance with conventions applied by formatting tools in Visual Studio and other editors</span></span>
* <span data-ttu-id="e9d77-107">オンラインの他のコードと同様</span><span class="sxs-lookup"><span data-stu-id="e9d77-107">Similar to other code online</span></span>

<span data-ttu-id="e9d77-108">これらのガイドラインは[、Anh-Dung Phan](https://github.com/dungpa)による[F# フォーマット規則の包括的なガイド](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md)に基づいています。</span><span class="sxs-lookup"><span data-stu-id="e9d77-108">These guidelines are based on [A comprehensive guide to F# Formatting Conventions](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) by [Anh-Dung Phan](https://github.com/dungpa).</span></span>

## <a name="general-rules-for-indentation"></a><span data-ttu-id="e9d77-109">インデントの一般的な規則</span><span class="sxs-lookup"><span data-stu-id="e9d77-109">General rules for indentation</span></span>

<span data-ttu-id="e9d77-110">F# では、既定で大きな空白を使用します。</span><span class="sxs-lookup"><span data-stu-id="e9d77-110">F# uses significant white space by default.</span></span> <span data-ttu-id="e9d77-111">以下のガイドラインは、この問題を両立させる方法についてのガイダンスを提供することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="e9d77-111">The following guidelines are intended to provide guidance as to how to juggle some challenges this can impose.</span></span>

### <a name="using-spaces"></a><span data-ttu-id="e9d77-112">スペースの使用</span><span class="sxs-lookup"><span data-stu-id="e9d77-112">Using spaces</span></span>

<span data-ttu-id="e9d77-113">インデントが必要な場合は、タブではなくスペースを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9d77-113">When indentation is required, you must use spaces, not tabs.</span></span> <span data-ttu-id="e9d77-114">少なくとも 1 つのスペースが必要です。</span><span class="sxs-lookup"><span data-stu-id="e9d77-114">At least one space is required.</span></span> <span data-ttu-id="e9d77-115">組織では、インデントに使用するスペースの数を指定するコーディング標準を作成できます。インデントが発生する各レベルで、2、3、または 4 つのインデントのスペースが一般的です。</span><span class="sxs-lookup"><span data-stu-id="e9d77-115">Your organization can create coding standards to specify the number of spaces to use for indentation; two, three, or four spaces of indentation at each level where indentation occurs is typical.</span></span>

<span data-ttu-id="e9d77-116">**インデントごとに 4 つのスペースを使用することをお勧めします。**</span><span class="sxs-lookup"><span data-stu-id="e9d77-116">**We recommend four spaces per indentation.**</span></span>

<span data-ttu-id="e9d77-117">しかし、プログラムのインデントは主観的な問題です。</span><span class="sxs-lookup"><span data-stu-id="e9d77-117">That said, indentation of programs is a subjective matter.</span></span> <span data-ttu-id="e9d77-118">バリエーションは問題ありませんが、最初に従うべきルールは*インデントの一貫性です*。</span><span class="sxs-lookup"><span data-stu-id="e9d77-118">Variations are OK, but the first rule you should follow is *consistency of indentation*.</span></span> <span data-ttu-id="e9d77-119">一般的に受け入れられているインデントスタイルを選択し、コードベース全体で体系的に使用します。</span><span class="sxs-lookup"><span data-stu-id="e9d77-119">Choose a generally accepted style of indentation and use it systematically throughout your codebase.</span></span>

## <a name="formatting-white-space"></a><span data-ttu-id="e9d77-120">空白の書式設定</span><span class="sxs-lookup"><span data-stu-id="e9d77-120">Formatting white space</span></span>

<span data-ttu-id="e9d77-121">F# は空白に依存します。</span><span class="sxs-lookup"><span data-stu-id="e9d77-121">F# is white space sensitive.</span></span> <span data-ttu-id="e9d77-122">空白からのセマンティクスのほとんどは適切なインデントで覆われていますが、考慮すべき点がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="e9d77-122">Although most semantics from white space are covered by proper indentation, there are some other things to consider.</span></span>

### <a name="formatting-operators-in-arithmetic-expressions"></a><span data-ttu-id="e9d77-123">算術式での演算子の書式設定</span><span class="sxs-lookup"><span data-stu-id="e9d77-123">Formatting operators in arithmetic expressions</span></span>

<span data-ttu-id="e9d77-124">常に二項算術式の周囲に空白を使用します。</span><span class="sxs-lookup"><span data-stu-id="e9d77-124">Always use white space around binary arithmetic expressions:</span></span>

```fsharp
let subtractThenAdd x = x - 1 + 3
```

<span data-ttu-id="e9d77-125">単項`-`演算子は、常に、否定する値の直後に置く必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9d77-125">Unary `-` operators should always be immediately followed by the value they are negating:</span></span>

```fsharp
// OK
let negate x = -x

// Bad
let negateBad x = - x
```

<span data-ttu-id="e9d77-126">演算子の後に空白文字を追加`-`すると、他のユーザーが混乱する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e9d77-126">Adding a white-space character after the `-` operator can lead to confusion for others.</span></span>

<span data-ttu-id="e9d77-127">要約すると、常に重要です。</span><span class="sxs-lookup"><span data-stu-id="e9d77-127">In summary, it's important to always:</span></span>

* <span data-ttu-id="e9d77-128">空白で二項演算子を囲む</span><span class="sxs-lookup"><span data-stu-id="e9d77-128">Surround binary operators with white space</span></span>
* <span data-ttu-id="e9d77-129">単項演算子の後に末尾の空白文字が表示されない</span><span class="sxs-lookup"><span data-stu-id="e9d77-129">Never have trailing white space after a unary operator</span></span>

<span data-ttu-id="e9d77-130">二項算術演算子のガイドラインは特に重要です。</span><span class="sxs-lookup"><span data-stu-id="e9d77-130">The binary arithmetic operator guideline is especially important.</span></span> <span data-ttu-id="e9d77-131">バイナリ`-`演算子を囲まなかった場合、特定の書式設定の選択肢と組み合わせると、それを単項`-`として解釈する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e9d77-131">Failing to surround a binary `-` operator, when combined with certain formatting choices, could lead to interpreting it as a unary `-`.</span></span>

### <a name="surround-a-custom-operator-definition-with-white-space"></a><span data-ttu-id="e9d77-132">カスタム演算子定義を空白で囲む</span><span class="sxs-lookup"><span data-stu-id="e9d77-132">Surround a custom operator definition with white space</span></span>

<span data-ttu-id="e9d77-133">オペレーター定義を囲むには、必ず空白を使用します。</span><span class="sxs-lookup"><span data-stu-id="e9d77-133">Always use white space to surround an operator definition:</span></span>

```fsharp
// OK
let ( !> ) x f = f x

// Bad
let (!>) x f = f x
```

<span data-ttu-id="e9d77-134">で始まり、複数の`*`文字を持つカスタム演算子の場合、定義の先頭に空白を追加して、コンパイラのあいまいさを避ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9d77-134">For any custom operator that starts with `*` and that has more than one character, you need to add a white space to the beginning of the definition to avoid a compiler ambiguity.</span></span> <span data-ttu-id="e9d77-135">このため、すべての演算子の定義を単一の空白文字で囲むだけですることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e9d77-135">Because of this, we recommend that you simply surround the definitions of all operators with a single white-space character.</span></span>

### <a name="surround-function-parameter-arrows-with-white-space"></a><span data-ttu-id="e9d77-136">空白を使用して関数パラメーターの矢印を囲む</span><span class="sxs-lookup"><span data-stu-id="e9d77-136">Surround function parameter arrows with white space</span></span>

<span data-ttu-id="e9d77-137">関数のシグネチャを定義する場合は、記号の周囲に空白`->`を使用します。</span><span class="sxs-lookup"><span data-stu-id="e9d77-137">When defining the signature of a function, use white space around the `->` symbol:</span></span>

```fsharp
// OK
type MyFun = int -> int -> string

// Bad
type MyFunBad = int->int->string
```

### <a name="surround-function-arguments-with-white-space"></a><span data-ttu-id="e9d77-138">関数の引数を空白で囲む</span><span class="sxs-lookup"><span data-stu-id="e9d77-138">Surround function arguments with white space</span></span>

<span data-ttu-id="e9d77-139">関数を定義する場合は、各引数の前後に空白を使用します。</span><span class="sxs-lookup"><span data-stu-id="e9d77-139">When defining a function, use white space around each argument.</span></span>

```fsharp
// OK
let myFun (a: decimal) b c = a + b + c

// Bad
let myFunBad (a:decimal)(b)c = a + b + c
```

### <a name="place-parameters-on-a-new-line-for-long-member-definitions"></a><span data-ttu-id="e9d77-140">長いメンバー定義の新しい行にパラメーターを配置する</span><span class="sxs-lookup"><span data-stu-id="e9d77-140">Place parameters on a new line for long member definitions</span></span>

<span data-ttu-id="e9d77-141">メンバー定義が非常に長い場合は、新しい行にパラメーターを配置し、1 つのスコープをインデントします。</span><span class="sxs-lookup"><span data-stu-id="e9d77-141">If you have a very long member definition, place the parameters on new lines and indent them one scope.</span></span>

```fsharp
type C() =
    member _.LongMethodWithLotsOfParameters(
        aVeryLongType: AVeryLongTypeThatYouNeedToUse
        aSecondVeryLongType: AVeryLongTypeThatYouNeedToUse
        aThirdVeryLongType: AVeryLongTypeThatYouNeedToUse) =
        // ... the body of the method follows
```

<span data-ttu-id="e9d77-142">これは、コンストラクターにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="e9d77-142">This also applies to constructors:</span></span>

```fsharp
type C(
    aVeryLongType: AVeryLongTypeThatYouNeedToUse
    aSecondVeryLongType: AVeryLongTypeThatYouNeedToUse
    aThirdVeryLongType: AVeryLongTypeThatYouNeedToUse) =
    // ... the body of the class follows
```

### <a name="type-annotations"></a><span data-ttu-id="e9d77-143">注釈を入力する</span><span class="sxs-lookup"><span data-stu-id="e9d77-143">Type annotations</span></span>

#### <a name="right-pad-function-argument-type-annotations"></a><span data-ttu-id="e9d77-144">右パッド関数引数タイプの注釈</span><span class="sxs-lookup"><span data-stu-id="e9d77-144">Right-pad function argument type annotations</span></span>

<span data-ttu-id="e9d77-145">型の注釈を使用して引数を定義する場合は、記号`:`の後に空白を使用します。</span><span class="sxs-lookup"><span data-stu-id="e9d77-145">When defining arguments with type annotations, use white space after the `:` symbol:</span></span>

```fsharp
// OK
let complexFunction (a: int) (b: int) c = a + b + c

// Bad
let complexFunctionBad (a :int) (b :int) (c:int) = a + b + c
```

#### <a name="surround-return-type-annotations-with-white-space"></a><span data-ttu-id="e9d77-146">空白で戻り値の型の注釈を囲む</span><span class="sxs-lookup"><span data-stu-id="e9d77-146">Surround return type annotations with white space</span></span>

<span data-ttu-id="e9d77-147">let バインド関数または値型の注釈 (関数の場合は戻り値の型) では、記号の前後`:`に空白を使用します。</span><span class="sxs-lookup"><span data-stu-id="e9d77-147">In a let-bound function or value type annotation (return type in the case of a function), use white space before and after the `:` symbol:</span></span>

```fsharp
// OK
let expensiveToCompute : int = 0 // Type annotation for let-bound value
let myFun (a: decimal) b c : decimal = a + b + c // Type annotation for the return type of a function
// Bad
let expensiveToComputeBad1:int = 1
let expensiveToComputeBad2 :int = 2
let myFunBad (a: decimal) b c:decimal = a + b + c
```

## <a name="formatting-blank-lines"></a><span data-ttu-id="e9d77-148">空白行の書式設定</span><span class="sxs-lookup"><span data-stu-id="e9d77-148">Formatting blank lines</span></span>

* <span data-ttu-id="e9d77-149">最上位の関数とクラス定義を 2 行の空白行で区切ります。</span><span class="sxs-lookup"><span data-stu-id="e9d77-149">Separate top-level function and class definitions with two blank lines.</span></span>
* <span data-ttu-id="e9d77-150">クラス内のメソッド定義は、1 行の空白行で区切られます。</span><span class="sxs-lookup"><span data-stu-id="e9d77-150">Method definitions inside a class are separated by a single blank line.</span></span>
* <span data-ttu-id="e9d77-151">関連する関数のグループを分けるために、余分な空白行を使用できます (控えめに)。</span><span class="sxs-lookup"><span data-stu-id="e9d77-151">Extra blank lines may be used (sparingly) to separate groups of related functions.</span></span> <span data-ttu-id="e9d77-152">一連の関連するワンライナー (ダミー実装など) の間では、空白行を省略できます。</span><span class="sxs-lookup"><span data-stu-id="e9d77-152">Blank lines may be omitted between a bunch of related one-liners (for example, a set of dummy implementations).</span></span>
* <span data-ttu-id="e9d77-153">関数では、控えめに、論理セクションを示すために空白行を使用します。</span><span class="sxs-lookup"><span data-stu-id="e9d77-153">Use blank lines in functions, sparingly, to indicate logical sections.</span></span>

## <a name="formatting-comments"></a><span data-ttu-id="e9d77-154">コメントの書式設定</span><span class="sxs-lookup"><span data-stu-id="e9d77-154">Formatting comments</span></span>

<span data-ttu-id="e9d77-155">一般的には、ML スタイルのブロック コメントよりも複数のダブルスラッシュコメントを好みます。</span><span class="sxs-lookup"><span data-stu-id="e9d77-155">Generally prefer multiple double-slash comments over ML-style block comments.</span></span>

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    ML-style comments are fine, but not a .NET-ism.
    They are useful when needing to modify multi-line comments, though.
*)
```

<span data-ttu-id="e9d77-156">インラインコメントは、最初の文字を大文字にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9d77-156">Inline comments should capitalize the first letter.</span></span>

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a><span data-ttu-id="e9d77-157">名前付け規則</span><span class="sxs-lookup"><span data-stu-id="e9d77-157">Naming conventions</span></span>

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a><span data-ttu-id="e9d77-158">クラスバインド、式バインド、パターンバインド値および関数に対して camelCase を使用する</span><span class="sxs-lookup"><span data-stu-id="e9d77-158">Use camelCase for class-bound, expression-bound, and pattern-bound values and functions</span></span>

<span data-ttu-id="e9d77-159">ローカル変数として、またはパターン一致と関数定義でバインドされているすべての名前に camelCase を使用することは、一般的で受け入れられている F# スタイルです。</span><span class="sxs-lookup"><span data-stu-id="e9d77-159">It is common and accepted F# style to use camelCase for all names bound as local variables or in pattern matches and function definitions.</span></span>

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

<span data-ttu-id="e9d77-160">クラス内のローカルバインド関数も camelCase を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9d77-160">Locally bound functions in classes should also use camelCase.</span></span>

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-module-bound-public-functions"></a><span data-ttu-id="e9d77-161">モジュールバインドされたパブリック関数に camelCase を使用する</span><span class="sxs-lookup"><span data-stu-id="e9d77-161">Use camelCase for module-bound public functions</span></span>

<span data-ttu-id="e9d77-162">モジュールバインド関数がパブリック API の一部である場合は、camelCase を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9d77-162">When a module-bound function is part of a public API, it should use camelCase:</span></span>

```fsharp
module MyAPI =
    let publicFunctionOne param1 param2 param2 = ...

    let publicFunctionTwo param1 param2 param3 = ...
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a><span data-ttu-id="e9d77-163">内部およびプライベートモジュールバインド値および関数に camelCase を使用する</span><span class="sxs-lookup"><span data-stu-id="e9d77-163">Use camelCase for internal and private module-bound values and functions</span></span>

<span data-ttu-id="e9d77-164">次のようなプライベート モジュールバインド値には、camelCase を使用します。</span><span class="sxs-lookup"><span data-stu-id="e9d77-164">Use camelCase for private module-bound values, including the following:</span></span>

* <span data-ttu-id="e9d77-165">スクリプト内のアドホック関数</span><span class="sxs-lookup"><span data-stu-id="e9d77-165">Ad hoc functions in scripts</span></span>

* <span data-ttu-id="e9d77-166">モジュールまたは型の内部実装を構成する値</span><span class="sxs-lookup"><span data-stu-id="e9d77-166">Values making up the internal implementation of a module or type</span></span>

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a><span data-ttu-id="e9d77-167">パラメーターにキャメルケースを使用する</span><span class="sxs-lookup"><span data-stu-id="e9d77-167">Use camelCase for parameters</span></span>

<span data-ttu-id="e9d77-168">すべてのパラメータは.NETの命名規則に従って camelCase を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9d77-168">All parameters should use camelCase in accordance with .NET naming conventions.</span></span>

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a><span data-ttu-id="e9d77-169">モジュールに PascalCase を使用する</span><span class="sxs-lookup"><span data-stu-id="e9d77-169">Use PascalCase for modules</span></span>

<span data-ttu-id="e9d77-170">すべてのモジュール (最上位、内部、プライベート、ネスト) は PascalCase を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9d77-170">All modules (top-level, internal, private, nested) should use PascalCase.</span></span>

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a><span data-ttu-id="e9d77-171">型宣言、メンバー、およびラベルに PascalCase を使用する</span><span class="sxs-lookup"><span data-stu-id="e9d77-171">Use PascalCase for type declarations, members, and labels</span></span>

<span data-ttu-id="e9d77-172">クラス、インターフェイス、構造体、列挙体、デリゲート、レコード、および判別共用体は、すべて PascalCase で名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9d77-172">Classes, interfaces, structs, enumerations, delegates, records, and discriminated unions should all be named with PascalCase.</span></span> <span data-ttu-id="e9d77-173">レコードおよび判別共用体の型およびラベル内のメンバーも、PascalCase を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9d77-173">Members within types and labels for records and discriminated unions should also use PascalCase.</span></span>

```fsharp
type IMyInterface =
    abstract Something: int

type MyClass() =
    member this.MyMethod(x, y) = x + y

type MyRecord = { IntVal: int; StringVal: string }

type SchoolPerson =
    | Professor
    | Student
    | Advisor
    | Administrator
```

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a><span data-ttu-id="e9d77-174">NET に固有の構造に PascalCase を使用する</span><span class="sxs-lookup"><span data-stu-id="e9d77-174">Use PascalCase for constructs intrinsic to .NET</span></span>

<span data-ttu-id="e9d77-175">名前空間、例外、イベント、およびプロジェクト名`.dll`も PascalCase を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9d77-175">Namespaces, exceptions, events, and project/`.dll` names should also use PascalCase.</span></span> <span data-ttu-id="e9d77-176">これにより、他の .NET 言語からの消費が消費者にとってより自然に感じられますが、.NET の名前付け規則と一致することもあります。</span><span class="sxs-lookup"><span data-stu-id="e9d77-176">Not only does this make consumption from other .NET languages feel more natural to consumers, it's also consistent with .NET naming conventions that you are likely to encounter.</span></span>

### <a name="avoid-underscores-in-names"></a><span data-ttu-id="e9d77-177">名前にアンダースコアを付けないようにする</span><span class="sxs-lookup"><span data-stu-id="e9d77-177">Avoid underscores in names</span></span>

<span data-ttu-id="e9d77-178">歴史的に、一部の F# ライブラリは名前にアンダースコアを使用していました。</span><span class="sxs-lookup"><span data-stu-id="e9d77-178">Historically, some F# libraries have used underscores in names.</span></span> <span data-ttu-id="e9d77-179">しかし、.NET の名前付け規則と競合しているため、これは広く受け入れられません。</span><span class="sxs-lookup"><span data-stu-id="e9d77-179">However, this is no longer widely accepted, partly because it clashes with .NET naming conventions.</span></span> <span data-ttu-id="e9d77-180">しかし、一部の F# プログラマは、歴史的な理由の一部でアンダースコアを使用しており、寛容さと尊敬が重要です。</span><span class="sxs-lookup"><span data-stu-id="e9d77-180">That said, some F# programmers use underscores heavily, partly for historical reasons, and tolerance and respect is important.</span></span> <span data-ttu-id="e9d77-181">しかし、スタイルは、それを使用するかどうかの選択肢を持っている他の人によってしばしば嫌われていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e9d77-181">However, be aware that the style is often disliked by others who have a choice about whether to use it.</span></span>

<span data-ttu-id="e9d77-182">1 つの例外には、アンダースコアが一般的なネイティブ コンポーネントとの相互運用が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e9d77-182">One exception includes interoperating with native components, where underscores are common.</span></span>

### <a name="use-standard-f-operators"></a><span data-ttu-id="e9d77-183">標準 F# 演算子を使用する</span><span class="sxs-lookup"><span data-stu-id="e9d77-183">Use standard F# operators</span></span>

<span data-ttu-id="e9d77-184">次の演算子は、F# 標準ライブラリで定義されており、同等の演算子を定義する代わりに使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9d77-184">The following operators are defined in the F# standard library and should be used instead of defining equivalents.</span></span> <span data-ttu-id="e9d77-185">コードを読みやすく慣用化する傾向にあるため、これらの演算子を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e9d77-185">Using these operators is recommended as it tends to make code more readable and idiomatic.</span></span> <span data-ttu-id="e9d77-186">OCaml やその他の関数型プログラミング言語のバックグラウンドを持つ開発者は、さまざまなイディオムに慣れているかもしれません。</span><span class="sxs-lookup"><span data-stu-id="e9d77-186">Developers with a background in OCaml or other functional programming language may be accustomed to different idioms.</span></span> <span data-ttu-id="e9d77-187">次の一覧は、推奨される F# 演算子をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="e9d77-187">The following list summarizes the recommended F# operators.</span></span>

```fsharp
x |> f // Forward pipeline
f >> g // Forward composition
x |> ignore // Discard away a value
x + y // Overloaded addition (including string concatenation)
x - y // Overloaded subtraction
x * y // Overloaded multiplication
x / y // Overloaded division
x % y // Overloaded modulus
x && y // Lazy/short-cut "and"
x || y // Lazy/short-cut "or"
x <<< y // Bitwise left shift
x >>> y // Bitwise right shift
x ||| y // Bitwise or, also for working with “flags” enumeration
x &&& y // Bitwise and, also for working with “flags” enumeration
x ^^^ y // Bitwise xor, also for working with “flags” enumeration
```

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a><span data-ttu-id="e9d77-188">ジェネリックのプレフィックス構文 (`Foo<T>`) を優先して後置構文`T Foo`( ) に使用する</span><span class="sxs-lookup"><span data-stu-id="e9d77-188">Use prefix syntax for generics (`Foo<T>`) in preference to postfix syntax (`T Foo`)</span></span>

<span data-ttu-id="e9d77-189">F# は、ジェネリック型の名前付けの後置 ML スタイル`int list`(たとえば) とプレフィックス .NET スタイル`list<int>`(たとえば) を継承します。</span><span class="sxs-lookup"><span data-stu-id="e9d77-189">F# inherits both the postfix ML style of naming generic types (for example, `int list`) as well as the prefix .NET style (for example, `list<int>`).</span></span> <span data-ttu-id="e9d77-190">次の 5 種類の特定の種類を除き、.NET スタイルを優先します。</span><span class="sxs-lookup"><span data-stu-id="e9d77-190">Prefer the .NET style, except for five specific types:</span></span>

1. <span data-ttu-id="e9d77-191">F# リストの場合は、後置形式`int list`ではなく`list<int>`、 を使用します。</span><span class="sxs-lookup"><span data-stu-id="e9d77-191">For F# Lists, use the postfix form: `int list` rather than `list<int>`.</span></span>
2. <span data-ttu-id="e9d77-192">F# オプションの場合は、後置形式`int option`ではなく`option<int>`、 を使用します。</span><span class="sxs-lookup"><span data-stu-id="e9d77-192">For F# Options, use the postfix form: `int option` rather than `option<int>`.</span></span>
3. <span data-ttu-id="e9d77-193">F# 値オプションの場合は、後置形式`int voption`ではなく`voption<int>`、 を使用します。</span><span class="sxs-lookup"><span data-stu-id="e9d77-193">For F# Value Options, use the postfix form: `int voption` rather than `voption<int>`.</span></span>
4. <span data-ttu-id="e9d77-194">F# 配列の場合は、 または`int[]``int array``array<int>`ではなく構文名を使用します。</span><span class="sxs-lookup"><span data-stu-id="e9d77-194">For F# arrays, use the syntactic name `int[]` rather than `int array` or `array<int>`.</span></span>
5. <span data-ttu-id="e9d77-195">[参照セル]`int ref`には、 `ref<int>` `Ref<int>`または ではなく を使用します。</span><span class="sxs-lookup"><span data-stu-id="e9d77-195">For Reference Cells, use `int ref` rather than `ref<int>` or `Ref<int>`.</span></span>

<span data-ttu-id="e9d77-196">その他のすべての型では、プレフィックス フォームを使用します。</span><span class="sxs-lookup"><span data-stu-id="e9d77-196">For all other types, use the prefix form.</span></span>

## <a name="formatting-tuples"></a><span data-ttu-id="e9d77-197">タプルの書式設定</span><span class="sxs-lookup"><span data-stu-id="e9d77-197">Formatting tuples</span></span>

<span data-ttu-id="e9d77-198">組のインスタンス化はかっこで囲み、その中の区切りコンマの後にはスペースを 1 つ`(1, 2)`入れる必要があります。 `(x, y, z)`</span><span class="sxs-lookup"><span data-stu-id="e9d77-198">A tuple instantiation should be parenthesized, and the delimiting commas within it should be followed by a single space, for example: `(1, 2)`, `(x, y, z)`.</span></span>

<span data-ttu-id="e9d77-199">タプルのパターンマッチングでは、括弧を省略することが一般的に認められています。</span><span class="sxs-lookup"><span data-stu-id="e9d77-199">It is commonly accepted to omit parentheses in pattern matching of tuples:</span></span>

```fsharp
let (x, y) = z // Destructuring
let x, y = z // OK

// OK
match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

<span data-ttu-id="e9d77-200">また、関数の戻り値がタプルである場合は、括弧を省略することも一般的に受け入れられます。</span><span class="sxs-lookup"><span data-stu-id="e9d77-200">It is also commonly accepted to omit parentheses if the tuple is the return value of a function:</span></span>

```fsharp
// OK
let update model msg =
    match msg with
    | 1 -> model + 1, []
    | _ -> model, [ msg ]
```

<span data-ttu-id="e9d77-201">要約すると、括弧で囲まれたタプルのインスタンス化を優先しますが、パターンマッチングや戻り値にタプルを使用する場合は、括弧を使用しないようにすると考えられます。</span><span class="sxs-lookup"><span data-stu-id="e9d77-201">In summary, prefer parenthesized tuple instantiations, but when using tuples for pattern matching or a return value, it is considered fine to avoid parentheses.</span></span>

## <a name="formatting-discriminated-union-declarations"></a><span data-ttu-id="e9d77-202">判別共用体宣言のフォーマット</span><span class="sxs-lookup"><span data-stu-id="e9d77-202">Formatting discriminated union declarations</span></span>

<span data-ttu-id="e9d77-203">4`|`つのスペースで型定義をインデントします。</span><span class="sxs-lookup"><span data-stu-id="e9d77-203">Indent `|` in type definition by four spaces:</span></span>

```fsharp
// OK
type Volume =
    | Liter of float
    | FluidOunce of float
    | ImperialPint of float

// Not OK
type Volume =
| Liter of float
| USPint of float
| ImperialPint of float
```

## <a name="formatting-discriminated-unions"></a><span data-ttu-id="e9d77-204">判別共用体の書式設定</span><span class="sxs-lookup"><span data-stu-id="e9d77-204">Formatting discriminated unions</span></span>

<span data-ttu-id="e9d77-205">複数行に分割されたインスタンス化された判別共用体は、含まれるデータにインデントを伴う新しいスコープを与える必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9d77-205">Instantiated Discriminated Unions that split across multiple lines should give contained data a new scope with indentation:</span></span>

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

<span data-ttu-id="e9d77-206">閉じ括弧は新しい行にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="e9d77-206">The closing parenthesis can also be on a new line:</span></span>

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-record-declarations"></a><span data-ttu-id="e9d77-207">レコード宣言の書式設定</span><span class="sxs-lookup"><span data-stu-id="e9d77-207">Formatting record declarations</span></span>

<span data-ttu-id="e9d77-208">型定義`{`で 4 つのスペースでインデントし、同じ行でフィールド リストを開始します。</span><span class="sxs-lookup"><span data-stu-id="e9d77-208">Indent `{` in type definition by four spaces and start the field list on the same line:</span></span>

```fsharp
// OK
type PostalAddress =
    { Address: string
      City: string
      Zip: string }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

// Not OK
type PostalAddress =
  { Address: string
    City: string
    Zip: string }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

// Unusual in F#
type PostalAddress =
    {
        Address: string
        City: string
        Zip: string
    }
```

<span data-ttu-id="e9d77-209">レコードにインターフェイス実装またはメンバーを宣言する場合は、開始トークンを新しい行に配置し、終了トークンを新しい行に配置することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e9d77-209">Placing the opening token on a new line and the closing token on a new line is preferable if you are declaring interface implementations or members on the record:</span></span>

```fsharp
// Declaring additional members on PostalAddress
type PostalAddress =
    {
        Address: string
        City: string
        Zip: string
    }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

type MyRecord =
    {
        SomeField: int
    }
    interface IMyInterface
```

## <a name="formatting-records"></a><span data-ttu-id="e9d77-210">レコードの書式設定</span><span class="sxs-lookup"><span data-stu-id="e9d77-210">Formatting records</span></span>

<span data-ttu-id="e9d77-211">短いレコードは 1 行で書くことができます。</span><span class="sxs-lookup"><span data-stu-id="e9d77-211">Short records can be written in one line:</span></span>

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

<span data-ttu-id="e9d77-212">長いレコードは、ラベルに新しい行を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9d77-212">Records that are longer should use new lines for labels:</span></span>

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

<span data-ttu-id="e9d77-213">開始トークンを新しい行に配置し、コンテンツを 1 つのスコープにタブ付けし、新しい行に閉じるトークンを配置することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e9d77-213">Placing the opening token on a new line, the contents tabbed over one scope, and the closing token on a new line is preferable if you are:</span></span>

* <span data-ttu-id="e9d77-214">インデントスコープが異なるコード内でレコードを移動する</span><span class="sxs-lookup"><span data-stu-id="e9d77-214">Moving records around in code with different indentation scopes</span></span>
* <span data-ttu-id="e9d77-215">関数にパイピング</span><span class="sxs-lookup"><span data-stu-id="e9d77-215">Piping them into a function</span></span>

```fsharp
let rainbow =
    {
        Boss1 = "Jeffrey"
        Boss2 = "Jeffrey"
        Boss3 = "Jeffrey"
        Boss4 = "Jeffrey"
        Boss5 = "Jeffrey"
        Boss6 = "Jeffrey"
        Boss7 = "Jeffrey"
        Boss8 = "Jeffrey"
        Lackeys = ["Zippy"; "George"; "Bungle"]
    }

type MyRecord =
    {
        SomeField: int
    }
    interface IMyInterface

let foo a =
    a
    |> Option.map (fun x ->
        {
            MyField = x
        })
```

<span data-ttu-id="e9d77-216">リスト要素と配列要素にも同じ規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="e9d77-216">The same rules apply for list and array elements.</span></span>

## <a name="formatting-copy-and-update-record-expressions"></a><span data-ttu-id="e9d77-217">コピーと更新のレコード式の書式設定</span><span class="sxs-lookup"><span data-stu-id="e9d77-217">Formatting copy-and-update record expressions</span></span>

<span data-ttu-id="e9d77-218">コピーと更新のレコード式はレコードであるため、同様のガイドラインが適用されます。</span><span class="sxs-lookup"><span data-stu-id="e9d77-218">A copy-and-update record expression is still a record, so similar guidelines apply.</span></span>

<span data-ttu-id="e9d77-219">短い式は、1 行に収めることができます。</span><span class="sxs-lookup"><span data-stu-id="e9d77-219">Short expressions can fit on one line:</span></span>

```fsharp
let point2 = { point with X = 1; Y = 2 }
```

<span data-ttu-id="e9d77-220">長い式では、新しい行を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9d77-220">Longer expressions should use new lines:</span></span>

```fsharp
let rainbow2 =
    { rainbow with
        Boss = "Jeffrey"
        Lackeys = ["Zippy"; "George"; "Bungle"] }
```

<span data-ttu-id="e9d77-221">また、レコード ガイダンスと同様に、かっこを個別に行に配置し、式で 1 つのスコープを右にインデントすることもできます。</span><span class="sxs-lookup"><span data-stu-id="e9d77-221">And as with the record guidance, you may want to dedicate separate lines for the braces and indent one scope to the right with the expression.</span></span> <span data-ttu-id="e9d77-222">かっこを使用せずにオプションで値をラップするなど、特殊なケースでは、次のように 1 行にかっこを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9d77-222">In some special cases, such as wrapping a value with an optional without parentheses, you may need to keep a brace on one line:</span></span>

```fsharp
type S = { F1: int; F2: string }
type State = { F:  S option }

let state = { F = Some { F1 = 1; F2 = "Hello" } }
let newState =
    {
        state with
            F = Some {
                    F1 = 0
                    F2 = ""
                }
    }
```

## <a name="formatting-lists-and-arrays"></a><span data-ttu-id="e9d77-223">リストと配列の書式設定</span><span class="sxs-lookup"><span data-stu-id="e9d77-223">Formatting lists and arrays</span></span>

<span data-ttu-id="e9d77-224">演算子`x :: l`の周囲にスペース`::`を入`::`れる (インフィックス演算子なので、スペースで囲まれた) を使用して書き込みます。</span><span class="sxs-lookup"><span data-stu-id="e9d77-224">Write `x :: l` with spaces around the `::` operator (`::` is an infix operator, hence surrounded by spaces).</span></span>

<span data-ttu-id="e9d77-225">単一行で宣言されたリストと配列は、開始ブラケットの後、右括弧の前にスペースを置く必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9d77-225">List and arrays declared on a single line should have a space after the opening bracket and before the closing bracket:</span></span>

```fsharp
let xs = [ 1; 2; 3 ]
let ys = [| 1; 2; 3; |]
```

<span data-ttu-id="e9d77-226">2 つの異なる中かっこのような演算子の間には、常に少なくとも 1 つのスペースを使用してください。</span><span class="sxs-lookup"><span data-stu-id="e9d77-226">Always use at least one space between two distinct brace-like operators.</span></span> <span data-ttu-id="e9d77-227">たとえば、 と の`[`間にはスペースを`{`残します。</span><span class="sxs-lookup"><span data-stu-id="e9d77-227">For example, leave a space between a `[` and a `{`.</span></span>

```fsharp
// OK
[ { IngredientName = "Green beans"; Quantity = 250 }
  { IngredientName = "Pine nuts"; Quantity = 250 }
  { IngredientName = "Feta cheese"; Quantity = 250 }
  { IngredientName = "Olive oil"; Quantity = 10 }
  { IngredientName = "Lemon"; Quantity = 1 } ]

// Not OK
[{ IngredientName = "Green beans"; Quantity = 250 }
 { IngredientName = "Pine nuts"; Quantity = 250 }
 { IngredientName = "Feta cheese"; Quantity = 250 }
 { IngredientName = "Olive oil"; Quantity = 10 }
 { IngredientName = "Lemon"; Quantity = 1 }]
```

<span data-ttu-id="e9d77-228">同じガイドラインが、タプルのリストまたは配列にも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="e9d77-228">The same guideline applies for lists or arrays of tuples.</span></span>

<span data-ttu-id="e9d77-229">複数の行に分割されたリストと配列は、レコードと同様の規則に従います。</span><span class="sxs-lookup"><span data-stu-id="e9d77-229">Lists and arrays that split across multiple lines follow a similar rule as records do:</span></span>

```fsharp
let pascalsTriangle =
    [|
        [| 1 |]
        [| 1; 1 |]
        [| 1; 2; 1 |]
        [| 1; 3; 3; 1 |]
        [| 1; 4; 6; 4; 1 |]
        [| 1; 5; 10; 10; 5; 1 |]
        [| 1; 6; 15; 20; 15; 6; 1 |]
        [| 1; 7; 21; 35; 35; 21; 7; 1 |]
        [| 1; 8; 28; 56; 70; 56; 28; 8; 1 |]
    |]
```

<span data-ttu-id="e9d77-230">レコードと同様に、最初と右の角かっこを独自の行に宣言すると、コードの移動や関数へのパイプ処理が簡単になります。</span><span class="sxs-lookup"><span data-stu-id="e9d77-230">And as with records, declaring the opening and closing brackets on their own line will make moving code around and piping into functions easier.</span></span>

<span data-ttu-id="e9d77-231">配列とリストをプログラムで生成する場合は`->`、`do ... yield`値が常に生成される場合よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="e9d77-231">When generating arrays and lists programmatically, prefer `->` over `do ... yield` when a value is always generated:</span></span>

```fsharp
// Preferred
let squares = [ for x in 1..10 -> x*x ]

// Not preferred
let squares' = [ for x in 1..10 do yield x*x ]
```

<span data-ttu-id="e9d77-232">古いバージョンの F# 言語では`yield`、条件付きでデータが生成される場合や、評価する連続した式が存在する場合に指定する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="e9d77-232">Older versions of the F# language required specifying `yield` in situations where data may be generated conditionally, or there may be consecutive expressions to be evaluated.</span></span> <span data-ttu-id="e9d77-233">古い F#`yield`言語バージョンでコンパイルする必要がある場合を除き、これらのキーワードを省略することをおすすめします。</span><span class="sxs-lookup"><span data-stu-id="e9d77-233">Prefer omitting these `yield` keywords unless you must compile with an older F# language version:</span></span>

```fsharp
// Preferred
let daysOfWeek includeWeekend =
    [
        "Monday"
        "Tuesday"
        "Wednesday"
        "Thursday"
        "Friday"
        if includeWeekend then
            "Saturday"
            "Sunday"
    ]

// Not preferred
let daysOfWeek' includeWeekend =
    [
        yield "Monday"
        yield "Tuesday"
        yield "Wednesday"
        yield "Thursday"
        yield "Friday"
        if includeWeekend then
            yield "Saturday"
            yield "Sunday"
    ]
```

<span data-ttu-id="e9d77-234">場合によっては、`do...yield`読みやすさを助けるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="e9d77-234">In some cases, `do...yield` may aid in readability.</span></span> <span data-ttu-id="e9d77-235">主観的ではあるが、これらのケースは考慮すべきである。</span><span class="sxs-lookup"><span data-stu-id="e9d77-235">These cases, though subjective, should be taken into consideration.</span></span>

## <a name="formatting-if-expressions"></a><span data-ttu-id="e9d77-236">式の場合の書式設定</span><span class="sxs-lookup"><span data-stu-id="e9d77-236">Formatting if expressions</span></span>

<span data-ttu-id="e9d77-237">条件のインデントは、条件を構成する式のサイズによって異なります。</span><span class="sxs-lookup"><span data-stu-id="e9d77-237">Indentation of conditionals depends on the sizes of the expressions that make them up.</span></span> <span data-ttu-id="e9d77-238">が`cond``e1`短い`e2`場合は、1 行に書くだけです。</span><span class="sxs-lookup"><span data-stu-id="e9d77-238">If `cond`, `e1` and `e2` are short, simply write them on one line:</span></span>

```fsharp
if cond then e1 else e2
```

<span data-ttu-id="e9d77-239">または`cond``e2`より`e1`長いが複数行でない場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e9d77-239">If either `cond`, `e1` or `e2` are longer, but not multi-line:</span></span>

```fsharp
if cond
then e1
else e2
```

<span data-ttu-id="e9d77-240">式のいずれかが複数行の場合:</span><span class="sxs-lookup"><span data-stu-id="e9d77-240">If any of the expressions are multi-line:</span></span>

```fsharp
if cond then
    e1
else
    e2
```

<span data-ttu-id="e9d77-241">を使用して`elif`複数の`else`条件を設定し、同じスコープでインデント`if`します。</span><span class="sxs-lookup"><span data-stu-id="e9d77-241">Multiple conditionals with `elif` and `else` are indented at the same scope as the `if`:</span></span>

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a><span data-ttu-id="e9d77-242">パターンマッチングコンストラクト</span><span class="sxs-lookup"><span data-stu-id="e9d77-242">Pattern matching constructs</span></span>

<span data-ttu-id="e9d77-243">インデントを`|`指定しない一致の各句に a を使用します。</span><span class="sxs-lookup"><span data-stu-id="e9d77-243">Use a `|` for each clause of a match with no indentation.</span></span> <span data-ttu-id="e9d77-244">式が短い場合は、各部分式も単純である場合は、1 行を使用することを検討できます。</span><span class="sxs-lookup"><span data-stu-id="e9d77-244">If the expression is short, you can consider using a single line if each subexpression is also simple.</span></span>

```fsharp
// OK
match l with
| { him = x; her = "Posh" } :: tail -> x
| _ :: tail -> findDavid tail
| [] -> failwith "Couldn't find David"

// Not OK
match l with
    | { him = x; her = "Posh" } :: tail -> x
    | _ :: tail -> findDavid tail
    | [] -> failwith "Couldn't find David"
```

<span data-ttu-id="e9d77-245">パターンマッチング矢印の右側の式が大きすぎる場合は、次の行に移動し、1 ステップインデントします`match`/`|`。</span><span class="sxs-lookup"><span data-stu-id="e9d77-245">If the expression on the right of the pattern matching arrow is too large, move it to the following line, indented one step from the `match`/`|`.</span></span>

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

<span data-ttu-id="e9d77-246">で始まる`function`匿名関数のパターンマッチングは、通常、インデントしすぎないようにします。</span><span class="sxs-lookup"><span data-stu-id="e9d77-246">Pattern matching of anonymous functions, starting by `function`, should generally not indent too far.</span></span> <span data-ttu-id="e9d77-247">たとえば、次のように 1 つのスコープをインデントすると問題ありません。</span><span class="sxs-lookup"><span data-stu-id="e9d77-247">For example, indenting one scope as follows is fine:</span></span>

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

<span data-ttu-id="e9d77-248">で定義`let`された関数のパターンマッチング`let rec`は、 キーワードが使用されている場合`let``function`でも、 の開始後に 4 つのスペースをインデントする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9d77-248">Pattern matching in functions defined by `let` or `let rec` should be indented four spaces after starting of `let`, even if `function` keyword is used:</span></span>

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

<span data-ttu-id="e9d77-249">矢印の位置合わせはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="e9d77-249">We do not recommend aligning arrows.</span></span>

## <a name="formatting-trywith-expressions"></a><span data-ttu-id="e9d77-250">数式を使用して書式設定する</span><span class="sxs-lookup"><span data-stu-id="e9d77-250">Formatting try/with expressions</span></span>

<span data-ttu-id="e9d77-251">例外の種類でのパターンマッチングは、 と`with`同じレベルでインデントする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9d77-251">Pattern matching on the exception type should be indented at the same level as `with`.</span></span>

```fsharp
try
    if System.DateTime.Now.Second % 3 = 0 then
        raise (new System.Exception())
    else
        raise (new System.ApplicationException())
with
| :? System.ApplicationException ->
    printfn "A second that was not a multiple of 3"
| _ ->
    printfn "A second that was a multiple of 3"
```

## <a name="formatting-function-parameter-application"></a><span data-ttu-id="e9d77-252">書式設定機能パラメータアプリケーション</span><span class="sxs-lookup"><span data-stu-id="e9d77-252">Formatting function parameter application</span></span>

<span data-ttu-id="e9d77-253">一般に、ほとんどの関数パラメーター・アプリケーションは同じ行で行われます。</span><span class="sxs-lookup"><span data-stu-id="e9d77-253">In general, most function parameter application is done on the same line.</span></span>

<span data-ttu-id="e9d77-254">新しい行の関数にパラメータを適用する場合は、1 つのスコープでインデントします。</span><span class="sxs-lookup"><span data-stu-id="e9d77-254">If you wish to apply parameters to a function on a new line, indent them by one scope.</span></span>

```fsharp
// OK
sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity

// OK
sprintf
     "\t%s - %i\n\r"
     x.IngredientName x.Quantity

// OK
let printVolumes x =
    printf "Volume in liters = %f, in us pints = %f, in imperial = %f"
        (convertVolumeToLiter x)
        (convertVolumeUSPint x)
        (convertVolumeImperialPint x)
```

<span data-ttu-id="e9d77-255">ラムダ式には、関数の引数と同じガイドラインが適用されます。</span><span class="sxs-lookup"><span data-stu-id="e9d77-255">The same guidelines apply for lambda expressions as function arguments.</span></span> <span data-ttu-id="e9d77-256">ラムダ式の本体の場合、本体は、1 つのスコープでインデントされた別の行を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="e9d77-256">If the body of a lambda expression, the body can have another line, indented by one scope</span></span>

```fsharp
let printListWithOffset a list1 =
    List.iter
        (fun elem -> printfn "%d" (a + elem))
        list1

// OK if lambda body is long enough
let printListWithOffset a list1 =
    List.iter
        (fun elem ->
            printfn "%d" (a + elem))
        list1
```

<span data-ttu-id="e9d77-257">ただし、ラムダ式の本体が複数の行である場合は、複数行のコンストラクトを関数に単一の引数として適用するのではなく、別の関数に組み込みます。</span><span class="sxs-lookup"><span data-stu-id="e9d77-257">However, if the body of a lambda expression is more than one line, consider factoring it out into a separate function rather than have a multi-line construct applied as a single argument to a function.</span></span>

### <a name="formatting-infix-operators"></a><span data-ttu-id="e9d77-258">インフィックス演算子の書式設定</span><span class="sxs-lookup"><span data-stu-id="e9d77-258">Formatting infix operators</span></span>

<span data-ttu-id="e9d77-259">演算子はスペースで区切ります。</span><span class="sxs-lookup"><span data-stu-id="e9d77-259">Separate operators by spaces.</span></span> <span data-ttu-id="e9d77-260">この規則の明白な例外は`!`、`.`演算子と演算子です。</span><span class="sxs-lookup"><span data-stu-id="e9d77-260">Obvious exceptions to this rule are the `!` and `.` operators.</span></span>

<span data-ttu-id="e9d77-261">インフィックス式は、同じ列にラインナップしても問題があります。</span><span class="sxs-lookup"><span data-stu-id="e9d77-261">Infix expressions are OK to lineup on same column:</span></span>

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a><span data-ttu-id="e9d77-262">パイプライン演算子の書式設定</span><span class="sxs-lookup"><span data-stu-id="e9d77-262">Formatting pipeline operators</span></span>

<span data-ttu-id="e9d77-263">パイプライン`|>`演算子は、操作する式の下に移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9d77-263">Pipeline `|>` operators should go underneath the expressions they operate on.</span></span>

```fsharp
// Preferred approach
let methods2 =
    System.AppDomain.CurrentDomain.GetAssemblies()
    |> List.ofArray
    |> List.map (fun assm -> assm.GetTypes())
    |> Array.concat
    |> List.ofArray
    |> List.map (fun t -> t.GetMethods())
    |> Array.concat

// Not OK
let methods2 = System.AppDomain.CurrentDomain.GetAssemblies()
            |> List.ofArray
            |> List.map (fun assm -> assm.GetTypes())
            |> Array.concat
            |> List.ofArray
            |> List.map (fun t -> t.GetMethods())
            |> Array.concat
```

### <a name="formatting-modules"></a><span data-ttu-id="e9d77-264">モジュールのフォーマット</span><span class="sxs-lookup"><span data-stu-id="e9d77-264">Formatting modules</span></span>

<span data-ttu-id="e9d77-265">ローカル モジュール内のコードはモジュールに対してインデントする必要がありますが、最上位モジュールのコードはインデントしないでください。</span><span class="sxs-lookup"><span data-stu-id="e9d77-265">Code in a local module must be indented relative to the module, but code in a top-level module should not be indented.</span></span> <span data-ttu-id="e9d77-266">名前空間要素はインデントする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e9d77-266">Namespace elements do not have to be indented.</span></span>

```fsharp
// A is a top-level module.
module A

let function1 a b = a - b * b
```

```fsharp
// A1 and A2 are local modules.
module A1 =
    let function1 a b = a*a + b*b

module A2 =
    let function2 a b = a*a - b*b
```

### <a name="formatting-object-expressions-and-interfaces"></a><span data-ttu-id="e9d77-267">オブジェクトの式とインターフェイスの書式設定</span><span class="sxs-lookup"><span data-stu-id="e9d77-267">Formatting object expressions and interfaces</span></span>

<span data-ttu-id="e9d77-268">オブジェクト式とインタフェースは、4 つのスペースの後`member`にインデントされるのと同じように整列する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9d77-268">Object expressions and interfaces should be aligned in the same way with `member` being indented after four spaces.</span></span>

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s: String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-white-space-in-expressions"></a><span data-ttu-id="e9d77-269">式の空白の書式設定</span><span class="sxs-lookup"><span data-stu-id="e9d77-269">Formatting white space in expressions</span></span>

<span data-ttu-id="e9d77-270">F# 式では、余分な空白を避けてください。</span><span class="sxs-lookup"><span data-stu-id="e9d77-270">Avoid extraneous white space in F# expressions.</span></span>

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

<span data-ttu-id="e9d77-271">名前付き引数にも、 を囲`=`むスペースを持たないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9d77-271">Named arguments should also not have space surrounding the `=`:</span></span>

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```

## <a name="formatting-attributes"></a><span data-ttu-id="e9d77-272">属性の書式設定</span><span class="sxs-lookup"><span data-stu-id="e9d77-272">Formatting attributes</span></span>

<span data-ttu-id="e9d77-273">[属性](../language-reference/attributes.md)は、次の構成要素の上に配置されます。</span><span class="sxs-lookup"><span data-stu-id="e9d77-273">[Attributes](../language-reference/attributes.md) are placed above a construct:</span></span>

```fsharp
[<SomeAttribute>]
type MyClass() = ...

[<RequireQualifiedAccess>]
module M =
    let f x = x

[<Struct>]
type MyRecord =
    { Label1: int
      Label2: string }
```

### <a name="formatting-attributes-on-parameters"></a><span data-ttu-id="e9d77-274">パラメータの属性の書式設定</span><span class="sxs-lookup"><span data-stu-id="e9d77-274">Formatting attributes on parameters</span></span>

<span data-ttu-id="e9d77-275">属性は、パラメーターの場所にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="e9d77-275">Attributes can also be places on parameters.</span></span> <span data-ttu-id="e9d77-276">この場合は、パラメータと同じ行に、名前の前に置きます。</span><span class="sxs-lookup"><span data-stu-id="e9d77-276">In this case, place then on the same line as the parameter and before the name:</span></span>

```fsharp
// Defines a class that takes an optional value as input defaulting to false.
type C() =
    member _.M([<Optional; DefaultParameterValue(false)>] doSomething: bool)
```

### <a name="formatting-multiple-attributes"></a><span data-ttu-id="e9d77-277">複数の属性の書式設定</span><span class="sxs-lookup"><span data-stu-id="e9d77-277">Formatting multiple attributes</span></span>

<span data-ttu-id="e9d77-278">パラメータではないコンストラクトに複数の属性が適用される場合、行ごとに 1 つの属性が存在するように配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9d77-278">When multiple attributes are applied to a construct that is not a parameter, they should be placed such that there is one attribute per line:</span></span>

```fsharp
[<Struct>]
[<IsByRefLike>]
type MyRecord =
    { Label1: int
      Label2: string }
```

<span data-ttu-id="e9d77-279">パラメーターに適用する場合、それらは同じ行にあり、区切り記号で`;`区切られている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9d77-279">When applied to a parameter, they must be on the same line and separated by a `;` separator.</span></span>

## <a name="formatting-literals"></a><span data-ttu-id="e9d77-280">リテラルの書式設定</span><span class="sxs-lookup"><span data-stu-id="e9d77-280">Formatting literals</span></span>

<span data-ttu-id="e9d77-281">[属性を使用する F# リテラルは](../language-reference/literals.md)、属性を独自の行に配置し、PascalCase の名前付けを使用する必要があります。 `Literal`</span><span class="sxs-lookup"><span data-stu-id="e9d77-281">[F# literals](../language-reference/literals.md) using the `Literal` attribute should place the attribute on its own line and use PascalCase naming:</span></span>

```fsharp
[<Literal>]
let Path = __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let MyUrl = "www.mywebsitethatiamworkingwith.com"
```

<span data-ttu-id="e9d77-282">属性を値と同じ行に配置しないでください。</span><span class="sxs-lookup"><span data-stu-id="e9d77-282">Avoid placing the attribute on the same line as the value.</span></span>
