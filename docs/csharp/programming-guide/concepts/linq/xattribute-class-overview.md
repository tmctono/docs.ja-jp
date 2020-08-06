---
title: XAttribute クラスの概要 (C#)
description: 属性は、要素に関連付けられている名前と値のペアです。 XAttribute によって XML 属性が表されます。 C# で LINQ to XML の属性を操作する方法について説明します。
ms.date: 07/20/2015
ms.assetid: 5a630f24-f9ad-400e-831e-c14ebfc9e142
ms.openlocfilehash: 8a19de601041bbb20241c959e909483b97bcf797
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302231"
---
# <a name="xattribute-class-overview-c"></a><span data-ttu-id="a2032-105">XAttribute クラスの概要 (C#)</span><span class="sxs-lookup"><span data-stu-id="a2032-105">XAttribute Class Overview (C#)</span></span>
<span data-ttu-id="a2032-106">属性は、要素に関連付けられている名前と値のペアです。</span><span class="sxs-lookup"><span data-stu-id="a2032-106">Attributes are name/value pairs that are associated with an element.</span></span> <span data-ttu-id="a2032-107"><xref:System.Xml.Linq.XAttribute> クラスは、XML 属性を表します。</span><span class="sxs-lookup"><span data-stu-id="a2032-107">The <xref:System.Xml.Linq.XAttribute> class represents XML attributes.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="a2032-108">概要</span><span class="sxs-lookup"><span data-stu-id="a2032-108">Overview</span></span>  
 <span data-ttu-id="a2032-109">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] での属性の操作は、要素の操作に似ています。</span><span class="sxs-lookup"><span data-stu-id="a2032-109">Working with attributes in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is similar to working with elements.</span></span> <span data-ttu-id="a2032-110">コンストラクターはほぼ同じです。</span><span class="sxs-lookup"><span data-stu-id="a2032-110">Their constructors are similar.</span></span> <span data-ttu-id="a2032-111">それぞれのコレクションの取得に使用するメソッドもほぼ同じです。</span><span class="sxs-lookup"><span data-stu-id="a2032-111">The methods that you use to retrieve collections of them are similar.</span></span> <span data-ttu-id="a2032-112">属性のコレクションの LINQ クエリ式は、要素のコレクションの LINQ クエリ式とよく似ています。</span><span class="sxs-lookup"><span data-stu-id="a2032-112">A LINQ query expression for a collection of attributes looks very similar to a LINQ query expression for a collection of elements.</span></span>  
  
 <span data-ttu-id="a2032-113">属性が要素に追加された順序は保持されます。</span><span class="sxs-lookup"><span data-stu-id="a2032-113">The order in which attributes were added to an element is preserved.</span></span> <span data-ttu-id="a2032-114">つまり、属性を反復処理する場合、属性は追加された順序と同じ順序で表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2032-114">That is, when you iterate through the attributes, you see them in the same order that they were added.</span></span>  
  
## <a name="the-xattribute-constructor"></a><span data-ttu-id="a2032-115">XAttribute コンストラクター</span><span class="sxs-lookup"><span data-stu-id="a2032-115">The XAttribute Constructor</span></span>  
 <span data-ttu-id="a2032-116">最もよく使用する <xref:System.Xml.Linq.XAttribute> クラスのコンストラクターを次に示します。</span><span class="sxs-lookup"><span data-stu-id="a2032-116">The following constructor of the <xref:System.Xml.Linq.XAttribute> class is the one that you will most commonly use:</span></span>  
  
|<span data-ttu-id="a2032-117">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="a2032-117">Constructor</span></span>|<span data-ttu-id="a2032-118">説明</span><span class="sxs-lookup"><span data-stu-id="a2032-118">Description</span></span>|  
|-----------------|-----------------|  
|`XAttribute(XName name, object content)`|<span data-ttu-id="a2032-119"><xref:System.Xml.Linq.XAttribute> オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="a2032-119">Creates an <xref:System.Xml.Linq.XAttribute> object.</span></span> <span data-ttu-id="a2032-120">`name` 引数には属性の名前を指定し、`content` には属性のコンテンツを指定します。</span><span class="sxs-lookup"><span data-stu-id="a2032-120">The `name` argument specifies the name of the attribute; `content` specifies the content of the attribute.</span></span>|  
  
