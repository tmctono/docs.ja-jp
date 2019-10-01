---
title: Like 演算子 (Visual Basic)
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
ms.openlocfilehash: 795ecc2e80d57af29ccd50c50d2dd209c6425e40
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701135"
---
# <a name="like-operator-visual-basic"></a><span data-ttu-id="2bb2b-102">Like 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2bb2b-102">Like Operator (Visual Basic)</span></span>
<span data-ttu-id="2bb2b-103">文字列をパターンと比較します。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-103">Compares a string against a pattern.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="2bb2b-104">@No__t-0 演算子は、現在、.NET Core および .NET Standard プロジェクトではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-104">The `Like` operator is currently not supported in .NET Core and .NET Standard projects.</span></span>

## <a name="syntax"></a><span data-ttu-id="2bb2b-105">構文</span><span class="sxs-lookup"><span data-stu-id="2bb2b-105">Syntax</span></span>  
  
```vb  
result = string Like pattern  
```  
  
## <a name="parts"></a><span data-ttu-id="2bb2b-106">指定項目</span><span class="sxs-lookup"><span data-stu-id="2bb2b-106">Parts</span></span>  
 `result`  
 <span data-ttu-id="2bb2b-107">必須。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-107">Required.</span></span> <span data-ttu-id="2bb2b-108">@No__t 0 の変数。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-108">Any `Boolean` variable.</span></span> <span data-ttu-id="2bb2b-109">結果は `string` @no__t が @no__t を満たすかどうかを示す0の値になります。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-109">The result is a `Boolean` value indicating whether or not the `string` satisfies the `pattern`.</span></span>  
  
 `string`  
 <span data-ttu-id="2bb2b-110">必須。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-110">Required.</span></span> <span data-ttu-id="2bb2b-111">任意のブール型 ( `String` ) の式を指定します。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-111">Any `String` expression.</span></span>  
  
 `pattern`  
 <span data-ttu-id="2bb2b-112">必須。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-112">Required.</span></span> <span data-ttu-id="2bb2b-113">「解説」で説明されているパターン一致規則に準拠する任意の `String` 式。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-113">Any `String` expression conforming to the pattern-matching conventions described in "Remarks."</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2bb2b-114">コメント</span><span class="sxs-lookup"><span data-stu-id="2bb2b-114">Remarks</span></span>  
 <span data-ttu-id="2bb2b-115">@No__t-0 の値が `pattern` に含まれるパターンを満たす場合、`result` は `True` になります。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-115">If the value in `string` satisfies the pattern contained in `pattern`, `result` is `True`.</span></span> <span data-ttu-id="2bb2b-116">文字列がパターンを満たさない場合、`result` は `False` になります。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-116">If the string does not satisfy the pattern, `result` is `False`.</span></span> <span data-ttu-id="2bb2b-117">@No__t-0 と `pattern` の両方が空の文字列の場合、結果は `True` になります。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-117">If both `string` and `pattern` are empty strings, the result is `True`.</span></span>  
  
## <a name="comparison-method"></a><span data-ttu-id="2bb2b-118">比較方法</span><span class="sxs-lookup"><span data-stu-id="2bb2b-118">Comparison Method</span></span>  
 <span data-ttu-id="2bb2b-119">@No__t-0 演算子の動作は、 [Option Compare ステートメント](../../../visual-basic/language-reference/statements/option-compare-statement.md)によって異なります。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-119">The behavior of the `Like` operator depends on the [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span></span> <span data-ttu-id="2bb2b-120">各ソースファイルの既定の文字列比較方法は、`Option Compare Binary` です。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-120">The default string comparison method for each source file is `Option Compare Binary`.</span></span>  
  
## <a name="pattern-options"></a><span data-ttu-id="2bb2b-121">パターンオプション</span><span class="sxs-lookup"><span data-stu-id="2bb2b-121">Pattern Options</span></span>  
 <span data-ttu-id="2bb2b-122">組み込みのパターン照合では、文字列比較に使用できるさまざまなツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-122">Built-in pattern matching provides a versatile tool for string comparisons.</span></span> <span data-ttu-id="2bb2b-123">パターンマッチング機能を使用すると、@no__t 0 の各文字を特定の文字、ワイルドカード文字、文字リスト、または文字範囲に一致させることができます。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-123">The pattern-matching features allow you to match each character in `string` against a specific character, a wildcard character, a character list, or a character range.</span></span> <span data-ttu-id="2bb2b-124">次の表に、`pattern` で使用できる文字と、それが一致する文字を示します。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-124">The following table shows the characters allowed in `pattern` and what they match.</span></span>  
  
