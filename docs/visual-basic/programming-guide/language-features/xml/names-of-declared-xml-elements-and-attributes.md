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
ms.openlocfilehash: 2142674c3de4c5ac9e806c1328daa3efb697beb9
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085621"
---
# <a name="names-of-declared-xml-elements-and-attributes-visual-basic"></a><span data-ttu-id="18bb7-102">宣言する XML 要素と属性の名前 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="18bb7-102">Names of Declared XML Elements and Attributes (Visual Basic)</span></span>

<span data-ttu-id="18bb7-103">このトピックでは、XML リテラルで XML 要素と属性に名前を付けるための Visual Basic ガイドラインを示します。</span><span class="sxs-lookup"><span data-stu-id="18bb7-103">This topic provides Visual Basic guidelines for naming XML elements and attributes in XML literals.</span></span>  <span data-ttu-id="18bb7-104">XML リテラルでは、ローカル名を指定することも修飾名を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="18bb7-104">In an XML literal, you can specify a local name or a qualified name.</span></span> <span data-ttu-id="18bb7-105">修飾名は、XML 名前空間プレフィックス、コロン、およびローカル名から成ります。</span><span class="sxs-lookup"><span data-stu-id="18bb7-105">A qualified name consists of an XML namespace prefix, a colon, and a local name.</span></span> <span data-ttu-id="18bb7-106">XML 名前空間プレフィックスの詳細については、「[XML 要素リテラル](../../../language-reference/xml-literals/xml-element-literal.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18bb7-106">For more information about XML namespace prefixes, see [XML Element Literal](../../../language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="18bb7-107">ルール</span><span class="sxs-lookup"><span data-stu-id="18bb7-107">Rules</span></span>  

 <span data-ttu-id="18bb7-108">Visual Basic での要素または属性のローカル名は、次の規則に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="18bb7-108">A local name of an element or attribute in Visual Basic must adhere to the following rules.</span></span>  
  
- <span data-ttu-id="18bb7-109">名前空間で始めることができます。</span><span class="sxs-lookup"><span data-stu-id="18bb7-109">It can begin with a namespace.</span></span> <span data-ttu-id="18bb7-110">先頭は英文字またはアンダースコア (`_`) にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="18bb7-110">It must begin with an alphabetical character or an underscore (`_`).</span></span>  
  
- <span data-ttu-id="18bb7-111">アルファベット文字、10 進数字、アンダースコア、ピリオド (.)、ハイフン (-) のみを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="18bb7-111">It must contain only alphabetical characters, decimal digits, underscores, periods (.), and hyphens (-).</span></span>  
  
- <span data-ttu-id="18bb7-112">文字の長さは 1,024 文字以内とする必要があります。</span><span class="sxs-lookup"><span data-stu-id="18bb7-112">It must not be more than 1,024 characters long.</span></span>  
  
- <span data-ttu-id="18bb7-113">名前に表示されるコロンは、名前空間の境界を示します。</span><span class="sxs-lookup"><span data-stu-id="18bb7-113">Colons that appear in names indicate namespace demarcation.</span></span> <span data-ttu-id="18bb7-114">したがって、コロンを使用できるのは、特定の名前の XML 名前空間を指定する場合のみとなります。</span><span class="sxs-lookup"><span data-stu-id="18bb7-114">Therefore, you can use colons only to specify an XML namespace for a particular name.</span></span>  
  
 <span data-ttu-id="18bb7-115">さらに、次のガイドラインに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="18bb7-115">In addition, you should adhere to the following guideline.</span></span>  
  
- <span data-ttu-id="18bb7-116">XML 1.0 仕様では、文字列 "xml" の大文字小文字のどのバリエーションで始まる名前もすべて予約されています。</span><span class="sxs-lookup"><span data-stu-id="18bb7-116">The XML 1.0 specification reserves all names starting with the string "xml", of any capitalization variation.</span></span> <span data-ttu-id="18bb7-117">したがって、要素名と属性名にはこれらの名前を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="18bb7-117">Therefore, do not use those names for your element and attribute names.</span></span>  
  
### <a name="name-length-guidelines"></a><span data-ttu-id="18bb7-118">名前の長さのガイドライン</span><span class="sxs-lookup"><span data-stu-id="18bb7-118">Name Length Guidelines</span></span>  

 <span data-ttu-id="18bb7-119">現実問題として、名前は、可能な限り短くしながらも、要素の性質を明確に特定するものにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="18bb7-119">As a practical matter, a name should be as short as possible while still clearly identifying the nature of the element.</span></span> <span data-ttu-id="18bb7-120">これにより、コードの読みやすさが向上し、行の長さとソース ファイルのサイズが減少します。</span><span class="sxs-lookup"><span data-stu-id="18bb7-120">This improves the readability of your code and reduces line length and source-file size.</span></span>  
  
 <span data-ttu-id="18bb7-121">ただし、要素について、またコードでのその使用方法について適切に説明できないような短い名前にはしないでください。</span><span class="sxs-lookup"><span data-stu-id="18bb7-121">However, your name should not be so short that it does not adequately describe the element or how your code uses it.</span></span> <span data-ttu-id="18bb7-122">これはコードの読みやすさのために重要です。</span><span class="sxs-lookup"><span data-stu-id="18bb7-122">This is important for the readability of your code.</span></span> <span data-ttu-id="18bb7-123">他の誰かが理解しようとするとき、または自分自身がそれを記述して長い時間が経過してからそれを見た場合に、適切な要素名であれば時間を節約できます。</span><span class="sxs-lookup"><span data-stu-id="18bb7-123">If somebody else is trying to understand it, or if you yourself are looking at it a long time after you wrote it, appropriate element names can save time.</span></span>  
  
## <a name="case-sensitivity-in-names"></a><span data-ttu-id="18bb7-124">名前の大文字と小文字の区別</span><span class="sxs-lookup"><span data-stu-id="18bb7-124">Case Sensitivity in Names</span></span>  

 <span data-ttu-id="18bb7-125">XML 要素名では大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="18bb7-125">XML element names are case sensitive.</span></span> <span data-ttu-id="18bb7-126">つまり、英字の大文字と小文字の違いしかない 2 つの名前を比較した場合、Visual Basic コンパイラではそれらを異なる名前と解釈します。</span><span class="sxs-lookup"><span data-stu-id="18bb7-126">This means that when the Visual Basic compiler compares two names that differ in alphabetical case only, it interprets them as different names.</span></span> <span data-ttu-id="18bb7-127">たとえば、`ABC` と `abc` は別々の要素を示していると解釈されます。</span><span class="sxs-lookup"><span data-stu-id="18bb7-127">For example, it interprets `ABC` and `abc` as referring to separate elements.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="18bb7-128">XML 名前空間</span><span class="sxs-lookup"><span data-stu-id="18bb7-128">XML Namespaces</span></span>  

 <span data-ttu-id="18bb7-129">XML 要素リテラルを作成するときに、要素名に XML 名前空間プレフィックスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="18bb7-129">When creating an XML element literal, you can specify the XML namespace prefix for the element name.</span></span> <span data-ttu-id="18bb7-130">詳細については、「[XML 要素リテラル](../../../language-reference/xml-literals/xml-element-literal.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18bb7-130">For more information, see [XML Element Literal](../../../language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18bb7-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="18bb7-131">See also</span></span>

- [<span data-ttu-id="18bb7-132">Visual Basic での XML の作成</span><span class="sxs-lookup"><span data-stu-id="18bb7-132">Creating XML in Visual Basic</span></span>](creating-xml.md)
- [<span data-ttu-id="18bb7-133">XML 要素リテラル</span><span class="sxs-lookup"><span data-stu-id="18bb7-133">XML Element Literal</span></span>](../../../language-reference/xml-literals/xml-element-literal.md)
