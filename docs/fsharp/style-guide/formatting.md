---
title: F#コードの書式設定に関するガイドライン
description: 書式設定するためのガイドラインについて説明しますF#コード。
ms.date: 02/08/2019
ms.openlocfilehash: 259d4bb2147d1fc8bc5d35d7ff2e3c34ec2185d0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61902591"
---
# <a name="f-code-formatting-guidelines"></a><span data-ttu-id="f80c0-103">F#コードの書式設定に関するガイドライン</span><span class="sxs-lookup"><span data-stu-id="f80c0-103">F# code formatting guidelines</span></span>

<span data-ttu-id="f80c0-104">この記事では、F# コードが実行されるように、コードを書式設定する方法に関するガイドラインを提供します。</span><span class="sxs-lookup"><span data-stu-id="f80c0-104">This article offers guidelines for how to format your code so that your F# code is:</span></span>

* <span data-ttu-id="f80c0-105">一般に読みやすくとして表示</span><span class="sxs-lookup"><span data-stu-id="f80c0-105">Generally viewed as more legible</span></span>
* <span data-ttu-id="f80c0-106">Visual Studio のツールとその他のエディターの書式設定が適用される規則に従って、します。</span><span class="sxs-lookup"><span data-stu-id="f80c0-106">Is in accordance with conventions applied by formatting tools in Visual Studio and other editors</span></span>
* <span data-ttu-id="f80c0-107">その他のコードをオンラインに似ています</span><span class="sxs-lookup"><span data-stu-id="f80c0-107">Similar to other code online</span></span>