|<span data-ttu-id="2bb2b-125">@No__t 内の文字数-0</span><span class="sxs-lookup"><span data-stu-id="2bb2b-125">Characters in `pattern`</span></span>|<span data-ttu-id="2bb2b-126">@No__t での一致-0</span><span class="sxs-lookup"><span data-stu-id="2bb2b-126">Matches in `string`</span></span>|  
|-----------------------------|-------------------------|  
|`?`|<span data-ttu-id="2bb2b-127">任意の 1 文字</span><span class="sxs-lookup"><span data-stu-id="2bb2b-127">Any single character</span></span>|  
|`*`|<span data-ttu-id="2bb2b-128">0個以上の文字</span><span class="sxs-lookup"><span data-stu-id="2bb2b-128">Zero or more characters</span></span>|  
|`#`|<span data-ttu-id="2bb2b-129">任意の1桁 (0 ~ 9)</span><span class="sxs-lookup"><span data-stu-id="2bb2b-129">Any single digit (0–9)</span></span>|  
|`[charlist]`|<span data-ttu-id="2bb2b-130">@No__t-0 の任意の1文字</span><span class="sxs-lookup"><span data-stu-id="2bb2b-130">Any single character in `charlist`</span></span>|  
|`[!charlist]`|<span data-ttu-id="2bb2b-131">@No__t 0 以外の任意の1文字</span><span class="sxs-lookup"><span data-stu-id="2bb2b-131">Any single character not in `charlist`</span></span>|  
  
## <a name="character-lists"></a><span data-ttu-id="2bb2b-132">文字リスト</span><span class="sxs-lookup"><span data-stu-id="2bb2b-132">Character Lists</span></span>  
 <span data-ttu-id="2bb2b-133">角かっこ (`[ ]`) で囲まれた1つ以上の文字 (`charlist`) のグループを使用して、`string` の任意の1文字に一致させることができ、数字を含むほぼすべての文字コードを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-133">A group of one or more characters (`charlist`) enclosed in brackets (`[ ]`) can be used to match any single character in `string` and can include almost any character code, including digits.</span></span>  
  
 <span data-ttu-id="2bb2b-134">@No__t-1 の先頭にある感嘆符 (`!`) は、`charlist` の文字を除く任意の文字が `string` で見つかった場合に一致することを意味します。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-134">An exclamation point (`!`) at the beginning of `charlist` means that a match is made if any character except the characters in `charlist` is found in `string`.</span></span> <span data-ttu-id="2bb2b-135">かっこの外側で使用すると、感嘆符自体が一致します。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-135">When used outside brackets, the exclamation point matches itself.</span></span>  
  
## <a name="special-characters"></a><span data-ttu-id="2bb2b-136">特殊文字</span><span class="sxs-lookup"><span data-stu-id="2bb2b-136">Special Characters</span></span>  
 <span data-ttu-id="2bb2b-137">特殊文字の左角かっこ (`[`)、疑問符 (`?`)、番号記号 (`#`)、アスタリスク (`*`) と一致させるには、角かっこで囲みます。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-137">To match the special characters left bracket (`[`), question mark (`?`), number sign (`#`), and asterisk (`*`), enclose them in brackets.</span></span> <span data-ttu-id="2bb2b-138">右角かっこ (`]`) は、それ自体に一致するグループ内では使用できませんが、グループの外側で個別の文字として使用することはできます。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-138">The right bracket (`]`) cannot be used within a group to match itself, but it can be used outside a group as an individual character.</span></span>  
  
 <span data-ttu-id="2bb2b-139">@No__t-0 という文字シーケンスは、長さが0の文字列と見なされます (`""`)。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-139">The character sequence `[]` is considered a zero-length string (`""`).</span></span> <span data-ttu-id="2bb2b-140">ただし、角かっこで囲まれた文字リストの一部にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-140">However, it cannot be part of a character list enclosed in brackets.</span></span> <span data-ttu-id="2bb2b-141">@No__t-0 の位置に文字のグループのいずれかが含まれているかどうかを確認する場合、または文字をまったく使用しない場合は、`Like` を2回使用できます。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-141">If you want to check whether a position in `string` contains one of a group of characters or no character at all, you can use `Like` twice.</span></span> <span data-ttu-id="2bb2b-142">例については、「[方法: 文字列をパターン @ no__t-0 と照合します。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-142">For an example, see [How to: Match a String against a Pattern](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md).</span></span>  
  
