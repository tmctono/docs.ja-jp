---
title: OrElse 演算子 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- OrElse
- vb.OrElse
helpviewer_keywords:
- short-circuiting
- operators [Visual Basic], short-circuiting
- operators [Visual Basic], disjunction
- short-circuit evaluation
- OrElse operator [Visual Basic]
ms.assetid: 253803d8-05b0-47d7-b213-abd222847779
ms.openlocfilehash: 02be78c8f2b7529f1fb0e46e9fe610a3c66b0652
ms.sourcegitcommit: 83ecdf731dc1920bca31f017b1556c917aafd7a0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2019
ms.locfileid: "67860140"
---
# <a name="orelse-operator-visual-basic"></a><span data-ttu-id="4de9d-102">OrElse 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4de9d-102">OrElse Operator (Visual Basic)</span></span>
<span data-ttu-id="4de9d-103">ショート サーキットの 2 つの式の包括的論理和演算を実行します。</span><span class="sxs-lookup"><span data-stu-id="4de9d-103">Performs short-circuiting inclusive logical disjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4de9d-104">構文</span><span class="sxs-lookup"><span data-stu-id="4de9d-104">Syntax</span></span>  
  
```vb
result = expression1 OrElse expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="4de9d-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="4de9d-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="4de9d-106">必須。</span><span class="sxs-lookup"><span data-stu-id="4de9d-106">Required.</span></span> <span data-ttu-id="4de9d-107">任意のブール型 ( `Boolean` ) の式を指定します。</span><span class="sxs-lookup"><span data-stu-id="4de9d-107">Any `Boolean` expression.</span></span>  
  
 `expression1`  
 <span data-ttu-id="4de9d-108">必須。</span><span class="sxs-lookup"><span data-stu-id="4de9d-108">Required.</span></span> <span data-ttu-id="4de9d-109">任意のブール型 ( `Boolean` ) の式を指定します。</span><span class="sxs-lookup"><span data-stu-id="4de9d-109">Any `Boolean` expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="4de9d-110">必須。</span><span class="sxs-lookup"><span data-stu-id="4de9d-110">Required.</span></span> <span data-ttu-id="4de9d-111">任意のブール型 ( `Boolean` ) の式を指定します。</span><span class="sxs-lookup"><span data-stu-id="4de9d-111">Any `Boolean` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4de9d-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="4de9d-112">Remarks</span></span>  
 <span data-ttu-id="4de9d-113">論理操作はモード*ショート サーキット*場合は、コンパイルされたコードは、別の式の結果に応じて 1 つの式の評価をバイパスできます。</span><span class="sxs-lookup"><span data-stu-id="4de9d-113">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="4de9d-114">最初に評価される式の結果には、操作の最終的な結果が判断した場合必要はありません 2 番目の式を評価するため、最終的な結果を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="4de9d-114">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="4de9d-115">ショート サーキットと、バイパスされる式は、複雑な場合、またはプロシージャの呼び出しが含まれる場合にパフォーマンスを向上できます。</span><span class="sxs-lookup"><span data-stu-id="4de9d-115">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="4de9d-116">いずれかまたは両方の式に評価される場合`True`、`result`は`True`します。</span><span class="sxs-lookup"><span data-stu-id="4de9d-116">If either or both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="4de9d-117">次の表はどのように`result`決定されます。</span><span class="sxs-lookup"><span data-stu-id="4de9d-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="4de9d-118">場合`expression1`は</span><span class="sxs-lookup"><span data-stu-id="4de9d-118">If `expression1` is</span></span>|<span data-ttu-id="4de9d-119">`expression2`は</span><span class="sxs-lookup"><span data-stu-id="4de9d-119">And `expression2` is</span></span>|<span data-ttu-id="4de9d-120">値`result`は</span><span class="sxs-lookup"><span data-stu-id="4de9d-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|<span data-ttu-id="4de9d-121">(評価されていません)</span><span class="sxs-lookup"><span data-stu-id="4de9d-121">(not evaluated)</span></span>|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="4de9d-122">データの種類</span><span class="sxs-lookup"><span data-stu-id="4de9d-122">Data Types</span></span>  
 <span data-ttu-id="4de9d-123">`OrElse`のみの演算子が定義されている、[ブール データ型](../../../visual-basic/language-reference/data-types/boolean-data-type.md)します。</span><span class="sxs-lookup"><span data-stu-id="4de9d-123">The `OrElse` operator is defined only for the [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span></span> <span data-ttu-id="4de9d-124">Visual Basic の変換を必要に応じて、各オペランド`Boolean`式を評価する前にします。</span><span class="sxs-lookup"><span data-stu-id="4de9d-124">Visual Basic converts each operand as necessary to `Boolean` before evaluating the expression.</span></span> <span data-ttu-id="4de9d-125">数値型に結果を割り当てた場合はこれからの Visual Basic に変換します`Boolean`その型にように`False`なります`0`と`True`なります`-1`。</span><span class="sxs-lookup"><span data-stu-id="4de9d-125">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type such that `False` becomes `0` and `True` becomes `-1`.</span></span>
<span data-ttu-id="4de9d-126">詳細については、次を参照してください[ブール型の変換。](../data-types/boolean-data-type.md#type-conversions)</span><span class="sxs-lookup"><span data-stu-id="4de9d-126">For more information, see [Boolean Type Conversions](../data-types/boolean-data-type.md#type-conversions)</span></span>
  
## <a name="overloading"></a><span data-ttu-id="4de9d-127">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="4de9d-127">Overloading</span></span>  
 <span data-ttu-id="4de9d-128">[または演算子](../../../visual-basic/language-reference/operators/or-operator.md)と[IsTrue 演算子](../../../visual-basic/language-reference/operators/istrue-operator.md)できる*オーバー ロードされた*、ことクラスまたは構造体は動作を再定義オペランドは、そのクラスの型を持つことを意味します。または、構造体。</span><span class="sxs-lookup"><span data-stu-id="4de9d-128">The [Or Operator](../../../visual-basic/language-reference/operators/or-operator.md) and the [IsTrue Operator](../../../visual-basic/language-reference/operators/istrue-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="4de9d-129">オーバー ロード、`Or`と`IsTrue`演算子の動作に影響、`OrElse`演算子。</span><span class="sxs-lookup"><span data-stu-id="4de9d-129">Overloading the `Or` and `IsTrue` operators affects the behavior of the `OrElse` operator.</span></span> <span data-ttu-id="4de9d-130">コードで使用する場合`OrElse`クラスまたは構造体をオーバー ロードで`Or`と`IsTrue`、その再定義された動作を確認してください。</span><span class="sxs-lookup"><span data-stu-id="4de9d-130">If your code uses `OrElse` on a class or structure that overloads `Or` and `IsTrue`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="4de9d-131">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4de9d-131">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4de9d-132">例</span><span class="sxs-lookup"><span data-stu-id="4de9d-132">Example</span></span>  
 <span data-ttu-id="4de9d-133">次の例では、`OrElse`演算子を 2 つの式に対して論理和演算を実行します。</span><span class="sxs-lookup"><span data-stu-id="4de9d-133">The following example uses the `OrElse` operator to perform logical disjunction on two expressions.</span></span> <span data-ttu-id="4de9d-134">結果は、`Boolean`値を表す 2 つの式のいずれかが true かどうか。</span><span class="sxs-lookup"><span data-stu-id="4de9d-134">The result is a `Boolean` value that represents whether either of the two expressions is true.</span></span> <span data-ttu-id="4de9d-135">最初の式が場合`True`、2 つ目は評価されません。</span><span class="sxs-lookup"><span data-stu-id="4de9d-135">If the first expression is `True`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#37)]  
  
 <span data-ttu-id="4de9d-136">前の例の結果を生成する`True`、 `True`、および`False`それぞれします。</span><span class="sxs-lookup"><span data-stu-id="4de9d-136">The preceding example produces results of `True`, `True`, and `False` respectively.</span></span> <span data-ttu-id="4de9d-137">計算に`firstCheck`、1 つは、既にあるために、2 番目の式は評価されません`True`します。</span><span class="sxs-lookup"><span data-stu-id="4de9d-137">In the calculation of `firstCheck`, the second expression is not evaluated because the first is already `True`.</span></span> <span data-ttu-id="4de9d-138">計算に 2 番目の式を評価するただし、`secondCheck`します。</span><span class="sxs-lookup"><span data-stu-id="4de9d-138">However, the second expression is evaluated in the calculation of `secondCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4de9d-139">例</span><span class="sxs-lookup"><span data-stu-id="4de9d-139">Example</span></span>  
 <span data-ttu-id="4de9d-140">次の例は、 `If`.`Then` 2 つのプロシージャ呼び出しを含むステートメント。</span><span class="sxs-lookup"><span data-stu-id="4de9d-140">The following example shows an `If`...`Then` statement containing two procedure calls.</span></span> <span data-ttu-id="4de9d-141">最初の呼び出しが返された場合`True`、2 番目の手順は呼び出されません。</span><span class="sxs-lookup"><span data-stu-id="4de9d-141">If the first call returns `True`, the second procedure is not called.</span></span> <span data-ttu-id="4de9d-142">2 番目の手順で、コードのこのセクションの実行時に常に実行する重要なタスクを実行する場合は、予期しない結果を生成これでした。</span><span class="sxs-lookup"><span data-stu-id="4de9d-142">This could produce unexpected results if the second procedure performs important tasks that should always be performed when this section of the code runs.</span></span>  
  
 [!code-vb[VbVbalrOperators#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#38)]  
  
## <a name="see-also"></a><span data-ttu-id="4de9d-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="4de9d-143">See also</span></span>

- [<span data-ttu-id="4de9d-144">論理/ビット演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4de9d-144">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="4de9d-145">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="4de9d-145">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="4de9d-146">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="4de9d-146">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="4de9d-147">Or 演算子</span><span class="sxs-lookup"><span data-stu-id="4de9d-147">Or Operator</span></span>](../../../visual-basic/language-reference/operators/or-operator.md)
- [<span data-ttu-id="4de9d-148">IsTrue 演算子</span><span class="sxs-lookup"><span data-stu-id="4de9d-148">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [<span data-ttu-id="4de9d-149">Visual Basic での論理とビット処理演算子</span><span class="sxs-lookup"><span data-stu-id="4de9d-149">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
