---
title: '方法 : 注釈を使用して XSLT スタイルの LINQ to XML ツリーを変換する'
ms.date: 07/20/2015
ms.assetid: 08e91fa2-dac2-4463-9ef1-87b1ac3fa890
ms.openlocfilehash: d9cb32462535f099107343bd9069b4da3508c5b0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348356"
---
# <a name="how-to-use-annotations-to-transform-linq-to-xml-trees-in-an-xslt-style-visual-basic"></a><span data-ttu-id="292c4-102">方法: 注釈を使用して XSLT スタイルの LINQ to XML ツリーを変換する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="292c4-102">How to: Use Annotations to Transform LINQ to XML Trees in an XSLT Style (Visual Basic)</span></span>

<span data-ttu-id="292c4-103">注釈を使用することで、XML ツリーの変換が容易になります。</span><span class="sxs-lookup"><span data-stu-id="292c4-103">Annotations can be used to facilitate transforms of an XML tree.</span></span>

<span data-ttu-id="292c4-104">XML ドキュメントには、"ドキュメント中心で混合コンテンツを含んでいる" ものがあります。</span><span class="sxs-lookup"><span data-stu-id="292c4-104">Some XML documents are "document centric with mixed content."</span></span> <span data-ttu-id="292c4-105">このようなドキュメントでは、必ずしも要素の子ノードの構造を把握する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="292c4-105">With such documents, you don't necessarily know the shape of child nodes of an element.</span></span> <span data-ttu-id="292c4-106">たとえば、テキストを含んでいるノードは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="292c4-106">For instance, a node that contains text may look like this:</span></span>

```xml
<text>A phrase with <b>bold</b> and <i>italic</i> text.</text>
```

<span data-ttu-id="292c4-107">どのテキスト ノードにも、任意の数の `<b>` と `<i>` が子要素として存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="292c4-107">For any given text node, there may be any number of child `<b>` and `<i>` elements.</span></span> <span data-ttu-id="292c4-108">この方法は、他の多くの状況にまで拡張されています。たとえば、通常の段落、箇条書きの段落、ビットマップなど、さまざまな子要素を含むことができるページなどです。</span><span class="sxs-lookup"><span data-stu-id="292c4-108">This approach extends to a number of other situations: such as, pages that can contain a variety of child elements, such as regular paragraphs, bulleted paragraphs, and bitmaps.</span></span> <span data-ttu-id="292c4-109">テーブルのセルには、テキスト、ドロップダウン リスト、またはビットマップが含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="292c4-109">Cells in a table may contain text, drop down lists, or bitmaps.</span></span> <span data-ttu-id="292c4-110">ドキュメント中心の XML の主要な特性の 1 つは、特定の要素がどの子要素を持つかがわからない点です。</span><span class="sxs-lookup"><span data-stu-id="292c4-110">One of the primary characteristics of document centric XML is that you do not know which child element any particular element will have.</span></span>

<span data-ttu-id="292c4-111">ツリー内の要素を変換するとき、その要素の子について詳しく理解している必要がない場合は、注釈を使用するこの方法が効果的です。</span><span class="sxs-lookup"><span data-stu-id="292c4-111">If you want to transform elements in a tree where you don't necessarily know much about the children of the elements that you want to transform, then this approach that uses annotations is an effective approach.</span></span>

<span data-ttu-id="292c4-112">この方法の概要は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="292c4-112">The summary of the approach is:</span></span>

- <span data-ttu-id="292c4-113">最初に、ツリー内の要素に置換要素を使用して注釈を付けます。</span><span class="sxs-lookup"><span data-stu-id="292c4-113">First, annotate elements in the tree with a replacement element.</span></span>

