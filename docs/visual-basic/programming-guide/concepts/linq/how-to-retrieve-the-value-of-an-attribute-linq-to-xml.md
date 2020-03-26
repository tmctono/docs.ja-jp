---
title: '方法: 属性の値を取得する (LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 5f4b3790-c83f-4eb3-a889-e3587edf3ca1
ms.openlocfilehash: 6593639dcdc234ddda808cfdb5e85ebe1a771b62
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2020
ms.locfileid: "80248948"
---
# <a name="how-to-retrieve-the-value-of-an-attribute-linq-to-xml-visual-basic"></a><span data-ttu-id="1ec77-102">方法: 属性の値を取得する (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1ec77-102">How to: Retrieve the Value of an Attribute (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="1ec77-103">このトピックでは、属性の値を取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1ec77-103">This topic shows how to obtain the value of attributes.</span></span> <span data-ttu-id="1ec77-104">主に 2 つの方法があります。1 つは、<xref:System.Xml.Linq.XAttribute> を目的の型にキャストする方法です。その後、明示的な変換演算子によって、要素または属性のコンテンツが指定した型に変換されます。</span><span class="sxs-lookup"><span data-stu-id="1ec77-104">There are two main ways: You can cast an <xref:System.Xml.Linq.XAttribute> to the desired type; the explicit conversion operator then converts the contents of the element or attribute to the specified type.</span></span> <span data-ttu-id="1ec77-105">もう 1 つは、<xref:System.Xml.Linq.XAttribute.Value%2A> プロパティを使用する方法です。</span><span class="sxs-lookup"><span data-stu-id="1ec77-105">Alternatively, you can use the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span> <span data-ttu-id="1ec77-106">ただし、通常はキャストがより適切な方法です。</span><span class="sxs-lookup"><span data-stu-id="1ec77-106">However, casting is generally the better approach.</span></span> <span data-ttu-id="1ec77-107">属性を null 許容値型にキャストすると、存在する可能性のある属性の値を取得する場合と存在しない可能性のある属性の値を取得する場合に、コードを記述する方が簡単になります。</span><span class="sxs-lookup"><span data-stu-id="1ec77-107">If you cast the attribute to a nullable value type, the code is simpler to write when retrieving the value of an attribute that might or might not exist.</span></span> <span data-ttu-id="1ec77-108">この手法の例については、「[方法: 要素の値を取得する (LINQ to XML) (Visual Basic)」を参照](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md)してください。</span><span class="sxs-lookup"><span data-stu-id="1ec77-108">For examples of this technique, see [How to: Retrieve the Value of an Element (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ec77-109">例</span><span class="sxs-lookup"><span data-stu-id="1ec77-109">Example</span></span>  
 <span data-ttu-id="1ec77-110">Visual Basic では、統合属性プロパティを使用して属性の値を取得できます。</span><span class="sxs-lookup"><span data-stu-id="1ec77-110">In Visual Basic, you can use the integrated attribute property to retrieve the value of an attribute.</span></span>  
  
```vb  
Dim root As XElement = <Root Attr="abcde"/>  
Console.WriteLine(root)  
Dim str As String = root.@Attr  
Console.WriteLine(str)  
```  
  
 <span data-ttu-id="1ec77-111">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="1ec77-111">This example produces the following output:</span></span>  
  
```xml  
<Root Attr="abcde" />  
abcde  
```  
  
## <a name="example"></a><span data-ttu-id="1ec77-112">例</span><span class="sxs-lookup"><span data-stu-id="1ec77-112">Example</span></span>  
 <span data-ttu-id="1ec77-113">Visual Basic では、統合属性プロパティを使用して属性の値を設定できます。</span><span class="sxs-lookup"><span data-stu-id="1ec77-113">In Visual Basic, you can use the integrated attribute property to set the value of an attribute.</span></span> <span data-ttu-id="1ec77-114">また、統合属性プロパティを使用して存在しない属性の値を設定すると、その属性が作成されます。</span><span class="sxs-lookup"><span data-stu-id="1ec77-114">Further, if you use the integrated attribute property to set the value of an attribute that does not exist, the attribute will be created.</span></span>  
  
```vb  
Dim root As XElement = <Root Att1="content"/>  
root.@Att1 = "new content"  
root.@Att2 = "new attribute"  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="1ec77-115">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="1ec77-115">This example produces the following output:</span></span>  
  
```xml  
<Root Att1="new content" Att2="new attribute" />  
```  
  
## <a name="example"></a><span data-ttu-id="1ec77-116">例</span><span class="sxs-lookup"><span data-stu-id="1ec77-116">Example</span></span>  
 <span data-ttu-id="1ec77-117">属性が名前空間内にある場合にその属性の値を取得する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="1ec77-117">The following example shows how to retrieve the value of an attribute where the attribute is in a namespace.</span></span> <span data-ttu-id="1ec77-118">詳細については、「[名前空間の概要 (LINQ to XML) (Visual Basic)」](namespaces-overview-linq-to-xml.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ec77-118">For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="1ec77-119">この例の結果は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="1ec77-119">This example produces the following output:</span></span>  
  
```console  
abcde  
```  
  
## <a name="see-also"></a><span data-ttu-id="1ec77-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="1ec77-120">See also</span></span>

- [<span data-ttu-id="1ec77-121">LINQ to XML 軸 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1ec77-121">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
