---
title: 簡略化された構成
ms.date: 03/30/2017
ms.assetid: dcbe1f84-437c-495f-9324-2bc09fd79ea9
ms.openlocfilehash: 4e316290c045b75896c61e36c1646440c18678e2
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249631"
---
# <a name="simplified-configuration"></a><span data-ttu-id="09b81-102">簡略化された構成</span><span class="sxs-lookup"><span data-stu-id="09b81-102">Simplified Configuration</span></span>
<span data-ttu-id="09b81-103">Windows 通信基盤 (WCF) サービスを構成することは、複雑な作業になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="09b81-103">Configuring Windows Communication Foundation (WCF) services can be a complex task.</span></span> <span data-ttu-id="09b81-104">さまざまなオプションがあり、どの設定が必要であるかをいつでも簡単に判断できるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="09b81-104">There are many different options and it is not always easy to determine what settings are required.</span></span> <span data-ttu-id="09b81-105">構成ファイルは WCF サービスの柔軟性を高めますが、問題を見つけるのが難しい多くのソースでもあります。</span><span class="sxs-lookup"><span data-stu-id="09b81-105">While configuration files increase the flexibility of WCF services, they also are the source for many hard to find problems.</span></span> [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] <span data-ttu-id="09b81-106">では、このような問題に対応し、サービス構成の規模と複雑さを軽減する手段を提供しています。</span><span class="sxs-lookup"><span data-stu-id="09b81-106">addresses these problems and provides a way to reduce the size and complexity of service configuration.</span></span>  
  
## <a name="simplified-configuration"></a><span data-ttu-id="09b81-107">簡略化された構成</span><span class="sxs-lookup"><span data-stu-id="09b81-107">Simplified Configuration</span></span>  
 <span data-ttu-id="09b81-108">WCF サービス構成ファイルでは、<`system.serviceModel`> セクションには`service`、ホストされる各サービスの<>要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="09b81-108">In WCF service configuration files, the <`system.serviceModel`> section contains a <`service`> element for each service hosted.</span></span> <span data-ttu-id="09b81-109">>要素`service`<には、各サービスに公開`endpoint`されるエンドポイントを指定する<>要素のコレクションと、必要に応じて一連のサービス動作が含まれます。</span><span class="sxs-lookup"><span data-stu-id="09b81-109">The <`service`> element contains a collection of <`endpoint`> elements that specify the endpoints exposed for each service and optionally a set of service behaviors.</span></span> <span data-ttu-id="09b81-110"><>`endpoint`要素は、エンドポイントによって公開されるアドレス、バインディング、およびコントラクトを指定し、必要に応じて、構成とエンドポイントの動作をバインドします。</span><span class="sxs-lookup"><span data-stu-id="09b81-110">The <`endpoint`> elements specify the address, binding, and contract exposed by the endpoint, and optionally binding configuration and endpoint behaviors.</span></span> <span data-ttu-id="09b81-111"><`system.serviceModel`> セクションには、サービス`behaviors`またはエンドポイントの動作を指定できる<>要素も含まれています。</span><span class="sxs-lookup"><span data-stu-id="09b81-111">The <`system.serviceModel`> section also contains a <`behaviors`> element that allows you to specify service or endpoint behaviors.</span></span> <span data-ttu-id="09b81-112">次の例は、構成`system.serviceModel`ファイルの<>セクションを示しています。</span><span class="sxs-lookup"><span data-stu-id="09b81-112">The following example shows the <`system.serviceModel`> section of a configuration file.</span></span>  
  