<span data-ttu-id="f80c0-108">これらのガイドラインに基づいています[F# の書式設定規則に包括的なガイド](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md)によって[Anh 協力 Phan](https://github.com/dungpa)します。</span><span class="sxs-lookup"><span data-stu-id="f80c0-108">These guidelines are based on [A comprehensive guide to F# Formatting Conventions](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) by [Anh-Dung Phan](https://github.com/dungpa).</span></span>

## <a name="general-rules-for-indentation"></a><span data-ttu-id="f80c0-109">インデントの一般的な規則</span><span class="sxs-lookup"><span data-stu-id="f80c0-109">General rules for indentation</span></span>

<span data-ttu-id="f80c0-110">F#既定では、有意の空白を使用します。</span><span class="sxs-lookup"><span data-stu-id="f80c0-110">F# uses significant white space by default.</span></span> <span data-ttu-id="f80c0-111">次のガイドラインはこれをかけることがいくつかの課題を使い分ける方法についてのガイダンスを提供するためのものです。</span><span class="sxs-lookup"><span data-stu-id="f80c0-111">The following guidelines are intended to provide guidance as to how to juggle some challenges this can impose.</span></span>

### <a name="using-spaces"></a><span data-ttu-id="f80c0-112">スペースを使用します。</span><span class="sxs-lookup"><span data-stu-id="f80c0-112">Using spaces</span></span>

<span data-ttu-id="f80c0-113">インデントが必要な場合は、スペース、タブではなくを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f80c0-113">When indentation is required, you must use spaces, not tabs.</span></span> <span data-ttu-id="f80c0-114">少なくとも 1 つの領域が必要です。</span><span class="sxs-lookup"><span data-stu-id="f80c0-114">At least one space is required.</span></span> <span data-ttu-id="f80c0-115">組織がインデントに使用する空白文字の数を指定するコーディング規則を作成できます。各レベルのインデントを設定するインデントの 2 つ、3 つまたは 4 つのスペースが一般的です。</span><span class="sxs-lookup"><span data-stu-id="f80c0-115">Your organization can create coding standards to specify the number of spaces to use for indentation; two, three or four spaces of indentation at each level where indentation occurs is typical.</span></span>

<span data-ttu-id="f80c0-116">**インデントあたり 4 つのスペースをお勧めします。**</span><span class="sxs-lookup"><span data-stu-id="f80c0-116">**We recommend 4 spaces per indentation.**</span></span>

<span data-ttu-id="f80c0-117">ただし、プログラムのインデントは主観的な問題。</span><span class="sxs-lookup"><span data-stu-id="f80c0-117">That said, indentation of programs is a subjective matter.</span></span> <span data-ttu-id="f80c0-118">バリエーションが [ok] が最初の規則に従う必要がありますが、*インデントの一貫性*します。</span><span class="sxs-lookup"><span data-stu-id="f80c0-118">Variations are OK, but the first rule you should follow is *consistency of indentation*.</span></span> <span data-ttu-id="f80c0-119">インデントの一般的に受け入れられるスタイルを選択し、コードベース全体で体系的に使用します。</span><span class="sxs-lookup"><span data-stu-id="f80c0-119">Choose a generally accepted style of indentation and use it systematically throughout your codebase.</span></span>

## <a name="formatting-white-space"></a><span data-ttu-id="f80c0-120">空白文字を書式設定</span><span class="sxs-lookup"><span data-stu-id="f80c0-120">Formatting white space</span></span>

<span data-ttu-id="f80c0-121">F#機密性の高い空白などです。</span><span class="sxs-lookup"><span data-stu-id="f80c0-121">F# is white space sensitive.</span></span> <span data-ttu-id="f80c0-122">適切なインデントによってカバーされて空白からほとんどのセマンティクスは、その他の考慮事項があります。</span><span class="sxs-lookup"><span data-stu-id="f80c0-122">Although most semantics from white space are covered by proper indentation, there are some other things to consider.</span></span>

### <a name="formatting-operators-in-arithmetic-expressions"></a><span data-ttu-id="f80c0-123">算術式の演算子を書式設定</span><span class="sxs-lookup"><span data-stu-id="f80c0-123">Formatting operators in arithmetic expressions</span></span>

<span data-ttu-id="f80c0-124">二項演算式の周囲の空白を常に使用するには。</span><span class="sxs-lookup"><span data-stu-id="f80c0-124">Always use white space around binary arithmetic expressions:</span></span>

```fsharp
let subtractThenAdd x = x - 1 + 3
```

<span data-ttu-id="f80c0-125">単項`-`が否定されますが、値が演算子の直後に。</span><span class="sxs-lookup"><span data-stu-id="f80c0-125">Unary `-` operators should always have the value they are negating immediately follow:</span></span>

```fsharp
// OK
let negate x = -x

// Bad
let negateBad x = - x
```

<span data-ttu-id="f80c0-126">後の空白文字を追加、`-`演算子は、他のユーザーの混乱を招くことができます。</span><span class="sxs-lookup"><span data-stu-id="f80c0-126">Adding a white-space character after the `-` operator can lead to confusion for others.</span></span>

<span data-ttu-id="f80c0-127">要約すると、常に重要ですが。</span><span class="sxs-lookup"><span data-stu-id="f80c0-127">In summary, it's important to always:</span></span>

* <span data-ttu-id="f80c0-128">空白文字で二項演算子のブロックの挿入</span><span class="sxs-lookup"><span data-stu-id="f80c0-128">Surround binary operators with white space</span></span>
* <span data-ttu-id="f80c0-129">単項演算子の後に末尾の空白文字があることはありません。</span><span class="sxs-lookup"><span data-stu-id="f80c0-129">Never have trailing white space after a unary operator</span></span>

<span data-ttu-id="f80c0-130">二項算術演算子のガイドラインは、特に重要です。</span><span class="sxs-lookup"><span data-stu-id="f80c0-130">The binary arithmetic operator guideline is especially important.</span></span> <span data-ttu-id="f80c0-131">バイナリ ブロックの挿入に失敗する`-`演算子、特定の書式設定が選択されている項目と組み合わせたときに、単項演算子として解釈する可能性があります`-`します。</span><span class="sxs-lookup"><span data-stu-id="f80c0-131">Failing to surround a binary `-` operator, when combined with certain formatting choices, could lead to interpreting it as a unary `-`.</span></span>

### <a name="surround-a-custom-operator-definition-with-white-space"></a><span data-ttu-id="f80c0-132">空白文字でカスタム演算子の定義ブロックの挿入</span><span class="sxs-lookup"><span data-stu-id="f80c0-132">Surround a custom operator definition with white space</span></span>

<span data-ttu-id="f80c0-133">常に演算子の定義を囲む空白を使用します。</span><span class="sxs-lookup"><span data-stu-id="f80c0-133">Always use white space to surround an operator definition:</span></span>

```fsharp
// OK
let ( !> ) x f = f x

// Bad
let (!>) x f = f x
```

<span data-ttu-id="f80c0-134">始まる任意のカスタム演算子の`*`と 1 つ以上の文字を持つ、コンパイラのあいまいさを避けるために、定義の先頭に空白文字を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f80c0-134">For any custom operator that starts with `*` and that has more than one character, you need to add a white space to the beginning of the definition to avoid a compiler ambiguity.</span></span> <span data-ttu-id="f80c0-135">このため、単に 1 つの空白文字を持つすべての演算子の定義を囲むことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f80c0-135">Because of this, we recommend that you simply surround the definitions of all operators with a single white-space character.</span></span>

### <a name="surround-function-parameter-arrows-with-white-space"></a><span data-ttu-id="f80c0-136">空白文字で関数パラメーターの矢印を囲む</span><span class="sxs-lookup"><span data-stu-id="f80c0-136">Surround function parameter arrows with white space</span></span>

<span data-ttu-id="f80c0-137">関数のシグネチャを定義するときに、周囲の空白を使用して、`->`シンボル。</span><span class="sxs-lookup"><span data-stu-id="f80c0-137">When defining the signature of a function, use white space around the `->` symbol:</span></span>

```fsharp
// OK
type MyFun = int -> int -> string

// Bad
type MyFunBad = int->int->string
```

## <a name="formatting-blank-lines"></a><span data-ttu-id="f80c0-138">空白行を書式設定</span><span class="sxs-lookup"><span data-stu-id="f80c0-138">Formatting blank lines</span></span>

* <span data-ttu-id="f80c0-139">独立したトップレベル関数やクラスの定義 2 つの空白行を含む。</span><span class="sxs-lookup"><span data-stu-id="f80c0-139">Separate top-level function and class definitions with two blank lines.</span></span>
* <span data-ttu-id="f80c0-140">クラス内でメソッドの定義は、単一の空白行で区切られます。</span><span class="sxs-lookup"><span data-stu-id="f80c0-140">Method definitions inside a class are separated by a single blank line.</span></span>
* <span data-ttu-id="f80c0-141">余分な空白行は、関連する関数のグループを区切る (控えめ) に使用する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f80c0-141">Extra blank lines may be used (sparingly) to separate groups of related functions.</span></span> <span data-ttu-id="f80c0-142">一連の関連困ら (たとえば、ダミーの実装のセット) の間の空白行は省略できます。</span><span class="sxs-lookup"><span data-stu-id="f80c0-142">Blank lines may be omitted between a bunch of related one-liners (for example, a set of dummy implementations).</span></span>
* <span data-ttu-id="f80c0-143">論理的なセクションを示すために、関数では、空白行を使用します。</span><span class="sxs-lookup"><span data-stu-id="f80c0-143">Use blank lines in functions, sparingly, to indicate logical sections.</span></span>

## <a name="formatting-comments"></a><span data-ttu-id="f80c0-144">コメントの書式設定</span><span class="sxs-lookup"><span data-stu-id="f80c0-144">Formatting comments</span></span>

<span data-ttu-id="f80c0-145">一般に ML スタイル ブロックのコメントを複数のコメントをダブル スラッシュを好みます。</span><span class="sxs-lookup"><span data-stu-id="f80c0-145">Generally prefer multiple double-slash comments over ML-style block comments.</span></span>

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    ML-style comments are fine, but not a .NET-ism.
    They are useful when needing to modify multi-line comments, though.
*)
```

<span data-ttu-id="f80c0-146">インライン コメントは、最初の文字を大文字にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f80c0-146">Inline comments should capitalize the first letter.</span></span>

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a><span data-ttu-id="f80c0-147">名前付け規則</span><span class="sxs-lookup"><span data-stu-id="f80c0-147">Naming conventions</span></span>

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a><span data-ttu-id="f80c0-148">キャメル ケースを使用して、クラス バインド、バインド式とパターン バインドの値と関数</span><span class="sxs-lookup"><span data-stu-id="f80c0-148">Use camelCase for class-bound, expression-bound and pattern-bound values and functions</span></span>

<span data-ttu-id="f80c0-149">一般的な camelCase を使用して、すべての名前を指定できる F# スタイルには、ローカル変数として、またはパターン マッチと関数定義がバインドされています。</span><span class="sxs-lookup"><span data-stu-id="f80c0-149">It is common and accepted F# style to use camelCase for all names bound as local variables or in pattern matches and function definitions.</span></span>

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

<span data-ttu-id="f80c0-150">クラスのローカルにバインドされた関数は、camelCase を使用してもする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f80c0-150">Locally-bound functions in classes should also use camelCase.</span></span>

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-module-bound-public-functions"></a><span data-ttu-id="f80c0-151">キャメル ケースを使用してバインド モジュールのパブリック関数</span><span class="sxs-lookup"><span data-stu-id="f80c0-151">Use camelCase for module-bound public functions</span></span>

<span data-ttu-id="f80c0-152">モジュール連結関数は、パブリック API の一部が、camelCase を使用します。</span><span class="sxs-lookup"><span data-stu-id="f80c0-152">When a module-bound function is part of a public API, it should use camelCase:</span></span>

```fsharp
module MyAPI =
    let publicFunctionOne param1 param2 param2 = ...

    let publicFunctionTwo param1 param2 param3 = ...
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a><span data-ttu-id="f80c0-153">キャメル ケースを使用して、内部、プライベート モジュール連結値および関数</span><span class="sxs-lookup"><span data-stu-id="f80c0-153">Use camelCase for internal and private module-bound values and functions</span></span>

