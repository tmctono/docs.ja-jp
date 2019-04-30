---
title: close と abort を使用して WCF クライアントのリソースを解放する
description: Dispose は失敗し、ネットワークが失敗したときに例外をスローすることができます。 動作が望ましくない可能性があります。 代わりに、閉じるを使用し、ネットワークが失敗したときに、クライアントのリソースを解放する中止します。
ms.date: 11/12/2018
ms.assetid: aff82a8d-933d-4bdc-b0c2-c2f7527204fb
ms.openlocfilehash: 58f828d9cd85806f5f04c349a7de18828ab5f6f2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62007574"
---
# <a name="close-and-abort-release-resources-safely-when-network-connections-have-dropped"></a><span data-ttu-id="4cc19-105">終了、中止のネットワーク接続が削除されるときに安全に、リソースを解放</span><span class="sxs-lookup"><span data-stu-id="4cc19-105">Close and Abort release resources safely when network connections have dropped</span></span>

<span data-ttu-id="4cc19-106">このサンプルを使用して、`Close`と`Abort`型指定されたクライアントを使用する場合は、リソースをクリーンアップする方法。</span><span class="sxs-lookup"><span data-stu-id="4cc19-106">This sample demonstrates using the `Close` and `Abort` methods to clean up resources when using a typed client.</span></span> <span data-ttu-id="4cc19-107">`using`ステートメントでは、ネットワーク接続が堅牢なときに例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="4cc19-107">The `using` statement causes exceptions when the network connection is not robust.</span></span> <span data-ttu-id="4cc19-108">このサンプルがに基づいて、 [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md)電卓サービスを実装します。</span><span class="sxs-lookup"><span data-stu-id="4cc19-108">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="4cc19-109">この例では、クライアントはコンソール アプリケーション (.exe) であり、サービスはインターネット インフォメーション サービス (IIS) によってホストされます。</span><span class="sxs-lookup"><span data-stu-id="4cc19-109">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>

> [!NOTE]
> <span data-ttu-id="4cc19-110">このサンプルのセットアップ手順とビルド手順については、このトピックの最後を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cc19-110">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="4cc19-111">このサンプルでは、C# の "using" ステートメントを型指定のあるクライアントと共に使用する際に発生する 2 つの一般的な問題と、例外が発生した後に正しくクリーンアップするコードを示します。</span><span class="sxs-lookup"><span data-stu-id="4cc19-111">This sample shows two of the common problems that occur when using the C# "using" statement with typed clients, as well as code that correctly cleans up after exceptions.</span></span>

<span data-ttu-id="4cc19-112">C# の "using" ステートメントにより `Dispose`() が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4cc19-112">The C# "using" statement results in a call to `Dispose`().</span></span> <span data-ttu-id="4cc19-113">これは `Close`() と同じで、ネットワーク エラーが発生したときに例外をスローする場合があります。</span><span class="sxs-lookup"><span data-stu-id="4cc19-113">This is the same as `Close`(), which may throw exceptions when a network error occurs.</span></span> <span data-ttu-id="4cc19-114">`Dispose`() への呼び出しは、"using" ブロックの閉じかっこで暗黙的に発生するので、コードを記述するユーザーとコードを読み取るユーザーの両者が、これを例外の発生元と気付かない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4cc19-114">Because the call to `Dispose`() happens implicitly at the closing brace of the "using" block, this source of exceptions is likely to go unnoticed both by people writing the code and reading the code.</span></span> <span data-ttu-id="4cc19-115">これは、アプリケーション エラーの潜在的な原因となります。</span><span class="sxs-lookup"><span data-stu-id="4cc19-115">This represents a potential source of application errors.</span></span>

<span data-ttu-id="4cc19-116">最初の問題は、次の `DemonstrateProblemUsingCanThrow` メソッドに示すように、閉じかっこで例外がスローされるとその後のコードが実行されないことです。</span><span class="sxs-lookup"><span data-stu-id="4cc19-116">The first problem, illustrated in the `DemonstrateProblemUsingCanThrow` method, is that the closing brace throws an exception and the code after the closing brace does not execute:</span></span>