## <a name="character-ranges"></a><span data-ttu-id="2bb2b-143">文字範囲</span><span class="sxs-lookup"><span data-stu-id="2bb2b-143">Character Ranges</span></span>  
 <span data-ttu-id="2bb2b-144">ハイフン (`–`) を使用して範囲の下限と上限を区切ることにより、`charlist` は文字の範囲を指定できます。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-144">By using a hyphen (`–`) to separate the lower and upper bounds of the range, `charlist` can specify a range of characters.</span></span> <span data-ttu-id="2bb2b-145">たとえば、`string` の対応する文字位置に `A` ~ `Z` の範囲内の任意の文字が含まれている場合、`[A–Z]` は一致と見なされます。 @no__t また、対応する文字位置に含まれる文字がの外にある場合は、一致と見なされます。範囲 `H` – `L`。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-145">For example, `[A–Z]` results in a match if the corresponding character position in `string` contains any character within the range `A`–`Z`, and `[!H–L]` results in a match if the corresponding character position contains any character outside the range `H`–`L`.</span></span>  
  
 <span data-ttu-id="2bb2b-146">文字の範囲を指定する場合は、昇順の並べ替え順序、つまり、小さい方から順に表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-146">When you specify a range of characters, they must appear in ascending sort order, that is, from lowest to highest.</span></span> <span data-ttu-id="2bb2b-147">したがって、`[A–Z]` は有効なパターンですが、`[Z–A]` は無効です。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-147">Thus, `[A–Z]` is a valid pattern, but `[Z–A]` is not.</span></span>  
  
### <a name="multiple-character-ranges"></a><span data-ttu-id="2bb2b-148">複数の文字範囲</span><span class="sxs-lookup"><span data-stu-id="2bb2b-148">Multiple Character Ranges</span></span>  
 <span data-ttu-id="2bb2b-149">同じ文字位置に複数の範囲を指定するには、区切り記号を使用せずに同じ角かっこ内に配置します。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-149">To specify multiple ranges for the same character position, put them within the same brackets without delimiters.</span></span> <span data-ttu-id="2bb2b-150">たとえば、`[A–CX–Z]` の場合、`string` 内の対応する文字位置に `A` ~ `C` の範囲のいずれかの文字が含まれているか、または `X` – @no__t の範囲内にある場合は一致と見なされます。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-150">For example, `[A–CX–Z]` results in a match if the corresponding character position in `string` contains any character within either the range `A`–`C` or the range `X`–`Z`.</span></span>  
  
### <a name="usage-of-the-hyphen"></a><span data-ttu-id="2bb2b-151">ハイフンの使用</span><span class="sxs-lookup"><span data-stu-id="2bb2b-151">Usage of the Hyphen</span></span>  
 <span data-ttu-id="2bb2b-152">ハイフン (`–`) は、その先頭 (感嘆符の後)、または @no__t の最後にある場合があります。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-152">A hyphen (`–`) can appear either at the beginning (after an exclamation point, if any) or at the end of `charlist` to match itself.</span></span> <span data-ttu-id="2bb2b-153">その他の場所では、ハイフンは、ハイフンの両側の文字で区切られた文字の範囲を識別します。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-153">In any other location, the hyphen identifies a range of characters delimited by the characters on either side of the hyphen.</span></span>  
  
## <a name="collating-sequence"></a><span data-ttu-id="2bb2b-154">照合順序</span><span class="sxs-lookup"><span data-stu-id="2bb2b-154">Collating Sequence</span></span>  
 <span data-ttu-id="2bb2b-155">指定された範囲の意味は、実行時の文字の順序によって異なります。 `Option Compare` と、コードが実行されているシステムのロケール設定によって決まります。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-155">The meaning of a specified range depends on the character ordering at run time, as determined by `Option Compare` and the locale setting of the system the code is running on.</span></span> <span data-ttu-id="2bb2b-156">@No__t-0 の場合、`[A–E]` の範囲は `A`、`B`、`C`、`D`、および `E` と一致します。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-156">With `Option Compare Binary`, the range `[A–E]` matches `A`, `B`, `C`, `D`, and `E`.</span></span> <span data-ttu-id="2bb2b-157">@No__t 0 の場合、`[A–E]` は `A`、`a`、@no__t 4、`à`、`B`、`b`、`C`、`c`、0、1、2、3 に一致します。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-157">With `Option Compare Text`, `[A–E]` matches `A`, `a`, `À`, `à`, `B`, `b`, `C`, `c`, `D`, `d`, `E`, and `e`.</span></span> <span data-ttu-id="2bb2b-158">アクセント文字が並べ替え順でアクセントが付いていない文字の後になるため、範囲が `Ê` または `ê` と一致しません。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-158">The range does not match `Ê` or `ê` because accented characters collate after unaccented characters in the sort order.</span></span>  
  