<span data-ttu-id="f80c0-154">プライベート モジュール連結値は、次のようには、camelCase を使用します。</span><span class="sxs-lookup"><span data-stu-id="f80c0-154">Use camelCase for private module-bound values, including the following:</span></span>

* <span data-ttu-id="f80c0-155">スクリプトでアドホック関数</span><span class="sxs-lookup"><span data-stu-id="f80c0-155">Ad hoc functions in scripts</span></span>

* <span data-ttu-id="f80c0-156">モジュールまたは型の内部実装を作成する値</span><span class="sxs-lookup"><span data-stu-id="f80c0-156">Values making up the internal implementation of a module or type</span></span>

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a><span data-ttu-id="f80c0-157">パラメーターにキャメル ケースを使用します。</span><span class="sxs-lookup"><span data-stu-id="f80c0-157">Use camelCase for parameters</span></span>

<span data-ttu-id="f80c0-158">すべてのパラメーターは、.NET の名前付け規則に従って、camelCase を使用してください。</span><span class="sxs-lookup"><span data-stu-id="f80c0-158">All parameters should use camelCase in accordance with .NET naming conventions.</span></span>

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a><span data-ttu-id="f80c0-159">PascalCase モジュールを使用します。</span><span class="sxs-lookup"><span data-stu-id="f80c0-159">Use PascalCase for modules</span></span>

<span data-ttu-id="f80c0-160">(最上位レベル、内部、プライベートの入れ子になった) のすべてのモジュールは PascalCase を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f80c0-160">All modules (top-level, internal, private, nested) should use PascalCase.</span></span>

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a><span data-ttu-id="f80c0-161">PascalCase を使用して、型宣言、メンバー、およびラベル</span><span class="sxs-lookup"><span data-stu-id="f80c0-161">Use PascalCase for type declarations, members, and labels</span></span>

<span data-ttu-id="f80c0-162">クラス、インターフェイス、構造体、列挙、デリゲート、レコード、および判別共用体がすべての名前は PascalCase です。</span><span class="sxs-lookup"><span data-stu-id="f80c0-162">Classes, interfaces, structs, enumerations, delegates, records, and discriminated unions should all be named with PascalCase.</span></span> <span data-ttu-id="f80c0-163">型およびレコード、判別共用体のラベル内のメンバーは、PascalCase を使用してもする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f80c0-163">Members within types and labels for records and discriminated unions should also use PascalCase.</span></span>

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

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a><span data-ttu-id="f80c0-164">PascalCase を使用して、.NET に固有の構成要素</span><span class="sxs-lookup"><span data-stu-id="f80c0-164">Use PascalCase for constructs intrinsic to .NET</span></span>