```csharp
using (CalculatorClient client = new CalculatorClient())
{
    ...
} // <-- this line might throw
Console.WriteLine("Hope this code wasn't important, because it might not happen.");
```

<span data-ttu-id="4cc19-117">using ブロック内部からスローされる例外がない場合、または using ブロック内のすべての例外がキャッチされた場合でも、`Console.WriteLine` は発生しません。閉じかっこでの `Dispose`() の暗黙の呼び出しによって例外がスローされるためです。</span><span class="sxs-lookup"><span data-stu-id="4cc19-117">Even if nothing inside the using block throws an exception or all exceptions inside the using block are caught, the `Console.WriteLine` might not happen because the implicit `Dispose`() call at the closing brace might throw an exception.</span></span>

<span data-ttu-id="4cc19-118">2 番目の問題は、次の `DemonstrateProblemUsingCanThrowAndMask` メソッドで示すように、閉じかっこで別の例外が暗黙的にスローされる点です。</span><span class="sxs-lookup"><span data-stu-id="4cc19-118">The second problem, illustrated in the `DemonstrateProblemUsingCanThrowAndMask` method, is another implication of the closing brace throwing an exception:</span></span>

```csharp
using (CalculatorClient client = new CalculatorClient())
{
    ...
    throw new ApplicationException("Hope this exception was not important, because "+
                                   "it might be masked by the Close exception.");
} // <-- this line might throw an exception.
```

<span data-ttu-id="4cc19-119">`Dispose`() は "最後の" ブロック内で発生するので、`ApplicationException`() が失敗した場合、`Dispose` は using ブロックの外側には表示されません。</span><span class="sxs-lookup"><span data-stu-id="4cc19-119">Because the `Dispose`() occurs inside a "finally" block, the `ApplicationException` is never seen outside the using block if the `Dispose`() fails.</span></span> <span data-ttu-id="4cc19-120">外側のコードで、`ApplicationException` の発生時期を認識できるよう考慮されている場合は、この例外をマスクすると、"using" コンストラクトが問題の原因となる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4cc19-120">If the code outside must know about when the `ApplicationException` occurs, the "using" construct may cause problems by masking this exception.</span></span>

<span data-ttu-id="4cc19-121">最後に、このサンプルでは、`DemonstrateCleanupWithExceptions` で例外が発生した場合に正しくクリーンアップする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4cc19-121">Finally, the sample demonstrates how to clean up correctly when exceptions occur in `DemonstrateCleanupWithExceptions`.</span></span> <span data-ttu-id="4cc19-122">ここでは、try/catch ブロックを使用してエラーを報告し、`Abort` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4cc19-122">This uses a try/catch block to report errors and call `Abort`.</span></span> <span data-ttu-id="4cc19-123">参照してください、[予想例外](../../../../docs/framework/wcf/samples/expected-exceptions.md)クライアントの呼び出しから例外をキャッチする詳細についてはサンプルです。</span><span class="sxs-lookup"><span data-stu-id="4cc19-123">See the [Expected Exceptions](../../../../docs/framework/wcf/samples/expected-exceptions.md) sample for more details about catching exceptions from client calls.</span></span>

```csharp
try
{
    ...
    client.Close();
}
catch (CommunicationException e)
{
    ...
    client.Abort();
}
catch (TimeoutException e)
{
    ...
    client.Abort();
}
catch (Exception e)
{
    ...
    client.Abort();
    throw;
}
```

