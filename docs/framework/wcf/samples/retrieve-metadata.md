---
title: メタデータの抽出
ms.date: 03/30/2017
ms.assetid: e8a6ef8c-a195-495a-a15e-7d92bdf0b28c
ms.openlocfilehash: 9b1adf4ed2a09625ca19016f531936002fff757d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183390"
---
# <a name="retrieve-metadata"></a><span data-ttu-id="888df-102">メタデータの抽出</span><span class="sxs-lookup"><span data-stu-id="888df-102">Retrieve Metadata</span></span>
<span data-ttu-id="888df-103">このサンプルでは、サービスからメタデータを動的に取得し、通信に使用するエンドポイントを選択するクライアントを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="888df-103">This sample demonstrates how to implement a client that dynamically retrieves metadata from a service to choose an endpoint with which to communicate.</span></span> <span data-ttu-id="888df-104">このサンプルは、[作業の開始に](../../../../docs/framework/wcf/samples/getting-started-sample.md)基づいています。</span><span class="sxs-lookup"><span data-stu-id="888df-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span> <span data-ttu-id="888df-105">サービスは、バインディングを使用するベース アドレスのエンドポイントと、バインディングを使用した {*baseaddress*} /secure のセキュリティで保護された`wsHttpBinding`エンドポイントの 2 つのエンドポイントを公開するように変更されました。 `basicHttpBinding`</span><span class="sxs-lookup"><span data-stu-id="888df-105">The service has been modified to expose two endpoints—an endpoint at the base address using the `basicHttpBinding` binding, and a secure endpoint at {*baseaddress*}/secure using the `wsHttpBinding` binding.</span></span> <span data-ttu-id="888df-106">これらのエンドポイント アドレスとバインディングを使用してクライアントを構成する代わりに、クライアントでは <xref:System.ServiceModel.Description.MetadataExchangeClient> クラスを使用してサービスのメタデータを動的に取得し、<xref:System.ServiceModel.Description.ServiceEndpointCollection> クラスを使用してこのメタデータを <xref:System.ServiceModel.Description.WsdlImporter> としてインポートします。</span><span class="sxs-lookup"><span data-stu-id="888df-106">Instead of configuring the client with the endpoint addresses and bindings, the client dynamically retrieves the metadata for the service using the <xref:System.ServiceModel.Description.MetadataExchangeClient> class and then imports the metadata as a <xref:System.ServiceModel.Description.ServiceEndpointCollection> using the <xref:System.ServiceModel.Description.WsdlImporter> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="888df-107">このサンプルのセットアップ手順とビルド手順については、このトピックの最後を参照してください。</span><span class="sxs-lookup"><span data-stu-id="888df-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="888df-108">クライアント アプリケーションはインポートされた <xref:System.ServiceModel.Description.ServiceEndpointCollection> を使用して、サービスとの通信に使用するクライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="888df-108">The client application uses the imported <xref:System.ServiceModel.Description.ServiceEndpointCollection> to create clients to communicate with the service.</span></span> <span data-ttu-id="888df-109">クライアント アプリケーションは、取得した各エンドポイントを反復処理し、`ICalculator` コントラクトを実装した各エンドポイントと通信を行います。</span><span class="sxs-lookup"><span data-stu-id="888df-109">The client application iterates through each retrieved endpoint and communicates with each endpoint that implements the `ICalculator` contract.</span></span> <span data-ttu-id="888df-110">適切なアドレスとバインディングは取得したエンドポイントで提供されます。これによって、クライアントは各エンドポイントと通信するように構成されます。次のサンプル コードを参照してください。</span><span class="sxs-lookup"><span data-stu-id="888df-110">The appropriate address and binding are provided with the retrieved endpoint, so that the client is configured to communicate with each endpoint, as shown in the following sample code.</span></span>  
  
```csharp
// Create a MetadataExchangeClient for retrieving metadata.  
EndpointAddress mexAddress = new EndpointAddress(ConfigurationManager.AppSettings["mexAddress"]);  
MetadataExchangeClient mexClient = new MetadataExchangeClient(mexAddress);  
  
// Retrieve the metadata for all endpoints using metadata exchange protocol (mex).  
MetadataSet metadataSet = mexClient.GetMetadata();  
  
//Convert the metadata into endpoints.  
WsdlImporter importer = new WsdlImporter(metadataSet);  
ServiceEndpointCollection endpoints = importer.ImportAllEndpoints();  
  
CalculatorClient client = null;  
ContractDescription contract = ContractDescription.GetContract(typeof(ICalculator));  
// Communicate with each endpoint that supports the ICalculator contract.  
foreach (ServiceEndpoint ep in endpoints)  
{  
    if (ep.Contract.Namespace.Equals(contract.Namespace) && ep.Contract.Name.Equals(contract.Name))  
    {  
        // Create a client using the endpoint address and binding.  
        client = new CalculatorClient(ep.Binding, new EndpointAddress(ep.Address.Uri));  
        Console.WriteLine("Communicate with endpoint: ");  
        Console.WriteLine("   AddressPath={0}", ep.Address.Uri.PathAndQuery);  
        Console.WriteLine("   Binding={0}", ep.Binding.Name);  
        // Call operations.  
        DoCalculations(client);  
  
        //Closing the client gracefully closes the connection and cleans up resources.  
        client.Close();  
    }  
}  
```  
  
 <span data-ttu-id="888df-111">クライアント コンソール ウィンドウには、各エンドポイントに送信された操作が、そのエンドポイントのアドレス パスとバインディング名と共に表示されます。</span><span class="sxs-lookup"><span data-stu-id="888df-111">The client console window displays the operations sent to each of the endpoints, displaying the address path and binding name.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="888df-112">サンプルをセットアップ、ビルド、および実行するには</span><span class="sxs-lookup"><span data-stu-id="888df-112">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="888df-113">[Windows コミュニケーションファウンデーション サンプルのワンタイム セットアップ手順を](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)実行したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="888df-113">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="888df-114">ソリューションの C# エディション、C++ エディション、または Visual Basic .NET エディションをビルドするには[、「Windows コミュニケーション ファウンデーション のサンプルのビルド」の手順に](../../../../docs/framework/wcf/samples/building-the-samples.md)従ってください。</span><span class="sxs-lookup"><span data-stu-id="888df-114">To build the C#, C++, or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="888df-115">単一または複数のコンピューターにまたがる構成でサンプルを実行するには[、「Windows コミュニケーション ファウンデーション サンプルの実行」の手順に](../../../../docs/framework/wcf/samples/running-the-samples.md)従います。</span><span class="sxs-lookup"><span data-stu-id="888df-115">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="888df-116">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="888df-116">The samples may already be installed on your machine.</span></span> <span data-ttu-id="888df-117">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="888df-117">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="888df-118">このディレクトリが存在しない場合は[、.NET Framework 4 の Windows コミュニケーション ファウンデーション (WCF) および Windows ワークフローファウンデーション (WF) サンプル](https://www.microsoft.com/download/details.aspx?id=21459)に移動して、すべての Windows 通信基盤 (WCF) とサンプルを[!INCLUDE[wf1](../../../../includes/wf1-md.md)]ダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="888df-118">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="888df-119">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="888df-119">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\RetrieveMetadata`  
