---
title: 方法:単一の子要素を取得する (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: ce37db9e-76fa-46eb-b4cc-e8f32d22ad90
ms.openlocfilehash: 5f2f675f5ce4914124f62981a2591441260b6976
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69592627"
---
# <a name="how-to-retrieve-a-single-child-element-linq-to-xml-c"></a><span data-ttu-id="6b9b1-102">方法:単一の子要素を取得する (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="6b9b1-102">How to: Retrieve a Single Child Element (LINQ to XML) (C#)</span></span>
<span data-ttu-id="6b9b1-103">このトピックでは、子要素名を指定して単一の子要素を取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6b9b1-103">This topic explains how to retrieve a single child element, given the name of the child element.</span></span> <span data-ttu-id="6b9b1-104">子要素の名前が既知であり、この名前を持つ要素が 1 つしか存在しない場合は、コレクションの代わりに 1 つの要素だけを取得する方が便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="6b9b1-104">When you know the name of the child element and that there is only one element that has this name, it can be convenient to retrieve just one element, instead of a collection.</span></span>  
  
 <span data-ttu-id="6b9b1-105"><xref:System.Xml.Linq.XContainer.Element%2A> メソッドは、指定された <xref:System.Xml.Linq.XElement> を持つ最初の子 <xref:System.Xml.Linq.XName> を返します。</span><span class="sxs-lookup"><span data-stu-id="6b9b1-105">The <xref:System.Xml.Linq.XContainer.Element%2A> method returns the first child <xref:System.Xml.Linq.XElement> with the specified <xref:System.Xml.Linq.XName>.</span></span>  
  
 <span data-ttu-id="6b9b1-106">Visual Basic で単一の子要素を取得する場合の一般的な方法は、XML プロパティを使用し、配列インデクサー表記を使用して最初の要素を取得する方法です。</span><span class="sxs-lookup"><span data-stu-id="6b9b1-106">If you want to retrieve a single child element in Visual Basic, a common approach is to use the XML property, and then retrieve the first element using array indexer notation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b9b1-107">例</span><span class="sxs-lookup"><span data-stu-id="6b9b1-107">Example</span></span>  
 <span data-ttu-id="6b9b1-108"><xref:System.Xml.Linq.XContainer.Element%2A> メソッドの使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6b9b1-108">The following example demonstrates the use of the <xref:System.Xml.Linq.XContainer.Element%2A> method.</span></span> <span data-ttu-id="6b9b1-109">この例では、`po` という名前の XML ツリーを受け取り、`Comment` という名前の最初の要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="6b9b1-109">This example takes the XML tree named `po` and finds the first element named `Comment`.</span></span>  
  
 <span data-ttu-id="6b9b1-110">Visual Basic の例では、配列インデクサー表記を使用して単一の要素を取得しています。</span><span class="sxs-lookup"><span data-stu-id="6b9b1-110">The Visual Basic example shows using array indexer notation to retrieve a single element.</span></span>  
  
 <span data-ttu-id="6b9b1-111">この例では、XML ドキュメント、[サンプル XML ファイル: 一般的な購買発注書 (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md) を使用します。</span><span class="sxs-lookup"><span data-stu-id="6b9b1-111">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
XElement po = XElement.Load("PurchaseOrder.xml");  
XElement e = po.Element("DeliveryNotes");  
Console.WriteLine(e);  
```  
  
 <span data-ttu-id="6b9b1-112">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="6b9b1-112">This example produces the following output:</span></span>  
  
```xml  
<DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>  
```  
  
## <a name="example"></a><span data-ttu-id="6b9b1-113">例</span><span class="sxs-lookup"><span data-stu-id="6b9b1-113">Example</span></span>  
 <span data-ttu-id="6b9b1-114">上記と同じコードを使用して、名前空間内の XML から要素を取得する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6b9b1-114">The following example shows the same code for XML that is in a namespace.</span></span> <span data-ttu-id="6b9b1-115">詳細については、「[名前空間の概要 (LINQ to XML)](namespaces-overview-linq-to-xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b9b1-115">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="6b9b1-116">この例では、次の XML ドキュメントを使用します: [サンプル XML ファイル: 名前空間内の一般的な購買発注書](./sample-xml-file-typical-purchase-order-in-a-namespace.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="6b9b1-116">This example uses the following XML document: [Sample XML File: Typical Purchase Order in a Namespace](./sample-xml-file-typical-purchase-order-in-a-namespace.md).</span></span>  
  
```csharp  
XElement po = XElement.Load("PurchaseOrderInNamespace.xml");  
XNamespace aw = "http://www.adventure-works.com";  
XElement e = po.Element(aw + "DeliveryNotes");  
Console.WriteLine(e);  
```  
  
 <span data-ttu-id="6b9b1-117">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="6b9b1-117">This example produces the following output:</span></span>  
  
```xml  
<aw:DeliveryNotes xmlns:aw="http://www.adventure-works.com">Please leave packages in shed by driveway.</aw:DeliveryNotes>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6b9b1-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="6b9b1-118">See also</span></span>

- [<span data-ttu-id="6b9b1-119">LINQ to XML 軸 (C#)</span><span class="sxs-lookup"><span data-stu-id="6b9b1-119">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
