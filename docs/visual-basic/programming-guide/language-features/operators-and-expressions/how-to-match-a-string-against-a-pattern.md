---
title: '方法: (Visual Basic) パターンとの比較の文字列と一致します。'
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
ms.openlocfilehash: e5eb6bd5b5e7b2f0c3692c0fa2431a0b8f295299
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64649725"
---
# <a name="how-to-match-a-string-against-a-pattern-visual-basic"></a><span data-ttu-id="60856-102">方法: (Visual Basic) パターンとの比較の文字列と一致します。</span><span class="sxs-lookup"><span data-stu-id="60856-102">How to: Match a String against a Pattern (Visual Basic)</span></span>
<span data-ttu-id="60856-103">式かどうかを検索する場合、[文字列データ型](../../../../visual-basic/language-reference/data-types/string-data-type.md)を使用して、パターンを満たす、 [Like 演算子](../../../../visual-basic/language-reference/operators/like-operator.md)します。</span><span class="sxs-lookup"><span data-stu-id="60856-103">If you want to find out if an expression of the [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md) satisfies a pattern, then you can use the [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md).</span></span>  
  
 <span data-ttu-id="60856-104">`Like` 2 つのオペランドを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="60856-104">`Like` takes two operands.</span></span> <span data-ttu-id="60856-105">左のオペランドは、文字列式であり、右のオペランドが照合に使用するパターンを含む文字列。</span><span class="sxs-lookup"><span data-stu-id="60856-105">The left operand is a string expression, and the right operand is a string containing the pattern to be used for matching.</span></span> <span data-ttu-id="60856-106">`Like` 返します、`Boolean`文字列式が、パターンを満たすかどうかを示す値。</span><span class="sxs-lookup"><span data-stu-id="60856-106">`Like` returns a `Boolean` value indicating whether the string expression satisfies the pattern.</span></span>  
  
 <span data-ttu-id="60856-107">特定の文字、ワイルドカード文字、文字のリスト、または文字の範囲に対して文字列式内の各文字と一致することができます。</span><span class="sxs-lookup"><span data-stu-id="60856-107">You can match each character in the string expression against a specific character, a wildcard character, a character list, or a character range.</span></span> <span data-ttu-id="60856-108">仕様パターン文字列内の位置は、文字列式に一致する文字の位置に対応します。</span><span class="sxs-lookup"><span data-stu-id="60856-108">The positions of the specifications in the pattern string correspond to the positions of the characters to be matched in the string expression.</span></span>  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-specific-character"></a><span data-ttu-id="60856-109">特定の文字の文字列式での文字と一致するには</span><span class="sxs-lookup"><span data-stu-id="60856-109">To match a character in the string expression against a specific character</span></span>  
  
