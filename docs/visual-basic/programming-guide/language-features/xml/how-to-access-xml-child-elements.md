---
title: '方法: アクセスの XML 子要素 (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 6689eb36-c471-469f-a82d-099ab8197b25
ms.openlocfilehash: 3c00166e471b7c6d69bd7f6fc3bda87b651d7d46
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64598664"
---
# <a name="how-to-access-xml-child-elements-visual-basic"></a><span data-ttu-id="b6545-102">方法: アクセスの XML 子要素 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b6545-102">How to: Access XML Child Elements (Visual Basic)</span></span>
<span data-ttu-id="b6545-103">この例では、軸のプロパティを XML 要素で指定した名前を持つすべての XML 子要素にアクセスする子を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b6545-103">This example shows how to use a child axis property to access all XML child elements that have a specified name in an XML element.</span></span> <span data-ttu-id="b6545-104">具体的を使用して、<xref:System.Xml.Linq.XElement.Value%2A>プロパティをコレクション内の最初の要素の値を取得、`name`子軸プロパティを返します。</span><span class="sxs-lookup"><span data-stu-id="b6545-104">In particular, it uses the <xref:System.Xml.Linq.XElement.Value%2A> property to get the value of the first element in the collection that the `name` child axis property returns.</span></span> <span data-ttu-id="b6545-105">`name`という名前のすべての子要素を取得する子軸プロパティ`phone`で、`contact`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="b6545-105">The `name` child axis property gets all child elements named `phone` in the `contact` object.</span></span> <span data-ttu-id="b6545-106">またこの例では、`phone`という名前のすべての子要素にアクセスする子軸プロパティ`phone`に格納されている、`contact`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="b6545-106">This example also uses the `phone` child axis property to access all child elements named `phone` that are contained in the `contact` object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6545-107">例</span><span class="sxs-lookup"><span data-stu-id="b6545-107">Example</span></span>  
 [!code-vb[VbXMLSamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b6545-108">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="b6545-108">Compiling the Code</span></span>  
 <span data-ttu-id="b6545-109">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b6545-109">This example requires:</span></span>  
  
- <span data-ttu-id="b6545-110"><xref:System.Xml.Linq> 名前空間への参照</span><span class="sxs-lookup"><span data-stu-id="b6545-110">A reference to the <xref:System.Xml.Linq> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6545-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="b6545-111">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>
- [<span data-ttu-id="b6545-112">XML 子軸プロパティ</span><span class="sxs-lookup"><span data-stu-id="b6545-112">XML Child Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)
- [<span data-ttu-id="b6545-113">XML Value プロパティ</span><span class="sxs-lookup"><span data-stu-id="b6545-113">XML Value Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [<span data-ttu-id="b6545-114">Visual Basic での XML へのアクセス</span><span class="sxs-lookup"><span data-stu-id="b6545-114">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [<span data-ttu-id="b6545-115">XML</span><span class="sxs-lookup"><span data-stu-id="b6545-115">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
