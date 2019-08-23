---
title: メッセージ セキュリティと相互の証明書
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 99d7a528-7ae4-4d39-a0f9-3066ea237de0
ms.openlocfilehash: bd64531116b1588683c2f5c8964e78e41e371ecf
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955342"
---
# <a name="message-security-with-mutual-certificates"></a><span data-ttu-id="cda46-102">メッセージ セキュリティと相互の証明書</span><span class="sxs-lookup"><span data-stu-id="cda46-102">Message Security with Mutual Certificates</span></span>
<span data-ttu-id="cda46-103">次のシナリオは、メッセージセキュリティモードを使用してセキュリティで保護された Windows Communication Foundation (WCF) サービスとクライアントを示しています。</span><span class="sxs-lookup"><span data-stu-id="cda46-103">The following scenario shows a Windows Communication Foundation (WCF) service and client secured using message security mode.</span></span> <span data-ttu-id="cda46-104">クライアントとサービスは、証明書を使用して認証されます。</span><span class="sxs-lookup"><span data-stu-id="cda46-104">The client and the service are authenticated with certificates.</span></span>  
  
 <span data-ttu-id="cda46-105">このシナリオは、X.509 証明書トークン プロファイルと共に WS-Security を使用するため、相互運用性があります。</span><span class="sxs-lookup"><span data-stu-id="cda46-105">This scenario is interoperable because it uses WS-Security with the X.509 certificate token profile.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cda46-106">このシナリオでは、サービス証明書のネゴシエーションは実行されません。</span><span class="sxs-lookup"><span data-stu-id="cda46-106">This scenario does not perform negotiation of the service certificate.</span></span> <span data-ttu-id="cda46-107">通信を開始する前に、サービス証明書をクライアントに提供しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="cda46-107">The service certificate must be provided to the client in advance of any communication.</span></span> <span data-ttu-id="cda46-108">サーバー証明書は、アプリケーションと共に配布したり、帯域外通信で提供できます。</span><span class="sxs-lookup"><span data-stu-id="cda46-108">The server certificate can be distributed with the application or provided in an out-of-band communication.</span></span>  
  
 <span data-ttu-id="cda46-109">![相互証明書を使用したメッセージセキュリティ](../../../../docs/framework/wcf/feature-details/media/f4157312-b17c-416c-a5ee-fa7b54db211b.gif "f4157312-b17c-416c-a5ee-fa7b54db211b")</span><span class="sxs-lookup"><span data-stu-id="cda46-109">![Message security with mutual certificates](../../../../docs/framework/wcf/feature-details/media/f4157312-b17c-416c-a5ee-fa7b54db211b.gif "f4157312-b17c-416c-a5ee-fa7b54db211b")</span></span>  
  
|<span data-ttu-id="cda46-110">特性</span><span class="sxs-lookup"><span data-stu-id="cda46-110">Characteristic</span></span>|<span data-ttu-id="cda46-111">説明</span><span class="sxs-lookup"><span data-stu-id="cda46-111">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="cda46-112">セキュリティ モード</span><span class="sxs-lookup"><span data-stu-id="cda46-112">Security Mode</span></span>|<span data-ttu-id="cda46-113">メッセージ</span><span class="sxs-lookup"><span data-stu-id="cda46-113">Message</span></span>|  
|<span data-ttu-id="cda46-114">相互運用性</span><span class="sxs-lookup"><span data-stu-id="cda46-114">Interoperability</span></span>|<span data-ttu-id="cda46-115">○ WS-Security および X.509 証明書トークン プロファイルと互換性があるクライアントとサービスで相互運用性があります。</span><span class="sxs-lookup"><span data-stu-id="cda46-115">Yes, with WS-Security and X.509 certificate token profile compatible clients and services.</span></span>|  
|<span data-ttu-id="cda46-116">認証</span><span class="sxs-lookup"><span data-stu-id="cda46-116">Authentication</span></span>|<span data-ttu-id="cda46-117">サーバーとクライアントの相互認証</span><span class="sxs-lookup"><span data-stu-id="cda46-117">Mutual authentication of the server and client.</span></span>|  
|<span data-ttu-id="cda46-118">整合性</span><span class="sxs-lookup"><span data-stu-id="cda46-118">Integrity</span></span>|<span data-ttu-id="cda46-119">はい</span><span class="sxs-lookup"><span data-stu-id="cda46-119">Yes</span></span>|  
|<span data-ttu-id="cda46-120">機密性</span><span class="sxs-lookup"><span data-stu-id="cda46-120">Confidentiality</span></span>|<span data-ttu-id="cda46-121">はい</span><span class="sxs-lookup"><span data-stu-id="cda46-121">Yes</span></span>|  
|<span data-ttu-id="cda46-122">Transport</span><span class="sxs-lookup"><span data-stu-id="cda46-122">Transport</span></span>|<span data-ttu-id="cda46-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="cda46-123">HTTP</span></span>|  
|<span data-ttu-id="cda46-124">バインディング</span><span class="sxs-lookup"><span data-stu-id="cda46-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="cda46-125">サービス</span><span class="sxs-lookup"><span data-stu-id="cda46-125">Service</span></span>  
 <span data-ttu-id="cda46-126">次のコードと構成は、別々に実行します。</span><span class="sxs-lookup"><span data-stu-id="cda46-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="cda46-127">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="cda46-127">Do one of the following:</span></span>  
  
