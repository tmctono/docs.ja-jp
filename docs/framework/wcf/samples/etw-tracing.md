---
title: ETW トレース
ms.date: 03/30/2017
ms.assetid: ac99a063-e2d2-40cc-b659-d23c2f783f92
ms.openlocfilehash: a5c2f173978f514aa4627caa476a595d8d45d4f9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051924"
---
# <a name="etw-tracing"></a><span data-ttu-id="cc168-102">ETW トレース</span><span class="sxs-lookup"><span data-stu-id="cc168-102">ETW Tracing</span></span>
<span data-ttu-id="cc168-103">このサンプルでは、Event Tracing for Windows (ETW) と、このサンプルに用意されている `ETWTraceListener` を使用して、エンドツーエンド (E2E) のトレースを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="cc168-103">This sample demonstrates how to implement End-to-End (E2E) tracing using Event Tracing for Windows (ETW) and the `ETWTraceListener` that is provided with this sample.</span></span> <span data-ttu-id="cc168-104">サンプルがに基づいて、 [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) ETW トレースが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cc168-104">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) and includes ETW tracing.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc168-105">このサンプルのセットアップ手順とビルド手順については、このトピックの最後を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc168-105">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="cc168-106">このサンプルに精通していることを前提としています。[トレースとメッセージ ログ](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md)します。</span><span class="sxs-lookup"><span data-stu-id="cc168-106">This sample assumes that you are familiar with [Tracing and Message Logging](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).</span></span>  
  
 <span data-ttu-id="cc168-107"><xref:System.Diagnostics> トレース モデル内の各トレース ソースでは、データのトレース場所とトレース方法を決定するトレース リスナーを複数設定できます。</span><span class="sxs-lookup"><span data-stu-id="cc168-107">Each trace source in the <xref:System.Diagnostics> tracing model can have multiple trace listeners that determine where and how the data is traced.</span></span> <span data-ttu-id="cc168-108">リスナの種類では、トレース データの記録形式が定義されます。</span><span class="sxs-lookup"><span data-stu-id="cc168-108">The type of listener defines the format in which trace data is logged.</span></span> <span data-ttu-id="cc168-109">リスナを構成に追加する方法を、次のコード サンプルに示します。</span><span class="sxs-lookup"><span data-stu-id="cc168-109">The following code sample shows how to add the listener to configuration.</span></span>  
  
