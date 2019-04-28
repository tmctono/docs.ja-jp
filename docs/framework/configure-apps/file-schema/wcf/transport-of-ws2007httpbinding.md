---
title: <transport> の <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
ms.openlocfilehash: a1540b53d4af76141c1daee60a6bddbbecd9d6da
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788298"
---
# <a name="transport-of-ws2007httpbinding"></a><span data-ttu-id="0af54-102">\<トランスポート > の\<ws2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="0af54-102">\<transport> of \<ws2007HttpBinding></span></span>
<span data-ttu-id="0af54-103">HTTP トランスポートの認証設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="0af54-103">Defines authentication settings for the HTTP transport.</span></span>  
  
 <span data-ttu-id="0af54-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="0af54-104">\<system.serviceModel></span></span>  
<span data-ttu-id="0af54-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="0af54-105">\<bindings></span></span>  
<span data-ttu-id="0af54-106">\<ws2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="0af54-106">\<ws2007HttpBinding></span></span>  
<span data-ttu-id="0af54-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="0af54-107">\<binding></span></span>  
<span data-ttu-id="0af54-108">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="0af54-108">\<security></span></span>  
<span data-ttu-id="0af54-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="0af54-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0af54-110">構文</span><span class="sxs-lookup"><span data-stu-id="0af54-110">Syntax</span></span>  
  
```xml  
<transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
           proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
           realm="string" />
```  
  
## <a name="type"></a><span data-ttu-id="0af54-111">型</span><span class="sxs-lookup"><span data-stu-id="0af54-111">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0af54-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="0af54-112">Attributes and Elements</span></span>  
 <span data-ttu-id="0af54-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="0af54-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0af54-114">属性</span><span class="sxs-lookup"><span data-stu-id="0af54-114">Attributes</span></span>  
  