- <span data-ttu-id="cda46-128">構成を使用せずに、コードを使用してスタンドアロン サービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="cda46-128">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="cda46-129">提供された構成を使用してサービスを作成しますが、エンドポイントを定義しません。</span><span class="sxs-lookup"><span data-stu-id="cda46-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="cda46-130">コード</span><span class="sxs-lookup"><span data-stu-id="cda46-130">Code</span></span>  
 <span data-ttu-id="cda46-131">次のコードでは、メッセージ セキュリティを使用するサービス エンドポイントを作成します。</span><span class="sxs-lookup"><span data-stu-id="cda46-131">The following code shows creates a service endpoint that uses message security.</span></span> <span data-ttu-id="cda46-132">サービスには、自身を認証するための証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="cda46-132">The service requires a certificate to authenticate itself.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#13)]
 [!code-vb[C_SecurityScenarios#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#13)]  
  
### <a name="configuration"></a><span data-ttu-id="cda46-133">構成</span><span class="sxs-lookup"><span data-stu-id="cda46-133">Configuration</span></span>  
 <span data-ttu-id="cda46-134">コードの代わりに次の構成を使用して、同じサービスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="cda46-134">The following configuration can be used instead of the code to create the same service.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="serviceCredentialBehavior">  
          <serviceCredentials>  
            <serviceCertificate findValue="Contoso.com"   
                                storeLocation="LocalMachine"  
                                storeName="My"   
                                x509FindType="FindBySubjectName" />  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service behaviorConfiguration="serviceCredentialBehavior"   
               name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"   
                  binding="wsHttpBinding"  
                  bindingConfiguration="InteropCertificateBinding"  
                  name="WSHttpBinding_ICalculator"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="InteropCertificateBinding">  
          <security mode="Message">  
            <message clientCredentialType="Certificate"  
                     negotiateServiceCredential="false"  
                     establishSecurityContext="false" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="cda46-135">クライアント</span><span class="sxs-lookup"><span data-stu-id="cda46-135">Client</span></span>  
 <span data-ttu-id="cda46-136">次のコードと構成は、別々に実行します。</span><span class="sxs-lookup"><span data-stu-id="cda46-136">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="cda46-137">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="cda46-137">Do one of the following:</span></span>  
  
- <span data-ttu-id="cda46-138">コード (およびクライアント コード) を使用してスタンドアロン クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="cda46-138">Create a stand-alone client using the code (and client code).</span></span>  
  
- <span data-ttu-id="cda46-139">エンドポイント アドレスを定義しないクライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="cda46-139">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="cda46-140">代わりに、引数として構成名を受け取るクライアント コンストラクターを使用します。</span><span class="sxs-lookup"><span data-stu-id="cda46-140">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="cda46-141">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="cda46-141">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="cda46-142">コード</span><span class="sxs-lookup"><span data-stu-id="cda46-142">Code</span></span>  
 <span data-ttu-id="cda46-143">クライアントを作成する場合のコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="cda46-143">The following code creates the client.</span></span> <span data-ttu-id="cda46-144">セキュリティ モードは Message に設定され、クライアント資格情報の種類は Certificate に設定されています。</span><span class="sxs-lookup"><span data-stu-id="cda46-144">The security mode is set to Message, and the client credential type is set to Certificate.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#20](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#20)]
 [!code-vb[C_SecurityScenarios#20](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#20)]  
  
### <a name="configuration"></a><span data-ttu-id="cda46-145">構成</span><span class="sxs-lookup"><span data-stu-id="cda46-145">Configuration</span></span>  
 <span data-ttu-id="cda46-146">次のコードは、クライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="cda46-146">The following configures the client.</span></span> <span data-ttu-id="cda46-147">クライアント証明書は、 [ \<clientCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md)を使用して指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cda46-147">A client certificate must be specified using the [\<clientCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md).</span></span> <span data-ttu-id="cda46-148">また、サービス証明書は、 [ \<defaultcertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md)を使用して指定されます。</span><span class="sxs-lookup"><span data-stu-id="cda46-148">Also, the service certificate is specified using the [\<defaultCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md).</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="ClientCredentialsBehavior">  
          <clientCredentials>  
            <clientCertificate findValue="Cohowinery.com"   
                 storeLocation="CurrentUser"  
                 storeName="My"  
                 x509FindType="FindBySubjectName" />  
            <serviceCertificate>  
              <defaultCertificate findValue="Contoso.com"   
                                  storeLocation="CurrentUser"  
                                  storeName="TrustedPeople"  
                                  x509FindType="FindBySubjectName" />  
            </serviceCertificate>  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="Certificate"   
                     negotiateServiceCredential="false"  
                     establishSecurityContext="false" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://machineName/Calculator"   
                behaviorConfiguration="ClientCredentialsBehavior"  
                binding="wsHttpBinding"   
                bindingConfiguration="WSHttpBinding_ICalculator"  
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator">  
        <identity>  
          <certificate encodedValue="Encoded_Value_Not_Shown" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cda46-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="cda46-149">See also</span></span>

- [<span data-ttu-id="cda46-150">セキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="cda46-150">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [<span data-ttu-id="cda46-151">Windows Server App Fabric のセキュリティモデル</span><span class="sxs-lookup"><span data-stu-id="cda46-151">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
- [<span data-ttu-id="cda46-152">方法: 開発時にトランスポートセキュリティのために WCF に一時的な証明書を作成してインストールする</span><span class="sxs-lookup"><span data-stu-id="cda46-152">How to: Create and Install Temporary Certificates in WCF for Transport Security During Development</span></span>](https://go.microsoft.com/fwlink/?LinkId=244264)
