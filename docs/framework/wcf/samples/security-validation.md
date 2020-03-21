---
title: セキュリティ検証
ms.date: 03/30/2017
ms.assetid: 48dcd496-0c4f-48ce-8b9b-0e25b77ffa58
ms.openlocfilehash: 17e6e250c6b345477f7c9b377eb8e16ff4331ca7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183379"
---
# <a name="security-validation"></a><span data-ttu-id="8263c-102">セキュリティ検証</span><span class="sxs-lookup"><span data-stu-id="8263c-102">Security Validation</span></span>
<span data-ttu-id="8263c-103">このサンプルでは、サービスが特定の条件を満たしていることを確認するカスタム動作を使用して、コンピューター上のサービスを検証する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8263c-103">This sample demonstrates how to use a custom behavior to validate services on a computer to ensure they meet specific criteria.</span></span> <span data-ttu-id="8263c-104">このサンプルでは、サービス上の各エンドポイントをスキャンし、セキュリティ保護されたバインディング要素が含まれているかどうかを確認するカスタム動作を使用して、サービスを検証します。</span><span class="sxs-lookup"><span data-stu-id="8263c-104">In this sample, services are validated by the custom behavior by scanning through each endpoint on the service and checking to see whether they contain secure binding elements.</span></span> <span data-ttu-id="8263c-105">このサンプルは、[作業の開始に](../../../../docs/framework/wcf/samples/getting-started-sample.md)基づいています。</span><span class="sxs-lookup"><span data-stu-id="8263c-105">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8263c-106">このサンプルのセットアップ手順とビルド手順については、このトピックの最後を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8263c-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="endpoint-validation-custom-behavior"></a><span data-ttu-id="8263c-107">エンドポイント検証のカスタム動作</span><span class="sxs-lookup"><span data-stu-id="8263c-107">Endpoint Validation Custom Behavior</span></span>  
 <span data-ttu-id="8263c-108">`Validate` インターフェイスに含まれる <xref:System.ServiceModel.Description.IServiceBehavior> メソッドにユーザー コードを追加することによって、サービスまたはエンドポイントにカスタム動作を与え、ユーザー定義のアクションを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="8263c-108">By adding user code to the `Validate` method contained in the <xref:System.ServiceModel.Description.IServiceBehavior> interface, custom behavior can be given to a service or endpoint to perform user-defined actions.</span></span> <span data-ttu-id="8263c-109">次のコードを使用すると、サービスに含まれる各エンドポイントをループし、バインディング コレクションからセキュリティ保護されたバインディングが検索されます。</span><span class="sxs-lookup"><span data-stu-id="8263c-109">The following code is used to loop through each endpoint contained in a service, which searches through their binding collections for secure bindings.</span></span>  
  
```csharp
public void Validate(ServiceDescription serviceDescription,
                                       ServiceHostBase serviceHostBase)  
{  
    // Loop through each endpoint individually, gathering their
    // binding elements.  
    foreach (ServiceEndpoint endpoint in serviceDescription.Endpoints)  
    {  
        secureElementFound = false;  
  
        // Retrieve the endpoint's binding element collection.  
        BindingElementCollection bindingElements =
            endpoint.Binding.CreateBindingElements();  
  
        // Look to see if the binding elements collection contains any
        // secure binding elements. Transport, Asymmetric, and Symmetric
        // binding elements are all derived from SecurityBindingElement.  
        if ((bindingElements.Find<SecurityBindingElement>() != null) || (bindingElements.Find<HttpsTransportBindingElement>() != null) || (bindingElements.Find<WindowsStreamSecurityBindingElement>() != null) || (bindingElements.Find<SslStreamSecurityBindingElement>() != null))  
        {  
            secureElementFound = true;  
        }  
  
    // Send a message to the system event viewer when an endpoint is deemed insecure.  
    if (!secureElementFound)  
        throw new Exception(System.DateTime.Now.ToString() + ": The endpoint \"" + endpoint.Name + "\" has no secure bindings.");  
    }  
}  
```  
  
 <span data-ttu-id="8263c-110">次のコードを Web.config ファイルに追加すると、サービスで識別される `serviceValidate` 動作の拡張が追加されます。</span><span class="sxs-lookup"><span data-stu-id="8263c-110">Adding the following code to Web.config file adds the `serviceValidate` behavior extension for the service to recognize.</span></span>  
  
```xml  
<system.serviceModel>  
    <extensions>  
        <behaviorExtensions>  
            <add name="endpointValidate" type="Microsoft.ServiceModel.Samples.EndpointValidateElement, endpointValidate, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null" />  
        </behaviorExtensions>  
    </extensions>  
...  
```  
  
 <span data-ttu-id="8263c-111">動作の拡張がサービスに追加されると、`endpointValidate` の動作を Web.config ファイルの動作リストに追加でき、さらにはサービスに追加できるようになります。</span><span class="sxs-lookup"><span data-stu-id="8263c-111">Once the behavior extension is added to the service, it is now possible to add the `endpointValidate` behavior to the list of behaviors in the Web.config file and thus, to the service.</span></span>  
  