- <span data-ttu-id="292c4-114">2 番目に、ツリー全体を反復処理して、各要素をその注釈で置換する新しいツリーを作成します。</span><span class="sxs-lookup"><span data-stu-id="292c4-114">Second, iterate through the entire tree, creating a new tree where you replace each element with its annotation.</span></span> <span data-ttu-id="292c4-115">ここで示す例では、`XForm` という関数で新しいツリーの反復処理と作成を実装しています。</span><span class="sxs-lookup"><span data-stu-id="292c4-115">This example implements the iteration and creation of the new tree in a function named `XForm`.</span></span>

<span data-ttu-id="292c4-116">この方法の詳細な構成は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="292c4-116">In detail, the approach consists of:</span></span>

- <span data-ttu-id="292c4-117">構造を変換する一連の要素を返す 1 つ以上の LINQ to XML クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="292c4-117">Execute one or more LINQ to XML queries that return the set of elements that you want to transform from one shape to another.</span></span> <span data-ttu-id="292c4-118">クエリ内の要素ごとに、新しい <xref:System.Xml.Linq.XElement> オブジェクトをその要素に対する注釈として追加します。</span><span class="sxs-lookup"><span data-stu-id="292c4-118">For each element in the query, add a new <xref:System.Xml.Linq.XElement> object as an annotation to the element.</span></span> <span data-ttu-id="292c4-119">変換後の新しいツリーでは、注釈付きの要素がこの新しい要素で置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="292c4-119">This new element will replace the annotated element in the new, transformed tree.</span></span> <span data-ttu-id="292c4-120">例で示すように、このコードは簡単に記述できます。</span><span class="sxs-lookup"><span data-stu-id="292c4-120">This is simple code to write, as demonstrated by the example.</span></span>

- <span data-ttu-id="292c4-121">注釈として追加される新しい要素に新しい子ノードを含めることで、目的の構造を持つサブツリーを形成できます。</span><span class="sxs-lookup"><span data-stu-id="292c4-121">The new element that is added as an annotation can contain new child nodes; it can form a sub-tree with any desired shape.</span></span>

- <span data-ttu-id="292c4-122">特別な規則として、この目的で作成された別の名前空間 (この例では `http://www.microsoft.com/LinqToXmlTransform/2007` という名前空間) に新しい要素の子ノードが含まれている場合、その子ノードは新しいツリーにコピーされません。</span><span class="sxs-lookup"><span data-stu-id="292c4-122">There is a special rule: If a child node of the new element is in a different namespace, a namespace that is made up for this purpose (in this example, the namespace is `http://www.microsoft.com/LinqToXmlTransform/2007`), then that child element is not copied to the new tree.</span></span> <span data-ttu-id="292c4-123">代わりに、名前空間が上記の特別な名前空間で、かつ要素のローカル名が `ApplyTransforms` である場合は、ソース ツリー内の要素の子ノードが反復処理され、新しいツリーにコピーされます (例外として、注釈付きの子要素自体はここで示す規則に従って変換されます)。</span><span class="sxs-lookup"><span data-stu-id="292c4-123">Instead, if the namespace is the above mentioned special namespace, and the local name of the element is `ApplyTransforms`, then the child nodes of the element in the source tree are iterated, and copied to the new tree (with the exception that annotated child elements are themselves transformed according to these rules).</span></span>

- <span data-ttu-id="292c4-124">これは、XSL での変換の仕様にある程度似ています。</span><span class="sxs-lookup"><span data-stu-id="292c4-124">This is somewhat analogous to the specification of transforms in XSL.</span></span> <span data-ttu-id="292c4-125">一連のノードを選択するクエリは、テンプレートの XPath 式に似ています。</span><span class="sxs-lookup"><span data-stu-id="292c4-125">The query that selects a set of nodes is analogous to the XPath expression for a template.</span></span> <span data-ttu-id="292c4-126">注釈として保存される新しい <xref:System.Xml.Linq.XElement> を作成するコードは、XSL のシーケンス コンストラクターに似ています。また、`ApplyTransforms` 要素は、XSL の `xsl:apply-templates` 要素と機能的に似ています。</span><span class="sxs-lookup"><span data-stu-id="292c4-126">The code to create the new <xref:System.Xml.Linq.XElement> that is saved as an annotation is analogous to the sequence constructor in XSL, and the `ApplyTransforms` element is analogous in function to the `xsl:apply-templates` element in XSL.</span></span>

