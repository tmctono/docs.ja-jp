---
title: <transport> の <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
ms.openlocfilehash: 60e8758d653848176ca3f287e253bd7990e78470
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91162050"
---
# <a name="transport-of-ws2007httpbinding"></a><span data-ttu-id="7e5d4-102">\<transport> の \<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="7e5d4-102">\<transport> of \<ws2007HttpBinding></span></span>

<span data-ttu-id="7e5d4-103">HTTP トランスポートの認証設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="7e5d4-103">Defines authentication settings for the HTTP transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007HttpBinding>**](ws2007httpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-ws2007httpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="7e5d4-104">構文</span><span class="sxs-lookup"><span data-stu-id="7e5d4-104">Syntax</span></span>  
  
```xml  
<transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
           proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
           realm="string" />
```  
  
## <a name="type"></a><span data-ttu-id="7e5d4-105">種類</span><span class="sxs-lookup"><span data-stu-id="7e5d4-105">Type</span></span>  

 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7e5d4-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7e5d4-106">Attributes and Elements</span></span>  

 <span data-ttu-id="7e5d4-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7e5d4-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7e5d4-108">属性</span><span class="sxs-lookup"><span data-stu-id="7e5d4-108">Attributes</span></span>  
  
|<span data-ttu-id="7e5d4-109">属性</span><span class="sxs-lookup"><span data-stu-id="7e5d4-109">Attribute</span></span>|<span data-ttu-id="7e5d4-110">[説明]</span><span class="sxs-lookup"><span data-stu-id="7e5d4-110">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="7e5d4-111">サービスに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="7e5d4-111">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="7e5d4-112">この属性は <xref:System.ServiceModel.HttpClientCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="7e5d4-112">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="7e5d4-113">ドメイン プロキシに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="7e5d4-113">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="7e5d4-114">この属性は <xref:System.ServiceModel.HttpProxyCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="7e5d4-114">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="7e5d4-115">ダイジェスト認証または基本認証の認証レルム。</span><span class="sxs-lookup"><span data-stu-id="7e5d4-115">The authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="7e5d4-116">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="7e5d4-116">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="7e5d4-117">認証レルムでは、少なくとも、認証を実行するホストの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="7e5d4-117">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="7e5d4-118">アクセス権のあるユーザーのコレクションも指定できます。</span><span class="sxs-lookup"><span data-stu-id="7e5d4-118">It can also specify a collection of users who have access.</span></span> <span data-ttu-id="7e5d4-119">ユーザーは、認証レルムを照会して、複数のユーザー名とパスワードの候補のうち、どれを使用できるかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="7e5d4-119">A user can query the authentication realm to determine which one of the several possible usernames and passwords can be used.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="7e5d4-120">clientCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="7e5d4-120">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="7e5d4-121">値</span><span class="sxs-lookup"><span data-stu-id="7e5d4-121">Value</span></span>|<span data-ttu-id="7e5d4-122">説明</span><span class="sxs-lookup"><span data-stu-id="7e5d4-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7e5d4-123">None</span><span class="sxs-lookup"><span data-stu-id="7e5d4-123">None</span></span>|<span data-ttu-id="7e5d4-124">セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="7e5d4-124">Security is disabled.</span></span>|  
|<span data-ttu-id="7e5d4-125">Basic</span><span class="sxs-lookup"><span data-stu-id="7e5d4-125">Basic</span></span>|<span data-ttu-id="7e5d4-126">基本認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="7e5d4-126">Uses basic authentication.</span></span>|  
|<span data-ttu-id="7e5d4-127">ダイジェスト</span><span class="sxs-lookup"><span data-stu-id="7e5d4-127">Digest</span></span>|<span data-ttu-id="7e5d4-128">ダイジェスト認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="7e5d4-128">Uses digest authentication.</span></span>|  
|<span data-ttu-id="7e5d4-129">Ntlm</span><span class="sxs-lookup"><span data-stu-id="7e5d4-129">Ntlm</span></span>|<span data-ttu-id="7e5d4-130">Windows ドメインのフォールバックとして NTLM 認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="7e5d4-130">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="7e5d4-131">Windows</span><span class="sxs-lookup"><span data-stu-id="7e5d4-131">Windows</span></span>|<span data-ttu-id="7e5d4-132">統合 Windows 認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="7e5d4-132">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="7e5d4-133">Certificate</span><span class="sxs-lookup"><span data-stu-id="7e5d4-133">Certificate</span></span>|<span data-ttu-id="7e5d4-134">X.509 証明書を使用して、クライアントを認証します。</span><span class="sxs-lookup"><span data-stu-id="7e5d4-134">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="7e5d4-135">proxyCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="7e5d4-135">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="7e5d4-136">値</span><span class="sxs-lookup"><span data-stu-id="7e5d4-136">Value</span></span>|<span data-ttu-id="7e5d4-137">説明</span><span class="sxs-lookup"><span data-stu-id="7e5d4-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7e5d4-138">None</span><span class="sxs-lookup"><span data-stu-id="7e5d4-138">None</span></span>|<span data-ttu-id="7e5d4-139">セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="7e5d4-139">Security is disabled.</span></span>|  
|<span data-ttu-id="7e5d4-140">Basic</span><span class="sxs-lookup"><span data-stu-id="7e5d4-140">Basic</span></span>|<span data-ttu-id="7e5d4-141">基本認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="7e5d4-141">Uses basic authentication.</span></span>|  
|<span data-ttu-id="7e5d4-142">ダイジェスト</span><span class="sxs-lookup"><span data-stu-id="7e5d4-142">Digest</span></span>|<span data-ttu-id="7e5d4-143">ダイジェスト認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="7e5d4-143">Uses digest authentication.</span></span>|  
|<span data-ttu-id="7e5d4-144">Ntlm</span><span class="sxs-lookup"><span data-stu-id="7e5d4-144">Ntlm</span></span>|<span data-ttu-id="7e5d4-145">Windows ドメインのフォールバックとして NTLM を使用します。</span><span class="sxs-lookup"><span data-stu-id="7e5d4-145">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="7e5d4-146">Windows</span><span class="sxs-lookup"><span data-stu-id="7e5d4-146">Windows</span></span>|<span data-ttu-id="7e5d4-147">統合 Windows 認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="7e5d4-147">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="7e5d4-148">Certificate</span><span class="sxs-lookup"><span data-stu-id="7e5d4-148">Certificate</span></span>|<span data-ttu-id="7e5d4-149">X.509 証明書を使用して、クライアントを認証します。</span><span class="sxs-lookup"><span data-stu-id="7e5d4-149">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7e5d4-150">子要素</span><span class="sxs-lookup"><span data-stu-id="7e5d4-150">Child Elements</span></span>  

 <span data-ttu-id="7e5d4-151">None</span><span class="sxs-lookup"><span data-stu-id="7e5d4-151">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7e5d4-152">親要素</span><span class="sxs-lookup"><span data-stu-id="7e5d4-152">Parent Elements</span></span>  
  
|<span data-ttu-id="7e5d4-153">要素</span><span class="sxs-lookup"><span data-stu-id="7e5d4-153">Element</span></span>|<span data-ttu-id="7e5d4-154">説明</span><span class="sxs-lookup"><span data-stu-id="7e5d4-154">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-ws2007httpbinding.md)|<span data-ttu-id="7e5d4-155">要素のセキュリティ機能を表し [\<ws2007HttpBinding>](ws2007httpbinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="7e5d4-155">Represents the security capabilities of the [\<ws2007HttpBinding>](ws2007httpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7e5d4-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="7e5d4-156">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>
- [<span data-ttu-id="7e5d4-157">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="7e5d4-157">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="7e5d4-158">バインド</span><span class="sxs-lookup"><span data-stu-id="7e5d4-158">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="7e5d4-159">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="7e5d4-159">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="7e5d4-160">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="7e5d4-160">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