```xml  
<behaviors>  
    <serviceBehaviors>  
        <behavior name="CalcServiceSEB1">  
            <serviceMetadata httpGetEnabled="true" />  
            <endpointValidate />  
        </behavior>  
    </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="8263c-112">動作とその拡張が Web.config ファイルに追加されると、動作は個別のサービスに適用されます。一方で Machine.config ファイルに追加された場合は、動作はコンピューター上でアクティブなすべてのサービスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="8263c-112">Behaviors and their extensions that are added to the Web.config file apply behavior to individual services, while when added to the Machine.config file apply behavior to every service active on the computer.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8263c-113">動作をすべてのサービスに追加する場合、Machine.config ファイルの変更を行う前に、このファイルのバックアップを推奨するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8263c-113">When adding behavior to all services, it is suggested to backup the Machine.config file before making any change.</span></span>  
  
 <span data-ttu-id="8263c-114">ここで、このサンプルの client\bin ディレクトリに用意されたクライアントを実行します。</span><span class="sxs-lookup"><span data-stu-id="8263c-114">Now run the client provided in the client\bin directory of this sample.</span></span> <span data-ttu-id="8263c-115">例外が発生し、"要求されたサービス ' はhttp://localhost/servicemodelsamples/service.svcアクティブ化できませんでした" というメッセージが表示されました。</span><span class="sxs-lookup"><span data-stu-id="8263c-115">An exception has occurs with the following message: "The requested service, 'http://localhost/servicemodelsamples/service.svc' could not be activated."</span></span> <span data-ttu-id="8263c-116">これは予期される例外です。エンドポイント検証の動作により、エンドポイントがセキュリティで保護されていないと見なされ、サービスが開始されないためです。</span><span class="sxs-lookup"><span data-stu-id="8263c-116">This is expected because an endpoint is considered insecure by the endpoint validating behavior and prevents the service from being started.</span></span> <span data-ttu-id="8263c-117">さらにこの動作によって、エンドポイントがセキュリティ保護されていないという内部例外がスローされ、システム イベント ビューアで "WebHost" カテゴリの "System.ServiceModel 4.0.0.0" ソースの下にメッセージが書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="8263c-117">The behavior also throws an internal exception that describes which endpoint is insecure and writes a message to the system Event Viewer under the "System.ServiceModel 4.0.0.0" source and the "WebHost" category.</span></span> <span data-ttu-id="8263c-118">さらにこのサンプルでは、サービスのトレースを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="8263c-118">It is also possible to turn on tracing on the service in this sample.</span></span> <span data-ttu-id="8263c-119">これによって、サービス トレース ビューア ツールを使用してサービス トレースの結果を開き、エンドポイント検証の動作からスローされた例外を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="8263c-119">This allows the user to view the exceptions thrown by endpoint validating behavior by opening the resulting service traces using the Service Trace Viewer tool.</span></span>  
  
#### <a name="to-view-failed-endpoint-validation-exception-messages-in-the-event-viewer"></a><span data-ttu-id="8263c-120">エンドポイント検証エラーの例外メッセージをイベント ビューアーで表示するには</span><span class="sxs-lookup"><span data-stu-id="8263c-120">To view failed endpoint validation exception messages in the Event Viewer</span></span>  
  
1. <span data-ttu-id="8263c-121">[**スタート**] メニューをクリックし、[**ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8263c-121">Click the **Start** menu and select **Run…**.</span></span>  
  
2. <span data-ttu-id="8263c-122">「 `eventvwr` 」と入力して **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8263c-122">Type `eventvwr` and click **OK**.</span></span>  
  
3. <span data-ttu-id="8263c-123">[イベント ビューア] ウィンドウで、[**アプリケーション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8263c-123">In the Event Viewer window, click **Application**.</span></span>  
  
4. <span data-ttu-id="8263c-124">セキュリティで保護されていないエンドポイント メッセージを表示するには、**アプリケーション**ウィンドウの [WebHost] カテゴリの下に最近追加された "System.ServiceModel 4.0.0.0" イベントをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="8263c-124">Double-click the recently added "System.ServiceModel 4.0.0.0" event under the "WebHost" category in the **Application** window to view insecure endpoint messages.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="8263c-125">サンプルをセットアップ、ビルド、および実行するには</span><span class="sxs-lookup"><span data-stu-id="8263c-125">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="8263c-126">[Windows コミュニケーションファウンデーション サンプルのワンタイム セットアップ手順を](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)実行したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="8263c-126">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="8263c-127">ソリューションの C# 版または Visual Basic .NET 版をビルドするには、「 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="8263c-127">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="8263c-128">単一または複数のコンピューターにまたがる構成でサンプルを実行するには[、「Windows コミュニケーション ファウンデーション サンプルの実行」の手順に](../../../../docs/framework/wcf/samples/running-the-samples.md)従います。</span><span class="sxs-lookup"><span data-stu-id="8263c-128">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="8263c-129">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="8263c-129">The samples may already be installed on your computer.</span></span> <span data-ttu-id="8263c-130">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8263c-130">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="8263c-131">このディレクトリが存在しない場合は[、.NET Framework 4 の Windows コミュニケーション ファウンデーション (WCF) および Windows ワークフローファウンデーション (WF) サンプル](https://www.microsoft.com/download/details.aspx?id=21459)に移動して、すべての Windows 通信基盤 (WCF) とサンプルを[!INCLUDE[wf1](../../../../includes/wf1-md.md)]ダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="8263c-131">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8263c-132">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="8263c-132">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ServiceValidation`  
  
## <a name="see-also"></a><span data-ttu-id="8263c-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="8263c-133">See also</span></span>

- <span data-ttu-id="8263c-134">[AppFabric の監視のサンプル](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="8263c-134">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
