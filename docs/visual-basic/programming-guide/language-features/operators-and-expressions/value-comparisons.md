---
title: 値の比較
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
ms.openlocfilehash: f766eaaada486a0f70838bafb754d25070ff4174
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346286"
---
# <a name="value-comparisons-visual-basic"></a><span data-ttu-id="a8b77-102">値の比較 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8b77-102">Value Comparisons (Visual Basic)</span></span>
<span data-ttu-id="a8b77-103">比較演算子を使用すると、数値変数の値を比較する式を作成できます。</span><span class="sxs-lookup"><span data-stu-id="a8b77-103">Comparison operators can be used to construct expressions that compare the values of numeric variables.</span></span> <span data-ttu-id="a8b77-104">これらの式は、比較が true であるか false であるかに基づいて、`Boolean` 値を返します。</span><span class="sxs-lookup"><span data-stu-id="a8b77-104">These expressions return a `Boolean` value based on whether the comparison is true or false.</span></span> <span data-ttu-id="a8b77-105">このような式の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a8b77-105">Examples of such an expression are as follows.</span></span>  
  
 `45 > 26`  
  
 `26 > 45`  
  
 <span data-ttu-id="a8b77-106">最初の式は `True`に評価されます。45が26を超えるためです。</span><span class="sxs-lookup"><span data-stu-id="a8b77-106">The first expression evaluates to `True`, because 45 is greater than 26.</span></span> <span data-ttu-id="a8b77-107">2番目の例は `False`に評価されます。これは、26が45を超えていないためです。</span><span class="sxs-lookup"><span data-stu-id="a8b77-107">The second example evaluates to `False`, because 26 is not greater than 45.</span></span>  
  
 <span data-ttu-id="a8b77-108">この方法では、数値式を比較することもできます。</span><span class="sxs-lookup"><span data-stu-id="a8b77-108">You can also compare numeric expressions in this fashion.</span></span> <span data-ttu-id="a8b77-109">比較する式は、次の例のように、複雑な式にすることができます。</span><span class="sxs-lookup"><span data-stu-id="a8b77-109">The expressions you compare can themselves be complex expressions, as in the following example.</span></span>  
  
 `x / 45 * (y +17) >= System.Math.Sqrt(z) / (p - (x * 16))`  
  
 <span data-ttu-id="a8b77-110">前の複合式には、リテラル、変数、および関数呼び出しが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a8b77-110">The preceding complex expression includes literals, variables, and function calls.</span></span> <span data-ttu-id="a8b77-111">比較演算子の両側の式が評価され、結果の値が `>=` 比較演算子を使用して比較されます。</span><span class="sxs-lookup"><span data-stu-id="a8b77-111">The expressions on both sides of the comparison operator are evaluated, and the resulting values are then compared using the `>=` comparison operator.</span></span> <span data-ttu-id="a8b77-112">左辺の式の値が、右側の式の値以上の場合、式全体が `True`に評価されますが、それ以外の場合は、`False`として評価されます。</span><span class="sxs-lookup"><span data-stu-id="a8b77-112">If the value of the expression on the left side is greater than or equal to the value of the expression on the right, the entire expression evaluates to `True`; otherwise, it evaluates to `False`.</span></span>  
  
 <span data-ttu-id="a8b77-113">値を比較する式は、次の例に示すように、`If...Then` の構造で最もよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="a8b77-113">Expressions that compare values are most commonly used in `If...Then` constructions, as in the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#84)]  
  
 <span data-ttu-id="a8b77-114">`=` 記号は、代入演算子でもあり、比較演算子でもあります。</span><span class="sxs-lookup"><span data-stu-id="a8b77-114">The `=` sign is a comparison operator as well as an assignment operator.</span></span> <span data-ttu-id="a8b77-115">次の例に示すように、比較演算子として使用すると、左側の値が右側の値と等しいかどうかが評価されます。</span><span class="sxs-lookup"><span data-stu-id="a8b77-115">When used as a comparison operator, it evaluates whether the value on the left is equal to the value on the right, as shown in the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#85](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#85)]  
  
 <span data-ttu-id="a8b77-116">また、`If`、`While`、`Loop`、または `ElseIf` のステートメントなどの `Boolean` 値が必要な場合や、`Boolean` 変数に値を割り当てたり渡したりする場合は、比較式を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="a8b77-116">You can also use a comparison expression anywhere a `Boolean` value is needed, such as in an `If`, `While`, `Loop`, or `ElseIf` statement, or when assigning to or passing a value to a `Boolean` variable.</span></span> <span data-ttu-id="a8b77-117">次の例では、比較式によって返される値が `Boolean` 変数に代入されます。</span><span class="sxs-lookup"><span data-stu-id="a8b77-117">In the following example, the value returned by the comparison expression is assigned to a `Boolean` variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#86](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#86)]  
  
## <a name="see-also"></a><span data-ttu-id="a8b77-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="a8b77-118">See also</span></span>

- [<span data-ttu-id="a8b77-119">ブール式</span><span class="sxs-lookup"><span data-stu-id="a8b77-119">Boolean Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [<span data-ttu-id="a8b77-120">演算子および式</span><span class="sxs-lookup"><span data-stu-id="a8b77-120">Operators and Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="a8b77-121">Visual Basic の比較演算子</span><span class="sxs-lookup"><span data-stu-id="a8b77-121">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="a8b77-122">方法 : 数値を計算する</span><span class="sxs-lookup"><span data-stu-id="a8b77-122">How to: Calculate Numeric Values</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)
- [<span data-ttu-id="a8b77-123">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="a8b77-123">Operator Precedence in Visual Basic</span></span>](../../../../visual-basic/language-reference/operators/operator-precedence.md)
