---
title: <transport> の <netTcpBinding>
ms.date: 03/30/2017
ms.assetid: 49462e0a-66e1-463f-b3e1-c83a441673c6
ms.openlocfilehash: 265b68e058919d1d5c5f1dbcfb1419b57be9aeab
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915549"
---
# <a name="transport-of-nettcpbinding"></a><span data-ttu-id="29398-102">\<netTcpBinding> の \<transport></span><span class="sxs-lookup"><span data-stu-id="29398-102">\<transport> of \<netTcpBinding></span></span>
<span data-ttu-id="29398-103">[ \<NetTcpBinding >](nettcpbinding.md)で構成されるエンドポイントのメッセージレベルのセキュリティ要件の種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="29398-103">Defines the type of message-level security requirements for an endpoint configured with the [\<netTcpBinding>](nettcpbinding.md).</span></span>  
  
 <span data-ttu-id="29398-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="29398-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="29398-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="29398-105">\<bindings></span></span>  
<span data-ttu-id="29398-106">\<netTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="29398-106">\<netTcpBinding></span></span>  
<span data-ttu-id="29398-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="29398-107">\<binding></span></span>  
<span data-ttu-id="29398-108">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="29398-108">\<security></span></span>  
<span data-ttu-id="29398-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="29398-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29398-110">構文</span><span class="sxs-lookup"><span data-stu-id="29398-110">Syntax</span></span>  
  
