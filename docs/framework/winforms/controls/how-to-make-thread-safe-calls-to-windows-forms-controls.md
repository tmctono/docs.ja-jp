---
title: '方法: Windows フォーム コントロールのスレッド セーフな呼び出しを行う'
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
ms.openlocfilehash: 3211df1f0e585780039471b80b5b913613ad9bbd
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57714009"
---
# <a name="how-to-make-thread-safe-calls-to-windows-forms-controls"></a><span data-ttu-id="8d444-102">方法: Windows フォーム コントロールのスレッド セーフな呼び出しを行う</span><span class="sxs-lookup"><span data-stu-id="8d444-102">How to: Make thread-safe calls to Windows Forms controls</span></span>

<span data-ttu-id="8d444-103">マルチ スレッドは、Windows フォームのアプリのパフォーマンスを向上させることができますが、Windows フォーム コントロールへのアクセスがスレッド セーフでは本質的にはありません。</span><span class="sxs-lookup"><span data-stu-id="8d444-103">Multithreading can improve the performance of Windows Forms apps, but access to Windows Forms controls isn't inherently thread-safe.</span></span> <span data-ttu-id="8d444-104">マルチ スレッドは、非常に深刻かつ複雑なバグ、コードを公開できます。</span><span class="sxs-lookup"><span data-stu-id="8d444-104">Multithreading can expose your code to very serious and complex bugs.</span></span> <span data-ttu-id="8d444-105">2 つまたは複数のスレッドが、コントロールの操作では、コントロールが不整合な状態に強制的に移動でき、競合状態、デッドロック、およびがフリーズやハングすることができます。</span><span class="sxs-lookup"><span data-stu-id="8d444-105">Two or more threads manipulating a control can force the control into an inconsistent state and lead to race conditions, deadlocks, and freezes or hangs.</span></span> <span data-ttu-id="8d444-106">実装する場合は、マルチ スレッド アプリケーションでは、スレッド セーフな方法で、スレッド間のコントロールを呼び出すことを確認します。</span><span class="sxs-lookup"><span data-stu-id="8d444-106">If you implement multithreading in your app, be sure to call cross-thread controls in a thread-safe way.</span></span> <span data-ttu-id="8d444-107">詳細については、[マネージ スレッド処理のベスト プラクティス](../../../standard/threading/managed-threading-best-practices.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d444-107">For more information, see [Managed threading best practices](../../../standard/threading/managed-threading-best-practices.md).</span></span> 

<span data-ttu-id="8d444-108">Windows フォーム コントロールをそのコントロールを作成していないスレッドから安全に呼び出すに 2 つの方法はあります。</span><span class="sxs-lookup"><span data-stu-id="8d444-108">There are two ways to safely call a Windows Forms control from a thread that didn't create that control.</span></span> <span data-ttu-id="8d444-109">使用することができます、<xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName>コントロールを呼び出し、メイン スレッドで作成したデリゲートを呼び出すメソッド。</span><span class="sxs-lookup"><span data-stu-id="8d444-109">You can use the <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> method to call a delegate created in the main thread, which in turn calls the control.</span></span> <span data-ttu-id="8d444-110">または、実装することができます、<xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>結果のレポートから、バック グラウンド スレッドで実行される作業を分離するにはイベント ドリブン モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="8d444-110">Or, you can implement a <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>, which uses an event-driven model to separate work done in the background thread from reporting on the results.</span></span> 

## <a name="unsafe-cross-thread-calls"></a><span data-ttu-id="8d444-111">安全でないスレッド間の呼び出し</span><span class="sxs-lookup"><span data-stu-id="8d444-111">Unsafe cross-thread calls</span></span>

