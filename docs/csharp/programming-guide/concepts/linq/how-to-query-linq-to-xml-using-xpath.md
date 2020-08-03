---
title: XPath を使用して LINQ to XML にクエリを実行する方法 (C#)
description: C# の拡張メソッドを使用し、XPath を使用して XML ツリーに対してクエリを実行することができます。 一般に、LINQ to XML で XPath を使用することはお勧めしません。
ms.date: 07/20/2015
ms.assetid: ee5af263-4ab1-45e5-b792-33a3221b426d
ms.openlocfilehash: fff45a93380b5af85aa640fc690783cc95e6298b
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104344"
---
# <a name="how-to-query-linq-to-xml-using-xpath-c"></a>XPath を使用して LINQ to XML にクエリを実行する方法 (C#)
このトピックでは、XPath を使用して XML ツリーに対してクエリを実行できる拡張メソッドについて説明します。 これらの拡張メソッドの使用に関する詳細については、<xref:System.Xml.XPath.Extensions?displayProperty=nameWithType> を参照してください。  
  
 古いコードの広範な利用など、XPath を使用してクエリを実行する特別な理由がない限りは、XPath を LINQ to XML と共に使用することはお勧めできません。 XPath クエリは、[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] クエリよりもパフォーマンスが低くなります。  
  
## <a name="example"></a>例  
 次の例では、小さな XML ツリーを作成し、<xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> を使用して要素のセットを選択します。  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child1", 1),  
    new XElement("Child1", 2),  
    new XElement("Child1", 3),  
    new XElement("Child2", 4),  
    new XElement("Child2", 5),  
    new XElement("Child2", 6)  
);  
IEnumerable<XElement> list = root.XPathSelectElements("./Child2");  
foreach (XElement el in list)  
    Console.WriteLine(el);  
```  
  
 この例を実行すると、次の出力が生成されます。  
  
```xml  
<Child2>4</Child2>  
<Child2>5</Child2>  
<Child2>6</Child2>  
```  
  