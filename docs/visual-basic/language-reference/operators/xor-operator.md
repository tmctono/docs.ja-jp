---
title: Xor 演算子
ms.date: 07/20/2015
f1_keywords:
- vb.Xor
helpviewer_keywords:
- exclusive OR operator [Visual Basic]
- logical exclusion
- operators [Visual Basic], exclusive or
- exclusion operator [Visual Basic]
- operators [Visual Basic], bitwise
- bitwise operators [Visual Basic], XOR operator
- Xor operator [Visual Basic]
- Xor keyword [Visual Basic]
- bitwise comparison [Visual Basic]
ms.assetid: 036000a9-3934-4e7f-a9d0-a816de3d84a6
ms.openlocfilehash: 999050314d674fa98833083d84796e471c22971d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406341"
---
# <a name="xor-operator-visual-basic"></a><span data-ttu-id="a89b6-102">Xor 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a89b6-102">Xor Operator (Visual Basic)</span></span>
<span data-ttu-id="a89b6-103">2 つの `Boolean` 式の場合は排他的論理和、2 つの数値式の場合はビットごとの排他を求めます。</span><span class="sxs-lookup"><span data-stu-id="a89b6-103">Performs a logical exclusion on two `Boolean` expressions, or a bitwise exclusion on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a89b6-104">構文</span><span class="sxs-lookup"><span data-stu-id="a89b6-104">Syntax</span></span>  
  
