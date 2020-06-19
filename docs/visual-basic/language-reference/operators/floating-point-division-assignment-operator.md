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
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331034"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="6aa18-102">/= 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6aa18-102">/= Operator (Visual Basic)</span></span>
<span data-ttu-id="6aa18-103">変数またはプロパティの値を式の値で除算し、その浮動小数点の結果を変数またはプロパティに代入します。</span><span class="sxs-lookup"><span data-stu-id="6aa18-103">Divides the value of a variable or property by the value of an expression and assigns the floating-point result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6aa18-104">構文</span><span class="sxs-lookup"><span data-stu-id="6aa18-104">Syntax</span></span>  
  
```vb  
variableorproperty /= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="6aa18-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="6aa18-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="6aa18-106">必須です。</span><span class="sxs-lookup"><span data-stu-id="6aa18-106">Required.</span></span> <span data-ttu-id="6aa18-107">任意の数値変数またはプロパティ。</span><span class="sxs-lookup"><span data-stu-id="6aa18-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="6aa18-108">必須です。</span><span class="sxs-lookup"><span data-stu-id="6aa18-108">Required.</span></span> <span data-ttu-id="6aa18-109">任意の数式。</span><span class="sxs-lookup"><span data-stu-id="6aa18-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6aa18-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="6aa18-110">Remarks</span></span>  
 <span data-ttu-id="6aa18-111">`/=` 演算子の左側の要素には、単純なスカラー変数、プロパティ、または配列の要素を指定できます。</span><span class="sxs-lookup"><span data-stu-id="6aa18-111">The element on the left side of the `/=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="6aa18-112">変数またはプロパティを [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md) にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="6aa18-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="6aa18-113">`/=` 演算子は、最初に (演算子の左側にある) 変数またはプロパティの値を (演算子の右側にある) 式の値で除算します。</span><span class="sxs-lookup"><span data-stu-id="6aa18-113">The `/=` operator first divides the value of the variable or property (on the left-hand side of the operator) by the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="6aa18-114">次に、この演算子はその演算の浮動小数点の結果を変数またはプロパティに代入します。</span><span class="sxs-lookup"><span data-stu-id="6aa18-114">The operator then assigns the floating-point result of that operation to the variable or property.</span></span>  
  
 <span data-ttu-id="6aa18-115">このステートメントにより、左側の変数またはプロパティに `Double` 値が代入されます。</span><span class="sxs-lookup"><span data-stu-id="6aa18-115">This statement assigns a `Double` value to the variable or property on the left.</span></span> <span data-ttu-id="6aa18-116">`Option Strict` が `On` の場合、`variableorproperty` は `Double` である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6aa18-116">If `Option Strict` is `On`, `variableorproperty` must be a `Double`.</span></span> <span data-ttu-id="6aa18-117">`Option Strict` が `Off` の場合、Visual Basic によって暗黙的な変換が実行され、結果の値が `variableorproperty` に代入されます。実行時にエラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6aa18-117">If `Option Strict` is `Off`, Visual Basic performs an implicit conversion and assigns the resulting value to `variableorproperty`, with a possible error at run time.</span></span> <span data-ttu-id="6aa18-118">詳細については、「[拡大変換と縮小変換](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)」および「[Option Strict ステートメント](../../../visual-basic/language-reference/statements/option-strict-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6aa18-118">For more information, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="6aa18-119">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="6aa18-119">Overloading</span></span>  
 <span data-ttu-id="6aa18-120">[/ 演算子 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) は "*オーバーロード*" できます。つまり、オペランドの型がクラスまたは構造体であるとき、そのクラスまたは構造体でその動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="6aa18-120">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="6aa18-121">`/` 演算子をオーバーロードすると、`/=` 演算子の動作に影響します。</span><span class="sxs-lookup"><span data-stu-id="6aa18-121">Overloading the `/` operator affects the behavior of the `/=` operator.</span></span> <span data-ttu-id="6aa18-122">コードで、`/` をオーバーロードしているクラスまたは構造体に対して `/=` を使用する場合は、再定義される動作を必ず理解してください。</span><span class="sxs-lookup"><span data-stu-id="6aa18-122">If your code uses `/=` on a class or structure that overloads `/`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="6aa18-123">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6aa18-123">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6aa18-124">例</span><span class="sxs-lookup"><span data-stu-id="6aa18-124">Example</span></span>  
 <span data-ttu-id="6aa18-125">次の例では、`/=` 演算子を使用して 1 番目の `Integer` 変数を 2 番目の変数で除算し、商を 1 番目の変数に代入します。</span><span class="sxs-lookup"><span data-stu-id="6aa18-125">The following example uses the `/=` operator to divide one `Integer` variable by a second and assign the quotient to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="6aa18-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="6aa18-126">See also</span></span>

- [<span data-ttu-id="6aa18-127">/ 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6aa18-127">/ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)
- [<span data-ttu-id="6aa18-128">\\= 演算子</span><span class="sxs-lookup"><span data-stu-id="6aa18-128">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [<span data-ttu-id="6aa18-129">代入演算子</span><span class="sxs-lookup"><span data-stu-id="6aa18-129">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="6aa18-130">算術演算子</span><span class="sxs-lookup"><span data-stu-id="6aa18-130">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="6aa18-131">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="6aa18-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="6aa18-132">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="6aa18-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="6aa18-133">ステートメント</span><span class="sxs-lookup"><span data-stu-id="6aa18-133">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
