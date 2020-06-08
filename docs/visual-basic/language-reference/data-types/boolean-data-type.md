---
title: Boolean データ型
ms.date: 07/20/2015
f1_keywords:
- vb.FALSE
- vb.TRUE
- vb.Boolean
helpviewer_keywords:
- Boolean data type
- Boolean values [Visual Basic], False keyword
- False keyword [Visual Basic]
- True keyword [Visual Basic]
- Boolean values [Visual Basic], True keyword
ms.assetid: 4858e630-4813-4216-a55e-f4d0feb884e4
ms.openlocfilehash: 851c524a83c5f24b77a151634a96798249c5905e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84374422"
---
# <a name="boolean-data-type-visual-basic"></a><span data-ttu-id="09bc8-102">ブール型 (Boolean) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="09bc8-102">Boolean Data Type (Visual Basic)</span></span>

<span data-ttu-id="09bc8-103">`True` または `False` のみ可能な値を保持します。</span><span class="sxs-lookup"><span data-stu-id="09bc8-103">Holds values that can be only `True` or `False`.</span></span> <span data-ttu-id="09bc8-104">キーワード `True` と `False` は `Boolean` 変数の 2 つの状態に対応しています。</span><span class="sxs-lookup"><span data-stu-id="09bc8-104">The keywords `True` and `False` correspond to the two states of `Boolean` variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="09bc8-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="09bc8-105">Remarks</span></span>  

 <span data-ttu-id="09bc8-106">[ブール データ型 (Visual Basic)](boolean-data-type.md) を使用して、true/false、yes/no、on/off などの 2 つの状態の値を格納します。</span><span class="sxs-lookup"><span data-stu-id="09bc8-106">Use the [Boolean Data Type (Visual Basic)](boolean-data-type.md) to contain two-state values such as true/false, yes/no, or on/off.</span></span>  
  
 <span data-ttu-id="09bc8-107">`Boolean` の既定値は `False`です。</span><span class="sxs-lookup"><span data-stu-id="09bc8-107">The default value of `Boolean` is `False`.</span></span>  
  
 <span data-ttu-id="09bc8-108">`Boolean` 値は数値として格納されず、格納された値は数値と等価であると見なされません。</span><span class="sxs-lookup"><span data-stu-id="09bc8-108">`Boolean` values are not stored as numbers, and the stored values are not intended to be equivalent to numbers.</span></span> <span data-ttu-id="09bc8-109">`True` と `False` に対して等価の数値に依存するコードを記述することは避けてください。</span><span class="sxs-lookup"><span data-stu-id="09bc8-109">You should never write code that relies on equivalent numeric values for `True` and `False`.</span></span> <span data-ttu-id="09bc8-110">可能な限り、`Boolean` 変数には、仕様で定められている論理値以外の値を使用しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="09bc8-110">Whenever possible, you should restrict usage of `Boolean` variables to the logical values for which they are designed.</span></span>  
  
## <a name="type-conversions"></a><span data-ttu-id="09bc8-111">型変換</span><span class="sxs-lookup"><span data-stu-id="09bc8-111">Type Conversions</span></span>  

 <span data-ttu-id="09bc8-112">Visual Basic で数値データ型の値を `Boolean` に変換すると、0 は `False` になり、その他のすべての値は `True` になります。</span><span class="sxs-lookup"><span data-stu-id="09bc8-112">When Visual Basic converts numeric data type values to `Boolean`, 0 becomes `False` and all other values become `True`.</span></span> <span data-ttu-id="09bc8-113">Visual Basic で `Boolean` 値を数値型に変換すると、`False` は 0 になり、`True` は -1 になります。</span><span class="sxs-lookup"><span data-stu-id="09bc8-113">When Visual Basic converts `Boolean` values to numeric types, `False` becomes 0 and `True` becomes -1.</span></span>  
  
 <span data-ttu-id="09bc8-114">`Boolean` 値と数値データ型の間で変換を行う場合、.NET Framework の変換メソッドでは、必ずしも Visual Basic の変換キーワードと同じ結果が生成されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="09bc8-114">When you convert between `Boolean` values and numeric data types, keep in mind that the .NET Framework conversion methods do not always produce the same results as the Visual Basic conversion keywords.</span></span> <span data-ttu-id="09bc8-115">これは、Visual Basic の変換では、以前のバージョンと互換性のある動作が保持されているためです。</span><span class="sxs-lookup"><span data-stu-id="09bc8-115">This is because the Visual Basic conversion retains behavior compatible with previous versions.</span></span> <span data-ttu-id="09bc8-116">詳細については、「[データ型のトラブルシューティング](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)」の「Boolean Type Does Not Convert to Numeric Type Accurately」(ブール型で数値型に正確に変換されない) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09bc8-116">For more information, see "Boolean Type Does Not Convert to Numeric Type Accurately" in [Troubleshooting Data Types](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="09bc8-117">プログラミングのヒント</span><span class="sxs-lookup"><span data-stu-id="09bc8-117">Programming Tips</span></span>  
  
