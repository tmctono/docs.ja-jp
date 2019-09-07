---
title: <transport> の <wsHttpBinding>
ms.date: 03/30/2017
ms.assetid: 21e38acf-450a-4bda-82b6-de305e1f7cd8
ms.openlocfilehash: 95cfa076f62f767af431ff5a0bcc2ca31b824e30
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399243"
---
# <a name="transport-of-wshttpbinding"></a><span data-ttu-id="27f87-102">\<wsHttpBinding > の\<transport ></span><span class="sxs-lookup"><span data-stu-id="27f87-102">\<transport> of \<wsHttpBinding></span></span>

<span data-ttu-id="27f87-103">HTTP トランスポートの認証設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="27f87-103">Defines authentication settings for the HTTP transport.</span></span>

<span data-ttu-id="27f87-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="27f87-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="27f87-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="27f87-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="27f87-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<バインド >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="27f87-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="27f87-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsHttpBinding >** ](wshttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="27f87-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsHttpBinding>**](wshttpbinding.md)</span></span>\
<span data-ttu-id="27f87-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<バインド >** </span><span class="sxs-lookup"><span data-stu-id="27f87-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="27f87-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<セキュリティ >** ](security-of-wshttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="27f87-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wshttpbinding.md)</span></span>\
<span data-ttu-id="27f87-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<トランスポート >**</span><span class="sxs-lookup"><span data-stu-id="27f87-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="27f87-111">構文</span><span class="sxs-lookup"><span data-stu-id="27f87-111">Syntax</span></span>

```xml
<wsHttpBinding>
  <binding>
    <security mode="None|Transport|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="Basic|Certificate|Digest|None|Ntlm|Windows"
                 proxyCredentialType="Basic|Digest|None|Ntlm|Windows"
                 realm="string" />
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</wsHttpBinding>
```

## <a name="type"></a><span data-ttu-id="27f87-112">型</span><span class="sxs-lookup"><span data-stu-id="27f87-112">Type</span></span>

<xref:System.ServiceModel.HttpTransportSecurity>

## <a name="attributes-and-elements"></a><span data-ttu-id="27f87-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="27f87-113">Attributes and Elements</span></span>

<span data-ttu-id="27f87-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="27f87-114">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="27f87-115">属性</span><span class="sxs-lookup"><span data-stu-id="27f87-115">Attributes</span></span>

|<span data-ttu-id="27f87-116">属性</span><span class="sxs-lookup"><span data-stu-id="27f87-116">Attribute</span></span>|<span data-ttu-id="27f87-117">説明</span><span class="sxs-lookup"><span data-stu-id="27f87-117">Description</span></span>|
|---------------|-----------------|
|`clientCredentialType`|<span data-ttu-id="27f87-118">サービスに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="27f87-118">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="27f87-119">この属性は <xref:System.ServiceModel.HttpClientCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="27f87-119">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|
|`proxyCredentialType`|<span data-ttu-id="27f87-120">ドメイン プロキシに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="27f87-120">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="27f87-121">この属性は <xref:System.ServiceModel.HttpProxyCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="27f87-121">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|
|`realm`|<span data-ttu-id="27f87-122">ダイジェストまたは基本認証の認証レルムを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="27f87-122">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="27f87-123">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="27f87-123">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="27f87-124">認証レルムでは、少なくとも、認証を実行するホストの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="27f87-124">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="27f87-125">アクセス権のあるユーザーのコレクションも指定できます。</span><span class="sxs-lookup"><span data-stu-id="27f87-125">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="27f87-126">ユーザーは、認証レルムを照会して、複数のユーザー名およびパスワードの候補のうち、どれを使用できるかを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="27f87-126">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|
|`policyEnforcement`|<span data-ttu-id="27f87-127">この列挙体は、<xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> を適用するタイミングを指定します。</span><span class="sxs-lookup"><span data-stu-id="27f87-127">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="27f87-128">1. Never – ポリシーが適用されることはありません (拡張保護は無効になります)。</span><span class="sxs-lookup"><span data-stu-id="27f87-128">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="27f87-129">2. WhenSupported – ポリシーが適用されるのは、クライアントが拡張保護をサポートしている場合のみです。</span><span class="sxs-lookup"><span data-stu-id="27f87-129">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="27f87-130">3.Always – ポリシーは常に適用されます。</span><span class="sxs-lookup"><span data-stu-id="27f87-130">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="27f87-131">拡張保護をサポートしていないクライアントは認証に失敗します。</span><span class="sxs-lookup"><span data-stu-id="27f87-131">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|

## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="27f87-132">clientCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="27f87-132">clientCredentialType Attribute</span></span>

|<span data-ttu-id="27f87-133">値</span><span class="sxs-lookup"><span data-stu-id="27f87-133">Value</span></span>|<span data-ttu-id="27f87-134">説明</span><span class="sxs-lookup"><span data-stu-id="27f87-134">Description</span></span>|
|-----------|-----------------|
|`None`|<span data-ttu-id="27f87-135">セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="27f87-135">Security is disabled.</span></span>|
|`Basic`|<span data-ttu-id="27f87-136">基本認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="27f87-136">Uses basic authentication.</span></span>|
|`Digest`|<span data-ttu-id="27f87-137">ダイジェスト認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="27f87-137">Uses digest authentication.</span></span>|
|`Ntlm`|<span data-ttu-id="27f87-138">Windows ドメインのフォールバックとして NTLM 認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="27f87-138">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|
|`Windows`|<span data-ttu-id="27f87-139">統合 Windows 認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="27f87-139">Uses integrated Windows authentication.</span></span>|
|`Certificate`|<span data-ttu-id="27f87-140">X.509 証明書を使用して、クライアントを認証します。</span><span class="sxs-lookup"><span data-stu-id="27f87-140">Uses X.509 certificates to authenticate the client.</span></span>|

## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="27f87-141">proxyCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="27f87-141">proxyCredentialType Attribute</span></span>

|<span data-ttu-id="27f87-142">値</span><span class="sxs-lookup"><span data-stu-id="27f87-142">Value</span></span>|<span data-ttu-id="27f87-143">説明</span><span class="sxs-lookup"><span data-stu-id="27f87-143">Description</span></span>|
|-----------|-----------------|
|`None`|<span data-ttu-id="27f87-144">セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="27f87-144">Security is disabled.</span></span>|
|`Basic`|<span data-ttu-id="27f87-145">基本認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="27f87-145">Uses basic authentication.</span></span>|
|`Digest`|<span data-ttu-id="27f87-146">ダイジェスト認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="27f87-146">Uses digest authentication.</span></span>|
|`Ntlm`|<span data-ttu-id="27f87-147">Windows ドメインのフォールバックとして NTLM を使用します。</span><span class="sxs-lookup"><span data-stu-id="27f87-147">Uses NTLM as a fallback with a Windows domain.</span></span>|
|`Windows`|<span data-ttu-id="27f87-148">統合 Windows 認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="27f87-148">Uses integrated Windows authentication.</span></span>|
|`Certificate`|<span data-ttu-id="27f87-149">X.509 証明書を使用して、クライアントを認証します。</span><span class="sxs-lookup"><span data-stu-id="27f87-149">Uses X.509 certificates to authenticate the client.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="27f87-150">子要素</span><span class="sxs-lookup"><span data-stu-id="27f87-150">Child Elements</span></span>

<span data-ttu-id="27f87-151">なし。</span><span class="sxs-lookup"><span data-stu-id="27f87-151">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="27f87-152">親要素</span><span class="sxs-lookup"><span data-stu-id="27f87-152">Parent Elements</span></span>

|<span data-ttu-id="27f87-153">要素</span><span class="sxs-lookup"><span data-stu-id="27f87-153">Element</span></span>|<span data-ttu-id="27f87-154">説明</span><span class="sxs-lookup"><span data-stu-id="27f87-154">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="27f87-155">\<security></span><span class="sxs-lookup"><span data-stu-id="27f87-155">\<security></span></span>](security-of-wshttpbinding.md)|<span data-ttu-id="27f87-156">[ \<WsHttpBinding >](wshttpbinding.md)のセキュリティ機能を表します。</span><span class="sxs-lookup"><span data-stu-id="27f87-156">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md).</span></span>|

## <a name="see-also"></a><span data-ttu-id="27f87-157">関連項目</span><span class="sxs-lookup"><span data-stu-id="27f87-157">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [<span data-ttu-id="27f87-158">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="27f87-158">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="27f87-159">バインディング</span><span class="sxs-lookup"><span data-stu-id="27f87-159">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="27f87-160">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="27f87-160">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="27f87-161">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="27f87-161">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="27f87-162">\<binding></span><span class="sxs-lookup"><span data-stu-id="27f87-162">\<binding></span></span>](../../../misc/binding.md)
