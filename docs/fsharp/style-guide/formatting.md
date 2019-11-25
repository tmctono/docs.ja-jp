---
title: F# コードのフォーマットに関するガイドライン
description: コードを書式設定F#するためのガイドラインについて説明します。
ms.date: 11/04/2019
ms.openlocfilehash: 895c8211731b47bd4c59d762d5806cfc1bfe232d
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089312"
---
# <a name="f-code-formatting-guidelines"></a><span data-ttu-id="3c2f0-103">F# コードのフォーマットに関するガイドライン</span><span class="sxs-lookup"><span data-stu-id="3c2f0-103">F# code formatting guidelines</span></span>

<span data-ttu-id="3c2f0-104">この記事では、コードを次のようF#に書式設定する方法に関するガイドラインを提供します。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-104">This article offers guidelines for how to format your code so that your F# code is:</span></span>

* <span data-ttu-id="3c2f0-105">一般に読みやすく表示される</span><span class="sxs-lookup"><span data-stu-id="3c2f0-105">Generally viewed as more legible</span></span>
* <span data-ttu-id="3c2f0-106">は、Visual Studio や他のエディターの書式設定ツールによって適用された規則に従っています</span><span class="sxs-lookup"><span data-stu-id="3c2f0-106">Is in accordance with conventions applied by formatting tools in Visual Studio and other editors</span></span>
* <span data-ttu-id="3c2f0-107">他のコードと同様</span><span class="sxs-lookup"><span data-stu-id="3c2f0-107">Similar to other code online</span></span>

