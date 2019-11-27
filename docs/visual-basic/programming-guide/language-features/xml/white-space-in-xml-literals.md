---
title: XML リテラルでの空白文字
ms.date: 07/20/2015
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
ms.openlocfilehash: 56ededeb12d07e979bc86b03924e1ae0f0432822
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74336010"
---
# <a name="white-space-in-xml-literals-visual-basic"></a><span data-ttu-id="0dfc6-102">XML リテラルでの空白文字 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0dfc6-102">White Space in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="0dfc6-103">Visual Basic コンパイラは、[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] オブジェクトを作成するときに、XML リテラルから有意な空白文字のみを組み込みます。</span><span class="sxs-lookup"><span data-stu-id="0dfc6-103">The Visual Basic compiler incorporates only the significant white space characters from an XML literal when it creates a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object.</span></span> <span data-ttu-id="0dfc6-104">意味のない空白文字は組み込まれていません。</span><span class="sxs-lookup"><span data-stu-id="0dfc6-104">The insignificant white space characters are not incorporated.</span></span>  
  
## <a name="significant-and-insignificant-white-space"></a><span data-ttu-id="0dfc6-105">有意で意味のない空白</span><span class="sxs-lookup"><span data-stu-id="0dfc6-105">Significant and Insignificant White Space</span></span>  
 <span data-ttu-id="0dfc6-106">XML リテラルの空白文字は、3つの領域でのみ重要です。</span><span class="sxs-lookup"><span data-stu-id="0dfc6-106">White space characters in XML literals are significant in only three areas:</span></span>  
  
- <span data-ttu-id="0dfc6-107">属性値に含まれている場合。</span><span class="sxs-lookup"><span data-stu-id="0dfc6-107">When they are in an attribute value.</span></span>  
  
- <span data-ttu-id="0dfc6-108">要素のテキストコンテンツの一部であり、テキストに他の文字も含まれている場合。</span><span class="sxs-lookup"><span data-stu-id="0dfc6-108">When they are part of an element's text content and the text also contains other characters.</span></span>  
  
- <span data-ttu-id="0dfc6-109">要素のテキストコンテンツの埋め込み式に含まれている場合。</span><span class="sxs-lookup"><span data-stu-id="0dfc6-109">When they are in an embedded expression for an element's text content.</span></span>  
  
 <span data-ttu-id="0dfc6-110">それ以外の場合、コンパイラは空白文字を意味のないものとして扱い、リテラルの [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] オブジェクトには含まれません。</span><span class="sxs-lookup"><span data-stu-id="0dfc6-110">Otherwise, the compiler treats white space characters as insignificant and does not include then in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object for the literal.</span></span>  
  
 <span data-ttu-id="0dfc6-111">XML リテラルに意味のない空白を含めるには、空白を含む文字列リテラルを含む埋め込み式を使用します。</span><span class="sxs-lookup"><span data-stu-id="0dfc6-111">To include insignificant white space in an XML literal, use an embedded expression that contains a string literal with the white space.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0dfc6-112">XML 要素リテラルに `xml:space` 属性が含まれている場合、Visual Basic コンパイラは <xref:System.Xml.Linq.XElement> オブジェクトに属性を含めますが、この属性を追加しても、コンパイラが空白を処理する方法は変更されません。</span><span class="sxs-lookup"><span data-stu-id="0dfc6-112">If the `xml:space` attribute appears in an XML element literal, the Visual Basic compiler includes the attribute in the <xref:System.Xml.Linq.XElement> object, but adding this attribute does not change how the compiler treats white space.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="0dfc6-113">使用例</span><span class="sxs-lookup"><span data-stu-id="0dfc6-113">Examples</span></span>  
 <span data-ttu-id="0dfc6-114">次の例には、outer と inner の2つの XML 要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0dfc6-114">The following example contains two XML elements, outer and inner.</span></span> <span data-ttu-id="0dfc6-115">両方の要素には、テキストコンテンツ内に空白が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0dfc6-115">Both elements contain white space in their text content.</span></span> <span data-ttu-id="0dfc6-116">外側の要素の空白文字は、空白と XML 要素のみが含まれているため、意味がありません。</span><span class="sxs-lookup"><span data-stu-id="0dfc6-116">The white space in the outer element is insignificant because it contains only white space and an XML element.</span></span> <span data-ttu-id="0dfc6-117">内部要素の空白は、空白とテキストが含まれているため、重要です。</span><span class="sxs-lookup"><span data-stu-id="0dfc6-117">The white space in the inner element is significant because it contains white space and text.</span></span>  
  
 [!code-vb[VbXMLSamples#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#29)]  
  
 <span data-ttu-id="0dfc6-118">このコードを実行すると、次のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0dfc6-118">When run, this code displays the following text.</span></span>  
  
```xml  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0dfc6-119">参照</span><span class="sxs-lookup"><span data-stu-id="0dfc6-119">See also</span></span>

- [<span data-ttu-id="0dfc6-120">Visual Basic での XML の作成</span><span class="sxs-lookup"><span data-stu-id="0dfc6-120">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
