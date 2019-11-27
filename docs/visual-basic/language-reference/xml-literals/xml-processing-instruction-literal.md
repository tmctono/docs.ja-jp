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
ms.openlocfilehash: 3602a81feae9287a77d060bb46f10eefee4fc05d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347046"
---
# <a name="xml-processing-instruction-literal-visual-basic"></a><span data-ttu-id="53c2c-102">XML 処理命令リテラル (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="53c2c-102">XML Processing Instruction Literal (Visual Basic)</span></span>
<span data-ttu-id="53c2c-103"><xref:System.Xml.Linq.XProcessingInstruction> オブジェクトを表すリテラル。</span><span class="sxs-lookup"><span data-stu-id="53c2c-103">A literal representing an <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53c2c-104">構文</span><span class="sxs-lookup"><span data-stu-id="53c2c-104">Syntax</span></span>  
  
```xml  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a><span data-ttu-id="53c2c-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="53c2c-105">Parts</span></span>  
 `<?`  
 <span data-ttu-id="53c2c-106">必須。</span><span class="sxs-lookup"><span data-stu-id="53c2c-106">Required.</span></span> <span data-ttu-id="53c2c-107">XML 処理命令リテラルの開始を示します。</span><span class="sxs-lookup"><span data-stu-id="53c2c-107">Denotes the start of the XML processing instruction literal.</span></span>  
  
 `piName`  
 <span data-ttu-id="53c2c-108">必須。</span><span class="sxs-lookup"><span data-stu-id="53c2c-108">Required.</span></span> <span data-ttu-id="53c2c-109">処理命令が対象とするアプリケーションを示す名前。</span><span class="sxs-lookup"><span data-stu-id="53c2c-109">Name indicating which application the processing instruction targets.</span></span> <span data-ttu-id="53c2c-110">"Xml" または "XML" で始めることはできません。</span><span class="sxs-lookup"><span data-stu-id="53c2c-110">Cannot begin with "xml" or "XML".</span></span>  
  
 `piData`  
 <span data-ttu-id="53c2c-111">省略可。</span><span class="sxs-lookup"><span data-stu-id="53c2c-111">Optional.</span></span> <span data-ttu-id="53c2c-112">`piName` が対象とするアプリケーションで XML ドキュメントを処理する方法を示す文字列。</span><span class="sxs-lookup"><span data-stu-id="53c2c-112">String indicating how the application targeted by `piName` should process the XML document.</span></span>  
  
 `?>`  
 <span data-ttu-id="53c2c-113">必須。</span><span class="sxs-lookup"><span data-stu-id="53c2c-113">Required.</span></span> <span data-ttu-id="53c2c-114">処理命令の終了を示します。</span><span class="sxs-lookup"><span data-stu-id="53c2c-114">Denotes the end of the processing instruction.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="53c2c-115">戻り値</span><span class="sxs-lookup"><span data-stu-id="53c2c-115">Return Value</span></span>  
 <span data-ttu-id="53c2c-116"><xref:System.Xml.Linq.XProcessingInstruction> オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="53c2c-116">An <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="53c2c-117">コメント</span><span class="sxs-lookup"><span data-stu-id="53c2c-117">Remarks</span></span>  
 <span data-ttu-id="53c2c-118">XML 処理命令リテラルは、アプリケーションで XML ドキュメントを処理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="53c2c-118">XML processing instruction literals indicate how applications should process an XML document.</span></span> <span data-ttu-id="53c2c-119">アプリケーションで XML ドキュメントが読み込まれると、アプリケーションは XML 処理命令を確認して、ドキュメントの処理方法を決定できます。</span><span class="sxs-lookup"><span data-stu-id="53c2c-119">When an application loads an XML document, the application can check the XML processing instructions to determine how to process the document.</span></span> <span data-ttu-id="53c2c-120">アプリケーションは、`piName` と `piData`の意味を解釈します。</span><span class="sxs-lookup"><span data-stu-id="53c2c-120">The application interprets the meaning of `piName` and `piData`.</span></span>  
  
 <span data-ttu-id="53c2c-121">XML ドキュメントリテラルでは、XML 処理命令と同様の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="53c2c-121">The XML document literal uses syntax that is similar to that of the XML processing instruction.</span></span> <span data-ttu-id="53c2c-122">詳細については、「 [XML ドキュメントリテラル](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53c2c-122">For more information, see [XML Document Literal](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="53c2c-123">XML 1.0 仕様ではこれらの識別子が予約されているため、`piName` 要素を文字列 "xml" または "XML" で始めることはできません。</span><span class="sxs-lookup"><span data-stu-id="53c2c-123">The `piName` element cannot begin with the strings "xml" or "XML", because the XML 1.0 specification reserves those identifiers.</span></span>  
  
 <span data-ttu-id="53c2c-124">XML 処理命令リテラルを変数に割り当てるか、XML ドキュメントリテラルに含めることができます。</span><span class="sxs-lookup"><span data-stu-id="53c2c-124">You can assign an XML processing instruction literal to a variable or include it in an XML document literal.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="53c2c-125">XML リテラルは、行連結文字を必要とせずに、複数の行にまたがることができます。</span><span class="sxs-lookup"><span data-stu-id="53c2c-125">An XML literal can span multiple lines without needing line continuation characters.</span></span> <span data-ttu-id="53c2c-126">これにより、XML ドキュメントからコンテンツをコピーし、Visual Basic プログラムに直接貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="53c2c-126">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="53c2c-127">Visual Basic コンパイラは、XML 処理命令のリテラルを <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> コンストラクターへの呼び出しに変換します。</span><span class="sxs-lookup"><span data-stu-id="53c2c-127">The Visual Basic compiler converts the XML processing instruction literal to a call to the <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="53c2c-128">例</span><span class="sxs-lookup"><span data-stu-id="53c2c-128">Example</span></span>  
 <span data-ttu-id="53c2c-129">次の例では、XML ドキュメントのスタイルシートを識別する処理命令を作成します。</span><span class="sxs-lookup"><span data-stu-id="53c2c-129">The following example creates a processing instruction identifying a style-sheet for an XML document.</span></span>  
  
 [!code-vb[VbXMLSamples#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="53c2c-130">参照</span><span class="sxs-lookup"><span data-stu-id="53c2c-130">See also</span></span>

- <xref:System.Xml.Linq.XProcessingInstruction>
- [<span data-ttu-id="53c2c-131">XML ドキュメント リテラル</span><span class="sxs-lookup"><span data-stu-id="53c2c-131">XML Document Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [<span data-ttu-id="53c2c-132">XML リテラル</span><span class="sxs-lookup"><span data-stu-id="53c2c-132">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="53c2c-133">Visual Basic での XML の作成</span><span class="sxs-lookup"><span data-stu-id="53c2c-133">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
