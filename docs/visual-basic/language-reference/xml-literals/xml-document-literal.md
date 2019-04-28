---
title: XML ドキュメント リテラル (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralDocument
helpviewer_keywords:
- XML document literal [Visual Basic]
- XML literals [Visual Basic], document
- XML documents [Visual Basic], creating
- document literal [Visual Basic]
ms.assetid: f7bbee56-0911-41de-b907-96f20450137b
ms.openlocfilehash: f58c1365e145166dfe122d455854d44526300a1e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61799308"
---
# <a name="xml-document-literal-visual-basic"></a><span data-ttu-id="18518-102">XML ドキュメント リテラル (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="18518-102">XML Document Literal (Visual Basic)</span></span>
<span data-ttu-id="18518-103">リテラルを表す、<xref:System.Xml.Linq.XDocument>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="18518-103">A literal representing an <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18518-104">構文</span><span class="sxs-lookup"><span data-stu-id="18518-104">Syntax</span></span>  
  
```xml  
<?xml version="1.0" [encoding="encoding"] [standalone="standalone"] ?>  
[ piCommentList ]  
rootElement  
[ piCommentList ]  
```  
  
## <a name="parts"></a><span data-ttu-id="18518-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="18518-105">Parts</span></span>  
  
|<span data-ttu-id="18518-106">用語</span><span class="sxs-lookup"><span data-stu-id="18518-106">Term</span></span>|<span data-ttu-id="18518-107">定義</span><span class="sxs-lookup"><span data-stu-id="18518-107">Definition</span></span>|  
|---|---|  
|`encoding`|<span data-ttu-id="18518-108">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="18518-108">Optional.</span></span> <span data-ttu-id="18518-109">リテラル テキストをどのエンコード ドキュメントの宣言を使用します。</span><span class="sxs-lookup"><span data-stu-id="18518-109">Literal text declaring which encoding the document uses.</span></span>|  
|`standalone`|<span data-ttu-id="18518-110">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="18518-110">Optional.</span></span> <span data-ttu-id="18518-111">リテラル テキスト。</span><span class="sxs-lookup"><span data-stu-id="18518-111">Literal text.</span></span> <span data-ttu-id="18518-112">"Yes"にする必要がありますまたは"no"です。</span><span class="sxs-lookup"><span data-stu-id="18518-112">Must be "yes" or "no".</span></span>|  
|`piCommentList`|<span data-ttu-id="18518-113">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="18518-113">Optional.</span></span> <span data-ttu-id="18518-114">XML 処理命令と XML コメントの一覧です。</span><span class="sxs-lookup"><span data-stu-id="18518-114">List of XML processing instructions and XML comments.</span></span> <span data-ttu-id="18518-115">次の形式を取ります。</span><span class="sxs-lookup"><span data-stu-id="18518-115">Takes the following format:</span></span><br /><br /> <span data-ttu-id="18518-116">`piComment [` `piComment` `... ]`</span><span class="sxs-lookup"><span data-stu-id="18518-116">`piComment [` `piComment` `... ]`</span></span><br /><br /> <span data-ttu-id="18518-117">各`piComment`次のいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="18518-117">Each `piComment` can be one of the following:</span></span><br /><br /> <span data-ttu-id="18518-118">-   [XML 処理命令リテラル](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)します。</span><span class="sxs-lookup"><span data-stu-id="18518-118">-   [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span></span><br /><span data-ttu-id="18518-119">-   [XML コメント リテラル](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)します。</span><span class="sxs-lookup"><span data-stu-id="18518-119">-   [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span></span>|  
|`rootElement`|<span data-ttu-id="18518-120">必須。</span><span class="sxs-lookup"><span data-stu-id="18518-120">Required.</span></span> <span data-ttu-id="18518-121">ドキュメントのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="18518-121">Root element of the document.</span></span> <span data-ttu-id="18518-122">形式は、次のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="18518-122">The format is one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="18518-123">[XML 要素リテラル](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)します。</span><span class="sxs-lookup"><span data-stu-id="18518-123">[XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span></li><li><span data-ttu-id="18518-124">形式の式を埋め込む`<%=` `elementExp` `%>`します。</span><span class="sxs-lookup"><span data-stu-id="18518-124">Embedded expression of the form `<%=` `elementExp` `%>`.</span></span> <span data-ttu-id="18518-125">`elementExp`次のいずれかを返します。</span><span class="sxs-lookup"><span data-stu-id="18518-125">The `elementExp` returns one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="18518-126"><xref:System.Xml.Linq.XElement> オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="18518-126">An <xref:System.Xml.Linq.XElement> object.</span></span></li><li><span data-ttu-id="18518-127">1 つを含むコレクション<xref:System.Xml.Linq.XElement>オブジェクトと任意の数の<xref:System.Xml.Linq.XProcessingInstruction>と<xref:System.Xml.Linq.XComment>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="18518-127">A collection that contains one <xref:System.Xml.Linq.XElement> object and any number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects.</span></span></li></ul></li></ul><br /> <span data-ttu-id="18518-128">詳細については、次を参照してください。 [XML での埋め込み式](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)します。</span><span class="sxs-lookup"><span data-stu-id="18518-128">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="18518-129">戻り値</span><span class="sxs-lookup"><span data-stu-id="18518-129">Return Value</span></span>  
 <span data-ttu-id="18518-130"><xref:System.Xml.Linq.XDocument> オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="18518-130">An <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18518-131">Remarks</span><span class="sxs-lookup"><span data-stu-id="18518-131">Remarks</span></span>  
 <span data-ttu-id="18518-132">XML ドキュメント リテラルは、リテラルの先頭に XML 宣言で識別されます。</span><span class="sxs-lookup"><span data-stu-id="18518-132">An XML document literal is identified by the XML declaration at the start of the literal.</span></span> <span data-ttu-id="18518-133">各 XML ドキュメント リテラルには、XML のルート要素の 1 つだけ必要がありますが、任意の数 XML 処理命令と XML コメントのことができます。</span><span class="sxs-lookup"><span data-stu-id="18518-133">Although each XML document literal must have exactly one root XML element, it can have any number of XML processing instructions and XML comments.</span></span>  
  
 <span data-ttu-id="18518-134">XML ドキュメント リテラルは、XML 要素ではできません。</span><span class="sxs-lookup"><span data-stu-id="18518-134">An XML document literal cannot appear in an XML element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="18518-135">XML リテラルは、行継続文字を使用せず複数の行にまたがることができます。</span><span class="sxs-lookup"><span data-stu-id="18518-135">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="18518-136">これにより、XML ドキュメントの内容をコピーし、Visual Basic プログラムに直接貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="18518-136">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="18518-137">Visual Basic コンパイラの呼び出しにリテラルの XML ドキュメントを変換する、<xref:System.Xml.Linq.XDocument.%23ctor%2A>と<xref:System.Xml.Linq.XDeclaration.%23ctor%2A>コンス トラクター。</span><span class="sxs-lookup"><span data-stu-id="18518-137">The Visual Basic compiler converts the XML document literal into calls to the <xref:System.Xml.Linq.XDocument.%23ctor%2A> and <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> constructors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18518-138">例</span><span class="sxs-lookup"><span data-stu-id="18518-138">Example</span></span>  
 <span data-ttu-id="18518-139">次の例では、XML 宣言、処理命令、コメント、および別の要素を格納する要素を含む XML ドキュメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="18518-139">The following example creates an XML document that has an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
 [!code-vb[VbXMLSamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="18518-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="18518-140">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- <xref:System.Xml.Linq.XProcessingInstruction>
- <xref:System.Xml.Linq.XComment>
- <xref:System.Xml.Linq.XDocument>
- [<span data-ttu-id="18518-141">XML 処理命令リテラル</span><span class="sxs-lookup"><span data-stu-id="18518-141">XML Processing Instruction Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)
- [<span data-ttu-id="18518-142">XML コメント リテラル</span><span class="sxs-lookup"><span data-stu-id="18518-142">XML Comment Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)
- [<span data-ttu-id="18518-143">XML 要素リテラル</span><span class="sxs-lookup"><span data-stu-id="18518-143">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="18518-144">XML リテラル</span><span class="sxs-lookup"><span data-stu-id="18518-144">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="18518-145">Visual Basic での XML の作成</span><span class="sxs-lookup"><span data-stu-id="18518-145">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="18518-146">XML での埋め込み式</span><span class="sxs-lookup"><span data-stu-id="18518-146">Embedded Expressions in XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
