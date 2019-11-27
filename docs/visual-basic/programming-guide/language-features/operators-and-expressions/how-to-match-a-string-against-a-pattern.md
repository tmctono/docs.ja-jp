---
title: '方法 : 文字列がパターンに一致するかを調べる'
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
ms.openlocfilehash: 49328a72c2cff78b8fe13ca73209d224495ad7a1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343635"
---
# <a name="how-to-match-a-string-against-a-pattern-visual-basic"></a><span data-ttu-id="64329-102">方法: 文字列がパターンに一致するかどうかを調べる (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="64329-102">How to: Match a String against a Pattern (Visual Basic)</span></span>

<span data-ttu-id="64329-103">[文字列データ型](../../../../visual-basic/language-reference/data-types/string-data-type.md)の式がパターンを満たすかどうかを確認するには、 [Like 演算子](../../../../visual-basic/language-reference/operators/like-operator.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="64329-103">If you want to find out if an expression of the [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md) satisfies a pattern, then you can use the [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md).</span></span>

<span data-ttu-id="64329-104">`Like` は2つのオペランドを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="64329-104">`Like` takes two operands.</span></span> <span data-ttu-id="64329-105">左オペランドは文字列式で、右オペランドは照合に使用されるパターンを含む文字列です。</span><span class="sxs-lookup"><span data-stu-id="64329-105">The left operand is a string expression, and the right operand is a string containing the pattern to be used for matching.</span></span> <span data-ttu-id="64329-106">`Like` は、文字列式がパターンを満たすかどうかを示す `Boolean` 値を返します。</span><span class="sxs-lookup"><span data-stu-id="64329-106">`Like` returns a `Boolean` value indicating whether the string expression satisfies the pattern.</span></span>

<span data-ttu-id="64329-107">文字列式の各文字は、特定の文字、ワイルドカード文字、文字リスト、または文字範囲に対して一致させることができます。</span><span class="sxs-lookup"><span data-stu-id="64329-107">You can match each character in the string expression against a specific character, a wildcard character, a character list, or a character range.</span></span> <span data-ttu-id="64329-108">パターン文字列内の仕様の位置は、文字列式で一致する文字の位置に対応します。</span><span class="sxs-lookup"><span data-stu-id="64329-108">The positions of the specifications in the pattern string correspond to the positions of the characters to be matched in the string expression.</span></span>

## <a name="to-match-a-character-in-the-string-expression-against-a-specific-character"></a><span data-ttu-id="64329-109">文字列式の文字を特定の文字に一致させるには</span><span class="sxs-lookup"><span data-stu-id="64329-109">To match a character in the string expression against a specific character</span></span>

<span data-ttu-id="64329-110">特定の文字をパターン文字列に直接配置します。</span><span class="sxs-lookup"><span data-stu-id="64329-110">Put the specific character directly in the pattern string.</span></span> <span data-ttu-id="64329-111">一部の特殊文字は、角かっこ (`[ ]`) で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="64329-111">Certain special characters must be enclosed in brackets (`[ ]`).</span></span> <span data-ttu-id="64329-112">詳細については、「 [Like 演算子](../../../../visual-basic/language-reference/operators/like-operator.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64329-112">For more information, see [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md).</span></span>

<span data-ttu-id="64329-113">次の例では、`myString` が単一の文字 `H`で構成されているかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="64329-113">The following example tests whether `myString` consists exactly of the single character `H`.</span></span>

[!code-vb[VbVbalrOperators#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#70)]

## <a name="to-match-a-character-in-the-string-expression-against-a-wildcard-character"></a><span data-ttu-id="64329-114">文字列式の文字をワイルドカード文字に一致させるには</span><span class="sxs-lookup"><span data-stu-id="64329-114">To match a character in the string expression against a wildcard character</span></span>

<span data-ttu-id="64329-115">パターン文字列に疑問符 (`?`) を入力します。</span><span class="sxs-lookup"><span data-stu-id="64329-115">Put a question mark (`?`) in the pattern string.</span></span> <span data-ttu-id="64329-116">この位置にある有効な文字によって、一致が成功します。</span><span class="sxs-lookup"><span data-stu-id="64329-116">Any valid character in this position makes a successful match.</span></span>

<span data-ttu-id="64329-117">次の例では、`myString` が1つの `W` 文字で構成されているかどうかをテストし、その後に任意の値のちょうど2文字を指定します。</span><span class="sxs-lookup"><span data-stu-id="64329-117">The following example tests whether `myString` consists of the single character `W` followed by exactly two characters of any values.</span></span>

[!code-vb[VbVbalrOperators#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#71)]

## <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters"></a><span data-ttu-id="64329-118">文字列式の文字を文字の一覧に一致させるには</span><span class="sxs-lookup"><span data-stu-id="64329-118">To match a character in the string expression against a list of characters</span></span>

<span data-ttu-id="64329-119">パターン文字列に角かっこ (`[ ]`) を挿入し、角かっこ内に文字の一覧を挿入します。</span><span class="sxs-lookup"><span data-stu-id="64329-119">Put brackets (`[ ]`) in the pattern string, and inside the brackets put the list of characters.</span></span> <span data-ttu-id="64329-120">文字をコンマまたは他の区切り記号で区切ることは避けてください。</span><span class="sxs-lookup"><span data-stu-id="64329-120">Do not separate the characters with commas or any other separator.</span></span> <span data-ttu-id="64329-121">リスト内の任意の1文字が、一致と見なされます。</span><span class="sxs-lookup"><span data-stu-id="64329-121">Any single character in the list makes a successful match.</span></span>

<span data-ttu-id="64329-122">次の例では、`myString` が有効な文字で構成されているかどうかをテストし、その後に `A`、`C`、または `E`の文字の1つだけを指定します。</span><span class="sxs-lookup"><span data-stu-id="64329-122">The following example tests whether `myString` consists of any valid character followed by exactly one of the characters `A`, `C`, or `E`.</span></span>

[!code-vb[VbVbalrOperators#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#72)]

<span data-ttu-id="64329-123">この照合では大文字と小文字が区別されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="64329-123">Note that this match is case-sensitive.</span></span>

## <a name="to-match-a-character-in-the-string-expression-against-a-range-of-characters"></a><span data-ttu-id="64329-124">文字列式の文字を文字の範囲に一致させるには</span><span class="sxs-lookup"><span data-stu-id="64329-124">To match a character in the string expression against a range of characters</span></span>

<span data-ttu-id="64329-125">パターン文字列に角かっこ (`[ ]`) を挿入し、角かっこ内には、ハイフン (`–`) で区切られた範囲内の最低文字と最高文字を格納します。</span><span class="sxs-lookup"><span data-stu-id="64329-125">Put brackets (`[ ]`) in the pattern string, and inside the brackets put the lowest and highest characters in the range, separated by a hyphen (`–`).</span></span> <span data-ttu-id="64329-126">範囲内の任意の1文字が、一致と見なされます。</span><span class="sxs-lookup"><span data-stu-id="64329-126">Any single character within the range makes a successful match.</span></span>

<span data-ttu-id="64329-127">次の例では、`myString` が文字 `num` で構成されているかどうかをテストし、その後に `i`、`j`、`k`、`l`、`m`、または `n`の文字の1つだけを指定します。</span><span class="sxs-lookup"><span data-stu-id="64329-127">The following example tests whether `myString` consists of the characters `num` followed by exactly one of the characters `i`, `j`, `k`, `l`, `m`, or `n`.</span></span>

[!code-vb[VbVbalrOperators#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#73)]

<span data-ttu-id="64329-128">この照合では大文字と小文字が区別されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="64329-128">Note that this match is case-sensitive.</span></span>

## <a name="matching-empty-strings"></a><span data-ttu-id="64329-129">一致 (空の文字列を)</span><span class="sxs-lookup"><span data-stu-id="64329-129">Matching Empty Strings</span></span>

<span data-ttu-id="64329-130">`Like` は、シーケンスの `[]` を長さ0の文字列 (`""`) として扱います。</span><span class="sxs-lookup"><span data-stu-id="64329-130">`Like` treats the sequence `[]` as a zero-length string (`""`).</span></span> <span data-ttu-id="64329-131">`[]` を使用すると、文字列式全体が空であるかどうかをテストできますが、文字列式内の特定の位置が空かどうかをテストすることはできません。</span><span class="sxs-lookup"><span data-stu-id="64329-131">You can use `[]` to test whether the entire string expression is empty, but you cannot use it to test if a particular position in the string expression is empty.</span></span> <span data-ttu-id="64329-132">テストする必要があるオプションの1つが空の位置である場合は、`Like` を複数回使用できます。</span><span class="sxs-lookup"><span data-stu-id="64329-132">If an empty position is one of the options you need to test for, you can use `Like` more than once.</span></span>

### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters-or-no-character"></a><span data-ttu-id="64329-133">文字列式の文字を文字のリストまたは文字の一覧と一致させるには</span><span class="sxs-lookup"><span data-stu-id="64329-133">To match a character in the string expression against a list of characters or no character</span></span>

1. <span data-ttu-id="64329-134">同じ文字列式で `Like` 演算子を2回呼び出し、 [Or 演算子](../../../../visual-basic/language-reference/operators/or-operator.md)または[OrElse 演算子](../../../../visual-basic/language-reference/operators/orelse-operator.md)のいずれかを使用して2つの呼び出しを接続します。</span><span class="sxs-lookup"><span data-stu-id="64329-134">Call the `Like` operator twice on the same string expression, and connect the two calls with either the [Or Operator](../../../../visual-basic/language-reference/operators/or-operator.md) or the [OrElse Operator](../../../../visual-basic/language-reference/operators/orelse-operator.md).</span></span>

2. <span data-ttu-id="64329-135">最初の `Like` 句のパターン文字列には、文字リストを角かっこ (`[ ]`) で囲んで指定します。</span><span class="sxs-lookup"><span data-stu-id="64329-135">In the pattern string for the first `Like` clause, include the character list, enclosed in brackets (`[ ]`).</span></span>

3. <span data-ttu-id="64329-136">2番目の `Like` 句のパターン文字列では、対象の位置に文字を入れないでください。</span><span class="sxs-lookup"><span data-stu-id="64329-136">In the pattern string for the second `Like` clause, do not put any character at the position in question.</span></span>

    <span data-ttu-id="64329-137">次の例では、7桁の電話番号を、正確に3桁の数字、その後にスペース、ハイフン (`–`)、ピリオド (`.`)、または文字をまったく含まない `phoneNum` をテストします。</span><span class="sxs-lookup"><span data-stu-id="64329-137">The following example tests the seven-digit telephone number `phoneNum` for exactly three numeric digits, followed by a space, a hyphen (`–`), a period (`.`), or no character at all, followed by exactly four numeric digits.</span></span>

    [!code-vb[VbVbalrOperators#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#74)]

## <a name="see-also"></a><span data-ttu-id="64329-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="64329-138">See also</span></span>

- [<span data-ttu-id="64329-139">比較演算子</span><span class="sxs-lookup"><span data-stu-id="64329-139">Comparison Operators</span></span>](../../../../visual-basic/language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="64329-140">演算子および式</span><span class="sxs-lookup"><span data-stu-id="64329-140">Operators and Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="64329-141">Like 演算子</span><span class="sxs-lookup"><span data-stu-id="64329-141">Like Operator</span></span>](../../../../visual-basic/language-reference/operators/like-operator.md)
- [<span data-ttu-id="64329-142">String データ型</span><span class="sxs-lookup"><span data-stu-id="64329-142">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)