<span data-ttu-id="3c2f0-108">これらのガイドラインは、 [: Ahn-dung Phan](https://github.com/dungpa)による[ F#書式設定規則の包括的なガイド](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md)に基づいています。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-108">These guidelines are based on [A comprehensive guide to F# Formatting Conventions](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) by [Anh-Dung Phan](https://github.com/dungpa).</span></span>

## <a name="general-rules-for-indentation"></a><span data-ttu-id="3c2f0-109">インデントの一般的な規則</span><span class="sxs-lookup"><span data-stu-id="3c2f0-109">General rules for indentation</span></span>

<span data-ttu-id="3c2f0-110">F#既定では有意の空白文字が使用されます。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-110">F# uses significant white space by default.</span></span> <span data-ttu-id="3c2f0-111">次のガイドラインは、このような問題の対処方法に関するガイダンスを提供することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-111">The following guidelines are intended to provide guidance as to how to juggle some challenges this can impose.</span></span>

### <a name="using-spaces"></a><span data-ttu-id="3c2f0-112">スペースの使用</span><span class="sxs-lookup"><span data-stu-id="3c2f0-112">Using spaces</span></span>

<span data-ttu-id="3c2f0-113">インデントが必要な場合は、タブではなく、スペースを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-113">When indentation is required, you must use spaces, not tabs.</span></span> <span data-ttu-id="3c2f0-114">少なくとも1つのスペースが必要です。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-114">At least one space is required.</span></span> <span data-ttu-id="3c2f0-115">組織では、インデントに使用するスペースの数を指定するためのコーディング標準を作成できます。インデントが発生する各レベルで、2つ、3つ、または4個のインデントが行われます。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-115">Your organization can create coding standards to specify the number of spaces to use for indentation; two, three or four spaces of indentation at each level where indentation occurs is typical.</span></span>

<span data-ttu-id="3c2f0-116">**インデントごとに4つのスペースを推奨します。**</span><span class="sxs-lookup"><span data-stu-id="3c2f0-116">**We recommend 4 spaces per indentation.**</span></span>

<span data-ttu-id="3c2f0-117">ただし、プログラムのインデントは主観的な意味を持ちます。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-117">That said, indentation of programs is a subjective matter.</span></span> <span data-ttu-id="3c2f0-118">バリエーションは問題ありませんが、最初に従う必要がある規則は、*インデントの一貫性*です。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-118">Variations are OK, but the first rule you should follow is *consistency of indentation*.</span></span> <span data-ttu-id="3c2f0-119">一般的に受け入れられているインデントのスタイルを選択し、コードベース全体で使用します。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-119">Choose a generally accepted style of indentation and use it systematically throughout your codebase.</span></span>

## <a name="formatting-white-space"></a><span data-ttu-id="3c2f0-120">空白文字の書式設定</span><span class="sxs-lookup"><span data-stu-id="3c2f0-120">Formatting white space</span></span>

<span data-ttu-id="3c2f0-121">F#は空白を区別します。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-121">F# is white space sensitive.</span></span> <span data-ttu-id="3c2f0-122">空白のほとんどのセマンティクスは適切なインデントによってカバーされますが、他にも考慮すべき点があります。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-122">Although most semantics from white space are covered by proper indentation, there are some other things to consider.</span></span>

### <a name="formatting-operators-in-arithmetic-expressions"></a><span data-ttu-id="3c2f0-123">算術式での演算子の書式設定</span><span class="sxs-lookup"><span data-stu-id="3c2f0-123">Formatting operators in arithmetic expressions</span></span>

<span data-ttu-id="3c2f0-124">バイナリ算術式の前後には常に空白文字を使用します。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-124">Always use white space around binary arithmetic expressions:</span></span>

```fsharp
let subtractThenAdd x = x - 1 + 3
```

<span data-ttu-id="3c2f0-125">単項 `-` 演算子には、常に次のように否定される値が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-125">Unary `-` operators should always have the value they are negating immediately follow:</span></span>

```fsharp
// OK
let negate x = -x

// Bad
let negateBad x = - x
```

<span data-ttu-id="3c2f0-126">`-` 演算子の後に空白文字を追加すると、他のユーザーの混乱を招く可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-126">Adding a white-space character after the `-` operator can lead to confusion for others.</span></span>

<span data-ttu-id="3c2f0-127">要約すると、常に次のことが重要になります。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-127">In summary, it's important to always:</span></span>

* <span data-ttu-id="3c2f0-128">バイナリ演算子を空白で囲む</span><span class="sxs-lookup"><span data-stu-id="3c2f0-128">Surround binary operators with white space</span></span>
* <span data-ttu-id="3c2f0-129">単項演算子の後に末尾の空白を含めることはできません</span><span class="sxs-lookup"><span data-stu-id="3c2f0-129">Never have trailing white space after a unary operator</span></span>

<span data-ttu-id="3c2f0-130">二項算術演算子のガイドラインは特に重要です。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-130">The binary arithmetic operator guideline is especially important.</span></span> <span data-ttu-id="3c2f0-131">バイナリ `-` 演算子を囲まないと、特定の書式設定の選択肢と組み合わせると、単項 `-`として解釈される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-131">Failing to surround a binary `-` operator, when combined with certain formatting choices, could lead to interpreting it as a unary `-`.</span></span>

### <a name="surround-a-custom-operator-definition-with-white-space"></a><span data-ttu-id="3c2f0-132">カスタム演算子の定義を空白で囲む</span><span class="sxs-lookup"><span data-stu-id="3c2f0-132">Surround a custom operator definition with white space</span></span>

<span data-ttu-id="3c2f0-133">演算子の定義を囲むには、常に空白文字を使用します。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-133">Always use white space to surround an operator definition:</span></span>

```fsharp
// OK
let ( !> ) x f = f x

// Bad
let (!>) x f = f x
```

<span data-ttu-id="3c2f0-134">`*` で始まり、複数の文字を持つカスタム演算子については、コンパイラのあいまいさを避けるために、定義の先頭に空白を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-134">For any custom operator that starts with `*` and that has more than one character, you need to add a white space to the beginning of the definition to avoid a compiler ambiguity.</span></span> <span data-ttu-id="3c2f0-135">このため、すべての演算子の定義を1つの空白文字で囲むことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-135">Because of this, we recommend that you simply surround the definitions of all operators with a single white-space character.</span></span>

### <a name="surround-function-parameter-arrows-with-white-space"></a><span data-ttu-id="3c2f0-136">関数パラメーターの矢印を空白で囲む</span><span class="sxs-lookup"><span data-stu-id="3c2f0-136">Surround function parameter arrows with white space</span></span>

<span data-ttu-id="3c2f0-137">関数の署名を定義するときは、`->` 記号の周囲に空白文字を使用します。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-137">When defining the signature of a function, use white space around the `->` symbol:</span></span>

```fsharp
// OK
type MyFun = int -> int -> string

// Bad
type MyFunBad = int->int->string
```

### <a name="surround-function-arguments-with-white-space"></a><span data-ttu-id="3c2f0-138">関数の引数を空白で囲む</span><span class="sxs-lookup"><span data-stu-id="3c2f0-138">Surround function arguments with white space</span></span>

<span data-ttu-id="3c2f0-139">関数を定義する場合は、各引数の前後に空白文字を使用します。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-139">When defining a function, use white space around each argument.</span></span>

```fsharp
// OK
let myFun (a: decimal) b c = a + b + c

// Bad
let myFunBad (a:decimal)(b)c = a + b + c
```

### <a name="place-parameters-on-a-new-line-for-very-long-member-definitions"></a><span data-ttu-id="3c2f0-140">非常に長いメンバー定義のために新しい行にパラメーターを配置する</span><span class="sxs-lookup"><span data-stu-id="3c2f0-140">Place parameters on a new line for very long member definitions</span></span>

<span data-ttu-id="3c2f0-141">非常に長いメンバー定義がある場合は、パラメーターを新しい行に配置し、1つのスコープにインデントを設定します。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-141">If you have a very long member definition, place the parameters on new lines and indent them one scope.</span></span>

```fsharp
type C() =
    member _.LongMethodWithLotsOfParameters(
        aVeryLongType: AVeryLongTypeThatYouNeedToUse
        aSecondVeryLongType: AVeryLongTypeThatYouNeedToUse
        aThirdVeryLongType: AVeryLongTypeThatYouNeedToUse) =
        // ... the body of the method follows
```

<span data-ttu-id="3c2f0-142">これは、コンストラクターにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-142">This also applies to constructors:</span></span>

```fsharp
type C(
    aVeryLongType: AVeryLongTypeThatYouNeedToUse
    aSecondVeryLongType: AVeryLongTypeThatYouNeedToUse
    aThirdVeryLongType: AVeryLongTypeThatYouNeedToUse) =
    // ... the body of the class follows
```

### <a name="type-annotations"></a><span data-ttu-id="3c2f0-143">型の注釈</span><span class="sxs-lookup"><span data-stu-id="3c2f0-143">Type annotations</span></span>

#### <a name="right-pad-function-argument-type-annotations"></a><span data-ttu-id="3c2f0-144">右埋め込み関数の引数の型の注釈</span><span class="sxs-lookup"><span data-stu-id="3c2f0-144">Right-pad function argument type annotations</span></span>

<span data-ttu-id="3c2f0-145">型の注釈を持つ引数を定義する場合は、`:` の記号の後に空白文字を使用します。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-145">When defining arguments with type annotations, use white space after the `:` symbol:</span></span>

```fsharp
// OK
let complexFunction (a: int) (b: int) c = a + b + c

// Bad
let complexFunctionBad (a :int) (b :int) (c:int) = a + b + c
```

#### <a name="surround-return-type-annotations-with-white-space"></a><span data-ttu-id="3c2f0-146">戻り値の型の注釈を空白で囲む</span><span class="sxs-lookup"><span data-stu-id="3c2f0-146">Surround return type annotations with white space</span></span>

<span data-ttu-id="3c2f0-147">Let バインド関数または値型の注釈 (関数の場合は戻り値の型) では、`:` 記号の前後に空白文字を使用します。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-147">In a let-bound function or value type annotation (return type in the case of a function), use white space before and after the `:` symbol:</span></span>

```fsharp
// OK
let expensiveToCompute : int = 0 // Type annotation for let-bound value
let myFun (a: decimal) b c : decimal = a + b + c // Type annotation for the return type of a function
// Bad
let expensiveToComputeBad1:int = 1
let expensiveToComputeBad2 :int = 2
let myFunBad (a: decimal) b c:decimal = a + b + c
```

## <a name="formatting-blank-lines"></a><span data-ttu-id="3c2f0-148">空白行の書式設定</span><span class="sxs-lookup"><span data-stu-id="3c2f0-148">Formatting blank lines</span></span>

* <span data-ttu-id="3c2f0-149">最上位の関数とクラスの定義を、2つの空白行で区切ります。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-149">Separate top-level function and class definitions with two blank lines.</span></span>
* <span data-ttu-id="3c2f0-150">クラス内のメソッド定義は、1つの空白行で区切られます。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-150">Method definitions inside a class are separated by a single blank line.</span></span>
* <span data-ttu-id="3c2f0-151">関連する関数のグループを分離するために、余分な空白行を使用する (控えめに) ことがあります。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-151">Extra blank lines may be used (sparingly) to separate groups of related functions.</span></span> <span data-ttu-id="3c2f0-152">関連する1つの liners (たとえば、一連のダミーの実装) 間で空白行を省略することができます。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-152">Blank lines may be omitted between a bunch of related one-liners (for example, a set of dummy implementations).</span></span>
* <span data-ttu-id="3c2f0-153">論理セクションを示すには、関数の空白行を控えめに使用します。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-153">Use blank lines in functions, sparingly, to indicate logical sections.</span></span>

## <a name="formatting-comments"></a><span data-ttu-id="3c2f0-154">コメントの書式設定</span><span class="sxs-lookup"><span data-stu-id="3c2f0-154">Formatting comments</span></span>

<span data-ttu-id="3c2f0-155">一般に、ML スタイルのブロックコメントに対しては、複数のダブルスラッシュコメントを優先します。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-155">Generally prefer multiple double-slash comments over ML-style block comments.</span></span>

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    ML-style comments are fine, but not a .NET-ism.
    They are useful when needing to modify multi-line comments, though.
*)
```

<span data-ttu-id="3c2f0-156">インラインコメントは、最初の文字を大文字にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-156">Inline comments should capitalize the first letter.</span></span>

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a><span data-ttu-id="3c2f0-157">名前付け規則</span><span class="sxs-lookup"><span data-stu-id="3c2f0-157">Naming conventions</span></span>

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a><span data-ttu-id="3c2f0-158">クラスバインド、式バインド、およびパターンバインドの値と関数にキャメルケースを使用する</span><span class="sxs-lookup"><span data-stu-id="3c2f0-158">Use camelCase for class-bound, expression-bound and pattern-bound values and functions</span></span>

<span data-ttu-id="3c2f0-159">これは、ローカル変数F#としてバインドされたすべての名前、またはパターン一致と関数定義でキャメルケースを使用するための一般的なスタイルです。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-159">It is common and accepted F# style to use camelCase for all names bound as local variables or in pattern matches and function definitions.</span></span>

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

<span data-ttu-id="3c2f0-160">クラスのローカルバインド関数は、キャメルケースも使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-160">Locally-bound functions in classes should also use camelCase.</span></span>

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-module-bound-public-functions"></a><span data-ttu-id="3c2f0-161">モジュールバインドパブリック関数にキャメルケースを使用する</span><span class="sxs-lookup"><span data-stu-id="3c2f0-161">Use camelCase for module-bound public functions</span></span>

<span data-ttu-id="3c2f0-162">モジュールバインド関数がパブリック API の一部である場合、キャメルケースを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-162">When a module-bound function is part of a public API, it should use camelCase:</span></span>

```fsharp
module MyAPI =
    let publicFunctionOne param1 param2 param2 = ...

    let publicFunctionTwo param1 param2 param3 = ...
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a><span data-ttu-id="3c2f0-163">内部およびプライベートのモジュールバインド値および関数にキャメルケースを使用する</span><span class="sxs-lookup"><span data-stu-id="3c2f0-163">Use camelCase for internal and private module-bound values and functions</span></span>

