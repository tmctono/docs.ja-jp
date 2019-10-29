---
title: パターン マッチ
description: でF#パターンを使用して、データを論理構造と比較したり、データを構成要素に分解したり、データから情報を抽出したりする方法について説明します。
ms.date: 10/27/2019
ms.openlocfilehash: 1acb795cbe5581898ae5e1439098f906a8a16b93
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2019
ms.locfileid: "73041010"
---
# <a name="pattern-matching"></a><span data-ttu-id="d8697-103">パターン マッチ</span><span class="sxs-lookup"><span data-stu-id="d8697-103">Pattern Matching</span></span>

<span data-ttu-id="d8697-104">パターンは、入力データの変換規則です。</span><span class="sxs-lookup"><span data-stu-id="d8697-104">Patterns are rules for transforming input data.</span></span> <span data-ttu-id="d8697-105">データを論理構造と比較したり、データを構成要素に分解したり、さまざまな方法でデータから情報を抽出したりするために、F# 言語全体で使用されます。</span><span class="sxs-lookup"><span data-stu-id="d8697-105">They are used throughout the F# language to compare data with a logical structure or structures, decompose data into constituent parts, or extract information from data in various ways.</span></span>

## <a name="remarks"></a><span data-ttu-id="d8697-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="d8697-106">Remarks</span></span>