- <span data-ttu-id="292c4-127">この方法の利点の 1 つは、クエリを作成するときに、常に未変更のソース ツリーに対してクエリを記述する点です。</span><span class="sxs-lookup"><span data-stu-id="292c4-127">One advantage to taking this approach - as you formulate queries, you are always writing queries on the unmodified source tree.</span></span> <span data-ttu-id="292c4-128">ツリーに対する変更が記述中のクエリに与える影響を考慮する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="292c4-128">You need not worry about how modifications to the tree affect the queries that you are writing.</span></span>

## <a name="transforming-a-tree"></a><span data-ttu-id="292c4-129">ツリーの変換</span><span class="sxs-lookup"><span data-stu-id="292c4-129">Transforming a Tree</span></span>

<span data-ttu-id="292c4-130">最初の例では、すべての `Paragraph` ノードの名前を `para`に変更します。</span><span class="sxs-lookup"><span data-stu-id="292c4-130">This first example renames all `Paragraph` nodes to `para`:</span></span>

```vb
Imports <xmlns:xf="http://www.microsoft.com/LinqToXmlTransform/2007">

Module Module1
    Dim at As XName = GetXmlNamespace(xf) + "ApplyTransforms"

    Sub Main()
        Dim root As XElement = _
            <Root>
                <Paragraph>This is a sentence with <b>bold</b> and <i>italic</i> text.</Paragraph>
                <Paragraph>More text.</Paragraph>
            </Root>

        ' Replace Paragraph with p.
        For Each el In root...<Paragraph>
            ' same idea as xsl:apply-templates
            el.AddAnnotation( _
                <para>
                    <<%= at %>></>
                </para>)
        Next

        ' The XForm function, shown later in this topic, accomplishes the transform
        Dim newRoot As XElement = XForm(root)
        Console.WriteLine(newRoot)
    End Sub
End Module
```

 <span data-ttu-id="292c4-131">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="292c4-131">This example produces the following output:</span></span>

```xml
<Root>
  <para>This is a sentence with <b>bold</b> and <i>italic</i> text.</para>
  <para>More text.</para>
</Root>
```

## <a name="a-more-complicated-transform"></a><span data-ttu-id="292c4-132">より複雑な変換</span><span class="sxs-lookup"><span data-stu-id="292c4-132">A more complicated transform</span></span>

<span data-ttu-id="292c4-133">次の例では、ツリーに対してクエリを実行し、`Data` 要素の平均と合計を計算して、それらを新しい要素としてツリーに追加します。</span><span class="sxs-lookup"><span data-stu-id="292c4-133">The following example queries the tree and calculates the average and sum of the `Data` elements, and adds them as new elements to the tree.</span></span>

```vb
Imports <xmlns:xf="http://www.microsoft.com/LinqToXmlTransform/2007">

Module Module1
    Dim at As XName = GetXmlNamespace(xf) + "ApplyTransforms"

    Sub Main()
        Dim data As XElement = _
            <Root>
                <Data>20</Data>
                <Data>10</Data>
                <Data>3</Data>
            </Root>

        ' While adding annotations, you can query the source tree all you want,
        ' as the tree is not mutated while annotating.
        data.AddAnnotation( _
            <Root>
                <<%= at %>/>
                <Average>
                    <%= _
                        String.Format("{0:F4}", _
                        data.Elements("Data") _
                        .Select(Function(z) CDec(z)).Average()) _
                    %>
                </Average>
                <Sum>
                    <%= _
                        data.Elements("Data").Select(Function(z) CInt(z)).Sum() _
                    %>
                </Sum>
            </Root> _
        )

        Console.WriteLine("Before Transform")
        Console.WriteLine("----------------")
        Console.WriteLine(data)
        Console.WriteLine(vbNewLine)

        ' The XForm function, shown later in this topic, accomplishes the transform
        Dim newData As XElement = XForm(data)

        Console.WriteLine("After Transform")
        Console.WriteLine("----------------")
        Console.WriteLine(newData)
    End Sub
End Module
```