> [!NOTE]
> <span data-ttu-id="4cc19-124">ステートメントと ServiceHost を使用します。多くの自己ホスト アプリケーションでは、サービスをホストして少々、ServiceHost.Close がほとんどこのようなアプリケーションを使用して、安全に使用できるように、例外がスロー ステートメントを ServiceHost と共にします。</span><span class="sxs-lookup"><span data-stu-id="4cc19-124">The using statement and ServiceHost: Many self-hosting applications do little more than host a service, and ServiceHost.Close rarely throws an exception, so such applications can safely use the using statement with ServiceHost.</span></span> <span data-ttu-id="4cc19-125">ただし、ServiceHost.Close では `CommunicationException` がスローされる場合があることに注意してください。したがって、ServiceHost を閉じた後でアプリケーションを続行する場合は、using ステートメントを使用せずに前のパターンに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cc19-125">However, be aware that ServiceHost.Close can throw a `CommunicationException`, so if your application continues after closing the ServiceHost, you should avoid the using statement and follow the pattern previously given.</span></span>

<span data-ttu-id="4cc19-126">このサンプルを実行すると、操作応答と例外がクライアントのコンソール ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4cc19-126">When you run the sample, the operation responses and exceptions are displayed in the client console window.</span></span>

<span data-ttu-id="4cc19-127">クライアント プロセスでは 3 つのシナリオが実行されます。各シナリオでは `Divide` の呼び出しが試行されます。</span><span class="sxs-lookup"><span data-stu-id="4cc19-127">The client process runs three scenarios, each of which attempts to call `Divide`.</span></span> <span data-ttu-id="4cc19-128">最初のシナリオでは、`Dispose`() からの例外のためにスキップされるコードを示します。</span><span class="sxs-lookup"><span data-stu-id="4cc19-128">The first scenario demonstrates code being skipped because of an exception from `Dispose`().</span></span> <span data-ttu-id="4cc19-129">2 番目のシナリオでは、`Dispose`() からの例外のためにマスクされる重要な例外を示します。</span><span class="sxs-lookup"><span data-stu-id="4cc19-129">The second scenario demonstrates an important exception being masked because of an exception from `Dispose`().</span></span> <span data-ttu-id="4cc19-130">3 番目のシナリオでは、正しいクリーンアップを示します。</span><span class="sxs-lookup"><span data-stu-id="4cc19-130">The third scenario demonstrates correct clean up.</span></span>

<span data-ttu-id="4cc19-131">クライアント プロセスから予期される出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4cc19-131">The expected output from the client process is:</span></span>

```
=
= Demonstrating problem:  closing brace of using statement can throw.
=
Got System.ServiceModel.CommunicationException from Divide.
Got System.ServiceModel.Security.MessageSecurityException
=
= Demonstrating problem:  closing brace of using statement can mask other Exceptions.
=
Got System.ServiceModel.CommunicationException from Divide.
Got System.ServiceModel.Security.MessageSecurityException
=
= Demonstrating cleanup with Exceptions.
=
Calling client.Add(0.0, 0.0);
        client.Add(0.0, 0.0); returned 0
Calling client.Divide(0.0, 0.0);
Got System.ServiceModel.CommunicationException from Divide.

Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="4cc19-132">サンプルをセットアップ、ビルド、および実行するには</span><span class="sxs-lookup"><span data-stu-id="4cc19-132">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="4cc19-133">実行したことを確認、 [Windows Communication Foundation サンプルの 1 回限りのセットアップ手順](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="4cc19-133">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="4cc19-134">ソリューションの C# 版または Visual Basic .NET 版をビルドするには、「 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="4cc19-134">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

3. <span data-ttu-id="4cc19-135">1 つまたは複数コンピュータ構成では、サンプルを実行する手順については、 [Windows Communication Foundation サンプルの実行](../../../../docs/framework/wcf/samples/running-the-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="4cc19-135">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4cc19-136">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="4cc19-136">The samples may already be installed on your machine.</span></span> <span data-ttu-id="4cc19-137">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4cc19-137">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="4cc19-138">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="4cc19-138">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4cc19-139">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="4cc19-139">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\UsingUsing`
