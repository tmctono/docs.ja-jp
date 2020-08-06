---
title: 属性の値を取得する方法 (LINQ to XML) (C#)
description: 属性の値を取得する方法について説明します。 コード例を参照し、使用可能なその他のリソースを確認してください。
ms.date: 07/20/2015
ms.assetid: 817bbe89-5979-4234-bf0c-46f63692ac8c
ms.openlocfilehash: 5ee6995a54829b6d992e2982e6a6effcabf76470
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301555"
---
# <a name="how-to-retrieve-the-value-of-an-attribute-linq-to-xml-c"></a><span data-ttu-id="0950b-104">属性の値を取得する方法 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="0950b-104">How to retrieve the value of an attribute (LINQ to XML) (C#)</span></span>
<span data-ttu-id="0950b-105">このトピックでは、属性の値を取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0950b-105">This topic shows how to obtain the value of attributes.</span></span> <span data-ttu-id="0950b-106">主に 2 つの方法があります。1 つは、<xref:System.Xml.Linq.XAttribute> を目的の型にキャストする方法です。その後、明示的な変換演算子によって、要素または属性のコンテンツが指定した型に変換されます。</span><span class="sxs-lookup"><span data-stu-id="0950b-106">There are two main ways: You can cast an <xref:System.Xml.Linq.XAttribute> to the desired type; the explicit conversion operator then converts the contents of the element or attribute to the specified type.</span></span> <span data-ttu-id="0950b-107">もう 1 つは、<xref:System.Xml.Linq.XAttribute.Value%2A> プロパティを使用する方法です。</span><span class="sxs-lookup"><span data-stu-id="0950b-107">Alternatively, you can use the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span> <span data-ttu-id="0950b-108">ただし、通常はキャストがより適切な方法です。</span><span class="sxs-lookup"><span data-stu-id="0950b-108">However, casting is generally the better approach.</span></span> <span data-ttu-id="0950b-109">属性を null 許容の値の型にキャストすると、存在しているかどうかが不明確な属性の値を取得する場合にコードをより簡単に記述できます。</span><span class="sxs-lookup"><span data-stu-id="0950b-109">If you cast the attribute to a nullable value type, the code is simpler to write when retrieving the value of an attribute that might or might not exist.</span></span> <span data-ttu-id="0950b-110">この手法の例については、「[要素の値を取得する方法 (LINQ to XML) (C#)](./how-to-retrieve-the-value-of-an-element-linq-to-xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0950b-110">For examples of this technique, see [How to retrieve the value of an element (LINQ to XML) (C#)](./how-to-retrieve-the-value-of-an-element-linq-to-xml.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0950b-111">例</span><span class="sxs-lookup"><span data-stu-id="0950b-111">Example</span></span>  
 <span data-ttu-id="0950b-112">属性の値を取得するには、<xref:System.Xml.Linq.XAttribute> オブジェクトを目的の型にキャストします。</span><span class="sxs-lookup"><span data-stu-id="0950b-112">To retrieve the value of an attribute, you just cast the <xref:System.Xml.Linq.XAttribute> object to your desired type.</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
                    new XAttribute("Attr", "abcde")  
                );  
Console.WriteLine(root);  
string str = (string)root.Attribute("Attr");  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="0950b-113">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="0950b-113">This example produces the following output:</span></span>  
  
```output  
<Root Attr="abcde" />  
abcde  
```  
  
## <a name="example"></a><span data-ttu-id="0950b-114">例</span><span class="sxs-lookup"><span data-stu-id="0950b-114">Example</span></span>  
 <span data-ttu-id="0950b-115">属性が名前空間内にある場合にその属性の値を取得する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="0950b-115">The following example shows how to retrieve the value of an attribute where the attribute is in a namespace.</span></span> <span data-ttu-id="0950b-116">詳細については、「[名前空間の概要 (LINQ to XML)](namespaces-overview-linq-to-xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0950b-116">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = new XElement(aw + "Root",  
                    new XAttribute(aw + "Attr", "abcde")  
                );  
string str = (string)root.Attribute(aw + "Attr");  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="0950b-117">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="0950b-117">This example produces the following output:</span></span>  
  
```output  
abcde  
```  
  
## <a name="see-also"></a><span data-ttu-id="0950b-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="0950b-118">See also</span></span>

- [<span data-ttu-id="0950b-119">LINQ to XML 軸 (C#)</span><span class="sxs-lookup"><span data-stu-id="0950b-119">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
