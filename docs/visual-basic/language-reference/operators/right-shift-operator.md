---
title: '>> 演算子'
ms.date: 07/20/2015
f1_keywords:
- vb.>>
helpviewer_keywords:
- operator>>
- '>> operator [Visual Basic]'
- bit shift operators [Visual Basic]
- operator >>
- right shift operators [Visual Basic]
ms.assetid: 054dc6a6-47d9-47ef-82da-cfa2b59fbf8f
ms.openlocfilehash: cabf8c569435cc0fc98282f5e8f5fd410e6708dc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347820"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="c09d3-102">> > 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c09d3-102">>> Operator (Visual Basic)</span></span>
<span data-ttu-id="c09d3-103">ビットパターンに対して算術右シフトを実行します。</span><span class="sxs-lookup"><span data-stu-id="c09d3-103">Performs an arithmetic right shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c09d3-104">構文</span><span class="sxs-lookup"><span data-stu-id="c09d3-104">Syntax</span></span>  
  
```vb  
result = pattern >> amount  
```  
  
## <a name="parts"></a><span data-ttu-id="c09d3-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="c09d3-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="c09d3-106">必須。</span><span class="sxs-lookup"><span data-stu-id="c09d3-106">Required.</span></span> <span data-ttu-id="c09d3-107">整数の数値。</span><span class="sxs-lookup"><span data-stu-id="c09d3-107">Integral numeric value.</span></span> <span data-ttu-id="c09d3-108">ビットパターンをシフトした結果。</span><span class="sxs-lookup"><span data-stu-id="c09d3-108">The result of shifting the bit pattern.</span></span> <span data-ttu-id="c09d3-109">データ型は `pattern`のデータ型と同じです。</span><span class="sxs-lookup"><span data-stu-id="c09d3-109">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="c09d3-110">必須。</span><span class="sxs-lookup"><span data-stu-id="c09d3-110">Required.</span></span> <span data-ttu-id="c09d3-111">整数の数値式。</span><span class="sxs-lookup"><span data-stu-id="c09d3-111">Integral numeric expression.</span></span> <span data-ttu-id="c09d3-112">シフトされるビットパターン。</span><span class="sxs-lookup"><span data-stu-id="c09d3-112">The bit pattern to be shifted.</span></span> <span data-ttu-id="c09d3-113">データ型は、整数型 (`SByte`、`Byte`、`Short`、`UShort`、`Integer`、`UInteger`、`Long`、または `ULong`) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c09d3-113">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="c09d3-114">必須。</span><span class="sxs-lookup"><span data-stu-id="c09d3-114">Required.</span></span> <span data-ttu-id="c09d3-115">数値式。</span><span class="sxs-lookup"><span data-stu-id="c09d3-115">Numeric expression.</span></span> <span data-ttu-id="c09d3-116">ビットパターンをシフトするビット数。</span><span class="sxs-lookup"><span data-stu-id="c09d3-116">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="c09d3-117">データ型 `Integer`、または `Integer`に拡大変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c09d3-117">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c09d3-118">コメント</span><span class="sxs-lookup"><span data-stu-id="c09d3-118">Remarks</span></span>  
 <span data-ttu-id="c09d3-119">算術シフトは循環していません。つまり、結果の一方の端からシフトされたビットはもう一方の端には再入されません。</span><span class="sxs-lookup"><span data-stu-id="c09d3-119">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="c09d3-120">算術右シフトでは、右端のビット位置を超えてシフトされたビットは破棄され、左端 (符号) ビットは左側に空いているビット位置に反映されます。</span><span class="sxs-lookup"><span data-stu-id="c09d3-120">In an arithmetic right shift, the bits shifted beyond the rightmost bit position are discarded, and the leftmost (sign) bit is propagated into the bit positions vacated at the left.</span></span> <span data-ttu-id="c09d3-121">これは、`pattern` に負の値がある場合、空いている位置が1に設定されることを意味します。それ以外の場合は0に設定されます。</span><span class="sxs-lookup"><span data-stu-id="c09d3-121">This means that if `pattern` has a negative value, the vacated positions are set to one; otherwise they are set to zero.</span></span>  
  
 <span data-ttu-id="c09d3-122">`Byte`、`UShort`、`UInteger`、および `ULong` のデータ型は符号なしであるため、伝達する符号ビットはありません。</span><span class="sxs-lookup"><span data-stu-id="c09d3-122">Note that the data types `Byte`, `UShort`, `UInteger`, and `ULong` are unsigned, so there is no sign bit to propagate.</span></span> <span data-ttu-id="c09d3-123">`pattern` が符号なしの型の場合、空いている位置は常に0に設定されます。</span><span class="sxs-lookup"><span data-stu-id="c09d3-123">If `pattern` is of any unsigned type, the vacated positions are always set to zero.</span></span>  
  
 <span data-ttu-id="c09d3-124">結果よりも多くのビットがシフトされないようにするため、Visual Basic は `pattern`のデータ型に対応するサイズマスクを使用して `amount` の値をマスクします。</span><span class="sxs-lookup"><span data-stu-id="c09d3-124">To prevent shifting by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask corresponding to the data type of `pattern`.</span></span> <span data-ttu-id="c09d3-125">これらの値のバイナリとは、シフトの量に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c09d3-125">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="c09d3-126">サイズマスクは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c09d3-126">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="c09d3-127">`pattern` のデータ型</span><span class="sxs-lookup"><span data-stu-id="c09d3-127">Data type of `pattern`</span></span>|<span data-ttu-id="c09d3-128">サイズマスク (10 進数)</span><span class="sxs-lookup"><span data-stu-id="c09d3-128">Size mask (decimal)</span></span>|<span data-ttu-id="c09d3-129">サイズマスク (16 進数)</span><span class="sxs-lookup"><span data-stu-id="c09d3-129">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="c09d3-130">`SByte`, `Byte`</span><span class="sxs-lookup"><span data-stu-id="c09d3-130">`SByte`, `Byte`</span></span>|<span data-ttu-id="c09d3-131">7</span><span class="sxs-lookup"><span data-stu-id="c09d3-131">7</span></span>|<span data-ttu-id="c09d3-132">& H00000007</span><span class="sxs-lookup"><span data-stu-id="c09d3-132">&H00000007</span></span>|  