<span data-ttu-id="292c4-134">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="292c4-134">This example produces the following output:</span></span>

```console
Before Transform
----------------
<Root>
  <Data>20</Data>
  <Data>10</Data>
  <Data>3</Data>
</Root>

After Transform
----------------
<Root>
  <Data>20</Data>
  <Data>10</Data>
  <Data>3</Data>
  <Average>11.0000</Average>
  <Sum>33</Sum>
</Root>
```

## <a name="effecting-the-transform"></a><span data-ttu-id="292c4-135">変換の影響</span><span class="sxs-lookup"><span data-stu-id="292c4-135">Effecting the transform</span></span>

<span data-ttu-id="292c4-136">小さな関数 `XForm` によって、元の注釈付きツリーから変換された新しいツリーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="292c4-136">A small function, `XForm`, creates a new transformed tree from the original, annotated tree.</span></span>

<span data-ttu-id="292c4-137">この関数の擬似コードはかなり単純です。</span><span class="sxs-lookup"><span data-stu-id="292c4-137">The pseudo code for the function is quite simple:</span></span>

> <span data-ttu-id="292c4-138">関数は、引数として XElement を受け取り、XElement を返します。</span><span class="sxs-lookup"><span data-stu-id="292c4-138">The function takes an XElement as an argument and returns an XElement.</span></span>
>
> <span data-ttu-id="292c4-139">要素に XElement 注釈がある場合は、新しい XElement を返します。</span><span class="sxs-lookup"><span data-stu-id="292c4-139">If an element has an XElement annotation, then return a new XElement:</span></span>
>
> - <span data-ttu-id="292c4-140">新しい XElement の名前は、annotation 要素の名前です。</span><span class="sxs-lookup"><span data-stu-id="292c4-140">The name of the new XElement is the annotation element's name.</span></span>
> - <span data-ttu-id="292c4-141">すべての属性が注釈から新しいノードにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="292c4-141">All attributes are copied from the annotation to the new node.</span></span>
> - <span data-ttu-id="292c4-142">すべての子ノードは注釈からコピーされます。ただし、特殊なノード xf: ApplyTransforms が認識され、ソース要素の子ノードが反復処理される点が異なります。</span><span class="sxs-lookup"><span data-stu-id="292c4-142">All child nodes are copied from the annotation, with the exception that the special node xf:ApplyTransforms is recognized, and the source element's child nodes are iterated.</span></span> <span data-ttu-id="292c4-143">ソースの子ノードが XElement でない場合は、新しいツリーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="292c4-143">If the source child node is not an XElement, it is copied to the new tree.</span></span> <span data-ttu-id="292c4-144">ソースの子が XElement の場合は、この関数を再帰的に呼び出して変換されます。</span><span class="sxs-lookup"><span data-stu-id="292c4-144">If the source child is an XElement, then it is transformed by calling this function recursively.</span></span>
>
> <span data-ttu-id="292c4-145">要素に注釈が付いていない場合は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="292c4-145">If an element is not annotated:</span></span>
>
> - <span data-ttu-id="292c4-146">新しい XElement を返す</span><span class="sxs-lookup"><span data-stu-id="292c4-146">Return a new XElement</span></span>
>   - <span data-ttu-id="292c4-147">新しい XElement の名前は、ソース要素の名前です。</span><span class="sxs-lookup"><span data-stu-id="292c4-147">The name of the new XElement is the source element's name.</span></span>
>   - <span data-ttu-id="292c4-148">すべての属性は、ソース要素からコピー先の要素にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="292c4-148">All attributes are copied from the source element to the destination's element.</span></span>
>   - <span data-ttu-id="292c4-149">すべての子ノードは、ソース要素からコピーされます。</span><span class="sxs-lookup"><span data-stu-id="292c4-149">All child nodes are copied from the source element.</span></span>
>   - <span data-ttu-id="292c4-150">ソースの子ノードが XElement でない場合は、新しいツリーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="292c4-150">If the source child node is not an XElement, it is copied to the new tree.</span></span> <span data-ttu-id="292c4-151">ソースの子が XElement の場合は、この関数を再帰的に呼び出して変換されます。</span><span class="sxs-lookup"><span data-stu-id="292c4-151">If the source child is an XElement, then it is transformed by calling this function recursively.</span></span>

