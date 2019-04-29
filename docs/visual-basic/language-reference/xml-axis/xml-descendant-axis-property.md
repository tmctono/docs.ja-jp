---
title: XML 子孫軸プロパティ (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyDescendantsAxis
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML descendant axis property [Visual Basic]
- descendant axis property [Visual Basic]
- XML axis [Visual Basic], descendant
- XML [Visual Basic], accessing
ms.assetid: a178f85b-5d54-438f-8479-40b62af6fe76
ms.openlocfilehash: bc1dff6dc3b580079087f370212b7d3acd30e4fb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938672"
---
# <a name="xml-descendant-axis-property-visual-basic"></a><span data-ttu-id="2bd93-102">XML 子孫軸プロパティ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2bd93-102">XML Descendant Axis Property (Visual Basic)</span></span>

<span data-ttu-id="2bd93-103">次の子孫にアクセスできます。<xref:System.Xml.Linq.XElement>オブジェクト、<xref:System.Xml.Linq.XDocument>オブジェクト、コレクションの<xref:System.Xml.Linq.XElement>オブジェクト、または一連の<xref:System.Xml.Linq.XDocument>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="2bd93-103">Provides access to the descendants of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>

## <a name="syntax"></a><span data-ttu-id="2bd93-104">構文</span><span class="sxs-lookup"><span data-stu-id="2bd93-104">Syntax</span></span>

```
object...<descendant>
```

## <a name="parts"></a><span data-ttu-id="2bd93-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="2bd93-105">Parts</span></span>

<span data-ttu-id="2bd93-106">`object` 必須。</span><span class="sxs-lookup"><span data-stu-id="2bd93-106">`object` Required.</span></span> <span data-ttu-id="2bd93-107"><xref:System.Xml.Linq.XElement> オブジェクト、<xref:System.Xml.Linq.XDocument> オブジェクト、<xref:System.Xml.Linq.XElement> オブジェクトのコレクション、または <xref:System.Xml.Linq.XDocument> オブジェクトのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="2bd93-107">An <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>

<span data-ttu-id="2bd93-108">`...<` 必須。</span><span class="sxs-lookup"><span data-stu-id="2bd93-108">`...<` Required.</span></span> <span data-ttu-id="2bd93-109">子孫軸プロパティの開始を示します。</span><span class="sxs-lookup"><span data-stu-id="2bd93-109">Denotes the start of a descendant axis property.</span></span>

<span data-ttu-id="2bd93-110">`descendant` 必須。</span><span class="sxs-lookup"><span data-stu-id="2bd93-110">`descendant` Required.</span></span> <span data-ttu-id="2bd93-111">フォームにアクセスする子孫ノードの名前 [`prefix:]name`します。</span><span class="sxs-lookup"><span data-stu-id="2bd93-111">Name of the descendant nodes to access, of the form [`prefix:]name`.</span></span>

|<span data-ttu-id="2bd93-112">パーツ</span><span class="sxs-lookup"><span data-stu-id="2bd93-112">Part</span></span>|<span data-ttu-id="2bd93-113">説明</span><span class="sxs-lookup"><span data-stu-id="2bd93-113">Description</span></span>|
|----------|-----------------|
|`prefix`|<span data-ttu-id="2bd93-114">任意。</span><span class="sxs-lookup"><span data-stu-id="2bd93-114">Optional.</span></span> <span data-ttu-id="2bd93-115">子孫ノードの XML 名前空間プレフィックス。</span><span class="sxs-lookup"><span data-stu-id="2bd93-115">XML namespace prefix for the descendant node.</span></span> <span data-ttu-id="2bd93-116">使用して定義されているグローバル XML 名前空間にある必要があります、`Imports`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="2bd93-116">Must be a global XML namespace that is defined by using an `Imports` statement.</span></span>|
|`name`|<span data-ttu-id="2bd93-117">必須。</span><span class="sxs-lookup"><span data-stu-id="2bd93-117">Required.</span></span> <span data-ttu-id="2bd93-118">子孫ノードのローカル名。</span><span class="sxs-lookup"><span data-stu-id="2bd93-118">Local name of the descendant node.</span></span> <span data-ttu-id="2bd93-119">参照してください[宣言する XML 要素と属性の名前](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)します。</span><span class="sxs-lookup"><span data-stu-id="2bd93-119">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|

<span data-ttu-id="2bd93-120">`>` 必須。</span><span class="sxs-lookup"><span data-stu-id="2bd93-120">`>` Required.</span></span> <span data-ttu-id="2bd93-121">子孫軸プロパティの終了を示します。</span><span class="sxs-lookup"><span data-stu-id="2bd93-121">Denotes the end of a descendant axis property.</span></span>

## <a name="return-value"></a><span data-ttu-id="2bd93-122">戻り値</span><span class="sxs-lookup"><span data-stu-id="2bd93-122">Return Value</span></span>

<span data-ttu-id="2bd93-123"><xref:System.Xml.Linq.XElement> オブジェクトのコレクション。</span><span class="sxs-lookup"><span data-stu-id="2bd93-123">A collection of <xref:System.Xml.Linq.XElement> objects.</span></span>

## <a name="remarks"></a><span data-ttu-id="2bd93-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="2bd93-124">Remarks</span></span>

<span data-ttu-id="2bd93-125">XML 子孫軸プロパティを使用して情報を取得する子孫ノードにアクセスすることができます、<xref:System.Xml.Linq.XElement>または<xref:System.Xml.Linq.XDocument>オブジェクトのコレクションから、または<xref:System.Xml.Linq.XElement>または<xref:System.Xml.Linq.XDocument>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="2bd93-125">You can use an XML descendant axis property to access descendant nodes by name from an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object, or from a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="2bd93-126">XML を使用して、`Value`返されたコレクション内の最初の子孫ノードの値にアクセスするプロパティ。</span><span class="sxs-lookup"><span data-stu-id="2bd93-126">Use the XML `Value` property to access the value of the first descendant node in the returned collection.</span></span> <span data-ttu-id="2bd93-127">詳細については、次を参照してください。 [XML Value プロパティ](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)します。</span><span class="sxs-lookup"><span data-stu-id="2bd93-127">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>

<span data-ttu-id="2bd93-128">Visual Basic コンパイラでは、descendant 軸のプロパティへの呼び出しに変換します、<xref:System.Xml.Linq.XContainer.Descendants%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="2bd93-128">The Visual Basic compiler converts descendant axis properties into calls to the <xref:System.Xml.Linq.XContainer.Descendants%2A> method.</span></span>

## <a name="xml-namespaces"></a><span data-ttu-id="2bd93-129">XML 名前空間</span><span class="sxs-lookup"><span data-stu-id="2bd93-129">XML Namespaces</span></span>

<span data-ttu-id="2bd93-130">Descendant 軸のプロパティの名前をグローバルに宣言されている XML 名前空間のみを使用できます、`Imports`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="2bd93-130">The name in a descendant axis property can use only XML namespaces declared globally with the `Imports` statement.</span></span> <span data-ttu-id="2bd93-131">XML 要素リテラル内でローカルに宣言されている XML 名前空間は使用できません。</span><span class="sxs-lookup"><span data-stu-id="2bd93-131">It cannot use XML namespaces declared locally within XML element literals.</span></span> <span data-ttu-id="2bd93-132">詳細については、次を参照してください。 [Imports ステートメント (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)します。</span><span class="sxs-lookup"><span data-stu-id="2bd93-132">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>

## <a name="example"></a><span data-ttu-id="2bd93-133">例</span><span class="sxs-lookup"><span data-stu-id="2bd93-133">Example</span></span>

<span data-ttu-id="2bd93-134">次の例は、という名前の最初の子孫ノードの値にアクセスする方法を示しています。`name`という名前のすべての子孫ノードの値と`phone`から、`contacts`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="2bd93-134">The following example shows how to access the value of the first descendant node named `name` and the values of all descendant nodes named `phone` from the `contacts` object.</span></span>

[!code-vb[VbXMLSamples#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#25)]

<span data-ttu-id="2bd93-135">このコードを実行すると、次のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2bd93-135">This code displays the following text:</span></span>

`Name: Patrick Hines`

`Home Phone = 206-555-0144`

## <a name="example"></a><span data-ttu-id="2bd93-136">例</span><span class="sxs-lookup"><span data-stu-id="2bd93-136">Example</span></span>

<span data-ttu-id="2bd93-137">次の例では、`ns` を名前空間プレフィックスとして宣言します。</span><span class="sxs-lookup"><span data-stu-id="2bd93-137">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="2bd93-138">XML リテラルを作成し、修飾名を持つ最初の子ノードの値にアクセスする次の名前空間のプレフィックスを使用して`ns:name`します。</span><span class="sxs-lookup"><span data-stu-id="2bd93-138">It then uses the prefix of the namespace to create an XML literal and access the value of the first child node with the qualified name `ns:name`.</span></span>

[!code-vb[VbXMLSamples#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples12.vb#26)]

<span data-ttu-id="2bd93-139">このコードを実行すると、次のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2bd93-139">This code displays the following text:</span></span>

`Name: Patrick Hines`

## <a name="see-also"></a><span data-ttu-id="2bd93-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="2bd93-140">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="2bd93-141">XML 軸プロパティ</span><span class="sxs-lookup"><span data-stu-id="2bd93-141">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="2bd93-142">XML リテラル</span><span class="sxs-lookup"><span data-stu-id="2bd93-142">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="2bd93-143">Visual Basic での XML の作成</span><span class="sxs-lookup"><span data-stu-id="2bd93-143">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="2bd93-144">宣言する XML 要素と属性の名前</span><span class="sxs-lookup"><span data-stu-id="2bd93-144">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
