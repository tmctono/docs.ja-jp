---
title: XmlReader へのシリアル化 (XSLT の呼び出し)
ms.date: 07/20/2015
ms.assetid: 8b64f95a-e8f6-40f7-99f9-a8002c63af96
ms.openlocfilehash: e51bfc031ad6d5d0eb98718f5d547fb18eb45295
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84357375"
---
# <a name="serializing-to-an-xmlreader-invoking-xslt-visual-basic"></a><span data-ttu-id="1fd93-102">XmlReader へのシリアル化 (XSLT の呼び出し) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1fd93-102">Serializing to an XmlReader (Invoking XSLT) (Visual Basic)</span></span>
<span data-ttu-id="1fd93-103">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] の <xref:System.Xml?displayProperty=nameWithType> 相互運用機能を使用する場合、<xref:System.Xml.Linq.XNode.CreateReader%2A> を使用して <xref:System.Xml.XmlReader> を作成できます。</span><span class="sxs-lookup"><span data-stu-id="1fd93-103">When you use the <xref:System.Xml?displayProperty=nameWithType> interoperability capabilities of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can use <xref:System.Xml.Linq.XNode.CreateReader%2A> to create an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="1fd93-104">この <xref:System.Xml.XmlReader> から読み取りを行うモジュールは、XML ツリーからノードを読み取って適宜処理します。</span><span class="sxs-lookup"><span data-stu-id="1fd93-104">The module that reads from this <xref:System.Xml.XmlReader> reads the nodes from the XML tree and processes them accordingly.</span></span>  
  
## <a name="invoking-an-xslt-transformation"></a><span data-ttu-id="1fd93-105">XSLT 変換の呼び出し</span><span class="sxs-lookup"><span data-stu-id="1fd93-105">Invoking an XSLT Transformation</span></span>  
 <span data-ttu-id="1fd93-106">このメソッドは、XSLT 変換を呼び出すときに使用できます。</span><span class="sxs-lookup"><span data-stu-id="1fd93-106">One possible use for this method is when invoking an XSLT transformation.</span></span> <span data-ttu-id="1fd93-107">この例では、XML ツリーを作成し、この XML ツリーから <xref:System.Xml.XmlReader> を作成して、新しいドキュメントを作成します。次に、この新しいドキュメントに書き込むために <xref:System.Xml.XmlWriter> を作成します。</span><span class="sxs-lookup"><span data-stu-id="1fd93-107">You can create an XML tree, create an <xref:System.Xml.XmlReader> from the XML tree, create a new document, and then create an <xref:System.Xml.XmlWriter> to write into the new document.</span></span> <span data-ttu-id="1fd93-108">次に、XSLT 変換を呼び出して、<xref:System.Xml.XmlReader> と <xref:System.Xml.XmlWriter> を渡します。</span><span class="sxs-lookup"><span data-stu-id="1fd93-108">Then, you can invoke the XSLT transformation, passing in <xref:System.Xml.XmlReader> and <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="1fd93-109">変換が正常に完了すると、新しい XML ツリーに変換結果が挿入されます。</span><span class="sxs-lookup"><span data-stu-id="1fd93-109">After the transformation successfully completes, the new XML tree is populated with the results of the transformation.</span></span>  
  
```vb  
Dim xslMarkup As XDocument = _  
    <?xml version='1.0'?>  
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
    </xsl:stylesheet>  
  
Dim xmlTree As XDocument = _  
    <?xml version='1.0'?>  
    <Parent>  
        <Child1>Child1 data</Child1>  
        <Child2>Child2 data</Child2>  
    </Parent>  
  
Dim newTree As XDocument = New XDocument()  
Using writer As XmlWriter = newTree.CreateWriter()  
    ' Load the style sheet.  
    Dim xslt As XslCompiledTransform = New XslCompiledTransform()  
    xslt.Load(xslMarkup.CreateReader())  
  
    ' Execute the transformation and output the results to a writer.  
    xslt.Transform(xmlTree.CreateReader(), writer)  
End Using  
  
Console.WriteLine(newTree)  
```  
  
 <span data-ttu-id="1fd93-110">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="1fd93-110">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <C1>Child1 data</C1>  
  <C2>Child2 data</C2>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1fd93-111">参照</span><span class="sxs-lookup"><span data-stu-id="1fd93-111">See also</span></span>

- [<span data-ttu-id="1fd93-112">XML ツリーのシリアル化 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1fd93-112">Serializing XML Trees (Visual Basic)</span></span>](serializing-xml-trees.md)
