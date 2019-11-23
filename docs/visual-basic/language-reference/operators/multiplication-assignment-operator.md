---
title: '*= 演算子'
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
ms.openlocfilehash: 4b60fa44a92bff683e13f850da025d7fe753618d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349783"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="ed4bd-102">\*= 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed4bd-102">\*= Operator (Visual Basic)</span></span>
<span data-ttu-id="ed4bd-103">Multiplies the value of a variable or property by the value of an expression and assigns the result to the variable or property.</span><span class="sxs-lookup"><span data-stu-id="ed4bd-103">Multiplies the value of a variable or property by the value of an expression and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed4bd-104">構文</span><span class="sxs-lookup"><span data-stu-id="ed4bd-104">Syntax</span></span>  
  
```vb  
variableorproperty *= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="ed4bd-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="ed4bd-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="ed4bd-106">必須です。</span><span class="sxs-lookup"><span data-stu-id="ed4bd-106">Required.</span></span> <span data-ttu-id="ed4bd-107">Any numeric variable or property.</span><span class="sxs-lookup"><span data-stu-id="ed4bd-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="ed4bd-108">必須です。</span><span class="sxs-lookup"><span data-stu-id="ed4bd-108">Required.</span></span> <span data-ttu-id="ed4bd-109">任意の数式。</span><span class="sxs-lookup"><span data-stu-id="ed4bd-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ed4bd-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="ed4bd-110">Remarks</span></span>  
 <span data-ttu-id="ed4bd-111">The element on the left side of the `*=` operator can be a simple scalar variable, a property, or an element of an array.</span><span class="sxs-lookup"><span data-stu-id="ed4bd-111">The element on the left side of the `*=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="ed4bd-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="ed4bd-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="ed4bd-113">The `*=` operator first multiplies the value of the expression (on the right-hand side of the operator) by the value of the variable or property (on the left-hand side of the operator).</span><span class="sxs-lookup"><span data-stu-id="ed4bd-113">The `*=` operator first multiplies the value of the expression (on the right-hand side of the operator) by the value of the variable or property (on the left-hand side of the operator).</span></span> <span data-ttu-id="ed4bd-114">The operator then assigns the result of that operation to the variable or property.</span><span class="sxs-lookup"><span data-stu-id="ed4bd-114">The operator then assigns the result of that operation to the variable or property.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="ed4bd-115">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="ed4bd-115">Overloading</span></span>  
 <span data-ttu-id="ed4bd-116">The [\* Operator](../../../visual-basic/language-reference/operators/multiplication-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span><span class="sxs-lookup"><span data-stu-id="ed4bd-116">The [\* Operator](../../../visual-basic/language-reference/operators/multiplication-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="ed4bd-117">Overloading the `*` operator affects the behavior of the `*=` operator.</span><span class="sxs-lookup"><span data-stu-id="ed4bd-117">Overloading the `*` operator affects the behavior of the `*=` operator.</span></span> <span data-ttu-id="ed4bd-118">If your code uses `*=` on a class or structure that overloads `*`, be sure you understand its redefined behavior.</span><span class="sxs-lookup"><span data-stu-id="ed4bd-118">If your code uses `*=` on a class or structure that overloads `*`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="ed4bd-119">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed4bd-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed4bd-120">例</span><span class="sxs-lookup"><span data-stu-id="ed4bd-120">Example</span></span>  
 <span data-ttu-id="ed4bd-121">The following example uses the `*=` operator to multiply one `Integer` variable by a second and assign the result to the first variable.</span><span class="sxs-lookup"><span data-stu-id="ed4bd-121">The following example uses the `*=` operator to multiply one `Integer` variable by a second and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="ed4bd-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="ed4bd-122">See also</span></span>

- [<span data-ttu-id="ed4bd-123">\* 演算子</span><span class="sxs-lookup"><span data-stu-id="ed4bd-123">\* Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-operator.md)
- [<span data-ttu-id="ed4bd-124">代入演算子</span><span class="sxs-lookup"><span data-stu-id="ed4bd-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="ed4bd-125">算術演算子</span><span class="sxs-lookup"><span data-stu-id="ed4bd-125">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="ed4bd-126">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="ed4bd-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="ed4bd-127">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="ed4bd-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="ed4bd-128">ステートメント</span><span class="sxs-lookup"><span data-stu-id="ed4bd-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
