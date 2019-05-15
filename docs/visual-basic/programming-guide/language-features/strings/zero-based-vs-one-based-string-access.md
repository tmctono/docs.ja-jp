---
title: 0 から始まる文字列アクセスとVisual Basic における文字列の 1 から始まるアクセス
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
ms.openlocfilehash: cc8f286de41d7e44225e889e73ff3c7b1fdbd881
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591749"
---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a><span data-ttu-id="a56ea-102">0 から始まる文字列アクセスとVisual Basic における文字列の 1 から始まるアクセス</span><span class="sxs-lookup"><span data-stu-id="a56ea-102">Zero-based vs. One-based String Access in Visual Basic</span></span>
<span data-ttu-id="a56ea-103">このトピックでは、Visual Basic と .NET Framework の文字列の文字へのアクセスを提供する方法を比較します。</span><span class="sxs-lookup"><span data-stu-id="a56ea-103">This topic compares how Visual Basic and the .NET Framework provide access to the characters in a string.</span></span> <span data-ttu-id="a56ea-104">.NET Framework は、Visual Basic では、関数によって、0 から始まると 1 つベースのアクセスは常に、文字列の文字に 0 から始まるへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="a56ea-104">The .NET Framework always provides zero-based access to the characters in a string, whereas Visual Basic provides zero-based and one-based access, depending on the function.</span></span>  
  
## <a name="one-based"></a><span data-ttu-id="a56ea-105">1 から始まる</span><span class="sxs-lookup"><span data-stu-id="a56ea-105">One-Based</span></span>  
 <span data-ttu-id="a56ea-106">1 から始まる Visual Basic の関数の例は、検討してください、`Mid`関数。</span><span class="sxs-lookup"><span data-stu-id="a56ea-106">For an example of a one-based Visual Basic function, consider the `Mid` function.</span></span> <span data-ttu-id="a56ea-107">これは、位置 1 から始まる、部分文字列を開始する文字位置を示す引数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a56ea-107">It takes an argument that indicates the character position at which the substring will start, starting with position 1.</span></span> <span data-ttu-id="a56ea-108">.NET Framework<xref:System.String.Substring%2A?displayProperty=nameWithType>メソッドは位置の 0 から始まるの部分文字列を開始するには、文字列内の文字のインデックスを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a56ea-108">The .NET Framework <xref:System.String.Substring%2A?displayProperty=nameWithType> method takes an index of the character in the string at which the substring is to start, starting with position 0.</span></span> <span data-ttu-id="a56ea-109">したがって、"ABCDE"文字列がある場合、個々 の文字の番号付けは 1,2,3,4,5 で使用するため、`Mid`関数が 0,1,2,3,4 で使用するため、<xref:System.String.Substring%2A?displayProperty=nameWithType>メソッド。</span><span class="sxs-lookup"><span data-stu-id="a56ea-109">Thus, if you have a string "ABCDE", the individual characters are numbered 1,2,3,4,5 for use with the `Mid` function, but 0,1,2,3,4 for use with the <xref:System.String.Substring%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="zero-based"></a><span data-ttu-id="a56ea-110">0 から始まる</span><span class="sxs-lookup"><span data-stu-id="a56ea-110">Zero-Based</span></span>  
 <span data-ttu-id="a56ea-111">0 から始まる Visual Basic の関数の例は、検討してください、`Split`関数。</span><span class="sxs-lookup"><span data-stu-id="a56ea-111">For an example of a zero-based Visual Basic function, consider the `Split` function.</span></span> <span data-ttu-id="a56ea-112">文字列を分割し、これらの部分文字列を含む配列を返します。</span><span class="sxs-lookup"><span data-stu-id="a56ea-112">It splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="a56ea-113">.NET Framework<xref:System.String.Split%2A?displayProperty=nameWithType>もメソッドは文字列を分割し、部分文字列を含む配列を返します。</span><span class="sxs-lookup"><span data-stu-id="a56ea-113">The .NET Framework <xref:System.String.Split%2A?displayProperty=nameWithType> method also splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="a56ea-114">`Split`関数と<xref:System.String.Split%2A>メソッドは、.NET Framework の配列を返す、0 から始まる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a56ea-114">Because the `Split` function and <xref:System.String.Split%2A> method return .NET Framework arrays, they must be zero-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a56ea-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="a56ea-115">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- <xref:Microsoft.VisualBasic.Strings.Split%2A>
- <xref:System.String.Substring%2A>
- <xref:System.String.Split%2A>
- [<span data-ttu-id="a56ea-116">Visual Basic の文字列の概要</span><span class="sxs-lookup"><span data-stu-id="a56ea-116">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
