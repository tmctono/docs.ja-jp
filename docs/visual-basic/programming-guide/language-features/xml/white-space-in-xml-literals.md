---
title: XML リテラルでの空白文字 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
ms.openlocfilehash: 08be345557d10a528aa03234883eba1b3a31beaa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62054940"
---
# <a name="white-space-in-xml-literals-visual-basic"></a><span data-ttu-id="78223-102">XML リテラルでの空白文字 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="78223-102">White Space in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="78223-103">作成時に、Visual Basic コンパイラは XML リテラルの有意の空白文字だけが組み込まれて、[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="78223-103">The Visual Basic compiler incorporates only the significant white space characters from an XML literal when it creates a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object.</span></span> <span data-ttu-id="78223-104">余分な空白文字は組み込まれません。</span><span class="sxs-lookup"><span data-stu-id="78223-104">The insignificant white space characters are not incorporated.</span></span>  
  
## <a name="significant-and-insignificant-white-space"></a><span data-ttu-id="78223-105">有意の空白文字</span><span class="sxs-lookup"><span data-stu-id="78223-105">Significant and Insignificant White Space</span></span>  
 <span data-ttu-id="78223-106">XML リテラルの空白文字は、のみの 3 つの領域には重要です。</span><span class="sxs-lookup"><span data-stu-id="78223-106">White space characters in XML literals are significant in only three areas:</span></span>  
  
- <span data-ttu-id="78223-107">属性値に含まれる場合。</span><span class="sxs-lookup"><span data-stu-id="78223-107">When they are in an attribute value.</span></span>  
  
- <span data-ttu-id="78223-108">要素のテキスト コンテンツの一部であるし、テキストには、その他の文字も含まれています。</span><span class="sxs-lookup"><span data-stu-id="78223-108">When they are part of an element's text content and the text also contains other characters.</span></span>  
  
- <span data-ttu-id="78223-109">要素のテキスト コンテンツの埋め込み式に含まれる場合。</span><span class="sxs-lookup"><span data-stu-id="78223-109">When they are in an embedded expression for an element's text content.</span></span>  
  
 <span data-ttu-id="78223-110">それ以外の場合、コンパイラとして意味のない空白文字を処理しでは、含まれません、[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]リテラルのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="78223-110">Otherwise, the compiler treats white space characters as insignificant and does not include then in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object for the literal.</span></span>  
  
 <span data-ttu-id="78223-111">余分な空白を XML リテラルに含めるには、文字列リテラルの空白を含む埋め込み式を使用します。</span><span class="sxs-lookup"><span data-stu-id="78223-111">To include insignificant white space in an XML literal, use an embedded expression that contains a string literal with the white space.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="78223-112">場合、 `xml:space` XML 要素リテラルの属性が表示されたら、Visual Basic コンパイラにはで属性が含まれています、<xref:System.Xml.Linq.XElement>オブジェクトが、この属性は、コンパイラによる空白の処理方法を変更していないを追加します。</span><span class="sxs-lookup"><span data-stu-id="78223-112">If the `xml:space` attribute appears in an XML element literal, the Visual Basic compiler includes the attribute in the <xref:System.Xml.Linq.XElement> object, but adding this attribute does not change how the compiler treats white space.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="78223-113">使用例</span><span class="sxs-lookup"><span data-stu-id="78223-113">Examples</span></span>  
 <span data-ttu-id="78223-114">次の例には、外部と内部の 2 つの XML 要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="78223-114">The following example contains two XML elements, outer and inner.</span></span> <span data-ttu-id="78223-115">両方の要素には、そのテキスト コンテンツ内の空白が含まれます。</span><span class="sxs-lookup"><span data-stu-id="78223-115">Both elements contain white space in their text content.</span></span> <span data-ttu-id="78223-116">空白と XML 要素のみが含まれているため、外側の要素内の空白は意味はありません。</span><span class="sxs-lookup"><span data-stu-id="78223-116">The white space in the outer element is insignificant because it contains only white space and an XML element.</span></span> <span data-ttu-id="78223-117">空白文字とテキストが含まれているために、内部の要素内の空白は重要です。</span><span class="sxs-lookup"><span data-stu-id="78223-117">The white space in the inner element is significant because it contains white space and text.</span></span>  
  
 [!code-vb[VbXMLSamples#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#29)]  
  
 <span data-ttu-id="78223-118">実行すると、このコードは、次のテキストを表示します。</span><span class="sxs-lookup"><span data-stu-id="78223-118">When run, this code displays the following text.</span></span>  
  
```xml  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a><span data-ttu-id="78223-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="78223-119">See also</span></span>

- [<span data-ttu-id="78223-120">Visual Basic での XML の作成</span><span class="sxs-lookup"><span data-stu-id="78223-120">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
