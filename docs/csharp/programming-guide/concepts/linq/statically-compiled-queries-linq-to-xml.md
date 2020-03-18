---
title: 静的にコンパイルされたクエリ (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 3bf558fe-0705-479d-86d4-00188f5fcf9c
ms.openlocfilehash: 98725cece1006ba13afb64bb8ae17ae6e62c53cf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "70253031"
---
# <a name="statically-compiled-queries-linq-to-xml-c"></a><span data-ttu-id="2ed9c-102">静的にコンパイルされたクエリ (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="2ed9c-102">Statically Compiled Queries (LINQ to XML) (C#)</span></span>
<span data-ttu-id="2ed9c-103"><xref:System.Xml.XmlDocument> に対し、LINQ to XML で最も重要なパフォーマンスの利点の 1 つは、XPath のクエリは実行時に解釈する必要がある一方で LINQ to XML のクエリは静的にコンパイルされるという点です。</span><span class="sxs-lookup"><span data-stu-id="2ed9c-103">One of the most important performance benefits LINQ to XML, as opposed to <xref:System.Xml.XmlDocument>, is that queries in LINQ to XML are statically compiled, whereas XPath queries must be interpreted at run time.</span></span> <span data-ttu-id="2ed9c-104">この機能は LINQ to XML に組み込まれているので、追加の手順を実行することなく利用できますが、その違いを理解しておくと、この 2 つの技術のどちらかを選ぶときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2ed9c-104">This feature is built in to LINQ to XML, so you do not have to perform extra steps to take advantage of it, but it is helpful to understand the distinction when choosing between the two technologies.</span></span> <span data-ttu-id="2ed9c-105">このトピックでは、相違点について説明します。</span><span class="sxs-lookup"><span data-stu-id="2ed9c-105">This topic explains the difference.</span></span>  
  
## <a name="statically-compiled-queries-vs-xpath"></a><span data-ttu-id="2ed9c-106">静的にコンパイルされたクエリと XPath</span><span class="sxs-lookup"><span data-stu-id="2ed9c-106">Statically Compiled Queries vs. XPath</span></span>  
 <span data-ttu-id="2ed9c-107">次の例は、指定した名前と指定した値の属性がある子孫要素を取得する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="2ed9c-107">The following example shows how to get the descendant elements with a specified name, and with an attribute with a specified value.</span></span>  
  
 <span data-ttu-id="2ed9c-108">これに相当する XPath 式は、`//Address[@Type='Shipping']` です。</span><span class="sxs-lookup"><span data-stu-id="2ed9c-108">The following is the equivalent XPath expression: `//Address[@Type='Shipping']`</span></span>
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
IEnumerable<XElement> list1 =  
    from el in po.Descendants("Address")  
    where (string)el.Attribute("Type") == "Shipping"  
    select el;  
  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="2ed9c-109">この例のクエリ式は、コンパイラによってメソッドベースのクエリ構文に書き換えられています。</span><span class="sxs-lookup"><span data-stu-id="2ed9c-109">The query expression in this example is re-written by the compiler to method-based query syntax.</span></span> <span data-ttu-id="2ed9c-110">メソッドベースのクエリ構文で書かれた次の例では、前の例と同じ結果が生成されます。</span><span class="sxs-lookup"><span data-stu-id="2ed9c-110">The following example, which is written in method-based query syntax, produces the same results as the previous one:</span></span>  
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
IEnumerable<XElement> list1 =  
    po  
    .Descendants("Address")  
    .Where(el => (string)el.Attribute("Type") == "Shipping");  
  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="2ed9c-111"><xref:System.Linq.Enumerable.Where%2A> メソッドは拡張メソッドです。</span><span class="sxs-lookup"><span data-stu-id="2ed9c-111">The <xref:System.Linq.Enumerable.Where%2A> method is an extension method.</span></span> <span data-ttu-id="2ed9c-112">詳細については、「[拡張メソッド](../../classes-and-structs/extension-methods.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ed9c-112">For more information, see [Extension Methods](../../classes-and-structs/extension-methods.md).</span></span> <span data-ttu-id="2ed9c-113"><xref:System.Linq.Enumerable.Where%2A> は拡張メソッドであるため、上記のクエリは次のように書かれたかのようにコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="2ed9c-113">Because <xref:System.Linq.Enumerable.Where%2A> is an extension method, the query above is compiled as though it were written as follows:</span></span>  
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
IEnumerable<XElement> list1 =  
    System.Linq.Enumerable.Where(  
        po.Descendants("Address"),  
        el => (string)el.Attribute("Type") == "Shipping");  
  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="2ed9c-114">この例では、前の 2 つの例と同じ結果が生成されます。</span><span class="sxs-lookup"><span data-stu-id="2ed9c-114">This example produces exactly the same results as the previous two examples.</span></span> <span data-ttu-id="2ed9c-115">これは、静的にリンクされたメソッド呼び出しにクエリが効果的にコンパイルされたことを示します。</span><span class="sxs-lookup"><span data-stu-id="2ed9c-115">This illustrates the fact that queries are effectively compiled into statically linked method calls.</span></span> <span data-ttu-id="2ed9c-116">これと反復子の遅延実行セマンティクスが組み合わさることで、パフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="2ed9c-116">This, combined with the deferred execution semantics of iterators, improves performance.</span></span> <span data-ttu-id="2ed9c-117">反復子の遅延実行セマンティクスの詳細については、「[LINQ to XML における遅延実行とレイジー評価 (C#)](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ed9c-117">For more information about the deferred execution semantics of iterators, see [Deferred Execution and Lazy Evaluation in LINQ to XML (C#)](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2ed9c-118">これらは、コンパイラが書き込むコードの例です。</span><span class="sxs-lookup"><span data-stu-id="2ed9c-118">These examples are representative of the code that the compiler might write.</span></span> <span data-ttu-id="2ed9c-119">実際の実装はこれらの例と若干異なる可能性がありますが、パフォーマンスは同じか類似したものになります。</span><span class="sxs-lookup"><span data-stu-id="2ed9c-119">The actual implementation might differ slightly from these examples, but the performance will be the same or similar to these examples.</span></span>  
  
## <a name="executing-xpath-expressions-with-xmldocument"></a><span data-ttu-id="2ed9c-120">XmlDocument を使用した XPath 式の実行</span><span class="sxs-lookup"><span data-stu-id="2ed9c-120">Executing XPath Expressions with XmlDocument</span></span>  
 <span data-ttu-id="2ed9c-121">次の例では、<xref:System.Xml.XmlDocument> を使用して前の例と同じ結果を達成します。</span><span class="sxs-lookup"><span data-stu-id="2ed9c-121">The following example uses <xref:System.Xml.XmlDocument> to accomplish the same results as the previous examples:</span></span>  
  
```csharp  
XmlReader reader = XmlReader.Create("PurchaseOrders.xml");  
XmlDocument doc = new XmlDocument();  
doc.Load(reader);  
XmlNodeList nl = doc.SelectNodes(".//Address[@Type='Shipping']");  
foreach (XmlNode n in nl)  
    Console.WriteLine(n.OuterXml);  
reader.Close();  
```  
  
 <span data-ttu-id="2ed9c-122">このクエリは、LINQ to XML を使用する例と同じ出力を返します。唯一の違いは、出力する XML が LINQ to XML ではインデントされるのに対し、<xref:System.Xml.XmlDocument> ではインデントされないという点です。</span><span class="sxs-lookup"><span data-stu-id="2ed9c-122">This query returns the same output as the examples that use LINQ to XML; the only difference is that LINQ to XML indents the printed XML, whereas <xref:System.Xml.XmlDocument> does not.</span></span>  
  
 <span data-ttu-id="2ed9c-123">ただし、一般に <xref:System.Xml.XmlDocument> の方法では、<xref:System.Xml.XmlNode.SelectNodes%2A> メソッドが呼び出されるたびに内部で次の処理を行わなければならないため、LINQ to XML ほどのパフォーマンスは達成できません。</span><span class="sxs-lookup"><span data-stu-id="2ed9c-123">However, the <xref:System.Xml.XmlDocument> approach generally does not perform as well as LINQ to XML, because the <xref:System.Xml.XmlNode.SelectNodes%2A> method must do the following internally every time it is called:</span></span>  
  
- <span data-ttu-id="2ed9c-124">XPath 式を含んでいる文字列を解析してトークンに分解します。</span><span class="sxs-lookup"><span data-stu-id="2ed9c-124">It parses the string that contains the XPath expression, breaking the string into tokens.</span></span>  
  
- <span data-ttu-id="2ed9c-125">トークンを検証して、XPath 式が有効であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2ed9c-125">It validates the tokens to make sure that the XPath expression is valid.</span></span>  
  
- <span data-ttu-id="2ed9c-126">式を内部式ツリーに変換します。</span><span class="sxs-lookup"><span data-stu-id="2ed9c-126">It translates the expression into an internal expression tree.</span></span>  
  
- <span data-ttu-id="2ed9c-127">ノードを反復処理し、式の評価に基づいて結果セットのノードを適切に選択します。</span><span class="sxs-lookup"><span data-stu-id="2ed9c-127">It iterates through the nodes, appropriately selecting the nodes for the result set based on the evaluation of the expression.</span></span>  
  
 <span data-ttu-id="2ed9c-128">この場合、対応する LINQ to XML のクエリよりも処理量がかなり多くなります。</span><span class="sxs-lookup"><span data-stu-id="2ed9c-128">This is significantly more than the work done by the corresponding LINQ to XML query.</span></span> <span data-ttu-id="2ed9c-129">具体的なパフォーマンスの違いはクエリの種類によって異なりますが、一般に LINQ to XML のクエリは処理量が少ないため、<xref:System.Xml.XmlDocument> を使用して XPath 式を評価するよりも良いパフォーマンスが得られます。</span><span class="sxs-lookup"><span data-stu-id="2ed9c-129">The specific performance difference varies for different types of queries, but in general LINQ to XML queries do less work, and therefore perform better, than evaluating XPath expressions using <xref:System.Xml.XmlDocument>.</span></span>  