```xml  
<system.serviceModel>  
  <behaviors>  
    <serviceBehaviors>  
      <behavior name="MyServiceBehavior">  
        <serviceMetadata httpGetEnabled="true" />  
        <serviceDebug includeExceptionDetailInFaults="false" />  
      </behavior>  
    </serviceBehaviors>  
  </behaviors>  
  <bindings>  
   <basicHttpBinding>  
      <binding name=MyBindingConfig"  
               maxBufferSize="100"  
               maxReceiveBufferSize="100" />  
   </basicHttpBinding>  
   </bindings>   <services>  
    <service behaviorConfiguration="MyServiceBehavior"  
             name="MyService">  
      <endpoint address=""  
                binding="basicHttpBinding"  
                contract="ICalculator"  
                bindingConfiguration="MyBindingConfig" />  
      <endpoint address="mex"  
                binding="mexHttpBinding"  
                contract="IMetadataExchange"/>  
    </service>  
  </services>  
</system.serviceModel>  
```  
  
 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]<span data-ttu-id="09b81-113"><>要素の要件を削除することで、WCF サービスの`service`構成が容易になります。</span><span class="sxs-lookup"><span data-stu-id="09b81-113">makes configuring a WCF service easier by removing the requirement for the <`service`> element.</span></span> <span data-ttu-id="09b81-114"><`service`> セクションを追加したり、><`service`セクションにエンドポイントを追加したりしない場合、サービスがプログラムでエンドポイントを定義しない場合、サービスに対して 1 つずつ、サービスによって実装される各コントラクトに対して、サービスに対して既定のエンドポイントのセットが自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="09b81-114">If you do not add a <`service`>  section or add any endpoints in a <`service`> section and your service does not programmatically define any endpoints, then a set of default endpoints are automatically added to your service, one for each service base address and for each contract implemented by your service.</span></span> <span data-ttu-id="09b81-115">これらの各エンドポイントでは、エンドポイント アドレスがベース アドレスに対応し、バインドがベース アドレス スキームで決定されます。また、コントラクトは、サービスによって実装されるコントラクトになります。</span><span class="sxs-lookup"><span data-stu-id="09b81-115">In each of these endpoints, the endpoint address corresponds to the base address, the binding is determined by the base address scheme and the contract is the one implemented by your service.</span></span> <span data-ttu-id="09b81-116">エンドポイントまたはサービスの動作を指定する必要も、バインド設定を変更する必要もない場合、サービス構成ファイルを指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="09b81-116">If you do not need to specify any endpoints or service behaviors or make any binding setting changes, you do not need to specify a service configuration file at all.</span></span> <span data-ttu-id="09b81-117">サービスが 2 つのコントラクトを実装し、ホストが HTTP トランスポートと TCP トランスポートの両方を有効にしている場合、サービス ホストは、それぞれのトランスポートを使用する各コントラクトに対して 1 つずつ、合計 4 つの既定のエンドポイントを作成します。</span><span class="sxs-lookup"><span data-stu-id="09b81-117">If a service implements two contracts and the host enables both HTTP and TCP transports the service host creates four default endpoints, one for each contract using each transport.</span></span> <span data-ttu-id="09b81-118">既定のエンドポイントを作成するには、使用するバインドをサービス ホストに伝える必要があります。</span><span class="sxs-lookup"><span data-stu-id="09b81-118">To create default endpoints the service host must know what bindings to use.</span></span> <span data-ttu-id="09b81-119">これらの設定は、<`protocolMappings` `system.serviceModel`> セクション内の<> セクションで指定します。</span><span class="sxs-lookup"><span data-stu-id="09b81-119">These settings are specified in a <`protocolMappings`> section within the <`system.serviceModel`> section.</span></span> <span data-ttu-id="09b81-120"><>`protocolMappings`セクションには、バインディングの種類にマップされたトランスポート プロトコル スキームの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="09b81-120">The <`protocolMappings`> section contains a list of transport protocol schemes mapped to binding types.</span></span> <span data-ttu-id="09b81-121">サービス ホストは、渡されたベース アドレスを使用して、使用するバインドを決定します。</span><span class="sxs-lookup"><span data-stu-id="09b81-121">The service host uses the base addresses passed to it to determine which binding to use.</span></span> <span data-ttu-id="09b81-122">次の例では、<>`protocolMappings`要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="09b81-122">The following example uses the <`protocolMappings`> element.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="09b81-123">バインディングまたは動作のような既定の構成要素を変更すると、構成階層の下のレベルで定義されたサービスはこれらの既定のバインディングおよび動作を使用している可能性があるため、影響を受けることがあります。</span><span class="sxs-lookup"><span data-stu-id="09b81-123">Changing default configuration elements, such as bindings or behaviors, might affect services defined in lower levels of the configuration hierarchy, since they might be using these default bindings and behaviors.</span></span> <span data-ttu-id="09b81-124">したがって、既定のバインディングおよび動作を変更する場合は、これらの変更が階層の他のサービスに影響を与える可能性があることに注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09b81-124">Thus, whoever changes default bindings and behaviors needs to be aware that these changes might affect other services in the hierarchy.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="09b81-125">インターネット インフォメーション サービス (IIS) または Windows プロセス アクティブ化サービス (WAS) にホストされるサービスは、仮想ディレクトリをベース アドレスとして使用します。</span><span class="sxs-lookup"><span data-stu-id="09b81-125">Services hosted under Internet Information Services (IIS) or Windows Process Activation Service (WAS) use the virtual directory as their base address.</span></span>  
  
