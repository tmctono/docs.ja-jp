---
title: << 演算子 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.<<
helpviewer_keywords:
- bit shift operators [Visual Basic]
- << operator [Visual Basic]
- operator <<, Visual Basic left shift operator
ms.assetid: fdb93d25-81ba-417f-b808-41207bfb8440
ms.openlocfilehash: 75c16c27dc919ba365cbe3c28c61a1e46496b0ae
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768291"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="c5b90-102">\<\< 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c5b90-102">\<\< Operator (Visual Basic)</span></span>
<span data-ttu-id="c5b90-103">ビット パターン上で算術左シフトを実行します。</span><span class="sxs-lookup"><span data-stu-id="c5b90-103">Performs an arithmetic left shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5b90-104">構文</span><span class="sxs-lookup"><span data-stu-id="c5b90-104">Syntax</span></span>  
  
```  
result = pattern << amount  
```  
  
## <a name="parts"></a><span data-ttu-id="c5b90-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="c5b90-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="c5b90-106">必須。</span><span class="sxs-lookup"><span data-stu-id="c5b90-106">Required.</span></span> <span data-ttu-id="c5b90-107">整数値。</span><span class="sxs-lookup"><span data-stu-id="c5b90-107">Integral numeric value.</span></span> <span data-ttu-id="c5b90-108">ビット パターンのシフトの結果。</span><span class="sxs-lookup"><span data-stu-id="c5b90-108">The result of shifting the bit pattern.</span></span> <span data-ttu-id="c5b90-109">データ型がの場合と同じ`pattern`します。</span><span class="sxs-lookup"><span data-stu-id="c5b90-109">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="c5b90-110">必須。</span><span class="sxs-lookup"><span data-stu-id="c5b90-110">Required.</span></span> <span data-ttu-id="c5b90-111">整数の数値式です。</span><span class="sxs-lookup"><span data-stu-id="c5b90-111">Integral numeric expression.</span></span> <span data-ttu-id="c5b90-112">シフトするビット パターンです。</span><span class="sxs-lookup"><span data-stu-id="c5b90-112">The bit pattern to be shifted.</span></span> <span data-ttu-id="c5b90-113">データ型は整数型である必要があります (`SByte`、 `Byte`、 `Short`、 `UShort`、 `Integer`、 `UInteger`、 `Long`、または`ULong`)。</span><span class="sxs-lookup"><span data-stu-id="c5b90-113">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="c5b90-114">必須。</span><span class="sxs-lookup"><span data-stu-id="c5b90-114">Required.</span></span> <span data-ttu-id="c5b90-115">数値式。</span><span class="sxs-lookup"><span data-stu-id="c5b90-115">Numeric expression.</span></span> <span data-ttu-id="c5b90-116">ビット パターンをシフトするビット数。</span><span class="sxs-lookup"><span data-stu-id="c5b90-116">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="c5b90-117">データ型である必要があります`Integer`に拡大変換または`Integer`します。</span><span class="sxs-lookup"><span data-stu-id="c5b90-117">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c5b90-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="c5b90-118">Remarks</span></span>  
 <span data-ttu-id="c5b90-119">算術シフトは循環、つまり、もう一方の端に結果の 1 つの端のシフトは行われません。</span><span class="sxs-lookup"><span data-stu-id="c5b90-119">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="c5b90-120">算術左シフトでは、結果のデータ型の範囲を超えてシフトが破棄され、右側の空いたビット位置が 0 に設定します。</span><span class="sxs-lookup"><span data-stu-id="c5b90-120">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span></span>  
  
 <span data-ttu-id="c5b90-121">結果が保持できるより多くのビットをシフトを防ぐためには、Visual Basic がの値をマスク`amount`のデータ型に対応するサイズのマスクを持つ`pattern`します。</span><span class="sxs-lookup"><span data-stu-id="c5b90-121">To prevent a shift by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask that corresponds to the data type of `pattern`.</span></span> <span data-ttu-id="c5b90-122">これらの値のバイナリとは、シフト数に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c5b90-122">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="c5b90-123">マスク サイズは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c5b90-123">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="c5b90-124">データ型 `pattern`</span><span class="sxs-lookup"><span data-stu-id="c5b90-124">Data type of `pattern`</span></span>|<span data-ttu-id="c5b90-125">サイズのマスク (10 進数)</span><span class="sxs-lookup"><span data-stu-id="c5b90-125">Size mask (decimal)</span></span>|<span data-ttu-id="c5b90-126">サイズのマスク (16 進数)</span><span class="sxs-lookup"><span data-stu-id="c5b90-126">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="c5b90-127">`SByte`, `Byte`</span><span class="sxs-lookup"><span data-stu-id="c5b90-127">`SByte`, `Byte`</span></span>|<span data-ttu-id="c5b90-128">7</span><span class="sxs-lookup"><span data-stu-id="c5b90-128">7</span></span>|<span data-ttu-id="c5b90-129">&AMP; H00000007</span><span class="sxs-lookup"><span data-stu-id="c5b90-129">&H00000007</span></span>|  
