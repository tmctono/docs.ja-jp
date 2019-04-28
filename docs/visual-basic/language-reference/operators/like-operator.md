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
ms.openlocfilehash: 38e56b8c0ec6bab89052ee42a2cd9c24053c658e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768330"
---
# <a name="like-operator-visual-basic"></a><span data-ttu-id="874fc-102">Like 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="874fc-102">Like Operator (Visual Basic)</span></span>
<span data-ttu-id="874fc-103">文字列をパターンと比較します。</span><span class="sxs-lookup"><span data-stu-id="874fc-103">Compares a string against a pattern.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="874fc-104">`Like`演算子が .NET Core と .NET Standard プロジェクトでサポートされていません現在します。</span><span class="sxs-lookup"><span data-stu-id="874fc-104">The `Like` operator is currently not supported in .NET Core and .NET Standard projects.</span></span>

## <a name="syntax"></a><span data-ttu-id="874fc-105">構文</span><span class="sxs-lookup"><span data-stu-id="874fc-105">Syntax</span></span>  
  
```  
result = string Like pattern  
```  
  
## <a name="parts"></a><span data-ttu-id="874fc-106">指定項目</span><span class="sxs-lookup"><span data-stu-id="874fc-106">Parts</span></span>  
 `result`  
 <span data-ttu-id="874fc-107">必須。</span><span class="sxs-lookup"><span data-stu-id="874fc-107">Required.</span></span> <span data-ttu-id="874fc-108">すべて`Boolean`変数。</span><span class="sxs-lookup"><span data-stu-id="874fc-108">Any `Boolean` variable.</span></span> <span data-ttu-id="874fc-109">結果は、`Boolean`を示す値かどうか、`string`を満たす、`pattern`します。</span><span class="sxs-lookup"><span data-stu-id="874fc-109">The result is a `Boolean` value indicating whether or not the `string` satisfies the `pattern`.</span></span>  
  
 `string`  
 <span data-ttu-id="874fc-110">必須。</span><span class="sxs-lookup"><span data-stu-id="874fc-110">Required.</span></span> <span data-ttu-id="874fc-111">任意のブール型 ( `String` ) の式を指定します。</span><span class="sxs-lookup"><span data-stu-id="874fc-111">Any `String` expression.</span></span>  
  
 `pattern`  
 <span data-ttu-id="874fc-112">必須。</span><span class="sxs-lookup"><span data-stu-id="874fc-112">Required.</span></span> <span data-ttu-id="874fc-113">すべて`String`「解説」で説明されているパターン一致規則に準拠している式。</span><span class="sxs-lookup"><span data-stu-id="874fc-113">Any `String` expression conforming to the pattern-matching conventions described in "Remarks."</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="874fc-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="874fc-114">Remarks</span></span>  
 <span data-ttu-id="874fc-115">場合の値`string`がパターンに含まれるを満たす`pattern`、`result`は`True`します。</span><span class="sxs-lookup"><span data-stu-id="874fc-115">If the value in `string` satisfies the pattern contained in `pattern`, `result` is `True`.</span></span> <span data-ttu-id="874fc-116">文字列がパターンを満たさない場合`result`は`False`します。</span><span class="sxs-lookup"><span data-stu-id="874fc-116">If the string does not satisfy the pattern, `result` is `False`.</span></span> <span data-ttu-id="874fc-117">両方`string`と`pattern`空の文字列には、結果は`True`します。</span><span class="sxs-lookup"><span data-stu-id="874fc-117">If both `string` and `pattern` are empty strings, the result is `True`.</span></span>  
  
