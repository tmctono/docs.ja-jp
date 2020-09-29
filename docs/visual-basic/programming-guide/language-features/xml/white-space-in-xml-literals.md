---
title: XML リテラルでの空白文字
ms.date: 07/20/2015
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
ms.openlocfilehash: 5db8f92117e77d96eab34f28758546393e2afca0
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91099100"
---
# <a name="white-space-in-xml-literals-visual-basic"></a><span data-ttu-id="d3f32-102">XML リテラルでの空白文字 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d3f32-102">White Space in XML Literals (Visual Basic)</span></span>

<span data-ttu-id="d3f32-103">Visual Basic コンパイラは、[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] オブジェクトを作成するときに、XML リテラルから有意の空白文字のみを組み込みます。</span><span class="sxs-lookup"><span data-stu-id="d3f32-103">The Visual Basic compiler incorporates only the significant white space characters from an XML literal when it creates a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object.</span></span> <span data-ttu-id="d3f32-104">意味のない空白文字は組み込まれません。</span><span class="sxs-lookup"><span data-stu-id="d3f32-104">The insignificant white space characters are not incorporated.</span></span>  
  
## <a name="significant-and-insignificant-white-space"></a><span data-ttu-id="d3f32-105">有意の空白と意味のない空白</span><span class="sxs-lookup"><span data-stu-id="d3f32-105">Significant and Insignificant White Space</span></span>  

 <span data-ttu-id="d3f32-106">XML リテラルの空白文字は、次の 3 つの領域でのみ意味があります。</span><span class="sxs-lookup"><span data-stu-id="d3f32-106">White space characters in XML literals are significant in only three areas:</span></span>  
  
- <span data-ttu-id="d3f32-107">属性値に含まれている場合。</span><span class="sxs-lookup"><span data-stu-id="d3f32-107">When they are in an attribute value.</span></span>  
  
- <span data-ttu-id="d3f32-108">要素のテキスト コンテンツの一部であり、テキストに他の文字も含まれている場合。</span><span class="sxs-lookup"><span data-stu-id="d3f32-108">When they are part of an element's text content and the text also contains other characters.</span></span>  
  
- <span data-ttu-id="d3f32-109">要素のテキスト コンテンツの埋め込み式に含まれている場合。</span><span class="sxs-lookup"><span data-stu-id="d3f32-109">When they are in an embedded expression for an element's text content.</span></span>  
  
 <span data-ttu-id="d3f32-110">それ以外の場合、空白文字はコンパイラによって意味のないものとして扱われ、リテラルの [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] オブジェクトに含まれません。</span><span class="sxs-lookup"><span data-stu-id="d3f32-110">Otherwise, the compiler treats white space characters as insignificant and does not include then in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object for the literal.</span></span>  
  
 <span data-ttu-id="d3f32-111">XML リテラルに意味のない空白を含めるには、空白を含む文字列リテラルを含む埋め込み式を使用します。</span><span class="sxs-lookup"><span data-stu-id="d3f32-111">To include insignificant white space in an XML literal, use an embedded expression that contains a string literal with the white space.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d3f32-112">XML 要素リテラルに `xml:space` 属性が含まれている場合、Visual Basic コンパイラによって <xref:System.Xml.Linq.XElement> オブジェクトに属性が含まれますが、この属性を追加しても、コンパイラが空白を処理する方法は変わりません。</span><span class="sxs-lookup"><span data-stu-id="d3f32-112">If the `xml:space` attribute appears in an XML element literal, the Visual Basic compiler includes the attribute in the <xref:System.Xml.Linq.XElement> object, but adding this attribute does not change how the compiler treats white space.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="d3f32-113">使用例</span><span class="sxs-lookup"><span data-stu-id="d3f32-113">Examples</span></span>  

 <span data-ttu-id="d3f32-114">次の例には、2 つの XML 要素 (outer と inner) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d3f32-114">The following example contains two XML elements, outer and inner.</span></span> <span data-ttu-id="d3f32-115">どちらの要素にも、テキスト コンテンツ内に空白が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d3f32-115">Both elements contain white space in their text content.</span></span> <span data-ttu-id="d3f32-116">outer 要素には空白と XML 要素しか含まれていないため、その空白は意味がありません。</span><span class="sxs-lookup"><span data-stu-id="d3f32-116">The white space in the outer element is insignificant because it contains only white space and an XML element.</span></span> <span data-ttu-id="d3f32-117">inner 要素には空白とテキストが含まれているため、その空白は有意です。</span><span class="sxs-lookup"><span data-stu-id="d3f32-117">The white space in the inner element is significant because it contains white space and text.</span></span>  
  
 [!code-vb[VbXMLSamples#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#29)]  
  
 <span data-ttu-id="d3f32-118">このコードを実行すると、次のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d3f32-118">When run, this code displays the following text.</span></span>  
  
```xml  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d3f32-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="d3f32-119">See also</span></span>

- [<span data-ttu-id="d3f32-120">Visual Basic での XML の作成</span><span class="sxs-lookup"><span data-stu-id="d3f32-120">Creating XML in Visual Basic</span></span>](creating-xml.md)
