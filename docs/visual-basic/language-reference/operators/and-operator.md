---
title: And 演算子 (Visual Basic)
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
ms.openlocfilehash: 7e25f25677fa684427bdaf00cea73916ffbad655
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61608360"
---
# <a name="and-operator-visual-basic"></a><span data-ttu-id="6b620-102">And 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6b620-102">And Operator (Visual Basic)</span></span>
<span data-ttu-id="6b620-103">2 つの論理積を求めます`Boolean`式、または 2 つの数値式のビットごとの積。</span><span class="sxs-lookup"><span data-stu-id="6b620-103">Performs a logical conjunction on two `Boolean` expressions, or a bitwise conjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b620-104">構文</span><span class="sxs-lookup"><span data-stu-id="6b620-104">Syntax</span></span>  
  
```  
result = expression1 And expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="6b620-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="6b620-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="6b620-106">必須。</span><span class="sxs-lookup"><span data-stu-id="6b620-106">Required.</span></span> <span data-ttu-id="6b620-107">すべて`Boolean`または数値式です。</span><span class="sxs-lookup"><span data-stu-id="6b620-107">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="6b620-108">ブール値の比較の`result`は 2 つの論理積`Boolean`値。</span><span class="sxs-lookup"><span data-stu-id="6b620-108">For Boolean comparison, `result` is the logical conjunction of two `Boolean` values.</span></span> <span data-ttu-id="6b620-109">ビットごとの演算`result`は 2 つの数値ビット パターンのビットごとの積を表す数値です。</span><span class="sxs-lookup"><span data-stu-id="6b620-109">For bitwise operations, `result` is a numeric value representing the bitwise conjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="6b620-110">必須。</span><span class="sxs-lookup"><span data-stu-id="6b620-110">Required.</span></span> <span data-ttu-id="6b620-111">すべて`Boolean`または数値式です。</span><span class="sxs-lookup"><span data-stu-id="6b620-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="6b620-112">必須。</span><span class="sxs-lookup"><span data-stu-id="6b620-112">Required.</span></span> <span data-ttu-id="6b620-113">すべて`Boolean`または数値式です。</span><span class="sxs-lookup"><span data-stu-id="6b620-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b620-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="6b620-114">Remarks</span></span>  
 <span data-ttu-id="6b620-115">ブール値の比較の`result`は`True`場合にのみ、両方`expression1`と`expression2`に評価される`True`します。</span><span class="sxs-lookup"><span data-stu-id="6b620-115">For Boolean comparison, `result` is `True` if and only if both `expression1` and `expression2` evaluate to `True`.</span></span> <span data-ttu-id="6b620-116">次の表はどのように`result`決定されます。</span><span class="sxs-lookup"><span data-stu-id="6b620-116">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="6b620-117">場合`expression1`は</span><span class="sxs-lookup"><span data-stu-id="6b620-117">If `expression1` is</span></span>|<span data-ttu-id="6b620-118">`expression2`は</span><span class="sxs-lookup"><span data-stu-id="6b620-118">And `expression2` is</span></span>|<span data-ttu-id="6b620-119">値`result`は</span><span class="sxs-lookup"><span data-stu-id="6b620-119">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  <span data-ttu-id="6b620-120">ブール値の比較で、`And`演算子では、両方の式では、プロシージャの呼び出しを含めることが常に評価されます。</span><span class="sxs-lookup"><span data-stu-id="6b620-120">In a Boolean comparison, the `And` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="6b620-121">[AndAlso 演算子](../../../visual-basic/language-reference/operators/andalso-operator.md)実行*ショート サーキット*、つまり、その場合`expression1`は`False`、し`expression2`は評価されません。</span><span class="sxs-lookup"><span data-stu-id="6b620-121">The [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) performs *short-circuiting*, which means that if `expression1` is `False`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="6b620-122">数値の値に適用すると、`And`演算子が 2 つの数値式で同じ位置にビットのビット単位の比較を実行し、対応するでビットを設定`result`次の表に従ってします。</span><span class="sxs-lookup"><span data-stu-id="6b620-122">When applied to numeric values, the `And` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="6b620-123">場合にビット`expression1`は</span><span class="sxs-lookup"><span data-stu-id="6b620-123">If bit in `expression1` is</span></span>|<span data-ttu-id="6b620-124">ビットと`expression2`は</span><span class="sxs-lookup"><span data-stu-id="6b620-124">And bit in `expression2` is</span></span>|<span data-ttu-id="6b620-125">内のビット`result`は</span><span class="sxs-lookup"><span data-stu-id="6b620-125">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="6b620-126">1</span><span class="sxs-lookup"><span data-stu-id="6b620-126">1</span></span>|<span data-ttu-id="6b620-127">1</span><span class="sxs-lookup"><span data-stu-id="6b620-127">1</span></span>|<span data-ttu-id="6b620-128">1</span><span class="sxs-lookup"><span data-stu-id="6b620-128">1</span></span>|  
|<span data-ttu-id="6b620-129">1</span><span class="sxs-lookup"><span data-stu-id="6b620-129">1</span></span>|<span data-ttu-id="6b620-130">0</span><span class="sxs-lookup"><span data-stu-id="6b620-130">0</span></span>|<span data-ttu-id="6b620-131">0</span><span class="sxs-lookup"><span data-stu-id="6b620-131">0</span></span>|  
|<span data-ttu-id="6b620-132">0</span><span class="sxs-lookup"><span data-stu-id="6b620-132">0</span></span>|<span data-ttu-id="6b620-133">1</span><span class="sxs-lookup"><span data-stu-id="6b620-133">1</span></span>|<span data-ttu-id="6b620-134">0</span><span class="sxs-lookup"><span data-stu-id="6b620-134">0</span></span>|  
|<span data-ttu-id="6b620-135">0</span><span class="sxs-lookup"><span data-stu-id="6b620-135">0</span></span>|<span data-ttu-id="6b620-136">0</span><span class="sxs-lookup"><span data-stu-id="6b620-136">0</span></span>|<span data-ttu-id="6b620-137">0</span><span class="sxs-lookup"><span data-stu-id="6b620-137">0</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="6b620-138">論理/ビット処理演算子の他の算術演算子や関係演算子よりも優先順位の低いため、ビットごとの演算は、正確な結果を確認するためにかっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b620-138">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate results.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="6b620-139">データの種類</span><span class="sxs-lookup"><span data-stu-id="6b620-139">Data Types</span></span>  
 <span data-ttu-id="6b620-140">いずれかのオペランドで構成される場合`Boolean`式と 1 つの数値式では、Visual Basic に変換します、`Boolean`式を数値に (– 1 `True` 0 `False`) し、ビットごとの演算を実行します。</span><span class="sxs-lookup"><span data-stu-id="6b620-140">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="6b620-141">ブール値の比較結果のデータ型は`Boolean`します。</span><span class="sxs-lookup"><span data-stu-id="6b620-141">For a Boolean comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="6b620-142">ビット単位の比較結果のデータ型は数値型のデータ型に適した`expression1`と`expression2`します。</span><span class="sxs-lookup"><span data-stu-id="6b620-142">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="6b620-143">「リレーショナルとビットごとの比較」表を参照して[演算子結果のデータ型](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)します。</span><span class="sxs-lookup"><span data-stu-id="6b620-143">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6b620-144">`And`演算子は、*オーバー ロードされた*、つまり、ことクラスまたは構造体を再定義できますその動作はそのクラスまたは構造体の型。</span><span class="sxs-lookup"><span data-stu-id="6b620-144">The `And` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="6b620-145">コードは、このようなクラスまたは構造体に、この演算子を使用する場合は、再定義された動作を確認ください。</span><span class="sxs-lookup"><span data-stu-id="6b620-145">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="6b620-146">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b620-146">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b620-147">例</span><span class="sxs-lookup"><span data-stu-id="6b620-147">Example</span></span>  
 <span data-ttu-id="6b620-148">次の例では、`And`演算子を 2 つの式に対して論理積を実行します。</span><span class="sxs-lookup"><span data-stu-id="6b620-148">The following example uses the `And` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="6b620-149">結果は、`Boolean`が両方の式かどうかを表す値`True`します。</span><span class="sxs-lookup"><span data-stu-id="6b620-149">The result is a `Boolean` value that represents whether both of the expressions are `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#22)]  
  
 <span data-ttu-id="6b620-150">前の例の結果を生成する`True`と`False`、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="6b620-150">The preceding example produces results of `True` and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b620-151">例</span><span class="sxs-lookup"><span data-stu-id="6b620-151">Example</span></span>  
 <span data-ttu-id="6b620-152">次の例では、`And`オペレーターが 2 つの数値式のビットごとの論理積を実行します。</span><span class="sxs-lookup"><span data-stu-id="6b620-152">The following example uses the `And` operator to perform logical conjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="6b620-153">オペランドの対応するビットが 1 に設定する両方の場合、結果パターンのビットが設定されます。</span><span class="sxs-lookup"><span data-stu-id="6b620-153">The bit in the result pattern is set if the corresponding bits in the operands are both set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#23)]  
  
 <span data-ttu-id="6b620-154">前の例では、それぞれ 8、2、および 0 の場合の結果を生成します。</span><span class="sxs-lookup"><span data-stu-id="6b620-154">The preceding example produces results of 8, 2, and 0, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b620-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="6b620-155">See also</span></span>

- [<span data-ttu-id="6b620-156">論理/ビット演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6b620-156">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="6b620-157">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="6b620-157">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="6b620-158">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="6b620-158">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="6b620-159">AndAlso 演算子</span><span class="sxs-lookup"><span data-stu-id="6b620-159">AndAlso Operator</span></span>](../../../visual-basic/language-reference/operators/andalso-operator.md)
- [<span data-ttu-id="6b620-160">Visual Basic での論理とビット処理演算子</span><span class="sxs-lookup"><span data-stu-id="6b620-160">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
