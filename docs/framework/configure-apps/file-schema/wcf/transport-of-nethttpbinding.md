---
title: <transport> の <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: 3b180006-1661-43bf-a699-96fd3da469af
ms.openlocfilehash: b975015a9c9a0af53117900c45d917ce1c1a53e9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "73732814"
---
# <a name="transport-of-nethttpbinding"></a><span data-ttu-id="e1f50-102">\<transport> の \<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="e1f50-102">\<transport> of \<netHttpBinding></span></span>
<span data-ttu-id="e1f50-103">HTTP トランスポートの認証パラメーターを制御するプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="e1f50-103">Defines properties that control authentication parameters for the HTTP transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="e1f50-104">構文</span><span class="sxs-lookup"><span data-stu-id="e1f50-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e1f50-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e1f50-105">Attributes and Elements</span></span>  
 <span data-ttu-id="e1f50-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e1f50-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e1f50-107">属性</span><span class="sxs-lookup"><span data-stu-id="e1f50-107">Attributes</span></span>  
  
|<span data-ttu-id="e1f50-108">属性</span><span class="sxs-lookup"><span data-stu-id="e1f50-108">Attribute</span></span>|<span data-ttu-id="e1f50-109">説明</span><span class="sxs-lookup"><span data-stu-id="e1f50-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e1f50-110">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="e1f50-110">clientCredentialType</span></span>|<span data-ttu-id="e1f50-111">-HTTP 認証を使用してクライアント認証を実行するときに使用される資格情報の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="e1f50-111">-   Specifies the type of credential to be used when performing client authentication using HTTP authentication.</span></span>  <span data-ttu-id="e1f50-112">既定値は、`None` です。</span><span class="sxs-lookup"><span data-stu-id="e1f50-112">The default is `None`.</span></span> <span data-ttu-id="e1f50-113">この属性は <xref:System.ServiceModel.HttpClientCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="e1f50-113">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|<span data-ttu-id="e1f50-114">proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="e1f50-114">proxyCredentialType</span></span>|<span data-ttu-id="e1f50-115">-HTTP 経由のプロキシを使用してドメイン内からクライアント認証を実行するときに使用される資格情報の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="e1f50-115">-   Specifies the type of credential to be used when performing client authentication from within a domain using a proxy over HTTP.</span></span> <span data-ttu-id="e1f50-116">この属性は、親 `mode` 要素の `security` 属性が `Transport` または `TransportCredentialsOnly` の場合にだけ適用されます。</span><span class="sxs-lookup"><span data-stu-id="e1f50-116">This attribute is applicable only when the `mode` attribute of the parent `security` element is `Transport` or `TransportCredentialsOnly`.</span></span> <span data-ttu-id="e1f50-117">この属性は <xref:System.ServiceModel.HttpProxyCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="e1f50-117">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|<span data-ttu-id="e1f50-118">realm</span><span class="sxs-lookup"><span data-stu-id="e1f50-118">realm</span></span>|<span data-ttu-id="e1f50-119">ダイジェストまたは基本認証の HTTP 認証方式によって使用されるレルムを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="e1f50-119">A string that specifies the realm that is used by the HTTP authentication scheme for digest or basic authentication.</span></span> <span data-ttu-id="e1f50-120">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="e1f50-120">The default is an empty string.</span></span>|  
|<span data-ttu-id="e1f50-121">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="e1f50-121">policyEnforcement</span></span>|<span data-ttu-id="e1f50-122">この列挙体は、<xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> を適用するタイミングを指定します。</span><span class="sxs-lookup"><span data-stu-id="e1f50-122">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="e1f50-123">1. never –ポリシーは適用されません (拡張保護は無効になります)。</span><span class="sxs-lookup"><span data-stu-id="e1f50-123">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="e1f50-124">2. WhenSupported –ポリシーは、クライアントが拡張保護をサポートしている場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="e1f50-124">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="e1f50-125">3. always –ポリシーは常に適用されます。</span><span class="sxs-lookup"><span data-stu-id="e1f50-125">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="e1f50-126">拡張保護をサポートしていないクライアントは認証に失敗します。</span><span class="sxs-lookup"><span data-stu-id="e1f50-126">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
|<span data-ttu-id="e1f50-127">protectionScenario</span><span class="sxs-lookup"><span data-stu-id="e1f50-127">protectionScenario</span></span>|<span data-ttu-id="e1f50-128">この列挙体は、ポリシーによって適用される保護シナリオを指定します。</span><span class="sxs-lookup"><span data-stu-id="e1f50-128">This enumeration specifies the protection scenario enforced by the policy.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="e1f50-129">clientCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="e1f50-129">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="e1f50-130">値</span><span class="sxs-lookup"><span data-stu-id="e1f50-130">Value</span></span>|<span data-ttu-id="e1f50-131">説明</span><span class="sxs-lookup"><span data-stu-id="e1f50-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e1f50-132">なし</span><span class="sxs-lookup"><span data-stu-id="e1f50-132">None</span></span>|<span data-ttu-id="e1f50-133">メッセージは、転送中はセキュリティで保護されません。</span><span class="sxs-lookup"><span data-stu-id="e1f50-133">Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="e1f50-134">Basic</span><span class="sxs-lookup"><span data-stu-id="e1f50-134">Basic</span></span>|<span data-ttu-id="e1f50-135">基本認証を指定します。</span><span class="sxs-lookup"><span data-stu-id="e1f50-135">Specifies basic authentication.</span></span>|  
|<span data-ttu-id="e1f50-136">ダイジェスト</span><span class="sxs-lookup"><span data-stu-id="e1f50-136">Digest</span></span>|<span data-ttu-id="e1f50-137">ダイジェスト認証を指定します。</span><span class="sxs-lookup"><span data-stu-id="e1f50-137">Specifies digest authentication.</span></span>|  
|<span data-ttu-id="e1f50-138">Ntlm</span><span class="sxs-lookup"><span data-stu-id="e1f50-138">Ntlm</span></span>|<span data-ttu-id="e1f50-139">Windows 認証に失敗した場合で可能な場合は、NTLM 認証を指定します。</span><span class="sxs-lookup"><span data-stu-id="e1f50-139">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="e1f50-140">Windows</span><span class="sxs-lookup"><span data-stu-id="e1f50-140">Windows</span></span>|<span data-ttu-id="e1f50-141">Windows 統合認証を指定します。</span><span class="sxs-lookup"><span data-stu-id="e1f50-141">Specifies Windows integrated authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="e1f50-142">proxyCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="e1f50-142">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="e1f50-143">値</span><span class="sxs-lookup"><span data-stu-id="e1f50-143">Value</span></span>|<span data-ttu-id="e1f50-144">説明</span><span class="sxs-lookup"><span data-stu-id="e1f50-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e1f50-145">なし</span><span class="sxs-lookup"><span data-stu-id="e1f50-145">None</span></span>|<span data-ttu-id="e1f50-146">-メッセージは、転送中にセキュリティ保護されません。</span><span class="sxs-lookup"><span data-stu-id="e1f50-146">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="e1f50-147">Basic</span><span class="sxs-lookup"><span data-stu-id="e1f50-147">Basic</span></span>|<span data-ttu-id="e1f50-148">RFC 2617 『HTTP Authentication: Basic and Digest Authentication』で定義されているとおりに基本認証を指定します。</span><span class="sxs-lookup"><span data-stu-id="e1f50-148">Specifies basic authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="e1f50-149">ダイジェスト</span><span class="sxs-lookup"><span data-stu-id="e1f50-149">Digest</span></span>|<span data-ttu-id="e1f50-150">RFC 2617 『HTTP Authentication: Basic and Digest Authentication』で定義されているとおりにダイジェスト認証を指定します。</span><span class="sxs-lookup"><span data-stu-id="e1f50-150">Specifies digest authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="e1f50-151">Ntlm</span><span class="sxs-lookup"><span data-stu-id="e1f50-151">Ntlm</span></span>|<span data-ttu-id="e1f50-152">Windows 認証に失敗した場合で可能な場合は、NTLM 認証を指定します。</span><span class="sxs-lookup"><span data-stu-id="e1f50-152">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="e1f50-153">Windows</span><span class="sxs-lookup"><span data-stu-id="e1f50-153">Windows</span></span>|<span data-ttu-id="e1f50-154">Windows 統合認証を指定します。</span><span class="sxs-lookup"><span data-stu-id="e1f50-154">Specifies Windows integrated authentication.</span></span>|  
|<span data-ttu-id="e1f50-155">Certificate</span><span class="sxs-lookup"><span data-stu-id="e1f50-155">Certificate</span></span>|<span data-ttu-id="e1f50-156">証明書を使用したクライアント認証を実行します。</span><span class="sxs-lookup"><span data-stu-id="e1f50-156">Performs client authentication using a certificate.</span></span> <span data-ttu-id="e1f50-157">このオプションは、親要素の `Mode` の `security` 属性が Transport に設定されている場合のみ機能し、TransportCredentialOnly に設定されている場合は機能しません。</span><span class="sxs-lookup"><span data-stu-id="e1f50-157">This option works only if the `Mode` attribute of the parent `security` element is set to Transport, and will not work if it is set to TransportCredentialOnly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e1f50-158">子要素</span><span class="sxs-lookup"><span data-stu-id="e1f50-158">Child Elements</span></span>  
 <span data-ttu-id="e1f50-159">なし</span><span class="sxs-lookup"><span data-stu-id="e1f50-159">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e1f50-160">親要素</span><span class="sxs-lookup"><span data-stu-id="e1f50-160">Parent Elements</span></span>  
  