|<span data-ttu-id="c09d3-133">`Short`, `UShort`</span><span class="sxs-lookup"><span data-stu-id="c09d3-133">`Short`, `UShort`</span></span>|<span data-ttu-id="c09d3-134">15</span><span class="sxs-lookup"><span data-stu-id="c09d3-134">15</span></span>|<span data-ttu-id="c09d3-135">& H0000000F</span><span class="sxs-lookup"><span data-stu-id="c09d3-135">&H0000000F</span></span>|  
|<span data-ttu-id="c09d3-136">`Integer`, `UInteger`</span><span class="sxs-lookup"><span data-stu-id="c09d3-136">`Integer`, `UInteger`</span></span>|<span data-ttu-id="c09d3-137">31</span><span class="sxs-lookup"><span data-stu-id="c09d3-137">31</span></span>|<span data-ttu-id="c09d3-138">& H0000001F</span><span class="sxs-lookup"><span data-stu-id="c09d3-138">&H0000001F</span></span>|  
|<span data-ttu-id="c09d3-139">`Long`, `ULong`</span><span class="sxs-lookup"><span data-stu-id="c09d3-139">`Long`, `ULong`</span></span>|<span data-ttu-id="c09d3-140">63</span><span class="sxs-lookup"><span data-stu-id="c09d3-140">63</span></span>|<span data-ttu-id="c09d3-141">& H0000003F</span><span class="sxs-lookup"><span data-stu-id="c09d3-141">&H0000003F</span></span>|  
  
 <span data-ttu-id="c09d3-142">`amount` が0の場合、`result` の値は `pattern`の値と同じになります。</span><span class="sxs-lookup"><span data-stu-id="c09d3-142">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="c09d3-143">`amount` が負の場合は、符号なしの値として取得され、適切なサイズマスクでマスクされます。</span><span class="sxs-lookup"><span data-stu-id="c09d3-143">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="c09d3-144">算術シフトではオーバーフロー例外は生成されません。</span><span class="sxs-lookup"><span data-stu-id="c09d3-144">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="c09d3-145">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="c09d3-145">Overloading</span></span>  
 <span data-ttu-id="c09d3-146">`>>` 演算子は*オーバーロード*することができます。つまり、クラスまたは構造体がそのクラスまたは構造体の型を持つ場合に、クラスまたは構造体がその動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="c09d3-146">The `>>` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="c09d3-147">コードでこのようなクラスまたは構造体に対してこの演算子を使用する場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c09d3-147">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="c09d3-148">詳細については、「[演算子プロシージャ](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c09d3-148">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c09d3-149">例</span><span class="sxs-lookup"><span data-stu-id="c09d3-149">Example</span></span>  
 <span data-ttu-id="c09d3-150">次の例では、`>>` 演算子を使用して、整数値に対して算術右シフトを実行します。</span><span class="sxs-lookup"><span data-stu-id="c09d3-150">The following example uses the `>>` operator to perform arithmetic right shifts on integral values.</span></span> <span data-ttu-id="c09d3-151">結果は、シフトする式と同じデータ型になります。</span><span class="sxs-lookup"><span data-stu-id="c09d3-151">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#14)]  
  
 <span data-ttu-id="c09d3-152">前の例の結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="c09d3-152">The results of the preceding example are as follows:</span></span>  
  
