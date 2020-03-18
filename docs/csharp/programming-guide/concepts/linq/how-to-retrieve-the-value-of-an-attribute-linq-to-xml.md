---
title: 属性の値を取得する方法 (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 817bbe89-5979-4234-bf0c-46f63692ac8c
ms.openlocfilehash: d5b8bb3b5857b82a61367953b8e1cd63bea90beb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "75347427"
---
# <a name="how-to-retrieve-the-value-of-an-attribute-linq-to-xml-c"></a><span data-ttu-id="1bd9d-102">属性の値を取得する方法 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="1bd9d-102">How to retrieve the value of an attribute (LINQ to XML) (C#)</span></span>
<span data-ttu-id="1bd9d-103">このトピックでは、属性の値を取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1bd9d-103">This topic shows how to obtain the value of attributes.</span></span> <span data-ttu-id="1bd9d-104">主に 2 つの方法があります。1 つは、<xref:System.Xml.Linq.XAttribute> を目的の型にキャストする方法です。その後、明示的な変換演算子によって、要素または属性のコンテンツが指定した型に変換されます。</span><span class="sxs-lookup"><span data-stu-id="1bd9d-104">There are two main ways: You can cast an <xref:System.Xml.Linq.XAttribute> to the desired type; the explicit conversion operator then converts the contents of the element or attribute to the specified type.</span></span> <span data-ttu-id="1bd9d-105">もう 1 つは、<xref:System.Xml.Linq.XAttribute.Value%2A> プロパティを使用する方法です。</span><span class="sxs-lookup"><span data-stu-id="1bd9d-105">Alternatively, you can use the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span> <span data-ttu-id="1bd9d-106">ただし、通常はキャストがより適切な方法です。</span><span class="sxs-lookup"><span data-stu-id="1bd9d-106">However, casting is generally the better approach.</span></span> <span data-ttu-id="1bd9d-107">属性を NULL 値が許容される型にキャストすると、存在が不明確な属性の値を取得する場合にコードをより簡単に記述できます。</span><span class="sxs-lookup"><span data-stu-id="1bd9d-107">If you cast the attribute to a nullable type, the code is simpler to write when retrieving the value of an attribute that might or might not exist.</span></span> <span data-ttu-id="1bd9d-108">この手法の例については、「[要素の値を取得する方法 (LINQ to XML) (C#)](./how-to-retrieve-the-value-of-an-element-linq-to-xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bd9d-108">For examples of this technique, see [How to retrieve the value of an element (LINQ to XML) (C#)](./how-to-retrieve-the-value-of-an-element-linq-to-xml.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1bd9d-109">例</span><span class="sxs-lookup"><span data-stu-id="1bd9d-109">Example</span></span>  
 <span data-ttu-id="1bd9d-110">属性の値を取得するには、<xref:System.Xml.Linq.XAttribute> オブジェクトを目的の型にキャストします。</span><span class="sxs-lookup"><span data-stu-id="1bd9d-110">To retrieve the value of an attribute, you just cast the <xref:System.Xml.Linq.XAttribute> object to your desired type.</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
                    new XAttribute("Attr", "abcde")  
                );  
Console.WriteLine(root);  
string str = (string)root.Attribute("Attr");  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="1bd9d-111">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="1bd9d-111">This example produces the following output:</span></span>  
  
```output  
<Root Attr="abcde" />  
abcde  
```  
  
## <a name="example"></a><span data-ttu-id="1bd9d-112">例</span><span class="sxs-lookup"><span data-stu-id="1bd9d-112">Example</span></span>  
 <span data-ttu-id="1bd9d-113">属性が名前空間内にある場合にその属性の値を取得する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="1bd9d-113">The following example shows how to retrieve the value of an attribute where the attribute is in a namespace.</span></span> <span data-ttu-id="1bd9d-114">詳細については、「[名前空間の概要 (LINQ to XML)](namespaces-overview-linq-to-xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bd9d-114">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = new XElement(aw + "Root",  
                    new XAttribute(aw + "Attr", "abcde")  
                );  
string str = (string)root.Attribute(aw + "Attr");  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="1bd9d-115">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="1bd9d-115">This example produces the following output:</span></span>  
  
```output  
abcde  
```  
  
## <a name="see-also"></a><span data-ttu-id="1bd9d-116">参照</span><span class="sxs-lookup"><span data-stu-id="1bd9d-116">See also</span></span>

- [<span data-ttu-id="1bd9d-117">LINQ to XML 軸 (C#)</span><span class="sxs-lookup"><span data-stu-id="1bd9d-117">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
