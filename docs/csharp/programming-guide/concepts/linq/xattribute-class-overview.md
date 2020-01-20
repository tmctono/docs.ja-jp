---
title: XAttribute クラスの概要 (C#)
ms.date: 07/20/2015
ms.assetid: 5a630f24-f9ad-400e-831e-c14ebfc9e142
ms.openlocfilehash: 7a806314664c6319fc45cff0dddedbe38027059d
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635666"
---
# <a name="xattribute-class-overview-c"></a><span data-ttu-id="780ba-102">XAttribute クラスの概要 (C#)</span><span class="sxs-lookup"><span data-stu-id="780ba-102">XAttribute Class Overview (C#)</span></span>
<span data-ttu-id="780ba-103">属性は、要素に関連付けられている名前と値のペアです。</span><span class="sxs-lookup"><span data-stu-id="780ba-103">Attributes are name/value pairs that are associated with an element.</span></span> <span data-ttu-id="780ba-104"><xref:System.Xml.Linq.XAttribute> クラスは、XML 属性を表します。</span><span class="sxs-lookup"><span data-stu-id="780ba-104">The <xref:System.Xml.Linq.XAttribute> class represents XML attributes.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="780ba-105">概要</span><span class="sxs-lookup"><span data-stu-id="780ba-105">Overview</span></span>  
 <span data-ttu-id="780ba-106">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] での属性の操作は、要素の操作に似ています。</span><span class="sxs-lookup"><span data-stu-id="780ba-106">Working with attributes in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is similar to working with elements.</span></span> <span data-ttu-id="780ba-107">コンストラクターはほぼ同じです。</span><span class="sxs-lookup"><span data-stu-id="780ba-107">Their constructors are similar.</span></span> <span data-ttu-id="780ba-108">それぞれのコレクションの取得に使用するメソッドもほぼ同じです。</span><span class="sxs-lookup"><span data-stu-id="780ba-108">The methods that you use to retrieve collections of them are similar.</span></span> <span data-ttu-id="780ba-109">属性のコレクションの LINQ クエリ式は、要素のコレクションの LINQ クエリ式とよく似ています。</span><span class="sxs-lookup"><span data-stu-id="780ba-109">A LINQ query expression for a collection of attributes looks very similar to a LINQ query expression for a collection of elements.</span></span>  
  
 <span data-ttu-id="780ba-110">属性が要素に追加された順序は保持されます。</span><span class="sxs-lookup"><span data-stu-id="780ba-110">The order in which attributes were added to an element is preserved.</span></span> <span data-ttu-id="780ba-111">つまり、属性を反復処理する場合、属性は追加された順序と同じ順序で表示されます。</span><span class="sxs-lookup"><span data-stu-id="780ba-111">That is, when you iterate through the attributes, you see them in the same order that they were added.</span></span>  
  
## <a name="the-xattribute-constructor"></a><span data-ttu-id="780ba-112">XAttribute コンストラクター</span><span class="sxs-lookup"><span data-stu-id="780ba-112">The XAttribute Constructor</span></span>  
 <span data-ttu-id="780ba-113">最もよく使用する <xref:System.Xml.Linq.XAttribute> クラスのコンストラクターを次に示します。</span><span class="sxs-lookup"><span data-stu-id="780ba-113">The following constructor of the <xref:System.Xml.Linq.XAttribute> class is the one that you will most commonly use:</span></span>  
  
|<span data-ttu-id="780ba-114">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="780ba-114">Constructor</span></span>|<span data-ttu-id="780ba-115">説明</span><span class="sxs-lookup"><span data-stu-id="780ba-115">Description</span></span>|  
|-----------------|-----------------|  
|`XAttribute(XName name, object content)`|<span data-ttu-id="780ba-116"><xref:System.Xml.Linq.XAttribute> オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="780ba-116">Creates an <xref:System.Xml.Linq.XAttribute> object.</span></span> <span data-ttu-id="780ba-117">`name` 引数には属性の名前を指定し、`content` には属性のコンテンツを指定します。</span><span class="sxs-lookup"><span data-stu-id="780ba-117">The `name` argument specifies the name of the attribute; `content` specifies the content of the attribute.</span></span>|  
  
### <a name="creating-an-element-with-an-attribute"></a><span data-ttu-id="780ba-118">属性を持つ要素の作成</span><span class="sxs-lookup"><span data-stu-id="780ba-118">Creating an Element with an Attribute</span></span>  
 <span data-ttu-id="780ba-119">次のコードは、属性を含む要素を作成する一般的なタスクを示しています。</span><span class="sxs-lookup"><span data-stu-id="780ba-119">The following code shows the common task of creating an element that contains an attribute:</span></span>  
  
