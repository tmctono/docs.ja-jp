---
title: '&amp;= 演算子 (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.&=
helpviewer_keywords:
- operator &=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '&= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 0cf262fc-1a05-419a-a503-60013f111c8a
ms.openlocfilehash: a79e779d8fcf549daeabc494e0a55deee30b5d22
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58835467"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="c38b9-102">&amp;= 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c38b9-102">&amp;= Operator (Visual Basic)</span></span>
<span data-ttu-id="c38b9-103">連結、`String`式を`String`変数またはプロパティし、結果を変数またはプロパティに代入します。</span><span class="sxs-lookup"><span data-stu-id="c38b9-103">Concatenates a `String` expression to a `String` variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c38b9-104">構文</span><span class="sxs-lookup"><span data-stu-id="c38b9-104">Syntax</span></span>  
  
```  
variableorproperty &= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="c38b9-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="c38b9-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="c38b9-106">必須。</span><span class="sxs-lookup"><span data-stu-id="c38b9-106">Required.</span></span> <span data-ttu-id="c38b9-107">すべて`String`変数またはプロパティ。</span><span class="sxs-lookup"><span data-stu-id="c38b9-107">Any `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="c38b9-108">必須。</span><span class="sxs-lookup"><span data-stu-id="c38b9-108">Required.</span></span> <span data-ttu-id="c38b9-109">任意のブール型 ( `String` ) の式を指定します。</span><span class="sxs-lookup"><span data-stu-id="c38b9-109">Any `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c38b9-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="c38b9-110">Remarks</span></span>  
 <span data-ttu-id="c38b9-111">左側にある要素、`&=`演算子は、単純なスカラー変数、プロパティ、または配列の要素。</span><span class="sxs-lookup"><span data-stu-id="c38b9-111">The element on the left side of the `&=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="c38b9-112">変数またはプロパティにすることはできません[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)します。</span><span class="sxs-lookup"><span data-stu-id="c38b9-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span> <span data-ttu-id="c38b9-113">`&=`演算子の連結、 `String` 、右辺の式、`String`変数またはプロパティの左側にし、結果を代入する変数またはプロパティの左側にします。</span><span class="sxs-lookup"><span data-stu-id="c38b9-113">The `&=` operator concatenates the `String` expression on its right to the `String` variable or property on its left, and assigns the result to the variable or property on its left.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="c38b9-114">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="c38b9-114">Overloading</span></span>  
 <span data-ttu-id="c38b9-115">[& 演算子](../../../visual-basic/language-reference/operators/concatenation-operator.md)できる*オーバー ロードされた*、ことクラスまたは構造体を再定義できますその動作はそのクラスまたは構造体の型つまりします。</span><span class="sxs-lookup"><span data-stu-id="c38b9-115">The [& Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="c38b9-116">オーバー ロード、`&`演算子の動作に影響、`&=`演算子。</span><span class="sxs-lookup"><span data-stu-id="c38b9-116">Overloading the `&` operator affects the behavior of the `&=` operator.</span></span> <span data-ttu-id="c38b9-117">コードで使用する場合`&=`クラスまたは構造体をオーバー ロードで`&`、再定義された動作を確認してください。</span><span class="sxs-lookup"><span data-stu-id="c38b9-117">If your code uses `&=` on a class or structure that overloads `&`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="c38b9-118">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c38b9-118">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c38b9-119">例</span><span class="sxs-lookup"><span data-stu-id="c38b9-119">Example</span></span>  
 <span data-ttu-id="c38b9-120">次の例では、`&=`を 2 つの連結演算子`String`変数と、その結果、最初の変数を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c38b9-120">The following example uses the `&=` operator to concatenate two `String` variables and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="c38b9-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="c38b9-121">See also</span></span>

- [<span data-ttu-id="c38b9-122">& 演算子</span><span class="sxs-lookup"><span data-stu-id="c38b9-122">& Operator</span></span>](../../../visual-basic/language-reference/operators/concatenation-operator.md)
- [<span data-ttu-id="c38b9-123">+= 演算子</span><span class="sxs-lookup"><span data-stu-id="c38b9-123">+= Operator</span></span>](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)
- [<span data-ttu-id="c38b9-124">代入演算子</span><span class="sxs-lookup"><span data-stu-id="c38b9-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="c38b9-125">連結演算子</span><span class="sxs-lookup"><span data-stu-id="c38b9-125">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="c38b9-126">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="c38b9-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="c38b9-127">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="c38b9-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="c38b9-128">ステートメント</span><span class="sxs-lookup"><span data-stu-id="c38b9-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