<span data-ttu-id="8d444-112">コントロールを作成していないスレッドから直接呼び出しは安全ではありません。</span><span class="sxs-lookup"><span data-stu-id="8d444-112">It's unsafe to call a control directly from a thread that didn't create it.</span></span> <span data-ttu-id="8d444-113">次のコード スニペットは、安全でない呼び出しを示しています、<xref:System.Windows.Forms.TextBox?displayProperty=nameWithType>コントロール。</span><span class="sxs-lookup"><span data-stu-id="8d444-113">The following code snippet illustrates an unsafe call to the <xref:System.Windows.Forms.TextBox?displayProperty=nameWithType> control.</span></span> <span data-ttu-id="8d444-114">`Button1_Click`イベント ハンドラーを作成する新しい`WriteTextUnsafe`スレッドで、設定、メイン スレッドの<xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType>プロパティを直接します。</span><span class="sxs-lookup"><span data-stu-id="8d444-114">The `Button1_Click` event handler creates a new `WriteTextUnsafe` thread, which sets the main thread's <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> property directly.</span></span> 

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

<span data-ttu-id="8d444-115">Visual Studio デバッガーは、発生させることによってこれらの安全でないスレッドの呼び出しを検出、<xref:System.InvalidOperationException>メッセージと共に**スレッド間の操作が無効です。コントロール""上で作成されたスレッド以外のスレッドからアクセスします。**</span><span class="sxs-lookup"><span data-stu-id="8d444-115">The Visual Studio debugger detects these unsafe thread calls by raising an <xref:System.InvalidOperationException> with the message, **Cross-thread operation not valid. Control "" accessed from a thread other than the thread it was created on.**</span></span> <span data-ttu-id="8d444-116"><xref:System.InvalidOperationException>常に、Visual Studio のデバッグ時に安全でないスレッド間の呼び出しが発生し、アプリの実行時に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8d444-116">The <xref:System.InvalidOperationException> always occurs for unsafe cross-thread calls during Visual Studio debugging, and may occur at app runtime.</span></span> <span data-ttu-id="8d444-117">問題を修正する必要がありますが、設定して、例外を無効にすることができます、<xref:System.Windows.Forms.Control.CheckForIllegalCrossThreadCalls%2A?displayProperty=nameWithType>プロパティを`false`します。</span><span class="sxs-lookup"><span data-stu-id="8d444-117">You should fix the issue, but you can disable the exception by setting the <xref:System.Windows.Forms.Control.CheckForIllegalCrossThreadCalls%2A?displayProperty=nameWithType> property to `false`.</span></span>

## <a name="safe-cross-thread-calls"></a><span data-ttu-id="8d444-118">スレッド間の安全な呼び出し</span><span class="sxs-lookup"><span data-stu-id="8d444-118">Safe cross-thread calls</span></span> 

<span data-ttu-id="8d444-119">次のコード例は、それを作成していないスレッドから、Windows フォーム コントロールを安全に呼び出す 2 つの方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="8d444-119">The following code examples demonstrate two ways to safely call a Windows Forms control from a thread that didn't create it:</span></span> 
1. <span data-ttu-id="8d444-120"><xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName>メソッドを呼び出すコントロールをメイン スレッドからデリゲートを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8d444-120">The <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> method, which calls a delegate from the main thread to call the control.</span></span> 
2. <span data-ttu-id="8d444-121">A<xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>コンポーネントであり、イベント ドリブン モデルを提供します。</span><span class="sxs-lookup"><span data-stu-id="8d444-121">A <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> component, which offers an event-driven model.</span></span> 

<span data-ttu-id="8d444-122">どちらの例では、シミュレートする 2 番目の 1 つのバック グラウンド スレッド スリープは、そのスレッドで実行されている動作します。</span><span class="sxs-lookup"><span data-stu-id="8d444-122">In both examples, the background thread sleeps for one second to simulate work being done in that thread.</span></span> 

<span data-ttu-id="8d444-123">ビルドしてから、.NET Framework アプリとしてこれらの例を実行することができます、C#または Visual Basic のコマンド ライン。</span><span class="sxs-lookup"><span data-stu-id="8d444-123">You can build and run these examples as .NET Framework apps from the C# or Visual Basic command line.</span></span> <span data-ttu-id="8d444-124">詳細については、[csc.exe を](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)または[(Visual Basic) コマンドラインからビルド](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d444-124">For more information, see [Command-line building with csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) or [Build from the command line (Visual Basic)](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span> 

