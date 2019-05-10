---
title: 倍精度浮動小数点数型 (Double) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Double
helpviewer_keywords:
- 'identifier type characters [Visual Basic], #'
- trailing zeros
- real numbers
- trailing 0 characters [Visual Basic]
- 0 characters [Visual Basic], trailing
- literal type characters [Visual Basic], R
- data types [Visual Basic], assigning
- Double data type [Visual Basic]
- '# identifier type character'
- double-precision numbers
- floating-point numbers [Visual Basic], Double data type
- R literal type character [Visual Basic]
- zeros, trailing
- Double data type
ms.assetid: 0c5670f7-fcb1-453a-bef1-374730cd38fd
ms.openlocfilehash: 6273f6c9e71f286bdbebc3fe1953988b43de3101
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663203"
---
# <a name="double-data-type-visual-basic"></a><span data-ttu-id="55301-102">倍精度浮動小数点数型 (Double) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="55301-102">Double Data Type (Visual Basic)</span></span>
<span data-ttu-id="55301-103">-- をから IEEE の 64 ビット (8 バイト) の倍精度浮動小数点数の符号付き 4.94065645841246544E-負の値と 4.94065645841246544E から 324-324 1.79769313486231570 e + 308 ~正の値。</span><span class="sxs-lookup"><span data-stu-id="55301-103">Holds signed IEEE 64-bit (8-byte) double-precision floating-point numbers that range in value from -1.79769313486231570E+308 through -4.94065645841246544E-324 for negative values and from 4.94065645841246544E-324 through 1.79769313486231570E+308 for positive values.</span></span> <span data-ttu-id="55301-104">倍精度数値には、実数の概数が格納されます。</span><span class="sxs-lookup"><span data-stu-id="55301-104">Double-precision numbers store an approximation of a real number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55301-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="55301-105">Remarks</span></span>  
 <span data-ttu-id="55301-106">`Double`データ型最大および最小の大きさを提供しています。</span><span class="sxs-lookup"><span data-stu-id="55301-106">The `Double` data type provides the largest and smallest possible magnitudes for a number.</span></span>  
  
 <span data-ttu-id="55301-107">`Double` の既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="55301-107">The default value of `Double` is 0.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="55301-108">プログラミングのヒント</span><span class="sxs-lookup"><span data-stu-id="55301-108">Programming Tips</span></span>  
  
- <span data-ttu-id="55301-109">**有効桁数です。**</span><span class="sxs-lookup"><span data-stu-id="55301-109">**Precision.**</span></span> <span data-ttu-id="55301-110">浮動小数点数を使用するときに、常にないことを正確に表現メモリ内に注意してください。</span><span class="sxs-lookup"><span data-stu-id="55301-110">When you work with floating-point numbers, remember that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="55301-111">値の比較などの特定の操作から予期しない結果に可能性と`Mod`演算子。</span><span class="sxs-lookup"><span data-stu-id="55301-111">This could lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="55301-112">詳細については、次を参照してください。[データ型のトラブルシューティング](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)します。</span><span class="sxs-lookup"><span data-stu-id="55301-112">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
- <span data-ttu-id="55301-113">**後続のゼロ。**</span><span class="sxs-lookup"><span data-stu-id="55301-113">**Trailing Zeros.**</span></span> <span data-ttu-id="55301-114">浮動小数点データ型には、末尾のゼロの文字の任意の内部表現はありません。</span><span class="sxs-lookup"><span data-stu-id="55301-114">The floating-point data types do not have any internal representation of trailing zero characters.</span></span> <span data-ttu-id="55301-115">たとえば、これらは区別されません 4.2000 および 4.2 します。</span><span class="sxs-lookup"><span data-stu-id="55301-115">For example, they do not distinguish between 4.2000 and 4.2.</span></span> <span data-ttu-id="55301-116">その結果、末尾のゼロは表示されません表示した場合、または印刷の浮動小数点値。</span><span class="sxs-lookup"><span data-stu-id="55301-116">Consequently, trailing zero characters do not appear when you display or print floating-point values.</span></span>  
  
- <span data-ttu-id="55301-117">**型宣言文字。**</span><span class="sxs-lookup"><span data-stu-id="55301-117">**Type Characters.**</span></span> <span data-ttu-id="55301-118">あるリテラルにリテラルの型文字 `R` を付けると、そのリテラルは `Double` に変換されます。</span><span class="sxs-lookup"><span data-stu-id="55301-118">Appending the literal type character `R` to a literal forces it to the `Double` data type.</span></span> <span data-ttu-id="55301-119">たとえば、整数値が続く場合`R`に値が変更された、`Double`します。</span><span class="sxs-lookup"><span data-stu-id="55301-119">For example, if an integer value is followed by `R`, the value is changed to a `Double`.</span></span>  
  
    ```  
    ' Visual Basic expands the 4 in the statement Dim dub As Double = 4R to 4.0:  
    Dim dub As Double = 4.0R  
    ```  
  
     <span data-ttu-id="55301-120">ある識別子に識別子の型文字 `#` を付けると、その識別子は整数型 (`Double`) に変換されます。</span><span class="sxs-lookup"><span data-stu-id="55301-120">Appending the identifier type character `#` to any identifier forces it to `Double`.</span></span> <span data-ttu-id="55301-121">次の例では、変数`num`として型指定された、 `Double`:</span><span class="sxs-lookup"><span data-stu-id="55301-121">In the following example, the variable `num` is typed as a `Double`:</span></span>  
  
    ```  
    Dim num# = 3  
    ```  
  
- <span data-ttu-id="55301-122">**フレームワークの型。**</span><span class="sxs-lookup"><span data-stu-id="55301-122">**Framework Type.**</span></span> <span data-ttu-id="55301-123">.NET Framework において対応する型は、<xref:System.Double?displayProperty=nameWithType> 構造体です。</span><span class="sxs-lookup"><span data-stu-id="55301-123">The corresponding type in the .NET Framework is the <xref:System.Double?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55301-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="55301-124">See also</span></span>

- <xref:System.Double?displayProperty=nameWithType>
- [<span data-ttu-id="55301-125">データの種類</span><span class="sxs-lookup"><span data-stu-id="55301-125">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="55301-126">Decimal データ型</span><span class="sxs-lookup"><span data-stu-id="55301-126">Decimal Data Type</span></span>](../../../visual-basic/language-reference/data-types/decimal-data-type.md)
- [<span data-ttu-id="55301-127">Single データ型</span><span class="sxs-lookup"><span data-stu-id="55301-127">Single Data Type</span></span>](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [<span data-ttu-id="55301-128">データ型変換関数</span><span class="sxs-lookup"><span data-stu-id="55301-128">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="55301-129">変換の概要</span><span class="sxs-lookup"><span data-stu-id="55301-129">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="55301-130">データ型の有効な使用方法</span><span class="sxs-lookup"><span data-stu-id="55301-130">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="55301-131">トラブルシューティング (データ型)</span><span class="sxs-lookup"><span data-stu-id="55301-131">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="55301-132">型文字</span><span class="sxs-lookup"><span data-stu-id="55301-132">Type Characters</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
