---
title: 要素の値を取得する方法 (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 4228c007-07c9-4cf2-a45b-e7074c109581
ms.openlocfilehash: c4bb78e937fe0de08242923cdd7cd638abf571c7
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805835"
---
# <a name="how-to-retrieve-the-value-of-an-element-linq-to-xml-c"></a><span data-ttu-id="1cb39-102">要素の値を取得する方法 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="1cb39-102">How to retrieve the value of an element (LINQ to XML) (C#)</span></span>

<span data-ttu-id="1cb39-103">この記事では、要素の値を取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1cb39-103">This article shows how to get the value of elements.</span></span> <span data-ttu-id="1cb39-104">値を取得するには、主に 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="1cb39-104">There are two main ways to get the value:</span></span>

- <span data-ttu-id="1cb39-105"><xref:System.Xml.Linq.XElement> または <xref:System.Xml.Linq.XAttribute> を目的の型にキャストします。</span><span class="sxs-lookup"><span data-stu-id="1cb39-105">Cast an <xref:System.Xml.Linq.XElement> or an <xref:System.Xml.Linq.XAttribute> to the desired type.</span></span> <span data-ttu-id="1cb39-106">その後、明示的な変換演算子によって、要素または属性のコンテンツが指定した型に変換され、変数に代入されます。</span><span class="sxs-lookup"><span data-stu-id="1cb39-106">The explicit conversion operator then converts the contents of the element or attribute to the specified type and assigns it to your variable.</span></span>

- <span data-ttu-id="1cb39-107"><xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> または <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="1cb39-107">Use the <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> or <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType> properties.</span></span> <span data-ttu-id="1cb39-108">また、これらのプロパティを使用して値を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="1cb39-108">You can also set the value using these properties.</span></span>

<span data-ttu-id="1cb39-109">C# の場合、通常はキャストがより適切な方法です。</span><span class="sxs-lookup"><span data-stu-id="1cb39-109">With C#, casting is generally the better approach.</span></span> <span data-ttu-id="1cb39-110">要素または属性を null 許容の値の型にキャストすると、存在しているかどうかが不明確な要素 (または属性) の値を取得する場合にコードをより簡単に記述できます。</span><span class="sxs-lookup"><span data-stu-id="1cb39-110">If you cast the element or attribute to a nullable value type, the code is simpler to write when retrieving the value of an element (or attribute) that might or might not exist.</span></span> <span data-ttu-id="1cb39-111">この記事の[最後の例](#element-might-not-exist-example)では、要素が存在しない可能性がある場合に、キャストがより単純であることを示しています。</span><span class="sxs-lookup"><span data-stu-id="1cb39-111">The [last example](#element-might-not-exist-example) in this article demonstrates that casting is simpler in the case where the element might not exist.</span></span> <span data-ttu-id="1cb39-112">ただし、<xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> プロパティの場合とは異なり、キャストを通じて要素のコンテンツを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="1cb39-112">However, you cannot set the contents of an element through casting, as you can through <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="string-cast-example"></a><span data-ttu-id="1cb39-113">文字列キャストの例</span><span class="sxs-lookup"><span data-stu-id="1cb39-113">String cast example</span></span>  
 <span data-ttu-id="1cb39-114">要素の値を取得するには、<xref:System.Xml.Linq.XElement> オブジェクトを目的の型にキャストします。</span><span class="sxs-lookup"><span data-stu-id="1cb39-114">To retrieve the value of an element, cast the <xref:System.Xml.Linq.XElement> object to your desired type.</span></span> <span data-ttu-id="1cb39-115">次に示すように、要素は文字列にキャストできます。</span><span class="sxs-lookup"><span data-stu-id="1cb39-115">You can cast an element to a string, as follows:</span></span>  
  
```csharp  
XElement e = new XElement("StringElement", "abcde");  
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + (string)e);  
```  
  
 <span data-ttu-id="1cb39-116">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="1cb39-116">This example produces the following output:</span></span>  
  
```output  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="integer-cast-example"></a><span data-ttu-id="1cb39-117">整数キャストの例</span><span class="sxs-lookup"><span data-stu-id="1cb39-117">Integer cast example</span></span>  
 <span data-ttu-id="1cb39-118">文字列以外の型に要素をキャストすることもできます。</span><span class="sxs-lookup"><span data-stu-id="1cb39-118">You can also cast elements to types other than string.</span></span> <span data-ttu-id="1cb39-119">たとえば、次のコードに示すように、整数を含んだ要素を `int` にキャストできます。</span><span class="sxs-lookup"><span data-stu-id="1cb39-119">For example, if you have an element that contains an integer, you can cast it to `int`, as shown in the following code:</span></span>  
  
```csharp  
XElement e = new XElement("Age", "44");  
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + (int)e);  
```  
  
 <span data-ttu-id="1cb39-120">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="1cb39-120">This example produces the following output:</span></span>  
  
```output  
<Age>44</Age>  
Value of e:44  
```  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="1cb39-121">では、`string`、`bool`、`bool?`、`int`、`int?`、`uint`、`uint?`、`long`、`long?`、`ulong`、`ulong?`、`float`、`float?`、`double`、`double?`、`decimal`、`decimal?`、`DateTime`、`DateTime?`、`TimeSpan`、`TimeSpan?`、`GUID`、および `GUID?` というデータ型について明示的なキャスト演算子を用意しています。</span><span class="sxs-lookup"><span data-stu-id="1cb39-121">provides explicit cast operators for the following data types: `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID`, and `GUID?`.</span></span>  
  
 <span data-ttu-id="1cb39-122">また、[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] は、<xref:System.Xml.Linq.XAttribute> オブジェクトについても同様のキャスト演算子を用意しています。</span><span class="sxs-lookup"><span data-stu-id="1cb39-122">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] provides the same cast operators for <xref:System.Xml.Linq.XAttribute> objects.</span></span>  
  
## <a name="value-property-example"></a><span data-ttu-id="1cb39-123">Value プロパティの例</span><span class="sxs-lookup"><span data-stu-id="1cb39-123">Value property example</span></span>  
 <span data-ttu-id="1cb39-124"><xref:System.Xml.Linq.XElement.Value%2A> プロパティを使用すると、要素のコンテンツを取得できます。</span><span class="sxs-lookup"><span data-stu-id="1cb39-124">You can use the <xref:System.Xml.Linq.XElement.Value%2A> property to retrieve the contents of an element:</span></span>  
  
```csharp  
XElement e = new XElement("StringElement", "abcde");
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + e.Value);  
```  
  
 <span data-ttu-id="1cb39-125">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="1cb39-125">This example produces the following output:</span></span>  
  
```output  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="element-might-not-exist-example"></a><span data-ttu-id="1cb39-126">要素が存在しない可能性の例</span><span class="sxs-lookup"><span data-stu-id="1cb39-126">Element might not exist example</span></span>
 <span data-ttu-id="1cb39-127">存在しているかどうかが明確でない要素の値の取得を試行する場合があります。</span><span class="sxs-lookup"><span data-stu-id="1cb39-127">Sometimes you try to retrieve the value of an element even though you're not sure if it exists.</span></span> <span data-ttu-id="1cb39-128">このケースでは、null 許容参照型または null 許容の値の型にキャストされた要素を代入するときに、その要素が存在しない場合、代入された変数は `null` に設定されます。</span><span class="sxs-lookup"><span data-stu-id="1cb39-128">In this case, when you assign the casted element to a nullable reference type or nullable value type, if the element does not exist, the assigned variable is set to `null`.</span></span> <span data-ttu-id="1cb39-129">要素が存在するかどうかわからないときは、<xref:System.Xml.Linq.XElement.Value%2A> プロパティよりもキャストを使用した方が簡単であることを、次のコードは示しています。</span><span class="sxs-lookup"><span data-stu-id="1cb39-129">The following code shows that when the element might or might not exist, it is easier to use casting than to use the <xref:System.Xml.Linq.XElement.Value%2A> property.</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child1", "child 1 content"),  
    new XElement("Child2", "2")  
);  
  
