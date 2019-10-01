---
title: -= 演算子 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.-=
helpviewer_keywords:
- -= operator [Visual Basic]
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator -=
- compound assignment statements [Visual Basic]
ms.assetid: 5ead0c37-ae50-48f7-8435-8e341d81cae1
ms.openlocfilehash: f857c8bf2f89120e047c49674ce9e8a3bff22f7d
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701315"
---
# <a name="--operator-visual-basic"></a><span data-ttu-id="89eb1-102">-= 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="89eb1-102">-= Operator (Visual Basic)</span></span>
<span data-ttu-id="89eb1-103">変数またはプロパティの値から式の値を減算し、その結果を変数またはプロパティに代入します。</span><span class="sxs-lookup"><span data-stu-id="89eb1-103">Subtracts the value of an expression from the value of a variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89eb1-104">構文</span><span class="sxs-lookup"><span data-stu-id="89eb1-104">Syntax</span></span>  
  
```vb  
variableorproperty -= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="89eb1-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="89eb1-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="89eb1-106">必須。</span><span class="sxs-lookup"><span data-stu-id="89eb1-106">Required.</span></span> <span data-ttu-id="89eb1-107">任意の数値変数またはプロパティ。</span><span class="sxs-lookup"><span data-stu-id="89eb1-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="89eb1-108">必須。</span><span class="sxs-lookup"><span data-stu-id="89eb1-108">Required.</span></span> <span data-ttu-id="89eb1-109">任意の数式。</span><span class="sxs-lookup"><span data-stu-id="89eb1-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89eb1-110">コメント</span><span class="sxs-lookup"><span data-stu-id="89eb1-110">Remarks</span></span>  
 <span data-ttu-id="89eb1-111">@No__t-0 演算子の左側の要素は、単純なスカラー変数、プロパティ、または配列の要素にすることができます。</span><span class="sxs-lookup"><span data-stu-id="89eb1-111">The element on the left side of the `-=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="89eb1-112">変数またはプロパティを[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="89eb1-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="89eb1-113">@No__t-0 演算子は、演算子の左側の変数またはプロパティの値から (演算子の右側にある) 式の値を最初に減算します (演算子の左辺の)。</span><span class="sxs-lookup"><span data-stu-id="89eb1-113">The `-=` operator first subtracts the value of the expression (on the right-hand side of the operator) from the value of the variable or property (on the left-hand side of the operator).</span></span> <span data-ttu-id="89eb1-114">次に、演算子は、その操作の結果を変数またはプロパティに代入します。</span><span class="sxs-lookup"><span data-stu-id="89eb1-114">The operator then assigns the result of that operation to the variable or property.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="89eb1-115">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="89eb1-115">Overloading</span></span>  
 <span data-ttu-id="89eb1-116">[-演算子 (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md)は*オーバーロード*できます。つまり、クラスまたは構造体がそのクラスまたは構造体の型を持つ場合に、クラスまたは構造体がその動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="89eb1-116">The [- Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="89eb1-117">@No__t-0 演算子のオーバーロードは、`-=` 演算子の動作に影響します。</span><span class="sxs-lookup"><span data-stu-id="89eb1-117">Overloading the `-` operator affects the behavior of the `-=` operator.</span></span> <span data-ttu-id="89eb1-118">コードで `-` をオーバーロードするクラスまたは構造体に @no__t 0 を使用している場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="89eb1-118">If your code uses `-=` on a class or structure that overloads `-`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="89eb1-119">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89eb1-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="89eb1-120">例</span><span class="sxs-lookup"><span data-stu-id="89eb1-120">Example</span></span>  
 <span data-ttu-id="89eb1-121">次の例では、`-=` 演算子を使用して、1つの @no__t 変数を別の変数から減算し、その結果を後者の変数に代入します。</span><span class="sxs-lookup"><span data-stu-id="89eb1-121">The following example uses the `-=` operator to subtract one `Integer` variable from another and assign the result to the latter variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="89eb1-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="89eb1-122">See also</span></span>

- [<span data-ttu-id="89eb1-123">-演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="89eb1-123">- Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/subtraction-operator.md)
- [<span data-ttu-id="89eb1-124">代入演算子</span><span class="sxs-lookup"><span data-stu-id="89eb1-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="89eb1-125">算術演算子</span><span class="sxs-lookup"><span data-stu-id="89eb1-125">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="89eb1-126">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="89eb1-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="89eb1-127">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="89eb1-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="89eb1-128">ステートメント</span><span class="sxs-lookup"><span data-stu-id="89eb1-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
