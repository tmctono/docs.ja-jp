---
title: 資格情報ネゴシエーションを使用しない Windows クライアントを使用するメッセージ セキュリティ
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fc07a26c-cbee-41c5-8fb0-329085fef749
ms.openlocfilehash: d3b05a1786131a119d516edeba0d6e8e24289f87
ms.sourcegitcommit: 09b4090b78f52fd09b0e430cd4b26576f1fdf96e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2020
ms.locfileid: "76212025"
---
# <a name="message-security-with-a-windows-client-without-credential-negotiation"></a><span data-ttu-id="5a187-102">資格情報ネゴシエーションを使用しない Windows クライアントを使用するメッセージ セキュリティ</span><span class="sxs-lookup"><span data-stu-id="5a187-102">Message Security with a Windows Client without Credential Negotiation</span></span>

<span data-ttu-id="5a187-103">次のシナリオは、Kerberos プロトコルによって保護された Windows Communication Foundation (WCF) クライアントとサービスを示しています。</span><span class="sxs-lookup"><span data-stu-id="5a187-103">The following scenario shows a Windows Communication Foundation (WCF) client and service secured by the Kerberos protocol.</span></span>

<span data-ttu-id="5a187-104">サービスとクライアントは、いずれも同じドメインまたは信頼できるドメインに配置されています。</span><span class="sxs-lookup"><span data-stu-id="5a187-104">Both the service and the client are in the same domain or trusted domains.</span></span>

> [!NOTE]
> <span data-ttu-id="5a187-105">このシナリオと[Windows クライアントを使用したメッセージセキュリティ](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client.md)の違いは、このシナリオでは、アプリケーションメッセージを送信する前にサービスとのサービス資格情報がネゴシエートされないことです。</span><span class="sxs-lookup"><span data-stu-id="5a187-105">The difference between this scenario and [Message Security with a Windows Client](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client.md) is that this scenario does not negotiate the service credential with the service prior to sending the application message.</span></span> <span data-ttu-id="5a187-106">また、このシナリオでは Kerberos プロトコルを使用するので、Windows ドメイン環境が必要になります。</span><span class="sxs-lookup"><span data-stu-id="5a187-106">Additionally, because this requires the Kerberos protocol, this scenario requires a Windows domain environment.</span></span>

<span data-ttu-id="5a187-107">![資格情報ネゴシエーションを使用しないメッセージセキュリティ](../../../../docs/framework/wcf/feature-details/media/0c9f9baa-2439-4ef9-92f4-43c242d85d0d.gif "0c9f9baa-2439-4ef9-92f4-43c242d85d0d")</span><span class="sxs-lookup"><span data-stu-id="5a187-107">![Message security without credential negotiation](../../../../docs/framework/wcf/feature-details/media/0c9f9baa-2439-4ef9-92f4-43c242d85d0d.gif "0c9f9baa-2439-4ef9-92f4-43c242d85d0d")</span></span>

|<span data-ttu-id="5a187-108">特徴</span><span class="sxs-lookup"><span data-stu-id="5a187-108">Characteristic</span></span>|<span data-ttu-id="5a187-109">説明</span><span class="sxs-lookup"><span data-stu-id="5a187-109">Description</span></span>|
|--------------------|-----------------|
|<span data-ttu-id="5a187-110">セキュリティ モード</span><span class="sxs-lookup"><span data-stu-id="5a187-110">Security Mode</span></span>|<span data-ttu-id="5a187-111">[メッセージ]</span><span class="sxs-lookup"><span data-stu-id="5a187-111">Message</span></span>|
|<span data-ttu-id="5a187-112">相互運用性</span><span class="sxs-lookup"><span data-stu-id="5a187-112">Interoperability</span></span>|<span data-ttu-id="5a187-113">○ Kerberos トークン プロファイル互換クライアントを使用する WS-Security</span><span class="sxs-lookup"><span data-stu-id="5a187-113">Yes, WS-Security with Kerberos token-profile compatible clients</span></span>|
|<span data-ttu-id="5a187-114">認証 (サーバー)</span><span class="sxs-lookup"><span data-stu-id="5a187-114">Authentication (Server)</span></span>|<span data-ttu-id="5a187-115">サーバーとクライアントの相互認証</span><span class="sxs-lookup"><span data-stu-id="5a187-115">Mutual authentication of the server and client</span></span>|
|<span data-ttu-id="5a187-116">認証 (クライアント)</span><span class="sxs-lookup"><span data-stu-id="5a187-116">Authentication (Client)</span></span>|<span data-ttu-id="5a187-117">サーバーとクライアントの相互認証</span><span class="sxs-lookup"><span data-stu-id="5a187-117">Mutual authentication of the server and client</span></span>|
|<span data-ttu-id="5a187-118">整合性</span><span class="sxs-lookup"><span data-stu-id="5a187-118">Integrity</span></span>|<span data-ttu-id="5a187-119">○</span><span class="sxs-lookup"><span data-stu-id="5a187-119">Yes</span></span>|
|<span data-ttu-id="5a187-120">機密性</span><span class="sxs-lookup"><span data-stu-id="5a187-120">Confidentiality</span></span>|<span data-ttu-id="5a187-121">○</span><span class="sxs-lookup"><span data-stu-id="5a187-121">Yes</span></span>|
|<span data-ttu-id="5a187-122">Transport</span><span class="sxs-lookup"><span data-stu-id="5a187-122">Transport</span></span>|<span data-ttu-id="5a187-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="5a187-123">HTTP</span></span>|
|<span data-ttu-id="5a187-124">バインディング</span><span class="sxs-lookup"><span data-stu-id="5a187-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|

