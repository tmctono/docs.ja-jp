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
ms.openlocfilehash: 1cb4d372d3ac228f29c6fa45f124796e5dfb6709
ms.sourcegitcommit: 83ecdf731dc1920bca31f017b1556c917aafd7a0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2019
ms.locfileid: "67859886"
---
# <a name="andalso-operator-visual-basic"></a><span data-ttu-id="da9ff-102">AndAlso 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="da9ff-102">AndAlso Operator (Visual Basic)</span></span>
<span data-ttu-id="da9ff-103">ショート サーキットの 2 つの式の論理積を実行します。</span><span class="sxs-lookup"><span data-stu-id="da9ff-103">Performs short-circuiting logical conjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da9ff-104">構文</span><span class="sxs-lookup"><span data-stu-id="da9ff-104">Syntax</span></span>  
  
```vb
result = expression1 AndAlso expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="da9ff-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="da9ff-105">Parts</span></span>  
  
|<span data-ttu-id="da9ff-106">用語</span><span class="sxs-lookup"><span data-stu-id="da9ff-106">Term</span></span>|<span data-ttu-id="da9ff-107">定義</span><span class="sxs-lookup"><span data-stu-id="da9ff-107">Definition</span></span>|  
|---|---|  
|`result`|<span data-ttu-id="da9ff-108">必須。</span><span class="sxs-lookup"><span data-stu-id="da9ff-108">Required.</span></span> <span data-ttu-id="da9ff-109">任意のブール型 ( `Boolean` ) の式を指定します。</span><span class="sxs-lookup"><span data-stu-id="da9ff-109">Any `Boolean` expression.</span></span> <span data-ttu-id="da9ff-110">結果は、 `Boolean` 2 つの式の比較の結果。</span><span class="sxs-lookup"><span data-stu-id="da9ff-110">The result is the `Boolean` result of comparison of the two expressions.</span></span>|  
|`expression1`|<span data-ttu-id="da9ff-111">必須。</span><span class="sxs-lookup"><span data-stu-id="da9ff-111">Required.</span></span> <span data-ttu-id="da9ff-112">任意のブール型 ( `Boolean` ) の式を指定します。</span><span class="sxs-lookup"><span data-stu-id="da9ff-112">Any `Boolean` expression.</span></span>|  
|`expression2`|<span data-ttu-id="da9ff-113">必須。</span><span class="sxs-lookup"><span data-stu-id="da9ff-113">Required.</span></span> <span data-ttu-id="da9ff-114">任意のブール型 ( `Boolean` ) の式を指定します。</span><span class="sxs-lookup"><span data-stu-id="da9ff-114">Any `Boolean` expression.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="da9ff-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="da9ff-115">Remarks</span></span>  
 <span data-ttu-id="da9ff-116">論理操作はモード*ショート サーキット*場合は、コンパイルされたコードは、別の式の結果に応じて 1 つの式の評価をバイパスできます。</span><span class="sxs-lookup"><span data-stu-id="da9ff-116">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="da9ff-117">最初に評価される式の結果には、操作の最終的な結果が判断した場合必要はありません 2 番目の式を評価するため、最終的な結果を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="da9ff-117">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="da9ff-118">ショート サーキットと、バイパスされる式は、複雑な場合、またはプロシージャの呼び出しが含まれる場合にパフォーマンスを向上できます。</span><span class="sxs-lookup"><span data-stu-id="da9ff-118">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="da9ff-119">両方の式が評価される場合`True`、`result`は`True`します。</span><span class="sxs-lookup"><span data-stu-id="da9ff-119">If both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="da9ff-120">次の表はどのように`result`決定されます。</span><span class="sxs-lookup"><span data-stu-id="da9ff-120">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="da9ff-121">場合`expression1`は</span><span class="sxs-lookup"><span data-stu-id="da9ff-121">If `expression1` is</span></span>|<span data-ttu-id="da9ff-122">`expression2`は</span><span class="sxs-lookup"><span data-stu-id="da9ff-122">And `expression2` is</span></span>|<span data-ttu-id="da9ff-123">値`result`は</span><span class="sxs-lookup"><span data-stu-id="da9ff-123">The value of `result` is</span></span>|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|<span data-ttu-id="da9ff-124">(評価されていません)</span><span class="sxs-lookup"><span data-stu-id="da9ff-124">(not evaluated)</span></span>|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="da9ff-125">データの種類</span><span class="sxs-lookup"><span data-stu-id="da9ff-125">Data Types</span></span>  
 <span data-ttu-id="da9ff-126">`AndAlso`のみの演算子が定義されている、[ブール データ型](../../../visual-basic/language-reference/data-types/boolean-data-type.md)します。</span><span class="sxs-lookup"><span data-stu-id="da9ff-126">The `AndAlso` operator is defined only for the [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span></span> <span data-ttu-id="da9ff-127">Visual Basic の変換を必要に応じて、各オペランド`Boolean`式を評価する前にします。</span><span class="sxs-lookup"><span data-stu-id="da9ff-127">Visual Basic converts each operand as necessary to `Boolean` before evaluating the expression.</span></span> <span data-ttu-id="da9ff-128">数値型に結果を割り当てた場合はこれからの Visual Basic に変換します`Boolean`その型にように`False`なります`0`と`True`なります`-1`。</span><span class="sxs-lookup"><span data-stu-id="da9ff-128">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type such that `False` becomes `0` and `True` becomes `-1`.</span></span>
<span data-ttu-id="da9ff-129">詳細については、次を参照してください[ブール型の変換。](../data-types/boolean-data-type.md#type-conversions)</span><span class="sxs-lookup"><span data-stu-id="da9ff-129">For more information, see [Boolean Type Conversions](../data-types/boolean-data-type.md#type-conversions)</span></span>
  
## <a name="overloading"></a><span data-ttu-id="da9ff-130">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="da9ff-130">Overloading</span></span>  
 <span data-ttu-id="da9ff-131">[And 演算子](../../../visual-basic/language-reference/operators/and-operator.md)と[IsFalse 演算子](../../../visual-basic/language-reference/operators/isfalse-operator.md)できる*オーバー ロードされた*、いるクラスまたは構造体を再定義できますの動作はその型つまりクラスまたは構造体。</span><span class="sxs-lookup"><span data-stu-id="da9ff-131">The [And Operator](../../../visual-basic/language-reference/operators/and-operator.md) and the [IsFalse Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="da9ff-132">オーバー ロード、`And`と`IsFalse`演算子の動作に影響、`AndAlso`演算子。</span><span class="sxs-lookup"><span data-stu-id="da9ff-132">Overloading the `And` and `IsFalse` operators affects the behavior of the `AndAlso` operator.</span></span> <span data-ttu-id="da9ff-133">コードで使用する場合`AndAlso`クラスまたは構造体をオーバー ロードで`And`と`IsFalse`、その再定義された動作を確認してください。</span><span class="sxs-lookup"><span data-stu-id="da9ff-133">If your code uses `AndAlso` on a class or structure that overloads `And` and `IsFalse`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="da9ff-134">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da9ff-134">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="da9ff-135">例</span><span class="sxs-lookup"><span data-stu-id="da9ff-135">Example</span></span>  
 <span data-ttu-id="da9ff-136">次の例では、`AndAlso`演算子を 2 つの式に対して論理積を実行します。</span><span class="sxs-lookup"><span data-stu-id="da9ff-136">The following example uses the `AndAlso` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="da9ff-137">結果は、`Boolean`全体が式を連結するかどうかを表す値は true。</span><span class="sxs-lookup"><span data-stu-id="da9ff-137">The result is a `Boolean` value that represents whether the entire conjoined expression is true.</span></span> <span data-ttu-id="da9ff-138">最初の式が場合`False`、2 つ目は評価されません。</span><span class="sxs-lookup"><span data-stu-id="da9ff-138">If the first expression is `False`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#24)]  
  
 <span data-ttu-id="da9ff-139">前の例の結果を生成する`True`、 `False`、および`False`、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="da9ff-139">The preceding example produces results of `True`, `False`, and `False`, respectively.</span></span> <span data-ttu-id="da9ff-140">計算に`secondCheck`、1 つは、既にあるために、2 番目の式は評価されません`False`します。</span><span class="sxs-lookup"><span data-stu-id="da9ff-140">In the calculation of `secondCheck`, the second expression is not evaluated because the first is already `False`.</span></span> <span data-ttu-id="da9ff-141">計算に 2 番目の式を評価するただし、`thirdCheck`します。</span><span class="sxs-lookup"><span data-stu-id="da9ff-141">However, the second expression is evaluated in the calculation of `thirdCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da9ff-142">例</span><span class="sxs-lookup"><span data-stu-id="da9ff-142">Example</span></span>  
 <span data-ttu-id="da9ff-143">次の例は、`Function`プロシージャの配列の要素間で指定された値を検索します。</span><span class="sxs-lookup"><span data-stu-id="da9ff-143">The following example shows a `Function` procedure that searches for a given value among the elements of an array.</span></span> <span data-ttu-id="da9ff-144">配列が空の場合、または配列の長さを超過した場合、`While`ステートメントでは、検索する値に対して配列の要素はテストしません。</span><span class="sxs-lookup"><span data-stu-id="da9ff-144">If the array is empty, or if the array length has been exceeded, the `While` statement does not test the array element against the search value.</span></span>  
  
 [!code-vb[VbVbalrOperators#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#25)]  
  
## <a name="see-also"></a><span data-ttu-id="da9ff-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="da9ff-145">See also</span></span>

- [<span data-ttu-id="da9ff-146">論理/ビット演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="da9ff-146">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="da9ff-147">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="da9ff-147">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="da9ff-148">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="da9ff-148">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="da9ff-149">And 演算子</span><span class="sxs-lookup"><span data-stu-id="da9ff-149">And Operator</span></span>](../../../visual-basic/language-reference/operators/and-operator.md)
- [<span data-ttu-id="da9ff-150">IsFalse 演算子</span><span class="sxs-lookup"><span data-stu-id="da9ff-150">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [<span data-ttu-id="da9ff-151">Visual Basic での論理とビット処理演算子</span><span class="sxs-lookup"><span data-stu-id="da9ff-151">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
