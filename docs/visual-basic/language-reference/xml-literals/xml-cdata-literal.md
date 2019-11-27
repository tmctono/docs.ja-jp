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
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349432"
---
# <a name="xml-cdata-literal-visual-basic"></a><span data-ttu-id="5d932-102">XML CDATA リテラル (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d932-102">XML CDATA Literal (Visual Basic)</span></span>
<span data-ttu-id="5d932-103"><xref:System.Xml.Linq.XCData> オブジェクトを表すリテラル。</span><span class="sxs-lookup"><span data-stu-id="5d932-103">A literal representing an <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d932-104">構文</span><span class="sxs-lookup"><span data-stu-id="5d932-104">Syntax</span></span>  
  
```xml  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a><span data-ttu-id="5d932-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="5d932-105">Parts</span></span>  
 `<![CDATA[`  
 <span data-ttu-id="5d932-106">必須。</span><span class="sxs-lookup"><span data-stu-id="5d932-106">Required.</span></span> <span data-ttu-id="5d932-107">XML CDATA セクションの先頭を示します。</span><span class="sxs-lookup"><span data-stu-id="5d932-107">Denotes the start of the XML CDATA section.</span></span>  
  
 `content`  
 <span data-ttu-id="5d932-108">必須。</span><span class="sxs-lookup"><span data-stu-id="5d932-108">Required.</span></span> <span data-ttu-id="5d932-109">XML CDATA セクションに表示されるテキストコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="5d932-109">Text content to appear in the XML CDATA section.</span></span>  
  
 `]]>`  
 <span data-ttu-id="5d932-110">必須。</span><span class="sxs-lookup"><span data-stu-id="5d932-110">Required.</span></span> <span data-ttu-id="5d932-111">セクションの末尾を示します。</span><span class="sxs-lookup"><span data-stu-id="5d932-111">Denotes the end of the section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5d932-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="5d932-112">Return Value</span></span>  
 <span data-ttu-id="5d932-113"><xref:System.Xml.Linq.XCData> オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="5d932-113">An <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d932-114">コメント</span><span class="sxs-lookup"><span data-stu-id="5d932-114">Remarks</span></span>  
 <span data-ttu-id="5d932-115">XML CDATA セクションには未加工のテキストが含まれていますが、それを含む XML では解析できません。</span><span class="sxs-lookup"><span data-stu-id="5d932-115">XML CDATA sections contain raw text that should be included, but not parsed, with the XML that contains it.</span></span> <span data-ttu-id="5d932-116">XML CDATA セクションには、任意のテキストを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="5d932-116">A XML CDATA section can contain any text.</span></span> <span data-ttu-id="5d932-117">これには、予約済みの XML 文字が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5d932-117">This includes reserved XML characters.</span></span> <span data-ttu-id="5d932-118">XML CDATA セクションは、シーケンス "]" > "で終了します。</span><span class="sxs-lookup"><span data-stu-id="5d932-118">The XML CDATA section ends with the sequence "]]>".</span></span> <span data-ttu-id="5d932-119">これは、次の点を意味します。</span><span class="sxs-lookup"><span data-stu-id="5d932-119">This implies the following points:</span></span>  
  
- <span data-ttu-id="5d932-120">埋め込み式の区切り記号が有効な XML CDATA コンテンツであるため、XML CDATA リテラルで埋め込み式を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="5d932-120">You cannot use an embedded expression in an XML CDATA literal because the embedded expression delimiters are valid XML CDATA content.</span></span>  
  
- <span data-ttu-id="5d932-121">XML CDATA セクションを入れ子にすることはできません。 `content` に値 "]] >" を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="5d932-121">XML CDATA sections cannot be nested, because `content` cannot contain the value "]]>".</span></span>  
  
 <span data-ttu-id="5d932-122">XML CDATA リテラルを変数に割り当てるか、XML 要素リテラルに含めることができます。</span><span class="sxs-lookup"><span data-stu-id="5d932-122">You can assign an XML CDATA literal to a variable, or include it in an XML element literal.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5d932-123">XML リテラルは複数の行にまたがることができますが、行連結文字は使用しません。</span><span class="sxs-lookup"><span data-stu-id="5d932-123">An XML literal can span multiple lines but does not use line continuation characters.</span></span> <span data-ttu-id="5d932-124">これにより、XML ドキュメントからコンテンツをコピーし、Visual Basic プログラムに直接貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="5d932-124">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="5d932-125">Visual Basic コンパイラは、XML CDATA リテラルを <xref:System.Xml.Linq.XCData.%23ctor%2A> コンストラクターへの呼び出しに変換します。</span><span class="sxs-lookup"><span data-stu-id="5d932-125">The Visual Basic compiler converts the XML CDATA literal to a call to the <xref:System.Xml.Linq.XCData.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d932-126">例</span><span class="sxs-lookup"><span data-stu-id="5d932-126">Example</span></span>  
 <span data-ttu-id="5d932-127">次の例では、"リテラル \<XML > タグを含めることができる" というテキストを含む CDATA セクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="5d932-127">The following example creates a CDATA section that contains the text "Can contain literal \<XML> tags".</span></span>  
  
 [!code-vb[VbXMLSamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="5d932-128">参照</span><span class="sxs-lookup"><span data-stu-id="5d932-128">See also</span></span>

- <xref:System.Xml.Linq.XCData>
- [<span data-ttu-id="5d932-129">XML 要素リテラル</span><span class="sxs-lookup"><span data-stu-id="5d932-129">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="5d932-130">XML リテラル</span><span class="sxs-lookup"><span data-stu-id="5d932-130">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="5d932-131">Visual Basic での XML の作成</span><span class="sxs-lookup"><span data-stu-id="5d932-131">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
