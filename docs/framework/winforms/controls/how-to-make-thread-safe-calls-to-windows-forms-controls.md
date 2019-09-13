---
title: '方法: Windows フォームコントロールに対してスレッドセーフな呼び出しを行う'
ms.date: 02/19/2019
dev_langs:
- csharp
- vb
f1_keywords:
- EHInvalidOperation.WinForms.IllegalCrossThreadCall
helpviewer_keywords:
- thread safety [Windows Forms], calling controls [Windows Forms]
- calling controls [Windows Forms], thread safety [Windows Forms]
- CheckForIllegalCrossThreadCalls property [Windows Forms]
- Windows Forms controls [Windows Forms], multithreading
- BackgroundWorker class [Windows Forms], examples
- threading [Windows Forms], cross-thread calls
- controls [Windows Forms], multithreading
ms.assetid: 138f38b6-1099-4fd5-910c-390b41cbad35
ms.openlocfilehash: 78ad7b16d5220972a61848c0c80cd884afa842d9
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928617"
---
# <a name="how-to-make-thread-safe-calls-to-windows-forms-controls"></a><span data-ttu-id="0e6e7-102">方法: Windows フォームコントロールに対してスレッドセーフな呼び出しを行う</span><span class="sxs-lookup"><span data-stu-id="0e6e7-102">How to: Make thread-safe calls to Windows Forms controls</span></span>

<span data-ttu-id="0e6e7-103">マルチスレッドは Windows フォームアプリのパフォーマンスを向上させることができますが、Windows フォームコントロールへのアクセスは本質的にスレッドセーフではありません。</span><span class="sxs-lookup"><span data-stu-id="0e6e7-103">Multithreading can improve the performance of Windows Forms apps, but access to Windows Forms controls isn't inherently thread-safe.</span></span> <span data-ttu-id="0e6e7-104">マルチスレッドでは、非常に深刻で複雑なバグにコードを公開できます。</span><span class="sxs-lookup"><span data-stu-id="0e6e7-104">Multithreading can expose your code to very serious and complex bugs.</span></span> <span data-ttu-id="0e6e7-105">コントロールを操作する2つ以上のスレッドによって、コントロールが一貫性のない状態になり、競合状態、デッドロック、フリーズまたはハングが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0e6e7-105">Two or more threads manipulating a control can force the control into an inconsistent state and lead to race conditions, deadlocks, and freezes or hangs.</span></span> <span data-ttu-id="0e6e7-106">アプリにマルチスレッドを実装する場合は、スレッドセーフな方法でスレッド間コントロールを呼び出すようにしてください。</span><span class="sxs-lookup"><span data-stu-id="0e6e7-106">If you implement multithreading in your app, be sure to call cross-thread controls in a thread-safe way.</span></span> <span data-ttu-id="0e6e7-107">詳細については、「[マネージスレッド処理のベストプラクティス](../../../standard/threading/managed-threading-best-practices.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e6e7-107">For more information, see [Managed threading best practices](../../../standard/threading/managed-threading-best-practices.md).</span></span> 

<span data-ttu-id="0e6e7-108">コントロールを作成していないスレッドから Windows フォームコントロールを安全に呼び出すには、2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="0e6e7-108">There are two ways to safely call a Windows Forms control from a thread that didn't create that control.</span></span> <span data-ttu-id="0e6e7-109"><xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName>メソッドを使用して、メインスレッドで作成されたデリゲートを呼び出すことができます。このデリゲートは、コントロールを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="0e6e7-109">You can use the <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> method to call a delegate created in the main thread, which in turn calls the control.</span></span> <span data-ttu-id="0e6e7-110">または、を実装<xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>できます。これは、イベントドリブンモデルを使用して、バックグラウンドスレッドで実行された作業を結果のレポートから分離します。</span><span class="sxs-lookup"><span data-stu-id="0e6e7-110">Or, you can implement a <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>, which uses an event-driven model to separate work done in the background thread from reporting on the results.</span></span> 

## <a name="unsafe-cross-thread-calls"></a><span data-ttu-id="0e6e7-111">安全でないクロススレッド呼び出し</span><span class="sxs-lookup"><span data-stu-id="0e6e7-111">Unsafe cross-thread calls</span></span>

