---
title: = 演算子 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Assign
- vb.=
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
ms.openlocfilehash: ca4c519dd80c07f54dc1c3dfe70daf6948446363
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2019
ms.locfileid: "71591838"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="878ed-102">= 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="878ed-102">= Operator (Visual Basic)</span></span>
<span data-ttu-id="878ed-103">変数またはプロパティに値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="878ed-103">Assigns a value to a variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="878ed-104">構文</span><span class="sxs-lookup"><span data-stu-id="878ed-104">Syntax</span></span>  
  
```vb  
variableorproperty = value  
```  
  
## <a name="parts"></a><span data-ttu-id="878ed-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="878ed-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="878ed-106">任意の書き込み可能な変数または任意のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="878ed-106">Any writable variable or any property.</span></span>  
  
 `value`  
 <span data-ttu-id="878ed-107">任意のリテラル、定数、または式。</span><span class="sxs-lookup"><span data-stu-id="878ed-107">Any literal, constant, or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="878ed-108">コメント</span><span class="sxs-lookup"><span data-stu-id="878ed-108">Remarks</span></span>  
 <span data-ttu-id="878ed-109">等号 (`=`) の左側の要素は、単純なスカラー変数、プロパティ、または配列の要素にすることができます。</span><span class="sxs-lookup"><span data-stu-id="878ed-109">The element on the left side of the equal sign (`=`) can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="878ed-110">変数またはプロパティを[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="878ed-110">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span> <span data-ttu-id="878ed-111">@No__t-0 演算子は、左側の変数またはプロパティに右辺の値を代入します。</span><span class="sxs-lookup"><span data-stu-id="878ed-111">The `=` operator assigns the value on its right to the variable or property on its left.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="878ed-112">@No__t-0 演算子は、比較演算子としても使用されます。</span><span class="sxs-lookup"><span data-stu-id="878ed-112">The `=` operator is also used as a comparison operator.</span></span> <span data-ttu-id="878ed-113">詳細については、「[比較演算子](../../../visual-basic/language-reference/operators/comparison-operators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="878ed-113">For details, see [Comparison Operators](../../../visual-basic/language-reference/operators/comparison-operators.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="878ed-114">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="878ed-114">Overloading</span></span>  
 <span data-ttu-id="878ed-115">@No__t-0 演算子は、代入演算子としてではなく、関係比較演算子としてのみオーバーロードできます。</span><span class="sxs-lookup"><span data-stu-id="878ed-115">The `=` operator can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span> <span data-ttu-id="878ed-116">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="878ed-116">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="878ed-117">例</span><span class="sxs-lookup"><span data-stu-id="878ed-117">Example</span></span>  
 <span data-ttu-id="878ed-118">次の例は、代入演算子を示しています。</span><span class="sxs-lookup"><span data-stu-id="878ed-118">The following example demonstrates the assignment operator.</span></span> <span data-ttu-id="878ed-119">右側の値は、左側の変数に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="878ed-119">The value on the right is assigned to the variable on the left.</span></span>  
  
 [!code-vb[VbVbalrOperators#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="878ed-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="878ed-120">See also</span></span>

- [<span data-ttu-id="878ed-121">& = 演算子</span><span class="sxs-lookup"><span data-stu-id="878ed-121">&= Operator</span></span>](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="878ed-122">\*= 演算子</span><span class="sxs-lookup"><span data-stu-id="878ed-122">\*= Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)
- [<span data-ttu-id="878ed-123">+= 演算子</span><span class="sxs-lookup"><span data-stu-id="878ed-123">+= Operator</span></span>](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)
- [<span data-ttu-id="878ed-124">-= 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="878ed-124">-= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
- [<span data-ttu-id="878ed-125">/= 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="878ed-125">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [<span data-ttu-id="878ed-126">\\ = 演算子</span><span class="sxs-lookup"><span data-stu-id="878ed-126">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [<span data-ttu-id="878ed-127">^= 演算子</span><span class="sxs-lookup"><span data-stu-id="878ed-127">^= Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)
- [<span data-ttu-id="878ed-128">ステートメント</span><span class="sxs-lookup"><span data-stu-id="878ed-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="878ed-129">比較演算子</span><span class="sxs-lookup"><span data-stu-id="878ed-129">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="878ed-130">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="878ed-130">ReadOnly</span></span>](../../../visual-basic/language-reference/modifiers/readonly.md)
- [<span data-ttu-id="878ed-131">ローカル型の推論</span><span class="sxs-lookup"><span data-stu-id="878ed-131">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