## <a name="service"></a><span data-ttu-id="5a187-125">サービス</span><span class="sxs-lookup"><span data-stu-id="5a187-125">Service</span></span>

<span data-ttu-id="5a187-126">次のコードと構成は、別々に実行します。</span><span class="sxs-lookup"><span data-stu-id="5a187-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="5a187-127">以下のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="5a187-127">Do one of the following:</span></span>

- <span data-ttu-id="5a187-128">構成を使用せずに、コードを使用してスタンドアロン サービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="5a187-128">Create a stand-alone service using the code with no configuration.</span></span>

- <span data-ttu-id="5a187-129">提供された構成を使用してサービスを作成しますが、エンドポイントを定義しません。</span><span class="sxs-lookup"><span data-stu-id="5a187-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>

### <a name="code"></a><span data-ttu-id="5a187-130">コード</span><span class="sxs-lookup"><span data-stu-id="5a187-130">Code</span></span>

<span data-ttu-id="5a187-131">次のコードは、メッセージ セキュリティを使用するサービス エンドポイントを作成します。</span><span class="sxs-lookup"><span data-stu-id="5a187-131">The following code creates a service endpoint that uses message security.</span></span> <span data-ttu-id="5a187-132">このコードは、サービス資格情報のネゴシエーションとセキュリティ コンテキスト トークン (SCT) の確立を無効にします。</span><span class="sxs-lookup"><span data-stu-id="5a187-132">The code disables service credential negotiation, and the establishment of a security context token (SCT).</span></span>

> [!NOTE]
> <span data-ttu-id="5a187-133">ネゴシエートせずに Windows の資格情報を使用するには、サービスのユーザー アカウントが、Active Directory ドメインを使用して登録されたサービス プリンシパル名 (SPN) にアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a187-133">To use the Windows credential type without negotiation, the service's user account must have access to service principal name (SPN) that is registered with the Active Directory domain.</span></span> <span data-ttu-id="5a187-134">この操作を行う方法は 2 とおりあります。</span><span class="sxs-lookup"><span data-stu-id="5a187-134">You can do this in two ways:</span></span>

1. <span data-ttu-id="5a187-135">`NetworkService` アカウントまたは `LocalSystem` アカウントを使用してサービスを実行します。</span><span class="sxs-lookup"><span data-stu-id="5a187-135">Use the `NetworkService` or `LocalSystem` account to run your service.</span></span> <span data-ttu-id="5a187-136">これらのアカウントは、コンピューターが Active Directory ドメインに参加したときに確立されたコンピューターの SPN にアクセスできるため、WCF はサービスのメタデータ内のサービスのエンドポイント内に適切な SPN 要素を自動的に生成します (Web サービスの説明言語 (WSDL))。</span><span class="sxs-lookup"><span data-stu-id="5a187-136">Because those accounts have access to the machine SPN that is established when the machine joins the Active Directory domain, WCF automatically generates the proper SPN element inside the service's endpoint in the service's metadata (Web Services Description Language, or WSDL).</span></span>