```xml  
<protocolMapping>  
  <add scheme="http"     binding="basicHttpBinding" bindingConfiguration="MyBindingConfiguration"/>  
  <add scheme="net.tcp"  binding="netTcpBinding"/>  
  <add scheme="net.pipe" binding="netNamedPipeBinding"/>  
  <add scheme="net.msmq" binding="netMSMQBinding"/>  
</protocolMapping>  
```  
  
 <span data-ttu-id="09b81-126">前の例では、"http" スキームで始まるベース アドレスのエンドポイントは、<xref:System.ServiceModel.BasicHttpBinding> を使用します。</span><span class="sxs-lookup"><span data-stu-id="09b81-126">In the previous example, an endpoint with a base address that starts with the "http" scheme uses the <xref:System.ServiceModel.BasicHttpBinding>.</span></span> <span data-ttu-id="09b81-127">"net.tcp" スキームで始まるベース アドレスのエンドポイントは、<xref:System.ServiceModel.NetTcpBinding> を使用します。</span><span class="sxs-lookup"><span data-stu-id="09b81-127">An endpoint with a base address that starts with the "net.tcp" scheme uses the <xref:System.ServiceModel.NetTcpBinding>.</span></span> <span data-ttu-id="09b81-128">ローカルの App.config または Web.config ファイルの設定はオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="09b81-128">You can override settings in a local App.config or Web.config file.</span></span>  
  
 <span data-ttu-id="09b81-129"><>`protocolMappings`セクション内の各要素は、スキームとバインディングを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09b81-129">Each element within the <`protocolMappings`> section must specify a scheme and a binding.</span></span> <span data-ttu-id="09b81-130">必要に応じて、構成`bindingConfiguration`ファイルの<>`bindings`セクション内のバインディング構成を指定する属性を指定できます。</span><span class="sxs-lookup"><span data-stu-id="09b81-130">Optionally it can specify a `bindingConfiguration` attribute that specifies a binding configuration within the <`bindings`> section of the configuration file.</span></span> <span data-ttu-id="09b81-131">`bindingConfiguration` が指定されていない場合は、適切なバインド型の匿名バインド構成が使用されます。</span><span class="sxs-lookup"><span data-stu-id="09b81-131">If no `bindingConfiguration` is specified, the anonymous binding configuration of the appropriate binding type is used.</span></span>  
  
 <span data-ttu-id="09b81-132">サービス動作は、<> セクション内の匿名<>`behavior`セクションを使用して`serviceBehaviors`、既定のエンドポイントに対して構成されます。</span><span class="sxs-lookup"><span data-stu-id="09b81-132">Service behaviors are configured for the default endpoints by using anonymous <`behavior`> sections within <`serviceBehaviors`> sections.</span></span> <span data-ttu-id="09b81-133">名前のない<>`behavior`要素<>`serviceBehaviors`内でサービスの動作を構成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="09b81-133">Any unnamed <`behavior`> elements within <`serviceBehaviors`> are used to configure service behaviors.</span></span> <span data-ttu-id="09b81-134">たとえば、次の構成ファイルでは、ホスト内のすべてのサービスで、サービス メタデータの公開が有効になります。</span><span class="sxs-lookup"><span data-stu-id="09b81-134">For example, the following configuration file enables service metadata publishing for all services within the host.</span></span>  
  
