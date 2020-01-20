---
title: XElement クラスの概要 (C#)
ms.date: 07/20/2015
ms.assetid: 2b9f0cd8-a1d1-4037-accf-0f38a410fa11
ms.openlocfilehash: d77c725b3c786b8a8fa2b0eeab4bc4b30f298218
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635471"
---
# <a name="xelement-class-overview-c"></a><span data-ttu-id="93b0c-102">XElement クラスの概要 (C#)</span><span class="sxs-lookup"><span data-stu-id="93b0c-102">XElement Class Overview (C#)</span></span>
<span data-ttu-id="93b0c-103"><xref:System.Xml.Linq.XElement> クラスは、[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] の基礎クラスの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="93b0c-103">The <xref:System.Xml.Linq.XElement> class is one of the fundamental classes in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span> <span data-ttu-id="93b0c-104">これは XML 要素を表します。</span><span class="sxs-lookup"><span data-stu-id="93b0c-104">It represents an XML element.</span></span> <span data-ttu-id="93b0c-105">このクラスを使用すると、要素の作成、要素のコンテンツの変更、子要素の追加、変更、削除、要素への属性の追加、および要素のコンテンツのテキスト形式へのシリアル化を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="93b0c-105">You can use this class to create elements; change the content of the element; add, change, or delete child elements; add attributes to an element; or serialize the contents of an element in text form.</span></span> <span data-ttu-id="93b0c-106"><xref:System.Xml?displayProperty=nameWithType>、<xref:System.Xml.XmlReader>、<xref:System.Xml.XmlWriter> などの、<xref:System.Xml.Xsl.XslCompiledTransform> の他のクラスと相互運用することもできます。</span><span class="sxs-lookup"><span data-stu-id="93b0c-106">You can also interoperate with other classes in <xref:System.Xml?displayProperty=nameWithType>, such as <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, and <xref:System.Xml.Xsl.XslCompiledTransform>.</span></span>  
  
<span data-ttu-id="93b0c-107">このトピックでは、<xref:System.Xml.Linq.XElement> クラスによって提供される機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="93b0c-107">This topic describes the functionality provided by the <xref:System.Xml.Linq.XElement> class.</span></span>  
  
## <a name="constructing-xml-trees"></a><span data-ttu-id="93b0c-108">XML ツリーの構築</span><span class="sxs-lookup"><span data-stu-id="93b0c-108">Constructing XML Trees</span></span>  
 <span data-ttu-id="93b0c-109">次のようなさまざまな方法で XML ツリーを構築できます。</span><span class="sxs-lookup"><span data-stu-id="93b0c-109">You can construct XML trees in a variety of ways, including the following:</span></span>  
  
- <span data-ttu-id="93b0c-110">コードで XML ツリーを構築できます。</span><span class="sxs-lookup"><span data-stu-id="93b0c-110">You can construct an XML tree in code.</span></span> <span data-ttu-id="93b0c-111">詳しくは、「[XML ツリーの作成 (C#)](./linq-to-xml-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="93b0c-111">For more information, see [Creating XML Trees (C#)](./linq-to-xml-overview.md).</span></span>  
  
- <span data-ttu-id="93b0c-112"><xref:System.IO.TextReader>、テキスト ファイル、Web アドレス (URL) など、さまざまなソースから XML を解析できます。</span><span class="sxs-lookup"><span data-stu-id="93b0c-112">You can parse XML from various sources, including a <xref:System.IO.TextReader>, text files, or a Web address (URL).</span></span> <span data-ttu-id="93b0c-113">詳しくは、「[XML の解析 (C#)](./how-to-parse-a-string.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="93b0c-113">For more information, see [Parsing XML (C#)](./how-to-parse-a-string.md).</span></span>  
  
- <span data-ttu-id="93b0c-114"><xref:System.Xml.XmlReader> を使用してツリーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="93b0c-114">You can use an <xref:System.Xml.XmlReader> to populate the tree.</span></span> <span data-ttu-id="93b0c-115">詳細については、「<xref:System.Xml.Linq.XNode.ReadFrom%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="93b0c-115">For more information, see <xref:System.Xml.Linq.XNode.ReadFrom%2A>.</span></span>  
  
- <span data-ttu-id="93b0c-116"><xref:System.Xml.XmlWriter> にコンテンツを書き込むことができるモジュールがある場合は、<xref:System.Xml.Linq.XContainer.CreateWriter%2A> メソッドを使用してライターを作成し、このライターをモジュールに渡し、<xref:System.Xml.XmlWriter> に書き込まれたコンテンツを使用して XML ツリーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="93b0c-116">If you have a module that can write content to an <xref:System.Xml.XmlWriter>, you can use the <xref:System.Xml.Linq.XContainer.CreateWriter%2A> method to create a writer, pass the writer to the module, and then use the content that is written to the <xref:System.Xml.XmlWriter> to populate the XML tree.</span></span>  
  
 <span data-ttu-id="93b0c-117">しかし、XML ツリーを作成する最も一般的な方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="93b0c-117">However, the most common way to create an XML tree is as follows:</span></span>  
  
```csharp  
XElement contacts =  
    new XElement("Contacts",  
        new XElement("Contact",  
            new XElement("Name", "Patrick Hines"),   
            new XElement("Phone", "206-555-0144"),  
            new XElement("Address",  
                new XElement("Street1", "123 Main St"),  
                new XElement("City", "Mercer Island"),  
                new XElement("State", "WA"),  
                new XElement("Postal", "68042")  
            )  
        )  
    );  
```  
  
 <span data-ttu-id="93b0c-118">XML ツリーを作成するもう 1 つの一般的な方法では、次の例に示すように、LINQ クエリの結果を使用して XML ツリーを設定します。</span><span class="sxs-lookup"><span data-stu-id="93b0c-118">Another very common technique for creating an XML tree involves using the results of a LINQ query to populate an XML tree, as shown in the following example:</span></span>  
  
```csharp  
XElement srcTree = new XElement("Root",  
    new XElement("Element", 1),  
    new XElement("Element", 2),  
    new XElement("Element", 3),  
    new XElement("Element", 4),  
    new XElement("Element", 5)  
);  
XElement xmlTree = new XElement("Root",  
    new XElement("Child", 1),  
    new XElement("Child", 2),  
    from el in srcTree.Elements()  
    where (int)el > 2  
    select el  
);  
Console.WriteLine(xmlTree);  
```  
  
 <span data-ttu-id="93b0c-119">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="93b0c-119">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Element>3</Element>  
  <Element>4</Element>  
  <Element>5</Element>  
</Root>  
```  
  
## <a name="serializing-xml-trees"></a><span data-ttu-id="93b0c-120">XML ツリーのシリアル化</span><span class="sxs-lookup"><span data-stu-id="93b0c-120">Serializing XML Trees</span></span>  
 <span data-ttu-id="93b0c-121">XML ツリーは、<xref:System.IO.File>、<xref:System.IO.TextWriter>、または <xref:System.Xml.XmlWriter> にシリアル化できます。</span><span class="sxs-lookup"><span data-stu-id="93b0c-121">You can serialize the XML tree to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="93b0c-122">詳しくは、「[XML ツリーのシリアル化 (C#)](./preserving-white-space-while-serializing.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="93b0c-122">For more information, see [Serializing XML Trees (C#)](./preserving-white-space-while-serializing.md).</span></span>  
  
## <a name="retrieving-xml-data-via-axis-methods"></a><span data-ttu-id="93b0c-123">軸メソッドによる XML データの取得</span><span class="sxs-lookup"><span data-stu-id="93b0c-123">Retrieving XML Data via Axis Methods</span></span>  
 <span data-ttu-id="93b0c-124">軸メソッドを使用すると、属性、子要素、子孫要素、および祖先要素を取得できます。</span><span class="sxs-lookup"><span data-stu-id="93b0c-124">You can use axis methods to retrieve attributes, child elements, descendant elements, and ancestor elements.</span></span> <span data-ttu-id="93b0c-125">LINQ クエリは、軸メソッドに対して機能し、XML ツリーを操作して処理するための、柔軟で強力な複数の機能を備えています。</span><span class="sxs-lookup"><span data-stu-id="93b0c-125">LINQ queries operate on axis methods, and provide several flexible and powerful ways to navigate through and process an XML tree.</span></span>  
  
 <span data-ttu-id="93b0c-126">詳しくは、「[LINQ to XML 軸 (C#)](./linq-to-xml-axes-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="93b0c-126">For more information, see [LINQ to XML Axes (C#)](./linq-to-xml-axes-overview.md).</span></span>  
  
## <a name="querying-xml-trees"></a><span data-ttu-id="93b0c-127">XML ツリーのクエリ</span><span class="sxs-lookup"><span data-stu-id="93b0c-127">Querying XML Trees</span></span>  
 <span data-ttu-id="93b0c-128">XML ツリーからデータを抽出する LINQ クエリを記述できます。</span><span class="sxs-lookup"><span data-stu-id="93b0c-128">You can write LINQ queries that extract data from an XML tree.</span></span>  
  
 <span data-ttu-id="93b0c-129">詳しくは、「[XML ツリーのクエリ (C#)](./how-to-find-an-element-with-a-specific-attribute.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="93b0c-129">For more information, see [Querying XML Trees (C#)](./how-to-find-an-element-with-a-specific-attribute.md).</span></span>  
  
## <a name="modifying-xml-trees"></a><span data-ttu-id="93b0c-130">XML ツリーの変更</span><span class="sxs-lookup"><span data-stu-id="93b0c-130">Modifying XML Trees</span></span>  
 <span data-ttu-id="93b0c-131">要素を変更するには、そのコンテンツや属性を変更するなど、さまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="93b0c-131">You can modify an element in a variety of ways, including changing its content or attributes.</span></span> <span data-ttu-id="93b0c-132">要素を親から削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="93b0c-132">You can also remove an element from its parent.</span></span>  
  
 <span data-ttu-id="93b0c-133">詳しくは、「[XML ツリーの変更 (LINQ to XML) (C#)](./in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="93b0c-133">For more information, see [Modifying XML Trees (LINQ to XML) (C#)](./in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93b0c-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="93b0c-134">See also</span></span>

- [<span data-ttu-id="93b0c-135">LINQ to XML プログラミングの概要 (C#)</span><span class="sxs-lookup"><span data-stu-id="93b0c-135">LINQ to XML Programming Overview (C#)</span></span>](serializing-to-files-textwriters-and-xmlwriters.md)