// The following assignments show why it is easier to use  
// casting when the element might or might not exist.  
  
string c1 = (string)root.Element("Child1");  
Console.WriteLine("c1:{0}", c1 == null ? "element does not exist" : c1);  
  
int? c2 = (int?)root.Element("Child2");  
Console.WriteLine("c2:{0}", c2 == null ? "element does not exist" : c2.ToString());  
  
string c3 = (string)root.Element("Child3");  
Console.WriteLine("c3:{0}", c3 == null ? "element does not exist" : c3);  
  
int? c4 = (int?)root.Element("Child4");  
Console.WriteLine("c4:{0}", c4 == null ? "element does not exist" : c4.ToString());  
  
Console.WriteLine();  
  
// The following assignments show the required code when using  
// the Value property when the element might or might not exist.  
// Notice that this is more difficult than the casting approach.  
  
XElement e1 = root.Element("Child1");  
string v1;  
if (e1 == null)  
    v1 = null;  
else  
    v1 = e1.Value;  
Console.WriteLine("v1:{0}", v1 == null ? "element does not exist" : v1);  
  
XElement e2 = root.Element("Child2");  
int? v2;  
if (e2 == null)  
    v2 = null;  
else  
    v2 = Int32.Parse(e2.Value);  
Console.WriteLine("v2:{0}", v2 == null ? "element does not exist" : v2.ToString());  
  
XElement e3 = root.Element("Child3");  
string v3;  
if (e3 == null)  
    v3 = null;  
else  
    v3 = e3.Value;  
Console.WriteLine("v3:{0}", v3 == null ? "element does not exist" : v3);  
  
XElement e4 = root.Element("Child4");  
int? v4;  
if (e4 == null)  
    v4 = null;  
else  
    v4 = Int32.Parse(e4.Value);  
Console.WriteLine("v4:{0}", v4 == null ? "element does not exist" : v4.ToString());  
```  
  
 <span data-ttu-id="1cb39-130">このコードを実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="1cb39-130">This code produces the following output:</span></span>  
  
```output  
c1:child 1 content  
c2:2  
c3:element does not exist  
c4:element does not exist  
  
v1:child 1 content  
v2:2  
v3:element does not exist  
v4:element does not exist  
```  
  
 <span data-ttu-id="1cb39-131">通常、要素や属性のコンテンツを取得するには、キャストを使用する方が単純なコードになります。</span><span class="sxs-lookup"><span data-stu-id="1cb39-131">In general, you can write simpler code when using casting to retrieve the contents of elements and attributes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cb39-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="1cb39-132">See also</span></span>

- [<span data-ttu-id="1cb39-133">LINQ to XML 軸 (C#)</span><span class="sxs-lookup"><span data-stu-id="1cb39-133">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
