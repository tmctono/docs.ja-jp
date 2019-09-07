---
title: <transport> の <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: 3b180006-1661-43bf-a699-96fd3da469af
ms.openlocfilehash: 521aaf3913a1d30d10a674b71d4d98affcabc296
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399340"
---
# <a name="transport-of-nethttpbinding"></a><span data-ttu-id="2746f-102">\<netHttpBinding の\<トランスポート > ></span><span class="sxs-lookup"><span data-stu-id="2746f-102">\<transport> of \<netHttpBinding></span></span>
<span data-ttu-id="2746f-103">HTTP トランスポートの認証パラメーターを制御するプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="2746f-103">Defines properties that control authentication parameters for the HTTP transport.</span></span>  
  
<span data-ttu-id="2746f-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2746f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2746f-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2746f-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2746f-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<バインド >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="2746f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="2746f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netHttpBinding >** ](nethttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="2746f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)</span></span>\
<span data-ttu-id="2746f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<バインド >** </span><span class="sxs-lookup"><span data-stu-id="2746f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="2746f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<セキュリティ >** ](security-of-nethttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="2746f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-nethttpbinding.md)</span></span>\
<span data-ttu-id="2746f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<トランスポート >**</span><span class="sxs-lookup"><span data-stu-id="2746f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2746f-111">構文</span><span class="sxs-lookup"><span data-stu-id="2746f-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2746f-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="2746f-112">Attributes and Elements</span></span>  
 <span data-ttu-id="2746f-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2746f-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2746f-114">属性</span><span class="sxs-lookup"><span data-stu-id="2746f-114">Attributes</span></span>  
  
