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
ms.openlocfilehash: 47d3239af6ff24501e6babc23c0db4103c477796
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701064"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="423f7-102">\*= 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="423f7-102">\*= Operator (Visual Basic)</span></span>
<span data-ttu-id="423f7-103">変数またはプロパティの値を式の値で乗算し、その結果を変数またはプロパティに代入します。</span><span class="sxs-lookup"><span data-stu-id="423f7-103">Multiplies the value of a variable or property by the value of an expression and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="423f7-104">構文</span><span class="sxs-lookup"><span data-stu-id="423f7-104">Syntax</span></span>  
  
```vb  
variableorproperty *= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="423f7-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="423f7-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="423f7-106">必須。</span><span class="sxs-lookup"><span data-stu-id="423f7-106">Required.</span></span> <span data-ttu-id="423f7-107">任意の数値変数またはプロパティ。</span><span class="sxs-lookup"><span data-stu-id="423f7-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="423f7-108">必須。</span><span class="sxs-lookup"><span data-stu-id="423f7-108">Required.</span></span> <span data-ttu-id="423f7-109">任意の数式。</span><span class="sxs-lookup"><span data-stu-id="423f7-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="423f7-110">コメント</span><span class="sxs-lookup"><span data-stu-id="423f7-110">Remarks</span></span>  
 <span data-ttu-id="423f7-111">@No__t-0 演算子の左側の要素は、単純なスカラー変数、プロパティ、または配列の要素にすることができます。</span><span class="sxs-lookup"><span data-stu-id="423f7-111">The element on the left side of the `*=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="423f7-112">変数またはプロパティを[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="423f7-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="423f7-113">@No__t 0 演算子は、最初に式の値 (演算子の右側) を変数またはプロパティの値 (演算子の左辺) に乗算します。この演算子は、演算子の右辺にある式の値によって乗算されます。</span><span class="sxs-lookup"><span data-stu-id="423f7-113">The `*=` operator first multiplies the value of the expression (on the right-hand side of the operator) by the value of the variable or property (on the left-hand side of the operator).</span></span> <span data-ttu-id="423f7-114">次に、演算子は、その操作の結果を変数またはプロパティに代入します。</span><span class="sxs-lookup"><span data-stu-id="423f7-114">The operator then assigns the result of that operation to the variable or property.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="423f7-115">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="423f7-115">Overloading</span></span>  
 <span data-ttu-id="423f7-116">[\* 演算子](../../../visual-basic/language-reference/operators/multiplication-operator.md)は*オーバーロード*することができます。つまり、クラスまたは構造体がそのクラスまたは構造体の型を持つ場合に、クラスまたは構造体がその動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="423f7-116">The [\* Operator](../../../visual-basic/language-reference/operators/multiplication-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="423f7-117">@No__t-0 演算子のオーバーロードは、`*=` 演算子の動作に影響します。</span><span class="sxs-lookup"><span data-stu-id="423f7-117">Overloading the `*` operator affects the behavior of the `*=` operator.</span></span> <span data-ttu-id="423f7-118">コードで `*` をオーバーロードするクラスまたは構造体に @no__t 0 を使用している場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="423f7-118">If your code uses `*=` on a class or structure that overloads `*`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="423f7-119">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="423f7-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="423f7-120">例</span><span class="sxs-lookup"><span data-stu-id="423f7-120">Example</span></span>  
 <span data-ttu-id="423f7-121">次の例では、`*=` 演算子を使用して1つの @no__t 1 つの変数を2番目の変数に乗算し、その結果を最初の変数に代入します。</span><span class="sxs-lookup"><span data-stu-id="423f7-121">The following example uses the `*=` operator to multiply one `Integer` variable by a second and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="423f7-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="423f7-122">See also</span></span>

- [<span data-ttu-id="423f7-123">\* 演算子</span><span class="sxs-lookup"><span data-stu-id="423f7-123">\* Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-operator.md)
- [<span data-ttu-id="423f7-124">代入演算子</span><span class="sxs-lookup"><span data-stu-id="423f7-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="423f7-125">算術演算子</span><span class="sxs-lookup"><span data-stu-id="423f7-125">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="423f7-126">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="423f7-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="423f7-127">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="423f7-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="423f7-128">ステートメント</span><span class="sxs-lookup"><span data-stu-id="423f7-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
