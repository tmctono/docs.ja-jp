---
title: <transport> の <wsHttpBinding>
ms.date: 03/30/2017
ms.assetid: 21e38acf-450a-4bda-82b6-de305e1f7cd8
ms.openlocfilehash: 1afeed62fcbf3b083d69a7cedb7eb80b81f5c17b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "73732739"
---
# <a name="transport-of-wshttpbinding"></a><span data-ttu-id="de5c4-102">\<transport> の \<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="de5c4-102">\<transport> of \<wsHttpBinding></span></span>

<span data-ttu-id="de5c4-103">HTTP トランスポートの認証設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="de5c4-103">Defines authentication settings for the HTTP transport.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsHttpBinding>**](wshttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wshttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  

## <a name="syntax"></a><span data-ttu-id="de5c4-104">構文</span><span class="sxs-lookup"><span data-stu-id="de5c4-104">Syntax</span></span>

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

## <a name="type"></a><span data-ttu-id="de5c4-105">Type</span><span class="sxs-lookup"><span data-stu-id="de5c4-105">Type</span></span>

<xref:System.ServiceModel.HttpTransportSecurity>

## <a name="attributes-and-elements"></a><span data-ttu-id="de5c4-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="de5c4-106">Attributes and Elements</span></span>

<span data-ttu-id="de5c4-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="de5c4-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="de5c4-108">属性</span><span class="sxs-lookup"><span data-stu-id="de5c4-108">Attributes</span></span>

|<span data-ttu-id="de5c4-109">属性</span><span class="sxs-lookup"><span data-stu-id="de5c4-109">Attribute</span></span>|<span data-ttu-id="de5c4-110">説明</span><span class="sxs-lookup"><span data-stu-id="de5c4-110">Description</span></span>|
|---------------|-----------------|
|`clientCredentialType`|<span data-ttu-id="de5c4-111">サービスに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="de5c4-111">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="de5c4-112">この属性は <xref:System.ServiceModel.HttpClientCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="de5c4-112">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|
|`proxyCredentialType`|<span data-ttu-id="de5c4-113">ドメイン プロキシに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="de5c4-113">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="de5c4-114">この属性は <xref:System.ServiceModel.HttpProxyCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="de5c4-114">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|
|`realm`|<span data-ttu-id="de5c4-115">ダイジェストまたは基本認証の認証レルムを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="de5c4-115">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="de5c4-116">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="de5c4-116">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="de5c4-117">認証レルムでは、少なくとも、認証を実行するホストの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="de5c4-117">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="de5c4-118">アクセス権のあるユーザーのコレクションも指定できます。</span><span class="sxs-lookup"><span data-stu-id="de5c4-118">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="de5c4-119">ユーザーは、認証レルムを照会して、複数のユーザー名およびパスワードの候補のうち、どれを使用できるかを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="de5c4-119">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|
|`policyEnforcement`|<span data-ttu-id="de5c4-120">この列挙体は、<xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> を適用するタイミングを指定します。</span><span class="sxs-lookup"><span data-stu-id="de5c4-120">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="de5c4-121">1. never –ポリシーは適用されません (拡張保護は無効になります)。</span><span class="sxs-lookup"><span data-stu-id="de5c4-121">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="de5c4-122">2. WhenSupported –ポリシーは、クライアントが拡張保護をサポートしている場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="de5c4-122">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="de5c4-123">3. always –ポリシーは常に適用されます。</span><span class="sxs-lookup"><span data-stu-id="de5c4-123">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="de5c4-124">拡張保護をサポートしていないクライアントは認証に失敗します。</span><span class="sxs-lookup"><span data-stu-id="de5c4-124">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|

## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="de5c4-125">clientCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="de5c4-125">clientCredentialType Attribute</span></span>

|<span data-ttu-id="de5c4-126">値</span><span class="sxs-lookup"><span data-stu-id="de5c4-126">Value</span></span>|<span data-ttu-id="de5c4-127">Description</span><span class="sxs-lookup"><span data-stu-id="de5c4-127">Description</span></span>|
|-----------|-----------------|
|`None`|<span data-ttu-id="de5c4-128">セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="de5c4-128">Security is disabled.</span></span>|
|`Basic`|<span data-ttu-id="de5c4-129">基本認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="de5c4-129">Uses basic authentication.</span></span>|
|`Digest`|<span data-ttu-id="de5c4-130">ダイジェスト認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="de5c4-130">Uses digest authentication.</span></span>|
|`Ntlm`|<span data-ttu-id="de5c4-131">Windows ドメインのフォールバックとして NTLM 認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="de5c4-131">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|
|`Windows`|<span data-ttu-id="de5c4-132">統合 Windows 認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="de5c4-132">Uses integrated Windows authentication.</span></span>|
|`Certificate`|<span data-ttu-id="de5c4-133">X.509 証明書を使用して、クライアントを認証します。</span><span class="sxs-lookup"><span data-stu-id="de5c4-133">Uses X.509 certificates to authenticate the client.</span></span>|

## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="de5c4-134">proxyCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="de5c4-134">proxyCredentialType Attribute</span></span>

|<span data-ttu-id="de5c4-135">値</span><span class="sxs-lookup"><span data-stu-id="de5c4-135">Value</span></span>|<span data-ttu-id="de5c4-136">Description</span><span class="sxs-lookup"><span data-stu-id="de5c4-136">Description</span></span>|
|-----------|-----------------|
|`None`|<span data-ttu-id="de5c4-137">セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="de5c4-137">Security is disabled.</span></span>|
|`Basic`|<span data-ttu-id="de5c4-138">基本認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="de5c4-138">Uses basic authentication.</span></span>|
|`Digest`|<span data-ttu-id="de5c4-139">ダイジェスト認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="de5c4-139">Uses digest authentication.</span></span>|
|`Ntlm`|<span data-ttu-id="de5c4-140">Windows ドメインのフォールバックとして NTLM を使用します。</span><span class="sxs-lookup"><span data-stu-id="de5c4-140">Uses NTLM as a fallback with a Windows domain.</span></span>|
|`Windows`|<span data-ttu-id="de5c4-141">統合 Windows 認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="de5c4-141">Uses integrated Windows authentication.</span></span>|
|`Certificate`|<span data-ttu-id="de5c4-142">X.509 証明書を使用して、クライアントを認証します。</span><span class="sxs-lookup"><span data-stu-id="de5c4-142">Uses X.509 certificates to authenticate the client.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="de5c4-143">子要素</span><span class="sxs-lookup"><span data-stu-id="de5c4-143">Child Elements</span></span>

<span data-ttu-id="de5c4-144">なし。</span><span class="sxs-lookup"><span data-stu-id="de5c4-144">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="de5c4-145">親要素</span><span class="sxs-lookup"><span data-stu-id="de5c4-145">Parent Elements</span></span>

|<span data-ttu-id="de5c4-146">要素</span><span class="sxs-lookup"><span data-stu-id="de5c4-146">Element</span></span>|<span data-ttu-id="de5c4-147">Description</span><span class="sxs-lookup"><span data-stu-id="de5c4-147">Description</span></span>|
|-------------|-----------------|
|[\<security>](security-of-wshttpbinding.md)|<span data-ttu-id="de5c4-148">のセキュリティ機能を表し [\<wsHttpBinding>](wshttpbinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="de5c4-148">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md).</span></span>|

## <a name="see-also"></a><span data-ttu-id="de5c4-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="de5c4-149">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [<span data-ttu-id="de5c4-150">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="de5c4-150">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="de5c4-151">バインド</span><span class="sxs-lookup"><span data-stu-id="de5c4-151">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="de5c4-152">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="de5c4-152">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="de5c4-153">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="de5c4-153">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
