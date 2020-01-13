---
title: $ - 文字列補間 - C# リファレンス
description: 文字列補間では、従来の複合文字列の書式設定よりも読み取りやすく、便利な構文を書式指定文字列の出力に提供します。
ms.date: 09/02/2019
f1_keywords:
- $_CSharpKeyword
- $
helpviewer_keywords:
- $ special character [C#]
- string interpolation [C#]
- interpolated string [C#]
author: pkulikov
ms.openlocfilehash: b32bbbb0bd99878822d7ca5abdba80b46539846a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715077"
---
# <a name="---string-interpolation-c-reference"></a><span data-ttu-id="431cb-103">$ - 文字列補間 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="431cb-103">$ - string interpolation (C# reference)</span></span>

<span data-ttu-id="431cb-104">`$` 特殊文字は、リテラル文字列を*挿入文字列*として識別します。</span><span class="sxs-lookup"><span data-stu-id="431cb-104">The `$` special character identifies a string literal as an *interpolated string*.</span></span> <span data-ttu-id="431cb-105">挿入文字列は、*補間式*が含まれている可能性がある文字列リテラルです。</span><span class="sxs-lookup"><span data-stu-id="431cb-105">An interpolated string is a string literal that might contain *interpolation expressions*.</span></span> <span data-ttu-id="431cb-106">挿入文字列が結果の文字列に解決されると、補間式を含む項目は、式の結果の文字列表現によって置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="431cb-106">When an interpolated string is resolved to a result string, items with interpolation expressions are replaced by the string representations of the expression results.</span></span> <span data-ttu-id="431cb-107">この機能は、C# 6 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="431cb-107">This feature is available starting with C# 6.</span></span>

<span data-ttu-id="431cb-108">文字列補間では、[複合文字列の書式設定](../../../standard/base-types/composite-formatting.md)機能よりも読み取りやすく便利な構文を使用して書式指定された文字列を作成できます。</span><span class="sxs-lookup"><span data-stu-id="431cb-108">String interpolation provides a more readable and convenient syntax to create formatted strings than a [string composite formatting](../../../standard/base-types/composite-formatting.md) feature.</span></span> <span data-ttu-id="431cb-109">次の例では、両方の機能を使用して、同じ出力を生成します。</span><span class="sxs-lookup"><span data-stu-id="431cb-109">The following example uses both features to produce the same output:</span></span>

[!code-csharp-interactive[compare with composite formatting](~/samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#1)]

## <a name="structure-of-an-interpolated-string"></a><span data-ttu-id="431cb-110">挿入文字列の構造</span><span class="sxs-lookup"><span data-stu-id="431cb-110">Structure of an interpolated string</span></span>

<span data-ttu-id="431cb-111">文字列リテラルを挿入文字列として識別するため、先頭に `$` の記号を追加してください。</span><span class="sxs-lookup"><span data-stu-id="431cb-111">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span> <span data-ttu-id="431cb-112">`$` と文字列リテラルを開始する `"` の間に空白を入れることはできません。</span><span class="sxs-lookup"><span data-stu-id="431cb-112">You cannot have any white space between the `$` and the `"` that starts a string literal.</span></span>

<span data-ttu-id="431cb-113">補間式を含む項目の構造は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="431cb-113">The structure of an item with an interpolation expression is as follows:</span></span>

```csharp
{<interpolationExpression>[,<alignment>][:<formatString>]}
```

<span data-ttu-id="431cb-114">角かっこ内の要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="431cb-114">Elements in square brackets are optional.</span></span> <span data-ttu-id="431cb-115">次の表は、それぞれの要素の説明です。</span><span class="sxs-lookup"><span data-stu-id="431cb-115">The following table describes each element:</span></span>

|<span data-ttu-id="431cb-116">要素</span><span class="sxs-lookup"><span data-stu-id="431cb-116">Element</span></span>|<span data-ttu-id="431cb-117">説明</span><span class="sxs-lookup"><span data-stu-id="431cb-117">Description</span></span>|
|-------------|-----------------|
|`interpolationExpression`|<span data-ttu-id="431cb-118">書式設定される結果を生成する式です。</span><span class="sxs-lookup"><span data-stu-id="431cb-118">The expression that produces a result to be formatted.</span></span> <span data-ttu-id="431cb-119">`null` の文字列表記は <xref:System.String.Empty?displayProperty=nameWithType> です。</span><span class="sxs-lookup"><span data-stu-id="431cb-119">String representation of `null` is <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>|
|`alignment`|<span data-ttu-id="431cb-120">式の結果の文字列表現で、最小文字数を定義する値を持つ定数式です。</span><span class="sxs-lookup"><span data-stu-id="431cb-120">The constant expression whose value defines the minimum number of characters in the string representation of the expression result.</span></span> <span data-ttu-id="431cb-121">正の場合は、文字列表現は右揃えで配置され、負の場合は、左揃えで配置されます。</span><span class="sxs-lookup"><span data-stu-id="431cb-121">If positive, the string representation is right-aligned; if negative, it's left-aligned.</span></span> <span data-ttu-id="431cb-122">詳細については、「[Alignment コンポーネント](../../../standard/base-types/composite-formatting.md#alignment-component)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="431cb-122">For more information, see [Alignment Component](../../../standard/base-types/composite-formatting.md#alignment-component).</span></span>|
|`formatString`|<span data-ttu-id="431cb-123">式の結果の型によってサポートされる書式指定文字列です。</span><span class="sxs-lookup"><span data-stu-id="431cb-123">A format string that is supported by the type of the expression result.</span></span> <span data-ttu-id="431cb-124">詳細については、「[Format String コンポーネント](../../../standard/base-types/composite-formatting.md#format-string-component)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="431cb-124">For more information, see [Format String Component](../../../standard/base-types/composite-formatting.md#format-string-component).</span></span>|

<span data-ttu-id="431cb-125">次の例では、前述したオプションの書式設定コンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="431cb-125">The following example uses optional formatting components described above:</span></span>

[!code-csharp-interactive[specify alignment and format string](~/samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#2)]

## <a name="special-characters"></a><span data-ttu-id="431cb-126">特殊文字</span><span class="sxs-lookup"><span data-stu-id="431cb-126">Special characters</span></span>

<span data-ttu-id="431cb-127">挿入文字列で生成された文字列にかっこ "{" または "}" を含めるには、2 つのかっこ "{{" または "}}" を使用します。</span><span class="sxs-lookup"><span data-stu-id="431cb-127">To include a brace, "{" or "}", in the text produced by an interpolated string, use two braces, "{{" or "}}".</span></span> <span data-ttu-id="431cb-128">詳細については、「[エスケープ中かっこ ({})](../../../standard/base-types/composite-formatting.md#escaping-braces)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="431cb-128">For more information, see [Escaping Braces](../../../standard/base-types/composite-formatting.md#escaping-braces).</span></span>

<span data-ttu-id="431cb-129">コロン (":") が補間式の項目で特別な意味を持つときに、補間式で[条件演算子](../operators/conditional-operator.md)を使用するには、その式を丸かっこで囲みます。</span><span class="sxs-lookup"><span data-stu-id="431cb-129">As the colon (":") has special meaning in an interpolation expression item, in order to use a [conditional operator](../operators/conditional-operator.md) in an interpolation expression, enclose that expression in parentheses.</span></span>

<span data-ttu-id="431cb-130">次の例では、かっこを結果の文字列に含める方法、および補間式で条件演算子を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="431cb-130">The following example shows how to include a brace in a result string and how to use a conditional operator in an interpolation expression:</span></span>

[!code-csharp-interactive[example with ternary conditional operator](~/samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#3)]

<span data-ttu-id="431cb-131">verbatim 補間文字列は、`$` 文字で始まり、`@` 文字が続きます。</span><span class="sxs-lookup"><span data-stu-id="431cb-131">An interpolated verbatim string starts with the `$` character followed by the `@` character.</span></span> <span data-ttu-id="431cb-132">逐語的文字列の詳細については、[string](../builtin-types/reference-types.md) と [逐語的識別子](verbatim.md)に関するトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="431cb-132">For more information about verbatim strings, see the [string](../builtin-types/reference-types.md) and [verbatim identifier](verbatim.md) topics.</span></span>

> [!NOTE]
> <span data-ttu-id="431cb-133">C# 8.0 以降では、`$` と `@` のトークンを任意の順序で使用できます。`$@"..."` と `@$"..."` はどちらも有効な verbatim 補間文字列です。</span><span class="sxs-lookup"><span data-stu-id="431cb-133">Starting with C# 8.0, you can use the `$` and `@` tokens in any order: both `$@"..."` and `@$"..."` are valid interpolated verbatim strings.</span></span> <span data-ttu-id="431cb-134">以前のバージョンの C# では、`$` トークンは `@` トークンの前に記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="431cb-134">In earlier C# versions, the `$` token must appear before the `@` token.</span></span>

## <a name="implicit-conversions-and-how-to-specify-iformatprovider-implementation"></a><span data-ttu-id="431cb-135">暗黙的な変換と `IFormatProvider` 実装の指定方法</span><span class="sxs-lookup"><span data-stu-id="431cb-135">Implicit conversions and how to specify `IFormatProvider` implementation</span></span>

<span data-ttu-id="431cb-136">挿入文字列から暗黙の変換を行う方法は 3 種類あります。</span><span class="sxs-lookup"><span data-stu-id="431cb-136">There are three implicit conversions from an interpolated string:</span></span>

1. <span data-ttu-id="431cb-137">挿入文字列から <xref:System.String> インスタンスへの変換。これは、適切に書式設定された文字列表現の結果で置き換えられる、補間式の項目を含む挿入文字列分析の結果です。</span><span class="sxs-lookup"><span data-stu-id="431cb-137">Conversion of an interpolated string to a <xref:System.String> instance that is the result of interpolated string resolution with interpolation expression items being replaced with the properly formatted string representations of their results.</span></span> <span data-ttu-id="431cb-138">この変換では <xref:System.Globalization.CultureInfo.CurrentCulture> を使用して、式の結果の書式を設定します。</span><span class="sxs-lookup"><span data-stu-id="431cb-138">This conversion uses the <xref:System.Globalization.CultureInfo.CurrentCulture> to format expression results.</span></span>

1. <span data-ttu-id="431cb-139">書式設定される式の結果と、挿入文字列から複合書式指定文字列を表す <xref:System.FormattableString> インスタンスへの変換。</span><span class="sxs-lookup"><span data-stu-id="431cb-139">Conversion of an interpolated string to a <xref:System.FormattableString> instance that represents a composite format string along with the expression results to be formatted.</span></span> <span data-ttu-id="431cb-140">これは、単一の <xref:System.FormattableString> インスタンスから、カルチャ固有のコンテンツを持つ複数の結果文字列の作成を可能にするものです。</span><span class="sxs-lookup"><span data-stu-id="431cb-140">That allows you to create multiple result strings with culture-specific content from a single <xref:System.FormattableString> instance.</span></span> <span data-ttu-id="431cb-141">そのためには、次のいずれかのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="431cb-141">To do that, call one of the following methods:</span></span>

      - <span data-ttu-id="431cb-142"><xref:System.Globalization.CultureInfo.CurrentCulture> の結果文字列を生成する <xref:System.FormattableString.ToString> オーバーロード。</span><span class="sxs-lookup"><span data-stu-id="431cb-142">A <xref:System.FormattableString.ToString> overload that produces a result string for the <xref:System.Globalization.CultureInfo.CurrentCulture>.</span></span>
      - <span data-ttu-id="431cb-143"><xref:System.Globalization.CultureInfo.InvariantCulture> の結果文字列を生成する <xref:System.FormattableString.Invariant%2A> メソッド。</span><span class="sxs-lookup"><span data-stu-id="431cb-143">An <xref:System.FormattableString.Invariant%2A> method that produces a result string for the <xref:System.Globalization.CultureInfo.InvariantCulture>.</span></span>
      - <span data-ttu-id="431cb-144">特定のカルチャの結果文字列を生成する <xref:System.FormattableString.ToString(System.IFormatProvider)> メソッド。</span><span class="sxs-lookup"><span data-stu-id="431cb-144">A <xref:System.FormattableString.ToString(System.IFormatProvider)> method that produces a result string for a specified culture.</span></span>

    <span data-ttu-id="431cb-145"><xref:System.FormattableString.ToString(System.IFormatProvider)> メソッドを使用して、カスタム書式設定をサポートする <xref:System.IFormatProvider> インターフェイスのユーザー定義の実装を提供することもできます。</span><span class="sxs-lookup"><span data-stu-id="431cb-145">You also can use the <xref:System.FormattableString.ToString(System.IFormatProvider)> method to provide a user-defined implementation of the <xref:System.IFormatProvider> interface that supports custom formatting.</span></span> <span data-ttu-id="431cb-146">詳細については、「[ICustomFormatter を使用したカスタム書式設定](../../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter)」の「[.NET での書式設定](../../../standard/base-types/formatting-types.md)」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="431cb-146">For more information, see the [Custom formatting with ICustomFormatter](../../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter) section of the [Formatting types in .NET](../../../standard/base-types/formatting-types.md) article.</span></span>

1. <span data-ttu-id="431cb-147">挿入文字列から <xref:System.IFormattable> インスタンスへの変換。これは、単一の <xref:System.IFormattable> インスタンスから、カルチャ固有のコンテンツを持つ複数の結果文字列の作成も可能にするものです。</span><span class="sxs-lookup"><span data-stu-id="431cb-147">Conversion of an interpolated string to an <xref:System.IFormattable> instance that also allows you to create multiple result strings with culture-specific content from a single <xref:System.IFormattable> instance.</span></span>

<span data-ttu-id="431cb-148">次の例では、カルチャ固有の結果の文字列を作成するために、<xref:System.FormattableString> への暗黙の変換を使用します。</span><span class="sxs-lookup"><span data-stu-id="431cb-148">The following example uses implicit conversion to <xref:System.FormattableString> to create culture-specific result strings:</span></span>

[!code-csharp-interactive[create culture-specific result strings](~/samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#4)]

## <a name="additional-resources"></a><span data-ttu-id="431cb-149">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="431cb-149">Additional resources</span></span>

<span data-ttu-id="431cb-150">文字列補間を初めてお使いの場合は、[C# の文字列補完](../../tutorials/exploration/interpolated-strings.yml)に関する対話形式チュートリアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="431cb-150">If you are new to string interpolation, see the [String interpolation in C#](../../tutorials/exploration/interpolated-strings.yml) interactive tutorial.</span></span> <span data-ttu-id="431cb-151">また、補完された文字列を使用して書式設定された文字列を生成する方法を示したもう 1 つのチュートリアル「[C# における文字列補完](../../tutorials/string-interpolation.md)」も確認してください。</span><span class="sxs-lookup"><span data-stu-id="431cb-151">You also can check another [String interpolation in C#](../../tutorials/string-interpolation.md) tutorial that demonstrates how to use interpolated strings to produce formatted strings.</span></span>

## <a name="compilation-of-interpolated-strings"></a><span data-ttu-id="431cb-152">補完文字列のコンパイル</span><span class="sxs-lookup"><span data-stu-id="431cb-152">Compilation of interpolated strings</span></span>

<span data-ttu-id="431cb-153">補完文字列が `string` 型の場合、通常は <xref:System.String.Format%2A?displayProperty=nameWithType> メソッドの呼び出しに変換されます。</span><span class="sxs-lookup"><span data-stu-id="431cb-153">If an interpolated string has the type `string`, it's typically transformed into a <xref:System.String.Format%2A?displayProperty=nameWithType> method call.</span></span> <span data-ttu-id="431cb-154">分析後の動作が連結と等しくなるようであれば、コンパイラでは、<xref:System.String.Format%2A?displayProperty=nameWithType> を <xref:System.String.Concat%2A?displayProperty=nameWithType> に置換する場合があります。</span><span class="sxs-lookup"><span data-stu-id="431cb-154">The compiler may replace <xref:System.String.Format%2A?displayProperty=nameWithType> with <xref:System.String.Concat%2A?displayProperty=nameWithType> if the analyzed behavior would be equivalent to concatenation.</span></span>

<span data-ttu-id="431cb-155">補間文字列の型が <xref:System.IFormattable> または <xref:System.FormattableString> の場合、コンパイラは <xref:System.Runtime.CompilerServices.FormattableStringFactory.Create%2A?displayProperty=nameWithType> メソッドの呼び出しを生成します。</span><span class="sxs-lookup"><span data-stu-id="431cb-155">If an interpolated string has the type <xref:System.IFormattable> or <xref:System.FormattableString>, the compiler generates a call to the <xref:System.Runtime.CompilerServices.FormattableStringFactory.Create%2A?displayProperty=nameWithType> method.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="431cb-156">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="431cb-156">C# language specification</span></span>

<span data-ttu-id="431cb-157">詳しくは、[C# 言語仕様](~/_csharplang/spec/introduction.md)に関するページの[補完文字列](~/_csharplang/spec/expressions.md#interpolated-strings)のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="431cb-157">For more information, see the [Interpolated strings](~/_csharplang/spec/expressions.md#interpolated-strings) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="431cb-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="431cb-158">See also</span></span>

- [<span data-ttu-id="431cb-159">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="431cb-159">C# reference</span></span>](../index.md)
- [<span data-ttu-id="431cb-160">C# 特殊文字</span><span class="sxs-lookup"><span data-stu-id="431cb-160">C# special characters</span></span>](index.md)
- [<span data-ttu-id="431cb-161">文字列</span><span class="sxs-lookup"><span data-stu-id="431cb-161">Strings</span></span>](../../programming-guide/strings/index.md)
- [<span data-ttu-id="431cb-162">数値結果テーブルの書式設定</span><span class="sxs-lookup"><span data-stu-id="431cb-162">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="431cb-163">複合書式指定</span><span class="sxs-lookup"><span data-stu-id="431cb-163">Composite formatting</span></span>](../../../standard/base-types/composite-formatting.md)
- <xref:System.String.Format%2A?displayProperty=nameWithType>
