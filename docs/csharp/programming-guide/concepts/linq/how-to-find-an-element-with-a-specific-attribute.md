---
title: 特定の属性を持つ要素を検索する方法 (C#)
ms.date: 07/20/2015
ms.assetid: b92591aa-3cfb-490e-99f6-da8de335e362
ms.openlocfilehash: 106885b8658c493caab3101e6b4ce921589076eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141164"
---
# <a name="how-to-find-an-element-with-a-specific-attribute-c"></a><span data-ttu-id="edfa0-102">特定の属性を持つ要素を検索する方法 (C#)</span><span class="sxs-lookup"><span data-stu-id="edfa0-102">How to find an element with a specific attribute (C#)</span></span>
<span data-ttu-id="edfa0-103">このトピックでは、特定の値を含む属性を持つ要素を検索する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="edfa0-103">This topic shows how to find an element that has an attribute that has a specific value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="edfa0-104">例</span><span class="sxs-lookup"><span data-stu-id="edfa0-104">Example</span></span>  
 <span data-ttu-id="edfa0-105">この例では、"Billing" の値を含む `Address` 属性を持つ `Type` 要素を検索する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="edfa0-105">The example shows how to find the `Address` element that has a `Type` attribute with a value of "Billing".</span></span>  
  
 <span data-ttu-id="edfa0-106">この例では、「[サンプル XML ファイル: 一般的な購買発注書 (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md)」の XML ドキュメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="edfa0-106">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("PurchaseOrder.xml");  
IEnumerable<XElement> address =  
    from el in root.Elements("Address")  
    where (string)el.Attribute("Type") == "Billing"  
    select el;  
foreach (XElement el in address)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="edfa0-107">このコードを実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="edfa0-107">This code produces the following output:</span></span>  
  
```xml  
<Address Type="Billing">  
  <Name>Tai Yee</Name>  
  <Street>8 Oak Avenue</Street>  
  <City>Old Town</City>  
  <State>PA</State>  
  <Zip>95819</Zip>  
  <Country>USA</Country>  
</Address>  
```  
  
## <a name="example"></a><span data-ttu-id="edfa0-108">例</span><span class="sxs-lookup"><span data-stu-id="edfa0-108">Example</span></span>  
 <span data-ttu-id="edfa0-109">次の例は名前空間に含まれている XML 用のクエリです。これらのクエリは上の例と同じ機能を表しています。</span><span class="sxs-lookup"><span data-stu-id="edfa0-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="edfa0-110">詳細については、「[名前空間の概要 (LINQ to XML)](namespaces-overview-linq-to-xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edfa0-110">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="edfa0-111">この例では、XML ドキュメントの「[サンプル XML ファイル : 名前空間内の一般的な購買発注書](./sample-xml-file-typical-purchase-order-in-a-namespace.md)」を使用します。</span><span class="sxs-lookup"><span data-stu-id="edfa0-111">This example uses the following XML document: [Sample XML File: Typical Purchase Order in a Namespace](./sample-xml-file-typical-purchase-order-in-a-namespace.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("PurchaseOrderInNamespace.xml");  
XNamespace aw = "http://www.adventure-works.com";  
IEnumerable<XElement> address =  
    from el in root.Elements(aw + "Address")  
    where (string)el.Attribute(aw + "Type") == "Billing"  
    select el;  
foreach (XElement el in address)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="edfa0-112">このコードを実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="edfa0-112">This code produces the following output:</span></span>  
  
```xml  
<aw:Address aw:Type="Billing" xmlns:aw="http://www.adventure-works.com">  
  <aw:Name>Tai Yee</aw:Name>  
  <aw:Street>8 Oak Avenue</aw:Street>  
  <aw:City>Old Town</aw:City>  
  <aw:State>PA</aw:State>  
  <aw:Zip>95819</aw:Zip>  
  <aw:Country>USA</aw:Country>  
</aw:Address>  
```  
  
## <a name="see-also"></a><span data-ttu-id="edfa0-113">参照</span><span class="sxs-lookup"><span data-stu-id="edfa0-113">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [<span data-ttu-id="edfa0-114">標準クエリ演算子の概要 (C#)</span><span class="sxs-lookup"><span data-stu-id="edfa0-114">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="edfa0-115">射影操作 (C#)</span><span class="sxs-lookup"><span data-stu-id="edfa0-115">Projection Operations (C#)</span></span>](./projection-operations.md)
