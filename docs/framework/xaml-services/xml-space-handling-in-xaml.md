---
title: XAML における xml:space の処理
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], white-space processing
- xml:space attribute [XAML Services]
- white-space processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
ms.openlocfilehash: 20a25b36857a7116f3599e3fbbbe4b438540f782
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2019
ms.locfileid: "58037055"
---
# <a name="xmlspace-handling-in-xaml"></a><span data-ttu-id="8929e-102">XAML における xml:space の処理</span><span class="sxs-lookup"><span data-stu-id="8929e-102">xml:space Handling in XAML</span></span>
<span data-ttu-id="8929e-103">`xml:space`属性は、オブジェクト要素内で大量の空白処理動作を宣言する XML で定義された属性。</span><span class="sxs-lookup"><span data-stu-id="8929e-103">The `xml:space` attribute is an XML-defined attribute that declares the significant white-space processing behavior within an object element.</span></span> <span data-ttu-id="8929e-104">この動作は、要素内に含まれるすべてのコンテンツ (内部テキ スト) に関連する場所`xml:space`が宣言され、スコープも子要素にします。</span><span class="sxs-lookup"><span data-stu-id="8929e-104">This behavior is relevant for all content (inner text) contained within the element where `xml:space` is declared, and also scopes to child elements.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="8929e-105">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="8929e-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object xml:space="preserve" />  
```  
  
 <span data-ttu-id="8929e-106">\- または -</span><span class="sxs-lookup"><span data-stu-id="8929e-106">\- or -</span></span>  
  
```xaml  
<object xml:space="default" />  
```  
  
## <a name="remarks"></a><span data-ttu-id="8929e-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="8929e-107">Remarks</span></span>  
 <span data-ttu-id="8929e-108">定義、`xml:space`はその 2 つの値を含む XAML 内の属性に由来`xml:space`W3C XML 仕様で「特別な属性」として定義されています。</span><span class="sxs-lookup"><span data-stu-id="8929e-108">The definition for the `xml:space` attribute in XAML including its two possible values is derived from `xml:space` as defined as a "special attribute" by W3C specifications for XML.</span></span>  
  
 <span data-ttu-id="8929e-109">既定値、`xml:space`属性は、リテラル値`"default"`します。</span><span class="sxs-lookup"><span data-stu-id="8929e-109">The default value of the `xml:space` attribute is the literal value `"default"`.</span></span> <span data-ttu-id="8929e-110">値の`"default"`、または`xml:space`が反映されていません、すべてのトピックで定義されているの重要な空白文字の解析動作が既定の処理、[空白 XAML 処理](whitespace-processing-in-xaml.md)。</span><span class="sxs-lookup"><span data-stu-id="8929e-110">For the value `"default"`, or if `xml:space` is not indicated at all, the behavior of significant white-space parsing is the default handling, as defined in the topic [White-space processing in XAML](whitespace-processing-in-xaml.md).</span></span>  
  
 <span data-ttu-id="8929e-111">オブジェクト要素のコンテンツ内の空白を保持するために次のように指定します。`xml:space="preserve"`に、そのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="8929e-111">To preserve white space within object element content, specify `xml:space="preserve"` on that object element.</span></span>  
  
 <span data-ttu-id="8929e-112">ほとんどの解釈、`xml:space`属性の効果と属性の値が子要素にスコープ設定されます。</span><span class="sxs-lookup"><span data-stu-id="8929e-112">Under most interpretations, the `xml:space` attribute effects and the value of the attribute are scoped to child elements.</span></span>  
  
 <span data-ttu-id="8929e-113">空白文字で XAML 処理の詳細については、[空白 XAML 処理](whitespace-processing-in-xaml.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8929e-113">For a complete discussion of white-space processing in XAML, see [White-space processing in XAML](whitespace-processing-in-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8929e-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="8929e-114">See also</span></span>
- [<span data-ttu-id="8929e-115">空白 XAML での処理</span><span class="sxs-lookup"><span data-stu-id="8929e-115">White-space processing in XAML</span></span>](whitespace-processing-in-xaml.md)
- [<span data-ttu-id="8929e-116">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="8929e-116">XAML Overview (WPF)</span></span>](../wpf/advanced/xaml-overview-wpf.md)
