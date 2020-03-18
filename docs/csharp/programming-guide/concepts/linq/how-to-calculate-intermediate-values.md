---
title: 中間値を計算する方法 (C#)
ms.date: 07/20/2015
ms.assetid: 7fd3001f-f8f9-4bce-879f-d4c7af8a04fe
ms.openlocfilehash: 3ead3bfb02f7c9192db96996c1f1e01a86a4191a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141447"
---
# <a name="how-to-calculate-intermediate-values-c"></a><span data-ttu-id="af62b-102">中間値を計算する方法 (C#)</span><span class="sxs-lookup"><span data-stu-id="af62b-102">How to calculate intermediate values (C#)</span></span>
<span data-ttu-id="af62b-103">この例では、並べ替え、フィルタリング、および選択を実行する際に使用できる中間値を計算する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="af62b-103">This example shows how to calculate intermediate values that can be used in sorting, filtering, and selecting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af62b-104">例</span><span class="sxs-lookup"><span data-stu-id="af62b-104">Example</span></span>  
 <span data-ttu-id="af62b-105">次の例では、`Let` 句を使用します。</span><span class="sxs-lookup"><span data-stu-id="af62b-105">The following example uses the `Let` clause.</span></span>  
  
 <span data-ttu-id="af62b-106">この例では、「[サンプル XML ファイル: 数値データ (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md)」の XML ドキュメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="af62b-106">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("Data.xml");  
IEnumerable<decimal> extensions =  
    from el in root.Elements("Data")  
    let extension = (decimal)el.Element("Quantity") * (decimal)el.Element("Price")  
    where extension >= 25  
    orderby extension  
    select extension;  
foreach (decimal ex in extensions)  
    Console.WriteLine(ex);  
```  
  
 <span data-ttu-id="af62b-107">このコードを実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="af62b-107">This code produces the following output:</span></span>  
  
```output  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
  
## <a name="example"></a><span data-ttu-id="af62b-108">例</span><span class="sxs-lookup"><span data-stu-id="af62b-108">Example</span></span>  
 <span data-ttu-id="af62b-109">次の例は名前空間に含まれている XML 用のクエリです。これらのクエリは上の例と同じ機能を表しています。</span><span class="sxs-lookup"><span data-stu-id="af62b-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="af62b-110">詳細については、「[名前空間の概要 (LINQ to XML)](namespaces-overview-linq-to-xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af62b-110">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="af62b-111">この例では、「[サンプル XML ファイル: 名前空間内の数値データ](./sample-xml-file-numerical-data-in-a-namespace.md)」の XML ドキュメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="af62b-111">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](./sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("DataInNamespace.xml");  
XNamespace ad = "http://www.adatum.com";  
IEnumerable<decimal> extensions =  
    from el in root.Elements(ad + "Data")  
    let extension = (decimal)el.Element(ad + "Quantity") * (decimal)el.Element(ad + "Price")  
    where extension >= 25  
    orderby extension  
    select extension;  
foreach (decimal ex in extensions)  
    Console.WriteLine(ex);  
```  
  
 <span data-ttu-id="af62b-112">このコードを実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="af62b-112">This code produces the following output:</span></span>  
  
```output  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
