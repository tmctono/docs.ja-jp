---
title: ルート要素を検索する方法 (XPath-LINQ to XML) (C#)
description: この C# の例では、サンプル XML ドキュメントのルート要素を取得する方法で XPath と LINQ to XML を比較します。
ms.date: 07/20/2015
ms.assetid: 4fd824e0-4d39-429b-b092-f6a5c046ee6c
ms.openlocfilehash: 220899823210c5cd6e9834541ca87e4d8394b4ff
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105184"
---
# <a name="how-to-find-the-root-element-xpath-linq-to-xml-c"></a><span data-ttu-id="ba9ca-103">ルート要素を検索する方法 (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="ba9ca-103">How to find the root element (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="ba9ca-104">このトピックでは、XPath および [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] を使用してルート要素を取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ba9ca-104">This topic shows how to get the root element with XPath and [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
 <span data-ttu-id="ba9ca-105">XPath 式を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ba9ca-105">The XPath expression is:</span></span>  
  
 `/PurchaseOrders`  
  
## <a name="example"></a><span data-ttu-id="ba9ca-106">例</span><span class="sxs-lookup"><span data-stu-id="ba9ca-106">Example</span></span>  
 <span data-ttu-id="ba9ca-107">この例では、ルート要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="ba9ca-107">This example finds the root element.</span></span>  
  
 <span data-ttu-id="ba9ca-108">この例では、次の XML ドキュメントを使用します: 「[サンプル XML ファイル:複数の購買発注書 (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="ba9ca-108">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
// LINQ to XML query  
XElement el1 = po.Root;  
  
// XPath expression  
XElement el2 = po.XPathSelectElement("/PurchaseOrders");  
  
if (el1 == el2)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(el1.Name);  
```  
  
 <span data-ttu-id="ba9ca-109">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="ba9ca-109">This example produces the following output:</span></span>  
  
```output  
Results are identical  
PurchaseOrders  
```  
