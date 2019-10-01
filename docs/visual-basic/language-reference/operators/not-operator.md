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
ms.openlocfilehash: 5ebc5f9dbf674a9a6560bd96b3e8c9edcae08a81
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701073"
---
# <a name="not-operator-visual-basic"></a><span data-ttu-id="9770a-102">Not 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9770a-102">Not Operator (Visual Basic)</span></span>
<span data-ttu-id="9770a-103">@No__t 0 式の場合は論理否定、数値式の場合はビットごとの否定を実行します。</span><span class="sxs-lookup"><span data-stu-id="9770a-103">Performs logical negation on a `Boolean` expression, or bitwise negation on a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9770a-104">構文</span><span class="sxs-lookup"><span data-stu-id="9770a-104">Syntax</span></span>  
  
```vb  
result = Not expression  
```  
  
## <a name="parts"></a><span data-ttu-id="9770a-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="9770a-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="9770a-106">必須。</span><span class="sxs-lookup"><span data-stu-id="9770a-106">Required.</span></span> <span data-ttu-id="9770a-107">`Boolean` Or 数値式。</span><span class="sxs-lookup"><span data-stu-id="9770a-107">Any `Boolean` or numeric expression.</span></span>  
  
 `expression`  
 <span data-ttu-id="9770a-108">必須。</span><span class="sxs-lookup"><span data-stu-id="9770a-108">Required.</span></span> <span data-ttu-id="9770a-109">`Boolean` Or 数値式。</span><span class="sxs-lookup"><span data-stu-id="9770a-109">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9770a-110">コメント</span><span class="sxs-lookup"><span data-stu-id="9770a-110">Remarks</span></span>  
 <span data-ttu-id="9770a-111">@No__t 0 の式の場合、次の表は `result` がどのように決定されるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="9770a-111">For `Boolean` expressions, the following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="9770a-112">が`expression`の場合</span><span class="sxs-lookup"><span data-stu-id="9770a-112">If `expression` is</span></span>|<span data-ttu-id="9770a-113">@No__t-0 の値はです。</span><span class="sxs-lookup"><span data-stu-id="9770a-113">The value of `result` is</span></span>|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 <span data-ttu-id="9770a-114">数値式の場合、`Not` 演算子は任意の数値式のビット値を反転し、次の表に従って `result` の対応するビットを設定します。</span><span class="sxs-lookup"><span data-stu-id="9770a-114">For numeric expressions, the `Not` operator inverts the bit values of any numeric expression and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="9770a-115">@No__t のビットが0の場合</span><span class="sxs-lookup"><span data-stu-id="9770a-115">If bit in `expression` is</span></span>|<span data-ttu-id="9770a-116">@No__t-0 のビットはです。</span><span class="sxs-lookup"><span data-stu-id="9770a-116">The bit in `result` is</span></span>|  
|-------------------------------|----------------------------|  
|<span data-ttu-id="9770a-117">1</span><span class="sxs-lookup"><span data-stu-id="9770a-117">1</span></span>|<span data-ttu-id="9770a-118">0</span><span class="sxs-lookup"><span data-stu-id="9770a-118">0</span></span>|  
|<span data-ttu-id="9770a-119">0</span><span class="sxs-lookup"><span data-stu-id="9770a-119">0</span></span>|<span data-ttu-id="9770a-120">1</span><span class="sxs-lookup"><span data-stu-id="9770a-120">1</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="9770a-121">論理演算子とビット処理演算子は、他の算術演算子および関係演算子より優先順位が低いので、ビットごとの演算は、正確な実行を保証するためにかっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="9770a-121">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="9770a-122">データ型</span><span class="sxs-lookup"><span data-stu-id="9770a-122">Data Types</span></span>  
 <span data-ttu-id="9770a-123">ブール否定の場合、結果のデータ型は `Boolean` になります。</span><span class="sxs-lookup"><span data-stu-id="9770a-123">For a Boolean negation, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="9770a-124">ビットごとの否定の場合、結果のデータ型は `expression` と同じになります。</span><span class="sxs-lookup"><span data-stu-id="9770a-124">For a bitwise negation, the result data type is the same as that of `expression`.</span></span> <span data-ttu-id="9770a-125">ただし、expression が `Decimal` の場合、結果は-1 @no__t ます。</span><span class="sxs-lookup"><span data-stu-id="9770a-125">However, if expression is `Decimal`, the result is `Long`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="9770a-126">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="9770a-126">Overloading</span></span>  
 <span data-ttu-id="9770a-127">@No__t-0 演算子は*オーバーロード*できます。つまり、クラスまたは構造体のオペランドがそのクラスまたは構造体の型を持つ場合に、クラスまたは構造体がその動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="9770a-127">The `Not` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="9770a-128">コードでこのようなクラスまたは構造体に対してこの演算子を使用する場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9770a-128">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="9770a-129">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9770a-129">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9770a-130">例</span><span class="sxs-lookup"><span data-stu-id="9770a-130">Example</span></span>  
 <span data-ttu-id="9770a-131">次の例では、`Not` 演算子を使用して、`Boolean` 式の論理否定を実行します。</span><span class="sxs-lookup"><span data-stu-id="9770a-131">The following example uses the `Not` operator to perform logical negation on a `Boolean` expression.</span></span> <span data-ttu-id="9770a-132">結果は、式の値の逆を表す @no__t 0 の値になります。</span><span class="sxs-lookup"><span data-stu-id="9770a-132">The result is a `Boolean` value that represents the reverse of the value of the expression.</span></span>  
  
 [!code-vb[VbVbalrOperators#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#33)]  
  
 <span data-ttu-id="9770a-133">前の例では、`False` と `True` の結果がそれぞれ生成されます。</span><span class="sxs-lookup"><span data-stu-id="9770a-133">The preceding example produces results of `False` and `True`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9770a-134">例</span><span class="sxs-lookup"><span data-stu-id="9770a-134">Example</span></span>  
 <span data-ttu-id="9770a-135">次の例では、`Not` 演算子を使用して、数値式の個々のビットの論理否定を実行します。</span><span class="sxs-lookup"><span data-stu-id="9770a-135">The following example uses the `Not` operator to perform logical negation of the individual bits of a numeric expression.</span></span> <span data-ttu-id="9770a-136">結果パターンのビットは、オペランドパターンの対応するビットの逆順 (符号ビットを含む) に設定されます。</span><span class="sxs-lookup"><span data-stu-id="9770a-136">The bit in the result pattern is set to the reverse of the corresponding bit in the operand pattern, including the sign bit.</span></span>  
  
 [!code-vb[VbVbalrOperators#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#34)]  
  
 <span data-ttu-id="9770a-137">前の例では、それぞれ–11、–9、および–7の結果が生成されます。</span><span class="sxs-lookup"><span data-stu-id="9770a-137">The preceding example produces results of –11, –9, and –7, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9770a-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="9770a-138">See also</span></span>

- [<span data-ttu-id="9770a-139">論理/ビット演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9770a-139">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="9770a-140">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="9770a-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="9770a-141">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="9770a-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="9770a-142">Visual Basic の論理演算子とビット処理演算子</span><span class="sxs-lookup"><span data-stu-id="9770a-142">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
