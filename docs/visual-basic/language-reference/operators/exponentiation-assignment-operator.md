---
title: ^= 演算子
ms.date: 07/20/2015
f1_keywords:
- vb.^=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- ^= operator [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 397da132-2d96-4a85-a7bc-f7c730a608c9
ms.openlocfilehash: fe5e8fc2b64b9e7c33483612071d338a0ee22768
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331294"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="ea7f7-102">^= 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ea7f7-102">^= Operator (Visual Basic)</span></span>
<span data-ttu-id="ea7f7-103">変数またはプロパティの値を式のべき乗にし、結果を変数またはプロパティに代入します。</span><span class="sxs-lookup"><span data-stu-id="ea7f7-103">Raises the value of a variable or property to the power of an expression and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea7f7-104">構文</span><span class="sxs-lookup"><span data-stu-id="ea7f7-104">Syntax</span></span>  
  
```vb  
variableorproperty ^= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="ea7f7-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="ea7f7-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="ea7f7-106">必須。</span><span class="sxs-lookup"><span data-stu-id="ea7f7-106">Required.</span></span> <span data-ttu-id="ea7f7-107">任意の数値変数またはプロパティ。</span><span class="sxs-lookup"><span data-stu-id="ea7f7-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="ea7f7-108">必須。</span><span class="sxs-lookup"><span data-stu-id="ea7f7-108">Required.</span></span> <span data-ttu-id="ea7f7-109">任意の数式。</span><span class="sxs-lookup"><span data-stu-id="ea7f7-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea7f7-110">コメント</span><span class="sxs-lookup"><span data-stu-id="ea7f7-110">Remarks</span></span>  
 <span data-ttu-id="ea7f7-111">`^=` 演算子の左側の要素は、単純なスカラー変数、プロパティ、または配列の要素にすることができます。</span><span class="sxs-lookup"><span data-stu-id="ea7f7-111">The element on the left side of the `^=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="ea7f7-112">変数またはプロパティを[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ea7f7-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="ea7f7-113">`^=` 演算子は、まず、演算子の左辺の変数またはプロパティの値を、式の値 (演算子の右側) に対してべき乗します (演算子の左辺にある)。</span><span class="sxs-lookup"><span data-stu-id="ea7f7-113">The `^=` operator first raises the value of the variable or property (on the left-hand side of the operator) to the power of the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="ea7f7-114">次に、演算子は、その操作の結果を変数またはプロパティに戻します。</span><span class="sxs-lookup"><span data-stu-id="ea7f7-114">The operator then assigns the result of that operation back to the variable or property.</span></span>  
  
 <span data-ttu-id="ea7f7-115">Visual Basic は、常に[Double データ型](../../../visual-basic/language-reference/data-types/double-data-type.md)の指数演算を実行します。</span><span class="sxs-lookup"><span data-stu-id="ea7f7-115">Visual Basic always performs exponentiation in the [Double Data Type](../../../visual-basic/language-reference/data-types/double-data-type.md).</span></span> <span data-ttu-id="ea7f7-116">異なる型のオペランドは `Double`に変換され、結果は常に `Double`になります。</span><span class="sxs-lookup"><span data-stu-id="ea7f7-116">Operands of any different type are converted to `Double`, and the result is always `Double`.</span></span>  
  
 <span data-ttu-id="ea7f7-117">`expression` の値には、小数、負、またはその両方を指定できます。</span><span class="sxs-lookup"><span data-stu-id="ea7f7-117">The value of `expression` can be fractional, negative, or both.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="ea7f7-118">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="ea7f7-118">Overloading</span></span>  
 <span data-ttu-id="ea7f7-119">[^ 演算子](../../../visual-basic/language-reference/operators/exponentiation-operator.md)は*オーバーロード*することができます。つまり、クラスまたは構造体がそのクラスまたは構造体の型を持つ場合に、クラスまたは構造体がその動作を再定義できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="ea7f7-119">The [^ Operator](../../../visual-basic/language-reference/operators/exponentiation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="ea7f7-120">`^` 演算子のオーバーロードは、`^=` 演算子の動作に影響します。</span><span class="sxs-lookup"><span data-stu-id="ea7f7-120">Overloading the `^` operator affects the behavior of the `^=` operator.</span></span> <span data-ttu-id="ea7f7-121">コードで `^`をオーバーロードするクラスまたは構造体の `^=` を使用する場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ea7f7-121">If your code uses `^=` on a class or structure that overloads `^`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="ea7f7-122">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea7f7-122">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea7f7-123">例</span><span class="sxs-lookup"><span data-stu-id="ea7f7-123">Example</span></span>  
 <span data-ttu-id="ea7f7-124">次の例では、`^=` 演算子を使用して、1つの `Integer` 変数の値を2番目の変数のべき乗に上げ、その結果を最初の変数に代入します。</span><span class="sxs-lookup"><span data-stu-id="ea7f7-124">The following example uses the `^=` operator to raise the value of one `Integer` variable to the power of a second variable and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="ea7f7-125">参照</span><span class="sxs-lookup"><span data-stu-id="ea7f7-125">See also</span></span>

- [<span data-ttu-id="ea7f7-126">^ 演算子</span><span class="sxs-lookup"><span data-stu-id="ea7f7-126">^ Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-operator.md)
- [<span data-ttu-id="ea7f7-127">代入演算子</span><span class="sxs-lookup"><span data-stu-id="ea7f7-127">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="ea7f7-128">算術演算子</span><span class="sxs-lookup"><span data-stu-id="ea7f7-128">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="ea7f7-129">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="ea7f7-129">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="ea7f7-130">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="ea7f7-130">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="ea7f7-131">ステートメント</span><span class="sxs-lookup"><span data-stu-id="ea7f7-131">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
