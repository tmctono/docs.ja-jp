---
title: '方法: 属性 (LINQ to XML) の値を取得する (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 5f4b3790-c83f-4eb3-a889-e3587edf3ca1
ms.openlocfilehash: d03b2b146ad2f6b796ba6589cf99d06aa429535d
ms.sourcegitcommit: eb9ff6f364cde6f11322e03800d8f5ce302f3c73
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2019
ms.locfileid: "68710500"
---
# <a name="how-to-retrieve-the-value-of-an-attribute-linq-to-xml-visual-basic"></a><span data-ttu-id="419d0-102">方法: 属性 (LINQ to XML) の値を取得する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="419d0-102">How to: Retrieve the Value of an Attribute (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="419d0-103">このトピックでは、属性の値を取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="419d0-103">This topic shows how to obtain the value of attributes.</span></span> <span data-ttu-id="419d0-104">主に 2 つの方法があります。1 つは、<xref:System.Xml.Linq.XAttribute> を目的の型にキャストする方法です。その後、明示的な変換演算子によって、要素または属性のコンテンツが指定した型に変換されます。</span><span class="sxs-lookup"><span data-stu-id="419d0-104">There are two main ways: You can cast an <xref:System.Xml.Linq.XAttribute> to the desired type; the explicit conversion operator then converts the contents of the element or attribute to the specified type.</span></span> <span data-ttu-id="419d0-105">もう 1 つは、<xref:System.Xml.Linq.XAttribute.Value%2A> プロパティを使用する方法です。</span><span class="sxs-lookup"><span data-stu-id="419d0-105">Alternatively, you can use the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span> <span data-ttu-id="419d0-106">ただし、通常はキャストがより適切な方法です。</span><span class="sxs-lookup"><span data-stu-id="419d0-106">However, casting is generally the better approach.</span></span> <span data-ttu-id="419d0-107">属性を NULL 値が許容される型にキャストすると、存在が不明確な属性の値を取得する場合にコードをより簡単に記述できます。</span><span class="sxs-lookup"><span data-stu-id="419d0-107">If you cast the attribute to a nullable type, the code is simpler to write when retrieving the value of an attribute that might or might not exist.</span></span> <span data-ttu-id="419d0-108">この手法の例については、「[方法:要素の値 (LINQ to XML) を取得します (Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md))。</span><span class="sxs-lookup"><span data-stu-id="419d0-108">For examples of this technique, see [How to: Retrieve the Value of an Element (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="419d0-109">例</span><span class="sxs-lookup"><span data-stu-id="419d0-109">Example</span></span>  
 <span data-ttu-id="419d0-110">Visual Basic では、統合属性プロパティを使用して属性の値を取得できます。</span><span class="sxs-lookup"><span data-stu-id="419d0-110">In Visual Basic, you can use the integrated attribute property to retrieve the value of an attribute.</span></span>  
  
```vb  
Dim root As XElement = <Root Attr="abcde"/>  
Console.WriteLine(root)  
Dim str As String = root.@Attr  
Console.WriteLine(str)  
```  
  
 <span data-ttu-id="419d0-111">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="419d0-111">This example produces the following output:</span></span>  
  
```xml  
<Root Attr="abcde" />  
abcde  
```  
  
## <a name="example"></a><span data-ttu-id="419d0-112">例</span><span class="sxs-lookup"><span data-stu-id="419d0-112">Example</span></span>  
 <span data-ttu-id="419d0-113">Visual Basic では、統合属性プロパティを使用して属性の値を設定できます。</span><span class="sxs-lookup"><span data-stu-id="419d0-113">In Visual Basic, you can use the integrated attribute property to set the value of an attribute.</span></span> <span data-ttu-id="419d0-114">また、統合属性プロパティを使用して存在しない属性の値を設定すると、その属性が作成されます。</span><span class="sxs-lookup"><span data-stu-id="419d0-114">Further, if you use the integrated attribute property to set the value of an attribute that does not exist, the attribute will be created.</span></span>  
  
```vb  
Dim root As XElement = <Root Att1="content"/>  
root.@Att1 = "new content"  
root.@Att2 = "new attribute"  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="419d0-115">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="419d0-115">This example produces the following output:</span></span>  
  
```xml  
<Root Att1="new content" Att2="new attribute" />  
```  
  
## <a name="example"></a><span data-ttu-id="419d0-116">例</span><span class="sxs-lookup"><span data-stu-id="419d0-116">Example</span></span>  
 <span data-ttu-id="419d0-117">属性が名前空間内にある場合にその属性の値を取得する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="419d0-117">The following example shows how to retrieve the value of an attribute where the attribute is in a namespace.</span></span> <span data-ttu-id="419d0-118">詳細については、「[名前空間の概要」 (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="419d0-118">For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <aw:Root aw:Attr="abcde"/>  
        Dim str As String = root.@aw:Attr  
        Console.WriteLine(str)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="419d0-119">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="419d0-119">This example produces the following output:</span></span>  
  
```  
abcde  
```  
  
## <a name="see-also"></a><span data-ttu-id="419d0-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="419d0-120">See also</span></span>

- [<span data-ttu-id="419d0-121">LINQ to XML 軸 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="419d0-121">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
