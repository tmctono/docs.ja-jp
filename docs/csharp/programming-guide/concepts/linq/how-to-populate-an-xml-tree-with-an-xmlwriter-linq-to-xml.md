---
title: 方法:XmlWriter を使用して XML ツリーを設定する (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: cd5674d1-5c54-4efc-ba68-e23b2875295f
ms.openlocfilehash: 88b088ddad54d1fef67cb4c86f8df4eee7bf3662
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69593106"
---
# <a name="how-to-populate-an-xml-tree-with-an-xmlwriter-linq-to-xml-c"></a><span data-ttu-id="7c2b5-102">方法:XmlWriter を使用して XML ツリーを設定する (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="7c2b5-102">How to: Populate an XML Tree with an XmlWriter (LINQ to XML) (C#)</span></span>
<span data-ttu-id="7c2b5-103">XML ツリーを設定する方法の 1 つは、<xref:System.Xml.Linq.XContainer.CreateWriter%2A> を使用して <xref:System.Xml.XmlWriter> を作成し、この <xref:System.Xml.XmlWriter> に書き込みを行うことです。</span><span class="sxs-lookup"><span data-stu-id="7c2b5-103">One way to populate an XML tree is to use <xref:System.Xml.Linq.XContainer.CreateWriter%2A> to create an <xref:System.Xml.XmlWriter>, and then write to the <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="7c2b5-104">XML ツリーには、<xref:System.Xml.XmlWriter> に書き込まれたすべてのノードが挿入されます。</span><span class="sxs-lookup"><span data-stu-id="7c2b5-104">The XML tree is populated with all nodes that are written to the <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="7c2b5-105">通常この方法は、[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] と、<xref:System.Xml.XmlWriter> への書き込みを必要とする別のクラス (<xref:System.Xml.Xsl.XslCompiledTransform> など) を併用する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="7c2b5-105">You would typically use this method when you use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] with another class that expects to write to an <xref:System.Xml.XmlWriter>, such as <xref:System.Xml.Xsl.XslCompiledTransform>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c2b5-106">例</span><span class="sxs-lookup"><span data-stu-id="7c2b5-106">Example</span></span>  
 <span data-ttu-id="7c2b5-107"><xref:System.Xml.Linq.XContainer.CreateWriter%2A> は、XSLT 変換を呼び出すときに使用できます。</span><span class="sxs-lookup"><span data-stu-id="7c2b5-107">One possible use for <xref:System.Xml.Linq.XContainer.CreateWriter%2A> is when invoking an XSLT transformation.</span></span> <span data-ttu-id="7c2b5-108">この例では、XML ツリーを作成し、この XML ツリーから <xref:System.Xml.XmlReader> を作成して、新しいドキュメントを作成します。次に、この新しいドキュメントに書き込むために <xref:System.Xml.XmlWriter> を作成します。</span><span class="sxs-lookup"><span data-stu-id="7c2b5-108">This example creates an XML tree, creates an <xref:System.Xml.XmlReader> from the XML tree, creates a new document, and then creates an <xref:System.Xml.XmlWriter> to write into the new document.</span></span> <span data-ttu-id="7c2b5-109">次に、XSLT 変換を呼び出して、<xref:System.Xml.XmlReader> と <xref:System.Xml.XmlWriter> を渡します。</span><span class="sxs-lookup"><span data-stu-id="7c2b5-109">It then invokes the XSLT transformation, passing in <xref:System.Xml.XmlReader> and <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="7c2b5-110">変換が正常に完了すると、新しい XML ツリーに変換結果が挿入されます。</span><span class="sxs-lookup"><span data-stu-id="7c2b5-110">After the transformation successfully completes, the new XML tree is populated with the results of the transformation.</span></span>  
  
```csharp  
string xslMarkup = @"<?xml version='1.0'?>  
<xsl:stylesheet xmlns:xsl='http://www.w3.org/1999/XSL/Transform' version='1.0'>  
    <xsl:template match='/Parent'>  
        <Root>  
            <C1>  
            <xsl:value-of select='Child1'/>  
            </C1>  
            <C2>  
            <xsl:value-of select='Child2'/>  
            </C2>  
        </Root>  
    </xsl:template>  
</xsl:stylesheet>";  
  
XDocument xmlTree = new XDocument(  
    new XElement("Parent",  
        new XElement("Child1", "Child1 data"),  
        new XElement("Child2", "Child2 data")  
    )  
);  
  
XDocument newTree = new XDocument();  
using (XmlWriter writer = newTree.CreateWriter())  
{  
    // Load the style sheet.  
    XslCompiledTransform xslt = new XslCompiledTransform();  
    xslt.Load(XmlReader.Create(new StringReader(xslMarkup)));  
  
    // Execute the transformation and output the results to a writer.  
    xslt.Transform(xmlTree.CreateReader(), writer);  
}  
  
Console.WriteLine(newTree);  
```  
  
 <span data-ttu-id="7c2b5-111">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="7c2b5-111">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <C1>Child1 data</C1>  
  <C2>Child2 data</C2>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7c2b5-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="7c2b5-112">See also</span></span>

- <xref:System.Xml.Linq.XContainer.CreateWriter%2A>
- <xref:System.Xml.XmlWriter>
- <xref:System.Xml.Xsl.XslCompiledTransform>
- [<span data-ttu-id="7c2b5-113">XML ツリーの作成 (C#)</span><span class="sxs-lookup"><span data-stu-id="7c2b5-113">Creating XML Trees (C#)</span></span>](./linq-to-xml-overview.md)
