---
title: '方法: アクセスの XML 子孫要素 (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
ms.openlocfilehash: 008fd599e527ad4a8d483d2468a57ece1d2b4bdc
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64598599"
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a><span data-ttu-id="ae4c5-102">方法: アクセスの XML 子孫要素 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ae4c5-102">How to: Access XML Descendant Elements (Visual Basic)</span></span>
<span data-ttu-id="ae4c5-103">この例では、descendant 軸のプロパティを使用して、指定した名前を持ち、XML 要素に含まれるすべての XML 要素にアクセスする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ae4c5-103">This example shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under an XML element.</span></span> <span data-ttu-id="ae4c5-104">具体的を使用して、`Value`プロパティをコレクション内の最初の要素の値を取得、 `name` descendant 軸のプロパティを返します。</span><span class="sxs-lookup"><span data-stu-id="ae4c5-104">In particular, it uses the `Value` property to get the value of the first element in the collection that the `name` descendant axis property returns.</span></span> <span data-ttu-id="ae4c5-105">`name`子孫軸プロパティという名前のすべての要素を取得する`name`に格納されている、`contacts`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ae4c5-105">The `name` descendant axis property gets all elements named `name` that are contained in the `contacts` object.</span></span> <span data-ttu-id="ae4c5-106">またこの例では、`phone`という名前のすべての子孫にアクセスする子孫軸プロパティ`phone`に格納されている、`contacts`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ae4c5-106">This example also uses the `phone` descendant axis property to access all descendants named `phone` that are contained in the `contacts` object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae4c5-107">例</span><span class="sxs-lookup"><span data-stu-id="ae4c5-107">Example</span></span>  
 [!code-vb[VbXMLSamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ae4c5-108">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="ae4c5-108">Compiling the Code</span></span>  
 <span data-ttu-id="ae4c5-109">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ae4c5-109">This example requires:</span></span>  
  
- <span data-ttu-id="ae4c5-110"><xref:System.Xml.Linq> 名前空間への参照</span><span class="sxs-lookup"><span data-stu-id="ae4c5-110">A reference to the <xref:System.Xml.Linq> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae4c5-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="ae4c5-111">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>
- [<span data-ttu-id="ae4c5-112">XML 子孫軸プロパティ</span><span class="sxs-lookup"><span data-stu-id="ae4c5-112">XML Descendant Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)
- [<span data-ttu-id="ae4c5-113">XML Value プロパティ</span><span class="sxs-lookup"><span data-stu-id="ae4c5-113">XML Value Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [<span data-ttu-id="ae4c5-114">Visual Basic での XML へのアクセス</span><span class="sxs-lookup"><span data-stu-id="ae4c5-114">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [<span data-ttu-id="ae4c5-115">XML</span><span class="sxs-lookup"><span data-stu-id="ae4c5-115">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
