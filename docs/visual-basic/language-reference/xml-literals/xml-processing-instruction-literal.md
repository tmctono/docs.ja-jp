---
title: XML 処理命令リテラル
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralProcessingInstruction
helpviewer_keywords:
- XML literals [Visual Basic], processing instruction
- XML processing instruction literal [Visual Basic]
- processing instruction literal [Visual Basic]
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
ms.openlocfilehash: 9bd1781e01bc4cbf1ce5da8c454ab2f5a679aead
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400177"
---
# <a name="xml-processing-instruction-literal-visual-basic"></a><span data-ttu-id="47459-102">XML 処理命令リテラル (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="47459-102">XML Processing Instruction Literal (Visual Basic)</span></span>
<span data-ttu-id="47459-103"><xref:System.Xml.Linq.XProcessingInstruction> オブジェクトを表すリテラル。</span><span class="sxs-lookup"><span data-stu-id="47459-103">A literal representing an <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47459-104">構文</span><span class="sxs-lookup"><span data-stu-id="47459-104">Syntax</span></span>  
  
```xml  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a><span data-ttu-id="47459-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="47459-105">Parts</span></span>  
 `<?`  
 <span data-ttu-id="47459-106">必須です。</span><span class="sxs-lookup"><span data-stu-id="47459-106">Required.</span></span> <span data-ttu-id="47459-107">XML 処理命令リテラルの先頭を表します。</span><span class="sxs-lookup"><span data-stu-id="47459-107">Denotes the start of the XML processing instruction literal.</span></span>  
  
 `piName`  
 <span data-ttu-id="47459-108">必須です。</span><span class="sxs-lookup"><span data-stu-id="47459-108">Required.</span></span> <span data-ttu-id="47459-109">処理命令の対象となるアプリケーションを示す名前。</span><span class="sxs-lookup"><span data-stu-id="47459-109">Name indicating which application the processing instruction targets.</span></span> <span data-ttu-id="47459-110">"xml" または "XML" では開始できません。</span><span class="sxs-lookup"><span data-stu-id="47459-110">Cannot begin with "xml" or "XML".</span></span>  
  
 `piData`  
 <span data-ttu-id="47459-111">任意。</span><span class="sxs-lookup"><span data-stu-id="47459-111">Optional.</span></span> <span data-ttu-id="47459-112">`piName` の対象となるアプリケーションが XML ドキュメントを処理する方法を示す文字列。</span><span class="sxs-lookup"><span data-stu-id="47459-112">String indicating how the application targeted by `piName` should process the XML document.</span></span>  
  
 `?>`  
 <span data-ttu-id="47459-113">必須です。</span><span class="sxs-lookup"><span data-stu-id="47459-113">Required.</span></span> <span data-ttu-id="47459-114">処理命令の末尾を表します。</span><span class="sxs-lookup"><span data-stu-id="47459-114">Denotes the end of the processing instruction.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="47459-115">戻り値</span><span class="sxs-lookup"><span data-stu-id="47459-115">Return Value</span></span>  
 <span data-ttu-id="47459-116"><xref:System.Xml.Linq.XProcessingInstruction> オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="47459-116">An <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47459-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="47459-117">Remarks</span></span>  
 <span data-ttu-id="47459-118">XML 処理命令リテラルは、アプリケーションが XML ドキュメントを処理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="47459-118">XML processing instruction literals indicate how applications should process an XML document.</span></span> <span data-ttu-id="47459-119">アプリケーションは XML ドキュメントを読み込むとき、XML 処理命令を確認して、そのドキュメントの処理方法を判断します。</span><span class="sxs-lookup"><span data-stu-id="47459-119">When an application loads an XML document, the application can check the XML processing instructions to determine how to process the document.</span></span> <span data-ttu-id="47459-120">アプリケーションによって解釈されるのは、`piName` と `piData` の意味です。</span><span class="sxs-lookup"><span data-stu-id="47459-120">The application interprets the meaning of `piName` and `piData`.</span></span>  
  
 <span data-ttu-id="47459-121">XML ドキュメント リテラルでは、XML 処理命令と似た構文が使用されます。</span><span class="sxs-lookup"><span data-stu-id="47459-121">The XML document literal uses syntax that is similar to that of the XML processing instruction.</span></span> <span data-ttu-id="47459-122">詳細については、「[XML ドキュメント リテラル](xml-document-literal.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47459-122">For more information, see [XML Document Literal](xml-document-literal.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="47459-123">`piName` 要素の先頭に "xml" または "XML" 文字列を使用することはできません。これらの識別子は、XML 1.0 仕様で予約されているためです。</span><span class="sxs-lookup"><span data-stu-id="47459-123">The `piName` element cannot begin with the strings "xml" or "XML", because the XML 1.0 specification reserves those identifiers.</span></span>  
  
 <span data-ttu-id="47459-124">XML 処理命令リテラルは、変数に代入するか、XML ドキュメント リテラルに含めることができます。</span><span class="sxs-lookup"><span data-stu-id="47459-124">You can assign an XML processing instruction literal to a variable or include it in an XML document literal.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="47459-125">XML リテラルは、行連結文字なしで複数行にまたがることができます。</span><span class="sxs-lookup"><span data-stu-id="47459-125">An XML literal can span multiple lines without needing line continuation characters.</span></span> <span data-ttu-id="47459-126">これにより、XML ドキュメントからコンテンツをコピーして、Visual Basic プログラムに直接貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="47459-126">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="47459-127">XML 処理命令リテラルは、Visual Basic コンパイラによって、<xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> コンストラクターへの呼び出しに変換されます。</span><span class="sxs-lookup"><span data-stu-id="47459-127">The Visual Basic compiler converts the XML processing instruction literal to a call to the <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47459-128">例</span><span class="sxs-lookup"><span data-stu-id="47459-128">Example</span></span>  
 <span data-ttu-id="47459-129">次の例では、XML ドキュメントのスタイルシートを特定する処理命令を作成します。</span><span class="sxs-lookup"><span data-stu-id="47459-129">The following example creates a processing instruction identifying a style-sheet for an XML document.</span></span>  
  
 [!code-vb[VbXMLSamples#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="47459-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="47459-130">See also</span></span>

- <xref:System.Xml.Linq.XProcessingInstruction>
- [<span data-ttu-id="47459-131">XML ドキュメント リテラル</span><span class="sxs-lookup"><span data-stu-id="47459-131">XML Document Literal</span></span>](xml-document-literal.md)
- [<span data-ttu-id="47459-132">XML リテラル</span><span class="sxs-lookup"><span data-stu-id="47459-132">XML Literals</span></span>](index.md)
- [<span data-ttu-id="47459-133">Visual Basic での XML の作成</span><span class="sxs-lookup"><span data-stu-id="47459-133">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
