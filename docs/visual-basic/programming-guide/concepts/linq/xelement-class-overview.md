---
title: XElement クラスの概要
ms.date: 07/20/2015
ms.assetid: 52331fcd-6023-4d19-b423-7b24f2d86ded
ms.openlocfilehash: 2e5a1e161345df39ff5c006f751fb293cad60510
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636667"
---
# <a name="xelement-class-overview-visual-basic"></a><span data-ttu-id="d420d-102">XElement クラスの概要 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d420d-102">XElement Class Overview (Visual Basic)</span></span>
<span data-ttu-id="d420d-103"><xref:System.Xml.Linq.XElement> クラスは、[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] の基礎クラスの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="d420d-103">The <xref:System.Xml.Linq.XElement> class is one of the fundamental classes in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span> <span data-ttu-id="d420d-104">これは XML 要素を表します。</span><span class="sxs-lookup"><span data-stu-id="d420d-104">It represents an XML element.</span></span> <span data-ttu-id="d420d-105">このクラスを使用すると、要素の作成、要素のコンテンツの変更、子要素の追加、変更、削除、要素への属性の追加、および要素のコンテンツのテキスト形式へのシリアル化を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d420d-105">You can use this class to create elements; change the content of the element; add, change, or delete child elements; add attributes to an element; or serialize the contents of an element in text form.</span></span> <span data-ttu-id="d420d-106"><xref:System.Xml?displayProperty=nameWithType>、<xref:System.Xml.XmlReader>、<xref:System.Xml.XmlWriter> などの、<xref:System.Xml.Xsl.XslCompiledTransform> の他のクラスと相互運用することもできます。</span><span class="sxs-lookup"><span data-stu-id="d420d-106">You can also interoperate with other classes in <xref:System.Xml?displayProperty=nameWithType>, such as <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, and <xref:System.Xml.Xsl.XslCompiledTransform>.</span></span>  
  
## <a name="xelement-functionality"></a><span data-ttu-id="d420d-107">XElement の機能</span><span class="sxs-lookup"><span data-stu-id="d420d-107">XElement Functionality</span></span>  
 <span data-ttu-id="d420d-108">このトピックでは、<xref:System.Xml.Linq.XElement> クラスによって提供される機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="d420d-108">This topic describes the functionality provided by the <xref:System.Xml.Linq.XElement> class.</span></span>  
  
### <a name="constructing-xml-trees"></a><span data-ttu-id="d420d-109">XML ツリーの構築</span><span class="sxs-lookup"><span data-stu-id="d420d-109">Constructing XML Trees</span></span>  
 <span data-ttu-id="d420d-110">次のようなさまざまな方法で XML ツリーを構築できます。</span><span class="sxs-lookup"><span data-stu-id="d420d-110">You can construct XML trees in a variety of ways, including the following:</span></span>  
  
