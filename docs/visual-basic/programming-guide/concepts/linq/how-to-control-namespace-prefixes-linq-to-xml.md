---
title: '方法: コントロールの名前空間プレフィックス (Visual Basic) (LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 2fcf28a5-31b6-409d-84ea-27c22f71fc9f
ms.openlocfilehash: 2b89b49aa76df526c08143cad49685386ffd5e7c
ms.sourcegitcommit: eb9ff6f364cde6f11322e03800d8f5ce302f3c73
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2019
ms.locfileid: "68709818"
---
# <a name="how-to-control-namespace-prefixes-visual-basic-linq-to-xml"></a><span data-ttu-id="ab94f-102">方法: コントロールの名前空間プレフィックス (Visual Basic) (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="ab94f-102">How to: Control Namespace Prefixes (Visual Basic) (LINQ to XML)</span></span>
<span data-ttu-id="ab94f-103">このトピックでは、名前空間プレフィックスを制御する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ab94f-103">This topic describes how you can control namespace prefixes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ab94f-104">例</span><span class="sxs-lookup"><span data-stu-id="ab94f-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="ab94f-105">説明</span><span class="sxs-lookup"><span data-stu-id="ab94f-105">Description</span></span>  
 <span data-ttu-id="ab94f-106">この例では、2 つの名前空間を宣言します。</span><span class="sxs-lookup"><span data-stu-id="ab94f-106">This example declares two namespaces.</span></span> <span data-ttu-id="ab94f-107">`http://www.adventure-works.com`名前空間に`aw`プレフィックス`fc`があり、名前空間のプレフィックスがであることを指定します。 `www.fourthcoffee.com`</span><span class="sxs-lookup"><span data-stu-id="ab94f-107">It specifies that the `http://www.adventure-works.com` namespace has the prefix `aw`, and that the `www.fourthcoffee.com` namespace has the prefix of `fc`.</span></span>  
  
### <a name="code"></a><span data-ttu-id="ab94f-108">コード</span><span class="sxs-lookup"><span data-stu-id="ab94f-108">Code</span></span>  
  
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
  
### <a name="comments"></a><span data-ttu-id="ab94f-109">コメント</span><span class="sxs-lookup"><span data-stu-id="ab94f-109">Comments</span></span>  
 <span data-ttu-id="ab94f-110">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="ab94f-110">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:fc="www.fourthcoffee.com" xmlns:aw="http://www.adventure-works.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ab94f-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="ab94f-111">See also</span></span>

- [<span data-ttu-id="ab94f-112">名前空間の概要 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ab94f-112">Namespaces Overview (LINQ to XML) (Visual Basic)</span></span>](namespaces-overview-linq-to-xml.md)