<span data-ttu-id="8d444-125">.NET Core 3.0 以降では、ことができますもビルドおよび実行する例では、.NET Core アプリを Windows として .NET Core の Windows フォームのあるフォルダーから *\<フォルダー名>.csproj* プロジェクト ファイル。</span><span class="sxs-lookup"><span data-stu-id="8d444-125">Starting with .NET Core 3.0, you can also build and run the examples as Windows .NET Core apps from a folder that has a .NET Core Windows Forms *\<folder name>.csproj* project file.</span></span> 

## <a name="example-use-the-invoke-method-with-a-delegate"></a><span data-ttu-id="8d444-126">例:デリゲートで Invoke メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="8d444-126">Example: Use the Invoke method with a delegate</span></span>

<span data-ttu-id="8d444-127">次の例では、Windows フォーム コントロールのスレッド セーフな呼び出しを確保するためのパターンを示します。</span><span class="sxs-lookup"><span data-stu-id="8d444-127">The following example demonstrates a pattern for ensuring thread-safe calls to a Windows Forms control.</span></span> <span data-ttu-id="8d444-128">これは、クエリを<xref:System.Windows.Forms.Control.InvokeRequired%2A?displayProperty=fullName>コントロールを比較し、プロパティの呼び出し元のスレッド id ですスレッドの ID を作成する。</span><span class="sxs-lookup"><span data-stu-id="8d444-128">It queries the <xref:System.Windows.Forms.Control.InvokeRequired%2A?displayProperty=fullName> property, which compares the control's creating thread ID to the calling thread ID.</span></span> <span data-ttu-id="8d444-129">スレッド Id が同じ場合は、コントロールを直接呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8d444-129">If the thread IDs are the same, it calls the control directly.</span></span> <span data-ttu-id="8d444-130">呼び出しスレッド Id が異なる場合、<xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=nameWithType>コントロールに実際の呼び出し、メイン スレッドからのデリゲート メソッド。</span><span class="sxs-lookup"><span data-stu-id="8d444-130">If the thread IDs are different, it calls the <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=nameWithType> method with a delegate from the main thread, which makes the actual call to the control.</span></span>

<span data-ttu-id="8d444-131">`SafeCallDelegate`設定を有効に、<xref:System.Windows.Forms.TextBox>コントロールの<xref:System.Windows.Forms.TextBox.Text%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="8d444-131">The `SafeCallDelegate` enables setting the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span> <span data-ttu-id="8d444-132">`WriteTextSafe`メソッド クエリ<xref:System.Windows.Forms.Control.InvokeRequired%2A>します。</span><span class="sxs-lookup"><span data-stu-id="8d444-132">The `WriteTextSafe` method queries <xref:System.Windows.Forms.Control.InvokeRequired%2A>.</span></span> <span data-ttu-id="8d444-133">場合<xref:System.Windows.Forms.Control.InvokeRequired%2A>返します`true`、`WriteTextSafe`渡します、`SafeCallDelegate`を<xref:System.Windows.Forms.Control.Invoke%2A>をコントロールには、実際の呼び出しを行うメソッドです。</span><span class="sxs-lookup"><span data-stu-id="8d444-133">If <xref:System.Windows.Forms.Control.InvokeRequired%2A> returns `true`, `WriteTextSafe` passes the `SafeCallDelegate` to the <xref:System.Windows.Forms.Control.Invoke%2A> method to make the actual call to the control.</span></span> <span data-ttu-id="8d444-134">場合<xref:System.Windows.Forms.Control.InvokeRequired%2A>返します`false`、`WriteTextSafe`設定、<xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType>直接します。</span><span class="sxs-lookup"><span data-stu-id="8d444-134">If <xref:System.Windows.Forms.Control.InvokeRequired%2A> returns `false`, `WriteTextSafe` sets the <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> directly.</span></span> <span data-ttu-id="8d444-135">`Button1_Click`イベント ハンドラーが新しいスレッドを作成および実行される、`WriteTextSafe`メソッド。</span><span class="sxs-lookup"><span data-stu-id="8d444-135">The `Button1_Click` event handler creates the new thread and runs the `WriteTextSafe` method.</span></span> 

 [!code-csharp[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/vb/Form1.vb)]  

