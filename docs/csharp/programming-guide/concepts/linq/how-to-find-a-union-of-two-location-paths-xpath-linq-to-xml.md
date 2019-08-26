---
title: 方法:2 つのロケーション パスの和集合を検索する (XPath-LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 069622d3-2b58-4919-8903-710a564c0788
ms.openlocfilehash: 9fc88a8784958294ba6077893a5d54110de335a0
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69593742"
---
# <a name="how-to-find-a-union-of-two-location-paths-xpath-linq-to-xml-c"></a><span data-ttu-id="919d7-102">方法:2 つのロケーション パスの和集合を検索する (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="919d7-102">How to: Find a Union of Two Location Paths (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="919d7-103">XPath を使用すると、2 つの XPath ロケーション パスの結果の和集合を検索できます。</span><span class="sxs-lookup"><span data-stu-id="919d7-103">XPath allows you to find the union of the results of two XPath location paths.</span></span>  
  
 <span data-ttu-id="919d7-104">XPath 式を次に示します。</span><span class="sxs-lookup"><span data-stu-id="919d7-104">The XPath expression is:</span></span>  
  
 `//Category|//Price`  
  
 <span data-ttu-id="919d7-105"><xref:System.Linq.Enumerable.Concat%2A> 標準クエリ演算子を使用すると、同じ結果を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="919d7-105">You can achieve the same results by using the <xref:System.Linq.Enumerable.Concat%2A> standard query operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="919d7-106">例</span><span class="sxs-lookup"><span data-stu-id="919d7-106">Example</span></span>  
 <span data-ttu-id="919d7-107">この例では、`Category` 要素と `Price` 要素をすべて検索し、それらを 1 つのコレクションに連結します。</span><span class="sxs-lookup"><span data-stu-id="919d7-107">This example finds all of the `Category` elements and all of the `Price` elements, and concatenates them into a single collection.</span></span> <span data-ttu-id="919d7-108">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] クエリで <xref:System.Xml.Linq.Extensions.InDocumentOrder%2A> を呼び出して、結果を並べ替えていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="919d7-108">Note that the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query calls <xref:System.Xml.Linq.Extensions.InDocumentOrder%2A> to order the results.</span></span> <span data-ttu-id="919d7-109">XPath 式の評価結果もドキュメント順になります。</span><span class="sxs-lookup"><span data-stu-id="919d7-109">The results of the XPath expression evaluation are also in document order.</span></span>  
  
 <span data-ttu-id="919d7-110">この例では、次の XML ドキュメントを使用します: 「[サンプル XML ファイル:数値データ (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md)」。</span><span class="sxs-lookup"><span data-stu-id="919d7-110">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument data = XDocument.Load("Data.xml");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 =  
    data  
    .Descendants("Category")  
    .Concat(  
        data  
        .Descendants("Price")  
    )  
    .InDocumentOrder();  
  
// XPath expression  
IEnumerable<XElement> list2 = data.XPathSelectElements("//Category|//Price");  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="919d7-111">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="919d7-111">This example produces the following output:</span></span>  
  
```  
Results are identical  
<Category>A</Category>  
<Price>24.50</Price>  
<Category>B</Category>  
<Price>89.99</Price>  
<Category>A</Category>  
<Price>4.95</Price>  
<Category>A</Category>  
<Price>66.00</Price>  
<Category>B</Category>  
<Price>.99</Price>  
<Category>A</Category>  
<Price>29.00</Price>  
<Category>B</Category>  
<Price>6.99</Price>  
```  
  