```xml  
<netTcpBinding>
  <binding>
    <security mode="None|Transport|Message|TransportWithMessageCredential">
      <transport clientCredentialType="None|Windows|Certificate"
                 protectionLevel="None|Sign|EncryptAndSign"
                 sslProtocols="Tls|Tls11|Tls12">
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</netTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="29398-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="29398-111">Attributes and Elements</span></span>  
 <span data-ttu-id="29398-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="29398-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="29398-113">属性</span><span class="sxs-lookup"><span data-stu-id="29398-113">Attributes</span></span>  
  
|<span data-ttu-id="29398-114">属性</span><span class="sxs-lookup"><span data-stu-id="29398-114">Attribute</span></span>|<span data-ttu-id="29398-115">説明</span><span class="sxs-lookup"><span data-stu-id="29398-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="29398-116">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="29398-116">clientCredentialType</span></span>|<span data-ttu-id="29398-117">任意。</span><span class="sxs-lookup"><span data-stu-id="29398-117">Optional.</span></span> <span data-ttu-id="29398-118">トランスポート セキュリティを使用してクライアント認証を実行するときに使用される資格情報の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="29398-118">Specifies the type of credential to be used when performing client authentication using Transport security.</span></span><br /><br /> <span data-ttu-id="29398-119">-既定値は`Windows`です。</span><span class="sxs-lookup"><span data-stu-id="29398-119">-   The default value is `Windows`.</span></span><br /><span data-ttu-id="29398-120">-この属性の型<xref:System.ServiceModel.TcpClientCredentialType>はです。</span><span class="sxs-lookup"><span data-stu-id="29398-120">-   This attribute is of type <xref:System.ServiceModel.TcpClientCredentialType>.</span></span>|  
|<span data-ttu-id="29398-121">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="29398-121">protectionLevel</span></span>|<span data-ttu-id="29398-122">任意。</span><span class="sxs-lookup"><span data-stu-id="29398-122">Optional.</span></span> <span data-ttu-id="29398-123">TCP トランスポートのレベルでセキュリティを定義します。</span><span class="sxs-lookup"><span data-stu-id="29398-123">Defines security at the level of the TCP transport.</span></span> <span data-ttu-id="29398-124">メッセージに署名を付けることで、メッセージの転送中に第三者によって改ざんされるリスクが軽減されます。</span><span class="sxs-lookup"><span data-stu-id="29398-124">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="29398-125">暗号化によって、トランスポート中にデータ レベルのプライバシーが提供されます。</span><span class="sxs-lookup"><span data-stu-id="29398-125">Encryption provides data-level privacy during transport.</span></span><br /><br /> <span data-ttu-id="29398-126">既定値は `EncryptAndSign` です。</span><span class="sxs-lookup"><span data-stu-id="29398-126">The default value is `EncryptAndSign`.</span></span>|  
|<span data-ttu-id="29398-127">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="29398-127">sslProtocols</span></span>|<span data-ttu-id="29398-128">どの SslProtocols がサポートされているのかを指定する SslProtocols 列挙型フラグの値。</span><span class="sxs-lookup"><span data-stu-id="29398-128">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="29398-129">既定値は Tls&#124;Tls11&#124;Tls12 です。</span><span class="sxs-lookup"><span data-stu-id="29398-129">The default is Tls&#124;Tls11&#124;Tls12.</span></span>|  
|<span data-ttu-id="29398-130">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="29398-130">policyEnforcement</span></span>|<span data-ttu-id="29398-131">この列挙体は、<xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> を適用するタイミングを指定します。</span><span class="sxs-lookup"><span data-stu-id="29398-131">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="29398-132">1. Never – ポリシーが適用されることはありません (拡張保護は無効になります)。</span><span class="sxs-lookup"><span data-stu-id="29398-132">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="29398-133">2. WhenSupported – ポリシーが適用されるのは、クライアントが拡張保護をサポートしている場合のみです。</span><span class="sxs-lookup"><span data-stu-id="29398-133">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="29398-134">3.Always – ポリシーは常に適用されます。</span><span class="sxs-lookup"><span data-stu-id="29398-134">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="29398-135">拡張保護をサポートしていないクライアントは認証に失敗します。</span><span class="sxs-lookup"><span data-stu-id="29398-135">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="29398-136">clientCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="29398-136">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="29398-137">値</span><span class="sxs-lookup"><span data-stu-id="29398-137">Value</span></span>|<span data-ttu-id="29398-138">説明</span><span class="sxs-lookup"><span data-stu-id="29398-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="29398-139">なし</span><span class="sxs-lookup"><span data-stu-id="29398-139">None</span></span>|<span data-ttu-id="29398-140">クライアントは匿名です。</span><span class="sxs-lookup"><span data-stu-id="29398-140">The client is anonymous.</span></span> <span data-ttu-id="29398-141">これには、サービスの証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="29398-141">This requires a certificate for the service.</span></span>|  
|<span data-ttu-id="29398-142">Windows</span><span class="sxs-lookup"><span data-stu-id="29398-142">Windows</span></span>|<span data-ttu-id="29398-143">SP ネゴシエーション (Kerberos ネゴシエーション) を使用して、クライアントの Windows 認証を指定します。</span><span class="sxs-lookup"><span data-stu-id="29398-143">Specifies Windows authentication of the client using SP Negotiation (Kerberos negotiation).</span></span>|  
|<span data-ttu-id="29398-144">証明書</span><span class="sxs-lookup"><span data-stu-id="29398-144">Certificate</span></span>|<span data-ttu-id="29398-145">クライアントは、証明書を使用して認証されます。</span><span class="sxs-lookup"><span data-stu-id="29398-145">The client is authenticated using a certificate.</span></span> <span data-ttu-id="29398-146">これは SSL ネゴシエーションを使用し、サービスの証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="29398-146">This uses SSL Negotiation and requires a certificate for the service.</span></span>|  
  
## <a name="protectionlevel-attribute"></a><span data-ttu-id="29398-147">protectionLevel 属性</span><span class="sxs-lookup"><span data-stu-id="29398-147">protectionLevel Attribute</span></span>  
  
|<span data-ttu-id="29398-148">値</span><span class="sxs-lookup"><span data-stu-id="29398-148">Value</span></span>|<span data-ttu-id="29398-149">説明</span><span class="sxs-lookup"><span data-stu-id="29398-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="29398-150">なし</span><span class="sxs-lookup"><span data-stu-id="29398-150">None</span></span>|<span data-ttu-id="29398-151">保護されません。</span><span class="sxs-lookup"><span data-stu-id="29398-151">No protection.</span></span>|  
|<span data-ttu-id="29398-152">Sign</span><span class="sxs-lookup"><span data-stu-id="29398-152">Sign</span></span>|<span data-ttu-id="29398-153">メッセージは署名されます。</span><span class="sxs-lookup"><span data-stu-id="29398-153">Messages are signed.</span></span>|  
|<span data-ttu-id="29398-154">EncryptAndSign</span><span class="sxs-lookup"><span data-stu-id="29398-154">EncryptAndSign</span></span>|<span data-ttu-id="29398-155">-メッセージは暗号化され、署名されます。</span><span class="sxs-lookup"><span data-stu-id="29398-155">-   Messages are encrypted and signed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="29398-156">子要素</span><span class="sxs-lookup"><span data-stu-id="29398-156">Child Elements</span></span>  
 <span data-ttu-id="29398-157">なし</span><span class="sxs-lookup"><span data-stu-id="29398-157">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="29398-158">親要素</span><span class="sxs-lookup"><span data-stu-id="29398-158">Parent Elements</span></span>  
  
|<span data-ttu-id="29398-159">要素</span><span class="sxs-lookup"><span data-stu-id="29398-159">Element</span></span>|<span data-ttu-id="29398-160">説明</span><span class="sxs-lookup"><span data-stu-id="29398-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="29398-161">\<security></span><span class="sxs-lookup"><span data-stu-id="29398-161">\<security></span></span>](security-of-nettcpbinding.md)|<span data-ttu-id="29398-162">[ \<NetTcpBinding >](nettcpbinding.md)のセキュリティ機能を指定します。</span><span class="sxs-lookup"><span data-stu-id="29398-162">Specifies the security capabilities of the [\<netTcpBinding>](nettcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29398-163">Remarks</span><span class="sxs-lookup"><span data-stu-id="29398-163">Remarks</span></span>  
 <span data-ttu-id="29398-164">トランスポート セキュリティは、SOAP メッセージの整合性と機密性の保護、および相互認証に使用します。</span><span class="sxs-lookup"><span data-stu-id="29398-164">Use Transport security for integrity and confidentiality of the SOAP message and for mutual authentication.</span></span> <span data-ttu-id="29398-165">このセキュリティ モードがバインディング上で選択された場合、チャネル スタックはセキュリティ トランスポートを使用して構成され、SOAP メッセージは Windows (ネゴシエート) や TCP 上の SSL などのトランスポート セキュリティを使用して保護されます。</span><span class="sxs-lookup"><span data-stu-id="29398-165">If this security mode is selected on a binding, the channel stack is configured using a secure transport and the SOAP messages are secured using transport security such as Windows (Negotiate) or SSL over TCP.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29398-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="29398-166">See also</span></span>

- <xref:System.ServiceModel.TcpTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetTcpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>
- [<span data-ttu-id="29398-167">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="29398-167">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="29398-168">バインディング</span><span class="sxs-lookup"><span data-stu-id="29398-168">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="29398-169">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="29398-169">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="29398-170">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="29398-170">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="29398-171">\<binding></span><span class="sxs-lookup"><span data-stu-id="29398-171">\<binding></span></span>](../../../misc/binding.md)
