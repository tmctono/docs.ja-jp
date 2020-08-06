---
title: 要素を並べ替える方法 (C#)
description: 要素を並べ替える方法について説明します。 XML ドキュメントで、結果を並べ替えるクエリを作成する方法の例を確認します。
ms.date: 07/20/2015
ms.assetid: aee6fbbc-81fd-4b3e-b40f-6ed7b3bd3fee
ms.openlocfilehash: 669d9cf583e6ab70c93be39ad271eaf104f88718
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301438"
---
# <a name="how-to-sort-elements-c"></a><span data-ttu-id="c1bcc-104">要素を並べ替える方法 (C#)</span><span class="sxs-lookup"><span data-stu-id="c1bcc-104">How to sort elements (C#)</span></span>
<span data-ttu-id="c1bcc-105">この例では、結果を並べ替えるクエリの作成方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c1bcc-105">This example shows how to write a query that sorts its results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1bcc-106">例</span><span class="sxs-lookup"><span data-stu-id="c1bcc-106">Example</span></span>  
 <span data-ttu-id="c1bcc-107">この例では、次の XML ドキュメントを使用します: 「[サンプル XML ファイル:数値データ (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md) を使用します。</span><span class="sxs-lookup"><span data-stu-id="c1bcc-107">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="c1bcc-108">このコードを実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="c1bcc-108">This code produces the following output:</span></span>  
  
```output  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="example"></a><span data-ttu-id="c1bcc-109">例</span><span class="sxs-lookup"><span data-stu-id="c1bcc-109">Example</span></span>  
 <span data-ttu-id="c1bcc-110">次の例は名前空間に含まれている XML 用のクエリです。これらのクエリは上の例と同じ機能を表しています。</span><span class="sxs-lookup"><span data-stu-id="c1bcc-110">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="c1bcc-111">詳細については、「[名前空間の概要 (LINQ to XML)](namespaces-overview-linq-to-xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1bcc-111">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="c1bcc-112">この例では、次の XML ドキュメントを使用します: 「[サンプル XML ファイル:名前空間内の数値データ](./sample-xml-file-numerical-data-in-a-namespace.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="c1bcc-112">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](./sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
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
  
 <span data-ttu-id="c1bcc-113">このコードを実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="c1bcc-113">This code produces the following output:</span></span>  
  
```output  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="see-also"></a><span data-ttu-id="c1bcc-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="c1bcc-114">See also</span></span>

- [<span data-ttu-id="c1bcc-115">データの並べ替え (C#)</span><span class="sxs-lookup"><span data-stu-id="c1bcc-115">Sorting Data (C#)</span></span>](./sorting-data.md)
