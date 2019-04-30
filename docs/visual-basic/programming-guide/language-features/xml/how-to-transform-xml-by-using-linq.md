---
title: '方法: LINQ (Visual Basic) を使用した XML を変換します。'
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], transforming
- LINQ to XML [Visual Basic], transforming XML
ms.assetid: 815687f4-0bc2-4c0b-adc6-d78744aa356f
ms.openlocfilehash: c34d3988c89e0ce07676e9181200fc039010b50a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62028435"
---
# <a name="how-to-transform-xml-by-using-linq-visual-basic"></a><span data-ttu-id="564e7-102">方法: LINQ (Visual Basic) を使用した XML を変換します。</span><span class="sxs-lookup"><span data-stu-id="564e7-102">How to: Transform XML by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="564e7-103">[XML リテラル](../../../../visual-basic/language-reference/xml-literals/index.md)簡単に 1 つのソースから XML を読み取るし、新しい XML 形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="564e7-103">[XML Literals](../../../../visual-basic/language-reference/xml-literals/index.md) make it easy to read XML from one source and transform it to a new XML format.</span></span> <span data-ttu-id="564e7-104">変換、コンテンツを取得する LINQ クエリを利用したり、既存のドキュメントの内容を新しい XML 形式に変更できます。</span><span class="sxs-lookup"><span data-stu-id="564e7-104">You can take advantage of LINQ queries to retrieve the content to transform, or change content in an existing document to a new XML format.</span></span>  
  
 <span data-ttu-id="564e7-105">このトピックの例では、XML ソース ドキュメントからブラウザーで表示する HTML へのコンテンツを変換します。</span><span class="sxs-lookup"><span data-stu-id="564e7-105">The example in this topic transforms content from an XML source document to HTML to be viewed in a browser.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-transform-an-xml-document"></a><span data-ttu-id="564e7-106">XML ドキュメントを変換するには</span><span class="sxs-lookup"><span data-stu-id="564e7-106">To transform an XML document</span></span>  
  
1. <span data-ttu-id="564e7-107">Visual Studio で、新しい Visual Basic プロジェクトを作成、**コンソール アプリケーション**プロジェクト テンプレート。</span><span class="sxs-lookup"><span data-stu-id="564e7-107">In Visual Studio, create a new Visual Basic project in the **Console Application** project template.</span></span>  
  
2. <span data-ttu-id="564e7-108">Visual Basic コードを変更するプロジェクトで作成した Module1.vb ファイルをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="564e7-108">Double-click the Module1.vb file created in the project to modify the Visual Basic code.</span></span> <span data-ttu-id="564e7-109">次のコードを追加、`Sub Main`の`Module1`モジュール。</span><span class="sxs-lookup"><span data-stu-id="564e7-109">Add the following code to the `Sub Main` of the `Module1` module.</span></span> <span data-ttu-id="564e7-110">このコードではソース XML ドキュメントとして、<xref:System.Xml.Linq.XDocument>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="564e7-110">This code creates the source XML document as an <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
    ```vb  
    Dim catalog =   
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
              Get the expert insights, practical code samples,   
              and best practices you need   
              to advance your expertise with <technology>Visual   
              Basic .NET</technology>.   
              Learn how to create faster, more reliable applications  
              based on professional,   
              pragmatic guidance by today's top <audience>developers</audience>.  
            </Description>  
          </Book>  
        </Catalog>  
    ```  
  
     <span data-ttu-id="564e7-111">[方法: ファイル、文字列、または Stream から XML を読み込む](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)。</span><span class="sxs-lookup"><span data-stu-id="564e7-111">[How to: Load XML from a File, String, or Stream](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md).</span></span>  
  
3. <span data-ttu-id="564e7-112">、元の XML ドキュメントを作成するコードの後に、すべてを取得する次のコードを追加、\<書籍 > オブジェクトの要素を HTML ドキュメントに変換します。</span><span class="sxs-lookup"><span data-stu-id="564e7-112">After the code to create the source XML document, add the following code to retrieve all the \<Book> elements from the object and transform them into an HTML document.</span></span> <span data-ttu-id="564e7-113">一覧\<Book > 要素のコレクションを返す LINQ クエリを使用して作成<xref:System.Xml.Linq.XElement>変換後の HTML が含まれているオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="564e7-113">The list of \<Book> elements is created by using a LINQ query that returns a collection of <xref:System.Xml.Linq.XElement> objects that contain the transformed HTML.</span></span> <span data-ttu-id="564e7-114">埋め込み式を使用すると、新しい XML 形式でソース ドキュメントからの値を入力します。</span><span class="sxs-lookup"><span data-stu-id="564e7-114">You can use embedded expressions to put the values from the source document in the new XML format.</span></span>  
  
     <span data-ttu-id="564e7-115">使用して、結果の HTML ドキュメントがファイルに書き込まれます、<xref:System.Xml.Linq.XElement.Save%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="564e7-115">The resulting HTML document is written to a file by using the <xref:System.Xml.Linq.XElement.Save%2A> method.</span></span>  
  
    ```vb  
    Dim htmlOutput =   
      <html>  
        <body>  
          <%= From book In catalog.<Catalog>.<Book>   
              Select <div>  
                       <h1><%= book.<Title>.Value %></h1>  
                       <h3><%= "By " & book.<Author>.Value %></h3>  
                        <h3><%= "Price = " & book.<Price>.Value %></h3>  
                        <h2>Description</h2>  
                        <%= TransformDescription(book.<Description>(0)) %>  
                        <hr/>  
                      </div> %>  
        </body>  
      </html>  
  
    htmlOutput.Save("BookDescription.html")  
    ```  
  
