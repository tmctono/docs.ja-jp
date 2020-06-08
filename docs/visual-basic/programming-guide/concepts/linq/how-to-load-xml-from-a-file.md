---
title: '方法: ファイルから XML を読み込む'
ms.date: 07/20/2015
ms.assetid: e2d337ad-8ac8-4671-b694-30e5ca1413b7
ms.openlocfilehash: faea93b8eea2b713a8beb7fe199be7d644a07706
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84398000"
---
# <a name="how-to-load-xml-from-a-file-visual-basic"></a><span data-ttu-id="be426-102">方法: ファイルから XML を読み込む (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be426-102">How to: Load XML from a File (Visual Basic)</span></span>

<span data-ttu-id="be426-103">このトピックでは、<xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> メソッドを使用して URI から XML を読み込む方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="be426-103">This topic shows how to load XML from a URI by using the <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> method.</span></span>

## <a name="example"></a><span data-ttu-id="be426-104">例</span><span class="sxs-lookup"><span data-stu-id="be426-104">Example</span></span>

<span data-ttu-id="be426-105">次の例では、ファイルから XML ドキュメントを読み込む方法を示します。</span><span class="sxs-lookup"><span data-stu-id="be426-105">The following example shows how to load an XML document from a file.</span></span> <span data-ttu-id="be426-106">この例では、books.xml を読み込んで、XML ツリーをコンソールに出力します。</span><span class="sxs-lookup"><span data-stu-id="be426-106">The following example loads books.xml and outputs the XML tree to the console.</span></span>

<span data-ttu-id="be426-107">この例では、XML ドキュメント、「[サンプル XML ファイル:書籍 (LINQ to XML)](sample-xml-file-books-linq-to-xml.md) を使用します。</span><span class="sxs-lookup"><span data-stu-id="be426-107">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](sample-xml-file-books-linq-to-xml.md).</span></span>

```vb
Dim booksFromFile As XElement = XElement.Load("books.xml")
Console.WriteLine(booksFromFile)
```

<span data-ttu-id="be426-108">このコードを実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="be426-108">This code produces the following output:</span></span>

```xml
<Catalog>
  <Book id="bk101">
    <Author>Garghentini, Davide</Author>
    <Title>XML Developer's Guide</Title>
    <Genre>Computer</Genre>
    <Price>44.95</Price>
    <PublishDate>2000-10-01</PublishDate>
    <Description>An in-depth look at creating applications
      with XML.</Description>
  </Book>
  <Book id="bk102">
    <Author>Garcia, Debra</Author>
    <Title>Midnight Rain</Title>
    <Genre>Fantasy</Genre>
    <Price>5.95</Price>
    <PublishDate>2000-12-16</PublishDate>
    <Description>A former architect battles corporate zombies,
      an evil sorceress, and her own childhood to become queen
      of the world.</Description>
  </Book>
</Catalog>
```

## <a name="see-also"></a><span data-ttu-id="be426-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="be426-109">See also</span></span>

- [<span data-ttu-id="be426-110">XML の解析 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be426-110">Parsing XML (Visual Basic)</span></span>](parsing-xml.md)
