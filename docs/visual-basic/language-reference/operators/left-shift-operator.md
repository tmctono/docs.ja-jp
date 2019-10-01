---
title: < < 演算子 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.<<
helpviewer_keywords:
- bit shift operators [Visual Basic]
- << operator [Visual Basic]
- operator <<, Visual Basic left shift operator
ms.assetid: fdb93d25-81ba-417f-b808-41207bfb8440
ms.openlocfilehash: 1300ab60e825e7910825be2c65dcab90135ba988
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701121"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="e8c8f-102">\<\<演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e8c8f-102">\<\< Operator (Visual Basic)</span></span>
<span data-ttu-id="e8c8f-103">ビットパターンに対して算術左シフトを実行します。</span><span class="sxs-lookup"><span data-stu-id="e8c8f-103">Performs an arithmetic left shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8c8f-104">構文</span><span class="sxs-lookup"><span data-stu-id="e8c8f-104">Syntax</span></span>  
  
```vb  
result = pattern << amount  
```  
  
## <a name="parts"></a><span data-ttu-id="e8c8f-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="e8c8f-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="e8c8f-106">必須。</span><span class="sxs-lookup"><span data-stu-id="e8c8f-106">Required.</span></span> <span data-ttu-id="e8c8f-107">整数の数値。</span><span class="sxs-lookup"><span data-stu-id="e8c8f-107">Integral numeric value.</span></span> <span data-ttu-id="e8c8f-108">ビットパターンをシフトした結果。</span><span class="sxs-lookup"><span data-stu-id="e8c8f-108">The result of shifting the bit pattern.</span></span> <span data-ttu-id="e8c8f-109">データ型は、の`pattern`データ型と同じです。</span><span class="sxs-lookup"><span data-stu-id="e8c8f-109">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="e8c8f-110">必須。</span><span class="sxs-lookup"><span data-stu-id="e8c8f-110">Required.</span></span> <span data-ttu-id="e8c8f-111">整数の数値式。</span><span class="sxs-lookup"><span data-stu-id="e8c8f-111">Integral numeric expression.</span></span> <span data-ttu-id="e8c8f-112">シフトされるビットパターン。</span><span class="sxs-lookup"><span data-stu-id="e8c8f-112">The bit pattern to be shifted.</span></span> <span data-ttu-id="e8c8f-113">データ`SByte`型は、整数型 ( `UShort` `Short`、 `Byte`、、 `Integer` `UInteger` `ULong`、、、、または) である必要があります。 `Long`</span><span class="sxs-lookup"><span data-stu-id="e8c8f-113">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="e8c8f-114">必須。</span><span class="sxs-lookup"><span data-stu-id="e8c8f-114">Required.</span></span> <span data-ttu-id="e8c8f-115">数値式。</span><span class="sxs-lookup"><span data-stu-id="e8c8f-115">Numeric expression.</span></span> <span data-ttu-id="e8c8f-116">ビットパターンをシフトするビット数。</span><span class="sxs-lookup"><span data-stu-id="e8c8f-116">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="e8c8f-117">データ型は、 `Integer`またはに`Integer`拡大変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8c8f-117">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8c8f-118">コメント</span><span class="sxs-lookup"><span data-stu-id="e8c8f-118">Remarks</span></span>  
 <span data-ttu-id="e8c8f-119">算術シフトは循環していません。つまり、結果の一方の端からシフトされたビットはもう一方の端には再入されません。</span><span class="sxs-lookup"><span data-stu-id="e8c8f-119">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="e8c8f-120">算術左シフトでは、結果のデータ型の範囲を超えてシフトされたビットは破棄され、右側に空いているビット位置は0に設定されます。</span><span class="sxs-lookup"><span data-stu-id="e8c8f-120">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span></span>  
  
 <span data-ttu-id="e8c8f-121">結果よりも多くのビットでシフトを防止するために、Visual Basic は `pattern` のデータ型に対応するサイズマスクを使用して `amount` の値をマスクします。</span><span class="sxs-lookup"><span data-stu-id="e8c8f-121">To prevent a shift by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask that corresponds to the data type of `pattern`.</span></span> <span data-ttu-id="e8c8f-122">これらの値のバイナリとは、シフトの量に使用されます。</span><span class="sxs-lookup"><span data-stu-id="e8c8f-122">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="e8c8f-123">サイズマスクは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e8c8f-123">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="e8c8f-124">@No__t のデータ型-0</span><span class="sxs-lookup"><span data-stu-id="e8c8f-124">Data type of `pattern`</span></span>|<span data-ttu-id="e8c8f-125">サイズマスク (10 進数)</span><span class="sxs-lookup"><span data-stu-id="e8c8f-125">Size mask (decimal)</span></span>|<span data-ttu-id="e8c8f-126">サイズマスク (16 進数)</span><span class="sxs-lookup"><span data-stu-id="e8c8f-126">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="e8c8f-127">`SByte`, `Byte`</span><span class="sxs-lookup"><span data-stu-id="e8c8f-127">`SByte`, `Byte`</span></span>|<span data-ttu-id="e8c8f-128">7</span><span class="sxs-lookup"><span data-stu-id="e8c8f-128">7</span></span>|<span data-ttu-id="e8c8f-129">& H00000007</span><span class="sxs-lookup"><span data-stu-id="e8c8f-129">&H00000007</span></span>|  
