---
title: <transport> の <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: 3b180006-1661-43bf-a699-96fd3da469af
ms.openlocfilehash: 44e334c3313f93a23ca7df15ba377c5568a92397
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788376"
---
# <a name="transport-of-nethttpbinding"></a><span data-ttu-id="d05a4-102">\<トランスポート > の\<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="d05a4-102">\<transport> of \<netHttpBinding></span></span>
<span data-ttu-id="d05a4-103">HTTP トランスポートの認証パラメーターを制御するプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="d05a4-103">Defines properties that control authentication parameters for the HTTP transport.</span></span>  
  
<span data-ttu-id="d05a4-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d05a4-104">\<system.serviceModel></span></span>  
<span data-ttu-id="d05a4-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="d05a4-105">\<bindings></span></span>  
<span data-ttu-id="d05a4-106">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="d05a4-106">\<netHttpBinding></span></span>  
<span data-ttu-id="d05a4-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="d05a4-107">\<binding></span></span>  
<span data-ttu-id="d05a4-108">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="d05a4-108">\<security></span></span>  
<span data-ttu-id="d05a4-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="d05a4-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d05a4-110">構文</span><span class="sxs-lookup"><span data-stu-id="d05a4-110">Syntax</span></span>  
  
```xml  
<netHttpBinding>
  <binding>
    <security mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"
                 proxyCredentialType="None|Basic|Digest|Ntlm|Windows"
                 realm="string">
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</netHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d05a4-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d05a4-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d05a4-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d05a4-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d05a4-113">属性</span><span class="sxs-lookup"><span data-stu-id="d05a4-113">Attributes</span></span>  
  
|<span data-ttu-id="d05a4-114">属性</span><span class="sxs-lookup"><span data-stu-id="d05a4-114">Attribute</span></span>|<span data-ttu-id="d05a4-115">説明</span><span class="sxs-lookup"><span data-stu-id="d05a4-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d05a4-116">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="d05a4-116">clientCredentialType</span></span>|<span data-ttu-id="d05a4-117">-HTTP 認証を使用してクライアント認証を実行するときに使用される資格情報の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="d05a4-117">-   Specifies the type of credential to be used when performing client authentication using HTTP authentication.</span></span>  <span data-ttu-id="d05a4-118">既定値は `None` です。</span><span class="sxs-lookup"><span data-stu-id="d05a4-118">The default is `None`.</span></span> <span data-ttu-id="d05a4-119">この属性は <xref:System.ServiceModel.HttpClientCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="d05a4-119">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|<span data-ttu-id="d05a4-120">proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="d05a4-120">proxyCredentialType</span></span>|<span data-ttu-id="d05a4-121">-HTTP 経由でプロキシを使用してドメイン内からクライアント認証を実行するときに使用される資格情報の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="d05a4-121">-   Specifies the type of credential to be used when performing client authentication from within a domain using a proxy over HTTP.</span></span> <span data-ttu-id="d05a4-122">この属性は、親 `mode` 要素の `security` 属性が `Transport` または `TransportCredentialsOnly` の場合にだけ適用されます。</span><span class="sxs-lookup"><span data-stu-id="d05a4-122">This attribute is applicable only when the `mode` attribute of the parent `security` element is `Transport` or `TransportCredentialsOnly`.</span></span> <span data-ttu-id="d05a4-123">この属性は <xref:System.ServiceModel.HttpProxyCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="d05a4-123">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|<span data-ttu-id="d05a4-124">realm</span><span class="sxs-lookup"><span data-stu-id="d05a4-124">realm</span></span>|<span data-ttu-id="d05a4-125">ダイジェストまたは基本認証の HTTP 認証方式によって使用されるレルムを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="d05a4-125">A string that specifies the realm that is used by the HTTP authentication scheme for digest or basic authentication.</span></span> <span data-ttu-id="d05a4-126">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="d05a4-126">The default is an empty string.</span></span>|  
|<span data-ttu-id="d05a4-127">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="d05a4-127">policyEnforcement</span></span>|<span data-ttu-id="d05a4-128">この列挙体は、<xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> を適用するタイミングを指定します。</span><span class="sxs-lookup"><span data-stu-id="d05a4-128">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="d05a4-129">1.Never – ポリシーが適用されることはありません (拡張保護は無効になります)。</span><span class="sxs-lookup"><span data-stu-id="d05a4-129">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="d05a4-130">2.WhenSupported – ポリシーが適用されるのは、クライアントが拡張保護をサポートしている場合のみです。</span><span class="sxs-lookup"><span data-stu-id="d05a4-130">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="d05a4-131">3.Always – ポリシーは常に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d05a4-131">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="d05a4-132">拡張保護をサポートしていないクライアントは認証に失敗します。</span><span class="sxs-lookup"><span data-stu-id="d05a4-132">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
|<span data-ttu-id="d05a4-133">protectionScenario</span><span class="sxs-lookup"><span data-stu-id="d05a4-133">protectionScenario</span></span>|<span data-ttu-id="d05a4-134">この列挙体は、ポリシーによって適用される保護シナリオを指定します。</span><span class="sxs-lookup"><span data-stu-id="d05a4-134">This enumeration specifies the protection scenario enforced by the policy.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="d05a4-135">clientCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="d05a4-135">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="d05a4-136">[値]</span><span class="sxs-lookup"><span data-stu-id="d05a4-136">Value</span></span>|<span data-ttu-id="d05a4-137">説明</span><span class="sxs-lookup"><span data-stu-id="d05a4-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d05a4-138">なし</span><span class="sxs-lookup"><span data-stu-id="d05a4-138">None</span></span>|<span data-ttu-id="d05a4-139">メッセージは、転送中はセキュリティで保護されません。</span><span class="sxs-lookup"><span data-stu-id="d05a4-139">Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="d05a4-140">Basic</span><span class="sxs-lookup"><span data-stu-id="d05a4-140">Basic</span></span>|<span data-ttu-id="d05a4-141">基本認証を指定します。</span><span class="sxs-lookup"><span data-stu-id="d05a4-141">Specifies basic authentication.</span></span>|  
|<span data-ttu-id="d05a4-142">Digest</span><span class="sxs-lookup"><span data-stu-id="d05a4-142">Digest</span></span>|<span data-ttu-id="d05a4-143">ダイジェスト認証を指定します。</span><span class="sxs-lookup"><span data-stu-id="d05a4-143">Specifies digest authentication.</span></span>|  
|<span data-ttu-id="d05a4-144">Ntlm</span><span class="sxs-lookup"><span data-stu-id="d05a4-144">Ntlm</span></span>|<span data-ttu-id="d05a4-145">Windows 認証に失敗した場合で可能な場合は、NTLM 認証を指定します。</span><span class="sxs-lookup"><span data-stu-id="d05a4-145">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="d05a4-146">Windows</span><span class="sxs-lookup"><span data-stu-id="d05a4-146">Windows</span></span>|<span data-ttu-id="d05a4-147">Windows 統合認証を指定します。</span><span class="sxs-lookup"><span data-stu-id="d05a4-147">Specifies Windows integrated authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="d05a4-148">proxyCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="d05a4-148">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="d05a4-149">[値]</span><span class="sxs-lookup"><span data-stu-id="d05a4-149">Value</span></span>|<span data-ttu-id="d05a4-150">説明</span><span class="sxs-lookup"><span data-stu-id="d05a4-150">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d05a4-151">なし</span><span class="sxs-lookup"><span data-stu-id="d05a4-151">None</span></span>|<span data-ttu-id="d05a4-152">メッセージの数は、転送中にセキュリティ保護されません。</span><span class="sxs-lookup"><span data-stu-id="d05a4-152">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="d05a4-153">Basic</span><span class="sxs-lookup"><span data-stu-id="d05a4-153">Basic</span></span>|<span data-ttu-id="d05a4-154">RFC 2617 – HTTP Authentication で定義されている基本認証を指定します。基本認証とダイジェスト認証です。</span><span class="sxs-lookup"><span data-stu-id="d05a4-154">Specifies basic authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="d05a4-155">Digest</span><span class="sxs-lookup"><span data-stu-id="d05a4-155">Digest</span></span>|<span data-ttu-id="d05a4-156">RFC 2617 – HTTP Authentication で定義されている、ダイジェスト認証を指定します。基本認証とダイジェスト認証です。</span><span class="sxs-lookup"><span data-stu-id="d05a4-156">Specifies digest authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="d05a4-157">Ntlm</span><span class="sxs-lookup"><span data-stu-id="d05a4-157">Ntlm</span></span>|<span data-ttu-id="d05a4-158">Windows 認証に失敗した場合で可能な場合は、NTLM 認証を指定します。</span><span class="sxs-lookup"><span data-stu-id="d05a4-158">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="d05a4-159">Windows</span><span class="sxs-lookup"><span data-stu-id="d05a4-159">Windows</span></span>|<span data-ttu-id="d05a4-160">Windows 統合認証を指定します。</span><span class="sxs-lookup"><span data-stu-id="d05a4-160">Specifies Windows integrated authentication.</span></span>|  
|<span data-ttu-id="d05a4-161">証明書</span><span class="sxs-lookup"><span data-stu-id="d05a4-161">Certificate</span></span>|<span data-ttu-id="d05a4-162">証明書を使用したクライアント認証を実行します。</span><span class="sxs-lookup"><span data-stu-id="d05a4-162">Performs client authentication using a certificate.</span></span> <span data-ttu-id="d05a4-163">このオプションは、親要素の `Mode` の `security` 属性が Transport に設定されている場合のみ機能し、TransportCredentialOnly に設定されている場合は機能しません。</span><span class="sxs-lookup"><span data-stu-id="d05a4-163">This option works only if the `Mode` attribute of the parent `security` element is set to Transport, and will not work if it is set to TransportCredentialOnly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d05a4-164">子要素</span><span class="sxs-lookup"><span data-stu-id="d05a4-164">Child Elements</span></span>  
 <span data-ttu-id="d05a4-165">なし</span><span class="sxs-lookup"><span data-stu-id="d05a4-165">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d05a4-166">親要素</span><span class="sxs-lookup"><span data-stu-id="d05a4-166">Parent Elements</span></span>  
  
|<span data-ttu-id="d05a4-167">要素</span><span class="sxs-lookup"><span data-stu-id="d05a4-167">Element</span></span>|<span data-ttu-id="d05a4-168">説明</span><span class="sxs-lookup"><span data-stu-id="d05a4-168">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d05a4-169">\<security></span><span class="sxs-lookup"><span data-stu-id="d05a4-169">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nethttpbinding.md)|<span data-ttu-id="d05a4-170">セキュリティ機能を定義、 [ \<netHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nethttpbinding.md)します。</span><span class="sxs-lookup"><span data-stu-id="d05a4-170">Defines the security capabilities for the [\<netHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/nethttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d05a4-171">例</span><span class="sxs-lookup"><span data-stu-id="d05a4-171">Example</span></span>  
 <span data-ttu-id="d05a4-172">基本的なバインディングを使用した SSL トランスポート セキュリティの使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d05a4-172">The following example demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="d05a4-173">既定で、基本的なバインディングは HTTP 通信をサポートします。</span><span class="sxs-lookup"><span data-stu-id="d05a4-173">By default, the basic binding supports HTTP communication.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <endpoint address=""
                binding="netHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>
  <bindings>
    <netHttpBinding>
      <!-- Configure basicHttpBinding with Transport security -->
      <!-- mode and clientCredentialType set to None. -->
      <binding name="Binding1">
        <security mode="Transport">
          <transport clientCredentialType="None"
                     proxyCredentialType="None">
            <extendedProtectionPolicy policyEnforcement="WhenSupported"
                                      protectionScenario="TransportSelected">
              <customServiceNames>
              </customServiceNames>
            </extendedProtectionPolicy>
          </transport>
        </security>
      </binding>
    </netHttpBinding>
  </bindings>
</system.serviceModel>
```  
  
## <a name="see-also"></a><span data-ttu-id="d05a4-174">関連項目</span><span class="sxs-lookup"><span data-stu-id="d05a4-174">See also</span></span>

- <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- <xref:System.ServiceModel.HttpTransportSecurity>
- [<span data-ttu-id="d05a4-175">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="d05a4-175">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="d05a4-176">バインディング</span><span class="sxs-lookup"><span data-stu-id="d05a4-176">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="d05a4-177">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="d05a4-177">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="d05a4-178">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="d05a4-178">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="d05a4-179">\<binding></span><span class="sxs-lookup"><span data-stu-id="d05a4-179">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
