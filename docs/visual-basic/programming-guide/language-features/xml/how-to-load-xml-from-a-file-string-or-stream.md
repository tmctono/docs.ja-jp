---
title: '方法: ファイル、文字列、またはストリームからの XML の読み込み'
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
ms.openlocfilehash: 7a2a0513a066ae8ea8a70f7a5ae340ab29de7d25
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330960"
---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a><span data-ttu-id="dff3a-102">方法: ファイル、文字列、またはストリームから XML を読み込む (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dff3a-102">How to: Load XML from a File, String, or Stream (Visual Basic)</span></span>

<span data-ttu-id="dff3a-103">複数のメソッドを使用して、[XML リテラル](../../../../visual-basic/language-reference/xml-literals/index.md)を作成し、外部ソースからファイル、文字列、ストリームなどの内容を取り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="dff3a-103">You can create [XML Literals](../../../../visual-basic/language-reference/xml-literals/index.md) and populate them with the contents from an external source such as a file, a string, or a stream by using several methods.</span></span> <span data-ttu-id="dff3a-104">以降の例でこれらのメソッドを示します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-104">These methods are shown in the following examples.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-load-xml-from-a-file"></a><span data-ttu-id="dff3a-105">ファイルから XML を読み込むには</span><span class="sxs-lookup"><span data-stu-id="dff3a-105">To load XML from a file</span></span>

<span data-ttu-id="dff3a-106">ファイルから <xref:System.Xml.Linq.XElement> や <xref:System.Xml.Linq.XDocument> オブジェクトなどの XML リテラルを取り込むには、`Load` メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-106">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a file, use the `Load` method.</span></span> <span data-ttu-id="dff3a-107">このメソッドは、入力としてファイル パス、テキスト ストリーム、または XML ストリームを受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="dff3a-107">This method can take a file path, text stream, or XML stream as input.</span></span>

<span data-ttu-id="dff3a-108">次のコード例では、<xref:System.Xml.Linq.XDocument.Load%28System.String%29> メソッドを使用して、<xref:System.Xml.Linq.XDocument> オブジェクトにテキスト ファイルから XML を取り込む方法を示します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-108">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Load%28System.String%29> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a text file.</span></span>

[!code-vb[VbXMLSamples#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#43)]

## <a name="to-load-xml-from-a-string"></a><span data-ttu-id="dff3a-109">文字列から XML を読み込むには</span><span class="sxs-lookup"><span data-stu-id="dff3a-109">To load XML from a string</span></span>

<span data-ttu-id="dff3a-110">文字列から <xref:System.Xml.Linq.XElement> や <xref:System.Xml.Linq.XDocument> オブジェクトなどの XML リテラルを取り込むには、`Parse` メソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="dff3a-110">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a string, you can use the `Parse` method.</span></span>

<span data-ttu-id="dff3a-111">次のコード例では、<xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> メソッドを使用して、<xref:System.Xml.Linq.XDocument> オブジェクトに文字列から XML を取り込む方法を示します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-111">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a string.</span></span>

[!code-vb[VbXMLSamples#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#47)]

## <a name="to-load-xml-from-a-stream"></a><span data-ttu-id="dff3a-112">ストリームから XML を読み込むには</span><span class="sxs-lookup"><span data-stu-id="dff3a-112">To load XML from a stream</span></span>

<span data-ttu-id="dff3a-113">ストリームから <xref:System.Xml.Linq.XElement> や <xref:System.Xml.Linq.XDocument> オブジェクトなどの XML リテラルを取り込むには、`Load` メソッドまたは <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> メソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="dff3a-113">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a stream, you can use the `Load` method or the <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="dff3a-114">次のコード例では、<xref:System.Xml.Linq.XNode.ReadFrom%2A> メソッドを使用して、<xref:System.Xml.Linq.XDocument> オブジェクトに XML ストリームから XML を取り込む方法を示します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-114">The following code example shows the use of the <xref:System.Xml.Linq.XNode.ReadFrom%2A> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from an XML stream.</span></span>

[!code-vb[VbXMLSamples#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#46)]

## <a name="see-also"></a><span data-ttu-id="dff3a-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="dff3a-115">See also</span></span>

- <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>
- [<span data-ttu-id="dff3a-116">XML リテラル</span><span class="sxs-lookup"><span data-stu-id="dff3a-116">XML Literals</span></span>](../../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="dff3a-117">XML</span><span class="sxs-lookup"><span data-stu-id="dff3a-117">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="dff3a-118">Visual Basic での XML の操作</span><span class="sxs-lookup"><span data-stu-id="dff3a-118">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