- <span data-ttu-id="c09d3-153">`result1` は 2560 (0000 1010 0000 0000) です。</span><span class="sxs-lookup"><span data-stu-id="c09d3-153">`result1` is 2560 (0000 1010 0000 0000).</span></span>  
  
- <span data-ttu-id="c09d3-154">`result2` は 160 (0000 0000 1010 0000) です。</span><span class="sxs-lookup"><span data-stu-id="c09d3-154">`result2` is 160 (0000 0000 1010 0000).</span></span>  
  
- <span data-ttu-id="c09d3-155">`result3` は 2 (0000 0000 0000 0010) です。</span><span class="sxs-lookup"><span data-stu-id="c09d3-155">`result3` is 2 (0000 0000 0000 0010).</span></span>  
  
- <span data-ttu-id="c09d3-156">`result4` は 640 (0000 0010 1000 0000) です。</span><span class="sxs-lookup"><span data-stu-id="c09d3-156">`result4` is 640 (0000 0010 1000 0000).</span></span>  
  
- <span data-ttu-id="c09d3-157">`result5` が 0 (右に15桁に移動) です。</span><span class="sxs-lookup"><span data-stu-id="c09d3-157">`result5` is 0 (shifted 15 places to the right).</span></span>  
  
 <span data-ttu-id="c09d3-158">`result4` のシフト量は18および15として計算されます。この値は2になります。</span><span class="sxs-lookup"><span data-stu-id="c09d3-158">The shift amount for `result4` is calculated as 18 AND 15, which equals 2.</span></span>  
  
 <span data-ttu-id="c09d3-159">次の例は、負の値での算術シフトを示しています。</span><span class="sxs-lookup"><span data-stu-id="c09d3-159">The following example shows arithmetic shifts on a negative value.</span></span>  
  
 [!code-vb[VbVbalrOperators#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#55)]  
  
 <span data-ttu-id="c09d3-160">前の例の結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="c09d3-160">The results of the preceding example are as follows:</span></span>  
  
- <span data-ttu-id="c09d3-161">`negresult1` は-512 (1111 1110 0000 0000) です。</span><span class="sxs-lookup"><span data-stu-id="c09d3-161">`negresult1` is -512 (1111 1110 0000 0000).</span></span>  
  
- <span data-ttu-id="c09d3-162">`negresult2` が-1 (符号ビットが伝達されます) です。</span><span class="sxs-lookup"><span data-stu-id="c09d3-162">`negresult2` is -1 (the sign bit is propagated).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c09d3-163">参照</span><span class="sxs-lookup"><span data-stu-id="c09d3-163">See also</span></span>

- [<span data-ttu-id="c09d3-164">ビット シフト演算子</span><span class="sxs-lookup"><span data-stu-id="c09d3-164">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="c09d3-165">代入演算子</span><span class="sxs-lookup"><span data-stu-id="c09d3-165">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="c09d3-166">>>= 演算子</span><span class="sxs-lookup"><span data-stu-id="c09d3-166">>>= Operator</span></span>](../../../visual-basic/language-reference/operators/right-shift-assignment-operator.md)
- [<span data-ttu-id="c09d3-167">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="c09d3-167">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="c09d3-168">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="c09d3-168">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="c09d3-169">Visual Basic の算術演算子</span><span class="sxs-lookup"><span data-stu-id="c09d3-169">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
