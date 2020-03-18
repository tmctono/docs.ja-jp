---
title: Windows で .NET for Apache Spark アプリケーションをデバッグする
description: Windows で .NET for Apache Spark アプリケーションをデバッグする方法について学習します。
ms.date: 01/29/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: dac6aed1f7faba7f07b722a6dac0da930ab9ec66
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "79185805"
---
# <a name="debug-a-net-for-apache-spark-application"></a><span data-ttu-id="ca9c4-103">.NET for Apache Spark アプリケーションをデバッグする</span><span class="sxs-lookup"><span data-stu-id="ca9c4-103">Debug a .NET for Apache Spark application</span></span>

<span data-ttu-id="ca9c4-104">このハウツーでは、Windows 上で .NET for Apache Spark アプリケーションをデバッグするための手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca9c4-104">This how-to provides the steps to debug your .NET for Apache Spark application on Windows.</span></span>

## <a name="debug-your-application"></a><span data-ttu-id="ca9c4-105">アプリケーションをデバッグする</span><span class="sxs-lookup"><span data-stu-id="ca9c4-105">Debug your application</span></span>

<span data-ttu-id="ca9c4-106">新しいコマンド プロンプト ウィンドウを開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ca9c4-106">Open a new command prompt window and run the following command:</span></span>

```shell
spark-submit \
  --class org.apache.spark.deploy.dotnet.DotnetRunner \
  --master local \
  <path-to-microsoft-spark-jar> \
  debug
```

<span data-ttu-id="ca9c4-107">このコマンドを実行すると、次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca9c4-107">When you run the command, you see the following output:</span></span>

```console
***********************************************************************
* .NET Backend running debug mode. Press enter to exit *
***********************************************************************
```

<span data-ttu-id="ca9c4-108">デバッグ モードでは、DotnetRunner によって .NET アプリケーションが起動されることはなく、代わりにユーザーが .NET アプリを起動するのを待機します。</span><span class="sxs-lookup"><span data-stu-id="ca9c4-108">In debug mode, DotnetRunner does not launch the .NET application, but instead waits for you to start the .NET app.</span></span> <span data-ttu-id="ca9c4-109">このコマンド プロンプト ウィンドウを開いたままにして、C# デバッガーを使用して .NET アプリケーションを起動し、アプリケーションをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="ca9c4-109">Leave this command prompt window open and start your .NET application through C# debugger to debug your application.</span></span> <span data-ttu-id="ca9c4-110">C# デバッガー ([Windows または macOS 用 Visual Studio デバッガー](https://visualstudio.microsoft.com/vs/)、または [Visual Studio Code の C# デバッガー拡張機能](https://code.visualstudio.com/Docs/editor/debugging)) を使用して .NET アプリケーションを起動し、アプリケーションをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="ca9c4-110">Start your .NET application with a C# debugger ([Visual Studio Debugger for Windows/macOS](https://visualstudio.microsoft.com/vs/) or [C# Debugger Extension in Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging)) to debug your application.</span></span>

## <a name="debug-a-user-defined-function-udf"></a><span data-ttu-id="ca9c4-111">ユーザー定義関数 (UDF) をデバッグする</span><span class="sxs-lookup"><span data-stu-id="ca9c4-111">Debug a user-defined function (UDF)</span></span>

> [!NOTE]
> <span data-ttu-id="ca9c4-112">ユーザー定義関数は、Windows で Visual Studio デバッガーを使用する場合にのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="ca9c4-112">User-defined functions are supported only on Windows with Visual Studio Debugger.</span></span>

<span data-ttu-id="ca9c4-113">`spark-submit` を実行する前に、次の環境変数を設定します。</span><span class="sxs-lookup"><span data-stu-id="ca9c4-113">Before running `spark-submit`, set the following environment variable:</span></span>

```bat
set DOTNET_WORKER_DEBUG=1
```

<span data-ttu-id="ca9c4-114">Spark アプリケーションを実行すると、`Choose Just-In-Time Debugger` ウィンドウがポップアップ表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca9c4-114">When you run your Spark application, a `Choose Just-In-Time Debugger` window will pop up.</span></span> <span data-ttu-id="ca9c4-115">Visual Studio デバッガーを選択してください。</span><span class="sxs-lookup"><span data-stu-id="ca9c4-115">Choose a Visual Studio debugger.</span></span>

