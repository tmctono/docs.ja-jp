---
title: 属性のコレクションを取得する方法 (LINQ to XML) (C#)
description: この C# の Attributes メソッドによって、要素の属性が取得されます。 この LINQ to XML の例では、要素の属性のコレクションを反復処理します。
ms.date: 07/20/2015
ms.assetid: a49ee7a3-b2c2-4d49-9b5c-b7c6c41f4f13
ms.openlocfilehash: 5994086db6133530e63eb1328a7b524d30a0797d
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103376"
---
# <a name="how-to-retrieve-a-collection-of-attributes-linq-to-xml-c"></a>属性のコレクションを取得する方法 (LINQ to XML) (C#)
このトピックでは、<xref:System.Xml.Linq.XElement.Attributes%2A> メソッドについて説明します。 このメソッドは、要素の属性を取得します。  
  
## <a name="example"></a>例  
 次の例では、要素の属性のコレクションを反復処理する方法を示します。  
  
```csharp  
XElement val = new XElement("Value",  
    new XAttribute("ID", "1243"),  
    new XAttribute("Type", "int"),  
    new XAttribute("ConvertableTo", "double"),  
    "100");  
IEnumerable<XAttribute> listOfAttributes =  
    from att in val.Attributes()  
    select att;  
foreach (XAttribute a in listOfAttributes)  
    Console.WriteLine(a);  
```  
  
 このコードを実行すると、次の出力が生成されます。  
  
```output  
ID="1243"  
Type="int"  
ConvertableTo="double"  
```  
  
## <a name="see-also"></a>関連項目

- [LINQ to XML 軸 (C#)](./linq-to-xml-axes-overview.md)
