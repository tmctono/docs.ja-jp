---
title: "'Class' ステートメントの終わりには、対応する 'End Class' を指定しなければなりません。"
ms.date: 07/20/2015
f1_keywords:
- vbc30481
- bc30481
helpviewer_keywords:
- BC30481
ms.assetid: 583f3029-bc3a-4e06-866f-92dbecc46f19
ms.openlocfilehash: 01c231f577d21028e9ef92f37c7ac5f7f1fe2aa3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415389"
---
# <a name="class-statement-must-end-with-a-matching-end-class"></a><span data-ttu-id="dffba-102">'Class' ステートメントの終わりには、対応する 'End Class' を指定しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="dffba-102">'Class' statement must end with a matching 'End Class'</span></span>
<span data-ttu-id="dffba-103">`Class` は `Class` ブロックを開始するために使用します。ブロックの先頭にのみ指定でき、対応する`End Class` ステートメントでブロックを終えます。</span><span class="sxs-lookup"><span data-stu-id="dffba-103">`Class` is used to initiate a `Class` block; hence it can only appear at the beginning of the block, with a matching `End Class` statement ending the block.</span></span> <span data-ttu-id="dffba-104">`Class` ステートメントが重複しているか、`Class` ブロックの最後に `End Class` が使用されませんでした。</span><span class="sxs-lookup"><span data-stu-id="dffba-104">Either you have a redundant `Class` statement, or you have not ended your `Class` block with `End Class`.</span></span>  
  
 <span data-ttu-id="dffba-105">**エラー ID:** BC30481</span><span class="sxs-lookup"><span data-stu-id="dffba-105">**Error ID:** BC30481</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="dffba-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="dffba-106">To correct this error</span></span>  
  
- <span data-ttu-id="dffba-107">不要な `Class` ステートメントを見つけて削除します。</span><span class="sxs-lookup"><span data-stu-id="dffba-107">Locate and remove the unnecessary `Class` statement.</span></span>  
  
- <span data-ttu-id="dffba-108">一致する `End Class` で `Class` ブロックを終了します。</span><span class="sxs-lookup"><span data-stu-id="dffba-108">Conclude the `Class` block with a matching `End Class`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dffba-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="dffba-109">See also</span></span>

- [<span data-ttu-id="dffba-110">End \<keyword> ステートメント</span><span class="sxs-lookup"><span data-stu-id="dffba-110">End \<keyword> Statement</span></span>](../statements/end-keyword-statement.md)
- [<span data-ttu-id="dffba-111">Class ステートメント</span><span class="sxs-lookup"><span data-stu-id="dffba-111">Class Statement</span></span>](../statements/class-statement.md)
