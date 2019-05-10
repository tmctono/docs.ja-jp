---
title: 宣言する XML 要素と属性の名前 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [XML in Visual Basic]
- element names [XML in Visual Basic]
- names in XML literals [Visual Basic]
- attribute names [XML in Visual Basic]
- XML literals [Visual Basic], element names
ms.assetid: cc110118-b6cf-4ff9-a4e4-6233c90c9fbf
ms.openlocfilehash: dbe85b456f46c40c9cc9a703b38e11992edd24cf
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64598278"
---
# <a name="names-of-declared-xml-elements-and-attributes-visual-basic"></a><span data-ttu-id="9ab05-102">宣言する XML 要素と属性の名前 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9ab05-102">Names of Declared XML Elements and Attributes (Visual Basic)</span></span>
<span data-ttu-id="9ab05-103">このトピックでは、XML リテラルの XML 要素と属性の名前付けの Visual Basic のガイドラインを提供します。</span><span class="sxs-lookup"><span data-stu-id="9ab05-103">This topic provides Visual Basic guidelines for naming XML elements and attributes in XML literals.</span></span>  <span data-ttu-id="9ab05-104">XML リテラルでは、ローカル名または修飾名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="9ab05-104">In an XML literal, you can specify a local name or a qualified name.</span></span> <span data-ttu-id="9ab05-105">修飾名は、XML 名前空間プレフィックス、コロン、およびローカル名で構成されます。</span><span class="sxs-lookup"><span data-stu-id="9ab05-105">A qualified name consists of an XML namespace prefix, a colon, and a local name.</span></span> <span data-ttu-id="9ab05-106">XML 名前空間プレフィックスの詳細については、次を参照してください。 [XML 要素リテラル](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)します。</span><span class="sxs-lookup"><span data-stu-id="9ab05-106">For more information about XML namespace prefixes, see [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="9ab05-107">ルール</span><span class="sxs-lookup"><span data-stu-id="9ab05-107">Rules</span></span>  
 <span data-ttu-id="9ab05-108">要素または Visual Basic での属性のローカル名は、次の規則に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ab05-108">A local name of an element or attribute in Visual Basic must adhere to the following rules.</span></span>  
  
- <span data-ttu-id="9ab05-109">名前空間がそれを開始できます。</span><span class="sxs-lookup"><span data-stu-id="9ab05-109">It can begin with a namespace.</span></span> <span data-ttu-id="9ab05-110">先頭にアルファベットまたはアンダー スコア (`_`)。</span><span class="sxs-lookup"><span data-stu-id="9ab05-110">It must begin with an alphabetical character or an underscore (`_`).</span></span>  
  
- <span data-ttu-id="9ab05-111">それだけアルファベット文字、10 進数字、アンダー スコア、ピリオド (.)、およびハイフンを含める必要があります (-)。</span><span class="sxs-lookup"><span data-stu-id="9ab05-111">It must contain only alphabetical characters, decimal digits, underscores, periods (.), and hyphens (-).</span></span>  
  
- <span data-ttu-id="9ab05-112">1,024 を超える文字はできません。</span><span class="sxs-lookup"><span data-stu-id="9ab05-112">It must not be more than 1,024 characters long.</span></span>  
  
- <span data-ttu-id="9ab05-113">名前に含まれるコロンは、名前空間の区切りを示します。</span><span class="sxs-lookup"><span data-stu-id="9ab05-113">Colons that appear in names indicate namespace demarcation.</span></span> <span data-ttu-id="9ab05-114">そのため、特定の名前の XML 名前空間を指定するだけのコロンを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="9ab05-114">Therefore, you can use colons only to specify an XML namespace for a particular name.</span></span>  
  
 <span data-ttu-id="9ab05-115">さらは、次のガイドラインに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ab05-115">In addition, you should adhere to the following guideline.</span></span>  
  
- <span data-ttu-id="9ab05-116">XML 1.0 仕様では、任意の大文字と小文字のバリエーションの"xml"、文字列で始まるすべての名前を予約します。</span><span class="sxs-lookup"><span data-stu-id="9ab05-116">The XML 1.0 specification reserves all names starting with the string "xml", of any capitalization variation.</span></span> <span data-ttu-id="9ab05-117">したがって、これらの要素名および属性名は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="9ab05-117">Therefore, do not use those names for your element and attribute names.</span></span>  
  
### <a name="name-length-guidelines"></a><span data-ttu-id="9ab05-118">名前の長さのガイドライン</span><span class="sxs-lookup"><span data-stu-id="9ab05-118">Name Length Guidelines</span></span>  
 <span data-ttu-id="9ab05-119">実際には、名前はできるだけ短く中の要素の特性を明確にします。</span><span class="sxs-lookup"><span data-stu-id="9ab05-119">As a practical matter, a name should be as short as possible while still clearly identifying the nature of the element.</span></span> <span data-ttu-id="9ab05-120">これは、コードの読みやすさが向上し、行の長さとソース ファイルのサイズを縮小します。</span><span class="sxs-lookup"><span data-stu-id="9ab05-120">This improves the readability of your code and reduces line length and source-file size.</span></span>  
  
 <span data-ttu-id="9ab05-121">ただし、自分の名前は、長さいない適切に記述できる、要素またはコードがそれを使用する方法である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ab05-121">However, your name should not be so short that it does not adequately describe the element or how your code uses it.</span></span> <span data-ttu-id="9ab05-122">これは、コードの読みやすさにとって重要です。</span><span class="sxs-lookup"><span data-stu-id="9ab05-122">This is important for the readability of your code.</span></span> <span data-ttu-id="9ab05-123">それを理解しようとする他の人がいる場合、または自分で探している場合に作成した後、長い時間は、適切な要素名は、時間を節約できます。</span><span class="sxs-lookup"><span data-stu-id="9ab05-123">If somebody else is trying to understand it, or if you yourself are looking at it a long time after you wrote it, appropriate element names can save time.</span></span>  
  
## <a name="case-sensitivity-in-names"></a><span data-ttu-id="9ab05-124">名前に大文字小文字の区別</span><span class="sxs-lookup"><span data-stu-id="9ab05-124">Case Sensitivity in Names</span></span>  
 <span data-ttu-id="9ab05-125">XML 要素名は大文字小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="9ab05-125">XML element names are case sensitive.</span></span> <span data-ttu-id="9ab05-126">つまり、Visual Basic コンパイラでは、アルファベットの大文字小文字のみが異なる 2 つの名前を比較をする際にいると解釈別の名前。</span><span class="sxs-lookup"><span data-stu-id="9ab05-126">This means that when the Visual Basic compiler compares two names that differ in alphabetical case only, it interprets them as different names.</span></span> <span data-ttu-id="9ab05-127">たとえば、解釈`ABC`と`abc`要素を区切るを指しています。</span><span class="sxs-lookup"><span data-stu-id="9ab05-127">For example, it interprets `ABC` and `abc` as referring to separate elements.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="9ab05-128">XML 名前空間</span><span class="sxs-lookup"><span data-stu-id="9ab05-128">XML Namespaces</span></span>  
 <span data-ttu-id="9ab05-129">XML 要素リテラルを作成する場合は、要素名の XML 名前空間プレフィックスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="9ab05-129">When creating an XML element literal, you can specify the XML namespace prefix for the element name.</span></span> <span data-ttu-id="9ab05-130">詳細については、次を参照してください。 [XML 要素リテラル](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)します。</span><span class="sxs-lookup"><span data-stu-id="9ab05-130">For more information, see [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ab05-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="9ab05-131">See also</span></span>

- [<span data-ttu-id="9ab05-132">Visual Basic での XML の作成</span><span class="sxs-lookup"><span data-stu-id="9ab05-132">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="9ab05-133">XML 要素リテラル</span><span class="sxs-lookup"><span data-stu-id="9ab05-133">XML Element Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