<span data-ttu-id="d8697-107">パターンは、`match` 式などの多くの言語構成要素で使用されます。</span><span class="sxs-lookup"><span data-stu-id="d8697-107">Patterns are used in many language constructs, such as the `match` expression.</span></span> <span data-ttu-id="d8697-108">`let` 束縛、ラムダ式、および `try...with` 式に関連付けられている例外ハンドラーで関数の引数を処理する場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="d8697-108">They are used when you are processing arguments for functions in `let` bindings, lambda expressions, and in the exception handlers associated with the `try...with` expression.</span></span> <span data-ttu-id="d8697-109">詳細については、「 [Match 式](match-expressions.md)、 [let 束縛](./functions/let-bindings.md)、[ラムダ式: `fun` キーワード](./functions/lambda-expressions-the-fun-keyword.md)」、および「[例外: `try...with` 式](./exception-handling/the-try-with-expression.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8697-109">For more information, see [Match Expressions](match-expressions.md), [let Bindings](./functions/let-bindings.md), [Lambda Expressions: The `fun` Keyword](./functions/lambda-expressions-the-fun-keyword.md), and [Exceptions: The `try...with` Expression](./exception-handling/the-try-with-expression.md).</span></span>

<span data-ttu-id="d8697-110">たとえば、`match` 式では、*パターン*はパイプ記号の後になります。</span><span class="sxs-lookup"><span data-stu-id="d8697-110">For example, in the `match` expression, the *pattern* is what follows the pipe symbol.</span></span>

```fsharp
match expression with
| pattern [ when condition ] -> result-expression
...
```

<span data-ttu-id="d8697-111">各パターンは、なんらかの方法で入力を変換する際の規則として機能します。</span><span class="sxs-lookup"><span data-stu-id="d8697-111">Each pattern acts as a rule for transforming input in some way.</span></span> <span data-ttu-id="d8697-112">`match` 式では、各パターンが順に調べられ、入力データにパターンとの互換性があるかどうかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="d8697-112">In the `match` expression, each pattern is examined in turn to see if the input data is compatible with the pattern.</span></span> <span data-ttu-id="d8697-113">一致が見つかった場合は、結果の式が実行されます。</span><span class="sxs-lookup"><span data-stu-id="d8697-113">If a match is found, the result expression is executed.</span></span> <span data-ttu-id="d8697-114">一致が見つからなかった場合は、次のパターン規則がテストされます。</span><span class="sxs-lookup"><span data-stu-id="d8697-114">If a match is not found, the next pattern rule is tested.</span></span> <span data-ttu-id="d8697-115">*条件*部分が[一致式](match-expressions.md)で説明されている場合は、省略可能です。</span><span class="sxs-lookup"><span data-stu-id="d8697-115">The optional when *condition* part is explained in [Match Expressions](match-expressions.md).</span></span>

<span data-ttu-id="d8697-116">サポートされているパターンを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="d8697-116">Supported patterns are shown in the following table.</span></span> <span data-ttu-id="d8697-117">実行時に、表に示されている順序で次の各パターンに対して入力がテストされます。パターンは、コードに示されているとおりに先頭から末尾へ、各行のパターンの左から右へ、再帰的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d8697-117">At run time, the input is tested against each of the following patterns in the order listed in the table, and patterns are applied recursively, from first to last as they appear in your code, and from left to right for the patterns on each line.</span></span>

|<span data-ttu-id="d8697-118">名</span><span class="sxs-lookup"><span data-stu-id="d8697-118">Name</span></span>|<span data-ttu-id="d8697-119">説明</span><span class="sxs-lookup"><span data-stu-id="d8697-119">Description</span></span>|<span data-ttu-id="d8697-120">例</span><span class="sxs-lookup"><span data-stu-id="d8697-120">Example</span></span>|
|----|-----------|-------|
|<span data-ttu-id="d8697-121">定数パターン</span><span class="sxs-lookup"><span data-stu-id="d8697-121">Constant pattern</span></span>|<span data-ttu-id="d8697-122">数値、文字、リテラル文字列、列挙定数、または定義済みのリテラル識別子</span><span class="sxs-lookup"><span data-stu-id="d8697-122">Any numeric, character, or string literal, an enumeration constant, or a defined literal identifier</span></span>|<span data-ttu-id="d8697-123">`1.0`, `"test"`, `30`, `Color.Red`</span><span class="sxs-lookup"><span data-stu-id="d8697-123">`1.0`, `"test"`, `30`, `Color.Red`</span></span>|
|<span data-ttu-id="d8697-124">識別子パターン</span><span class="sxs-lookup"><span data-stu-id="d8697-124">Identifier pattern</span></span>|<span data-ttu-id="d8697-125">判別共用体のケース値、例外ラベル、またはアクティブ パターンのケース</span><span class="sxs-lookup"><span data-stu-id="d8697-125">A case value of a discriminated union, an exception label, or an active pattern case</span></span>|`Some(x)`<br /><br />`Failure(msg)`|
|<span data-ttu-id="d8697-126">変数パターン</span><span class="sxs-lookup"><span data-stu-id="d8697-126">Variable pattern</span></span>|<span data-ttu-id="d8697-127">*identifier*</span><span class="sxs-lookup"><span data-stu-id="d8697-127">*identifier*</span></span>|`a`|
|<span data-ttu-id="d8697-128">`as` パターン</span><span class="sxs-lookup"><span data-stu-id="d8697-128">`as` pattern</span></span>|<span data-ttu-id="d8697-129">*識別子*としての*パターン*</span><span class="sxs-lookup"><span data-stu-id="d8697-129">*pattern* as *identifier*</span></span>|`(a, b) as tuple1`|
|<span data-ttu-id="d8697-130">OR パターン</span><span class="sxs-lookup"><span data-stu-id="d8697-130">OR pattern</span></span>|<span data-ttu-id="d8697-131">*pattern1* &#124; *pattern2*</span><span class="sxs-lookup"><span data-stu-id="d8697-131">*pattern1* &#124; *pattern2*</span></span>|<code>([h] &#124; [h; _])</code>|
|<span data-ttu-id="d8697-132">AND パターン</span><span class="sxs-lookup"><span data-stu-id="d8697-132">AND pattern</span></span>|<span data-ttu-id="d8697-133">*pattern1* &amp; *pattern2*</span><span class="sxs-lookup"><span data-stu-id="d8697-133">*pattern1* &amp; *pattern2*</span></span>|`(a, b) & (_, "test")`|
|<span data-ttu-id="d8697-134">Cons パターン</span><span class="sxs-lookup"><span data-stu-id="d8697-134">Cons pattern</span></span>|<span data-ttu-id="d8697-135">*識別子*::*リスト-識別子*</span><span class="sxs-lookup"><span data-stu-id="d8697-135">*identifier* :: *list-identifier*</span></span>|`h :: t`|
|<span data-ttu-id="d8697-136">リスト パターン</span><span class="sxs-lookup"><span data-stu-id="d8697-136">List pattern</span></span>|<span data-ttu-id="d8697-137">[ *pattern_1*;...;*pattern_n* ]</span><span class="sxs-lookup"><span data-stu-id="d8697-137">[ *pattern_1*; ... ; *pattern_n* ]</span></span>|`[ a; b; c ]`|
|<span data-ttu-id="d8697-138">配列パターン</span><span class="sxs-lookup"><span data-stu-id="d8697-138">Array pattern</span></span>|<span data-ttu-id="d8697-139">[&#124; *pattern_1*;..;*pattern_n* &#124;]</span><span class="sxs-lookup"><span data-stu-id="d8697-139">[&#124; *pattern_1*; ..; *pattern_n* &#124;]</span></span>|<code>[&#124; a; b; c &#124;]</code>|
|<span data-ttu-id="d8697-140">かっこで囲まれたパターン</span><span class="sxs-lookup"><span data-stu-id="d8697-140">Parenthesized pattern</span></span>|<span data-ttu-id="d8697-141">(*パターン*)</span><span class="sxs-lookup"><span data-stu-id="d8697-141">( *pattern* )</span></span>|`( a )`|
|<span data-ttu-id="d8697-142">タプル パターン</span><span class="sxs-lookup"><span data-stu-id="d8697-142">Tuple pattern</span></span>|<span data-ttu-id="d8697-143">( *pattern_1*,..., *pattern_n* )</span><span class="sxs-lookup"><span data-stu-id="d8697-143">( *pattern_1*, ... , *pattern_n* )</span></span>|`( a, b )`|
|<span data-ttu-id="d8697-144">レコード パターン</span><span class="sxs-lookup"><span data-stu-id="d8697-144">Record pattern</span></span>|<span data-ttu-id="d8697-145">{ *identifier1* = *pattern_1*;...;*identifier_n* = *pattern_n* }</span><span class="sxs-lookup"><span data-stu-id="d8697-145">{ *identifier1* = *pattern_1*; ... ; *identifier_n* = *pattern_n* }</span></span>|`{ Name = name; }`|
|<span data-ttu-id="d8697-146">ワイルドカード パターン</span><span class="sxs-lookup"><span data-stu-id="d8697-146">Wildcard pattern</span></span>|<span data-ttu-id="d8697-147">_</span><span class="sxs-lookup"><span data-stu-id="d8697-147">_</span></span>|`_`|
|<span data-ttu-id="d8697-148">型の注釈が指定されたパターン</span><span class="sxs-lookup"><span data-stu-id="d8697-148">Pattern together with type annotation</span></span>|<span data-ttu-id="d8697-149">*pattern* :*型*</span><span class="sxs-lookup"><span data-stu-id="d8697-149">*pattern* : *type*</span></span>|`a : int`|
|<span data-ttu-id="d8697-150">型テスト パターン</span><span class="sxs-lookup"><span data-stu-id="d8697-150">Type test pattern</span></span>|<span data-ttu-id="d8697-151">:?</span><span class="sxs-lookup"><span data-stu-id="d8697-151">:?</span></span> <span data-ttu-id="d8697-152">*型*[as*識別子*]</span><span class="sxs-lookup"><span data-stu-id="d8697-152">*type* [ as *identifier* ]</span></span>|`:? System.DateTime as dt`|
|<span data-ttu-id="d8697-153">null パターン</span><span class="sxs-lookup"><span data-stu-id="d8697-153">Null pattern</span></span>|<span data-ttu-id="d8697-154">null</span><span class="sxs-lookup"><span data-stu-id="d8697-154">null</span></span>|`null`|

## <a name="constant-patterns"></a><span data-ttu-id="d8697-155">定数パターン</span><span class="sxs-lookup"><span data-stu-id="d8697-155">Constant Patterns</span></span>

<span data-ttu-id="d8697-156">定数パターンは、数値、文字、リテラル文字列、列挙定数 (列挙型名が含まれる) です。</span><span class="sxs-lookup"><span data-stu-id="d8697-156">Constant patterns are numeric, character, and string literals, enumeration constants (with the enumeration type name included).</span></span> <span data-ttu-id="d8697-157">定数パターンのみが含まれる `match` 式は、他の言語の case ステートメントと比較できます。</span><span class="sxs-lookup"><span data-stu-id="d8697-157">A `match` expression that has only constant patterns can be compared to a case statement in other languages.</span></span> <span data-ttu-id="d8697-158">入力がリテラル値と比較され、値が等しい場合にはパターンが一致します。</span><span class="sxs-lookup"><span data-stu-id="d8697-158">The input is compared with the literal value and the pattern matches if the values are equal.</span></span> <span data-ttu-id="d8697-159">リテラルの型に、入力の型との互換性があることが必要です。</span><span class="sxs-lookup"><span data-stu-id="d8697-159">The type of the literal must be compatible with the type of the input.</span></span>

<span data-ttu-id="d8697-160">リテラル パターンの使用例を次に示します。変数パターンと OR パターンも使用します。</span><span class="sxs-lookup"><span data-stu-id="d8697-160">The following example demonstrates the use of literal patterns, and also uses a variable pattern and an OR pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4801.fs)]

