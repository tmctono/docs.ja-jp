---
title: '方法: カスタム WS-Metadata Exchange バインディングを構成する'
ms.date: 03/30/2017
helpviewer_keywords:
- WS-Metadata Exchange [WCF]
- WS-Metadata Exchange [WCF], configuring a custom binding
ms.assetid: cdba4d73-da64-4805-bc56-9822becfd1e4
ms.openlocfilehash: c3582ba3c434bb763889faebcc27407f67af7b1e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795653"
---
# <a name="how-to-configure-a-custom-ws-metadata-exchange-binding"></a><span data-ttu-id="accf2-102">方法: カスタム WS-Metadata Exchange バインディングを構成する</span><span class="sxs-lookup"><span data-stu-id="accf2-102">How to: Configure a Custom WS-Metadata Exchange Binding</span></span>
<span data-ttu-id="accf2-103">ここでは、カスタム WS-Metadata Exchange バインディングを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="accf2-103">This topic will explain how to configure a custom WS-Metadata exchange binding.</span></span> <span data-ttu-id="accf2-104">Windows Communication Foundation (WCF) には、4つのシステム定義のメタデータバインドが含まれていますが、必要なバインドを使用してメタデータを公開できます。</span><span class="sxs-lookup"><span data-stu-id="accf2-104">Windows Communication Foundation (WCF) includes four system-defined metadata bindings, but you can publish metadata using any binding you want.</span></span> <span data-ttu-id="accf2-105">ここでは、`wsHttpBinding` を使用してメタデータを公開する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="accf2-105">This topic will show you how to publish metadata using the `wsHttpBinding`.</span></span> <span data-ttu-id="accf2-106">このバインディングでは、メタデータをセキュリティで保護して公開することができます。</span><span class="sxs-lookup"><span data-stu-id="accf2-106">This binding gives you the option of exposing metadata in a secure way.</span></span> <span data-ttu-id="accf2-107">この記事のコードは、[はじめに](../samples/getting-started-sample.md)に基づいています。</span><span class="sxs-lookup"><span data-stu-id="accf2-107">The code in this article is based on the [Getting Started](../samples/getting-started-sample.md).</span></span>  
  
### <a name="using-a-configuration-file"></a><span data-ttu-id="accf2-108">構成ファイルの使用</span><span class="sxs-lookup"><span data-stu-id="accf2-108">Using a configuration file</span></span>  
  
1. <span data-ttu-id="accf2-109">サービスの構成ファイルで、`serviceMetadata` タグを含んだサービス動作を追加します。</span><span class="sxs-lookup"><span data-stu-id="accf2-109">In the service's configuration file, add a service behavior that contains the `serviceMetadata` tag:</span></span>  
  
    ```xml  
    <behaviors>  
       <serviceBehaviors>  
         <behavior name="CalculatorServiceBehavior">  
           <serviceMetadata httpGetEnabled="True"/>  
         </behavior>  
       </serviceBehaviors>  
    </behaviors>  
    ```  
  
2. <span data-ttu-id="accf2-110">この新しい動作を参照する `behaviorConfiguration` 属性をサービス タグに追加します。</span><span class="sxs-lookup"><span data-stu-id="accf2-110">Add a `behaviorConfiguration` attribute to the service tag that references this new behavior:</span></span>  
  
    ```xml  
    <service        name="Microsoft.ServiceModel.Samples.CalculatorService"  
    behaviorConfiguration="CalculatorServiceBehavior">   
    ```  
  
3. <span data-ttu-id="accf2-111">メタデータ エンドポイントを追加し、アドレスに mex、バインディングに `wsHttpBinding`、コントラクトに <xref:System.ServiceModel.Description.IMetadataExchange> をそれぞれ指定します。</span><span class="sxs-lookup"><span data-stu-id="accf2-111">Add a metadata endpoint specifying mex as the address, `wsHttpBinding` as the binding, and <xref:System.ServiceModel.Description.IMetadataExchange> as the contract:</span></span>  
  
    ```xml  
    <endpoint address="mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange" />  
    ```  
  
4. <span data-ttu-id="accf2-112">Metadata Exchange エンドポイントが適切に動作することを確認するには、クライアントの構成ファイルにエンドポイント タグを追加します。</span><span class="sxs-lookup"><span data-stu-id="accf2-112">To verify the metadata exchange endpoint is working correctly add an endpoint tag in the client configuration file:</span></span>  
  
    ```xml  
    <endpoint name="MyMexEndpoint"               address="http://localhost:8000/servicemodelsamples/service/mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange"/>  
    ```  
  
5. <span data-ttu-id="accf2-113">クライアントの Main() メソッドで、新しい <xref:System.ServiceModel.Description.MetadataExchangeClient> インスタンスを作成し、その <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> プロパティを `true` に設定し、<xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> を呼び出して返されるメタデータのコレクションを反復処理します。</span><span class="sxs-lookup"><span data-stu-id="accf2-113">In the client's Main() method, create a new <xref:System.ServiceModel.Description.MetadataExchangeClient> instance, set its <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> property to `true`, call <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> and then iterate through the collection of metadata returned:</span></span>  
  
    ```  
    string mexAddress = "http://localhost:8000/servicemodelsamples/service/mex";  
  
    MetadataExchangeClient mexClient = new MetadataExchangeClient("MyMexEndpoint");  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet mdSet = mexClient.GetMetadata(new EndpointAddress(mexAddress));  
    foreach (MetadataSection section in mdSet.MetadataSections)  
    Console.WriteLine("Metadata section: " + section.Dialect.ToString());  
    ```  
  
