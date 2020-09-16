---
title: インライン コードを使用した IIS ホスティング
ms.date: 03/30/2017
helpviewer_keywords:
- Web hosted service
- IIS Hosting Using Inline Code Sample [Windows Communication Foundation]
ms.assetid: 56fe3687-a34b-4661-8e30-b33770f413fa
ms.openlocfilehash: 41e19c318953d7e97eb5183c5a16a3780813f94c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558997"
---
# <a name="iis-hosting-using-inline-code"></a><span data-ttu-id="2c5f7-102">インライン コードを使用した IIS ホスティング</span><span class="sxs-lookup"><span data-stu-id="2c5f7-102">IIS Hosting Using Inline Code</span></span>

<span data-ttu-id="2c5f7-103">このサンプルでは、インターネット インフォメーション サービス (IIS) によってホストされるサービスを実装する方法を示します。サービス コードは .svc ファイルにインラインで含まれており、必要に応じてコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="2c5f7-103">This sample demonstrates how to implement a service hosted by Internet Information Services (IIS), where the service code is contained in-line in a .svc file and is compiled on demand.</span></span> <span data-ttu-id="2c5f7-104">サービス コードは、アプリケーションの \App_Code ディレクトリにあるソース コード ファイルに直接実装するか、または \bin に配置されるアセンブリにコンパイルすることもできます。</span><span class="sxs-lookup"><span data-stu-id="2c5f7-104">Service code can also be implemented directly in source code files located in the application's \App_Code directory, or compiled into assembly deployed in \bin.</span></span> <span data-ttu-id="2c5f7-105">ただし、このサンプルではこれらの手法は示しません。</span><span class="sxs-lookup"><span data-stu-id="2c5f7-105">This sample does not demonstrate these techniques.</span></span>

> [!NOTE]
> <span data-ttu-id="2c5f7-106">このサンプルのセットアップ手順とビルド手順については、このトピックの最後を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c5f7-106">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2c5f7-107">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="2c5f7-107">The samples may already be installed on your computer.</span></span> <span data-ttu-id="2c5f7-108">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="2c5f7-108">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="2c5f7-109">このディレクトリが存在しない場合は、 [Windows Communication Foundation (wcf) および Windows Workflow Foundation (WF) のサンプルの .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) にアクセスして、すべての WINDOWS COMMUNICATION FOUNDATION (wcf) とサンプルをダウンロードして [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ください。</span><span class="sxs-lookup"><span data-stu-id="2c5f7-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2c5f7-110">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="2c5f7-110">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebHost\InlineCode`

<span data-ttu-id="2c5f7-111">このサンプルでは、要求/応答通信パターンを定義するコントラクトを実装する一般的なサービスを示します。</span><span class="sxs-lookup"><span data-stu-id="2c5f7-111">The sample demonstrates a typical service that implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="2c5f7-112">このサービスは IIS によってホストされ、サービス コードは Service.svc ファイルに完全に含まれています。</span><span class="sxs-lookup"><span data-stu-id="2c5f7-112">The service is hosted in IIS and the service code is entirely contained in the Service.svc file.</span></span> <span data-ttu-id="2c5f7-113">サービスはホストによってアクティブ化され、このサービスに最初に送信されるメッセージによって必要に応じてコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="2c5f7-113">The service is host-activated and compiled on-demand by the first message sent to the service.</span></span> <span data-ttu-id="2c5f7-114">あらかじめコンパイルしておく必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2c5f7-114">There is no pre-compilation necessary.</span></span> <span data-ttu-id="2c5f7-115">サービスは、次に示すコードで定義される `ICalculator` コントラクトを実装します。</span><span class="sxs-lookup"><span data-stu-id="2c5f7-115">The service implements an `ICalculator` contract as defined in the following code:</span></span>

```csharp
// Define a service contract.
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
    public interface ICalculator
{
    [OperationContract]
    double Add(double n1, double n2);
    [OperationContract]
    double Subtract(double n1, double n2);
    [OperationContract]
    double Multiply(double n1, double n2);
    [OperationContract]
    double Divide(double n1, double n2);
}
```

<span data-ttu-id="2c5f7-116">このサービス実装は、計算を行い、結果を返します。</span><span class="sxs-lookup"><span data-stu-id="2c5f7-116">The service implementation calculates and returns the appropriate result.</span></span>

`<%@ServiceHost language=c# Debug="true" Service="Microsoft.ServiceModel.Samples.CalculatorService" %>`

```csharp
// Service class that implements the service contract.
public class CalculatorService : ICalculator
{
    public double Add(double n1, double n2)
    {
        return n1 + n2;
    }
    public double Subtract(double n1, double n2)
    {
        return n1 - n2;
    }
    public double Multiply(double n1, double n2)
    {
        return n1 * n2;
    }
    public double Divide(double n1, double n2)
    {
        return n1 / n2;
    }
}
```

<span data-ttu-id="2c5f7-117">このサンプルを実行すると、操作要求および応答がクライアントのコンソール ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="2c5f7-117">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="2c5f7-118">クライアントをシャットダウンするには、クライアント ウィンドウで Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="2c5f7-118">Press ENTER in the client window to shut down the client.</span></span>

```console
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="2c5f7-119">サンプルをセットアップ、ビルド、および実行するには</span><span class="sxs-lookup"><span data-stu-id="2c5f7-119">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="2c5f7-120">[Windows Communication Foundation サンプルの1回限りのセットアップ手順](one-time-setup-procedure-for-the-wcf-samples.md)を実行したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="2c5f7-120">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="2c5f7-121">ソリューションの C# 版または Visual Basic .NET 版をビルドするには、「 [Building the Windows Communication Foundation Samples](building-the-samples.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="2c5f7-121">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="2c5f7-122">ソリューションをビルドした後、setup.bat を実行して IIS 7.0 で ServiceModelSamples アプリケーションを設定します。</span><span class="sxs-lookup"><span data-stu-id="2c5f7-122">After the solution has been built, run setup.bat to set up the ServiceModelSamples Application in IIS 7.0.</span></span> <span data-ttu-id="2c5f7-123">これで、ServiceModelSamples ディレクトリが IIS 7.0 アプリケーションとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="2c5f7-123">The ServiceModelSamples directory should now appear as an IIS 7.0 Application.</span></span>

4. <span data-ttu-id="2c5f7-124">サンプルを単一コンピューター構成または複数コンピューター構成で実行するには、「 [Windows Communication Foundation サンプルの実行](running-the-samples.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="2c5f7-124">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span> <span data-ttu-id="2c5f7-125">このサービスを呼び出すことができるクライアントアプリケーションを作成する方法の例については、「 [方法: クライアントを作成](../how-to-create-a-wcf-client.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c5f7-125">For an example on how to create a client application that can call this service, see [How to: Create a Client](../how-to-create-a-wcf-client.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2c5f7-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="2c5f7-126">See also</span></span>

- <span data-ttu-id="2c5f7-127">[AppFabric のホストおよび永続化のサンプル](/previous-versions/appfabric/ff383418(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="2c5f7-127">[AppFabric Hosting and Persistence Samples](/previous-versions/appfabric/ff383418(v=azure.10))</span></span>
