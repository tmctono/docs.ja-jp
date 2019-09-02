---
title: '方法: 中間値を計算する (C#)'
ms.date: 07/20/2015
ms.assetid: 7fd3001f-f8f9-4bce-879f-d4c7af8a04fe
ms.openlocfilehash: fe3f992e85b3fb508fced943e1428a4fb6ae2490
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205380"
---
# <a name="how-to-calculate-intermediate-values-c"></a><span data-ttu-id="e569e-102">方法: 中間値を計算する (C#)</span><span class="sxs-lookup"><span data-stu-id="e569e-102">How to: Calculate Intermediate Values (C#)</span></span>
<span data-ttu-id="e569e-103">この例では、並べ替え、フィルタリング、および選択を実行する際に使用できる中間値を計算する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e569e-103">This example shows how to calculate intermediate values that can be used in sorting, filtering, and selecting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e569e-104">例</span><span class="sxs-lookup"><span data-stu-id="e569e-104">Example</span></span>  
 <span data-ttu-id="e569e-105">次の例では、`Let` 句を使用します。</span><span class="sxs-lookup"><span data-stu-id="e569e-105">The following example uses the `Let` clause.</span></span>  
  
 <span data-ttu-id="e569e-106">この例では、XML ドキュメント、「[サンプル XML ファイル:数値データ (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md) を使用します。</span><span class="sxs-lookup"><span data-stu-id="e569e-106">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="e569e-107">このコードを実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="e569e-107">This code produces the following output:</span></span>  
  
```output  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
  
## <a name="example"></a><span data-ttu-id="e569e-108">例</span><span class="sxs-lookup"><span data-stu-id="e569e-108">Example</span></span>  
 <span data-ttu-id="e569e-109">次の例は名前空間に含まれている XML 用のクエリです。これらのクエリは上の例と同じ機能を表しています。</span><span class="sxs-lookup"><span data-stu-id="e569e-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="e569e-110">詳細については、「[名前空間の概要 (LINQ to XML)](namespaces-overview-linq-to-xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e569e-110">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="e569e-111">この例では、次の XML ドキュメントを使用します: [サンプル XML ファイル: 名前空間内の数値データ](./sample-xml-file-numerical-data-in-a-namespace.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="e569e-111">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](./sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
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
  
 <span data-ttu-id="e569e-112">このコードを実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="e569e-112">This code produces the following output:</span></span>  
  
```output  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
