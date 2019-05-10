---
title: '方法: XML リテラル (Visual Basic) に式を埋め込む'
ms.date: 07/20/2015
helpviewer_keywords:
- embedded expressions [Visual Basic]
- XML literals [Visual Basic], embedded expressions
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
ms.openlocfilehash: ca80ac666e8676e4e58a9741b00125c0126570fa
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64598380"
---
# <a name="how-to-embed-expressions-in-xml-literals-visual-basic"></a><span data-ttu-id="3331f-102">方法: XML リテラル (Visual Basic) に式を埋め込む</span><span class="sxs-lookup"><span data-stu-id="3331f-102">How to: Embed Expressions in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="3331f-103">埋め込み式 XML ドキュメント、フラグメント、または実行時に作成されたコンテンツを含む要素を作成するには、XML リテラルを組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="3331f-103">You can combine XML literals with embedded expressions to create an XML document, fragment, or element that contains content created at run time.</span></span> <span data-ttu-id="3331f-104">次の例では、組み込み式を使用して、実行時にコンテンツの要素、属性、および要素名を設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3331f-104">The following examples demonstrate how to use embedded expressions to populate element content, attributes, and element names at run time.</span></span>  
  
 <span data-ttu-id="3331f-105">埋め込み式の構文は、 `<%=` `exp` `%>`、同じ構文であるを[!INCLUDE[vstecasp](~/includes/vstecasp-md.md)]を使用します。</span><span class="sxs-lookup"><span data-stu-id="3331f-105">The syntax for an embedded expression is `<%=` `exp` `%>`, which is the same syntax that [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] uses.</span></span> <span data-ttu-id="3331f-106">詳細については、次を参照してください。 [XML での埋め込み式](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)します。</span><span class="sxs-lookup"><span data-stu-id="3331f-106">For more information, see [Embedded Expressions in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>  
  
 <span data-ttu-id="3331f-107">使用することも、 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Api を作成する[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3331f-107">You can also use the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs to create [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects.</span></span> <span data-ttu-id="3331f-108">詳細については、「 <xref:System.Xml.Linq.XElement> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3331f-108">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="3331f-109">手順</span><span class="sxs-lookup"><span data-stu-id="3331f-109">Procedures</span></span>  
  
#### <a name="to-insert-text-as-element-content"></a><span data-ttu-id="3331f-110">要素の内容としてテキストを挿入するには</span><span class="sxs-lookup"><span data-stu-id="3331f-110">To insert text as element content</span></span>  
  
- <span data-ttu-id="3331f-111">次の例に含まれているテキストを挿入する方法を示しています、`contactName`かっこと右の名前の要素間変数。</span><span class="sxs-lookup"><span data-stu-id="3331f-111">The following example shows how to insert the text that is contained in the `contactName` variable between the opening and closing name elements.</span></span>  
  
     [!code-vb[VbXMLSamples#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#39)]  
  
     <span data-ttu-id="3331f-112">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="3331f-112">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-as-an-attribute-value"></a><span data-ttu-id="3331f-113">属性値としてテキストを挿入するには</span><span class="sxs-lookup"><span data-stu-id="3331f-113">To insert text as an attribute value</span></span>  
  
- <span data-ttu-id="3331f-114">次の例に含まれているテキストを挿入する方法を示しています、`phoneType`変数の値として、`type`属性。</span><span class="sxs-lookup"><span data-stu-id="3331f-114">The following example shows how to insert the text that is contained in the `phoneType` variable as the value of the `type` attribute.</span></span>  
  
     [!code-vb[VbXMLSamples#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#40)]  
  
     <span data-ttu-id="3331f-115">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="3331f-115">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-for-an-element-name"></a><span data-ttu-id="3331f-116">要素名のテキストを挿入するには</span><span class="sxs-lookup"><span data-stu-id="3331f-116">To insert text for an element name</span></span>  
  
- <span data-ttu-id="3331f-117">次の例に含まれているテキストを挿入する方法を示しています、`elementName`変数としての要素の名前。</span><span class="sxs-lookup"><span data-stu-id="3331f-117">The following example shows how to insert the text that is contained in the `elementName` variable as the name of an element.</span></span>  
  
     <span data-ttu-id="3331f-118">この手法を使用して要素を作成するときに、それらを閉じる必要があります、 \</> タグです。</span><span class="sxs-lookup"><span data-stu-id="3331f-118">When creating elements by using this technique, you must close them with the \</> tag.</span></span>  
  
     [!code-vb[VbXMLSamples#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#41)]  
  
     <span data-ttu-id="3331f-119">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="3331f-119">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3331f-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="3331f-120">See also</span></span>

- [<span data-ttu-id="3331f-121">方法: XML リテラルを作成します。</span><span class="sxs-lookup"><span data-stu-id="3331f-121">How to: Create XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)
- [<span data-ttu-id="3331f-122">XML での埋め込み式</span><span class="sxs-lookup"><span data-stu-id="3331f-122">Embedded Expressions in XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [<span data-ttu-id="3331f-123">Visual Basic での XML の作成</span><span class="sxs-lookup"><span data-stu-id="3331f-123">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="3331f-124">XML</span><span class="sxs-lookup"><span data-stu-id="3331f-124">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