<span data-ttu-id="f80c0-165">名前空間、例外、イベント、およびプロジェクト/`.dll`名も PascalCase を使用します。</span><span class="sxs-lookup"><span data-stu-id="f80c0-165">Namespaces, exceptions, events, and project/`.dll` names should also use PascalCase.</span></span> <span data-ttu-id="f80c0-166">だけでなく、これにより、コンシューマーに自然に感じられる他の .NET 言語から消費も発生する可能性がある .NET の名前付け規則と一致します。</span><span class="sxs-lookup"><span data-stu-id="f80c0-166">Not only does this make consumption from other .NET languages feel more natural to consumers, it's also consistent with .NET naming conventions that you are likely to encounter.</span></span>

### <a name="avoid-underscores-in-names"></a><span data-ttu-id="f80c0-167">名前にアンダー スコアを回避します。</span><span class="sxs-lookup"><span data-stu-id="f80c0-167">Avoid underscores in names</span></span>

<span data-ttu-id="f80c0-168">従来、一部の F# ライブラリは、名前にアンダー スコアを使用するが。</span><span class="sxs-lookup"><span data-stu-id="f80c0-168">Historically, some F# libraries have used underscores in names.</span></span> <span data-ttu-id="f80c0-169">ただし、これが不要になった広く受け入れられて .NET の名前付け規則と衝突ためです。</span><span class="sxs-lookup"><span data-stu-id="f80c0-169">However, this is no longer widely accepted, partly because it clashes with .NET naming conventions.</span></span> <span data-ttu-id="f80c0-170">ただし、F# プログラマによってアンダー スコアは使用頻度の高い、一部の歴史的な理由と許容範囲と点が重要です。</span><span class="sxs-lookup"><span data-stu-id="f80c0-170">That said, some F# programmers use underscores heavily, partly for historical reasons, and tolerance and respect is important.</span></span> <span data-ttu-id="f80c0-171">ただし、スタイルが使用するかどうかの選択肢を持つ他のユーザーによって多くの場合、我慢しなければならないこともあります。</span><span class="sxs-lookup"><span data-stu-id="f80c0-171">However, be aware that the style is often disliked by others who have a choice about whether to use it.</span></span>

<span data-ttu-id="f80c0-172">いくつかの例外には、アンダー スコアが非常に一般的であるネイティブのコンポーネントとの相互運用が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f80c0-172">Some exceptions includes interoperating with native components, where underscores are very common.</span></span>

### <a name="use-standard-f-operators"></a><span data-ttu-id="f80c0-173">標準的な F# 演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="f80c0-173">Use standard F# operators</span></span>

<span data-ttu-id="f80c0-174">次の演算子は、F# の標準ライブラリで定義され、対応を定義する代わりに使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f80c0-174">The following operators are defined in the F# standard library and should be used instead of defining equivalents.</span></span> <span data-ttu-id="f80c0-175">読みやすく、慣用コードを作成する傾向が、これらの演算子の使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f80c0-175">Using these operators is recommended as it tends to make code more readable and idiomatic.</span></span> <span data-ttu-id="f80c0-176">OCaml またはその他の関数型プログラミング言語の背景を持つ開発者は、さまざまな表現方法に慣れて可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f80c0-176">Developers with a background in OCaml or other functional programming language may be accustomed to different idioms.</span></span> <span data-ttu-id="f80c0-177">次の一覧は、推奨の F# 演算子をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="f80c0-177">The following list summarizes the recommended F# operators.</span></span>

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

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a><span data-ttu-id="f80c0-178">ジェネリックのプレフィックスの構文を使用して (`Foo<T>`) 方が優先的後置構文 (`T Foo`)</span><span class="sxs-lookup"><span data-stu-id="f80c0-178">Use prefix syntax for generics (`Foo<T>`) in preference to postfix syntax (`T Foo`)</span></span>

<span data-ttu-id="f80c0-179">F#ジェネリック型の名前付けの両方、後置 ML スタイルを継承 (たとえば、 `int list`) .NET スタイルのプレフィックスと (たとえば、 `list<int>`)。</span><span class="sxs-lookup"><span data-stu-id="f80c0-179">F# inherits both the postfix ML style of naming generic types (for example, `int list`) as well as the prefix .NET style (for example, `list<int>`).</span></span> <span data-ttu-id="f80c0-180">次の 4 つの特定の型を除く、.NET スタイルを優先するには。</span><span class="sxs-lookup"><span data-stu-id="f80c0-180">Prefer the .NET style, except for four specific types:</span></span>

1. <span data-ttu-id="f80c0-181">F#後置形式を使用して、リスト、:`int list`なく`list<int>`します。</span><span class="sxs-lookup"><span data-stu-id="f80c0-181">For F# Lists, use the postfix form: `int list` rather than `list<int>`.</span></span>
2. <span data-ttu-id="f80c0-182">F#オプションを使用して、後置形式:`int option`なく`option<int>`します。</span><span class="sxs-lookup"><span data-stu-id="f80c0-182">For F# Options, use the postfix form: `int option` rather than `option<int>`.</span></span>
3. <span data-ttu-id="f80c0-183">F#構文の名前を使用して、配列、`int[]`なく`int array`または`array<int>`します。</span><span class="sxs-lookup"><span data-stu-id="f80c0-183">For F# arrays, use the syntactic name `int[]` rather than `int array` or `array<int>`.</span></span>
4. <span data-ttu-id="f80c0-184">参照セルを使用して`int ref`なく`ref<int>`または`Ref<int>`します。</span><span class="sxs-lookup"><span data-stu-id="f80c0-184">For Reference Cells, use `int ref` rather than `ref<int>` or `Ref<int>`.</span></span>

<span data-ttu-id="f80c0-185">他のすべての種類では、前置形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="f80c0-185">For all other types, use the prefix form.</span></span>