<span data-ttu-id="3c2f0-164">次のように、プライベートのモジュールバインド値にはキャメルケースを使用します。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-164">Use camelCase for private module-bound values, including the following:</span></span>

* <span data-ttu-id="3c2f0-165">スクリプト内のアドホック関数</span><span class="sxs-lookup"><span data-stu-id="3c2f0-165">Ad hoc functions in scripts</span></span>

* <span data-ttu-id="3c2f0-166">モジュールまたは型の内部実装を構成する値</span><span class="sxs-lookup"><span data-stu-id="3c2f0-166">Values making up the internal implementation of a module or type</span></span>

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a><span data-ttu-id="3c2f0-167">パラメーターにキャメルケースを使用する</span><span class="sxs-lookup"><span data-stu-id="3c2f0-167">Use camelCase for parameters</span></span>

<span data-ttu-id="3c2f0-168">すべてのパラメーターは、.NET の名前付け規則に従ってキャメルケースを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-168">All parameters should use camelCase in accordance with .NET naming conventions.</span></span>

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a><span data-ttu-id="3c2f0-169">モジュールに対してパスワードを使用する</span><span class="sxs-lookup"><span data-stu-id="3c2f0-169">Use PascalCase for modules</span></span>

<span data-ttu-id="3c2f0-170">すべてのモジュール (最上位レベル、内部、プライベート、入れ子になっている) では、文字を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-170">All modules (top-level, internal, private, nested) should use PascalCase.</span></span>

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a><span data-ttu-id="3c2f0-171">型宣言、メンバー、およびラベルに対しては、文字を使用します。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-171">Use PascalCase for type declarations, members, and labels</span></span>

