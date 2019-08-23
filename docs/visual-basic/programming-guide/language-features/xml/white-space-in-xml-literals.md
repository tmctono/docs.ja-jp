---
title: XML リテラルでの空白文字 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
ms.openlocfilehash: f72dcc25b158d793850069e5cc32c3a3c02fad17
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939209"
---
# <a name="white-space-in-xml-literals-visual-basic"></a><span data-ttu-id="64e22-102">XML リテラルでの空白文字 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="64e22-102">White Space in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="64e22-103">Visual Basic コンパイラは、オブジェクトを[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]作成するときに、XML リテラルから有意な空白文字のみを組み込みます。</span><span class="sxs-lookup"><span data-stu-id="64e22-103">The Visual Basic compiler incorporates only the significant white space characters from an XML literal when it creates a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object.</span></span> <span data-ttu-id="64e22-104">意味のない空白文字は組み込まれていません。</span><span class="sxs-lookup"><span data-stu-id="64e22-104">The insignificant white space characters are not incorporated.</span></span>  
  
## <a name="significant-and-insignificant-white-space"></a><span data-ttu-id="64e22-105">有意で意味のない空白</span><span class="sxs-lookup"><span data-stu-id="64e22-105">Significant and Insignificant White Space</span></span>  
 <span data-ttu-id="64e22-106">XML リテラルの空白文字は、3つの領域でのみ重要です。</span><span class="sxs-lookup"><span data-stu-id="64e22-106">White space characters in XML literals are significant in only three areas:</span></span>  
  
- <span data-ttu-id="64e22-107">属性値に含まれている場合。</span><span class="sxs-lookup"><span data-stu-id="64e22-107">When they are in an attribute value.</span></span>  
  
- <span data-ttu-id="64e22-108">要素のテキストコンテンツの一部であり、テキストに他の文字も含まれている場合。</span><span class="sxs-lookup"><span data-stu-id="64e22-108">When they are part of an element's text content and the text also contains other characters.</span></span>  
  
- <span data-ttu-id="64e22-109">要素のテキストコンテンツの埋め込み式に含まれている場合。</span><span class="sxs-lookup"><span data-stu-id="64e22-109">When they are in an embedded expression for an element's text content.</span></span>  
  
 <span data-ttu-id="64e22-110">それ以外の場合、コンパイラは空白文字を意味のないものとして[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]扱い、リテラルのオブジェクトには含まれません。</span><span class="sxs-lookup"><span data-stu-id="64e22-110">Otherwise, the compiler treats white space characters as insignificant and does not include then in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object for the literal.</span></span>  
  
 <span data-ttu-id="64e22-111">XML リテラルに意味のない空白を含めるには、空白を含む文字列リテラルを含む埋め込み式を使用します。</span><span class="sxs-lookup"><span data-stu-id="64e22-111">To include insignificant white space in an XML literal, use an embedded expression that contains a string literal with the white space.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="64e22-112">XML 要素リテラルに<xref:System.Xml.Linq.XElement> 属性が含まれている場合、VisualBasicコンパイラでは、オブジェクトに属性が含まれますが、この属性を追加しても、コンパイラが空白を処理する方法は変更されません。`xml:space`</span><span class="sxs-lookup"><span data-stu-id="64e22-112">If the `xml:space` attribute appears in an XML element literal, the Visual Basic compiler includes the attribute in the <xref:System.Xml.Linq.XElement> object, but adding this attribute does not change how the compiler treats white space.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="64e22-113">使用例</span><span class="sxs-lookup"><span data-stu-id="64e22-113">Examples</span></span>  
 <span data-ttu-id="64e22-114">次の例には、outer と inner の2つの XML 要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="64e22-114">The following example contains two XML elements, outer and inner.</span></span> <span data-ttu-id="64e22-115">両方の要素には、テキストコンテンツ内に空白が含まれています。</span><span class="sxs-lookup"><span data-stu-id="64e22-115">Both elements contain white space in their text content.</span></span> <span data-ttu-id="64e22-116">外側の要素の空白文字は、空白と XML 要素のみが含まれているため、意味がありません。</span><span class="sxs-lookup"><span data-stu-id="64e22-116">The white space in the outer element is insignificant because it contains only white space and an XML element.</span></span> <span data-ttu-id="64e22-117">内部要素の空白は、空白とテキストが含まれているため、重要です。</span><span class="sxs-lookup"><span data-stu-id="64e22-117">The white space in the inner element is significant because it contains white space and text.</span></span>  
  
 [!code-vb[VbXMLSamples#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#29)]  
  
 <span data-ttu-id="64e22-118">このコードを実行すると、次のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="64e22-118">When run, this code displays the following text.</span></span>  
  
```xml  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a><span data-ttu-id="64e22-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="64e22-119">See also</span></span>

- [<span data-ttu-id="64e22-120">Visual Basic での XML の作成</span><span class="sxs-lookup"><span data-stu-id="64e22-120">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