<span data-ttu-id="d8697-161">リテラル パターンにはこの他に、列挙定数に基づくパターンもあります。</span><span class="sxs-lookup"><span data-stu-id="d8697-161">Another example of a literal pattern is a pattern based on enumeration constants.</span></span> <span data-ttu-id="d8697-162">列挙定数を使用するときは、列挙型名を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8697-162">You must specify the enumeration type name when you use enumeration constants.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4802.fs)]

## <a name="identifier-patterns"></a><span data-ttu-id="d8697-163">識別子パターン</span><span class="sxs-lookup"><span data-stu-id="d8697-163">Identifier Patterns</span></span>

<span data-ttu-id="d8697-164">パターンが有効な識別子になる文字列の場合は、識別子の形式でパターンの照合方法が決まります。</span><span class="sxs-lookup"><span data-stu-id="d8697-164">If the pattern is a string of characters that forms a valid identifier, the form of the identifier determines how the pattern is matched.</span></span> <span data-ttu-id="d8697-165">識別子が 2 文字以上で、大文字で始まる場合は、コンパイラが識別子パターンとの照合を試みます。</span><span class="sxs-lookup"><span data-stu-id="d8697-165">If the identifier is longer than a single character and starts with an uppercase character, the compiler tries to make a match to the identifier pattern.</span></span> <span data-ttu-id="d8697-166">このパターンの識別子は、Literal 属性が指定された値、判別共用体のケース、例外識別子、またはアクティブ パターンのケースです。</span><span class="sxs-lookup"><span data-stu-id="d8697-166">The identifier for this pattern could be a value marked with the Literal attribute, a discriminated union case, an exception identifier, or an active pattern case.</span></span> <span data-ttu-id="d8697-167">一致する識別子が見つからない場合は、照合が失敗し、次のパターン規則の変数パターンが入力と比較されます。</span><span class="sxs-lookup"><span data-stu-id="d8697-167">If no matching identifier is found, the match fails and the next pattern rule, the variable pattern, is compared to the input.</span></span>