<span data-ttu-id="3c2f0-172">クラス、インターフェイス、構造体、列挙型、デリゲート、レコード、および判別共用体の名前は、すべて、文字を使用した名前にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-172">Classes, interfaces, structs, enumerations, delegates, records, and discriminated unions should all be named with PascalCase.</span></span> <span data-ttu-id="3c2f0-173">レコードと判別共用体の型およびラベル内のメンバーも、文字を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-173">Members within types and labels for records and discriminated unions should also use PascalCase.</span></span>

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

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a><span data-ttu-id="3c2f0-174">.NET に固有の構造体には、パスワードを使用する</span><span class="sxs-lookup"><span data-stu-id="3c2f0-174">Use PascalCase for constructs intrinsic to .NET</span></span>

<span data-ttu-id="3c2f0-175">名前空間、例外、イベント、およびプロジェクト/`.dll` 名でも、使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-175">Namespaces, exceptions, events, and project/`.dll` names should also use PascalCase.</span></span> <span data-ttu-id="3c2f0-176">他の .NET 言語からの消費が、コンシューマーにとって自然なものであるだけでなく、発生する可能性のある .NET の名前付け規則とも一貫しています。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-176">Not only does this make consumption from other .NET languages feel more natural to consumers, it's also consistent with .NET naming conventions that you are likely to encounter.</span></span>

### <a name="avoid-underscores-in-names"></a><span data-ttu-id="3c2f0-177">名前にアンダースコアを使わない</span><span class="sxs-lookup"><span data-stu-id="3c2f0-177">Avoid underscores in names</span></span>

<span data-ttu-id="3c2f0-178">これまで、 F#一部のライブラリでは、名前にアンダースコアが使用されていました。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-178">Historically, some F# libraries have used underscores in names.</span></span> <span data-ttu-id="3c2f0-179">ただし、これは .NET の名前付け規則と競合するため、広く受け入れられなくなりました。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-179">However, this is no longer widely accepted, partly because it clashes with .NET naming conventions.</span></span> <span data-ttu-id="3c2f0-180">ただし、プログラマにF#よっては、アンダースコアが頻繁に使用され、履歴上の理由により、許容範囲と尊重が重要になります。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-180">That said, some F# programmers use underscores heavily, partly for historical reasons, and tolerance and respect is important.</span></span> <span data-ttu-id="3c2f0-181">ただし、スタイルは多くの場合、使用するかどうかを選択できる他のユーザーによって無効になっていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-181">However, be aware that the style is often disliked by others who have a choice about whether to use it.</span></span>

<span data-ttu-id="3c2f0-182">一部の例外には、ネイティブコンポーネントとの相互運用が含まれており、アンダースコアは非常に一般的です。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-182">Some exceptions includes interoperating with native components, where underscores are very common.</span></span>

### <a name="use-standard-f-operators"></a><span data-ttu-id="3c2f0-183">標準F#の演算子を使用する</span><span class="sxs-lookup"><span data-stu-id="3c2f0-183">Use standard F# operators</span></span>

<span data-ttu-id="3c2f0-184">次の演算子はF#標準ライブラリで定義されており、同等のを定義する代わりに使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-184">The following operators are defined in the F# standard library and should be used instead of defining equivalents.</span></span> <span data-ttu-id="3c2f0-185">コードを読みやすくし、慣用的なする傾向があるため、これらの演算子を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-185">Using these operators is recommended as it tends to make code more readable and idiomatic.</span></span> <span data-ttu-id="3c2f0-186">OCaml または他の関数型プログラミング言語の背景を持つ開発者は、さまざまな表現方法に慣れている場合があります。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-186">Developers with a background in OCaml or other functional programming language may be accustomed to different idioms.</span></span> <span data-ttu-id="3c2f0-187">次の一覧は、推奨F#される演算子をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-187">The following list summarizes the recommended F# operators.</span></span>

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

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a><span data-ttu-id="3c2f0-188">後置構文 (`T Foo`) の場合は、ジェネリック (`Foo<T>`) のプレフィックス構文を使用します</span><span class="sxs-lookup"><span data-stu-id="3c2f0-188">Use prefix syntax for generics (`Foo<T>`) in preference to postfix syntax (`T Foo`)</span></span>

<span data-ttu-id="3c2f0-189">F#は、ジェネリック型の名前付けの後置形式の ML スタイル (`int list`など) と、プレフィックス .NET スタイル (たとえば、`list<int>`) の両方を継承します。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-189">F# inherits both the postfix ML style of naming generic types (for example, `int list`) as well as the prefix .NET style (for example, `list<int>`).</span></span> <span data-ttu-id="3c2f0-190">次の5つの特定の種類を除き、.NET スタイルを優先します。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-190">Prefer the .NET style, except for five specific types:</span></span>

