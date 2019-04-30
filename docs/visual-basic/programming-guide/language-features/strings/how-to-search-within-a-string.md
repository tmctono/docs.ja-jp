---
title: '方法: 文字列 (Visual Basic) 内の検索'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], finding
- strings [Visual Basic], searching
- examples [Visual Basic], strings
ms.assetid: ae4c79e0-08ea-489f-bdb2-5eb6d355f284
ms.openlocfilehash: b690aa78a2cf07b0db5bdd28d7d71ed4a79fbf61
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032085"
---
# <a name="how-to-search-within-a-string-visual-basic"></a><span data-ttu-id="e55e8-102">方法: 文字列 (Visual Basic) 内の検索</span><span class="sxs-lookup"><span data-stu-id="e55e8-102">How to: Search Within a String (Visual Basic)</span></span>
<span data-ttu-id="e55e8-103">この例では、<xref:System.String.IndexOf%2A>メソッドを<xref:System.String>部分文字列の最初に見つかった位置のインデックスを報告するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="e55e8-103">This example calls the <xref:System.String.IndexOf%2A> method on a <xref:System.String> object to report the index of the first occurrence of a substring.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e55e8-104">例</span><span class="sxs-lookup"><span data-stu-id="e55e8-104">Example</span></span>  
 [!code-vb[VbVbalrStrings#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e55e8-105">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="e55e8-105">Compiling the Code</span></span>  
 <span data-ttu-id="e55e8-106">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e55e8-106">This example requires:</span></span>  
  
- <span data-ttu-id="e55e8-107">`Imports`ステートメントの指定、<xref:System>名前空間。</span><span class="sxs-lookup"><span data-stu-id="e55e8-107">An `Imports` statement specifying the <xref:System> namespace.</span></span> <span data-ttu-id="e55e8-108">詳細については、「[Imports ステートメント (.NET 名前空間および型)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e55e8-108">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="e55e8-109">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="e55e8-109">Robust Programming</span></span>  
 <span data-ttu-id="e55e8-110"><xref:System.String.IndexOf%2A>メソッドは、最初に見つかった部分文字列の最初の文字の位置を報告します。</span><span class="sxs-lookup"><span data-stu-id="e55e8-110">The <xref:System.String.IndexOf%2A> method reports the location of the first character of the first occurrence of the substring.</span></span> <span data-ttu-id="e55e8-111">インデックスには文字列の最初の文字がインデックス 0 のことを意味する 0 から始まります。</span><span class="sxs-lookup"><span data-stu-id="e55e8-111">The index is 0-based, which means the first character of a string has an index of 0.</span></span>  
  
 <span data-ttu-id="e55e8-112">場合<xref:System.String.IndexOf%2A>、部分文字列が見つからない-1 を返します。</span><span class="sxs-lookup"><span data-stu-id="e55e8-112">If <xref:System.String.IndexOf%2A> does not find the substring, it returns -1.</span></span>  
  
 <span data-ttu-id="e55e8-113"><xref:System.String.IndexOf%2A>メソッドは大文字であり、現在のカルチャを使用します。</span><span class="sxs-lookup"><span data-stu-id="e55e8-113">The <xref:System.String.IndexOf%2A> method is case-sensitive and uses the current culture.</span></span>  
  
 <span data-ttu-id="e55e8-114">最適なエラーに制御するために文字列の検索をする可能性があります、`Try`のブロックを[お試しください.キャッチしてください.Finally ステートメント](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)構築します。</span><span class="sxs-lookup"><span data-stu-id="e55e8-114">For optimal error control, you might want to enclose the string search in the `Try` block of a [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) construction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e55e8-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="e55e8-115">See also</span></span>

- <xref:System.String.IndexOf%2A>
- [<span data-ttu-id="e55e8-116">Try...Catch...Finally ステートメント</span><span class="sxs-lookup"><span data-stu-id="e55e8-116">Try...Catch...Finally Statement</span></span>](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="e55e8-117">Visual Basic の文字列の概要</span><span class="sxs-lookup"><span data-stu-id="e55e8-117">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
- [<span data-ttu-id="e55e8-118">文字列</span><span class="sxs-lookup"><span data-stu-id="e55e8-118">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)