<span data-ttu-id="d8697-168">判別共用体パターンは、単純な名前付きケースであるか、値またはタプル (複数の値を含む) を含むかのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="d8697-168">Discriminated union patterns can be simple named cases or they can have a value, or a tuple containing multiple values.</span></span> <span data-ttu-id="d8697-169">値が存在する場合は、値の識別子を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8697-169">If there is a value, you must specify an identifier for the value.</span></span> <span data-ttu-id="d8697-170">タプルの場合は、タプルの各要素の識別子、または 1 つ以上の名前付きの共用体フィールドのフィールド名の識別子、を持つタプル パターンを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8697-170">In the case of a tuple, you must supply a tuple pattern with an identifier for each element of the tuple or an identifier with a field name for one or more named union fields.</span></span> <span data-ttu-id="d8697-171">例については、このセクションのコード例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8697-171">See the code examples in this section for examples.</span></span>

<span data-ttu-id="d8697-172">`option` 型は、`Some` と `None` の 2 つのケースを持つ判別共用体です。</span><span class="sxs-lookup"><span data-stu-id="d8697-172">The `option` type is a discriminated union that has two cases, `Some` and `None`.</span></span> <span data-ttu-id="d8697-173">一方のケース (`Some`) には値が含まれますが、もう一方のケース (`None`) は単なる名前付きケースです。</span><span class="sxs-lookup"><span data-stu-id="d8697-173">One case (`Some`) has a value, but the other (`None`) is just a named case.</span></span> <span data-ttu-id="d8697-174">したがって、`Some` には、`Some` ケースに関連付けられた値の変数が必要ですが、`None` は単体で使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8697-174">Therefore, `Some` needs to have a variable for the value associated with the `Some` case, but `None` must appear by itself.</span></span> <span data-ttu-id="d8697-175">次のコードでは、`var1` 変数に、`Some` ケースとの照合で取得された値が指定されます。</span><span class="sxs-lookup"><span data-stu-id="d8697-175">In the following code, the variable `var1` is given the value that is obtained by matching to the `Some` case.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4803.fs)]

