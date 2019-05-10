---
title: Long データ型 (Visual Basic)
ms.date: 01/31/2018
f1_keywords:
- vb.Long
helpviewer_keywords:
- identifier type characters [Visual Basic], &
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- '& identifier type character'
- integer numbers
- literal type characters [Visual Basic], L
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- L literal type character [Visual Basic]
- integers [Visual Basic], types
- Long keyword [Visual Basic]
- data types [Visual Basic], integral
- data types [Visual Basic], assigning
- Long data type
ms.assetid: b4770c34-1804-4f8c-b512-c10b0893e516
ms.openlocfilehash: 7b4226c83f25807e013823031820d58790bb6db2
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2019
ms.locfileid: "64912782"
---
# <a name="long-data-type-visual-basic"></a><span data-ttu-id="e28ce-102">Long データ型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e28ce-102">Long data type (Visual Basic)</span></span>

<span data-ttu-id="e28ce-103">符号付き 64 ビット (8 バイト) の整数 9,223,372,036,854,775,807-9,223,372,036,854,775,808 から値までの保持 (9.2... E + 18)。</span><span class="sxs-lookup"><span data-stu-id="e28ce-103">Holds signed 64-bit (8-byte) integers ranging in value from -9,223,372,036,854,775,808 through 9,223,372,036,854,775,807 (9.2...E+18).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e28ce-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="e28ce-104">Remarks</span></span>

 <span data-ttu-id="e28ce-105">使用して、`Long`が大きすぎてに収まるように整数値を格納するデータ型、`Integer`データ型。</span><span class="sxs-lookup"><span data-stu-id="e28ce-105">Use the `Long` data type to contain integer numbers that are too large to fit in the `Integer` data type.</span></span>  
  
 <span data-ttu-id="e28ce-106">`Long` の既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="e28ce-106">The default value of `Long` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="e28ce-107">リテラルの割り当て</span><span class="sxs-lookup"><span data-stu-id="e28ce-107">Literal assignments</span></span> 

<span data-ttu-id="e28ce-108">宣言し、初期化を`Long`10 進リテラル、16 進リテラル、8 進数のリテラルを割り当てることや (Visual Basic 2017 以降) バイナリ リテラルでは、変数。</span><span class="sxs-lookup"><span data-stu-id="e28ce-108">You can declare and initialize a `Long` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="e28ce-109">整数リテラルが `Long` の範囲外にある場合 (つまり、<xref:System.Int64.MinValue?displayProperty=nameWithType> より小さいか、<xref:System.Int64.MaxValue?displayProperty=nameWithType> より大きい場合)、コンパイル エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="e28ce-109">If the integer literal is outside the range of `Long` (that is, if it is less than <xref:System.Int64.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int64.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="e28ce-110">次の例では、整数 4,294,967,296 を 10 進リテラル、16 進リテラル、バイナリ リテラルで表したものが、`Long` 値に割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="e28ce-110">In the following example, integers equal to 4,294,967,296 that are represented as decimal, hexadecimal, and binary literals are assigned to `Long` values.</span></span>
  
[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Long)]  

> [!NOTE]
> <span data-ttu-id="e28ce-111">プレフィックスを使用する`&h`または`&H`を 16 進リテラル、プレフィックスを示すために`&b`または`&B`、バイナリ リテラル、およびプレフィックスを示すために`&o`または`&O`を 8 進数のリテラルを示すためにします。</span><span class="sxs-lookup"><span data-stu-id="e28ce-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="e28ce-112">10 進リテラルには、プレフィックスはありません。</span><span class="sxs-lookup"><span data-stu-id="e28ce-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="e28ce-113">Visual Basic 2017 から始めて、使用することできますも、アンダー スコア文字`_`、読みやすさを強化するために、桁区切り記号として次の例として示します。</span><span class="sxs-lookup"><span data-stu-id="e28ce-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

<span data-ttu-id="e28ce-114">Visual Basic 15.5 以降では、使用することできますもアンダー スコア文字 (`_`) プレフィックスと 16 進数、バイナリ、または 8 進数の桁の間の先頭の区切り記号として。</span><span class="sxs-lookup"><span data-stu-id="e28ce-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="e28ce-115">例:</span><span class="sxs-lookup"><span data-stu-id="e28ce-115">For example:</span></span>