|<span data-ttu-id="2746f-115">属性</span><span class="sxs-lookup"><span data-stu-id="2746f-115">Attribute</span></span>|<span data-ttu-id="2746f-116">説明</span><span class="sxs-lookup"><span data-stu-id="2746f-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2746f-117">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="2746f-117">clientCredentialType</span></span>|<span data-ttu-id="2746f-118">-HTTP 認証を使用してクライアント認証を実行するときに使用される資格情報の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="2746f-118">-   Specifies the type of credential to be used when performing client authentication using HTTP authentication.</span></span>  <span data-ttu-id="2746f-119">既定値は `None` です。</span><span class="sxs-lookup"><span data-stu-id="2746f-119">The default is `None`.</span></span> <span data-ttu-id="2746f-120">この属性は <xref:System.ServiceModel.HttpClientCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="2746f-120">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|<span data-ttu-id="2746f-121">proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="2746f-121">proxyCredentialType</span></span>|<span data-ttu-id="2746f-122">-HTTP 経由のプロキシを使用してドメイン内からクライアント認証を実行するときに使用される資格情報の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="2746f-122">-   Specifies the type of credential to be used when performing client authentication from within a domain using a proxy over HTTP.</span></span> <span data-ttu-id="2746f-123">この属性は、親 `mode` 要素の `security` 属性が `Transport` または `TransportCredentialsOnly` の場合にだけ適用されます。</span><span class="sxs-lookup"><span data-stu-id="2746f-123">This attribute is applicable only when the `mode` attribute of the parent `security` element is `Transport` or `TransportCredentialsOnly`.</span></span> <span data-ttu-id="2746f-124">この属性は <xref:System.ServiceModel.HttpProxyCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="2746f-124">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|<span data-ttu-id="2746f-125">realm</span><span class="sxs-lookup"><span data-stu-id="2746f-125">realm</span></span>|<span data-ttu-id="2746f-126">ダイジェストまたは基本認証の HTTP 認証方式によって使用されるレルムを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="2746f-126">A string that specifies the realm that is used by the HTTP authentication scheme for digest or basic authentication.</span></span> <span data-ttu-id="2746f-127">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="2746f-127">The default is an empty string.</span></span>|  
|<span data-ttu-id="2746f-128">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="2746f-128">policyEnforcement</span></span>|<span data-ttu-id="2746f-129">この列挙体は、<xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> を適用するタイミングを指定します。</span><span class="sxs-lookup"><span data-stu-id="2746f-129">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="2746f-130">1. Never – ポリシーが適用されることはありません (拡張保護は無効になります)。</span><span class="sxs-lookup"><span data-stu-id="2746f-130">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="2746f-131">2. WhenSupported – ポリシーが適用されるのは、クライアントが拡張保護をサポートしている場合のみです。</span><span class="sxs-lookup"><span data-stu-id="2746f-131">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="2746f-132">3.Always – ポリシーは常に適用されます。</span><span class="sxs-lookup"><span data-stu-id="2746f-132">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="2746f-133">拡張保護をサポートしていないクライアントは認証に失敗します。</span><span class="sxs-lookup"><span data-stu-id="2746f-133">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
|<span data-ttu-id="2746f-134">protectionScenario</span><span class="sxs-lookup"><span data-stu-id="2746f-134">protectionScenario</span></span>|<span data-ttu-id="2746f-135">この列挙体は、ポリシーによって適用される保護シナリオを指定します。</span><span class="sxs-lookup"><span data-stu-id="2746f-135">This enumeration specifies the protection scenario enforced by the policy.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="2746f-136">clientCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="2746f-136">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="2746f-137">値</span><span class="sxs-lookup"><span data-stu-id="2746f-137">Value</span></span>|<span data-ttu-id="2746f-138">説明</span><span class="sxs-lookup"><span data-stu-id="2746f-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2746f-139">なし</span><span class="sxs-lookup"><span data-stu-id="2746f-139">None</span></span>|<span data-ttu-id="2746f-140">メッセージは、転送中はセキュリティで保護されません。</span><span class="sxs-lookup"><span data-stu-id="2746f-140">Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="2746f-141">Basic</span><span class="sxs-lookup"><span data-stu-id="2746f-141">Basic</span></span>|<span data-ttu-id="2746f-142">基本認証を指定します。</span><span class="sxs-lookup"><span data-stu-id="2746f-142">Specifies basic authentication.</span></span>|  
|<span data-ttu-id="2746f-143">Digest</span><span class="sxs-lookup"><span data-stu-id="2746f-143">Digest</span></span>|<span data-ttu-id="2746f-144">ダイジェスト認証を指定します。</span><span class="sxs-lookup"><span data-stu-id="2746f-144">Specifies digest authentication.</span></span>|  
|<span data-ttu-id="2746f-145">Ntlm</span><span class="sxs-lookup"><span data-stu-id="2746f-145">Ntlm</span></span>|<span data-ttu-id="2746f-146">Windows 認証に失敗した場合で可能な場合は、NTLM 認証を指定します。</span><span class="sxs-lookup"><span data-stu-id="2746f-146">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="2746f-147">Windows</span><span class="sxs-lookup"><span data-stu-id="2746f-147">Windows</span></span>|<span data-ttu-id="2746f-148">Windows 統合認証を指定します。</span><span class="sxs-lookup"><span data-stu-id="2746f-148">Specifies Windows integrated authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="2746f-149">proxyCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="2746f-149">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="2746f-150">値</span><span class="sxs-lookup"><span data-stu-id="2746f-150">Value</span></span>|<span data-ttu-id="2746f-151">説明</span><span class="sxs-lookup"><span data-stu-id="2746f-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2746f-152">なし</span><span class="sxs-lookup"><span data-stu-id="2746f-152">None</span></span>|<span data-ttu-id="2746f-153">-メッセージは、転送中にセキュリティ保護されません。</span><span class="sxs-lookup"><span data-stu-id="2746f-153">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="2746f-154">Basic</span><span class="sxs-lookup"><span data-stu-id="2746f-154">Basic</span></span>|<span data-ttu-id="2746f-155">RFC 2617 – HTTP 認証による定義に従った基本認証を指定します。基本認証とダイジェスト認証。</span><span class="sxs-lookup"><span data-stu-id="2746f-155">Specifies basic authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="2746f-156">Digest</span><span class="sxs-lookup"><span data-stu-id="2746f-156">Digest</span></span>|<span data-ttu-id="2746f-157">RFC 2617 – HTTP 認証で定義されているダイジェスト認証を指定します。基本認証とダイジェスト認証。</span><span class="sxs-lookup"><span data-stu-id="2746f-157">Specifies digest authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="2746f-158">Ntlm</span><span class="sxs-lookup"><span data-stu-id="2746f-158">Ntlm</span></span>|<span data-ttu-id="2746f-159">Windows 認証に失敗した場合で可能な場合は、NTLM 認証を指定します。</span><span class="sxs-lookup"><span data-stu-id="2746f-159">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="2746f-160">Windows</span><span class="sxs-lookup"><span data-stu-id="2746f-160">Windows</span></span>|<span data-ttu-id="2746f-161">Windows 統合認証を指定します。</span><span class="sxs-lookup"><span data-stu-id="2746f-161">Specifies Windows integrated authentication.</span></span>|  
|<span data-ttu-id="2746f-162">証明書</span><span class="sxs-lookup"><span data-stu-id="2746f-162">Certificate</span></span>|<span data-ttu-id="2746f-163">証明書を使用したクライアント認証を実行します。</span><span class="sxs-lookup"><span data-stu-id="2746f-163">Performs client authentication using a certificate.</span></span> <span data-ttu-id="2746f-164">このオプションは、親要素の `Mode` の `security` 属性が Transport に設定されている場合のみ機能し、TransportCredentialOnly に設定されている場合は機能しません。</span><span class="sxs-lookup"><span data-stu-id="2746f-164">This option works only if the `Mode` attribute of the parent `security` element is set to Transport, and will not work if it is set to TransportCredentialOnly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2746f-165">子要素</span><span class="sxs-lookup"><span data-stu-id="2746f-165">Child Elements</span></span>  
 <span data-ttu-id="2746f-166">なし</span><span class="sxs-lookup"><span data-stu-id="2746f-166">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2746f-167">親要素</span><span class="sxs-lookup"><span data-stu-id="2746f-167">Parent Elements</span></span>  
  
