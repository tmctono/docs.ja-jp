---
title: '方法: ファイル、文字列、またはストリームからの XML の読み込み (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
ms.openlocfilehash: ba88ae19abc216a318d6c2069ab0846d5db8a346
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71054173"
---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a><span data-ttu-id="bfe3f-102">方法: ファイル、文字列、またはストリームからの XML の読み込み (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bfe3f-102">How to: Load XML from a File, String, or Stream (Visual Basic)</span></span>

<span data-ttu-id="bfe3f-103">[XML リテラル](../../../../visual-basic/language-reference/xml-literals/index.md)を作成し、複数のメソッドを使用して、ファイル、文字列、ストリームなどの外部ソースからの内容を読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="bfe3f-103">You can create [XML Literals](../../../../visual-basic/language-reference/xml-literals/index.md) and populate them with the contents from an external source such as a file, a string, or a stream by using several methods.</span></span> <span data-ttu-id="bfe3f-104">これらのメソッドを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="bfe3f-104">These methods are shown in the following examples.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-load-xml-from-a-file"></a><span data-ttu-id="bfe3f-105">ファイルから XML を読み込むには</span><span class="sxs-lookup"><span data-stu-id="bfe3f-105">To load XML from a file</span></span>

<span data-ttu-id="bfe3f-106">ファイル<xref:System.Xml.Linq.XElement>やオブジェクトなどの XML リテラルにデータ<xref:System.Xml.Linq.XDocument>を設定するには、 `Load`メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="bfe3f-106">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a file, use the `Load` method.</span></span> <span data-ttu-id="bfe3f-107">このメソッドは、ファイルパス、テキストストリーム、または XML ストリームを入力として受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="bfe3f-107">This method can take a file path, text stream, or XML stream as input.</span></span>

<span data-ttu-id="bfe3f-108">次のコード例では、 <xref:System.Xml.Linq.XDocument.Load%28System.String%29>メソッドを使用して、テキストファイルの XML を使用して<xref:System.Xml.Linq.XDocument>オブジェクトを設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bfe3f-108">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Load%28System.String%29> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a text file.</span></span>

[!code-vb[VbXMLSamples#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#43)]

## <a name="to-load-xml-from-a-string"></a><span data-ttu-id="bfe3f-109">文字列から XML を読み込むには</span><span class="sxs-lookup"><span data-stu-id="bfe3f-109">To load XML from a string</span></span>

<span data-ttu-id="bfe3f-110">オブジェクト<xref:System.Xml.Linq.XElement> `Parse`や<xref:System.Xml.Linq.XDocument>オブジェクトなどの XML リテラルに文字列を設定するには、メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="bfe3f-110">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a string, you can use the `Parse` method.</span></span>

<span data-ttu-id="bfe3f-111">次のコード例では、 <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType>メソッドを使用して、文字列から XML を使用して<xref:System.Xml.Linq.XDocument>オブジェクトを設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bfe3f-111">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a string.</span></span>

[!code-vb[VbXMLSamples#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#47)]

## <a name="to-load-xml-from-a-stream"></a><span data-ttu-id="bfe3f-112">ストリームから XML を読み込むには</span><span class="sxs-lookup"><span data-stu-id="bfe3f-112">To load XML from a stream</span></span>

<span data-ttu-id="bfe3f-113">ストリームからオブジェクト<xref:System.Xml.Linq.XElement>や<xref:System.Xml.Linq.XDocument>オブジェクトなどの XML リテラルにデータを設定するには、 `Load`メソッドまたは<xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="bfe3f-113">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a stream, you can use the `Load` method or the <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="bfe3f-114">次のコード例では、 <xref:System.Xml.Linq.XNode.ReadFrom%2A>メソッドを使用して、xml ストリームの xml を使用して<xref:System.Xml.Linq.XDocument>オブジェクトを設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bfe3f-114">The following code example shows the use of the <xref:System.Xml.Linq.XNode.ReadFrom%2A> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from an XML stream.</span></span>

[!code-vb[VbXMLSamples#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#46)]

## <a name="see-also"></a><span data-ttu-id="bfe3f-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="bfe3f-115">See also</span></span>

- <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>
- [<span data-ttu-id="bfe3f-116">XML リテラル</span><span class="sxs-lookup"><span data-stu-id="bfe3f-116">XML Literals</span></span>](../../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="bfe3f-117">XML</span><span class="sxs-lookup"><span data-stu-id="bfe3f-117">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="bfe3f-118">Visual Basic での XML の操作</span><span class="sxs-lookup"><span data-stu-id="bfe3f-118">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
