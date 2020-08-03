---
title: 直前の兄弟を検索する方法 (XPath-LINQ to XML) (C#)
description: この C# の例では、ノードの直前の兄弟を検索する方法で XPath と LINQ to XML を比較します。
ms.date: 07/20/2015
ms.assetid: 74c06201-0b1b-4b5e-b3ac-0092980614e6
ms.openlocfilehash: eaee7f1205ce0d0b2a9c2c41d96ba532573a1384
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105198"
---
# <a name="how-to-find-the-immediate-preceding-sibling-xpath-linq-to-xml-c"></a>直前の兄弟を検索する方法 (XPath-LINQ to XML) (C#)
ノードの直前の兄弟を検索することが必要になる場合があります。 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] とは対照的に、XPath では先行する兄弟軸の位置述語にはセマンティクス上の違いがあります。この  と XPath の相違点は、注目すべき特徴といえます。  
  
## <a name="example"></a>例  
 この例では、[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] クエリは、<xref:System.Linq.Enumerable.Last%2A> 演算子を使用して、<xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A> から返されるコレクション内の最後のノードを検索します。 一方、XPath 式は、値が 1 の述語を使用して直前の要素を検索します。  
  
```csharp  
XElement root = XElement.Parse(  
    @"<Root>  
    <Child1/>  
    <Child2/>  
    <Child3/>  
    <Child4/>  
</Root>");  
XElement child4 = root.Element("Child4");  
  
// LINQ to XML query  
XElement el1 =  
    child4  
    .ElementsBeforeSelf()  
    .Last();  
  
// XPath expression  
XElement el2 =  
    ((IEnumerable)child4  
                 .XPathEvaluate("preceding-sibling::*[1]"))  
                 .Cast<XElement>()  
                 .First();  
  
if (el1 == el2)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(el1);  
```  
  
 この例を実行すると、次の出力が生成されます。  
  
```output  
Results are identical  
<Child3 />  
```  
