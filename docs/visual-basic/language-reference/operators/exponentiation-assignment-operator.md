---
title: ^= 演算子 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.^=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- ^= operator [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 397da132-2d96-4a85-a7bc-f7c730a608c9
ms.openlocfilehash: fe5d7b3dcb55192167512e0934e09cff7dfddb6d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778522"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="1c48f-102">^= 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1c48f-102">^= Operator (Visual Basic)</span></span>
<span data-ttu-id="1c48f-103">変数または式のプロパティの値を生成し、結果を変数またはプロパティに代入します。</span><span class="sxs-lookup"><span data-stu-id="1c48f-103">Raises the value of a variable or property to the power of an expression and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c48f-104">構文</span><span class="sxs-lookup"><span data-stu-id="1c48f-104">Syntax</span></span>  
  
```  
variableorproperty ^= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="1c48f-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="1c48f-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="1c48f-106">必須。</span><span class="sxs-lookup"><span data-stu-id="1c48f-106">Required.</span></span> <span data-ttu-id="1c48f-107">任意の数値型の変数またはプロパティ。</span><span class="sxs-lookup"><span data-stu-id="1c48f-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="1c48f-108">必須。</span><span class="sxs-lookup"><span data-stu-id="1c48f-108">Required.</span></span> <span data-ttu-id="1c48f-109">任意の数式。</span><span class="sxs-lookup"><span data-stu-id="1c48f-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c48f-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="1c48f-110">Remarks</span></span>  
 <span data-ttu-id="1c48f-111">左側にある要素、`^=`演算子は、単純なスカラー変数、プロパティ、または配列の要素。</span><span class="sxs-lookup"><span data-stu-id="1c48f-111">The element on the left side of the `^=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="1c48f-112">変数またはプロパティにすることはできません[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)します。</span><span class="sxs-lookup"><span data-stu-id="1c48f-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="1c48f-113">`^=`演算子は最初 (演算子の右側にある) の式の値の電源を変数または (演算子の左側にある) のプロパティの値を生成します。</span><span class="sxs-lookup"><span data-stu-id="1c48f-113">The `^=` operator first raises the value of the variable or property (on the left-hand side of the operator) to the power of the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="1c48f-114">演算子は、変数またはプロパティに、その操作の結果を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1c48f-114">The operator then assigns the result of that operation back to the variable or property.</span></span>  
  
 <span data-ttu-id="1c48f-115">Visual Basic の指数演算を常に実行する、 [Double データ型](../../../visual-basic/language-reference/data-types/double-data-type.md)します。</span><span class="sxs-lookup"><span data-stu-id="1c48f-115">Visual Basic always performs exponentiation in the [Double Data Type](../../../visual-basic/language-reference/data-types/double-data-type.md).</span></span> <span data-ttu-id="1c48f-116">さまざまな型のオペランドが変換されます`Double`、結果は常と`Double`します。</span><span class="sxs-lookup"><span data-stu-id="1c48f-116">Operands of any different type are converted to `Double`, and the result is always `Double`.</span></span>  
  
 <span data-ttu-id="1c48f-117">値`expression`、小数部は、負の値、またはその両方です。</span><span class="sxs-lookup"><span data-stu-id="1c48f-117">The value of `expression` can be fractional, negative, or both.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="1c48f-118">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="1c48f-118">Overloading</span></span>  
 <span data-ttu-id="1c48f-119">[^ 演算子](../../../visual-basic/language-reference/operators/exponentiation-operator.md)できます*オーバー ロードされた*、つまり、ことクラスまたは構造体を再定義できますその動作はそのクラスまたは構造体の型。</span><span class="sxs-lookup"><span data-stu-id="1c48f-119">The [^ Operator](../../../visual-basic/language-reference/operators/exponentiation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="1c48f-120">オーバー ロード、`^`演算子の動作に影響、`^=`演算子。</span><span class="sxs-lookup"><span data-stu-id="1c48f-120">Overloading the `^` operator affects the behavior of the `^=` operator.</span></span> <span data-ttu-id="1c48f-121">コードで使用する場合`^=`クラスまたは構造体をオーバー ロードで`^`、再定義された動作を確認してください。</span><span class="sxs-lookup"><span data-stu-id="1c48f-121">If your code uses `^=` on a class or structure that overloads `^`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="1c48f-122">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c48f-122">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c48f-123">例</span><span class="sxs-lookup"><span data-stu-id="1c48f-123">Example</span></span>  
 <span data-ttu-id="1c48f-124">次の例では、`^=`いずれかの値を上げる演算子`Integer`2 番目の変数と割り当て、最初の変数に結果の変数。</span><span class="sxs-lookup"><span data-stu-id="1c48f-124">The following example uses the `^=` operator to raise the value of one `Integer` variable to the power of a second variable and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="1c48f-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="1c48f-125">See also</span></span>

- [<span data-ttu-id="1c48f-126">^ 演算子</span><span class="sxs-lookup"><span data-stu-id="1c48f-126">^ Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-operator.md)
- [<span data-ttu-id="1c48f-127">代入演算子</span><span class="sxs-lookup"><span data-stu-id="1c48f-127">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="1c48f-128">算術演算子</span><span class="sxs-lookup"><span data-stu-id="1c48f-128">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="1c48f-129">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="1c48f-129">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="1c48f-130">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="1c48f-130">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="1c48f-131">ステートメント</span><span class="sxs-lookup"><span data-stu-id="1c48f-131">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
