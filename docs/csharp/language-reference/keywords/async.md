---
title: async - C# リファレンス
ms.date: 05/22/2017
f1_keywords:
- async_CSharpKeyword
helpviewer_keywords:
- async keyword [C#]
- async method [C#]
- async [C#]
ms.assetid: 16f14f09-b2ce-42c7-a875-e4eca5d50674
ms.openlocfilehash: 92e94d6fe1c07ab5cd8f29d040401a737a1db78e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173654"
---
# <a name="async-c-reference"></a><span data-ttu-id="12732-102">async (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="12732-102">async (C# Reference)</span></span>

<span data-ttu-id="12732-103">`async` 修飾子を使用して、メソッド、[ラムダ式](../../programming-guide/statements-expressions-operators/lambda-expressions.md)、または[匿名メソッド](../operators/delegate-operator.md)が非同期であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="12732-103">Use the `async` modifier to specify that a method, [lambda expression](../../programming-guide/statements-expressions-operators/lambda-expressions.md), or [anonymous method](../operators/delegate-operator.md) is asynchronous.</span></span> <span data-ttu-id="12732-104">この修飾子が使用されているメソッドまたは式を、"*非同期メソッド*" と呼びます。</span><span class="sxs-lookup"><span data-stu-id="12732-104">If you use this modifier on a method or expression, it's referred to as an *async method*.</span></span> <span data-ttu-id="12732-105">次の例では、`ExampleMethodAsync` という名前の非同期メソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="12732-105">The following example defines an async method named `ExampleMethodAsync`:</span></span>
  
```csharp  
public async Task<int> ExampleMethodAsync()  
{  
    // . . . .  
}  
```  

<span data-ttu-id="12732-106">非同期プログラミングに慣れていない場合、または、非同期メソッドで [`await` 演算子](../operators/await.md)を使って、実行時間が長くなる可能性のある処理を、呼び出し元のスレッドをブロックすることなく実行する方法を理解していない場合は、「[async および await を使用した非同期プログラミング](../../programming-guide/concepts/async/index.md)」の概要を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12732-106">If you're new to asynchronous programming or do not understand how an async method uses the [`await` operator](../operators/await.md) to do potentially long-running work without blocking the caller’s thread, read the introduction in [Asynchronous Programming with async and await](../../programming-guide/concepts/async/index.md).</span></span> <span data-ttu-id="12732-107">次のコードは、非同期メソッド内のコードで、<xref:System.Net.Http.HttpClient.GetStringAsync%2a?displayProperty=nameWithType> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="12732-107">The following code is found inside an async method and calls the <xref:System.Net.Http.HttpClient.GetStringAsync%2a?displayProperty=nameWithType> method:</span></span>
  
```csharp  
string contents = await httpClient.GetStringAsync(requestUrl);  
```  
  
<span data-ttu-id="12732-108">非同期メソッドは、最初の `await` 式に到達するまで同期的に実行されますが、この時点で、待機していたタスクが完了するまで中断されます。</span><span class="sxs-lookup"><span data-stu-id="12732-108">An async method runs synchronously until it reaches its first `await` expression, at which point the method is suspended until the awaited task is complete.</span></span> <span data-ttu-id="12732-109">次のセクションの例で示すように、その間はメソッドの呼び出し元に制御が戻ります。</span><span class="sxs-lookup"><span data-stu-id="12732-109">In the meantime, control returns to the caller of the method, as the example in the next section shows.</span></span>  
  
<span data-ttu-id="12732-110">`async` キーワードで修飾されているメソッドに `await` 式またはステートメントが含まれていない場合、メソッドは同期的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="12732-110">If the method that the `async` keyword modifies doesn't contain an `await` expression or statement, the method executes synchronously.</span></span> <span data-ttu-id="12732-111">`await` ステートメントが含まれていない非同期メソッドが存在する場合は、その状態がエラーを示す可能性があるため、コンパイラによって警告が通知されます。</span><span class="sxs-lookup"><span data-stu-id="12732-111">A compiler warning alerts you to any async methods that don't contain `await` statements, because that situation might indicate an error.</span></span> <span data-ttu-id="12732-112">「[コンパイラの警告 (レベル 1) CS4014](../compiler-messages/cs4014.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="12732-112">See [Compiler Warning (level 1) CS4014](../compiler-messages/cs4014.md).</span></span>  
  
 <span data-ttu-id="12732-113">`async` は、メソッド、ラムダ式、または匿名メソッドを修飾する場合にのみキーワードとなるため、コンテキスト キーワードです。</span><span class="sxs-lookup"><span data-stu-id="12732-113">The `async` keyword is contextual in that it's a keyword only when it modifies a method, a lambda expression, or an anonymous method.</span></span> <span data-ttu-id="12732-114">それ以外の場合は、識別子として解釈されます。</span><span class="sxs-lookup"><span data-stu-id="12732-114">In all other contexts, it's interpreted as an identifier.</span></span>  
  
## <a name="example"></a><span data-ttu-id="12732-115">例</span><span class="sxs-lookup"><span data-stu-id="12732-115">Example</span></span>  
<span data-ttu-id="12732-116">次の例は、非同期のイベント ハンドラー `StartButton_Click` と非同期メソッド `ExampleMethodAsync` との間の制御構造および制御フローを示しています。</span><span class="sxs-lookup"><span data-stu-id="12732-116">The following example shows the structure and flow of control between an async event handler, `StartButton_Click`, and an async method, `ExampleMethodAsync`.</span></span> <span data-ttu-id="12732-117">非同期メソッドの結果は、Web ページの文字数です。</span><span class="sxs-lookup"><span data-stu-id="12732-117">The result from the async method is the number of characters of a web page.</span></span> <span data-ttu-id="12732-118">このコードは、Visual Studio で Windows Presentation Foundation (WPF) アプリまたは Windows ストア アプリを作成する場合に適しています。アプリの設定に関するコード内のコメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="12732-118">The code is suitable for a Windows Presentation Foundation (WPF) app or Windows Store app that you create in Visual Studio; see the code comments for setting up the app.</span></span>  

<span data-ttu-id="12732-119">このコードは、Visual Studio で、Windows Presentation Foundation (WPF) アプリまたは Windows ストア アプリとして実行できます。</span><span class="sxs-lookup"><span data-stu-id="12732-119">You can run this code in Visual Studio as a Windows Presentation Foundation (WPF) app or a Windows Store app.</span></span> <span data-ttu-id="12732-120">`StartButton` という名前のボタン コントロールと、`ResultsTextBox` という名前のテキストボックス コントロールが必要です。</span><span class="sxs-lookup"><span data-stu-id="12732-120">You need a Button control named `StartButton` and a Textbox control named `ResultsTextBox`.</span></span> <span data-ttu-id="12732-121">次のように、名前とハンドラーを必ず設定してください。</span><span class="sxs-lookup"><span data-stu-id="12732-121">Remember to set the names and handler so that you have something like this:</span></span>  

```xaml
<Button Content="Button" HorizontalAlignment="Left" Margin="88,77,0,0" VerticalAlignment="Top" Width="75"  
        Click="StartButton_Click" Name="StartButton"/>  
<TextBox HorizontalAlignment="Left" Height="137" Margin="88,140,0,0" TextWrapping="Wrap"
         Text="&lt;Enter a URL&gt;" VerticalAlignment="Top" Width="310" Name="ResultsTextBox"/>  
```
  
<span data-ttu-id="12732-122">WPF アプリとしてコードを実行するには:</span><span class="sxs-lookup"><span data-stu-id="12732-122">To run the code as a WPF app:</span></span>  

- <span data-ttu-id="12732-123">次のコードを、MainWindow.xaml.cs の `MainWindow` クラスに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="12732-123">Paste this code into the `MainWindow` class in MainWindow.xaml.cs.</span></span>  
- <span data-ttu-id="12732-124">System.Net.Http に対する参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="12732-124">Add a reference to System.Net.Http.</span></span>  
- <span data-ttu-id="12732-125">System.Net.Http に対する `using` ディレクティブを追加します。</span><span class="sxs-lookup"><span data-stu-id="12732-125">Add a `using` directive for System.Net.Http.</span></span>  
  
<span data-ttu-id="12732-126">Windows ストア アプリとしてコードを実行するには:</span><span class="sxs-lookup"><span data-stu-id="12732-126">To run the code as a Windows Store app:</span></span>  

- <span data-ttu-id="12732-127">次のコードを、MainPage.xaml.cs の `MainPage` クラスに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="12732-127">Paste this code into the `MainPage` class in MainPage.xaml.cs.</span></span>  
- <span data-ttu-id="12732-128">System.Net.Http と System.Threading.Tasks に対する using ディレクティブを追加します。</span><span class="sxs-lookup"><span data-stu-id="12732-128">Add using directives for System.Net.Http and System.Threading.Tasks.</span></span>  
  
[!code-csharp[wpf-async](../../../../samples/snippets/csharp/language-reference/keywords/async/wpf/mainwindow.xaml.cs#1)]
  
> [!IMPORTANT]
> <span data-ttu-id="12732-129">タスクの詳細、およびタスクを待機している間に実行されるコードの詳細については、「[Async および Await を使用した非同期プログラミング](../../programming-guide/concepts/async/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="12732-129">For more information about tasks and the code that executes while waiting for a task, see [Asynchronous Programming with async and await](../../programming-guide/concepts/async/index.md).</span></span> <span data-ttu-id="12732-130">同様の要素を使用する WPF 例の完全版については、「[チュートリアル: Async と Await を使用した Web へのアクセス](../../programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="12732-130">For a full WPF example that uses similar elements, see [Walkthrough: Accessing the Web by Using Async and Await](../../programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span>  
  
## <a name="return-types"></a><span data-ttu-id="12732-131">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="12732-131">Return Types</span></span>  
<span data-ttu-id="12732-132">非同期メソッドの戻り値の型を次に示します。</span><span class="sxs-lookup"><span data-stu-id="12732-132">An async method can have the following return types:</span></span>

- <xref:System.Threading.Tasks.Task>
- <xref:System.Threading.Tasks.Task%601>
- <span data-ttu-id="12732-133">[void](../builtin-types/void.md)。</span><span class="sxs-lookup"><span data-stu-id="12732-133">[void](../builtin-types/void.md).</span></span> <span data-ttu-id="12732-134">`async void` メソッドは、呼び出し元でそれらのメソッドを `await` できず、正常終了またはエラー状態を報告するために別のメカニズムを実装する必要があるため、一般に、イベント ハンドラー以外のコードには推奨されません。</span><span class="sxs-lookup"><span data-stu-id="12732-134">`async void` methods are generally discouraged for code other than event handlers because callers cannot `await` those methods and must implement a different mechanism to report successful completion or error conditions.</span></span>
- <span data-ttu-id="12732-135">C# 7.0 以降、アクセス可能な `GetAwaiter` を持つ任意の型です。</span><span class="sxs-lookup"><span data-stu-id="12732-135">Starting with C# 7.0, any type that has an accessible `GetAwaiter` method.</span></span> <span data-ttu-id="12732-136">`System.Threading.Tasks.ValueTask<TResult>` 型はこの実装例で、</span><span class="sxs-lookup"><span data-stu-id="12732-136">The `System.Threading.Tasks.ValueTask<TResult>` type is one such implementation.</span></span> <span data-ttu-id="12732-137">NuGet パッケージ `System.Threading.Tasks.Extensions` を追加することで使用できます。</span><span class="sxs-lookup"><span data-stu-id="12732-137">It is available by adding the NuGet package `System.Threading.Tasks.Extensions`.</span></span>

<span data-ttu-id="12732-138">非同期メソッドでは [in](./in-parameter-modifier.md)、[ref](./ref.md)、[out](./out-parameter-modifier.md) パラメーターを宣言できません。また、[参照戻り値](../../programming-guide/classes-and-structs/ref-returns.md)を指定することもできません。ただし、これらのパラメーターを持つメソッドを呼び出すことはできます。</span><span class="sxs-lookup"><span data-stu-id="12732-138">The async method can't declare any [in](./in-parameter-modifier.md), [ref](./ref.md) or [out](./out-parameter-modifier.md) parameters, nor can it have a [reference return value](../../programming-guide/classes-and-structs/ref-returns.md), but it can call methods that have such parameters.</span></span>  
  
<span data-ttu-id="12732-139">メソッドの `Task<TResult>`return[ ステートメントで ](./return.md) 型のオペランドを指定している場合、非同期メソッドの戻り値の型として `TResult` を指定します。</span><span class="sxs-lookup"><span data-stu-id="12732-139">You specify `Task<TResult>` as the return type of an async method if the [return](./return.md) statement of the method specifies an operand of type `TResult`.</span></span> <span data-ttu-id="12732-140">メソッドの完了時に意味のある値を返さない場合は、`Task` を使用します。</span><span class="sxs-lookup"><span data-stu-id="12732-140">You use `Task` if no meaningful value is returned when the method is completed.</span></span> <span data-ttu-id="12732-141">これにより、メソッドの呼び出しでは `Task` が返されますが、`Task` の完了時に、`await` を待機している `Task` 式はすべて、`void` に評価されます。</span><span class="sxs-lookup"><span data-stu-id="12732-141">That is, a call to the method returns a `Task`, but when the `Task` is completed, any `await` expression that's awaiting the `Task` evaluates to `void`.</span></span>  
  
<span data-ttu-id="12732-142">戻り値の型 `void` は主として、その戻り値の型が要求されるイベント ハンドラーの定義に使用されます。</span><span class="sxs-lookup"><span data-stu-id="12732-142">You use the `void` return type primarily to define event handlers, which require that return type.</span></span> <span data-ttu-id="12732-143">`void` を返す非同期メソッドの呼び出し元は、このメソッドを待機できず、このメソッドがスローする例外をキャッチできません。</span><span class="sxs-lookup"><span data-stu-id="12732-143">The caller of a `void`-returning async method can't await it and can't catch exceptions that the method throws.</span></span>  

<span data-ttu-id="12732-144">C# 7.0 以降、`GetAwaiter` メソッドを持つ別の型 (通常は値の型) を返して、コードのパフォーマンスが重要なセクションでメモリ割り当てを最小限に抑えます。</span><span class="sxs-lookup"><span data-stu-id="12732-144">Starting with C# 7.0, you return another type, typically a value type, that has a `GetAwaiter` method to minimize memory allocations in performance-critical sections of code.</span></span>

<span data-ttu-id="12732-145">使用例を含む詳細については、「[非同期の戻り値の型](../../programming-guide/concepts/async/async-return-types.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="12732-145">For more information and examples, see [Async Return Types](../../programming-guide/concepts/async/async-return-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12732-146">参照</span><span class="sxs-lookup"><span data-stu-id="12732-146">See also</span></span>

- <xref:System.Runtime.CompilerServices.AsyncStateMachineAttribute>
- [<span data-ttu-id="12732-147">await</span><span class="sxs-lookup"><span data-stu-id="12732-147">await</span></span>](../operators/await.md)
- [<span data-ttu-id="12732-148">チュートリアル: Async と Await を使用した Web へのアクセス</span><span class="sxs-lookup"><span data-stu-id="12732-148">Walkthrough: Accessing the Web by Using Async and Await</span></span>](../../programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)
- [<span data-ttu-id="12732-149">Async および Await を使用した非同期プログラミング</span><span class="sxs-lookup"><span data-stu-id="12732-149">Asynchronous Programming with async and await</span></span>](../../programming-guide/concepts/async/index.md)
