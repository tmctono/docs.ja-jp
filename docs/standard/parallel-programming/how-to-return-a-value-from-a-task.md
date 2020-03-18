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
ms.openlocfilehash: 495f68114bfe960b8182be4ab76b72043b2d0cc7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "73141673"
---
# <a name="how-to-return-a-value-from-a-task"></a><span data-ttu-id="d6403-102">方法: タスクから値を返す</span><span class="sxs-lookup"><span data-stu-id="d6403-102">How to: Return a Value from a Task</span></span>
<span data-ttu-id="d6403-103">この例では、<xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> の型を使用して <xref:System.Threading.Tasks.Task%601.Result%2A> プロパティから値を返す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d6403-103">This example shows how to use the <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> type to return a value from the <xref:System.Threading.Tasks.Task%601.Result%2A> property.</span></span> <span data-ttu-id="d6403-104">C:\Users\Public\Pictures\Sample Pictures\ ディレクトリが存在している必要があり、それがファイルを含んでいる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6403-104">It requires that the C:\Users\Public\Pictures\Sample Pictures\ directory exists, and that it contains files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6403-105">例</span><span class="sxs-lookup"><span data-stu-id="d6403-105">Example</span></span>  
 [!code-csharp[TPL#10](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/returnavalue10.cs#10)]
 [!code-vb[TPL#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/10_returnavalue.vb#10)]  
  
 <span data-ttu-id="d6403-106"><xref:System.Threading.Tasks.Task%601.Result%2A> プロパティは、タスクが終了するまで呼び出し元のスレッドをブロックします。</span><span class="sxs-lookup"><span data-stu-id="d6403-106">The <xref:System.Threading.Tasks.Task%601.Result%2A> property blocks the calling thread until the task finishes.</span></span>  
  
 <span data-ttu-id="d6403-107">1 つの <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> の結果を継続タスクに渡す方法を確認するには、「[継続タスクを使用したタスクの連結](../../../docs/standard/parallel-programming/chaining-tasks-by-using-continuation-tasks.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6403-107">To see how to pass the result of one <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> to a continuation task, see [Chaining Tasks by Using Continuation Tasks](../../../docs/standard/parallel-programming/chaining-tasks-by-using-continuation-tasks.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6403-108">参照</span><span class="sxs-lookup"><span data-stu-id="d6403-108">See also</span></span>

- [<span data-ttu-id="d6403-109">タスク ベースの非同期プログラミング</span><span class="sxs-lookup"><span data-stu-id="d6403-109">Task-based Asynchronous Programming</span></span>](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
- [<span data-ttu-id="d6403-110">PLINQ および TPL のラムダ式</span><span class="sxs-lookup"><span data-stu-id="d6403-110">Lambda Expressions in PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