<span data-ttu-id="ca9c4-116">デバッガーは、[TaskRunner.cs](https://github.com/dotnet/spark/blob/5e9c08b430b4bc56b5f42252c4b73437377afaed/src/csharp/Microsoft.Spark.Worker/TaskRunner.cs#L52) 内の次の場所で中断します。</span><span class="sxs-lookup"><span data-stu-id="ca9c4-116">The debugger will break at the following location in [TaskRunner.cs](https://github.com/dotnet/spark/blob/5e9c08b430b4bc56b5f42252c4b73437377afaed/src/csharp/Microsoft.Spark.Worker/TaskRunner.cs#L52):</span></span>

```csharp
if (EnvironmentUtils.GetEnvironmentVariableAsBool("DOTNET_WORKER_DEBUG"))
{
    Debugger.Launch(); // <-- The debugger will break here.
}
```

<span data-ttu-id="ca9c4-117">デバッグする予定の UDF が含まれている *.cs* ファイルに移動し、[ブレークポイントを設定します](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints?view=vs-2019)。</span><span class="sxs-lookup"><span data-stu-id="ca9c4-117">Navigate to the *.cs* file that contains the UDF that you plan to debug, and [set a breakpoint](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints?view=vs-2019).</span></span> <span data-ttu-id="ca9c4-118">UDF を含むアセンブリがまだワーカーに読み込まれていないため、このブレークポイントでは `The breakpoint will not currently be hit` と表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca9c4-118">The breakpoint will say `The breakpoint will not currently be hit` because the worker hasn't loaded the assembly that contains UDF yet.</span></span>

<span data-ttu-id="ca9c4-119">`F5` キーを押してアプリケーションを続行すれば、最終的にこのブレークポイントはヒットするようになります。</span><span class="sxs-lookup"><span data-stu-id="ca9c4-119">Hit `F5` to continue your application and the breakpoint will eventually be hit.</span></span>

> [!NOTE]
> <span data-ttu-id="ca9c4-120">[Just-In-Time デバッガーを選択する] ウィンドウは、タスクごとにポップアップ表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca9c4-120">The Choose Just-In-Time Debugger window pops up for each task.</span></span> <span data-ttu-id="ca9c4-121">過剰なポップアップを回避するには、Executor の数を小さい数に設定します。</span><span class="sxs-lookup"><span data-stu-id="ca9c4-121">To avoid excessive pop-ups, set the number of executors to a low number.</span></span> <span data-ttu-id="ca9c4-122">たとえば、spark-submit に対して **--master local[1]** オプションを指定し、タスク数を 1 に設定できます。これにより、1 つのデバッガー インスタンスが起動されます。</span><span class="sxs-lookup"><span data-stu-id="ca9c4-122">For example, you can use the **--master local[1]** option for spark-submit to set the number of tasks to 1, which launches a single debugger instance.</span></span>

## <a name="debug-scala-code"></a><span data-ttu-id="ca9c4-123">Scala コードをデバッグする</span><span class="sxs-lookup"><span data-stu-id="ca9c4-123">Debug Scala code</span></span>

<span data-ttu-id="ca9c4-124">Scala 側のコード (`DotnetRunner`、`DotnetBackendHandler` など) をデバッグする必要がある場合は、次のコマンドを使い、[IntelliJ](https://www.jetbrains.com/help/idea/attaching-to-local-process.html) を使用して実行中のプロセスにデバッガーをアタッチできます。</span><span class="sxs-lookup"><span data-stu-id="ca9c4-124">If you need to debug the Scala-side code (`DotnetRunner`, `DotnetBackendHandler`, etc.), you can use the following command and attach a debugger to the running process using [IntelliJ](https://www.jetbrains.com/help/idea/attaching-to-local-process.html):</span></span>

```shell
spark-submit \
  --driver-java-options -agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=5005 \
  --class org.apache.spark.deploy.dotnet.DotnetRunner \
  --master local \
  <path-to-microsoft-spark-jar> \
  <path-to-your-app-exe> <argument(s)-to-your-app>
```

<span data-ttu-id="ca9c4-125">コマンドを実行した後、[Intellij](https://www.jetbrains.com/help/idea/attaching-to-local-process.html) を使用して実行中のプロセスにデバッガーを追加します。</span><span class="sxs-lookup"><span data-stu-id="ca9c4-125">After you run the command, attach a debugger to the running process using [Intellij](https://www.jetbrains.com/help/idea/attaching-to-local-process.html).</span></span>

## <a name="next-steps"></a><span data-ttu-id="ca9c4-126">次のステップ</span><span class="sxs-lookup"><span data-stu-id="ca9c4-126">Next steps</span></span>

* [<span data-ttu-id="ca9c4-127">.NET for Apache Spark の概要</span><span class="sxs-lookup"><span data-stu-id="ca9c4-127">Get started with .NET for Apache Spark</span></span>](../tutorials/get-started.md)
* [<span data-ttu-id="ca9c4-128">.NET for Apache Spark アプリケーションを Azure HDInsight にデプロイする</span><span class="sxs-lookup"><span data-stu-id="ca9c4-128">Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>](../tutorials/hdinsight-deployment.md)
* [<span data-ttu-id="ca9c4-129">.NET for Apache Spark アプリケーションを Databricks にデプロイする</span><span class="sxs-lookup"><span data-stu-id="ca9c4-129">Deploy a .NET for Apache Spark application to Databricks</span></span>](../tutorials/databricks-deployment.md)
* [<span data-ttu-id="ca9c4-130">.NET for Apache Spark アプリケーションを Amazon EMR Spark にデプロイする</span><span class="sxs-lookup"><span data-stu-id="ca9c4-130">Deploy a .NET for Apache Spark application to Amazon EMR Spark</span></span>](../tutorials/amazon-emr-spark-deployment.md)