|<span data-ttu-id="0af54-115">属性</span><span class="sxs-lookup"><span data-stu-id="0af54-115">Attribute</span></span>|<span data-ttu-id="0af54-116">説明</span><span class="sxs-lookup"><span data-stu-id="0af54-116">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="0af54-117">サービスに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="0af54-117">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="0af54-118">この属性は <xref:System.ServiceModel.HttpClientCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="0af54-118">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="0af54-119">ドメイン プロキシに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="0af54-119">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="0af54-120">この属性は <xref:System.ServiceModel.HttpProxyCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="0af54-120">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="0af54-121">ダイジェスト認証または基本認証の認証レルム。</span><span class="sxs-lookup"><span data-stu-id="0af54-121">The authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="0af54-122">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="0af54-122">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="0af54-123">認証レルムでは、少なくとも、認証を実行するホストの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="0af54-123">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="0af54-124">アクセス権のあるユーザーのコレクションも指定できます。</span><span class="sxs-lookup"><span data-stu-id="0af54-124">It can also specify a collection of users who have access.</span></span> <span data-ttu-id="0af54-125">ユーザーは、認証レルムを照会して、複数のユーザー名とパスワードの候補のうち、どれを使用できるかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="0af54-125">A user can query the authentication realm to determine which one of the several possible usernames and passwords can be used.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="0af54-126">clientCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="0af54-126">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="0af54-127">[値]</span><span class="sxs-lookup"><span data-stu-id="0af54-127">Value</span></span>|<span data-ttu-id="0af54-128">説明</span><span class="sxs-lookup"><span data-stu-id="0af54-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0af54-129">なし</span><span class="sxs-lookup"><span data-stu-id="0af54-129">None</span></span>|<span data-ttu-id="0af54-130">セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="0af54-130">Security is disabled.</span></span>|  
|<span data-ttu-id="0af54-131">Basic</span><span class="sxs-lookup"><span data-stu-id="0af54-131">Basic</span></span>|<span data-ttu-id="0af54-132">基本認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="0af54-132">Uses basic authentication.</span></span>|  
|<span data-ttu-id="0af54-133">Digest</span><span class="sxs-lookup"><span data-stu-id="0af54-133">Digest</span></span>|<span data-ttu-id="0af54-134">ダイジェスト認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="0af54-134">Uses digest authentication.</span></span>|  
|<span data-ttu-id="0af54-135">Ntlm</span><span class="sxs-lookup"><span data-stu-id="0af54-135">Ntlm</span></span>|<span data-ttu-id="0af54-136">Windows ドメインのフォールバックとして NTLM 認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="0af54-136">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="0af54-137">Windows</span><span class="sxs-lookup"><span data-stu-id="0af54-137">Windows</span></span>|<span data-ttu-id="0af54-138">統合 Windows 認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="0af54-138">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="0af54-139">証明書</span><span class="sxs-lookup"><span data-stu-id="0af54-139">Certificate</span></span>|<span data-ttu-id="0af54-140">X.509 証明書を使用して、クライアントを認証します。</span><span class="sxs-lookup"><span data-stu-id="0af54-140">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="0af54-141">proxyCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="0af54-141">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="0af54-142">[値]</span><span class="sxs-lookup"><span data-stu-id="0af54-142">Value</span></span>|<span data-ttu-id="0af54-143">説明</span><span class="sxs-lookup"><span data-stu-id="0af54-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0af54-144">なし</span><span class="sxs-lookup"><span data-stu-id="0af54-144">None</span></span>|<span data-ttu-id="0af54-145">セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="0af54-145">Security is disabled.</span></span>|  
|<span data-ttu-id="0af54-146">Basic</span><span class="sxs-lookup"><span data-stu-id="0af54-146">Basic</span></span>|<span data-ttu-id="0af54-147">基本認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="0af54-147">Uses basic authentication.</span></span>|  
|<span data-ttu-id="0af54-148">Digest</span><span class="sxs-lookup"><span data-stu-id="0af54-148">Digest</span></span>|<span data-ttu-id="0af54-149">ダイジェスト認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="0af54-149">Uses digest authentication.</span></span>|  
|<span data-ttu-id="0af54-150">Ntlm</span><span class="sxs-lookup"><span data-stu-id="0af54-150">Ntlm</span></span>|<span data-ttu-id="0af54-151">Windows ドメインのフォールバックとして NTLM を使用します。</span><span class="sxs-lookup"><span data-stu-id="0af54-151">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="0af54-152">Windows</span><span class="sxs-lookup"><span data-stu-id="0af54-152">Windows</span></span>|<span data-ttu-id="0af54-153">統合 Windows 認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="0af54-153">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="0af54-154">証明書</span><span class="sxs-lookup"><span data-stu-id="0af54-154">Certificate</span></span>|<span data-ttu-id="0af54-155">X.509 証明書を使用して、クライアントを認証します。</span><span class="sxs-lookup"><span data-stu-id="0af54-155">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0af54-156">子要素</span><span class="sxs-lookup"><span data-stu-id="0af54-156">Child Elements</span></span>  
 <span data-ttu-id="0af54-157">なし</span><span class="sxs-lookup"><span data-stu-id="0af54-157">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0af54-158">親要素</span><span class="sxs-lookup"><span data-stu-id="0af54-158">Parent Elements</span></span>  
  
|<span data-ttu-id="0af54-159">要素</span><span class="sxs-lookup"><span data-stu-id="0af54-159">Element</span></span>|<span data-ttu-id="0af54-160">説明</span><span class="sxs-lookup"><span data-stu-id="0af54-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0af54-161">\<security></span><span class="sxs-lookup"><span data-stu-id="0af54-161">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-ws2007httpbinding.md)|<span data-ttu-id="0af54-162">セキュリティ機能を表す、 [ \<ws2007HttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md)要素。</span><span class="sxs-lookup"><span data-stu-id="0af54-162">Represents the security capabilities of the [\<ws2007HttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0af54-163">関連項目</span><span class="sxs-lookup"><span data-stu-id="0af54-163">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>
- [<span data-ttu-id="0af54-164">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="0af54-164">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="0af54-165">バインディング</span><span class="sxs-lookup"><span data-stu-id="0af54-165">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="0af54-166">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="0af54-166">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="0af54-167">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="0af54-167">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="0af54-168">\<binding></span><span class="sxs-lookup"><span data-stu-id="0af54-168">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
