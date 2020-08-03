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
# <a name="how-to-retrieve-a-collection-of-attributes-linq-to-xml-c"></a><span data-ttu-id="d4cbd-104">属性のコレクションを取得する方法 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="d4cbd-104">How to retrieve a collection of attributes (LINQ to XML) (C#)</span></span>
<span data-ttu-id="d4cbd-105">このトピックでは、<xref:System.Xml.Linq.XElement.Attributes%2A> メソッドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d4cbd-105">This topic introduces the <xref:System.Xml.Linq.XElement.Attributes%2A> method.</span></span> <span data-ttu-id="d4cbd-106">このメソッドは、要素の属性を取得します。</span><span class="sxs-lookup"><span data-stu-id="d4cbd-106">This method retrieves the attributes of an element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4cbd-107">例</span><span class="sxs-lookup"><span data-stu-id="d4cbd-107">Example</span></span>  
 <span data-ttu-id="d4cbd-108">次の例では、要素の属性のコレクションを反復処理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d4cbd-108">The following example shows how to iterate through the collection of attributes of an element.</span></span>  
  
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
  
 <span data-ttu-id="d4cbd-109">このコードを実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="d4cbd-109">This code produces the following output:</span></span>  
  
```output  
ID="1243"  
Type="int"  
ConvertableTo="double"  
```  
  
## <a name="see-also"></a><span data-ttu-id="d4cbd-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="d4cbd-110">See also</span></span>

- [<span data-ttu-id="d4cbd-111">LINQ to XML 軸 (C#)</span><span class="sxs-lookup"><span data-stu-id="d4cbd-111">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
