---
title: 命令型
ms.date: 03/30/2017
ms.assetid: 4f7ce807-c0e4-407a-92a6-22abafb40b51
ms.openlocfilehash: 2484b6a6a8e5a62676eb9e9830a91f91ac923eff
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144683"
---
# <a name="imperative"></a><span data-ttu-id="1363f-102">命令型</span><span class="sxs-lookup"><span data-stu-id="1363f-102">Imperative</span></span>

<span data-ttu-id="1363f-103">このサンプルでは、コードを使用するサービスについて、構成で <xref:System.ServiceModel.WSHttpBinding> バインディングを定義する代わりに `wsHttpBinding` を定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1363f-103">This sample demonstrates how to define a <xref:System.ServiceModel.WSHttpBinding> for a service using code, instead of defining the `wsHttpBinding` binding in configuration.</span></span> <span data-ttu-id="1363f-104">このサンプルは、電卓サービスを実装する[作業の開始](getting-started-sample.md)に基づいています。</span><span class="sxs-lookup"><span data-stu-id="1363f-104">This sample is based on the [Getting Started](getting-started-sample.md) that implements a calculator service.</span></span>

> [!NOTE]
> <span data-ttu-id="1363f-105">このサンプルのセットアップ手順とビルド手順については、このトピックの最後を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1363f-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="1363f-106">次のコードは、バインディングをコードで強制的に定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1363f-106">The following code demonstrates how to define a binding imperatively in code.</span></span>

```csharp
public static void Main()
{
    WSHttpBinding binding = new WSHttpBinding();
    binding.Name = "binding1";
    binding.HostNameComparisonMode =
        HostNameComparisonMode.StrongWildcard;
    binding.Security.Mode = SecurityMode.Message;
    binding.ReliableSession.Enabled = false;
    binding.TransactionFlow = false;

    Uri baseAddress =
        new Uri("http://localhost:8000/servicemodelsamples/service");

    // Create a ServiceHost for the CalculatorService type and provide the base address.
    using(ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress))
    {
        serviceHost.AddServiceEndpoint(typeof(ICalculator),
                                       binding, baseAddress);
        // Open the ServiceHostBase to create listeners and start listening for messages.
        serviceHost.Open();

        // The service can now be accessed.
        Console.WriteLine("The service is ready.");
        Console.WriteLine("Press <ENTER> to terminate service.");
        Console.WriteLine();
        Console.ReadLine();
        // Close the ServiceHostBase to shutdown the service.
        serviceHost.Close();
    }
}
```

 <span data-ttu-id="1363f-107">クライアントは、チャネルを作成してサービスと通信します。次のサンプル コードを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1363f-107">The client creates a channel to communicate with the service as shown in the following sample code.</span></span>

```csharp
WSHttpBinding binding = new WSHttpBinding();
binding.Name = "binding1";
binding.HostNameComparisonMode = HostNameComparisonMode.StrongWildcard;
binding.Security.Mode = SecurityMode.Message;
binding.ReliableSession.Enabled = false;
binding.TransactionFlow = false;

String url = "http://localhost:8000/servicemodelsamples/service";
EndpointAddress address = new EndpointAddress(url);
ChannelFactory<ICalculator> channelFactory = new ChannelFactory<ICalculator>(binding,address);
ICalculator channel = channelFactory.CreateChannel();
```

 <span data-ttu-id="1363f-108">このサンプルを実行すると、操作要求および応答がクライアントのコンソール ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1363f-108">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="1363f-109">クライアントをシャットダウンするには、クライアント ウィンドウで Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="1363f-109">Press ENTER in the client window to shut down the client.</span></span>

```console
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="1363f-110">サンプルをセットアップ、ビルド、および実行するには</span><span class="sxs-lookup"><span data-stu-id="1363f-110">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="1363f-111">[Windows コミュニケーション ファウンデーション サンプルの 1 回限りのセットアップ手順を](one-time-setup-procedure-for-the-wcf-samples.md)実行していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1363f-111">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="1363f-112">ソリューションの C# 版または Visual Basic .NET 版をビルドするには、「 [Building the Windows Communication Foundation Samples](building-the-samples.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="1363f-112">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="1363f-113">単一または複数のコンピューターにまたがる構成でサンプルを実行するには[、「Windows コミュニケーション ファウンデーション サンプルの実行」の手順に](running-the-samples.md)従います。</span><span class="sxs-lookup"><span data-stu-id="1363f-113">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1363f-114">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="1363f-114">The samples may already be installed on your machine.</span></span> <span data-ttu-id="1363f-115">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="1363f-115">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="1363f-116">このディレクトリが存在しない場合は[、.NET Framework 4 の Windows コミュニケーション ファウンデーション (WCF) および Windows ワークフローファウンデーション (WF) サンプル](https://www.microsoft.com/download/details.aspx?id=21459)に移動して、すべての Windows 通信基盤 (WCF) とサンプルを[!INCLUDE[wf1](../../../../includes/wf1-md.md)]ダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="1363f-116">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1363f-117">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="1363f-117">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Imperative`
