---
title: '方法: 親 (XPATH-LINQ to XML) の属性を検索 (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 9d2572fd-27d4-426c-b079-16854cb9ec7d
ms.openlocfilehash: ded20c173063492d260aee5ba55f3c4c585bd961
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62021649"
---
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="c140b-102">方法: 親 (XPATH-LINQ to XML) の属性を検索 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c140b-102">How to: Find an Attribute of the Parent (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="c140b-103">このトピックでは、親要素に移動してその属性を検索する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c140b-103">This topic shows how to navigate to the parent element and find an attribute of it.</span></span>  
  
 <span data-ttu-id="c140b-104">XPath 式を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c140b-104">The XPath expression is:</span></span>  
  
 `../@id`  
  
## <a name="example"></a><span data-ttu-id="c140b-105">例</span><span class="sxs-lookup"><span data-stu-id="c140b-105">Example</span></span>  
 <span data-ttu-id="c140b-106">この例では、まず `Author` 要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="c140b-106">This example first finds an `Author` element.</span></span> <span data-ttu-id="c140b-107">次に、親要素の `id` 属性を検索します。</span><span class="sxs-lookup"><span data-stu-id="c140b-107">It then finds the `id` attribute of the parent element.</span></span>  
  
 <span data-ttu-id="c140b-108">この例では、XML ドキュメント、「[サンプル XML ファイル:書籍 (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md)」。</span><span class="sxs-lookup"><span data-stu-id="c140b-108">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span></span>  
  
```vb  
Dim books As XDocument = XDocument.Load("Books.xml")  
Dim author As XElement = books.Root.<Book>.<Author>.FirstOrDefault()  
  
' LINQ to XML query  
Dim att1 As XAttribute = author.Parent.Attribute("id")  
  
' XPath expression  
Dim att2 As XAttribute = DirectCast(author.XPathEvaluate("../@id"),  _  
    IEnumerable).Cast(Of XAttribute)().First()  
  
If att1 Is att2 Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
Console.WriteLine(att1)  
```  
  
 <span data-ttu-id="c140b-109">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="c140b-109">This example produces the following output:</span></span>  
  
```  
Results are identical  
id="bk101"  
```  
  
## <a name="see-also"></a><span data-ttu-id="c140b-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="c140b-110">See also</span></span>

- [<span data-ttu-id="c140b-111">LINQ to XML XPath ユーザー (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c140b-111">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
