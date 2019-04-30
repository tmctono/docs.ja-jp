---
title: '方法: XML リテラル (Visual Basic) の変更します。'
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], Value
- XML literals [Visual Basic]
- XML literals [Visual Basic], modifying
ms.assetid: 4e864522-a37a-43a2-8236-af80277c5482
ms.openlocfilehash: 003715b04f3a5c0fb41e846beb189f117378ea58
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053029"
---
# <a name="how-to-modify-xml-literals-visual-basic"></a><span data-ttu-id="62ed2-102">方法: XML リテラル (Visual Basic) の変更します。</span><span class="sxs-lookup"><span data-stu-id="62ed2-102">How to: Modify XML Literals (Visual Basic)</span></span>

<span data-ttu-id="62ed2-103">Visual Basic では、XML リテラルを変更する便利な手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="62ed2-103">Visual Basic provides convenient ways to modify XML literals.</span></span> <span data-ttu-id="62ed2-104">追加したり、要素と属性を削除し、新しい XML 要素を持つ既存の要素を置換することもできます。</span><span class="sxs-lookup"><span data-stu-id="62ed2-104">You can add or delete elements and attributes, and you can also replace an existing element with a new XML element.</span></span> <span data-ttu-id="62ed2-105">このトピックでは、既存の XML リテラルを変更する方法のいくつかの例を示します。</span><span class="sxs-lookup"><span data-stu-id="62ed2-105">This topic provides several examples of how to modify an existing XML literal.</span></span>

### <a name="to-modify-the-value-of-an-xml-literal"></a><span data-ttu-id="62ed2-106">XML リテラルの値を変更するには</span><span class="sxs-lookup"><span data-stu-id="62ed2-106">To modify the value of an XML literal</span></span>

