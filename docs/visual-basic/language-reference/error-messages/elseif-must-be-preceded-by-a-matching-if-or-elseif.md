---
title: "	'#Else' の前には、対応する '#If' または '#ElseIf' が必要です。"
ms.date: 07/20/2015
f1_keywords:
- vbc30014
- bc30014
helpviewer_keywords:
- BC30014
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
ms.openlocfilehash: fbb8ce974a618349bd4b5e7a2a25a165d91787a7
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58832256"
---
# <a name="elseif-must-be-preceded-by-a-matching-if-or-elseif"></a><span data-ttu-id="f1a8a-102">	'#Else' の前には、対応する '#If' または '#ElseIf' が必要です。</span><span class="sxs-lookup"><span data-stu-id="f1a8a-102">'#ElseIf' must be preceded by a matching '#If' or '#ElseIf'</span></span>
<span data-ttu-id="f1a8a-103">`#ElseIf` は条件付きコンパイル ディレクティブです。</span><span class="sxs-lookup"><span data-stu-id="f1a8a-103">`#ElseIf` is a conditional compilation directive.</span></span> <span data-ttu-id="f1a8a-104">`#ElseIf`句の前に、対応する`#If`または`#ElseIf`句が必要です。</span><span class="sxs-lookup"><span data-stu-id="f1a8a-104">An `#ElseIf` clause must be preceded by a matching `#If` or `#ElseIf` clause.</span></span>  
  
 <span data-ttu-id="f1a8a-105">**エラー ID:** BC30014</span><span class="sxs-lookup"><span data-stu-id="f1a8a-105">**Error ID:** BC30014</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f1a8a-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="f1a8a-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="f1a8a-107">先行する`#If`または`#ElseIf`と、この`#ElseIf`とが、間に条件付きコンパイル ブロックを挿入することによって分離されていないこと、または`#End If`句を間違った場所に記述したために分離されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f1a8a-107">Check that a preceding `#If` or `#ElseIf` has not been separated from this `#ElseIf` by an intervening conditional compilation block or an incorrectly placed `#End If`.</span></span>  
  
2.  <span data-ttu-id="f1a8a-108">`#ElseIf`の前に`#Else`ディレクティブがある場合は、その`#Else`を削除するか、`#ElseIf`に変更します。</span><span class="sxs-lookup"><span data-stu-id="f1a8a-108">If the `#ElseIf` is preceded by a `#Else` directive, either remove the `#Else` or change it to an `#ElseIf`.</span></span>  
  
3.  <span data-ttu-id="f1a8a-109">すべて問題ない場合は、条件付きコンパイル ブロックの先頭に `#If` ディレクティブを追加します。</span><span class="sxs-lookup"><span data-stu-id="f1a8a-109">If everything else is in order, add an `#If` directive to the beginning of the conditional compilation block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1a8a-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1a8a-110">See also</span></span>

- [<span data-ttu-id="f1a8a-111">#If...Then...#Else ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="f1a8a-111">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
