---
title: OrElse 演算子
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
ms.openlocfilehash: 361de44711c3b41411f2fa1dd81a3dd8db6b01e6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348242"
---
# <a name="orelse-operator-visual-basic"></a><span data-ttu-id="d9d2c-102">OrElse 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9d2c-102">OrElse Operator (Visual Basic)</span></span>
<span data-ttu-id="d9d2c-103">2つの式のショートサーキット包括論理和を実行します。</span><span class="sxs-lookup"><span data-stu-id="d9d2c-103">Performs short-circuiting inclusive logical disjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9d2c-104">構文</span><span class="sxs-lookup"><span data-stu-id="d9d2c-104">Syntax</span></span>  
  
```vb
result = expression1 OrElse expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="d9d2c-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="d9d2c-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="d9d2c-106">必須。</span><span class="sxs-lookup"><span data-stu-id="d9d2c-106">Required.</span></span> <span data-ttu-id="d9d2c-107">任意のブール型 ( `Boolean` ) の式を指定します。</span><span class="sxs-lookup"><span data-stu-id="d9d2c-107">Any `Boolean` expression.</span></span>  
  
 `expression1`  
 <span data-ttu-id="d9d2c-108">必須。</span><span class="sxs-lookup"><span data-stu-id="d9d2c-108">Required.</span></span> <span data-ttu-id="d9d2c-109">任意のブール型 ( `Boolean` ) の式を指定します。</span><span class="sxs-lookup"><span data-stu-id="d9d2c-109">Any `Boolean` expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="d9d2c-110">必須。</span><span class="sxs-lookup"><span data-stu-id="d9d2c-110">Required.</span></span> <span data-ttu-id="d9d2c-111">任意のブール型 ( `Boolean` ) の式を指定します。</span><span class="sxs-lookup"><span data-stu-id="d9d2c-111">Any `Boolean` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d9d2c-112">コメント</span><span class="sxs-lookup"><span data-stu-id="d9d2c-112">Remarks</span></span>  
 <span data-ttu-id="d9d2c-113">コンパイルされたコードが別の式の結果に応じて1つの式の評価をバイパスできる場合、論理操作は*ショートサーキット*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="d9d2c-113">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="d9d2c-114">最初に評価された式の結果が演算の最終結果を決定した場合、最終的な結果を変更できないため、2番目の式を評価する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d9d2c-114">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="d9d2c-115">ショートサーキットは、バイパスされた式が複雑な場合や、プロシージャ呼び出しが関係している場合に、パフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="d9d2c-115">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="d9d2c-116">いずれかまたは両方の式が `True`に評価される場合、`result` は `True`です。</span><span class="sxs-lookup"><span data-stu-id="d9d2c-116">If either or both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="d9d2c-117">次の表は、`result` がどのように決定されるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="d9d2c-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="d9d2c-118">`expression1` の場合</span><span class="sxs-lookup"><span data-stu-id="d9d2c-118">If `expression1` is</span></span>|<span data-ttu-id="d9d2c-119">`expression2`</span><span class="sxs-lookup"><span data-stu-id="d9d2c-119">And `expression2` is</span></span>|<span data-ttu-id="d9d2c-120">`result` の値はです。</span><span class="sxs-lookup"><span data-stu-id="d9d2c-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|<span data-ttu-id="d9d2c-121">(評価なし)</span><span class="sxs-lookup"><span data-stu-id="d9d2c-121">(not evaluated)</span></span>|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="d9d2c-122">データ型</span><span class="sxs-lookup"><span data-stu-id="d9d2c-122">Data Types</span></span>  
 <span data-ttu-id="d9d2c-123">`OrElse` 演算子は、[ブールデータ型](../../../visual-basic/language-reference/data-types/boolean-data-type.md)に対してのみ定義されます。</span><span class="sxs-lookup"><span data-stu-id="d9d2c-123">The `OrElse` operator is defined only for the [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span></span> <span data-ttu-id="d9d2c-124">Visual Basic は、式を評価する前に、必要に応じて各オペランドを `Boolean` に変換します。</span><span class="sxs-lookup"><span data-stu-id="d9d2c-124">Visual Basic converts each operand as necessary to `Boolean` before evaluating the expression.</span></span> <span data-ttu-id="d9d2c-125">結果を数値型に代入すると、Visual Basic によって `Boolean` からその型に変換され、`False` が `0` になり、`True` が `-1`になります。</span><span class="sxs-lookup"><span data-stu-id="d9d2c-125">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type such that `False` becomes `0` and `True` becomes `-1`.</span></span>
<span data-ttu-id="d9d2c-126">詳細については、「[ブール型変換](../data-types/boolean-data-type.md#type-conversions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9d2c-126">For more information, see [Boolean Type Conversions](../data-types/boolean-data-type.md#type-conversions).</span></span>
  
## <a name="overloading"></a><span data-ttu-id="d9d2c-127">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="d9d2c-127">Overloading</span></span>  
 <span data-ttu-id="d9d2c-128">[Or 演算子](../../../visual-basic/language-reference/operators/or-operator.md)と[IsTrue 演算子](../../../visual-basic/language-reference/operators/istrue-operator.md)を*オーバーロード*することができます。つまり、クラスまたは構造体が、そのクラスまたは構造体の型を持つ場合に、その動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="d9d2c-128">The [Or Operator](../../../visual-basic/language-reference/operators/or-operator.md) and the [IsTrue Operator](../../../visual-basic/language-reference/operators/istrue-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="d9d2c-129">`Or` 演算子と `IsTrue` 演算子のオーバーロードは、`OrElse` 演算子の動作に影響します。</span><span class="sxs-lookup"><span data-stu-id="d9d2c-129">Overloading the `Or` and `IsTrue` operators affects the behavior of the `OrElse` operator.</span></span> <span data-ttu-id="d9d2c-130">コードで `Or` と `IsTrue`をオーバーロードするクラスまたは構造体の `OrElse` を使用する場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d9d2c-130">If your code uses `OrElse` on a class or structure that overloads `Or` and `IsTrue`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="d9d2c-131">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9d2c-131">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9d2c-132">例</span><span class="sxs-lookup"><span data-stu-id="d9d2c-132">Example</span></span>  
 <span data-ttu-id="d9d2c-133">次の例では、`OrElse` 演算子を使用して、2つの式の論理和を実行します。</span><span class="sxs-lookup"><span data-stu-id="d9d2c-133">The following example uses the `OrElse` operator to perform logical disjunction on two expressions.</span></span> <span data-ttu-id="d9d2c-134">結果は、2つの式のいずれかが true であるかどうかを示す `Boolean` 値になります。</span><span class="sxs-lookup"><span data-stu-id="d9d2c-134">The result is a `Boolean` value that represents whether either of the two expressions is true.</span></span> <span data-ttu-id="d9d2c-135">最初の式が `True`場合、2番目の式は評価されません。</span><span class="sxs-lookup"><span data-stu-id="d9d2c-135">If the first expression is `True`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#37)]  
  
 <span data-ttu-id="d9d2c-136">前の例では、`True`、`True`、および `False` の結果がそれぞれ生成されます。</span><span class="sxs-lookup"><span data-stu-id="d9d2c-136">The preceding example produces results of `True`, `True`, and `False` respectively.</span></span> <span data-ttu-id="d9d2c-137">`firstCheck`の計算では、最初の式が既に `True`ているため、2番目の式は評価されません。</span><span class="sxs-lookup"><span data-stu-id="d9d2c-137">In the calculation of `firstCheck`, the second expression is not evaluated because the first is already `True`.</span></span> <span data-ttu-id="d9d2c-138">ただし、2番目の式は `secondCheck`の計算で評価されます。</span><span class="sxs-lookup"><span data-stu-id="d9d2c-138">However, the second expression is evaluated in the calculation of `secondCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9d2c-139">例</span><span class="sxs-lookup"><span data-stu-id="d9d2c-139">Example</span></span>  
 <span data-ttu-id="d9d2c-140">次の例は、2つのプロシージャ呼び出しを含む `If`...`Then` ステートメントを示しています。</span><span class="sxs-lookup"><span data-stu-id="d9d2c-140">The following example shows an `If`...`Then` statement containing two procedure calls.</span></span> <span data-ttu-id="d9d2c-141">最初の呼び出しで `True`が返された場合、2番目のプロシージャは呼び出されません。</span><span class="sxs-lookup"><span data-stu-id="d9d2c-141">If the first call returns `True`, the second procedure is not called.</span></span> <span data-ttu-id="d9d2c-142">この場合、2番目のプロシージャが、コードのこのセクションの実行時に常に実行する必要がある重要なタスクを実行すると、予期しない結果が生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d9d2c-142">This could produce unexpected results if the second procedure performs important tasks that should always be performed when this section of the code runs.</span></span>  
  
 [!code-vb[VbVbalrOperators#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#38)]  
  
## <a name="see-also"></a><span data-ttu-id="d9d2c-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="d9d2c-143">See also</span></span>

- [<span data-ttu-id="d9d2c-144">論理/ビット演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9d2c-144">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="d9d2c-145">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="d9d2c-145">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="d9d2c-146">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="d9d2c-146">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="d9d2c-147">Or 演算子</span><span class="sxs-lookup"><span data-stu-id="d9d2c-147">Or Operator</span></span>](../../../visual-basic/language-reference/operators/or-operator.md)
- [<span data-ttu-id="d9d2c-148">IsTrue 演算子</span><span class="sxs-lookup"><span data-stu-id="d9d2c-148">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [<span data-ttu-id="d9d2c-149">Visual Basic の論理演算子とビット処理演算子</span><span class="sxs-lookup"><span data-stu-id="d9d2c-149">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
