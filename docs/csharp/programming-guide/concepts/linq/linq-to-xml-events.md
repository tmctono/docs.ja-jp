---
title: LINQ to XML イベント (C#)
description: C# で LINQ to XML イベントを任意の XObject のインスタンスに追加します。 その XObject の XML ツリーが変更されたときに、イベント ハンドラーによってイベントが受け取られます。
ms.date: 07/20/2015
ms.assetid: ce7de951-cba7-4870-9962-733eb01cd680
ms.openlocfilehash: 576b0a5d0472bddd66e01d3bef8f3affa1c9458b
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165418"
---
# <a name="linq-to-xml-events-c"></a><span data-ttu-id="043ca-104">LINQ to XML イベント (C#)</span><span class="sxs-lookup"><span data-stu-id="043ca-104">LINQ to XML Events (C#)</span></span>
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="043ca-105">イベントを使うと、XML ツリーが変更されるときに通知を受けることができます。</span><span class="sxs-lookup"><span data-stu-id="043ca-105">events enable you to be notified when an XML tree is altered.</span></span>  
  
 <span data-ttu-id="043ca-106">イベントは、任意の <xref:System.Xml.Linq.XObject> のインスタンスに追加できます。</span><span class="sxs-lookup"><span data-stu-id="043ca-106">You can add events to an instance of any <xref:System.Xml.Linq.XObject>.</span></span> <span data-ttu-id="043ca-107">イベント ハンドラーは、その <xref:System.Xml.Linq.XObject> およびその任意の子孫に対する変更のイベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="043ca-107">The event handler will then receive events for modifications to that <xref:System.Xml.Linq.XObject> and any of its descendants.</span></span> <span data-ttu-id="043ca-108">たとえば、イベント ハンドラーをツリーのルートに追加して、そのツリーに対するすべての変更をイベント ハンドラーから処理できます。</span><span class="sxs-lookup"><span data-stu-id="043ca-108">For example, you can add an event handler to the root of the tree, and handle all modifications to the tree from that event handler.</span></span>  
  
 <span data-ttu-id="043ca-109">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] イベントの例については、<xref:System.Xml.Linq.XObject.Changing> および <xref:System.Xml.Linq.XObject.Changed> を参照してください。</span><span class="sxs-lookup"><span data-stu-id="043ca-109">For examples of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] events, see <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed>.</span></span>  
  
## <a name="types-and-events"></a><span data-ttu-id="043ca-110">型とイベント</span><span class="sxs-lookup"><span data-stu-id="043ca-110">Types and Events</span></span>  
 <span data-ttu-id="043ca-111">イベントを使用する場合は、次の型を使用できます。</span><span class="sxs-lookup"><span data-stu-id="043ca-111">You use the following types when working with events:</span></span>  
  
|<span data-ttu-id="043ca-112">種類</span><span class="sxs-lookup"><span data-stu-id="043ca-112">Type</span></span>|<span data-ttu-id="043ca-113">[説明]</span><span class="sxs-lookup"><span data-stu-id="043ca-113">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Xml.Linq.XObjectChange>|<span data-ttu-id="043ca-114"><xref:System.Xml.Linq.XObject> に対してイベントが生成されるときのイベントの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="043ca-114">Specifies the event type when an event is raised for an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<xref:System.Xml.Linq.XObjectChangeEventArgs>|<span data-ttu-id="043ca-115"><xref:System.Xml.Linq.XObject.Changing> イベントおよび <xref:System.Xml.Linq.XObject.Changed> イベントのデータを提供します。</span><span class="sxs-lookup"><span data-stu-id="043ca-115">Provides data for the <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed> events.</span></span>|  
  
 <span data-ttu-id="043ca-116">XML ツリーを変更するときに次のイベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="043ca-116">The following events are raised when you modify an XML tree:</span></span>  
  
