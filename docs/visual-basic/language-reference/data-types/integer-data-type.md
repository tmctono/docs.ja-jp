---
title: '`Integer` データ型 (Visual Basic)'
ms.date: 01/31/2018
f1_keywords:
- vb.Integer
- Integer
helpviewer_keywords:
- numbers [Visual Basic], whole
- enumerated values [Visual Basic]
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- literal type characters [Visual Basic], I
- integers [Visual Basic], types
- data types [Visual Basic], integral
- '% identifier type character'
- data types [Visual Basic], assigning
- identifier type characters [Visual Basic], %
- I literal type character [Visual Basic]
- Integer data type
ms.assetid: a8f233b4-4be3-455c-861b-05af2fbb6c60
ms.openlocfilehash: b553471fad6411cd5aa2edf42d8424aa652e9589
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592112"
---
# <a name="integer-data-type-visual-basic"></a><span data-ttu-id="1805e-102">`Integer` データ型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1805e-102">Integer data type (Visual Basic)</span></span>
<span data-ttu-id="1805e-103">-2,147,483,648 から 2,147,483,647 までの符号付き 32 ビット (4 バイト) の整数を保持します。</span><span class="sxs-lookup"><span data-stu-id="1805e-103">Holds signed 32-bit (4-byte) integers that range in value from -2,147,483,648 through 2,147,483,647.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1805e-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="1805e-104">Remarks</span></span>
 <span data-ttu-id="1805e-105">`Integer` データ型は、32 ビットのプロセッサでパフォーマンスが最大になります。</span><span class="sxs-lookup"><span data-stu-id="1805e-105">The `Integer` data type provides optimal performance on a 32-bit processor.</span></span> <span data-ttu-id="1805e-106">他の整数型では、メモリとの間の読み込みと格納により長い時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="1805e-106">The other integral types are slower to load and store from and to memory.</span></span>  
  
 <span data-ttu-id="1805e-107">`Integer` の既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="1805e-107">The default value of `Integer` is 0.</span></span>  

## <a name="literal-assignments"></a><span data-ttu-id="1805e-108">リテラルの割り当て</span><span class="sxs-lookup"><span data-stu-id="1805e-108">Literal assignments</span></span>

