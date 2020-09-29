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
ms.openlocfilehash: 00f43bc9bae6d550ed175906777ac273fc8e9a23
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873343"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="910fa-102">>> 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="910fa-102">>> Operator (Visual Basic)</span></span>

<span data-ttu-id="910fa-103">ビット パターンに対して算術右シフトを実行します。</span><span class="sxs-lookup"><span data-stu-id="910fa-103">Performs an arithmetic right shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="910fa-104">構文</span><span class="sxs-lookup"><span data-stu-id="910fa-104">Syntax</span></span>  
  
```vb  
result = pattern >> amount  
```  
  
## <a name="parts"></a><span data-ttu-id="910fa-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="910fa-105">Parts</span></span>  

 `result`  
 <span data-ttu-id="910fa-106">必須です。</span><span class="sxs-lookup"><span data-stu-id="910fa-106">Required.</span></span> <span data-ttu-id="910fa-107">整数数値。</span><span class="sxs-lookup"><span data-stu-id="910fa-107">Integral numeric value.</span></span> <span data-ttu-id="910fa-108">ビット パターンをシフトした結果。</span><span class="sxs-lookup"><span data-stu-id="910fa-108">The result of shifting the bit pattern.</span></span> <span data-ttu-id="910fa-109">データ型は `pattern` のデータ型と同じです。</span><span class="sxs-lookup"><span data-stu-id="910fa-109">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="910fa-110">必須です。</span><span class="sxs-lookup"><span data-stu-id="910fa-110">Required.</span></span> <span data-ttu-id="910fa-111">整数数値式。</span><span class="sxs-lookup"><span data-stu-id="910fa-111">Integral numeric expression.</span></span> <span data-ttu-id="910fa-112">シフトするビット パターン。</span><span class="sxs-lookup"><span data-stu-id="910fa-112">The bit pattern to be shifted.</span></span> <span data-ttu-id="910fa-113">データ型は、整数型 (`SByte`、`Byte`、`Short`、`UShort`、`Integer`、`UInteger`、`Long`、または `ULong`) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="910fa-113">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="910fa-114">必須です。</span><span class="sxs-lookup"><span data-stu-id="910fa-114">Required.</span></span> <span data-ttu-id="910fa-115">数値式。</span><span class="sxs-lookup"><span data-stu-id="910fa-115">Numeric expression.</span></span> <span data-ttu-id="910fa-116">ビット パターンをシフトするビット数。</span><span class="sxs-lookup"><span data-stu-id="910fa-116">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="910fa-117">データ型は `Integer` であるか、`Integer` に拡大変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="910fa-117">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="910fa-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="910fa-118">Remarks</span></span>  

 <span data-ttu-id="910fa-119">算術シフトは循環ではありません。つまり、結果の一方の端からシフトされたビットはもう一方の端に再入されません。</span><span class="sxs-lookup"><span data-stu-id="910fa-119">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="910fa-120">算術右シフトでは、右端のビット位置を超えてシフトされたビットは破棄され、左端 (符号) ビットは左側の空いたビット位置に伝搬されます。</span><span class="sxs-lookup"><span data-stu-id="910fa-120">In an arithmetic right shift, the bits shifted beyond the rightmost bit position are discarded, and the leftmost (sign) bit is propagated into the bit positions vacated at the left.</span></span> <span data-ttu-id="910fa-121">したがって、`pattern` に負の値がある場合、空いている位置は 1 に設定されます。それ以外の場合は 0 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="910fa-121">This means that if `pattern` has a negative value, the vacated positions are set to one; otherwise they are set to zero.</span></span>  
  
 <span data-ttu-id="910fa-122">`Byte`、`UShort`、`UInteger`、および `ULong` データ型は符号なしであるため、伝搬する符号ビットはありません。</span><span class="sxs-lookup"><span data-stu-id="910fa-122">Note that the data types `Byte`, `UShort`, `UInteger`, and `ULong` are unsigned, so there is no sign bit to propagate.</span></span> <span data-ttu-id="910fa-123">`pattern` が符号なしの型の場合、空いている位置は常に 0 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="910fa-123">If `pattern` is of any unsigned type, the vacated positions are always set to zero.</span></span>  
  
 <span data-ttu-id="910fa-124">結果で保持できるよりも多くのビットがシフトされないようにするため、Visual Basic は `pattern` のデータ型に対応するサイズ マスクを使用して `amount` の値をマスクします。</span><span class="sxs-lookup"><span data-stu-id="910fa-124">To prevent shifting by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask corresponding to the data type of `pattern`.</span></span> <span data-ttu-id="910fa-125">これらの値のバイナリ AND がシフト量に使用されます。</span><span class="sxs-lookup"><span data-stu-id="910fa-125">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="910fa-126">サイズ マスクを次に示します。</span><span class="sxs-lookup"><span data-stu-id="910fa-126">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="910fa-127">`pattern` のデータ型</span><span class="sxs-lookup"><span data-stu-id="910fa-127">Data type of `pattern`</span></span>|<span data-ttu-id="910fa-128">サイズ マスク (10 進数)</span><span class="sxs-lookup"><span data-stu-id="910fa-128">Size mask (decimal)</span></span>|<span data-ttu-id="910fa-129">サイズ マスク (16 進数)</span><span class="sxs-lookup"><span data-stu-id="910fa-129">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="910fa-130">`SByte`、`Byte`</span><span class="sxs-lookup"><span data-stu-id="910fa-130">`SByte`, `Byte`</span></span>|<span data-ttu-id="910fa-131">7</span><span class="sxs-lookup"><span data-stu-id="910fa-131">7</span></span>|<span data-ttu-id="910fa-132">&H00000007</span><span class="sxs-lookup"><span data-stu-id="910fa-132">&H00000007</span></span>|  