### <a name="configuring-by-code"></a><span data-ttu-id="accf2-114">コードによる構成</span><span class="sxs-lookup"><span data-stu-id="accf2-114">Configuring by code</span></span>  
  
1. <span data-ttu-id="accf2-115"><xref:System.ServiceModel.WSHttpBinding> バインディングのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="accf2-115">Create a <xref:System.ServiceModel.WSHttpBinding> binding instance:</span></span>  
  
    ```  
    WSHttpBinding binding = new WSHttpBinding();  
    ```  
  
2. <span data-ttu-id="accf2-116"><xref:System.ServiceModel.ServiceHost> インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="accf2-116">Create a <xref:System.ServiceModel.ServiceHost> instance:</span></span>  
  
    ```  
    ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress);  
    ```  
  
3. <span data-ttu-id="accf2-117">サービス エンドポイントと <xref:System.ServiceModel.Description.ServiceMetadataBehavior> インスタンスを追加します。</span><span class="sxs-lookup"><span data-stu-id="accf2-117">Add a service endpoint and add a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance:</span></span>  
  
    ```  
    serviceHost.AddServiceEndpoint(typeof(ICalculator), binding, baseAddress);  
    ServiceMetadataBehavior smb = new ServiceMetadataBehavior();  
    smb.HttpGetEnabled = true;  
    serviceHost.Description.Behaviors.Add(smb);  
    ```  
  
4. <span data-ttu-id="accf2-118">前に作成した <xref:System.ServiceModel.WSHttpBinding> を指定する Metadata Exchange エンドポイントを追加します。</span><span class="sxs-lookup"><span data-stu-id="accf2-118">Add a metadata exchange endpoint, specifying the <xref:System.ServiceModel.WSHttpBinding> created earlier:</span></span>  
  
    ```  
    serviceHost.AddServiceEndpoint(typeof(IMetadataExchange), binding, mexAddress);  
    ```  
  
5. <span data-ttu-id="accf2-119">Metadata Exchange エンドポイントが適切に動作することを確認するには、クライアントの構成ファイルにエンドポイント タグを追加します。</span><span class="sxs-lookup"><span data-stu-id="accf2-119">To verify that the metadata exchange endpoint is working correctly, add an endpoint tag in the client configuration file:</span></span>  
  
    ```xml  
    <endpoint name="MyMexEndpoint"               address="http://localhost:8000/servicemodelsamples/service/mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange"/>  
    ```  
  
6. <span data-ttu-id="accf2-120">クライアントの Main() メソッドで、新しい <xref:System.ServiceModel.Description.MetadataExchangeClient> インスタンスを作成し、その <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> プロパティを `true` に設定し、<xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> を呼び出して返されるメタデータのコレクションを反復処理します。</span><span class="sxs-lookup"><span data-stu-id="accf2-120">In the client's Main() method, create a new <xref:System.ServiceModel.Description.MetadataExchangeClient> instance, set the <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> property to `true`, call <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> and then iterate through the collection of metadata returned:</span></span>  
  
    ```  
    string mexAddress = "http://localhost:8000/servicemodelsamples/service/mex";  
  
    MetadataExchangeClient mexClient = new MetadataExchangeClient("MyMexEndpoint");  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet mdSet = mexClient.GetMetadata(new EndpointAddress(mexAddress));  
    foreach (MetadataSection section in mdSet.MetadataSections)  
    Console.WriteLine("Metadata section: " + section.Dialect.ToString());  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="accf2-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="accf2-121">See also</span></span>

- [<span data-ttu-id="accf2-122">メタデータ公開動作</span><span class="sxs-lookup"><span data-stu-id="accf2-122">Metadata Publishing Behavior</span></span>](../samples/metadata-publishing-behavior.md)
- [<span data-ttu-id="accf2-123">メタデータの抽出</span><span class="sxs-lookup"><span data-stu-id="accf2-123">Retrieve Metadata</span></span>](../samples/retrieve-metadata.md)
- [<span data-ttu-id="accf2-124">メタデータ</span><span class="sxs-lookup"><span data-stu-id="accf2-124">Metadata</span></span>](../feature-details/metadata.md)
- [<span data-ttu-id="accf2-125">メタデータの公開</span><span class="sxs-lookup"><span data-stu-id="accf2-125">Publishing Metadata</span></span>](../feature-details/publishing-metadata.md)
- [<span data-ttu-id="accf2-126">メタデータ エンドポイントを公開する</span><span class="sxs-lookup"><span data-stu-id="accf2-126">Publishing Metadata Endpoints</span></span>](../publishing-metadata-endpoints.md)
