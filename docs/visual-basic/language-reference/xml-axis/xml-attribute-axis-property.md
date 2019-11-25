---
title: XML Attribute Axis Property
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyAttributeAxis
helpviewer_keywords:
- attribute axis property [Visual Basic]
- Visual Basic code, accessing XML
- XML attribute axis property [Visual Basic]
- XML axis [Visual Basic], attribute
- XML [Visual Basic], accessing
ms.assetid: 7a4777e1-0618-4de9-9510-fb9ace2bf4db
ms.openlocfilehash: 109c4b45a5e3ed4e3e4db49687df5cb127a5e0c6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352672"
---
# <a name="xml-attribute-axis-property-visual-basic"></a><span data-ttu-id="b9c0e-102">XML 属性軸プロパティ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b9c0e-102">XML Attribute Axis Property (Visual Basic)</span></span>
<span data-ttu-id="b9c0e-103">Provides access to the value of an attribute for an <xref:System.Xml.Linq.XElement> object or to the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span><span class="sxs-lookup"><span data-stu-id="b9c0e-103">Provides access to the value of an attribute for an <xref:System.Xml.Linq.XElement> object or to the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9c0e-104">構文</span><span class="sxs-lookup"><span data-stu-id="b9c0e-104">Syntax</span></span>  
  
```vb  
object.@attribute  
' -or-  
object.@<attribute>  
```  
  
## <a name="parts"></a><span data-ttu-id="b9c0e-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="b9c0e-105">Parts</span></span>  
 `object`  
 <span data-ttu-id="b9c0e-106">必須です。</span><span class="sxs-lookup"><span data-stu-id="b9c0e-106">Required.</span></span> <span data-ttu-id="b9c0e-107">An <xref:System.Xml.Linq.XElement> object or a collection of <xref:System.Xml.Linq.XElement> objects.</span><span class="sxs-lookup"><span data-stu-id="b9c0e-107">An <xref:System.Xml.Linq.XElement> object or a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="b9c0e-108">.@</span><span class="sxs-lookup"><span data-stu-id="b9c0e-108">.@</span></span>  
 <span data-ttu-id="b9c0e-109">必須です。</span><span class="sxs-lookup"><span data-stu-id="b9c0e-109">Required.</span></span> <span data-ttu-id="b9c0e-110">Denotes the start of an attribute axis property.</span><span class="sxs-lookup"><span data-stu-id="b9c0e-110">Denotes the start of an attribute axis property.</span></span>  
  
 <  
 <span data-ttu-id="b9c0e-111">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="b9c0e-111">Optional.</span></span> <span data-ttu-id="b9c0e-112">Denotes the beginning of the name of the attribute when `attribute` is not a valid identifier in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b9c0e-112">Denotes the beginning of the name of the attribute when `attribute` is not a valid identifier in Visual Basic.</span></span>  
  
 `attribute`  
 <span data-ttu-id="b9c0e-113">必須です。</span><span class="sxs-lookup"><span data-stu-id="b9c0e-113">Required.</span></span> <span data-ttu-id="b9c0e-114">Name of the attribute to access, of the form [`prefix`:]`name`.</span><span class="sxs-lookup"><span data-stu-id="b9c0e-114">Name of the attribute to access, of the form [`prefix`:]`name`.</span></span>  
  
