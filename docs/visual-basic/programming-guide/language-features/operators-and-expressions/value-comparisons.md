---
title: 値の比較 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], comparing values
- Visual Basic code, operators
- Visual Basic code, expressions
- comparison operators [Visual Basic], comparing expressions
- numeric expressions
- operators [Visual Basic], comparison
- expressions [Visual Basic], comparing
ms.assetid: 60da0c76-9458-4afc-97e9-44a7939c064c
ms.openlocfilehash: 270b226d0a1aa7d08721e6f9ed36d68492685af3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61864392"
---
# <a name="value-comparisons-visual-basic"></a><span data-ttu-id="b4e00-102">値の比較 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b4e00-102">Value Comparisons (Visual Basic)</span></span>
<span data-ttu-id="b4e00-103">比較演算子は、数値変数の値を比較する式を作成できます。</span><span class="sxs-lookup"><span data-stu-id="b4e00-103">Comparison operators can be used to construct expressions that compare the values of numeric variables.</span></span> <span data-ttu-id="b4e00-104">これらの式を返す、`Boolean`比較が true かどうかに基づいて、値または false。</span><span class="sxs-lookup"><span data-stu-id="b4e00-104">These expressions return a `Boolean` value based on whether the comparison is true or false.</span></span> <span data-ttu-id="b4e00-105">このような式の例は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b4e00-105">Examples of such an expression are as follows.</span></span>  
  
 `45 > 26`  
  
 `26 > 45`  
  
 <span data-ttu-id="b4e00-106">最初の式の評価が`True`45 が 26 よりも大きいためです。</span><span class="sxs-lookup"><span data-stu-id="b4e00-106">The first expression evaluates to `True`, because 45 is greater than 26.</span></span> <span data-ttu-id="b4e00-107">2 番目の例を評価する`False`26 は 45 より大きいためです。</span><span class="sxs-lookup"><span data-stu-id="b4e00-107">The second example evaluates to `False`, because 26 is not greater than 45.</span></span>  
  
 <span data-ttu-id="b4e00-108">この方法での数値式を比較することもできます。</span><span class="sxs-lookup"><span data-stu-id="b4e00-108">You can also compare numeric expressions in this fashion.</span></span> <span data-ttu-id="b4e00-109">次の例のように、複雑な式を比較する式をできます自体あります。</span><span class="sxs-lookup"><span data-stu-id="b4e00-109">The expressions you compare can themselves be complex expressions, as in the following example.</span></span>  
  
 `x / 45 * (y +17) >= System.Math.Sqrt(z) / (p - (x * 16))`  
  
 <span data-ttu-id="b4e00-110">上記の複雑な式には、リテラル、変数、および関数呼び出しが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b4e00-110">The preceding complex expression includes literals, variables, and function calls.</span></span> <span data-ttu-id="b4e00-111">比較演算子の両側の式を評価し、結果として得られる値が比較を使用し、`>=`比較演算子。</span><span class="sxs-lookup"><span data-stu-id="b4e00-111">The expressions on both sides of the comparison operator are evaluated, and the resulting values are then compared using the `>=` comparison operator.</span></span> <span data-ttu-id="b4e00-112">左側にある式の値がより大きいか、右の式の値と等しい、全体の式の評価が`True`。 それ以外に評価されます`False`します。</span><span class="sxs-lookup"><span data-stu-id="b4e00-112">If the value of the expression on the left side is greater than or equal to the value of the expression on the right, the entire expression evaluates to `True`; otherwise, it evaluates to `False`.</span></span>  
  
 <span data-ttu-id="b4e00-113">値を比較する式で最もよく使用される`If...Then`構造は、次の例に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="b4e00-113">Expressions that compare values are most commonly used in `If...Then` constructions, as in the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#84)]  
  
 <span data-ttu-id="b4e00-114">`=`符号は、比較演算子と代入演算子。</span><span class="sxs-lookup"><span data-stu-id="b4e00-114">The `=` sign is a comparison operator as well as an assignment operator.</span></span> <span data-ttu-id="b4e00-115">比較演算子として使用する場合は、次の例に示すように、左側の値が、右側の値と等しいかどうかを評価します。</span><span class="sxs-lookup"><span data-stu-id="b4e00-115">When used as a comparison operator, it evaluates whether the value on the left is equal to the value on the right, as shown in the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#85](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#85)]  
  
 <span data-ttu-id="b4e00-116">任意の場所、比較式を使用することもできます。、`Boolean`の値が必要なようにこのような、 `If`、 `While`、 `Loop`、または`ElseIf`ステートメント、またはへの割り当てに値を渡しているか、`Boolean`変数。</span><span class="sxs-lookup"><span data-stu-id="b4e00-116">You can also use a comparison expression anywhere a `Boolean` value is needed, such as in an `If`, `While`, `Loop`, or `ElseIf` statement, or when assigning to or passing a value to a `Boolean` variable.</span></span> <span data-ttu-id="b4e00-117">次の例では、比較式によって返される値が割り当てられている、`Boolean`変数。</span><span class="sxs-lookup"><span data-stu-id="b4e00-117">In the following example, the value returned by the comparison expression is assigned to a `Boolean` variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#86](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#86)]  
  
## <a name="see-also"></a><span data-ttu-id="b4e00-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="b4e00-118">See also</span></span>

- [<span data-ttu-id="b4e00-119">ブール式</span><span class="sxs-lookup"><span data-stu-id="b4e00-119">Boolean Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [<span data-ttu-id="b4e00-120">演算子および式</span><span class="sxs-lookup"><span data-stu-id="b4e00-120">Operators and Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="b4e00-121">Visual Basic における比較演算子</span><span class="sxs-lookup"><span data-stu-id="b4e00-121">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="b4e00-122">方法: 数値を計算します。</span><span class="sxs-lookup"><span data-stu-id="b4e00-122">How to: Calculate Numeric Values</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)
- [<span data-ttu-id="b4e00-123">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="b4e00-123">Operator Precedence in Visual Basic</span></span>](../../../../visual-basic/language-reference/operators/operator-precedence.md)
