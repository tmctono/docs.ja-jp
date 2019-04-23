---
title: <transport> の <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
ms.openlocfilehash: a1540b53d4af76141c1daee60a6bddbbecd9d6da
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59153869"
---
# <a name="transport-of-ws2007httpbinding"></a><span data-ttu-id="1b99e-102">\<トランスポート > の\<ws2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="1b99e-102">\<transport> of \<ws2007HttpBinding></span></span>
<span data-ttu-id="1b99e-103">HTTP トランスポートの認証設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="1b99e-103">Defines authentication settings for the HTTP transport.</span></span>  
  
 <span data-ttu-id="1b99e-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1b99e-104">\<system.serviceModel></span></span>  
<span data-ttu-id="1b99e-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="1b99e-105">\<bindings></span></span>  
<span data-ttu-id="1b99e-106">\<ws2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="1b99e-106">\<ws2007HttpBinding></span></span>  
<span data-ttu-id="1b99e-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="1b99e-107">\<binding></span></span>  
<span data-ttu-id="1b99e-108">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="1b99e-108">\<security></span></span>  
<span data-ttu-id="1b99e-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="1b99e-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b99e-110">構文</span><span class="sxs-lookup"><span data-stu-id="1b99e-110">Syntax</span></span>  
  
```xml  
<transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
           proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
           realm="string" />
```  
  
## <a name="type"></a><span data-ttu-id="1b99e-111">型</span><span class="sxs-lookup"><span data-stu-id="1b99e-111">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1b99e-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1b99e-112">Attributes and Elements</span></span>  
 <span data-ttu-id="1b99e-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1b99e-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1b99e-114">属性</span><span class="sxs-lookup"><span data-stu-id="1b99e-114">Attributes</span></span>  
  
