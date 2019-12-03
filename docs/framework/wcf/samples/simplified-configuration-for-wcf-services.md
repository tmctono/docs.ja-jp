---
title: WCF サービスの簡略化された構成
ms.date: 03/30/2017
ms.assetid: 1e39ec25-18a3-4fdc-b6a3-9dfafbd60112
ms.openlocfilehash: a1188ad9ed56ebb24754785546b6a5b54cd2b840
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715428"
---
# <a name="simplified-configuration-for-wcf-services"></a><span data-ttu-id="5d6cd-102">WCF サービスの簡略化された構成</span><span class="sxs-lookup"><span data-stu-id="5d6cd-102">Simplified Configuration for WCF Services</span></span>
<span data-ttu-id="5d6cd-103">このサンプルでは、Windows Communication Foundation (WCF) を使用して、一般的なサービスとクライアントを実装して構成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5d6cd-103">This sample demonstrates how to implement and configure a typical service and client using Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="5d6cd-104">このサンプルは、他のすべての基本的な技術サンプルの基礎になります。</span><span class="sxs-lookup"><span data-stu-id="5d6cd-104">This sample is the basis for all other basic technology samples.</span></span>  
  
 <span data-ttu-id="5d6cd-105">このサービスは、サービスと通信するためのエンドポイントを公開し、.NET Framework 4 の簡略化された構成を使用します。</span><span class="sxs-lookup"><span data-stu-id="5d6cd-105">This service, which exposes an endpoint for communicating with the service, uses the simplified configuration in .NET Framework 4.</span></span> <span data-ttu-id="5d6cd-106">.NET Framework 4 より前の場合、エンドポイントは通常、次の構成コード例に示すように、構成ファイル (Web.config) で定義されます。</span><span class="sxs-lookup"><span data-stu-id="5d6cd-106">Prior to .NET Framework 4, the endpoint is typically defined in a configuration file (Web.config), as shown in the following example configuration code.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- Copyright ©) Microsoft Corporation.  All Rights Reserved. -->  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service name="Microsoft.Samples.GettingStarted.CalculatorService"  
               behaviorConfiguration="CalculatorServiceBehavior">  
        <endpoint address="" binding="basicHttpBinding" contract="ICalculator"/>  
        <endpoint address="mex" binding="mexHttpBinding" contract="IMetadataExchange"/>  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="5d6cd-107">.NET Framework 4 では、`<service>` 要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="5d6cd-107">In .NET Framework 4, the `<service>` element is optional.</span></span> <span data-ttu-id="5d6cd-108">サービスでエンドポイントが定義されていない場合、各ベース アドレスのエンドポイントと実装されたコントラクトがサービスに追加されます。</span><span class="sxs-lookup"><span data-stu-id="5d6cd-108">When a service does not define any endpoints, an endpoint for each base address and contract implemented are added to the service.</span></span> <span data-ttu-id="5d6cd-109">このベース アドレスがコントラクト名に追加されてエンドポイントが決定され、バインドがアドレス スキームで決定されます。</span><span class="sxs-lookup"><span data-stu-id="5d6cd-109">The base address is appended to the contract name to determine the endpoint and the binding is determined by the address scheme.</span></span> <span data-ttu-id="5d6cd-110">次のコード例は、簡略化された構成ファイルを示しています。</span><span class="sxs-lookup"><span data-stu-id="5d6cd-110">The following code example demonstrates a simplified configuration file.</span></span> <span data-ttu-id="5d6cd-111">構成されているように、サービスは、同じコンピューター上のクライアントによって `http://localhost/servicemodelsamples/service.svc` にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5d6cd-111">As configured, the service can be accessed at `http://localhost/servicemodelsamples/service.svc` by a client on the same computer.</span></span> <span data-ttu-id="5d6cd-112">リモート コンピューター上のクライアントがサービスにアクセスするには、localhost の代わりに完全修飾ドメイン名を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d6cd-112">For clients on remote computers to access the service, a fully-qualified domain name must be specified instead of localhost.</span></span> <span data-ttu-id="5d6cd-113">既定では、サービスはメタデータを公開しません。</span><span class="sxs-lookup"><span data-stu-id="5d6cd-113">The service does not expose metadata by default.</span></span> <span data-ttu-id="5d6cd-114">そのため、サービスは <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 動作を有効にします。</span><span class="sxs-lookup"><span data-stu-id="5d6cd-114">As such, the service turns on the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> behavior.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- Copyright © Microsoft Corporation.  All Rights Reserved. -->  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
### <a name="to-use-this-sample"></a><span data-ttu-id="5d6cd-115">このサンプルを使用するには</span><span class="sxs-lookup"><span data-stu-id="5d6cd-115">To use this sample</span></span>  
  
1. <span data-ttu-id="5d6cd-116">[Windows Communication Foundation サンプルの1回限りのセットアップ手順](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)を実行したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="5d6cd-116">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="5d6cd-117">ソリューションをビルドするには、「 [Windows Communication Foundation サンプルのビルド](../../../../docs/framework/wcf/samples/building-the-samples.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="5d6cd-117">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="5d6cd-118">次の手順に従ってサンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="5d6cd-118">Run the sample by following these steps:</span></span>  
  
    1. <span data-ttu-id="5d6cd-119">**サービス**プロジェクトを右クリックし、 **[スタートアッププロジェクトに設定]** をクリックして、Ctrl キーを押し**ながら F5**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="5d6cd-119">Right click the **Service** project and select **Set as StartUp project**, then press **Ctrl+F5**.</span></span>  
  
    2. <span data-ttu-id="5d6cd-120">コンソール出力でサービスが動作していることが確認されるまで待機します。</span><span class="sxs-lookup"><span data-stu-id="5d6cd-120">Wait for the console output confirming that the service is up and running.</span></span>  
  
    3. <span data-ttu-id="5d6cd-121">**クライアント**プロジェクトを右クリックし、 **[スタートアッププロジェクトに設定]** をクリックして、Ctrl キーを押し**ながら F5**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="5d6cd-121">Right click the **Client** project and select **Set as StartUp project**, then press **Ctrl+F5**.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="5d6cd-122">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="5d6cd-122">The samples may already be installed on your computer.</span></span> <span data-ttu-id="5d6cd-123">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5d6cd-123">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="5d6cd-124">このディレクトリが存在しない場合は、 [Windows Communication Foundation (wcf) および Windows Workflow Foundation (WF) のサンプルの .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459)にアクセスして、すべての WINDOWS COMMUNICATION FOUNDATION (wcf) と [!INCLUDE[wf1](../../../../includes/wf1-md.md)] サンプルをダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="5d6cd-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5d6cd-125">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="5d6cd-125">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigSimplificationIn40`  
  
## <a name="see-also"></a><span data-ttu-id="5d6cd-126">参照</span><span class="sxs-lookup"><span data-stu-id="5d6cd-126">See also</span></span>

- [<span data-ttu-id="5d6cd-127">AppFabric 管理のサンプル</span><span class="sxs-lookup"><span data-stu-id="5d6cd-127">AppFabric Management Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193960)
- [<span data-ttu-id="5d6cd-128">簡略化された構成</span><span class="sxs-lookup"><span data-stu-id="5d6cd-128">Simplified Configuration</span></span>](../../../../docs/framework/wcf/simplified-configuration.md)
