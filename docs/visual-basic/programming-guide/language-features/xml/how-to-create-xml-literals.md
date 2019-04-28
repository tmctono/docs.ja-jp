---
title: '方法: XML リテラル (Visual Basic) を作成します。'
ms.date: 07/20/2015
helpviewer_keywords:
- XML literals [Visual Basic], creating
ms.assetid: 573a6db5-b14d-4e42-b356-8cc7e2d77745
ms.openlocfilehash: 836ec4390e7675effe57c75c79768272d66925a3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775909"
---
# <a name="how-to-create-xml-literals-visual-basic"></a><span data-ttu-id="3fc1c-102">方法: XML リテラル (Visual Basic) を作成します。</span><span class="sxs-lookup"><span data-stu-id="3fc1c-102">How to: Create XML Literals (Visual Basic)</span></span>
<span data-ttu-id="3fc1c-103">XML リテラルを使用して、XML ドキュメント、フラグメント、または要素をコード内で直接作成できます。</span><span class="sxs-lookup"><span data-stu-id="3fc1c-103">You can create an XML document, fragment, or element directly in code by using an XML literal.</span></span> <span data-ttu-id="3fc1c-104">このトピックの例では、次の 3 つの子要素を持つ XML 要素を作成する方法と、XML ドキュメントを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3fc1c-104">The examples in this topic demonstrate how to create an XML element that has three child elements, and how to create an XML document.</span></span>  
  
 <span data-ttu-id="3fc1c-105">使用することも、 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Api を作成する[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3fc1c-105">You can also use the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs to create [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects.</span></span> <span data-ttu-id="3fc1c-106">詳細については、「 <xref:System.Xml.Linq.XElement> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3fc1c-106">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
### <a name="to-create-an-xml-element"></a><span data-ttu-id="3fc1c-107">XML 要素を作成するには</span><span class="sxs-lookup"><span data-stu-id="3fc1c-107">To create an XML element</span></span>  
  
- <span data-ttu-id="3fc1c-108">実際の XML 構文と同じでは、XML リテラル構文を使用して XML インラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="3fc1c-108">Create the XML inline by using the XML literal syntax, which is the same as the actual XML syntax.</span></span>  
  
     [!code-vb[VbXMLSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
     <span data-ttu-id="3fc1c-109">コードを実行します。</span><span class="sxs-lookup"><span data-stu-id="3fc1c-109">Run the code.</span></span> <span data-ttu-id="3fc1c-110">このコードの出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3fc1c-110">The output of this code is:</span></span>  
  
     `<contact>`  
  
     `<name>Patrick Hines</name>`  
  
     `<phone type="home">206-555-0144</phone>`  
  
     `<phone type="work">425-555-0145</phone>`  
  
     `</contact>`  
  
### <a name="to-create-an-xml-document"></a><span data-ttu-id="3fc1c-111">XML ドキュメントを作成するには</span><span class="sxs-lookup"><span data-stu-id="3fc1c-111">To create an XML document</span></span>  
  
- <span data-ttu-id="3fc1c-112">XML ドキュメントのインラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="3fc1c-112">Create the XML document inline.</span></span> <span data-ttu-id="3fc1c-113">次のコードは、リテラルの構文、XML 宣言、処理命令、コメント、および別の要素を格納する要素を含む XML ドキュメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="3fc1c-113">The following code creates an XML document that has literal syntax, an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
     [!code-vb[VbXMLSamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#30)]  
  
     <span data-ttu-id="3fc1c-114">コードを実行します。</span><span class="sxs-lookup"><span data-stu-id="3fc1c-114">Run the code.</span></span> <span data-ttu-id="3fc1c-115">このコードの出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3fc1c-115">The output of this code is:</span></span>  
  
     `<?xml-stylesheet type="text/xsl" href="show_book.xsl"?>`  
  
     `<!-- Tests that the application works. -->`  
  
     `<books>`  
  
     `<book/>`  
  
     `</books>`  
  
## <a name="see-also"></a><span data-ttu-id="3fc1c-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="3fc1c-116">See also</span></span>

- [<span data-ttu-id="3fc1c-117">XML</span><span class="sxs-lookup"><span data-stu-id="3fc1c-117">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="3fc1c-118">Visual Basic での XML の作成</span><span class="sxs-lookup"><span data-stu-id="3fc1c-118">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="3fc1c-119">XML 要素リテラル</span><span class="sxs-lookup"><span data-stu-id="3fc1c-119">XML Element Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="3fc1c-120">XML ドキュメント リテラル</span><span class="sxs-lookup"><span data-stu-id="3fc1c-120">XML Document Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