<span data-ttu-id="0e6e7-112">コントロールを作成していないスレッドから直接呼び出すことは安全ではありません。</span><span class="sxs-lookup"><span data-stu-id="0e6e7-112">It's unsafe to call a control directly from a thread that didn't create it.</span></span> <span data-ttu-id="0e6e7-113">次のコードスニペットは、コントロールへの<xref:System.Windows.Forms.TextBox?displayProperty=nameWithType>安全でない呼び出しを示しています。</span><span class="sxs-lookup"><span data-stu-id="0e6e7-113">The following code snippet illustrates an unsafe call to the <xref:System.Windows.Forms.TextBox?displayProperty=nameWithType> control.</span></span> <span data-ttu-id="0e6e7-114">イベント`Button1_Click`ハンドラーは、メインスレッド`WriteTextUnsafe`の<xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType>プロパティを直接設定する新しいスレッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="0e6e7-114">The `Button1_Click` event handler creates a new `WriteTextUnsafe` thread, which sets the main thread's <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> property directly.</span></span> 

```csharp
private void Button1_Click(object sender, EventArgs e)
{
    thread2 = new Thread(new ThreadStart(WriteTextUnsafe));
    thread2.Start();
}
private void WriteTextUnsafe()
{
    textBox1.Text = "This text was set unsafely.";
}
```

```vb
Private Sub Button1_Click(ByVal sender As Object, e As EventArgs) Handles Button1.Click
    Thread2 = New Thread(New ThreadStart(AddressOf WriteTextUnsafe))
    Thread2.Start()
End Sub

Private Sub WriteTextUnsafe()
    TextBox1.Text = "This text was set unsafely."
End Sub
```

<span data-ttu-id="0e6e7-115">Visual Studio デバッガーは、メッセージを使用してを発生<xref:System.InvalidOperationException>させ、 **スレッド間の操作が無効であることによって、これらのアンセーフスレッド呼び出しを検出します。コントロール "" が作成されたスレッド以外のスレッドからアクセスされました。**</span><span class="sxs-lookup"><span data-stu-id="0e6e7-115">The Visual Studio debugger detects these unsafe thread calls by raising an <xref:System.InvalidOperationException> with the message, **Cross-thread operation not valid. Control "" accessed from a thread other than the thread it was created on.**</span></span> <span data-ttu-id="0e6e7-116">は<xref:System.InvalidOperationException> 、Visual Studio のデバッグ中に安全でないクロススレッド呼び出しに対して常に発生し、アプリの実行時に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0e6e7-116">The <xref:System.InvalidOperationException> always occurs for unsafe cross-thread calls during Visual Studio debugging, and may occur at app runtime.</span></span> <span data-ttu-id="0e6e7-117">この問題は解決する必要がありますが、 <xref:System.Windows.Forms.Control.CheckForIllegalCrossThreadCalls%2A?displayProperty=nameWithType>プロパティをに`false`設定することによって例外を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="0e6e7-117">You should fix the issue, but you can disable the exception by setting the <xref:System.Windows.Forms.Control.CheckForIllegalCrossThreadCalls%2A?displayProperty=nameWithType> property to `false`.</span></span>

## <a name="safe-cross-thread-calls"></a><span data-ttu-id="0e6e7-118">安全なクロススレッド呼び出し</span><span class="sxs-lookup"><span data-stu-id="0e6e7-118">Safe cross-thread calls</span></span> 

<span data-ttu-id="0e6e7-119">次のコード例は、作成されていないスレッドから Windows フォームコントロールを安全に呼び出す2つの方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="0e6e7-119">The following code examples demonstrate two ways to safely call a Windows Forms control from a thread that didn't create it:</span></span> 

1. <span data-ttu-id="0e6e7-120">メソッド<xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> 。このメソッドは、コントロールを呼び出すメインスレッドからデリゲートを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="0e6e7-120">The <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> method, which calls a delegate from the main thread to call the control.</span></span> 
2. <span data-ttu-id="0e6e7-121">イベントドリブンモデルを提供するコンポーネント。<xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="0e6e7-121">A <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> component, which offers an event-driven model.</span></span> 

<span data-ttu-id="0e6e7-122">どちらの例でも、バックグラウンドスレッドは1秒間スリープして、そのスレッドで実行されている作業をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="0e6e7-122">In both examples, the background thread sleeps for one second to simulate work being done in that thread.</span></span> 

<span data-ttu-id="0e6e7-123">これらの例は、または Visual Basic のC#コマンドラインから .NET Framework アプリとしてビルドして実行できます。</span><span class="sxs-lookup"><span data-stu-id="0e6e7-123">You can build and run these examples as .NET Framework apps from the C# or Visual Basic command line.</span></span> <span data-ttu-id="0e6e7-124">詳細については、「 [csc.exe を使用したコマンドライン](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)からのビルド」または「[コマンドラインからのビルド (Visual Basic)](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e6e7-124">For more information, see [Command-line building with csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) or [Build from the command line (Visual Basic)](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span> 