- <span data-ttu-id="60856-110">特定の文字をパターン文字列に直接配置します。</span><span class="sxs-lookup"><span data-stu-id="60856-110">Put the specific character directly in the pattern string.</span></span> <span data-ttu-id="60856-111">特定の特殊文字は、角かっこで囲む必要があります (`[ ]`)。</span><span class="sxs-lookup"><span data-stu-id="60856-111">Certain special characters must be enclosed in brackets (`[ ]`).</span></span> <span data-ttu-id="60856-112">詳細については、次を参照してください。 [Like 演算子](../../../../visual-basic/language-reference/operators/like-operator.md)します。</span><span class="sxs-lookup"><span data-stu-id="60856-112">For more information, see [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md).</span></span>  
  
     <span data-ttu-id="60856-113">次の例をテストするかどうか`myString`1 文字だけで構成されます`H`します。</span><span class="sxs-lookup"><span data-stu-id="60856-113">The following example tests whether `myString` consists exactly of the single character `H`.</span></span>  
  
     [!code-vb[VbVbalrOperators#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#70)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-wildcard-character"></a><span data-ttu-id="60856-114">ワイルドカード文字の文字列式の文字と一致するには</span><span class="sxs-lookup"><span data-stu-id="60856-114">To match a character in the string expression against a wildcard character</span></span>  
  
- <span data-ttu-id="60856-115">疑問符 () の配置 (`?`) パターン文字列にします。</span><span class="sxs-lookup"><span data-stu-id="60856-115">Put a question mark (`?`) in the pattern string.</span></span> <span data-ttu-id="60856-116">この位置に任意の有効な文字は、検索が成功します。</span><span class="sxs-lookup"><span data-stu-id="60856-116">Any valid character in this position makes a successful match.</span></span>  
  
     <span data-ttu-id="60856-117">次の例のテストするかどうか`myString`1 文字から成る`W`の後ろに任意の値の 2 つの文字。</span><span class="sxs-lookup"><span data-stu-id="60856-117">The following example tests whether `myString` consists of the single character `W` followed by exactly two characters of any values.</span></span>  
  
     [!code-vb[VbVbalrOperators#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#71)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters"></a><span data-ttu-id="60856-118">文字の一覧に対して、文字列式での文字と一致するには</span><span class="sxs-lookup"><span data-stu-id="60856-118">To match a character in the string expression against a list of characters</span></span>  
  
- <span data-ttu-id="60856-119">角かっこを配置 (`[ ]`) で、パターン文字列とかっこ文字の一覧に格納します。</span><span class="sxs-lookup"><span data-stu-id="60856-119">Put brackets (`[ ]`) in the pattern string, and inside the brackets put the list of characters.</span></span> <span data-ttu-id="60856-120">コンマまたはその他の任意の区切り記号の文字を分離されません。</span><span class="sxs-lookup"><span data-stu-id="60856-120">Do not separate the characters with commas or any other separator.</span></span> <span data-ttu-id="60856-121">任意の 1 文字の一覧では、検索が成功します。</span><span class="sxs-lookup"><span data-stu-id="60856-121">Any single character in the list makes a successful match.</span></span>  
  
     <span data-ttu-id="60856-122">次の例のテストかどうか`myString`続く文字を 1 つの有効な任意の文字から成る`A`、 `C`、または`E`します。</span><span class="sxs-lookup"><span data-stu-id="60856-122">The following example tests whether `myString` consists of any valid character followed by exactly one of the characters `A`, `C`, or `E`.</span></span>  
  
     [!code-vb[VbVbalrOperators#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#72)]  
  
     <span data-ttu-id="60856-123">この照合の小文字が区別されるに注意してください。</span><span class="sxs-lookup"><span data-stu-id="60856-123">Note that this match is case-sensitive.</span></span>  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-range-of-characters"></a><span data-ttu-id="60856-124">文字の範囲に対して文字列式での文字と一致するには</span><span class="sxs-lookup"><span data-stu-id="60856-124">To match a character in the string expression against a range of characters</span></span>  
  
- <span data-ttu-id="60856-125">角かっこを配置 (`[ ]`) パターン文字列、および最低と最高の文字の範囲に、かっこ内では、ハイフンで区切られた (`–`)。</span><span class="sxs-lookup"><span data-stu-id="60856-125">Put brackets (`[ ]`) in the pattern string, and inside the brackets put the lowest and highest characters in the range, separated by a hyphen (`–`).</span></span> <span data-ttu-id="60856-126">範囲内の任意の 1 文字では、成功した一致。</span><span class="sxs-lookup"><span data-stu-id="60856-126">Any single character within the range makes a successful match.</span></span>  
  
     <span data-ttu-id="60856-127">次の例のテストかどうか`myString`文字から成る`num`文字 1 個続く`i`、 `j`、 `k`、 `l`、 `m`、または`n`します。</span><span class="sxs-lookup"><span data-stu-id="60856-127">The following example tests whether `myString` consists of the characters `num` followed by exactly one of the characters `i`, `j`, `k`, `l`, `m`, or `n`.</span></span>  
  
     [!code-vb[VbVbalrOperators#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#73)]  
  
     <span data-ttu-id="60856-128">この照合の小文字が区別されるに注意してください。</span><span class="sxs-lookup"><span data-stu-id="60856-128">Note that this match is case-sensitive.</span></span>  
  
## <a name="matching-empty-strings"></a><span data-ttu-id="60856-129">空の文字列に一致します。</span><span class="sxs-lookup"><span data-stu-id="60856-129">Matching Empty Strings</span></span>  
 <span data-ttu-id="60856-130">`Like` シーケンス処理`[]`長さ 0 の文字列として (`""`)。</span><span class="sxs-lookup"><span data-stu-id="60856-130">`Like` treats the sequence `[]` as a zero-length string (`""`).</span></span> <span data-ttu-id="60856-131">使用することができます`[]`文字列全体の式が空では、文字列式で特定の位置が空かどうかを使用することはできないかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="60856-131">You can use `[]` to test whether the entire string expression is empty, but you cannot use it to test if a particular position in the string expression is empty.</span></span> <span data-ttu-id="60856-132">空の位置が、オプションのいずれかである場合は、テストするには、使用できる必要があります。 `Like` 2 回以上。</span><span class="sxs-lookup"><span data-stu-id="60856-132">If an empty position is one of the options you need to test for, you can use `Like` more than once.</span></span>  
  
#### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters-or-no-character"></a><span data-ttu-id="60856-133">文字または文字の一覧に対して、文字列式での文字と一致するには</span><span class="sxs-lookup"><span data-stu-id="60856-133">To match a character in the string expression against a list of characters or no character</span></span>  
  
1. <span data-ttu-id="60856-134">呼び出す、`Like`演算子を 2 回に同じ文字列式、および 2 つの呼び出しのいずれかで接続、[または演算子](../../../../visual-basic/language-reference/operators/or-operator.md)または[OrElse 演算子](../../../../visual-basic/language-reference/operators/orelse-operator.md)します。</span><span class="sxs-lookup"><span data-stu-id="60856-134">Call the `Like` operator twice on the same string expression, and connect the two calls with either the [Or Operator](../../../../visual-basic/language-reference/operators/or-operator.md) or the [OrElse Operator](../../../../visual-basic/language-reference/operators/orelse-operator.md).</span></span>  
  
2. <span data-ttu-id="60856-135">最初のパターン文字列に`Like`句では、角かっこで囲まれた、文字の一覧が含まれます (`[ ]`)。</span><span class="sxs-lookup"><span data-stu-id="60856-135">In the pattern string for the first `Like` clause, include the character list, enclosed in brackets (`[ ]`).</span></span>  
  
3. <span data-ttu-id="60856-136">2 つ目のパターン文字列内`Like`句では、配置しない任意の文字位置にある問題です。</span><span class="sxs-lookup"><span data-stu-id="60856-136">In the pattern string for the second `Like` clause, do not put any character at the position in question.</span></span>  
  
     <span data-ttu-id="60856-137">次の例は、7 桁の電話番号をテスト`phoneNum`の 3 桁の数字の後にスペース、ハイフン (`–`)、ピリオド (`.`)、または文字、後ろにないに 4 桁の数値。</span><span class="sxs-lookup"><span data-stu-id="60856-137">The following example tests the seven-digit telephone number `phoneNum` for exactly three numeric digits, followed by a space, a hyphen (`–`), a period (`.`), or no character at all, followed by exactly four numeric digits.</span></span>  
  
     [!code-vb[VbVbalrOperators#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#74)]  
  
## <a name="see-also"></a><span data-ttu-id="60856-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="60856-138">See also</span></span>

- [<span data-ttu-id="60856-139">比較演算子</span><span class="sxs-lookup"><span data-stu-id="60856-139">Comparison Operators</span></span>](../../../../visual-basic/language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="60856-140">演算子および式</span><span class="sxs-lookup"><span data-stu-id="60856-140">Operators and Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="60856-141">Like 演算子</span><span class="sxs-lookup"><span data-stu-id="60856-141">Like Operator</span></span>](../../../../visual-basic/language-reference/operators/like-operator.md)
- [<span data-ttu-id="60856-142">String データ型</span><span class="sxs-lookup"><span data-stu-id="60856-142">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)
