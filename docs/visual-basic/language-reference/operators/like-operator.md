---
title: Like 演算子
ms.date: 07/20/2015
f1_keywords:
- Like
- vb.Like
helpviewer_keywords:
- similar to
- pattern matching
- Like operator [Visual Basic]
- '? symbol, wildcard character'
- string comparison [Visual Basic], Like operator
- strings [Visual Basic], comparing
- comparison operators [Visual Basic]
- symbols, wildcard
- wildcards, Like operator
- strings [Visual Basic], matching
- string comparison [Visual Basic], sorting data
- data [Visual Basic], sorting
- text [Visual Basic], comparing
- operators [Visual Basic], pattern-matching
- data [Visual Basic], string comparisons
- string comparison [Visual Basic], Like operators
ms.assetid: 966283ec-80e2-4294-baa8-c75baff804f9
ms.openlocfilehash: 5db9488bbec716156a3ab464042c0853241a82b1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350946"
---
# <a name="like-operator-visual-basic"></a><span data-ttu-id="8fffd-102">Like 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8fffd-102">Like Operator (Visual Basic)</span></span>
<span data-ttu-id="8fffd-103">文字列をパターンと比較します。</span><span class="sxs-lookup"><span data-stu-id="8fffd-103">Compares a string against a pattern.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="8fffd-104">`Like` 演算子は、現在、.NET Core および .NET Standard プロジェクトではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8fffd-104">The `Like` operator is currently not supported in .NET Core and .NET Standard projects.</span></span>

## <a name="syntax"></a><span data-ttu-id="8fffd-105">構文</span><span class="sxs-lookup"><span data-stu-id="8fffd-105">Syntax</span></span>  
  
```vb  
result = string Like pattern  
```  
  
## <a name="parts"></a><span data-ttu-id="8fffd-106">指定項目</span><span class="sxs-lookup"><span data-stu-id="8fffd-106">Parts</span></span>  
 `result`  
 <span data-ttu-id="8fffd-107">必須。</span><span class="sxs-lookup"><span data-stu-id="8fffd-107">Required.</span></span> <span data-ttu-id="8fffd-108">任意の `Boolean` 変数。</span><span class="sxs-lookup"><span data-stu-id="8fffd-108">Any `Boolean` variable.</span></span> <span data-ttu-id="8fffd-109">結果は、`string` が `pattern`を満たすかどうかを示す `Boolean` 値です。</span><span class="sxs-lookup"><span data-stu-id="8fffd-109">The result is a `Boolean` value indicating whether or not the `string` satisfies the `pattern`.</span></span>  
  
 `string`  
 <span data-ttu-id="8fffd-110">必須。</span><span class="sxs-lookup"><span data-stu-id="8fffd-110">Required.</span></span> <span data-ttu-id="8fffd-111">任意のブール型 ( `String` ) の式を指定します。</span><span class="sxs-lookup"><span data-stu-id="8fffd-111">Any `String` expression.</span></span>  
  
 `pattern`  
 <span data-ttu-id="8fffd-112">必須。</span><span class="sxs-lookup"><span data-stu-id="8fffd-112">Required.</span></span> <span data-ttu-id="8fffd-113">「解説」で説明されているパターン一致規則に準拠した任意の `String` 式。</span><span class="sxs-lookup"><span data-stu-id="8fffd-113">Any `String` expression conforming to the pattern-matching conventions described in "Remarks."</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8fffd-114">コメント</span><span class="sxs-lookup"><span data-stu-id="8fffd-114">Remarks</span></span>  
 <span data-ttu-id="8fffd-115">`string` の値が `pattern`に含まれるパターンを満たす場合、`result` は `True`です。</span><span class="sxs-lookup"><span data-stu-id="8fffd-115">If the value in `string` satisfies the pattern contained in `pattern`, `result` is `True`.</span></span> <span data-ttu-id="8fffd-116">文字列がパターンを満たさない場合は、`result` が `False`ます。</span><span class="sxs-lookup"><span data-stu-id="8fffd-116">If the string does not satisfy the pattern, `result` is `False`.</span></span> <span data-ttu-id="8fffd-117">`string` と `pattern` の両方が空の文字列の場合、結果は `True`ます。</span><span class="sxs-lookup"><span data-stu-id="8fffd-117">If both `string` and `pattern` are empty strings, the result is `True`.</span></span>  
  
