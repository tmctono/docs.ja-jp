---
title: 方法:属性のコレクションを取得する (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: a49ee7a3-b2c2-4d49-9b5c-b7c6c41f4f13
ms.openlocfilehash: b37600f02cd012e688d161a079c3c8647545cb2c
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69592667"
---
# <a name="how-to-retrieve-a-collection-of-attributes-linq-to-xml-c"></a><span data-ttu-id="2d2a0-102">方法:属性のコレクションを取得する (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="2d2a0-102">How to: Retrieve a Collection of Attributes (LINQ to XML) (C#)</span></span>
<span data-ttu-id="2d2a0-103">このトピックでは、<xref:System.Xml.Linq.XElement.Attributes%2A> メソッドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2d2a0-103">This topic introduces the <xref:System.Xml.Linq.XElement.Attributes%2A> method.</span></span> <span data-ttu-id="2d2a0-104">このメソッドは、要素の属性を取得します。</span><span class="sxs-lookup"><span data-stu-id="2d2a0-104">This method retrieves the attributes of an element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d2a0-105">例</span><span class="sxs-lookup"><span data-stu-id="2d2a0-105">Example</span></span>  
 <span data-ttu-id="2d2a0-106">次の例では、要素の属性のコレクションを反復処理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2d2a0-106">The following example shows how to iterate through the collection of attributes of an element.</span></span>  
  
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
  
 <span data-ttu-id="2d2a0-107">このコードを実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="2d2a0-107">This code produces the following output:</span></span>  
  
```  
ID="1243"  
Type="int"  
ConvertableTo="double"  
```  
  
## <a name="see-also"></a><span data-ttu-id="2d2a0-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d2a0-108">See also</span></span>

- [<span data-ttu-id="2d2a0-109">LINQ to XML 軸 (C#)</span><span class="sxs-lookup"><span data-stu-id="2d2a0-109">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
