---
title: コード内での WCF サービスの構成
ms.date: 03/30/2017
ms.assetid: 193c725d-134f-4d31-a8f8-4e575233bff6
ms.openlocfilehash: 699549305ce8ca17480285e33570c01d00c7cb97
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69948431"
---
# <a name="configuring-wcf-services-in-code"></a><span data-ttu-id="d7d85-102">コード内での WCF サービスの構成</span><span class="sxs-lookup"><span data-stu-id="d7d85-102">Configuring WCF Services in Code</span></span>
<span data-ttu-id="d7d85-103">Windows Communication Foundation (WCF) を使用すると、開発者は構成ファイルまたはコードを使用してサービスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="d7d85-103">Windows Communication Foundation (WCF) allows developers to configure services using configuration files or code.</span></span>  <span data-ttu-id="d7d85-104">構成ファイルは、サービスを配置した後に構成する必要がある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="d7d85-104">Configuration files are useful when a service needs to be configured after being deployed.</span></span> <span data-ttu-id="d7d85-105">構成ファイルを使用する場合、IT 専門家は構成ファイルを更新するだけで、再コンパイルの必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d7d85-105">When using configuration files, an IT professional only needs to update the configuration file, no recompilation is required.</span></span> <span data-ttu-id="d7d85-106">ただし、構成ファイルの管理は複雑で難しくなる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d7d85-106">Configuration files, however, can be complex and difficult to maintain.</span></span> <span data-ttu-id="d7d85-107">構成ファイルのデバッグはサポートされていません。また、構成要素は名前で参照されるため、構成ファイルの作成時にエラーが発生しやすく、構成ファイルの作成が困難になります。</span><span class="sxs-lookup"><span data-stu-id="d7d85-107">There is no support for debugging configuration files and configuration elements are referenced by names which makes authoring configuration files error-prone and difficult.</span></span> <span data-ttu-id="d7d85-108">WCF では、コードでサービスを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="d7d85-108">WCF also allows you to configure services in code.</span></span> <span data-ttu-id="d7d85-109">以前のバージョンの WCF (4.0 およびそれ以前) では、自己ホスト型のシナリオでは、コード<xref:System.ServiceModel.ServiceHost>内のサービスの構成は簡単でした。クラスは、ServiceHost を呼び出す前にエンドポイントと動作を構成することを許可していました。</span><span class="sxs-lookup"><span data-stu-id="d7d85-109">In earlier versions of WCF (4.0 and earlier) configuring services in code was easy in self-hosted scenarios, the <xref:System.ServiceModel.ServiceHost> class allowed you to configure endpoints and behaviors prior to calling ServiceHost.Open.</span></span> <span data-ttu-id="d7d85-110">ただし、Web ホストのシナリオでは、<xref:System.ServiceModel.ServiceHost> クラスに直接アクセスできません。</span><span class="sxs-lookup"><span data-stu-id="d7d85-110">In web hosted scenarios, however, you don’t have direct access to the <xref:System.ServiceModel.ServiceHost> class.</span></span> <span data-ttu-id="d7d85-111">Web ホスト サービスを構成するには、`System.ServiceModel.ServiceHostFactory` を作成して必要な構成を実行する <xref:System.ServiceModel.Activation.ServiceHostFactory> を作成する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="d7d85-111">To configure a web hosted service you were required to create a `System.ServiceModel.ServiceHostFactory` that created the <xref:System.ServiceModel.Activation.ServiceHostFactory> and performed any needed configuration.</span></span> <span data-ttu-id="d7d85-112">.NET 4.5 以降、WCF では、自己ホスト型サービスと web ホステッドサービスの両方をコード内で簡単に構成できます。</span><span class="sxs-lookup"><span data-stu-id="d7d85-112">Starting with .NET 4.5, WCF provides an easier way to configure both self-hosted and web hosted services in code.</span></span>  
  
## <a name="the-configure-method"></a><span data-ttu-id="d7d85-113">Configure メソッド</span><span class="sxs-lookup"><span data-stu-id="d7d85-113">The Configure method</span></span>  
 <span data-ttu-id="d7d85-114">サービス実装クラスで、次のシグネチャを持つ `Configure` という名前のパブリックな静的メソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="d7d85-114">Simply define a public static method called `Configure` with the following signature in your service implementation class:</span></span>  
  