<span data-ttu-id="d8697-176">次の例では、`PersonName` 判別共用体に、名前に使用できる形式を表す文字列および文字が混在しています。</span><span class="sxs-lookup"><span data-stu-id="d8697-176">In the following example, the `PersonName` discriminated union contains a mixture of strings and characters that represent possible forms of names.</span></span> <span data-ttu-id="d8697-177">判別共用体のケースは `FirstOnly`、`LastOnly`、および `FirstLast` です。</span><span class="sxs-lookup"><span data-stu-id="d8697-177">The cases of the discriminated union are `FirstOnly`, `LastOnly`, and `FirstLast`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4804.fs)]

<span data-ttu-id="d8697-178">名前付きフィールドがある判別共用体の場合、名前付きフィールドの値を抽出するために等号 (=) を使用します。</span><span class="sxs-lookup"><span data-stu-id="d8697-178">For discriminated unions that have named fields, you use the equals sign (=) to extract the value of a named field.</span></span> <span data-ttu-id="d8697-179">たとえば、次のような宣言を持つ判別共用体について検討します。</span><span class="sxs-lookup"><span data-stu-id="d8697-179">For example, consider a discriminated union with a declaration like the following.</span></span>

```fsharp
type Shape =
    | Rectangle of height : float * width : float
    | Circle of radius : float
```

<span data-ttu-id="d8697-180">次のようにパターン一致式の中で名前付きフィールドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d8697-180">You can use the named fields in a pattern matching expression as follows.</span></span>

```fsharp
let matchShape shape =
    match shape with
    | Rectangle(height = h) -> printfn "Rectangle with length %f" h
    | Circle(r) -> printfn "Circle with radius %f" r
```

<span data-ttu-id="d8697-181">前の例では、名前付きフィールドの使用は省略可能であり、したがって、`Circle(r)` と `Circle(radius = r)` は同じ結果になります。</span><span class="sxs-lookup"><span data-stu-id="d8697-181">The use of the named field is optional, so in the previous example, both `Circle(r)` and `Circle(radius = r)` have the same effect.</span></span>

<span data-ttu-id="d8697-182">複数のフィールドを指定する場合は、区切り記号としてセミコロン (;) を使用します。</span><span class="sxs-lookup"><span data-stu-id="d8697-182">When you specify multiple fields, use the semicolon (;) as a separator.</span></span>

```fsharp
match shape with
| Rectangle(height = h; width = w) -> printfn "Rectangle with height %f and width %f" h w
| _ -> ()
```

