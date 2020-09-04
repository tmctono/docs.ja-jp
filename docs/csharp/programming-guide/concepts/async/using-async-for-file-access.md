---
title: ファイルへの非同期アクセス (C#)
description: C# で非同期機能を使用してファイルにアクセスする方法について説明します。 コールバックを使用したり、複数のメソッドでコードを分割したりせずに、非同期メソッドを呼び出すことができます。
ms.date: 08/19/2020
ms.assetid: bb018fea-5313-4c80-ab3f-7c24b2145bd9
ms.openlocfilehash: 9a8db6004e8fff2cb39f0c350b403b56ea619e54
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812043"
---
# <a name="asynchronous-file-access-c"></a><span data-ttu-id="f9119-104">ファイルへの非同期アクセス (C#)</span><span class="sxs-lookup"><span data-stu-id="f9119-104">Asynchronous file access (C#)</span></span>

<span data-ttu-id="f9119-105">ファイルにアクセスする際に非同期機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f9119-105">You can use the async feature to access files.</span></span> <span data-ttu-id="f9119-106">非同期機能を使用すると、コールバックの使用や複数のメソッドまたはラムダ式へのコードの分割を行わずに、非同期メソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="f9119-106">By using the async feature, you can call into asynchronous methods without using callbacks or splitting your code across multiple methods or lambda expressions.</span></span> <span data-ttu-id="f9119-107">同期コードを非同期コードにするには、同期メソッドの代わりに非同期メソッドを呼び出して、コードにいくつかのキーワードを追加するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="f9119-107">To make synchronous code asynchronous, you just call an asynchronous method instead of a synchronous method and add a few keywords to the code.</span></span>

<span data-ttu-id="f9119-108">ファイル アクセスの呼び出しに非同期性を適用する利点には、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="f9119-108">You might consider the following reasons for adding asynchrony to file access calls:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="f9119-109">非同期性により、UI アプリケーションの応答性が向上します。非同期処理を開始した UI スレッドが他の処理を実行できるためです。</span><span class="sxs-lookup"><span data-stu-id="f9119-109">Asynchrony makes UI applications more responsive because the UI thread that launches the operation can perform other work.</span></span> <span data-ttu-id="f9119-110">UI スレッドが、時間のかかるコード、たとえば 50 ミリ秒を超えるコードを実行する必要がある場合、I/O が完了して、UI スレッドがキーボードやマウス入力などのイベントを再度処理できるようになるまで、UI が停止することがあります。</span><span class="sxs-lookup"><span data-stu-id="f9119-110">If the UI thread must execute code that takes a long time (for example, more than 50 milliseconds), the UI may freeze until the I/O is complete and the UI thread can again process keyboard and mouse input and other events.</span></span>
> - <span data-ttu-id="f9119-111">非同期性を適用すると、スレッドの必要性が軽減され、ASP.NET などのサーバー ベースのアプリケーションのスケーラビリティが向上します。</span><span class="sxs-lookup"><span data-stu-id="f9119-111">Asynchrony improves the scalability of ASP.NET and other server-based applications by reducing the need for threads.</span></span> <span data-ttu-id="f9119-112">アプリケーションが応答ごとに専用スレッドを使用している場合、1,000 個の要求を同時に処理するには、1,000 個のスレッドが必要です。</span><span class="sxs-lookup"><span data-stu-id="f9119-112">If the application uses a dedicated thread per response and a thousand requests are being handled simultaneously, a thousand threads are needed.</span></span> <span data-ttu-id="f9119-113">非同期操作では、待機中にスレッドを使用する必要はほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="f9119-113">Asynchronous operations often don't need to use a thread during the wait.</span></span> <span data-ttu-id="f9119-114">既存の I/O 完了スレッドが最後に少しだけ使用されます。</span><span class="sxs-lookup"><span data-stu-id="f9119-114">They use the existing I/O completion thread briefly at the end.</span></span>
> - <span data-ttu-id="f9119-115">現状ではファイル アクセス操作の待機時間が非常に短くても、将来に大幅に長くなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f9119-115">The latency of a file access operation might be very low under current conditions, but the latency may greatly increase in the future.</span></span> <span data-ttu-id="f9119-116">たとえば、地球の裏側にあるサーバーにファイルが移動される場合があります。</span><span class="sxs-lookup"><span data-stu-id="f9119-116">For example, a file may be moved to a server that's across the world.</span></span>
> - <span data-ttu-id="f9119-117">非同期機能の使用に伴うオーバーヘッドはわずかです。</span><span class="sxs-lookup"><span data-stu-id="f9119-117">The added overhead of using the Async feature is small.</span></span>
> - <span data-ttu-id="f9119-118">非同期タスクは簡単に並列実行できます。</span><span class="sxs-lookup"><span data-stu-id="f9119-118">Asynchronous tasks can easily be run in parallel.</span></span>

## <a name="use-appropriate-classes"></a><span data-ttu-id="f9119-119">適切なクラスを使用する</span><span class="sxs-lookup"><span data-stu-id="f9119-119">Use appropriate classes</span></span>

<span data-ttu-id="f9119-120">このトピックの簡単な例では、<xref:System.IO.File.WriteAllTextAsync%2A?displayProperty=nameWithType> と <xref:System.IO.File.ReadAllTextAsync%2A?displayProperty=nameWithType> について説明します。</span><span class="sxs-lookup"><span data-stu-id="f9119-120">The simple examples in this topic demonstrate <xref:System.IO.File.WriteAllTextAsync%2A?displayProperty=nameWithType> and <xref:System.IO.File.ReadAllTextAsync%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f9119-121">ファイル I/O 操作を有限制御するには、<xref:System.IO.FileStream> クラスを使用します。これには、オペレーティング システムのレベルで非同期 I/O を発生させるオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="f9119-121">For finite control over the file I/O operations, use the <xref:System.IO.FileStream> class, which has an option that causes asynchronous I/O to occur at the operating system level.</span></span> <span data-ttu-id="f9119-122">このオプションを使用することにより、多くの場合、スレッド プール スレッドがブロックされるのを回避できます。</span><span class="sxs-lookup"><span data-stu-id="f9119-122">By using this option, you can avoid blocking a thread pool thread in many cases.</span></span> <span data-ttu-id="f9119-123">このオプションを有効にするには、コンストラクター呼び出しで `useAsync=true` または `options=FileOptions.Asynchronous` 引数を指定します。</span><span class="sxs-lookup"><span data-stu-id="f9119-123">To enable this option, you specify the `useAsync=true` or `options=FileOptions.Asynchronous` argument in the constructor call.</span></span>

<span data-ttu-id="f9119-124">ファイル パスを指定して <xref:System.IO.StreamReader> と <xref:System.IO.StreamWriter> を直接開いた場合、それらでこのオプションを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="f9119-124">You can't use this option with <xref:System.IO.StreamReader> and <xref:System.IO.StreamWriter> if you open them directly by specifying a file path.</span></span> <span data-ttu-id="f9119-125">一方、<xref:System.IO.FileStream> クラスによって開かれた <xref:System.IO.Stream> を使用する場合は、このオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f9119-125">However, you can use this option if you provide them a <xref:System.IO.Stream> that the <xref:System.IO.FileStream> class opened.</span></span> <span data-ttu-id="f9119-126">UI アプリでは、スレッド プール スレッドがブロックされても、非同期呼び出しは高速になります。これは、UI スレッドは待機中にブロックされないためです。</span><span class="sxs-lookup"><span data-stu-id="f9119-126">Asynchronous calls are faster in UI apps even if a thread pool thread is blocked, because the UI thread isn't blocked during the wait.</span></span>

## <a name="write-text"></a><span data-ttu-id="f9119-127">テキストを書き込む</span><span class="sxs-lookup"><span data-stu-id="f9119-127">Write text</span></span>

<span data-ttu-id="f9119-128">次の例では、ファイルにテキストを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="f9119-128">The following examples write text to a file.</span></span> <span data-ttu-id="f9119-129">各 await ステートメントに達すると、メソッドは直ちに終了します。</span><span class="sxs-lookup"><span data-stu-id="f9119-129">At each await statement, the method immediately exits.</span></span> <span data-ttu-id="f9119-130">ファイル I/O が完了すると、メソッドは await ステートメントの後のステートメントから再開します。</span><span class="sxs-lookup"><span data-stu-id="f9119-130">When the file I/O is complete, the method resumes at the statement that follows the await statement.</span></span> <span data-ttu-id="f9119-131">async 修飾子は、await ステートメントを使用するメソッドの定義に含まれます。</span><span class="sxs-lookup"><span data-stu-id="f9119-131">The async modifier is in the definition of methods that use the await statement.</span></span>

### <a name="simple-example"></a><span data-ttu-id="f9119-132">簡単な例</span><span class="sxs-lookup"><span data-stu-id="f9119-132">Simple example</span></span>

:::code language="csharp" source="snippets/file-access/Program.cs" id="SimpleWrite":::

### <a name="finite-control-example"></a><span data-ttu-id="f9119-133">有限制御の例</span><span class="sxs-lookup"><span data-stu-id="f9119-133">Finite control example</span></span>

:::code language="csharp" source="snippets/file-access/Program.cs" id="WriteText":::

<span data-ttu-id="f9119-134">元の例には `await sourceStream.WriteAsync(encodedText, 0, encodedText.Length);` ステートメントがあります。これは、次の 2 つのステートメントの省略形です。</span><span class="sxs-lookup"><span data-stu-id="f9119-134">The original example has the statement `await sourceStream.WriteAsync(encodedText, 0, encodedText.Length);`, which is a contraction of the following two statements:</span></span>

```csharp
Task theTask = sourceStream.WriteAsync(encodedText, 0, encodedText.Length);
await theTask;
```

<span data-ttu-id="f9119-135">最初のステートメントはタスクを返し、ファイル処理を開始します。</span><span class="sxs-lookup"><span data-stu-id="f9119-135">The first statement returns a task and causes file processing to start.</span></span> <span data-ttu-id="f9119-136">await が含まれた 2 番目のステートメントによって、メソッドが直ちに終了し、別のタスクを返します。</span><span class="sxs-lookup"><span data-stu-id="f9119-136">The second statement with the await causes the method to immediately exit and return a different task.</span></span> <span data-ttu-id="f9119-137">ファイル処理が完了すると、await の後のステートメントに実行が戻ります。</span><span class="sxs-lookup"><span data-stu-id="f9119-137">When the file processing later completes, execution returns to the statement that follows the await.</span></span>

## <a name="read-text"></a><span data-ttu-id="f9119-138">テキストを読み取る</span><span class="sxs-lookup"><span data-stu-id="f9119-138">Read text</span></span>

<span data-ttu-id="f9119-139">次の例では、ファイルからテキストを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="f9119-139">The following examples read text from a file.</span></span>

### <a name="simple-example"></a><span data-ttu-id="f9119-140">簡単な例</span><span class="sxs-lookup"><span data-stu-id="f9119-140">Simple example</span></span>

:::code language="csharp" source="snippets/file-access/Program.cs" id="SimpleRead":::

### <a name="finite-control-example"></a><span data-ttu-id="f9119-141">有限制御の例</span><span class="sxs-lookup"><span data-stu-id="f9119-141">Finite control example</span></span>

<span data-ttu-id="f9119-142">テキストはバッファーに格納されます。この例では <xref:System.Text.StringBuilder> に配置されます。</span><span class="sxs-lookup"><span data-stu-id="f9119-142">The text is buffered and, in this case, placed into a <xref:System.Text.StringBuilder>.</span></span> <span data-ttu-id="f9119-143">前の例と異なり、await の評価で値が生成されます。</span><span class="sxs-lookup"><span data-stu-id="f9119-143">Unlike in the previous example, the evaluation of the await produces a value.</span></span> <span data-ttu-id="f9119-144"><xref:System.IO.Stream.ReadAsync%2A> メソッドによって <xref:System.Threading.Tasks.Task>\<<xref:System.Int32>> が返されます。処理の完了後、await の評価によって `Int32` 値 `numRead` が生成されます。</span><span class="sxs-lookup"><span data-stu-id="f9119-144">The <xref:System.IO.Stream.ReadAsync%2A> method returns a <xref:System.Threading.Tasks.Task>\<<xref:System.Int32>>, so the evaluation of the await produces an `Int32` value `numRead` after the operation completes.</span></span> <span data-ttu-id="f9119-145">詳しくは、「[非同期の戻り値の型 (C#)](async-return-types.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f9119-145">For more information, see [Async Return Types (C#)](async-return-types.md).</span></span>

:::code language="csharp" source="snippets/file-access/Program.cs" id="ReadText":::

## <a name="parallel-asynchronous-io"></a><span data-ttu-id="f9119-146">並列非同期 I/O</span><span class="sxs-lookup"><span data-stu-id="f9119-146">Parallel asynchronous I/O</span></span>

<span data-ttu-id="f9119-147">次の例では、10 個のテキスト ファイルを記述する並列処理を示します。</span><span class="sxs-lookup"><span data-stu-id="f9119-147">The following examples demonstrate parallel processing by writing 10 text files.</span></span>

### <a name="simple-example"></a><span data-ttu-id="f9119-148">簡単な例</span><span class="sxs-lookup"><span data-stu-id="f9119-148">Simple example</span></span>

:::code language="csharp" source="snippets/file-access/Program.cs" id="SimpleParallelWrite":::

### <a name="finite-control-example"></a><span data-ttu-id="f9119-149">有限制御の例</span><span class="sxs-lookup"><span data-stu-id="f9119-149">Finite control example</span></span>

<span data-ttu-id="f9119-150"><xref:System.IO.Stream.WriteAsync%2A> メソッドは、ファイルごとにタスクを返します。タスクはタスクの一覧に追加されます。</span><span class="sxs-lookup"><span data-stu-id="f9119-150">For each file, the <xref:System.IO.Stream.WriteAsync%2A> method returns a task that is then added to a list of tasks.</span></span> <span data-ttu-id="f9119-151">`await Task.WhenAll(tasks);` ステートメントはメソッドを終了し、すべてのタスクのファイル処理が完了すると、メソッド内で再開します。</span><span class="sxs-lookup"><span data-stu-id="f9119-151">The `await Task.WhenAll(tasks);` statement exits the method and resumes within the method when file processing is complete for all of the tasks.</span></span>

<span data-ttu-id="f9119-152">この例では、タスクの完了後、`finally` ブロックのすべての <xref:System.IO.FileStream> インスタンスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="f9119-152">The example closes all <xref:System.IO.FileStream> instances in a `finally` block after the tasks are complete.</span></span> <span data-ttu-id="f9119-153">`using` ステートメントで `FileStream` が作成された場合は、タスクが完了する前に `FileStream` が破棄されることがあります。</span><span class="sxs-lookup"><span data-stu-id="f9119-153">If each `FileStream` was instead created in a `using` statement, the `FileStream` might be disposed of before the task was complete.</span></span>

<span data-ttu-id="f9119-154">パフォーマンスの向上の多くは、非同期処理ではなく並列処理によって実現されます。</span><span class="sxs-lookup"><span data-stu-id="f9119-154">Any performance boost is almost entirely from the parallel processing and not the asynchronous processing.</span></span> <span data-ttu-id="f9119-155">非同期性の利点は、複数のスレッドやユーザー インターフェイス スレッドが拘束されない点にあります。</span><span class="sxs-lookup"><span data-stu-id="f9119-155">The advantages of asynchrony are that it doesn't tie up multiple threads, and that it doesn't tie up the user interface thread.</span></span>

:::code language="csharp" source="snippets/file-access/Program.cs" id="ParallelWriteText":::

<span data-ttu-id="f9119-156"><xref:System.IO.Stream.WriteAsync%2A> メソッドと <xref:System.IO.Stream.ReadAsync%2A> メソッドを使用すると、<xref:System.Threading.CancellationToken> を指定して、途中で処理をキャンセルすることができます。</span><span class="sxs-lookup"><span data-stu-id="f9119-156">When using the <xref:System.IO.Stream.WriteAsync%2A> and <xref:System.IO.Stream.ReadAsync%2A> methods, you can specify a <xref:System.Threading.CancellationToken>, which you can use to cancel the operation mid-stream.</span></span> <span data-ttu-id="f9119-157">詳細については、「[マネージド スレッドのキャンセル](../../../../standard/threading/cancellation-in-managed-threads.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9119-157">For more information, see [Cancellation in managed threads](../../../../standard/threading/cancellation-in-managed-threads.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f9119-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="f9119-158">See also</span></span>

- [<span data-ttu-id="f9119-159">Async および Await を使用した非同期プログラミング (C#)</span><span class="sxs-lookup"><span data-stu-id="f9119-159">Asynchronous programming with async and await (C#)</span></span>](index.md)
- [<span data-ttu-id="f9119-160">非同期の戻り値の型 (C#)</span><span class="sxs-lookup"><span data-stu-id="f9119-160">Async return types (C#)</span></span>](async-return-types.md)
