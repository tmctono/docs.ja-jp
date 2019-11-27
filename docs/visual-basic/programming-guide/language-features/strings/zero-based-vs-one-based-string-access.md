---
title: 0から始まる文字列アクセスと1から始まる文字列アクセス
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
ms.openlocfilehash: 97e60038bc7ec0f030939d0980b786bffebcfb9a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354300"
---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a><span data-ttu-id="c3b67-102">Visual Basic における文字列アクセスのインデックス番号</span><span class="sxs-lookup"><span data-stu-id="c3b67-102">Zero-based vs. One-based String Access in Visual Basic</span></span>
<span data-ttu-id="c3b67-103">このトピックでは、Visual Basic と .NET Framework が文字列内の文字へのアクセスを提供する方法を比較します。</span><span class="sxs-lookup"><span data-stu-id="c3b67-103">This topic compares how Visual Basic and the .NET Framework provide access to the characters in a string.</span></span> <span data-ttu-id="c3b67-104">.NET Framework は、文字列内の文字へのゼロベースのアクセスを常に提供します。一方、Visual Basic は、関数に応じて、0から始まる、1から始まるアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="c3b67-104">The .NET Framework always provides zero-based access to the characters in a string, whereas Visual Basic provides zero-based and one-based access, depending on the function.</span></span>  
  
## <a name="one-based"></a><span data-ttu-id="c3b67-105">1から始まる</span><span class="sxs-lookup"><span data-stu-id="c3b67-105">One-Based</span></span>  
 <span data-ttu-id="c3b67-106">1ベースの Visual Basic 関数の例については、`Mid` 関数を検討してください。</span><span class="sxs-lookup"><span data-stu-id="c3b67-106">For an example of a one-based Visual Basic function, consider the `Mid` function.</span></span> <span data-ttu-id="c3b67-107">位置1から始まる部分文字列の開始位置を示す引数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="c3b67-107">It takes an argument that indicates the character position at which the substring will start, starting with position 1.</span></span> <span data-ttu-id="c3b67-108">.NET Framework <xref:System.String.Substring%2A?displayProperty=nameWithType> メソッドは、位置0から開始して、部分文字列を開始する文字列内の文字のインデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="c3b67-108">The .NET Framework <xref:System.String.Substring%2A?displayProperty=nameWithType> method takes an index of the character in the string at which the substring is to start, starting with position 0.</span></span> <span data-ttu-id="c3b67-109">したがって、文字列 "ABCDE...Z" を使用している場合、個々の文字には、`Mid` 関数で使用するために1、2、3、4、5の番号が付けられますが、<xref:System.String.Substring%2A?displayProperty=nameWithType> メソッドで使用する場合は0、1、2、3、4になります。</span><span class="sxs-lookup"><span data-stu-id="c3b67-109">Thus, if you have a string "ABCDE", the individual characters are numbered 1,2,3,4,5 for use with the `Mid` function, but 0,1,2,3,4 for use with the <xref:System.String.Substring%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="zero-based"></a><span data-ttu-id="c3b67-110">0から始まる</span><span class="sxs-lookup"><span data-stu-id="c3b67-110">Zero-Based</span></span>  
 <span data-ttu-id="c3b67-111">0から始まる Visual Basic 関数の例については、`Split` 関数を検討してください。</span><span class="sxs-lookup"><span data-stu-id="c3b67-111">For an example of a zero-based Visual Basic function, consider the `Split` function.</span></span> <span data-ttu-id="c3b67-112">文字列を分割し、部分文字列を含む配列を返します。</span><span class="sxs-lookup"><span data-stu-id="c3b67-112">It splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="c3b67-113">また、.NET Framework <xref:System.String.Split%2A?displayProperty=nameWithType> メソッドは文字列を分割し、部分文字列を含む配列を返します。</span><span class="sxs-lookup"><span data-stu-id="c3b67-113">The .NET Framework <xref:System.String.Split%2A?displayProperty=nameWithType> method also splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="c3b67-114">`Split` 関数と <xref:System.String.Split%2A> メソッドは .NET Framework 配列を返すため、0から始まる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3b67-114">Because the `Split` function and <xref:System.String.Split%2A> method return .NET Framework arrays, they must be zero-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3b67-115">参照</span><span class="sxs-lookup"><span data-stu-id="c3b67-115">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- <xref:Microsoft.VisualBasic.Strings.Split%2A>
- <xref:System.String.Substring%2A>
- <xref:System.String.Split%2A>
- [<span data-ttu-id="c3b67-116">Visual Basic の文字列の概要</span><span class="sxs-lookup"><span data-stu-id="c3b67-116">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