<span data-ttu-id="0e6e7-125">.NET Core 3.0 以降では、ことができますもビルドおよび実行する例では、.NET Core アプリを Windows として .NET Core の Windows フォームのあるフォルダーから *\<フォルダー名>.csproj* プロジェクト ファイル。</span><span class="sxs-lookup"><span data-stu-id="0e6e7-125">Starting with .NET Core 3.0, you can also build and run the examples as Windows .NET Core apps from a folder that has a .NET Core Windows Forms *\<folder name>.csproj* project file.</span></span> 

## <a name="example-use-the-invoke-method-with-a-delegate"></a><span data-ttu-id="0e6e7-126">例:デリゲートで Invoke メソッドを使用する</span><span class="sxs-lookup"><span data-stu-id="0e6e7-126">Example: Use the Invoke method with a delegate</span></span>

<span data-ttu-id="0e6e7-127">次の例は、Windows フォームコントロールへのスレッドセーフな呼び出しを保証するパターンを示しています。</span><span class="sxs-lookup"><span data-stu-id="0e6e7-127">The following example demonstrates a pattern for ensuring thread-safe calls to a Windows Forms control.</span></span> <span data-ttu-id="0e6e7-128">このメソッドは<xref:System.Windows.Forms.Control.InvokeRequired%2A?displayProperty=fullName> 、プロパティに対してクエリを行います。これにより、コントロールの作成スレッド id が呼び出し元のスレッド id と比較されます。</span><span class="sxs-lookup"><span data-stu-id="0e6e7-128">It queries the <xref:System.Windows.Forms.Control.InvokeRequired%2A?displayProperty=fullName> property, which compares the control's creating thread ID to the calling thread ID.</span></span> <span data-ttu-id="0e6e7-129">スレッド Id が同じである場合は、コントロールを直接呼び出します。</span><span class="sxs-lookup"><span data-stu-id="0e6e7-129">If the thread IDs are the same, it calls the control directly.</span></span> <span data-ttu-id="0e6e7-130">スレッド id が異なる場合は、メインスレッドから<xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=nameWithType>のデリゲートを使用してメソッドを呼び出します。これにより、コントロールへの実際の呼び出しが行われます。</span><span class="sxs-lookup"><span data-stu-id="0e6e7-130">If the thread IDs are different, it calls the <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=nameWithType> method with a delegate from the main thread, which makes the actual call to the control.</span></span>

<span data-ttu-id="0e6e7-131">を`SafeCallDelegate`使用すると<xref:System.Windows.Forms.TextBox> 、コントロール<xref:System.Windows.Forms.TextBox.Text%2A>のプロパティを設定できます。</span><span class="sxs-lookup"><span data-stu-id="0e6e7-131">The `SafeCallDelegate` enables setting the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span> <span data-ttu-id="0e6e7-132">メソッド`WriteTextSafe`がクエリ<xref:System.Windows.Forms.Control.InvokeRequired%2A>を行います。</span><span class="sxs-lookup"><span data-stu-id="0e6e7-132">The `WriteTextSafe` method queries <xref:System.Windows.Forms.Control.InvokeRequired%2A>.</span></span> <span data-ttu-id="0e6e7-133">が<xref:System.Windows.Forms.Control.InvokeRequired%2A> `true` `SafeCallDelegate` を返す<xref:System.Windows.Forms.Control.Invoke%2A>場合は、をメソッドに渡して、コントロールへの実際の呼び出しを行います。`WriteTextSafe`</span><span class="sxs-lookup"><span data-stu-id="0e6e7-133">If <xref:System.Windows.Forms.Control.InvokeRequired%2A> returns `true`, `WriteTextSafe` passes the `SafeCallDelegate` to the <xref:System.Windows.Forms.Control.Invoke%2A> method to make the actual call to the control.</span></span> <span data-ttu-id="0e6e7-134">が<xref:System.Windows.Forms.Control.InvokeRequired%2A>を`false`返す`WriteTextSafe`場合は<xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> 、を直接設定します。</span><span class="sxs-lookup"><span data-stu-id="0e6e7-134">If <xref:System.Windows.Forms.Control.InvokeRequired%2A> returns `false`, `WriteTextSafe` sets the <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> directly.</span></span> <span data-ttu-id="0e6e7-135">イベント`Button1_Click`ハンドラーは、新しいスレッドを作成し、 `WriteTextSafe`メソッドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0e6e7-135">The `Button1_Click` event handler creates the new thread and runs the `WriteTextSafe` method.</span></span> 

 [!code-csharp[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/vb/Form1.vb)]  