```xml  
<system.diagnostics>  
    <sources>  
        <source name="System.ServiceModel"   
             switchValue="Verbose,ActivityTracing"  
             propagateActivity="true">  
            <listeners>  
                <add type=  
                   "System.Diagnostics.DefaultTraceListener"  
                   name="Default">  
                   <filter type="" />  
                </add>  
                <add name="ETW">  
                    <filter type="" />  
                </add>  
            </listeners>  
        </source>  
    </sources>  
    <sharedListeners>  
        <add type=  
            "Microsoft.ServiceModel.Samples.EtwTraceListener, ETWTraceListener"  
            name="ETW" traceOutputOptions="Timestamp">  
            <filter type="" />  
       </add>  
    </sharedListeners>  
</system.diagnostics>  
```  
  
 <span data-ttu-id="cc168-110">このリスナを使用する前に、ETW トレース セッションを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc168-110">Before using this listener, an ETW Trace Session must be started.</span></span> <span data-ttu-id="cc168-111">このセッションは、Logman.exe または Tracelog.exe を使用して開始できます。</span><span class="sxs-lookup"><span data-stu-id="cc168-111">This session can be started by using Logman.exe or Tracelog.exe.</span></span> <span data-ttu-id="cc168-112">このサンプルには、ETW トレース セッションをセットアップするための SetupETW.bat ファイルと、セッションを閉じてログ ファイルを完了するための CleanupETW.bat ファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cc168-112">A SetupETW.bat file is included with this sample so that you can set up the ETW Trace Session along with a CleanupETW.bat file for closing the session and completing the log file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc168-113">このサンプルのセットアップ手順とビルド手順については、このトピックの最後を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc168-113">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span> <span data-ttu-id="cc168-114">これらのツールの詳細については、次を参照してください。 <https://go.microsoft.com/fwlink/?LinkId=56580></span><span class="sxs-lookup"><span data-stu-id="cc168-114">For more information about these tools, see <https://go.microsoft.com/fwlink/?LinkId=56580></span></span>  
  
 <span data-ttu-id="cc168-115">ETWTraceListener を使用する場合、トレースはバイナリの .etl ファイルにログ記録されます。</span><span class="sxs-lookup"><span data-stu-id="cc168-115">When using the ETWTraceListener, traces are logged in binary .etl files.</span></span> <span data-ttu-id="cc168-116">ServiceModel トレースが有効な場合、生成されるすべてのトレースは同じファイルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="cc168-116">With ServiceModel tracing turned on, all generated traces appear in the same file.</span></span> <span data-ttu-id="cc168-117">使用[サービス トレース ビューアー ツール (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) .etl および .svclog ログ ファイルを表示するためです。</span><span class="sxs-lookup"><span data-stu-id="cc168-117">Use [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) for viewing .etl and .svclog log files.</span></span> <span data-ttu-id="cc168-118">このビューアでは、メッセージを送信側から受信側や使用地点までトレースできる、システムのエンドツーエンドのビューが作成されます。</span><span class="sxs-lookup"><span data-stu-id="cc168-118">The viewer creates an end-to-end view of the system that makes it possible to trace a message from its source to its destination and point of consumption.</span></span>  
  
 <span data-ttu-id="cc168-119">ETW トレース リスナは、循環ログをサポートします。</span><span class="sxs-lookup"><span data-stu-id="cc168-119">The ETW Trace Listener supports circular logging.</span></span> <span data-ttu-id="cc168-120">この機能を有効にするには**開始**、**実行**と種類`cmd`コマンド コンソールを起動します。</span><span class="sxs-lookup"><span data-stu-id="cc168-120">To enable this feature, go to **Start**, **Run** and type `cmd` to start a command console.</span></span> <span data-ttu-id="cc168-121">次のコマンドでは、`<logfilename>` パラメータを使用するログ ファイル名に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="cc168-121">In the following command, replace the `<logfilename>` parameter with the name of your log file.</span></span>  
  
```  
logman create trace Wcf -o <logfilename> -p "{411a0819-c24b-428c-83e2-26b41091702e}" -f bincirc -max 1000  
```  
  
 <span data-ttu-id="cc168-122">`-f` スイッチと `-max` スイッチは省略できます。</span><span class="sxs-lookup"><span data-stu-id="cc168-122">The `-f` and `-max` switches are optional.</span></span> <span data-ttu-id="cc168-123">これらのスイッチでは、それぞれバイナリの循環形式と 1000 MB の最大ログ サイズが指定されます。</span><span class="sxs-lookup"><span data-stu-id="cc168-123">They specify the binary circular format and max log size of 1000MB respectively.</span></span> <span data-ttu-id="cc168-124">`-p` スイッチは、トレース プロバイダーを指定する際に使用します。</span><span class="sxs-lookup"><span data-stu-id="cc168-124">The `-p` switch is used to specify the trace provider.</span></span> <span data-ttu-id="cc168-125">この例では、`"{411a0819-c24b-428c-83e2-26b41091702e}"` は "XML ETW サンプル プロバイダー" の GUID です。</span><span class="sxs-lookup"><span data-stu-id="cc168-125">In our example, `"{411a0819-c24b-428c-83e2-26b41091702e}"` is the GUID for "XML ETW Sample Provider".</span></span>  
  
 <span data-ttu-id="cc168-126">セッションを開始するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="cc168-126">To start the session, type in the following command.</span></span>  
  
```  
Logman start Wcf  
```  
  
 <span data-ttu-id="cc168-127">ログ記録を完了したら、次のコマンドを使用してセッションを停止できます。</span><span class="sxs-lookup"><span data-stu-id="cc168-127">After you have finished logging, you can stop the session with the following command.</span></span>  
  
```  
Logman stop Wcf  
```  
  
 <span data-ttu-id="cc168-128">このプロセスの任意のツールで処理できるバイナリの循環ログの生成を含む[サービス トレース ビューアー ツール (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)または Tracerpt します。</span><span class="sxs-lookup"><span data-stu-id="cc168-128">This process generates binary circular logs that you can process with your tool of choice, including [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) or Tracerpt.</span></span>  
  
 <span data-ttu-id="cc168-129">確認することも、[循環トレース](../../../../docs/framework/wcf/samples/circular-tracing.md)循環ログ記録を実行する代替リスナの詳細についてはサンプルです。</span><span class="sxs-lookup"><span data-stu-id="cc168-129">You can also review the [Circular Tracing](../../../../docs/framework/wcf/samples/circular-tracing.md) sample for more information on an alternative listener to perform circular logging.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="cc168-130">サンプルをセットアップ、ビルド、および実行するには</span><span class="sxs-lookup"><span data-stu-id="cc168-130">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="cc168-131">実行済みであるかどうかを必ず、 [Windows Communication Foundation サンプルの 1 回限りのセットアップ手順](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="cc168-131">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="cc168-132">ソリューションをビルドする手順については、 [Windows Communication Foundation サンプルのビルド](../../../../docs/framework/wcf/samples/building-the-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="cc168-132">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cc168-133">RegisterProvider.bat、SetupETW.bat、および CleanupETW.bat コマンドを使用するには、ローカル管理者アカウントで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc168-133">To use the RegisterProvider.bat, SetupETW.bat and CleanupETW.bat commands, you must run under a local administrator account.</span></span> <span data-ttu-id="cc168-134">[!INCLUDE[wv](../../../../includes/wv-md.md)] 以降を使用している場合は、コマンド プロンプトも管理者権限で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc168-134">If you are using [!INCLUDE[wv](../../../../includes/wv-md.md)] or later, you must also run the command prompt with elevated privileges.</span></span> <span data-ttu-id="cc168-135">これを行うには、コマンド プロンプトのアイコンを右クリックし、をクリックして**管理者として実行**します。</span><span class="sxs-lookup"><span data-stu-id="cc168-135">To do so, right-click the command prompt icon, then click **Run as administrator**.</span></span>  
  
3. <span data-ttu-id="cc168-136">サンプルを実行する前に、クライアントとサーバーで RegisterProvider.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="cc168-136">Before running the sample, run RegisterProvider.bat on the client and server.</span></span> <span data-ttu-id="cc168-137">この結果、トレースを生成する ETWTracingSampleLog.etl ファイルがセットアップされます。このトレースはサービス トレース ビューアで読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="cc168-137">This sets up the resulting ETWTracingSampleLog.etl file to generate traces that can be read by the Service Trace Viewer.</span></span> <span data-ttu-id="cc168-138">このファイルは、C:\logs フォルダにあります。</span><span class="sxs-lookup"><span data-stu-id="cc168-138">This file can be found in the C:\logs folder.</span></span> <span data-ttu-id="cc168-139">このフォルダーが存在しない場合はフォルダーを作成する必要があります。作成しない場合、トレースは生成されません。</span><span class="sxs-lookup"><span data-stu-id="cc168-139">If this folder does not exist, it must be created or no traces are generated.</span></span> <span data-ttu-id="cc168-140">次に、クライアント コンピューターとサーバー コンピューターで SetupETW.bat を実行し、ETW トレース セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="cc168-140">Then, run SetupETW.bat on the client and server computers to begin the ETW Trace Session.</span></span> <span data-ttu-id="cc168-141">SetupETW.bat ファイルは、CS\Client フォルダーの下にあります。</span><span class="sxs-lookup"><span data-stu-id="cc168-141">The SetupETW.bat file can be found under the CS\Client folder.</span></span>  
  
4. <span data-ttu-id="cc168-142">1 つまたは複数コンピューター構成では、サンプルを実行する手順については、 [Windows Communication Foundation サンプルの実行](../../../../docs/framework/wcf/samples/running-the-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="cc168-142">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
5. <span data-ttu-id="cc168-143">サンプルの使用が終わったら、CleanupETW.bat を実行して ETWTracingSampleLog.etl ファイルの作成を完了します。</span><span class="sxs-lookup"><span data-stu-id="cc168-143">When the sample is completed, run CleanupETW.bat to complete the creation of the ETWTracingSampleLog.etl file.</span></span>  
  
6. <span data-ttu-id="cc168-144">サービス トレース ビューア内で ETWTracingSampleLog.etl ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="cc168-144">Open the ETWTracingSampleLog.etl file from within the Service Trace Viewer.</span></span> <span data-ttu-id="cc168-145">このバイナリ形式のファイルを .svclog ファイルとして保存するかどうかを尋ねるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cc168-145">You will be prompted to save the binary formatted file as a .svclog file.</span></span>  
  
7. <span data-ttu-id="cc168-146">新しく作成された .svclog ファイルをサービス トレース ビューアー内で開き、ETW トレースと ServiceModel トレースを表示します。</span><span class="sxs-lookup"><span data-stu-id="cc168-146">Open the newly created .svclog file from within the Service Trace Viewer to view the ETW and ServiceModel traces.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cc168-147">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="cc168-147">The samples may already be installed on your computer.</span></span> <span data-ttu-id="cc168-148">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="cc168-148">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="cc168-149">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="cc168-149">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="cc168-150">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="cc168-150">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\AnalyticTrace`  
  
## <a name="see-also"></a><span data-ttu-id="cc168-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="cc168-151">See also</span></span>

- [<span data-ttu-id="cc168-152">AppFabric の監視のサンプル</span><span class="sxs-lookup"><span data-stu-id="cc168-152">AppFabric Monitoring Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193959)
