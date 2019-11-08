---
title: <transport> の <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
ms.openlocfilehash: 0cd20c607b0c4ddd3ecfd806d38ba63b4a5c5a25
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73732766"
---
# <a name="transport-of-ws2007httpbinding"></a><span data-ttu-id="71c61-102">\<ws2007HttpBinding > の \<トランスポート ></span><span class="sxs-lookup"><span data-stu-id="71c61-102">\<transport> of \<ws2007HttpBinding></span></span>
<span data-ttu-id="71c61-103">HTTP トランスポートの認証設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="71c61-103">Defines authentication settings for the HTTP transport.</span></span>  
  
<span data-ttu-id="71c61-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="71c61-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="71c61-105">&nbsp; &nbsp;[ **\<system >** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="71c61-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="71c61-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**バインド**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="71c61-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="71c61-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ws2007HttpBinding >** ](ws2007httpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="71c61-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007HttpBinding>**](ws2007httpbinding.md)</span></span>\
<span data-ttu-id="71c61-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**バインド >** </span><span class="sxs-lookup"><span data-stu-id="71c61-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="71c61-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**セキュリティ >** ](security-of-ws2007httpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="71c61-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-ws2007httpbinding.md)</span></span>\
<span data-ttu-id="71c61-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**トランスポート >**</span><span class="sxs-lookup"><span data-stu-id="71c61-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71c61-111">構文</span><span class="sxs-lookup"><span data-stu-id="71c61-111">Syntax</span></span>  
  
```xml  
<transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
           proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
           realm="string" />
```  
  
## <a name="type"></a><span data-ttu-id="71c61-112">[種類]</span><span class="sxs-lookup"><span data-stu-id="71c61-112">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="71c61-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="71c61-113">Attributes and Elements</span></span>  
 <span data-ttu-id="71c61-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="71c61-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="71c61-115">属性</span><span class="sxs-lookup"><span data-stu-id="71c61-115">Attributes</span></span>  
  
|<span data-ttu-id="71c61-116">属性</span><span class="sxs-lookup"><span data-stu-id="71c61-116">Attribute</span></span>|<span data-ttu-id="71c61-117">説明</span><span class="sxs-lookup"><span data-stu-id="71c61-117">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="71c61-118">サービスに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="71c61-118">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="71c61-119">この属性は <xref:System.ServiceModel.HttpClientCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="71c61-119">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="71c61-120">ドメイン プロキシに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="71c61-120">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="71c61-121">この属性は <xref:System.ServiceModel.HttpProxyCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="71c61-121">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="71c61-122">ダイジェスト認証または基本認証の認証レルム。</span><span class="sxs-lookup"><span data-stu-id="71c61-122">The authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="71c61-123">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="71c61-123">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="71c61-124">認証レルムでは、少なくとも、認証を実行するホストの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="71c61-124">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="71c61-125">アクセス権のあるユーザーのコレクションも指定できます。</span><span class="sxs-lookup"><span data-stu-id="71c61-125">It can also specify a collection of users who have access.</span></span> <span data-ttu-id="71c61-126">ユーザーは、認証レルムを照会して、複数のユーザー名とパスワードの候補のうち、どれを使用できるかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="71c61-126">A user can query the authentication realm to determine which one of the several possible usernames and passwords can be used.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="71c61-127">clientCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="71c61-127">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="71c61-128">[値]</span><span class="sxs-lookup"><span data-stu-id="71c61-128">Value</span></span>|<span data-ttu-id="71c61-129">説明</span><span class="sxs-lookup"><span data-stu-id="71c61-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="71c61-130">None</span><span class="sxs-lookup"><span data-stu-id="71c61-130">None</span></span>|<span data-ttu-id="71c61-131">セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="71c61-131">Security is disabled.</span></span>|  
|<span data-ttu-id="71c61-132">Basic</span><span class="sxs-lookup"><span data-stu-id="71c61-132">Basic</span></span>|<span data-ttu-id="71c61-133">基本認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="71c61-133">Uses basic authentication.</span></span>|  
|<span data-ttu-id="71c61-134">Digest</span><span class="sxs-lookup"><span data-stu-id="71c61-134">Digest</span></span>|<span data-ttu-id="71c61-135">ダイジェスト認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="71c61-135">Uses digest authentication.</span></span>|  
|<span data-ttu-id="71c61-136">Ntlm</span><span class="sxs-lookup"><span data-stu-id="71c61-136">Ntlm</span></span>|<span data-ttu-id="71c61-137">Windows ドメインのフォールバックとして NTLM 認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="71c61-137">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="71c61-138">Windows</span><span class="sxs-lookup"><span data-stu-id="71c61-138">Windows</span></span>|<span data-ttu-id="71c61-139">統合 Windows 認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="71c61-139">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="71c61-140">証明書</span><span class="sxs-lookup"><span data-stu-id="71c61-140">Certificate</span></span>|<span data-ttu-id="71c61-141">X.509 証明書を使用して、クライアントを認証します。</span><span class="sxs-lookup"><span data-stu-id="71c61-141">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="71c61-142">proxyCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="71c61-142">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="71c61-143">[値]</span><span class="sxs-lookup"><span data-stu-id="71c61-143">Value</span></span>|<span data-ttu-id="71c61-144">説明</span><span class="sxs-lookup"><span data-stu-id="71c61-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="71c61-145">None</span><span class="sxs-lookup"><span data-stu-id="71c61-145">None</span></span>|<span data-ttu-id="71c61-146">セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="71c61-146">Security is disabled.</span></span>|  
|<span data-ttu-id="71c61-147">Basic</span><span class="sxs-lookup"><span data-stu-id="71c61-147">Basic</span></span>|<span data-ttu-id="71c61-148">基本認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="71c61-148">Uses basic authentication.</span></span>|  
|<span data-ttu-id="71c61-149">Digest</span><span class="sxs-lookup"><span data-stu-id="71c61-149">Digest</span></span>|<span data-ttu-id="71c61-150">ダイジェスト認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="71c61-150">Uses digest authentication.</span></span>|  
|<span data-ttu-id="71c61-151">Ntlm</span><span class="sxs-lookup"><span data-stu-id="71c61-151">Ntlm</span></span>|<span data-ttu-id="71c61-152">Windows ドメインのフォールバックとして NTLM を使用します。</span><span class="sxs-lookup"><span data-stu-id="71c61-152">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="71c61-153">Windows</span><span class="sxs-lookup"><span data-stu-id="71c61-153">Windows</span></span>|<span data-ttu-id="71c61-154">統合 Windows 認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="71c61-154">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="71c61-155">証明書</span><span class="sxs-lookup"><span data-stu-id="71c61-155">Certificate</span></span>|<span data-ttu-id="71c61-156">X.509 証明書を使用して、クライアントを認証します。</span><span class="sxs-lookup"><span data-stu-id="71c61-156">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="71c61-157">子要素</span><span class="sxs-lookup"><span data-stu-id="71c61-157">Child Elements</span></span>  
 <span data-ttu-id="71c61-158">None</span><span class="sxs-lookup"><span data-stu-id="71c61-158">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="71c61-159">親要素</span><span class="sxs-lookup"><span data-stu-id="71c61-159">Parent Elements</span></span>  
  
|<span data-ttu-id="71c61-160">要素</span><span class="sxs-lookup"><span data-stu-id="71c61-160">Element</span></span>|<span data-ttu-id="71c61-161">説明</span><span class="sxs-lookup"><span data-stu-id="71c61-161">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="71c61-162">\< セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="71c61-162">\<security></span></span>](security-of-ws2007httpbinding.md)|<span data-ttu-id="71c61-163">[\<ws2007HttpBinding >](ws2007httpbinding.md)要素のセキュリティ機能を表します。</span><span class="sxs-lookup"><span data-stu-id="71c61-163">Represents the security capabilities of the [\<ws2007HttpBinding>](ws2007httpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="71c61-164">関連項目</span><span class="sxs-lookup"><span data-stu-id="71c61-164">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>
- [<span data-ttu-id="71c61-165">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="71c61-165">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="71c61-166">バインディング</span><span class="sxs-lookup"><span data-stu-id="71c61-166">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="71c61-167">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="71c61-167">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="71c61-168">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="71c61-168">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="71c61-169">\<binding ></span><span class="sxs-lookup"><span data-stu-id="71c61-169">\<binding></span></span>](bindings.md)
