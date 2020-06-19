---
title: << 演算子
ms.date: 07/20/2015
f1_keywords:
- vb.<<
helpviewer_keywords:
- bit shift operators [Visual Basic]
- << operator [Visual Basic]
- operator <<, Visual Basic left shift operator
ms.assetid: fdb93d25-81ba-417f-b808-41207bfb8440
ms.openlocfilehash: 327d0e5cbd1ebcc43bd47fb068f4513940c2165a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350982"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="29994-102">\<\< 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="29994-102">\<\< Operator (Visual Basic)</span></span>
<span data-ttu-id="29994-103">ビット パターンに対して算術左シフトを実行します。</span><span class="sxs-lookup"><span data-stu-id="29994-103">Performs an arithmetic left shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29994-104">構文</span><span class="sxs-lookup"><span data-stu-id="29994-104">Syntax</span></span>  
  
```vb  
result = pattern << amount  
```  
  
## <a name="parts"></a><span data-ttu-id="29994-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="29994-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="29994-106">必須です。</span><span class="sxs-lookup"><span data-stu-id="29994-106">Required.</span></span> <span data-ttu-id="29994-107">整数数値。</span><span class="sxs-lookup"><span data-stu-id="29994-107">Integral numeric value.</span></span> <span data-ttu-id="29994-108">ビット パターンをシフトした結果。</span><span class="sxs-lookup"><span data-stu-id="29994-108">The result of shifting the bit pattern.</span></span> <span data-ttu-id="29994-109">データ型は `pattern` のデータ型と同じです。</span><span class="sxs-lookup"><span data-stu-id="29994-109">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="29994-110">必須です。</span><span class="sxs-lookup"><span data-stu-id="29994-110">Required.</span></span> <span data-ttu-id="29994-111">整数数値式。</span><span class="sxs-lookup"><span data-stu-id="29994-111">Integral numeric expression.</span></span> <span data-ttu-id="29994-112">シフトするビット パターン。</span><span class="sxs-lookup"><span data-stu-id="29994-112">The bit pattern to be shifted.</span></span> <span data-ttu-id="29994-113">データ型は、整数型 (`SByte`、`Byte`、`Short`、`UShort`、`Integer`、`UInteger`、`Long`、または `ULong`) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="29994-113">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="29994-114">必須です。</span><span class="sxs-lookup"><span data-stu-id="29994-114">Required.</span></span> <span data-ttu-id="29994-115">数値式。</span><span class="sxs-lookup"><span data-stu-id="29994-115">Numeric expression.</span></span> <span data-ttu-id="29994-116">ビット パターンをシフトするビット数。</span><span class="sxs-lookup"><span data-stu-id="29994-116">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="29994-117">データ型は `Integer` であるか、`Integer` に拡大変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29994-117">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="29994-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="29994-118">Remarks</span></span>  
 <span data-ttu-id="29994-119">算術シフトは循環ではありません。つまり、結果の一方の端からシフトされたビットはもう一方の端には再入されません。</span><span class="sxs-lookup"><span data-stu-id="29994-119">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="29994-120">算術左シフトでは、結果のデータ型の範囲を超えてシフトされたビットは破棄され、右側に空いたビット位置は 0 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="29994-120">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span></span>  
  
 <span data-ttu-id="29994-121">結果で保持できるよりも多くのビットがシフトされないようにするため、Visual Basic は `pattern` のデータ型に対応するサイズ マスクを使用して `amount` の値をマスクします。</span><span class="sxs-lookup"><span data-stu-id="29994-121">To prevent a shift by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask that corresponds to the data type of `pattern`.</span></span> <span data-ttu-id="29994-122">これらの値のバイナリ AND がシフト量に使用されます。</span><span class="sxs-lookup"><span data-stu-id="29994-122">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="29994-123">サイズ マスクを次に示します。</span><span class="sxs-lookup"><span data-stu-id="29994-123">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="29994-124">`pattern` のデータ型</span><span class="sxs-lookup"><span data-stu-id="29994-124">Data type of `pattern`</span></span>|<span data-ttu-id="29994-125">サイズ マスク (10 進数)</span><span class="sxs-lookup"><span data-stu-id="29994-125">Size mask (decimal)</span></span>|<span data-ttu-id="29994-126">サイズ マスク (16 進数)</span><span class="sxs-lookup"><span data-stu-id="29994-126">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="29994-127">`SByte`、`Byte`</span><span class="sxs-lookup"><span data-stu-id="29994-127">`SByte`, `Byte`</span></span>|<span data-ttu-id="29994-128">7</span><span class="sxs-lookup"><span data-stu-id="29994-128">7</span></span>|<span data-ttu-id="29994-129">&H00000007</span><span class="sxs-lookup"><span data-stu-id="29994-129">&H00000007</span></span>|  