|<span data-ttu-id="c5b90-130">`Short`, `UShort`</span><span class="sxs-lookup"><span data-stu-id="c5b90-130">`Short`, `UShort`</span></span>|<span data-ttu-id="c5b90-131">16</span><span class="sxs-lookup"><span data-stu-id="c5b90-131">15</span></span>|<span data-ttu-id="c5b90-132">&AMP; H0000000F</span><span class="sxs-lookup"><span data-stu-id="c5b90-132">&H0000000F</span></span>|  
|<span data-ttu-id="c5b90-133">`Integer`, `UInteger`</span><span class="sxs-lookup"><span data-stu-id="c5b90-133">`Integer`, `UInteger`</span></span>|<span data-ttu-id="c5b90-134">31</span><span class="sxs-lookup"><span data-stu-id="c5b90-134">31</span></span>|<span data-ttu-id="c5b90-135">&AMP; H0000001F</span><span class="sxs-lookup"><span data-stu-id="c5b90-135">&H0000001F</span></span>|  
|<span data-ttu-id="c5b90-136">`Long`, `ULong`</span><span class="sxs-lookup"><span data-stu-id="c5b90-136">`Long`, `ULong`</span></span>|<span data-ttu-id="c5b90-137">63</span><span class="sxs-lookup"><span data-stu-id="c5b90-137">63</span></span>|<span data-ttu-id="c5b90-138">&AMP; H0000003F</span><span class="sxs-lookup"><span data-stu-id="c5b90-138">&H0000003F</span></span>|  
  
 <span data-ttu-id="c5b90-139">場合`amount`の値は 0 が`result`の値と同一では、`pattern`します。</span><span class="sxs-lookup"><span data-stu-id="c5b90-139">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="c5b90-140">場合`amount`が負の場合、符号なしの値として取得され、適切なサイズのマスクでマスクします。</span><span class="sxs-lookup"><span data-stu-id="c5b90-140">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="c5b90-141">算術シフトでは、オーバーフロー例外が生成されません。</span><span class="sxs-lookup"><span data-stu-id="c5b90-141">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c5b90-142">`<<`演算子は、*オーバー ロードされた*、つまり、ことクラスまたは構造体を再定義できますその動作はそのクラスまたは構造体の型。</span><span class="sxs-lookup"><span data-stu-id="c5b90-142">The `<<` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="c5b90-143">場合は、コードでは、この演算子を使用して、このようなクラスまたは構造体で、再定義された動作を理解していることを確認してあります。</span><span class="sxs-lookup"><span data-stu-id="c5b90-143">If your code uses this operator on such a class or structure, be sure that you understand its redefined behavior.</span></span> <span data-ttu-id="c5b90-144">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5b90-144">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5b90-145">例</span><span class="sxs-lookup"><span data-stu-id="c5b90-145">Example</span></span>  
 <span data-ttu-id="c5b90-146">次の例では、`<<`演算子を整数値の算術左シフトを実行します。</span><span class="sxs-lookup"><span data-stu-id="c5b90-146">The following example uses the `<<` operator to perform arithmetic left shifts on integral values.</span></span> <span data-ttu-id="c5b90-147">結果は常に同じデータとしてシフトされる式の型を持ちます。</span><span class="sxs-lookup"><span data-stu-id="c5b90-147">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#12)]  
  
 <span data-ttu-id="c5b90-148">前の例の結果は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c5b90-148">The results of the previous example are as follows:</span></span>  
  
- <span data-ttu-id="c5b90-149">`result1` 192 (0000 0000 1100 0000) です。</span><span class="sxs-lookup"><span data-stu-id="c5b90-149">`result1` is 192 (0000 0000 1100 0000).</span></span>  
  
- <span data-ttu-id="c5b90-150">`result2` 3072 (0000 1100 0000 0000)。</span><span class="sxs-lookup"><span data-stu-id="c5b90-150">`result2` is 3072 (0000 1100 0000 0000).</span></span>  
  
- <span data-ttu-id="c5b90-151">`result3` -32768 (1000 0000 0000 0000) です。</span><span class="sxs-lookup"><span data-stu-id="c5b90-151">`result3` is -32768 (1000 0000 0000 0000).</span></span>  
  
- <span data-ttu-id="c5b90-152">`result4` 384 (0000 0001 1000 0000) です。</span><span class="sxs-lookup"><span data-stu-id="c5b90-152">`result4` is 384 (0000 0001 1000 0000).</span></span>  
  
- <span data-ttu-id="c5b90-153">`result5` 0 (シフト 15 桁) です。</span><span class="sxs-lookup"><span data-stu-id="c5b90-153">`result5` is 0 (shifted 15 places to the left).</span></span>  
  
 <span data-ttu-id="c5b90-154">シフト数`result4`17 として計算されますが 1 に等しいと 15 です。</span><span class="sxs-lookup"><span data-stu-id="c5b90-154">The shift amount for `result4` is calculated as 17 AND 15, which equals 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5b90-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="c5b90-155">See also</span></span>

- [<span data-ttu-id="c5b90-156">ビット シフト演算子</span><span class="sxs-lookup"><span data-stu-id="c5b90-156">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="c5b90-157">代入演算子</span><span class="sxs-lookup"><span data-stu-id="c5b90-157">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="c5b90-158"><<= 演算子</span><span class="sxs-lookup"><span data-stu-id="c5b90-158"><<= Operator</span></span>](../../../visual-basic/language-reference/operators/left-shift-assignment-operator.md)
- [<span data-ttu-id="c5b90-159">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="c5b90-159">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="c5b90-160">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="c5b90-160">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="c5b90-161">Visual Basic における算術演算子</span><span class="sxs-lookup"><span data-stu-id="c5b90-161">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
