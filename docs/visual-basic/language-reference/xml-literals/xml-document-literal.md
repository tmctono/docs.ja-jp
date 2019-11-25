---
title: XML ドキュメント リテラル
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralDocument
helpviewer_keywords:
- XML document literal [Visual Basic]
- XML literals [Visual Basic], document
- XML documents [Visual Basic], creating
- document literal [Visual Basic]
ms.assetid: f7bbee56-0911-41de-b907-96f20450137b
ms.openlocfilehash: db77cccd26c87e271d6db45ce514ab6dabbc53e3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349382"
---
# <a name="xml-document-literal-visual-basic"></a><span data-ttu-id="61af5-102">XML ドキュメント リテラル (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="61af5-102">XML Document Literal (Visual Basic)</span></span>
<span data-ttu-id="61af5-103">A literal representing an <xref:System.Xml.Linq.XDocument> object.</span><span class="sxs-lookup"><span data-stu-id="61af5-103">A literal representing an <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61af5-104">構文</span><span class="sxs-lookup"><span data-stu-id="61af5-104">Syntax</span></span>  
  
```xml  
<?xml version="1.0" [encoding="encoding"] [standalone="standalone"] ?>  
[ piCommentList ]  
rootElement  
[ piCommentList ]  
```  
  
## <a name="parts"></a><span data-ttu-id="61af5-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="61af5-105">Parts</span></span>  
  