|<span data-ttu-id="29994-130">`Short`、`UShort`</span><span class="sxs-lookup"><span data-stu-id="29994-130">`Short`, `UShort`</span></span>|<span data-ttu-id="29994-131">15</span><span class="sxs-lookup"><span data-stu-id="29994-131">15</span></span>|<span data-ttu-id="29994-132">&H0000000F</span><span class="sxs-lookup"><span data-stu-id="29994-132">&H0000000F</span></span>|  
|<span data-ttu-id="29994-133">`Integer`、`UInteger`</span><span class="sxs-lookup"><span data-stu-id="29994-133">`Integer`, `UInteger`</span></span>|<span data-ttu-id="29994-134">31</span><span class="sxs-lookup"><span data-stu-id="29994-134">31</span></span>|<span data-ttu-id="29994-135">&H0000001F</span><span class="sxs-lookup"><span data-stu-id="29994-135">&H0000001F</span></span>|  
|<span data-ttu-id="29994-136">`Long`、`ULong`</span><span class="sxs-lookup"><span data-stu-id="29994-136">`Long`, `ULong`</span></span>|<span data-ttu-id="29994-137">63</span><span class="sxs-lookup"><span data-stu-id="29994-137">63</span></span>|<span data-ttu-id="29994-138">&H0000003F</span><span class="sxs-lookup"><span data-stu-id="29994-138">&H0000003F</span></span>|  
  
 <span data-ttu-id="29994-139">`amount` が 0 の場合、`result` の値は `pattern` の値と同じになります。</span><span class="sxs-lookup"><span data-stu-id="29994-139">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="29994-140">`amount` が負の場合は、符号なしの値として取得され、適切なサイズ マスクでマスクされます。</span><span class="sxs-lookup"><span data-stu-id="29994-140">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="29994-141">算術シフトではオーバーフロー例外は発生しません。</span><span class="sxs-lookup"><span data-stu-id="29994-141">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="29994-142">`<<` 演算子は "*オーバーロード*" できます。つまり、オペランドがクラスまたは構造体の型を持っているときに、クラスまたは構造体はその動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="29994-142">The `<<` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="29994-143">コードで、そのようなクラスまたは構造体に対してこの演算子を使用する場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="29994-143">If your code uses this operator on such a class or structure, be sure that you understand its redefined behavior.</span></span> <span data-ttu-id="29994-144">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29994-144">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="29994-145">例</span><span class="sxs-lookup"><span data-stu-id="29994-145">Example</span></span>  
 <span data-ttu-id="29994-146">次の例では、`<<` 演算子を使用して、整数値に対して算術左シフトを実行しています。</span><span class="sxs-lookup"><span data-stu-id="29994-146">The following example uses the `<<` operator to perform arithmetic left shifts on integral values.</span></span> <span data-ttu-id="29994-147">結果のデータ型は、シフトする式のデータ型と常に同じになります。</span><span class="sxs-lookup"><span data-stu-id="29994-147">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#12)]  
  
 <span data-ttu-id="29994-148">前の例の結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="29994-148">The results of the previous example are as follows:</span></span>  
  
- <span data-ttu-id="29994-149">`result1` は 192 (0000 0000 1100 0000) です。</span><span class="sxs-lookup"><span data-stu-id="29994-149">`result1` is 192 (0000 0000 1100 0000).</span></span>  
  
- <span data-ttu-id="29994-150">`result2` は 3072 (0000 1100 0000 0000) です。</span><span class="sxs-lookup"><span data-stu-id="29994-150">`result2` is 3072 (0000 1100 0000 0000).</span></span>  
  
- <span data-ttu-id="29994-151">`result3` は -32768 (1000 0000 0000 0000) です。</span><span class="sxs-lookup"><span data-stu-id="29994-151">`result3` is -32768 (1000 0000 0000 0000).</span></span>  
  
- <span data-ttu-id="29994-152">`result4` は 384 (0000 0001 1000 0000) です。</span><span class="sxs-lookup"><span data-stu-id="29994-152">`result4` is 384 (0000 0001 1000 0000).</span></span>  
  
- <span data-ttu-id="29994-153">`result5` は 0 (左に 15 シフト) です。</span><span class="sxs-lookup"><span data-stu-id="29994-153">`result5` is 0 (shifted 15 places to the left).</span></span>  
  
 <span data-ttu-id="29994-154">`result4` のシフト量は 17 AND 15 として計算されます。これは 1 と同等です。</span><span class="sxs-lookup"><span data-stu-id="29994-154">The shift amount for `result4` is calculated as 17 AND 15, which equals 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29994-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="29994-155">See also</span></span>

- [<span data-ttu-id="29994-156">ビット シフト演算子</span><span class="sxs-lookup"><span data-stu-id="29994-156">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="29994-157">代入演算子</span><span class="sxs-lookup"><span data-stu-id="29994-157">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="29994-158"><<= 演算子</span><span class="sxs-lookup"><span data-stu-id="29994-158"><<= Operator</span></span>](../../../visual-basic/language-reference/operators/left-shift-assignment-operator.md)
- [<span data-ttu-id="29994-159">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="29994-159">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="29994-160">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="29994-160">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="29994-161">Visual Basic における算術演算子</span><span class="sxs-lookup"><span data-stu-id="29994-161">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
