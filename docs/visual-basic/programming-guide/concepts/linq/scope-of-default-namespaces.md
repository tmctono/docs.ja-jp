---
title: Visual Basic の既定の名前空間のスコープ
ms.date: 07/20/2015
ms.assetid: d4cce80c-342f-4097-be8b-40ab0bfa90ba
ms.openlocfilehash: af868454c9d1dce7d8bf5a1902f64eff8db8780c
ms.sourcegitcommit: eb9ff6f364cde6f11322e03800d8f5ce302f3c73
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2019
ms.locfileid: "68710352"
---
# <a name="scope-of-default-namespaces-in-visual-basic"></a><span data-ttu-id="8079c-102">Visual Basic の既定の名前空間のスコープ</span><span class="sxs-lookup"><span data-stu-id="8079c-102">Scope of Default Namespaces in Visual Basic</span></span>
<span data-ttu-id="8079c-103">XML ツリーで表される既定の名前空間は、クエリのスコープ内にありません。</span><span class="sxs-lookup"><span data-stu-id="8079c-103">Default namespaces as represented in the XML tree are not in scope for queries.</span></span> <span data-ttu-id="8079c-104">既定の名前空間に含まれる XML が存在する場合は、<xref:System.Xml.Linq.XNamespace> 変数を宣言し、この変数をローカル名と組み合わせて作成した修飾名をクエリで使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8079c-104">If you have XML that is in a default namespace, you still must declare an <xref:System.Xml.Linq.XNamespace> variable, and combine it with the local name to make a qualified name to be used in the query.</span></span>  
  
 <span data-ttu-id="8079c-105">XML ツリーのクエリにおける最も一般的な問題の 1 つは、XML ツリーに既定の名前空間がある場合に、XML が名前空間に含まれていないものとして開発者がクエリを記述してしまうことです。</span><span class="sxs-lookup"><span data-stu-id="8079c-105">One of the most common problems when querying XML trees is that if the XML tree has a default namespace, the developer sometimes writes the query as though the XML were not in a namespace.</span></span>  
  
 <span data-ttu-id="8079c-106">このトピックの最初に示す一連の例では、既定の名前空間内の XML が読み込まれても、クエリが不適切に実行される典型的な例を示しています。</span><span class="sxs-lookup"><span data-stu-id="8079c-106">The first set of examples in this topic shows a typical way that XML in a default namespace is loaded, but is queried improperly.</span></span>  
  
 <span data-ttu-id="8079c-107">2 番目に示す一連の例では、名前空間内の XML に対してクエリを実行できるようにするために必要な修正を示しています。</span><span class="sxs-lookup"><span data-stu-id="8079c-107">The second set of examples show the necessary corrections so that you can query XML in a namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8079c-108">例</span><span class="sxs-lookup"><span data-stu-id="8079c-108">Example</span></span>  
 <span data-ttu-id="8079c-109">この例では、名前空間内にある XML の作成、および空の結果セットを返すクエリを示します。</span><span class="sxs-lookup"><span data-stu-id="8079c-109">This example shows the creation of XML in a namespace, and a query that returns an empty result set.</span></span>  
  
### <a name="code"></a><span data-ttu-id="8079c-110">コード</span><span class="sxs-lookup"><span data-stu-id="8079c-110">Code</span></span>  
  
```vb  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root xmlns='http://www.adventure-works.com'>  
                <Child>1</Child>  
                <Child>2</Child>  
                <Child>3</Child>  
                <AnotherChild>4</AnotherChild>  
                <AnotherChild>5</AnotherChild>  
                <AnotherChild>6</AnotherChild>  
            </Root>  
        Dim c1 As IEnumerable(Of XElement) = _  
                From el In root.<Child> _  
                Select el  
        Console.WriteLine("Result set follows:")  
        For Each el As XElement In c1  
            Console.WriteLine(CInt(el))  
        Next  
        Console.WriteLine("End of result set")  
    End Sub  
End Module  
```  
  
### <a name="comments"></a><span data-ttu-id="8079c-111">コメント</span><span class="sxs-lookup"><span data-stu-id="8079c-111">Comments</span></span>  
 <span data-ttu-id="8079c-112">この例を実行すると、次の結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="8079c-112">This example produces the following result:</span></span>  
  
```  
Result set follows:  
End of result set  
```  
  
## <a name="example"></a><span data-ttu-id="8079c-113">例</span><span class="sxs-lookup"><span data-stu-id="8079c-113">Example</span></span>  
 <span data-ttu-id="8079c-114">この例では、名前空間内にある XML の作成と、適切に記述されたクエリを示します。</span><span class="sxs-lookup"><span data-stu-id="8079c-114">This example shows the creation of XML in a namespace, and a query that is coded properly.</span></span>  
  
 <span data-ttu-id="8079c-115">上記の不適切なコード例とは対照的に、Visual Basic を使用する場合の正しい方法は、グローバルな既定の名前空間を宣言して初期化することです。</span><span class="sxs-lookup"><span data-stu-id="8079c-115">In contrast to the incorrectly coded example above, the correct approach when using Visual Basic is to declare and initialize a global default namespace.</span></span> <span data-ttu-id="8079c-116">これにより、すべての XML プロパティが既定の名前空間に配置されます。</span><span class="sxs-lookup"><span data-stu-id="8079c-116">This places all XML properties in the default namespace.</span></span> <span data-ttu-id="8079c-117">この例を正しく動作させるために必要な変更はこれだけです。</span><span class="sxs-lookup"><span data-stu-id="8079c-117">No other modifications are required to the example to make it work properly.</span></span>  
  
### <a name="code"></a><span data-ttu-id="8079c-118">コード</span><span class="sxs-lookup"><span data-stu-id="8079c-118">Code</span></span>  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root xmlns='http://www.adventure-works.com'>  
                <Child>1</Child>  
                <Child>2</Child>  
                <Child>3</Child>  
                <AnotherChild>4</AnotherChild>  
                <AnotherChild>5</AnotherChild>  
                <AnotherChild>6</AnotherChild>  
            </Root>  
        Dim c1 As IEnumerable(Of XElement) = _  
                From el In root.<Child> _  
                Select el  
        Console.WriteLine("Result set follows:")  
        For Each el As XElement In c1  
            Console.WriteLine(el.Value)  
        Next  
        Console.WriteLine("End of result set")  
    End Sub  
End Module  
```  
  
### <a name="comments"></a><span data-ttu-id="8079c-119">コメント</span><span class="sxs-lookup"><span data-stu-id="8079c-119">Comments</span></span>  
 <span data-ttu-id="8079c-120">この例を実行すると、次の結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="8079c-120">This example produces the following result:</span></span>  
  
```  
Result set follows:  
1  
2  
3  
End of result set  
```  
  
## <a name="see-also"></a><span data-ttu-id="8079c-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="8079c-121">See also</span></span>

- [<span data-ttu-id="8079c-122">名前空間の概要 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8079c-122">Namespaces Overview (LINQ to XML) (Visual Basic)</span></span>](namespaces-overview-linq-to-xml.md)
