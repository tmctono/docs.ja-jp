---
title: XML 要素と XML 属性の名前を修飾する方法
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- qualifying XML names
- qualifying XML elements
- XML namespaces, qualifying elements and names in
ms.assetid: 44719f90-7e15-42e8-a9e2-282287e2b5bf
ms.openlocfilehash: db0795dd83cc96aba49dd435c875e98a9a6c18cb
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159872"
---
# <a name="how-to-qualify-xml-element-and-xml-attribute-names"></a><span data-ttu-id="fd28f-102">XML 要素と XML 属性の名前を修飾する方法</span><span class="sxs-lookup"><span data-stu-id="fd28f-102">How to qualify XML element and XML attribute names</span></span>

<span data-ttu-id="fd28f-103"><xref:System.Xml.Serialization.XmlSerializerNamespaces> クラスのインスタンスに含まれる XML 名前空間は、 [xml の名前空間](https://www.w3.org/TR/REC-xml-names/)と呼ばれる WORLD WIDE WEB コンソーシアム (W3C) の仕様に準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd28f-103">XML namespaces contained by instances of the <xref:System.Xml.Serialization.XmlSerializerNamespaces> class must conform to the World Wide Web Consortium (W3C) specification called [Namespaces in XML](https://www.w3.org/TR/REC-xml-names/).</span></span>

<span data-ttu-id="fd28f-104">XML 名前空間を使用すると、XML ドキュメント内の XML 要素および XML 属性の名前を修飾できます。</span><span class="sxs-lookup"><span data-stu-id="fd28f-104">XML namespaces provide a method for qualifying the names of XML elements and XML attributes in XML documents.</span></span> <span data-ttu-id="fd28f-105">修飾名は、プレフィックスとローカル名がコロンで区切られた構成になっています。</span><span class="sxs-lookup"><span data-stu-id="fd28f-105">A qualified name consists of a prefix and a local name, separated by a colon.</span></span> <span data-ttu-id="fd28f-106">プレフィックスはプレースホルダーとしてのみ機能し、名前空間を指定する URI に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="fd28f-106">The prefix functions only as a placeholder; it is mapped to a URI that specifies a namespace.</span></span> <span data-ttu-id="fd28f-107">汎用的に管理される URI 名前空間とローカル名を組み合わせることにより、生成される名前は、必ず汎用的に一意になります。</span><span class="sxs-lookup"><span data-stu-id="fd28f-107">The combination of the universally managed URI namespace and the local name produces a name that is guaranteed to be universally unique.</span></span>

<span data-ttu-id="fd28f-108">`XmlSerializerNamespaces` のインスタンスを作成し、そのオブジェクトに名前空間のペアを追加することで、XML ドキュメントで使用されるプレフィックスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="fd28f-108">By creating an instance of `XmlSerializerNamespaces` and adding the namespace pairs to the object, you can specify the prefixes used in an XML document.</span></span>

## <a name="to-create-qualified-names-in-an-xml-document"></a><span data-ttu-id="fd28f-109">XML ドキュメントにおける修飾名を作成するには</span><span class="sxs-lookup"><span data-stu-id="fd28f-109">To create qualified names in an XML document</span></span>

1. <span data-ttu-id="fd28f-110">`XmlSerializerNamespaces` クラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="fd28f-110">Create an instance of the `XmlSerializerNamespaces` class.</span></span>

2. <span data-ttu-id="fd28f-111">すべてのプレフィックスと名前空間のペアを `XmlSerializerNamespaces` に追加します。</span><span class="sxs-lookup"><span data-stu-id="fd28f-111">Add all prefixes and namespace pairs to the `XmlSerializerNamespaces`.</span></span>

3. <span data-ttu-id="fd28f-112">`System.Xml.Serialization` が XML ドキュメントにシリアル化する各メンバーやクラスに、適切な <xref:System.Xml.Serialization.XmlSerializer> 属性を適用します。</span><span class="sxs-lookup"><span data-stu-id="fd28f-112">Apply the appropriate `System.Xml.Serialization` attribute to each member or class that the <xref:System.Xml.Serialization.XmlSerializer> is to serialize into an XML document.</span></span>

    <span data-ttu-id="fd28f-113">適用できる属性は、<xref:System.Xml.Serialization.XmlAnyElementAttribute>、<xref:System.Xml.Serialization.XmlArrayAttribute>、<xref:System.Xml.Serialization.XmlArrayItemAttribute>、<xref:System.Xml.Serialization.XmlAttributeAttribute>、<xref:System.Xml.Serialization.XmlElementAttribute>、<xref:System.Xml.Serialization.XmlRootAttribute>、および <xref:System.Xml.Serialization.XmlTypeAttribute> です。</span><span class="sxs-lookup"><span data-stu-id="fd28f-113">The available attributes are: <xref:System.Xml.Serialization.XmlAnyElementAttribute>, <xref:System.Xml.Serialization.XmlArrayAttribute>, <xref:System.Xml.Serialization.XmlArrayItemAttribute>, <xref:System.Xml.Serialization.XmlAttributeAttribute>, <xref:System.Xml.Serialization.XmlElementAttribute>, <xref:System.Xml.Serialization.XmlRootAttribute>, and <xref:System.Xml.Serialization.XmlTypeAttribute>.</span></span>

4. <span data-ttu-id="fd28f-114">各属性の `Namespace` プロパティを、`XmlSerializerNamespaces` のいずれかの名前空間値に設定します。</span><span class="sxs-lookup"><span data-stu-id="fd28f-114">Set the `Namespace` property of each attribute to one of the namespace values from the `XmlSerializerNamespaces`.</span></span>

5. <span data-ttu-id="fd28f-115">`XmlSerializerNamespaces` を `Serialize` の `XmlSerializer` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="fd28f-115">Pass the `XmlSerializerNamespaces` to the `Serialize` method of the `XmlSerializer`.</span></span>

## <a name="example"></a><span data-ttu-id="fd28f-116">例</span><span class="sxs-lookup"><span data-stu-id="fd28f-116">Example</span></span>

<span data-ttu-id="fd28f-117">`XmlSerializerNamespaces` を作成し、このオブジェクトにプレフィックスと名前空間のペアを 2 つ追加する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="fd28f-117">The following example creates an `XmlSerializerNamespaces`, and adds two prefix and namespace pairs to the object.</span></span> <span data-ttu-id="fd28f-118">このコードでは、`XmlSerializer` クラスのインスタンスをシリアル化するために使用される `Books` を作成します。</span><span class="sxs-lookup"><span data-stu-id="fd28f-118">The code creates an `XmlSerializer` that is used to serialize an instance of the `Books` class.</span></span> <span data-ttu-id="fd28f-119">また、`Serialize` を使用して `XmlSerializerNamespaces` メソッドを呼び出し、XML にプレフィックス付き名前空間を含めることができるようにします。</span><span class="sxs-lookup"><span data-stu-id="fd28f-119">The code calls the `Serialize` method with the `XmlSerializerNamespaces`, allowing the XML to contain prefixed namespaces.</span></span>

```vb
Imports System.IO
Imports System.Xml
Imports System.Xml.Serialization

Public Module Program

    Public Sub Main()
        SerializeObject("XmlNamespaces.xml")
    End Sub

    Public Sub SerializeObject(filename As String)
        Dim mySerializer As New XmlSerializer(GetType(Books))
        ' Writing a file requires a TextWriter.
        Dim myWriter As New StreamWriter(filename)

        ' Creates an XmlSerializerNamespaces and adds two
        ' prefix-namespace pairs.
        Dim myNamespaces As New XmlSerializerNamespaces()
        myNamespaces.Add("books", "http://www.cpandl.com")
        myNamespaces.Add("money", "http://www.cohowinery.com")

        ' Creates a Book.
        Dim myBook As New Book()
        myBook.TITLE = "A Book Title"
        Dim myPrice As New Price()
        myPrice.price = CDec(9.95)
        myPrice.currency = "US Dollar"
        myBook.PRICE = myPrice
        Dim myBooks As New Books()
        myBooks.Book = myBook
        mySerializer.Serialize(myWriter, myBooks, myNamespaces)
        myWriter.Close()
    End Sub
End Module

Public Class Books
    <XmlElement([Namespace] := "http://www.cohowinery.com")> _
    Public Book As Book
End Class

<XmlType([Namespace] := "http://www.cpandl.com")> _
Public Class Book
    <XmlElement([Namespace] := "http://www.cpandl.com")> _
    Public TITLE As String
    <XmlElement([Namespace] := "http://www.cohowinery.com")> _
    Public PRICE As Price
End Class

Public Class Price
    <XmlAttribute([Namespace] := "http://www.cpandl.com")> _
    Public currency As String
    <XmlElement([Namespace] := "http://www.cohowinery.com")> _
    Public price As Decimal
End Class
```

```csharp
using System;
using System.IO;
using System.Xml;
using System.Xml.Serialization;

public class Program
{
    public static void Main()
    {
        SerializeObject("XmlNamespaces.xml");
    }

    public static void SerializeObject(string filename)
    {
        var mySerializer = new XmlSerializer(typeof(Books));
        // Writing a file requires a TextWriter.
        TextWriter myWriter = new StreamWriter(filename);

        // Creates an XmlSerializerNamespaces and adds two
        // prefix-namespace pairs.
        var myNamespaces = new XmlSerializerNamespaces();
        myNamespaces.Add("books", "http://www.cpandl.com");
        myNamespaces.Add("money", "http://www.cohowinery.com");

        // Creates a Book.
        var myBook = new Book();
        myBook.TITLE = "A Book Title";
        var myPrice = new Price();
        myPrice.price = (decimal) 9.95;
        myPrice.currency = "US Dollar";
        myBook.PRICE = myPrice;
        var myBooks = new Books();
        myBooks.Book = myBook;
        mySerializer.Serialize(myWriter, myBooks, myNamespaces);
        myWriter.Close();
    }
}

public class Books
{
    [XmlElement(Namespace = "http://www.cohowinery.com")]
    public Book Book;
}

[XmlType(Namespace ="http://www.cpandl.com")]
public class Book
{
    [XmlElement(Namespace = "http://www.cpandl.com")]
    public string TITLE;
    [XmlElement(Namespace ="http://www.cohowinery.com")]
    public Price PRICE;
}

public class Price
{
    [XmlAttribute(Namespace = "http://www.cpandl.com")]
    public string currency;
    [XmlElement(Namespace = "http://www.cohowinery.com")]
    public decimal price;
}
```

## <a name="see-also"></a><span data-ttu-id="fd28f-120">参照</span><span class="sxs-lookup"><span data-stu-id="fd28f-120">See also</span></span>

- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="fd28f-121">XML スキーマ定義ツールと XML シリアル化</span><span class="sxs-lookup"><span data-stu-id="fd28f-121">The XML Schema Definition Tool and XML Serialization</span></span>](the-xml-schema-definition-tool-and-xml-serialization.md)
- [<span data-ttu-id="fd28f-122">XML シリアル化の概要</span><span class="sxs-lookup"><span data-stu-id="fd28f-122">Introducing XML Serialization</span></span>](introducing-xml-serialization.md)
- [<span data-ttu-id="fd28f-123">XmlSerializer クラス</span><span class="sxs-lookup"><span data-stu-id="fd28f-123">XmlSerializer Class</span></span>](xref:System.Xml.Serialization.XmlSerializer)
- [<span data-ttu-id="fd28f-124">XML シリアル化を制御する属性</span><span class="sxs-lookup"><span data-stu-id="fd28f-124">Attributes That Control XML Serialization</span></span>](attributes-that-control-xml-serialization.md)
- [<span data-ttu-id="fd28f-125">方法 : XML ストリームの代替要素名を指定する</span><span class="sxs-lookup"><span data-stu-id="fd28f-125">How to: Specify an Alternate Element Name for an XML Stream</span></span>](how-to-specify-an-alternate-element-name-for-an-xml-stream.md)
- [<span data-ttu-id="fd28f-126">方法 : オブジェクトをシリアル化する</span><span class="sxs-lookup"><span data-stu-id="fd28f-126">How to: Serialize an Object</span></span>](how-to-serialize-an-object.md)
- [<span data-ttu-id="fd28f-127">方法 : オブジェクトを逆シリアル化する</span><span class="sxs-lookup"><span data-stu-id="fd28f-127">How to: Deserialize an Object</span></span>](how-to-deserialize-an-object.md)