## <a name="formatting-tuples"></a><span data-ttu-id="f80c0-186">タプルの書式設定</span><span class="sxs-lookup"><span data-stu-id="f80c0-186">Formatting tuples</span></span>

<span data-ttu-id="f80c0-187">タプル インスタンス化はかっこで囲まれた、する必要があり、内で使用する区切りコンマをたとえば、1 つのスペースで従う必要が: `(1, 2)`、`(x, y, z)`します。</span><span class="sxs-lookup"><span data-stu-id="f80c0-187">A tuple instantiation should be parenthesized, and the delimiting commas within should be followed by a single space, for example: `(1, 2)`, `(x, y, z)`.</span></span>

<span data-ttu-id="f80c0-188">タプルのパターン マッチングでは、かっこを省略することがよく受け入れられます。</span><span class="sxs-lookup"><span data-stu-id="f80c0-188">It is commonly accepted to omit parentheses in pattern matching of tuples:</span></span>

```fsharp
let (x, y) = z // Destructuring
let x, y = z // OK

// OK
match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

<span data-ttu-id="f80c0-189">タプルが関数の戻り値の場合は、かっこを省略することもよく受け入れられます。</span><span class="sxs-lookup"><span data-stu-id="f80c0-189">It is also commonly accepted to omit parentheses if the tuple is the return value of a function:</span></span>

```fsharp
// OK
let update model msg =
    match msg with
    | 1 -> model + 1, []
    | _ -> model, [ msg ]
