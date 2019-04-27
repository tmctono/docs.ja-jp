---
title: '方法: コントロールの Namespace プレフィックス (Visual Basic) (LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 2fcf28a5-31b6-409d-84ea-27c22f71fc9f
ms.openlocfilehash: 7e5a05d2fa93e61338f450d0a4d890fa94c04fd2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61855401"
---
# <a name="how-to-control-namespace-prefixes-visual-basic-linq-to-xml"></a><span data-ttu-id="ca7c1-102">方法: コントロールの Namespace プレフィックス (Visual Basic) (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="ca7c1-102">How to: Control Namespace Prefixes (Visual Basic) (LINQ to XML)</span></span>
<span data-ttu-id="ca7c1-103">このトピックでは、名前空間プレフィックスを制御する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca7c1-103">This topic describes how you can control namespace prefixes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca7c1-104">例</span><span class="sxs-lookup"><span data-stu-id="ca7c1-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="ca7c1-105">説明</span><span class="sxs-lookup"><span data-stu-id="ca7c1-105">Description</span></span>  
 <span data-ttu-id="ca7c1-106">この例では、2 つの名前空間を宣言します。</span><span class="sxs-lookup"><span data-stu-id="ca7c1-106">This example declares two namespaces.</span></span> <span data-ttu-id="ca7c1-107">指定します、`http://www.adventure-works.com`名前空間のプレフィックス`aw`、および、`www.fourthcoffee.com`名前空間のプレフィックスを持つ`fc`します。</span><span class="sxs-lookup"><span data-stu-id="ca7c1-107">It specifies that the `http://www.adventure-works.com` namespace has the prefix `aw`, and that the `www.fourthcoffee.com` namespace has the prefix of `fc`.</span></span>  
  
### <a name="code"></a><span data-ttu-id="ca7c1-108">コード</span><span class="sxs-lookup"><span data-stu-id="ca7c1-108">Code</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
Imports <xmlns:fc="www.fourthcoffee.com">  
  
Module Module1  
  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <fc:Child>  
                    <aw:DifferentChild>other content</aw:DifferentChild>  
                </fc:Child>  
                <aw:Child2>c2 content</aw:Child2>  
                <fc:Child3>c3 content</fc:Child3>  
            </aw:Root>  
        Console.WriteLine(root)  
    End Sub  
  
End Module  
```  
  
### <a name="comments"></a><span data-ttu-id="ca7c1-109">コメント</span><span class="sxs-lookup"><span data-stu-id="ca7c1-109">Comments</span></span>  
 <span data-ttu-id="ca7c1-110">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="ca7c1-110">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:fc="www.fourthcoffee.com" xmlns:aw="http://www.adventure-works.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ca7c1-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="ca7c1-111">See also</span></span>

- [<span data-ttu-id="ca7c1-112">XML 名前空間 (Visual Basic) の使用</span><span class="sxs-lookup"><span data-stu-id="ca7c1-112">Working with XML Namespaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