## <a name="digraph-characters"></a><span data-ttu-id="2bb2b-159">Digraph の文字</span><span class="sxs-lookup"><span data-stu-id="2bb2b-159">Digraph Characters</span></span>  
 <span data-ttu-id="2bb2b-160">言語によっては、2つの異なる文字を表すアルファベット文字があります。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-160">In some languages, there are alphabetic characters that represent two separate characters.</span></span> <span data-ttu-id="2bb2b-161">たとえば、複数の言語では、文字 `æ` を使用して文字 `a` と `e` が一緒に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-161">For example, several languages use the character `æ` to represent the characters `a` and `e` when they appear together.</span></span> <span data-ttu-id="2bb2b-162">@No__t 0 演算子は、1つの digraph 文字と2つの個別の文字が等価であることを認識します。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-162">The `Like` operator recognizes that the single digraph character and the two individual characters are equivalent.</span></span>  
  
 <span data-ttu-id="2bb2b-163">Digraph 文字を使用する言語がシステムのロケール設定で指定されている場合、`pattern` または `string` のいずれかで1つの digraph 文字が出現すると、他方の文字列の等価の2文字シーケンスと一致します。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-163">When a language that uses a digraph character is specified in the system locale settings, an occurrence of the single digraph character in either `pattern` or `string` matches the equivalent two-character sequence in the other string.</span></span> <span data-ttu-id="2bb2b-164">同様に、角かっこで囲まれた @no__t 0 の digraph 文字 (単独、リスト、または範囲内) は、`string` の2文字のシーケンスと一致します。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-164">Similarly, a digraph character in `pattern` enclosed in brackets (by itself, in a list, or in a range) matches the equivalent two-character sequence in `string`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="2bb2b-165">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="2bb2b-165">Overloading</span></span>  
 <span data-ttu-id="2bb2b-166">@No__t-0 演算子は*オーバーロード*できます。つまり、クラスまたは構造体がそのクラスまたは構造体の型を持つ場合に、クラスまたは構造体がその動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-166">The `Like` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="2bb2b-167">コードでこのようなクラスまたは構造体に対してこの演算子を使用する場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-167">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="2bb2b-168">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-168">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2bb2b-169">例</span><span class="sxs-lookup"><span data-stu-id="2bb2b-169">Example</span></span>  
 <span data-ttu-id="2bb2b-170">この例では、`Like` 演算子を使用して、文字列をさまざまなパターンと比較します。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-170">This example uses the `Like` operator to compare strings to various patterns.</span></span> <span data-ttu-id="2bb2b-171">結果は、各文字列がパターンを満たすかどうかを示す @no__t 0 の変数になります。</span><span class="sxs-lookup"><span data-stu-id="2bb2b-171">The results go into a `Boolean` variable indicating whether each string satisfies the pattern.</span></span>  
  
 [!code-vb[VbVbalrOperators#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="2bb2b-172">関連項目</span><span class="sxs-lookup"><span data-stu-id="2bb2b-172">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.InStr%2A>
- <xref:Microsoft.VisualBasic.Strings.StrComp%2A>
- [<span data-ttu-id="2bb2b-173">比較演算子</span><span class="sxs-lookup"><span data-stu-id="2bb2b-173">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="2bb2b-174">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="2bb2b-174">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="2bb2b-175">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="2bb2b-175">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="2bb2b-176">Option Compare ステートメント</span><span class="sxs-lookup"><span data-stu-id="2bb2b-176">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [<span data-ttu-id="2bb2b-177">演算子および式</span><span class="sxs-lookup"><span data-stu-id="2bb2b-177">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- <span data-ttu-id="2bb2b-178">[2 つのオブジェクトが等しいかどうかをテストする方法パターンに対して文字列を一致させます @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="2bb2b-178">[How to: Match a String against a Pattern](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md)</span></span>
