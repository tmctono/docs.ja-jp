---
title: 指定した時間の経過後の非同期タスクのキャンセル (C#)
description: 指定した期間内に完了していない、関連付けられたタスクのキャンセルをスケジュールする方法について説明します。
ms.date: 08/19/2020
ms.topic: tutorial
ms.assetid: 194282c2-399f-46da-a7a6-96674e00b0b3
ms.openlocfilehash: ad9064f8f45a737982ffc35ab4ea2395ddae9016
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811419"
---
# <a name="cancel-async-tasks-after-a-period-of-time-c"></a><span data-ttu-id="48537-103">指定した時間の経過後の非同期タスクのキャンセル (C#)</span><span class="sxs-lookup"><span data-stu-id="48537-103">Cancel async tasks after a period of time (C#)</span></span>

<span data-ttu-id="48537-104"><xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=nameWithType> メソッドを使用すると、一定の時間が過ぎた後に非同期操作が完了するまで待たない場合に、キャンセルすることができます。</span><span class="sxs-lookup"><span data-stu-id="48537-104">You can cancel an asynchronous operation after a period of time by using the <xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=nameWithType> method if you don't want to wait for the operation to finish.</span></span> <span data-ttu-id="48537-105">このメソッドは、`CancelAfter` 式によって指定された時間内に完了しない、関連付けられたタスクのキャンセルをスケジュールします。</span><span class="sxs-lookup"><span data-stu-id="48537-105">This method schedules the cancellation of any associated tasks that aren't complete within the period of time that's designated by the `CancelAfter` expression.</span></span>

<span data-ttu-id="48537-106">この例は、[タスクの一覧のキャンセル (C#)](cancel-an-async-task-or-a-list-of-tasks.md)に関する記事で開発したコードに追加して、Web サイトの一覧をダウンロードしてそれぞれのコンテンツの長さを表示します。</span><span class="sxs-lookup"><span data-stu-id="48537-106">This example adds to the code that's developed in [Cancel a list of tasks (C#)](cancel-an-async-task-or-a-list-of-tasks.md) to download a list of websites and to display the length of the contents of each one.</span></span>

<span data-ttu-id="48537-107">このチュートリアルの内容:</span><span class="sxs-lookup"><span data-stu-id="48537-107">This tutorial covers:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="48537-108">既存の .NET コンソール アプリケーションの更新</span><span class="sxs-lookup"><span data-stu-id="48537-108">Updating an existing .NET console application</span></span>
> - <span data-ttu-id="48537-109">キャンセルのスケジュール</span><span class="sxs-lookup"><span data-stu-id="48537-109">Scheduling a cancellation</span></span>

## <a name="prerequisites"></a><span data-ttu-id="48537-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="48537-110">Prerequisites</span></span>

<span data-ttu-id="48537-111">このチュートリアルには、次のものが必要です。</span><span class="sxs-lookup"><span data-stu-id="48537-111">This tutorial requires the following:</span></span>

- <span data-ttu-id="48537-112">[タスクの一覧のキャンセル (C#)](cancel-an-async-task-or-a-list-of-tasks.md) のチュートリアルでアプリケーションを作成しておきます</span><span class="sxs-lookup"><span data-stu-id="48537-112">You're expected to have created an application in the [Cancel a list of tasks (C#)](cancel-an-async-task-or-a-list-of-tasks.md) tutorial</span></span>
- [<span data-ttu-id="48537-113">.NET 5.0 以降の SDK</span><span class="sxs-lookup"><span data-stu-id="48537-113">.NET 5.0 or later SDK</span></span>](https://dotnet.microsoft.com/download/dotnet/5.0)
- <span data-ttu-id="48537-114">統合開発環境 (IDE)</span><span class="sxs-lookup"><span data-stu-id="48537-114">Integrated development environment (IDE)</span></span>
  - [<span data-ttu-id="48537-115">Visual Studio、Visual Studio Code、または Visual Studio for Mac をお勧めします</span><span class="sxs-lookup"><span data-stu-id="48537-115">We recommend Visual Studio, Visual Studio Code, or Visual Studio for Mac</span></span>](https://visualstudio.microsoft.com)

## <a name="update-application-entry-point"></a><span data-ttu-id="48537-116">アプリケーション エントリ ポイントの更新</span><span class="sxs-lookup"><span data-stu-id="48537-116">Update application entry point</span></span>

<span data-ttu-id="48537-117">既存の`Main` メソッドを以下に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="48537-117">Replace the existing `Main` method with the following:</span></span>

```csharp
static async Task Main()
{
    Console.WriteLine("Application started.");

    try
    {
        s_cts.CancelAfter(3500);

        await SumPageSizesAsync();
    }
    catch (TaskCanceledException)
    {
        Console.WriteLine("\nTasks cancelled: timed out.\n");
    }

    Console.WriteLine("Application ending.");
}
```

<span data-ttu-id="48537-118">更新された `Main` メソッドで、いくつかの指示メッセージがコンソールに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="48537-118">The updated `Main` method writes a few instructional messages to the console.</span></span> <span data-ttu-id="48537-119">[try catch](../../../language-reference/keywords/try-catch.md) 内で、<xref:System.Threading.CancellationTokenSource.CancelAfter(System.Int32)?displayProperty=nameWithType> を呼び出してキャンセルをスケジュールします。</span><span class="sxs-lookup"><span data-stu-id="48537-119">Within the [try catch](../../../language-reference/keywords/try-catch.md), a call to <xref:System.Threading.CancellationTokenSource.CancelAfter(System.Int32)?displayProperty=nameWithType> to schedule a cancellation.</span></span> <span data-ttu-id="48537-120">これにより、一定の期間後にキャンセルが通知されます。</span><span class="sxs-lookup"><span data-stu-id="48537-120">This will signal cancellation after a period of time.</span></span>

<span data-ttu-id="48537-121">次に、`SumPageSizesAsync` メソッドが待機されます。</span><span class="sxs-lookup"><span data-stu-id="48537-121">Next, the `SumPageSizesAsync` method is awaited.</span></span> <span data-ttu-id="48537-122">スケジュールされたキャンセルよりも、すべての URL の処理が早く行われると、アプリケーションは終了します。</span><span class="sxs-lookup"><span data-stu-id="48537-122">If processing all of the URLs occurs faster than the scheduled cancellation, the application ends.</span></span> <span data-ttu-id="48537-123">ただし、すべての URL が処理される前にスケジュールされたキャンセルがトリガーされると、<xref:System.Threading.Tasks.TaskCanceledException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="48537-123">However, if the scheduled cancellation is triggered before all of the URLs are processed, a <xref:System.Threading.Tasks.TaskCanceledException> is thrown.</span></span>

### <a name="example-application-output"></a><span data-ttu-id="48537-124">アプリケーション出力の例</span><span class="sxs-lookup"><span data-stu-id="48537-124">Example application output</span></span>

```console
Application started.

https://docs.microsoft.com                                       37,357
https://docs.microsoft.com/aspnet/core                           85,589
https://docs.microsoft.com/azure                                398,939
https://docs.microsoft.com/azure/devops                          73,663

Tasks cancelled: timed out.

Application ending.
```

## <a name="complete-example"></a><span data-ttu-id="48537-125">コード例全体</span><span class="sxs-lookup"><span data-stu-id="48537-125">Complete example</span></span>

<span data-ttu-id="48537-126">次のコードは、この例の *Program.cs* ファイルの完全なテキストです。</span><span class="sxs-lookup"><span data-stu-id="48537-126">The following code is the complete text of the *Program.cs* file for the example.</span></span>

:::code language="csharp" source="snippets/cancel-tasks/cancel-task-after-period-of-time/Program.cs":::

## <a name="see-also"></a><span data-ttu-id="48537-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="48537-127">See also</span></span>

- <xref:System.Threading.CancellationToken>
- <xref:System.Threading.CancellationTokenSource>
- [<span data-ttu-id="48537-128">Async および Await を使用した非同期プログラミング (C#)</span><span class="sxs-lookup"><span data-stu-id="48537-128">Asynchronous programming with async and await (C#)</span></span>](index.md)
- [<span data-ttu-id="48537-129">タスクの一覧をキャンセルする (C#)</span><span class="sxs-lookup"><span data-stu-id="48537-129">Cancel a list of tasks (C#)</span></span>](cancel-an-async-task-or-a-list-of-tasks.md)
