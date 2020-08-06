---
title: 親の属性を検索する方法 (XPath-LINQ to XML) (C#)
description: 親要素の属性を検索する方法について説明します。 サンプル XML ドキュメントを使用するコード例を確認します。
ms.date: 07/20/2015
ms.assetid: dbef9d89-a5c4-431f-80cc-7a2ebf323f86
ms.openlocfilehash: 03344bb66f617970d9598c91366eb7d69514397a
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303297"
---
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-c"></a>親の属性を検索する方法 (XPath-LINQ to XML) (C#)

このトピックでは、親要素に移動してその属性を検索する方法を示します。

XPath 式を次に示します。

`../@id`

## <a name="example"></a>例

この例では、まず `Author` 要素を検索します。 次に、親要素の `id` 属性を検索します。

この例では、次の XML ドキュメントを使用します: 「[サンプル XML ファイル:書籍 (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md)」。

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

この例を実行すると、次の出力が生成されます。

```output
Results are identical
id="bk101"
```
