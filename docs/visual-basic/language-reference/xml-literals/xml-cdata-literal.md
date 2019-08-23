---
title: XML CDATA リテラル (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralCdata
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
ms.openlocfilehash: 248f3cf31f686de3af2ea06012aa4a6d4f3f29fc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942916"
---
# <a name="xml-cdata-literal-visual-basic"></a><span data-ttu-id="7a8a0-102">XML CDATA リテラル (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7a8a0-102">XML CDATA Literal (Visual Basic)</span></span>
<span data-ttu-id="7a8a0-103"><xref:System.Xml.Linq.XCData>オブジェクトを表すリテラル。</span><span class="sxs-lookup"><span data-stu-id="7a8a0-103">A literal representing an <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a8a0-104">構文</span><span class="sxs-lookup"><span data-stu-id="7a8a0-104">Syntax</span></span>  
  
```xml  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a><span data-ttu-id="7a8a0-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="7a8a0-105">Parts</span></span>  
 `<![CDATA[`  
 <span data-ttu-id="7a8a0-106">必須。</span><span class="sxs-lookup"><span data-stu-id="7a8a0-106">Required.</span></span> <span data-ttu-id="7a8a0-107">XML CDATA セクションの先頭を示します。</span><span class="sxs-lookup"><span data-stu-id="7a8a0-107">Denotes the start of the XML CDATA section.</span></span>  
  
 `content`  
 <span data-ttu-id="7a8a0-108">必須。</span><span class="sxs-lookup"><span data-stu-id="7a8a0-108">Required.</span></span> <span data-ttu-id="7a8a0-109">XML CDATA セクションに表示されるテキストコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="7a8a0-109">Text content to appear in the XML CDATA section.</span></span>  
  
 `]]>`  
 <span data-ttu-id="7a8a0-110">必須。</span><span class="sxs-lookup"><span data-stu-id="7a8a0-110">Required.</span></span> <span data-ttu-id="7a8a0-111">セクションの末尾を示します。</span><span class="sxs-lookup"><span data-stu-id="7a8a0-111">Denotes the end of the section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7a8a0-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="7a8a0-112">Return Value</span></span>  
 <span data-ttu-id="7a8a0-113"><xref:System.Xml.Linq.XCData> オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="7a8a0-113">An <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7a8a0-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="7a8a0-114">Remarks</span></span>  
 <span data-ttu-id="7a8a0-115">XML CDATA セクションには未加工のテキストが含まれていますが、それを含む XML では解析できません。</span><span class="sxs-lookup"><span data-stu-id="7a8a0-115">XML CDATA sections contain raw text that should be included, but not parsed, with the XML that contains it.</span></span> <span data-ttu-id="7a8a0-116">XML CDATA セクションには、任意のテキストを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="7a8a0-116">A XML CDATA section can contain any text.</span></span> <span data-ttu-id="7a8a0-117">これには、予約済みの XML 文字が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7a8a0-117">This includes reserved XML characters.</span></span> <span data-ttu-id="7a8a0-118">XML CDATA セクションは、シーケンス "]" > "で終了します。</span><span class="sxs-lookup"><span data-stu-id="7a8a0-118">The XML CDATA section ends with the sequence "]]>".</span></span> <span data-ttu-id="7a8a0-119">これは、次の点を意味します。</span><span class="sxs-lookup"><span data-stu-id="7a8a0-119">This implies the following points:</span></span>  
  
- <span data-ttu-id="7a8a0-120">埋め込み式の区切り記号が有効な XML CDATA コンテンツであるため、XML CDATA リテラルで埋め込み式を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="7a8a0-120">You cannot use an embedded expression in an XML CDATA literal because the embedded expression delimiters are valid XML CDATA content.</span></span>  
  
- <span data-ttu-id="7a8a0-121">XML CDATA セクションを入れ子に`content`することはできません。には値 "]] >" を含めることができません。</span><span class="sxs-lookup"><span data-stu-id="7a8a0-121">XML CDATA sections cannot be nested, because `content` cannot contain the value "]]>".</span></span>  
  
 <span data-ttu-id="7a8a0-122">XML CDATA リテラルを変数に割り当てるか、XML 要素リテラルに含めることができます。</span><span class="sxs-lookup"><span data-stu-id="7a8a0-122">You can assign an XML CDATA literal to a variable, or include it in an XML element literal.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7a8a0-123">XML リテラルは複数の行にまたがることができますが、行連結文字は使用しません。</span><span class="sxs-lookup"><span data-stu-id="7a8a0-123">An XML literal can span multiple lines but does not use line continuation characters.</span></span> <span data-ttu-id="7a8a0-124">これにより、XML ドキュメントからコンテンツをコピーし、Visual Basic プログラムに直接貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="7a8a0-124">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="7a8a0-125">Visual Basic コンパイラは、XML CDATA リテラルをコンストラクターの<xref:System.Xml.Linq.XCData.%23ctor%2A>呼び出しに変換します。</span><span class="sxs-lookup"><span data-stu-id="7a8a0-125">The Visual Basic compiler converts the XML CDATA literal to a call to the <xref:System.Xml.Linq.XCData.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a8a0-126">例</span><span class="sxs-lookup"><span data-stu-id="7a8a0-126">Example</span></span>  
 <span data-ttu-id="7a8a0-127">次の例では、"リテラル\<XML > タグを含めることができます" というテキストを含む CDATA セクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="7a8a0-127">The following example creates a CDATA section that contains the text "Can contain literal \<XML> tags".</span></span>  
  
 [!code-vb[VbXMLSamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="7a8a0-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="7a8a0-128">See also</span></span>

- <xref:System.Xml.Linq.XCData>
- [<span data-ttu-id="7a8a0-129">XML 要素リテラル</span><span class="sxs-lookup"><span data-stu-id="7a8a0-129">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="7a8a0-130">XML リテラル</span><span class="sxs-lookup"><span data-stu-id="7a8a0-130">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="7a8a0-131">Visual Basic での XML の作成</span><span class="sxs-lookup"><span data-stu-id="7a8a0-131">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
