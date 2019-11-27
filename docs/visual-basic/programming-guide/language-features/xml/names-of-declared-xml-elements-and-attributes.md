---
title: 宣言する XML 要素と属性の名前
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [XML in Visual Basic]
- element names [XML in Visual Basic]
- names in XML literals [Visual Basic]
- attribute names [XML in Visual Basic]
- XML literals [Visual Basic], element names
ms.assetid: cc110118-b6cf-4ff9-a4e4-6233c90c9fbf
ms.openlocfilehash: 12fbd1f4332391b1acdcf12e101d82627ebbeaff
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74335996"
---
# <a name="names-of-declared-xml-elements-and-attributes-visual-basic"></a><span data-ttu-id="8350c-102">宣言する XML 要素と属性の名前 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8350c-102">Names of Declared XML Elements and Attributes (Visual Basic)</span></span>
<span data-ttu-id="8350c-103">このトピックでは、xml リテラルの XML 要素と属性に名前を付けるための Visual Basic ガイドラインについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8350c-103">This topic provides Visual Basic guidelines for naming XML elements and attributes in XML literals.</span></span>  <span data-ttu-id="8350c-104">XML リテラルでは、ローカル名または修飾名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="8350c-104">In an XML literal, you can specify a local name or a qualified name.</span></span> <span data-ttu-id="8350c-105">修飾名は、XML 名前空間プレフィックス、コロン、およびローカル名で構成されます。</span><span class="sxs-lookup"><span data-stu-id="8350c-105">A qualified name consists of an XML namespace prefix, a colon, and a local name.</span></span> <span data-ttu-id="8350c-106">XML 名前空間プレフィックスの詳細については、「 [Xml 要素リテラル](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8350c-106">For more information about XML namespace prefixes, see [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="8350c-107">ルール</span><span class="sxs-lookup"><span data-stu-id="8350c-107">Rules</span></span>  
 <span data-ttu-id="8350c-108">Visual Basic 内の要素または属性のローカル名は、次の規則に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="8350c-108">A local name of an element or attribute in Visual Basic must adhere to the following rules.</span></span>  
  
- <span data-ttu-id="8350c-109">名前空間で開始できます。</span><span class="sxs-lookup"><span data-stu-id="8350c-109">It can begin with a namespace.</span></span> <span data-ttu-id="8350c-110">先頭は英文字またはアンダースコア (`_`) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8350c-110">It must begin with an alphabetical character or an underscore (`_`).</span></span>  
  
- <span data-ttu-id="8350c-111">アルファベット文字、10進数字、アンダースコア、ピリオド (.)、ハイフン (-) のみを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="8350c-111">It must contain only alphabetical characters, decimal digits, underscores, periods (.), and hyphens (-).</span></span>  
  
- <span data-ttu-id="8350c-112">長さは1024文字以下でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="8350c-112">It must not be more than 1,024 characters long.</span></span>  
  
- <span data-ttu-id="8350c-113">名前に表示されるコロンは、名前空間の境界を示します。</span><span class="sxs-lookup"><span data-stu-id="8350c-113">Colons that appear in names indicate namespace demarcation.</span></span> <span data-ttu-id="8350c-114">したがって、コロンは、特定の名前の XML 名前空間を指定する場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="8350c-114">Therefore, you can use colons only to specify an XML namespace for a particular name.</span></span>  
  
 <span data-ttu-id="8350c-115">さらに、次のガイドラインに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="8350c-115">In addition, you should adhere to the following guideline.</span></span>  
  
- <span data-ttu-id="8350c-116">XML 1.0 仕様では、文字列 "xml" で始まるすべての名前が、大文字と小文字の違いによって予約されています。</span><span class="sxs-lookup"><span data-stu-id="8350c-116">The XML 1.0 specification reserves all names starting with the string "xml", of any capitalization variation.</span></span> <span data-ttu-id="8350c-117">したがって、要素名と属性名にはこれらの名前を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="8350c-117">Therefore, do not use those names for your element and attribute names.</span></span>  
  
### <a name="name-length-guidelines"></a><span data-ttu-id="8350c-118">名前の長さのガイドライン</span><span class="sxs-lookup"><span data-stu-id="8350c-118">Name Length Guidelines</span></span>  
 <span data-ttu-id="8350c-119">実際には、要素の性質を明確に識別しながら、可能な限り短い名前を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8350c-119">As a practical matter, a name should be as short as possible while still clearly identifying the nature of the element.</span></span> <span data-ttu-id="8350c-120">これにより、コードの読みやすさが向上し、行の長さとソースファイルのサイズが減少します。</span><span class="sxs-lookup"><span data-stu-id="8350c-120">This improves the readability of your code and reduces line length and source-file size.</span></span>  
  
 <span data-ttu-id="8350c-121">ただし、要素が正しく記述されていない場合や、コードで要素が使用されている場合は、名前を短くすることはできません。</span><span class="sxs-lookup"><span data-stu-id="8350c-121">However, your name should not be so short that it does not adequately describe the element or how your code uses it.</span></span> <span data-ttu-id="8350c-122">これは、コードを読みやすくするために重要です。</span><span class="sxs-lookup"><span data-stu-id="8350c-122">This is important for the readability of your code.</span></span> <span data-ttu-id="8350c-123">他のユーザーがそれを理解しようとしている場合、または記述した後に長い時間を見ている場合は、適切な要素名を使用すると時間を節約できます。</span><span class="sxs-lookup"><span data-stu-id="8350c-123">If somebody else is trying to understand it, or if you yourself are looking at it a long time after you wrote it, appropriate element names can save time.</span></span>  
  
## <a name="case-sensitivity-in-names"></a><span data-ttu-id="8350c-124">名前の大文字と小文字の区別</span><span class="sxs-lookup"><span data-stu-id="8350c-124">Case Sensitivity in Names</span></span>  
 <span data-ttu-id="8350c-125">XML 要素名では大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="8350c-125">XML element names are case sensitive.</span></span> <span data-ttu-id="8350c-126">つまり、Visual Basic コンパイラでは、アルファベット順の場合にのみ異なる2つの名前を比較すると、異なる名前として解釈されます。</span><span class="sxs-lookup"><span data-stu-id="8350c-126">This means that when the Visual Basic compiler compares two names that differ in alphabetical case only, it interprets them as different names.</span></span> <span data-ttu-id="8350c-127">たとえば、`ABC` を解釈し、個別の要素を参照するように `abc` します。</span><span class="sxs-lookup"><span data-stu-id="8350c-127">For example, it interprets `ABC` and `abc` as referring to separate elements.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="8350c-128">XML 名前空間</span><span class="sxs-lookup"><span data-stu-id="8350c-128">XML Namespaces</span></span>  
 <span data-ttu-id="8350c-129">XML 要素リテラルを作成するときに、要素名の XML 名前空間プレフィックスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="8350c-129">When creating an XML element literal, you can specify the XML namespace prefix for the element name.</span></span> <span data-ttu-id="8350c-130">詳細については、「 [XML 要素リテラル](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8350c-130">For more information, see [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8350c-131">参照</span><span class="sxs-lookup"><span data-stu-id="8350c-131">See also</span></span>

- [<span data-ttu-id="8350c-132">Visual Basic での XML の作成</span><span class="sxs-lookup"><span data-stu-id="8350c-132">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="8350c-133">XML 要素リテラル</span><span class="sxs-lookup"><span data-stu-id="8350c-133">XML Element Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
