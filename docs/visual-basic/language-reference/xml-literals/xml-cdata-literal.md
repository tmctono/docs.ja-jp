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
ms.openlocfilehash: 889ec7f93d0503edac51652dda217c6a9f654f9b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64621431"
---
# <a name="xml-cdata-literal-visual-basic"></a><span data-ttu-id="9cbaf-102">XML CDATA リテラル (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9cbaf-102">XML CDATA Literal (Visual Basic)</span></span>
<span data-ttu-id="9cbaf-103">リテラルを表す、<xref:System.Xml.Linq.XCData>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="9cbaf-103">A literal representing an <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cbaf-104">構文</span><span class="sxs-lookup"><span data-stu-id="9cbaf-104">Syntax</span></span>  
  
```xml  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a><span data-ttu-id="9cbaf-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="9cbaf-105">Parts</span></span>  
 `<![CDATA[`  
 <span data-ttu-id="9cbaf-106">必須。</span><span class="sxs-lookup"><span data-stu-id="9cbaf-106">Required.</span></span> <span data-ttu-id="9cbaf-107">XML CDATA セクションの開始を示します。</span><span class="sxs-lookup"><span data-stu-id="9cbaf-107">Denotes the start of the XML CDATA section.</span></span>  
  
 `content`  
 <span data-ttu-id="9cbaf-108">必須。</span><span class="sxs-lookup"><span data-stu-id="9cbaf-108">Required.</span></span> <span data-ttu-id="9cbaf-109">XML CDATA セクションに表示するテキスト コンテンツ。</span><span class="sxs-lookup"><span data-stu-id="9cbaf-109">Text content to appear in the XML CDATA section.</span></span>  
  
 `]]>`  
 <span data-ttu-id="9cbaf-110">必須。</span><span class="sxs-lookup"><span data-stu-id="9cbaf-110">Required.</span></span> <span data-ttu-id="9cbaf-111">セクションの終了を示します。</span><span class="sxs-lookup"><span data-stu-id="9cbaf-111">Denotes the end of the section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9cbaf-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="9cbaf-112">Return Value</span></span>  
 <span data-ttu-id="9cbaf-113"><xref:System.Xml.Linq.XCData> オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="9cbaf-113">An <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9cbaf-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="9cbaf-114">Remarks</span></span>  
 <span data-ttu-id="9cbaf-115">XML CDATA セクションを含む未加工のテキストが含まれている場合は、それを含んでいる XML を解析できません。</span><span class="sxs-lookup"><span data-stu-id="9cbaf-115">XML CDATA sections contain raw text that should be included, but not parsed, with the XML that contains it.</span></span> <span data-ttu-id="9cbaf-116">XML CDATA セクションは、任意のテキストを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="9cbaf-116">A XML CDATA section can contain any text.</span></span> <span data-ttu-id="9cbaf-117">これには、予約済み XML 文字が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9cbaf-117">This includes reserved XML characters.</span></span> <span data-ttu-id="9cbaf-118">XML CDATA セクションは、シーケンスで終わる"] >"。</span><span class="sxs-lookup"><span data-stu-id="9cbaf-118">The XML CDATA section ends with the sequence "]]>".</span></span> <span data-ttu-id="9cbaf-119">これは、次の点を意味します。</span><span class="sxs-lookup"><span data-stu-id="9cbaf-119">This implies the following points:</span></span>  
  
- <span data-ttu-id="9cbaf-120">埋め込み式の区切り記号が有効な XML の CDATA コンテンツであるので、XML CDATA リテラルの埋め込み式を使うことはできません。</span><span class="sxs-lookup"><span data-stu-id="9cbaf-120">You cannot use an embedded expression in an XML CDATA literal because the embedded expression delimiters are valid XML CDATA content.</span></span>  
  
- <span data-ttu-id="9cbaf-121">XML CDATA セクションは入れ子にできないため、`content`値を含めることはできません"] >"。</span><span class="sxs-lookup"><span data-stu-id="9cbaf-121">XML CDATA sections cannot be nested, because `content` cannot contain the value "]]>".</span></span>  
  
 <span data-ttu-id="9cbaf-122">XML CDATA リテラルの変数を割り当てたり、XML 要素リテラルに含めることができます。</span><span class="sxs-lookup"><span data-stu-id="9cbaf-122">You can assign an XML CDATA literal to a variable, or include it in an XML element literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9cbaf-123">XML リテラルでは、複数の行にまたがることができますが、行継続文字を使用しません。</span><span class="sxs-lookup"><span data-stu-id="9cbaf-123">An XML literal can span multiple lines but does not use line continuation characters.</span></span> <span data-ttu-id="9cbaf-124">これにより、XML ドキュメントの内容をコピーし、Visual Basic プログラムに直接貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="9cbaf-124">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="9cbaf-125">Visual Basic コンパイラに、XML CDATA リテラルへの呼び出しに変換します、<xref:System.Xml.Linq.XCData.%23ctor%2A>コンス トラクター。</span><span class="sxs-lookup"><span data-stu-id="9cbaf-125">The Visual Basic compiler converts the XML CDATA literal to a call to the <xref:System.Xml.Linq.XCData.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9cbaf-126">例</span><span class="sxs-lookup"><span data-stu-id="9cbaf-126">Example</span></span>  
 <span data-ttu-id="9cbaf-127">次の例では、テキストを含む CDATA セクション"リテラルを含めることができます\<XML > タグ"。</span><span class="sxs-lookup"><span data-stu-id="9cbaf-127">The following example creates a CDATA section that contains the text "Can contain literal \<XML> tags".</span></span>  
  
 [!code-vb[VbXMLSamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="9cbaf-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="9cbaf-128">See also</span></span>

- <xref:System.Xml.Linq.XCData>
- [<span data-ttu-id="9cbaf-129">XML 要素リテラル</span><span class="sxs-lookup"><span data-stu-id="9cbaf-129">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="9cbaf-130">XML リテラル</span><span class="sxs-lookup"><span data-stu-id="9cbaf-130">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="9cbaf-131">Visual Basic での XML の作成</span><span class="sxs-lookup"><span data-stu-id="9cbaf-131">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