<span data-ttu-id="d8697-183">アクティブ パターンを使用すると、より複雑なカスタム パターン マッチを定義できます。</span><span class="sxs-lookup"><span data-stu-id="d8697-183">Active patterns enable you to define more complex custom pattern matching.</span></span> <span data-ttu-id="d8697-184">アクティブパターンの詳細については、「[アクティブパターン](active-patterns.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8697-184">For more information about active patterns, see [Active Patterns](active-patterns.md).</span></span>

<span data-ttu-id="d8697-185">識別子が例外であるケースは、例外ハンドラーのコンテキストのパターン マッチで使用されます。</span><span class="sxs-lookup"><span data-stu-id="d8697-185">The case in which the identifier is an exception is used in pattern matching in the context of exception handlers.</span></span> <span data-ttu-id="d8697-186">例外処理でのパターンマッチングの詳細については、「[例外: `try...with` 式](./exception-handling/the-try-with-expression.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8697-186">For information about pattern matching in exception handling, see [Exceptions: The `try...with` Expression](./exception-handling/the-try-with-expression.md).</span></span>

## <a name="variable-patterns"></a><span data-ttu-id="d8697-187">変数パターン</span><span class="sxs-lookup"><span data-stu-id="d8697-187">Variable Patterns</span></span>

<span data-ttu-id="d8697-188">変数パターンでは、照合される値が変数名に割り当てられ、その変数名を、`->` 記号の右側の実行式で使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d8697-188">The variable pattern assigns the value being matched to a variable name, which is then available for use in the execution expression to the right of the `->` symbol.</span></span> <span data-ttu-id="d8697-189">変数パターン単体はどの入力にも一致しますが、多くの場合、変数パターンはその他のパターン内で使用されます。このため、タプルや配列などのより複雑な構造体を変数に分解することが可能になります。</span><span class="sxs-lookup"><span data-stu-id="d8697-189">A variable pattern alone matches any input, but variable patterns often appear within other patterns, therefore enabling more complex structures such as tuples and arrays to be decomposed into variables.</span></span>

<span data-ttu-id="d8697-190">タプル パターン内で変数パターンを使用する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d8697-190">The following example demonstrates a variable pattern within a tuple pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4805.fs)]

## <a name="as-pattern"></a><span data-ttu-id="d8697-191">as パターン</span><span class="sxs-lookup"><span data-stu-id="d8697-191">as Pattern</span></span>

<span data-ttu-id="d8697-192">`as` パターンは、`as` 句が追加されたパターンです。</span><span class="sxs-lookup"><span data-stu-id="d8697-192">The `as` pattern is a pattern that has an `as` clause appended to it.</span></span> <span data-ttu-id="d8697-193">`as` 句は、照合する値を `match` 式の実行式で使用できる名前に束縛します。または、このパターンが `let` 束縛で使用される場合は、名前が束縛としてローカル スコープに追加されます。</span><span class="sxs-lookup"><span data-stu-id="d8697-193">The `as` clause binds the matched value to a name that can be used in the execution expression of a `match` expression, or, in the case where this pattern is used in a `let` binding, the name is added as a binding to the local scope.</span></span>

<span data-ttu-id="d8697-194">`as` パターンの使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d8697-194">The following example uses an `as` pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4806.fs)]

## <a name="or-pattern"></a><span data-ttu-id="d8697-195">OR パターン</span><span class="sxs-lookup"><span data-stu-id="d8697-195">OR Pattern</span></span>

<span data-ttu-id="d8697-196">OR パターンは、入力データが複数のパターンと一致する場合に、同じコードを結果として実行するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="d8697-196">The OR pattern is used when input data can match multiple patterns, and you want to execute the same code as a result.</span></span> <span data-ttu-id="d8697-197">OR パターンの両側の型に互換性があることが必要です。</span><span class="sxs-lookup"><span data-stu-id="d8697-197">The types of both sides of the OR pattern must be compatible.</span></span>

<span data-ttu-id="d8697-198">OR パターンの使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d8697-198">The following example demonstrates the OR pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4807.fs)]

## <a name="and-pattern"></a><span data-ttu-id="d8697-199">AND パターン</span><span class="sxs-lookup"><span data-stu-id="d8697-199">AND Pattern</span></span>

<span data-ttu-id="d8697-200">AND パターンでは、入力が 2 つのパターンと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8697-200">The AND pattern requires that the input match two patterns.</span></span> <span data-ttu-id="d8697-201">AND パターンの両側の型に互換性があることが必要です。</span><span class="sxs-lookup"><span data-stu-id="d8697-201">The types of both sides of the AND pattern must be compatible.</span></span>

<span data-ttu-id="d8697-202">次の例は、このトピックで後述する「[組パターン](https://msdn.microsoft.com/library/#tuple)」で示した `detectZeroTuple` に似ていますが、ここでは `var1` と `var2` の両方を and パターンを使用して値として取得します。</span><span class="sxs-lookup"><span data-stu-id="d8697-202">The following example is like `detectZeroTuple` shown in the [Tuple Pattern](https://msdn.microsoft.com/library/#tuple) section later in this topic, but here both `var1` and `var2` are obtained as values by using the AND pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4808.fs)]

## <a name="cons-pattern"></a><span data-ttu-id="d8697-203">Cons パターン</span><span class="sxs-lookup"><span data-stu-id="d8697-203">Cons Pattern</span></span>

<span data-ttu-id="d8697-204">欠点パターンは、リストを最初の要素、*先頭*、および残りの要素 (*末尾*) を含むリストに分解するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d8697-204">The cons pattern is used to decompose a list into the first element, the *head*, and a list that contains the remaining elements, the *tail*.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4809.fs)]

## <a name="list-pattern"></a><span data-ttu-id="d8697-205">リスト パターン</span><span class="sxs-lookup"><span data-stu-id="d8697-205">List Pattern</span></span>

<span data-ttu-id="d8697-206">リスト パターンでは、リストをいくつかの要素に分解できます。</span><span class="sxs-lookup"><span data-stu-id="d8697-206">The list pattern enables lists to be decomposed into a number of elements.</span></span> <span data-ttu-id="d8697-207">リスト パターン自体は、特定の数の要素を含むリストとだけ一致します。</span><span class="sxs-lookup"><span data-stu-id="d8697-207">The list pattern itself can match only lists of a specific number of elements.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4810.fs)]

## <a name="array-pattern"></a><span data-ttu-id="d8697-208">配列パターン</span><span class="sxs-lookup"><span data-stu-id="d8697-208">Array Pattern</span></span>

<span data-ttu-id="d8697-209">配列パターンはリスト パターンに似ており、特定の長さの配列を分解するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="d8697-209">The array pattern resembles the list pattern and can be used to decompose arrays of a specific length.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4811.fs)]

