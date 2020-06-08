---
title: '方法: タスクから値を返す'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to return a value
ms.assetid: c4bc0f44-eba2-4e96-9e03-1cc787461e61
ms.openlocfilehash: 144d004d697b84a011cedafc7d07b679ef8852c3
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288148"
---
# <a name="how-to-return-a-value-from-a-task"></a><span data-ttu-id="ad429-102">方法: タスクから値を返す</span><span class="sxs-lookup"><span data-stu-id="ad429-102">How to: Return a Value from a Task</span></span>
<span data-ttu-id="ad429-103">この例では、<xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> の型を使用して <xref:System.Threading.Tasks.Task%601.Result%2A> プロパティから値を返す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ad429-103">This example shows how to use the <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> type to return a value from the <xref:System.Threading.Tasks.Task%601.Result%2A> property.</span></span> <span data-ttu-id="ad429-104">C:\Users\Public\Pictures\Sample Pictures\ ディレクトリが存在している必要があり、それがファイルを含んでいる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad429-104">It requires that the C:\Users\Public\Pictures\Sample Pictures\ directory exists, and that it contains files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad429-105">例</span><span class="sxs-lookup"><span data-stu-id="ad429-105">Example</span></span>  
 [!code-csharp[TPL#10](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/returnavalue10.cs#10)]
 [!code-vb[TPL#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/10_returnavalue.vb#10)]  
  
 <span data-ttu-id="ad429-106"><xref:System.Threading.Tasks.Task%601.Result%2A> プロパティは、タスクが終了するまで呼び出し元のスレッドをブロックします。</span><span class="sxs-lookup"><span data-stu-id="ad429-106">The <xref:System.Threading.Tasks.Task%601.Result%2A> property blocks the calling thread until the task finishes.</span></span>  
  
 <span data-ttu-id="ad429-107">1 つの <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> の結果を継続タスクに渡す方法を確認するには、「[継続タスクを使用したタスクの連結](chaining-tasks-by-using-continuation-tasks.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad429-107">To see how to pass the result of one <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> to a continuation task, see [Chaining Tasks by Using Continuation Tasks](chaining-tasks-by-using-continuation-tasks.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad429-108">参照</span><span class="sxs-lookup"><span data-stu-id="ad429-108">See also</span></span>

- [<span data-ttu-id="ad429-109">タスク ベースの非同期プログラミング</span><span class="sxs-lookup"><span data-stu-id="ad429-109">Task-based Asynchronous Programming</span></span>](task-based-asynchronous-programming.md)
- [<span data-ttu-id="ad429-110">PLINQ および TPL のラムダ式</span><span class="sxs-lookup"><span data-stu-id="ad429-110">Lambda Expressions in PLINQ and TPL</span></span>](lambda-expressions-in-plinq-and-tpl.md)
