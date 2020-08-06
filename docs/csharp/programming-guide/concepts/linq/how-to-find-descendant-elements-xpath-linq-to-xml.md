---
title: 子孫要素を検索する方法 (XPath-LINQ to XML) (C#)
description: XPath 式を使用して、特定の名前を持つ子孫要素を検索する方法について説明します。 サンプル XML ファイルを使用するコード例を確認します。
ms.date: 07/20/2015
ms.assetid: b318da39-bb8b-4c56-a019-e13b12b01831
ms.openlocfilehash: c5a998a05f866203f3b684b8847a4a5647c12e5b
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303271"
---
# <a name="how-to-find-descendant-elements-xpath-linq-to-xml-c"></a><span data-ttu-id="3bf26-104">子孫要素を検索する方法 (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="3bf26-104">How to find descendant elements (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="3bf26-105">このトピックでは、特定の名前を指定して子孫要素を取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3bf26-105">This topic shows how to get the descendant elements with a particular name.</span></span>  
  
 <span data-ttu-id="3bf26-106">XPath 式は `//Name` です。</span><span class="sxs-lookup"><span data-stu-id="3bf26-106">The XPath expression is `//Name`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3bf26-107">例</span><span class="sxs-lookup"><span data-stu-id="3bf26-107">Example</span></span>  
 <span data-ttu-id="3bf26-108">この例では、`Name` という名前の子孫要素をすべて検索します。</span><span class="sxs-lookup"><span data-stu-id="3bf26-108">This example finds all descendants named `Name`.</span></span>  
  
 <span data-ttu-id="3bf26-109">この例では、次の XML ドキュメントを使用します: 「[サンプル XML ファイル:複数の購買発注書 (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="3bf26-109">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="3bf26-110">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="3bf26-110">This example produces the following output:</span></span>  
  
```output  
Results are identical  
<Name>Ellen Adams</Name>  
<Name>Tai Yee</Name>  
<Name>Cristian Osorio</Name>  
<Name>Cristian Osorio</Name>  
<Name>Jessica Arnold</Name>  
<Name>Jessica Arnold</Name>  
```  
