---
title: '方法: 直前の兄弟 (XPath LINQ to XML) を検索する (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: ec046283-9fe2-4440-b295-860bf700099d
ms.openlocfilehash: 46f5b0d2d32e8dcba5f8c9e164a027a8e8118f4d
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582693"
---
# <a name="how-to-find-the-immediate-preceding-sibling-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="01a9a-102">方法: 直前の兄弟 (XPath LINQ to XML) を検索する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="01a9a-102">How to: Find the Immediate Preceding Sibling (XPath-LINQ to XML) (Visual Basic)</span></span>

<span data-ttu-id="01a9a-103">ノードの直前の兄弟を検索することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="01a9a-103">Sometimes you want to find the immediate preceding sibling to a node.</span></span> <span data-ttu-id="01a9a-104">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] とは対照的に、XPath では先行する兄弟軸の位置述語にはセマンティクス上の違いがあります。この  と XPath の相違点は、注目すべき特徴といえます。</span><span class="sxs-lookup"><span data-stu-id="01a9a-104">Due to the difference in the semantics of positional predicates for the preceding sibling axes in XPath as opposed to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], this is one of the more interesting comparisons.</span></span>

## <a name="example"></a><span data-ttu-id="01a9a-105">例</span><span class="sxs-lookup"><span data-stu-id="01a9a-105">Example</span></span>

<span data-ttu-id="01a9a-106">この例では、[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] クエリは、<xref:System.Linq.Enumerable.Last%2A> 演算子を使用して、<xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A> から返されるコレクション内の最後のノードを検索します。</span><span class="sxs-lookup"><span data-stu-id="01a9a-106">In this example, the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query uses the <xref:System.Linq.Enumerable.Last%2A> operator to find the last node in the collection returned by <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>.</span></span> <span data-ttu-id="01a9a-107">一方、XPath 式は、値が 1 の述語を使用して直前の要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="01a9a-107">By contrast, the XPath expression uses a predicate with a value of 1 to find the immediately preceding element.</span></span>

```vb
Dim root As XElement = _
    <Root>
        <Child1/>
        <Child2/>
        <Child3/>
        <Child4/>
    </Root>
Dim child4 As XElement = root.Element("Child4")

' LINQ to XML query
Dim el1 As XElement = child4.ElementsBeforeSelf().Last()

' XPath expression
Dim el2 As XElement = _
    DirectCast(child4.XPathEvaluate("preceding-sibling::*[1]"),  _
    IEnumerable).Cast(Of XElement)().First()

If el1 Is el2 Then
    Console.WriteLine("Results are identical")
Else
    Console.WriteLine("Results differ")
End If
Console.WriteLine(el1)
```

<span data-ttu-id="01a9a-108">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="01a9a-108">This example produces the following output:</span></span>

```console
Results are identical
<Child3 />
```

## <a name="see-also"></a><span data-ttu-id="01a9a-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="01a9a-109">See also</span></span>

- [<span data-ttu-id="01a9a-110">XPath ユーザーの LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="01a9a-110">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