```

<span data-ttu-id="f80c0-190">要約すると、かっこで囲まれたタプルのインスタンス化、必要に応じてをパターンに一致するか、戻り値のタプルを使用する場合と見なされるかっこを回避するために問題ありません。</span><span class="sxs-lookup"><span data-stu-id="f80c0-190">In summary, prefer parenthesized tuple instantiations, but when using tuples for pattern matching or a return value, it is considered fine to avoid parentheses.</span></span>

## <a name="formatting-discriminated-union-declarations"></a><span data-ttu-id="f80c0-191">判別共用体の宣言の書式設定</span><span class="sxs-lookup"><span data-stu-id="f80c0-191">Formatting discriminated union declarations</span></span>

<span data-ttu-id="f80c0-192">インデント`|`によって 4 つのスペースの種類の定義。</span><span class="sxs-lookup"><span data-stu-id="f80c0-192">Indent `|` in type definition by 4 spaces:</span></span>

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

## <a name="formatting-discriminated-unions"></a><span data-ttu-id="f80c0-193">判別共用体の書式設定</span><span class="sxs-lookup"><span data-stu-id="f80c0-193">Formatting discriminated unions</span></span>

<span data-ttu-id="f80c0-194">複数行にわたって判別の共用体はインスタンス化されたはインデントで新しいスコープに含まれているデータを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f80c0-194">Instantiated Discriminated Unions that split across multiple lines should give contained data a new scope with indentation:</span></span>

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

<span data-ttu-id="f80c0-195">新しい行の終わりかっこのこともできます。</span><span class="sxs-lookup"><span data-stu-id="f80c0-195">The closing parenthesis can also be on a new line:</span></span>

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-record-declarations"></a><span data-ttu-id="f80c0-196">レコードの宣言を書式設定</span><span class="sxs-lookup"><span data-stu-id="f80c0-196">Formatting record declarations</span></span>

<span data-ttu-id="f80c0-197">インデント`{`4 で定義型で空白し、同じ行にフィールド リストの先頭します。</span><span class="sxs-lookup"><span data-stu-id="f80c0-197">Indent `{` in type definition by 4 spaces and start the field list on the same line:</span></span>

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

<span data-ttu-id="f80c0-198">開始トークンを配置する、新しい行で、新しい行に終了トークンは、レコードのメンバー、またはインターフェイスの実装を宣言する場合に推奨されます。</span><span class="sxs-lookup"><span data-stu-id="f80c0-198">Placing the opening token on a new line and the closing token on a new line is preferable if you are declaring interface implementations or members on the record:</span></span>

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

## <a name="formatting-records"></a><span data-ttu-id="f80c0-199">レコードを書式設定</span><span class="sxs-lookup"><span data-stu-id="f80c0-199">Formatting records</span></span>

<span data-ttu-id="f80c0-200">1 行では、短いレコードを記述することができます。</span><span class="sxs-lookup"><span data-stu-id="f80c0-200">Short records can be written in one line:</span></span>

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

<span data-ttu-id="f80c0-201">長いレコードは、新しい行を使用して、ラベルの必要があります。</span><span class="sxs-lookup"><span data-stu-id="f80c0-201">Records that are longer should use new lines for labels:</span></span>

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

<span data-ttu-id="f80c0-202">開始を配置して、タブ付きトークンを新しい行に、内容、1 つのスコープ、新しい行に終了トークンがいる場合に適しています。</span><span class="sxs-lookup"><span data-stu-id="f80c0-202">Placing the opening token on a new line, the contents tabbed over one scope, and the closing token on a new line is preferable if you are:</span></span>

* <span data-ttu-id="f80c0-203">インデントの異なるスコープを使用したコード内でレコードを移動します。</span><span class="sxs-lookup"><span data-stu-id="f80c0-203">Moving records around in code with different indentation scopes</span></span>
* <span data-ttu-id="f80c0-204">関数にパイプすること</span><span class="sxs-lookup"><span data-stu-id="f80c0-204">Piping them into a function</span></span>

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

<span data-ttu-id="f80c0-205">リストと配列の要素の場合と同じ規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="f80c0-205">The same rules apply for list and array elements.</span></span>

## <a name="formatting-copy-and-update-record-expressions"></a><span data-ttu-id="f80c0-206">レコードのコピーと更新の式を書式設定</span><span class="sxs-lookup"><span data-stu-id="f80c0-206">Formatting copy-and-update record expressions</span></span>

<span data-ttu-id="f80c0-207">レコードのコピーと更新式はまだ、レコードのようなガイドラインが適用されます。</span><span class="sxs-lookup"><span data-stu-id="f80c0-207">A copy-and-update record expression is still a record, so similar guidelines apply.</span></span>

<span data-ttu-id="f80c0-208">短い式は、1 行に収めることができます。</span><span class="sxs-lookup"><span data-stu-id="f80c0-208">Short expressions can fit on one line:</span></span>

```fsharp
let point2 = { point with X = 1; Y = 2 }
```

<span data-ttu-id="f80c0-209">長い式では、新しい行を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f80c0-209">Longer expressions should use new lines:</span></span>

```fsharp
let rainbow2 =
    { rainbow with
        Boss = "Jeffrey"
        Lackeys = ["Zippy"; "George"; "Bungle"] }
```

<span data-ttu-id="f80c0-210">として、レコードのガイダンスとすることも、中かっこの別々 の行を割り当てるし、式の右側に 1 つのスコープにインデントを設定します。</span><span class="sxs-lookup"><span data-stu-id="f80c0-210">And as with the record guidance, you may want to dedicate separate lines for the braces and indent one scope to the right with the expression.</span></span> <span data-ttu-id="f80c0-211">でかっこがない場合、オプションの値をラッピングなどのいくつかの特殊なケースでする必要があります 1 行に中かっこを保持することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f80c0-211">Note that in some special cases, such as wrapping a value with an optional without parentheses, you may need to keep a brace on one line:</span></span>

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

## <a name="formatting-lists-and-arrays"></a><span data-ttu-id="f80c0-212">書式設定のリストと配列</span><span class="sxs-lookup"><span data-stu-id="f80c0-212">Formatting lists and arrays</span></span>

<span data-ttu-id="f80c0-213">書き込み`x :: l`の前後のスペースで、`::`演算子 (`::`が空白で囲まれたため、挿入演算子)。</span><span class="sxs-lookup"><span data-stu-id="f80c0-213">Write `x :: l` with spaces around the `::` operator (`::` is an infix operator, hence surrounded by spaces).</span></span>

<span data-ttu-id="f80c0-214">リストと 1 つの行で宣言された配列は、角かっこと終わりかっこの前にスペースを入れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f80c0-214">List and arrays declared on a single line should have a space after the opening bracket and before the closing bracket:</span></span>

```fsharp
let xs = [ 1; 2; 3 ]
let ys = [| 1; 2; 3; |]
```

<span data-ttu-id="f80c0-215">常に 2 つの個別の中かっこのような演算子の間に少なくとも 1 つの領域を使用します。</span><span class="sxs-lookup"><span data-stu-id="f80c0-215">Always use at least one space between two distinct brace-like operators.</span></span> <span data-ttu-id="f80c0-216">たとえば、間に空白のままに、`[`と`{`します。</span><span class="sxs-lookup"><span data-stu-id="f80c0-216">For example, leave a space between a `[` and a `{`.</span></span>

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

<span data-ttu-id="f80c0-217">リストまたは組の配列と同じガイドラインが適用されます。</span><span class="sxs-lookup"><span data-stu-id="f80c0-217">The same guideline applies for lists or arrays of tuples.</span></span>

<span data-ttu-id="f80c0-218">リストと複数行にわたって配列は、同様のルール、レコードと同様に従います。</span><span class="sxs-lookup"><span data-stu-id="f80c0-218">Lists and arrays that split across multiple lines follow a similar rule as records do:</span></span>

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

<span data-ttu-id="f80c0-219">レコードと同様、独自の行の開始タグと終了の角かっこを宣言することは簡単に移動コードと関数にパイプします。</span><span class="sxs-lookup"><span data-stu-id="f80c0-219">And as with records, declaring the opening and closing brackets on their own line will make moving code around and piping into functions easier.</span></span>

## <a name="formatting-if-expressions"></a><span data-ttu-id="f80c0-220">書式設定の if 式</span><span class="sxs-lookup"><span data-stu-id="f80c0-220">Formatting if expressions</span></span>

<span data-ttu-id="f80c0-221">条件文のインデントは、それらを構成する式のサイズによって異なります。</span><span class="sxs-lookup"><span data-stu-id="f80c0-221">Indentation of conditionals depends on the sizes of the expressions that make them up.</span></span> <span data-ttu-id="f80c0-222">場合`cond`、`e1`と`e2`短く、単純に 1 行に書き込むには。</span><span class="sxs-lookup"><span data-stu-id="f80c0-222">If `cond`, `e1` and `e2` are short, simply write them on one line:</span></span>

```fsharp
if cond then e1 else e2
```

<span data-ttu-id="f80c0-223">いずれか`cond`、`e1`または`e2`は長くなりますが、複数行にありません。</span><span class="sxs-lookup"><span data-stu-id="f80c0-223">If either `cond`, `e1` or `e2` are longer, but not multi-line:</span></span>

```fsharp
if cond
then e1
else e2
```

<span data-ttu-id="f80c0-224">複数行の式のいずれかの場合。</span><span class="sxs-lookup"><span data-stu-id="f80c0-224">If any of the expressions are multi-line:</span></span>

```fsharp
if cond then
    e1
else
    e2
```

<span data-ttu-id="f80c0-225">複数の条件で`elif`と`else`と同じスコープでインデントは、 `if`:</span><span class="sxs-lookup"><span data-stu-id="f80c0-225">Multiple conditionals with `elif` and `else` are indented at the same scope as the `if`:</span></span>

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a><span data-ttu-id="f80c0-226">パターン マッチング</span><span class="sxs-lookup"><span data-stu-id="f80c0-226">Pattern matching constructs</span></span>

<span data-ttu-id="f80c0-227">使用して、`|`インデントなしの一致の各句。</span><span class="sxs-lookup"><span data-stu-id="f80c0-227">Use a `|` for each clause of a match with no indentation.</span></span> <span data-ttu-id="f80c0-228">式が短い場合は、各部分式が単純でもある場合は、1 行を使用を検討できます。</span><span class="sxs-lookup"><span data-stu-id="f80c0-228">If the expression is short, you can consider using a single line if each subexpression is also simple.</span></span>

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

<span data-ttu-id="f80c0-229">パターン マッチングの矢印の右側の式が大きすぎる場合は、次の行のインデントが設定された 1 つの手順に移動、 `match` /`|`します。</span><span class="sxs-lookup"><span data-stu-id="f80c0-229">If the expression on the right of the pattern matching arrow is too large, move it to the following line, indented one step from the `match`/`|`.</span></span>

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

<span data-ttu-id="f80c0-230">パターン マッチングして以降、匿名関数の`function`、遠すぎていないインデントする必要があります一般にします。</span><span class="sxs-lookup"><span data-stu-id="f80c0-230">Pattern matching of anonymous functions, starting by `function`, should generally not indent too far.</span></span> <span data-ttu-id="f80c0-231">たとえば、次のように 1 つのスコープをインデントも可能です。</span><span class="sxs-lookup"><span data-stu-id="f80c0-231">For example, indenting one scope as follows is fine:</span></span>

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

<span data-ttu-id="f80c0-232">パターン マッチングで定義されている関数に`let`または`let rec`の開始後にインデントが設定された 4 つのスペースにする必要があります`let`場合でも、`function`キーワードの使用します。</span><span class="sxs-lookup"><span data-stu-id="f80c0-232">Pattern matching in functions defined by `let` or `let rec` should be indented 4 spaces after starting of `let`, even if `function` keyword is used:</span></span>

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

<span data-ttu-id="f80c0-233">矢印の整列はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="f80c0-233">We do not recommend aligning arrows.</span></span>

## <a name="formatting-trywith-expressions"></a><span data-ttu-id="f80c0-234">書式設定してみてください/式を</span><span class="sxs-lookup"><span data-stu-id="f80c0-234">Formatting try/with expressions</span></span>

<span data-ttu-id="f80c0-235">例外の種類に一致するパターンと同じレベルでインデントする`with`します。</span><span class="sxs-lookup"><span data-stu-id="f80c0-235">Pattern matching on the exception type should be indented at the same level as `with`.</span></span>

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

## <a name="formatting-function-parameter-application"></a><span data-ttu-id="f80c0-236">関数パラメーターのアプリケーションを書式設定</span><span class="sxs-lookup"><span data-stu-id="f80c0-236">Formatting function parameter application</span></span>

<span data-ttu-id="f80c0-237">一般に、関数パラメーターのほとんどのアプリケーションは、同じ行に行われます。</span><span class="sxs-lookup"><span data-stu-id="f80c0-237">In general, most function parameter application is done on the same line.</span></span>

<span data-ttu-id="f80c0-238">新しい行に関数にパラメーターを適用する場合は、1 つのスコープでインデントします。</span><span class="sxs-lookup"><span data-stu-id="f80c0-238">If you wish to apply parameters to a function on a new line, indent them by one scope.</span></span>

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

<span data-ttu-id="f80c0-239">関数の引数としてラムダ式と同じガイドラインが適用されます。</span><span class="sxs-lookup"><span data-stu-id="f80c0-239">The same guidelines apply for lambda expressions as function arguments.</span></span> <span data-ttu-id="f80c0-240">ラムダ式の本体の本文には別の行を設定できる場合は、1 つのスコープでインデント</span><span class="sxs-lookup"><span data-stu-id="f80c0-240">If the body of a lambda expression, the body can have another line, indented by one scope</span></span>

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

<span data-ttu-id="f80c0-241">ただし、ラムダ式の本体が 1 つ以上の行の場合は、別の関数にファクタリング アウトを検討してくださいではなく 1 つの引数として関数に適用される複数行の構築します。</span><span class="sxs-lookup"><span data-stu-id="f80c0-241">However, if the body of a lambda expression is more than one line, consider factoring it out into a separate function rather than have a multi-line construct applied as a single argument to a function.</span></span>

### <a name="formatting-infix-operators"></a><span data-ttu-id="f80c0-242">挿入演算子を書式設定</span><span class="sxs-lookup"><span data-stu-id="f80c0-242">Formatting infix operators</span></span>

<span data-ttu-id="f80c0-243">スペースで別の演算子。</span><span class="sxs-lookup"><span data-stu-id="f80c0-243">Separate operators by spaces.</span></span> <span data-ttu-id="f80c0-244">このルールの明確な例外は、`!`と`.`演算子。</span><span class="sxs-lookup"><span data-stu-id="f80c0-244">Obvious exceptions to this rule are the `!` and `.` operators.</span></span>

<span data-ttu-id="f80c0-245">挿入辞の式では、[ok] を同じ列に編成します。</span><span class="sxs-lookup"><span data-stu-id="f80c0-245">Infix expressions are OK to lineup on same column:</span></span>

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a><span data-ttu-id="f80c0-246">パイプライン演算子を書式設定</span><span class="sxs-lookup"><span data-stu-id="f80c0-246">Formatting pipeline operators</span></span>

<span data-ttu-id="f80c0-247">パイプライン`|>`演算子は、上で動作する式の下に移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f80c0-247">Pipeline `|>` operators should go underneath the expressions they operate on.</span></span>

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

### <a name="formatting-modules"></a><span data-ttu-id="f80c0-248">モジュールの書式設定</span><span class="sxs-lookup"><span data-stu-id="f80c0-248">Formatting modules</span></span>

<span data-ttu-id="f80c0-249">モジュールの基準としたローカル モジュール内のコードのインデントを設定する必要がありますが、最上位レベルのモジュール内のコードはインデントされませんする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f80c0-249">Code in a local module must be indented relative to the module, but code in a top-level module should not be indented.</span></span> <span data-ttu-id="f80c0-250">Namespace 要素は、インデントを設定するのにはありません。</span><span class="sxs-lookup"><span data-stu-id="f80c0-250">Namespace elements do not have to be indented.</span></span>

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

### <a name="formatting-object-expressions-and-interfaces"></a><span data-ttu-id="f80c0-251">オブジェクトの式とインターフェイスの書式設定</span><span class="sxs-lookup"><span data-stu-id="f80c0-251">Formatting object expressions and interfaces</span></span>

<span data-ttu-id="f80c0-252">同じ方法では、オブジェクトの式とインターフェイスを配置する必要があります`member`される 4 つのスペース後の分だけインデントされます。</span><span class="sxs-lookup"><span data-stu-id="f80c0-252">Object expressions and interfaces should be aligned in the same way with `member` being indented after 4 spaces.</span></span>

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s: String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-white-space-in-expressions"></a><span data-ttu-id="f80c0-253">式内の空白の書式設定</span><span class="sxs-lookup"><span data-stu-id="f80c0-253">Formatting white space in expressions</span></span>

<span data-ttu-id="f80c0-254">余分な空白文字を避けるためF#式。</span><span class="sxs-lookup"><span data-stu-id="f80c0-254">Avoid extraneous white space in F# expressions.</span></span>

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

<span data-ttu-id="f80c0-255">名前付き引数も必要はありません領域を囲む、 `=`:</span><span class="sxs-lookup"><span data-stu-id="f80c0-255">Named arguments should also not have space surrounding the `=`:</span></span>

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```

## <a name="formatting-attributes"></a><span data-ttu-id="f80c0-256">属性の書式設定</span><span class="sxs-lookup"><span data-stu-id="f80c0-256">Formatting attributes</span></span>

<span data-ttu-id="f80c0-257">[属性](../language-reference/attributes.md)コンス トラクターを上に配置されます。</span><span class="sxs-lookup"><span data-stu-id="f80c0-257">[Attributes](../language-reference/attributes.md) are placed above a construct:</span></span>

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

### <a name="formatting-attributes-on-parameters"></a><span data-ttu-id="f80c0-258">パラメーターに属性を書式設定</span><span class="sxs-lookup"><span data-stu-id="f80c0-258">Formatting attributes on parameters</span></span>

<span data-ttu-id="f80c0-259">属性は、パラメーターの場所をこともできます。</span><span class="sxs-lookup"><span data-stu-id="f80c0-259">Attributes can also be places on parameters.</span></span> <span data-ttu-id="f80c0-260">ここでは、名の前に、パラメーターとして同じ行にし、配置します。</span><span class="sxs-lookup"><span data-stu-id="f80c0-260">In this case, place then on the same line as the parameter and before the name:</span></span>

```fsharp
// Defines a class that takes an optional value as input defaulting to false.
type C() =
    member __.M([<Optional; DefaultParameterValue(false)>] doSomething: bool)
```

### <a name="formatting-multiple-attributes"></a><span data-ttu-id="f80c0-261">複数の属性を書式設定</span><span class="sxs-lookup"><span data-stu-id="f80c0-261">Formatting multiple attributes</span></span>

<span data-ttu-id="f80c0-262">パラメーターではないコンストラクトに適用されると、複数の属性は、1 行につき 1 つの属性が存在するようなに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f80c0-262">When multiple attributes are applied to a construct that is not a parameter, they should be placed such that there is one attribute per line:</span></span>

```fsharp
[<Struct>]
[<IsByRefLike>]
type MyRecord =
    { Label1: int
      Label2: string }
```

<span data-ttu-id="f80c0-263">同じ行に配置する必要がありで区切られた、パラメーターに適用するときに、`;`区切り記号。</span><span class="sxs-lookup"><span data-stu-id="f80c0-263">When applied to a parameter, they must be on the same line and separated by a `;` separator.</span></span>

## <a name="formatting-literals"></a><span data-ttu-id="f80c0-264">書式設定リテラル</span><span class="sxs-lookup"><span data-stu-id="f80c0-264">Formatting literals</span></span>

<span data-ttu-id="f80c0-265">[F#リテラル](../language-reference/literals.md)を使用して、`Literal`属性が独自の行に属性を配置し、camelCase 名前付けを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f80c0-265">[F# literals](../language-reference/literals.md) using the `Literal` attribute should place the attribute on its own line and use camelCase naming:</span></span>

```fsharp
[<Literal>]
let path = __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let myUrl = "www.mywebsitethatiamworkingwith.com"
```

<span data-ttu-id="f80c0-266">属性値と同じ行を配置しないでください。</span><span class="sxs-lookup"><span data-stu-id="f80c0-266">Avoid placing the attribute on the same line as the value.</span></span>