1. <span data-ttu-id="62ed2-107">XML リテラルの値を変更するには、XML リテラルおよび設定への参照を取得、`Value`プロパティを目的の値にします。</span><span class="sxs-lookup"><span data-stu-id="62ed2-107">To modify the value of an XML literal, obtain a reference to the XML literal and set the `Value` property to the desired value.</span></span>

    <span data-ttu-id="62ed2-108">次のコード例は、すべての値を更新、\<価格 > XML ドキュメント内の要素。</span><span class="sxs-lookup"><span data-stu-id="62ed2-108">The following code example updates the value of all the \<Price> elements in an XML document.</span></span>

    [!code-vb[VbXmlSamples2#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#4)]

    <span data-ttu-id="62ed2-109">次は、サンプルのソース XML に示し、このコード例から XML に変更されました。</span><span class="sxs-lookup"><span data-stu-id="62ed2-109">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="62ed2-110">ソース XML:</span><span class="sxs-lookup"><span data-stu-id="62ed2-110">Source XML:</span></span>

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101">
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
      </Book>
      <Book id="bk331">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
      </Book>
    </Catalog>
    ```

    <span data-ttu-id="62ed2-111">変更された XML:</span><span class="sxs-lookup"><span data-stu-id="62ed2-111">Modified XML:</span></span>

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101">
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>47.20</Price>
      </Book>
      <Book id="bk331">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>48.25</Price>
      </Book>
    </Catalog>
    ```

    > [!NOTE]
    > <span data-ttu-id="62ed2-112">`Value`プロパティはコレクション内の最初の XML 要素を参照します。</span><span class="sxs-lookup"><span data-stu-id="62ed2-112">The `Value` property refers to the first XML element in a collection.</span></span> <span data-ttu-id="62ed2-113">コレクションで同じ名前を持つ 1 つ以上の要素がある場合は、設定、`Value`プロパティがコレクション内の最初の要素だけに影響します。</span><span class="sxs-lookup"><span data-stu-id="62ed2-113">If there is more than one element that has the same name in a collection, setting the `Value` property affects only the first element in the collection.</span></span>

### <a name="to-add-an-attribute-to-an-xml-literal"></a><span data-ttu-id="62ed2-114">XML リテラルに属性を追加するには</span><span class="sxs-lookup"><span data-stu-id="62ed2-114">To add an attribute to an XML literal</span></span>

1. <span data-ttu-id="62ed2-115">XML リテラルには、属性を追加するには、リテラルの XML への参照をまず取得します。</span><span class="sxs-lookup"><span data-stu-id="62ed2-115">To add an attribute to an XML literal, first obtain a reference to the XML literal.</span></span> <span data-ttu-id="62ed2-116">新しい XML 属性軸プロパティを追加することで、属性を追加できます。</span><span class="sxs-lookup"><span data-stu-id="62ed2-116">You can then add an attribute by adding a new XML attribute axis property.</span></span> <span data-ttu-id="62ed2-117">追加することも、新しい<xref:System.Xml.Linq.XAttribute>オブジェクトを XML リテラルを使用して、<xref:System.Xml.Linq.XContainer.Add%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="62ed2-117">You can also add a new <xref:System.Xml.Linq.XAttribute> object to the XML literal by using the <xref:System.Xml.Linq.XContainer.Add%2A> method.</span></span> <span data-ttu-id="62ed2-118">次の例では、両方のオプションを示します。</span><span class="sxs-lookup"><span data-stu-id="62ed2-118">The following example shows both options.</span></span>

    [!code-vb[VbXmlSamples2#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#5)]

    <span data-ttu-id="62ed2-119">次は、サンプルのソース XML に示し、このコード例から XML に変更されました。</span><span class="sxs-lookup"><span data-stu-id="62ed2-119">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="62ed2-120">ソース XML:</span><span class="sxs-lookup"><span data-stu-id="62ed2-120">Source XML:</span></span>

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101" >
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
      </Book>
      <Book id="bk331">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
      </Book>
    </Catalog>
    ```

    <span data-ttu-id="62ed2-121">変更された XML:</span><span class="sxs-lookup"><span data-stu-id="62ed2-121">Modified XML:</span></span>

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101" genre="Computer" editorEmail="someone@example.com">
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
      </Book>
      <Book id="bk331" genre="Computer" editorEmail="someone@example.com">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
      </Book>
    </Catalog>
    ```

    <span data-ttu-id="62ed2-122">XML 属性軸プロパティの詳細については、次を参照してください。 [XML 属性軸プロパティ](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)します。</span><span class="sxs-lookup"><span data-stu-id="62ed2-122">For more information about XML attribute axis properties, see [XML Attribute Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md).</span></span>

### <a name="to-add-an-element-to-an-xml-literal"></a><span data-ttu-id="62ed2-123">XML リテラルに要素を追加するには</span><span class="sxs-lookup"><span data-stu-id="62ed2-123">To add an element to an XML literal</span></span>

1. <span data-ttu-id="62ed2-124">XML リテラルには、要素を追加するには、リテラルの XML への参照をまず取得します。</span><span class="sxs-lookup"><span data-stu-id="62ed2-124">To add an element to an XML literal, first obtain a reference to the XML literal.</span></span> <span data-ttu-id="62ed2-125">追加できる新しい<xref:System.Xml.Linq.XElement>オブジェクトを使用して要素の最後のサブ要素として、<xref:System.Xml.Linq.XContainer.Add%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="62ed2-125">You can then add a new <xref:System.Xml.Linq.XElement> object as the last sub-element of the element by using the <xref:System.Xml.Linq.XContainer.Add%2A> method.</span></span> <span data-ttu-id="62ed2-126">新しいを追加する<xref:System.Xml.Linq.XElement>オブジェクトを使用して最初のサブ要素として、<xref:System.Xml.Linq.XContainer.AddFirst%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="62ed2-126">You can add a new <xref:System.Xml.Linq.XElement> object as the first sub-element by using the <xref:System.Xml.Linq.XContainer.AddFirst%2A> method.</span></span>

    <span data-ttu-id="62ed2-127">その他のサブ要素を基準に特定の場所に新しい要素を追加するには、隣接するサブ要素への参照をまず取得します。</span><span class="sxs-lookup"><span data-stu-id="62ed2-127">To add a new element in a specific location relative to other sub-elements, first obtain a reference to an adjacent sub-element.</span></span> <span data-ttu-id="62ed2-128">追加できる新しい<xref:System.Xml.Linq.XElement>オブジェクトを使用して隣接するサブ要素の前に、<xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="62ed2-128">You can then add the new <xref:System.Xml.Linq.XElement> object before the adjacent sub-element by using the <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> method.</span></span> <span data-ttu-id="62ed2-129">追加することも、新しい<xref:System.Xml.Linq.XElement>オブジェクトを使用して隣接するサブ要素の後に、<xref:System.Xml.Linq.XNode.AddAfterSelf%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="62ed2-129">You can also add the new <xref:System.Xml.Linq.XElement> object after the adjacent sub-element by using the <xref:System.Xml.Linq.XNode.AddAfterSelf%2A> method.</span></span>

    <span data-ttu-id="62ed2-130">次の例では、これらの各手法の例を示します。</span><span class="sxs-lookup"><span data-stu-id="62ed2-130">The following example shows examples of each of these techniques.</span></span>

    [!code-vb[VbXmlSamples2#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#6)]

    <span data-ttu-id="62ed2-131">次は、サンプルのソース XML に示し、このコード例から XML に変更されました。</span><span class="sxs-lookup"><span data-stu-id="62ed2-131">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="62ed2-132">ソース XML:</span><span class="sxs-lookup"><span data-stu-id="62ed2-132">Source XML:</span></span>

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101" >
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
      </Book>
      <Book id="bk331">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
      </Book>
    </Catalog>
    ```

    <span data-ttu-id="62ed2-133">変更された XML:</span><span class="sxs-lookup"><span data-stu-id="62ed2-133">Modified XML:</span></span>

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101" >
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
      </Book>
      <Book id="bk000"></Book>
      <Book id="bk331">
        <Publisher>Microsoft Press</Publisher>
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
        <PublishDate>2005-2-14</PublishDate>
      </Book>
      <Book id="bk999"></Book>
    </Catalog>
    ```

### <a name="to-remove-an-element-or-attribute-from-an-xml-literal"></a><span data-ttu-id="62ed2-134">XML リテラルから要素または属性を削除するには</span><span class="sxs-lookup"><span data-stu-id="62ed2-134">To remove an element or attribute from an XML literal</span></span>

1. <span data-ttu-id="62ed2-135">XML リテラルから要素または属性を削除するには、要素または属性と呼び出しへの参照を取得、`Remove`メソッドを次の例に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="62ed2-135">To remove an element or an attribute from an XML literal, obtain a reference to the element or attribute and call the `Remove` method, as shown in the following example.</span></span>

    [!code-vb[VbXmlSamples2#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#7)]

    <span data-ttu-id="62ed2-136">次は、サンプルのソース XML に示し、このコード例から XML に変更されました。</span><span class="sxs-lookup"><span data-stu-id="62ed2-136">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="62ed2-137">ソース XML:</span><span class="sxs-lookup"><span data-stu-id="62ed2-137">Source XML:</span></span>

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101" genre="Computer" editorEmail="someone@example.com">
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
      </Book>
      <Book id="bk000"></Book>
      <Book id="bk331" genre="Computer" editorEmail="someone@example.com">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
      </Book>
      <Book id="bk999"></Book>
    </Catalog>
    ```

    <span data-ttu-id="62ed2-138">変更された XML:</span><span class="sxs-lookup"><span data-stu-id="62ed2-138">Modified XML:</span></span>

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101" editorEmail="someone@example.com">
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
      </Book>
      <Book id="bk000"></Book>
      <Book id="bk331" editorEmail="someone@example.com">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
      </Book></Catalog>
    ```

    <span data-ttu-id="62ed2-139">XML リテラルからすべての要素または属性を削除するに XML リテラルへの参照を取得し、呼び出し、<xref:System.Xml.Linq.XElement.RemoveAll%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="62ed2-139">To remove all elements or attributes from an XML literal, obtain a reference to the XML literal and call the <xref:System.Xml.Linq.XElement.RemoveAll%2A> method.</span></span>

### <a name="to-modify-an-xml-literal"></a><span data-ttu-id="62ed2-140">XML リテラルを変更するには</span><span class="sxs-lookup"><span data-stu-id="62ed2-140">To modify an XML literal</span></span>

1. <span data-ttu-id="62ed2-141">XML 要素の名前を変更するには、要素への参照をまず取得します。</span><span class="sxs-lookup"><span data-stu-id="62ed2-141">To change the name of an XML element, first obtain a reference to the element.</span></span> <span data-ttu-id="62ed2-142">新しいを作成できます<xref:System.Xml.Linq.XElement>オブジェクトを持つ新しい名前を指定し、新しい渡す<xref:System.Xml.Linq.XElement>オブジェクトを<xref:System.Xml.Linq.XNode.ReplaceWith%2A>メソッドは、既存の<xref:System.Xml.Linq.XElement>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="62ed2-142">You can then create a new <xref:System.Xml.Linq.XElement> object that has a new name and pass the new <xref:System.Xml.Linq.XElement> object to the <xref:System.Xml.Linq.XNode.ReplaceWith%2A> method of the existing <xref:System.Xml.Linq.XElement> object.</span></span>

    <span data-ttu-id="62ed2-143">自分が置き換える要素のサブ要素を保持する必要がありますが、新しい値を設定<xref:System.Xml.Linq.XElement>オブジェクトを<xref:System.Xml.Linq.XContainer.Nodes%2A>は既存の要素のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="62ed2-143">If the element that you are replacing has sub-elements that must be preserved, set the value of the new <xref:System.Xml.Linq.XElement> object to the <xref:System.Xml.Linq.XContainer.Nodes%2A> property of the existing element.</span></span> <span data-ttu-id="62ed2-144">これにより、既存の要素の内部 XML を新しい要素の値が設定されます。</span><span class="sxs-lookup"><span data-stu-id="62ed2-144">This will set the value of the new element to the inner XML of the existing element.</span></span> <span data-ttu-id="62ed2-145">それ以外の場合に新しい要素の値を設定することができます、`Value`は既存の要素のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="62ed2-145">Otherwise, you can set the value of the new element to the `Value` property of the existing element.</span></span>

    <span data-ttu-id="62ed2-146">次のコード例は、すべてが置き換わります\<説明 > を持つ要素を\<抽象 > 要素。</span><span class="sxs-lookup"><span data-stu-id="62ed2-146">The following code example replaces all \<Description> elements with an \<Abstract> element.</span></span> <span data-ttu-id="62ed2-147">コンテンツ、\<説明 > 要素は、新しい保持\<抽象 > 要素を使用して、<xref:System.Xml.Linq.XContainer.Nodes%2A>のプロパティ、\<説明 ><xref:System.Xml.Linq.XElement>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="62ed2-147">The content of the \<Description> element is preserved in the new \<Abstract> element by using the <xref:System.Xml.Linq.XContainer.Nodes%2A> property of the \<Description> <xref:System.Xml.Linq.XElement> object.</span></span>

    [!code-vb[VbXmlSamples2#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#8)]

    <span data-ttu-id="62ed2-148">次は、サンプルのソース XML に示し、このコード例から XML に変更されました。</span><span class="sxs-lookup"><span data-stu-id="62ed2-148">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="62ed2-149">ソース XML:</span><span class="sxs-lookup"><span data-stu-id="62ed2-149">Source XML:</span></span>

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101">
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
        <Description>
          An in-depth look at creating applications
          with <technology>XML</technology>. For
          <audience>beginners</audience> or
          <audience>advanced</audience> developers.
        </Description>
      </Book>
      <Book id="bk331">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
        <Description>
          Get the expert insights, practical code samples, and best
          practices you need to advance your expertise with
          <technology>Visual Basic .NET</technology>.
          Learn how to create faster, more reliable applications
          based on professional, pragmatic guidance by today's top
          <audience>developers</audience>.
        </Description>
      </Book>
    </Catalog>
    ```

    <span data-ttu-id="62ed2-150">変更された XML:</span><span class="sxs-lookup"><span data-stu-id="62ed2-150">Modified XML:</span></span>

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101">
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <MSRP>44.95</MSRP>    <Abstract>
          An in-depth look at creating applications
          with <technology>XML</technology>. For
          <audience>beginners</audience> or
          <audience>advanced</audience> developers.
        </Abstract>
      </Book>
      <Book id="bk331">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <MSRP>45.95</MSRP>    <Abstract>
          Get the expert insights, practical code samples, and best
          practices you need to advance your expertise with
          <technology>Visual Basic .NET</technology>.
          Learn how to create faster, more reliable applications
          based on professional, pragmatic guidance by today's top
          <audience>developers</audience>.
        </Abstract>
      </Book>
    </Catalog>
    ```

## <a name="see-also"></a><span data-ttu-id="62ed2-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="62ed2-151">See also</span></span>

- [<span data-ttu-id="62ed2-152">Visual Basic での XML の操作</span><span class="sxs-lookup"><span data-stu-id="62ed2-152">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
- [<span data-ttu-id="62ed2-153">XML</span><span class="sxs-lookup"><span data-stu-id="62ed2-153">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="62ed2-154">方法: ファイル、文字列、または Stream から XML を読み込む</span><span class="sxs-lookup"><span data-stu-id="62ed2-154">How to: Load XML from a File, String, or Stream</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)
- [<span data-ttu-id="62ed2-155">LINQ</span><span class="sxs-lookup"><span data-stu-id="62ed2-155">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="62ed2-156">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="62ed2-156">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
