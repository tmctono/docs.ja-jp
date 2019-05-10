---
title: '方法: ファイル、文字列、または Stream (Visual Basic) から XML を読み込む'
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
ms.openlocfilehash: 097c766fc9efbc810859ab693d3b26f5c1db57ec
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64598332"
---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a><span data-ttu-id="bdc6b-102">方法: ファイル、文字列、または Stream (Visual Basic) から XML を読み込む</span><span class="sxs-lookup"><span data-stu-id="bdc6b-102">How to: Load XML from a File, String, or Stream (Visual Basic)</span></span>
<span data-ttu-id="bdc6b-103">作成することができます[XML リテラル](../../../../visual-basic/language-reference/xml-literals/index.md)しをいくつかのメソッドを使用して、ファイル、文字列またはストリームなどの外部ソースからコンテンツを設定します。</span><span class="sxs-lookup"><span data-stu-id="bdc6b-103">You can create [XML Literals](../../../../visual-basic/language-reference/xml-literals/index.md) and populate them with the contents from an external source such as a file, a string, or a stream by using several methods.</span></span> <span data-ttu-id="bdc6b-104">次の例では、これらのメソッドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bdc6b-104">These methods are shown in the following examples.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-load-xml-from-a-file"></a><span data-ttu-id="bdc6b-105">ファイルから XML を読み込めません</span><span class="sxs-lookup"><span data-stu-id="bdc6b-105">To load XML from a file</span></span>  
  
- <span data-ttu-id="bdc6b-106">XML リテラルなどを設定する、<xref:System.Xml.Linq.XElement>または<xref:System.Xml.Linq.XDocument>オブジェクトを使用して、ファイルから、`Load`メソッド。</span><span class="sxs-lookup"><span data-stu-id="bdc6b-106">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a file, use the `Load` method.</span></span> <span data-ttu-id="bdc6b-107">このメソッドは、入力としてファイル パス、テキストのストリームまたは XML ストリームを受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="bdc6b-107">This method can take a file path, text stream, or XML stream as input.</span></span>  
  
     <span data-ttu-id="bdc6b-108">次のコード例の使用を示しています、<xref:System.Xml.Linq.XDocument.Load%28System.String%29>メソッドを<xref:System.Xml.Linq.XDocument>テキスト ファイルから XML を持つオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="bdc6b-108">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Load%28System.String%29> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a text file.</span></span>  
  
     [!code-vb[VbXMLSamples#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#43)]  
  
### <a name="to-load-xml-from-a-string"></a><span data-ttu-id="bdc6b-109">文字列から XML を読み込めません</span><span class="sxs-lookup"><span data-stu-id="bdc6b-109">To load XML from a string</span></span>  
  
- <span data-ttu-id="bdc6b-110">XML リテラルなどを設定する、<xref:System.Xml.Linq.XElement>または<xref:System.Xml.Linq.XDocument>オブジェクト、文字列から使用することができます、`Parse`メソッド。</span><span class="sxs-lookup"><span data-stu-id="bdc6b-110">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a string, you can use the `Parse` method.</span></span>  
  
     <span data-ttu-id="bdc6b-111">次のコード例の使用を示しています、<xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType>メソッドを<xref:System.Xml.Linq.XDocument>xml 文字列からのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="bdc6b-111">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a string.</span></span>  
  
     [!code-vb[VbXMLSamples#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#47)]  
  
### <a name="to-load-xml-from-a-stream"></a><span data-ttu-id="bdc6b-112">ストリームから XML を読み込めません</span><span class="sxs-lookup"><span data-stu-id="bdc6b-112">To load XML from a stream</span></span>  
  
- <span data-ttu-id="bdc6b-113">XML リテラルなどを設定する、<xref:System.Xml.Linq.XElement>または<xref:System.Xml.Linq.XDocument>オブジェクト、ストリームから使用することができます、`Load`メソッドまたは<xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>メソッド。</span><span class="sxs-lookup"><span data-stu-id="bdc6b-113">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a stream, you can use the `Load` method or the <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="bdc6b-114">次のコード例の使用を示しています、<xref:System.Xml.Linq.XNode.ReadFrom%2A>メソッドを<xref:System.Xml.Linq.XDocument>XML ストリームから XML を持つオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="bdc6b-114">The following code example shows the use of the <xref:System.Xml.Linq.XNode.ReadFrom%2A> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from an XML stream.</span></span>  
  
 [!code-vb[VbXMLSamples#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#46)]  
  
## <a name="see-also"></a><span data-ttu-id="bdc6b-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="bdc6b-115">See also</span></span>

- <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>
- [<span data-ttu-id="bdc6b-116">XML リテラル</span><span class="sxs-lookup"><span data-stu-id="bdc6b-116">XML Literals</span></span>](../../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="bdc6b-117">XML</span><span class="sxs-lookup"><span data-stu-id="bdc6b-117">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="bdc6b-118">Visual Basic での XML の操作</span><span class="sxs-lookup"><span data-stu-id="bdc6b-118">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
