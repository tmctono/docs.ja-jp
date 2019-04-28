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
ms.openlocfilehash: 0cba3a995fb1ab774c8a5308e58f0b6905fc23f3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781174"
---
# <a name="xor-operator-visual-basic"></a><span data-ttu-id="39724-102">Xor 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="39724-102">Xor Operator (Visual Basic)</span></span>
<span data-ttu-id="39724-103">2 つの排他的論理和`Boolean`式、または 2 つの数値式の和を求めます。</span><span class="sxs-lookup"><span data-stu-id="39724-103">Performs a logical exclusion on two `Boolean` expressions, or a bitwise exclusion on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39724-104">構文</span><span class="sxs-lookup"><span data-stu-id="39724-104">Syntax</span></span>  
  
```  
result = expression1 Xor expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="39724-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="39724-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="39724-106">必須。</span><span class="sxs-lookup"><span data-stu-id="39724-106">Required.</span></span> <span data-ttu-id="39724-107">すべて`Boolean`または数値型の変数。</span><span class="sxs-lookup"><span data-stu-id="39724-107">Any `Boolean` or numeric variable.</span></span> <span data-ttu-id="39724-108">ブール値の比較の`result`は 2 つの論理和 (排他的論理和)`Boolean`値。</span><span class="sxs-lookup"><span data-stu-id="39724-108">For Boolean comparison, `result` is the logical exclusion (exclusive logical disjunction) of two `Boolean` values.</span></span> <span data-ttu-id="39724-109">ビットごとの演算`result`は、ビットごと (排他的論理和) の 2 つの数値ビット パターンを表す数値です。</span><span class="sxs-lookup"><span data-stu-id="39724-109">For bitwise operations, `result` is a numeric value that represents the bitwise exclusion (exclusive bitwise disjunction) of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="39724-110">必須。</span><span class="sxs-lookup"><span data-stu-id="39724-110">Required.</span></span> <span data-ttu-id="39724-111">すべて`Boolean`または数値式です。</span><span class="sxs-lookup"><span data-stu-id="39724-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="39724-112">必須。</span><span class="sxs-lookup"><span data-stu-id="39724-112">Required.</span></span> <span data-ttu-id="39724-113">すべて`Boolean`または数値式です。</span><span class="sxs-lookup"><span data-stu-id="39724-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39724-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="39724-114">Remarks</span></span>  
 <span data-ttu-id="39724-115">ブール値の比較の`result`は`True`場合にのみの 1 つだけ`expression1`と`expression2`に評価される`True`します。</span><span class="sxs-lookup"><span data-stu-id="39724-115">For Boolean comparison, `result` is `True` if and only if exactly one of `expression1` and `expression2` evaluates to `True`.</span></span> <span data-ttu-id="39724-116">つまり、場合にのみ`expression1`と`expression2`評価に反対`Boolean`値。</span><span class="sxs-lookup"><span data-stu-id="39724-116">That is, if and only if `expression1` and `expression2` evaluate to opposite `Boolean` values.</span></span> <span data-ttu-id="39724-117">次の表はどのように`result`決定されます。</span><span class="sxs-lookup"><span data-stu-id="39724-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="39724-118">場合`expression1`は</span><span class="sxs-lookup"><span data-stu-id="39724-118">If `expression1` is</span></span>|<span data-ttu-id="39724-119">`expression2`は</span><span class="sxs-lookup"><span data-stu-id="39724-119">And `expression2` is</span></span>|<span data-ttu-id="39724-120">値`result`は</span><span class="sxs-lookup"><span data-stu-id="39724-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`False`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  <span data-ttu-id="39724-121">ブール値の比較で、`Xor`演算子では、両方の式では、プロシージャの呼び出しを含めることが常に評価されます。</span><span class="sxs-lookup"><span data-stu-id="39724-121">In a Boolean comparison, the `Xor` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="39724-122">相当するショート サーキットはありません`Xor`結果は常に両方のオペランドに依存します。</span><span class="sxs-lookup"><span data-stu-id="39724-122">There is no short-circuiting counterpart to `Xor`, because the result always depends on both operands.</span></span> <span data-ttu-id="39724-123">*ショート サーキット*論理演算子を参照してください[AndAlso 演算子](../../../visual-basic/language-reference/operators/andalso-operator.md)と[OrElse 演算子](../../../visual-basic/language-reference/operators/orelse-operator.md)します。</span><span class="sxs-lookup"><span data-stu-id="39724-123">For *short-circuiting* logical operators, see [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) and [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md).</span></span>  
  
 <span data-ttu-id="39724-124">ビットごとの演算、`Xor`演算子が 2 つの数値式で同じ位置にビットのビット単位の比較を実行し、対応するでビットを設定`result`次の表に従ってします。</span><span class="sxs-lookup"><span data-stu-id="39724-124">For bitwise operations, the `Xor` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="39724-125">場合にビット`expression1`は</span><span class="sxs-lookup"><span data-stu-id="39724-125">If bit in `expression1` is</span></span>|<span data-ttu-id="39724-126">ビットと`expression2`は</span><span class="sxs-lookup"><span data-stu-id="39724-126">And bit in `expression2` is</span></span>|<span data-ttu-id="39724-127">内のビット`result`は</span><span class="sxs-lookup"><span data-stu-id="39724-127">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="39724-128">1</span><span class="sxs-lookup"><span data-stu-id="39724-128">1</span></span>|<span data-ttu-id="39724-129">1</span><span class="sxs-lookup"><span data-stu-id="39724-129">1</span></span>|<span data-ttu-id="39724-130">0</span><span class="sxs-lookup"><span data-stu-id="39724-130">0</span></span>|  
|<span data-ttu-id="39724-131">1</span><span class="sxs-lookup"><span data-stu-id="39724-131">1</span></span>|<span data-ttu-id="39724-132">0</span><span class="sxs-lookup"><span data-stu-id="39724-132">0</span></span>|<span data-ttu-id="39724-133">1</span><span class="sxs-lookup"><span data-stu-id="39724-133">1</span></span>|  
|<span data-ttu-id="39724-134">0</span><span class="sxs-lookup"><span data-stu-id="39724-134">0</span></span>|<span data-ttu-id="39724-135">1</span><span class="sxs-lookup"><span data-stu-id="39724-135">1</span></span>|<span data-ttu-id="39724-136">1</span><span class="sxs-lookup"><span data-stu-id="39724-136">1</span></span>|  
|<span data-ttu-id="39724-137">0</span><span class="sxs-lookup"><span data-stu-id="39724-137">0</span></span>|<span data-ttu-id="39724-138">0</span><span class="sxs-lookup"><span data-stu-id="39724-138">0</span></span>|<span data-ttu-id="39724-139">0</span><span class="sxs-lookup"><span data-stu-id="39724-139">0</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="39724-140">論理/ビット処理演算子の他の算術演算子や関係演算子よりも優先順位の低いため、ビットごとの演算は、正確に実行されるようにかっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="39724-140">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
 <span data-ttu-id="39724-141">たとえば、5 `Xor` 3 は 6 です。</span><span class="sxs-lookup"><span data-stu-id="39724-141">For example, 5 `Xor` 3 is 6.</span></span> <span data-ttu-id="39724-142">これが理由を確認するために、5、3 を 101 と 011 のバイナリ表現に変換します。</span><span class="sxs-lookup"><span data-stu-id="39724-142">To see why this is so, convert 5 and 3 to their binary representations, 101 and 011.</span></span> <span data-ttu-id="39724-143">101 Xor 011 では、110 が 6 の 10 進数のバイナリ表現であるを判断するのに前の表を使用します。</span><span class="sxs-lookup"><span data-stu-id="39724-143">Then use the previous table to determine that 101 Xor 011 is 110, which is the binary representation of the decimal number 6.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="39724-144">データの種類</span><span class="sxs-lookup"><span data-stu-id="39724-144">Data Types</span></span>  
 <span data-ttu-id="39724-145">いずれかのオペランドで構成される場合`Boolean`式と 1 つの数値式では、Visual Basic に変換します、`Boolean`式を数値に (– 1 `True` 0 `False`) し、ビットごとの演算を実行します。</span><span class="sxs-lookup"><span data-stu-id="39724-145">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="39724-146">`Boolean`比較、結果のデータ型は`Boolean`します。</span><span class="sxs-lookup"><span data-stu-id="39724-146">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="39724-147">ビット単位の比較結果のデータ型は数値型のデータ型に適した`expression1`と`expression2`します。</span><span class="sxs-lookup"><span data-stu-id="39724-147">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="39724-148">「リレーショナルとビットごとの比較」表を参照して[演算子結果のデータ型](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)します。</span><span class="sxs-lookup"><span data-stu-id="39724-148">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="39724-149">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="39724-149">Overloading</span></span>  
 <span data-ttu-id="39724-150">`Xor`演算子は、*オーバー ロードされた*、つまり、ことクラスまたは構造体を再定義できますその動作はそのクラスまたは構造体の型。</span><span class="sxs-lookup"><span data-stu-id="39724-150">The `Xor` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="39724-151">コードは、このようなクラスまたは構造体に、この演算子を使用する場合、再定義された動作を理解することを確認します。</span><span class="sxs-lookup"><span data-stu-id="39724-151">If your code uses this operator on such a class or structure, make sure you understand its redefined behavior.</span></span> <span data-ttu-id="39724-152">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39724-152">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="39724-153">例</span><span class="sxs-lookup"><span data-stu-id="39724-153">Example</span></span>  
 <span data-ttu-id="39724-154">次の例では、 `Xor` 2 つの式に対して論理和 (排他的論理和) を実行する演算子。</span><span class="sxs-lookup"><span data-stu-id="39724-154">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on two expressions.</span></span> <span data-ttu-id="39724-155">結果は、`Boolean`が式の 1 つだけかどうかを表す値`True`します。</span><span class="sxs-lookup"><span data-stu-id="39724-155">The result is a `Boolean` value that represents whether exactly one of the expressions is `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#40)]  
  
 <span data-ttu-id="39724-156">前の例の結果を生成する`False`、 `True`、および`False`、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="39724-156">The previous example produces results of `False`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39724-157">例</span><span class="sxs-lookup"><span data-stu-id="39724-157">Example</span></span>  
 <span data-ttu-id="39724-158">次の例では、`Xor`オペレーターが 2 つの数値式のビットごとの排他的論理和 (排他的論理和) を実行します。</span><span class="sxs-lookup"><span data-stu-id="39724-158">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="39724-159">オペランドの対応するビットを 1 つを 1 に設定されている場合、結果のパターンのビットが設定されます。</span><span class="sxs-lookup"><span data-stu-id="39724-159">The bit in the result pattern is set if exactly one of the corresponding bits in the operands is set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#41)]  
  
 <span data-ttu-id="39724-160">前の例では、それぞれ 2、12、14 の結果を生成します。</span><span class="sxs-lookup"><span data-stu-id="39724-160">The previous example produces results of 2, 12, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39724-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="39724-161">See also</span></span>

- [<span data-ttu-id="39724-162">論理/ビット演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="39724-162">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="39724-163">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="39724-163">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="39724-164">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="39724-164">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="39724-165">Visual Basic での論理とビット処理演算子</span><span class="sxs-lookup"><span data-stu-id="39724-165">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