2. <span data-ttu-id="5a187-137">任意の Active Directory ドメイン アカウントを使用してサービスを実行します。</span><span class="sxs-lookup"><span data-stu-id="5a187-137">Use an arbitrary Active Directory domain account to run your service.</span></span> <span data-ttu-id="5a187-138">この場合、そのドメイン アカウント用の SPN を確立する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a187-138">In this case, you need to establish an SPN for that domain account.</span></span> <span data-ttu-id="5a187-139">これを行うには、Setspn.exe ユーティリティ ツールを使用する方法があります。</span><span class="sxs-lookup"><span data-stu-id="5a187-139">One way of doing this is to use the Setspn.exe utility tool.</span></span> <span data-ttu-id="5a187-140">サービスのアカウントの SPN を作成したら、その SPN をメタデータ (WSDL) を通じてサービスのクライアントに発行するように WCF を構成します。</span><span class="sxs-lookup"><span data-stu-id="5a187-140">Once the SPN is created for the service's account, configure WCF to publish that SPN to the service's clients through its metadata (WSDL).</span></span> <span data-ttu-id="5a187-141">これを行うには、アプリケーション構成ファイルまたはコードのどちらかを使用して、公開されるエンドポイントのエンドポイント ID を設定します。</span><span class="sxs-lookup"><span data-stu-id="5a187-141">This is done by setting the endpoint identity for the exposed endpoint, either though an application configuration file or code.</span></span> <span data-ttu-id="5a187-142">プログラムで ID を公開する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="5a187-142">The following example publishes the identity programmatically.</span></span>