4. <span data-ttu-id="564e7-116">後`Sub Main`の`Module1`、新しいメソッドを追加 (`Sub`) に変換する、\<説明 > ノードが指定された HTML 形式にします。</span><span class="sxs-lookup"><span data-stu-id="564e7-116">After `Sub Main` of `Module1`, add a new method (`Sub`) to transform a \<Description> node into the specified HTML format.</span></span> <span data-ttu-id="564e7-117">このメソッドは、前の手順のコードによって呼び出されの形式を保持するために使用、 \<Description > 要素。</span><span class="sxs-lookup"><span data-stu-id="564e7-117">This method is called by the code in the previous step and is used to preserve the format of the \<Description> elements.</span></span>  
  
     <span data-ttu-id="564e7-118">このメソッドのサブ要素が置き換えられます、\<説明 > を持つ HTML 要素。</span><span class="sxs-lookup"><span data-stu-id="564e7-118">This method replaces sub-elements of the \<Description> element with HTML.</span></span> <span data-ttu-id="564e7-119">`ReplaceWith`メソッドは、サブ要素の位置を保持するために使用します。</span><span class="sxs-lookup"><span data-stu-id="564e7-119">The `ReplaceWith` method is used to preserve the location of the sub-elements.</span></span> <span data-ttu-id="564e7-120">変換後のコンテンツ、\<説明 > 要素は、HTML の段落に含まれます (\<p >) 要素。</span><span class="sxs-lookup"><span data-stu-id="564e7-120">The transformed content of the \<Description> element is included in an HTML paragraph (\<p>) element.</span></span> <span data-ttu-id="564e7-121"><xref:System.Xml.Linq.XContainer.Nodes%2A>の変換後のコンテンツを取得するプロパティが使用される、 \<Description > 要素。</span><span class="sxs-lookup"><span data-stu-id="564e7-121">The <xref:System.Xml.Linq.XContainer.Nodes%2A> property is used to retrieve the transformed content of the \<Description> element.</span></span> <span data-ttu-id="564e7-122">これにより、変換後のコンテンツにサブ要素が含まれること。</span><span class="sxs-lookup"><span data-stu-id="564e7-122">This ensures that sub-elements are included in the transformed content.</span></span>  
  
     <span data-ttu-id="564e7-123">後は、次のコードを追加`Sub Main`の`Module1`します。</span><span class="sxs-lookup"><span data-stu-id="564e7-123">Add the following code after `Sub Main` of `Module1`.</span></span>  
  
    ```vb  
    Public Function TransformDescription(ByVal desc As XElement) As XElement  
  
      ' Replace <technology> elements with <b>.  
      Dim content = (From element In desc...<technology>).ToList()  
  
      If content.Count > 0 Then  
        For i = 0 To content.Count - 1  
          content(i).ReplaceWith(<b><%= content(i).Value %></b>)  
        Next  
      End If  
  
      ' Replace <audience> elements with <i>.  
      content = (From element In desc...<audience>).ToList()  
  
      If content.Count > 0 Then  
        For i = 0 To content.Count - 1  
          content(i).ReplaceWith(<i><%= content(i).Value %></i>)  
        Next  
      End If  
  
      ' Return the updated contents of the <Description> element.  
      Return <p><%= desc.Nodes %></p>  
    End Function  
    ```  
  
5. <span data-ttu-id="564e7-124">変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="564e7-124">Save your changes.</span></span>  
  
6. <span data-ttu-id="564e7-125">F5 キーを押して、コードを実行します。</span><span class="sxs-lookup"><span data-stu-id="564e7-125">Press F5 to run the code.</span></span> <span data-ttu-id="564e7-126">保存されたドキュメントは次のようにします。</span><span class="sxs-lookup"><span data-stu-id="564e7-126">The resulting saved document will resemble the following:</span></span>  
  
    ```  
    <?xml version="1.0"?>  
    <html>  
      <body>  
        <div>  
          <h1>XML Developer's Guide</h1>  
          <h3>By Garghentini, Davide</h3>  
          <h3>Price = 44.95</h3>  
          <h2>Description</h2>  
          <p>  
            An in-depth look at creating applications  
            with <b>XML</b>. For   
            <i>beginners</i> or   
            <i>advanced</i> developers.  
          </p>  
          <hr />  
        </div>  
        <div>  
          <h1>Developing Applications with Visual Basic .NET</h1>  
          <h3>By Spencer, Phil</h3>  
          <h3>Price = 45.95</h3>  
          <h2>Description</h2>  
          <p>  
            Get the expert insights, practical code   
            samples, and best practices you need   
            to advance your expertise with <b>Visual   
            Basic .NET</b>. Learn how to create faster,  
            more reliable applications based on  
            professional, pragmatic guidance by today's   
            top <i>developers</i>.  
          </p>  
          <hr />  
        </div>  
      </body>  
    </html>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="564e7-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="564e7-127">See also</span></span>

- [<span data-ttu-id="564e7-128">XML リテラル</span><span class="sxs-lookup"><span data-stu-id="564e7-128">XML Literals</span></span>](../../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="564e7-129">Visual Basic での XML の操作</span><span class="sxs-lookup"><span data-stu-id="564e7-129">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
- [<span data-ttu-id="564e7-130">XML</span><span class="sxs-lookup"><span data-stu-id="564e7-130">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="564e7-131">方法: ファイル、文字列、または Stream から XML を読み込む</span><span class="sxs-lookup"><span data-stu-id="564e7-131">How to: Load XML from a File, String, or Stream</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)
- [<span data-ttu-id="564e7-132">LINQ</span><span class="sxs-lookup"><span data-stu-id="564e7-132">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="564e7-133">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="564e7-133">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
