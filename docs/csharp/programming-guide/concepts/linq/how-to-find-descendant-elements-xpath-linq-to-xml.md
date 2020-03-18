---
title: 子孫要素を検索する方法 (XPath-LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: b318da39-bb8b-4c56-a019-e13b12b01831
ms.openlocfilehash: c90651502629284c67cc16de8a1aa59c392ae178
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141105"
---
# <a name="how-to-find-descendant-elements-xpath-linq-to-xml-c"></a><span data-ttu-id="80a53-102">子孫要素を検索する方法 (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="80a53-102">How to find descendant elements (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="80a53-103">このトピックでは、特定の名前を指定して子孫要素を取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="80a53-103">This topic shows how to get the descendant elements with a particular name.</span></span>  
  
 <span data-ttu-id="80a53-104">XPath 式は `//Name` です。</span><span class="sxs-lookup"><span data-stu-id="80a53-104">The XPath expression is `//Name`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80a53-105">例</span><span class="sxs-lookup"><span data-stu-id="80a53-105">Example</span></span>  
 <span data-ttu-id="80a53-106">この例では、`Name` という名前の子孫要素をすべて検索します。</span><span class="sxs-lookup"><span data-stu-id="80a53-106">This example finds all descendants named `Name`.</span></span>  
  
 <span data-ttu-id="80a53-107">この例では、「[サンプル XML ファイル: 複数の購買発注書 (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md)」の XML ドキュメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="80a53-107">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 = po.Root.Descendants("Name");  
  
// XPath expression  
IEnumerable<XElement> list2 = po.XPathSelectElements("//Name");  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="80a53-108">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="80a53-108">This example produces the following output:</span></span>  
  
```output  
Results are identical  
<Name>Ellen Adams</Name>  
<Name>Tai Yee</Name>  
<Name>Cristian Osorio</Name>  
<Name>Cristian Osorio</Name>  
<Name>Jessica Arnold</Name>  
<Name>Jessica Arnold</Name>  
```  