<span data-ttu-id="5a187-143">Spn、Kerberos プロトコル、および Active Directory の詳細については、「 [Windows 用の Kerberos テクニカル補完](https://docs.microsoft.com/previous-versions/msp-n-p/ff649429(v=pandp.10))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a187-143">For more information about SPNs, the Kerberos protocol, and Active Directory, see [Kerberos Technical Supplement for Windows](https://docs.microsoft.com/previous-versions/msp-n-p/ff649429(v=pandp.10)).</span></span> <span data-ttu-id="5a187-144">エンドポイント id の詳細については、「[認証モードの認証](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a187-144">For more information about endpoint identities, see [SecurityBindingElement Authentication Modes](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md).</span></span>

[!code-csharp[C_SecurityScenarios#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#12)]
[!code-vb[C_SecurityScenarios#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#12)]

### <a name="configuration"></a><span data-ttu-id="5a187-145">の構成</span><span class="sxs-lookup"><span data-stu-id="5a187-145">Configuration</span></span>

<span data-ttu-id="5a187-146">コードの代わりに次の構成を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5a187-146">The following configuration can be used instead of the code.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <system.serviceModel>
    <behaviors />
    <services>
      <service behaviorConfiguration="" name="ServiceModel.Calculator">
        <endpoint address="http://localhost/Calculator"
                  binding="wsHttpBinding"
                  bindingConfiguration="KerberosBinding"
                  name="WSHttpBinding_ICalculator"
                  contract="ServiceModel.ICalculator"
                  listenUri="net.tcp://localhost/metadata" >
         <identity>
            <servicePrincipalName value="service_spn_name" />
         </identity>
        </endpoint>
      </service>
    </services>
    <bindings>
      <wsHttpBinding>
        <binding name="KerberosBinding">
          <security>
            <message negotiateServiceCredential="false"
                     establishSecurityContext="false" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    <client />
  </system.serviceModel>
</configuration>
```

## <a name="client"></a><span data-ttu-id="5a187-147">クライアント</span><span class="sxs-lookup"><span data-stu-id="5a187-147">Client</span></span>

<span data-ttu-id="5a187-148">次のコードと構成は、別々に実行します。</span><span class="sxs-lookup"><span data-stu-id="5a187-148">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="5a187-149">以下のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="5a187-149">Do one of the following:</span></span>

- <span data-ttu-id="5a187-150">コード (およびクライアント コード) を使用してスタンドアロン クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="5a187-150">Create a stand-alone client using the code (and client code).</span></span>

- <span data-ttu-id="5a187-151">エンドポイント アドレスを定義しないクライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="5a187-151">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="5a187-152">代わりに、引数として構成名を受け取るクライアント コンストラクターを使用します。</span><span class="sxs-lookup"><span data-stu-id="5a187-152">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="5a187-153">例:</span><span class="sxs-lookup"><span data-stu-id="5a187-153">For example:</span></span>

  [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
  [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]

### <a name="code"></a><span data-ttu-id="5a187-154">コード</span><span class="sxs-lookup"><span data-stu-id="5a187-154">Code</span></span>

<span data-ttu-id="5a187-155">クライアントを構成する場合のコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5a187-155">The following code configures the client.</span></span> <span data-ttu-id="5a187-156">セキュリティ モードは Message に設定され、クライアント資格情報の種類は Windows に設定されています。</span><span class="sxs-lookup"><span data-stu-id="5a187-156">The security mode is set to Message, and the client credential type is set to Windows.</span></span> <span data-ttu-id="5a187-157"><xref:System.ServiceModel.MessageSecurityOverHttp.NegotiateServiceCredential%2A> プロパティと <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> プロパティには、`false` が設定されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5a187-157">Note that the <xref:System.ServiceModel.MessageSecurityOverHttp.NegotiateServiceCredential%2A> and <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> properties are set to `false`.</span></span>

> [!NOTE]
> <span data-ttu-id="5a187-158">ネゴシエートせずに Windows の資格情報を使用するには、サービスとの通信を開始する前に、サービスのアカウントの SPN を使用してクライアントを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a187-158">To use Windows credential type without negotiation, the client must be configured with the service's account SPN prior to commencing the communication with the service.</span></span> <span data-ttu-id="5a187-159">クライアントは SPN を使用して Kerberos トークンを取得し、サービスとの通信を認証し保護します。</span><span class="sxs-lookup"><span data-stu-id="5a187-159">The client uses the SPN to get the Kerberos token to authenticate and secure the communication with the service.</span></span> <span data-ttu-id="5a187-160">サービスの SPN を使用してクライアントを構成する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="5a187-160">The following sample shows how to configure the client with the service's SPN.</span></span> <span data-ttu-id="5a187-161">[ServiceModel メタデータユーティリティツール (svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)を使用してクライアントを生成する場合、サービスのメタデータにその情報が含まれていれば、サービスの SPN は、サービスのメタデータ (WSDL) からクライアントに自動的に伝達されます。</span><span class="sxs-lookup"><span data-stu-id="5a187-161">If you are using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the client, the service's SPN will be automatically propagated to the client from the service's metadata (WSDL), if the service's metadata contains that information.</span></span> <span data-ttu-id="5a187-162">サービスのメタデータに SPN を含めるようにサービスを構成する方法の詳細については、このトピックで後述する「サービス」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a187-162">For more information about how to configure the service to include its SPN in the service's metadata, see the "Service" section later in this topic .</span></span>
>
> <span data-ttu-id="5a187-163">Spn、Kerberos、および Active Directory の詳細については、「 [Windows 用の Kerberos テクニカル補完](https://docs.microsoft.com/previous-versions/msp-n-p/ff649429(v=pandp.10))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a187-163">For more information about SPNs, Kerberos, and Active Directory, see [Kerberos Technical Supplement for Windows](https://docs.microsoft.com/previous-versions/msp-n-p/ff649429(v=pandp.10)).</span></span> <span data-ttu-id="5a187-164">エンドポイント id の詳細については、「[認証モードの認証](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a187-164">For more information about endpoint identities, see [SecurityBindingElement Authentication Modes](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md) topic.</span></span>

[!code-csharp[C_SecurityScenarios#19](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#19)]
[!code-vb[C_SecurityScenarios#19](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#19)]

### <a name="configuration"></a><span data-ttu-id="5a187-165">の構成</span><span class="sxs-lookup"><span data-stu-id="5a187-165">Configuration</span></span>

<span data-ttu-id="5a187-166">クライアントを構成する場合のコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5a187-166">The following code configures the client.</span></span> <span data-ttu-id="5a187-167">[\<servicePrincipalName >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceprincipalname.md)要素は、Active Directory ドメイン内のサービスのアカウントに登録されているサービスの SPN と一致するように設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a187-167">Note that the [\<servicePrincipalName>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceprincipalname.md) element must be set to match the service's SPN as registered for the service's account in the Active Directory domain.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <system.serviceModel>
    <bindings>
      <wsHttpBinding>
        <binding name="WSHttpBinding_ICalculator" >
          <security mode="Message">
            <message clientCredentialType="Windows"
                     negotiateServiceCredential="false"
                     establishSecurityContext="false" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    <client>
      <endpoint address="http://localhost/Calculator"
                binding="wsHttpBinding"
                bindingConfiguration="WSHttpBinding_ICalculator"
                contract="ICalculator"
                name="WSHttpBinding_ICalculator">
        <identity>
          <servicePrincipalName value="service_spn_name" />
        </identity>
      </endpoint>
    </client>
  </system.serviceModel>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="5a187-168">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a187-168">See also</span></span>

- [<span data-ttu-id="5a187-169">セキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="5a187-169">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [<span data-ttu-id="5a187-170">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="5a187-170">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- <span data-ttu-id="5a187-171">[Windows Server App Fabric のセキュリティモデル](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="5a187-171">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
