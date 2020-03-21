---
title: コントロールへのスレッド セーフな呼び出しを行う
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
ms.openlocfilehash: 365b1acb693b9ff2be603a3e659ed8d846a7696a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142005"
---
# <a name="how-to-make-thread-safe-calls-to-windows-forms-controls"></a><span data-ttu-id="a8571-102">方法 : Windows フォーム コントロールをスレッド セーフに呼び出す</span><span class="sxs-lookup"><span data-stu-id="a8571-102">How to: Make thread-safe calls to Windows Forms controls</span></span>

<span data-ttu-id="a8571-103">マルチスレッド化は Windows フォーム アプリのパフォーマンスを向上させることができますが、Windows フォーム コントロールへのアクセスは本質的にスレッド セーフではありません。</span><span class="sxs-lookup"><span data-stu-id="a8571-103">Multithreading can improve the performance of Windows Forms apps, but access to Windows Forms controls isn't inherently thread-safe.</span></span> <span data-ttu-id="a8571-104">マルチスレッド化は、コードを非常に深刻で複雑なバグにさらす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a8571-104">Multithreading can expose your code to very serious and complex bugs.</span></span> <span data-ttu-id="a8571-105">コントロールを操作する 2 つ以上のスレッドが、コントロールを強制的に不整合状態にし、競合状態、デッドロック、フリーズまたはハングを引き起こす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a8571-105">Two or more threads manipulating a control can force the control into an inconsistent state and lead to race conditions, deadlocks, and freezes or hangs.</span></span> <span data-ttu-id="a8571-106">アプリにマルチスレッドを実装する場合は、スレッド セーフな方法でスレッド間コントロールを呼び出してください。</span><span class="sxs-lookup"><span data-stu-id="a8571-106">If you implement multithreading in your app, be sure to call cross-thread controls in a thread-safe way.</span></span> <span data-ttu-id="a8571-107">詳細については、「マネージ[スレッド化のベスト プラクティス」を参照してください](../../../standard/threading/managed-threading-best-practices.md)。</span><span class="sxs-lookup"><span data-stu-id="a8571-107">For more information, see [Managed threading best practices](../../../standard/threading/managed-threading-best-practices.md).</span></span>

<span data-ttu-id="a8571-108">そのコントロールを作成していないスレッドから Windows フォーム コントロールを安全に呼び出す方法は 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="a8571-108">There are two ways to safely call a Windows Forms control from a thread that didn't create that control.</span></span> <span data-ttu-id="a8571-109">このメソッドを<xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName>使用して、メイン スレッドで作成されたデリゲートを呼び出し、そのデリゲートを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="a8571-109">You can use the <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> method to call a delegate created in the main thread, which in turn calls the control.</span></span> <span data-ttu-id="a8571-110">または、イベント駆動モデルを<xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>使用して、バックグラウンド スレッドで実行された作業と結果のレポートを区別する を実装できます。</span><span class="sxs-lookup"><span data-stu-id="a8571-110">Or, you can implement a <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>, which uses an event-driven model to separate work done in the background thread from reporting on the results.</span></span>

## <a name="unsafe-cross-thread-calls"></a><span data-ttu-id="a8571-111">安全でないスレッド間呼び出し</span><span class="sxs-lookup"><span data-stu-id="a8571-111">Unsafe cross-thread calls</span></span>

<span data-ttu-id="a8571-112">コントロールを作成しなかったスレッドから直接コントロールを呼び出すのは安全ではありません。</span><span class="sxs-lookup"><span data-stu-id="a8571-112">It's unsafe to call a control directly from a thread that didn't create it.</span></span> <span data-ttu-id="a8571-113">次のコード スニペットは、コントロールへの安全でない<xref:System.Windows.Forms.TextBox?displayProperty=nameWithType>呼び出しを示しています。</span><span class="sxs-lookup"><span data-stu-id="a8571-113">The following code snippet illustrates an unsafe call to the <xref:System.Windows.Forms.TextBox?displayProperty=nameWithType> control.</span></span> <span data-ttu-id="a8571-114">イベント`Button1_Click`ハンドラーは、メイン`WriteTextUnsafe`スレッドの<xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType>プロパティを直接設定する新しいスレッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="a8571-114">The `Button1_Click` event handler creates a new `WriteTextUnsafe` thread, which sets the main thread's <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> property directly.</span></span>

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

