---
title: <message> の <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9def5a35-475d-40d6-b716-ccdbd93863c7
ms.openlocfilehash: 62b1793d18ddc8edc1f55b02137c4e0a9f7327d2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738961"
---
# <a name="message-of-nethttpbinding"></a><span data-ttu-id="73399-102">\<message> の \<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="73399-102">\<message> of \<netHttpBinding></span></span>
<span data-ttu-id="73399-103">のメッセージレベルのセキュリティの設定を定義し [\<netHttpBinding>](nethttpbinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="73399-103">Defines the settings for message-level security of the [\<netHttpBinding>](nethttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**  
  
## <a name="syntax"></a><span data-ttu-id="73399-104">構文</span><span class="sxs-lookup"><span data-stu-id="73399-104">Syntax</span></span>  
  
```xml  
<message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
         clientCredentialType="UserName/Certificate" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="73399-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="73399-105">Attributes and Elements</span></span>  
 <span data-ttu-id="73399-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="73399-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="73399-107">属性</span><span class="sxs-lookup"><span data-stu-id="73399-107">Attributes</span></span>  
  
|<span data-ttu-id="73399-108">属性</span><span class="sxs-lookup"><span data-stu-id="73399-108">Attribute</span></span>|<span data-ttu-id="73399-109">説明</span><span class="sxs-lookup"><span data-stu-id="73399-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="73399-110">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="73399-110">algorithmSuite</span></span>|<span data-ttu-id="73399-111">メッセージの暗号化とキー ラップ アルゴリズムを設定します。</span><span class="sxs-lookup"><span data-stu-id="73399-111">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="73399-112">この属性は、アルゴリズムとキー サイズを指定する <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> 型です。</span><span class="sxs-lookup"><span data-stu-id="73399-112">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>, which specifies the algorithms and the key sizes.</span></span> <span data-ttu-id="73399-113">これらのアルゴリズムは、セキュリティ ポリシー言語 (WS-SecurityPolicy) 仕様で指定されたアルゴリズムにマップされます。</span><span class="sxs-lookup"><span data-stu-id="73399-113">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="73399-114">既定値は `Basic256` です。</span><span class="sxs-lookup"><span data-stu-id="73399-114">The default value is `Basic256`.</span></span>|  
|<span data-ttu-id="73399-115">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="73399-115">clientCredentialType</span></span>|<span data-ttu-id="73399-116">メッセージ ベースのセキュリティを使用してクライアント認証を実行するときに使用される資格情報の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="73399-116">Specifies the type of credential to be used when performing client authentication using message-based security.</span></span> <span data-ttu-id="73399-117">既定値は、`UserName` です。</span><span class="sxs-lookup"><span data-stu-id="73399-117">The default is `UserName`.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="73399-118">clientCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="73399-118">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="73399-119">値</span><span class="sxs-lookup"><span data-stu-id="73399-119">Value</span></span>|<span data-ttu-id="73399-120">Description</span><span class="sxs-lookup"><span data-stu-id="73399-120">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="73399-121">UserName</span><span class="sxs-lookup"><span data-stu-id="73399-121">UserName</span></span>|<span data-ttu-id="73399-122">-クライアントがユーザー名資格情報を使用してサーバーに対して認証される必要があります。</span><span class="sxs-lookup"><span data-stu-id="73399-122">-   Requires the client be authenticated to the server with a UserName credential.</span></span> <span data-ttu-id="73399-123">この資格情報は、<> 要素を使用して指定する必要があり `clientCredentials` ます。</span><span class="sxs-lookup"><span data-stu-id="73399-123">This credential needs to be specified using the <`clientCredentials`> element.</span></span><br /><span data-ttu-id="73399-124">-WCF では、パスワードダイジェストの送信や、パスワードを使用したキーの派生、およびメッセージセキュリティのためのこのようなキーの使用はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="73399-124">-   WCF does not support sending a password digest or deriving keys using passwords and using such keys for message security.</span></span> <span data-ttu-id="73399-125">そのため、ユーザー名の資格情報を使用する場合、WCF はトランスポートをセキュリティで保護するように強制します。</span><span class="sxs-lookup"><span data-stu-id="73399-125">Therefore, WCF enforces that the transport be secured when using UserName credentials.</span></span> <span data-ttu-id="73399-126">`basicHttpBinding` の場合は、SSL チャネルの設定が必要です。</span><span class="sxs-lookup"><span data-stu-id="73399-126">For the `basicHttpBinding`, this requires setting up an SSL channel.</span></span>|  
|<span data-ttu-id="73399-127">Certificate</span><span class="sxs-lookup"><span data-stu-id="73399-127">Certificate</span></span>|<span data-ttu-id="73399-128">証明書を使用してクライアントをサーバーに認証するように要求します。</span><span class="sxs-lookup"><span data-stu-id="73399-128">Requires that the client be authenticated to the server using a certificate.</span></span> <span data-ttu-id="73399-129">この場合のクライアント資格情報は、<> と <> を使用して指定する必要があり `clientCredentials` `clientCertificate` ます。</span><span class="sxs-lookup"><span data-stu-id="73399-129">The client credential in this case needs to be specified using <`clientCredentials`> and the <`clientCertificate`>.</span></span> <span data-ttu-id="73399-130">さらに、メッセージのセキュリティ モードを使用する場合は、クライアントにサービス証明書を準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73399-130">In addition, when using message security mode, the client needs to be provisioned with the service certificate.</span></span> <span data-ttu-id="73399-131">この場合のサービス資格情報は、 <xref:System.ServiceModel.Description.ClientCredentials> クラスまたは動作要素を使用して指定 `ClientCredentials` し、serviceCredentials の要素を使用してサービス証明書を指定する必要があり \<serviceCertificate> ます。</span><span class="sxs-lookup"><span data-stu-id="73399-131">The service credential in this case needs to be specified using <xref:System.ServiceModel.Description.ClientCredentials> class or `ClientCredentials` behavior element and specifying the service certificate using the \<serviceCertificate> element of serviceCredentials.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="73399-132">子要素</span><span class="sxs-lookup"><span data-stu-id="73399-132">Child Elements</span></span>  
 <span data-ttu-id="73399-133">なし</span><span class="sxs-lookup"><span data-stu-id="73399-133">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="73399-134">親要素</span><span class="sxs-lookup"><span data-stu-id="73399-134">Parent Elements</span></span>  
  
|<span data-ttu-id="73399-135">要素</span><span class="sxs-lookup"><span data-stu-id="73399-135">Element</span></span>|<span data-ttu-id="73399-136">Description</span><span class="sxs-lookup"><span data-stu-id="73399-136">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="73399-137"><`security`<の> 要素`netHttpBinding`></span><span class="sxs-lookup"><span data-stu-id="73399-137"><`security`> element of <`netHttpBinding`></span></span>|<span data-ttu-id="73399-138"><> 要素のセキュリティ機能を定義 `netHttpBinding` します。</span><span class="sxs-lookup"><span data-stu-id="73399-138">Defines the security capabilities for the <`netHttpBinding`> Element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="73399-139">例</span><span class="sxs-lookup"><span data-stu-id="73399-139">Example</span></span>  
 <span data-ttu-id="73399-140">このサンプルでは、basicHttpBinding とメッセージ セキュリティを使用するアプリケーションを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="73399-140">This sample demonstrates how to implement an application that uses the basicHttpBinding and message security.</span></span> <span data-ttu-id="73399-141">サービスの次の構成例では、エンドポイント定義によって basicHttpBinding が指定され、`Binding1` という名前のバインディング構成が参照されます。</span><span class="sxs-lookup"><span data-stu-id="73399-141">In the following configuration example for a service, the endpoint definition specifies the basicHttpBinding and references a binding configuration named `Binding1`.</span></span> <span data-ttu-id="73399-142">サービスがクライアントに対してサービス自体を認証するために使用する証明書は、`behaviors` 要素の下にある構成ファイルの `serviceCredentials` セクションで設定されます。</span><span class="sxs-lookup"><span data-stu-id="73399-142">The certificate that the service uses to authenticate itself to the client is set in the `behaviors` section of the configuration file under the `serviceCredentials` element.</span></span> <span data-ttu-id="73399-143">クライアントがサービスに対してクライアント自体を認証するために使用する証明書に適用される検証モードも、`behaviors` 要素の下にある `clientCertificate` セクションで設定されます。</span><span class="sxs-lookup"><span data-stu-id="73399-143">The validation mode that applies to the certificate that the client uses to authenticate itself to the service is also set in the `behaviors` section under the `clientCertificate` element.</span></span>  
  
 <span data-ttu-id="73399-144">同じバインディングとセキュリティの詳細が、クライアントの構成ファイルで指定されます。</span><span class="sxs-lookup"><span data-stu-id="73399-144">The same binding and security details are specified in the client configuration file.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <host>
        <baseAddresses>
          <add baseAddress="http://localhost:8000/ServiceModelSamples/service" />
        </baseAddresses>
      </host>
      <!-- this endpoint is exposed at the base address provided by host: http://localhost:8000/ServiceModelSamples/service  -->
      <endpoint address=""
                binding="basicHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
      <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->
      <endpoint address="mex"
                binding="mexHttpBinding"
                contract="IMetadataExchange" />
    </service>
  </services>
  <bindings>
    <basicHttpBinding>
      <!-- This configuration defines the SecurityMode as Message and
           the clientCredentialType as Certificate. -->
      <binding name="Binding1" >
        <security mode = "Message">
          <message clientCredentialType="Certificate" />
        </security>
      </binding>
    </basicHttpBinding>
  </bindings>
  <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->
  <behaviors>
    <serviceBehaviors>
      <behavior name="CalculatorServiceBehavior">
        <serviceMetadata httpGetEnabled="True" />
        <serviceDebug includeExceptionDetailInFaults="False" />
        <!-- The serviceCredentials behavior allows one to define a service certificate.
             A service certificate is used by a client to authenticate the service and provide message protection.
             This configuration references the "localhost" certificate installed during the setup instructions. -->
        <serviceCredentials>
          <serviceCertificate findValue="localhost"
                              storeLocation="LocalMachine"
                              storeName="My"
                              x509FindType="FindBySubjectName" />
          <clientCertificate>
            <!-- Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate
                 is in the user's Trusted People store, then it will be trusted without performing a
                 validation of the certificate's issuer chain. This setting is used here for convenience so that the
                 sample can be run without having to have certificates issued by a certification authority (CA).
                 This setting is less secure than the default, ChainTrust. The security implications of this
                 setting should be carefully considered before using PeerOrChainTrust in production code. -->
            <authentication certificateValidationMode="PeerOrChainTrust" />
          </clientCertificate>
        </serviceCredentials>
      </behavior>
    </serviceBehaviors>
  </behaviors>
</system.serviceModel>
```  
  
## <a name="see-also"></a><span data-ttu-id="73399-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="73399-145">See also</span></span>

- [<span data-ttu-id="73399-146">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="73399-146">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="73399-147">バインド</span><span class="sxs-lookup"><span data-stu-id="73399-147">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="73399-148">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="73399-148">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="73399-149">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="73399-149">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