```csharp  
XElement phone = new XElement("Phone",  
    new XAttribute("Type", "Home"),  
    "555-555-5555");  
Console.WriteLine(phone);  
```  
  
 <span data-ttu-id="780ba-120">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="780ba-120">This example produces the following output:</span></span>  
  
```xml  
<Phone Type="Home">555-555-5555</Phone>  
```  
  
### <a name="functional-construction-of-attributes"></a><span data-ttu-id="780ba-121">属性の関数型構築</span><span class="sxs-lookup"><span data-stu-id="780ba-121">Functional Construction of Attributes</span></span>  
 <span data-ttu-id="780ba-122"><xref:System.Xml.Linq.XAttribute> オブジェクトは、<xref:System.Xml.Linq.XElement> オブジェクトの構築と共にインラインで構築できます。</span><span class="sxs-lookup"><span data-stu-id="780ba-122">You can construct <xref:System.Xml.Linq.XAttribute> objects in-line with the construction of <xref:System.Xml.Linq.XElement> objects, as follows:</span></span>  
  
```csharp  
XElement c = new XElement("Customers",  
    new XElement("Customer",  
        new XElement("Name", "John Doe"),  
        new XElement("PhoneNumbers",  
            new XElement("Phone",  
                new XAttribute("type", "home"),  
                "555-555-5555"),  
            new XElement("Phone",  
                new XAttribute("type", "work"),  
                "666-666-6666")  
        )  
    )  
);  
Console.WriteLine(c);  
```  
  
 <span data-ttu-id="780ba-123">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="780ba-123">This example produces the following output:</span></span>  
  
```xml  
<Customers>  
  <Customer>  
    <Name>John Doe</Name>  
    <PhoneNumbers>  
      <Phone type="home">555-555-5555</Phone>  
      <Phone type="work">666-666-6666</Phone>  
    </PhoneNumbers>  
  </Customer>  
</Customers>  
```  
  
### <a name="attributes-are-not-nodes"></a><span data-ttu-id="780ba-124">属性はノードではない</span><span class="sxs-lookup"><span data-stu-id="780ba-124">Attributes Are Not Nodes</span></span>  
 <span data-ttu-id="780ba-125">属性と要素には、いくつかの違いがあります。</span><span class="sxs-lookup"><span data-stu-id="780ba-125">There are some differences between attributes and elements.</span></span> <span data-ttu-id="780ba-126"><xref:System.Xml.Linq.XAttribute> オブジェクトは、XML ツリーのノードではありません。</span><span class="sxs-lookup"><span data-stu-id="780ba-126"><xref:System.Xml.Linq.XAttribute> objects are not nodes in the XML tree.</span></span> <span data-ttu-id="780ba-127">属性は、XML 要素に関連付けられている名前と値のペアです。</span><span class="sxs-lookup"><span data-stu-id="780ba-127">They are name/value pairs associated with an XML element.</span></span> <span data-ttu-id="780ba-128">ドキュメント オブジェクト モデル (DOM) とは異なり、XML の構造をより密接に反映します。</span><span class="sxs-lookup"><span data-stu-id="780ba-128">In contrast to the Document Object Model (DOM), this more closely reflects the structure of XML.</span></span> <span data-ttu-id="780ba-129"><xref:System.Xml.Linq.XAttribute> オブジェクトは実際には XML ツリーのノードではありませんが、<xref:System.Xml.Linq.XAttribute> オブジェクトの操作は <xref:System.Xml.Linq.XElement> オブジェクトの操作とよく似ています。</span><span class="sxs-lookup"><span data-stu-id="780ba-129">Although <xref:System.Xml.Linq.XAttribute> objects are not actually nodes in the XML tree, working with <xref:System.Xml.Linq.XAttribute> objects is very similar to working with <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="780ba-130">属性と要素の区別は主に、ノード レベルで XML ツリーを操作するコードを記述する開発者にとってのみ重要な意味を持ちます。</span><span class="sxs-lookup"><span data-stu-id="780ba-130">This distinction is primarily important only to developers who are writing code that works with XML trees at the node level.</span></span> <span data-ttu-id="780ba-131">多くの開発者は、この区別を考慮する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="780ba-131">Many developers will not be concerned with this distinction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="780ba-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="780ba-132">See also</span></span>

- [<span data-ttu-id="780ba-133">LINQ to XML プログラミングの概要 (C#)</span><span class="sxs-lookup"><span data-stu-id="780ba-133">LINQ to XML Programming Overview (C#)</span></span>](./linq-to-xml-overview.md)