<span data-ttu-id="1805e-109">宣言し、初期化を`Integer`10 進リテラル、16 進リテラル、8 進数のリテラルを割り当てることや (Visual Basic 2017 以降) バイナリ リテラルでは、変数。</span><span class="sxs-lookup"><span data-stu-id="1805e-109">You can declare and initialize an `Integer` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="1805e-110">整数リテラルが `Integer` の範囲外にある場合 (つまり、<xref:System.Int32.MinValue?displayProperty=nameWithType> より小さいか、<xref:System.Int32.MaxValue?displayProperty=nameWithType> より大きい場合)、コンパイル エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="1805e-110">If the integer literal is outside the range of `Integer` (that is, if it is less than <xref:System.Int32.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int32.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="1805e-111">次の例では、整数 90,946 を 10 進リテラル、16 進リテラル、バイナリ リテラルで表したものが、`Integer` 値に割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="1805e-111">In the following example, integers equal to 90,946 that are represented as decimal, hexadecimal, and binary literals are assigned to `Integer` values.</span></span>

[!code-vb[integer](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Int)]  

> [!NOTE]
> <span data-ttu-id="1805e-112">プレフィックスを使用する`&h`または`&H`を 16 進リテラル、プレフィックスを示すために`&b`または`&B`、バイナリ リテラル、およびプレフィックスを示すために`&o`または`&O`を 8 進数のリテラルを示すためにします。</span><span class="sxs-lookup"><span data-stu-id="1805e-112">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="1805e-113">10 進リテラルには、プレフィックスはありません。</span><span class="sxs-lookup"><span data-stu-id="1805e-113">Decimal literals have no prefix.</span></span>

<span data-ttu-id="1805e-114">Visual Basic 2017 から始めて、使用することできますも、アンダー スコア文字`_`、読みやすさを強化するために、桁区切り記号として次の例として示します。</span><span class="sxs-lookup"><span data-stu-id="1805e-114">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[integer](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#IntS)]  

<span data-ttu-id="1805e-115">Visual Basic 15.5 以降では、使用することできますもアンダー スコア文字 (`_`) プレフィックスと 16 進数、バイナリ、または 8 進数の桁の間の先頭の区切り記号として。</span><span class="sxs-lookup"><span data-stu-id="1805e-115">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="1805e-116">例:</span><span class="sxs-lookup"><span data-stu-id="1805e-116">For example:</span></span>

```vb
Dim number As Integer = &H_C305_F860
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="1805e-117">数値リテラルを含めることも、 `I` [文字入力](../../programming-guide/language-features/data-types/type-characters.md)を示すために、`Integer`データ型は、次の例を示します。</span><span class="sxs-lookup"><span data-stu-id="1805e-117">Numeric literals can also include the `I` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `Integer` data type, as the following example shows.</span></span>

```vb
Dim number = &H_035826I
```

## <a name="programming-tips"></a><span data-ttu-id="1805e-118">プログラミングのヒント</span><span class="sxs-lookup"><span data-stu-id="1805e-118">Programming tips</span></span>

- <span data-ttu-id="1805e-119">**相互運用の考慮事項。**</span><span class="sxs-lookup"><span data-stu-id="1805e-119">**Interop Considerations.**</span></span> <span data-ttu-id="1805e-120">オートメーションまたは COM オブジェクトなど、.NET Framework 用に作成されていないコンポーネントとやり取りする場合に注意している`Integer`に他の環境は別のデータ幅 (16 ビット)。</span><span class="sxs-lookup"><span data-stu-id="1805e-120">If you are interfacing with components not written for the .NET Framework, such as Automation or COM objects, remember that `Integer` has a different data width (16 bits) in other environments.</span></span> <span data-ttu-id="1805e-121">そのようなコンポーネントに 16 ビットの引数を渡す場合は、新しい Visual Basic のコードで、整数型 (`Integer`) ではなく短整数型 (`Short`) として宣言します。</span><span class="sxs-lookup"><span data-stu-id="1805e-121">If you are passing a 16-bit argument to such a component, declare it as `Short` instead of `Integer` in your new Visual Basic code.</span></span>  
  
- <span data-ttu-id="1805e-122">**拡大します。**</span><span class="sxs-lookup"><span data-stu-id="1805e-122">**Widening.**</span></span> <span data-ttu-id="1805e-123">`Integer` データ型は、`Long`、`Decimal`、`Single`、または `Double` に拡大変換されます。</span><span class="sxs-lookup"><span data-stu-id="1805e-123">The `Integer` data type widens to `Long`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="1805e-124">これは、`Integer` エラーを発生させることなく、これらの型のいずれかに <xref:System.OverflowException?displayProperty=nameWithType> を変換できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="1805e-124">This means you can convert `Integer` to any one of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="1805e-125">**型宣言文字。**</span><span class="sxs-lookup"><span data-stu-id="1805e-125">**Type Characters.**</span></span> <span data-ttu-id="1805e-126">あるリテラルにリテラルの型文字 `I` を付けると、そのリテラルは `Integer` に変換されます。</span><span class="sxs-lookup"><span data-stu-id="1805e-126">Appending the literal type character `I` to a literal forces it to the `Integer` data type.</span></span> <span data-ttu-id="1805e-127">ある識別子に識別子の型文字 `%` を付けると、その識別子は整数型 (`Integer`) に変換されます。</span><span class="sxs-lookup"><span data-stu-id="1805e-127">Appending the identifier type character `%` to any identifier forces it to `Integer`.</span></span>  
  
- <span data-ttu-id="1805e-128">**フレームワークの型。**</span><span class="sxs-lookup"><span data-stu-id="1805e-128">**Framework Type.**</span></span> <span data-ttu-id="1805e-129">.NET Framework において対応する型は、<xref:System.Int32?displayProperty=nameWithType> 構造体です。</span><span class="sxs-lookup"><span data-stu-id="1805e-129">The corresponding type in the .NET Framework is the <xref:System.Int32?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="range"></a><span data-ttu-id="1805e-130">範囲</span><span class="sxs-lookup"><span data-stu-id="1805e-130">Range</span></span>

<span data-ttu-id="1805e-131">整数型の変数をその型の範囲外の数値に設定しようとすると、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="1805e-131">If you try to set a variable of an integral type to a number outside the range for that type, an error occurs.</span></span> <span data-ttu-id="1805e-132">小数に設定しようとすると、最も近い整数値に丸められます。</span><span class="sxs-lookup"><span data-stu-id="1805e-132">If you try to set it to a fraction, the number is rounded up or down to the nearest integer value.</span></span> <span data-ttu-id="1805e-133">2 つの整数値に等しく近い場合は、最も近い偶数の整数に丸められます。</span><span class="sxs-lookup"><span data-stu-id="1805e-133">If the number is equally close to two integer values, the value is rounded to the nearest even integer.</span></span> <span data-ttu-id="1805e-134">この処理により、常に中間値を単一方向に丸めるために発生する丸め誤差が最小限に抑えられます。</span><span class="sxs-lookup"><span data-stu-id="1805e-134">This behavior minimizes rounding errors that result from consistently rounding a midpoint value in a single direction.</span></span> <span data-ttu-id="1805e-135">丸めの例を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="1805e-135">The following code shows examples of rounding.</span></span>  

```vb  
' The valid range of an Integer variable is -2147483648 through +2147483647.  
Dim k As Integer  
' The following statement causes an error because the value is too large.  
k = 2147483648  
' The following statement sets k to 6.  
k = 5.9  
' The following statement sets k to 4  
k = 4.5  
' The following statement sets k to 6  
' Note, Visual Basic uses banker’s rounding (toward nearest even number)  
k = 5.5  
```

## <a name="see-also"></a><span data-ttu-id="1805e-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="1805e-136">See also</span></span>

- <xref:System.Int32?displayProperty=nameWithType>
- [<span data-ttu-id="1805e-137">データの種類</span><span class="sxs-lookup"><span data-stu-id="1805e-137">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="1805e-138">Long データ型</span><span class="sxs-lookup"><span data-stu-id="1805e-138">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)
- [<span data-ttu-id="1805e-139">Short データ型</span><span class="sxs-lookup"><span data-stu-id="1805e-139">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [<span data-ttu-id="1805e-140">データ型変換関数</span><span class="sxs-lookup"><span data-stu-id="1805e-140">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="1805e-141">変換の概要</span><span class="sxs-lookup"><span data-stu-id="1805e-141">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="1805e-142">データ型の有効な使用方法</span><span class="sxs-lookup"><span data-stu-id="1805e-142">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
