---
title: '方法: 文字列 (Visual Basic) 内の検索'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], finding
- strings [Visual Basic], searching
- examples [Visual Basic], strings
ms.assetid: ae4c79e0-08ea-489f-bdb2-5eb6d355f284
ms.openlocfilehash: c150299efe07809d0d33edf882771f552c3e5b63
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56982012"
---
# <a name="how-to-search-within-a-string-visual-basic"></a><span data-ttu-id="d7701-102">方法: 文字列 (Visual Basic) 内の検索</span><span class="sxs-lookup"><span data-stu-id="d7701-102">How to: Search Within a String (Visual Basic)</span></span>
<span data-ttu-id="d7701-103">この例では、<xref:System.String.IndexOf%2A>メソッドを<xref:System.String>部分文字列の最初に見つかった位置のインデックスを報告するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d7701-103">This example calls the <xref:System.String.IndexOf%2A> method on a <xref:System.String> object to report the index of the first occurrence of a substring.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7701-104">例</span><span class="sxs-lookup"><span data-stu-id="d7701-104">Example</span></span>  
 [!code-vb[VbVbalrStrings#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d7701-105">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="d7701-105">Compiling the Code</span></span>  
 <span data-ttu-id="d7701-106">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d7701-106">This example requires:</span></span>  
  
-   <span data-ttu-id="d7701-107">`Imports`ステートメントの指定、<xref:System>名前空間。</span><span class="sxs-lookup"><span data-stu-id="d7701-107">An `Imports` statement specifying the <xref:System> namespace.</span></span> <span data-ttu-id="d7701-108">詳細については、「[Imports ステートメント (.NET 名前空間および型)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7701-108">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="d7701-109">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="d7701-109">Robust Programming</span></span>  
 <span data-ttu-id="d7701-110"><xref:System.String.IndexOf%2A>メソッドは、最初に見つかった部分文字列の最初の文字の位置を報告します。</span><span class="sxs-lookup"><span data-stu-id="d7701-110">The <xref:System.String.IndexOf%2A> method reports the location of the first character of the first occurrence of the substring.</span></span> <span data-ttu-id="d7701-111">インデックスには文字列の最初の文字がインデックス 0 のことを意味する 0 から始まります。</span><span class="sxs-lookup"><span data-stu-id="d7701-111">The index is 0-based, which means the first character of a string has an index of 0.</span></span>  
  
 <span data-ttu-id="d7701-112">場合<xref:System.String.IndexOf%2A>、部分文字列が見つからない-1 を返します。</span><span class="sxs-lookup"><span data-stu-id="d7701-112">If <xref:System.String.IndexOf%2A> does not find the substring, it returns -1.</span></span>  
  
 <span data-ttu-id="d7701-113"><xref:System.String.IndexOf%2A>メソッドは大文字であり、現在のカルチャを使用します。</span><span class="sxs-lookup"><span data-stu-id="d7701-113">The <xref:System.String.IndexOf%2A> method is case-sensitive and uses the current culture.</span></span>  
  
 <span data-ttu-id="d7701-114">最適なエラーに制御するために文字列の検索をする可能性があります、`Try`のブロックを[お試しください.キャッチしてください.Finally ステートメント](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)構築します。</span><span class="sxs-lookup"><span data-stu-id="d7701-114">For optimal error control, you might want to enclose the string search in the `Try` block of a [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) construction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7701-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="d7701-115">See also</span></span>
- <xref:System.String.IndexOf%2A>
- [<span data-ttu-id="d7701-116">Try...Catch...Finally ステートメント</span><span class="sxs-lookup"><span data-stu-id="d7701-116">Try...Catch...Finally Statement</span></span>](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="d7701-117">Visual Basic の文字列の概要</span><span class="sxs-lookup"><span data-stu-id="d7701-117">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
- [<span data-ttu-id="d7701-118">文字列</span><span class="sxs-lookup"><span data-stu-id="d7701-118">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)
