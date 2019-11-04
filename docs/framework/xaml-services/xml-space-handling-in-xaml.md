---
title: XAML における xml:space の処理
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], white-space processing
- xml:space attribute [XAML Services]
- white-space processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
ms.openlocfilehash: 8f860f5ee42b5c1df43c4ec2b1003408bc1c0d8e
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458791"
---
# <a name="xmlspace-handling-in-xaml"></a><span data-ttu-id="41a6e-102">XAML における xml:space の処理</span><span class="sxs-lookup"><span data-stu-id="41a6e-102">xml:space Handling in XAML</span></span>
<span data-ttu-id="41a6e-103">`xml:space` 属性は、オブジェクト要素内の有意な空白処理動作を宣言する XML 定義の属性です。</span><span class="sxs-lookup"><span data-stu-id="41a6e-103">The `xml:space` attribute is an XML-defined attribute that declares the significant white-space processing behavior within an object element.</span></span> <span data-ttu-id="41a6e-104">この動作は、`xml:space` が宣言されている要素内に含まれるすべてのコンテンツ (内部テキスト) に関連し、子要素にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="41a6e-104">This behavior is relevant for all content (inner text) contained within the element where `xml:space` is declared, and also scopes to child elements.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="41a6e-105">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="41a6e-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object xml:space="preserve" />  
```  
  
 <span data-ttu-id="41a6e-106">\- または</span><span class="sxs-lookup"><span data-stu-id="41a6e-106">\- or -</span></span>  
  
```xaml  
<object xml:space="default" />  
```  
  
## <a name="remarks"></a><span data-ttu-id="41a6e-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="41a6e-107">Remarks</span></span>  
 <span data-ttu-id="41a6e-108">XAML の `xml:space` 属性の定義 (2 つの値を含む) は、XML の W3C 仕様による "特殊な属性" として定義されている `xml:space` から派生します。</span><span class="sxs-lookup"><span data-stu-id="41a6e-108">The definition for the `xml:space` attribute in XAML including its two possible values is derived from `xml:space` as defined as a "special attribute" by W3C specifications for XML.</span></span>  
  
 <span data-ttu-id="41a6e-109">`xml:space` 属性の既定値は `"default"`リテラル値です。</span><span class="sxs-lookup"><span data-stu-id="41a6e-109">The default value of the `xml:space` attribute is the literal value `"default"`.</span></span> <span data-ttu-id="41a6e-110">`"default"`値の場合、または `xml:space` がまったく示されていない場合は、「 [XAML での空白の処理](whitespace-processing-in-xaml.md)」で定義されているように、有意な空白の解析の動作が既定の処理になります。</span><span class="sxs-lookup"><span data-stu-id="41a6e-110">For the value `"default"`, or if `xml:space` is not indicated at all, the behavior of significant white-space parsing is the default handling, as defined in the topic [White-space processing in XAML](whitespace-processing-in-xaml.md).</span></span>  
  
 <span data-ttu-id="41a6e-111">オブジェクト要素のコンテンツ内の空白を保持するには、そのオブジェクト要素の `xml:space="preserve"` を指定します。</span><span class="sxs-lookup"><span data-stu-id="41a6e-111">To preserve white space within object element content, specify `xml:space="preserve"` on that object element.</span></span>  
  
 <span data-ttu-id="41a6e-112">ほとんどの解釈では、`xml:space` 属性の効果と属性の値が子要素にスコープ設定されます。</span><span class="sxs-lookup"><span data-stu-id="41a6e-112">Under most interpretations, the `xml:space` attribute effects and the value of the attribute are scoped to child elements.</span></span>  
  
 <span data-ttu-id="41a6e-113">XAML での空白の処理の詳細については、「 [xaml での空白の処理](whitespace-processing-in-xaml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41a6e-113">For a complete discussion of white-space processing in XAML, see [White-space processing in XAML](whitespace-processing-in-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41a6e-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="41a6e-114">See also</span></span>

- [<span data-ttu-id="41a6e-115">XAML での空白の処理</span><span class="sxs-lookup"><span data-stu-id="41a6e-115">White-space processing in XAML</span></span>](whitespace-processing-in-xaml.md)
- [<span data-ttu-id="41a6e-116">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="41a6e-116">XAML Overview (WPF)</span></span>](../../desktop-wpf/fundamentals/xaml.md)
