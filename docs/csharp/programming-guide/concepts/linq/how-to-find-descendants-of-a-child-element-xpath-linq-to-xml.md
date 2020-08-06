---
title: 子要素の子孫を検索する方法 (XPath-LINQ to XML) (C#)
description: XPath 式を使用して、特定の名前を持つ子要素の子孫要素を検索する方法について説明します。
ms.date: 07/20/2015
ms.assetid: 505b7512-bb8b-4f85-abbf-491f039c961e
ms.openlocfilehash: b8e110abc2e0df99c3fdf6d2846c7cbbc4736c1a
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303258"
---
# <a name="how-to-find-descendants-of-a-child-element-xpath-linq-to-xml-c"></a>子要素の子孫を検索する方法 (XPath-LINQ to XML) (C#)
このトピックでは、特定の名前を持つ子要素の子孫要素を取得する方法について説明します。  
  
 XPath 式を次に示します。  
  
 `./Paragraph//Text/text()`  
  
## <a name="example"></a>例  
 この例では、ワード プロセッシング ドキュメントの XML 表現からテキストを抽出する際に発生する問題をシミュレートします。 最初にすべての `Paragraph` 要素を選択し、次に各 `Text` 要素の `Paragraph` 子孫要素をすべて選択します。 `Text` 要素の `Comment` 子孫要素は選択しません。  
  
```csharp  
XElement root = XElement.Parse(  
@"<Root>  
  <Paragraph>  
    <Text>This is the start of</Text>  
  </Paragraph>  
  <Comment>  
    <Text>This comment is not part of the paragraph text.</Text>  
  </Comment>  
  <Paragraph>  
    <Annotation Emphasis='true'>  
      <Text> a sentence.</Text>  
    </Annotation>  
  </Paragraph>  
  <Paragraph>  
    <Text>  This is a second sentence.</Text>  
  </Paragraph>  
</Root>");  
  
// LINQ to XML query  
string str1 =  
    root  
    .Elements("Paragraph")  
    .Descendants("Text")  
    .Select(s => s.Value)  
    .Aggregate(  
        new StringBuilder(),  
        (s, i) => s.Append(i),  
        s => s.ToString()  
    );  
  
// XPath expression  
string str2 =  
    ((IEnumerable)root.XPathEvaluate("./Paragraph//Text/text()"))  
    .Cast<XText>()  
    .Select(s => s.Value)  
    .Aggregate(  
        new StringBuilder(),  
        (s, i) => s.Append(i),  
        s => s.ToString()  
    );  
  
if (str1 == str2)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(str2);  
```  
  
 この例を実行すると、次の出力が生成されます。  
  
```output  
Results are identical  
This is the start of a sentence.  This is a second sentence.  
```  
  