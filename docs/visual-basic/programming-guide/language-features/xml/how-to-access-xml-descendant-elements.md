---
title: '方法: XML 子孫要素にアクセスする'
ms.date: 07/20/2015
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
ms.openlocfilehash: 03c403aa3c187b0b9d2006104eccaa1f9cd8aec5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392637"
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a><span data-ttu-id="4713d-102">方法: XML 子孫要素にアクセスする (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4713d-102">How to: Access XML Descendant Elements (Visual Basic)</span></span>
<span data-ttu-id="4713d-103">この例では、子孫軸プロパティを使用して、指定した名前を持ち、XML 要素の下に含まれているすべての XML 要素にアクセスする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="4713d-103">This example shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under an XML element.</span></span> <span data-ttu-id="4713d-104">特に、`Value` プロパティを使用して、`name` 子孫軸プロパティによって返されるコレクション内の最初の要素の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="4713d-104">In particular, it uses the `Value` property to get the value of the first element in the collection that the `name` descendant axis property returns.</span></span> <span data-ttu-id="4713d-105">`name` 子孫軸プロパティでは、`contacts` オブジェクトに含まれる `name` という名前のすべての要素を取得します。</span><span class="sxs-lookup"><span data-stu-id="4713d-105">The `name` descendant axis property gets all elements named `name` that are contained in the `contacts` object.</span></span> <span data-ttu-id="4713d-106">また、この例では、`phone` 子孫軸プロパティを使用して、`contacts` オブジェクトに含まれている `phone` という名前のすべての子孫にアクセスしています。</span><span class="sxs-lookup"><span data-stu-id="4713d-106">This example also uses the `phone` descendant axis property to access all descendants named `phone` that are contained in the `contacts` object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4713d-107">例</span><span class="sxs-lookup"><span data-stu-id="4713d-107">Example</span></span>  
 [!code-vb[VbXMLSamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#31)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="4713d-108">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="4713d-108">Compile the code</span></span>  
 <span data-ttu-id="4713d-109">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4713d-109">This example requires:</span></span>  
  
- <span data-ttu-id="4713d-110"><xref:System.Xml.Linq> 名前空間への参照</span><span class="sxs-lookup"><span data-stu-id="4713d-110">A reference to the <xref:System.Xml.Linq> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4713d-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="4713d-111">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>
- [<span data-ttu-id="4713d-112">XML 子孫軸プロパティ</span><span class="sxs-lookup"><span data-stu-id="4713d-112">XML Descendant Axis Property</span></span>](../../../language-reference/xml-axis/xml-descendant-axis-property.md)
- [<span data-ttu-id="4713d-113">XML Value プロパティ</span><span class="sxs-lookup"><span data-stu-id="4713d-113">XML Value Property</span></span>](../../../language-reference/xml-axis/xml-value-property.md)
- [<span data-ttu-id="4713d-114">Visual Basic での XML へのアクセス</span><span class="sxs-lookup"><span data-stu-id="4713d-114">Accessing XML in Visual Basic</span></span>](accessing-xml.md)
- [<span data-ttu-id="4713d-115">XML</span><span class="sxs-lookup"><span data-stu-id="4713d-115">XML</span></span>](index.md)
