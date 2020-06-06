---
title: <transport> の <basicHttpBinding>
ms.date: 03/30/2017
ms.assetid: 4c5ba293-3d7e-47a6-b84e-e9022857b7e5
ms.openlocfilehash: c563339e4f854cc4e60f92dd5b8c0b39112dc000
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736124"
---
# <a name="transport-of-basichttpbinding"></a><span data-ttu-id="defe3-102">\<transport> の \<basicHttpBinding></span><span class="sxs-lookup"><span data-stu-id="defe3-102">\<transport> of \<basicHttpBinding></span></span>
<span data-ttu-id="defe3-103">HTTP トランスポートの認証パラメーターを制御するプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="defe3-103">Defines properties that control authentication parameters for the HTTP transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<basicHttpBinding>**](basichttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-basichttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="defe3-104">構文</span><span class="sxs-lookup"><span data-stu-id="defe3-104">Syntax</span></span>  
  
```xml  
<basicHttpBinding>
  <binding>
    <security mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"
                 proxyCredentialType="None|Basic|Digest|Ntlm|Windows"
                 realm="String">
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</basicHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="defe3-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="defe3-105">Attributes and Elements</span></span>  
 <span data-ttu-id="defe3-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="defe3-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="defe3-107">属性</span><span class="sxs-lookup"><span data-stu-id="defe3-107">Attributes</span></span>  
  
|<span data-ttu-id="defe3-108">属性</span><span class="sxs-lookup"><span data-stu-id="defe3-108">Attribute</span></span>|<span data-ttu-id="defe3-109">説明</span><span class="sxs-lookup"><span data-stu-id="defe3-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="defe3-110">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="defe3-110">clientCredentialType</span></span>|<span data-ttu-id="defe3-111">-HTTP 認証を使用してクライアント認証を実行するときに使用される資格情報の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="defe3-111">-   Specifies the type of credential to be used when performing client authentication using HTTP authentication.</span></span>  <span data-ttu-id="defe3-112">既定値は、`None` です。</span><span class="sxs-lookup"><span data-stu-id="defe3-112">The default is `None`.</span></span> <span data-ttu-id="defe3-113">この属性は <xref:System.ServiceModel.HttpClientCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="defe3-113">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|<span data-ttu-id="defe3-114">proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="defe3-114">proxyCredentialType</span></span>|<span data-ttu-id="defe3-115">-HTTP 経由のプロキシを使用してドメイン内からクライアント認証を実行するときに使用される資格情報の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="defe3-115">-   Specifies the type of credential to be used when performing client authentication from within a domain using a proxy over HTTP.</span></span> <span data-ttu-id="defe3-116">この属性は、親 `mode` 要素の `security` 属性が `Transport` または `TransportCredentialsOnly` の場合にだけ適用されます。</span><span class="sxs-lookup"><span data-stu-id="defe3-116">This attribute is applicable only when the `mode` attribute of the parent `security` element is `Transport` or `TransportCredentialsOnly`.</span></span> <span data-ttu-id="defe3-117">この属性は <xref:System.ServiceModel.HttpProxyCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="defe3-117">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|<span data-ttu-id="defe3-118">realm</span><span class="sxs-lookup"><span data-stu-id="defe3-118">realm</span></span>|<span data-ttu-id="defe3-119">ダイジェストまたは基本認証の HTTP 認証方式によって使用されるレルムを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="defe3-119">A string that specifies the realm that is used by the HTTP authentication scheme for digest or basic authentication.</span></span> <span data-ttu-id="defe3-120">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="defe3-120">The default is an empty string.</span></span>|  
|<span data-ttu-id="defe3-121">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="defe3-121">policyEnforcement</span></span>|<span data-ttu-id="defe3-122">この列挙体は、<xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> を適用するタイミングを指定します。</span><span class="sxs-lookup"><span data-stu-id="defe3-122">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="defe3-123">1. never –ポリシーは適用されません (拡張保護は無効になります)。</span><span class="sxs-lookup"><span data-stu-id="defe3-123">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="defe3-124">2. WhenSupported –ポリシーは、クライアントが拡張保護をサポートしている場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="defe3-124">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="defe3-125">3. always –ポリシーは常に適用されます。</span><span class="sxs-lookup"><span data-stu-id="defe3-125">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="defe3-126">拡張保護をサポートしていないクライアントは認証に失敗します。</span><span class="sxs-lookup"><span data-stu-id="defe3-126">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
|<span data-ttu-id="defe3-127">protectionScenario</span><span class="sxs-lookup"><span data-stu-id="defe3-127">protectionScenario</span></span>|<span data-ttu-id="defe3-128">この列挙体は、ポリシーによって適用される保護シナリオを指定します。</span><span class="sxs-lookup"><span data-stu-id="defe3-128">This enumeration specifies the protection scenario enforced by the policy.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="defe3-129">clientCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="defe3-129">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="defe3-130">値</span><span class="sxs-lookup"><span data-stu-id="defe3-130">Value</span></span>|<span data-ttu-id="defe3-131">説明</span><span class="sxs-lookup"><span data-stu-id="defe3-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="defe3-132">なし</span><span class="sxs-lookup"><span data-stu-id="defe3-132">None</span></span>|<span data-ttu-id="defe3-133">メッセージは、転送中はセキュリティで保護されません。</span><span class="sxs-lookup"><span data-stu-id="defe3-133">Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="defe3-134">Basic</span><span class="sxs-lookup"><span data-stu-id="defe3-134">Basic</span></span>|<span data-ttu-id="defe3-135">基本認証を指定します。</span><span class="sxs-lookup"><span data-stu-id="defe3-135">Specifies basic authentication.</span></span>|  
|<span data-ttu-id="defe3-136">ダイジェスト</span><span class="sxs-lookup"><span data-stu-id="defe3-136">Digest</span></span>|<span data-ttu-id="defe3-137">ダイジェスト認証を指定します。</span><span class="sxs-lookup"><span data-stu-id="defe3-137">Specifies digest authentication.</span></span>|  
|<span data-ttu-id="defe3-138">Ntlm</span><span class="sxs-lookup"><span data-stu-id="defe3-138">Ntlm</span></span>|<span data-ttu-id="defe3-139">Windows 認証に失敗した場合で可能な場合は、NTLM 認証を指定します。</span><span class="sxs-lookup"><span data-stu-id="defe3-139">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="defe3-140">Windows</span><span class="sxs-lookup"><span data-stu-id="defe3-140">Windows</span></span>|<span data-ttu-id="defe3-141">Windows 統合認証を指定します。</span><span class="sxs-lookup"><span data-stu-id="defe3-141">Specifies Windows integrated authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="defe3-142">proxyCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="defe3-142">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="defe3-143">値</span><span class="sxs-lookup"><span data-stu-id="defe3-143">Value</span></span>|<span data-ttu-id="defe3-144">説明</span><span class="sxs-lookup"><span data-stu-id="defe3-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="defe3-145">なし</span><span class="sxs-lookup"><span data-stu-id="defe3-145">None</span></span>|<span data-ttu-id="defe3-146">-メッセージは、転送中にセキュリティ保護されません。</span><span class="sxs-lookup"><span data-stu-id="defe3-146">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="defe3-147">Basic</span><span class="sxs-lookup"><span data-stu-id="defe3-147">Basic</span></span>|<span data-ttu-id="defe3-148">RFC 2617 『HTTP Authentication: Basic and Digest Authentication』で定義されているとおりに基本認証を指定します。</span><span class="sxs-lookup"><span data-stu-id="defe3-148">Specifies basic authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="defe3-149">ダイジェスト</span><span class="sxs-lookup"><span data-stu-id="defe3-149">Digest</span></span>|<span data-ttu-id="defe3-150">RFC 2617 『HTTP Authentication: Basic and Digest Authentication』で定義されているとおりにダイジェスト認証を指定します。</span><span class="sxs-lookup"><span data-stu-id="defe3-150">Specifies digest authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="defe3-151">Ntlm</span><span class="sxs-lookup"><span data-stu-id="defe3-151">Ntlm</span></span>|<span data-ttu-id="defe3-152">Windows 認証に失敗した場合で可能な場合は、NTLM 認証を指定します。</span><span class="sxs-lookup"><span data-stu-id="defe3-152">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="defe3-153">Windows</span><span class="sxs-lookup"><span data-stu-id="defe3-153">Windows</span></span>|<span data-ttu-id="defe3-154">Windows 統合認証を指定します。</span><span class="sxs-lookup"><span data-stu-id="defe3-154">Specifies Windows integrated authentication.</span></span>|  
|<span data-ttu-id="defe3-155">Certificate</span><span class="sxs-lookup"><span data-stu-id="defe3-155">Certificate</span></span>|<span data-ttu-id="defe3-156">証明書を使用したクライアント認証を実行します。</span><span class="sxs-lookup"><span data-stu-id="defe3-156">Performs client authentication using a certificate.</span></span> <span data-ttu-id="defe3-157">このオプションは、親要素の `Mode` の `security` 属性が Transport に設定されている場合のみ機能し、TransportCredentialOnly に設定されている場合は機能しません。</span><span class="sxs-lookup"><span data-stu-id="defe3-157">This option works only if the `Mode` attribute of the parent `security` element is set to Transport, and will not work if it is set to TransportCredentialOnly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="defe3-158">子要素</span><span class="sxs-lookup"><span data-stu-id="defe3-158">Child Elements</span></span>  
 <span data-ttu-id="defe3-159">なし</span><span class="sxs-lookup"><span data-stu-id="defe3-159">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="defe3-160">親要素</span><span class="sxs-lookup"><span data-stu-id="defe3-160">Parent Elements</span></span>  
  
|<span data-ttu-id="defe3-161">要素</span><span class="sxs-lookup"><span data-stu-id="defe3-161">Element</span></span>|<span data-ttu-id="defe3-162">Description</span><span class="sxs-lookup"><span data-stu-id="defe3-162">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-basichttpbinding.md)|<span data-ttu-id="defe3-163">のセキュリティ機能を定義 [\<basicHttpBinding>](basichttpbinding.md) します。</span><span class="sxs-lookup"><span data-stu-id="defe3-163">Defines the security capabilities for the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="defe3-164">例</span><span class="sxs-lookup"><span data-stu-id="defe3-164">Example</span></span>  
 <span data-ttu-id="defe3-165">基本的なバインディングを使用した SSL トランスポート セキュリティの使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="defe3-165">The following example demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="defe3-166">既定で、基本的なバインディングは HTTP 通信をサポートします。</span><span class="sxs-lookup"><span data-stu-id="defe3-166">By default, the basic binding supports HTTP communication.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <endpoint address=""
                binding="basicHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>
  <bindings>
    <basicHttpBinding>
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
    </basicHttpBinding>
  </bindings>
</system.serviceModel>
```  
  
## <a name="see-also"></a><span data-ttu-id="defe3-167">関連項目</span><span class="sxs-lookup"><span data-stu-id="defe3-167">See also</span></span>

- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.BasicHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- <xref:System.ServiceModel.HttpTransportSecurity>
- [<span data-ttu-id="defe3-168">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="defe3-168">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="defe3-169">バインド</span><span class="sxs-lookup"><span data-stu-id="defe3-169">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="defe3-170">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="defe3-170">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="defe3-171">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="defe3-171">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
