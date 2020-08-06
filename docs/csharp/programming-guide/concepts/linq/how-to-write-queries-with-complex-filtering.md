---
title: 複雑なフィルターを使用してクエリを記述する方法 (C#)
description: 複雑なフィルターを使用して LINQ to XML クエリを記述する方法について説明します。 コード例を参照し、追加リソースを確認してください。
ms.date: 07/20/2015
ms.assetid: 4065d901-cf89-4e47-8bf9-abb65acfb003
ms.openlocfilehash: 5d2c1aafc210b35d4d6b1f1b2d74b11966d90c80
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303427"
---
# <a name="how-to-write-queries-with-complex-filtering-c"></a><span data-ttu-id="743a9-104">複雑なフィルターを使用してクエリを記述する方法 (C#)</span><span class="sxs-lookup"><span data-stu-id="743a9-104">How to write queries with complex filtering (C#)</span></span>
<span data-ttu-id="743a9-105">複雑なフィルターを使用して LINQ to XML クエリを記述することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="743a9-105">Sometimes you want to write LINQ to XML queries with complex filters.</span></span> <span data-ttu-id="743a9-106">たとえば、特定の名前と値を持つ子要素を含む要素をすべて検索しなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="743a9-106">For example, you might have to find all elements that have a child element with a particular name and value.</span></span> <span data-ttu-id="743a9-107">このトピックでは、複雑なフィルターを使用してクエリを記述する例について説明します。</span><span class="sxs-lookup"><span data-stu-id="743a9-107">This topic gives an example of writing a query with complex filtering.</span></span>  
  
## <a name="example"></a><span data-ttu-id="743a9-108">例</span><span class="sxs-lookup"><span data-stu-id="743a9-108">Example</span></span>  
 <span data-ttu-id="743a9-109">この例では、`PurchaseOrder` 属性が "Shipping" で `Address` 子要素が "NY" である `Type` 子要素を含む `State` 要素をすべて検索します。</span><span class="sxs-lookup"><span data-stu-id="743a9-109">This example shows how to find all `PurchaseOrder` elements that have a child `Address` element that has a `Type` attribute equal to "Shipping" and a child `State` element equal to "NY".</span></span> <span data-ttu-id="743a9-110">この例では、入れ子になったクエリを `Where` 句で使用しています。コレクションに要素が含まれる場合、`Any` 演算子は `true` を返します。</span><span class="sxs-lookup"><span data-stu-id="743a9-110">It uses a nested query in the `Where` clause, and the `Any` operator returns `true` if the collection has any elements in it.</span></span> <span data-ttu-id="743a9-111">メソッド ベースのクエリ構文の詳細については、「[LINQ でのクエリ構文とメソッド構文](./query-syntax-and-method-syntax-in-linq.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="743a9-111">For information about using method-based query syntax, see [Query Syntax and Method Syntax in LINQ](./query-syntax-and-method-syntax-in-linq.md).</span></span>  
  
 <span data-ttu-id="743a9-112">この例では、次の XML ドキュメントを使用します: 「[サンプル XML ファイル:複数の購買発注書 (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="743a9-112">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="743a9-113">`Any` 演算子の詳細については、「[量指定子操作 (C#)](./quantifier-operations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="743a9-113">For more information about the `Any` operator, see [Quantifier Operations (C#)](./quantifier-operations.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("PurchaseOrders.xml");  
IEnumerable<XElement> purchaseOrders =  
    from el in root.Elements("PurchaseOrder")  
    where
        (from add in el.Elements("Address")  
        where  
            (string)add.Attribute("Type") == "Shipping" &&  
            (string)add.Element("State") == "NY"  
        select add)  
        .Any()  
    select el;  
foreach (XElement el in purchaseOrders)  
    Console.WriteLine((string)el.Attribute("PurchaseOrderNumber"));  
```  
  
 <span data-ttu-id="743a9-114">このコードを実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="743a9-114">This code produces the following output:</span></span>  
  
```output  
99505  
```  
  
## <a name="example"></a><span data-ttu-id="743a9-115">例</span><span class="sxs-lookup"><span data-stu-id="743a9-115">Example</span></span>  
 <span data-ttu-id="743a9-116">次の例は名前空間に含まれている XML 用のクエリです。これらのクエリは上の例と同じ機能を表しています。</span><span class="sxs-lookup"><span data-stu-id="743a9-116">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="743a9-117">詳細については、「[名前空間の概要 (LINQ to XML)](namespaces-overview-linq-to-xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="743a9-117">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="743a9-118">この例では、次の XML ドキュメントを使用します: [サンプル XML ファイル:名前空間内の複数の購買発注書](./sample-xml-file-multiple-purchase-orders-in-a-namespace.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="743a9-118">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders in a Namespace](./sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("PurchaseOrdersInNamespace.xml");  
XNamespace aw = "http://www.adventure-works.com";  
IEnumerable<XElement> purchaseOrders =  
    from el in root.Elements(aw + "PurchaseOrder")  
    where  
        (from add in el.Elements(aw + "Address")  
         where  
             (string)add.Attribute(aw + "Type") == "Shipping" &&  
             (string)add.Element(aw + "State") == "NY"  
         select add)  
        .Any()  
    select el;  
foreach (XElement el in purchaseOrders)  
    Console.WriteLine((string)el.Attribute(aw + "PurchaseOrderNumber"));  
```  
  
 <span data-ttu-id="743a9-119">このコードを実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="743a9-119">This code produces the following output:</span></span>  
  
```output  
99505  
```  
  
## <a name="see-also"></a><span data-ttu-id="743a9-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="743a9-120">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [<span data-ttu-id="743a9-121">射影操作 (C#)</span><span class="sxs-lookup"><span data-stu-id="743a9-121">Projection Operations (C#)</span></span>](./projection-operations.md)
- [<span data-ttu-id="743a9-122">量指定子操作 (C#)</span><span class="sxs-lookup"><span data-stu-id="743a9-122">Quantifier Operations (C#)</span></span>](./quantifier-operations.md)
