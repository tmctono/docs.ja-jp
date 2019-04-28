---
title: '\= 演算子 (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- '\='
- vb.\=
helpviewer_keywords:
- '\= operator [Visual Basic]'
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator \= [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 6f39915d-e398-4045-afcc-da6885e57b9c
ms.openlocfilehash: 377a14a76f67e938f24c973b5946abd63f851bfd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768351"
---
# <a name="-operator"></a><span data-ttu-id="93683-102">\\= 演算子</span><span class="sxs-lookup"><span data-stu-id="93683-102">\\= Operator</span></span>
<span data-ttu-id="93683-103">変数またはプロパティの値式の値で除算し、結果の整数値を変数またはプロパティに代入します。</span><span class="sxs-lookup"><span data-stu-id="93683-103">Divides the value of a variable or property by the value of an expression and assigns the integer result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93683-104">構文</span><span class="sxs-lookup"><span data-stu-id="93683-104">Syntax</span></span>  
  
```  
variableorproperty \= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="93683-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="93683-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="93683-106">必須。</span><span class="sxs-lookup"><span data-stu-id="93683-106">Required.</span></span> <span data-ttu-id="93683-107">任意の数値型の変数またはプロパティ。</span><span class="sxs-lookup"><span data-stu-id="93683-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="93683-108">必須。</span><span class="sxs-lookup"><span data-stu-id="93683-108">Required.</span></span> <span data-ttu-id="93683-109">任意の数式。</span><span class="sxs-lookup"><span data-stu-id="93683-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="93683-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="93683-110">Remarks</span></span>  
 <span data-ttu-id="93683-111">左側にある要素、`\=`演算子は、単純なスカラー変数、プロパティ、または配列の要素。</span><span class="sxs-lookup"><span data-stu-id="93683-111">The element on the left side of the `\=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="93683-112">変数またはプロパティにすることはできません[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)します。</span><span class="sxs-lookup"><span data-stu-id="93683-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="93683-113">`\=`演算子は、変数または、左側のプロパティの値の右側にある値で除算し、変数またはプロパティの左側に結果の整数値を割り当てます</span><span class="sxs-lookup"><span data-stu-id="93683-113">The `\=` operator divides the value of a variable or property on its left by the value on its right, and assigns the integer result to the variable or property on its left</span></span>  
  
 <span data-ttu-id="93683-114">整数の除算について詳しくは、次を参照してください。 [\ 演算子 (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)します。</span><span class="sxs-lookup"><span data-stu-id="93683-114">For further information on integer division, see [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="93683-115">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="93683-115">Overloading</span></span>  
 <span data-ttu-id="93683-116">`\`演算子は、*オーバー ロードされた*、つまり、ことクラスまたは構造体を再定義できますその動作はそのクラスまたは構造体の型。</span><span class="sxs-lookup"><span data-stu-id="93683-116">The `\` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="93683-117">オーバー ロード、`\`演算子の動作に影響、`\=`演算子。</span><span class="sxs-lookup"><span data-stu-id="93683-117">Overloading the `\` operator affects the behavior of the `\=` operator.</span></span> <span data-ttu-id="93683-118">コードで使用する場合`\=`クラスまたは構造体をオーバー ロードで`\`、再定義された動作を確認してください。</span><span class="sxs-lookup"><span data-stu-id="93683-118">If your code uses `\=` on a class or structure that overloads `\`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="93683-119">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="93683-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="93683-120">例</span><span class="sxs-lookup"><span data-stu-id="93683-120">Example</span></span>  
 <span data-ttu-id="93683-121">次の例では、`\=`演算子を 1 つの分割`Integer`秒と、整数の結果が最初の変数に割り当てるのでは、変数。</span><span class="sxs-lookup"><span data-stu-id="93683-121">The following example uses the `\=` operator to divide one `Integer` variable by a second and assign the integer result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="93683-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="93683-122">See also</span></span>

- [<span data-ttu-id="93683-123">\ 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="93683-123">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)
- [<span data-ttu-id="93683-124">/= 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="93683-124">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [<span data-ttu-id="93683-125">代入演算子</span><span class="sxs-lookup"><span data-stu-id="93683-125">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="93683-126">算術演算子</span><span class="sxs-lookup"><span data-stu-id="93683-126">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="93683-127">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="93683-127">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="93683-128">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="93683-128">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="93683-129">ステートメント</span><span class="sxs-lookup"><span data-stu-id="93683-129">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
