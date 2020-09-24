---
title: <transport> の <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: f150fb19-7de1-44af-81f4-86cad881cd05
ms.openlocfilehash: b9efc732832a8862373b14f657796a59fb52c1a1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91162115"
---
# <a name="transport-of-webhttpbinding"></a><span data-ttu-id="99cce-102">\<transport> の \<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="99cce-102">\<transport> of \<webHttpBinding></span></span>

<span data-ttu-id="99cce-103">HTTP 要求を受信するように構成されたサービス エンドポイントのトランスポート レベルのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="99cce-103">Defines the transport-level security settings for a service endpoint configured to receive HTTP requests.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<webHttpBinding>**](webhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-webhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="99cce-104">構文</span><span class="sxs-lookup"><span data-stu-id="99cce-104">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="99cce-105">種類</span><span class="sxs-lookup"><span data-stu-id="99cce-105">Type</span></span>  

 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99cce-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="99cce-106">Attributes and Elements</span></span>  

 <span data-ttu-id="99cce-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="99cce-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99cce-108">属性</span><span class="sxs-lookup"><span data-stu-id="99cce-108">Attributes</span></span>  
  
|<span data-ttu-id="99cce-109">属性</span><span class="sxs-lookup"><span data-stu-id="99cce-109">Attribute</span></span>|<span data-ttu-id="99cce-110">[説明]</span><span class="sxs-lookup"><span data-stu-id="99cce-110">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="99cce-111">サービスに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="99cce-111">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="99cce-112">この属性は <xref:System.ServiceModel.HttpClientCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="99cce-112">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="99cce-113">ドメイン プロキシに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="99cce-113">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="99cce-114">この属性は <xref:System.ServiceModel.HttpProxyCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="99cce-114">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="99cce-115">ダイジェストまたは基本認証の認証レルムを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="99cce-115">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="99cce-116">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="99cce-116">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="99cce-117">認証レルムでは、少なくとも、認証を実行するホストの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="99cce-117">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="99cce-118">アクセス権のあるユーザーのコレクションも指定できます。</span><span class="sxs-lookup"><span data-stu-id="99cce-118">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="99cce-119">ユーザーは、認証レルムを照会して、複数のユーザー名およびパスワードの候補のうち、どれを使用できるかを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="99cce-119">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|  
|`policyEnforcement`|<span data-ttu-id="99cce-120">この列挙体は、<xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> を適用するタイミングを指定します。</span><span class="sxs-lookup"><span data-stu-id="99cce-120">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="99cce-121">1. never –ポリシーは適用されません (拡張保護は無効になります)。</span><span class="sxs-lookup"><span data-stu-id="99cce-121">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="99cce-122">2. WhenSupported –ポリシーは、クライアントが拡張保護をサポートしている場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="99cce-122">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="99cce-123">3. always –ポリシーは常に適用されます。</span><span class="sxs-lookup"><span data-stu-id="99cce-123">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="99cce-124">拡張保護をサポートしていないクライアントは認証に失敗します。</span><span class="sxs-lookup"><span data-stu-id="99cce-124">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="99cce-125">clientCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="99cce-125">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="99cce-126">値</span><span class="sxs-lookup"><span data-stu-id="99cce-126">Value</span></span>|<span data-ttu-id="99cce-127">[説明]</span><span class="sxs-lookup"><span data-stu-id="99cce-127">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="99cce-128">セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="99cce-128">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="99cce-129">基本認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="99cce-129">Uses basic authentication.</span></span>|  
|`Certificate`|<span data-ttu-id="99cce-130">X.509 証明書を使用して、クライアントを認証します。</span><span class="sxs-lookup"><span data-stu-id="99cce-130">Uses X.509 certificates to authenticate the client.</span></span>|  
|`Digest`|<span data-ttu-id="99cce-131">ダイジェスト認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="99cce-131">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="99cce-132">Windows ドメインのフォールバックとして NTLM 認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="99cce-132">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="99cce-133">統合 Windows 認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="99cce-133">Uses integrated Windows authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="99cce-134">proxyCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="99cce-134">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="99cce-135">値</span><span class="sxs-lookup"><span data-stu-id="99cce-135">Value</span></span>|<span data-ttu-id="99cce-136">[説明]</span><span class="sxs-lookup"><span data-stu-id="99cce-136">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="99cce-137">セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="99cce-137">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="99cce-138">基本認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="99cce-138">Uses basic authentication.</span></span>|  
|`Digest`|<span data-ttu-id="99cce-139">ダイジェスト認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="99cce-139">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="99cce-140">Windows ドメインのフォールバックとして NTLM を使用します。</span><span class="sxs-lookup"><span data-stu-id="99cce-140">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="99cce-141">統合 Windows 認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="99cce-141">Uses integrated Windows authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="99cce-142">子要素</span><span class="sxs-lookup"><span data-stu-id="99cce-142">Child Elements</span></span>  

 <span data-ttu-id="99cce-143">なし。</span><span class="sxs-lookup"><span data-stu-id="99cce-143">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="99cce-144">親要素</span><span class="sxs-lookup"><span data-stu-id="99cce-144">Parent Elements</span></span>  
  
|<span data-ttu-id="99cce-145">要素</span><span class="sxs-lookup"><span data-stu-id="99cce-145">Element</span></span>|<span data-ttu-id="99cce-146">説明</span><span class="sxs-lookup"><span data-stu-id="99cce-146">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-webhttpbinding.md)|<span data-ttu-id="99cce-147">要素のセキュリティ機能を表し [\<wsHttpBinding>](wshttpbinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="99cce-147">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="99cce-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="99cce-148">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.WebHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WebHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [<span data-ttu-id="99cce-149">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="99cce-149">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="99cce-150">バインド</span><span class="sxs-lookup"><span data-stu-id="99cce-150">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="99cce-151">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="99cce-151">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="99cce-152">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="99cce-152">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- [<span data-ttu-id="99cce-153">WCF Web HTTP プログラミング モデル</span><span class="sxs-lookup"><span data-stu-id="99cce-153">WCF Web HTTP Programming Model</span></span>](../../../wcf/feature-details/wcf-web-http-programming-model.md)
