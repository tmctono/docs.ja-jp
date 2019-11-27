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
# <a name="xml-document-literal-visual-basic"></a><span data-ttu-id="89eea-102">XML ドキュメント リテラル (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="89eea-102">XML Document Literal (Visual Basic)</span></span>
<span data-ttu-id="89eea-103"><xref:System.Xml.Linq.XDocument> オブジェクトを表すリテラル。</span><span class="sxs-lookup"><span data-stu-id="89eea-103">A literal representing an <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89eea-104">構文</span><span class="sxs-lookup"><span data-stu-id="89eea-104">Syntax</span></span>  
  
```xml  
<?xml version="1.0" [encoding="encoding"] [standalone="standalone"] ?>  
[ piCommentList ]  
rootElement  
[ piCommentList ]  
```  
  
## <a name="parts"></a><span data-ttu-id="89eea-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="89eea-105">Parts</span></span>  
  
|<span data-ttu-id="89eea-106">用語</span><span class="sxs-lookup"><span data-stu-id="89eea-106">Term</span></span>|<span data-ttu-id="89eea-107">Definition</span><span class="sxs-lookup"><span data-stu-id="89eea-107">Definition</span></span>|  
|---|---|  
|`encoding`|<span data-ttu-id="89eea-108">省略可。</span><span class="sxs-lookup"><span data-stu-id="89eea-108">Optional.</span></span> <span data-ttu-id="89eea-109">ドキュメントが使用するエンコーディングを宣言するリテラルテキスト。</span><span class="sxs-lookup"><span data-stu-id="89eea-109">Literal text declaring which encoding the document uses.</span></span>|  
|`standalone`|<span data-ttu-id="89eea-110">省略可。</span><span class="sxs-lookup"><span data-stu-id="89eea-110">Optional.</span></span> <span data-ttu-id="89eea-111">リテラルテキスト。</span><span class="sxs-lookup"><span data-stu-id="89eea-111">Literal text.</span></span> <span data-ttu-id="89eea-112">"Yes" または "no" にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="89eea-112">Must be "yes" or "no".</span></span>|  
|`piCommentList`|<span data-ttu-id="89eea-113">省略可。</span><span class="sxs-lookup"><span data-stu-id="89eea-113">Optional.</span></span> <span data-ttu-id="89eea-114">XML 処理命令と XML コメントの一覧。</span><span class="sxs-lookup"><span data-stu-id="89eea-114">List of XML processing instructions and XML comments.</span></span> <span data-ttu-id="89eea-115">は、次の形式をとります。</span><span class="sxs-lookup"><span data-stu-id="89eea-115">Takes the following format:</span></span><br /><br /> <span data-ttu-id="89eea-116">`piComment [` `piComment` `... ]`</span><span class="sxs-lookup"><span data-stu-id="89eea-116">`piComment [` `piComment` `... ]`</span></span><br /><br /> <span data-ttu-id="89eea-117">各 `piComment` は、次のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="89eea-117">Each `piComment` can be one of the following:</span></span><br /><br /> <span data-ttu-id="89eea-118">[XML 処理命令リテラル](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)を -   します。</span><span class="sxs-lookup"><span data-stu-id="89eea-118">-   [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span></span><br /><span data-ttu-id="89eea-119">[XML コメントリテラル](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)を -   します。</span><span class="sxs-lookup"><span data-stu-id="89eea-119">-   [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span></span>|  
|`rootElement`|<span data-ttu-id="89eea-120">必須。</span><span class="sxs-lookup"><span data-stu-id="89eea-120">Required.</span></span> <span data-ttu-id="89eea-121">ドキュメントのルート要素。</span><span class="sxs-lookup"><span data-stu-id="89eea-121">Root element of the document.</span></span> <span data-ttu-id="89eea-122">形式は、次のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="89eea-122">The format is one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="89eea-123">[XML 要素リテラル](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)。</span><span class="sxs-lookup"><span data-stu-id="89eea-123">[XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span></li><li><span data-ttu-id="89eea-124">`elementExp` `%>``<%=` フォームの埋め込み式。</span><span class="sxs-lookup"><span data-stu-id="89eea-124">Embedded expression of the form `<%=` `elementExp` `%>`.</span></span> <span data-ttu-id="89eea-125">`elementExp` は、次のいずれかを返します。</span><span class="sxs-lookup"><span data-stu-id="89eea-125">The `elementExp` returns one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="89eea-126"><xref:System.Xml.Linq.XElement> オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="89eea-126">An <xref:System.Xml.Linq.XElement> object.</span></span></li><li><span data-ttu-id="89eea-127">1つの <xref:System.Xml.Linq.XElement> オブジェクトと、任意の数の <xref:System.Xml.Linq.XProcessingInstruction> および <xref:System.Xml.Linq.XComment> オブジェクトを含むコレクション。</span><span class="sxs-lookup"><span data-stu-id="89eea-127">A collection that contains one <xref:System.Xml.Linq.XElement> object and any number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects.</span></span></li></ul></li></ul><br /> <span data-ttu-id="89eea-128">詳細については、「 [XML での埋め込み式](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89eea-128">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="89eea-129">戻り値</span><span class="sxs-lookup"><span data-stu-id="89eea-129">Return Value</span></span>  
 <span data-ttu-id="89eea-130"><xref:System.Xml.Linq.XDocument> オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="89eea-130">An <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89eea-131">コメント</span><span class="sxs-lookup"><span data-stu-id="89eea-131">Remarks</span></span>  
 <span data-ttu-id="89eea-132">XML ドキュメントリテラルは、リテラルの先頭にある XML 宣言によって識別されます。</span><span class="sxs-lookup"><span data-stu-id="89eea-132">An XML document literal is identified by the XML declaration at the start of the literal.</span></span> <span data-ttu-id="89eea-133">各 XML ドキュメントリテラルは1つのルート XML 要素を持つ必要がありますが、xml 処理命令と XML コメントは、任意の数を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="89eea-133">Although each XML document literal must have exactly one root XML element, it can have any number of XML processing instructions and XML comments.</span></span>  
  
 <span data-ttu-id="89eea-134">Xml ドキュメントリテラルは XML 要素には記述できません。</span><span class="sxs-lookup"><span data-stu-id="89eea-134">An XML document literal cannot appear in an XML element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="89eea-135">XML リテラルは、行連結文字を使用せずに、複数の行にまたがることができます。</span><span class="sxs-lookup"><span data-stu-id="89eea-135">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="89eea-136">これにより、XML ドキュメントからコンテンツをコピーし、Visual Basic プログラムに直接貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="89eea-136">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="89eea-137">Visual Basic コンパイラは、XML ドキュメントリテラルを、<xref:System.Xml.Linq.XDocument.%23ctor%2A> コンストラクターと <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> コンストラクターの呼び出しに変換します。</span><span class="sxs-lookup"><span data-stu-id="89eea-137">The Visual Basic compiler converts the XML document literal into calls to the <xref:System.Xml.Linq.XDocument.%23ctor%2A> and <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> constructors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89eea-138">例</span><span class="sxs-lookup"><span data-stu-id="89eea-138">Example</span></span>  
 <span data-ttu-id="89eea-139">次の例では、xml 宣言、処理命令、コメント、および別の要素を含む要素を含む XML ドキュメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="89eea-139">The following example creates an XML document that has an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
 [!code-vb[VbXMLSamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="89eea-140">参照</span><span class="sxs-lookup"><span data-stu-id="89eea-140">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- <xref:System.Xml.Linq.XProcessingInstruction>
- <xref:System.Xml.Linq.XComment>
- <xref:System.Xml.Linq.XDocument>
- [<span data-ttu-id="89eea-141">XML 処理命令リテラル</span><span class="sxs-lookup"><span data-stu-id="89eea-141">XML Processing Instruction Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)
- [<span data-ttu-id="89eea-142">XML コメント リテラル</span><span class="sxs-lookup"><span data-stu-id="89eea-142">XML Comment Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)
- [<span data-ttu-id="89eea-143">XML 要素リテラル</span><span class="sxs-lookup"><span data-stu-id="89eea-143">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="89eea-144">XML リテラル</span><span class="sxs-lookup"><span data-stu-id="89eea-144">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="89eea-145">Visual Basic での XML の作成</span><span class="sxs-lookup"><span data-stu-id="89eea-145">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="89eea-146">XML での埋め込み式</span><span class="sxs-lookup"><span data-stu-id="89eea-146">Embedded Expressions in XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
