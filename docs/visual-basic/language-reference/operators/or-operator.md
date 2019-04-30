---
title: Or 演算子 (Visual Basic)
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
ms.openlocfilehash: 0277b6f24e62ed5f0cad3dae225c86fffc4c09b9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013518"
---
# <a name="or-operator-visual-basic"></a><span data-ttu-id="8df57-102">Or 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8df57-102">Or Operator (Visual Basic)</span></span>
<span data-ttu-id="8df57-103">2 つの論理和演算を実行します。`Boolean`式、または 2 つの数値式のビットごとの論理和。</span><span class="sxs-lookup"><span data-stu-id="8df57-103">Performs a logical disjunction on two `Boolean` expressions, or a bitwise disjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8df57-104">構文</span><span class="sxs-lookup"><span data-stu-id="8df57-104">Syntax</span></span>  
  
```  
result = expression1 Or expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="8df57-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="8df57-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="8df57-106">必須。</span><span class="sxs-lookup"><span data-stu-id="8df57-106">Required.</span></span> <span data-ttu-id="8df57-107">すべて`Boolean`または数値式です。</span><span class="sxs-lookup"><span data-stu-id="8df57-107">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="8df57-108">`Boolean`比較、`result`は 2 つの包括的論理和`Boolean`値。</span><span class="sxs-lookup"><span data-stu-id="8df57-108">For `Boolean` comparison, `result` is the inclusive logical disjunction of two `Boolean` values.</span></span> <span data-ttu-id="8df57-109">ビットごとの演算`result`は 2 つの数値ビット パターンの包括的論理和を表す数値です。</span><span class="sxs-lookup"><span data-stu-id="8df57-109">For bitwise operations, `result` is a numeric value representing the inclusive bitwise disjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="8df57-110">必須。</span><span class="sxs-lookup"><span data-stu-id="8df57-110">Required.</span></span> <span data-ttu-id="8df57-111">すべて`Boolean`または数値式です。</span><span class="sxs-lookup"><span data-stu-id="8df57-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="8df57-112">必須。</span><span class="sxs-lookup"><span data-stu-id="8df57-112">Required.</span></span> <span data-ttu-id="8df57-113">すべて`Boolean`または数値式です。</span><span class="sxs-lookup"><span data-stu-id="8df57-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8df57-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="8df57-114">Remarks</span></span>  
 <span data-ttu-id="8df57-115">`Boolean`比較、`result`は`False`場合にのみ、両方`expression1`と`expression2`に評価される`False`します。</span><span class="sxs-lookup"><span data-stu-id="8df57-115">For `Boolean` comparison, `result` is `False` if and only if both `expression1` and `expression2` evaluate to `False`.</span></span> <span data-ttu-id="8df57-116">次の表はどのように`result`決定されます。</span><span class="sxs-lookup"><span data-stu-id="8df57-116">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="8df57-117">場合`expression1`は</span><span class="sxs-lookup"><span data-stu-id="8df57-117">If `expression1` is</span></span>|<span data-ttu-id="8df57-118">`expression2`は</span><span class="sxs-lookup"><span data-stu-id="8df57-118">And `expression2` is</span></span>|<span data-ttu-id="8df57-119">値`result`は</span><span class="sxs-lookup"><span data-stu-id="8df57-119">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  <span data-ttu-id="8df57-120">`Boolean` 、比較、`Or`演算子では、両方の式では、プロシージャの呼び出しを含めることが常に評価されます。</span><span class="sxs-lookup"><span data-stu-id="8df57-120">In a `Boolean` comparison, the `Or` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="8df57-121">[OrElse 演算子](../../../visual-basic/language-reference/operators/orelse-operator.md)実行*ショート サーキット*、つまり、その場合`expression1`は`True`、し`expression2`は評価されません。</span><span class="sxs-lookup"><span data-stu-id="8df57-121">The [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md) performs *short-circuiting*, which means that if `expression1` is `True`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="8df57-122">ビットごとの演算、`Or`演算子が 2 つの数値式で同じ位置にビットのビット単位の比較を実行し、対応するでビットを設定`result`次の表に従ってします。</span><span class="sxs-lookup"><span data-stu-id="8df57-122">For bitwise operations, the `Or` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="8df57-123">場合にビット`expression1`は</span><span class="sxs-lookup"><span data-stu-id="8df57-123">If bit in `expression1` is</span></span>|<span data-ttu-id="8df57-124">ビットと`expression2`は</span><span class="sxs-lookup"><span data-stu-id="8df57-124">And bit in `expression2` is</span></span>|<span data-ttu-id="8df57-125">内のビット`result`は</span><span class="sxs-lookup"><span data-stu-id="8df57-125">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="8df57-126">1</span><span class="sxs-lookup"><span data-stu-id="8df57-126">1</span></span>|<span data-ttu-id="8df57-127">1</span><span class="sxs-lookup"><span data-stu-id="8df57-127">1</span></span>|<span data-ttu-id="8df57-128">1</span><span class="sxs-lookup"><span data-stu-id="8df57-128">1</span></span>|  
|<span data-ttu-id="8df57-129">1</span><span class="sxs-lookup"><span data-stu-id="8df57-129">1</span></span>|<span data-ttu-id="8df57-130">0</span><span class="sxs-lookup"><span data-stu-id="8df57-130">0</span></span>|<span data-ttu-id="8df57-131">1</span><span class="sxs-lookup"><span data-stu-id="8df57-131">1</span></span>|  
|<span data-ttu-id="8df57-132">0</span><span class="sxs-lookup"><span data-stu-id="8df57-132">0</span></span>|<span data-ttu-id="8df57-133">1</span><span class="sxs-lookup"><span data-stu-id="8df57-133">1</span></span>|<span data-ttu-id="8df57-134">1</span><span class="sxs-lookup"><span data-stu-id="8df57-134">1</span></span>|  
|<span data-ttu-id="8df57-135">0</span><span class="sxs-lookup"><span data-stu-id="8df57-135">0</span></span>|<span data-ttu-id="8df57-136">0</span><span class="sxs-lookup"><span data-stu-id="8df57-136">0</span></span>|<span data-ttu-id="8df57-137">0</span><span class="sxs-lookup"><span data-stu-id="8df57-137">0</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="8df57-138">論理/ビット処理演算子の他の算術演算子や関係演算子よりも優先順位の低いため、ビットごとの演算は、正確に実行されるようにかっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="8df57-138">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="8df57-139">データの種類</span><span class="sxs-lookup"><span data-stu-id="8df57-139">Data Types</span></span>  
 <span data-ttu-id="8df57-140">いずれかのオペランドで構成される場合`Boolean`式と 1 つの数値式では、Visual Basic に変換します、`Boolean`式を数値に (– 1 `True` 0 `False`) し、ビットごとの演算を実行します。</span><span class="sxs-lookup"><span data-stu-id="8df57-140">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="8df57-141">`Boolean`比較、結果のデータ型は`Boolean`します。</span><span class="sxs-lookup"><span data-stu-id="8df57-141">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="8df57-142">ビット単位の比較結果のデータ型は数値型のデータ型に適した`expression1`と`expression2`します。</span><span class="sxs-lookup"><span data-stu-id="8df57-142">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="8df57-143">「リレーショナルとビットごとの比較」表を参照して[演算子結果のデータ型](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)します。</span><span class="sxs-lookup"><span data-stu-id="8df57-143">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="8df57-144">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="8df57-144">Overloading</span></span>  
 <span data-ttu-id="8df57-145">`Or`演算子は、*オーバー ロードされた*、つまり、ことクラスまたは構造体を再定義できますその動作はそのクラスまたは構造体の型。</span><span class="sxs-lookup"><span data-stu-id="8df57-145">The `Or` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="8df57-146">コードは、このようなクラスまたは構造体に、この演算子を使用する場合は、再定義された動作を確認ください。</span><span class="sxs-lookup"><span data-stu-id="8df57-146">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="8df57-147">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8df57-147">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8df57-148">例</span><span class="sxs-lookup"><span data-stu-id="8df57-148">Example</span></span>  
 <span data-ttu-id="8df57-149">次の例では、`Or`オペレーターが 2 つの式の包括的論理和演算を実行します。</span><span class="sxs-lookup"><span data-stu-id="8df57-149">The following example uses the `Or` operator to perform an inclusive logical disjunction on two expressions.</span></span> <span data-ttu-id="8df57-150">結果は、`Boolean`を表す値が 2 つの式のいずれかどうか`True`します。</span><span class="sxs-lookup"><span data-stu-id="8df57-150">The result is a `Boolean` value that represents whether either of the two expressions is `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#35)]  
  
 <span data-ttu-id="8df57-151">前の例の結果を生成する`True`、 `True`、および`False`、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="8df57-151">The preceding example produces results of `True`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8df57-152">例</span><span class="sxs-lookup"><span data-stu-id="8df57-152">Example</span></span>  
 <span data-ttu-id="8df57-153">次の例では、`Or`オペレーターが 2 つの数値式のビットごとの包括的論理和を実行します。</span><span class="sxs-lookup"><span data-stu-id="8df57-153">The following example uses the `Or` operator to perform inclusive logical disjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="8df57-154">オペランドの対応するビットのいずれかを 1 に設定されている場合、結果のパターンのビットが設定されます。</span><span class="sxs-lookup"><span data-stu-id="8df57-154">The bit in the result pattern is set if either of the corresponding bits in the operands is set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#36)]  
  
 <span data-ttu-id="8df57-155">前の例では、それぞれ 10、14、および 14 の結果を生成します。</span><span class="sxs-lookup"><span data-stu-id="8df57-155">The preceding example produces results of 10, 14, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8df57-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="8df57-156">See also</span></span>

- [<span data-ttu-id="8df57-157">論理/ビット演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8df57-157">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="8df57-158">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="8df57-158">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="8df57-159">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="8df57-159">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="8df57-160">OrElse 演算子</span><span class="sxs-lookup"><span data-stu-id="8df57-160">OrElse Operator</span></span>](../../../visual-basic/language-reference/operators/orelse-operator.md)
- [<span data-ttu-id="8df57-161">Visual Basic での論理とビット処理演算子</span><span class="sxs-lookup"><span data-stu-id="8df57-161">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
