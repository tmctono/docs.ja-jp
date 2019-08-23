---
title: Xor 演算子 (Visual Basic)
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
ms.openlocfilehash: 59f27b92996e1506be5967de88c22fb88e06f5b7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965844"
---
# <a name="xor-operator-visual-basic"></a><span data-ttu-id="73b3e-102">Xor 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="73b3e-102">Xor Operator (Visual Basic)</span></span>
<span data-ttu-id="73b3e-103">2 `Boolean`つの式の論理上の除外、または2つの数値式のビットごとの除外を実行します。</span><span class="sxs-lookup"><span data-stu-id="73b3e-103">Performs a logical exclusion on two `Boolean` expressions, or a bitwise exclusion on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73b3e-104">構文</span><span class="sxs-lookup"><span data-stu-id="73b3e-104">Syntax</span></span>  
  
```  
result = expression1 Xor expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="73b3e-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="73b3e-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="73b3e-106">必須。</span><span class="sxs-lookup"><span data-stu-id="73b3e-106">Required.</span></span> <span data-ttu-id="73b3e-107">任意`Boolean`のまたは数値変数。</span><span class="sxs-lookup"><span data-stu-id="73b3e-107">Any `Boolean` or numeric variable.</span></span> <span data-ttu-id="73b3e-108">ブール値の比較`result`の場合、は2つ`Boolean`の値の論理的な排他的論理和です。</span><span class="sxs-lookup"><span data-stu-id="73b3e-108">For Boolean comparison, `result` is the logical exclusion (exclusive logical disjunction) of two `Boolean` values.</span></span> <span data-ttu-id="73b3e-109">ビットごとの演算`result`の場合、は、2つの数値ビットパターンのビットごとの排他的論理和を表す数値です。</span><span class="sxs-lookup"><span data-stu-id="73b3e-109">For bitwise operations, `result` is a numeric value that represents the bitwise exclusion (exclusive bitwise disjunction) of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="73b3e-110">必須。</span><span class="sxs-lookup"><span data-stu-id="73b3e-110">Required.</span></span> <span data-ttu-id="73b3e-111">`Boolean` Or 数値式。</span><span class="sxs-lookup"><span data-stu-id="73b3e-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="73b3e-112">必須。</span><span class="sxs-lookup"><span data-stu-id="73b3e-112">Required.</span></span> <span data-ttu-id="73b3e-113">`Boolean` Or 数値式。</span><span class="sxs-lookup"><span data-stu-id="73b3e-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73b3e-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="73b3e-114">Remarks</span></span>  
 <span data-ttu-id="73b3e-115">ブール値の比較`result`で`True`は、と`expression2`の`expression1`いずれかがに評価さ`True`れる場合にのみ、はになります。</span><span class="sxs-lookup"><span data-stu-id="73b3e-115">For Boolean comparison, `result` is `True` if and only if exactly one of `expression1` and `expression2` evaluates to `True`.</span></span> <span data-ttu-id="73b3e-116">つまり、 `expression1`と`expression2`が逆`Boolean`の値に評価される場合にのみ。</span><span class="sxs-lookup"><span data-stu-id="73b3e-116">That is, if and only if `expression1` and `expression2` evaluate to opposite `Boolean` values.</span></span> <span data-ttu-id="73b3e-117">次の表は、 `result`がどのように決定されるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="73b3e-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="73b3e-118">が`expression1`の場合</span><span class="sxs-lookup"><span data-stu-id="73b3e-118">If `expression1` is</span></span>|<span data-ttu-id="73b3e-119">と`expression2`は</span><span class="sxs-lookup"><span data-stu-id="73b3e-119">And `expression2` is</span></span>|<span data-ttu-id="73b3e-120">の`result`値はです。</span><span class="sxs-lookup"><span data-stu-id="73b3e-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`False`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> <span data-ttu-id="73b3e-121">ブール値の比較では`Xor` 、演算子は常に両方の式を評価します。これには、プロシージャ呼び出しを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="73b3e-121">In a Boolean comparison, the `Xor` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="73b3e-122">結果は常に両方のオペランドに`Xor`依存しているため、に対応するショートサーキットはありません。</span><span class="sxs-lookup"><span data-stu-id="73b3e-122">There is no short-circuiting counterpart to `Xor`, because the result always depends on both operands.</span></span> <span data-ttu-id="73b3e-123">*ショートサーキット*論理演算子については、「 [AndAlso 演算子](../../../visual-basic/language-reference/operators/andalso-operator.md)と[OrElse 演算子](../../../visual-basic/language-reference/operators/orelse-operator.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73b3e-123">For *short-circuiting* logical operators, see [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) and [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md).</span></span>  
  
 <span data-ttu-id="73b3e-124">ビットごとの演算の`Xor`場合、演算子は2つの数値式で同一の位置指定ビットのビットごと`result`の比較を実行し、次の表に従って、に対応するビットを設定します。</span><span class="sxs-lookup"><span data-stu-id="73b3e-124">For bitwise operations, the `Xor` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="73b3e-125">の`expression1`ビットがの場合</span><span class="sxs-lookup"><span data-stu-id="73b3e-125">If bit in `expression1` is</span></span>|<span data-ttu-id="73b3e-126">との`expression2`ビットは</span><span class="sxs-lookup"><span data-stu-id="73b3e-126">And bit in `expression2` is</span></span>|<span data-ttu-id="73b3e-127">の`result`ビットはです。</span><span class="sxs-lookup"><span data-stu-id="73b3e-127">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="73b3e-128">1</span><span class="sxs-lookup"><span data-stu-id="73b3e-128">1</span></span>|<span data-ttu-id="73b3e-129">1</span><span class="sxs-lookup"><span data-stu-id="73b3e-129">1</span></span>|<span data-ttu-id="73b3e-130">0</span><span class="sxs-lookup"><span data-stu-id="73b3e-130">0</span></span>|  
|<span data-ttu-id="73b3e-131">1</span><span class="sxs-lookup"><span data-stu-id="73b3e-131">1</span></span>|<span data-ttu-id="73b3e-132">0</span><span class="sxs-lookup"><span data-stu-id="73b3e-132">0</span></span>|<span data-ttu-id="73b3e-133">1</span><span class="sxs-lookup"><span data-stu-id="73b3e-133">1</span></span>|  
|<span data-ttu-id="73b3e-134">0</span><span class="sxs-lookup"><span data-stu-id="73b3e-134">0</span></span>|<span data-ttu-id="73b3e-135">1</span><span class="sxs-lookup"><span data-stu-id="73b3e-135">1</span></span>|<span data-ttu-id="73b3e-136">1</span><span class="sxs-lookup"><span data-stu-id="73b3e-136">1</span></span>|  
|<span data-ttu-id="73b3e-137">0</span><span class="sxs-lookup"><span data-stu-id="73b3e-137">0</span></span>|<span data-ttu-id="73b3e-138">0</span><span class="sxs-lookup"><span data-stu-id="73b3e-138">0</span></span>|<span data-ttu-id="73b3e-139">0</span><span class="sxs-lookup"><span data-stu-id="73b3e-139">0</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="73b3e-140">論理演算子とビット処理演算子は、他の算術演算子および関係演算子より優先順位が低いので、ビットごとの演算は、正確な実行を保証するためにかっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="73b3e-140">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
 <span data-ttu-id="73b3e-141">たとえば、5 `Xor` 3 は6です。</span><span class="sxs-lookup"><span data-stu-id="73b3e-141">For example, 5 `Xor` 3 is 6.</span></span> <span data-ttu-id="73b3e-142">その理由を確認するには、5と3をバイナリ表現101および011に変換します。</span><span class="sxs-lookup"><span data-stu-id="73b3e-142">To see why this is so, convert 5 and 3 to their binary representations, 101 and 011.</span></span> <span data-ttu-id="73b3e-143">次に、前の表を使用して、101 Xor 011 が110であることを確認します。これは、10進数6のバイナリ表現です。</span><span class="sxs-lookup"><span data-stu-id="73b3e-143">Then use the previous table to determine that 101 Xor 011 is 110, which is the binary representation of the decimal number 6.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="73b3e-144">データの種類</span><span class="sxs-lookup"><span data-stu-id="73b3e-144">Data Types</span></span>  
 <span data-ttu-id="73b3e-145">`Boolean`オペランドが1つの式と1つの数値式で構成され`Boolean`ている場合、Visual Basic は式を数値`True`に変換し`False`(の場合は–1、の場合は 0)、ビットごとの演算を実行します。</span><span class="sxs-lookup"><span data-stu-id="73b3e-145">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="73b3e-146">比較の場合、結果のデータ型は`Boolean`になります。 `Boolean`</span><span class="sxs-lookup"><span data-stu-id="73b3e-146">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="73b3e-147">ビットごとの比較の場合、結果のデータ型は、および`expression1` `expression2`のデータ型に適した数値型になります。</span><span class="sxs-lookup"><span data-stu-id="73b3e-147">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="73b3e-148">「[演算子の結果のデータ型](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)」の「リレーショナルおよびビットごとの比較」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73b3e-148">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="73b3e-149">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="73b3e-149">Overloading</span></span>  
 <span data-ttu-id="73b3e-150">演算子はオーバーロードできます。つまり、クラスまたは構造体がそのクラスまたは構造体の型を持つ場合に、クラスまたは構造体がその動作を再定義できます。 `Xor`</span><span class="sxs-lookup"><span data-stu-id="73b3e-150">The `Xor` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="73b3e-151">コードでこのようなクラスまたは構造体に対してこの演算子を使用する場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="73b3e-151">If your code uses this operator on such a class or structure, make sure you understand its redefined behavior.</span></span> <span data-ttu-id="73b3e-152">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73b3e-152">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="73b3e-153">例</span><span class="sxs-lookup"><span data-stu-id="73b3e-153">Example</span></span>  
 <span data-ttu-id="73b3e-154">次の例では`Xor` 、演算子を使用して、2つの式に対して論理的な排他的論理和を実行します。</span><span class="sxs-lookup"><span data-stu-id="73b3e-154">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on two expressions.</span></span> <span data-ttu-id="73b3e-155">結果は、式`Boolean`の1つだけがで`True`あるかどうかを表す値です。</span><span class="sxs-lookup"><span data-stu-id="73b3e-155">The result is a `Boolean` value that represents whether exactly one of the expressions is `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#40)]  
  
 <span data-ttu-id="73b3e-156">前の例では、 `False` `True`それぞれ、、 `False`およびの結果を生成します。</span><span class="sxs-lookup"><span data-stu-id="73b3e-156">The previous example produces results of `False`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73b3e-157">例</span><span class="sxs-lookup"><span data-stu-id="73b3e-157">Example</span></span>  
 <span data-ttu-id="73b3e-158">次の例では`Xor` 、演算子を使用して、2つの数値式の個々のビットに対して論理的な除外 (排他的論理和) を実行します。</span><span class="sxs-lookup"><span data-stu-id="73b3e-158">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="73b3e-159">オペランドの対応するビットの1つだけが1に設定されている場合、結果パターンのビットは設定されます。</span><span class="sxs-lookup"><span data-stu-id="73b3e-159">The bit in the result pattern is set if exactly one of the corresponding bits in the operands is set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#41)]  
  
 <span data-ttu-id="73b3e-160">前の例では、それぞれ2、12、14の結果が生成されます。</span><span class="sxs-lookup"><span data-stu-id="73b3e-160">The previous example produces results of 2, 12, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73b3e-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="73b3e-161">See also</span></span>

- [<span data-ttu-id="73b3e-162">論理/ビット演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="73b3e-162">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="73b3e-163">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="73b3e-163">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="73b3e-164">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="73b3e-164">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="73b3e-165">Visual Basic の論理演算子とビット処理演算子</span><span class="sxs-lookup"><span data-stu-id="73b3e-165">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
