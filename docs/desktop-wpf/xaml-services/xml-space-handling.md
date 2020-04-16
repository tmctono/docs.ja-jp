---
title: XAML における xml:space の処理
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], white-space processing
- xml:space attribute [XAML Services]
- white-space processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
ms.openlocfilehash: 886f906b6d1e3a10920dbf52e36bf76324c5a9f2
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432702"
---
# <a name="xmlspace-handling-in-xaml"></a><span data-ttu-id="0af06-102">XAML における xml:space の処理</span><span class="sxs-lookup"><span data-stu-id="0af06-102">xml:space Handling in XAML</span></span>

<span data-ttu-id="0af06-103">属性`xml:space`は、オブジェクト要素内の重要な空白の処理動作を宣言する XML 定義の属性です。</span><span class="sxs-lookup"><span data-stu-id="0af06-103">The `xml:space` attribute is an XML-defined attribute that declares the significant white-space processing behavior within an object element.</span></span> <span data-ttu-id="0af06-104">この動作は、宣言されている`xml:space`要素内に含まれるすべてのコンテンツ (内部テキスト) に関連し、子要素にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="0af06-104">This behavior is relevant for all content (inner text) contained within the element where `xml:space` is declared, and also scopes to child elements.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="0af06-105">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="0af06-105">XAML Attribute Usage</span></span>

```xaml
<object xml:space="preserve" />
```

 <span data-ttu-id="0af06-106">\- または</span><span class="sxs-lookup"><span data-stu-id="0af06-106">\- or -</span></span>

```xaml
<object xml:space="default" />
```

## <a name="remarks"></a><span data-ttu-id="0af06-107">解説</span><span class="sxs-lookup"><span data-stu-id="0af06-107">Remarks</span></span>

<span data-ttu-id="0af06-108">XAML の属性`xml:space`の定義には、2 つの値を含む`xml:space`XML の W3C 仕様によって "特殊な属性" として定義されたとおりに派生します。</span><span class="sxs-lookup"><span data-stu-id="0af06-108">The definition for the `xml:space` attribute in XAML including its two possible values is derived from `xml:space` as defined as a "special attribute" by W3C specifications for XML.</span></span>

<span data-ttu-id="0af06-109">属性の`xml:space`デフォルト値は リテラル値`"default"`です。</span><span class="sxs-lookup"><span data-stu-id="0af06-109">The default value of the `xml:space` attribute is the literal value `"default"`.</span></span> <span data-ttu-id="0af06-110">value`"default"`の場合、または`xml:space`まったく指定されていない場合は、[トピック「XAML での空白処理](white-space-processing.md)」で定義されているように、重要な空白の解析の動作が既定の処理になります。</span><span class="sxs-lookup"><span data-stu-id="0af06-110">For the value `"default"`, or if `xml:space` is not indicated at all, the behavior of significant white-space parsing is the default handling, as defined in the topic [White-space processing in XAML](white-space-processing.md).</span></span>

<span data-ttu-id="0af06-111">オブジェクト要素の内容内の空白を保持するには`xml:space="preserve"`、そのオブジェクト要素で指定します。</span><span class="sxs-lookup"><span data-stu-id="0af06-111">To preserve white space within object element content, specify `xml:space="preserve"` on that object element.</span></span>

<span data-ttu-id="0af06-112">ほとんどの解釈では、属性の`xml:space`効果と属性の値は、子要素にスコープされます。</span><span class="sxs-lookup"><span data-stu-id="0af06-112">Under most interpretations, the `xml:space` attribute effects and the value of the attribute are scoped to child elements.</span></span>

<span data-ttu-id="0af06-113">XAML での空白の処理の詳細については、「 XAML で[の空白の処理](white-space-processing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0af06-113">For a complete discussion of white-space processing in XAML, see [White-space processing in XAML](white-space-processing.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0af06-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="0af06-114">See also</span></span>

- [<span data-ttu-id="0af06-115">XAML での空白の処理</span><span class="sxs-lookup"><span data-stu-id="0af06-115">White-space processing in XAML</span></span>](white-space-processing.md)
- [<span data-ttu-id="0af06-116">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="0af06-116">XAML Overview (WPF)</span></span>](../fundamentals/xaml.md)
