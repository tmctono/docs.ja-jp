---
title: Boolean データ型 (Visual Basic)
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
ms.openlocfilehash: 7b64302d801a08f976de0ec969983c821f7a8471
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796995"
---
# <a name="boolean-data-type-visual-basic"></a><span data-ttu-id="93dc2-102">Boolean データ型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="93dc2-102">Boolean Data Type (Visual Basic)</span></span>
<span data-ttu-id="93dc2-103">値を保持できるのみ`True`または`False`します。</span><span class="sxs-lookup"><span data-stu-id="93dc2-103">Holds values that can be only `True` or `False`.</span></span> <span data-ttu-id="93dc2-104">キーワード`True`と`False`の 2 つの状態に対応して`Boolean`変数。</span><span class="sxs-lookup"><span data-stu-id="93dc2-104">The keywords `True` and `False` correspond to the two states of `Boolean` variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="93dc2-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="93dc2-105">Remarks</span></span>  
 <span data-ttu-id="93dc2-106">使用して、[Boolean データ型 (Visual Basic)](../../../visual-basic/language-reference/data-types/boolean-data-type.md) true または false などの 2 つの状態値が含まれてはい/いいえ、またはオン/オフにします。</span><span class="sxs-lookup"><span data-stu-id="93dc2-106">Use the [Boolean Data Type (Visual Basic)](../../../visual-basic/language-reference/data-types/boolean-data-type.md) to contain two-state values such as true/false, yes/no, or on/off.</span></span>  
  
 <span data-ttu-id="93dc2-107">`Boolean` の既定値は `False` です。</span><span class="sxs-lookup"><span data-stu-id="93dc2-107">The default value of `Boolean` is `False`.</span></span>  
  
 <span data-ttu-id="93dc2-108">`Boolean` 値は、数値として格納しないと、番号に相当する、保存された値が意図されていません。</span><span class="sxs-lookup"><span data-stu-id="93dc2-108">`Boolean` values are not stored as numbers, and the stored values are not intended to be equivalent to numbers.</span></span> <span data-ttu-id="93dc2-109">数値と等価の値に依存するコードを記述する必要がありますしない`True`と`False`します。</span><span class="sxs-lookup"><span data-stu-id="93dc2-109">You should never write code that relies on equivalent numeric values for `True` and `False`.</span></span> <span data-ttu-id="93dc2-110">使用を制限する必要があります、可能な限り`Boolean`変数を論理値に設計されています。</span><span class="sxs-lookup"><span data-stu-id="93dc2-110">Whenever possible, you should restrict usage of `Boolean` variables to the logical values for which they are designed.</span></span>  
  
