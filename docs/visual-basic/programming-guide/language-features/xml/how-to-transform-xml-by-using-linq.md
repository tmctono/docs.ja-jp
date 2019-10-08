---
title: '方法: LINQ を使用した XML の変換 (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], transforming
- LINQ to XML [Visual Basic], transforming XML
ms.assetid: 815687f4-0bc2-4c0b-adc6-d78744aa356f
ms.openlocfilehash: 08378775f2c30d8ebfcc4f7ceea6fc3ecb2066e5
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72003264"
---
# <a name="how-to-transform-xml-by-using-linq-visual-basic"></a><span data-ttu-id="2f05c-102">方法: LINQ を使用した XML の変換 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2f05c-102">How to: Transform XML by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="2f05c-103">[Xml リテラル](../../../../visual-basic/language-reference/xml-literals/index.md)を使用すると、1つのソースから xml を簡単に読み取り、新しい xml 形式に変換することができます。</span><span class="sxs-lookup"><span data-stu-id="2f05c-103">[XML Literals](../../../../visual-basic/language-reference/xml-literals/index.md) make it easy to read XML from one source and transform it to a new XML format.</span></span> <span data-ttu-id="2f05c-104">LINQ クエリを利用して、変換するコンテンツを取得したり、既存のドキュメントの内容を新しい XML 形式に変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="2f05c-104">You can take advantage of LINQ queries to retrieve the content to transform, or change content in an existing document to a new XML format.</span></span>  
  
 <span data-ttu-id="2f05c-105">このトピックの例では、XML ソースドキュメントから HTML にコンテンツを変換し、ブラウザーで表示されるようにします。</span><span class="sxs-lookup"><span data-stu-id="2f05c-105">The example in this topic transforms content from an XML source document to HTML to be viewed in a browser.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-transform-an-xml-document"></a><span data-ttu-id="2f05c-106">XML ドキュメントを変換するには</span><span class="sxs-lookup"><span data-stu-id="2f05c-106">To transform an XML document</span></span>  
  
1. <span data-ttu-id="2f05c-107">Visual Studio で、**コンソールアプリケーション**プロジェクトテンプレートに新しい Visual Basic プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="2f05c-107">In Visual Studio, create a new Visual Basic project in the **Console Application** project template.</span></span>  
  
2. <span data-ttu-id="2f05c-108">プロジェクトで作成された module1.vb ファイルをダブルクリックして、Visual Basic コードを変更します。</span><span class="sxs-lookup"><span data-stu-id="2f05c-108">Double-click the Module1.vb file created in the project to modify the Visual Basic code.</span></span> <span data-ttu-id="2f05c-109">@No__t-1 モジュールの `Sub Main` に次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="2f05c-109">Add the following code to the `Sub Main` of the `Module1` module.</span></span> <span data-ttu-id="2f05c-110">このコードでは、ソース XML ドキュメントを @no__t 0 オブジェクトとして作成します。</span><span class="sxs-lookup"><span data-stu-id="2f05c-110">This code creates the source XML document as an <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
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
  
     <span data-ttu-id="2f05c-111">[2 つのオブジェクトが等しいかどうかをテストする方法ファイル、文字列、または Stream から XML を読み込む](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)。</span><span class="sxs-lookup"><span data-stu-id="2f05c-111">[How to: Load XML from a File, String, or Stream](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md).</span></span>  
  
3. <span data-ttu-id="2f05c-112">ソース XML ドキュメントを作成するコードの後に、次のコードを追加して、オブジェクトからすべての @no__t 0Book > 要素を取得し、それらを HTML ドキュメントに変換します。</span><span class="sxs-lookup"><span data-stu-id="2f05c-112">After the code to create the source XML document, add the following code to retrieve all the \<Book> elements from the object and transform them into an HTML document.</span></span> <span data-ttu-id="2f05c-113">@No__t 0Book > 要素の一覧は、変換された HTML を含む <xref:System.Xml.Linq.XElement> オブジェクトのコレクションを返す LINQ クエリを使用して作成されます。</span><span class="sxs-lookup"><span data-stu-id="2f05c-113">The list of \<Book> elements is created by using a LINQ query that returns a collection of <xref:System.Xml.Linq.XElement> objects that contain the transformed HTML.</span></span> <span data-ttu-id="2f05c-114">埋め込み式を使用して、ソースドキュメントの値を新しい XML 形式で格納できます。</span><span class="sxs-lookup"><span data-stu-id="2f05c-114">You can use embedded expressions to put the values from the source document in the new XML format.</span></span>  
  
     <span data-ttu-id="2f05c-115">結果として得られる HTML ドキュメントは、<xref:System.Xml.Linq.XElement.Save%2A> メソッドを使用してファイルに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="2f05c-115">The resulting HTML document is written to a file by using the <xref:System.Xml.Linq.XElement.Save%2A> method.</span></span>  
  
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
  
