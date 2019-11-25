---
title: クライアント構成
ms.date: 03/30/2017
ms.assetid: 5da5bd3b-65d9-43b7-91b9-cc9e989b1350
ms.openlocfilehash: 6a5cbf5d536af8649b0b8bb93600e94a48c507c1
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141772"
---
# <a name="client-configuration"></a><span data-ttu-id="50696-102">クライアント構成</span><span class="sxs-lookup"><span data-stu-id="50696-102">Client Configuration</span></span>
<span data-ttu-id="50696-103">Windows Communication Foundation (WCF) クライアント構成を使用して、クライアントエンドポイントの "ABC" プロパティであるアドレス、バインド、動作、およびコントラクトを指定できます。このプロパティは、クライアントがサービスエンドポイントに接続するために使用します。</span><span class="sxs-lookup"><span data-stu-id="50696-103">You can use the Windows Communication Foundation (WCF) client configuration to specify the address, binding, behavior, and contract, the "ABC" properties of the client endpoint, which clients use to connect to service endpoints.</span></span> <span data-ttu-id="50696-104">[\<client >](../../configure-apps/file-schema/wcf/client.md)要素には、エンドポイント abcs の構成に使用される属性を持つ[\<エンドポイント >](../../configure-apps/file-schema/wcf/endpoint-of-client.md)要素があります。</span><span class="sxs-lookup"><span data-stu-id="50696-104">The [\<client>](../../configure-apps/file-schema/wcf/client.md) element has an [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-of-client.md) element whose attributes are used to configure the endpoint ABCs.</span></span> <span data-ttu-id="50696-105">これらの属性については、「[エンドポイントの構成](#configuring-endpoints)」セクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="50696-105">These attributes are discussed in the [Configuring Endpoints](#configuring-endpoints) section.</span></span>  
  
 <span data-ttu-id="50696-106">[\<エンドポイントの >](../../configure-apps/file-schema/wcf/endpoint-of-client.md)要素には、メタデータのインポートとエクスポートの設定を指定したり、カスタムアドレスヘッダーのコレクションを格納する\<[ヘッダー >](../../configure-apps/file-schema/wcf/headers.md)要素を使用したり、メッセージを交換する他のエンドポイントによるエンドポイントの認証を可能にする[\<id >](../../configure-apps/file-schema/wcf/identity.md)要素も含ま[\<](../../configure-apps/file-schema/wcf/metadata.md)れます。</span><span class="sxs-lookup"><span data-stu-id="50696-106">The [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-of-client.md) element also contains a [\<metadata>](../../configure-apps/file-schema/wcf/metadata.md) element that is used to specify settings for importing and exporting metadata, a [\<headers>](../../configure-apps/file-schema/wcf/headers.md) element that contains a collection of custom address headers, and an [\<identity>](../../configure-apps/file-schema/wcf/identity.md) element that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span> <span data-ttu-id="50696-107">[\<ヘッダー >](../../configure-apps/file-schema/wcf/headers.md)と[\<id >](../../configure-apps/file-schema/wcf/identity.md)要素は <xref:System.ServiceModel.EndpointAddress> に含まれており、[アドレス](../../wcf/feature-details/endpoint-addresses.md)に関する記事で説明されています。</span><span class="sxs-lookup"><span data-stu-id="50696-107">The [\<headers>](../../configure-apps/file-schema/wcf/headers.md) and [\<identity>](../../configure-apps/file-schema/wcf/identity.md) elements are part of the <xref:System.ServiceModel.EndpointAddress> and are discussed in the [Addresses](../../wcf/feature-details/endpoint-addresses.md) article.</span></span> <span data-ttu-id="50696-108">メタデータ拡張機能の使用方法について説明するトピックへのリンクについては、「[メタデータの構成](#configuring-metadata)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="50696-108">Links to topics that explain the use of metadata extensions are provided in the [Configuring Metadata](#configuring-metadata) section.</span></span>  
  
## <a name="configuring-endpoints"></a><span data-ttu-id="50696-109">エンドポイントの構成</span><span class="sxs-lookup"><span data-stu-id="50696-109">Configuring Endpoints</span></span>  
 <span data-ttu-id="50696-110">クライアント構成は、クライアントが1つまたは複数のエンドポイントを指定できるように設計されています。各エンドポイントには、それぞれ独自の名前、アドレス、およびコントラクトがあります。各エンドポイントは[\<バインド >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)を参照し、 [\<動作](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)は、エンドポイントを構成するために使用されるクライアント構成の要素 > ます。</span><span class="sxs-lookup"><span data-stu-id="50696-110">The client configuration is designed to allow the client to specify one or more endpoints, each with its own name, address, and contract, with each referencing the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) and [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elements in the client configuration to be used to configure that endpoint.</span></span> <span data-ttu-id="50696-111">クライアント構成ファイルは、WCF ランタイムが想定している名前であるため、"App.config" という名前にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="50696-111">The client configuration file should be named "App.config" because this is the name that the WCF runtime expects.</span></span> <span data-ttu-id="50696-112">クライアント構成ファイルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="50696-112">The following example shows a client configuration file.</span></span>  
  
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
// Add another endpoint by adding another <endpoint> element.  
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
        //Configure this binding here.  
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
  
 <span data-ttu-id="50696-113">省略可能な `name` 属性は、特定のコントラクトのエンドポイントを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="50696-113">The optional `name` attribute uniquely identifies an endpoint for a given contract.</span></span> <span data-ttu-id="50696-114">この属性は、サービスへのチャネルの作成時に、クライアント構成のどのエンドポイントをターゲットとし、読み込む必要があるかを指定するために、<xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> または <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> が使用します。</span><span class="sxs-lookup"><span data-stu-id="50696-114">It is used by the <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> or by the <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> to specify which endpoint in the client configuration is being targeted and must be loaded when a channel is created to service.</span></span> <span data-ttu-id="50696-115">ワイルドカードエンドポイント構成名 "\*" を使用できます。また、使用可能なエンドポイントが1つある場合は、ファイルにエンドポイント構成を読み込む必要があることを <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A> メソッドに示します。それ以外の場合は、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="50696-115">A wildcard endpoint configuration name "\*" is available and indicates to the <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A> method that it should load any endpoint configuration in the file, provided there is precisely one available, and otherwise throws an exception.</span></span> <span data-ttu-id="50696-116">この属性が省略されている場合、指定されたコントラクトの種類に関連する既定のエンドポイントとして、対応するエンドポイントが使用されます。</span><span class="sxs-lookup"><span data-stu-id="50696-116">If this attribute is omitted, the corresponding endpoint is used as the default endpoint associated with the specified contract type.</span></span> <span data-ttu-id="50696-117">`name` 属性の既定値は、他の名前と同様に一致する空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="50696-117">The default value for the `name` attribute is an empty string which is matched like any other name.</span></span>  
  
 <span data-ttu-id="50696-118">すべてのエンドポイントには、エンドポイントを検索および識別するために、アドレスが関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="50696-118">Every endpoint must have an address associated with it to locate and identify the endpoint.</span></span> <span data-ttu-id="50696-119">`address` 属性は、エンドポイントの場所を示す URL を指定するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="50696-119">The `address` attribute can be used to specify the URL that provides the location of the endpoint.</span></span> <span data-ttu-id="50696-120">ただし、サービス エンドポイントのアドレスは、コードで指定することもできます。その場合は、URI (Uniform Resource Identifier) を作成し、<xref:System.ServiceModel.ServiceHost> メソッドのいずれかを使用して、この URI を <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> に追加します。</span><span class="sxs-lookup"><span data-stu-id="50696-120">But the address for a service endpoint can also be specified in code by creating a Uniform Resource Identifier (URI) and is added to the <xref:System.ServiceModel.ServiceHost> using one of the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> methods.</span></span> <span data-ttu-id="50696-121">詳細については、「[アドレス](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="50696-121">For more information, see [Addresses](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md).</span></span> <span data-ttu-id="50696-122">概要を示すように、 [\<ヘッダー >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)と[\<id >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)要素は <xref:System.ServiceModel.EndpointAddress> の一部であり、「[アドレス](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md)」のトピックでも説明されています。</span><span class="sxs-lookup"><span data-stu-id="50696-122">As the introduction indicates, the [\<headers>](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) and [\<identity>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) elements are part of the <xref:System.ServiceModel.EndpointAddress> and are also discussed in the [Addresses](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md) topic.</span></span>  
  
 <span data-ttu-id="50696-123">`binding` 属性は、エンドポイントがサービスに接続する際に使用するバインディングの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="50696-123">The `binding` attribute indicates the type of binding the endpoint expects to use when connecting to a service.</span></span> <span data-ttu-id="50696-124">参照できるようにするには、種類は登録された構成セクションを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="50696-124">The type must have a registered configuration section if it is to be referenced.</span></span> <span data-ttu-id="50696-125">前の例では、これは[\<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)セクションです。これは、エンドポイントが <xref:System.ServiceModel.WSHttpBinding>を使用することを示します。</span><span class="sxs-lookup"><span data-stu-id="50696-125">In the previous example, this is the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) section, which indicates that the endpoint uses a <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="50696-126">ただし、エンドポイントが使用できる、指定された種類のバインディングが複数存在することもあります。</span><span class="sxs-lookup"><span data-stu-id="50696-126">But there may be more than one binding of a given type that the endpoint can use.</span></span> <span data-ttu-id="50696-127">これらのそれぞれには、(binding) type 要素内の独自の[\<バインド >](../../configure-apps/file-schema/wcf/bindings.md)要素があります。</span><span class="sxs-lookup"><span data-stu-id="50696-127">Each of these has its own [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element within the (binding) type element.</span></span> <span data-ttu-id="50696-128">`bindingconfiguration` 属性は、同じ種類のバインディングを識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="50696-128">The `bindingconfiguration` attribute is used to distinguish between bindings of the same type.</span></span> <span data-ttu-id="50696-129">この値は、 [\<binding >](../../configure-apps/file-schema/wcf/bindings.md)要素の `name` 属性と一致します。</span><span class="sxs-lookup"><span data-stu-id="50696-129">Its value is matched with the `name` attribute of the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element.</span></span> <span data-ttu-id="50696-130">構成を使用してクライアントバインディングを構成する方法の詳細については、「[方法: 構成でクライアントバインディングを指定](../../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="50696-130">For more information about how to configure a client binding using configuration, see [How to: Specify a Client Binding in Configuration](../../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md).</span></span>  
  
 <span data-ttu-id="50696-131">`behaviorConfiguration` 属性は、エンドポイントが使用する[\<endpointBehaviors behaviors](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)の[\<動作](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)を指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="50696-131">The `behaviorConfiguration` attribute is used to specify which [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) of the [\<endpointBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) the endpoint should use.</span></span> <span data-ttu-id="50696-132">値は、 [\<behavior >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)要素の `name` 属性と一致します。</span><span class="sxs-lookup"><span data-stu-id="50696-132">Its value is matched with the `name` attribute of the [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element.</span></span> <span data-ttu-id="50696-133">構成を使用してクライアントの動作を指定する例については、「[クライアントの動作の構成](../../../../docs/framework/wcf/configuring-client-behaviors.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="50696-133">For an example of using configuration to specify client behaviors, see [Configuring Client Behaviors](../../../../docs/framework/wcf/configuring-client-behaviors.md).</span></span>  
  
 <span data-ttu-id="50696-134">`contract` 属性は、エンドポイントが公開するコントラクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="50696-134">The `contract` attribute specifies which contract the endpoint is exposing.</span></span> <span data-ttu-id="50696-135">この値は、<xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> の <xref:System.ServiceModel.ServiceContractAttribute> にマップされます。</span><span class="sxs-lookup"><span data-stu-id="50696-135">This value maps to the <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> of the <xref:System.ServiceModel.ServiceContractAttribute>.</span></span> <span data-ttu-id="50696-136">既定値は、サービスを実装するクラスの完全な型名です。</span><span class="sxs-lookup"><span data-stu-id="50696-136">The default value is the full type name of the class that implements the service.</span></span>  
  
### <a name="configuring-metadata"></a><span data-ttu-id="50696-137">メタデータの構成</span><span class="sxs-lookup"><span data-stu-id="50696-137">Configuring Metadata</span></span>  
 <span data-ttu-id="50696-138">メタデータのインポート拡張を登録するために使用する設定を指定するには、 [\<metadata >](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md)要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="50696-138">The [\<metadata>](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md) element is used to specify settings used to register metadata import extensions.</span></span> <span data-ttu-id="50696-139">メタデータシステムの拡張の詳細については、「[メタデータシステムの拡張](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="50696-139">For more information about extending the metadata system, see [Extending the Metadata System](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50696-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="50696-140">See also</span></span>

- [<span data-ttu-id="50696-141">エンドポイント : アドレス、バインディング、およびコントラクト</span><span class="sxs-lookup"><span data-stu-id="50696-141">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
- [<span data-ttu-id="50696-142">クライアントの動作の構成</span><span class="sxs-lookup"><span data-stu-id="50696-142">Configuring Client Behaviors</span></span>](../../../../docs/framework/wcf/configuring-client-behaviors.md)
