---
title: Not 演算子 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Not
helpviewer_keywords:
- Boolean expressions, negating
- operators [Visual Basic], bitwise
- negation operator [Visual Basic]
- inverse bit values in variables [Visual Basic]
- bitwise operators [Visual Basic], NOT operator
- bitwise comparison [Visual Basic]
- Not operator [Visual Basic]
- logical negation
- operators [Visual Basic], negation
ms.assetid: 8f2ea83c-d2ed-480a-a474-3042a1cad9b5
ms.openlocfilehash: 4e54fdca9123ad5595eb9a8c5e2ac5bc303a8f6a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61936618"
---
# <a name="not-operator-visual-basic"></a><span data-ttu-id="67ceb-102">Not 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="67ceb-102">Not Operator (Visual Basic)</span></span>
<span data-ttu-id="67ceb-103">論理否定を実行、`Boolean`式、または数値式に対してビットごとの否定。</span><span class="sxs-lookup"><span data-stu-id="67ceb-103">Performs logical negation on a `Boolean` expression, or bitwise negation on a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67ceb-104">構文</span><span class="sxs-lookup"><span data-stu-id="67ceb-104">Syntax</span></span>  
  
```  
result = Not expression  
```  
  
## <a name="parts"></a><span data-ttu-id="67ceb-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="67ceb-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="67ceb-106">必須。</span><span class="sxs-lookup"><span data-stu-id="67ceb-106">Required.</span></span> <span data-ttu-id="67ceb-107">すべて`Boolean`または数値式です。</span><span class="sxs-lookup"><span data-stu-id="67ceb-107">Any `Boolean` or numeric expression.</span></span>  
  
 `expression`  
 <span data-ttu-id="67ceb-108">必須。</span><span class="sxs-lookup"><span data-stu-id="67ceb-108">Required.</span></span> <span data-ttu-id="67ceb-109">すべて`Boolean`または数値式です。</span><span class="sxs-lookup"><span data-stu-id="67ceb-109">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67ceb-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="67ceb-110">Remarks</span></span>  
 <span data-ttu-id="67ceb-111">`Boolean`式では、次の表はどのように`result`決定されます。</span><span class="sxs-lookup"><span data-stu-id="67ceb-111">For `Boolean` expressions, the following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="67ceb-112">場合`expression`は</span><span class="sxs-lookup"><span data-stu-id="67ceb-112">If `expression` is</span></span>|<span data-ttu-id="67ceb-113">値`result`は</span><span class="sxs-lookup"><span data-stu-id="67ceb-113">The value of `result` is</span></span>|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 <span data-ttu-id="67ceb-114">数値式の場合、`Not`演算子の任意の数値式のビット値を反転させるし、対応するではビットを設定`result`次の表に従ってします。</span><span class="sxs-lookup"><span data-stu-id="67ceb-114">For numeric expressions, the `Not` operator inverts the bit values of any numeric expression and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="67ceb-115">場合にビット`expression`は</span><span class="sxs-lookup"><span data-stu-id="67ceb-115">If bit in `expression` is</span></span>|<span data-ttu-id="67ceb-116">内のビット`result`は</span><span class="sxs-lookup"><span data-stu-id="67ceb-116">The bit in `result` is</span></span>|  
