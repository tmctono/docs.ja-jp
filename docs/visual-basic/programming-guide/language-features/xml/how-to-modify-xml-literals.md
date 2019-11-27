---
title: '方法 : XML リテラルの変更'
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], Value
- XML literals [Visual Basic]
- XML literals [Visual Basic], modifying
ms.assetid: 4e864522-a37a-43a2-8236-af80277c5482
ms.openlocfilehash: 99ec35addcb9fc8d886c9151cde87227b5113eb9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330857"
---
# <a name="how-to-modify-xml-literals-visual-basic"></a><span data-ttu-id="5d2d9-102">方法 : XML リテラルを変更する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d2d9-102">How to: Modify XML Literals (Visual Basic)</span></span>

<span data-ttu-id="5d2d9-103">Visual Basic には、XML リテラルを変更する便利な方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="5d2d9-103">Visual Basic provides convenient ways to modify XML literals.</span></span> <span data-ttu-id="5d2d9-104">要素と属性を追加したり削除したりできます。また、既存の要素を新しい XML 要素に置き換えることもできます。</span><span class="sxs-lookup"><span data-stu-id="5d2d9-104">You can add or delete elements and attributes, and you can also replace an existing element with a new XML element.</span></span> <span data-ttu-id="5d2d9-105">このトピックでは、既存の XML リテラルを変更する方法の例をいくつか紹介します。</span><span class="sxs-lookup"><span data-stu-id="5d2d9-105">This topic provides several examples of how to modify an existing XML literal.</span></span>

### <a name="to-modify-the-value-of-an-xml-literal"></a><span data-ttu-id="5d2d9-106">XML リテラルの値を変更するには</span><span class="sxs-lookup"><span data-stu-id="5d2d9-106">To modify the value of an XML literal</span></span>

