---
title: 方法:要素を並べ替える (C#)
ms.date: 07/20/2015
ms.assetid: aee6fbbc-81fd-4b3e-b40f-6ed7b3bd3fee
ms.openlocfilehash: 074428413fa57d8f0e5ae94970c2aeeeb9e4cc7c
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69592457"
---
# <a name="how-to-sort-elements-c"></a><span data-ttu-id="e3085-102">方法:要素を並べ替える (C#)</span><span class="sxs-lookup"><span data-stu-id="e3085-102">How to: Sort Elements (C#)</span></span>
<span data-ttu-id="e3085-103">この例では、結果を並べ替えるクエリの作成方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e3085-103">This example shows how to write a query that sorts its results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e3085-104">例</span><span class="sxs-lookup"><span data-stu-id="e3085-104">Example</span></span>  
 <span data-ttu-id="e3085-105">この例では、次の XML ドキュメントを使用します: 「[サンプル XML ファイル:数値データ (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md) を使用します。</span><span class="sxs-lookup"><span data-stu-id="e3085-105">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("Data.xml");  
IEnumerable<decimal> prices =  
    from el in root.Elements("Data")  
    let price = (decimal)el.Element("Price")  
    orderby price  
    select price;  
foreach (decimal el in prices)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="e3085-106">このコードを実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="e3085-106">This code produces the following output:</span></span>  
  
```  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="example"></a><span data-ttu-id="e3085-107">例</span><span class="sxs-lookup"><span data-stu-id="e3085-107">Example</span></span>  
 <span data-ttu-id="e3085-108">次の例は名前空間に含まれている XML 用のクエリです。これらのクエリは上の例と同じ機能を表しています。</span><span class="sxs-lookup"><span data-stu-id="e3085-108">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="e3085-109">詳細については、「[名前空間の概要 (LINQ to XML)](namespaces-overview-linq-to-xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3085-109">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="e3085-110">この例では、次の XML ドキュメントを使用します: [サンプル XML ファイル: 名前空間内の数値データ](./sample-xml-file-numerical-data-in-a-namespace.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="e3085-110">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](./sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("DataInNamespace.xml");  
XNamespace aw = "http://www.adatum.com";  
IEnumerable<decimal> prices =  
    from el in root.Elements(aw + "Data")  
    let price = (decimal)el.Element(aw + "Price")  
    orderby price  
    select price;  
foreach (decimal el in prices)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="e3085-111">このコードを実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="e3085-111">This code produces the following output:</span></span>  
  
```  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="see-also"></a><span data-ttu-id="e3085-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="e3085-112">See also</span></span>

- [<span data-ttu-id="e3085-113">データの並べ替え (C#)</span><span class="sxs-lookup"><span data-stu-id="e3085-113">Sorting Data (C#)</span></span>](./sorting-data.md)