|<span data-ttu-id="2746f-168">要素</span><span class="sxs-lookup"><span data-stu-id="2746f-168">Element</span></span>|<span data-ttu-id="2746f-169">説明</span><span class="sxs-lookup"><span data-stu-id="2746f-169">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2746f-170">\<security></span><span class="sxs-lookup"><span data-stu-id="2746f-170">\<security></span></span>](security-of-nethttpbinding.md)|<span data-ttu-id="2746f-171">[ \<NetHttpBinding >](nethttpbinding.md)のセキュリティ機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="2746f-171">Defines the security capabilities for the [\<netHttpBinding>](nethttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2746f-172">例</span><span class="sxs-lookup"><span data-stu-id="2746f-172">Example</span></span>  
 <span data-ttu-id="2746f-173">基本的なバインディングを使用した SSL トランスポート セキュリティの使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2746f-173">The following example demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="2746f-174">既定で、基本的なバインディングは HTTP 通信をサポートします。</span><span class="sxs-lookup"><span data-stu-id="2746f-174">By default, the basic binding supports HTTP communication.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2746f-175">関連項目</span><span class="sxs-lookup"><span data-stu-id="2746f-175">See also</span></span>

- <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- <xref:System.ServiceModel.HttpTransportSecurity>
- [<span data-ttu-id="2746f-176">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="2746f-176">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="2746f-177">バインディング</span><span class="sxs-lookup"><span data-stu-id="2746f-177">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="2746f-178">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="2746f-178">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="2746f-179">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="2746f-179">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="2746f-180">\<binding></span><span class="sxs-lookup"><span data-stu-id="2746f-180">\<binding></span></span>](../../../misc/binding.md)
