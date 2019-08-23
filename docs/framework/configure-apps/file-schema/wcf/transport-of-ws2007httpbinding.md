---
title: <transport> の <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
ms.openlocfilehash: ce8b2acb7d87b094958e20ca0b6cca9fc8266a8d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69911989"
---
# <a name="transport-of-ws2007httpbinding"></a><span data-ttu-id="acd30-102">\<ws2007HttpBinding の\<トランスポート > ></span><span class="sxs-lookup"><span data-stu-id="acd30-102">\<transport> of \<ws2007HttpBinding></span></span>
<span data-ttu-id="acd30-103">HTTP トランスポートの認証設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="acd30-103">Defines authentication settings for the HTTP transport.</span></span>  
  
 <span data-ttu-id="acd30-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="acd30-104">\<system.serviceModel></span></span>  
<span data-ttu-id="acd30-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="acd30-105">\<bindings></span></span>  
<span data-ttu-id="acd30-106">\<ws2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="acd30-106">\<ws2007HttpBinding></span></span>  
<span data-ttu-id="acd30-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="acd30-107">\<binding></span></span>  
<span data-ttu-id="acd30-108">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="acd30-108">\<security></span></span>  
<span data-ttu-id="acd30-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="acd30-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acd30-110">構文</span><span class="sxs-lookup"><span data-stu-id="acd30-110">Syntax</span></span>  
  
```xml  
<transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
           proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
           realm="string" />
```  
  
## <a name="type"></a><span data-ttu-id="acd30-111">型</span><span class="sxs-lookup"><span data-stu-id="acd30-111">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="acd30-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="acd30-112">Attributes and Elements</span></span>  
 <span data-ttu-id="acd30-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="acd30-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="acd30-114">属性</span><span class="sxs-lookup"><span data-stu-id="acd30-114">Attributes</span></span>  
  
