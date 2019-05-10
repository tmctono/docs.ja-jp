---
title: XML リテラルでの空白文字 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
ms.openlocfilehash: 903928087d5ad9c51040ba6bf65639f44d8c7dd6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64627436"
---
# <a name="white-space-in-xml-literals-visual-basic"></a><span data-ttu-id="ac1b6-102">XML リテラルでの空白文字 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ac1b6-102">White Space in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="ac1b6-103">作成時に、Visual Basic コンパイラは XML リテラルの有意の空白文字だけが組み込まれて、[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ac1b6-103">The Visual Basic compiler incorporates only the significant white space characters from an XML literal when it creates a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object.</span></span> <span data-ttu-id="ac1b6-104">余分な空白文字は組み込まれません。</span><span class="sxs-lookup"><span data-stu-id="ac1b6-104">The insignificant white space characters are not incorporated.</span></span>  
  
## <a name="significant-and-insignificant-white-space"></a><span data-ttu-id="ac1b6-105">有意の空白文字</span><span class="sxs-lookup"><span data-stu-id="ac1b6-105">Significant and Insignificant White Space</span></span>  
 <span data-ttu-id="ac1b6-106">XML リテラルの空白文字は、のみの 3 つの領域には重要です。</span><span class="sxs-lookup"><span data-stu-id="ac1b6-106">White space characters in XML literals are significant in only three areas:</span></span>  
  
- <span data-ttu-id="ac1b6-107">属性値に含まれる場合。</span><span class="sxs-lookup"><span data-stu-id="ac1b6-107">When they are in an attribute value.</span></span>  
  
- <span data-ttu-id="ac1b6-108">要素のテキスト コンテンツの一部であるし、テキストには、その他の文字も含まれています。</span><span class="sxs-lookup"><span data-stu-id="ac1b6-108">When they are part of an element's text content and the text also contains other characters.</span></span>  
  
- <span data-ttu-id="ac1b6-109">要素のテキスト コンテンツの埋め込み式に含まれる場合。</span><span class="sxs-lookup"><span data-stu-id="ac1b6-109">When they are in an embedded expression for an element's text content.</span></span>  
  
 <span data-ttu-id="ac1b6-110">それ以外の場合、コンパイラとして意味のない空白文字を処理しでは、含まれません、[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]リテラルのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ac1b6-110">Otherwise, the compiler treats white space characters as insignificant and does not include then in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object for the literal.</span></span>  
  
 <span data-ttu-id="ac1b6-111">余分な空白を XML リテラルに含めるには、文字列リテラルの空白を含む埋め込み式を使用します。</span><span class="sxs-lookup"><span data-stu-id="ac1b6-111">To include insignificant white space in an XML literal, use an embedded expression that contains a string literal with the white space.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac1b6-112">場合、 `xml:space` XML 要素リテラルの属性が表示されたら、Visual Basic コンパイラにはで属性が含まれています、<xref:System.Xml.Linq.XElement>オブジェクトが、この属性は、コンパイラによる空白の処理方法を変更していないを追加します。</span><span class="sxs-lookup"><span data-stu-id="ac1b6-112">If the `xml:space` attribute appears in an XML element literal, the Visual Basic compiler includes the attribute in the <xref:System.Xml.Linq.XElement> object, but adding this attribute does not change how the compiler treats white space.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="ac1b6-113">使用例</span><span class="sxs-lookup"><span data-stu-id="ac1b6-113">Examples</span></span>  
 <span data-ttu-id="ac1b6-114">次の例には、外部と内部の 2 つの XML 要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ac1b6-114">The following example contains two XML elements, outer and inner.</span></span> <span data-ttu-id="ac1b6-115">両方の要素には、そのテキスト コンテンツ内の空白が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ac1b6-115">Both elements contain white space in their text content.</span></span> <span data-ttu-id="ac1b6-116">空白と XML 要素のみが含まれているため、外側の要素内の空白は意味はありません。</span><span class="sxs-lookup"><span data-stu-id="ac1b6-116">The white space in the outer element is insignificant because it contains only white space and an XML element.</span></span> <span data-ttu-id="ac1b6-117">空白文字とテキストが含まれているために、内部の要素内の空白は重要です。</span><span class="sxs-lookup"><span data-stu-id="ac1b6-117">The white space in the inner element is significant because it contains white space and text.</span></span>  
  
 [!code-vb[VbXMLSamples#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#29)]  
  
 <span data-ttu-id="ac1b6-118">実行すると、このコードは、次のテキストを表示します。</span><span class="sxs-lookup"><span data-stu-id="ac1b6-118">When run, this code displays the following text.</span></span>  
  
```xml  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ac1b6-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="ac1b6-119">See also</span></span>

- [<span data-ttu-id="ac1b6-120">Visual Basic での XML の作成</span><span class="sxs-lookup"><span data-stu-id="ac1b6-120">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