<span data-ttu-id="a8571-115">Visual Studio デバッガーは、メッセージを持つを発生<xref:System.InvalidOperationException>させることによってこれらの安全でないスレッドの呼び出しを検出します,**スレッド間操作が無効です。作成されたスレッド以外のスレッドからアクセスされるコントロール "" 。**</span><span class="sxs-lookup"><span data-stu-id="a8571-115">The Visual Studio debugger detects these unsafe thread calls by raising an <xref:System.InvalidOperationException> with the message, **Cross-thread operation not valid. Control "" accessed from a thread other than the thread it was created on.**</span></span> <span data-ttu-id="a8571-116">常<xref:System.InvalidOperationException>に、Visual Studio のデバッグ中に安全でないスレッド間呼び出しに発生し、アプリの実行時に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a8571-116">The <xref:System.InvalidOperationException> always occurs for unsafe cross-thread calls during Visual Studio debugging, and may occur at app runtime.</span></span> <span data-ttu-id="a8571-117">この問題は修正する必要がありますが、プロパティを に設定することで例外<xref:System.Windows.Forms.Control.CheckForIllegalCrossThreadCalls%2A?displayProperty=nameWithType>を無効`false`にできます。</span><span class="sxs-lookup"><span data-stu-id="a8571-117">You should fix the issue, but you can disable the exception by setting the <xref:System.Windows.Forms.Control.CheckForIllegalCrossThreadCalls%2A?displayProperty=nameWithType> property to `false`.</span></span>

## <a name="safe-cross-thread-calls"></a><span data-ttu-id="a8571-118">安全なスレッド間呼び出し</span><span class="sxs-lookup"><span data-stu-id="a8571-118">Safe cross-thread calls</span></span>

<span data-ttu-id="a8571-119">次のコード例は、Windows フォーム コントロールを作成していないスレッドから安全に呼び出す 2 つの方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a8571-119">The following code examples demonstrate two ways to safely call a Windows Forms control from a thread that didn't create it:</span></span>

1. <span data-ttu-id="a8571-120"><xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName>メイン スレッドからデリゲートを呼び出してコントロールを呼び出すメソッド。</span><span class="sxs-lookup"><span data-stu-id="a8571-120">The <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> method, which calls a delegate from the main thread to call the control.</span></span>
2. <span data-ttu-id="a8571-121">イベント<xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>駆動モデルを提供するコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="a8571-121">A <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> component, which offers an event-driven model.</span></span>

<span data-ttu-id="a8571-122">どちらの例でも、バックグラウンド スレッドは 1 秒間スリープして、そのスレッドで実行される作業をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="a8571-122">In both examples, the background thread sleeps for one second to simulate work being done in that thread.</span></span>

<span data-ttu-id="a8571-123">これらの例は、C# または Visual Basic のコマンド ラインから .NET Framework アプリとしてビルドして実行できます。</span><span class="sxs-lookup"><span data-stu-id="a8571-123">You can build and run these examples as .NET Framework apps from the C# or Visual Basic command line.</span></span> <span data-ttu-id="a8571-124">詳細については、「 [csc.exe を使用したコマンド ラインビルド](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)」または「[コマンド ラインからビルドする (Visual Basic)」](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8571-124">For more information, see [Command-line building with csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) or [Build from the command line (Visual Basic)](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span>

<span data-ttu-id="a8571-125">NET Core 3.0 以降では、.NET Core Windows フォーム*\<フォルダー名>.csproj*プロジェクト ファイルを持つフォルダーから Windows .NET Core アプリとしてサンプルをビルドして実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="a8571-125">Starting with .NET Core 3.0, you can also build and run the examples as Windows .NET Core apps from a folder that has a .NET Core Windows Forms *\<folder name>.csproj* project file.</span></span>