1. <span data-ttu-id="3c2f0-191">リストF#の場合は、`list<int>`ではなく、後置形式の `int list` を使用します。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-191">For F# Lists, use the postfix form: `int list` rather than `list<int>`.</span></span>
2. <span data-ttu-id="3c2f0-192">オプションF#には、`option<int>`ではなく、後置形式の `int option` を使用します。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-192">For F# Options, use the postfix form: `int option` rather than `option<int>`.</span></span>
3. <span data-ttu-id="3c2f0-193">値F#オプションの場合は、`voption<int>`ではなく、後置形式の `int voption` を使用します。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-193">For F# Value Options, use the postfix form: `int voption` rather than `voption<int>`.</span></span>
4. <span data-ttu-id="3c2f0-194">配列F#の場合は、`int array` または `array<int>`ではなく、構文名 `int[]` を使用します。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-194">For F# arrays, use the syntactic name `int[]` rather than `int array` or `array<int>`.</span></span>
5. <span data-ttu-id="3c2f0-195">参照セルの場合は、`ref<int>` または `Ref<int>`ではなく `int ref` を使用します。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-195">For Reference Cells, use `int ref` rather than `ref<int>` or `Ref<int>`.</span></span>

<span data-ttu-id="3c2f0-196">それ以外のすべての型については、プレフィックスフォームを使用します。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-196">For all other types, use the prefix form.</span></span>

## <a name="formatting-tuples"></a><span data-ttu-id="3c2f0-197">タプルの書式設定</span><span class="sxs-lookup"><span data-stu-id="3c2f0-197">Formatting tuples</span></span>

<span data-ttu-id="3c2f0-198">組のインスタンス化は、かっこで囲む必要があります。また、内の区切り記号の後には、1つのスペースを指定する必要があります (例: `(1, 2)`、`(x, y, z)`)。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-198">A tuple instantiation should be parenthesized, and the delimiting commas within should be followed by a single space, for example: `(1, 2)`, `(x, y, z)`.</span></span>

<span data-ttu-id="3c2f0-199">通常は、組のパターンマッチングでかっこを省略することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-199">It is commonly accepted to omit parentheses in pattern matching of tuples:</span></span>

```fsharp
let (x, y) = z // Destructuring
let x, y = z // OK

// OK
match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

<span data-ttu-id="3c2f0-200">タプルが関数の戻り値の場合は、通常、かっこを省略することもできます。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-200">It is also commonly accepted to omit parentheses if the tuple is the return value of a function:</span></span>

```fsharp
// OK
let update model msg =
    match msg with
    | 1 -> model + 1, []
    | _ -> model, [ msg ]
