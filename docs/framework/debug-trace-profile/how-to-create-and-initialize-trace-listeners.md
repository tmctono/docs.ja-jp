---
title: '方法: トレース リスナーを作成し初期化する'
description: .NET で DefaultTraceListener などのクラスを使用して、トレースリスナーを作成および初期化する方法について説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- initializing trace listeners
- trace listeners, creating
- trace listeners, initializing
- tracing [.NET Framework], trace listeners
- logs, trace listeners
ms.assetid: 21726de1-61ee-4fdc-9dd0-3be49324d066
ms.openlocfilehash: 752306124e41a7fb7458daccc8c2891631eb9616
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051208"
---
# <a name="how-to-create-and-initialize-trace-listeners"></a><span data-ttu-id="659b7-103">方法: トレース リスナーを作成し初期化する</span><span class="sxs-lookup"><span data-stu-id="659b7-103">How to: Create and Initialize Trace Listeners</span></span>

<span data-ttu-id="659b7-104"><xref:System.Diagnostics.Debug?displayProperty=nameWithType> クラスと <xref:System.Diagnostics.Trace?displayProperty=nameWithType> クラスは、メッセージの受け取りと処理を実行する、リスナーと呼ばれるオブジェクトにメッセージを送ります。</span><span class="sxs-lookup"><span data-stu-id="659b7-104">The <xref:System.Diagnostics.Debug?displayProperty=nameWithType> and <xref:System.Diagnostics.Trace?displayProperty=nameWithType> classes send messages to objects called listeners that receive and process these messages.</span></span> <span data-ttu-id="659b7-105">トレースまたはデバッグを有効にすると、こうしたリスナーの 1 つである <xref:System.Diagnostics.DefaultTraceListener?displayProperty=nameWithType> が自動的に作成および初期化されます。</span><span class="sxs-lookup"><span data-stu-id="659b7-105">One such listener, the <xref:System.Diagnostics.DefaultTraceListener?displayProperty=nameWithType>, is automatically created and initialized when tracing or debugging is enabled.</span></span> <span data-ttu-id="659b7-106"><xref:System.Diagnostics.Trace> または <xref:System.Diagnostics.Debug> の出力を別のソースに送るには、別のトレース リスナーを作成して初期化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="659b7-106">If you want <xref:System.Diagnostics.Trace> or <xref:System.Diagnostics.Debug> output to be directed to any additional sources, you must create and initialize additional trace listeners.</span></span>

<span data-ttu-id="659b7-107">作成するリスナーには、アプリケーションのニーズが反映されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="659b7-107">The listeners you create should reflect your application's needs.</span></span> <span data-ttu-id="659b7-108">たとえば、すべてのトレース出力のテキスト レコードが必要である場合は、有効になったときにすべての出力を新しいテキスト ファイルに書き込む <xref:System.Diagnostics.TextWriterTraceListener> リスナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="659b7-108">For example, if you want a text record of all trace output, create a <xref:System.Diagnostics.TextWriterTraceListener> listener, which writes all output to a new text file when it is enabled.</span></span> <span data-ttu-id="659b7-109">一方、アプリケーションの実行時にのみ出力を表示する場合は、すべての出力をコンソール ウィンドウに送る <xref:System.Diagnostics.ConsoleTraceListener> リスナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="659b7-109">On the other hand, if you want to view output only during application execution, create a <xref:System.Diagnostics.ConsoleTraceListener> listener, which directs all output to a console window.</span></span> <span data-ttu-id="659b7-110"><xref:System.Diagnostics.EventLogTraceListener> は、トレース出力をイベント ログに転送することができます。</span><span class="sxs-lookup"><span data-stu-id="659b7-110">The <xref:System.Diagnostics.EventLogTraceListener> can direct trace output to an event log.</span></span> <span data-ttu-id="659b7-111">詳細については、「[トレースリスナー](trace-listeners.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="659b7-111">For more information, see [Trace Listeners](trace-listeners.md).</span></span>

<span data-ttu-id="659b7-112">トレース リスナーは、[アプリケーション構成ファイル](../configure-apps/index.md)またはコードで作成できます。</span><span class="sxs-lookup"><span data-stu-id="659b7-112">You can create trace listeners in an [application configuration file](../configure-apps/index.md) or in your code.</span></span> <span data-ttu-id="659b7-113">アプリケーション構成ファイルではコードを変更せずにトレース リスナーを追加、変更、または削除できるので、アプリケーション構成ファイルを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="659b7-113">We recommend the use of application configuration files, because they let you add, modify, or remove trace listeners without having to change your code.</span></span>

### <a name="to-create-and-use-a-trace-listener-by-using-a-configuration-file"></a><span data-ttu-id="659b7-114">構成ファイルを使用してトレース リスナーを作成して使用するには</span><span class="sxs-lookup"><span data-stu-id="659b7-114">To create and use a trace listener by using a configuration file</span></span>