<span data-ttu-id="292c4-152">この関数の実装を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="292c4-152">The following code is the implementation of this function:</span></span>

```vb
' Build a transformed XML tree per the annotations.
Function XForm(ByVal source As XElement) As XElement
    If source.Annotation(Of XElement)() IsNot Nothing Then
        Dim anno As XElement = source.Annotation(Of XElement)()
        Return _
            <<%= anno.Name.ToString() %>>
                <%= anno.Attributes() %>
                <%= anno.Nodes().Select(Function(n As XNode) _
                    GetSubNodes(n, source)) %>
            </>
    Else
        Return _
            <<%= source.Name %>>
                <%= source.Attributes() %>
                <%= source.Nodes().Select(Function(n) GetExpandedNodes(n)) %>
            </>
    End If
End Function

Private Function GetSubNodes(ByVal n As XNode, ByVal s As XElement) As Object
    Dim annoEl As XElement = TryCast(n, XElement)
    If annoEl IsNot Nothing Then
        If annoEl.Name = at Then
            Return s.Nodes().Select(Function(n2 As XNode) GetExpandedNodes(n2))
        End If
    End If
    Return n
End Function

Private Function GetExpandedNodes(ByVal n2 As XNode) As XNode
    Dim e2 As XElement = TryCast(n2, XElement)
    If e2 Is Nothing Then
        Return n2
    Else
        Return XForm(e2)
    End If
End Function
```

## <a name="complete-example"></a><span data-ttu-id="292c4-153">完全な例</span><span class="sxs-lookup"><span data-stu-id="292c4-153">Complete example</span></span>

<span data-ttu-id="292c4-154">次に示すのは、`XForm` 関数を含んだ完全なサンプル コードです。</span><span class="sxs-lookup"><span data-stu-id="292c4-154">The following code is a complete example that includes the `XForm` function.</span></span> <span data-ttu-id="292c4-155">ここには、この種の変換の一般的な使用方法がいくつか示されています。</span><span class="sxs-lookup"><span data-stu-id="292c4-155">It includes a few of the typical uses of this type of transform:</span></span>

