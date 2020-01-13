---
title: Or 演算子
ms.date: 07/20/2015
f1_keywords:
- vb.Or
helpviewer_keywords:
- Or operator [Visual Basic]
- operators [Visual Basic], bitwise
- inclusive Or operator [Visual Basic]
- bitwise operators [Visual Basic], OR operator
- Or keyword [Visual Basic]
- operators [Visual Basic], inclusive or
- operators [Visual Basic], disjunction
- bitwise comparison [Visual Basic]
- logical disjunction
- disjunction operator [Visual Basic]
ms.assetid: 41ed6905-bf3d-468a-9e3b-03c10d461891
ms.openlocfilehash: 8f28026b526c29a6122725b2689e53b7f6ee7327
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348250"
---
# <a name="or-operator-visual-basic"></a><span data-ttu-id="d9b9b-102">Or 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9b9b-102">Or Operator (Visual Basic)</span></span>
<span data-ttu-id="d9b9b-103">2つの `Boolean` 式の論理和または2つの数値式のビットごとの和を実行します。</span><span class="sxs-lookup"><span data-stu-id="d9b9b-103">Performs a logical disjunction on two `Boolean` expressions, or a bitwise disjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9b9b-104">構文</span><span class="sxs-lookup"><span data-stu-id="d9b9b-104">Syntax</span></span>  
  