|<span data-ttu-id="e1f50-161">要素</span><span class="sxs-lookup"><span data-stu-id="e1f50-161">Element</span></span>|<span data-ttu-id="e1f50-162">Description</span><span class="sxs-lookup"><span data-stu-id="e1f50-162">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-nethttpbinding.md)|<span data-ttu-id="e1f50-163">のセキュリティ機能を定義 [\<netHttpBinding>](nethttpbinding.md) します。</span><span class="sxs-lookup"><span data-stu-id="e1f50-163">Defines the security capabilities for the [\<netHttpBinding>](nethttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e1f50-164">例</span><span class="sxs-lookup"><span data-stu-id="e1f50-164">Example</span></span>  
 <span data-ttu-id="e1f50-165">基本的なバインディングを使用した SSL トランスポート セキュリティの使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e1f50-165">The following example demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="e1f50-166">既定で、基本的なバインディングは HTTP 通信をサポートします。</span><span class="sxs-lookup"><span data-stu-id="e1f50-166">By default, the basic binding supports HTTP communication.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e1f50-167">関連項目</span><span class="sxs-lookup"><span data-stu-id="e1f50-167">See also</span></span>

- <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- <xref:System.ServiceModel.HttpTransportSecurity>
- [<span data-ttu-id="e1f50-168">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="e1f50-168">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="e1f50-169">バインド</span><span class="sxs-lookup"><span data-stu-id="e1f50-169">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e1f50-170">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="e1f50-170">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e1f50-171">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="e1f50-171">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
