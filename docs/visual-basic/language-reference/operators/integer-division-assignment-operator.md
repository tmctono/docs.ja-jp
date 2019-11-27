---
title: '\= 演算子'
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
ms.openlocfilehash: 600acf9b41b63358da245fe602595fee4093b15b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330952"
---
# <a name="-operator"></a><span data-ttu-id="dca3a-102">\\= 演算子</span><span class="sxs-lookup"><span data-stu-id="dca3a-102">\\= Operator</span></span>
<span data-ttu-id="dca3a-103">式の値によって変数またはプロパティの値を除算し、その結果を変数またはプロパティに代入します。</span><span class="sxs-lookup"><span data-stu-id="dca3a-103">Divides the value of a variable or property by the value of an expression and assigns the integer result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dca3a-104">構文</span><span class="sxs-lookup"><span data-stu-id="dca3a-104">Syntax</span></span>  
  
```vb  
variableorproperty \= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="dca3a-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="dca3a-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="dca3a-106">必須。</span><span class="sxs-lookup"><span data-stu-id="dca3a-106">Required.</span></span> <span data-ttu-id="dca3a-107">任意の数値変数またはプロパティ。</span><span class="sxs-lookup"><span data-stu-id="dca3a-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="dca3a-108">必須。</span><span class="sxs-lookup"><span data-stu-id="dca3a-108">Required.</span></span> <span data-ttu-id="dca3a-109">任意の数式。</span><span class="sxs-lookup"><span data-stu-id="dca3a-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dca3a-110">コメント</span><span class="sxs-lookup"><span data-stu-id="dca3a-110">Remarks</span></span>  
 <span data-ttu-id="dca3a-111">`\=` 演算子の左側の要素は、単純なスカラー変数、プロパティ、または配列の要素にすることができます。</span><span class="sxs-lookup"><span data-stu-id="dca3a-111">The element on the left side of the `\=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="dca3a-112">変数またはプロパティを[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="dca3a-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="dca3a-113">`\=` 演算子は、変数またはプロパティの値を右側の値で除算し、整数の結果をその左側の変数またはプロパティに代入します。</span><span class="sxs-lookup"><span data-stu-id="dca3a-113">The `\=` operator divides the value of a variable or property on its left by the value on its right, and assigns the integer result to the variable or property on its left</span></span>  
  
 <span data-ttu-id="dca3a-114">整数除算の詳細については、「 [\ 演算子 (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dca3a-114">For further information on integer division, see [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="dca3a-115">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="dca3a-115">Overloading</span></span>  
 <span data-ttu-id="dca3a-116">`\` 演算子は*オーバーロード*することができます。つまり、クラスまたは構造体がそのクラスまたは構造体の型を持つ場合に、クラスまたは構造体がその動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="dca3a-116">The `\` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="dca3a-117">`\` 演算子のオーバーロードは、`\=` 演算子の動作に影響します。</span><span class="sxs-lookup"><span data-stu-id="dca3a-117">Overloading the `\` operator affects the behavior of the `\=` operator.</span></span> <span data-ttu-id="dca3a-118">コードで `\`をオーバーロードするクラスまたは構造体の `\=` を使用する場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="dca3a-118">If your code uses `\=` on a class or structure that overloads `\`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="dca3a-119">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dca3a-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dca3a-120">例</span><span class="sxs-lookup"><span data-stu-id="dca3a-120">Example</span></span>  
 <span data-ttu-id="dca3a-121">次の例では、`\=` 演算子を使用して1つの `Integer` 変数を2番目の変数に除算し、整数の結果を最初の変数に代入します。</span><span class="sxs-lookup"><span data-stu-id="dca3a-121">The following example uses the `\=` operator to divide one `Integer` variable by a second and assign the integer result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="dca3a-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="dca3a-122">See also</span></span>

- [<span data-ttu-id="dca3a-123">\ 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dca3a-123">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)
- [<span data-ttu-id="dca3a-124">/= 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dca3a-124">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [<span data-ttu-id="dca3a-125">代入演算子</span><span class="sxs-lookup"><span data-stu-id="dca3a-125">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="dca3a-126">算術演算子</span><span class="sxs-lookup"><span data-stu-id="dca3a-126">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="dca3a-127">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="dca3a-127">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="dca3a-128">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="dca3a-128">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="dca3a-129">ステートメント</span><span class="sxs-lookup"><span data-stu-id="dca3a-129">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