## <a name="parenthesized-pattern"></a><span data-ttu-id="d8697-210">かっこで囲まれたパターン</span><span class="sxs-lookup"><span data-stu-id="d8697-210">Parenthesized Pattern</span></span>

<span data-ttu-id="d8697-211">かっこでパターンを囲んで、目的の結合規則を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="d8697-211">Parentheses can be grouped around patterns to achieve the desired associativity.</span></span> <span data-ttu-id="d8697-212">次の例では、かっこを使用して、AND パターンと Cons パターンの間の結合規則を制御します。</span><span class="sxs-lookup"><span data-stu-id="d8697-212">In the following example, parentheses are used to control associativity between an AND pattern and a cons pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4812.fs)]

## <a name="tuple-pattern"></a><span data-ttu-id="d8697-213">タプル パターン</span><span class="sxs-lookup"><span data-stu-id="d8697-213">Tuple Pattern</span></span>

<span data-ttu-id="d8697-214">タプル パターンはタプル形式の入力と一致します。このパターンでは、タプル内の位置ごとにパターン マッチ変数を使用して、タプルを構成要素に分解できます。</span><span class="sxs-lookup"><span data-stu-id="d8697-214">The tuple pattern matches input in tuple form and enables the tuple to be decomposed into its constituent elements by using pattern matching variables for each position in the tuple.</span></span>

<span data-ttu-id="d8697-215">タプル パターンの使用例を次に示します。リテラル パターン、変数パターン、およびワイルドカード パターンも使用します。</span><span class="sxs-lookup"><span data-stu-id="d8697-215">The following example demonstrates the tuple pattern and also uses literal patterns, variable patterns, and the wildcard pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4813.fs)]

## <a name="record-pattern"></a><span data-ttu-id="d8697-216">レコード パターン</span><span class="sxs-lookup"><span data-stu-id="d8697-216">Record Pattern</span></span>

<span data-ttu-id="d8697-217">レコード パターンは、レコードを分解してフィールドの値を抽出するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d8697-217">The record pattern is used to decompose records to extract the values of fields.</span></span> <span data-ttu-id="d8697-218">パターンがレコードのすべてのフィールドを参照する必要はありません。省略されたフィールドは照合に使用されないため、抽出されません。</span><span class="sxs-lookup"><span data-stu-id="d8697-218">The pattern does not have to reference all fields of the record; any omitted fields just do not participate in matching and are not extracted.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4814.fs)]

## <a name="wildcard-pattern"></a><span data-ttu-id="d8697-219">ワイルドカード パターン</span><span class="sxs-lookup"><span data-stu-id="d8697-219">Wildcard Pattern</span></span>

<span data-ttu-id="d8697-220">ワイルドカード パターンは、アンダースコア (`_`) 文字で表され、変数パターンと同様にどの入力にも一致しますが、入力が変数に割り当てられるのではなく、破棄される点が異なります。</span><span class="sxs-lookup"><span data-stu-id="d8697-220">The wildcard pattern is represented by the underscore (`_`) character and matches any input, just like the variable pattern, except that the input is discarded instead of assigned to a variable.</span></span> <span data-ttu-id="d8697-221">多くの場合、ワイルドカード パターンは、その他のパターン内で `->` 記号の右側の式で不要な値のプレースホルダーとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="d8697-221">The wildcard pattern is often used within other patterns as a placeholder for values that are not needed in the expression to the right of the `->` symbol.</span></span> <span data-ttu-id="d8697-222">また、一致しなかった入力に対応するために、パターン リストの最後にワイルドカード パターンが使用されることもよくあります。</span><span class="sxs-lookup"><span data-stu-id="d8697-222">The wildcard pattern is also frequently used at the end of a list of patterns to match any unmatched input.</span></span> <span data-ttu-id="d8697-223">ワイルドカード パターンは、このトピックの多くのコード例で示されています。</span><span class="sxs-lookup"><span data-stu-id="d8697-223">The wildcard pattern is demonstrated in many code examples in this topic.</span></span> <span data-ttu-id="d8697-224">一例として、上記のコードを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8697-224">See the preceding code for one example.</span></span>