|<span data-ttu-id="acd30-115">属性</span><span class="sxs-lookup"><span data-stu-id="acd30-115">Attribute</span></span>|<span data-ttu-id="acd30-116">説明</span><span class="sxs-lookup"><span data-stu-id="acd30-116">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="acd30-117">サービスに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="acd30-117">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="acd30-118">この属性は <xref:System.ServiceModel.HttpClientCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="acd30-118">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="acd30-119">ドメイン プロキシに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="acd30-119">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="acd30-120">この属性は <xref:System.ServiceModel.HttpProxyCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="acd30-120">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="acd30-121">ダイジェスト認証または基本認証の認証レルム。</span><span class="sxs-lookup"><span data-stu-id="acd30-121">The authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="acd30-122">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="acd30-122">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="acd30-123">認証レルムでは、少なくとも、認証を実行するホストの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="acd30-123">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="acd30-124">アクセス権のあるユーザーのコレクションも指定できます。</span><span class="sxs-lookup"><span data-stu-id="acd30-124">It can also specify a collection of users who have access.</span></span> <span data-ttu-id="acd30-125">ユーザーは、認証レルムを照会して、複数のユーザー名とパスワードの候補のうち、どれを使用できるかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="acd30-125">A user can query the authentication realm to determine which one of the several possible usernames and passwords can be used.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="acd30-126">clientCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="acd30-126">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="acd30-127">値</span><span class="sxs-lookup"><span data-stu-id="acd30-127">Value</span></span>|<span data-ttu-id="acd30-128">説明</span><span class="sxs-lookup"><span data-stu-id="acd30-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="acd30-129">なし</span><span class="sxs-lookup"><span data-stu-id="acd30-129">None</span></span>|<span data-ttu-id="acd30-130">セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="acd30-130">Security is disabled.</span></span>|  
|<span data-ttu-id="acd30-131">Basic</span><span class="sxs-lookup"><span data-stu-id="acd30-131">Basic</span></span>|<span data-ttu-id="acd30-132">基本認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="acd30-132">Uses basic authentication.</span></span>|  
|<span data-ttu-id="acd30-133">Digest</span><span class="sxs-lookup"><span data-stu-id="acd30-133">Digest</span></span>|<span data-ttu-id="acd30-134">ダイジェスト認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="acd30-134">Uses digest authentication.</span></span>|  
|<span data-ttu-id="acd30-135">Ntlm</span><span class="sxs-lookup"><span data-stu-id="acd30-135">Ntlm</span></span>|<span data-ttu-id="acd30-136">Windows ドメインのフォールバックとして NTLM 認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="acd30-136">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="acd30-137">Windows</span><span class="sxs-lookup"><span data-stu-id="acd30-137">Windows</span></span>|<span data-ttu-id="acd30-138">統合 Windows 認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="acd30-138">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="acd30-139">証明書</span><span class="sxs-lookup"><span data-stu-id="acd30-139">Certificate</span></span>|<span data-ttu-id="acd30-140">X.509 証明書を使用して、クライアントを認証します。</span><span class="sxs-lookup"><span data-stu-id="acd30-140">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="acd30-141">proxyCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="acd30-141">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="acd30-142">値</span><span class="sxs-lookup"><span data-stu-id="acd30-142">Value</span></span>|<span data-ttu-id="acd30-143">説明</span><span class="sxs-lookup"><span data-stu-id="acd30-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="acd30-144">なし</span><span class="sxs-lookup"><span data-stu-id="acd30-144">None</span></span>|<span data-ttu-id="acd30-145">セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="acd30-145">Security is disabled.</span></span>|  
|<span data-ttu-id="acd30-146">Basic</span><span class="sxs-lookup"><span data-stu-id="acd30-146">Basic</span></span>|<span data-ttu-id="acd30-147">基本認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="acd30-147">Uses basic authentication.</span></span>|  
|<span data-ttu-id="acd30-148">Digest</span><span class="sxs-lookup"><span data-stu-id="acd30-148">Digest</span></span>|<span data-ttu-id="acd30-149">ダイジェスト認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="acd30-149">Uses digest authentication.</span></span>|  
|<span data-ttu-id="acd30-150">Ntlm</span><span class="sxs-lookup"><span data-stu-id="acd30-150">Ntlm</span></span>|<span data-ttu-id="acd30-151">Windows ドメインのフォールバックとして NTLM を使用します。</span><span class="sxs-lookup"><span data-stu-id="acd30-151">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="acd30-152">Windows</span><span class="sxs-lookup"><span data-stu-id="acd30-152">Windows</span></span>|<span data-ttu-id="acd30-153">統合 Windows 認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="acd30-153">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="acd30-154">証明書</span><span class="sxs-lookup"><span data-stu-id="acd30-154">Certificate</span></span>|<span data-ttu-id="acd30-155">X.509 証明書を使用して、クライアントを認証します。</span><span class="sxs-lookup"><span data-stu-id="acd30-155">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="acd30-156">子要素</span><span class="sxs-lookup"><span data-stu-id="acd30-156">Child Elements</span></span>  
 <span data-ttu-id="acd30-157">なし</span><span class="sxs-lookup"><span data-stu-id="acd30-157">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="acd30-158">親要素</span><span class="sxs-lookup"><span data-stu-id="acd30-158">Parent Elements</span></span>  
  
|<span data-ttu-id="acd30-159">要素</span><span class="sxs-lookup"><span data-stu-id="acd30-159">Element</span></span>|<span data-ttu-id="acd30-160">説明</span><span class="sxs-lookup"><span data-stu-id="acd30-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="acd30-161">\<security></span><span class="sxs-lookup"><span data-stu-id="acd30-161">\<security></span></span>](security-of-ws2007httpbinding.md)|<span data-ttu-id="acd30-162">Ws2007HttpBinding > 要素の[ \<](ws2007httpbinding.md)セキュリティ機能を表します。</span><span class="sxs-lookup"><span data-stu-id="acd30-162">Represents the security capabilities of the [\<ws2007HttpBinding>](ws2007httpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="acd30-163">関連項目</span><span class="sxs-lookup"><span data-stu-id="acd30-163">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>
- [<span data-ttu-id="acd30-164">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="acd30-164">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="acd30-165">バインディング</span><span class="sxs-lookup"><span data-stu-id="acd30-165">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="acd30-166">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="acd30-166">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="acd30-167">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="acd30-167">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="acd30-168">\<binding></span><span class="sxs-lookup"><span data-stu-id="acd30-168">\<binding></span></span>](../../../misc/binding.md)
