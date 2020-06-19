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
ms.openlocfilehash: 657b2a473b23789a8ba25fbd11c6b83538fa7803
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401421"
---
# <a name="or-operator-visual-basic"></a><span data-ttu-id="c29ce-102">Or 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c29ce-102">Or Operator (Visual Basic)</span></span>
<span data-ttu-id="c29ce-103">2 つの `Boolean` 式の場合は論理和演算、2 つの数値式の場合はビットごとの論理和演算を実行します。</span><span class="sxs-lookup"><span data-stu-id="c29ce-103">Performs a logical disjunction on two `Boolean` expressions, or a bitwise disjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c29ce-104">構文</span><span class="sxs-lookup"><span data-stu-id="c29ce-104">Syntax</span></span>  
  
```vb  
result = expression1 Or expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="c29ce-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="c29ce-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="c29ce-106">必須です。</span><span class="sxs-lookup"><span data-stu-id="c29ce-106">Required.</span></span> <span data-ttu-id="c29ce-107">任意の `Boolean` または数値式。</span><span class="sxs-lookup"><span data-stu-id="c29ce-107">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="c29ce-108">`Boolean` の比較の場合、`result` は 2 つの `Boolean` 値の包含論理和演算となります。</span><span class="sxs-lookup"><span data-stu-id="c29ce-108">For `Boolean` comparison, `result` is the inclusive logical disjunction of two `Boolean` values.</span></span> <span data-ttu-id="c29ce-109">ビットごとの演算の場合、`result` は 2 つの数値ビット パターンのビットごとの包含論理和演算を表す数値です。</span><span class="sxs-lookup"><span data-stu-id="c29ce-109">For bitwise operations, `result` is a numeric value representing the inclusive bitwise disjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="c29ce-110">必須です。</span><span class="sxs-lookup"><span data-stu-id="c29ce-110">Required.</span></span> <span data-ttu-id="c29ce-111">任意の `Boolean` または数値式。</span><span class="sxs-lookup"><span data-stu-id="c29ce-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="c29ce-112">必須です。</span><span class="sxs-lookup"><span data-stu-id="c29ce-112">Required.</span></span> <span data-ttu-id="c29ce-113">任意の `Boolean` または数値式。</span><span class="sxs-lookup"><span data-stu-id="c29ce-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c29ce-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="c29ce-114">Remarks</span></span>  
 <span data-ttu-id="c29ce-115">`Boolean` の比較では、`expression1` と `expression2` の両方が `False` に評価された場合にのみ、`result` は `False` になります。</span><span class="sxs-lookup"><span data-stu-id="c29ce-115">For `Boolean` comparison, `result` is `False` if and only if both `expression1` and `expression2` evaluate to `False`.</span></span> <span data-ttu-id="c29ce-116">次の表は、`result` がどのように決定されるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="c29ce-116">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="c29ce-117">`expression1` が次の場合</span><span class="sxs-lookup"><span data-stu-id="c29ce-117">If `expression1` is</span></span>|<span data-ttu-id="c29ce-118">かつ、`expression2` が次の場合</span><span class="sxs-lookup"><span data-stu-id="c29ce-118">And `expression2` is</span></span>|<span data-ttu-id="c29ce-119">`result` の値は次のようになります</span><span class="sxs-lookup"><span data-stu-id="c29ce-119">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> <span data-ttu-id="c29ce-120">`Boolean` の比較では、`Or` 演算子は常に両方の式を評価します。これには、プロシージャ呼び出しの実行を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="c29ce-120">In a `Boolean` comparison, the `Or` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="c29ce-121">[OrElse 演算子](orelse-operator.md)は "*ショートサーキット*" を実行します。つまり、`expression1` が `True` の場合、`expression2` は評価されません。</span><span class="sxs-lookup"><span data-stu-id="c29ce-121">The [OrElse Operator](orelse-operator.md) performs *short-circuiting*, which means that if `expression1` is `True`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="c29ce-122">ビットごとの演算の場合、`Or` 演算子は、2 つの数値式でまったく同じ位置にあるビットのビットごとの比較を実行し、次の表に従って `result` に対応するビットを設定します。</span><span class="sxs-lookup"><span data-stu-id="c29ce-122">For bitwise operations, the `Or` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="c29ce-123">`expression1` 内のビットが次の場合</span><span class="sxs-lookup"><span data-stu-id="c29ce-123">If bit in `expression1` is</span></span>|<span data-ttu-id="c29ce-124">かつ、`expression2` 内のビットが次の場合</span><span class="sxs-lookup"><span data-stu-id="c29ce-124">And bit in `expression2` is</span></span>|<span data-ttu-id="c29ce-125">`result` 内のビットは次のようになります</span><span class="sxs-lookup"><span data-stu-id="c29ce-125">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="c29ce-126">1</span><span class="sxs-lookup"><span data-stu-id="c29ce-126">1</span></span>|<span data-ttu-id="c29ce-127">1</span><span class="sxs-lookup"><span data-stu-id="c29ce-127">1</span></span>|<span data-ttu-id="c29ce-128">1</span><span class="sxs-lookup"><span data-stu-id="c29ce-128">1</span></span>|  
|<span data-ttu-id="c29ce-129">1</span><span class="sxs-lookup"><span data-stu-id="c29ce-129">1</span></span>|<span data-ttu-id="c29ce-130">0</span><span class="sxs-lookup"><span data-stu-id="c29ce-130">0</span></span>|<span data-ttu-id="c29ce-131">1</span><span class="sxs-lookup"><span data-stu-id="c29ce-131">1</span></span>|  
|<span data-ttu-id="c29ce-132">0</span><span class="sxs-lookup"><span data-stu-id="c29ce-132">0</span></span>|<span data-ttu-id="c29ce-133">1</span><span class="sxs-lookup"><span data-stu-id="c29ce-133">1</span></span>|<span data-ttu-id="c29ce-134">1</span><span class="sxs-lookup"><span data-stu-id="c29ce-134">1</span></span>|  
|<span data-ttu-id="c29ce-135">0</span><span class="sxs-lookup"><span data-stu-id="c29ce-135">0</span></span>|<span data-ttu-id="c29ce-136">0</span><span class="sxs-lookup"><span data-stu-id="c29ce-136">0</span></span>|<span data-ttu-id="c29ce-137">0</span><span class="sxs-lookup"><span data-stu-id="c29ce-137">0</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="c29ce-138">論理およびビット処理演算子は、他の算術演算子および関係演算子より優先順位が低いので、正確に実行するために、ビットごとの演算はかっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="c29ce-138">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="c29ce-139">データの種類</span><span class="sxs-lookup"><span data-stu-id="c29ce-139">Data Types</span></span>  
 <span data-ttu-id="c29ce-140">オペランドが 1 つの `Boolean` 式と 1 つの数値式で構成されている場合、Visual Basic は `Boolean` 式を数値に変換し (`True` の場合は 1、`False` の場合は 0)、ビットごとの演算を実行します。</span><span class="sxs-lookup"><span data-stu-id="c29ce-140">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="c29ce-141">`Boolean` の比較の場合、結果のデータ型は `Boolean` になります。</span><span class="sxs-lookup"><span data-stu-id="c29ce-141">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="c29ce-142">ビットごとの比較の場合、結果のデータ型は `expression1` および `expression2` のデータ型に適した数値型になります。</span><span class="sxs-lookup"><span data-stu-id="c29ce-142">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="c29ce-143">「[演算子の結果のデータ型](data-types-of-operator-results.md)」の「関係とビットごとの比較」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c29ce-143">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="c29ce-144">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="c29ce-144">Overloading</span></span>  
 <span data-ttu-id="c29ce-145">`Or` 演算子は "*オーバーロード*" できます。つまり、オペランドがクラスまたは構造体の型を持っているときに、クラスまたは構造体はその動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="c29ce-145">The `Or` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="c29ce-146">コードで、そのようなクラスまたは構造体に対してこの演算子が使用される場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c29ce-146">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="c29ce-147">詳細については、「 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c29ce-147">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c29ce-148">例</span><span class="sxs-lookup"><span data-stu-id="c29ce-148">Example</span></span>  
 <span data-ttu-id="c29ce-149">次の例では、`Or` 演算子を使用して、2 つの式の包含論理和演算を実行します。</span><span class="sxs-lookup"><span data-stu-id="c29ce-149">The following example uses the `Or` operator to perform an inclusive logical disjunction on two expressions.</span></span> <span data-ttu-id="c29ce-150">結果は、2 つの式のいずれかが `True` かどうかを表す `Boolean` 値です。</span><span class="sxs-lookup"><span data-stu-id="c29ce-150">The result is a `Boolean` value that represents whether either of the two expressions is `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#35)]  
  
 <span data-ttu-id="c29ce-151">前の例では、それぞれ `True`、`True`、`False` の結果が生成されます。</span><span class="sxs-lookup"><span data-stu-id="c29ce-151">The preceding example produces results of `True`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c29ce-152">例</span><span class="sxs-lookup"><span data-stu-id="c29ce-152">Example</span></span>  
 <span data-ttu-id="c29ce-153">次の例では、`Or` 演算子を使用して、2 つの数値式の個々のビットに対して包含論理和演算を実行します。</span><span class="sxs-lookup"><span data-stu-id="c29ce-153">The following example uses the `Or` operator to perform inclusive logical disjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="c29ce-154">オペランドの対応するビットのいずれかが 1 に設定されている場合、結果パターンのビットが設定されます。</span><span class="sxs-lookup"><span data-stu-id="c29ce-154">The bit in the result pattern is set if either of the corresponding bits in the operands is set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#36)]  
  
 <span data-ttu-id="c29ce-155">前の例では、それぞれ 10、14、14 の結果が生成されます。</span><span class="sxs-lookup"><span data-stu-id="c29ce-155">The preceding example produces results of 10, 14, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c29ce-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="c29ce-156">See also</span></span>

- [<span data-ttu-id="c29ce-157">論理/ビット演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c29ce-157">Logical/Bitwise Operators (Visual Basic)</span></span>](logical-bitwise-operators.md)
- [<span data-ttu-id="c29ce-158">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="c29ce-158">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="c29ce-159">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="c29ce-159">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="c29ce-160">OrElse 演算子</span><span class="sxs-lookup"><span data-stu-id="c29ce-160">OrElse Operator</span></span>](orelse-operator.md)
- [<span data-ttu-id="c29ce-161">Visual Basic の論理演算子とビット処理演算子</span><span class="sxs-lookup"><span data-stu-id="c29ce-161">Logical and Bitwise Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