## <a name="example-use-a-backgroundworker-event-handler"></a><span data-ttu-id="0e6e7-136">例:BackgroundWorker イベントハンドラーを使用する</span><span class="sxs-lookup"><span data-stu-id="0e6e7-136">Example: Use a BackgroundWorker event handler</span></span>

<span data-ttu-id="0e6e7-137">マルチスレッドを実装する簡単な方法は<xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> 、イベントドリブンモデルを使用するコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="0e6e7-137">An easy way to implement multithreading is with the <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> component, which uses an event-driven model.</span></span> <span data-ttu-id="0e6e7-138">バックグラウンドスレッドは、メイン<xref:System.ComponentModel.BackgroundWorker.DoWork?displayProperty=nameWithType>スレッドと対話しないイベントを実行します。</span><span class="sxs-lookup"><span data-stu-id="0e6e7-138">The background thread runs the <xref:System.ComponentModel.BackgroundWorker.DoWork?displayProperty=nameWithType> event, which doesn't interact with the main thread.</span></span> <span data-ttu-id="0e6e7-139">メインスレッドは、メイン<xref:System.ComponentModel.BackgroundWorker.ProgressChanged?displayProperty=nameWithType>スレッド<xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted?displayProperty=nameWithType>のコントロールを呼び出すことができるイベントハンドラーとイベントハンドラーを実行します。</span><span class="sxs-lookup"><span data-stu-id="0e6e7-139">The main thread runs the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged?displayProperty=nameWithType> and <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted?displayProperty=nameWithType> event handlers, which can call the main thread's controls.</span></span>

<span data-ttu-id="0e6e7-140">を使用<xref:System.ComponentModel.BackgroundWorker>してスレッドセーフな呼び出しを行うには、バックグラウンドスレッドでメソッドを作成して作業を実行し、 <xref:System.ComponentModel.BackgroundWorker.DoWork>イベントにバインドします。</span><span class="sxs-lookup"><span data-stu-id="0e6e7-140">To make a thread-safe call by using <xref:System.ComponentModel.BackgroundWorker>, create a method in the background thread to do the work, and bind it to the <xref:System.ComponentModel.BackgroundWorker.DoWork> event.</span></span> <span data-ttu-id="0e6e7-141">メインスレッドで別のメソッドを作成して、バックグラウンド作業の結果を報告し、イベント<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>または<xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>イベントにバインドします。</span><span class="sxs-lookup"><span data-stu-id="0e6e7-141">Create another method in the main thread to report the results of the background work, and bind it to the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> or <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event.</span></span> <span data-ttu-id="0e6e7-142">バックグラウンドスレッドを開始するには<xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A?displayProperty=nameWithType>、を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="0e6e7-142">To start the background thread, call <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A?displayProperty=nameWithType>.</span></span> 

<span data-ttu-id="0e6e7-143">この例では<xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 、イベントハンドラーを使用<xref:System.Windows.Forms.TextBox>して<xref:System.Windows.Forms.TextBox.Text%2A> 、コントロールのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="0e6e7-143">The example uses the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler to set the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span> <span data-ttu-id="0e6e7-144">イベントの<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>使用例については<xref:System.ComponentModel.BackgroundWorker>、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e6e7-144">For an example using the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event, see <xref:System.ComponentModel.BackgroundWorker>.</span></span> 

 [!code-csharp[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/vb/Form1.vb)]  

## <a name="see-also"></a><span data-ttu-id="0e6e7-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="0e6e7-145">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- [<span data-ttu-id="0e6e7-146">方法: バックグラウンドで操作を実行する</span><span class="sxs-lookup"><span data-stu-id="0e6e7-146">How to: Run an operation in the background</span></span>](how-to-run-an-operation-in-the-background.md)
- [<span data-ttu-id="0e6e7-147">方法: バックグラウンド操作を使用するフォームを実装する</span><span class="sxs-lookup"><span data-stu-id="0e6e7-147">How to: Implement a form that uses a background operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)
- [<span data-ttu-id="0e6e7-148">.NET Framework を使用したカスタム Windows フォームコントロールの開発</span><span class="sxs-lookup"><span data-stu-id="0e6e7-148">Develop custom Windows Forms controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
