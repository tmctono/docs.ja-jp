---
title: '方法: 文字列内を検索する'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], finding
- strings [Visual Basic], searching
- examples [Visual Basic], strings
ms.assetid: ae4c79e0-08ea-489f-bdb2-5eb6d355f284
ms.openlocfilehash: 655f746e4e496e1935afcd2a9f9fe36d9e3a2564
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75348419"
---
# <a name="how-to-search-within-a-string-visual-basic"></a><span data-ttu-id="958fc-102">方法: 文字列内を検索する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="958fc-102">How to: search within a string (Visual Basic)</span></span>

<span data-ttu-id="958fc-103">この記事では、Visual Basic 内の文字列内で検索する方法の例を示します。</span><span class="sxs-lookup"><span data-stu-id="958fc-103">This article shows an example of how to search within a string in Visual Basic.</span></span>

## <a name="example"></a><span data-ttu-id="958fc-104">使用例</span><span class="sxs-lookup"><span data-stu-id="958fc-104">Example</span></span>

<span data-ttu-id="958fc-105">この例では、<xref:System.String> オブジェクトの <xref:System.String.IndexOf%2A> メソッドを呼び出して、部分文字列が最初に見つかった位置のインデックスを報告します。</span><span class="sxs-lookup"><span data-stu-id="958fc-105">This example calls the <xref:System.String.IndexOf%2A> method on a <xref:System.String> object to report the index of the first occurrence of a substring:</span></span>

 [!code-vb[VbVbalrStrings#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#71)]

## <a name="robust-programming"></a><span data-ttu-id="958fc-106">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="958fc-106">Robust programming</span></span>

<span data-ttu-id="958fc-107"><xref:System.String.IndexOf%2A> メソッドは、最初に見つかった部分文字列の最初の文字の位置を返します。</span><span class="sxs-lookup"><span data-stu-id="958fc-107">The <xref:System.String.IndexOf%2A> method returns the location of the first character of the first occurrence of the substring.</span></span> <span data-ttu-id="958fc-108">インデックスは0から始まる値です。つまり、文字列の最初の文字のインデックスは0になります。</span><span class="sxs-lookup"><span data-stu-id="958fc-108">The index is 0-based, which means the first character of a string has an index of 0.</span></span>

<span data-ttu-id="958fc-109"><xref:System.String.IndexOf%2A> が部分文字列を見つけられなかった場合は、-1 を返します。</span><span class="sxs-lookup"><span data-stu-id="958fc-109">If <xref:System.String.IndexOf%2A> does not find the substring, it returns -1.</span></span>

<span data-ttu-id="958fc-110"><xref:System.String.IndexOf%2A> メソッドでは、大文字と小文字が区別され、現在のカルチャが使用されます。</span><span class="sxs-lookup"><span data-stu-id="958fc-110">The <xref:System.String.IndexOf%2A> method is case-sensitive and uses the current culture.</span></span>

<span data-ttu-id="958fc-111">最適なエラーに制御するために文字列の検索をする可能性があります、`Try`のブロックを[Try...Catch...Finally ステートメント](../../../language-reference/statements/try-catch-finally-statement.md)構築します。</span><span class="sxs-lookup"><span data-stu-id="958fc-111">For optimal error control, you might want to enclose the string search in the `Try` block of a [Try...Catch...Finally Statement](../../../language-reference/statements/try-catch-finally-statement.md) construction.</span></span>

## <a name="see-also"></a><span data-ttu-id="958fc-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="958fc-112">See also</span></span>

- <xref:System.String.IndexOf%2A>
- [<span data-ttu-id="958fc-113">Try...Catch...Finally ステートメント</span><span class="sxs-lookup"><span data-stu-id="958fc-113">Try...Catch...Finally Statement</span></span>](../../../language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="958fc-114">Visual Basic の文字列の概要</span><span class="sxs-lookup"><span data-stu-id="958fc-114">Introduction to Strings in Visual Basic</span></span>](introduction-to-strings.md)
- [<span data-ttu-id="958fc-115">文字列</span><span class="sxs-lookup"><span data-stu-id="958fc-115">Strings</span></span>](index.md)
