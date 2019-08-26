---
title: 方法:親の属性を検索する (XPath-LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: dbef9d89-a5c4-431f-80cc-7a2ebf323f86
ms.openlocfilehash: 2e6c124d2653fb4426b3abb693f0b58daa5413c2
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69593616"
---
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-c"></a><span data-ttu-id="0b9f5-102">方法:親の属性を検索する (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="0b9f5-102">How to: Find an Attribute of the Parent (XPath-LINQ to XML) (C#)</span></span>

<span data-ttu-id="0b9f5-103">このトピックでは、親要素に移動してその属性を検索する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0b9f5-103">This topic shows how to navigate to the parent element and find an attribute of it.</span></span>

<span data-ttu-id="0b9f5-104">XPath 式を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0b9f5-104">The XPath expression is:</span></span>

`../@id`

## <a name="example"></a><span data-ttu-id="0b9f5-105">例</span><span class="sxs-lookup"><span data-stu-id="0b9f5-105">Example</span></span>

<span data-ttu-id="0b9f5-106">この例では、まず `Author` 要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="0b9f5-106">This example first finds an `Author` element.</span></span> <span data-ttu-id="0b9f5-107">次に、親要素の `id` 属性を検索します。</span><span class="sxs-lookup"><span data-stu-id="0b9f5-107">It then finds the `id` attribute of the parent element.</span></span>

<span data-ttu-id="0b9f5-108">この例では、XML ドキュメント、「[サンプル XML ファイル:書籍 (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md)」。</span><span class="sxs-lookup"><span data-stu-id="0b9f5-108">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span></span>

```csharp
XDocument books = XDocument.Load("Books.xml");

XElement author =
    books
    .Root
    .Element("Book")
    .Element("Author");

// LINQ to XML query
XAttribute att1 =
    author
    .Parent
    .Attribute("id");

// XPath expression
XAttribute att2 = ((IEnumerable)author.XPathEvaluate("../@id")).Cast<XAttribute>().First();

if (att1 == att2)
    Console.WriteLine("Results are identical");
else
    Console.WriteLine("Results differ");
Console.WriteLine(att1);
```

<span data-ttu-id="0b9f5-109">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="0b9f5-109">This example produces the following output:</span></span>

```
Results are identical
id="bk101"
```
