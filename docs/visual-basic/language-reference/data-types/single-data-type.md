---
title: 単精度浮動小数点型 (Single) (Visual Basic)
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
ms.openlocfilehash: b90fdb562f9d65858ac477321a18067cc6e621a2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61971705"
---
# <a name="single-data-type-visual-basic"></a><span data-ttu-id="d88d0-102">単精度浮動小数点型 (Single) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d88d0-102">Single Data Type (Visual Basic)</span></span>
<span data-ttu-id="d88d0-103">IEEE 32 ビット (4 バイト) の単精度浮動小数点数が 3.4028235 e + 38 までの値の範囲の符号付き - 1.401298E を通じて-負の値と 1.401298E から 45-45 から 3.4028235 e + 38 までの正の値。</span><span class="sxs-lookup"><span data-stu-id="d88d0-103">Holds signed IEEE 32-bit (4-byte) single-precision floating-point numbers ranging in value from -3.4028235E+38 through -1.401298E-45 for negative values and from 1.401298E-45 through 3.4028235E+38 for positive values.</span></span> <span data-ttu-id="d88d0-104">単精度の数値では、実数の概算値を格納します。</span><span class="sxs-lookup"><span data-stu-id="d88d0-104">Single-precision numbers store an approximation of a real number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d88d0-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="d88d0-105">Remarks</span></span>  
 <span data-ttu-id="d88d0-106">使用して、`Single`データ型の完全なデータの幅を必要としない浮動小数点値を含む`Double`します。</span><span class="sxs-lookup"><span data-stu-id="d88d0-106">Use the `Single` data type to contain floating-point values that do not require the full data width of `Double`.</span></span> <span data-ttu-id="d88d0-107">場合によっては、共通言語ランタイムでをパックできる場合があります、`Single`変数、緊密に協力し、メモリ消費量を保存します。</span><span class="sxs-lookup"><span data-stu-id="d88d0-107">In some cases the common language runtime might be able to pack your `Single` variables closely together and save memory consumption.</span></span>  
  
 <span data-ttu-id="d88d0-108">`Single` の既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="d88d0-108">The default value of `Single` is 0.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="d88d0-109">プログラミングのヒント</span><span class="sxs-lookup"><span data-stu-id="d88d0-109">Programming Tips</span></span>  
  
- <span data-ttu-id="d88d0-110">**有効桁数です。**</span><span class="sxs-lookup"><span data-stu-id="d88d0-110">**Precision.**</span></span> <span data-ttu-id="d88d0-111">浮動小数点数を使用する場合が常にないことを正確に表現メモリ内に留意してください。</span><span class="sxs-lookup"><span data-stu-id="d88d0-111">When you work with floating-point numbers, keep in mind that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="d88d0-112">値の比較などの特定の操作から予期しない結果に可能性と`Mod`演算子。</span><span class="sxs-lookup"><span data-stu-id="d88d0-112">This could lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="d88d0-113">詳細については、次を参照してください。[データ型のトラブルシューティング](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)します。</span><span class="sxs-lookup"><span data-stu-id="d88d0-113">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
- <span data-ttu-id="d88d0-114">**拡大します。**</span><span class="sxs-lookup"><span data-stu-id="d88d0-114">**Widening.**</span></span> <span data-ttu-id="d88d0-115">`Single`拡大変換後のデータ型`Double`します。</span><span class="sxs-lookup"><span data-stu-id="d88d0-115">The `Single` data type widens to `Double`.</span></span> <span data-ttu-id="d88d0-116">つまり、変換できる`Single`に`Double`遭遇することがなく、<xref:System.OverflowException?displayProperty=nameWithType>エラー。</span><span class="sxs-lookup"><span data-stu-id="d88d0-116">This means you can convert `Single` to `Double` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="d88d0-117">**後続のゼロ。**</span><span class="sxs-lookup"><span data-stu-id="d88d0-117">**Trailing Zeros.**</span></span> <span data-ttu-id="d88d0-118">浮動小数点データ型には、末尾の 0 文字の任意の内部表現はありません。</span><span class="sxs-lookup"><span data-stu-id="d88d0-118">The floating-point data types do not have any internal representation of trailing 0 characters.</span></span> <span data-ttu-id="d88d0-119">たとえば、これらは区別されません 4.2000 および 4.2 します。</span><span class="sxs-lookup"><span data-stu-id="d88d0-119">For example, they do not distinguish between 4.2000 and 4.2.</span></span> <span data-ttu-id="d88d0-120">その結果、末尾の 0 文字では、表示または浮動小数点値を印刷するときに表示されません。</span><span class="sxs-lookup"><span data-stu-id="d88d0-120">Consequently, trailing 0 characters do not appear when you display or print floating-point values.</span></span>  
  
- <span data-ttu-id="d88d0-121">**型宣言文字。**</span><span class="sxs-lookup"><span data-stu-id="d88d0-121">**Type Characters.**</span></span> <span data-ttu-id="d88d0-122">あるリテラルにリテラルの型文字 `F` を付けると、そのリテラルは `Single` に変換されます。</span><span class="sxs-lookup"><span data-stu-id="d88d0-122">Appending the literal type character `F` to a literal forces it to the `Single` data type.</span></span> <span data-ttu-id="d88d0-123">ある識別子に識別子の型文字 `!` を付けると、その識別子は整数型 (`Single`) に変換されます。</span><span class="sxs-lookup"><span data-stu-id="d88d0-123">Appending the identifier type character `!` to any identifier forces it to `Single`.</span></span>  
  
- <span data-ttu-id="d88d0-124">**フレームワークの型。**</span><span class="sxs-lookup"><span data-stu-id="d88d0-124">**Framework Type.**</span></span> <span data-ttu-id="d88d0-125">.NET Framework において対応する型は、<xref:System.Single?displayProperty=nameWithType> 構造体です。</span><span class="sxs-lookup"><span data-stu-id="d88d0-125">The corresponding type in the .NET Framework is the <xref:System.Single?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d88d0-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="d88d0-126">See also</span></span>

- <xref:System.Single?displayProperty=nameWithType>
- [<span data-ttu-id="d88d0-127">データの種類</span><span class="sxs-lookup"><span data-stu-id="d88d0-127">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="d88d0-128">Decimal データ型</span><span class="sxs-lookup"><span data-stu-id="d88d0-128">Decimal Data Type</span></span>](../../../visual-basic/language-reference/data-types/decimal-data-type.md)
- [<span data-ttu-id="d88d0-129">Double 型</span><span class="sxs-lookup"><span data-stu-id="d88d0-129">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)
- [<span data-ttu-id="d88d0-130">データ型変換関数</span><span class="sxs-lookup"><span data-stu-id="d88d0-130">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="d88d0-131">変換の概要</span><span class="sxs-lookup"><span data-stu-id="d88d0-131">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="d88d0-132">データ型の有効な使用方法</span><span class="sxs-lookup"><span data-stu-id="d88d0-132">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="d88d0-133">トラブルシューティング (データ型)</span><span class="sxs-lookup"><span data-stu-id="d88d0-133">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