- <span data-ttu-id="09bc8-118">**負の数値。**</span><span class="sxs-lookup"><span data-stu-id="09bc8-118">**Negative Numbers.**</span></span> <span data-ttu-id="09bc8-119">`Boolean` は数値型ではなく、負の値を表すことはできません。</span><span class="sxs-lookup"><span data-stu-id="09bc8-119">`Boolean` is not a numeric type and cannot represent a negative value.</span></span> <span data-ttu-id="09bc8-120">いかなる場合でも、`Boolean` を使用して数値を保持しないでください。</span><span class="sxs-lookup"><span data-stu-id="09bc8-120">In any case, you should not use `Boolean` to hold numeric values.</span></span>  
  
- <span data-ttu-id="09bc8-121">**型文字。**</span><span class="sxs-lookup"><span data-stu-id="09bc8-121">**Type Characters.**</span></span> <span data-ttu-id="09bc8-122">`Boolean` には、リテラルの型文字も識別子の型文字も含まれません。</span><span class="sxs-lookup"><span data-stu-id="09bc8-122">`Boolean` has no literal type character or identifier type character.</span></span>  
  
- <span data-ttu-id="09bc8-123">**Framework の型。**</span><span class="sxs-lookup"><span data-stu-id="09bc8-123">**Framework Type.**</span></span> <span data-ttu-id="09bc8-124">.NET Framework において対応する型は、<xref:System.Boolean?displayProperty=nameWithType> 構造体です。</span><span class="sxs-lookup"><span data-stu-id="09bc8-124">The corresponding type in the .NET Framework is the <xref:System.Boolean?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09bc8-125">例</span><span class="sxs-lookup"><span data-stu-id="09bc8-125">Example</span></span>  

 <span data-ttu-id="09bc8-126">次の例で、`runningVB` は、シンプルな yes/no 設定を格納する `Boolean` 変数です。</span><span class="sxs-lookup"><span data-stu-id="09bc8-126">In the following example, `runningVB` is a `Boolean` variable, which stores a simple yes/no setting.</span></span>  
  
```vb  
Dim runningVB As Boolean  
' Check to see if program is running on Visual Basic engine.  
If scriptEngine = "VB" Then  
    runningVB = True  
End If  
```  
  
## <a name="see-also"></a><span data-ttu-id="09bc8-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="09bc8-127">See also</span></span>

- <xref:System.Boolean?displayProperty=nameWithType>
- [<span data-ttu-id="09bc8-128">データの種類</span><span class="sxs-lookup"><span data-stu-id="09bc8-128">Data Types</span></span>](index.md)
- [<span data-ttu-id="09bc8-129">データ型変換関数</span><span class="sxs-lookup"><span data-stu-id="09bc8-129">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="09bc8-130">変換の概要</span><span class="sxs-lookup"><span data-stu-id="09bc8-130">Conversion Summary</span></span>](../keywords/conversion-summary.md)
- [<span data-ttu-id="09bc8-131">データ型の有効な使用方法</span><span class="sxs-lookup"><span data-stu-id="09bc8-131">Efficient Use of Data Types</span></span>](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="09bc8-132">トラブルシューティング (データ型)</span><span class="sxs-lookup"><span data-stu-id="09bc8-132">Troubleshooting Data Types</span></span>](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="09bc8-133">CType 関数</span><span class="sxs-lookup"><span data-stu-id="09bc8-133">CType Function</span></span>](../functions/ctype-function.md)