```vb  
result = expression1 Xor expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="a89b6-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="a89b6-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="a89b6-106">必須です。</span><span class="sxs-lookup"><span data-stu-id="a89b6-106">Required.</span></span> <span data-ttu-id="a89b6-107">任意の `Boolean` または数値変数。</span><span class="sxs-lookup"><span data-stu-id="a89b6-107">Any `Boolean` or numeric variable.</span></span> <span data-ttu-id="a89b6-108">ブール値の比較の場合、`result` は 2 つの `Boolean` 値の排他的論理和 (排他的論理和演算) です。</span><span class="sxs-lookup"><span data-stu-id="a89b6-108">For Boolean comparison, `result` is the logical exclusion (exclusive logical disjunction) of two `Boolean` values.</span></span> <span data-ttu-id="a89b6-109">ビットごとの演算の場合、`result` は 2 つの数値ビット パターンのビットごとの排他 (ビットごとの排他的論理和演算) を表す数値です。</span><span class="sxs-lookup"><span data-stu-id="a89b6-109">For bitwise operations, `result` is a numeric value that represents the bitwise exclusion (exclusive bitwise disjunction) of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="a89b6-110">必須です。</span><span class="sxs-lookup"><span data-stu-id="a89b6-110">Required.</span></span> <span data-ttu-id="a89b6-111">任意の `Boolean` または数値式。</span><span class="sxs-lookup"><span data-stu-id="a89b6-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="a89b6-112">必須です。</span><span class="sxs-lookup"><span data-stu-id="a89b6-112">Required.</span></span> <span data-ttu-id="a89b6-113">任意の `Boolean` または数値式。</span><span class="sxs-lookup"><span data-stu-id="a89b6-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a89b6-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="a89b6-114">Remarks</span></span>  
 <span data-ttu-id="a89b6-115">ブール値の比較では、`expression1` と `expression2` のうち 1 つだけが `True` に評価される場合にのみ、`result` は `True` になります。</span><span class="sxs-lookup"><span data-stu-id="a89b6-115">For Boolean comparison, `result` is `True` if and only if exactly one of `expression1` and `expression2` evaluates to `True`.</span></span> <span data-ttu-id="a89b6-116">つまり、`expression1` と `expression2` とが逆の `Boolean` 値に評価される場合、かつその場合に限ります。</span><span class="sxs-lookup"><span data-stu-id="a89b6-116">That is, if and only if `expression1` and `expression2` evaluate to opposite `Boolean` values.</span></span> <span data-ttu-id="a89b6-117">次の表は、`result` がどのように決定されるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="a89b6-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="a89b6-118">`expression1` が次の場合</span><span class="sxs-lookup"><span data-stu-id="a89b6-118">If `expression1` is</span></span>|<span data-ttu-id="a89b6-119">かつ、`expression2` が次の場合</span><span class="sxs-lookup"><span data-stu-id="a89b6-119">And `expression2` is</span></span>|<span data-ttu-id="a89b6-120">`result` の値は次のようになります</span><span class="sxs-lookup"><span data-stu-id="a89b6-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`False`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> <span data-ttu-id="a89b6-121">ブール値の比較では、`Xor` 演算子は常に両方の式を評価します。これには、プロシージャ呼び出しを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a89b6-121">In a Boolean comparison, the `Xor` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="a89b6-122">結果は常に両方のオペランドに依存するため、`Xor` に対応するショートサーキットはありません。</span><span class="sxs-lookup"><span data-stu-id="a89b6-122">There is no short-circuiting counterpart to `Xor`, because the result always depends on both operands.</span></span> <span data-ttu-id="a89b6-123">"*ショートサーキット*" 論理演算子については、「[AndAlso 演算子](andalso-operator.md)」、および「[OrElse 演算子](orelse-operator.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a89b6-123">For *short-circuiting* logical operators, see [AndAlso Operator](andalso-operator.md) and [OrElse Operator](orelse-operator.md).</span></span>  
  
 <span data-ttu-id="a89b6-124">ビットごとの演算の場合、`Xor` 演算子は、2 つの数値式でまったく同じ位置にあるビットのビットごとの比較を実行し、次の表に従って `result` に対応するビットを設定します。</span><span class="sxs-lookup"><span data-stu-id="a89b6-124">For bitwise operations, the `Xor` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="a89b6-125">`expression1` 内のビットが次の場合</span><span class="sxs-lookup"><span data-stu-id="a89b6-125">If bit in `expression1` is</span></span>|<span data-ttu-id="a89b6-126">かつ、`expression2` 内のビットが次の場合</span><span class="sxs-lookup"><span data-stu-id="a89b6-126">And bit in `expression2` is</span></span>|<span data-ttu-id="a89b6-127">`result` 内のビットは次のようになります</span><span class="sxs-lookup"><span data-stu-id="a89b6-127">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="a89b6-128">1</span><span class="sxs-lookup"><span data-stu-id="a89b6-128">1</span></span>|<span data-ttu-id="a89b6-129">1</span><span class="sxs-lookup"><span data-stu-id="a89b6-129">1</span></span>|<span data-ttu-id="a89b6-130">0</span><span class="sxs-lookup"><span data-stu-id="a89b6-130">0</span></span>|  
|<span data-ttu-id="a89b6-131">1</span><span class="sxs-lookup"><span data-stu-id="a89b6-131">1</span></span>|<span data-ttu-id="a89b6-132">0</span><span class="sxs-lookup"><span data-stu-id="a89b6-132">0</span></span>|<span data-ttu-id="a89b6-133">1</span><span class="sxs-lookup"><span data-stu-id="a89b6-133">1</span></span>|  
|<span data-ttu-id="a89b6-134">0</span><span class="sxs-lookup"><span data-stu-id="a89b6-134">0</span></span>|<span data-ttu-id="a89b6-135">1</span><span class="sxs-lookup"><span data-stu-id="a89b6-135">1</span></span>|<span data-ttu-id="a89b6-136">1</span><span class="sxs-lookup"><span data-stu-id="a89b6-136">1</span></span>|  
|<span data-ttu-id="a89b6-137">0</span><span class="sxs-lookup"><span data-stu-id="a89b6-137">0</span></span>|<span data-ttu-id="a89b6-138">0</span><span class="sxs-lookup"><span data-stu-id="a89b6-138">0</span></span>|<span data-ttu-id="a89b6-139">0</span><span class="sxs-lookup"><span data-stu-id="a89b6-139">0</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="a89b6-140">論理演算子とビット演算子は、他の算術演算子および関係演算子より優先順位が低いので、正確な実行を保証するために、ビットごとの演算はかっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="a89b6-140">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
 <span data-ttu-id="a89b6-141">たとえば、5 `Xor` 3 は 6 です。</span><span class="sxs-lookup"><span data-stu-id="a89b6-141">For example, 5 `Xor` 3 is 6.</span></span> <span data-ttu-id="a89b6-142">なぜそのようになるのかを確認するには、5 と 3 をそれぞれのバイナリ表現 (101 および 011) に変換します。</span><span class="sxs-lookup"><span data-stu-id="a89b6-142">To see why this is so, convert 5 and 3 to their binary representations, 101 and 011.</span></span> <span data-ttu-id="a89b6-143">次に、前の表を使用して、101 Xor 011 が 110 になることを確認します。これは 10 進数 6 のバイナリ表現です。</span><span class="sxs-lookup"><span data-stu-id="a89b6-143">Then use the previous table to determine that 101 Xor 011 is 110, which is the binary representation of the decimal number 6.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="a89b6-144">データの種類</span><span class="sxs-lookup"><span data-stu-id="a89b6-144">Data Types</span></span>  
 <span data-ttu-id="a89b6-145">オペランドが 1 つの `Boolean` 式と 1 つの数値式で構成されている場合、Visual Basic では `Boolean` 式が数値に変換され (`True` の場合は –1、`False` の場合は 0)、ビットごとの演算が実行されます。</span><span class="sxs-lookup"><span data-stu-id="a89b6-145">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="a89b6-146">`Boolean` の比較の場合、結果のデータ型は `Boolean` になります。</span><span class="sxs-lookup"><span data-stu-id="a89b6-146">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="a89b6-147">ビットごとの比較の場合、結果のデータ型は `expression1` および `expression2` のデータ型に適した数値型になります。</span><span class="sxs-lookup"><span data-stu-id="a89b6-147">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="a89b6-148">[演算子の結果のデータ型](data-types-of-operator-results.md)に関するページ内の表 "関係とビットごとの比較" を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a89b6-148">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="a89b6-149">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="a89b6-149">Overloading</span></span>  
 <span data-ttu-id="a89b6-150">`Xor` 演算子を "*オーバーロード*" できます。つまり、オペランドの型がクラスまたは構造体であるとき、そのクラスまたは構造体で、演算子の動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="a89b6-150">The `Xor` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="a89b6-151">コード内で、そのようなクラスまたは構造体に対してこの演算子が使用されている場合は、再定義されたその動作を必ず理解してください。</span><span class="sxs-lookup"><span data-stu-id="a89b6-151">If your code uses this operator on such a class or structure, make sure you understand its redefined behavior.</span></span> <span data-ttu-id="a89b6-152">詳細については、「 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a89b6-152">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a89b6-153">例</span><span class="sxs-lookup"><span data-stu-id="a89b6-153">Example</span></span>  
 <span data-ttu-id="a89b6-154">次の例では、`Xor` 演算子を使用して、2 つの式の排他的論理和 (排他的論理和演算) を実行します。</span><span class="sxs-lookup"><span data-stu-id="a89b6-154">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on two expressions.</span></span> <span data-ttu-id="a89b6-155">結果は、それらの式のうちの 1 つだけが `True` であるかどうかを表す `Boolean` 値となります。</span><span class="sxs-lookup"><span data-stu-id="a89b6-155">The result is a `Boolean` value that represents whether exactly one of the expressions is `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#40)]  
  
 <span data-ttu-id="a89b6-156">前の例では、それぞれ `False`、`True`、および `False` の結果が生成されます。</span><span class="sxs-lookup"><span data-stu-id="a89b6-156">The previous example produces results of `False`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a89b6-157">例</span><span class="sxs-lookup"><span data-stu-id="a89b6-157">Example</span></span>  
 <span data-ttu-id="a89b6-158">次の例では、`Xor` 演算子を使用して、2 つの数値式の個々のビットに対して排他的論理和 (排他的論理和演算) を実行します。</span><span class="sxs-lookup"><span data-stu-id="a89b6-158">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="a89b6-159">オペランド内の対応するビットのうちの 1 つだけが 1 に設定されている場合に、結果パターンのビットが設定されます。</span><span class="sxs-lookup"><span data-stu-id="a89b6-159">The bit in the result pattern is set if exactly one of the corresponding bits in the operands is set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#41)]  
  
 <span data-ttu-id="a89b6-160">前の例では、それぞれ 2、12、14 の結果が生成されます。</span><span class="sxs-lookup"><span data-stu-id="a89b6-160">The previous example produces results of 2, 12, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a89b6-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="a89b6-161">See also</span></span>

- [<span data-ttu-id="a89b6-162">論理演算子とビット処理演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a89b6-162">Logical/Bitwise Operators (Visual Basic)</span></span>](logical-bitwise-operators.md)
- [<span data-ttu-id="a89b6-163">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="a89b6-163">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="a89b6-164">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="a89b6-164">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="a89b6-165">Visual Basic の論理演算子とビット演算子</span><span class="sxs-lookup"><span data-stu-id="a89b6-165">Logical and Bitwise Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