|<span data-ttu-id="043ca-117">Event</span><span class="sxs-lookup"><span data-stu-id="043ca-117">Event</span></span>|<span data-ttu-id="043ca-118">説明</span><span class="sxs-lookup"><span data-stu-id="043ca-118">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Xml.Linq.XObject.Changing>|<span data-ttu-id="043ca-119"><xref:System.Xml.Linq.XObject> またはその子孫のいずれかが変更される直前に発生します。</span><span class="sxs-lookup"><span data-stu-id="043ca-119">Occurs just before this <xref:System.Xml.Linq.XObject> or any of its descendants is going to change.</span></span>|  
|<xref:System.Xml.Linq.XObject.Changed>|<span data-ttu-id="043ca-120"><xref:System.Xml.Linq.XObject> またはその子孫のいずれかが変更されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="043ca-120">Occurs when an <xref:System.Xml.Linq.XObject> has changed or any of its descendants have changed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="043ca-121">例</span><span class="sxs-lookup"><span data-stu-id="043ca-121">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="043ca-122">説明</span><span class="sxs-lookup"><span data-stu-id="043ca-122">Description</span></span>  
 <span data-ttu-id="043ca-123">XML ツリー内の集計情報を維持する場合に、イベントは便利です。</span><span class="sxs-lookup"><span data-stu-id="043ca-123">Events are useful when you want to maintain some aggregate information in an XML tree.</span></span> <span data-ttu-id="043ca-124">たとえば、請求書の品目の合計である請求合計を維持する場合があります。</span><span class="sxs-lookup"><span data-stu-id="043ca-124">For example, you may want maintain an invoice total that is the sum of the line items of the invoice.</span></span> <span data-ttu-id="043ca-125">この例では、イベントを使用して、複合要素の `Items` の下にあるすべての子要素の合計を維持します。</span><span class="sxs-lookup"><span data-stu-id="043ca-125">This example uses events to maintain the total of all of the child elements under the complex element `Items`.</span></span>  
  
### <a name="code"></a><span data-ttu-id="043ca-126">コード</span><span class="sxs-lookup"><span data-stu-id="043ca-126">Code</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Total", "0"),  
    new XElement("Items")  
);  
XElement total = root.Element("Total");  
XElement items = root.Element("Items");  
items.Changed += (object sender, XObjectChangeEventArgs cea) =>  
{  
    switch (cea.ObjectChange)  
    {  
        case XObjectChange.Add:  
            if (sender is XElement)  
                total.Value = ((int)total + (int)(XElement)sender).ToString();  
            if (sender is XText)  
                total.Value = ((int)total + (int)((XText)sender).Parent).ToString();  
            break;  
        case XObjectChange.Remove:  
            if (sender is XElement)  
                total.Value = ((int)total - (int)(XElement)sender).ToString();  
            if (sender is XText)  
                total.Value = ((int)total - Int32.Parse(((XText)sender).Value)).ToString();  
            break;  
    }  
    Console.WriteLine("Changed {0} {1}",  
      sender.GetType().ToString(), cea.ObjectChange.ToString());  
};  
items.SetElementValue("Item1", 25);  
items.SetElementValue("Item2", 50);  
items.SetElementValue("Item2", 75);  
items.SetElementValue("Item3", 133);  
items.SetElementValue("Item1", null);  
items.SetElementValue("Item4", 100);  
Console.WriteLine("Total:{0}", (int)total);  
Console.WriteLine(root);  
```  
  
### <a name="comments"></a><span data-ttu-id="043ca-127">コメント</span><span class="sxs-lookup"><span data-stu-id="043ca-127">Comments</span></span>  
 <span data-ttu-id="043ca-128">このコードを実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="043ca-128">This code produces the following output:</span></span>  
  
```output  
Changed System.Xml.Linq.XElement Add  
Changed System.Xml.Linq.XElement Add  
Changed System.Xml.Linq.XText Remove  
Changed System.Xml.Linq.XText Add  
Changed System.Xml.Linq.XElement Add  
Changed System.Xml.Linq.XElement Remove  
Changed System.Xml.Linq.XElement Add  
Total:308  
<Root>  
  <Total>308</Total>  
  <Items>  
    <Item2>75</Item2>  
    <Item3>133</Item3>  
    <Item4>100</Item4>  
  </Items>  
</Root>  
```  
  