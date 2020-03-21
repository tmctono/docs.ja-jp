---
title: トランスポート セキュリティと証明書認証
ms.date: 03/30/2017
dev_langs:
- csharp
ms.assetid: 3d726b71-4d8b-4581-a3bb-02b9af51d11b
ms.openlocfilehash: ad2f0922afbd94e1699b383cf2fc9762771b637d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184327"
---
# <a name="transport-security-with-certificate-authentication"></a><span data-ttu-id="8decc-102">トランスポート セキュリティと証明書認証</span><span class="sxs-lookup"><span data-stu-id="8decc-102">Transport Security with Certificate Authentication</span></span>

<span data-ttu-id="8decc-103">この資料では、トランスポート セキュリティを使用する場合のサーバー認証とクライアント認証に X.509 証明書を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8decc-103">This article discusses using X.509 certificates for server and client authentication when using transport security.</span></span> <span data-ttu-id="8decc-104">X.509 証明書の詳細については、「[X.509 Public Key Certificates](/windows/desktop/SecCertEnroll/about-x-509-public-key-certificates)」(X.509 公開キー証明書) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8decc-104">For more information about X.509 certificates see [X.509 Public Key Certificates](/windows/desktop/SecCertEnroll/about-x-509-public-key-certificates).</span></span> <span data-ttu-id="8decc-105">証明書は、証明機関 (通常はサード パーティの証明書の発行者) によって発行される必要があります。</span><span class="sxs-lookup"><span data-stu-id="8decc-105">Certificates must be issued by a certification authority, which is often a third-party issuer of certificates.</span></span> <span data-ttu-id="8decc-106">Windows サーバー ドメインでは、そのドメインのクライアント コンピューターに対して証明書を発行する際に Active Directory 証明書サービスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8decc-106">On a Windows Server domain, Active Directory Certificate Services can be used to issue certificates to client computers on the domain.</span></span> <span data-ttu-id="8decc-107">このシナリオでは、Secure Sockets Layer (SSL) を使用して構成されたインターネット インフォメーション サービス (IIS) でサービスをホストします。</span><span class="sxs-lookup"><span data-stu-id="8decc-107">In this scenario, the service is hosted under Internet Information Services (IIS) which is configured with Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="8decc-108">サービスは、クライアントがサーバーの ID を確認するための SSL (X.509) 証明書を使用して構成されます。</span><span class="sxs-lookup"><span data-stu-id="8decc-108">The service is configured with an SSL (X.509) certificate to allow clients to verify the identity of the server.</span></span> <span data-ttu-id="8decc-109">クライアントも、サービスがクライアントの ID を確認するための X.509 証明書を使用して構成されます。</span><span class="sxs-lookup"><span data-stu-id="8decc-109">The client is also configured with an X.509 certificate that allows the service to verify the identity of the client.</span></span> <span data-ttu-id="8decc-110">サーバーの証明書はクライアントによって信頼されている必要があり、クライアントの証明書はサーバーによって信頼されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8decc-110">The server’s certificate must be trusted by the client and the client’s certificate must be trusted by the server.</span></span> <span data-ttu-id="8decc-111">サービスとクライアントが互いの身元を確認する方法の実際の仕組みは、この記事の範囲外です。</span><span class="sxs-lookup"><span data-stu-id="8decc-111">The actual mechanics of how the service and client verifies each other’s identity is beyond the scope of this article.</span></span> <span data-ttu-id="8decc-112">詳細については、ウィキペディアの[デジタル署名](https://en.wikipedia.org/wiki/Digital_signature)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8decc-112">For more information, see [Digital Signature](https://en.wikipedia.org/wiki/Digital_signature) on Wikipedia.</span></span>
  
 <span data-ttu-id="8decc-113">このシナリオでは、次の図に示すような要求/応答のメッセージ パターンを実装します。</span><span class="sxs-lookup"><span data-stu-id="8decc-113">This scenario implements a request/reply message pattern as illustrated by the following diagram.</span></span>  
  
 <span data-ttu-id="8decc-114">![証明書を使用した安全な転送](../../../../docs/framework/wcf/feature-details/media/8f7b8968-899f-4538-a9e8-0eaa872a291c.gif "8f7b8968-899f-4538-a9e8-0eaa872a291c")</span><span class="sxs-lookup"><span data-stu-id="8decc-114">![Secure transfer using certificates](../../../../docs/framework/wcf/feature-details/media/8f7b8968-899f-4538-a9e8-0eaa872a291c.gif "8f7b8968-899f-4538-a9e8-0eaa872a291c")</span></span>  
  
 <span data-ttu-id="8decc-115">サービスで証明書を使用する方法の詳細については、「[証明書の使用](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)」および「[方法 : SSL 証明書を使用してポートを構成する](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8decc-115">For more information about using a certificate with a service, see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md) and [How to: Configure a Port with an SSL Certificate](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span></span> <span data-ttu-id="8decc-116">このシナリオのさまざまな特性を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="8decc-116">The following table describes the various characteristics of the scenario.</span></span>  
  
|<span data-ttu-id="8decc-117">特徴</span><span class="sxs-lookup"><span data-stu-id="8decc-117">Characteristic</span></span>|<span data-ttu-id="8decc-118">説明</span><span class="sxs-lookup"><span data-stu-id="8decc-118">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="8decc-119">セキュリティ モード</span><span class="sxs-lookup"><span data-stu-id="8decc-119">Security Mode</span></span>|<span data-ttu-id="8decc-120">トランスポート</span><span class="sxs-lookup"><span data-stu-id="8decc-120">Transport</span></span>|  
|<span data-ttu-id="8decc-121">相互運用性</span><span class="sxs-lookup"><span data-stu-id="8decc-121">Interoperability</span></span>|<span data-ttu-id="8decc-122">既存の Web サービス クライアントおよびサービスとの相互運用性</span><span class="sxs-lookup"><span data-stu-id="8decc-122">With existing Web service clients and services.</span></span>|  
|<span data-ttu-id="8decc-123">認証 (サーバー)</span><span class="sxs-lookup"><span data-stu-id="8decc-123">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="8decc-124">認証 (クライアント)</span><span class="sxs-lookup"><span data-stu-id="8decc-124">Authentication (Client)</span></span>|<span data-ttu-id="8decc-125">○ (SSL 証明書を使用)</span><span class="sxs-lookup"><span data-stu-id="8decc-125">Yes (using an SSL certificate)</span></span><br /><br /> <span data-ttu-id="8decc-126">○ (X.509 証明書を使用)</span><span class="sxs-lookup"><span data-stu-id="8decc-126">Yes (using an X.509 certificate)</span></span>|  
|<span data-ttu-id="8decc-127">データの整合性</span><span class="sxs-lookup"><span data-stu-id="8decc-127">Data Integrity</span></span>|<span data-ttu-id="8decc-128">はい</span><span class="sxs-lookup"><span data-stu-id="8decc-128">Yes</span></span>|  
|<span data-ttu-id="8decc-129">データの機密性</span><span class="sxs-lookup"><span data-stu-id="8decc-129">Data Confidentiality</span></span>|<span data-ttu-id="8decc-130">はい</span><span class="sxs-lookup"><span data-stu-id="8decc-130">Yes</span></span>|  
|<span data-ttu-id="8decc-131">トランスポート</span><span class="sxs-lookup"><span data-stu-id="8decc-131">Transport</span></span>|<span data-ttu-id="8decc-132">HTTPS</span><span class="sxs-lookup"><span data-stu-id="8decc-132">HTTPS</span></span>|  
|<span data-ttu-id="8decc-133">バインド</span><span class="sxs-lookup"><span data-stu-id="8decc-133">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="configure-the-service"></a><span data-ttu-id="8decc-134">サービスの構成</span><span class="sxs-lookup"><span data-stu-id="8decc-134">Configure the Service</span></span>  
 <span data-ttu-id="8decc-135">このシナリオのサービスは IIS でホストされるので、web.config ファイルを使用して構成します。</span><span class="sxs-lookup"><span data-stu-id="8decc-135">Since the service in this scenario is hosted under IIS, it is configured with a web.config file.</span></span> <span data-ttu-id="8decc-136">次の web.config は、トランスポート セキュリティと X.509 クライアント資格情報を使用するように <xref:System.ServiceModel.WSHttpBinding> を構成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="8decc-136">The following web.config shows how to configure the <xref:System.ServiceModel.WSHttpBinding> to use transport security and X.509 client credentials.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <protocolMapping>  
      <add scheme="https" binding="wsHttpBinding" />  
    </protocolMapping>  
    <bindings>  
      <wsHttpBinding>  
        <!-- configure wsHttp binding with Transport security mode and clientCredentialType as Certificate -->  
        <binding>  
          <security mode="Transport">  
            <transport clientCredentialType="Certificate"/>
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>
           <serviceDebug includeExceptionDetailInFaults="True" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="configure-the-client"></a><span data-ttu-id="8decc-137">クライアントの構成</span><span class="sxs-lookup"><span data-stu-id="8decc-137">Configure the Client</span></span>  
 <span data-ttu-id="8decc-138">クライアントはコードまたは app.config ファイルで構成できます。</span><span class="sxs-lookup"><span data-stu-id="8decc-138">The client can be configured in code or in an app.config file.</span></span> <span data-ttu-id="8decc-139">次の例は、クライアントをコードで構成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="8decc-139">The following example shows how to configure the client in code.</span></span>  
  
```csharp
// Create the binding.  
var myBinding = new WSHttpBinding();  
myBinding.Security.Mode = SecurityMode.Transport;  
myBinding.Security.Transport.ClientCredentialType =  
   HttpClientCredentialType.Certificate;  
  
// Create the endpoint address. Note that the machine name
// must match the subject or DNS field of the X.509 certificate  
// used to authenticate the service.
var ea = new  
   EndpointAddress("https://localhost/CalculatorService/service.svc");  
  
// Create the client. The code for the calculator
// client is not shown here. See the sample applications  
// for examples of the calculator code.  
var cc =  
   new CalculatorClient(myBinding, ea);  
  
// The client must specify a certificate trusted by the server.  
cc.ClientCredentials.ClientCertificate.SetCertificate(  
    StoreLocation.CurrentUser,  
    StoreName.My,  
    X509FindType.FindBySubjectName,  
    "contoso.com");  
  
// Begin using the client.  
Console.WriteLine(cc.Add(100, 1111));  
//...  
cc.Close();  
```  
  
 <span data-ttu-id="8decc-140">また、次の例のように App.config ファイルでクライアントを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="8decc-140">Alternatively you can configure the client in an App.config file as shown in the following example:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
      <!-- this endpoint has an https: address -->  
      <endpoint address=" https://localhost/CalculatorService/service.svc "
                behaviorConfiguration="endpointCredentialBehavior"  
                binding="wsHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.Samples.TransportSecurity.ICalculator"/>  
    </client>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="endpointCredentialBehavior">  
          <clientCredentials>  
            <clientCertificate findValue="contoso.com"  
                               storeLocation="CurrentUser"  
                               storeName="My"  
                               x509FindType="FindBySubjectName" />  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <bindings>  
      <wsHttpBinding>  
        <!-- configure wsHttpbinding with Transport security mode  
                   and clientCredentialType as Certificate -->  
        <binding name="Binding1">  
          <security mode="Transport">  
            <transport clientCredentialType="Certificate"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
  </system.serviceModel>  
  
<startup><supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.0"/></startup></configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8decc-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="8decc-141">See also</span></span>

- [<span data-ttu-id="8decc-142">セキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="8decc-142">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- <span data-ttu-id="8decc-143">[Windows Server AppFabric のセキュリティ モデル](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="8decc-143">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
