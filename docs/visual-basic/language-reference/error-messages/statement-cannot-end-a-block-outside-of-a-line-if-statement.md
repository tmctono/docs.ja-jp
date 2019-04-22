---
title: If ステートメント行の外側でステートメント ブロックを終了することはできません。
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: 85573099ec0a3f8a23c17bdf384c4c105f9157df
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "58825795"
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-if-statement"></a><span data-ttu-id="781e7-102">If ステートメント行の外側でステートメント ブロックを終了することはできません。</span><span class="sxs-lookup"><span data-stu-id="781e7-102">Statement cannot end a block outside of a line 'If' statement</span></span>
<span data-ttu-id="781e7-103">単一行`If`ステートメントには、コロン (:) のうちの 1 つで区切られた複数のステートメントが含まれています、`End`単一行の外側のコントロール ブロックのステートメント`If`します。</span><span class="sxs-lookup"><span data-stu-id="781e7-103">A single-line `If` statement contains several statements separated by colons (:), one of which is an `End` statement for a control block outside the single-line `If`.</span></span> <span data-ttu-id="781e7-104">単一行`If`ステートメントは使用しないでください、`End If`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="781e7-104">Single-line `If` statements do not use the `End If` statement.</span></span>  
  
 <span data-ttu-id="781e7-105">**エラー ID:** BC32005</span><span class="sxs-lookup"><span data-stu-id="781e7-105">**Error ID:** BC32005</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="781e7-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="781e7-106">To correct this error</span></span>  
  
-   <span data-ttu-id="781e7-107">単一行を移動`If`ステートメントを含むコントロール ブロックの外側、`End If`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="781e7-107">Move the single-line `If` statement outside the control block that contains the `End If` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="781e7-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="781e7-108">See also</span></span>

- [<span data-ttu-id="781e7-109">If...Then...Else ステートメント</span><span class="sxs-lookup"><span data-stu-id="781e7-109">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
