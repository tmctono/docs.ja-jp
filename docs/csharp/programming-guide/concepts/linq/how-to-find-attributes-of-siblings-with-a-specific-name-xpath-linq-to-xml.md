---
title: 特定の名前を持つ兄弟の属性を検索する方法 (XPath-LINQ to XML) (C#)
description: コンテキスト ノードの兄弟が持つすべての属性を検索する方法について説明します。 サンプル XML ファイルを使用するコード例を確認します。
ms.date: 07/20/2015
ms.assetid: c3133d64-523f-422d-8838-73d36b945ca0
ms.openlocfilehash: 12bba22c91fef92fc3383d028ff9dfb8bd3cfa3e
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301698"
---
# <a name="how-to-find-attributes-of-siblings-with-a-specific-name-xpath-linq-to-xml-c"></a>特定の名前を持つ兄弟の属性を検索する方法 (XPath-LINQ to XML) (C#)
このトピックでは、コンテキスト ノードの兄弟が持つすべての属性を検索する方法について説明します。 コレクション内にある特定の名前の属性のみが返されます。  
  
 XPath 式を次に示します。  
  
 `../Book/@id`  
  
## <a name="example"></a>例  
 この例では、最初に `Book` 要素を検索し、次に `Book` という名前の兄弟要素をすべて検索します。その後、`id` という名前の属性をすべて検索します。 結果は属性のコレクションです。  
  
 この例では、次の XML ドキュメントを使用します: 「[サンプル XML ファイル:書籍 (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md)」。  
  
```csharp  
XDocument books = XDocument.Load("Books.xml");  
  
XElement book =
    books  
    .Root  
    .Element("Book");  
  
// LINQ to XML query  
IEnumerable<XAttribute> list1 =  
    from el in book.Parent.Elements("Book")  
    select el.Attribute("id");  
  
// XPath expression  
IEnumerable<XAttribute> list2 =  
  ((IEnumerable)book.XPathEvaluate("../Book/@id")).Cast<XAttribute>();  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XAttribute el in list1)  
    Console.WriteLine(el);  
```  
  
 この例を実行すると、次の出力が生成されます。  
  
```output  
Results are identical  
id="bk101"  
id="bk102"  
```  
  