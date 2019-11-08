---
title: <transport> の <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: f150fb19-7de1-44af-81f4-86cad881cd05
ms.openlocfilehash: e8016eb9058f132722587368f1f8c7c03220af4a
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73732791"
---
# <a name="transport-of-webhttpbinding"></a><span data-ttu-id="4a359-102">\<webHttpBinding > の \<トランスポート ></span><span class="sxs-lookup"><span data-stu-id="4a359-102">\<transport> of \<webHttpBinding></span></span>
<span data-ttu-id="4a359-103">HTTP 要求を受信するように構成されたサービス エンドポイントのトランスポート レベルのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="4a359-103">Defines the transport-level security settings for a service endpoint configured to receive HTTP requests.</span></span>  
  
<span data-ttu-id="4a359-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4a359-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4a359-105">&nbsp; &nbsp;[ **\<system >** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="4a359-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="4a359-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**バインド**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="4a359-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="4a359-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<webHttpBinding >** ](webhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="4a359-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<webHttpBinding>**](webhttpbinding.md)</span></span>\
<span data-ttu-id="4a359-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**バインド >** </span><span class="sxs-lookup"><span data-stu-id="4a359-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="4a359-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**セキュリティ >** ](security-of-webhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="4a359-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-webhttpbinding.md)</span></span>\
<span data-ttu-id="4a359-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**トランスポート >**</span><span class="sxs-lookup"><span data-stu-id="4a359-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a359-111">構文</span><span class="sxs-lookup"><span data-stu-id="4a359-111">Syntax</span></span>  
  
```xml  
<webHttpBinding>
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
</webHttpBinding>
```  
  
## <a name="type"></a><span data-ttu-id="4a359-112">[種類]</span><span class="sxs-lookup"><span data-stu-id="4a359-112">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4a359-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4a359-113">Attributes and Elements</span></span>  
 <span data-ttu-id="4a359-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4a359-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4a359-115">属性</span><span class="sxs-lookup"><span data-stu-id="4a359-115">Attributes</span></span>  
  
|<span data-ttu-id="4a359-116">属性</span><span class="sxs-lookup"><span data-stu-id="4a359-116">Attribute</span></span>|<span data-ttu-id="4a359-117">説明</span><span class="sxs-lookup"><span data-stu-id="4a359-117">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="4a359-118">サービスに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="4a359-118">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="4a359-119">この属性は <xref:System.ServiceModel.HttpClientCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="4a359-119">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="4a359-120">ドメイン プロキシに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="4a359-120">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="4a359-121">この属性は <xref:System.ServiceModel.HttpProxyCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="4a359-121">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="4a359-122">ダイジェストまたは基本認証の認証レルムを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="4a359-122">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="4a359-123">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="4a359-123">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="4a359-124">認証レルムでは、少なくとも、認証を実行するホストの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="4a359-124">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="4a359-125">アクセス権のあるユーザーのコレクションも指定できます。</span><span class="sxs-lookup"><span data-stu-id="4a359-125">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="4a359-126">ユーザーは、認証レルムを照会して、複数のユーザー名およびパスワードの候補のうち、どれを使用できるかを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="4a359-126">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|  
|`policyEnforcement`|<span data-ttu-id="4a359-127">この列挙体は、<xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> を適用するタイミングを指定します。</span><span class="sxs-lookup"><span data-stu-id="4a359-127">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="4a359-128">1. never –ポリシーは適用されません (拡張保護は無効になります)。</span><span class="sxs-lookup"><span data-stu-id="4a359-128">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="4a359-129">2. WhenSupported –ポリシーは、クライアントが拡張保護をサポートしている場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="4a359-129">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="4a359-130">3. always –ポリシーは常に適用されます。</span><span class="sxs-lookup"><span data-stu-id="4a359-130">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="4a359-131">拡張保護をサポートしていないクライアントは認証に失敗します。</span><span class="sxs-lookup"><span data-stu-id="4a359-131">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="4a359-132">clientCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="4a359-132">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="4a359-133">[値]</span><span class="sxs-lookup"><span data-stu-id="4a359-133">Value</span></span>|<span data-ttu-id="4a359-134">説明</span><span class="sxs-lookup"><span data-stu-id="4a359-134">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="4a359-135">セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="4a359-135">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="4a359-136">基本認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="4a359-136">Uses basic authentication.</span></span>|  
|`Certificate`|<span data-ttu-id="4a359-137">X.509 証明書を使用して、クライアントを認証します。</span><span class="sxs-lookup"><span data-stu-id="4a359-137">Uses X.509 certificates to authenticate the client.</span></span>|  
|`Digest`|<span data-ttu-id="4a359-138">ダイジェスト認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="4a359-138">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="4a359-139">Windows ドメインのフォールバックとして NTLM 認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="4a359-139">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="4a359-140">統合 Windows 認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="4a359-140">Uses integrated Windows authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="4a359-141">proxyCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="4a359-141">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="4a359-142">[値]</span><span class="sxs-lookup"><span data-stu-id="4a359-142">Value</span></span>|<span data-ttu-id="4a359-143">説明</span><span class="sxs-lookup"><span data-stu-id="4a359-143">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="4a359-144">セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="4a359-144">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="4a359-145">基本認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="4a359-145">Uses basic authentication.</span></span>|  
|`Digest`|<span data-ttu-id="4a359-146">ダイジェスト認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="4a359-146">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="4a359-147">Windows ドメインのフォールバックとして NTLM を使用します。</span><span class="sxs-lookup"><span data-stu-id="4a359-147">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="4a359-148">統合 Windows 認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="4a359-148">Uses integrated Windows authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4a359-149">子要素</span><span class="sxs-lookup"><span data-stu-id="4a359-149">Child Elements</span></span>  
 <span data-ttu-id="4a359-150">なし。</span><span class="sxs-lookup"><span data-stu-id="4a359-150">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4a359-151">親要素</span><span class="sxs-lookup"><span data-stu-id="4a359-151">Parent Elements</span></span>  
  
|<span data-ttu-id="4a359-152">要素</span><span class="sxs-lookup"><span data-stu-id="4a359-152">Element</span></span>|<span data-ttu-id="4a359-153">説明</span><span class="sxs-lookup"><span data-stu-id="4a359-153">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4a359-154">\< セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="4a359-154">\<security></span></span>](security-of-webhttpbinding.md)|<span data-ttu-id="4a359-155">[\<wsHttpBinding >](wshttpbinding.md)要素のセキュリティ機能を表します。</span><span class="sxs-lookup"><span data-stu-id="4a359-155">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4a359-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="4a359-156">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.WebHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WebHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [<span data-ttu-id="4a359-157">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="4a359-157">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="4a359-158">バインディング</span><span class="sxs-lookup"><span data-stu-id="4a359-158">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="4a359-159">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="4a359-159">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="4a359-160">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="4a359-160">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="4a359-161">\<binding ></span><span class="sxs-lookup"><span data-stu-id="4a359-161">\<binding></span></span>](bindings.md)
- [<span data-ttu-id="4a359-162">WCF Web HTTP プログラミング モデル</span><span class="sxs-lookup"><span data-stu-id="4a359-162">WCF Web HTTP Programming Model</span></span>](../../../wcf/feature-details/wcf-web-http-programming-model.md)