|<span data-ttu-id="1b99e-115">属性</span><span class="sxs-lookup"><span data-stu-id="1b99e-115">Attribute</span></span>|<span data-ttu-id="1b99e-116">説明</span><span class="sxs-lookup"><span data-stu-id="1b99e-116">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="1b99e-117">サービスに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="1b99e-117">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="1b99e-118">この属性は <xref:System.ServiceModel.HttpClientCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="1b99e-118">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="1b99e-119">ドメイン プロキシに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="1b99e-119">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="1b99e-120">この属性は <xref:System.ServiceModel.HttpProxyCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="1b99e-120">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="1b99e-121">ダイジェスト認証または基本認証の認証レルム。</span><span class="sxs-lookup"><span data-stu-id="1b99e-121">The authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="1b99e-122">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="1b99e-122">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="1b99e-123">認証レルムでは、少なくとも、認証を実行するホストの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="1b99e-123">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="1b99e-124">アクセス権のあるユーザーのコレクションも指定できます。</span><span class="sxs-lookup"><span data-stu-id="1b99e-124">It can also specify a collection of users who have access.</span></span> <span data-ttu-id="1b99e-125">ユーザーは、認証レルムを照会して、複数のユーザー名とパスワードの候補のうち、どれを使用できるかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="1b99e-125">A user can query the authentication realm to determine which one of the several possible usernames and passwords can be used.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="1b99e-126">clientCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="1b99e-126">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="1b99e-127">[値]</span><span class="sxs-lookup"><span data-stu-id="1b99e-127">Value</span></span>|<span data-ttu-id="1b99e-128">説明</span><span class="sxs-lookup"><span data-stu-id="1b99e-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1b99e-129">なし</span><span class="sxs-lookup"><span data-stu-id="1b99e-129">None</span></span>|<span data-ttu-id="1b99e-130">セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="1b99e-130">Security is disabled.</span></span>|  
|<span data-ttu-id="1b99e-131">Basic</span><span class="sxs-lookup"><span data-stu-id="1b99e-131">Basic</span></span>|<span data-ttu-id="1b99e-132">基本認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="1b99e-132">Uses basic authentication.</span></span>|  
|<span data-ttu-id="1b99e-133">Digest</span><span class="sxs-lookup"><span data-stu-id="1b99e-133">Digest</span></span>|<span data-ttu-id="1b99e-134">ダイジェスト認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="1b99e-134">Uses digest authentication.</span></span>|  
|<span data-ttu-id="1b99e-135">Ntlm</span><span class="sxs-lookup"><span data-stu-id="1b99e-135">Ntlm</span></span>|<span data-ttu-id="1b99e-136">Windows ドメインのフォールバックとして NTLM 認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="1b99e-136">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="1b99e-137">Windows</span><span class="sxs-lookup"><span data-stu-id="1b99e-137">Windows</span></span>|<span data-ttu-id="1b99e-138">統合 Windows 認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="1b99e-138">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="1b99e-139">証明書</span><span class="sxs-lookup"><span data-stu-id="1b99e-139">Certificate</span></span>|<span data-ttu-id="1b99e-140">X.509 証明書を使用して、クライアントを認証します。</span><span class="sxs-lookup"><span data-stu-id="1b99e-140">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="1b99e-141">proxyCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="1b99e-141">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="1b99e-142">[値]</span><span class="sxs-lookup"><span data-stu-id="1b99e-142">Value</span></span>|<span data-ttu-id="1b99e-143">説明</span><span class="sxs-lookup"><span data-stu-id="1b99e-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1b99e-144">なし</span><span class="sxs-lookup"><span data-stu-id="1b99e-144">None</span></span>|<span data-ttu-id="1b99e-145">セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="1b99e-145">Security is disabled.</span></span>|  
|<span data-ttu-id="1b99e-146">Basic</span><span class="sxs-lookup"><span data-stu-id="1b99e-146">Basic</span></span>|<span data-ttu-id="1b99e-147">基本認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="1b99e-147">Uses basic authentication.</span></span>|  
|<span data-ttu-id="1b99e-148">Digest</span><span class="sxs-lookup"><span data-stu-id="1b99e-148">Digest</span></span>|<span data-ttu-id="1b99e-149">ダイジェスト認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="1b99e-149">Uses digest authentication.</span></span>|  
|<span data-ttu-id="1b99e-150">Ntlm</span><span class="sxs-lookup"><span data-stu-id="1b99e-150">Ntlm</span></span>|<span data-ttu-id="1b99e-151">Windows ドメインのフォールバックとして NTLM を使用します。</span><span class="sxs-lookup"><span data-stu-id="1b99e-151">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="1b99e-152">Windows</span><span class="sxs-lookup"><span data-stu-id="1b99e-152">Windows</span></span>|<span data-ttu-id="1b99e-153">統合 Windows 認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="1b99e-153">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="1b99e-154">証明書</span><span class="sxs-lookup"><span data-stu-id="1b99e-154">Certificate</span></span>|<span data-ttu-id="1b99e-155">X.509 証明書を使用して、クライアントを認証します。</span><span class="sxs-lookup"><span data-stu-id="1b99e-155">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1b99e-156">子要素</span><span class="sxs-lookup"><span data-stu-id="1b99e-156">Child Elements</span></span>  
 <span data-ttu-id="1b99e-157">なし</span><span class="sxs-lookup"><span data-stu-id="1b99e-157">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1b99e-158">親要素</span><span class="sxs-lookup"><span data-stu-id="1b99e-158">Parent Elements</span></span>  
  
|<span data-ttu-id="1b99e-159">要素</span><span class="sxs-lookup"><span data-stu-id="1b99e-159">Element</span></span>|<span data-ttu-id="1b99e-160">説明</span><span class="sxs-lookup"><span data-stu-id="1b99e-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1b99e-161">\<security></span><span class="sxs-lookup"><span data-stu-id="1b99e-161">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-ws2007httpbinding.md)|<span data-ttu-id="1b99e-162">セキュリティ機能を表す、 [ \<ws2007HttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md)要素。</span><span class="sxs-lookup"><span data-stu-id="1b99e-162">Represents the security capabilities of the [\<ws2007HttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1b99e-163">関連項目</span><span class="sxs-lookup"><span data-stu-id="1b99e-163">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>
- [<span data-ttu-id="1b99e-164">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="1b99e-164">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="1b99e-165">バインディング</span><span class="sxs-lookup"><span data-stu-id="1b99e-165">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="1b99e-166">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="1b99e-166">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="1b99e-167">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="1b99e-167">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="1b99e-168">\<binding></span><span class="sxs-lookup"><span data-stu-id="1b99e-168">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