|<span data-ttu-id="910fa-133">`Short`、`UShort`</span><span class="sxs-lookup"><span data-stu-id="910fa-133">`Short`, `UShort`</span></span>|<span data-ttu-id="910fa-134">15</span><span class="sxs-lookup"><span data-stu-id="910fa-134">15</span></span>|<span data-ttu-id="910fa-135">&H0000000F</span><span class="sxs-lookup"><span data-stu-id="910fa-135">&H0000000F</span></span>|  
|<span data-ttu-id="910fa-136">`Integer`、`UInteger`</span><span class="sxs-lookup"><span data-stu-id="910fa-136">`Integer`, `UInteger`</span></span>|<span data-ttu-id="910fa-137">31</span><span class="sxs-lookup"><span data-stu-id="910fa-137">31</span></span>|<span data-ttu-id="910fa-138">&H0000001F</span><span class="sxs-lookup"><span data-stu-id="910fa-138">&H0000001F</span></span>|  
|<span data-ttu-id="910fa-139">`Long`、`ULong`</span><span class="sxs-lookup"><span data-stu-id="910fa-139">`Long`, `ULong`</span></span>|<span data-ttu-id="910fa-140">63</span><span class="sxs-lookup"><span data-stu-id="910fa-140">63</span></span>|<span data-ttu-id="910fa-141">&H0000003F</span><span class="sxs-lookup"><span data-stu-id="910fa-141">&H0000003F</span></span>|  
  
 <span data-ttu-id="910fa-142">`amount` が 0 の場合、`result` の値は `pattern` の値と同じになります。</span><span class="sxs-lookup"><span data-stu-id="910fa-142">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="910fa-143">`amount` が負の場合は、符号なしの値として扱われ、適切なサイズ マスクでマスクされます。</span><span class="sxs-lookup"><span data-stu-id="910fa-143">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="910fa-144">算術シフトではオーバーフロー例外は生成されません。</span><span class="sxs-lookup"><span data-stu-id="910fa-144">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="910fa-145">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="910fa-145">Overloading</span></span>  

 <span data-ttu-id="910fa-146">`>>` 演算子は "*オーバーロード*" できます。つまり、オペランドがクラスまたは構造体の型を持っているときに、クラスまたは構造体はその動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="910fa-146">The `>>` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="910fa-147">コードで、そのようなクラスまたは構造体に対してこの演算子が使用される場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="910fa-147">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="910fa-148">詳細については、「 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="910fa-148">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="910fa-149">例</span><span class="sxs-lookup"><span data-stu-id="910fa-149">Example</span></span>  

 <span data-ttu-id="910fa-150">次の例では、`>>` 演算子を使用して、整数値に対して算術右シフトを実行しています。</span><span class="sxs-lookup"><span data-stu-id="910fa-150">The following example uses the `>>` operator to perform arithmetic right shifts on integral values.</span></span> <span data-ttu-id="910fa-151">結果のデータ型は、シフトする式のデータ型と常に同じになります。</span><span class="sxs-lookup"><span data-stu-id="910fa-151">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#14)]  
  
 <span data-ttu-id="910fa-152">前の例の結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="910fa-152">The results of the preceding example are as follows:</span></span>  
  
