---
title: <transport> の <netTcpBinding>
ms.date: 03/30/2017
ms.assetid: 49462e0a-66e1-463f-b3e1-c83a441673c6
ms.openlocfilehash: 4ef08ad73a03dea21d27217364a7bacb46a3848e
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73735935"
---
# <a name="transport-of-nettcpbinding"></a><span data-ttu-id="66ebf-102">\<netTcpBinding> の \<transport></span><span class="sxs-lookup"><span data-stu-id="66ebf-102">\<transport> of \<netTcpBinding></span></span>
<span data-ttu-id="66ebf-103">[\<netTcpBinding >](nettcpbinding.md)で構成されるエンドポイントのメッセージレベルのセキュリティ要件の種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="66ebf-103">Defines the type of message-level security requirements for an endpoint configured with the [\<netTcpBinding>](nettcpbinding.md).</span></span>  
  
<span data-ttu-id="66ebf-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="66ebf-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="66ebf-105">&nbsp; &nbsp;[ **\<system >** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="66ebf-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="66ebf-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**バインド**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="66ebf-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="66ebf-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netTcpBinding >** ](nettcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="66ebf-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netTcpBinding>**](nettcpbinding.md)</span></span>\
<span data-ttu-id="66ebf-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**バインド >** </span><span class="sxs-lookup"><span data-stu-id="66ebf-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="66ebf-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**セキュリティ >** ](security-of-nettcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="66ebf-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-nettcpbinding.md)</span></span>\
<span data-ttu-id="66ebf-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**トランスポート >**</span><span class="sxs-lookup"><span data-stu-id="66ebf-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66ebf-111">構文</span><span class="sxs-lookup"><span data-stu-id="66ebf-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="66ebf-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="66ebf-112">Attributes and Elements</span></span>  
 <span data-ttu-id="66ebf-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="66ebf-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="66ebf-114">属性</span><span class="sxs-lookup"><span data-stu-id="66ebf-114">Attributes</span></span>  
  
|<span data-ttu-id="66ebf-115">属性</span><span class="sxs-lookup"><span data-stu-id="66ebf-115">Attribute</span></span>|<span data-ttu-id="66ebf-116">説明</span><span class="sxs-lookup"><span data-stu-id="66ebf-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="66ebf-117">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="66ebf-117">clientCredentialType</span></span>|<span data-ttu-id="66ebf-118">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="66ebf-118">Optional.</span></span> <span data-ttu-id="66ebf-119">トランスポート セキュリティを使用してクライアント認証を実行するときに使用される資格情報の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="66ebf-119">Specifies the type of credential to be used when performing client authentication using Transport security.</span></span><br /><br /> <span data-ttu-id="66ebf-120">-既定値は `Windows`です。</span><span class="sxs-lookup"><span data-stu-id="66ebf-120">-   The default value is `Windows`.</span></span><br /><span data-ttu-id="66ebf-121">-この属性の型は <xref:System.ServiceModel.TcpClientCredentialType>です。</span><span class="sxs-lookup"><span data-stu-id="66ebf-121">-   This attribute is of type <xref:System.ServiceModel.TcpClientCredentialType>.</span></span>|  
|<span data-ttu-id="66ebf-122">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="66ebf-122">protectionLevel</span></span>|<span data-ttu-id="66ebf-123">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="66ebf-123">Optional.</span></span> <span data-ttu-id="66ebf-124">TCP トランスポートのレベルでセキュリティを定義します。</span><span class="sxs-lookup"><span data-stu-id="66ebf-124">Defines security at the level of the TCP transport.</span></span> <span data-ttu-id="66ebf-125">メッセージに署名すると、転送中のメッセージが第三者によって改ざんされるリスクを軽減します。</span><span class="sxs-lookup"><span data-stu-id="66ebf-125">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="66ebf-126">暗号化により、転送中にデータレベルのプライバシーが提供されます。</span><span class="sxs-lookup"><span data-stu-id="66ebf-126">Encryption provides data-level privacy during transport.</span></span><br /><br /> <span data-ttu-id="66ebf-127">既定値は `EncryptAndSign`です。</span><span class="sxs-lookup"><span data-stu-id="66ebf-127">The default value is `EncryptAndSign`.</span></span>|  
|<span data-ttu-id="66ebf-128">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="66ebf-128">sslProtocols</span></span>|<span data-ttu-id="66ebf-129">どの SslProtocols がサポートされているのかを指定する SslProtocols 列挙型フラグの値。</span><span class="sxs-lookup"><span data-stu-id="66ebf-129">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="66ebf-130">既定値は Tls&#124;Tls11&#124;Tls12 です。</span><span class="sxs-lookup"><span data-stu-id="66ebf-130">The default is Tls&#124;Tls11&#124;Tls12.</span></span>|  
|<span data-ttu-id="66ebf-131">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="66ebf-131">policyEnforcement</span></span>|<span data-ttu-id="66ebf-132">この列挙体は、<xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> を適用するタイミングを指定します。</span><span class="sxs-lookup"><span data-stu-id="66ebf-132">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="66ebf-133">1. never –ポリシーは適用されません (拡張保護は無効になります)。</span><span class="sxs-lookup"><span data-stu-id="66ebf-133">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="66ebf-134">2. WhenSupported –ポリシーは、クライアントが拡張保護をサポートしている場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="66ebf-134">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="66ebf-135">3. always –ポリシーは常に適用されます。</span><span class="sxs-lookup"><span data-stu-id="66ebf-135">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="66ebf-136">拡張保護をサポートしていないクライアントは認証に失敗します。</span><span class="sxs-lookup"><span data-stu-id="66ebf-136">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="66ebf-137">clientCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="66ebf-137">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="66ebf-138">[値]</span><span class="sxs-lookup"><span data-stu-id="66ebf-138">Value</span></span>|<span data-ttu-id="66ebf-139">説明</span><span class="sxs-lookup"><span data-stu-id="66ebf-139">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="66ebf-140">None</span><span class="sxs-lookup"><span data-stu-id="66ebf-140">None</span></span>|<span data-ttu-id="66ebf-141">クライアントは匿名です。</span><span class="sxs-lookup"><span data-stu-id="66ebf-141">The client is anonymous.</span></span> <span data-ttu-id="66ebf-142">これには、サービスの証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="66ebf-142">This requires a certificate for the service.</span></span>|  
|<span data-ttu-id="66ebf-143">Windows</span><span class="sxs-lookup"><span data-stu-id="66ebf-143">Windows</span></span>|<span data-ttu-id="66ebf-144">SP ネゴシエーション (Kerberos ネゴシエーション) を使用して、クライアントの Windows 認証を指定します。</span><span class="sxs-lookup"><span data-stu-id="66ebf-144">Specifies Windows authentication of the client using SP Negotiation (Kerberos negotiation).</span></span>|  
|<span data-ttu-id="66ebf-145">証明書</span><span class="sxs-lookup"><span data-stu-id="66ebf-145">Certificate</span></span>|<span data-ttu-id="66ebf-146">クライアントは、証明書を使用して認証されます。</span><span class="sxs-lookup"><span data-stu-id="66ebf-146">The client is authenticated using a certificate.</span></span> <span data-ttu-id="66ebf-147">これは SSL ネゴシエーションを使用し、サービスの証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="66ebf-147">This uses SSL Negotiation and requires a certificate for the service.</span></span>|  
  
## <a name="protectionlevel-attribute"></a><span data-ttu-id="66ebf-148">protectionLevel 属性</span><span class="sxs-lookup"><span data-stu-id="66ebf-148">protectionLevel Attribute</span></span>  
  
|<span data-ttu-id="66ebf-149">[値]</span><span class="sxs-lookup"><span data-stu-id="66ebf-149">Value</span></span>|<span data-ttu-id="66ebf-150">説明</span><span class="sxs-lookup"><span data-stu-id="66ebf-150">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="66ebf-151">None</span><span class="sxs-lookup"><span data-stu-id="66ebf-151">None</span></span>|<span data-ttu-id="66ebf-152">保護されません。</span><span class="sxs-lookup"><span data-stu-id="66ebf-152">No protection.</span></span>|  
|<span data-ttu-id="66ebf-153">Sign</span><span class="sxs-lookup"><span data-stu-id="66ebf-153">Sign</span></span>|<span data-ttu-id="66ebf-154">メッセージは署名されます。</span><span class="sxs-lookup"><span data-stu-id="66ebf-154">Messages are signed.</span></span>|  
|<span data-ttu-id="66ebf-155">EncryptAndSign</span><span class="sxs-lookup"><span data-stu-id="66ebf-155">EncryptAndSign</span></span>|<span data-ttu-id="66ebf-156">-メッセージは暗号化され、署名されます。</span><span class="sxs-lookup"><span data-stu-id="66ebf-156">-   Messages are encrypted and signed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="66ebf-157">子要素</span><span class="sxs-lookup"><span data-stu-id="66ebf-157">Child Elements</span></span>  
 <span data-ttu-id="66ebf-158">None</span><span class="sxs-lookup"><span data-stu-id="66ebf-158">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="66ebf-159">親要素</span><span class="sxs-lookup"><span data-stu-id="66ebf-159">Parent Elements</span></span>  
  
|<span data-ttu-id="66ebf-160">要素</span><span class="sxs-lookup"><span data-stu-id="66ebf-160">Element</span></span>|<span data-ttu-id="66ebf-161">説明</span><span class="sxs-lookup"><span data-stu-id="66ebf-161">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="66ebf-162">\< セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="66ebf-162">\<security></span></span>](security-of-nettcpbinding.md)|<span data-ttu-id="66ebf-163">[\<netTcpBinding >](nettcpbinding.md)のセキュリティ機能を指定します。</span><span class="sxs-lookup"><span data-stu-id="66ebf-163">Specifies the security capabilities of the [\<netTcpBinding>](nettcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="66ebf-164">Remarks</span><span class="sxs-lookup"><span data-stu-id="66ebf-164">Remarks</span></span>  
 <span data-ttu-id="66ebf-165">トランスポート セキュリティは、SOAP メッセージの整合性と機密性の保護、および相互認証に使用します。</span><span class="sxs-lookup"><span data-stu-id="66ebf-165">Use Transport security for integrity and confidentiality of the SOAP message and for mutual authentication.</span></span> <span data-ttu-id="66ebf-166">このセキュリティ モードがバインディング上で選択された場合、チャネル スタックはセキュリティ トランスポートを使用して構成され、SOAP メッセージは Windows (ネゴシエート) や TCP 上の SSL などのトランスポート セキュリティを使用して保護されます。</span><span class="sxs-lookup"><span data-stu-id="66ebf-166">If this security mode is selected on a binding, the channel stack is configured using a secure transport and the SOAP messages are secured using transport security such as Windows (Negotiate) or SSL over TCP.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66ebf-167">関連項目</span><span class="sxs-lookup"><span data-stu-id="66ebf-167">See also</span></span>

- <xref:System.ServiceModel.TcpTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetTcpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>
- [<span data-ttu-id="66ebf-168">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="66ebf-168">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="66ebf-169">バインディング</span><span class="sxs-lookup"><span data-stu-id="66ebf-169">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="66ebf-170">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="66ebf-170">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="66ebf-171">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="66ebf-171">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="66ebf-172">\<binding ></span><span class="sxs-lookup"><span data-stu-id="66ebf-172">\<binding></span></span>](bindings.md)
