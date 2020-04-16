---
title: '{}エスケープ シーケンス - マークアップ拡張機能'
ms.date: 03/30/2017
f1_keywords:
- '{}'
helpviewer_keywords:
- XAML [XAML Services], quotation mark (")
- '{} escape sequence [XAML Services]'
- XAML [XAML Services], {} escape sequence
- XAML [XAML Services], escape sequence
- quotation mark (") [XAML Services]
- escape sequence [XAML Services]
ms.assetid: 3ce3e2ad-a868-43f9-9c98-b29561cb146e
ms.openlocfilehash: f84243994557d76fa52d72b060a1ba35460e98b0
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432966"
---
# <a name="-escape-sequence--markup-extension"></a><span data-ttu-id="a2ecd-102">{}エスケープ シーケンス/マークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="a2ecd-102">{} Escape sequence / markup extension</span></span>

<span data-ttu-id="a2ecd-103">属性値の XAML エスケープ シーケンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="a2ecd-103">Provides the XAML escape sequence for attribute values.</span></span> <span data-ttu-id="a2ecd-104">エスケープ シーケンスを使用すると、属性内の後続の値をリテラルとして解釈できます。</span><span class="sxs-lookup"><span data-stu-id="a2ecd-104">The escape sequence allows the subsequent values in the attribute to be interpreted as a literal.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="a2ecd-105">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="a2ecd-105">XAML Attribute Usage</span></span>

```xaml
<object property="{} literalValue" .../>
```

## <a name="xaml-property-element-usage"></a><span data-ttu-id="a2ecd-106">XAML プロパティ要素の使用</span><span class="sxs-lookup"><span data-stu-id="a2ecd-106">XAML Property Element Usage</span></span>

```xaml
<object>
  <object.property>
    {} literalValue
  </object.property>
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="a2ecd-107">XAML 値</span><span class="sxs-lookup"><span data-stu-id="a2ecd-107">XAML Values</span></span>

|||
|-|-|
|<span data-ttu-id="a2ecd-108">*リテラル値*</span><span class="sxs-lookup"><span data-stu-id="a2ecd-108">*literalValue*</span></span>|<span data-ttu-id="a2ecd-109">エスケープ シーケンスの後に続くリテラル文字列。</span><span class="sxs-lookup"><span data-stu-id="a2ecd-109">The literal string that follows the escape sequence.</span></span> <span data-ttu-id="a2ecd-110">通常、この文字列には、左または右かっこ ({または }) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a2ecd-110">Typically this string contains an open or close brace ({ or }).</span></span>|

## <a name="remarks"></a><span data-ttu-id="a2ecd-111">解説</span><span class="sxs-lookup"><span data-stu-id="a2ecd-111">Remarks</span></span>

<span data-ttu-id="a2ecd-112">XAML では、{}左中かっこ ({) をリテラル文字として使用できるように、エスケープ シーケンス ( ) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="a2ecd-112">The escape sequence ({}) is used so that an open brace ({) can be used as a literal character in XAML.</span></span>

<span data-ttu-id="a2ecd-113">XAML リーダーは、通常、マークアップ拡張機能のエントリ ポイントを示すために、左中かっこ ({) を使用しますが、最初に次の文字をチェックして、右中かっこ (}) であるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="a2ecd-113">XAML readers typically use the open brace ({) to denote the entry point of a markup extension; however, they first check the next character to determine whether it is a closing brace (}).</span></span> <span data-ttu-id="a2ecd-114">2 つの中かっこ ({}) が隣接している場合にのみ、エスケープ シーケンスと見なされます。</span><span class="sxs-lookup"><span data-stu-id="a2ecd-114">Only when the two braces ({}) are adjacent, are they considered an escape sequence.</span></span>

<span data-ttu-id="a2ecd-115">エスケープ シーケンスが検出された場合、XAML リーダーは文字列の残りの部分を文字列として処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2ecd-115">If the escape sequence is encountered, the XAML reader should process the remainder of the string as a string.</span></span> <span data-ttu-id="a2ecd-116">ただし、エスケープ シーケンスが型コンバーターを持つメンバーに適用される場合、文字列は XAML ライターによって解釈されるときに型変換を受ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a2ecd-116">However, if the escape sequence is applied to a member that has a type converter, the string might undergo type conversion when it is interpreted by a XAML writer.</span></span>

<span data-ttu-id="a2ecd-117">エスケープ シーケンスはマークアップ拡張機能ではなく、クラスによってバックされるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="a2ecd-117">The escape sequence is not a markup extension and is not backed by a class.</span></span> <span data-ttu-id="a2ecd-118">ただし、これは XAML リーダー (カスタム XAML リーダーを含む) が尊重すべき規則です。</span><span class="sxs-lookup"><span data-stu-id="a2ecd-118">However, it is a convention that XAML readers (including custom XAML readers) should respect.</span></span>

<span data-ttu-id="a2ecd-119">引用符 (") は、この方法でエスケープ シーケンスとして使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="a2ecd-119">A quotation mark (") cannot be used as an escape sequence in this manner.</span></span> <span data-ttu-id="a2ecd-120">非コンテンツ プロパティのプロパティ値として引用符を設定する必要がある場合は、プロパティ要素構文を使用し、引用符をプロパティ要素内の文字列として配置するか、XML 文字エンティティを使用します。</span><span class="sxs-lookup"><span data-stu-id="a2ecd-120">If you need to set a quotation mark as a property value for a noncontent property, use property element syntax and place the quotation mark as a string inside the property element, or use an XML character entity.</span></span> <span data-ttu-id="a2ecd-121">コンテンツ プロパティの場合、引用符はコンテンツ全体にすることができます。</span><span class="sxs-lookup"><span data-stu-id="a2ecd-121">For a content property, the quotation mark can be the entire content.</span></span>

<span data-ttu-id="a2ecd-122">XAML マークアップ拡張機能{}が出現する可能性がある場所に名前空間修飾子を含める必要がある XML 型を指定する場合、エスケープ シーケンス ( ) が頻繁に必要です。</span><span class="sxs-lookup"><span data-stu-id="a2ecd-122">The escape sequence ({}) is frequently required when specifying an XML type that must include a namespace qualifier in a location where a XAML markup extension might appear.</span></span> <span data-ttu-id="a2ecd-123">この場所には、XAML 属性値の開始と、等号 (=) の直後のマークアップ拡張機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a2ecd-123">This location includes the start of a XAML attribute value, and in a markup extension immediately after an equal sign (=).</span></span> <span data-ttu-id="a2ecd-124">XAML 属性値の先頭に表示される XML 名前空間のエスケープ シーケンスを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="a2ecd-124">The following example shows escape sequences for an XML namespace that appears at the start of a XAML attribute value.</span></span>

[!code-xaml[XLINQExample#StackPanelResources](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]

## <a name="see-also"></a><span data-ttu-id="a2ecd-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="a2ecd-125">See also</span></span>

- [<span data-ttu-id="a2ecd-126">XAML の型コンバーターおよびマークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="a2ecd-126">Type Converters and Markup Extensions for XAML</span></span>](type-converters-and-markup-extensions.md)
- [<span data-ttu-id="a2ecd-127">XML 文字エンティティと XAML</span><span class="sxs-lookup"><span data-stu-id="a2ecd-127">XML Character Entities and XAML</span></span>](xml-character-entities.md)
