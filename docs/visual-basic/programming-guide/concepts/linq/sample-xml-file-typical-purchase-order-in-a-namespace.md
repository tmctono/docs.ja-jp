---
title: サンプル XML ファイル:名前空間内の一般的な購買発注書 3
ms.date: 07/20/2015
ms.assetid: 38260901-c9f9-4240-9cbf-652c8b05021d
ms.openlocfilehash: e753d0a4d6bea3e4a01221258e1f5de3862c4ecb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84360840"
---
# <a name="sample-xml-file-typical-purchase-order-in-a-namespace"></a><span data-ttu-id="65bba-102">サンプル XML ファイル:名前空間内の一般的な購買発注書</span><span class="sxs-lookup"><span data-stu-id="65bba-102">Sample XML File: Typical Purchase Order in a Namespace</span></span>
<span data-ttu-id="65bba-103">次の XML ファイルは、[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ドキュメントのさまざまな例で使用されます。</span><span class="sxs-lookup"><span data-stu-id="65bba-103">The following XML file is used in various examples in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] documentation.</span></span> <span data-ttu-id="65bba-104">このファイルは、一般的な購買発注書です。</span><span class="sxs-lookup"><span data-stu-id="65bba-104">This file is a typical purchase order.</span></span> <span data-ttu-id="65bba-105">XML は名前空間に含まれています。</span><span class="sxs-lookup"><span data-stu-id="65bba-105">The XML is in a namespace.</span></span>  
  
## <a name="purchaseorderinnamespacexml"></a><span data-ttu-id="65bba-106">PurchaseOrderInNamespace.xml</span><span class="sxs-lookup"><span data-stu-id="65bba-106">PurchaseOrderInNamespace.xml</span></span>  
  
```xml  
<?xml version="1.0"?>  
<aw:PurchaseOrder  
    aw:PurchaseOrderNumber="99503"  
    aw:OrderDate="1999-10-20"  
    xmlns:aw="http://www.adventure-works.com">  
  <aw:Address aw:Type="Shipping">  
    <aw:Name>Ellen Adams</aw:Name>  
    <aw:Street>123 Maple Street</aw:Street>  
    <aw:City>Mill Valley</aw:City>  
    <aw:State>CA</aw:State>  
    <aw:Zip>10999</aw:Zip>  
    <aw:Country>USA</aw:Country>  
  </aw:Address>  
  <aw:Address aw:Type="Billing">  
    <aw:Name>Tai Yee</aw:Name>  
    <aw:Street>8 Oak Avenue</aw:Street>  
    <aw:City>Old Town</aw:City>  
    <aw:State>PA</aw:State>  
    <aw:Zip>95819</aw:Zip>  
    <aw:Country>USA</aw:Country>  
  </aw:Address>  
  <aw:DeliveryNotes>Please leave packages in shed by driveway.</aw:DeliveryNotes>  
  <aw:Items>  
    <aw:Item aw:PartNumber="872-AA">  
      <aw:ProductName>Lawnmower</aw:ProductName>  
      <aw:Quantity>1</aw:Quantity>  
      <aw:USPrice>148.95</aw:USPrice>  
      <aw:Comment>Confirm this is electric</aw:Comment>  
    </aw:Item>  
    <aw:Item aw:PartNumber="926-AA">  
      <aw:ProductName>Baby Monitor</aw:ProductName>  
      <aw:Quantity>2</aw:Quantity>  
      <aw:USPrice>39.98</aw:USPrice>  
      <aw:ShipDate>1999-05-21</aw:ShipDate>  
    </aw:Item>  
  </aw:Items>  
</aw:PurchaseOrder>  
```  
  
## <a name="see-also"></a><span data-ttu-id="65bba-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="65bba-107">See also</span></span>

- [<span data-ttu-id="65bba-108">サンプル XML ドキュメント (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="65bba-108">Sample XML Documents (LINQ to XML)</span></span>](sample-xml-documents-linq-to-xml.md)