- <span data-ttu-id="d420d-111">コードで XML ツリーを構築できます。</span><span class="sxs-lookup"><span data-stu-id="d420d-111">You can construct an XML tree in code.</span></span> <span data-ttu-id="d420d-112">詳細については、「 [XML ツリーの作成 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d420d-112">For more information, see [Creating XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).</span></span>  
  
- <span data-ttu-id="d420d-113"><xref:System.IO.TextReader>、テキスト ファイル、Web アドレス (URL) など、さまざまなソースから XML を解析できます。</span><span class="sxs-lookup"><span data-stu-id="d420d-113">You can parse XML from various sources, including a <xref:System.IO.TextReader>, text files, or a Web address (URL).</span></span> <span data-ttu-id="d420d-114">詳細については、「 [XML の解析 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d420d-114">For more information, see [Parsing XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md).</span></span>  
  
- <span data-ttu-id="d420d-115"><xref:System.Xml.XmlReader> を使用してツリーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="d420d-115">You can use an <xref:System.Xml.XmlReader> to populate the tree.</span></span> <span data-ttu-id="d420d-116">詳細については、「 <xref:System.Xml.Linq.XNode.ReadFrom%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d420d-116">For more information, see <xref:System.Xml.Linq.XNode.ReadFrom%2A>.</span></span>  
  
- <span data-ttu-id="d420d-117"><xref:System.Xml.XmlWriter> にコンテンツを書き込むことができるモジュールがある場合は、<xref:System.Xml.Linq.XContainer.CreateWriter%2A> メソッドを使用してライターを作成し、このライターをモジュールに渡し、<xref:System.Xml.XmlWriter> に書き込まれたコンテンツを使用して XML ツリーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="d420d-117">If you have a module that can write content to an <xref:System.Xml.XmlWriter>, you can use the <xref:System.Xml.Linq.XContainer.CreateWriter%2A> method to create a writer, pass the writer to the module, and then use the content that is written to the <xref:System.Xml.XmlWriter> to populate the XML tree.</span></span>  
  
 <span data-ttu-id="d420d-118">しかし、XML ツリーを作成する最も一般的な方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d420d-118">However, the most common way to create an XML tree is as follows:</span></span>  
  
```vb  
Dim contacts As XElement = _  
    <Contacts>  
        <Contact>  
            <Name>Patrick Hines</Name>  
            <Phone>206-555-0144</Phone>  
            <Address>  
                <Street1>123 Main St</Street1>  
                <City>Mercer Island</City>  
                <State>WA</State>  
                <Postal>68042</Postal>  
            </Address>  
        </Contact>  
    </Contacts>  
```  
  
 <span data-ttu-id="d420d-119">XML ツリーを作成するためのもう1つの一般的な方法は、次の例に示すように、LINQ クエリの結果を使用して XML ツリーを設定することです。</span><span class="sxs-lookup"><span data-stu-id="d420d-119">Another very common technique for creating an XML tree involves using the results of a LINQ query to populate an XML tree, as shown in the following example:</span></span>  
  
```vb  
Dim srcTree As XElement = _  
    <Root>  
        <Element>1</Element>  
        <Element>2</Element>  
        <Element>3</Element>  
        <Element>4</Element>  
        <Element>5</Element>  
    </Root>  
Dim xmlTree As XElement = _  
    <Root>  
        <Child>1</Child>  
        <Child>2</Child>  
        <%= From el In srcTree.Elements() _  
            Where el.Value > 2 _  
            Select el %>  
    </Root>  
Console.WriteLine(xmlTree)  
```  
  
 <span data-ttu-id="d420d-120">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="d420d-120">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Element>3</Element>  
  <Element>4</Element>  
  <Element>5</Element>  
</Root>  
```  
  
### <a name="serializing-xml-trees"></a><span data-ttu-id="d420d-121">XML ツリーのシリアル化</span><span class="sxs-lookup"><span data-stu-id="d420d-121">Serializing XML Trees</span></span>  
 <span data-ttu-id="d420d-122">XML ツリーは、<xref:System.IO.File>、<xref:System.IO.TextWriter>、または <xref:System.Xml.XmlWriter> にシリアル化できます。</span><span class="sxs-lookup"><span data-stu-id="d420d-122">You can serialize the XML tree to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="d420d-123">詳細については、「 [XML ツリーのシリアル化 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d420d-123">For more information, see [Serializing XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md).</span></span>  
  
### <a name="retrieving-xml-data-via-axis-methods"></a><span data-ttu-id="d420d-124">軸メソッドによる XML データの取得</span><span class="sxs-lookup"><span data-stu-id="d420d-124">Retrieving XML Data via Axis Methods</span></span>  
 <span data-ttu-id="d420d-125">軸メソッドを使用すると、属性、子要素、子孫要素、および祖先要素を取得できます。</span><span class="sxs-lookup"><span data-stu-id="d420d-125">You can use axis methods to retrieve attributes, child elements, descendant elements, and ancestor elements.</span></span> <span data-ttu-id="d420d-126">LINQ クエリは、軸メソッドに対して機能し、XML ツリーを移動して処理するための柔軟で強力な複数の方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="d420d-126">LINQ queries operate on axis methods, and provide several flexible and powerful ways to navigate through and process an XML tree.</span></span>  
  
 <span data-ttu-id="d420d-127">詳細については、「 [LINQ to XML 軸 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d420d-127">For more information, see [LINQ to XML Axes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md).</span></span>  
  
### <a name="querying-xml-trees"></a><span data-ttu-id="d420d-128">XML ツリーのクエリ</span><span class="sxs-lookup"><span data-stu-id="d420d-128">Querying XML Trees</span></span>  
 <span data-ttu-id="d420d-129">XML ツリーからデータを抽出する LINQ クエリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d420d-129">You can write LINQ queries that extract data from an XML tree.</span></span>  
  
 <span data-ttu-id="d420d-130">詳細については、「 [XML ツリーのクエリ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d420d-130">For more information, see [Querying XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md).</span></span>  
  
### <a name="modifying-xml-trees"></a><span data-ttu-id="d420d-131">XML ツリーの変更</span><span class="sxs-lookup"><span data-stu-id="d420d-131">Modifying XML Trees</span></span>  
 <span data-ttu-id="d420d-132">要素を変更するには、そのコンテンツや属性を変更するなど、さまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="d420d-132">You can modify an element in a variety of ways, including changing its content or attributes.</span></span> <span data-ttu-id="d420d-133">要素を親から削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="d420d-133">You can also remove an element from its parent.</span></span>  
  
 <span data-ttu-id="d420d-134">詳細については、「 [XML ツリーの変更 (LINQ to XML)」 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d420d-134">For more information, see [Modifying XML Trees (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d420d-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="d420d-135">See also</span></span>

- [<span data-ttu-id="d420d-136">LINQ to XML プログラミングの概要 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d420d-136">LINQ to XML Programming Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
