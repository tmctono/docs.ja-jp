---
title: 単精度浮動小数点型 (Single)
ms.date: 07/20/2015
f1_keywords:
- vb.Single
helpviewer_keywords:
- Single data type
- F literal type character [Visual Basic]
- trailing zeros
- real numbers
- literal type characters [Visual Basic], F
- trailing 0 characters [Visual Basic]
- identifier type characters [Visual Basic], !
- single-precision numbers
- '! identifier type character'
- 0 characters [Visual Basic], trailing
- data types [Visual Basic], assigning
- floating-point numbers [Visual Basic], Single data type
- numbers [Visual Basic], real
- zeros, trailing
- numbers [Visual Basic], floating point
ms.assetid: 224a2795-4cd5-496c-8f7a-a4f05a06d45d
ms.openlocfilehash: 60a688c510f6e36dca5809566b37a388429e18c7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343918"
---
# <a name="single-data-type-visual-basic"></a><span data-ttu-id="7d751-102">単精度浮動小数点型 (Single) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7d751-102">Single Data Type (Visual Basic)</span></span>

<span data-ttu-id="7d751-103">Holds signed IEEE 32-bit (4-byte) single-precision floating-point numbers ranging in value from -3.4028235E+38 through -1.401298E-45 for negative values and from 1.401298E-45 through 3.4028235E+38 for positive values.</span><span class="sxs-lookup"><span data-stu-id="7d751-103">Holds signed IEEE 32-bit (4-byte) single-precision floating-point numbers ranging in value from -3.4028235E+38 through -1.401298E-45 for negative values and from 1.401298E-45 through 3.4028235E+38 for positive values.</span></span> <span data-ttu-id="7d751-104">Single-precision numbers store an approximation of a real number.</span><span class="sxs-lookup"><span data-stu-id="7d751-104">Single-precision numbers store an approximation of a real number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d751-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="7d751-105">Remarks</span></span>  

 <span data-ttu-id="7d751-106">Use the `Single` data type to contain floating-point values that do not require the full data width of `Double`.</span><span class="sxs-lookup"><span data-stu-id="7d751-106">Use the `Single` data type to contain floating-point values that do not require the full data width of `Double`.</span></span> <span data-ttu-id="7d751-107">In some cases the common language runtime might be able to pack your `Single` variables closely together and save memory consumption.</span><span class="sxs-lookup"><span data-stu-id="7d751-107">In some cases the common language runtime might be able to pack your `Single` variables closely together and save memory consumption.</span></span>  
  
 <span data-ttu-id="7d751-108">`Single` の既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="7d751-108">The default value of `Single` is 0.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="7d751-109">プログラミングのヒント</span><span class="sxs-lookup"><span data-stu-id="7d751-109">Programming Tips</span></span>  
  
- <span data-ttu-id="7d751-110">**Precision.**</span><span class="sxs-lookup"><span data-stu-id="7d751-110">**Precision.**</span></span> <span data-ttu-id="7d751-111">When you work with floating-point numbers, keep in mind that they do not always have a precise representation in memory.</span><span class="sxs-lookup"><span data-stu-id="7d751-111">When you work with floating-point numbers, keep in mind that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="7d751-112">This could lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span><span class="sxs-lookup"><span data-stu-id="7d751-112">This could lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="7d751-113">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="7d751-113">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
- <span data-ttu-id="7d751-114">**Widening.**</span><span class="sxs-lookup"><span data-stu-id="7d751-114">**Widening.**</span></span> <span data-ttu-id="7d751-115">The `Single` data type widens to `Double`.</span><span class="sxs-lookup"><span data-stu-id="7d751-115">The `Single` data type widens to `Double`.</span></span> <span data-ttu-id="7d751-116">This means you can convert `Single` to `Double` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span><span class="sxs-lookup"><span data-stu-id="7d751-116">This means you can convert `Single` to `Double` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="7d751-117">**Trailing Zeros.**</span><span class="sxs-lookup"><span data-stu-id="7d751-117">**Trailing Zeros.**</span></span> <span data-ttu-id="7d751-118">The floating-point data types do not have any internal representation of trailing 0 characters.</span><span class="sxs-lookup"><span data-stu-id="7d751-118">The floating-point data types do not have any internal representation of trailing 0 characters.</span></span> <span data-ttu-id="7d751-119">For example, they do not distinguish between 4.2000 and 4.2.</span><span class="sxs-lookup"><span data-stu-id="7d751-119">For example, they do not distinguish between 4.2000 and 4.2.</span></span> <span data-ttu-id="7d751-120">Consequently, trailing 0 characters do not appear when you display or print floating-point values.</span><span class="sxs-lookup"><span data-stu-id="7d751-120">Consequently, trailing 0 characters do not appear when you display or print floating-point values.</span></span>  
  
- <span data-ttu-id="7d751-121">**Type Characters.**</span><span class="sxs-lookup"><span data-stu-id="7d751-121">**Type Characters.**</span></span> <span data-ttu-id="7d751-122">あるリテラルにリテラルの型文字 `F` を付けると、そのリテラルは `Single` に変換されます。</span><span class="sxs-lookup"><span data-stu-id="7d751-122">Appending the literal type character `F` to a literal forces it to the `Single` data type.</span></span> <span data-ttu-id="7d751-123">ある識別子に識別子の型文字 `!` を付けると、その識別子は整数型 (`Single`) に変換されます。</span><span class="sxs-lookup"><span data-stu-id="7d751-123">Appending the identifier type character `!` to any identifier forces it to `Single`.</span></span>  
  
- <span data-ttu-id="7d751-124">**Framework Type.**</span><span class="sxs-lookup"><span data-stu-id="7d751-124">**Framework Type.**</span></span> <span data-ttu-id="7d751-125">.NET Framework において対応する型は、<xref:System.Single?displayProperty=nameWithType> 構造体です。</span><span class="sxs-lookup"><span data-stu-id="7d751-125">The corresponding type in the .NET Framework is the <xref:System.Single?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d751-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="7d751-126">See also</span></span>

- <xref:System.Single?displayProperty=nameWithType>
- [<span data-ttu-id="7d751-127">データの種類</span><span class="sxs-lookup"><span data-stu-id="7d751-127">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="7d751-128">Decimal データ型</span><span class="sxs-lookup"><span data-stu-id="7d751-128">Decimal Data Type</span></span>](../../../visual-basic/language-reference/data-types/decimal-data-type.md)
- [<span data-ttu-id="7d751-129">Double 型</span><span class="sxs-lookup"><span data-stu-id="7d751-129">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)
- [<span data-ttu-id="7d751-130">データ型変換関数</span><span class="sxs-lookup"><span data-stu-id="7d751-130">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="7d751-131">変換の概要</span><span class="sxs-lookup"><span data-stu-id="7d751-131">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="7d751-132">データ型の有効な使用方法</span><span class="sxs-lookup"><span data-stu-id="7d751-132">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="7d751-133">トラブルシューティング (データ型)</span><span class="sxs-lookup"><span data-stu-id="7d751-133">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
