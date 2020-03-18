---
title: 位置に基づいて子要素を検索する方法 (XPath-LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: e35bb269-ec86-4c96-8321-12491a0eb2c3
ms.openlocfilehash: cc0ff5639345d36ebb0423a12b66de8f1a70ade1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141123"
---
# <a name="how-to-find-child-elements-based-on-position-xpath-linq-to-xml-c"></a><span data-ttu-id="5906e-102">位置に基づいて子要素を検索する方法 (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="5906e-102">How to find child elements based on position (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="5906e-103">要素をその位置に基づいて検索しなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="5906e-103">Sometimes you want to find elements based on their position.</span></span> <span data-ttu-id="5906e-104">2 番目の要素を検索したり、3 番目から 5 番目の要素を検索したりすることがあります。</span><span class="sxs-lookup"><span data-stu-id="5906e-104">You might want to find the second element, or you might want to find the third through the fifth element.</span></span>  
  
 <span data-ttu-id="5906e-105">XPath 式を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5906e-105">The XPath expression is:</span></span>  
  
 `Test[position() >= 2 and position() <= 4]`  
  
 <span data-ttu-id="5906e-106">レイジー方式でこの [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] クエリを記述する方法は 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="5906e-106">There are two approaches to writing this [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query in a lazy way.</span></span> <span data-ttu-id="5906e-107">1 つは <xref:System.Linq.Enumerable.Skip%2A> 演算子と <xref:System.Linq.Enumerable.Take%2A> 演算子を使用する方法で、もう 1 つはインデックスを受け取る <xref:System.Linq.Enumerable.Where%2A> オーバーロードを使用する方法です。</span><span class="sxs-lookup"><span data-stu-id="5906e-107">You can use the <xref:System.Linq.Enumerable.Skip%2A> and <xref:System.Linq.Enumerable.Take%2A> operators, or you can use the <xref:System.Linq.Enumerable.Where%2A> overload that takes an index.</span></span> <span data-ttu-id="5906e-108"><xref:System.Linq.Enumerable.Where%2A> オーバーロードを使用する場合は、2 つの引数を受け取るラムダ式を使用します。</span><span class="sxs-lookup"><span data-stu-id="5906e-108">When you use the <xref:System.Linq.Enumerable.Where%2A> overload, you use a lambda expression that takes two arguments.</span></span> <span data-ttu-id="5906e-109">次の例では、位置に基づいて選択する両方のメソッドを示します。</span><span class="sxs-lookup"><span data-stu-id="5906e-109">The following example shows both methods of selecting based on position.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5906e-110">例</span><span class="sxs-lookup"><span data-stu-id="5906e-110">Example</span></span>  
 <span data-ttu-id="5906e-111">この例では、2 番目から 4 番目の `Test` 要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="5906e-111">This example finds the second through the fourth `Test` element.</span></span> <span data-ttu-id="5906e-112">結果は要素のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="5906e-112">The result is a collection of elements.</span></span>  
  
 <span data-ttu-id="5906e-113">この例では、「[サンプル XML ファイル: テスト構成 (LINQ to XML)](./sample-xml-file-test-configuration-linq-to-xml.md)」の XML ドキュメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="5906e-113">This example uses the following XML document: [Sample XML File: Test Configuration (LINQ to XML)](./sample-xml-file-test-configuration-linq-to-xml.md).</span></span>  
  
```csharp  
XElement testCfg = XElement.Load("TestConfig.xml");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 =  
    testCfg  
    .Elements("Test")  
    .Skip(1)  
    .Take(3);  
  
// LINQ to XML query  
IEnumerable<XElement> list2 =  
    testCfg  
    .Elements("Test")  
    .Where((el, idx) => idx >= 1 && idx <= 3);  
  
// XPath expression  
IEnumerable<XElement> list3 =  
  testCfg.XPathSelectElements("Test[position() >= 2 and position() <= 4]");  
  
if (list1.Count() == list2.Count() &&  
    list1.Count() == list3.Count() &&  
    list1.Intersect(list2).Count() == list1.Count() &&  
    list1.Intersect(list3).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="5906e-114">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="5906e-114">This example produces the following output:</span></span>  
  
```output  
Results are identical  
<Test TestId="0002" TestType="CMD">  
  <Name>Find succeeding characters</Name>  
  <CommandLine>Examp2.EXE</CommandLine>  
  <Input>abc</Input>  
  <Output>def</Output>  
</Test>  
<Test TestId="0003" TestType="GUI">  
  <Name>Convert multiple numbers to strings</Name>  
  <CommandLine>Examp2.EXE /Verbose</CommandLine>  
  <Input>123</Input>  
  <Output>One Two Three</Output>  
</Test>  
<Test TestId="0004" TestType="GUI">  
  <Name>Find correlated key</Name>  
  <CommandLine>Examp3.EXE</CommandLine>  
  <Input>a1</Input>  
  <Output>b1</Output>  
</Test>  
```  