1. <span data-ttu-id="5d2d9-107">XML リテラルの値を変更するには、XML リテラルへの参照を取得し、`Value` プロパティを目的の値に設定します。</span><span class="sxs-lookup"><span data-stu-id="5d2d9-107">To modify the value of an XML literal, obtain a reference to the XML literal and set the `Value` property to the desired value.</span></span>

    <span data-ttu-id="5d2d9-108">次のコード例では、XML ドキュメント内のすべての \<Price > 要素の値を更新します。</span><span class="sxs-lookup"><span data-stu-id="5d2d9-108">The following code example updates the value of all the \<Price> elements in an XML document.</span></span>

    [!code-vb[VbXmlSamples2#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#4)]

    <span data-ttu-id="5d2d9-109">次に、このコード例のソース XML と変更された XML の例を示します。</span><span class="sxs-lookup"><span data-stu-id="5d2d9-109">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="5d2d9-110">ソース XML:</span><span class="sxs-lookup"><span data-stu-id="5d2d9-110">Source XML:</span></span>

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

    <span data-ttu-id="5d2d9-111">変更された XML:</span><span class="sxs-lookup"><span data-stu-id="5d2d9-111">Modified XML:</span></span>

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
    > <span data-ttu-id="5d2d9-112">`Value` プロパティは、コレクション内の最初の XML 要素を参照します。</span><span class="sxs-lookup"><span data-stu-id="5d2d9-112">The `Value` property refers to the first XML element in a collection.</span></span> <span data-ttu-id="5d2d9-113">コレクション内に同じ名前の要素が複数ある場合、`Value` プロパティの設定は、コレクション内の最初の要素にのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="5d2d9-113">If there is more than one element that has the same name in a collection, setting the `Value` property affects only the first element in the collection.</span></span>

### <a name="to-add-an-attribute-to-an-xml-literal"></a><span data-ttu-id="5d2d9-114">XML リテラルに属性を追加するには</span><span class="sxs-lookup"><span data-stu-id="5d2d9-114">To add an attribute to an XML literal</span></span>

1. <span data-ttu-id="5d2d9-115">XML リテラルに属性を追加するには、最初に XML リテラルへの参照を取得します。</span><span class="sxs-lookup"><span data-stu-id="5d2d9-115">To add an attribute to an XML literal, first obtain a reference to the XML literal.</span></span> <span data-ttu-id="5d2d9-116">その後、新しい XML 属性軸プロパティを追加して、属性を追加できます。</span><span class="sxs-lookup"><span data-stu-id="5d2d9-116">You can then add an attribute by adding a new XML attribute axis property.</span></span> <span data-ttu-id="5d2d9-117">また、<xref:System.Xml.Linq.XContainer.Add%2A> メソッドを使用して、新しい <xref:System.Xml.Linq.XAttribute> オブジェクトを XML リテラルに追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="5d2d9-117">You can also add a new <xref:System.Xml.Linq.XAttribute> object to the XML literal by using the <xref:System.Xml.Linq.XContainer.Add%2A> method.</span></span> <span data-ttu-id="5d2d9-118">次の例では、両方のオプションを示します。</span><span class="sxs-lookup"><span data-stu-id="5d2d9-118">The following example shows both options.</span></span>

    [!code-vb[VbXmlSamples2#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#5)]

    <span data-ttu-id="5d2d9-119">次に、このコード例のソース XML と変更された XML の例を示します。</span><span class="sxs-lookup"><span data-stu-id="5d2d9-119">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="5d2d9-120">ソース XML:</span><span class="sxs-lookup"><span data-stu-id="5d2d9-120">Source XML:</span></span>

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

    <span data-ttu-id="5d2d9-121">変更された XML:</span><span class="sxs-lookup"><span data-stu-id="5d2d9-121">Modified XML:</span></span>

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

    <span data-ttu-id="5d2d9-122">XML 属性軸のプロパティの詳細については、「 [Xml 属性軸](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)のプロパティ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d2d9-122">For more information about XML attribute axis properties, see [XML Attribute Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md).</span></span>

### <a name="to-add-an-element-to-an-xml-literal"></a><span data-ttu-id="5d2d9-123">XML リテラルに要素を追加するには</span><span class="sxs-lookup"><span data-stu-id="5d2d9-123">To add an element to an XML literal</span></span>

1. <span data-ttu-id="5d2d9-124">XML リテラルに要素を追加するには、最初に XML リテラルへの参照を取得します。</span><span class="sxs-lookup"><span data-stu-id="5d2d9-124">To add an element to an XML literal, first obtain a reference to the XML literal.</span></span> <span data-ttu-id="5d2d9-125">次に、<xref:System.Xml.Linq.XContainer.Add%2A> メソッドを使用して、新しい <xref:System.Xml.Linq.XElement> オブジェクトを要素の最後のサブ要素として追加できます。</span><span class="sxs-lookup"><span data-stu-id="5d2d9-125">You can then add a new <xref:System.Xml.Linq.XElement> object as the last sub-element of the element by using the <xref:System.Xml.Linq.XContainer.Add%2A> method.</span></span> <span data-ttu-id="5d2d9-126"><xref:System.Xml.Linq.XContainer.AddFirst%2A> メソッドを使用して、新しい <xref:System.Xml.Linq.XElement> オブジェクトを最初のサブ要素として追加できます。</span><span class="sxs-lookup"><span data-stu-id="5d2d9-126">You can add a new <xref:System.Xml.Linq.XElement> object as the first sub-element by using the <xref:System.Xml.Linq.XContainer.AddFirst%2A> method.</span></span>

    <span data-ttu-id="5d2d9-127">他のサブ要素を基準として、特定の位置に新しい要素を追加するには、最初に隣接するサブ要素への参照を取得します。</span><span class="sxs-lookup"><span data-stu-id="5d2d9-127">To add a new element in a specific location relative to other sub-elements, first obtain a reference to an adjacent sub-element.</span></span> <span data-ttu-id="5d2d9-128">次に、<xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> メソッドを使用して、隣接するサブ要素の前に新しい <xref:System.Xml.Linq.XElement> オブジェクトを追加できます。</span><span class="sxs-lookup"><span data-stu-id="5d2d9-128">You can then add the new <xref:System.Xml.Linq.XElement> object before the adjacent sub-element by using the <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> method.</span></span> <span data-ttu-id="5d2d9-129"><xref:System.Xml.Linq.XNode.AddAfterSelf%2A> メソッドを使用して、隣接するサブ要素の後に新しい <xref:System.Xml.Linq.XElement> オブジェクトを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="5d2d9-129">You can also add the new <xref:System.Xml.Linq.XElement> object after the adjacent sub-element by using the <xref:System.Xml.Linq.XNode.AddAfterSelf%2A> method.</span></span>

    <span data-ttu-id="5d2d9-130">次の例は、これらの各手法の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="5d2d9-130">The following example shows examples of each of these techniques.</span></span>

    [!code-vb[VbXmlSamples2#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#6)]

    <span data-ttu-id="5d2d9-131">次に、このコード例のソース XML と変更された XML の例を示します。</span><span class="sxs-lookup"><span data-stu-id="5d2d9-131">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="5d2d9-132">ソース XML:</span><span class="sxs-lookup"><span data-stu-id="5d2d9-132">Source XML:</span></span>

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

    <span data-ttu-id="5d2d9-133">変更された XML:</span><span class="sxs-lookup"><span data-stu-id="5d2d9-133">Modified XML:</span></span>

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

### <a name="to-remove-an-element-or-attribute-from-an-xml-literal"></a><span data-ttu-id="5d2d9-134">XML リテラルから要素または属性を削除するには</span><span class="sxs-lookup"><span data-stu-id="5d2d9-134">To remove an element or attribute from an XML literal</span></span>

1. <span data-ttu-id="5d2d9-135">XML リテラルから要素または属性を削除するには、次の例に示すように、要素または属性への参照を取得し、`Remove` メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="5d2d9-135">To remove an element or an attribute from an XML literal, obtain a reference to the element or attribute and call the `Remove` method, as shown in the following example.</span></span>

    [!code-vb[VbXmlSamples2#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#7)]

    <span data-ttu-id="5d2d9-136">次に、このコード例のソース XML と変更された XML の例を示します。</span><span class="sxs-lookup"><span data-stu-id="5d2d9-136">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="5d2d9-137">ソース XML:</span><span class="sxs-lookup"><span data-stu-id="5d2d9-137">Source XML:</span></span>

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

    <span data-ttu-id="5d2d9-138">変更された XML:</span><span class="sxs-lookup"><span data-stu-id="5d2d9-138">Modified XML:</span></span>

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

    <span data-ttu-id="5d2d9-139">XML リテラルからすべての要素または属性を削除するには、XML リテラルへの参照を取得し、<xref:System.Xml.Linq.XElement.RemoveAll%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="5d2d9-139">To remove all elements or attributes from an XML literal, obtain a reference to the XML literal and call the <xref:System.Xml.Linq.XElement.RemoveAll%2A> method.</span></span>

### <a name="to-modify-an-xml-literal"></a><span data-ttu-id="5d2d9-140">XML リテラルを変更するには</span><span class="sxs-lookup"><span data-stu-id="5d2d9-140">To modify an XML literal</span></span>

1. <span data-ttu-id="5d2d9-141">XML 要素の名前を変更するには、最初に要素への参照を取得します。</span><span class="sxs-lookup"><span data-stu-id="5d2d9-141">To change the name of an XML element, first obtain a reference to the element.</span></span> <span data-ttu-id="5d2d9-142">次に、新しい名前を持つ新しい <xref:System.Xml.Linq.XElement> オブジェクトを作成し、新しい <xref:System.Xml.Linq.XElement> オブジェクトを既存の <xref:System.Xml.Linq.XElement> オブジェクトの <xref:System.Xml.Linq.XNode.ReplaceWith%2A> メソッドに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="5d2d9-142">You can then create a new <xref:System.Xml.Linq.XElement> object that has a new name and pass the new <xref:System.Xml.Linq.XElement> object to the <xref:System.Xml.Linq.XNode.ReplaceWith%2A> method of the existing <xref:System.Xml.Linq.XElement> object.</span></span>

    <span data-ttu-id="5d2d9-143">置換する要素に保持する必要があるサブ要素がある場合は、新しい <xref:System.Xml.Linq.XElement> オブジェクトの値を既存の要素の <xref:System.Xml.Linq.XContainer.Nodes%2A> プロパティに設定します。</span><span class="sxs-lookup"><span data-stu-id="5d2d9-143">If the element that you are replacing has sub-elements that must be preserved, set the value of the new <xref:System.Xml.Linq.XElement> object to the <xref:System.Xml.Linq.XContainer.Nodes%2A> property of the existing element.</span></span> <span data-ttu-id="5d2d9-144">これにより、新しい要素の値が既存の要素の内部 XML に設定されます。</span><span class="sxs-lookup"><span data-stu-id="5d2d9-144">This will set the value of the new element to the inner XML of the existing element.</span></span> <span data-ttu-id="5d2d9-145">それ以外の場合は、新しい要素の値を、既存の要素の `Value` プロパティに設定できます。</span><span class="sxs-lookup"><span data-stu-id="5d2d9-145">Otherwise, you can set the value of the new element to the `Value` property of the existing element.</span></span>

    <span data-ttu-id="5d2d9-146">次のコード例では、すべての \<Description > 要素を \<抽象 > 要素に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="5d2d9-146">The following code example replaces all \<Description> elements with an \<Abstract> element.</span></span> <span data-ttu-id="5d2d9-147">\<Description > 要素の内容は、<xref:System.Xml.Linq.XContainer.Nodes%2A> の説明 \<オブジェクトの > のプロパティを使用して、新しい \<抽象 > 要素に保持されます。<xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="5d2d9-147">The content of the \<Description> element is preserved in the new \<Abstract> element by using the <xref:System.Xml.Linq.XContainer.Nodes%2A> property of the \<Description> <xref:System.Xml.Linq.XElement> object.</span></span>

    [!code-vb[VbXmlSamples2#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#8)]

    <span data-ttu-id="5d2d9-148">次に、このコード例のソース XML と変更された XML の例を示します。</span><span class="sxs-lookup"><span data-stu-id="5d2d9-148">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="5d2d9-149">ソース XML:</span><span class="sxs-lookup"><span data-stu-id="5d2d9-149">Source XML:</span></span>

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

    <span data-ttu-id="5d2d9-150">変更された XML:</span><span class="sxs-lookup"><span data-stu-id="5d2d9-150">Modified XML:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="5d2d9-151">参照</span><span class="sxs-lookup"><span data-stu-id="5d2d9-151">See also</span></span>

- [<span data-ttu-id="5d2d9-152">Visual Basic での XML の操作</span><span class="sxs-lookup"><span data-stu-id="5d2d9-152">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
- [<span data-ttu-id="5d2d9-153">XML</span><span class="sxs-lookup"><span data-stu-id="5d2d9-153">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="5d2d9-154">方法 : ファイル、文字列、またはストリームからの XML の読み込み</span><span class="sxs-lookup"><span data-stu-id="5d2d9-154">How to: Load XML from a File, String, or Stream</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)
- [<span data-ttu-id="5d2d9-155">LINQ</span><span class="sxs-lookup"><span data-stu-id="5d2d9-155">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="5d2d9-156">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="5d2d9-156">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
