---
title: クライアント構成
ms.date: 03/30/2017
ms.assetid: 5da5bd3b-65d9-43b7-91b9-cc9e989b1350
ms.openlocfilehash: 141b7f7fc04f98f267ce520544fb89451beac7b6
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463866"
---
# <a name="client-configuration"></a><span data-ttu-id="bdd92-102">クライアント構成</span><span class="sxs-lookup"><span data-stu-id="bdd92-102">Client Configuration</span></span>
<span data-ttu-id="bdd92-103">Windows 通信基盤 (WCF) クライアント構成を使用して、クライアントがサービス エンドポイントへの接続に使用するクライアント エンドポイントの "ABC" プロパティであるアドレス、バインディング、動作、およびコントラクトを指定できます。</span><span class="sxs-lookup"><span data-stu-id="bdd92-103">You can use the Windows Communication Foundation (WCF) client configuration to specify the address, binding, behavior, and contract, the "ABC" properties of the client endpoint, which clients use to connect to service endpoints.</span></span> <span data-ttu-id="bdd92-104">クライアント>要素には[\<、エンドポイント>](../../configure-apps/file-schema/wcf/endpoint-of-client.md)要素があり、その属性はエンドポイントの AFC を構成するために使用されます。 [ \<](../../configure-apps/file-schema/wcf/client.md)</span><span class="sxs-lookup"><span data-stu-id="bdd92-104">The [\<client>](../../configure-apps/file-schema/wcf/client.md) element has an [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-of-client.md) element whose attributes are used to configure the endpoint ABCs.</span></span> <span data-ttu-id="bdd92-105">これらの属性については、「[エンドポイントの構成」](#configuring-endpoints)セクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="bdd92-105">These attributes are discussed in the [Configuring Endpoints](#configuring-endpoints) section.</span></span>  
  
 <span data-ttu-id="bdd92-106">エンドポイント>要素には、メタデータ[\<>メタデータの](../../configure-apps/file-schema/wcf/metadata.md)インポートとエクスポートの設定を指定するために使用されるメタデータ要素、カスタム アドレス[\<ヘッダー](../../configure-apps/file-schema/wcf/headers.md)のコレクションを含むヘッダー>要素、および他のエンドポイントがメッセージを交換するエンドポイントの認証を有効にする[\<id>](../../configure-apps/file-schema/wcf/identity.md)要素も含まれます。 [ \<](../../configure-apps/file-schema/wcf/endpoint-of-client.md)</span><span class="sxs-lookup"><span data-stu-id="bdd92-106">The [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-of-client.md) element also contains a [\<metadata>](../../configure-apps/file-schema/wcf/metadata.md) element that is used to specify settings for importing and exporting metadata, a [\<headers>](../../configure-apps/file-schema/wcf/headers.md) element that contains a collection of custom address headers, and an [\<identity>](../../configure-apps/file-schema/wcf/identity.md) element that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span> <span data-ttu-id="bdd92-107">ヘッダー>と[\<id>](../../configure-apps/file-schema/wcf/identity.md)要素は、の一<xref:System.ServiceModel.EndpointAddress>部であり、[アドレス](../../wcf/feature-details/endpoint-addresses.md)の記事で説明します。 [ \<](../../configure-apps/file-schema/wcf/headers.md)</span><span class="sxs-lookup"><span data-stu-id="bdd92-107">The [\<headers>](../../configure-apps/file-schema/wcf/headers.md) and [\<identity>](../../configure-apps/file-schema/wcf/identity.md) elements are part of the <xref:System.ServiceModel.EndpointAddress> and are discussed in the [Addresses](../../wcf/feature-details/endpoint-addresses.md) article.</span></span> <span data-ttu-id="bdd92-108">メタデータ拡張機能の使用について説明するトピックへのリンクは、「[メタデータの構成」セクションに](#configuring-metadata)記載されています。</span><span class="sxs-lookup"><span data-stu-id="bdd92-108">Links to topics that explain the use of metadata extensions are provided in the [Configuring Metadata](#configuring-metadata) section.</span></span>  
  
## <a name="configuring-endpoints"></a><span data-ttu-id="bdd92-109">エンドポイントの構成</span><span class="sxs-lookup"><span data-stu-id="bdd92-109">Configuring Endpoints</span></span>  
 <span data-ttu-id="bdd92-110">クライアント構成は、クライアントが 1 つ以上のエンドポイントを指定できるように設計されており、各エンドポイントは独自の名前、アドレス、およびコントラクトを持ち、各エンドポイントは[\<、その](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)エンドポイントを構成するために使用するクライアント構成[\<の要素>バインディング>と動作](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)を参照します。</span><span class="sxs-lookup"><span data-stu-id="bdd92-110">The client configuration is designed to allow the client to specify one or more endpoints, each with its own name, address, and contract, with each referencing the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) and [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elements in the client configuration to be used to configure that endpoint.</span></span> <span data-ttu-id="bdd92-111">クライアント構成ファイルは、WCF ランタイムが予期する名前であるため、"App.config" という名前にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bdd92-111">The client configuration file should be named "App.config" because this is the name that the WCF runtime expects.</span></span> <span data-ttu-id="bdd92-112">クライアント構成ファイルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="bdd92-112">The following example shows a client configuration file.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
        <client>  
          <endpoint  
            name="endpoint1"  
            address="http://localhost/ServiceModelSamples/service.svc"  
            binding="wsHttpBinding"  
            bindingConfiguration="WSHttpBinding_IHello"  
            behaviorConfiguration="IHello_Behavior"  
            contract="IHello" >  
  
            <metadata>  
              <wsdlImporters>  
                <extension  
                  type="Microsoft.ServiceModel.Samples.WsdlDocumentationImporter, WsdlDocumentation"/>  
              </wsdlImporters>  
            </metadata>  
  
            <identity>  
              <servicePrincipalName value="host/localhost" />  
            </identity>  
          </endpoint>  
            <!-- Add another endpoint by adding another <endpoint> element. -->
          <endpoint  
            name="endpoint2">  
           //Configure another endpoint here.  
          </endpoint>  
        </client>  
  
//The bindings section references by the bindingConfiguration endpoint attribute.  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_IHello"
                 bypassProxyOnLocal="false"
                 hostNameComparisonMode="StrongWildcard">  
          <readerQuotas maxDepth="32"/>  
          <reliableSession ordered="true"
                           enabled="false" />  
          <security mode="Message">  
           //Security settings go here.  
          </security>  
        </binding>  
        <binding name="Another Binding"  
          <!-- Configure this binding here. -->  
        </binding>  
          </wsHttpBinding>  
     </bindings>  
  
//The behavior section references by the behaviorConfiguration endpoint attribute.  
        <behaviors>  
            <endpointBehaviors>  
                <behavior name=" IHello_Behavior ">  
                    <clientVia />  
                </behavior>  
            </endpointBehaviors>  
        </behaviors>  
  
    </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="bdd92-113">省略可能な `name` 属性は、特定のコントラクトのエンドポイントを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="bdd92-113">The optional `name` attribute uniquely identifies an endpoint for a given contract.</span></span> <span data-ttu-id="bdd92-114">この属性は、サービスへのチャネルの作成時に、クライアント構成のどのエンドポイントをターゲットとし、読み込む必要があるかを指定するために、<xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> または <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> が使用します。</span><span class="sxs-lookup"><span data-stu-id="bdd92-114">It is used by the <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> or by the <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> to specify which endpoint in the client configuration is being targeted and must be loaded when a channel is created to service.</span></span> <span data-ttu-id="bdd92-115">ワイルドカード エンドポイント構成名\*" " は使用可能で<xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A>、ファイル内のエンドポイント構成を読み込む必要があることをメソッドに示します。</span><span class="sxs-lookup"><span data-stu-id="bdd92-115">A wildcard endpoint configuration name "\*" is available and indicates to the <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A> method that it should load any endpoint configuration in the file, provided there is precisely one available, and otherwise throws an exception.</span></span> <span data-ttu-id="bdd92-116">この属性が省略されている場合、指定されたコントラクトの種類に関連する既定のエンドポイントとして、対応するエンドポイントが使用されます。</span><span class="sxs-lookup"><span data-stu-id="bdd92-116">If this attribute is omitted, the corresponding endpoint is used as the default endpoint associated with the specified contract type.</span></span> <span data-ttu-id="bdd92-117">`name` 属性の既定値は、他の名前と同様に一致する空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="bdd92-117">The default value for the `name` attribute is an empty string which is matched like any other name.</span></span>  
  
 <span data-ttu-id="bdd92-118">すべてのエンドポイントには、エンドポイントを検索および識別するために、アドレスが関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bdd92-118">Every endpoint must have an address associated with it to locate and identify the endpoint.</span></span> <span data-ttu-id="bdd92-119">`address` 属性は、エンドポイントの場所を示す URL を指定するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="bdd92-119">The `address` attribute can be used to specify the URL that provides the location of the endpoint.</span></span> <span data-ttu-id="bdd92-120">ただし、サービス エンドポイントのアドレスは、コードで指定することもできます。その場合は、URI (Uniform Resource Identifier) を作成し、<xref:System.ServiceModel.ServiceHost> メソッドのいずれかを使用して、この URI を <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> に追加します。</span><span class="sxs-lookup"><span data-stu-id="bdd92-120">But the address for a service endpoint can also be specified in code by creating a Uniform Resource Identifier (URI) and is added to the <xref:System.ServiceModel.ServiceHost> using one of the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> methods.</span></span> <span data-ttu-id="bdd92-121">詳細については、「アドレス」を参照[してください](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md)。</span><span class="sxs-lookup"><span data-stu-id="bdd92-121">For more information, see [Addresses](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md).</span></span> <span data-ttu-id="bdd92-122">序文が示すように、[\<ヘッダー>](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)と[\<id>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)要素は、の<xref:System.ServiceModel.EndpointAddress>一部であり、[また、アドレス](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md)トピックで説明します。</span><span class="sxs-lookup"><span data-stu-id="bdd92-122">As the introduction indicates, the [\<headers>](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) and [\<identity>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) elements are part of the <xref:System.ServiceModel.EndpointAddress> and are also discussed in the [Addresses](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md) topic.</span></span>  
  
 <span data-ttu-id="bdd92-123">`binding` 属性は、エンドポイントがサービスに接続する際に使用するバインディングの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="bdd92-123">The `binding` attribute indicates the type of binding the endpoint expects to use when connecting to a service.</span></span> <span data-ttu-id="bdd92-124">参照できるようにするには、種類は登録された構成セクションを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bdd92-124">The type must have a registered configuration section if it is to be referenced.</span></span> <span data-ttu-id="bdd92-125">前の例では、これは[\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)セクションで、エンドポイントが<xref:System.ServiceModel.WSHttpBinding>を使用することを示します。</span><span class="sxs-lookup"><span data-stu-id="bdd92-125">In the previous example, this is the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) section, which indicates that the endpoint uses a <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="bdd92-126">ただし、エンドポイントが使用できる、指定された種類のバインディングが複数存在することもあります。</span><span class="sxs-lookup"><span data-stu-id="bdd92-126">But there may be more than one binding of a given type that the endpoint can use.</span></span> <span data-ttu-id="bdd92-127">これらの要素のそれぞれは、(バインディング)型要素内で独自[\<のバインディング>](../../configure-apps/file-schema/wcf/bindings.md)要素を持ちます。</span><span class="sxs-lookup"><span data-stu-id="bdd92-127">Each of these has its own [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element within the (binding) type element.</span></span> <span data-ttu-id="bdd92-128">`bindingconfiguration` 属性は、同じ種類のバインディングを識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="bdd92-128">The `bindingconfiguration` attribute is used to distinguish between bindings of the same type.</span></span> <span data-ttu-id="bdd92-129">その値は`name`[\<、バインド>](../../configure-apps/file-schema/wcf/bindings.md)要素の属性と一致します。</span><span class="sxs-lookup"><span data-stu-id="bdd92-129">Its value is matched with the `name` attribute of the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element.</span></span> <span data-ttu-id="bdd92-130">構成を使用してクライアント のバインドを構成する方法の詳細については、「[方法 : 構成でクライアント バインドを指定する](../../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bdd92-130">For more information about how to configure a client binding using configuration, see [How to: Specify a Client Binding in Configuration](../../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md).</span></span>  
  
 <span data-ttu-id="bdd92-131">この`behaviorConfiguration`属性は、[\<エンドポイント](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)の[\<>動作](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)を指定するために使用>、エンドポイントが使用する動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="bdd92-131">The `behaviorConfiguration` attribute is used to specify which [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) of the [\<endpointBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) the endpoint should use.</span></span> <span data-ttu-id="bdd92-132">その値は、動作`name`[\<>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)要素の属性と一致します。</span><span class="sxs-lookup"><span data-stu-id="bdd92-132">Its value is matched with the `name` attribute of the [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element.</span></span> <span data-ttu-id="bdd92-133">クライアントの動作を指定する構成の使用例については、「[クライアント動作の構成」](../../../../docs/framework/wcf/configuring-client-behaviors.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bdd92-133">For an example of using configuration to specify client behaviors, see [Configuring Client Behaviors](../../../../docs/framework/wcf/configuring-client-behaviors.md).</span></span>  
  
 <span data-ttu-id="bdd92-134">`contract` 属性は、エンドポイントが公開するコントラクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="bdd92-134">The `contract` attribute specifies which contract the endpoint is exposing.</span></span> <span data-ttu-id="bdd92-135">この値は、<xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> の <xref:System.ServiceModel.ServiceContractAttribute> にマップされます。</span><span class="sxs-lookup"><span data-stu-id="bdd92-135">This value maps to the <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> of the <xref:System.ServiceModel.ServiceContractAttribute>.</span></span> <span data-ttu-id="bdd92-136">既定値は、サービスを実装するクラスの完全な型名です。</span><span class="sxs-lookup"><span data-stu-id="bdd92-136">The default value is the full type name of the class that implements the service.</span></span>  
  
### <a name="configuring-metadata"></a><span data-ttu-id="bdd92-137">メタデータの構成</span><span class="sxs-lookup"><span data-stu-id="bdd92-137">Configuring Metadata</span></span>  
 <span data-ttu-id="bdd92-138">[\<メタデータ>](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md)要素は、メタデータ インポート拡張機能の登録に使用される設定を指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="bdd92-138">The [\<metadata>](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md) element is used to specify settings used to register metadata import extensions.</span></span> <span data-ttu-id="bdd92-139">メタデータ システムの拡張の詳細については、「メタデータ[システムの拡張](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bdd92-139">For more information about extending the metadata system, see [Extending the Metadata System](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdd92-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="bdd92-140">See also</span></span>

- [<span data-ttu-id="bdd92-141">エンドポイント:アドレス、バインディング、およびコントラクト</span><span class="sxs-lookup"><span data-stu-id="bdd92-141">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
- [<span data-ttu-id="bdd92-142">クライアントの動作の構成</span><span class="sxs-lookup"><span data-stu-id="bdd92-142">Configuring Client Behaviors</span></span>](../../../../docs/framework/wcf/configuring-client-behaviors.md)