1. <span data-ttu-id="659b7-115">アプリケーション構成ファイルでトレース リスナーを宣言します。</span><span class="sxs-lookup"><span data-stu-id="659b7-115">Declare your trace listener in your application configuration file.</span></span> <span data-ttu-id="659b7-116">作成しているリスナーで他のオブジェクトが必要な場合は、必要なオブジェクトも宣言します。</span><span class="sxs-lookup"><span data-stu-id="659b7-116">If the listener you are creating requires any other objects, declare them as well.</span></span> <span data-ttu-id="659b7-117">テキスト ファイル `TextWriterOutput.log` への書き込みを実行する `myListener` というリスナーの作成方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="659b7-117">The following example shows how to create a listener called `myListener` that writes to the text file `TextWriterOutput.log`.</span></span>

    ```xml
    <configuration>
      <system.diagnostics>
        <trace autoflush="false" indentsize="4">
          <listeners>
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener" initializeData="TextWriterOutput.log" />
            <remove name="Default" />
          </listeners>
        </trace>
      </system.diagnostics>
    </configuration>
    ```

2. <span data-ttu-id="659b7-118">コードで <xref:System.Diagnostics.Trace> クラスを使用して、メッセージをトレース リスナーに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="659b7-118">Use the <xref:System.Diagnostics.Trace> class in your code to write a message to the trace listeners.</span></span>

    ```vb
    Trace.TraceInformation("Test message.")
    ' You must close or flush the trace to empty the output buffer.
    Trace.Flush()
    ```

    ```csharp
    Trace.TraceInformation("Test message.");
    // You must close or flush the trace to empty the output buffer.
    Trace.Flush();
    ```

### <a name="to-create-and-use-a-trace-listener-in-code"></a><span data-ttu-id="659b7-119">コードでトレース リスナーを作成して使用するには</span><span class="sxs-lookup"><span data-stu-id="659b7-119">To create and use a trace listener in code</span></span>

- <span data-ttu-id="659b7-120">トレース リスナーを <xref:System.Diagnostics.Trace.Listeners%2A> コレクションに追加し、トレース情報をリスナーに送ります。</span><span class="sxs-lookup"><span data-stu-id="659b7-120">Add the trace listener to the <xref:System.Diagnostics.Trace.Listeners%2A> collection and send trace information to the listeners.</span></span>

    ```vb
    Trace.Listeners.Add(New TextWriterTraceListener("TextWriterOutput.log", "myListener"))
    Trace.TraceInformation("Test message.")
    ' You must close or flush the trace to empty the output buffer.
    Trace.Flush()
    ```

    ```csharp
    Trace.Listeners.Add(new TextWriterTraceListener("TextWriterOutput.log", "myListener"));
    Trace.TraceInformation("Test message.");
    // You must close or flush the trace to empty the output buffer.
    Trace.Flush();
    ```

    <span data-ttu-id="659b7-121">\- または</span><span class="sxs-lookup"><span data-stu-id="659b7-121">\- or -</span></span>

- <span data-ttu-id="659b7-122">リスナーがトレース出力を受け取らないようにするには、リスナーを <xref:System.Diagnostics.Trace.Listeners%2A> コレクションに追加しないようにします。</span><span class="sxs-lookup"><span data-stu-id="659b7-122">If you do not want your listener to receive trace output, do not add it to the <xref:System.Diagnostics.Trace.Listeners%2A> collection.</span></span> <span data-ttu-id="659b7-123">リスナー自体の出力メソッドを呼び出すことにより、<xref:System.Diagnostics.Trace.Listeners%2A> コレクションから独立したリスナーを通じて出力を生成できます。</span><span class="sxs-lookup"><span data-stu-id="659b7-123">You can emit output through a listener independent of the <xref:System.Diagnostics.Trace.Listeners%2A> collection by calling the listener's own output methods.</span></span> <span data-ttu-id="659b7-124"><xref:System.Diagnostics.Trace.Listeners%2A> コレクションに属さないリスナーに行を書き込む方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="659b7-124">The following example shows how to write a line to a listener that is not in the <xref:System.Diagnostics.Trace.Listeners%2A> collection.</span></span>

    ```vb
    Dim myListener As New TextWriterTraceListener("TextWriterOutput.log", "myListener")
    myListener.WriteLine("Test message.")
    ' You must close or flush the trace listener to empty the output buffer.
    myListener.Flush()
    ```

    ```csharp
    TextWriterTraceListener myListener = new TextWriterTraceListener("TextWriterOutput.log", "myListener");
    myListener.WriteLine("Test message.");
    // You must close or flush the trace listener to empty the output buffer.
    myListener.Flush();
    ```

## <a name="see-also"></a><span data-ttu-id="659b7-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="659b7-125">See also</span></span>

- [<span data-ttu-id="659b7-126">トレース リスナー</span><span class="sxs-lookup"><span data-stu-id="659b7-126">Trace Listeners</span></span>](trace-listeners.md)
- [<span data-ttu-id="659b7-127">トレース スイッチ</span><span class="sxs-lookup"><span data-stu-id="659b7-127">Trace Switches</span></span>](trace-switches.md)
- [<span data-ttu-id="659b7-128">方法: アプリケーション コードにトレース ステートメントを追加する</span><span class="sxs-lookup"><span data-stu-id="659b7-128">How to: Add Trace Statements to Application Code</span></span>](how-to-add-trace-statements-to-application-code.md)
- [<span data-ttu-id="659b7-129">アプリケーションのトレースとインストルメント</span><span class="sxs-lookup"><span data-stu-id="659b7-129">Tracing and Instrumenting Applications</span></span>](tracing-and-instrumenting-applications.md)
