---
title: 名前空間内の要素を検索する方法 (XPath-LINQ to XML) (C#)
description: XPath 式を使用して名前空間内の要素を検索する方法について説明します。 2 つの名前空間を含む XML ツリーを読み取る例をご覧ください。
ms.date: 07/20/2015
ms.assetid: cae1c4ac-6cd5-46cf-9b1c-bd85bc9b7ea9
ms.openlocfilehash: 3bf15c4183e3ca339fa7090c21baff83526e37d3
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303232"
---
# <a name="how-to-find-elements-in-a-namespace-xpath-linq-to-xml-c"></a><span data-ttu-id="565c4-104">名前空間内の要素を検索する方法 (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="565c4-104">How to find elements in a namespace (XPath-LINQ to XML) (C#)</span></span>

<span data-ttu-id="565c4-105">XPath 式を使用すると、特定の名前空間内のノードを検索できます。</span><span class="sxs-lookup"><span data-stu-id="565c4-105">XPath expressions can find nodes in a particular namespace.</span></span> <span data-ttu-id="565c4-106">XPath 式では、名前空間を指定する名前空間プレフィックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="565c4-106">XPath expressions use namespace prefixes for specifying namespaces.</span></span> <span data-ttu-id="565c4-107">名前空間プレフィックスを含む XPath 式を解析するには、<xref:System.Xml.IXmlNamespaceResolver> を実装する XPath メソッドにオブジェクトを渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="565c4-107">To parse an XPath expression that contains namespace prefixes, you must pass an object to the XPath methods that implements <xref:System.Xml.IXmlNamespaceResolver>.</span></span> <span data-ttu-id="565c4-108">この例では <xref:System.Xml.XmlNamespaceManager> を使用します。</span><span class="sxs-lookup"><span data-stu-id="565c4-108">This example uses <xref:System.Xml.XmlNamespaceManager>.</span></span>

<span data-ttu-id="565c4-109">XPath 式を次に示します。</span><span class="sxs-lookup"><span data-stu-id="565c4-109">The XPath expression is:</span></span>

`./aw:*`

## <a name="example"></a><span data-ttu-id="565c4-110">例</span><span class="sxs-lookup"><span data-stu-id="565c4-110">Example</span></span>

<span data-ttu-id="565c4-111">次の例では、2 つの名前空間を含む XML ツリーを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="565c4-111">The following example reads an XML tree that contains two namespaces.</span></span> <span data-ttu-id="565c4-112"><xref:System.Xml.XmlReader> を使用して XML ドキュメントを読み込ます。</span><span class="sxs-lookup"><span data-stu-id="565c4-112">It uses an <xref:System.Xml.XmlReader> to read the XML document.</span></span> <span data-ttu-id="565c4-113">次に、<xref:System.Xml.XmlNameTable> から <xref:System.Xml.XmlReader> を取得し、<xref:System.Xml.XmlNamespaceManager> から <xref:System.Xml.XmlNameTable> を取得します。</span><span class="sxs-lookup"><span data-stu-id="565c4-113">It then gets an <xref:System.Xml.XmlNameTable> from the <xref:System.Xml.XmlReader>, and an <xref:System.Xml.XmlNamespaceManager> from the <xref:System.Xml.XmlNameTable>.</span></span> <span data-ttu-id="565c4-114">要素を選択する際には <xref:System.Xml.XmlNamespaceManager> を使用します。</span><span class="sxs-lookup"><span data-stu-id="565c4-114">It uses the <xref:System.Xml.XmlNamespaceManager> when selecting elements.</span></span>

```csharp
XmlReader reader = XmlReader.Create("ConsolidatedPurchaseOrders.xml");
XElement root = XElement.Load(reader);
XmlNameTable nameTable = reader.NameTable;
XmlNamespaceManager namespaceManager = new XmlNamespaceManager(nameTable);
namespaceManager.AddNamespace("aw", "http://www.adventure-works.com");
IEnumerable<XElement> list1 = root.XPathSelectElements("./aw:*", namespaceManager);
IEnumerable<XElement> list2 =
    from el in root.Elements()
    where el.Name.Namespace == "http://www.adventure-works.com"
    select el;
if (list1.Count() == list2.Count() &&
        list1.Intersect(list2).Count() == list1.Count())
    Console.WriteLine("Results are identical");
else
    Console.WriteLine("Results differ");
foreach (XElement el in list2)
    Console.WriteLine(el);
```

<span data-ttu-id="565c4-115">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="565c4-115">This example produces the following output:</span></span>

```output
Results are identical
<aw:PurchaseOrder PONumber="11223" Date="2000-01-15" xmlns:aw="http://www.adventure-works.com">
    <aw:ShippingAddress>
      <aw:Name>Chris Preston</aw:Name>
      <aw:Street>123 Main St.</aw:Street>
      <aw:City>Seattle</aw:City>
      <aw:State>WA</aw:State>
      <aw:Zip>98113</aw:Zip>
      <aw:Country>USA</aw:Country>
    </aw:ShippingAddress>
    <aw:BillingAddress>
      <aw:Name>Chris Preston</aw:Name>
      <aw:Street>123 Main St.</aw:Street>
      <aw:City>Seattle</aw:City>
      <aw:State>WA</aw:State>
      <aw:Zip>98113</aw:Zip>
      <aw:Country>USA</aw:Country>
    </aw:BillingAddress>
    <aw:DeliveryInstructions>Ship only complete order.</aw:DeliveryInstructions>
    <aw:Item PartNum="LIT-01">
      <aw:ProductID>Litware Networking Card</aw:ProductID>
      <aw:Qty>1</aw:Qty>
      <aw:Price>20.99</aw:Price>
    </aw:Item>
    <aw:Item PartNum="LIT-25">
      <aw:ProductID>Litware 17in LCD Monitor</aw:ProductID>
      <aw:Qty>1</aw:Qty>
      <aw:Price>199.99</aw:Price>
    </aw:Item>
  </aw:PurchaseOrder>
```