## <a name="comparison-method"></a><span data-ttu-id="8fffd-118">比較方法</span><span class="sxs-lookup"><span data-stu-id="8fffd-118">Comparison Method</span></span>  
 <span data-ttu-id="8fffd-119">`Like` 演算子の動作は、 [Option Compare ステートメント](../../../visual-basic/language-reference/statements/option-compare-statement.md)によって異なります。</span><span class="sxs-lookup"><span data-stu-id="8fffd-119">The behavior of the `Like` operator depends on the [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span></span> <span data-ttu-id="8fffd-120">各ソースファイルの既定の文字列比較方法は `Option Compare Binary`です。</span><span class="sxs-lookup"><span data-stu-id="8fffd-120">The default string comparison method for each source file is `Option Compare Binary`.</span></span>  
  
## <a name="pattern-options"></a><span data-ttu-id="8fffd-121">パターンオプション</span><span class="sxs-lookup"><span data-stu-id="8fffd-121">Pattern Options</span></span>  
 <span data-ttu-id="8fffd-122">組み込みのパターン照合では、文字列比較に使用できるさまざまなツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="8fffd-122">Built-in pattern matching provides a versatile tool for string comparisons.</span></span> <span data-ttu-id="8fffd-123">パターンマッチング機能を使用すると、`string` 内の各文字を、特定の文字、ワイルドカード文字、文字リスト、または文字範囲に対して一致させることができます。</span><span class="sxs-lookup"><span data-stu-id="8fffd-123">The pattern-matching features allow you to match each character in `string` against a specific character, a wildcard character, a character list, or a character range.</span></span> <span data-ttu-id="8fffd-124">次の表に、`pattern` で使用できる文字と、それらが一致する文字を示します。</span><span class="sxs-lookup"><span data-stu-id="8fffd-124">The following table shows the characters allowed in `pattern` and what they match.</span></span>  
  
|<span data-ttu-id="8fffd-125">`pattern` 内の文字</span><span class="sxs-lookup"><span data-stu-id="8fffd-125">Characters in `pattern`</span></span>|<span data-ttu-id="8fffd-126">`string` 内の一致</span><span class="sxs-lookup"><span data-stu-id="8fffd-126">Matches in `string`</span></span>|  
|-----------------------------|-------------------------|  
|`?`|<span data-ttu-id="8fffd-127">任意の 1 文字</span><span class="sxs-lookup"><span data-stu-id="8fffd-127">Any single character</span></span>|  
|`*`|<span data-ttu-id="8fffd-128">0個以上の文字</span><span class="sxs-lookup"><span data-stu-id="8fffd-128">Zero or more characters</span></span>|  
|`#`|<span data-ttu-id="8fffd-129">任意の1桁 (0 ~ 9)</span><span class="sxs-lookup"><span data-stu-id="8fffd-129">Any single digit (0–9)</span></span>|  
|`[charlist]`|<span data-ttu-id="8fffd-130">`charlist` 内の任意の1文字</span><span class="sxs-lookup"><span data-stu-id="8fffd-130">Any single character in `charlist`</span></span>|  
|`[!charlist]`|<span data-ttu-id="8fffd-131">`charlist` にない任意の1文字</span><span class="sxs-lookup"><span data-stu-id="8fffd-131">Any single character not in `charlist`</span></span>|  
  
## <a name="character-lists"></a><span data-ttu-id="8fffd-132">文字リスト</span><span class="sxs-lookup"><span data-stu-id="8fffd-132">Character Lists</span></span>  
 <span data-ttu-id="8fffd-133">角かっこ (`[ ]`) で囲まれた1つ以上の文字 (`charlist`) のグループを使用して `string` 内の任意の1文字と一致させることができ、数字を含むほぼすべての文字コードを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="8fffd-133">A group of one or more characters (`charlist`) enclosed in brackets (`[ ]`) can be used to match any single character in `string` and can include almost any character code, including digits.</span></span>  
  
 <span data-ttu-id="8fffd-134">`charlist` の先頭にある感嘆符 (`!`) は、`charlist` 内の文字を除く任意の文字が `string`で見つかった場合に一致することを意味します。</span><span class="sxs-lookup"><span data-stu-id="8fffd-134">An exclamation point (`!`) at the beginning of `charlist` means that a match is made if any character except the characters in `charlist` is found in `string`.</span></span> <span data-ttu-id="8fffd-135">かっこの外側で使用すると、感嘆符自体が一致します。</span><span class="sxs-lookup"><span data-stu-id="8fffd-135">When used outside brackets, the exclamation point matches itself.</span></span>  
  
## <a name="special-characters"></a><span data-ttu-id="8fffd-136">特殊文字</span><span class="sxs-lookup"><span data-stu-id="8fffd-136">Special Characters</span></span>  
 <span data-ttu-id="8fffd-137">特殊文字の左角かっこ (`[`)、疑問符 (`?`)、番号記号 (`#`)、アスタリスク (`*`) と一致させるには、角かっこで囲みます。</span><span class="sxs-lookup"><span data-stu-id="8fffd-137">To match the special characters left bracket (`[`), question mark (`?`), number sign (`#`), and asterisk (`*`), enclose them in brackets.</span></span> <span data-ttu-id="8fffd-138">右角かっこ (`]`) は、それ自体に一致するグループ内では使用できませんが、グループの外側で個別の文字として使用することはできます。</span><span class="sxs-lookup"><span data-stu-id="8fffd-138">The right bracket (`]`) cannot be used within a group to match itself, but it can be used outside a group as an individual character.</span></span>  
  
 <span data-ttu-id="8fffd-139">文字シーケンス `[]` は、長さが0の文字列 (`""`) と見なされます。</span><span class="sxs-lookup"><span data-stu-id="8fffd-139">The character sequence `[]` is considered a zero-length string (`""`).</span></span> <span data-ttu-id="8fffd-140">ただし、角かっこで囲まれた文字リストの一部にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="8fffd-140">However, it cannot be part of a character list enclosed in brackets.</span></span> <span data-ttu-id="8fffd-141">`string` 内の位置に文字のグループのいずれかが含まれているかどうかを確認したい場合は、`Like` を2回使用できます。</span><span class="sxs-lookup"><span data-stu-id="8fffd-141">If you want to check whether a position in `string` contains one of a group of characters or no character at all, you can use `Like` twice.</span></span> <span data-ttu-id="8fffd-142">例については、「[方法: 文字列をパターンに一致させる](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fffd-142">For an example, see [How to: Match a String against a Pattern](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md).</span></span>  
  
## <a name="character-ranges"></a><span data-ttu-id="8fffd-143">文字範囲</span><span class="sxs-lookup"><span data-stu-id="8fffd-143">Character Ranges</span></span>  
 <span data-ttu-id="8fffd-144">ハイフン (`–`) を使用して範囲の下限と上限を区切ることにより、`charlist` は文字の範囲を指定できます。</span><span class="sxs-lookup"><span data-stu-id="8fffd-144">By using a hyphen (`–`) to separate the lower and upper bounds of the range, `charlist` can specify a range of characters.</span></span> <span data-ttu-id="8fffd-145">たとえば、`string` 内の対応する文字位置に `A`–`Z`の範囲内の任意の文字が含まれている場合、`[A–Z]` は一致と見なされます。また、対応する文字位置に範囲外の文字が含まれている場合は、`[!H–L]` – `H`に一致します。`L`</span><span class="sxs-lookup"><span data-stu-id="8fffd-145">For example, `[A–Z]` results in a match if the corresponding character position in `string` contains any character within the range `A`–`Z`, and `[!H–L]` results in a match if the corresponding character position contains any character outside the range `H`–`L`.</span></span>  
  
 <span data-ttu-id="8fffd-146">文字の範囲を指定する場合は、昇順の並べ替え順序、つまり、小さい方から順に表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fffd-146">When you specify a range of characters, they must appear in ascending sort order, that is, from lowest to highest.</span></span> <span data-ttu-id="8fffd-147">したがって、`[A–Z]` は有効なパターンですが、`[Z–A]` は有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="8fffd-147">Thus, `[A–Z]` is a valid pattern, but `[Z–A]` is not.</span></span>  
  
### <a name="multiple-character-ranges"></a><span data-ttu-id="8fffd-148">複数の文字範囲</span><span class="sxs-lookup"><span data-stu-id="8fffd-148">Multiple Character Ranges</span></span>  
 <span data-ttu-id="8fffd-149">同じ文字位置に複数の範囲を指定するには、区切り記号を使用せずに同じ角かっこ内に配置します。</span><span class="sxs-lookup"><span data-stu-id="8fffd-149">To specify multiple ranges for the same character position, put them within the same brackets without delimiters.</span></span> <span data-ttu-id="8fffd-150">たとえば、`string` 内の対応する文字位置に `A`–`C` または `X`~`Z`の範囲内のいずれかの文字が含まれている場合は、`[A–CX–Z]` 結果が一致します。</span><span class="sxs-lookup"><span data-stu-id="8fffd-150">For example, `[A–CX–Z]` results in a match if the corresponding character position in `string` contains any character within either the range `A`–`C` or the range `X`–`Z`.</span></span>  
  
### <a name="usage-of-the-hyphen"></a><span data-ttu-id="8fffd-151">ハイフンの使用</span><span class="sxs-lookup"><span data-stu-id="8fffd-151">Usage of the Hyphen</span></span>  
 <span data-ttu-id="8fffd-152">ハイフン (`–`) は、先頭 (感嘆符の後)、または `charlist` の末尾に、それ自体に一致させることができます。</span><span class="sxs-lookup"><span data-stu-id="8fffd-152">A hyphen (`–`) can appear either at the beginning (after an exclamation point, if any) or at the end of `charlist` to match itself.</span></span> <span data-ttu-id="8fffd-153">その他の場所では、ハイフンは、ハイフンの両側の文字で区切られた文字の範囲を識別します。</span><span class="sxs-lookup"><span data-stu-id="8fffd-153">In any other location, the hyphen identifies a range of characters delimited by the characters on either side of the hyphen.</span></span>  
  
## <a name="collating-sequence"></a><span data-ttu-id="8fffd-154">照合順序</span><span class="sxs-lookup"><span data-stu-id="8fffd-154">Collating Sequence</span></span>  
 <span data-ttu-id="8fffd-155">指定された範囲の意味は、実行時の文字の順序によって異なります。 `Option Compare` と、コードが実行されているシステムのロケール設定によって決まります。</span><span class="sxs-lookup"><span data-stu-id="8fffd-155">The meaning of a specified range depends on the character ordering at run time, as determined by `Option Compare` and the locale setting of the system the code is running on.</span></span> <span data-ttu-id="8fffd-156">`Option Compare Binary`の場合、`[A–E]` 範囲は `A`、`B`、`C`、`D`、および `E`と一致します。</span><span class="sxs-lookup"><span data-stu-id="8fffd-156">With `Option Compare Binary`, the range `[A–E]` matches `A`, `B`, `C`, `D`, and `E`.</span></span> <span data-ttu-id="8fffd-157">`Option Compare Text`では、`[A–E]` は `A`、`a`、`À`、`à`、`B`、`b`、`C`、`c`、`D`、`d`、`E`、`e`と一致します。</span><span class="sxs-lookup"><span data-stu-id="8fffd-157">With `Option Compare Text`, `[A–E]` matches `A`, `a`, `À`, `à`, `B`, `b`, `C`, `c`, `D`, `d`, `E`, and `e`.</span></span> <span data-ttu-id="8fffd-158">この範囲は `Ê` または `ê` と一致しません。これは、アクセント記号付き文字が並べ替え順序でアクセントが付いていない文字の後になるためです。</span><span class="sxs-lookup"><span data-stu-id="8fffd-158">The range does not match `Ê` or `ê` because accented characters collate after unaccented characters in the sort order.</span></span>  
  
## <a name="digraph-characters"></a><span data-ttu-id="8fffd-159">Digraph の文字</span><span class="sxs-lookup"><span data-stu-id="8fffd-159">Digraph Characters</span></span>  
 <span data-ttu-id="8fffd-160">言語によっては、2つの異なる文字を表すアルファベット文字があります。</span><span class="sxs-lookup"><span data-stu-id="8fffd-160">In some languages, there are alphabetic characters that represent two separate characters.</span></span> <span data-ttu-id="8fffd-161">たとえば、いくつかの言語では、文字 `æ` を使用して `a` と `e` 文字が一緒に表示されます。</span><span class="sxs-lookup"><span data-stu-id="8fffd-161">For example, several languages use the character `æ` to represent the characters `a` and `e` when they appear together.</span></span> <span data-ttu-id="8fffd-162">`Like` 演算子は、1つの digraph 文字と2つの個別の文字が等価であることを認識します。</span><span class="sxs-lookup"><span data-stu-id="8fffd-162">The `Like` operator recognizes that the single digraph character and the two individual characters are equivalent.</span></span>  
  
 <span data-ttu-id="8fffd-163">Digraph 文字を使用する言語がシステムのロケール設定で指定されている場合、`pattern` または `string` の1つの digraph 文字が、他の文字列の等価の2文字シーケンスと一致します。</span><span class="sxs-lookup"><span data-stu-id="8fffd-163">When a language that uses a digraph character is specified in the system locale settings, an occurrence of the single digraph character in either `pattern` or `string` matches the equivalent two-character sequence in the other string.</span></span> <span data-ttu-id="8fffd-164">同様に、角かっこで囲まれた `pattern` の digraph 文字 (単独、リスト、または範囲内) は、`string`内の等価の2文字シーケンスと一致します。</span><span class="sxs-lookup"><span data-stu-id="8fffd-164">Similarly, a digraph character in `pattern` enclosed in brackets (by itself, in a list, or in a range) matches the equivalent two-character sequence in `string`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="8fffd-165">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="8fffd-165">Overloading</span></span>  
 <span data-ttu-id="8fffd-166">`Like` 演算子は*オーバーロード*することができます。つまり、クラスまたは構造体がそのクラスまたは構造体の型を持つ場合に、クラスまたは構造体がその動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="8fffd-166">The `Like` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="8fffd-167">コードでこのようなクラスまたは構造体に対してこの演算子を使用する場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8fffd-167">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="8fffd-168">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fffd-168">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8fffd-169">例</span><span class="sxs-lookup"><span data-stu-id="8fffd-169">Example</span></span>  
 <span data-ttu-id="8fffd-170">この例では、`Like` 演算子を使用して、文字列をさまざまなパターンと比較します。</span><span class="sxs-lookup"><span data-stu-id="8fffd-170">This example uses the `Like` operator to compare strings to various patterns.</span></span> <span data-ttu-id="8fffd-171">結果は、各文字列がパターンを満たすかどうかを示す `Boolean` 変数に入ります。</span><span class="sxs-lookup"><span data-stu-id="8fffd-171">The results go into a `Boolean` variable indicating whether each string satisfies the pattern.</span></span>  
  
 [!code-vb[VbVbalrOperators#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="8fffd-172">参照</span><span class="sxs-lookup"><span data-stu-id="8fffd-172">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.InStr%2A>
- <xref:Microsoft.VisualBasic.Strings.StrComp%2A>
- [<span data-ttu-id="8fffd-173">比較演算子</span><span class="sxs-lookup"><span data-stu-id="8fffd-173">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="8fffd-174">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="8fffd-174">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="8fffd-175">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="8fffd-175">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="8fffd-176">Option Compare ステートメント</span><span class="sxs-lookup"><span data-stu-id="8fffd-176">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [<span data-ttu-id="8fffd-177">演算子および式</span><span class="sxs-lookup"><span data-stu-id="8fffd-177">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="8fffd-178">方法 : 文字列がパターンに一致するかを調べる</span><span class="sxs-lookup"><span data-stu-id="8fffd-178">How to: Match a String against a Pattern</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md)