## <a name="example-use-the-invoke-method-with-a-delegate"></a><span data-ttu-id="a8571-126">例: デリゲートで Invoke メソッドを使用する</span><span class="sxs-lookup"><span data-stu-id="a8571-126">Example: Use the Invoke method with a delegate</span></span>

<span data-ttu-id="a8571-127">次の例は、Windows フォーム コントロールへのスレッド セーフな呼び出しを保証するためのパターンを示しています。</span><span class="sxs-lookup"><span data-stu-id="a8571-127">The following example demonstrates a pattern for ensuring thread-safe calls to a Windows Forms control.</span></span> <span data-ttu-id="a8571-128">このプロパティは、<xref:System.Windows.Forms.Control.InvokeRequired%2A?displayProperty=fullName>コントロールの作成スレッド ID と呼び出し元のスレッド ID を比較します。</span><span class="sxs-lookup"><span data-stu-id="a8571-128">It queries the <xref:System.Windows.Forms.Control.InvokeRequired%2A?displayProperty=fullName> property, which compares the control's creating thread ID to the calling thread ID.</span></span> <span data-ttu-id="a8571-129">スレッド ID が同じ場合は、コントロールを直接呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a8571-129">If the thread IDs are the same, it calls the control directly.</span></span> <span data-ttu-id="a8571-130">スレッド ID が異なる場合は、メイン<xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=nameWithType>スレッドのデリゲートを使用してメソッドを呼び出し、コントロールを実際に呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a8571-130">If the thread IDs are different, it calls the <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=nameWithType> method with a delegate from the main thread, which makes the actual call to the control.</span></span>

<span data-ttu-id="a8571-131">コントロール`SafeCallDelegate`の<xref:System.Windows.Forms.TextBox.Text%2A>プロパティを<xref:System.Windows.Forms.TextBox>設定できます。</span><span class="sxs-lookup"><span data-stu-id="a8571-131">The `SafeCallDelegate` enables setting the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span> <span data-ttu-id="a8571-132">メソッド`WriteTextSafe`は、<xref:System.Windows.Forms.Control.InvokeRequired%2A>を照会します。</span><span class="sxs-lookup"><span data-stu-id="a8571-132">The `WriteTextSafe` method queries <xref:System.Windows.Forms.Control.InvokeRequired%2A>.</span></span> <span data-ttu-id="a8571-133">が<xref:System.Windows.Forms.Control.InvokeRequired%2A>返`true`された`WriteTextSafe`場合は、 `SafeCallDelegate` <xref:System.Windows.Forms.Control.Invoke%2A>メソッドに渡され、コントロールへの実際の呼び出しが行われます。</span><span class="sxs-lookup"><span data-stu-id="a8571-133">If <xref:System.Windows.Forms.Control.InvokeRequired%2A> returns `true`, `WriteTextSafe` passes the `SafeCallDelegate` to the <xref:System.Windows.Forms.Control.Invoke%2A> method to make the actual call to the control.</span></span> <span data-ttu-id="a8571-134">を<xref:System.Windows.Forms.Control.InvokeRequired%2A>返`false`す`WriteTextSafe`場合は<xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType>、直接を設定します。</span><span class="sxs-lookup"><span data-stu-id="a8571-134">If <xref:System.Windows.Forms.Control.InvokeRequired%2A> returns `false`, `WriteTextSafe` sets the <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> directly.</span></span> <span data-ttu-id="a8571-135">イベント`Button1_Click`ハンドラーは、新しいスレッドを作成`WriteTextSafe`し、メソッドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a8571-135">The `Button1_Click` event handler creates the new thread and runs the `WriteTextSafe` method.</span></span>

 [!code-csharp[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/vb/Form1.vb)]  

## <a name="example-use-a-backgroundworker-event-handler"></a><span data-ttu-id="a8571-136">例: バックグラウンドワーカー イベント ハンドラを使用する</span><span class="sxs-lookup"><span data-stu-id="a8571-136">Example: Use a BackgroundWorker event handler</span></span>