4. <span data-ttu-id="2f05c-116">@No__t-1 の @no__t 後に、\<Description > ノードを指定された HTML 形式に変換する新しいメソッド (`Sub`) を追加します。</span><span class="sxs-lookup"><span data-stu-id="2f05c-116">After `Sub Main` of `Module1`, add a new method (`Sub`) to transform a \<Description> node into the specified HTML format.</span></span> <span data-ttu-id="2f05c-117">このメソッドは、前の手順のコードによって呼び出され、@no__t 0Description > 要素の形式を維持するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="2f05c-117">This method is called by the code in the previous step and is used to preserve the format of the \<Description> elements.</span></span>  
  
     <span data-ttu-id="2f05c-118">このメソッドは、\<Description > 要素のサブ要素を HTML に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="2f05c-118">This method replaces sub-elements of the \<Description> element with HTML.</span></span> <span data-ttu-id="2f05c-119">@No__t-0 メソッドは、サブ要素の場所を保持するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="2f05c-119">The `ReplaceWith` method is used to preserve the location of the sub-elements.</span></span> <span data-ttu-id="2f05c-120">@No__t-0Description > 要素の変換された内容は、HTML 段落 (@no__t 1p >) 要素に含まれます。</span><span class="sxs-lookup"><span data-stu-id="2f05c-120">The transformed content of the \<Description> element is included in an HTML paragraph (\<p>) element.</span></span> <span data-ttu-id="2f05c-121">@No__t-0 プロパティは、\<Description > 要素の変換された内容を取得するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="2f05c-121">The <xref:System.Xml.Linq.XContainer.Nodes%2A> property is used to retrieve the transformed content of the \<Description> element.</span></span> <span data-ttu-id="2f05c-122">これにより、変換されたコンテンツにサブ要素が含まれるようになります。</span><span class="sxs-lookup"><span data-stu-id="2f05c-122">This ensures that sub-elements are included in the transformed content.</span></span>  
  
     <span data-ttu-id="2f05c-123">@No__t-1 の `Sub Main` の後に次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="2f05c-123">Add the following code after `Sub Main` of `Module1`.</span></span>  
  
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
  
5. <span data-ttu-id="2f05c-124">変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="2f05c-124">Save your changes.</span></span>  
  
6. <span data-ttu-id="2f05c-125">F5 キーを押してコードを実行します。</span><span class="sxs-lookup"><span data-stu-id="2f05c-125">Press F5 to run the code.</span></span> <span data-ttu-id="2f05c-126">結果として保存されるドキュメントは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="2f05c-126">The resulting saved document will resemble the following:</span></span>  
  
    ```html  
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
  
## <a name="see-also"></a><span data-ttu-id="2f05c-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="2f05c-127">See also</span></span>

- [<span data-ttu-id="2f05c-128">XML リテラル</span><span class="sxs-lookup"><span data-stu-id="2f05c-128">XML Literals</span></span>](../../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="2f05c-129">Visual Basic での XML の操作</span><span class="sxs-lookup"><span data-stu-id="2f05c-129">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
- [<span data-ttu-id="2f05c-130">XML</span><span class="sxs-lookup"><span data-stu-id="2f05c-130">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- <span data-ttu-id="2f05c-131">[2 つのオブジェクトが等しいかどうかをテストする方法ファイル、文字列、またはストリームからの XML の読み込み @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="2f05c-131">[How to: Load XML from a File, String, or Stream](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)</span></span>
- [<span data-ttu-id="2f05c-132">LINQ</span><span class="sxs-lookup"><span data-stu-id="2f05c-132">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="2f05c-133">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="2f05c-133">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