## <a name="type-conversions"></a><span data-ttu-id="93dc2-111">型変換</span><span class="sxs-lookup"><span data-stu-id="93dc2-111">Type Conversions</span></span>  
 <span data-ttu-id="93dc2-112">Visual Basic でに数値データ型の値を変換するときに`Boolean`、0 になります`False`他のすべての値になると`True`します。</span><span class="sxs-lookup"><span data-stu-id="93dc2-112">When Visual Basic converts numeric data type values to `Boolean`, 0 becomes `False` and all other values become `True`.</span></span> <span data-ttu-id="93dc2-113">Visual Basic の変換と`Boolean`値、数値型を`False`が 0 になると`True`-1 になります。</span><span class="sxs-lookup"><span data-stu-id="93dc2-113">When Visual Basic converts `Boolean` values to numeric types, `False` becomes 0 and `True` becomes -1.</span></span>  
  
 <span data-ttu-id="93dc2-114">間で変換する際に`Boolean`値と、数値データ型を保持する .NET Framework の変換メソッドは常に生成しない Visual Basic の変換キーワードと同じ結果に注意してください。</span><span class="sxs-lookup"><span data-stu-id="93dc2-114">When you convert between `Boolean` values and numeric data types, keep in mind that the .NET Framework conversion methods do not always produce the same results as the Visual Basic conversion keywords.</span></span> <span data-ttu-id="93dc2-115">Visual Basic の変換には、以前のバージョンと互換性のある動作が保持されるためです。</span><span class="sxs-lookup"><span data-stu-id="93dc2-115">This is because the Visual Basic conversion retains behavior compatible with previous versions.</span></span> <span data-ttu-id="93dc2-116">詳細についてを参照してください「ブール型は変換する数値型不適切」[データ型のトラブルシューティング](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)します。</span><span class="sxs-lookup"><span data-stu-id="93dc2-116">For more information, see "Boolean Type Does Not Convert to Numeric Type Accurately" in [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="93dc2-117">プログラミングのヒント</span><span class="sxs-lookup"><span data-stu-id="93dc2-117">Programming Tips</span></span>  
  
- <span data-ttu-id="93dc2-118">**負の数。**</span><span class="sxs-lookup"><span data-stu-id="93dc2-118">**Negative Numbers.**</span></span> <span data-ttu-id="93dc2-119">`Boolean` 数値型ではないと、負の値を表すことはできません。</span><span class="sxs-lookup"><span data-stu-id="93dc2-119">`Boolean` is not a numeric type and cannot represent a negative value.</span></span> <span data-ttu-id="93dc2-120">いずれの場合も、行わないで`Boolean`数値の値を保持します。</span><span class="sxs-lookup"><span data-stu-id="93dc2-120">In any case, you should not use `Boolean` to hold numeric values.</span></span>  
  
- <span data-ttu-id="93dc2-121">**型宣言文字。**</span><span class="sxs-lookup"><span data-stu-id="93dc2-121">**Type Characters.**</span></span> <span data-ttu-id="93dc2-122">`Boolean` リテラルの型文字または識別子の型文字がありません。</span><span class="sxs-lookup"><span data-stu-id="93dc2-122">`Boolean` has no literal type character or identifier type character.</span></span>  
  
- <span data-ttu-id="93dc2-123">**フレームワークの型。**</span><span class="sxs-lookup"><span data-stu-id="93dc2-123">**Framework Type.**</span></span> <span data-ttu-id="93dc2-124">.NET Framework において対応する型は、<xref:System.Boolean?displayProperty=nameWithType> 構造体です。</span><span class="sxs-lookup"><span data-stu-id="93dc2-124">The corresponding type in the .NET Framework is the <xref:System.Boolean?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93dc2-125">例</span><span class="sxs-lookup"><span data-stu-id="93dc2-125">Example</span></span>  
 <span data-ttu-id="93dc2-126">次の例では、`runningVB`は、`Boolean`変数で、単純なはい/いいえの設定を格納します。</span><span class="sxs-lookup"><span data-stu-id="93dc2-126">In the following example, `runningVB` is a `Boolean` variable, which stores a simple yes/no setting.</span></span>  
  
```  
Dim runningVB As Boolean  
' Check to see if program is running on Visual Basic engine.  
If scriptEngine = "VB" Then  
    runningVB = True  
End If  
```  
  
## <a name="see-also"></a><span data-ttu-id="93dc2-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="93dc2-127">See also</span></span>

- <xref:System.Boolean?displayProperty=nameWithType>
- [<span data-ttu-id="93dc2-128">データの種類</span><span class="sxs-lookup"><span data-stu-id="93dc2-128">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="93dc2-129">データ型変換関数</span><span class="sxs-lookup"><span data-stu-id="93dc2-129">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="93dc2-130">変換の概要</span><span class="sxs-lookup"><span data-stu-id="93dc2-130">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="93dc2-131">データ型の有効な使用方法</span><span class="sxs-lookup"><span data-stu-id="93dc2-131">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="93dc2-132">トラブルシューティング (データ型)</span><span class="sxs-lookup"><span data-stu-id="93dc2-132">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="93dc2-133">CType 関数</span><span class="sxs-lookup"><span data-stu-id="93dc2-133">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)