## <a name="patterns-that-have-type-annotations"></a><span data-ttu-id="d8697-225">型の注釈が付けられたパターン</span><span class="sxs-lookup"><span data-stu-id="d8697-225">Patterns That Have Type Annotations</span></span>

<span data-ttu-id="d8697-226">パターンには型の注釈を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="d8697-226">Patterns can have type annotations.</span></span> <span data-ttu-id="d8697-227">このコメントはその他の型の注釈と同様に動作し、その他の型の注釈と同様に推論を導きます。</span><span class="sxs-lookup"><span data-stu-id="d8697-227">These behave like other type annotations and guide inference like other type annotations.</span></span> <span data-ttu-id="d8697-228">パターンの型の注釈はかっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8697-228">Parentheses are required around type annotations in patterns.</span></span> <span data-ttu-id="d8697-229">型の注釈が付けられたパターンを次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="d8697-229">The following code shows a pattern that has a type annotation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4815.fs)]

## <a name="type-test-pattern"></a><span data-ttu-id="d8697-230">型テスト パターン</span><span class="sxs-lookup"><span data-stu-id="d8697-230">Type Test Pattern</span></span>

<span data-ttu-id="d8697-231">型テスト パターンは、入力を型と照合するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d8697-231">The type test pattern is used to match the input against a type.</span></span> <span data-ttu-id="d8697-232">入力型がパターンで指定された型と一致する場合、またはその型の派生型である場合は、一致と見なされます。</span><span class="sxs-lookup"><span data-stu-id="d8697-232">If the input type is a match to (or a derived type of) the type specified in the pattern, the match succeeds.</span></span>

<span data-ttu-id="d8697-233">型テスト パターンの使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d8697-233">The following example demonstrates the type test pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4816.fs)]

<span data-ttu-id="d8697-234">識別子が特定の派生型であるかどうかを確認するだけの場合は、次の例に示すように、パターンの `as identifier` 部分は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="d8697-234">If you're only checking if an identifier is of a particular derived type, you don't need the `as identifier` part of the pattern, as shown in the following example:</span></span>

```fsharp
type A() = class end
type B() = inherit A()
type C() = inherit A()

let m (a: A) =
    match a with
    | :? B -> printfn "It's a B"
    | :? C -> printfn "It's a C"
    | _ -> ()
```

## <a name="null-pattern"></a><span data-ttu-id="d8697-235">null パターン</span><span class="sxs-lookup"><span data-stu-id="d8697-235">Null Pattern</span></span>

<span data-ttu-id="d8697-236">null パターンは null 値と一致します。null 値は、null 値を許可する型を使用しているときに示される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d8697-236">The null pattern matches the null value that can appear when you are working with types that allow a null value.</span></span> <span data-ttu-id="d8697-237">Null パターンは、.NET Framework コードと相互運用する場合によく使用されます。</span><span class="sxs-lookup"><span data-stu-id="d8697-237">Null patterns are frequently used when interoperating with .NET Framework code.</span></span> <span data-ttu-id="d8697-238">たとえば、.NET API の戻り値が `match` 式への入力である場合が考えられます。</span><span class="sxs-lookup"><span data-stu-id="d8697-238">For example, the return value of a .NET API might be the input to a `match` expression.</span></span> <span data-ttu-id="d8697-239">プログラム フローは、戻り値が null であるかどうかと、戻り値のその他の特性に基づいて制御できます。</span><span class="sxs-lookup"><span data-stu-id="d8697-239">You can control program flow based on whether the return value is null, and also on other characteristics of the returned value.</span></span> <span data-ttu-id="d8697-240">null パターンを使用すると、null 値が残りのプログラムに反映されるのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="d8697-240">You can use the null pattern to prevent null values from propagating to the rest of your program.</span></span>

<span data-ttu-id="d8697-241">null パターンと変数パターンの使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d8697-241">The following example uses the null pattern and the variable pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4817.fs)]

## <a name="see-also"></a><span data-ttu-id="d8697-242">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8697-242">See also</span></span>

- [<span data-ttu-id="d8697-243">match 式</span><span class="sxs-lookup"><span data-stu-id="d8697-243">Match Expressions</span></span>](match-expressions.md)
- [<span data-ttu-id="d8697-244">アクティブ パターン</span><span class="sxs-lookup"><span data-stu-id="d8697-244">Active Patterns</span></span>](active-patterns.md)
- [<span data-ttu-id="d8697-245">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="d8697-245">F# Language Reference</span></span>](index.md)