|<span data-ttu-id="b9c0e-115">パーツ</span><span class="sxs-lookup"><span data-stu-id="b9c0e-115">Part</span></span>|<span data-ttu-id="b9c0e-116">説明</span><span class="sxs-lookup"><span data-stu-id="b9c0e-116">Description</span></span>|  
|----------|-----------------|  
|`prefix`|<span data-ttu-id="b9c0e-117">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="b9c0e-117">Optional.</span></span> <span data-ttu-id="b9c0e-118">XML namespace prefix for the attribute.</span><span class="sxs-lookup"><span data-stu-id="b9c0e-118">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="b9c0e-119">`Imports` ステートメントを使用して定義されているグローバル XML 名前空間を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9c0e-119">Must be a global XML namespace defined with an `Imports` statement.</span></span>|  
|`name`|<span data-ttu-id="b9c0e-120">必須です。</span><span class="sxs-lookup"><span data-stu-id="b9c0e-120">Required.</span></span> <span data-ttu-id="b9c0e-121">Local attribute name.</span><span class="sxs-lookup"><span data-stu-id="b9c0e-121">Local attribute name.</span></span> <span data-ttu-id="b9c0e-122">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="b9c0e-122">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
  
 \>  
 <span data-ttu-id="b9c0e-123">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="b9c0e-123">Optional.</span></span> <span data-ttu-id="b9c0e-124">Denotes the end of the name of the attribute when `attribute` is not a valid identifier in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b9c0e-124">Denotes the end of the name of the attribute when `attribute` is not a valid identifier in Visual Basic.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b9c0e-125">戻り値</span><span class="sxs-lookup"><span data-stu-id="b9c0e-125">Return Value</span></span>  
 <span data-ttu-id="b9c0e-126">A string that contains the value of `attribute`.</span><span class="sxs-lookup"><span data-stu-id="b9c0e-126">A string that contains the value of `attribute`.</span></span> <span data-ttu-id="b9c0e-127">If the attribute name does not exist, `Nothing` is returned.</span><span class="sxs-lookup"><span data-stu-id="b9c0e-127">If the attribute name does not exist, `Nothing` is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9c0e-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="b9c0e-128">Remarks</span></span>  
 <span data-ttu-id="b9c0e-129">You can use an XML attribute axis property to access the value of an attribute by name from an <xref:System.Xml.Linq.XElement> object or from the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span><span class="sxs-lookup"><span data-stu-id="b9c0e-129">You can use an XML attribute axis property to access the value of an attribute by name from an <xref:System.Xml.Linq.XElement> object or from the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="b9c0e-130">You can retrieve an attribute value by name, or add a new attribute to an element by specifying a new name preceded by the @ identifier.</span><span class="sxs-lookup"><span data-stu-id="b9c0e-130">You can retrieve an attribute value by name, or add a new attribute to an element by specifying a new name preceded by the @ identifier.</span></span>  
  
 <span data-ttu-id="b9c0e-131">When you refer to an XML attribute using the @ identifier, the attribute value is returned as a string and you do not need to explicitly specify the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span><span class="sxs-lookup"><span data-stu-id="b9c0e-131">When you refer to an XML attribute using the @ identifier, the attribute value is returned as a string and you do not need to explicitly specify the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span>  
  
 <span data-ttu-id="b9c0e-132">The naming rules for XML attributes differ from the naming rules for Visual Basic identifiers.</span><span class="sxs-lookup"><span data-stu-id="b9c0e-132">The naming rules for XML attributes differ from the naming rules for Visual Basic identifiers.</span></span> <span data-ttu-id="b9c0e-133">To access an XML attribute that has a name that is not a valid Visual Basic identifier, enclose the name in angle brackets (\< and >).</span><span class="sxs-lookup"><span data-stu-id="b9c0e-133">To access an XML attribute that has a name that is not a valid Visual Basic identifier, enclose the name in angle brackets (\< and >).</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="b9c0e-134">XML 名前空間</span><span class="sxs-lookup"><span data-stu-id="b9c0e-134">XML Namespaces</span></span>  
 <span data-ttu-id="b9c0e-135">The name in an attribute axis property can use only XML namespace prefixes declared globally by using the `Imports` statement.</span><span class="sxs-lookup"><span data-stu-id="b9c0e-135">The name in an attribute axis property can use only XML namespace prefixes declared globally by using the `Imports` statement.</span></span> <span data-ttu-id="b9c0e-136">XML 要素リテラル内でローカルに宣言されている XML 名前空間プレフィックスは使用できません。</span><span class="sxs-lookup"><span data-stu-id="b9c0e-136">It cannot use XML namespace prefixes declared locally within XML element literals.</span></span> <span data-ttu-id="b9c0e-137">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="b9c0e-137">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9c0e-138">例</span><span class="sxs-lookup"><span data-stu-id="b9c0e-138">Example</span></span>  
 <span data-ttu-id="b9c0e-139">The following example shows how to get the values of the XML attributes named `type` from a collection of XML elements that are named `phone`.</span><span class="sxs-lookup"><span data-stu-id="b9c0e-139">The following example shows how to get the values of the XML attributes named `type` from a collection of XML elements that are named `phone`.</span></span>  
  
 [!code-vb[VbXMLSamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#12)]  
  
 <span data-ttu-id="b9c0e-140">このコードを実行すると、次のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b9c0e-140">This code displays the following text:</span></span>  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## <a name="example"></a><span data-ttu-id="b9c0e-141">例</span><span class="sxs-lookup"><span data-stu-id="b9c0e-141">Example</span></span>  
 <span data-ttu-id="b9c0e-142">The following example shows how to create attributes for an XML element both declaratively, as part of the XML, and dynamically by adding an attribute to an instance of an <xref:System.Xml.Linq.XElement> object.</span><span class="sxs-lookup"><span data-stu-id="b9c0e-142">The following example shows how to create attributes for an XML element both declaratively, as part of the XML, and dynamically by adding an attribute to an instance of an <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="b9c0e-143">The `type` attribute is created declaratively and the `owner` attribute is created dynamically.</span><span class="sxs-lookup"><span data-stu-id="b9c0e-143">The `type` attribute is created declaratively and the `owner` attribute is created dynamically.</span></span>  
  
 [!code-vb[VbXMLSamples#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#44)]  
  
 <span data-ttu-id="b9c0e-144">このコードを実行すると、次のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b9c0e-144">This code displays the following text:</span></span>  
  
```xml  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## <a name="example"></a><span data-ttu-id="b9c0e-145">例</span><span class="sxs-lookup"><span data-stu-id="b9c0e-145">Example</span></span>  
 <span data-ttu-id="b9c0e-146">The following example uses the angle bracket syntax to get the value of the XML attribute named `number-type`, which is not a valid identifier in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b9c0e-146">The following example uses the angle bracket syntax to get the value of the XML attribute named `number-type`, which is not a valid identifier in Visual Basic.</span></span>  
  
 [!code-vb[VbXMLSamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#13)]  
  
 <span data-ttu-id="b9c0e-147">このコードを実行すると、次のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b9c0e-147">This code displays the following text:</span></span>  
  
 `Phone type: work`  
  
## <a name="example"></a><span data-ttu-id="b9c0e-148">例</span><span class="sxs-lookup"><span data-stu-id="b9c0e-148">Example</span></span>  
 <span data-ttu-id="b9c0e-149">次の例では、`ns` を名前空間プレフィックスとして宣言します。</span><span class="sxs-lookup"><span data-stu-id="b9c0e-149">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="b9c0e-150">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name "`ns:name`".</span><span class="sxs-lookup"><span data-stu-id="b9c0e-150">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name "`ns:name`".</span></span>  
  
 [!code-vb[VbXMLSamples#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples6.vb#14)]  
  
 <span data-ttu-id="b9c0e-151">このコードを実行すると、次のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b9c0e-151">This code displays the following text:</span></span>  
  
 `Phone type: home`  
  
## <a name="see-also"></a><span data-ttu-id="b9c0e-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="b9c0e-152">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="b9c0e-153">XML 軸プロパティ</span><span class="sxs-lookup"><span data-stu-id="b9c0e-153">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="b9c0e-154">XML リテラル</span><span class="sxs-lookup"><span data-stu-id="b9c0e-154">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="b9c0e-155">Visual Basic での XML の作成</span><span class="sxs-lookup"><span data-stu-id="b9c0e-155">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="b9c0e-156">宣言する XML 要素と属性の名前</span><span class="sxs-lookup"><span data-stu-id="b9c0e-156">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
