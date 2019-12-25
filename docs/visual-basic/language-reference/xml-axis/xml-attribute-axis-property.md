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
# <a name="xml-attribute-axis-property-visual-basic"></a><span data-ttu-id="0c1a5-102">XML 属性軸プロパティ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c1a5-102">XML Attribute Axis Property (Visual Basic)</span></span>
<span data-ttu-id="0c1a5-103"><xref:System.Xml.Linq.XElement> オブジェクトの属性値、または <xref:System.Xml.Linq.XElement> オブジェクトのコレクション内の最初の要素へのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="0c1a5-103">Provides access to the value of an attribute for an <xref:System.Xml.Linq.XElement> object or to the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c1a5-104">構文</span><span class="sxs-lookup"><span data-stu-id="0c1a5-104">Syntax</span></span>  
  
```vb  
object.@attribute  
' -or-  
object.@<attribute>  
```  
  
## <a name="parts"></a><span data-ttu-id="0c1a5-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="0c1a5-105">Parts</span></span>  
 `object`  
 <span data-ttu-id="0c1a5-106">必須。</span><span class="sxs-lookup"><span data-stu-id="0c1a5-106">Required.</span></span> <span data-ttu-id="0c1a5-107"><xref:System.Xml.Linq.XElement> オブジェクトまたは <xref:System.Xml.Linq.XElement> オブジェクトのコレクション。</span><span class="sxs-lookup"><span data-stu-id="0c1a5-107">An <xref:System.Xml.Linq.XElement> object or a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="0c1a5-108">.@</span><span class="sxs-lookup"><span data-stu-id="0c1a5-108">.@</span></span>  
 <span data-ttu-id="0c1a5-109">必須。</span><span class="sxs-lookup"><span data-stu-id="0c1a5-109">Required.</span></span> <span data-ttu-id="0c1a5-110">属性軸プロパティの開始を示します。</span><span class="sxs-lookup"><span data-stu-id="0c1a5-110">Denotes the start of an attribute axis property.</span></span>  
  
 <  
 <span data-ttu-id="0c1a5-111">省略可。</span><span class="sxs-lookup"><span data-stu-id="0c1a5-111">Optional.</span></span> <span data-ttu-id="0c1a5-112">`attribute` が Visual Basic の有効な識別子ではない場合に、属性の名前の先頭を示します。</span><span class="sxs-lookup"><span data-stu-id="0c1a5-112">Denotes the beginning of the name of the attribute when `attribute` is not a valid identifier in Visual Basic.</span></span>  
  
 `attribute`  
 <span data-ttu-id="0c1a5-113">必須。</span><span class="sxs-lookup"><span data-stu-id="0c1a5-113">Required.</span></span> <span data-ttu-id="0c1a5-114">アクセスする属性の名前。 [`prefix`:]`name`の形式で指定します。</span><span class="sxs-lookup"><span data-stu-id="0c1a5-114">Name of the attribute to access, of the form [`prefix`:]`name`.</span></span>  
  