|-------------------------------|----------------------------|  
|<span data-ttu-id="67ceb-117">1</span><span class="sxs-lookup"><span data-stu-id="67ceb-117">1</span></span>|<span data-ttu-id="67ceb-118">0</span><span class="sxs-lookup"><span data-stu-id="67ceb-118">0</span></span>|  
|<span data-ttu-id="67ceb-119">0</span><span class="sxs-lookup"><span data-stu-id="67ceb-119">0</span></span>|<span data-ttu-id="67ceb-120">1</span><span class="sxs-lookup"><span data-stu-id="67ceb-120">1</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="67ceb-121">論理/ビット処理演算子の他の算術演算子や関係演算子よりも優先順位の低いため、ビットごとの演算は、正確に実行されるようにかっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="67ceb-121">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="67ceb-122">データの種類</span><span class="sxs-lookup"><span data-stu-id="67ceb-122">Data Types</span></span>  
 <span data-ttu-id="67ceb-123">論理否定の場合は、結果のデータ型は`Boolean`します。</span><span class="sxs-lookup"><span data-stu-id="67ceb-123">For a Boolean negation, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="67ceb-124">ビットごとの否定の結果のデータ型と同じ`expression`します。</span><span class="sxs-lookup"><span data-stu-id="67ceb-124">For a bitwise negation, the result data type is the same as that of `expression`.</span></span> <span data-ttu-id="67ceb-125">ただし、式が場合`Decimal`、結果は`Long`します。</span><span class="sxs-lookup"><span data-stu-id="67ceb-125">However, if expression is `Decimal`, the result is `Long`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="67ceb-126">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="67ceb-126">Overloading</span></span>  
 <span data-ttu-id="67ceb-127">`Not`演算子は、*オーバー ロードされた*、いるクラスまたは構造体を再定義できますの動作のオペランドがそのクラスまたは構造体の型を持つときにすることを意味します。</span><span class="sxs-lookup"><span data-stu-id="67ceb-127">The `Not` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="67ceb-128">コードは、このようなクラスまたは構造体に、この演算子を使用する場合は、再定義された動作を確認ください。</span><span class="sxs-lookup"><span data-stu-id="67ceb-128">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="67ceb-129">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67ceb-129">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="67ceb-130">例</span><span class="sxs-lookup"><span data-stu-id="67ceb-130">Example</span></span>  
 <span data-ttu-id="67ceb-131">次の例では、`Not`に対して論理否定を実行する演算子、`Boolean`式。</span><span class="sxs-lookup"><span data-stu-id="67ceb-131">The following example uses the `Not` operator to perform logical negation on a `Boolean` expression.</span></span> <span data-ttu-id="67ceb-132">結果は、`Boolean`式の値の逆の順序を表す値です。</span><span class="sxs-lookup"><span data-stu-id="67ceb-132">The result is a `Boolean` value that represents the reverse of the value of the expression.</span></span>  
  
 [!code-vb[VbVbalrOperators#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#33)]  
  
 <span data-ttu-id="67ceb-133">前の例の結果を生成する`False`と`True`、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="67ceb-133">The preceding example produces results of `False` and `True`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67ceb-134">例</span><span class="sxs-lookup"><span data-stu-id="67ceb-134">Example</span></span>  
 <span data-ttu-id="67ceb-135">次の例では、`Not`数値式のビットごとの論理否定を実行する演算子。</span><span class="sxs-lookup"><span data-stu-id="67ceb-135">The following example uses the `Not` operator to perform logical negation of the individual bits of a numeric expression.</span></span> <span data-ttu-id="67ceb-136">結果パターンのビットは符号ビットを含めて、オペランドのパターンに対応するビットの逆に設定されます。</span><span class="sxs-lookup"><span data-stu-id="67ceb-136">The bit in the result pattern is set to the reverse of the corresponding bit in the operand pattern, including the sign bit.</span></span>  
  
 [!code-vb[VbVbalrOperators#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#34)]  
  
 <span data-ttu-id="67ceb-137">前の例では、– 11、– 9、および – 7 の結果をそれぞれ生成されます。</span><span class="sxs-lookup"><span data-stu-id="67ceb-137">The preceding example produces results of –11, –9, and –7, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67ceb-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="67ceb-138">See also</span></span>

- [<span data-ttu-id="67ceb-139">論理/ビット演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="67ceb-139">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="67ceb-140">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="67ceb-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="67ceb-141">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="67ceb-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="67ceb-142">Visual Basic での論理とビット処理演算子</span><span class="sxs-lookup"><span data-stu-id="67ceb-142">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
