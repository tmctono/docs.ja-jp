---
title: 非同期アプリケーションの微調整
ms.date: 07/20/2015
ms.assetid: 4c3e7997-a95f-4fbe-a6ac-60ba042d30b9
ms.openlocfilehash: 6ad4f9a526e0497029ff8ddc3e93637a4f9acb00
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075435"
---
# <a name="fine-tuning-your-async-application-visual-basic"></a><span data-ttu-id="b91a0-102">非同期アプリケーションの微調整 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b91a0-102">Fine-Tuning Your Async Application (Visual Basic)</span></span>

<span data-ttu-id="b91a0-103"><xref:System.Threading.Tasks.Task> 型を使用できるメソッドとプロパティを使用して、非同期アプリケーションに精度と柔軟性を追加できます。</span><span class="sxs-lookup"><span data-stu-id="b91a0-103">You can add precision and flexibility to your async applications by using the methods and properties that the <xref:System.Threading.Tasks.Task> type makes available.</span></span> <span data-ttu-id="b91a0-104">このセクションのトピックでは <xref:System.Threading.CancellationToken> および `Task` などのような、重要な <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> メソッドおよび <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> の使用例を示します。</span><span class="sxs-lookup"><span data-stu-id="b91a0-104">The topics in this section show examples that use <xref:System.Threading.CancellationToken> and important `Task` methods such as <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="b91a0-105">`WhenAny` と `WhenAll` を使用すると、複数のタスクをより簡単に開始し、単一のタスクを監視して、その完了を待機できます。</span><span class="sxs-lookup"><span data-stu-id="b91a0-105">By using `WhenAny` and `WhenAll`, you can more easily start multiple tasks and await their completion by monitoring a single task.</span></span>  
  
- <span data-ttu-id="b91a0-106">`WhenAny` は、コレクションのいずれかのタスクが完了すると完了するタスクを返します。</span><span class="sxs-lookup"><span data-stu-id="b91a0-106">`WhenAny` returns a task that completes when any task in a collection is complete.</span></span>  
  
     <span data-ttu-id="b91a0-107">`WhenAny` を使う例については、「[完了後の残りの非同期タスクのキャンセル (Visual Basic)](cancel-remaining-async-tasks-after-one-is-complete.md)」および「[完了時での複数の同期タスクとプロセスの実行 (Visual Basic)](start-multiple-async-tasks-and-process-them-as-they-complete.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b91a0-107">For examples that use `WhenAny`, see  [Cancel Remaining Async Tasks after One Is Complete (Visual Basic)](cancel-remaining-async-tasks-after-one-is-complete.md)and [Start Multiple Async Tasks and Process Them As They Complete (Visual Basic)](start-multiple-async-tasks-and-process-them-as-they-complete.md).</span></span>  
  
- <span data-ttu-id="b91a0-108">`WhenAll` は、コレクションのすべてのタスクが完了すると完了するタスクを返します。</span><span class="sxs-lookup"><span data-stu-id="b91a0-108">`WhenAll` returns a task that completes when all tasks in a collection are complete.</span></span>  
  
     <span data-ttu-id="b91a0-109">詳細および `WhenAll` の使用例については、「[方法: Task.whenall を使用して非同期のチュートリアルを拡張する (Visual Basic)](how-to-extend-the-async-walkthrough-by-using-task-whenall.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b91a0-109">For more information and an example that uses `WhenAll`, see [How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>  
  
 <span data-ttu-id="b91a0-110">ここでは、次の例について説明します。</span><span class="sxs-lookup"><span data-stu-id="b91a0-110">This section includes the following examples.</span></span>  
  
- <span data-ttu-id="b91a0-111">[非同期タスクまたはタスクの一覧のキャンセル (Visual Basic)](cancel-an-async-task-or-a-list-of-tasks.md)</span><span class="sxs-lookup"><span data-stu-id="b91a0-111">[Cancel an Async Task or a List of Tasks (Visual Basic)](cancel-an-async-task-or-a-list-of-tasks.md).</span></span>  
  
- [<span data-ttu-id="b91a0-112">指定した時間の経過後の非同期タスクのキャンセル (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b91a0-112">Cancel Async Tasks after a Period of Time (Visual Basic)</span></span>](cancel-async-tasks-after-a-period-of-time.md)  
  
- [<span data-ttu-id="b91a0-113">完了後の残りの非同期タスクのキャンセル (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b91a0-113">Cancel Remaining Async Tasks after One Is Complete (Visual Basic)</span></span>](cancel-remaining-async-tasks-after-one-is-complete.md)  
  
- [<span data-ttu-id="b91a0-114">完了時での複数の同期タスクとプロセスの実行 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b91a0-114">Start Multiple Async Tasks and Process Them As They Complete (Visual Basic)</span></span>](start-multiple-async-tasks-and-process-them-as-they-complete.md)  
  
> [!NOTE]
> <span data-ttu-id="b91a0-115">この例を実行するには、コンピューターに Visual Studio 2012 以降および .NET Framework 4.5 以降がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b91a0-115">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
 <span data-ttu-id="b91a0-116">次の図が示すように、プロジェクトは、プロセスを開始するボタンとそれを取り消すボタンを含む UI を作成します。</span><span class="sxs-lookup"><span data-stu-id="b91a0-116">The projects create a UI that contains a button that starts the process and a button that cancels it, as the following image shows.</span></span> <span data-ttu-id="b91a0-117">ボタンの名前は `startButton` と `cancelButton` です。</span><span class="sxs-lookup"><span data-stu-id="b91a0-117">The buttons are named `startButton` and `cancelButton`.</span></span>  
  
 <span data-ttu-id="b91a0-118">![[キャンセル] ボタンが表示された WPF ウィンドウ](./media/fine-tuning-your-async-application/cancellation-and-start-button.png "[開始] ボタンと [停止] ボタンがあるダイアログボックス")</span><span class="sxs-lookup"><span data-stu-id="b91a0-118">![WPF window with Cancel button](./media/fine-tuning-your-async-application/cancellation-and-start-button.png "Dialog box with a Start and Stop button")</span></span>  
  
 <span data-ttu-id="b91a0-119">完全な Windows Presentation Foundation (WPF) プロジェクトは、「[Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)」 (非同期のサンプル: アプリケーションの微調整) からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="b91a0-119">You can download the complete Windows Presentation Foundation (WPF) projects from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b91a0-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="b91a0-120">See also</span></span>

- [<span data-ttu-id="b91a0-121">Async および Await を使用した非同期プログラミング (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b91a0-121">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](index.md)