|<span data-ttu-id="0c1a5-115">要素</span><span class="sxs-lookup"><span data-stu-id="0c1a5-115">Part</span></span>|<span data-ttu-id="0c1a5-116">説明</span><span class="sxs-lookup"><span data-stu-id="0c1a5-116">Description</span></span>|  
|----------|-----------------|  
|`prefix`|<span data-ttu-id="0c1a5-117">省略可。</span><span class="sxs-lookup"><span data-stu-id="0c1a5-117">Optional.</span></span> <span data-ttu-id="0c1a5-118">属性の XML 名前空間プレフィックス。</span><span class="sxs-lookup"><span data-stu-id="0c1a5-118">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="0c1a5-119">`Imports` ステートメントを使用して定義されているグローバル XML 名前空間を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c1a5-119">Must be a global XML namespace defined with an `Imports` statement.</span></span>|  
|`name`|<span data-ttu-id="0c1a5-120">必須。</span><span class="sxs-lookup"><span data-stu-id="0c1a5-120">Required.</span></span> <span data-ttu-id="0c1a5-121">ローカル属性名。</span><span class="sxs-lookup"><span data-stu-id="0c1a5-121">Local attribute name.</span></span> <span data-ttu-id="0c1a5-122">「[宣言された XML 要素と属性の名前」を](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c1a5-122">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
  
 \>  
 <span data-ttu-id="0c1a5-123">省略可。</span><span class="sxs-lookup"><span data-stu-id="0c1a5-123">Optional.</span></span> <span data-ttu-id="0c1a5-124">`attribute` が Visual Basic の有効な識別子ではない場合に、属性の名前の末尾を示します。</span><span class="sxs-lookup"><span data-stu-id="0c1a5-124">Denotes the end of the name of the attribute when `attribute` is not a valid identifier in Visual Basic.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0c1a5-125">戻り値</span><span class="sxs-lookup"><span data-stu-id="0c1a5-125">Return Value</span></span>  
 <span data-ttu-id="0c1a5-126">`attribute`の値を格納している文字列。</span><span class="sxs-lookup"><span data-stu-id="0c1a5-126">A string that contains the value of `attribute`.</span></span> <span data-ttu-id="0c1a5-127">属性名が存在しない場合は `Nothing` が返されます。</span><span class="sxs-lookup"><span data-stu-id="0c1a5-127">If the attribute name does not exist, `Nothing` is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c1a5-128">コメント</span><span class="sxs-lookup"><span data-stu-id="0c1a5-128">Remarks</span></span>  
 <span data-ttu-id="0c1a5-129">XML 属性軸プロパティを使用すると、<xref:System.Xml.Linq.XElement> オブジェクトまたは <xref:System.Xml.Linq.XElement> オブジェクトのコレクション内の最初の要素から、名前を指定して属性の値にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="0c1a5-129">You can use an XML attribute axis property to access the value of an attribute by name from an <xref:System.Xml.Linq.XElement> object or from the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="0c1a5-130">名前を指定して属性値を取得することも、@ identifier の前に新しい名前を指定することによって新しい属性を要素に追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="0c1a5-130">You can retrieve an attribute value by name, or add a new attribute to an element by specifying a new name preceded by the @ identifier.</span></span>  
  
 <span data-ttu-id="0c1a5-131">@ Identifier を使用して XML 属性を参照する場合、属性値は文字列として返されるため、<xref:System.Xml.Linq.XAttribute.Value%2A> プロパティを明示的に指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0c1a5-131">When you refer to an XML attribute using the @ identifier, the attribute value is returned as a string and you do not need to explicitly specify the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span>  
  
 <span data-ttu-id="0c1a5-132">XML 属性の名前付け規則は、Visual Basic 識別子の名前付け規則とは異なります。</span><span class="sxs-lookup"><span data-stu-id="0c1a5-132">The naming rules for XML attributes differ from the naming rules for Visual Basic identifiers.</span></span> <span data-ttu-id="0c1a5-133">有効な Visual Basic 識別子ではない名前を持つ XML 属性にアクセスするには、山かっこ (\< と >) で名前を囲みます。</span><span class="sxs-lookup"><span data-stu-id="0c1a5-133">To access an XML attribute that has a name that is not a valid Visual Basic identifier, enclose the name in angle brackets (\< and >).</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="0c1a5-134">XML 名前空間</span><span class="sxs-lookup"><span data-stu-id="0c1a5-134">XML Namespaces</span></span>  
 <span data-ttu-id="0c1a5-135">属性軸プロパティの名前は、`Imports` ステートメントを使用してグローバルに宣言された XML 名前空間プレフィックスのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0c1a5-135">The name in an attribute axis property can use only XML namespace prefixes declared globally by using the `Imports` statement.</span></span> <span data-ttu-id="0c1a5-136">XML 要素リテラル内でローカルに宣言されている XML 名前空間プレフィックスは使用できません。</span><span class="sxs-lookup"><span data-stu-id="0c1a5-136">It cannot use XML namespace prefixes declared locally within XML element literals.</span></span> <span data-ttu-id="0c1a5-137">詳細については、「[Imports ステートメント (XML 名前空間)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c1a5-137">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c1a5-138">例</span><span class="sxs-lookup"><span data-stu-id="0c1a5-138">Example</span></span>  
 <span data-ttu-id="0c1a5-139">次の例は、`phone`という名前の XML 要素のコレクションから、`type` という名前の XML 属性の値を取得する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="0c1a5-139">The following example shows how to get the values of the XML attributes named `type` from a collection of XML elements that are named `phone`.</span></span>  
  
 [!code-vb[VbXMLSamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#12)]  
  
 <span data-ttu-id="0c1a5-140">このコードを実行すると、次のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0c1a5-140">This code displays the following text:</span></span>  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## <a name="example"></a><span data-ttu-id="0c1a5-141">例</span><span class="sxs-lookup"><span data-stu-id="0c1a5-141">Example</span></span>  
 <span data-ttu-id="0c1a5-142">次の例では、xml 要素の属性を宣言によって XML の一部として、また <xref:System.Xml.Linq.XElement> オブジェクトのインスタンスに属性を追加することによって動的に作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0c1a5-142">The following example shows how to create attributes for an XML element both declaratively, as part of the XML, and dynamically by adding an attribute to an instance of an <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="0c1a5-143">`type` 属性は宣言によって作成され、`owner` 属性は動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="0c1a5-143">The `type` attribute is created declaratively and the `owner` attribute is created dynamically.</span></span>  
  
 [!code-vb[VbXMLSamples#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#44)]  
  
 <span data-ttu-id="0c1a5-144">このコードを実行すると、次のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0c1a5-144">This code displays the following text:</span></span>  
  
```xml  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## <a name="example"></a><span data-ttu-id="0c1a5-145">例</span><span class="sxs-lookup"><span data-stu-id="0c1a5-145">Example</span></span>  
 <span data-ttu-id="0c1a5-146">次の例では、山かっこ構文を使用して `number-type`という名前の XML 属性の値を取得しますが、これは Visual Basic の有効な識別子ではありません。</span><span class="sxs-lookup"><span data-stu-id="0c1a5-146">The following example uses the angle bracket syntax to get the value of the XML attribute named `number-type`, which is not a valid identifier in Visual Basic.</span></span>  
  
 [!code-vb[VbXMLSamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#13)]  
  
 <span data-ttu-id="0c1a5-147">このコードを実行すると、次のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0c1a5-147">This code displays the following text:</span></span>  
  
 `Phone type: work`  
  
## <a name="example"></a><span data-ttu-id="0c1a5-148">例</span><span class="sxs-lookup"><span data-stu-id="0c1a5-148">Example</span></span>  
 <span data-ttu-id="0c1a5-149">次の例では、`ns` を名前空間プレフィックスとして宣言します。</span><span class="sxs-lookup"><span data-stu-id="0c1a5-149">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="0c1a5-150">次に、名前空間のプレフィックスを使用して XML リテラルを作成し、修飾名 "`ns:name`" を持つ最初の子ノードにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="0c1a5-150">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name "`ns:name`".</span></span>  
  
 [!code-vb[VbXMLSamples#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples6.vb#14)]  
  
 <span data-ttu-id="0c1a5-151">このコードを実行すると、次のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0c1a5-151">This code displays the following text:</span></span>  
  
 `Phone type: home`  
  
## <a name="see-also"></a><span data-ttu-id="0c1a5-152">参照</span><span class="sxs-lookup"><span data-stu-id="0c1a5-152">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="0c1a5-153">XML 軸プロパティ</span><span class="sxs-lookup"><span data-stu-id="0c1a5-153">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="0c1a5-154">XML リテラル</span><span class="sxs-lookup"><span data-stu-id="0c1a5-154">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="0c1a5-155">Visual Basic での XML の作成</span><span class="sxs-lookup"><span data-stu-id="0c1a5-155">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="0c1a5-156">宣言する XML 要素と属性の名前</span><span class="sxs-lookup"><span data-stu-id="0c1a5-156">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