```vb
Dim number As Long = &H_0FAC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="e28ce-116">数値リテラルを含めることも、 `L` [文字入力](../../programming-guide/language-features/data-types/type-characters.md)を示すために、`Long`データ型は、次の例を示します。</span><span class="sxs-lookup"><span data-stu-id="e28ce-116">Numeric literals can also include the `L` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `Long` data type, as the following example shows.</span></span>

```vb
Dim number = &H_0FAC_0326_1489_D68CL
```

## <a name="programming-tips"></a><span data-ttu-id="e28ce-117">プログラミングのヒント</span><span class="sxs-lookup"><span data-stu-id="e28ce-117">Programming tips</span></span>

- <span data-ttu-id="e28ce-118">**相互運用の考慮事項。**</span><span class="sxs-lookup"><span data-stu-id="e28ce-118">**Interop Considerations.**</span></span> <span data-ttu-id="e28ce-119">.NET Framework、例のオートメーションまたは COM オブジェクト用に作成されていないコンポーネントとやり取りする場合に注意している`Long`に他の環境は別のデータ幅 (32 ビット)。</span><span class="sxs-lookup"><span data-stu-id="e28ce-119">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, remember that `Long` has a different data width (32 bits) in other environments.</span></span> <span data-ttu-id="e28ce-120">このようなコンポーネントに 32 ビットの引数を渡す場合の宣言として`Integer`の代わりに`Long`で新しい Visual Basic コードです。</span><span class="sxs-lookup"><span data-stu-id="e28ce-120">If you are passing a 32-bit argument to such a component, declare it as `Integer` instead of `Long` in your new Visual Basic code.</span></span>  
  
- <span data-ttu-id="e28ce-121">**拡大します。**</span><span class="sxs-lookup"><span data-stu-id="e28ce-121">**Widening.**</span></span> <span data-ttu-id="e28ce-122">`Long`拡大変換後のデータ型`Decimal`、 `Single`、または`Double`します。</span><span class="sxs-lookup"><span data-stu-id="e28ce-122">The `Long` data type widens to `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="e28ce-123">これは、`Long` エラーを発生させることなく、これらの型のいずれかに <xref:System.OverflowException?displayProperty=nameWithType> を変換できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="e28ce-123">This means you can convert `Long` to any one of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="e28ce-124">**型宣言文字。**</span><span class="sxs-lookup"><span data-stu-id="e28ce-124">**Type Characters.**</span></span> <span data-ttu-id="e28ce-125">あるリテラルにリテラルの型文字 `L` を付けると、そのリテラルは `Long` に変換されます。</span><span class="sxs-lookup"><span data-stu-id="e28ce-125">Appending the literal type character `L` to a literal forces it to the `Long` data type.</span></span> <span data-ttu-id="e28ce-126">ある識別子に識別子の型文字 `&` を付けると、その識別子は整数型 (`Long`) に変換されます。</span><span class="sxs-lookup"><span data-stu-id="e28ce-126">Appending the identifier type character `&` to any identifier forces it to `Long`.</span></span>  
  
- <span data-ttu-id="e28ce-127">**フレームワークの型。**</span><span class="sxs-lookup"><span data-stu-id="e28ce-127">**Framework Type.**</span></span> <span data-ttu-id="e28ce-128">.NET Framework において対応する型は、<xref:System.Int64?displayProperty=nameWithType> 構造体です。</span><span class="sxs-lookup"><span data-stu-id="e28ce-128">The corresponding type in the .NET Framework is the <xref:System.Int64?displayProperty=nameWithType> structure.</span></span>  

## <a name="see-also"></a><span data-ttu-id="e28ce-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="e28ce-129">See also</span></span>

- <xref:System.Int64>
- [<span data-ttu-id="e28ce-130">データの種類</span><span class="sxs-lookup"><span data-stu-id="e28ce-130">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="e28ce-131">Integer データ型</span><span class="sxs-lookup"><span data-stu-id="e28ce-131">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [<span data-ttu-id="e28ce-132">Short データ型</span><span class="sxs-lookup"><span data-stu-id="e28ce-132">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [<span data-ttu-id="e28ce-133">データ型変換関数</span><span class="sxs-lookup"><span data-stu-id="e28ce-133">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="e28ce-134">変換の概要</span><span class="sxs-lookup"><span data-stu-id="e28ce-134">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="e28ce-135">データ型の有効な使用方法</span><span class="sxs-lookup"><span data-stu-id="e28ce-135">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
