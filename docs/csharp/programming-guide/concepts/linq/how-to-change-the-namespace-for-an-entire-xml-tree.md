---
title: XML ツリー全体の名前空間を変更する方法 (C#)
ms.date: 07/20/2015
ms.assetid: 1584ff3b-c77d-4241-ab62-80adfb7bfc1b
ms.openlocfilehash: 6462cbb5001682b6a464c1446f8ae6de3c5669d1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141512"
---
# <a name="how-to-change-the-namespace-for-an-entire-xml-tree-c"></a><span data-ttu-id="5caa8-102">XML ツリー全体の名前空間を変更する方法 (C#)</span><span class="sxs-lookup"><span data-stu-id="5caa8-102">How to change the namespace for an entire XML tree (C#)</span></span>
<span data-ttu-id="5caa8-103">要素または属性の名前空間をプログラムで変更しなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="5caa8-103">You sometimes have to programmatically change the namespace for an element or an attribute.</span></span> <span data-ttu-id="5caa8-104">LINQ to XML では、この操作を簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5caa8-104">LINQ to XML makes this easy.</span></span> <span data-ttu-id="5caa8-105"><xref:System.Xml.Linq.XElement.Name%2A?displayProperty=nameWithType> プロパティを設定できます。</span><span class="sxs-lookup"><span data-stu-id="5caa8-105">The <xref:System.Xml.Linq.XElement.Name%2A?displayProperty=nameWithType> property can be set.</span></span> <span data-ttu-id="5caa8-106"><xref:System.Xml.Linq.XAttribute.Name%2A?displayProperty=nameWithType> プロパティは設定できませんが、簡単に属性を <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> にコピーし、既存の属性を削除して、目的の新しい名前空間に含まれる新しい属性を追加できます。</span><span class="sxs-lookup"><span data-stu-id="5caa8-106">The <xref:System.Xml.Linq.XAttribute.Name%2A?displayProperty=nameWithType> property cannot be set, but you can easily copy the attributes into a <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>, remove the existing attributes, and then add new attributes that are in the new desired namespace.</span></span>  
  
 <span data-ttu-id="5caa8-107">詳細については、「[名前空間の概要 (LINQ to XML)](namespaces-overview-linq-to-xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5caa8-107">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5caa8-108">例</span><span class="sxs-lookup"><span data-stu-id="5caa8-108">Example</span></span>  
 <span data-ttu-id="5caa8-109">次のコードは、名前空間に含まれない 2 つの XML ツリーを作成します。</span><span class="sxs-lookup"><span data-stu-id="5caa8-109">The following code creates two XML trees in no namespace.</span></span> <span data-ttu-id="5caa8-110">次に、各ツリーの名前空間を変更して、1 つのツリーに結合します。</span><span class="sxs-lookup"><span data-stu-id="5caa8-110">It then changes the namespace of each of the trees, and combines them into a single tree.</span></span>  
  
```csharp  
XElement tree1 = new XElement("Data",  
    new XElement("Child", "content",  
        new XAttribute("MyAttr", "content")  
    )  
);  
XElement tree2 = new XElement("Data",  
    new XElement("Child", "content",  
        new XAttribute("MyAttr", "content")  
    )  
);  
XNamespace aw = "http://www.adventure-works.com";  
XNamespace ad = "http://www.adatum.com";  
// change the namespace of every element and attribute in the first tree  
foreach (XElement el in tree1.DescendantsAndSelf())  
{  
    el.Name = aw.GetName(el.Name.LocalName);  
    List<XAttribute> atList = el.Attributes().ToList();  
    el.Attributes().Remove();  
    foreach (XAttribute at in atList)  
        el.Add(new XAttribute(aw.GetName(at.Name.LocalName), at.Value));  
}  
// change the namespace of every element and attribute in the second tree  
foreach (XElement el in tree2.DescendantsAndSelf())  
{  
    el.Name = ad.GetName(el.Name.LocalName);  
    List<XAttribute> atList = el.Attributes().ToList();  
    el.Attributes().Remove();  
    foreach (XAttribute at in atList)  
        el.Add(new XAttribute(ad.GetName(at.Name.LocalName), at.Value));  
}  
// add attribute namespaces so that the tree will be serialized with  
// the aw and ad namespace prefixes  
tree1.Add(  
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com")  
);  
tree2.Add(  
    new XAttribute(XNamespace.Xmlns + "ad", "http://www.adatum.com")  
);  
// create a new composite tree  
XElement root = new XElement("Root",  
    tree1,  
    tree2  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="5caa8-111">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="5caa8-111">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <aw:Data xmlns:aw="http://www.adventure-works.com">  
    <aw:Child aw:MyAttr="content">content</aw:Child>  
  </aw:Data>  
  <ad:Data xmlns:ad="http://www.adatum.com">  
    <ad:Child ad:MyAttr="content">content</ad:Child>  
  </ad:Data>  
</Root>  
```  
