---
title: And 演算子
ms.date: 07/20/2015
f1_keywords:
- vb.And
helpviewer_keywords:
- operators [Visual Basic], bitwise
- logical conjunction
- bitwise AND operator [Visual Basic]
- conjunction operator [Visual Basic]
- And operator [Visual Basic]
- bitwise operators [Visual Basic], AND operator
- operators [Visual Basic], conjunction
- bitwise comparison [Visual Basic]
ms.assetid: 2ea711f3-439a-4c7c-9e3a-1ffe3b0d6046
ms.openlocfilehash: 78a65843a449bd15d5615710e1685f40d94c37f7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350254"
---
# <a name="and-operator-visual-basic"></a><span data-ttu-id="24eee-102">And 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="24eee-102">And Operator (Visual Basic)</span></span>
<span data-ttu-id="24eee-103">2つの `Boolean` 式、または2つの数値式のビットごとの組み合わせに対して論理積を実行します。</span><span class="sxs-lookup"><span data-stu-id="24eee-103">Performs a logical conjunction on two `Boolean` expressions, or a bitwise conjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24eee-104">構文</span><span class="sxs-lookup"><span data-stu-id="24eee-104">Syntax</span></span>  
  
```vb  
result = expression1 And expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="24eee-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="24eee-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="24eee-106">必須。</span><span class="sxs-lookup"><span data-stu-id="24eee-106">Required.</span></span> <span data-ttu-id="24eee-107">任意の `Boolean` または数値式。</span><span class="sxs-lookup"><span data-stu-id="24eee-107">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="24eee-108">ブール型の比較の場合、`result` は2つの `Boolean` 値の論理積となります。</span><span class="sxs-lookup"><span data-stu-id="24eee-108">For Boolean comparison, `result` is the logical conjunction of two `Boolean` values.</span></span> <span data-ttu-id="24eee-109">ビットごとの演算の場合、`result` は2つの数値ビットパターンのビットごとの組み合わせを表す数値です。</span><span class="sxs-lookup"><span data-stu-id="24eee-109">For bitwise operations, `result` is a numeric value representing the bitwise conjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="24eee-110">必須。</span><span class="sxs-lookup"><span data-stu-id="24eee-110">Required.</span></span> <span data-ttu-id="24eee-111">任意の `Boolean` または数値式。</span><span class="sxs-lookup"><span data-stu-id="24eee-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="24eee-112">必須。</span><span class="sxs-lookup"><span data-stu-id="24eee-112">Required.</span></span> <span data-ttu-id="24eee-113">任意の `Boolean` または数値式。</span><span class="sxs-lookup"><span data-stu-id="24eee-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24eee-114">コメント</span><span class="sxs-lookup"><span data-stu-id="24eee-114">Remarks</span></span>  
 <span data-ttu-id="24eee-115">ブール値の比較では、`expression1` と `expression2` の両方が `True`に評価される場合にのみ、`result` が `True` ます。</span><span class="sxs-lookup"><span data-stu-id="24eee-115">For Boolean comparison, `result` is `True` if and only if both `expression1` and `expression2` evaluate to `True`.</span></span> <span data-ttu-id="24eee-116">次の表は、`result` がどのように決定されるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="24eee-116">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="24eee-117">`expression1` の場合</span><span class="sxs-lookup"><span data-stu-id="24eee-117">If `expression1` is</span></span>|<span data-ttu-id="24eee-118">`expression2`</span><span class="sxs-lookup"><span data-stu-id="24eee-118">And `expression2` is</span></span>|<span data-ttu-id="24eee-119">`result` の値はです。</span><span class="sxs-lookup"><span data-stu-id="24eee-119">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> <span data-ttu-id="24eee-120">ブール値の比較では、`And` 演算子は常に両方の式を評価します。これには、プロシージャ呼び出しを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="24eee-120">In a Boolean comparison, the `And` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="24eee-121">[AndAlso 演算子](../../../visual-basic/language-reference/operators/andalso-operator.md)は*ショートサーキット*を実行します。つまり、`expression1` が `False`場合、`expression2` は評価されません。</span><span class="sxs-lookup"><span data-stu-id="24eee-121">The [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) performs *short-circuiting*, which means that if `expression1` is `False`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="24eee-122">`And` 演算子は、数値に適用した場合、2つの数値式で同じ位置にあるビットのビットごとの比較を実行し、次の表に従って `result` に対応するビットを設定します。</span><span class="sxs-lookup"><span data-stu-id="24eee-122">When applied to numeric values, the `And` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="24eee-123">`expression1` のビットがの場合</span><span class="sxs-lookup"><span data-stu-id="24eee-123">If bit in `expression1` is</span></span>|<span data-ttu-id="24eee-124">`expression2` のビットは</span><span class="sxs-lookup"><span data-stu-id="24eee-124">And bit in `expression2` is</span></span>|<span data-ttu-id="24eee-125">`result` のビットはです。</span><span class="sxs-lookup"><span data-stu-id="24eee-125">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="24eee-126">1</span><span class="sxs-lookup"><span data-stu-id="24eee-126">1</span></span>|<span data-ttu-id="24eee-127">1</span><span class="sxs-lookup"><span data-stu-id="24eee-127">1</span></span>|<span data-ttu-id="24eee-128">1</span><span class="sxs-lookup"><span data-stu-id="24eee-128">1</span></span>|  
|<span data-ttu-id="24eee-129">1</span><span class="sxs-lookup"><span data-stu-id="24eee-129">1</span></span>|<span data-ttu-id="24eee-130">0</span><span class="sxs-lookup"><span data-stu-id="24eee-130">0</span></span>|<span data-ttu-id="24eee-131">0</span><span class="sxs-lookup"><span data-stu-id="24eee-131">0</span></span>|  
|<span data-ttu-id="24eee-132">0</span><span class="sxs-lookup"><span data-stu-id="24eee-132">0</span></span>|<span data-ttu-id="24eee-133">1</span><span class="sxs-lookup"><span data-stu-id="24eee-133">1</span></span>|<span data-ttu-id="24eee-134">0</span><span class="sxs-lookup"><span data-stu-id="24eee-134">0</span></span>|  
|<span data-ttu-id="24eee-135">0</span><span class="sxs-lookup"><span data-stu-id="24eee-135">0</span></span>|<span data-ttu-id="24eee-136">0</span><span class="sxs-lookup"><span data-stu-id="24eee-136">0</span></span>|<span data-ttu-id="24eee-137">0</span><span class="sxs-lookup"><span data-stu-id="24eee-137">0</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="24eee-138">論理演算子とビット処理演算子は、他の算術演算子および関係演算子より優先順位が低いので、ビットごとの演算は、正確な結果を得るためにかっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="24eee-138">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate results.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="24eee-139">データ型</span><span class="sxs-lookup"><span data-stu-id="24eee-139">Data Types</span></span>  
 <span data-ttu-id="24eee-140">オペランドが1つの `Boolean` 式と1つの数値式で構成されている場合、Visual Basic は `Boolean` 式を数値に変換し (`True` の場合は-1、`False`の場合は 0)、ビットごとの演算を実行します。</span><span class="sxs-lookup"><span data-stu-id="24eee-140">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="24eee-141">ブール値の比較の場合、結果のデータ型は `Boolean`になります。</span><span class="sxs-lookup"><span data-stu-id="24eee-141">For a Boolean comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="24eee-142">ビットごとの比較の場合、結果のデータ型は `expression1` および `expression2`のデータ型に適した数値型になります。</span><span class="sxs-lookup"><span data-stu-id="24eee-142">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="24eee-143">「[演算子の結果のデータ型](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)」の「リレーショナルおよびビットごとの比較」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24eee-143">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="24eee-144">`And` 演算子は*オーバーロード*することができます。つまり、クラスまたは構造体がそのクラスまたは構造体の型を持つ場合に、クラスまたは構造体がその動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="24eee-144">The `And` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="24eee-145">コードでこのようなクラスまたは構造体に対してこの演算子を使用する場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="24eee-145">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="24eee-146">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24eee-146">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="24eee-147">例</span><span class="sxs-lookup"><span data-stu-id="24eee-147">Example</span></span>  
 <span data-ttu-id="24eee-148">次の例では、`And` 演算子を使用して、2つの式の論理積を実行します。</span><span class="sxs-lookup"><span data-stu-id="24eee-148">The following example uses the `And` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="24eee-149">結果は、両方の式が `True`かどうかを表す `Boolean` 値です。</span><span class="sxs-lookup"><span data-stu-id="24eee-149">The result is a `Boolean` value that represents whether both of the expressions are `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#22)]  
  
 <span data-ttu-id="24eee-150">前の例では、`True` と `False`の結果がそれぞれ生成されます。</span><span class="sxs-lookup"><span data-stu-id="24eee-150">The preceding example produces results of `True` and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="24eee-151">例</span><span class="sxs-lookup"><span data-stu-id="24eee-151">Example</span></span>  
 <span data-ttu-id="24eee-152">次の例では、`And` 演算子を使用して、2つの数値式の個々のビットに対して論理積演算を実行します。</span><span class="sxs-lookup"><span data-stu-id="24eee-152">The following example uses the `And` operator to perform logical conjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="24eee-153">オペランドの対応するビットが両方とも1に設定されている場合、結果パターンのビットは設定されます。</span><span class="sxs-lookup"><span data-stu-id="24eee-153">The bit in the result pattern is set if the corresponding bits in the operands are both set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#23)]  
  
 <span data-ttu-id="24eee-154">前の例では、それぞれ8、2、および0の結果が生成されます。</span><span class="sxs-lookup"><span data-stu-id="24eee-154">The preceding example produces results of 8, 2, and 0, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24eee-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="24eee-155">See also</span></span>

- [<span data-ttu-id="24eee-156">論理/ビット演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="24eee-156">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="24eee-157">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="24eee-157">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="24eee-158">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="24eee-158">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="24eee-159">AndAlso 演算子</span><span class="sxs-lookup"><span data-stu-id="24eee-159">AndAlso Operator</span></span>](../../../visual-basic/language-reference/operators/andalso-operator.md)
- [<span data-ttu-id="24eee-160">Visual Basic の論理演算子とビット処理演算子</span><span class="sxs-lookup"><span data-stu-id="24eee-160">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
