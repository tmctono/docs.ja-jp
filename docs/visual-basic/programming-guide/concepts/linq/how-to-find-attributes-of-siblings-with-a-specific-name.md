---
title: '方法: 特定の名前 (XPath LINQ to XML) を持つ兄弟の属性を検索する (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 83b3ddca-830a-4b71-9756-9e4bdf907302
ms.openlocfilehash: 709c21cee37c42f7633b2b108b8846ddd8e3b4e7
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/10/2019
ms.locfileid: "72249897"
---
# <a name="how-to-find-attributes-of-siblings-with-a-specific-name-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="bf0c3-102">方法: 特定の名前 (XPath LINQ to XML) を持つ兄弟の属性を検索する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf0c3-102">How to: Find Attributes of Siblings with a Specific Name (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="bf0c3-103">このトピックでは、コンテキスト ノードの兄弟が持つすべての属性を検索する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-103">This topic shows how to find all attributes of the siblings of the context node.</span></span> <span data-ttu-id="bf0c3-104">コレクション内にある特定の名前の属性のみが返されます。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-104">Only attributes with a specific name are returned in the collection.</span></span>  
  
 <span data-ttu-id="bf0c3-105">XPath 式を次に示します。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-105">The XPath expression is:</span></span>  
  
 `../Book/@id`  
  
## <a name="example"></a><span data-ttu-id="bf0c3-106">例</span><span class="sxs-lookup"><span data-stu-id="bf0c3-106">Example</span></span>  
 <span data-ttu-id="bf0c3-107">この例では、最初に `Book` 要素を検索し、次に `Book` という名前の兄弟要素をすべて検索します。その後、`id` という名前の属性をすべて検索します。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-107">This example first finds a `Book` element, and then finds all sibling elements named `Book`, and then finds all attributes named `id`.</span></span> <span data-ttu-id="bf0c3-108">結果は属性のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-108">The result is a collection of attributes.</span></span>  
  
 <span data-ttu-id="bf0c3-109">この例では、次の XML ドキュメントを使用します: 「[サンプル XML ファイル:書籍 (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md)」。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-109">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span></span>  
  
```vb  
Dim books as XDocument = XDocument.Load("Books.xml")  
Dim book As XElement = books.Root.<Book>(0)  
  
' LINQ to XML query  
Dim list1 As IEnumerable(Of XAttribute) = _  
    From el In book.Parent.<Book> _  
    Select el.Attribute("id")  
  
' XPath expression  
Dim list2 As IEnumerable(Of XAttribute) = DirectCast(book. _  
    XPathEvaluate("../Book/@id"), IEnumerable).Cast(Of XAttribute)()  
  
If list1.Count() = list2.Count() And _  
        (list1.Intersect(list2)).Count() = list1.Count() Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
  
For Each el As XAttribute In list1  
    Console.WriteLine(el)  
Next  
```  
  
 <span data-ttu-id="bf0c3-110">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-110">This example produces the following output:</span></span>  
  
```console  
Results are identical  
id="bk101"  
id="bk102"  
```  
  
## <a name="see-also"></a><span data-ttu-id="bf0c3-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="bf0c3-111">See also</span></span>

- [<span data-ttu-id="bf0c3-112">XPath ユーザーの LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf0c3-112">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