<span data-ttu-id="a8571-137">マルチスレッドを実装する簡単な方法は、イベント<xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>駆動モデルを使用するコンポーネントを使用することです。</span><span class="sxs-lookup"><span data-stu-id="a8571-137">An easy way to implement multithreading is with the <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> component, which uses an event-driven model.</span></span> <span data-ttu-id="a8571-138">バックグラウンド スレッドは、<xref:System.ComponentModel.BackgroundWorker.DoWork?displayProperty=nameWithType>メイン スレッドと対話しないイベントを実行します。</span><span class="sxs-lookup"><span data-stu-id="a8571-138">The background thread runs the <xref:System.ComponentModel.BackgroundWorker.DoWork?displayProperty=nameWithType> event, which doesn't interact with the main thread.</span></span> <span data-ttu-id="a8571-139">メイン スレッドは<xref:System.ComponentModel.BackgroundWorker.ProgressChanged?displayProperty=nameWithType>、<xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted?displayProperty=nameWithType>および イベント ハンドラーを実行し、メイン スレッドのコントロールを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="a8571-139">The main thread runs the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged?displayProperty=nameWithType> and <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted?displayProperty=nameWithType> event handlers, which can call the main thread's controls.</span></span>

<span data-ttu-id="a8571-140">を使用<xref:System.ComponentModel.BackgroundWorker>してスレッド セーフな呼び出しを行うには、バックグラウンド スレッドでメソッドを作成して処理を行い<xref:System.ComponentModel.BackgroundWorker.DoWork>、イベントにバインドします。</span><span class="sxs-lookup"><span data-stu-id="a8571-140">To make a thread-safe call by using <xref:System.ComponentModel.BackgroundWorker>, create a method in the background thread to do the work, and bind it to the <xref:System.ComponentModel.BackgroundWorker.DoWork> event.</span></span> <span data-ttu-id="a8571-141">メイン スレッドに別のメソッドを作成して、バックグラウンド処理の結果を報告し、 または<xref:System.ComponentModel.BackgroundWorker.ProgressChanged><xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>イベントにバインドします。</span><span class="sxs-lookup"><span data-stu-id="a8571-141">Create another method in the main thread to report the results of the background work, and bind it to the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> or <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event.</span></span> <span data-ttu-id="a8571-142">バックグラウンド スレッドを開始するには、<xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A?displayProperty=nameWithType>を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a8571-142">To start the background thread, call <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="a8571-143">この例では、<xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>イベント ハンドラーを使用<xref:System.Windows.Forms.TextBox>してコントロールの<xref:System.Windows.Forms.TextBox.Text%2A>プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="a8571-143">The example uses the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler to set the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span> <span data-ttu-id="a8571-144"><xref:System.ComponentModel.BackgroundWorker.ProgressChanged>イベントの使用例については、を参照してください<xref:System.ComponentModel.BackgroundWorker>。</span><span class="sxs-lookup"><span data-stu-id="a8571-144">For an example using the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event, see <xref:System.ComponentModel.BackgroundWorker>.</span></span>

 [!code-csharp[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/vb/Form1.vb)]  

## <a name="see-also"></a><span data-ttu-id="a8571-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="a8571-145">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- [<span data-ttu-id="a8571-146">方法: 操作をバックグラウンドで実行する</span><span class="sxs-lookup"><span data-stu-id="a8571-146">How to: Run an operation in the background</span></span>](how-to-run-an-operation-in-the-background.md)
- [<span data-ttu-id="a8571-147">方法: バックグラウンド操作を使用するフォームを実装する</span><span class="sxs-lookup"><span data-stu-id="a8571-147">How to: Implement a form that uses a background operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)
- [<span data-ttu-id="a8571-148">.NET Framework を使用したカスタム Windows フォーム コントロールの開発</span><span class="sxs-lookup"><span data-stu-id="a8571-148">Develop custom Windows Forms controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