|<span data-ttu-id="e8c8f-130">`Short`, `UShort`</span><span class="sxs-lookup"><span data-stu-id="e8c8f-130">`Short`, `UShort`</span></span>|<span data-ttu-id="e8c8f-131">15</span><span class="sxs-lookup"><span data-stu-id="e8c8f-131">15</span></span>|<span data-ttu-id="e8c8f-132">& H0000000F</span><span class="sxs-lookup"><span data-stu-id="e8c8f-132">&H0000000F</span></span>|  
|<span data-ttu-id="e8c8f-133">`Integer`, `UInteger`</span><span class="sxs-lookup"><span data-stu-id="e8c8f-133">`Integer`, `UInteger`</span></span>|<span data-ttu-id="e8c8f-134">31</span><span class="sxs-lookup"><span data-stu-id="e8c8f-134">31</span></span>|<span data-ttu-id="e8c8f-135">& H0000001F</span><span class="sxs-lookup"><span data-stu-id="e8c8f-135">&H0000001F</span></span>|  
|<span data-ttu-id="e8c8f-136">`Long`, `ULong`</span><span class="sxs-lookup"><span data-stu-id="e8c8f-136">`Long`, `ULong`</span></span>|<span data-ttu-id="e8c8f-137">63</span><span class="sxs-lookup"><span data-stu-id="e8c8f-137">63</span></span>|<span data-ttu-id="e8c8f-138">& H0000003F</span><span class="sxs-lookup"><span data-stu-id="e8c8f-138">&H0000003F</span></span>|  
  
 <span data-ttu-id="e8c8f-139">@No__t-0 が0の場合、`result` の値は `pattern` の値と同じになります。</span><span class="sxs-lookup"><span data-stu-id="e8c8f-139">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="e8c8f-140">@No__t-0 が負の場合は、符号なしの値として取得され、適切なサイズマスクでマスクされます。</span><span class="sxs-lookup"><span data-stu-id="e8c8f-140">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="e8c8f-141">算術シフトではオーバーフロー例外は生成されません。</span><span class="sxs-lookup"><span data-stu-id="e8c8f-141">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e8c8f-142">@No__t-0 演算子は*オーバーロード*できます。つまり、クラスまたは構造体がそのクラスまたは構造体の型を持つ場合に、クラスまたは構造体がその動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="e8c8f-142">The `<<` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="e8c8f-143">コードでこのようなクラスまたは構造体に対してこの演算子を使用する場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e8c8f-143">If your code uses this operator on such a class or structure, be sure that you understand its redefined behavior.</span></span> <span data-ttu-id="e8c8f-144">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8c8f-144">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8c8f-145">例</span><span class="sxs-lookup"><span data-stu-id="e8c8f-145">Example</span></span>  
 <span data-ttu-id="e8c8f-146">次の例では、`<<` 演算子を使用して、整数値に対して算術左シフトを実行します。</span><span class="sxs-lookup"><span data-stu-id="e8c8f-146">The following example uses the `<<` operator to perform arithmetic left shifts on integral values.</span></span> <span data-ttu-id="e8c8f-147">結果は、シフトする式と同じデータ型になります。</span><span class="sxs-lookup"><span data-stu-id="e8c8f-147">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#12)]  
  
 <span data-ttu-id="e8c8f-148">前の例の結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="e8c8f-148">The results of the previous example are as follows:</span></span>  
  
- <span data-ttu-id="e8c8f-149">`result1` は 192 (0000 0000 1100 0000) です。</span><span class="sxs-lookup"><span data-stu-id="e8c8f-149">`result1` is 192 (0000 0000 1100 0000).</span></span>  
  
- <span data-ttu-id="e8c8f-150">`result2` は 3072 (0000 1100 0000 0000) です。</span><span class="sxs-lookup"><span data-stu-id="e8c8f-150">`result2` is 3072 (0000 1100 0000 0000).</span></span>  
  
- <span data-ttu-id="e8c8f-151">`result3` は-32768 (1000 0000 0000 0000) です。</span><span class="sxs-lookup"><span data-stu-id="e8c8f-151">`result3` is -32768 (1000 0000 0000 0000).</span></span>  
  
- <span data-ttu-id="e8c8f-152">`result4` は 384 (0000 0001 1000 0000) です。</span><span class="sxs-lookup"><span data-stu-id="e8c8f-152">`result4` is 384 (0000 0001 1000 0000).</span></span>  
  
- <span data-ttu-id="e8c8f-153">`result5` は 0 (左に15桁にシフト) です。</span><span class="sxs-lookup"><span data-stu-id="e8c8f-153">`result5` is 0 (shifted 15 places to the left).</span></span>  
  
 <span data-ttu-id="e8c8f-154">@No__t-0 のシフト量は、17と15として計算されます。この値は1になります。</span><span class="sxs-lookup"><span data-stu-id="e8c8f-154">The shift amount for `result4` is calculated as 17 AND 15, which equals 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8c8f-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="e8c8f-155">See also</span></span>

- [<span data-ttu-id="e8c8f-156">ビット シフト演算子</span><span class="sxs-lookup"><span data-stu-id="e8c8f-156">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="e8c8f-157">代入演算子</span><span class="sxs-lookup"><span data-stu-id="e8c8f-157">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="e8c8f-158"><<= 演算子</span><span class="sxs-lookup"><span data-stu-id="e8c8f-158"><<= Operator</span></span>](../../../visual-basic/language-reference/operators/left-shift-assignment-operator.md)
- [<span data-ttu-id="e8c8f-159">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="e8c8f-159">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="e8c8f-160">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="e8c8f-160">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="e8c8f-161">Visual Basic の算術演算子</span><span class="sxs-lookup"><span data-stu-id="e8c8f-161">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