- <span data-ttu-id="910fa-153">`result1` は 2560 (0000 1010 0000 0000) です。</span><span class="sxs-lookup"><span data-stu-id="910fa-153">`result1` is 2560 (0000 1010 0000 0000).</span></span>  
  
- <span data-ttu-id="910fa-154">`result2` は 160 (0000 0000 1010 0000) です。</span><span class="sxs-lookup"><span data-stu-id="910fa-154">`result2` is 160 (0000 0000 1010 0000).</span></span>  
  
- <span data-ttu-id="910fa-155">`result3` は 2 (0000 0000 0000 0010) です。</span><span class="sxs-lookup"><span data-stu-id="910fa-155">`result3` is 2 (0000 0000 0000 0010).</span></span>  
  
- <span data-ttu-id="910fa-156">`result4` は 640 (0000 0010 1000 0000) です。</span><span class="sxs-lookup"><span data-stu-id="910fa-156">`result4` is 640 (0000 0010 1000 0000).</span></span>  
  
- <span data-ttu-id="910fa-157">`result5` は 0 (右に 15 桁シフト)。</span><span class="sxs-lookup"><span data-stu-id="910fa-157">`result5` is 0 (shifted 15 places to the right).</span></span>  
  
 <span data-ttu-id="910fa-158">`result4` のシフト量は 18 AND 15 として計算されます。これは 2 と同等です。</span><span class="sxs-lookup"><span data-stu-id="910fa-158">The shift amount for `result4` is calculated as 18 AND 15, which equals 2.</span></span>  
  
 <span data-ttu-id="910fa-159">次の例は、負の値に対する算術シフトを示しています。</span><span class="sxs-lookup"><span data-stu-id="910fa-159">The following example shows arithmetic shifts on a negative value.</span></span>  
  
 [!code-vb[VbVbalrOperators#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#55)]  
  
 <span data-ttu-id="910fa-160">前の例の結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="910fa-160">The results of the preceding example are as follows:</span></span>  
  
- <span data-ttu-id="910fa-161">`negresult1` は -512 (1111 1110 0000 0000) です。</span><span class="sxs-lookup"><span data-stu-id="910fa-161">`negresult1` is -512 (1111 1110 0000 0000).</span></span>  
  
- <span data-ttu-id="910fa-162">`negresult2` は -1 です (符号ビットが伝播されます)。</span><span class="sxs-lookup"><span data-stu-id="910fa-162">`negresult2` is -1 (the sign bit is propagated).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="910fa-163">関連項目</span><span class="sxs-lookup"><span data-stu-id="910fa-163">See also</span></span>

- [<span data-ttu-id="910fa-164">ビット シフト演算子</span><span class="sxs-lookup"><span data-stu-id="910fa-164">Bit Shift Operators</span></span>](bit-shift-operators.md)
- [<span data-ttu-id="910fa-165">代入演算子</span><span class="sxs-lookup"><span data-stu-id="910fa-165">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="910fa-166">>>= 演算子</span><span class="sxs-lookup"><span data-stu-id="910fa-166">>>= Operator</span></span>](right-shift-assignment-operator.md)
- [<span data-ttu-id="910fa-167">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="910fa-167">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="910fa-168">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="910fa-168">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="910fa-169">Visual Basic における算術演算子</span><span class="sxs-lookup"><span data-stu-id="910fa-169">Arithmetic Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