## <a name="example-use-a-backgroundworker-event-handler"></a><span data-ttu-id="8d444-136">例:BackgroundWorker のイベント ハンドラーを使用します。</span><span class="sxs-lookup"><span data-stu-id="8d444-136">Example: Use a BackgroundWorker event handler</span></span>

<span data-ttu-id="8d444-137">簡単にマルチ スレッドの実装は、<xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>イベント ドリブン モデルを使用して、コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="8d444-137">An easy way to implement multithreading is with the <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> component, which uses an event-driven model.</span></span> <span data-ttu-id="8d444-138">バック グラウンド スレッドが、<xref:System.ComponentModel.BackgroundWorker.DoWork?displayProperty=nameWithType>イベントで、メイン スレッドと対話しません。</span><span class="sxs-lookup"><span data-stu-id="8d444-138">The background thread runs the <xref:System.ComponentModel.BackgroundWorker.DoWork?displayProperty=nameWithType> event, which doesn't interact with the main thread.</span></span> <span data-ttu-id="8d444-139">メイン スレッドが実行され、<xref:System.ComponentModel.BackgroundWorker.ProgressChanged?displayProperty=nameWithType>と<xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted?displayProperty=nameWithType>イベント ハンドラーは、メイン スレッドのコントロールを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="8d444-139">The main thread runs the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged?displayProperty=nameWithType> and <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted?displayProperty=nameWithType> event handlers, which can call the main thread's controls.</span></span>

<span data-ttu-id="8d444-140">使用して、スレッド セーフな呼び出しを行う<xref:System.ComponentModel.BackgroundWorker>、操作を実行するバック グラウンド スレッドでメソッドを作成し、バインドするに、は<xref:System.ComponentModel.BackgroundWorker.DoWork>イベント。</span><span class="sxs-lookup"><span data-stu-id="8d444-140">To make a thread-safe call by using <xref:System.ComponentModel.BackgroundWorker>, create a method in the background thread to do the work, and bind it to the <xref:System.ComponentModel.BackgroundWorker.DoWork> event.</span></span> <span data-ttu-id="8d444-141">バック グラウンド作業の結果を報告するメイン スレッドで別のメソッドを作成しにバインド、<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>または<xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>イベント。</span><span class="sxs-lookup"><span data-stu-id="8d444-141">Create another method in the main thread to report the results of the background work, and bind it to the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> or <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event.</span></span> <span data-ttu-id="8d444-142">バック グラウンド スレッドを開始するには、呼び出す<xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="8d444-142">To start the background thread, call <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A?displayProperty=nameWithType>.</span></span> 

<span data-ttu-id="8d444-143">この例では、<xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>イベント ハンドラーを設定する、<xref:System.Windows.Forms.TextBox>コントロールの<xref:System.Windows.Forms.TextBox.Text%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="8d444-143">The example uses the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler to set the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span> <span data-ttu-id="8d444-144">使用例について、<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>イベントを参照してください<xref:System.ComponentModel.BackgroundWorker>します。</span><span class="sxs-lookup"><span data-stu-id="8d444-144">For an example using the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event, see <xref:System.ComponentModel.BackgroundWorker>.</span></span> 

 [!code-csharp[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/vb/Form1.vb)]  

## <a name="see-also"></a><span data-ttu-id="8d444-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="8d444-145">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- [<span data-ttu-id="8d444-146">方法: バック グラウンドで操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="8d444-146">How to: Run an operation in the background</span></span>](how-to-run-an-operation-in-the-background.md)
- [<span data-ttu-id="8d444-147">方法: バック グラウンド操作を使用してフォームを実装します。</span><span class="sxs-lookup"><span data-stu-id="8d444-147">How to: Implement a form that uses a background operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)
- [<span data-ttu-id="8d444-148">.NET Framework でのカスタムの Windows フォーム コントロールを開発します。</span><span class="sxs-lookup"><span data-stu-id="8d444-148">Develop custom Windows Forms controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
