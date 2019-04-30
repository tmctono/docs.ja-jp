---
title: 0 から始まる文字列アクセスとVisual Basic における文字列の 1 から始まるアクセス
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
ms.openlocfilehash: a6ceb10d4a3cb9463551d8c85375ddbbb607ffdc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62024457"
---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a><span data-ttu-id="5a11f-102">0 から始まる文字列アクセスとVisual Basic における文字列の 1 から始まるアクセス</span><span class="sxs-lookup"><span data-stu-id="5a11f-102">Zero-based vs. One-based String Access in Visual Basic</span></span>
<span data-ttu-id="5a11f-103">このトピックでどのように Visual Basic、および[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]文字列内の文字へのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="5a11f-103">This topic compares how Visual Basic and the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] provide access to the characters in a string.</span></span> <span data-ttu-id="5a11f-104">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Visual Basic では、関数によって、0 から始まると 1 つベースのアクセスは常に、文字列の文字に 0 から始まるへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="5a11f-104">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] always provides zero-based access to the characters in a string, whereas Visual Basic provides zero-based and one-based access, depending on the function.</span></span>  
  
## <a name="one-based"></a><span data-ttu-id="5a11f-105">1 から始まる</span><span class="sxs-lookup"><span data-stu-id="5a11f-105">One-Based</span></span>  
 <span data-ttu-id="5a11f-106">1 から始まる Visual Basic の関数の例は、検討してください、`Mid`関数。</span><span class="sxs-lookup"><span data-stu-id="5a11f-106">For an example of a one-based Visual Basic function, consider the `Mid` function.</span></span> <span data-ttu-id="5a11f-107">これは、位置 1 から始まる、部分文字列を開始する文字位置を示す引数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="5a11f-107">It takes an argument that indicates the character position at which the substring will start, starting with position 1.</span></span> <span data-ttu-id="5a11f-108">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Substring%2A?displayProperty=nameWithType>メソッドは位置の 0 から始まるの部分文字列を開始するには、文字列内の文字のインデックスを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="5a11f-108">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Substring%2A?displayProperty=nameWithType> method takes an index of the character in the string at which the substring is to start, starting with position 0.</span></span> <span data-ttu-id="5a11f-109">したがって、"ABCDE"文字列がある場合、個々 の文字の番号付けは 1,2,3,4,5 で使用するため、`Mid`関数が 0,1,2,3,4 で使用するため、<xref:System.String.Substring%2A?displayProperty=nameWithType>メソッド。</span><span class="sxs-lookup"><span data-stu-id="5a11f-109">Thus, if you have a string "ABCDE", the individual characters are numbered 1,2,3,4,5 for use with the `Mid` function, but 0,1,2,3,4 for use with the <xref:System.String.Substring%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="zero-based"></a><span data-ttu-id="5a11f-110">0 から始まる</span><span class="sxs-lookup"><span data-stu-id="5a11f-110">Zero-Based</span></span>  
 <span data-ttu-id="5a11f-111">0 から始まる Visual Basic の関数の例は、検討してください、`Split`関数。</span><span class="sxs-lookup"><span data-stu-id="5a11f-111">For an example of a zero-based Visual Basic function, consider the `Split` function.</span></span> <span data-ttu-id="5a11f-112">文字列を分割し、これらの部分文字列を含む配列を返します。</span><span class="sxs-lookup"><span data-stu-id="5a11f-112">It splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="5a11f-113">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Split%2A?displayProperty=nameWithType>もメソッドは文字列を分割し、部分文字列を含む配列を返します。</span><span class="sxs-lookup"><span data-stu-id="5a11f-113">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Split%2A?displayProperty=nameWithType> method also splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="5a11f-114">`Split`関数と<xref:System.String.Split%2A>メソッドの戻り値[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]配列、する必要がある 0 から始まる。</span><span class="sxs-lookup"><span data-stu-id="5a11f-114">Because the `Split` function and <xref:System.String.Split%2A> method return [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] arrays, they must be zero-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a11f-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a11f-115">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- <xref:Microsoft.VisualBasic.Strings.Split%2A>
- <xref:System.String.Substring%2A>
- <xref:System.String.Split%2A>
- [<span data-ttu-id="5a11f-116">Visual Basic の文字列の概要</span><span class="sxs-lookup"><span data-stu-id="5a11f-116">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
