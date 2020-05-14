---
title: If ステートメント行の外側でステートメント ブロックを終了することはできません。
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: 0e645ccf17d0aba702a576791622aa4e9b3dd5e0
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64593265"
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-if-statement"></a><span data-ttu-id="05515-102">If ステートメント行の外側でステートメント ブロックを終了することはできません。</span><span class="sxs-lookup"><span data-stu-id="05515-102">Statement cannot end a block outside of a line 'If' statement</span></span>
<span data-ttu-id="05515-103">単一行の `If` ステートメントにコロン (:) で区切られた複数のステートメントが含まれていて、そのうちの 1 つが、単一行の `If` の外側にある制御ブロックの `End` ステートメントです。</span><span class="sxs-lookup"><span data-stu-id="05515-103">A single-line `If` statement contains several statements separated by colons (:), one of which is an `End` statement for a control block outside the single-line `If`.</span></span> <span data-ttu-id="05515-104">単一行の `If` ステートメントで、`End If` ステートメントが使用されません。</span><span class="sxs-lookup"><span data-stu-id="05515-104">Single-line `If` statements do not use the `End If` statement.</span></span>  
  
 <span data-ttu-id="05515-105">**エラー ID:** BC32005</span><span class="sxs-lookup"><span data-stu-id="05515-105">**Error ID:** BC32005</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="05515-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="05515-106">To correct this error</span></span>  
  
- <span data-ttu-id="05515-107">単一行の `If` ステートメントを、`End If` ステートメントが含まれている制御ブロックの外側に移動します。</span><span class="sxs-lookup"><span data-stu-id="05515-107">Move the single-line `If` statement outside the control block that contains the `End If` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05515-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="05515-108">See also</span></span>

- [<span data-ttu-id="05515-109">If...Then...Else ステートメント</span><span class="sxs-lookup"><span data-stu-id="05515-109">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