## <a name="comparison-method"></a><span data-ttu-id="874fc-118">比較メソッド</span><span class="sxs-lookup"><span data-stu-id="874fc-118">Comparison Method</span></span>  
 <span data-ttu-id="874fc-119">動作、`Like`演算子によって異なります、 [Option Compare ステートメント](../../../visual-basic/language-reference/statements/option-compare-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="874fc-119">The behavior of the `Like` operator depends on the [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span></span> <span data-ttu-id="874fc-120">各ソース ファイルの既定の文字列比較メソッドは`Option Compare Binary`します。</span><span class="sxs-lookup"><span data-stu-id="874fc-120">The default string comparison method for each source file is `Option Compare Binary`.</span></span>  
  
## <a name="pattern-options"></a><span data-ttu-id="874fc-121">パターンのオプション</span><span class="sxs-lookup"><span data-stu-id="874fc-121">Pattern Options</span></span>  
 <span data-ttu-id="874fc-122">組み込みのパターンに一致する文字列比較での多用途のツールを提供します。</span><span class="sxs-lookup"><span data-stu-id="874fc-122">Built-in pattern matching provides a versatile tool for string comparisons.</span></span> <span data-ttu-id="874fc-123">内の各文字に一致することは、パターン マッチング機能`string`に対して特定の文字、ワイルドカード文字、文字のリスト、または文字の範囲。</span><span class="sxs-lookup"><span data-stu-id="874fc-123">The pattern-matching features allow you to match each character in `string` against a specific character, a wildcard character, a character list, or a character range.</span></span> <span data-ttu-id="874fc-124">次の表で使用できる文字`pattern`一致したとします。</span><span class="sxs-lookup"><span data-stu-id="874fc-124">The following table shows the characters allowed in `pattern` and what they match.</span></span>  
  
|<span data-ttu-id="874fc-125">内の文字 `pattern`</span><span class="sxs-lookup"><span data-stu-id="874fc-125">Characters in `pattern`</span></span>|<span data-ttu-id="874fc-126">内の一致 `string`</span><span class="sxs-lookup"><span data-stu-id="874fc-126">Matches in `string`</span></span>|  
|-----------------------------|-------------------------|  
|`?`|<span data-ttu-id="874fc-127">任意の 1 文字</span><span class="sxs-lookup"><span data-stu-id="874fc-127">Any single character</span></span>|  
|`*`|<span data-ttu-id="874fc-128">0 個以上の文字</span><span class="sxs-lookup"><span data-stu-id="874fc-128">Zero or more characters</span></span>|  
|`#`|<span data-ttu-id="874fc-129">任意の 1 つの数字 (0 ~ 9)</span><span class="sxs-lookup"><span data-stu-id="874fc-129">Any single digit (0–9)</span></span>|  
|`[charlist]`|<span data-ttu-id="874fc-130">任意の 1 文字 `charlist`</span><span class="sxs-lookup"><span data-stu-id="874fc-130">Any single character in `charlist`</span></span>|  
|`[!charlist]`|<span data-ttu-id="874fc-131">内にない任意の 1 文字 `charlist`</span><span class="sxs-lookup"><span data-stu-id="874fc-131">Any single character not in `charlist`</span></span>|  
  
## <a name="character-lists"></a><span data-ttu-id="874fc-132">文字の一覧</span><span class="sxs-lookup"><span data-stu-id="874fc-132">Character Lists</span></span>  
 <span data-ttu-id="874fc-133">1 つまたは複数の文字グループ (`charlist`) 角かっこで囲む (`[ ]`) 内の任意の 1 文字を一致させることができます`string`桁の数字を含む、ほぼすべての文字コードを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="874fc-133">A group of one or more characters (`charlist`) enclosed in brackets (`[ ]`) can be used to match any single character in `string` and can include almost any character code, including digits.</span></span>  
  
 <span data-ttu-id="874fc-134">感嘆符 (`!`) の先頭に`charlist`内の文字を除く任意の文字の場合、一致が行われたことを意味`charlist`は`string`します。</span><span class="sxs-lookup"><span data-stu-id="874fc-134">An exclamation point (`!`) at the beginning of `charlist` means that a match is made if any character except the characters in `charlist` is found in `string`.</span></span> <span data-ttu-id="874fc-135">角かっこの外側を使用する場合、感嘆符自体と一致します。</span><span class="sxs-lookup"><span data-stu-id="874fc-135">When used outside brackets, the exclamation point matches itself.</span></span>  
  
## <a name="special-characters"></a><span data-ttu-id="874fc-136">特殊文字</span><span class="sxs-lookup"><span data-stu-id="874fc-136">Special Characters</span></span>  
 <span data-ttu-id="874fc-137">特殊文字の左角かっこの一致するように (`[`)、疑問符 (`?`)、シャープ記号 (`#`)、およびアスタリスク (`*`)、角かっこで囲みます。</span><span class="sxs-lookup"><span data-stu-id="874fc-137">To match the special characters left bracket (`[`), question mark (`?`), number sign (`#`), and asterisk (`*`), enclose them in brackets.</span></span> <span data-ttu-id="874fc-138">右の角かっこ (`]`) 自体には、一致するように、グループ内で使用できませんが、グループ外で個別の文字として使用することができます。</span><span class="sxs-lookup"><span data-stu-id="874fc-138">The right bracket (`]`) cannot be used within a group to match itself, but it can be used outside a group as an individual character.</span></span>  
  
 <span data-ttu-id="874fc-139">文字シーケンス`[]`長さ 0 の文字列と見なされます (`""`)。</span><span class="sxs-lookup"><span data-stu-id="874fc-139">The character sequence `[]` is considered a zero-length string (`""`).</span></span> <span data-ttu-id="874fc-140">ただし、角かっこで囲まれた文字の一覧の一部にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="874fc-140">However, it cannot be part of a character list enclosed in brackets.</span></span> <span data-ttu-id="874fc-141">内の位置かどうかを確認したい場合`string`1 つ含まれる使用できる一連の文字または文字の`Like`2 回です。</span><span class="sxs-lookup"><span data-stu-id="874fc-141">If you want to check whether a position in `string` contains one of a group of characters or no character at all, you can use `Like` twice.</span></span> <span data-ttu-id="874fc-142">例については、「[方法: 文字列をパターンに一致](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md)します。</span><span class="sxs-lookup"><span data-stu-id="874fc-142">For an example, see [How to: Match a String against a Pattern](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md).</span></span>  
  
## <a name="character-ranges"></a><span data-ttu-id="874fc-143">文字範囲</span><span class="sxs-lookup"><span data-stu-id="874fc-143">Character Ranges</span></span>  
 <span data-ttu-id="874fc-144">ハイフンを使用して (`–`) と、範囲の上限を設定する`charlist`文字の範囲を指定できます。</span><span class="sxs-lookup"><span data-stu-id="874fc-144">By using a hyphen (`–`) to separate the lower and upper bounds of the range, `charlist` can specify a range of characters.</span></span> <span data-ttu-id="874fc-145">たとえば、`[A–Z]`結果と一致する場合は、対応する文字の位置で`string`範囲内の任意の文字が含まれています`A`–`Z`、および`[!H–L]`結果と一致する場合は、対応する文字の位置範囲外の任意の文字を含む`H`–`L`します。</span><span class="sxs-lookup"><span data-stu-id="874fc-145">For example, `[A–Z]` results in a match if the corresponding character position in `string` contains any character within the range `A`–`Z`, and `[!H–L]` results in a match if the corresponding character position contains any character outside the range `H`–`L`.</span></span>  
  
 <span data-ttu-id="874fc-146">文字の範囲を指定すると、昇順には、並べ替え順を昇順で現れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="874fc-146">When you specify a range of characters, they must appear in ascending sort order, that is, from lowest to highest.</span></span> <span data-ttu-id="874fc-147">したがって、`[A–Z]`は有効なパターンが`[Z–A]`はありません。</span><span class="sxs-lookup"><span data-stu-id="874fc-147">Thus, `[A–Z]` is a valid pattern, but `[Z–A]` is not.</span></span>  
  
### <a name="multiple-character-ranges"></a><span data-ttu-id="874fc-148">複数の文字範囲</span><span class="sxs-lookup"><span data-stu-id="874fc-148">Multiple Character Ranges</span></span>  
 <span data-ttu-id="874fc-149">同じ文字の位置に複数の範囲を指定するには、区切り記号は同じ角かっこ内に配置します。</span><span class="sxs-lookup"><span data-stu-id="874fc-149">To specify multiple ranges for the same character position, put them within the same brackets without delimiters.</span></span> <span data-ttu-id="874fc-150">たとえば、`[A–CX–Z]`結果と一致する場合は、対応する文字の位置で`string`いずれかの範囲内の任意の文字が含まれています`A`–`C`または範囲`X`–`Z`します。</span><span class="sxs-lookup"><span data-stu-id="874fc-150">For example, `[A–CX–Z]` results in a match if the corresponding character position in `string` contains any character within either the range `A`–`C` or the range `X`–`Z`.</span></span>  
  
### <a name="usage-of-the-hyphen"></a><span data-ttu-id="874fc-151">ハイフンの使用</span><span class="sxs-lookup"><span data-stu-id="874fc-151">Usage of the Hyphen</span></span>  
 <span data-ttu-id="874fc-152">ハイフン (`–`) (後に感嘆符、存在する場合) の先頭にあるかの最後に表示できる`charlist`自体を一致するようにします。</span><span class="sxs-lookup"><span data-stu-id="874fc-152">A hyphen (`–`) can appear either at the beginning (after an exclamation point, if any) or at the end of `charlist` to match itself.</span></span> <span data-ttu-id="874fc-153">その他の任意の場所では、ハイフンは、ハイフンの両側の文字が区切り文字の範囲を識別します。</span><span class="sxs-lookup"><span data-stu-id="874fc-153">In any other location, the hyphen identifies a range of characters delimited by the characters on either side of the hyphen.</span></span>  
  
## <a name="collating-sequence"></a><span data-ttu-id="874fc-154">照合順序</span><span class="sxs-lookup"><span data-stu-id="874fc-154">Collating Sequence</span></span>  
 <span data-ttu-id="874fc-155">指定した範囲の意味は、文字によって決定される、実行時に順序によって異なります。 `Option Compare` 、システムのロケール設定で、コードが実行されているとします。</span><span class="sxs-lookup"><span data-stu-id="874fc-155">The meaning of a specified range depends on the character ordering at run time, as determined by `Option Compare` and the locale setting of the system the code is running on.</span></span> <span data-ttu-id="874fc-156">`Option Compare Binary`、範囲`[A–E]`と一致する`A`、 `B`、 `C`、 `D`、および`E`します。</span><span class="sxs-lookup"><span data-stu-id="874fc-156">With `Option Compare Binary`, the range `[A–E]` matches `A`, `B`, `C`, `D`, and `E`.</span></span> <span data-ttu-id="874fc-157">`Option Compare Text`、`[A–E]`と一致する`A`、 `a`、 `À`、 `à`、 `B`、 `b`、 `C`、 `c`、 `D`、 `d`、 `E`、および`e`します。</span><span class="sxs-lookup"><span data-stu-id="874fc-157">With `Option Compare Text`, `[A–E]` matches `A`, `a`, `À`, `à`, `B`, `b`, `C`, `c`, `D`, `d`, `E`, and `e`.</span></span> <span data-ttu-id="874fc-158">範囲と一致しません`Ê`または`ê`並べ替え順序でアクセントのない文字にアクセント記号付き文字を照合します。</span><span class="sxs-lookup"><span data-stu-id="874fc-158">The range does not match `Ê` or `ê` because accented characters collate after unaccented characters in the sort order.</span></span>  
  
## <a name="digraph-characters"></a><span data-ttu-id="874fc-159">Digraph 文字</span><span class="sxs-lookup"><span data-stu-id="874fc-159">Digraph Characters</span></span>  
 <span data-ttu-id="874fc-160">一部の言語を表す 2 つの文字の英字があります。</span><span class="sxs-lookup"><span data-stu-id="874fc-160">In some languages, there are alphabetic characters that represent two separate characters.</span></span> <span data-ttu-id="874fc-161">たとえば、複数の言語が文字を使用して`æ`の文字を表す`a`と`e`まとめて表示されます。</span><span class="sxs-lookup"><span data-stu-id="874fc-161">For example, several languages use the character `æ` to represent the characters `a` and `e` when they appear together.</span></span> <span data-ttu-id="874fc-162">`Like`演算子認識は、1 つ digraph 文字と 2 つの個別の文字を同等です。</span><span class="sxs-lookup"><span data-stu-id="874fc-162">The `Like` operator recognizes that the single digraph character and the two individual characters are equivalent.</span></span>  
  
 <span data-ttu-id="874fc-163">Digraph 文字を使用する言語がシステムのロケール設定で指定した場合、いずれかで 1 つ digraph 文字のオカレンス`pattern`または`string`他の文字列で同等の 2 文字シーケンスと一致します。</span><span class="sxs-lookup"><span data-stu-id="874fc-163">When a language that uses a digraph character is specified in the system locale settings, an occurrence of the single digraph character in either `pattern` or `string` matches the equivalent two-character sequence in the other string.</span></span> <span data-ttu-id="874fc-164">同様に、digraph 文字`pattern`角かっこで囲む (単独で、リスト、または範囲内) で同等の 2 文字のシーケンスと一致`string`します。</span><span class="sxs-lookup"><span data-stu-id="874fc-164">Similarly, a digraph character in `pattern` enclosed in brackets (by itself, in a list, or in a range) matches the equivalent two-character sequence in `string`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="874fc-165">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="874fc-165">Overloading</span></span>  
 <span data-ttu-id="874fc-166">`Like`演算子は、*オーバー ロードされた*、つまり、ことクラスまたは構造体を再定義できますその動作はそのクラスまたは構造体の型。</span><span class="sxs-lookup"><span data-stu-id="874fc-166">The `Like` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="874fc-167">コードは、このようなクラスまたは構造体に、この演算子を使用する場合は、再定義された動作を確認ください。</span><span class="sxs-lookup"><span data-stu-id="874fc-167">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="874fc-168">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="874fc-168">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="874fc-169">例</span><span class="sxs-lookup"><span data-stu-id="874fc-169">Example</span></span>  
 <span data-ttu-id="874fc-170">この例では、`Like`をさまざまなパターン文字列を比較する演算子。</span><span class="sxs-lookup"><span data-stu-id="874fc-170">This example uses the `Like` operator to compare strings to various patterns.</span></span> <span data-ttu-id="874fc-171">移動し、結果を`Boolean`各文字列がパターンを満たすかどうかを示す変数。</span><span class="sxs-lookup"><span data-stu-id="874fc-171">The results go into a `Boolean` variable indicating whether each string satisfies the pattern.</span></span>  
  
 [!code-vb[VbVbalrOperators#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="874fc-172">関連項目</span><span class="sxs-lookup"><span data-stu-id="874fc-172">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.InStr%2A>
- <xref:Microsoft.VisualBasic.Strings.StrComp%2A>
- [<span data-ttu-id="874fc-173">比較演算子</span><span class="sxs-lookup"><span data-stu-id="874fc-173">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="874fc-174">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="874fc-174">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="874fc-175">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="874fc-175">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="874fc-176">Option Compare ステートメント</span><span class="sxs-lookup"><span data-stu-id="874fc-176">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [<span data-ttu-id="874fc-177">演算子および式</span><span class="sxs-lookup"><span data-stu-id="874fc-177">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="874fc-178">方法: 文字列をパターンに一致します。</span><span class="sxs-lookup"><span data-stu-id="874fc-178">How to: Match a String against a Pattern</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md)
