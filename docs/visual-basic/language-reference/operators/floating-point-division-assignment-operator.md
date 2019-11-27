---
title: /= 演算子
ms.date: 07/20/2015
f1_keywords:
- vb./=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- /= operator [Visual Basic]
- operator /=
- compound assignment statements [Visual Basic]
ms.assetid: a1e22d0e-8380-4761-9da1-84fb51c34821
ms.openlocfilehash: a8a031e968df90496a4e263ae78d47045ccdc923
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331034"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="8e60b-102">/= 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8e60b-102">/= Operator (Visual Basic)</span></span>
<span data-ttu-id="8e60b-103">式の値によって変数またはプロパティの値を除算し、浮動小数点演算の結果を変数またはプロパティに代入します。</span><span class="sxs-lookup"><span data-stu-id="8e60b-103">Divides the value of a variable or property by the value of an expression and assigns the floating-point result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e60b-104">構文</span><span class="sxs-lookup"><span data-stu-id="8e60b-104">Syntax</span></span>  
  
```vb  
variableorproperty /= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="8e60b-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="8e60b-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="8e60b-106">必須。</span><span class="sxs-lookup"><span data-stu-id="8e60b-106">Required.</span></span> <span data-ttu-id="8e60b-107">任意の数値変数またはプロパティ。</span><span class="sxs-lookup"><span data-stu-id="8e60b-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="8e60b-108">必須。</span><span class="sxs-lookup"><span data-stu-id="8e60b-108">Required.</span></span> <span data-ttu-id="8e60b-109">任意の数式。</span><span class="sxs-lookup"><span data-stu-id="8e60b-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e60b-110">コメント</span><span class="sxs-lookup"><span data-stu-id="8e60b-110">Remarks</span></span>  
 <span data-ttu-id="8e60b-111">`/=` 演算子の左側の要素は、単純なスカラー変数、プロパティ、または配列の要素にすることができます。</span><span class="sxs-lookup"><span data-stu-id="8e60b-111">The element on the left side of the `/=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="8e60b-112">変数またはプロパティを[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="8e60b-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="8e60b-113">`/=` 演算子は、まず、変数またはプロパティの値 (演算子の左辺) を式の値 (演算子の右側) によって除算しています。</span><span class="sxs-lookup"><span data-stu-id="8e60b-113">The `/=` operator first divides the value of the variable or property (on the left-hand side of the operator) by the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="8e60b-114">次に、演算子は、その演算の浮動小数点の結果を変数またはプロパティに代入します。</span><span class="sxs-lookup"><span data-stu-id="8e60b-114">The operator then assigns the floating-point result of that operation to the variable or property.</span></span>  
  
 <span data-ttu-id="8e60b-115">このステートメントにより、左側の変数またはプロパティに `Double` 値が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="8e60b-115">This statement assigns a `Double` value to the variable or property on the left.</span></span> <span data-ttu-id="8e60b-116">`Option Strict` が `On`場合、`variableorproperty` は `Double`である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e60b-116">If `Option Strict` is `On`, `variableorproperty` must be a `Double`.</span></span> <span data-ttu-id="8e60b-117">`Option Strict` が `Off`場合、Visual Basic は暗黙的な変換を実行し、結果の値を `variableorproperty`に割り当てます。実行時にエラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8e60b-117">If `Option Strict` is `Off`, Visual Basic performs an implicit conversion and assigns the resulting value to `variableorproperty`, with a possible error at run time.</span></span> <span data-ttu-id="8e60b-118">詳細については、「[拡大変換と縮小変換](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)」および「 [Option Strict ステートメント](../../../visual-basic/language-reference/statements/option-strict-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e60b-118">For more information, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="8e60b-119">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="8e60b-119">Overloading</span></span>  
 <span data-ttu-id="8e60b-120">[/演算子 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)は*オーバーロード*することができます。つまり、クラスまたは構造体がそのクラスまたは構造体の型を持つ場合に、クラスまたは構造体がその動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="8e60b-120">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="8e60b-121">`/` 演算子のオーバーロードは、`/=` 演算子の動作に影響します。</span><span class="sxs-lookup"><span data-stu-id="8e60b-121">Overloading the `/` operator affects the behavior of the `/=` operator.</span></span> <span data-ttu-id="8e60b-122">コードで `/`をオーバーロードするクラスまたは構造体の `/=` を使用する場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8e60b-122">If your code uses `/=` on a class or structure that overloads `/`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="8e60b-123">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e60b-123">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e60b-124">例</span><span class="sxs-lookup"><span data-stu-id="8e60b-124">Example</span></span>  
 <span data-ttu-id="8e60b-125">次の例では、`/=` 演算子を使用して1つの `Integer` 変数を2番目の変数に除算し、商を最初の変数に代入します。</span><span class="sxs-lookup"><span data-stu-id="8e60b-125">The following example uses the `/=` operator to divide one `Integer` variable by a second and assign the quotient to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="8e60b-126">参照</span><span class="sxs-lookup"><span data-stu-id="8e60b-126">See also</span></span>

- [<span data-ttu-id="8e60b-127">/演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8e60b-127">/ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)
- [<span data-ttu-id="8e60b-128">\\= 演算子</span><span class="sxs-lookup"><span data-stu-id="8e60b-128">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [<span data-ttu-id="8e60b-129">代入演算子</span><span class="sxs-lookup"><span data-stu-id="8e60b-129">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="8e60b-130">算術演算子</span><span class="sxs-lookup"><span data-stu-id="8e60b-130">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="8e60b-131">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="8e60b-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="8e60b-132">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="8e60b-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="8e60b-133">ステートメント</span><span class="sxs-lookup"><span data-stu-id="8e60b-133">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
