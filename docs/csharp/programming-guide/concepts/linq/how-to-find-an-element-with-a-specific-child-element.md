---
title: 特定の子要素を持つ要素を検索する方法 (C#)
ms.date: 07/20/2015
ms.assetid: 00cf5555-374e-4369-bf93-7bd2e7f21db3
ms.openlocfilehash: 0536b1b92d4d7fc18b5d406bbcd24aefc6a840c6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141147"
---
# <a name="how-to-find-an-element-with-a-specific-child-element-c"></a><span data-ttu-id="fc1d8-102">特定の子要素を持つ要素を検索する方法 (C#)</span><span class="sxs-lookup"><span data-stu-id="fc1d8-102">How to find an element with a specific child element (C#)</span></span>
<span data-ttu-id="fc1d8-103">このトピックでは、特定の値を含む子要素を持つ特定の要素を検索する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fc1d8-103">This topic shows how to find a particular element that has a child element with a specific value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc1d8-104">例</span><span class="sxs-lookup"><span data-stu-id="fc1d8-104">Example</span></span>  
 <span data-ttu-id="fc1d8-105">この例では、"Examp2.EXE" の値を含む `Test` 子要素を持つ `CommandLine` 要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="fc1d8-105">The example finds the `Test` element that has a `CommandLine` child element with the value of "Examp2.EXE".</span></span>  
  
 <span data-ttu-id="fc1d8-106">この例では、「[サンプル XML ファイル: テスト構成 (LINQ to XML)](./sample-xml-file-test-configuration-linq-to-xml.md)」の XML ドキュメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="fc1d8-106">This example uses the following XML document: [Sample XML File: Test Configuration (LINQ to XML)](./sample-xml-file-test-configuration-linq-to-xml.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("TestConfig.xml");  
IEnumerable<XElement> tests =  
    from el in root.Elements("Test")  
    where (string)el.Element("CommandLine") == "Examp2.EXE"  
    select el;  
foreach (XElement el in tests)  
    Console.WriteLine((string)el.Attribute("TestId"));  
```  
  
 <span data-ttu-id="fc1d8-107">このコードを実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="fc1d8-107">This code produces the following output:</span></span>  
  
```output  
0002  
0006  
```  
  
## <a name="example"></a><span data-ttu-id="fc1d8-108">例</span><span class="sxs-lookup"><span data-stu-id="fc1d8-108">Example</span></span>  
 <span data-ttu-id="fc1d8-109">次の例は名前空間に含まれている XML 用のクエリです。これらのクエリは上の例と同じ機能を表しています。</span><span class="sxs-lookup"><span data-stu-id="fc1d8-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="fc1d8-110">詳細については、「[名前空間の概要 (LINQ to XML)](namespaces-overview-linq-to-xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc1d8-110">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="fc1d8-111">この例では、「[サンプル XML ファイル : 名前空間内のテスト構成](./sample-xml-file-test-configuration-in-a-namespace1.md)」の XML ドキュメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="fc1d8-111">This example uses the following XML document: [Sample XML File: Test Configuration in a Namespace](./sample-xml-file-test-configuration-in-a-namespace1.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("TestConfigInNamespace.xml");  
XNamespace ad = "http://www.adatum.com";  
IEnumerable<XElement> tests =  
    from el in root.Elements(ad + "Test")  
    where (string)el.Element(ad + "CommandLine") == "Examp2.EXE"  
    select el;  
foreach (XElement el in tests)  
    Console.WriteLine((string)el.Attribute("TestId"));  
```  
  
 <span data-ttu-id="fc1d8-112">このコードを実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="fc1d8-112">This code produces the following output:</span></span>  
  
```output  
0002  
0006  
```  
  
## <a name="see-also"></a><span data-ttu-id="fc1d8-113">参照</span><span class="sxs-lookup"><span data-stu-id="fc1d8-113">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [<span data-ttu-id="fc1d8-114">標準クエリ演算子の概要 (C#)</span><span class="sxs-lookup"><span data-stu-id="fc1d8-114">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="fc1d8-115">射影操作 (C#)</span><span class="sxs-lookup"><span data-stu-id="fc1d8-115">Projection Operations (C#)</span></span>](./projection-operations.md)
