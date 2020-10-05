---
title: = 演算子
ms.date: 07/20/2015
f1_keywords:
- vb.Assign
- vb.=
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
ms.openlocfilehash: eccea0b43564a4980778c9d1a5b8f9a8c2a9207d
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874822"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="2a4fa-102">= 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2a4fa-102">= Operator (Visual Basic)</span></span>

<span data-ttu-id="2a4fa-103">変数またはプロパティに値を代入します。</span><span class="sxs-lookup"><span data-stu-id="2a4fa-103">Assigns a value to a variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a4fa-104">構文</span><span class="sxs-lookup"><span data-stu-id="2a4fa-104">Syntax</span></span>  
  
```vb  
variableorproperty = value  
```  
  
## <a name="parts"></a><span data-ttu-id="2a4fa-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="2a4fa-105">Parts</span></span>  

 `variableorproperty`  
 <span data-ttu-id="2a4fa-106">任意の書き込み可能な変数または任意のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="2a4fa-106">Any writable variable or any property.</span></span>  
  
 `value`  
 <span data-ttu-id="2a4fa-107">任意のリテラル、定数、または式。</span><span class="sxs-lookup"><span data-stu-id="2a4fa-107">Any literal, constant, or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a4fa-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="2a4fa-108">Remarks</span></span>  

 <span data-ttu-id="2a4fa-109">等号 (`=`) の左側の要素として、単純なスカラー変数、プロパティ、または配列の要素を指定できます。</span><span class="sxs-lookup"><span data-stu-id="2a4fa-109">The element on the left side of the equal sign (`=`) can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="2a4fa-110">変数またはプロパティを [ReadOnly](../modifiers/readonly.md) にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="2a4fa-110">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span> <span data-ttu-id="2a4fa-111">`=` 演算子は、右辺の値を左辺の変数またはプロパティに代入します。</span><span class="sxs-lookup"><span data-stu-id="2a4fa-111">The `=` operator assigns the value on its right to the variable or property on its left.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2a4fa-112">`=` 演算子は、比較演算子としても使用されます。</span><span class="sxs-lookup"><span data-stu-id="2a4fa-112">The `=` operator is also used as a comparison operator.</span></span> <span data-ttu-id="2a4fa-113">詳細については、「[比較演算子](comparison-operators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a4fa-113">For details, see [Comparison Operators](comparison-operators.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="2a4fa-114">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="2a4fa-114">Overloading</span></span>  

 <span data-ttu-id="2a4fa-115">`=` 演算子は、代入演算子としてではなく、関係比較演算子としてのみオーバーロードできます。</span><span class="sxs-lookup"><span data-stu-id="2a4fa-115">The `=` operator can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span> <span data-ttu-id="2a4fa-116">詳細については、「 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a4fa-116">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a4fa-117">例</span><span class="sxs-lookup"><span data-stu-id="2a4fa-117">Example</span></span>  

 <span data-ttu-id="2a4fa-118">代入演算子の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2a4fa-118">The following example demonstrates the assignment operator.</span></span> <span data-ttu-id="2a4fa-119">右辺の値が左辺の変数に代入されます。</span><span class="sxs-lookup"><span data-stu-id="2a4fa-119">The value on the right is assigned to the variable on the left.</span></span>  
  
 [!code-vb[VbVbalrOperators#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="2a4fa-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a4fa-120">See also</span></span>

- [<span data-ttu-id="2a4fa-121">& = 演算子</span><span class="sxs-lookup"><span data-stu-id="2a4fa-121">&= Operator</span></span>](and-assignment-operator.md)
- [<span data-ttu-id="2a4fa-122">\*= 演算子</span><span class="sxs-lookup"><span data-stu-id="2a4fa-122">\*= Operator</span></span>](multiplication-assignment-operator.md)
- [<span data-ttu-id="2a4fa-123">+= 演算子</span><span class="sxs-lookup"><span data-stu-id="2a4fa-123">+= Operator</span></span>](addition-assignment-operator.md)
- [<span data-ttu-id="2a4fa-124">-= 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2a4fa-124">-= Operator (Visual Basic)</span></span>](subtraction-assignment-operator.md)
- [<span data-ttu-id="2a4fa-125">/= 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2a4fa-125">/= Operator (Visual Basic)</span></span>](floating-point-division-assignment-operator.md)
- [<span data-ttu-id="2a4fa-126">\\= 演算子</span><span class="sxs-lookup"><span data-stu-id="2a4fa-126">\\= Operator</span></span>](integer-division-assignment-operator.md)
- [<span data-ttu-id="2a4fa-127">^= 演算子</span><span class="sxs-lookup"><span data-stu-id="2a4fa-127">^= Operator</span></span>](exponentiation-assignment-operator.md)
- [<span data-ttu-id="2a4fa-128">ステートメント</span><span class="sxs-lookup"><span data-stu-id="2a4fa-128">Statements</span></span>](../../programming-guide/language-features/statements.md)
- [<span data-ttu-id="2a4fa-129">比較演算子</span><span class="sxs-lookup"><span data-stu-id="2a4fa-129">Comparison Operators</span></span>](comparison-operators.md)
- [<span data-ttu-id="2a4fa-130">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="2a4fa-130">ReadOnly</span></span>](../modifiers/readonly.md)
- [<span data-ttu-id="2a4fa-131">ローカル型の推論</span><span class="sxs-lookup"><span data-stu-id="2a4fa-131">Local Type Inference</span></span>](../../programming-guide/language-features/variables/local-type-inference.md)
