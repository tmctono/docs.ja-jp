---
title: AndAlso 演算子 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.AndAlso
- AndAlso
helpviewer_keywords:
- short-circuiting
- AndAlso operator [Visual Basic]
- operators [Visual Basic], short-circuiting
- operators [Visual Basic], conjunction
- short-circuit evaluation
ms.assetid: bbc15191-b374-495b-9b8f-7b8c2f4388eb
ms.openlocfilehash: 5ba8be5051d0723fd2654b9733933cd434ac3ac5
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965190"
---
# <a name="andalso-operator-visual-basic"></a><span data-ttu-id="ebaa8-102">AndAlso 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ebaa8-102">AndAlso Operator (Visual Basic)</span></span>
<span data-ttu-id="ebaa8-103">ショート サーキットの 2 つの式の論理積を実行します。</span><span class="sxs-lookup"><span data-stu-id="ebaa8-103">Performs short-circuiting logical conjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebaa8-104">構文</span><span class="sxs-lookup"><span data-stu-id="ebaa8-104">Syntax</span></span>  
  
```  
result = expression1 AndAlso expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="ebaa8-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="ebaa8-105">Parts</span></span>  
  
|<span data-ttu-id="ebaa8-106">用語</span><span class="sxs-lookup"><span data-stu-id="ebaa8-106">Term</span></span>|<span data-ttu-id="ebaa8-107">定義</span><span class="sxs-lookup"><span data-stu-id="ebaa8-107">Definition</span></span>|  
|---|---|  
|`result`|<span data-ttu-id="ebaa8-108">必須。</span><span class="sxs-lookup"><span data-stu-id="ebaa8-108">Required.</span></span> <span data-ttu-id="ebaa8-109">任意のブール型 ( `Boolean` ) の式を指定します。</span><span class="sxs-lookup"><span data-stu-id="ebaa8-109">Any `Boolean` expression.</span></span> <span data-ttu-id="ebaa8-110">結果は、 `Boolean` 2 つの式の比較の結果。</span><span class="sxs-lookup"><span data-stu-id="ebaa8-110">The result is the `Boolean` result of comparison of the two expressions.</span></span>|  
|`expression1`|<span data-ttu-id="ebaa8-111">必須。</span><span class="sxs-lookup"><span data-stu-id="ebaa8-111">Required.</span></span> <span data-ttu-id="ebaa8-112">任意のブール型 ( `Boolean` ) の式を指定します。</span><span class="sxs-lookup"><span data-stu-id="ebaa8-112">Any `Boolean` expression.</span></span>|  
|`expression2`|<span data-ttu-id="ebaa8-113">必須。</span><span class="sxs-lookup"><span data-stu-id="ebaa8-113">Required.</span></span> <span data-ttu-id="ebaa8-114">任意のブール型 ( `Boolean` ) の式を指定します。</span><span class="sxs-lookup"><span data-stu-id="ebaa8-114">Any `Boolean` expression.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ebaa8-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="ebaa8-115">Remarks</span></span>  
 <span data-ttu-id="ebaa8-116">論理操作はモード*ショート サーキット*場合は、コンパイルされたコードは、別の式の結果に応じて 1 つの式の評価をバイパスできます。</span><span class="sxs-lookup"><span data-stu-id="ebaa8-116">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="ebaa8-117">最初に評価される式の結果には、操作の最終的な結果が判断した場合必要はありません 2 番目の式を評価するため、最終的な結果を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="ebaa8-117">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="ebaa8-118">ショート サーキットと、バイパスされる式は、複雑な場合、またはプロシージャの呼び出しが含まれる場合にパフォーマンスを向上できます。</span><span class="sxs-lookup"><span data-stu-id="ebaa8-118">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="ebaa8-119">両方の式が評価される場合`True`、`result`は`True`します。</span><span class="sxs-lookup"><span data-stu-id="ebaa8-119">If both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="ebaa8-120">次の表はどのように`result`決定されます。</span><span class="sxs-lookup"><span data-stu-id="ebaa8-120">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="ebaa8-121">場合`expression1`は</span><span class="sxs-lookup"><span data-stu-id="ebaa8-121">If `expression1` is</span></span>|<span data-ttu-id="ebaa8-122">`expression2`は</span><span class="sxs-lookup"><span data-stu-id="ebaa8-122">And `expression2` is</span></span>|<span data-ttu-id="ebaa8-123">値`result`は</span><span class="sxs-lookup"><span data-stu-id="ebaa8-123">The value of `result` is</span></span>|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|<span data-ttu-id="ebaa8-124">(評価されていません)</span><span class="sxs-lookup"><span data-stu-id="ebaa8-124">(not evaluated)</span></span>|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="ebaa8-125">データの種類</span><span class="sxs-lookup"><span data-stu-id="ebaa8-125">Data Types</span></span>  
 <span data-ttu-id="ebaa8-126">`AndAlso`のみの演算子が定義されている、[ブール データ型](../../../visual-basic/language-reference/data-types/boolean-data-type.md)します。</span><span class="sxs-lookup"><span data-stu-id="ebaa8-126">The `AndAlso` operator is defined only for the [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span></span> <span data-ttu-id="ebaa8-127">Visual Basic の変換を必要に応じて、各オペランド`Boolean`全体での操作を実行および`Boolean`します。</span><span class="sxs-lookup"><span data-stu-id="ebaa8-127">Visual Basic converts each operand as necessary to `Boolean` and performs the operation entirely in `Boolean`.</span></span> <span data-ttu-id="ebaa8-128">Visual Basic 変換から数値型に結果を割り当てた場合`Boolean`その型にします。</span><span class="sxs-lookup"><span data-stu-id="ebaa8-128">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type.</span></span> <span data-ttu-id="ebaa8-129">これにより、予期しない動作が生成する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ebaa8-129">This could produce unexpected behavior.</span></span> <span data-ttu-id="ebaa8-130">たとえば、`5 AndAlso 12`結果`–1`に変換される`Integer`します。</span><span class="sxs-lookup"><span data-stu-id="ebaa8-130">For example, `5 AndAlso 12` results in `–1` when converted to `Integer`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="ebaa8-131">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="ebaa8-131">Overloading</span></span>  
 <span data-ttu-id="ebaa8-132">[And 演算子](../../../visual-basic/language-reference/operators/and-operator.md)と[IsFalse 演算子](../../../visual-basic/language-reference/operators/isfalse-operator.md)できる*オーバー ロードされた*、いるクラスまたは構造体を再定義できますの動作はその型つまりクラスまたは構造体。</span><span class="sxs-lookup"><span data-stu-id="ebaa8-132">The [And Operator](../../../visual-basic/language-reference/operators/and-operator.md) and the [IsFalse Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="ebaa8-133">オーバー ロード、`And`と`IsFalse`演算子の動作に影響、`AndAlso`演算子。</span><span class="sxs-lookup"><span data-stu-id="ebaa8-133">Overloading the `And` and `IsFalse` operators affects the behavior of the `AndAlso` operator.</span></span> <span data-ttu-id="ebaa8-134">コードで使用する場合`AndAlso`クラスまたは構造体をオーバー ロードで`And`と`IsFalse`、その再定義された動作を確認してください。</span><span class="sxs-lookup"><span data-stu-id="ebaa8-134">If your code uses `AndAlso` on a class or structure that overloads `And` and `IsFalse`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="ebaa8-135">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebaa8-135">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ebaa8-136">例</span><span class="sxs-lookup"><span data-stu-id="ebaa8-136">Example</span></span>  
 <span data-ttu-id="ebaa8-137">次の例では、`AndAlso`演算子を 2 つの式に対して論理積を実行します。</span><span class="sxs-lookup"><span data-stu-id="ebaa8-137">The following example uses the `AndAlso` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="ebaa8-138">結果は、`Boolean`全体が式を連結するかどうかを表す値は true。</span><span class="sxs-lookup"><span data-stu-id="ebaa8-138">The result is a `Boolean` value that represents whether the entire conjoined expression is true.</span></span> <span data-ttu-id="ebaa8-139">最初の式が場合`False`、2 つ目は評価されません。</span><span class="sxs-lookup"><span data-stu-id="ebaa8-139">If the first expression is `False`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#24)]  
  
 <span data-ttu-id="ebaa8-140">前の例の結果を生成する`True`、 `False`、および`False`、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="ebaa8-140">The preceding example produces results of `True`, `False`, and `False`, respectively.</span></span> <span data-ttu-id="ebaa8-141">計算に`secondCheck`、1 つは、既にあるために、2 番目の式は評価されません`False`します。</span><span class="sxs-lookup"><span data-stu-id="ebaa8-141">In the calculation of `secondCheck`, the second expression is not evaluated because the first is already `False`.</span></span> <span data-ttu-id="ebaa8-142">計算に 2 番目の式を評価するただし、`thirdCheck`します。</span><span class="sxs-lookup"><span data-stu-id="ebaa8-142">However, the second expression is evaluated in the calculation of `thirdCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ebaa8-143">例</span><span class="sxs-lookup"><span data-stu-id="ebaa8-143">Example</span></span>  
 <span data-ttu-id="ebaa8-144">次の例は、`Function`プロシージャの配列の要素間で指定された値を検索します。</span><span class="sxs-lookup"><span data-stu-id="ebaa8-144">The following example shows a `Function` procedure that searches for a given value among the elements of an array.</span></span> <span data-ttu-id="ebaa8-145">配列が空の場合、または配列の長さを超過した場合、`While`ステートメントでは、検索する値に対して配列の要素はテストしません。</span><span class="sxs-lookup"><span data-stu-id="ebaa8-145">If the array is empty, or if the array length has been exceeded, the `While` statement does not test the array element against the search value.</span></span>  
  
 [!code-vb[VbVbalrOperators#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#25)]  
  
## <a name="see-also"></a><span data-ttu-id="ebaa8-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="ebaa8-146">See also</span></span>
- [<span data-ttu-id="ebaa8-147">論理/ビット演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ebaa8-147">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="ebaa8-148">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="ebaa8-148">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="ebaa8-149">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="ebaa8-149">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="ebaa8-150">And 演算子</span><span class="sxs-lookup"><span data-stu-id="ebaa8-150">And Operator</span></span>](../../../visual-basic/language-reference/operators/and-operator.md)
- [<span data-ttu-id="ebaa8-151">IsFalse 演算子</span><span class="sxs-lookup"><span data-stu-id="ebaa8-151">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [<span data-ttu-id="ebaa8-152">Visual Basic での論理とビット処理演算子</span><span class="sxs-lookup"><span data-stu-id="ebaa8-152">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