```vb  
result = expression1 Or expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="d9b9b-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="d9b9b-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="d9b9b-106">必須。</span><span class="sxs-lookup"><span data-stu-id="d9b9b-106">Required.</span></span> <span data-ttu-id="d9b9b-107">任意の `Boolean` または数値式。</span><span class="sxs-lookup"><span data-stu-id="d9b9b-107">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="d9b9b-108">`Boolean` 比較の場合、`result` は2つの `Boolean` 値の包括論理和です。</span><span class="sxs-lookup"><span data-stu-id="d9b9b-108">For `Boolean` comparison, `result` is the inclusive logical disjunction of two `Boolean` values.</span></span> <span data-ttu-id="d9b9b-109">ビットごとの演算の場合、`result` は、2つの数値ビットパターンの包括的なビットごとの和を表す数値です。</span><span class="sxs-lookup"><span data-stu-id="d9b9b-109">For bitwise operations, `result` is a numeric value representing the inclusive bitwise disjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="d9b9b-110">必須。</span><span class="sxs-lookup"><span data-stu-id="d9b9b-110">Required.</span></span> <span data-ttu-id="d9b9b-111">任意の `Boolean` または数値式。</span><span class="sxs-lookup"><span data-stu-id="d9b9b-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="d9b9b-112">必須。</span><span class="sxs-lookup"><span data-stu-id="d9b9b-112">Required.</span></span> <span data-ttu-id="d9b9b-113">任意の `Boolean` または数値式。</span><span class="sxs-lookup"><span data-stu-id="d9b9b-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d9b9b-114">コメント</span><span class="sxs-lookup"><span data-stu-id="d9b9b-114">Remarks</span></span>  
 <span data-ttu-id="d9b9b-115">`Boolean` 比較では、`expression1` と `expression2` の両方が `False`に評価される場合にのみ、`result` が `False` ます。</span><span class="sxs-lookup"><span data-stu-id="d9b9b-115">For `Boolean` comparison, `result` is `False` if and only if both `expression1` and `expression2` evaluate to `False`.</span></span> <span data-ttu-id="d9b9b-116">次の表は、`result` がどのように決定されるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="d9b9b-116">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="d9b9b-117">`expression1` の場合</span><span class="sxs-lookup"><span data-stu-id="d9b9b-117">If `expression1` is</span></span>|<span data-ttu-id="d9b9b-118">`expression2`</span><span class="sxs-lookup"><span data-stu-id="d9b9b-118">And `expression2` is</span></span>|<span data-ttu-id="d9b9b-119">`result` の値はです。</span><span class="sxs-lookup"><span data-stu-id="d9b9b-119">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> <span data-ttu-id="d9b9b-120">`Boolean` の比較では、`Or` 演算子は常に両方の式を評価します。これには、プロシージャ呼び出しを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d9b9b-120">In a `Boolean` comparison, the `Or` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="d9b9b-121">[OrElse 演算子](../../../visual-basic/language-reference/operators/orelse-operator.md)は*ショートサーキット*を実行します。つまり、`expression1` が `True`場合、`expression2` は評価されません。</span><span class="sxs-lookup"><span data-stu-id="d9b9b-121">The [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md) performs *short-circuiting*, which means that if `expression1` is `True`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="d9b9b-122">ビットごとの演算の場合、`Or` 演算子は2つの数値式で同一の位置ビットのビットごとの比較を実行し、次の表に従って `result` に対応するビットを設定します。</span><span class="sxs-lookup"><span data-stu-id="d9b9b-122">For bitwise operations, the `Or` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="d9b9b-123">`expression1` のビットがの場合</span><span class="sxs-lookup"><span data-stu-id="d9b9b-123">If bit in `expression1` is</span></span>|<span data-ttu-id="d9b9b-124">`expression2` のビットは</span><span class="sxs-lookup"><span data-stu-id="d9b9b-124">And bit in `expression2` is</span></span>|<span data-ttu-id="d9b9b-125">`result` のビットはです。</span><span class="sxs-lookup"><span data-stu-id="d9b9b-125">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="d9b9b-126">1</span><span class="sxs-lookup"><span data-stu-id="d9b9b-126">1</span></span>|<span data-ttu-id="d9b9b-127">1</span><span class="sxs-lookup"><span data-stu-id="d9b9b-127">1</span></span>|<span data-ttu-id="d9b9b-128">1</span><span class="sxs-lookup"><span data-stu-id="d9b9b-128">1</span></span>|  
|<span data-ttu-id="d9b9b-129">1</span><span class="sxs-lookup"><span data-stu-id="d9b9b-129">1</span></span>|<span data-ttu-id="d9b9b-130">0</span><span class="sxs-lookup"><span data-stu-id="d9b9b-130">0</span></span>|<span data-ttu-id="d9b9b-131">1</span><span class="sxs-lookup"><span data-stu-id="d9b9b-131">1</span></span>|  
|<span data-ttu-id="d9b9b-132">0</span><span class="sxs-lookup"><span data-stu-id="d9b9b-132">0</span></span>|<span data-ttu-id="d9b9b-133">1</span><span class="sxs-lookup"><span data-stu-id="d9b9b-133">1</span></span>|<span data-ttu-id="d9b9b-134">1</span><span class="sxs-lookup"><span data-stu-id="d9b9b-134">1</span></span>|  
|<span data-ttu-id="d9b9b-135">0</span><span class="sxs-lookup"><span data-stu-id="d9b9b-135">0</span></span>|<span data-ttu-id="d9b9b-136">0</span><span class="sxs-lookup"><span data-stu-id="d9b9b-136">0</span></span>|<span data-ttu-id="d9b9b-137">0</span><span class="sxs-lookup"><span data-stu-id="d9b9b-137">0</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="d9b9b-138">論理演算子とビット処理演算子は、他の算術演算子および関係演算子より優先順位が低いので、ビットごとの演算は、正確な実行を保証するためにかっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9b9b-138">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="d9b9b-139">データ型</span><span class="sxs-lookup"><span data-stu-id="d9b9b-139">Data Types</span></span>  
 <span data-ttu-id="d9b9b-140">オペランドが1つの `Boolean` 式と1つの数値式で構成されている場合、Visual Basic は `Boolean` 式を数値に変換し (`True` の場合は-1、`False`の場合は 0)、ビットごとの演算を実行します。</span><span class="sxs-lookup"><span data-stu-id="d9b9b-140">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="d9b9b-141">`Boolean` の比較では、結果のデータ型は `Boolean`です。</span><span class="sxs-lookup"><span data-stu-id="d9b9b-141">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="d9b9b-142">ビットごとの比較の場合、結果のデータ型は `expression1` および `expression2`のデータ型に適した数値型になります。</span><span class="sxs-lookup"><span data-stu-id="d9b9b-142">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="d9b9b-143">「[演算子の結果のデータ型](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)」の「リレーショナルおよびビットごとの比較」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9b9b-143">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="d9b9b-144">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="d9b9b-144">Overloading</span></span>  
 <span data-ttu-id="d9b9b-145">`Or` 演算子は*オーバーロード*することができます。つまり、クラスまたは構造体がそのクラスまたは構造体の型を持つ場合に、クラスまたは構造体がその動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="d9b9b-145">The `Or` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="d9b9b-146">コードでこのようなクラスまたは構造体に対してこの演算子を使用する場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d9b9b-146">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="d9b9b-147">詳細については、「[演算子プロシージャ](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9b9b-147">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9b9b-148">例</span><span class="sxs-lookup"><span data-stu-id="d9b9b-148">Example</span></span>  
 <span data-ttu-id="d9b9b-149">次の例では、`Or` 演算子を使用して、2つの式の包括論理和を実行します。</span><span class="sxs-lookup"><span data-stu-id="d9b9b-149">The following example uses the `Or` operator to perform an inclusive logical disjunction on two expressions.</span></span> <span data-ttu-id="d9b9b-150">結果は、2つの式のどちらかが `True`かどうかを示す `Boolean` 値になります。</span><span class="sxs-lookup"><span data-stu-id="d9b9b-150">The result is a `Boolean` value that represents whether either of the two expressions is `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#35)]  
  
 <span data-ttu-id="d9b9b-151">前の例では、`True`、`True`、および `False`の結果がそれぞれ生成されます。</span><span class="sxs-lookup"><span data-stu-id="d9b9b-151">The preceding example produces results of `True`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9b9b-152">例</span><span class="sxs-lookup"><span data-stu-id="d9b9b-152">Example</span></span>  
 <span data-ttu-id="d9b9b-153">次の例では、`Or` 演算子を使用して、2つの数値式の個々のビットに対して包括的論理和を実行します。</span><span class="sxs-lookup"><span data-stu-id="d9b9b-153">The following example uses the `Or` operator to perform inclusive logical disjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="d9b9b-154">オペランドの対応するビットのいずれかが1に設定されている場合、結果パターンのビットは設定されます。</span><span class="sxs-lookup"><span data-stu-id="d9b9b-154">The bit in the result pattern is set if either of the corresponding bits in the operands is set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#36)]  
  
 <span data-ttu-id="d9b9b-155">前の例では、それぞれ10、14、14の結果が生成されます。</span><span class="sxs-lookup"><span data-stu-id="d9b9b-155">The preceding example produces results of 10, 14, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9b9b-156">参照</span><span class="sxs-lookup"><span data-stu-id="d9b9b-156">See also</span></span>

- [<span data-ttu-id="d9b9b-157">論理/ビット演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9b9b-157">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="d9b9b-158">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="d9b9b-158">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="d9b9b-159">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="d9b9b-159">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="d9b9b-160">OrElse 演算子</span><span class="sxs-lookup"><span data-stu-id="d9b9b-160">OrElse Operator</span></span>](../../../visual-basic/language-reference/operators/orelse-operator.md)
- [<span data-ttu-id="d9b9b-161">Visual Basic の論理演算子とビット処理演算子</span><span class="sxs-lookup"><span data-stu-id="d9b9b-161">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