```csharp  
public static void Configure(ServiceConfiguration config)  
```  
  
 <span data-ttu-id="d7d85-115">Configure メソッドは、開発者がエンドポイントおよび動作を追加できるようにする <xref:System.ServiceModel.ServiceConfiguration> インスタンスを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="d7d85-115">The Configure method takes a <xref:System.ServiceModel.ServiceConfiguration> instance that enables the developer to add endpoints and behaviors.</span></span> <span data-ttu-id="d7d85-116">このメソッドは、サービスホストが開かれる前に WCF によって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d7d85-116">This method is called by WCF before the service host is opened.</span></span> <span data-ttu-id="d7d85-117">app.config ファイルまたは web.config ファイルで指定されたすべてのサービスの構成設定は、定義されている場合、無視されます。</span><span class="sxs-lookup"><span data-stu-id="d7d85-117">When defined, any service configuration settings specified in an app.config or web.config file will be ignored.</span></span>  
  
 <span data-ttu-id="d7d85-118">次のコード スニペットは、`Configure` メソッドを定義し、サービス エンドポイント、エンドポイントの動作、およびサービスの動作を追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d7d85-118">The following code snippet illustrates how to define the `Configure` method and add a service endpoint, an endpoint behavior and service behaviors:</span></span>  
  
```csharp  
public class Service1 : IService1  
    {  
        public static void Configure(ServiceConfiguration config)  
        {  
            ServiceEndpoint se = new ServiceEndpoint(new ContractDescription("IService1"), new BasicHttpBinding(), new EndpointAddress("basic"));  
            se.Behaviors.Add(new MyEndpointBehavior());  
            config.AddServiceEndpoint(se);  
  
            config.Description.Behaviors.Add(new ServiceMetadataBehavior { HttpGetEnabled = true });  
            config.Description.Behaviors.Add(new ServiceDebugBehavior { IncludeExceptionDetailInFaults = true });  
        }  
  
        public string GetData(int value)  
        {  
            return $"You entered: {value}";
        }  
  
        public CompositeType GetDataUsingDataContract(CompositeType composite)  
        {  
            if (composite == null)  
            {  
                throw new ArgumentNullException("composite");  
            }  
            if (composite.BoolValue)  
            {  
                composite.StringValue += "Suffix";  
            }  
            return composite;  
        }  
    }  
```  
  
 <span data-ttu-id="d7d85-119">サービスで https などのプロトコルを有効にするには、プロトコルを使用するエンドポイントを明示的に追加するか、ServiceConfiguration.EnableProtocol(Binding) を呼び出すことによって自動的にエンドポイントを追加します。このメソッドは、プロトコルおよび定義された各サービス コントラクトと互換性がある各ベース アドレスのエンドポイントを追加します。</span><span class="sxs-lookup"><span data-stu-id="d7d85-119">To enable a protocol such as https for a service, you can either explicitly add an endpoint that uses the protocol or you can automatically add endpoints by calling ServiceConfiguration.EnableProtocol(Binding) which adds an endpoint for each base address compatible with the protocol and each service contract defined.</span></span> <span data-ttu-id="d7d85-120">次のコードは、ServiceConfiguration.EnableProtocol メソッドを使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d7d85-120">The following code illustrates how to use the ServiceConfiguration.EnableProtocol method:</span></span>  
  
```csharp  
public class Service1 : IService1   
{   
    public string GetData(int value);   
    public static void Configure(ServiceConfiguration config)   
    {   
        // Enable "Add Service Reference" support   
       config.Description.Behaviors.Add( new ServiceMetadataBehavior { HttpGetEnabled = true });   
       // set up support for http, https, net.tcp, net.pipe   
       config.EnableProtocol(new BasicHttpBinding());   
       config.EnableProtocol(new BasicHttpBinding());   
       config.EnableProtocol(new NetTcpBinding());   
       config.EnableProtocol(new NetNamedPipeBinding());   
       // add an extra BasicHttpBinding endpoint at http:///basic   
       config.AddServiceEndpoint(typeof(IService1), new BasicHttpBinding(),"basic");   
    }   
}   
```  
  
 <span data-ttu-id="d7d85-121"><`protocolMappings`> セクションの設定は、アプリケーションエンドポイントがプログラムによって<xref:System.ServiceModel.ServiceConfiguration>に追加されていない場合にのみ使用されます。必要に応じて、を呼び出し<xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A>て既定のアプリケーション構成ファイルからサービス構成を読み込んでから、設定を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="d7d85-121">The settings in the <`protocolMappings`> section are only used if no application endpoints are added to the <xref:System.ServiceModel.ServiceConfiguration> programmatically.You can optionally load the service configuration from the default application configuration file by calling <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> and then change the settings.</span></span> <span data-ttu-id="d7d85-122"><xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration> クラスを使って、集中化された構成から構成を読み込むこともできます。</span><span class="sxs-lookup"><span data-stu-id="d7d85-122">The <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration> class also allows you to load configuration from a centralized configuration.</span></span> <span data-ttu-id="d7d85-123">これを実装する方法を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="d7d85-123">The following code illustrates how to implement this:</span></span>  
  
