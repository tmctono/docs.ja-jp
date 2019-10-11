---
title: '方法: 親 (XPath LINQ to XML) の属性を検索する (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 9d2572fd-27d4-426c-b079-16854cb9ec7d
ms.openlocfilehash: ce8fbb828a5ea8df79f449d50f1d61702a4e3df2
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/10/2019
ms.locfileid: "72249924"
---
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="95e82-102">方法: 親 (XPath LINQ to XML) の属性を検索する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="95e82-102">How to: Find an Attribute of the Parent (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="95e82-103">このトピックでは、親要素に移動してその属性を検索する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="95e82-103">This topic shows how to navigate to the parent element and find an attribute of it.</span></span>  
  
 <span data-ttu-id="95e82-104">XPath 式を次に示します。</span><span class="sxs-lookup"><span data-stu-id="95e82-104">The XPath expression is:</span></span>  
  
 `../@id`  
  
## <a name="example"></a><span data-ttu-id="95e82-105">例</span><span class="sxs-lookup"><span data-stu-id="95e82-105">Example</span></span>  
 <span data-ttu-id="95e82-106">この例では、まず `Author` 要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="95e82-106">This example first finds an `Author` element.</span></span> <span data-ttu-id="95e82-107">次に、親要素の `id` 属性を検索します。</span><span class="sxs-lookup"><span data-stu-id="95e82-107">It then finds the `id` attribute of the parent element.</span></span>  
  
 <span data-ttu-id="95e82-108">この例では、XML ドキュメント、「[サンプル XML ファイル:書籍 (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md)」。</span><span class="sxs-lookup"><span data-stu-id="95e82-108">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="95e82-109">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="95e82-109">This example produces the following output:</span></span>  
  
```console  
Results are identical  
id="bk101"  
```  
  
## <a name="see-also"></a><span data-ttu-id="95e82-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="95e82-110">See also</span></span>

- [<span data-ttu-id="95e82-111">XPath ユーザーの LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="95e82-111">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