```vb
Imports System.Collections.Generic
Imports System.Linq
Imports System.Text
Imports System.Xml
Imports System.Xml.Linq

Imports <xmlns:xf="http://www.microsoft.com/LinqToXmlTransform/2007">

Module Module1
    Dim at As XName = GetXmlNamespace(xf) + "ApplyTransforms"

    ' Build a transformed XML tree per the annotations.
    Function XForm(ByVal source As XElement) As XElement
        If source.Annotation(Of XElement)() IsNot Nothing Then
            Dim anno As XElement = source.Annotation(Of XElement)()
            Return _
                <<%= anno.Name.ToString() %>>
                    <%= anno.Attributes() %>
                    <%= anno.Nodes().Select(Function(n As XNode) _
                        GetSubNodes(n, source)) %>
                </>
        Else
            Return _
                <<%= source.Name %>>
                    <%= source.Attributes() %>
                    <%= source.Nodes().Select(Function(n) GetExpandedNodes(n)) %>
                </>
        End If
    End Function

    Private Function GetSubNodes(ByVal n As XNode, ByVal s As XElement) As Object
        Dim annoEl As XElement = TryCast(n, XElement)
        If annoEl IsNot Nothing Then
            If annoEl.Name = at Then
                Return s.Nodes().Select(Function(n2 As XNode) GetExpandedNodes(n2))
            End If
        End If
        Return n
    End Function

    Private Function GetExpandedNodes(ByVal n2 As XNode) As XNode
        Dim e2 As XElement = TryCast(n2, XElement)
        If e2 Is Nothing Then
            Return n2
        Else
            Return XForm(e2)
        End If
    End Function

    Sub Main()
        Dim root As XElement = _
<Root Att1='123'>
    <!--A comment-->
    <Child>1</Child>
    <Child>2</Child>
    <Other>
        <GC>3</GC>
        <GC>4</GC>
    </Other>
    <SomeMixedContent>This is <i>an</i> element that <b>has</b> some mixed content</SomeMixedContent>
    <AnUnchangedElement>42</AnUnchangedElement>
</Root>

        ' Each of the following serves the same semantic purpose as
        ' XSLT templates and sequence constructors.

        ' Replace Child with NewChild.
        For Each el In root.<Child>
            el.AddAnnotation(<NewChild><%= CStr(el) %></NewChild>)
        Next

        ' Replace first GC with GrandChild, add an attribute.
        For Each el In root...<GC>.Take(1)
            el.AddAnnotation(<GrandChild ANewAttribute='999'><%= CStr(el) %></GrandChild>)
        Next

        ' Replace Other with NewOther, add new child elements around original content.
        For Each el In root.<Other>
            el.AddAnnotation( _
                <NewOther>
                    <MyNewChild>1</MyNewChild>
                    <<%= at %>></>
                    <ChildThatComesAfter/>
                </NewOther>)
        Next

        ' Change name of element that has mixed content.
        root...<SomeMixedContent>(0).AddAnnotation( _
                <MixedContent><<%= at %>></></MixedContent>)

        ' Replace <b> with <Bold>.
        For Each el In root...<b>
            el.AddAnnotation(<Bold><<%= at %>></></Bold>)
        Next

        ' Replace <i> with <Italic>.
        For Each el In root...<i>
            el.AddAnnotation(<Italic><<%= at %>></></Italic>)
        Next

        Console.WriteLine("Before Transform")
        Console.WriteLine("----------------")
        Console.WriteLine(root)
        Console.WriteLine(vbNewLine)
        Dim newRoot As XElement = XForm(root)

        Console.WriteLine("After Transform")
        Console.WriteLine("----------------")
        Console.WriteLine(newRoot)
    End Sub
End Module
```

<span data-ttu-id="292c4-156">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="292c4-156">This example produces the following output:</span></span>

```console
Before Transform
----------------
<Root Att1="123">
  <!--A comment-->
  <Child>1</Child>
  <Child>2</Child>
  <Other>
    <GC>3</GC>
    <GC>4</GC>
  </Other>
  <SomeMixedContent>This is <i>an</i> element that <b>has</b> some mixed content</SomeMixedContent>
  <AnUnchangedElement>42</AnUnchangedElement>
</Root>

After Transform
----------------
<Root Att1="123">
  <!--A comment-->
  <NewChild>1</NewChild>
  <NewChild>2</NewChild>
  <NewOther>
    <MyNewChild>1</MyNewChild>
    <GrandChild ANewAttribute="999">3</GrandChild>
    <GC>4</GC>
    <ChildThatComesAfter />
  </NewOther>
  <MixedContent>This is <Italic>an</Italic> element that <Bold>has</Bold> some mixed content</MixedContent>
  <AnUnchangedElement>42</AnUnchangedElement>
</Root>
```

## <a name="see-also"></a><span data-ttu-id="292c4-157">参照</span><span class="sxs-lookup"><span data-stu-id="292c4-157">See also</span></span>

- [<span data-ttu-id="292c4-158">高度な LINQ to XML プログラミング (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="292c4-158">Advanced LINQ to XML Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
