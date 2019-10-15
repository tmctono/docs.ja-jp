---
title: '方法: 文字列をパターンと照合する (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- comparison operators [Visual Basic], comparing strings
- pattern matching
- strings [Visual Basic], comparing
- string comparison [Visual Basic], operators
- Visual Basic code, operators
- pattern matching [Visual Basic], string comparison
- string comparison [Visual Basic]
- Like operator [Visual Basic], pattern matching
- pattern matching, empty strings
- operators [Visual Basic], comparison
ms.assetid: 19a83804-b5af-4739-928b-ac93e64e457f
ms.openlocfilehash: 0bac0869d9e319071abb31dd0576edf0450aa198
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71054152"
---
# <a name="how-to-match-a-string-against-a-pattern-visual-basic"></a><span data-ttu-id="bc4d3-102">方法: 文字列をパターンと照合する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bc4d3-102">How to: Match a String against a Pattern (Visual Basic)</span></span>

<span data-ttu-id="bc4d3-103">[文字列データ型](../../../../visual-basic/language-reference/data-types/string-data-type.md)の式がパターンを満たすかどうかを確認するには、 [Like 演算子](../../../../visual-basic/language-reference/operators/like-operator.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="bc4d3-103">If you want to find out if an expression of the [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md) satisfies a pattern, then you can use the [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md).</span></span>

<span data-ttu-id="bc4d3-104">`Like`2つのオペランドを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="bc4d3-104">`Like` takes two operands.</span></span> <span data-ttu-id="bc4d3-105">左オペランドは文字列式で、右オペランドは照合に使用されるパターンを含む文字列です。</span><span class="sxs-lookup"><span data-stu-id="bc4d3-105">The left operand is a string expression, and the right operand is a string containing the pattern to be used for matching.</span></span> <span data-ttu-id="bc4d3-106">`Like`文字列式がパターンを満たすかどうかを示す値を返します。`Boolean`</span><span class="sxs-lookup"><span data-stu-id="bc4d3-106">`Like` returns a `Boolean` value indicating whether the string expression satisfies the pattern.</span></span>

<span data-ttu-id="bc4d3-107">文字列式の各文字は、特定の文字、ワイルドカード文字、文字リスト、または文字範囲に対して一致させることができます。</span><span class="sxs-lookup"><span data-stu-id="bc4d3-107">You can match each character in the string expression against a specific character, a wildcard character, a character list, or a character range.</span></span> <span data-ttu-id="bc4d3-108">パターン文字列内の仕様の位置は、文字列式で一致する文字の位置に対応します。</span><span class="sxs-lookup"><span data-stu-id="bc4d3-108">The positions of the specifications in the pattern string correspond to the positions of the characters to be matched in the string expression.</span></span>

## <a name="to-match-a-character-in-the-string-expression-against-a-specific-character"></a><span data-ttu-id="bc4d3-109">文字列式の文字を特定の文字に一致させるには</span><span class="sxs-lookup"><span data-stu-id="bc4d3-109">To match a character in the string expression against a specific character</span></span>

<span data-ttu-id="bc4d3-110">特定の文字をパターン文字列に直接配置します。</span><span class="sxs-lookup"><span data-stu-id="bc4d3-110">Put the specific character directly in the pattern string.</span></span> <span data-ttu-id="bc4d3-111">特定の特殊文字は、角かっこ (`[ ]`) で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc4d3-111">Certain special characters must be enclosed in brackets (`[ ]`).</span></span> <span data-ttu-id="bc4d3-112">詳細については、「 [Like 演算子](../../../../visual-basic/language-reference/operators/like-operator.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc4d3-112">For more information, see [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md).</span></span>

<span data-ttu-id="bc4d3-113">次の例では`myString` 、が単一の文字`H`で構成されているかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="bc4d3-113">The following example tests whether `myString` consists exactly of the single character `H`.</span></span>

[!code-vb[VbVbalrOperators#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#70)]

## <a name="to-match-a-character-in-the-string-expression-against-a-wildcard-character"></a><span data-ttu-id="bc4d3-114">文字列式の文字をワイルドカード文字に一致させるには</span><span class="sxs-lookup"><span data-stu-id="bc4d3-114">To match a character in the string expression against a wildcard character</span></span>

<span data-ttu-id="bc4d3-115">パターン文字列に疑問符 (`?`) を入力します。</span><span class="sxs-lookup"><span data-stu-id="bc4d3-115">Put a question mark (`?`) in the pattern string.</span></span> <span data-ttu-id="bc4d3-116">この位置にある有効な文字によって、一致が成功します。</span><span class="sxs-lookup"><span data-stu-id="bc4d3-116">Any valid character in this position makes a successful match.</span></span>

<span data-ttu-id="bc4d3-117">次の例では`myString` 、が1つの`W`文字で構成され、その後に値が2文字続くかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="bc4d3-117">The following example tests whether `myString` consists of the single character `W` followed by exactly two characters of any values.</span></span>

[!code-vb[VbVbalrOperators#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#71)]

## <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters"></a><span data-ttu-id="bc4d3-118">文字列式の文字を文字の一覧に一致させるには</span><span class="sxs-lookup"><span data-stu-id="bc4d3-118">To match a character in the string expression against a list of characters</span></span>

<span data-ttu-id="bc4d3-119">パターン文字列に`[ ]`角かっこ () を挿入し、角かっこ内に文字のリストを配置します。</span><span class="sxs-lookup"><span data-stu-id="bc4d3-119">Put brackets (`[ ]`) in the pattern string, and inside the brackets put the list of characters.</span></span> <span data-ttu-id="bc4d3-120">文字をコンマまたは他の区切り記号で区切ることは避けてください。</span><span class="sxs-lookup"><span data-stu-id="bc4d3-120">Do not separate the characters with commas or any other separator.</span></span> <span data-ttu-id="bc4d3-121">リスト内の任意の1文字が、一致と見なされます。</span><span class="sxs-lookup"><span data-stu-id="bc4d3-121">Any single character in the list makes a successful match.</span></span>

<span data-ttu-id="bc4d3-122">次の例では`myString` 、が有効な文字で構成され、 `C`、、 `A`または`E`のいずれかの文字が続くかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="bc4d3-122">The following example tests whether `myString` consists of any valid character followed by exactly one of the characters `A`, `C`, or `E`.</span></span>

[!code-vb[VbVbalrOperators#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#72)]

<span data-ttu-id="bc4d3-123">この照合では大文字と小文字が区別されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="bc4d3-123">Note that this match is case-sensitive.</span></span>

## <a name="to-match-a-character-in-the-string-expression-against-a-range-of-characters"></a><span data-ttu-id="bc4d3-124">文字列式の文字を文字の範囲に一致させるには</span><span class="sxs-lookup"><span data-stu-id="bc4d3-124">To match a character in the string expression against a range of characters</span></span>

<span data-ttu-id="bc4d3-125">パターン文字列に`[ ]`角かっこ () を挿入し、角かっこ内には、ハイフン (`–`) で区切られた範囲内の最低文字と最高文字を指定します。</span><span class="sxs-lookup"><span data-stu-id="bc4d3-125">Put brackets (`[ ]`) in the pattern string, and inside the brackets put the lowest and highest characters in the range, separated by a hyphen (`–`).</span></span> <span data-ttu-id="bc4d3-126">範囲内の任意の1文字が、一致と見なされます。</span><span class="sxs-lookup"><span data-stu-id="bc4d3-126">Any single character within the range makes a successful match.</span></span>

<span data-ttu-id="bc4d3-127">次の例では`myString` 、が、、 `num` 、、 `m`、 `j` `l` `i`のいずれ`k`かの文字が続く文字で構成されているかどうかをテストします。`n`</span><span class="sxs-lookup"><span data-stu-id="bc4d3-127">The following example tests whether `myString` consists of the characters `num` followed by exactly one of the characters `i`, `j`, `k`, `l`, `m`, or `n`.</span></span>

[!code-vb[VbVbalrOperators#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#73)]

<span data-ttu-id="bc4d3-128">この照合では大文字と小文字が区別されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="bc4d3-128">Note that this match is case-sensitive.</span></span>

## <a name="matching-empty-strings"></a><span data-ttu-id="bc4d3-129">一致 (空の文字列を)</span><span class="sxs-lookup"><span data-stu-id="bc4d3-129">Matching Empty Strings</span></span>

<span data-ttu-id="bc4d3-130">`Like`シーケンス`[]`を長さ0の文字列 (`""`) として扱います。</span><span class="sxs-lookup"><span data-stu-id="bc4d3-130">`Like` treats the sequence `[]` as a zero-length string (`""`).</span></span> <span data-ttu-id="bc4d3-131">を使用`[]`すると、文字列式全体が空であるかどうかをテストできますが、文字列式内の特定の位置が空かどうかをテストすることはできません。</span><span class="sxs-lookup"><span data-stu-id="bc4d3-131">You can use `[]` to test whether the entire string expression is empty, but you cannot use it to test if a particular position in the string expression is empty.</span></span> <span data-ttu-id="bc4d3-132">空の位置が、テストする必要があるオプションの1つである場合は`Like` 、を複数回使用できます。</span><span class="sxs-lookup"><span data-stu-id="bc4d3-132">If an empty position is one of the options you need to test for, you can use `Like` more than once.</span></span>

### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters-or-no-character"></a><span data-ttu-id="bc4d3-133">文字列式の文字を文字のリストまたは文字の一覧と一致させるには</span><span class="sxs-lookup"><span data-stu-id="bc4d3-133">To match a character in the string expression against a list of characters or no character</span></span>

1. <span data-ttu-id="bc4d3-134">同じ文字列式で`Like` 演算子を2回呼び出し、[or演算子](../../../../visual-basic/language-reference/operators/or-operator.md)または[OrElse演算子](../../../../visual-basic/language-reference/operators/orelse-operator.md)のいずれかを使用して2つの呼び出しを接続します。</span><span class="sxs-lookup"><span data-stu-id="bc4d3-134">Call the `Like` operator twice on the same string expression, and connect the two calls with either the [Or Operator](../../../../visual-basic/language-reference/operators/or-operator.md) or the [OrElse Operator](../../../../visual-basic/language-reference/operators/orelse-operator.md).</span></span>

2. <span data-ttu-id="bc4d3-135">最初`Like`の句のパターン文字列には、文字リストを角かっこ (`[ ]`) で囲んで指定します。</span><span class="sxs-lookup"><span data-stu-id="bc4d3-135">In the pattern string for the first `Like` clause, include the character list, enclosed in brackets (`[ ]`).</span></span>

3. <span data-ttu-id="bc4d3-136">2番目`Like`の句のパターン文字列では、対象の位置に文字を入れないでください。</span><span class="sxs-lookup"><span data-stu-id="bc4d3-136">In the pattern string for the second `Like` clause, do not put any character at the position in question.</span></span>

    <span data-ttu-id="bc4d3-137">次の例では、正確に3桁`phoneNum`の電話番号をテストし、その後にスペース、ハイフン (`–`)、ピリオド (`.`)、または文字をまったく4桁の数字で指定します。</span><span class="sxs-lookup"><span data-stu-id="bc4d3-137">The following example tests the seven-digit telephone number `phoneNum` for exactly three numeric digits, followed by a space, a hyphen (`–`), a period (`.`), or no character at all, followed by exactly four numeric digits.</span></span>

    [!code-vb[VbVbalrOperators#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#74)]

## <a name="see-also"></a><span data-ttu-id="bc4d3-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="bc4d3-138">See also</span></span>

- [<span data-ttu-id="bc4d3-139">比較演算子</span><span class="sxs-lookup"><span data-stu-id="bc4d3-139">Comparison Operators</span></span>](../../../../visual-basic/language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="bc4d3-140">演算子および式</span><span class="sxs-lookup"><span data-stu-id="bc4d3-140">Operators and Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="bc4d3-141">Like 演算子</span><span class="sxs-lookup"><span data-stu-id="bc4d3-141">Like Operator</span></span>](../../../../visual-basic/language-reference/operators/like-operator.md)
- [<span data-ttu-id="bc4d3-142">String データ型</span><span class="sxs-lookup"><span data-stu-id="bc4d3-142">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)
