---
title: '方法: XML 子孫要素にアクセスする'
ms.date: 07/20/2015
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
ms.openlocfilehash: cc045114c67ee2917ef672e734bc852c40d408ac
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347154"
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a><span data-ttu-id="d532d-102">方法 : XML 子孫要素にアクセスする (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d532d-102">How to: Access XML Descendant Elements (Visual Basic)</span></span>
<span data-ttu-id="d532d-103">この例では、子孫軸プロパティを使用して、指定された名前を持ち、XML 要素に含まれているすべての XML 要素にアクセスする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d532d-103">This example shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under an XML element.</span></span> <span data-ttu-id="d532d-104">具体的には、`Value` プロパティを使用して、`name` 子孫軸プロパティが返すコレクション内の最初の要素の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="d532d-104">In particular, it uses the `Value` property to get the value of the first element in the collection that the `name` descendant axis property returns.</span></span> <span data-ttu-id="d532d-105">`name` の子孫軸プロパティは、`contacts` オブジェクトに含まれる `name` という名前のすべての要素を取得します。</span><span class="sxs-lookup"><span data-stu-id="d532d-105">The `name` descendant axis property gets all elements named `name` that are contained in the `contacts` object.</span></span> <span data-ttu-id="d532d-106">また、この例では、`phone` の子孫軸プロパティを使用して、`contacts` オブジェクトに含まれている `phone` という名前のすべての子孫にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="d532d-106">This example also uses the `phone` descendant axis property to access all descendants named `phone` that are contained in the `contacts` object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d532d-107">使用例</span><span class="sxs-lookup"><span data-stu-id="d532d-107">Example</span></span>  
 [!code-vb[VbXMLSamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#31)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="d532d-108">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="d532d-108">Compile the code</span></span>  
 <span data-ttu-id="d532d-109">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d532d-109">This example requires:</span></span>  
  
- <span data-ttu-id="d532d-110"><xref:System.Xml.Linq> 名前空間への参照</span><span class="sxs-lookup"><span data-stu-id="d532d-110">A reference to the <xref:System.Xml.Linq> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d532d-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="d532d-111">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>
- [<span data-ttu-id="d532d-112">XML 子孫軸プロパティ</span><span class="sxs-lookup"><span data-stu-id="d532d-112">XML Descendant Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)
- [<span data-ttu-id="d532d-113">XML Value プロパティ</span><span class="sxs-lookup"><span data-stu-id="d532d-113">XML Value Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [<span data-ttu-id="d532d-114">Visual Basic での XML へのアクセス</span><span class="sxs-lookup"><span data-stu-id="d532d-114">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [<span data-ttu-id="d532d-115">XML</span><span class="sxs-lookup"><span data-stu-id="d532d-115">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
