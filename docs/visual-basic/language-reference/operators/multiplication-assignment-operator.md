---
title: '*= 演算子 (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.*=
helpviewer_keywords:
- operator *=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '*= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 96c86509-6eb8-4682-8226-3852e049376f
ms.openlocfilehash: d672ac147a4d7b2c21f4fcb7ee6cdf91b8b4924b
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965333"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="8e1eb-102">\*= 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8e1eb-102">\*= Operator (Visual Basic)</span></span>
<span data-ttu-id="8e1eb-103">式の値で変数またはプロパティの値を乗算し、結果を変数またはプロパティに代入します。</span><span class="sxs-lookup"><span data-stu-id="8e1eb-103">Multiplies the value of a variable or property by the value of an expression and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e1eb-104">構文</span><span class="sxs-lookup"><span data-stu-id="8e1eb-104">Syntax</span></span>  
  
```  
variableorproperty *= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="8e1eb-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="8e1eb-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="8e1eb-106">必須。</span><span class="sxs-lookup"><span data-stu-id="8e1eb-106">Required.</span></span> <span data-ttu-id="8e1eb-107">任意の数値型の変数またはプロパティ。</span><span class="sxs-lookup"><span data-stu-id="8e1eb-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="8e1eb-108">必須。</span><span class="sxs-lookup"><span data-stu-id="8e1eb-108">Required.</span></span> <span data-ttu-id="8e1eb-109">任意の数式。</span><span class="sxs-lookup"><span data-stu-id="8e1eb-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e1eb-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="8e1eb-110">Remarks</span></span>  
 <span data-ttu-id="8e1eb-111">左側にある要素、`*=`演算子は、単純なスカラー変数、プロパティ、または配列の要素。</span><span class="sxs-lookup"><span data-stu-id="8e1eb-111">The element on the left side of the `*=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="8e1eb-112">変数またはプロパティにすることはできません[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)します。</span><span class="sxs-lookup"><span data-stu-id="8e1eb-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="8e1eb-113">`*=`演算子 (演算子の右側にある) の式の値を変数または (演算子の左側にある) のプロパティの値によって最初に乗算します。</span><span class="sxs-lookup"><span data-stu-id="8e1eb-113">The `*=` operator first multiplies the value of the expression (on the right-hand side of the operator) by the value of the variable or property (on the left-hand side of the operator).</span></span> <span data-ttu-id="8e1eb-114">演算子は、変数またはプロパティに、その操作の結果を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="8e1eb-114">The operator then assigns the result of that operation to the variable or property.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="8e1eb-115">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="8e1eb-115">Overloading</span></span>  
 <span data-ttu-id="8e1eb-116">[\* 演算子](../../../visual-basic/language-reference/operators/multiplication-operator.md)できます*オーバー ロードされた*、つまり、ことクラスまたは構造体を再定義できますその動作はそのクラスまたは構造体の型。</span><span class="sxs-lookup"><span data-stu-id="8e1eb-116">The [\* Operator](../../../visual-basic/language-reference/operators/multiplication-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="8e1eb-117">オーバー ロード、`*`演算子の動作に影響、`*=`演算子。</span><span class="sxs-lookup"><span data-stu-id="8e1eb-117">Overloading the `*` operator affects the behavior of the `*=` operator.</span></span> <span data-ttu-id="8e1eb-118">コードで使用する場合`*=`クラスまたは構造体をオーバー ロードで`*`、再定義された動作を確認してください。</span><span class="sxs-lookup"><span data-stu-id="8e1eb-118">If your code uses `*=` on a class or structure that overloads `*`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="8e1eb-119">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e1eb-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e1eb-120">例</span><span class="sxs-lookup"><span data-stu-id="8e1eb-120">Example</span></span>  
 <span data-ttu-id="8e1eb-121">次の例では、`*=`演算子を 1 つ`Integer`秒と、その結果、最初の変数を割り当てるのでは、変数。</span><span class="sxs-lookup"><span data-stu-id="8e1eb-121">The following example uses the `*=` operator to multiply one `Integer` variable by a second and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="8e1eb-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="8e1eb-122">See also</span></span>
- [<span data-ttu-id="8e1eb-123">\* 演算子</span><span class="sxs-lookup"><span data-stu-id="8e1eb-123">\* Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-operator.md)
- [<span data-ttu-id="8e1eb-124">代入演算子</span><span class="sxs-lookup"><span data-stu-id="8e1eb-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="8e1eb-125">算術演算子</span><span class="sxs-lookup"><span data-stu-id="8e1eb-125">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="8e1eb-126">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="8e1eb-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="8e1eb-127">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="8e1eb-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="8e1eb-128">ステートメント</span><span class="sxs-lookup"><span data-stu-id="8e1eb-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
