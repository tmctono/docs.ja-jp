---
title: XML リテラルの概要 2
ms.date: 07/20/2015
ms.assetid: 94fc0e03-978e-4c08-ab6c-0dc3c1e64f10
ms.openlocfilehash: 9f5c54574e51c537d9ea58d307afda10736d0d88
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266951"
---
# <a name="introduction-to-xml-literals-in-visual-basic"></a><span data-ttu-id="84f61-102">Visual Basic の XML リテラルの概要</span><span class="sxs-lookup"><span data-stu-id="84f61-102">Introduction to XML Literals in Visual Basic</span></span>
<span data-ttu-id="84f61-103">このセクションでは、Visual Basic での XML ツリーの作成について説明します。</span><span class="sxs-lookup"><span data-stu-id="84f61-103">This section provides information about creating XML trees in Visual Basic.</span></span>  
  
 <span data-ttu-id="84f61-104">XML ツリーのコンテンツとして LINQ クエリの結果を使用する方法については、「[機能構築 (LINQ to XML)(Visual Basic)」](../../../../visual-basic/programming-guide/concepts/linq/functional-construction-linq-to-xml.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84f61-104">For information about using the results of LINQ queries as the content for an XML tree, see [Functional Construction (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-construction-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="84f61-105">Visual Basic の XML リテラルの詳細については、「 Visual Basic で[の LINQ to XML の概要](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84f61-105">For more information on XML literals in Visual Basic, see [Overview of LINQ to XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md).</span></span>  
  
## <a name="creating-xml-trees"></a><span data-ttu-id="84f61-106">XML ツリーの作成</span><span class="sxs-lookup"><span data-stu-id="84f61-106">Creating XML Trees</span></span>  
 <span data-ttu-id="84f61-107"><xref:System.Xml.Linq.XElement> (この場合は `contacts`) を作成する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="84f61-107">The following example shows how to create an <xref:System.Xml.Linq.XElement>, in this case `contacts`:</span></span>  
  
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
  
### <a name="creating-an-xelement-with-simple-content"></a><span data-ttu-id="84f61-108">単純コンテンツを持つ XElement の作成</span><span class="sxs-lookup"><span data-stu-id="84f61-108">Creating an XElement with Simple Content</span></span>  
 <span data-ttu-id="84f61-109">次のように、単純コンテンツを含む <xref:System.Xml.Linq.XElement> を作成できます。</span><span class="sxs-lookup"><span data-stu-id="84f61-109">You can create an <xref:System.Xml.Linq.XElement> that contains simple content, as follows:</span></span>  
  
```vb  
Dim n as XElement = <Customer>Adventure Works</Customer>  
Console.WriteLine(n)
```  
  
 <span data-ttu-id="84f61-110">この例の結果は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="84f61-110">This example produces the following output:</span></span>  
  
```xml  
<Customer>Adventure Works</Customer>  
```  
  
### <a name="creating-an-empty-element"></a><span data-ttu-id="84f61-111">空要素の作成</span><span class="sxs-lookup"><span data-stu-id="84f61-111">Creating an Empty Element</span></span>  
 <span data-ttu-id="84f61-112">次のように、空の <xref:System.Xml.Linq.XElement> を作成できます。</span><span class="sxs-lookup"><span data-stu-id="84f61-112">You can create an empty <xref:System.Xml.Linq.XElement>, as follows:</span></span>  
  
```vb  
Dim n As XElement = <Customer/>  
Console.WriteLine(n)  
```  
  
 <span data-ttu-id="84f61-113">この例の結果は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="84f61-113">This example produces the following output:</span></span>  
  
```xml  
<Customer />  
```  
  
### <a name="using-embedded-expressions"></a><span data-ttu-id="84f61-114">組み込み式の使用</span><span class="sxs-lookup"><span data-stu-id="84f61-114">Using Embedded Expressions</span></span>  
 <span data-ttu-id="84f61-115">XML リテラルの重要な機能は、組み込み式を利用できることです。</span><span class="sxs-lookup"><span data-stu-id="84f61-115">An important feature of XML literals is that they allow embedded expressions.</span></span> <span data-ttu-id="84f61-116">組み込み式を使用すると、式を評価してその式の結果を XML ツリーに挿入できます。</span><span class="sxs-lookup"><span data-stu-id="84f61-116">Embedded expressions enable you to evaluate an expression and insert the results of the expression into the XML tree.</span></span> <span data-ttu-id="84f61-117">式が <xref:System.Xml.Linq.XElement> の型に評価される場合、要素がツリーに挿入されます。</span><span class="sxs-lookup"><span data-stu-id="84f61-117">If the expression evaluates to a type of <xref:System.Xml.Linq.XElement>, an element is inserted into the tree.</span></span> <span data-ttu-id="84f61-118">式が <xref:System.Xml.Linq.XAttribute> の型に評価される場合は、属性がツリーに挿入されます。</span><span class="sxs-lookup"><span data-stu-id="84f61-118">If the expression evaluates to a type of <xref:System.Xml.Linq.XAttribute>, an attribute is inserted into the tree.</span></span> <span data-ttu-id="84f61-119">要素および属性は、それらが有効となるツリーにのみ挿入できます。</span><span class="sxs-lookup"><span data-stu-id="84f61-119">You can insert elements and attributes into the tree only where they are valid.</span></span>  
  
 <span data-ttu-id="84f61-120">組み込み式に含めることができるのは 1 つの式だけであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="84f61-120">It is important to note that only a single expression can go into an embedded expression.</span></span> <span data-ttu-id="84f61-121">複数のステートメントを組み込むことはできません。</span><span class="sxs-lookup"><span data-stu-id="84f61-121">You cannot embed multiple statements.</span></span> <span data-ttu-id="84f61-122">式が複数の行にまたがる場合は、行連結文字を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="84f61-122">If an expression extends beyond a single line, you must use the line continuation character.</span></span>  
  
 <span data-ttu-id="84f61-123">組み込み式を使用して既存のノード (要素を含む) や属性を新しい XML ツリーに追加する場合に、その既存のノードに既に親があるときは、ノードが複製されます。</span><span class="sxs-lookup"><span data-stu-id="84f61-123">If you use an embedded expression to add existing nodes (including elements) and attributes to a new XML tree and if the existing nodes are already parented, the nodes are cloned.</span></span> <span data-ttu-id="84f61-124">新しく複製されたノードは、新しい XML ツリーにアタッチされます。</span><span class="sxs-lookup"><span data-stu-id="84f61-124">The newly cloned nodes are attached to the new XML tree.</span></span> <span data-ttu-id="84f61-125">既存のノードに親がない場合は、単にノードが新しい XML ツリーにアタッチされます。</span><span class="sxs-lookup"><span data-stu-id="84f61-125">If the existing nodes are not parented, the nodes are simply attached to the new XML tree.</span></span> <span data-ttu-id="84f61-126">このトピックの最後の例では、この動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="84f61-126">The last example in this topic demonstrates this.</span></span>  
  
 <span data-ttu-id="84f61-127">次の例では、組み込み式を使用して要素をツリーに挿入します。</span><span class="sxs-lookup"><span data-stu-id="84f61-127">The following example uses an embedded expression to insert an element into the tree:</span></span>  
  
```vb  
xmlTree1 As XElement = _  
    <Root>  
        <Child>Contents</Child>  
    </Root>  
Dim xmlTree2 As XElement = _  
    <Root>  
        <%= xmlTree1.<Child> %>  
    </Root>  
Console.WriteLine(xmlTree2)  
```  
  
 <span data-ttu-id="84f61-128">この例の結果は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="84f61-128">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child>Contents</Child>  
</Root>  
```  
  
### <a name="using-embedded-expressions-for-content"></a><span data-ttu-id="84f61-129">コンテンツに対する組み込み式の使用</span><span class="sxs-lookup"><span data-stu-id="84f61-129">Using Embedded Expressions for Content</span></span>  
 <span data-ttu-id="84f61-130">組み込み式を使用して要素のコンテンツを指定できます。</span><span class="sxs-lookup"><span data-stu-id="84f61-130">You can use an embedded expression to supply the content of an element:</span></span>  
  
```vb  
Dim str As String  
str = "Some content"  
Dim root As XElement = <Root><%= str %></Root>  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="84f61-131">この例の結果は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="84f61-131">This example produces the following output:</span></span>  
  
```xml  
<Root>Some content</Root>  
```  
  
### <a name="using-a-linq-query-in-an-embedded-expression"></a><span data-ttu-id="84f61-132">組み込み式での LINQ クエリの使用</span><span class="sxs-lookup"><span data-stu-id="84f61-132">Using a LINQ Query in an Embedded Expression</span></span>  
 <span data-ttu-id="84f61-133">要素のコンテンツに対する LINQ クエリの結果を使用できます。</span><span class="sxs-lookup"><span data-stu-id="84f61-133">You can use the results of a LINQ query for the content of an element:</span></span>  
  
```vb  
Dim arr As Integer() = {1, 2, 3}  
  
Dim n As XElement = _  
    <Root>  
        <%= From i In arr Select <Child><%= i %></Child> %>  
    </Root>  
  
Console.WriteLine(n)  
```  
  
 <span data-ttu-id="84f61-134">この例の結果は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="84f61-134">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Child>3</Child>  
</Root>  
```  
  
### <a name="using-embedded-expressions-for-node-names"></a><span data-ttu-id="84f61-135">ノード名に対する組み込み式の使用</span><span class="sxs-lookup"><span data-stu-id="84f61-135">Using Embedded Expressions for Node Names</span></span>  
 <span data-ttu-id="84f61-136">組み込み式を使用して、属性名、属性値、要素名、および要素値を計算することもできます。</span><span class="sxs-lookup"><span data-stu-id="84f61-136">You can also use embedded expressions to calculate attribute names, attribute values, element names, and element values:</span></span>  
  
```vb  
Dim eleName As String = "ele"  
Dim attName As String = "att"  
Dim attValue As String = "aValue"  
Dim eleValue As String = "eValue"  
Dim n As XElement = _  
    <Root <%= attName %>=<%= attValue %>>  
        <<%= eleName %>>  
            <%= eleValue %>  
        </>  
    </Root>  
Console.WriteLine(n)  
```  
  
 <span data-ttu-id="84f61-137">この例の結果は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="84f61-137">This example produces the following output:</span></span>  
  
```xml  
<Root att="aValue">  
  <ele>eValue</ele>  
</Root>  
```  
  
### <a name="cloning-vs-attaching"></a><span data-ttu-id="84f61-138">複製とアタッチ</span><span class="sxs-lookup"><span data-stu-id="84f61-138">Cloning vs. Attaching</span></span>  
 <span data-ttu-id="84f61-139">既に説明したとおり、組み込み式を使用して既存のノード (要素を含む) や属性を新しい XML ツリーに追加する場合に、その既存のノードに既に親があるときは、ノードが複製され、新しく複製されたノードが新しい XML ツリーにアタッチされます。</span><span class="sxs-lookup"><span data-stu-id="84f61-139">As mentioned earlier, if you use an embedded expression to add existing nodes (including elements) and attributes to a new XML tree, if the existing nodes are already parented, the nodes are cloned and the newly cloned nodes are attached to the new XML tree.</span></span> <span data-ttu-id="84f61-140">既存のノードに親がない場合は、単にノードが新しい XML ツリーにアタッチされます。</span><span class="sxs-lookup"><span data-stu-id="84f61-140">If the existing nodes are not parented, they are simply attached to the new XML tree.</span></span>  
  
```vb  
' Create a tree with a child element.  
Dim xmlTree1 As XElement = _  
    <Root>  
        <Child1>1</Child1>  
    </Root>  
  
' Create an element that is not parented.  
Dim child2 As XElement = <Child2>2</Child2>  
  
' Create a tree and add Child1 and Child2 to it.  
Dim xmlTree2 As XElement = _  
    <Root>  
        <%= xmlTree1.<Child1>(0) %>  
        <%= child2 %>  
    </Root>  
  
' Compare Child1 identity.  
Console.WriteLine("Child1 was {0}", _  
    IIf(xmlTree1.Element("Child1") Is xmlTree2.Element("Child1"), _  
    "attached", "cloned"))  
  
' Compare Child2 identity.  
Console.WriteLine("Child2 was {0}", _  
    IIf(child2 Is xmlTree2.Element("Child2"), _  
    "attached", "cloned"))  
```  
  
 <span data-ttu-id="84f61-141">この例の結果は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="84f61-141">This example produces the following output:</span></span>  
  
```console  
Child1 was cloned  
Child2 was attached  
```  
  
## <a name="see-also"></a><span data-ttu-id="84f61-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="84f61-142">See also</span></span>

- [<span data-ttu-id="84f61-143">XML ツリーの作成</span><span class="sxs-lookup"><span data-stu-id="84f61-143">Creating XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
