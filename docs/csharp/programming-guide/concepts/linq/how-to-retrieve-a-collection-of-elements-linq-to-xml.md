---
title: 要素のコレクションを取得する方法 (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: b849668c-7976-4974-b8e1-1cd587d34258
ms.openlocfilehash: 89799b17115fb56a93bda5fbc144b21b334a6974
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "75345020"
---
# <a name="how-to-retrieve-a-collection-of-elements-linq-to-xml-c"></a><span data-ttu-id="48b5a-102">要素のコレクションを取得する方法 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="48b5a-102">How to retrieve a collection of elements (LINQ to XML) (C#)</span></span>
<span data-ttu-id="48b5a-103">このトピックでは、<xref:System.Xml.Linq.XContainer.Elements%2A> メソッドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="48b5a-103">This topic demonstrates the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span> <span data-ttu-id="48b5a-104">このメソッドは、要素の子要素のコレクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="48b5a-104">This method retrieves a collection of the child elements of an element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="48b5a-105">例</span><span class="sxs-lookup"><span data-stu-id="48b5a-105">Example</span></span>  
 <span data-ttu-id="48b5a-106">この例では、`purchaseOrder` 要素の子要素を反復処理します。</span><span class="sxs-lookup"><span data-stu-id="48b5a-106">This example iterates through the child elements of the `purchaseOrder` element.</span></span>  
  
 <span data-ttu-id="48b5a-107">この例では、「[サンプル XML ファイル: 一般的な購買発注書 (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md)」の XML ドキュメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="48b5a-107">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
XElement po = XElement.Load("PurchaseOrder.xml");  
IEnumerable<XElement> childElements =  
    from el in po.Elements()  
    select el;  
foreach (XElement el in childElements)  
    Console.WriteLine("Name: " + el.Name);  
```  
  
 <span data-ttu-id="48b5a-108">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="48b5a-108">This example produces the following output.</span></span>  
  
```output  
Name: Address  
Name: Address  
Name: DeliveryNotes  
Name: Items  
```  
  
## <a name="see-also"></a><span data-ttu-id="48b5a-109">参照</span><span class="sxs-lookup"><span data-stu-id="48b5a-109">See also</span></span>

- [<span data-ttu-id="48b5a-110">LINQ to XML 軸 (C#)</span><span class="sxs-lookup"><span data-stu-id="48b5a-110">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