|<span data-ttu-id="61af5-106">用語</span><span class="sxs-lookup"><span data-stu-id="61af5-106">Term</span></span>|<span data-ttu-id="61af5-107">定義</span><span class="sxs-lookup"><span data-stu-id="61af5-107">Definition</span></span>|  
|---|---|  
|`encoding`|<span data-ttu-id="61af5-108">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="61af5-108">Optional.</span></span> <span data-ttu-id="61af5-109">Literal text declaring which encoding the document uses.</span><span class="sxs-lookup"><span data-stu-id="61af5-109">Literal text declaring which encoding the document uses.</span></span>|  
|`standalone`|<span data-ttu-id="61af5-110">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="61af5-110">Optional.</span></span> <span data-ttu-id="61af5-111">Literal text.</span><span class="sxs-lookup"><span data-stu-id="61af5-111">Literal text.</span></span> <span data-ttu-id="61af5-112">Must be "yes" or "no".</span><span class="sxs-lookup"><span data-stu-id="61af5-112">Must be "yes" or "no".</span></span>|  
|`piCommentList`|<span data-ttu-id="61af5-113">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="61af5-113">Optional.</span></span> <span data-ttu-id="61af5-114">List of XML processing instructions and XML comments.</span><span class="sxs-lookup"><span data-stu-id="61af5-114">List of XML processing instructions and XML comments.</span></span> <span data-ttu-id="61af5-115">Takes the following format:</span><span class="sxs-lookup"><span data-stu-id="61af5-115">Takes the following format:</span></span><br /><br /> <span data-ttu-id="61af5-116">`piComment [` `piComment` `... ]`</span><span class="sxs-lookup"><span data-stu-id="61af5-116">`piComment [` `piComment` `... ]`</span></span><br /><br /> <span data-ttu-id="61af5-117">Each `piComment` can be one of the following:</span><span class="sxs-lookup"><span data-stu-id="61af5-117">Each `piComment` can be one of the following:</span></span><br /><br /> <span data-ttu-id="61af5-118">-   [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span><span class="sxs-lookup"><span data-stu-id="61af5-118">-   [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span></span><br /><span data-ttu-id="61af5-119">-   [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span><span class="sxs-lookup"><span data-stu-id="61af5-119">-   [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span></span>|  
|`rootElement`|<span data-ttu-id="61af5-120">必須です。</span><span class="sxs-lookup"><span data-stu-id="61af5-120">Required.</span></span> <span data-ttu-id="61af5-121">Root element of the document.</span><span class="sxs-lookup"><span data-stu-id="61af5-121">Root element of the document.</span></span> <span data-ttu-id="61af5-122">The format is one of the following:</span><span class="sxs-lookup"><span data-stu-id="61af5-122">The format is one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="61af5-123">[XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="61af5-123">[XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span></li><li><span data-ttu-id="61af5-124">Embedded expression of the form `<%=` `elementExp` `%>`.</span><span class="sxs-lookup"><span data-stu-id="61af5-124">Embedded expression of the form `<%=` `elementExp` `%>`.</span></span> <span data-ttu-id="61af5-125">The `elementExp` returns one of the following:</span><span class="sxs-lookup"><span data-stu-id="61af5-125">The `elementExp` returns one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="61af5-126"><xref:System.Xml.Linq.XElement> オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="61af5-126">An <xref:System.Xml.Linq.XElement> object.</span></span></li><li><span data-ttu-id="61af5-127">A collection that contains one <xref:System.Xml.Linq.XElement> object and any number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects.</span><span class="sxs-lookup"><span data-stu-id="61af5-127">A collection that contains one <xref:System.Xml.Linq.XElement> object and any number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects.</span></span></li></ul></li></ul><br /> <span data-ttu-id="61af5-128">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="61af5-128">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="61af5-129">戻り値</span><span class="sxs-lookup"><span data-stu-id="61af5-129">Return Value</span></span>  
 <span data-ttu-id="61af5-130"><xref:System.Xml.Linq.XDocument> オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="61af5-130">An <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61af5-131">Remarks</span><span class="sxs-lookup"><span data-stu-id="61af5-131">Remarks</span></span>  
 <span data-ttu-id="61af5-132">An XML document literal is identified by the XML declaration at the start of the literal.</span><span class="sxs-lookup"><span data-stu-id="61af5-132">An XML document literal is identified by the XML declaration at the start of the literal.</span></span> <span data-ttu-id="61af5-133">Although each XML document literal must have exactly one root XML element, it can have any number of XML processing instructions and XML comments.</span><span class="sxs-lookup"><span data-stu-id="61af5-133">Although each XML document literal must have exactly one root XML element, it can have any number of XML processing instructions and XML comments.</span></span>  
  
 <span data-ttu-id="61af5-134">An XML document literal cannot appear in an XML element.</span><span class="sxs-lookup"><span data-stu-id="61af5-134">An XML document literal cannot appear in an XML element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="61af5-135">An XML literal can span multiple lines without using line continuation characters.</span><span class="sxs-lookup"><span data-stu-id="61af5-135">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="61af5-136">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span><span class="sxs-lookup"><span data-stu-id="61af5-136">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="61af5-137">The Visual Basic compiler converts the XML document literal into calls to the <xref:System.Xml.Linq.XDocument.%23ctor%2A> and <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> constructors.</span><span class="sxs-lookup"><span data-stu-id="61af5-137">The Visual Basic compiler converts the XML document literal into calls to the <xref:System.Xml.Linq.XDocument.%23ctor%2A> and <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> constructors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61af5-138">例</span><span class="sxs-lookup"><span data-stu-id="61af5-138">Example</span></span>  
 <span data-ttu-id="61af5-139">The following example creates an XML document that has an XML declaration, a processing instruction, a comment, and an element that contains another element.</span><span class="sxs-lookup"><span data-stu-id="61af5-139">The following example creates an XML document that has an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
 [!code-vb[VbXMLSamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="61af5-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="61af5-140">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- <xref:System.Xml.Linq.XProcessingInstruction>
- <xref:System.Xml.Linq.XComment>
- <xref:System.Xml.Linq.XDocument>
- [<span data-ttu-id="61af5-141">XML 処理命令リテラル</span><span class="sxs-lookup"><span data-stu-id="61af5-141">XML Processing Instruction Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)
- [<span data-ttu-id="61af5-142">XML コメント リテラル</span><span class="sxs-lookup"><span data-stu-id="61af5-142">XML Comment Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)
- [<span data-ttu-id="61af5-143">XML 要素リテラル</span><span class="sxs-lookup"><span data-stu-id="61af5-143">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="61af5-144">XML リテラル</span><span class="sxs-lookup"><span data-stu-id="61af5-144">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="61af5-145">Visual Basic での XML の作成</span><span class="sxs-lookup"><span data-stu-id="61af5-145">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="61af5-146">XML での埋め込み式</span><span class="sxs-lookup"><span data-stu-id="61af5-146">Embedded Expressions in XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
