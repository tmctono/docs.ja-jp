---
title: '方法: 要素名をフィルター処理する (LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: b1437b4a-48aa-4546-834a-d6d3ab015fe1
ms.openlocfilehash: ccb768030e10d73b839df71093a27ff11b918650
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84394338"
---
# <a name="how-to-filter-on-element-names-linq-to-xml-visual-basic"></a><span data-ttu-id="342b9-102">方法: 要素名をフィルター処理する (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="342b9-102">How to: Filter on Element Names (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="342b9-103"><xref:System.Collections.Generic.IEnumerable%601> の <xref:System.Xml.Linq.XElement> を返すメソッドのいずれかを呼び出す際に、要素名をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="342b9-103">When you call one of the methods that return <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, you can filter on the element name.</span></span>  
  
## <a name="example"></a><span data-ttu-id="342b9-104">例</span><span class="sxs-lookup"><span data-stu-id="342b9-104">Example</span></span>  
 <span data-ttu-id="342b9-105">この例では、指定した名前を持つ子孫だけが含まれるようにフィルター処理された子孫のコレクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="342b9-105">This example retrieves a collection of descendants that is filtered to contain only descendants with the specified name.</span></span>  
  
 <span data-ttu-id="342b9-106">この例では、次の XML ドキュメントを使用します: 「[サンプル XML ファイル:一般的な購買発注書 (LINQ to XML)](sample-xml-file-typical-purchase-order-linq-to-xml.md) を使用します。</span><span class="sxs-lookup"><span data-stu-id="342b9-106">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](sample-xml-file-typical-purchase-order-linq-to-xml.md).</span></span>  
  
```vb  
Dim po As XElement = XElement.Load("PurchaseOrder.xml")  
Dim items As IEnumerable(Of XElement) = _  
    From el In po...<ProductName> _  
    Select el  
For Each prdName As XElement In items  
    Console.WriteLine(prdName.Name.ToString & ":" & prdName.Value)  
Next  
```  
  
 <span data-ttu-id="342b9-107">このコードを実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="342b9-107">This code produces the following output:</span></span>  
  
```console  
ProductName:Lawnmower  
ProductName:Baby Monitor  
```  
  
 <span data-ttu-id="342b9-108"><xref:System.Collections.Generic.IEnumerable%601> コレクションの <xref:System.Xml.Linq.XElement> を返す他のメソッドは、同じパターンに従います。</span><span class="sxs-lookup"><span data-stu-id="342b9-108">The other methods that return <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement> collections follow the same pattern.</span></span> <span data-ttu-id="342b9-109">そのシグネチャは、<xref:System.Xml.Linq.XContainer.Elements%2A> および <xref:System.Xml.Linq.XContainer.Descendants%2A> と似ています。</span><span class="sxs-lookup"><span data-stu-id="342b9-109">Their signatures are similar to <xref:System.Xml.Linq.XContainer.Elements%2A> and <xref:System.Xml.Linq.XContainer.Descendants%2A>.</span></span> <span data-ttu-id="342b9-110">類似するシグネチャを持つメソッドの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="342b9-110">The following is the complete list of methods that have similar method signatures:</span></span>  
  
- <xref:System.Xml.Linq.XNode.Ancestors%2A>  
  
- <xref:System.Xml.Linq.XContainer.Descendants%2A>  
  
- <xref:System.Xml.Linq.XContainer.Elements%2A>  
  
- <xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A>  
  
- <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>  
  
- <xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A>  
  
- <xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A>  
  
## <a name="example"></a><span data-ttu-id="342b9-111">例</span><span class="sxs-lookup"><span data-stu-id="342b9-111">Example</span></span>  
 <span data-ttu-id="342b9-112">次の例は名前空間に含まれている XML 用のクエリです。これらのクエリは上の例と同じ機能を表しています。</span><span class="sxs-lookup"><span data-stu-id="342b9-112">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="342b9-113">詳細については、「[名前空間の概要 (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="342b9-113">For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="342b9-114">この例では、次の XML ドキュメントを使用します: [サンプル XML ファイル: 名前空間内の一般的な購買発注書](sample-xml-file-typical-purchase-order-in-a-namespace.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="342b9-114">This example uses the following XML document: [Sample XML File: Typical Purchase Order in a Namespace](sample-xml-file-typical-purchase-order-in-a-namespace.md).</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim po As XElement = XElement.Load("PurchaseOrderInNamespace.xml")  
        Dim items As IEnumerable(Of XElement) = _  
            From el In po...<aw:ProductName> _  
            Select el  
        For Each prdName As XElement In items  
            Console.WriteLine(prdName.Name.ToString & ":" & prdName.Value)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="342b9-115">このコードを実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="342b9-115">This code produces the following output:</span></span>  
  
```console  
{http://www.adventure-works.com}ProductName:Lawnmower  
{http://www.adventure-works.com}ProductName:Baby Monitor  
```  
  
## <a name="see-also"></a><span data-ttu-id="342b9-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="342b9-116">See also</span></span>

- [<span data-ttu-id="342b9-117">LINQ to XML 軸 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="342b9-117">LINQ to XML Axes (Visual Basic)</span></span>](linq-to-xml-axes.md)