```  
public class Service1 : IService1   
{   
    public void DoWork();   
    public static void Configure(ServiceConfiguration config)   
    {   
          config.LoadFromConfiguration(ConfigurationManager.OpenMappedExeConfiguration(new ExeConfigurationFileMap { ExeConfigFilename = @"c:\sharedConfig\MyConfig.config" }, ConfigurationUserLevel.None));   
    }   
}  
```  
  
> [!IMPORTANT]
> <span data-ttu-id="d7d85-124">では<xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> 、<`service``host`>の<>タグ内の<>設定が無視されることに注意してください。`system.serviceModel`</span><span class="sxs-lookup"><span data-stu-id="d7d85-124">Note that <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> ignores <`host`> settings within the <`service`> tag of <`system.serviceModel`>.</span></span> <span data-ttu-id="d7d85-125">概念的には`host`、< > は、サービス構成ではなくホスト構成に関するものであり、構成メソッドを実行する前に読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="d7d85-125">Conceptually, <`host`> is about host configuration, not service configuration, and it gets loaded before the Configure method executes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7d85-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="d7d85-126">See also</span></span>

- [<span data-ttu-id="d7d85-127">構成ファイルを使用してサービスを構成する方法</span><span class="sxs-lookup"><span data-stu-id="d7d85-127">Configuring Services Using Configuration Files</span></span>](../../../docs/framework/wcf/configuring-services-using-configuration-files.md)
- [<span data-ttu-id="d7d85-128">クライアントの動作の構成</span><span class="sxs-lookup"><span data-stu-id="d7d85-128">Configuring Client Behaviors</span></span>](../../../docs/framework/wcf/configuring-client-behaviors.md)
- [<span data-ttu-id="d7d85-129">簡略化された構成</span><span class="sxs-lookup"><span data-stu-id="d7d85-129">Simplified Configuration</span></span>](../../../docs/framework/wcf/simplified-configuration.md)
- [<span data-ttu-id="d7d85-130">構成</span><span class="sxs-lookup"><span data-stu-id="d7d85-130">Configuration</span></span>](../../../docs/framework/wcf/samples/configuration-sample.md)
- [<span data-ttu-id="d7d85-131">IIS と WAS における構成ベースのアクティブ化</span><span class="sxs-lookup"><span data-stu-id="d7d85-131">Configuration-Based Activation in IIS and WAS</span></span>](../../../docs/framework/wcf/feature-details/configuration-based-activation-in-iis-and-was.md)
- [<span data-ttu-id="d7d85-132">構成とメタデータのサポート</span><span class="sxs-lookup"><span data-stu-id="d7d85-132">Configuration and Metadata Support</span></span>](../../../docs/framework/wcf/extending/configuration-and-metadata-support.md)
- [<span data-ttu-id="d7d85-133">構成</span><span class="sxs-lookup"><span data-stu-id="d7d85-133">Configuration</span></span>](../../../docs/framework/wcf/diagnostics/exceptions-reference/configuration.md)
- [<span data-ttu-id="d7d85-134">方法: 構成でサービスバインディングを指定する</span><span class="sxs-lookup"><span data-stu-id="d7d85-134">How to: Specify a Service Binding in Configuration</span></span>](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)
- [<span data-ttu-id="d7d85-135">方法: 構成にサービスエンドポイントを作成する</span><span class="sxs-lookup"><span data-stu-id="d7d85-135">How to: Create a Service Endpoint in Configuration</span></span>](../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)
- [<span data-ttu-id="d7d85-136">方法: 構成ファイルを使用してサービスのメタデータを公開する</span><span class="sxs-lookup"><span data-stu-id="d7d85-136">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="d7d85-137">方法: 構成でクライアントバインディングを指定する</span><span class="sxs-lookup"><span data-stu-id="d7d85-137">How to: Specify a Client Binding in Configuration</span></span>](../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md)