```

<span data-ttu-id="3c2f0-201">まとめとして、かっこで囲まれたタプルのインスタンス化を使用しますが、パターンマッチングまたは戻り値に組を使用する場合は、かっこを使用しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-201">In summary, prefer parenthesized tuple instantiations, but when using tuples for pattern matching or a return value, it is considered fine to avoid parentheses.</span></span>

## <a name="formatting-discriminated-union-declarations"></a><span data-ttu-id="3c2f0-202">判別共用体宣言の書式設定</span><span class="sxs-lookup"><span data-stu-id="3c2f0-202">Formatting discriminated union declarations</span></span>

<span data-ttu-id="3c2f0-203">4つのスペースによる型定義内のインデント `|`:</span><span class="sxs-lookup"><span data-stu-id="3c2f0-203">Indent `|` in type definition by 4 spaces:</span></span>

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

## <a name="formatting-discriminated-unions"></a><span data-ttu-id="3c2f0-204">判別共用体の書式設定</span><span class="sxs-lookup"><span data-stu-id="3c2f0-204">Formatting discriminated unions</span></span>

<span data-ttu-id="3c2f0-205">複数の行に分割されるインスタンス化された判別共用体は、含まれるデータにインデントを含む新しいスコープを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-205">Instantiated Discriminated Unions that split across multiple lines should give contained data a new scope with indentation:</span></span>

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

<span data-ttu-id="3c2f0-206">右かっこは、新しい行にも指定できます。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-206">The closing parenthesis can also be on a new line:</span></span>

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-record-declarations"></a><span data-ttu-id="3c2f0-207">レコード宣言の書式設定</span><span class="sxs-lookup"><span data-stu-id="3c2f0-207">Formatting record declarations</span></span>

<span data-ttu-id="3c2f0-208">4つのスペースで型定義内の `{` をインデントし、同じ行でフィールドリストを開始します。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-208">Indent `{` in type definition by 4 spaces and start the field list on the same line:</span></span>

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

<span data-ttu-id="3c2f0-209">インターフェイスの実装やレコードのメンバーを宣言する場合は、開始トークンを新しい行に配置し、終了トークンを新しい行に配置することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-209">Placing the opening token on a new line and the closing token on a new line is preferable if you are declaring interface implementations or members on the record:</span></span>

```fsharp
// Declaring additional members on PostalAddress
type PostalAddress =
    {
        Address: string
        City: string
        Zip: string
    } with
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

type MyRecord =
    {
        SomeField: int
    }
    interface IMyInterface
```

## <a name="formatting-records"></a><span data-ttu-id="3c2f0-210">レコードの書式設定</span><span class="sxs-lookup"><span data-stu-id="3c2f0-210">Formatting records</span></span>

<span data-ttu-id="3c2f0-211">短いレコードは、1行に記述できます。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-211">Short records can be written in one line:</span></span>

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

<span data-ttu-id="3c2f0-212">ラベルに新しい行を使用する必要があるレコードは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-212">Records that are longer should use new lines for labels:</span></span>

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

<span data-ttu-id="3c2f0-213">次の場合は、開始トークンを新しい行に配置し、1つのスコープの上にある [コンテンツ] タブと、新しい行の終了トークンを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-213">Placing the opening token on a new line, the contents tabbed over one scope, and the closing token on a new line is preferable if you are:</span></span>

* <span data-ttu-id="3c2f0-214">異なるインデントスコープを持つコード内でのレコードの移動</span><span class="sxs-lookup"><span data-stu-id="3c2f0-214">Moving records around in code with different indentation scopes</span></span>
* <span data-ttu-id="3c2f0-215">関数にパイプする</span><span class="sxs-lookup"><span data-stu-id="3c2f0-215">Piping them into a function</span></span>

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

<span data-ttu-id="3c2f0-216">リストおよび配列要素にも同じ規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-216">The same rules apply for list and array elements.</span></span>

## <a name="formatting-copy-and-update-record-expressions"></a><span data-ttu-id="3c2f0-217">コピーおよび更新レコード式の書式設定</span><span class="sxs-lookup"><span data-stu-id="3c2f0-217">Formatting copy-and-update record expressions</span></span>

<span data-ttu-id="3c2f0-218">コピーと更新のレコード式は依然としてレコードであるため、同様のガイドラインが適用されます。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-218">A copy-and-update record expression is still a record, so similar guidelines apply.</span></span>

<span data-ttu-id="3c2f0-219">短い式は、1行に収めることができます。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-219">Short expressions can fit on one line:</span></span>

```fsharp
let point2 = { point with X = 1; Y = 2 }
```

<span data-ttu-id="3c2f0-220">長い式では、新しい行を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-220">Longer expressions should use new lines:</span></span>

```fsharp
let rainbow2 =
    { rainbow with
        Boss = "Jeffrey"
        Lackeys = ["Zippy"; "George"; "Bungle"] }
```

<span data-ttu-id="3c2f0-221">レコードガイダンスと同様に、中かっこに個別の行を追加し、式を使用して1つのスコープを右側にインデントすることもできます。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-221">And as with the record guidance, you may want to dedicate separate lines for the braces and indent one scope to the right with the expression.</span></span> <span data-ttu-id="3c2f0-222">一部の特殊なケースでは、かっこを使用せずに省略可能な値をラップする場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-222">Note that in some special cases, such as wrapping a value with an optional without parentheses, you may need to keep a brace on one line:</span></span>

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

## <a name="formatting-lists-and-arrays"></a><span data-ttu-id="3c2f0-223">リストと配列の書式設定</span><span class="sxs-lookup"><span data-stu-id="3c2f0-223">Formatting lists and arrays</span></span>

<span data-ttu-id="3c2f0-224">`::` 演算子の前後にスペースを使用して `x :: l` を記述します (`::` は挿入演算子であり、そのためスペースで囲まれています)。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-224">Write `x :: l` with spaces around the `::` operator (`::` is an infix operator, hence surrounded by spaces).</span></span>

<span data-ttu-id="3c2f0-225">1つの行で宣言されたリストと配列には、左角かっこの前と右角かっこの前にスペースが必要です。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-225">List and arrays declared on a single line should have a space after the opening bracket and before the closing bracket:</span></span>

```fsharp
let xs = [ 1; 2; 3 ]
let ys = [| 1; 2; 3; |]
```

<span data-ttu-id="3c2f0-226">2つの異なるかっこで囲まれた演算子の間には、常に少なくとも1つの空白文字を使用します。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-226">Always use at least one space between two distinct brace-like operators.</span></span> <span data-ttu-id="3c2f0-227">たとえば、`[` と `{`の間にはスペースを入れます。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-227">For example, leave a space between a `[` and a `{`.</span></span>

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

<span data-ttu-id="3c2f0-228">組のリストまたは配列にも同じガイドラインが適用されます。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-228">The same guideline applies for lists or arrays of tuples.</span></span>

<span data-ttu-id="3c2f0-229">複数の行にわたって分割されるリストと配列は、レコードと同様のルールに従います。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-229">Lists and arrays that split across multiple lines follow a similar rule as records do:</span></span>

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

<span data-ttu-id="3c2f0-230">レコードの場合と同様に、開始角かっこと右角かっこを独自の行で宣言すると、コードの移動や関数へのパイプ処理が容易になります。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-230">And as with records, declaring the opening and closing brackets on their own line will make moving code around and piping into functions easier.</span></span>

<span data-ttu-id="3c2f0-231">プログラムによって配列とリストを生成する場合は、常に値が生成されるときに `do ... yield` より `->` を優先します。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-231">When generating arrays and lists programmatically, prefer `->` over `do ... yield` when a value is always generated:</span></span>

```fsharp
// Preferred
let squares = [ for x in 1..10 -> x*x ]

// Not preferred
let squares' = [ for x in 1..10 do yield x*x ]
```

<span data-ttu-id="3c2f0-232">以前のバージョンのF#言語では、データが条件付きで生成される場合や、連続して評価される式がある場合に `yield` を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-232">Older versions of the F# language required specifying `yield` in situations where data may be generated conditionally, or there may be consecutive expressions to be evaluated.</span></span> <span data-ttu-id="3c2f0-233">古いF#言語バージョンでコンパイルする必要がある場合を除き、これらの `yield` キーワードは省略してください。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-233">Prefer omitting these `yield` keywords unless you must compile with an older F# language version:</span></span>

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

<span data-ttu-id="3c2f0-234">場合によっては、`do...yield` が読みやすくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-234">In some cases, `do...yield` may aid in readability.</span></span> <span data-ttu-id="3c2f0-235">ただし、このような場合は主観的に考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-235">These cases, though subjective, should be taken into consideration.</span></span>

## <a name="formatting-if-expressions"></a><span data-ttu-id="3c2f0-236">If 式の書式設定</span><span class="sxs-lookup"><span data-stu-id="3c2f0-236">Formatting if expressions</span></span>

<span data-ttu-id="3c2f0-237">条件のインデントは、それらを作成する式のサイズによって異なります。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-237">Indentation of conditionals depends on the sizes of the expressions that make them up.</span></span> <span data-ttu-id="3c2f0-238">`cond`、`e1` と `e2` が短い場合は、単に1行に記述するだけです。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-238">If `cond`, `e1` and `e2` are short, simply write them on one line:</span></span>

```fsharp
if cond then e1 else e2
```

<span data-ttu-id="3c2f0-239">`cond`のいずれかの場合、`e1` または `e2` は長くなりますが、複数行にはなりません。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-239">If either `cond`, `e1` or `e2` are longer, but not multi-line:</span></span>

```fsharp
if cond
then e1
else e2
```

<span data-ttu-id="3c2f0-240">式のいずれかが複数行の場合は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-240">If any of the expressions are multi-line:</span></span>

```fsharp
if cond then
    e1
else
    e2
```

<span data-ttu-id="3c2f0-241">`elif` と `else` を持つ複数の条件は、`if`と同じスコープでインデントされます。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-241">Multiple conditionals with `elif` and `else` are indented at the same scope as the `if`:</span></span>

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a><span data-ttu-id="3c2f0-242">パターン一致のコンストラクト</span><span class="sxs-lookup"><span data-stu-id="3c2f0-242">Pattern matching constructs</span></span>

<span data-ttu-id="3c2f0-243">照合の各句に対して、インデントなしの `|` を使用します。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-243">Use a `|` for each clause of a match with no indentation.</span></span> <span data-ttu-id="3c2f0-244">式が短い場合は、各部分式も単純である場合は単一行を使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-244">If the expression is short, you can consider using a single line if each subexpression is also simple.</span></span>

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

<span data-ttu-id="3c2f0-245">[パターン一致] の矢印の右側にある式が大きすぎる場合は、次の行に移動して、`match`/`|`の1つの手順をインデントします。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-245">If the expression on the right of the pattern matching arrow is too large, move it to the following line, indented one step from the `match`/`|`.</span></span>

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

<span data-ttu-id="3c2f0-246">`function`から始まる匿名関数のパターンマッチングは、通常はあまりインデントされません。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-246">Pattern matching of anonymous functions, starting by `function`, should generally not indent too far.</span></span> <span data-ttu-id="3c2f0-247">たとえば、次のように1つのスコープをインデントすることは問題ありません。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-247">For example, indenting one scope as follows is fine:</span></span>

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

<span data-ttu-id="3c2f0-248">`let` または `let rec` で定義された関数でのパターンマッチングは、`function` キーワードが使用されている場合でも、`let`の開始後に4つのスペースをインデントする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-248">Pattern matching in functions defined by `let` or `let rec` should be indented 4 spaces after starting of `let`, even if `function` keyword is used:</span></span>

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

<span data-ttu-id="3c2f0-249">矢印は配置しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-249">We do not recommend aligning arrows.</span></span>

## <a name="formatting-trywith-expressions"></a><span data-ttu-id="3c2f0-250">Try/with 式の書式設定</span><span class="sxs-lookup"><span data-stu-id="3c2f0-250">Formatting try/with expressions</span></span>

<span data-ttu-id="3c2f0-251">例外の種類のパターンマッチングは、`with`と同じレベルでインデントする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-251">Pattern matching on the exception type should be indented at the same level as `with`.</span></span>

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

## <a name="formatting-function-parameter-application"></a><span data-ttu-id="3c2f0-252">関数パラメーターアプリケーションの書式設定</span><span class="sxs-lookup"><span data-stu-id="3c2f0-252">Formatting function parameter application</span></span>

<span data-ttu-id="3c2f0-253">一般に、ほとんどの関数パラメーターアプリケーションは同じ行で実行されます。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-253">In general, most function parameter application is done on the same line.</span></span>

<span data-ttu-id="3c2f0-254">新しい行の関数にパラメーターを適用する場合は、1つのスコープでインデントします。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-254">If you wish to apply parameters to a function on a new line, indent them by one scope.</span></span>

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

<span data-ttu-id="3c2f0-255">ラムダ式には、関数の引数と同じガイドラインが適用されます。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-255">The same guidelines apply for lambda expressions as function arguments.</span></span> <span data-ttu-id="3c2f0-256">ラムダ式の本体の場合、本文は別の行を持つことができ、1つのスコープでインデントされます。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-256">If the body of a lambda expression, the body can have another line, indented by one scope</span></span>

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

<span data-ttu-id="3c2f0-257">ただし、ラムダ式の本体が複数行である場合は、複数行の構成要素を関数に1つの引数として適用するのではなく、別の関数にファクタリングすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-257">However, if the body of a lambda expression is more than one line, consider factoring it out into a separate function rather than have a multi-line construct applied as a single argument to a function.</span></span>

### <a name="formatting-infix-operators"></a><span data-ttu-id="3c2f0-258">挿入演算子の書式設定</span><span class="sxs-lookup"><span data-stu-id="3c2f0-258">Formatting infix operators</span></span>

<span data-ttu-id="3c2f0-259">演算子はスペースで区切ります。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-259">Separate operators by spaces.</span></span> <span data-ttu-id="3c2f0-260">このルールの明確な例外は、`!` 演算子と `.` 演算子です。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-260">Obvious exceptions to this rule are the `!` and `.` operators.</span></span>

<span data-ttu-id="3c2f0-261">挿入式は、同じ列に編成することができます。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-261">Infix expressions are OK to lineup on same column:</span></span>

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a><span data-ttu-id="3c2f0-262">パイプライン演算子の書式設定</span><span class="sxs-lookup"><span data-stu-id="3c2f0-262">Formatting pipeline operators</span></span>

<span data-ttu-id="3c2f0-263">パイプライン `|>` 演算子は、操作対象の式の下にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-263">Pipeline `|>` operators should go underneath the expressions they operate on.</span></span>

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

### <a name="formatting-modules"></a><span data-ttu-id="3c2f0-264">モジュールの書式設定</span><span class="sxs-lookup"><span data-stu-id="3c2f0-264">Formatting modules</span></span>

<span data-ttu-id="3c2f0-265">ローカルモジュール内のコードは、モジュールに対して相対的にインデントする必要がありますが、最上位レベルのモジュール内のコードをインデントすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-265">Code in a local module must be indented relative to the module, but code in a top-level module should not be indented.</span></span> <span data-ttu-id="3c2f0-266">名前空間要素をインデントする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-266">Namespace elements do not have to be indented.</span></span>

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

### <a name="formatting-object-expressions-and-interfaces"></a><span data-ttu-id="3c2f0-267">オブジェクト式およびインターフェイスの書式設定</span><span class="sxs-lookup"><span data-stu-id="3c2f0-267">Formatting object expressions and interfaces</span></span>

<span data-ttu-id="3c2f0-268">オブジェクトの式とインターフェイスは、4つのスペースの後にインデントを設定する `member` のと同じ方法で配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-268">Object expressions and interfaces should be aligned in the same way with `member` being indented after 4 spaces.</span></span>

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s: String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-white-space-in-expressions"></a><span data-ttu-id="3c2f0-269">式の空白の書式設定</span><span class="sxs-lookup"><span data-stu-id="3c2f0-269">Formatting white space in expressions</span></span>

<span data-ttu-id="3c2f0-270">式に余分なスペースF#を含めないでください。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-270">Avoid extraneous white space in F# expressions.</span></span>

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

<span data-ttu-id="3c2f0-271">名前付き引数には、`=`を囲む領域を指定することもできません。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-271">Named arguments should also not have space surrounding the `=`:</span></span>

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```

## <a name="formatting-attributes"></a><span data-ttu-id="3c2f0-272">属性の書式設定</span><span class="sxs-lookup"><span data-stu-id="3c2f0-272">Formatting attributes</span></span>

<span data-ttu-id="3c2f0-273">[属性](../language-reference/attributes.md)はコンストラクトの上に配置されます。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-273">[Attributes](../language-reference/attributes.md) are placed above a construct:</span></span>

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

### <a name="formatting-attributes-on-parameters"></a><span data-ttu-id="3c2f0-274">パラメーターの属性の書式設定</span><span class="sxs-lookup"><span data-stu-id="3c2f0-274">Formatting attributes on parameters</span></span>

<span data-ttu-id="3c2f0-275">属性をパラメーターに配置することもできます。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-275">Attributes can also be places on parameters.</span></span> <span data-ttu-id="3c2f0-276">この場合は、パラメーターと名前の前に次の行を配置します。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-276">In this case, place then on the same line as the parameter and before the name:</span></span>

```fsharp
// Defines a class that takes an optional value as input defaulting to false.
type C() =
    member _.M([<Optional; DefaultParameterValue(false)>] doSomething: bool)
```

### <a name="formatting-multiple-attributes"></a><span data-ttu-id="3c2f0-277">複数の属性の書式設定</span><span class="sxs-lookup"><span data-stu-id="3c2f0-277">Formatting multiple attributes</span></span>

<span data-ttu-id="3c2f0-278">パラメーターではないコンストラクトに複数の属性が適用されている場合は、1行につき1つの属性が存在するように配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-278">When multiple attributes are applied to a construct that is not a parameter, they should be placed such that there is one attribute per line:</span></span>

```fsharp
[<Struct>]
[<IsByRefLike>]
type MyRecord =
    { Label1: int
      Label2: string }
```

<span data-ttu-id="3c2f0-279">パラメーターに適用する場合は、同じ行に配置し、`;` の区切り記号で区切る必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-279">When applied to a parameter, they must be on the same line and separated by a `;` separator.</span></span>

## <a name="formatting-literals"></a><span data-ttu-id="3c2f0-280">リテラルの書式設定</span><span class="sxs-lookup"><span data-stu-id="3c2f0-280">Formatting literals</span></span>

<span data-ttu-id="3c2f0-281">`Literal` 属性を使用するリテラルでは、属性をそれ自体の行に配置し、文字の名前付けを使用します。 [ F# ](../language-reference/literals.md)</span><span class="sxs-lookup"><span data-stu-id="3c2f0-281">[F# literals](../language-reference/literals.md) using the `Literal` attribute should place the attribute on its own line and use PascalCase naming:</span></span>

```fsharp
[<Literal>]
let Path = __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let MyUrl = "www.mywebsitethatiamworkingwith.com"
```

<span data-ttu-id="3c2f0-282">属性を値と同じ行に配置することは避けてください。</span><span class="sxs-lookup"><span data-stu-id="3c2f0-282">Avoid placing the attribute on the same line as the value.</span></span>