```xml  
<system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>    <!-- No <service> tag is necessary. Default endpoints are added to the service -->  
    <!-- The service behavior with name="" is picked up by the service -->  
 </system.serviceModel>  
```  
  
 <span data-ttu-id="09b81-135">エンドポイントの動作は、>セクション内の`behavior`匿名<>`serviceBehaviors`セクション<使用して構成されます。</span><span class="sxs-lookup"><span data-stu-id="09b81-135">Endpoint behaviors are configured by using anonymous <`behavior`> sections within <`serviceBehaviors`> sections.</span></span>  
  
 <span data-ttu-id="09b81-136">以下は、このトピックの最初にある例と同じ内容ですが、簡略化された構成モデルを使用している構成ファイルの例です。</span><span class="sxs-lookup"><span data-stu-id="09b81-136">The following example is a configuration file equivalent to the one at the beginning of this topic that uses the simplified configuration model.</span></span>  
  
```xml  
<system.serviceModel>
    <behaviors>
      <serviceBehaviors>
        <behavior>
          <serviceMetadata httpGetEnabled="true" />
          <serviceDebug includeExceptionDetailInFaults="false" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
    <bindings>
       <basicHttpBinding>
          <binding maxBufferSize="100"
                   maxReceiveBufferSize="100" />
       </basicHttpBinding>
    </bindings>
    <!-- No <service> tag is necessary. Default endpoints will be added to the service -->
    <!-- The service behavior with name="" will be picked up by the service -->
    <protocolMapping>
      <add scheme="http" binding="basicHttpBinding" />
  </protocolMapping>
  </system.serviceModel>
```  
  
> [!IMPORTANT]
> <span data-ttu-id="09b81-137">この機能は、WCF サービス構成にのみ適用され、クライアント構成には適用されません。</span><span class="sxs-lookup"><span data-stu-id="09b81-137">This feature relates only to WCF service configuration, not client configuration.</span></span> <span data-ttu-id="09b81-138">ほとんどの場合、WCF クライアント構成は、svcutil.exe などのツールを使用したり、Visual Studio からサービス参照を追加したりすることで生成されます。</span><span class="sxs-lookup"><span data-stu-id="09b81-138">Most times, WCF client configuration will be generated by a tool such as svcutil.exe or adding a service reference from Visual Studio.</span></span> <span data-ttu-id="09b81-139">WCF クライアントを手動で構成する場合は、\<クライアント>要素を構成に追加し、呼び出すエンドポイントを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09b81-139">If you are manually configuring a WCF client you will need to add a \<client> element to the configuration and specify any endpoints you wish to call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09b81-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="09b81-140">See also</span></span>

- [<span data-ttu-id="09b81-141">構成ファイルを使用してサービスを構成する方法</span><span class="sxs-lookup"><span data-stu-id="09b81-141">Configuring Services Using Configuration Files</span></span>](configuring-services-using-configuration-files.md)
- [<span data-ttu-id="09b81-142">サービスのバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="09b81-142">Configuring Bindings for Services</span></span>](configuring-bindings-for-wcf-services.md)
- [<span data-ttu-id="09b81-143">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="09b81-143">Configuring System-Provided Bindings</span></span>](./feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="09b81-144">サービスの構成</span><span class="sxs-lookup"><span data-stu-id="09b81-144">Configuring Services</span></span>](configuring-services.md)
- [<span data-ttu-id="09b81-145">WCF サービスの構成</span><span class="sxs-lookup"><span data-stu-id="09b81-145">Configuring WCF services</span></span>](configuring-services.md)
- [<span data-ttu-id="09b81-146">コード内での WCF サービスの構成</span><span class="sxs-lookup"><span data-stu-id="09b81-146">Configuring WCF Services in Code</span></span>](configuring-wcf-services-in-code.md)