### <a name="creating-an-element-with-an-attribute"></a><span data-ttu-id="a2032-121">属性を持つ要素の作成</span><span class="sxs-lookup"><span data-stu-id="a2032-121">Creating an Element with an Attribute</span></span>  
 <span data-ttu-id="a2032-122">次のコードは、属性を含む要素を作成する一般的なタスクを示しています。</span><span class="sxs-lookup"><span data-stu-id="a2032-122">The following code shows the common task of creating an element that contains an attribute:</span></span>  
  
```csharp  
XElement phone = new XElement("Phone",  
    new XAttribute("Type", "Home"),  
    "555-555-5555");  
Console.WriteLine(phone);  
```  
  
 <span data-ttu-id="a2032-123">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="a2032-123">This example produces the following output:</span></span>  
  
```xml  
<Phone Type="Home">555-555-5555</Phone>  
```  
  
### <a name="functional-construction-of-attributes"></a><span data-ttu-id="a2032-124">属性の関数型構築</span><span class="sxs-lookup"><span data-stu-id="a2032-124">Functional Construction of Attributes</span></span>  
 <span data-ttu-id="a2032-125"><xref:System.Xml.Linq.XAttribute> オブジェクトは、<xref:System.Xml.Linq.XElement> オブジェクトの構築と共にインラインで構築できます。</span><span class="sxs-lookup"><span data-stu-id="a2032-125">You can construct <xref:System.Xml.Linq.XAttribute> objects in-line with the construction of <xref:System.Xml.Linq.XElement> objects, as follows:</span></span>  
  
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
  
 <span data-ttu-id="a2032-126">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="a2032-126">This example produces the following output:</span></span>  
  
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
  
### <a name="attributes-are-not-nodes"></a><span data-ttu-id="a2032-127">属性はノードではない</span><span class="sxs-lookup"><span data-stu-id="a2032-127">Attributes Are Not Nodes</span></span>  
 <span data-ttu-id="a2032-128">属性と要素には、いくつかの違いがあります。</span><span class="sxs-lookup"><span data-stu-id="a2032-128">There are some differences between attributes and elements.</span></span> <span data-ttu-id="a2032-129"><xref:System.Xml.Linq.XAttribute> オブジェクトは、XML ツリーのノードではありません。</span><span class="sxs-lookup"><span data-stu-id="a2032-129"><xref:System.Xml.Linq.XAttribute> objects are not nodes in the XML tree.</span></span> <span data-ttu-id="a2032-130">属性は、XML 要素に関連付けられている名前と値のペアです。</span><span class="sxs-lookup"><span data-stu-id="a2032-130">They are name/value pairs associated with an XML element.</span></span> <span data-ttu-id="a2032-131">ドキュメント オブジェクト モデル (DOM) とは異なり、XML の構造をより密接に反映します。</span><span class="sxs-lookup"><span data-stu-id="a2032-131">In contrast to the Document Object Model (DOM), this more closely reflects the structure of XML.</span></span> <span data-ttu-id="a2032-132"><xref:System.Xml.Linq.XAttribute> オブジェクトは実際には XML ツリーのノードではありませんが、<xref:System.Xml.Linq.XAttribute> オブジェクトの操作は <xref:System.Xml.Linq.XElement> オブジェクトの操作とよく似ています。</span><span class="sxs-lookup"><span data-stu-id="a2032-132">Although <xref:System.Xml.Linq.XAttribute> objects are not actually nodes in the XML tree, working with <xref:System.Xml.Linq.XAttribute> objects is very similar to working with <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="a2032-133">属性と要素の区別は主に、ノード レベルで XML ツリーを操作するコードを記述する開発者にとってのみ重要な意味を持ちます。</span><span class="sxs-lookup"><span data-stu-id="a2032-133">This distinction is primarily important only to developers who are writing code that works with XML trees at the node level.</span></span> <span data-ttu-id="a2032-134">多くの開発者は、この区別を考慮する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a2032-134">Many developers will not be concerned with this distinction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2032-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="a2032-135">See also</span></span>

- [<span data-ttu-id="a2032-136">LINQ to XML プログラミングの概要 (C#)</span><span class="sxs-lookup"><span data-stu-id="a2032-136">LINQ to XML Programming Overview (C#)</span></span>](./linq-to-xml-overview.md)
