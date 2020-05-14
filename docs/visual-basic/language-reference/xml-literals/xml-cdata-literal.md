---
title: XML CDATA リテラル
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralCdata
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
ms.openlocfilehash: 72e899e7bd30f2edf0e88207bb3b75bdf36fa11c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349432"
---
# <a name="xml-cdata-literal-visual-basic"></a><span data-ttu-id="e37cf-102">XML CDATA リテラル (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e37cf-102">XML CDATA Literal (Visual Basic)</span></span>
<span data-ttu-id="e37cf-103"><xref:System.Xml.Linq.XCData> オブジェクトを表すリテラル。</span><span class="sxs-lookup"><span data-stu-id="e37cf-103">A literal representing an <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e37cf-104">構文</span><span class="sxs-lookup"><span data-stu-id="e37cf-104">Syntax</span></span>  
  
```xml  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a><span data-ttu-id="e37cf-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="e37cf-105">Parts</span></span>  
 `<![CDATA[`  
 <span data-ttu-id="e37cf-106">必須です。</span><span class="sxs-lookup"><span data-stu-id="e37cf-106">Required.</span></span> <span data-ttu-id="e37cf-107">XML CDATA セクションの先頭を表します。</span><span class="sxs-lookup"><span data-stu-id="e37cf-107">Denotes the start of the XML CDATA section.</span></span>  
  
 `content`  
 <span data-ttu-id="e37cf-108">必須です。</span><span class="sxs-lookup"><span data-stu-id="e37cf-108">Required.</span></span> <span data-ttu-id="e37cf-109">XML CDATA セクションに表示されるテキスト コンテンツ。</span><span class="sxs-lookup"><span data-stu-id="e37cf-109">Text content to appear in the XML CDATA section.</span></span>  
  
 `]]>`  
 <span data-ttu-id="e37cf-110">必須です。</span><span class="sxs-lookup"><span data-stu-id="e37cf-110">Required.</span></span> <span data-ttu-id="e37cf-111">セクションの末尾を表します。</span><span class="sxs-lookup"><span data-stu-id="e37cf-111">Denotes the end of the section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e37cf-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="e37cf-112">Return Value</span></span>  
 <span data-ttu-id="e37cf-113"><xref:System.Xml.Linq.XCData> オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="e37cf-113">An <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e37cf-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="e37cf-114">Remarks</span></span>  
 <span data-ttu-id="e37cf-115">XML CDATA セクションには、未加工のテキストが含まれています。この未加工のテキストは XML に含める必要がありますが、そのテキストを含む XML で解析する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e37cf-115">XML CDATA sections contain raw text that should be included, but not parsed, with the XML that contains it.</span></span> <span data-ttu-id="e37cf-116">XML CDATA セクションには、任意のテキストを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e37cf-116">A XML CDATA section can contain any text.</span></span> <span data-ttu-id="e37cf-117">予約済み XML 文字も含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e37cf-117">This includes reserved XML characters.</span></span> <span data-ttu-id="e37cf-118">XML CDATA セクションの末尾には "]]>" シーケンスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="e37cf-118">The XML CDATA section ends with the sequence "]]>".</span></span> <span data-ttu-id="e37cf-119">これは以下を意味します。</span><span class="sxs-lookup"><span data-stu-id="e37cf-119">This implies the following points:</span></span>  
  
- <span data-ttu-id="e37cf-120">埋め込み式の区切り記号は有効な XML CDATA コンテンツであるため、XML CDATA リテラルでは埋め込み式を使用できません。</span><span class="sxs-lookup"><span data-stu-id="e37cf-120">You cannot use an embedded expression in an XML CDATA literal because the embedded expression delimiters are valid XML CDATA content.</span></span>  
  
- <span data-ttu-id="e37cf-121">`content` には値 "]]>" を含めることができないため、XML CDATA セクションを入れ子にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="e37cf-121">XML CDATA sections cannot be nested, because `content` cannot contain the value "]]>".</span></span>  
  
 <span data-ttu-id="e37cf-122">XML CDATA リテラルは、変数に代入するか、XML 要素リテラルに含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e37cf-122">You can assign an XML CDATA literal to a variable, or include it in an XML element literal.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e37cf-123">XML リテラルは複数行にまたがることができますが、行連結文字は使用されません。</span><span class="sxs-lookup"><span data-stu-id="e37cf-123">An XML literal can span multiple lines but does not use line continuation characters.</span></span> <span data-ttu-id="e37cf-124">これにより、XML ドキュメントからコンテンツをコピーして、Visual Basic プログラムに直接貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="e37cf-124">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="e37cf-125">XML CDATA リテラルは、Visual Basic コンパイラによって、<xref:System.Xml.Linq.XCData.%23ctor%2A> コンストラクターへの呼び出しに変換されます。</span><span class="sxs-lookup"><span data-stu-id="e37cf-125">The Visual Basic compiler converts the XML CDATA literal to a call to the <xref:System.Xml.Linq.XCData.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e37cf-126">例</span><span class="sxs-lookup"><span data-stu-id="e37cf-126">Example</span></span>  
 <span data-ttu-id="e37cf-127">次の例では、"Can contain literal \<XML> tags" というテキストを含む CDATA セクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="e37cf-127">The following example creates a CDATA section that contains the text "Can contain literal \<XML> tags".</span></span>  
  
 [!code-vb[VbXMLSamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="e37cf-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="e37cf-128">See also</span></span>

- <xref:System.Xml.Linq.XCData>
- [<span data-ttu-id="e37cf-129">XML 要素リテラル</span><span class="sxs-lookup"><span data-stu-id="e37cf-129">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="e37cf-130">XML リテラル</span><span class="sxs-lookup"><span data-stu-id="e37cf-130">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="e37cf-131">Visual Basic での XML の作成</span><span class="sxs-lookup"><span data-stu-id="e37cf-131">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
