---
title: <security> の <wsHttpBinding>
ms.date: 03/30/2017
ms.assetid: 8658b162-2ddf-4162-a869-aa517a42288a
ms.openlocfilehash: 9f984759fb52242bf8030a101b567c14627dd314
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158696"
---
# <a name="security-of-wshttpbinding"></a><span data-ttu-id="14440-102">\<security> の \<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="14440-102">\<security> of \<wsHttpBinding></span></span>

<span data-ttu-id="14440-103">のセキュリティ機能を表し [\<wsHttpBinding>](wshttpbinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="14440-103">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsHttpBinding>**](wshttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="14440-104">構文</span><span class="sxs-lookup"><span data-stu-id="14440-104">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithMessageCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="String"
             defaultClientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             defaultProxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             defaultRealm="String" />
  <message clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
           algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           establishSecurityContext="Boolean"
           negotiateServiceCredential="Boolean" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14440-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="14440-105">Attributes and Elements</span></span>  

 <span data-ttu-id="14440-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="14440-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14440-107">属性</span><span class="sxs-lookup"><span data-stu-id="14440-107">Attributes</span></span>  
  
|<span data-ttu-id="14440-108">属性</span><span class="sxs-lookup"><span data-stu-id="14440-108">Attribute</span></span>|<span data-ttu-id="14440-109">[説明]</span><span class="sxs-lookup"><span data-stu-id="14440-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="14440-110">mode</span><span class="sxs-lookup"><span data-stu-id="14440-110">mode</span></span>|<span data-ttu-id="14440-111">Optional.</span><span class="sxs-lookup"><span data-stu-id="14440-111">-   Optional.</span></span> <span data-ttu-id="14440-112">適用するセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="14440-112">Specifies the type of security that is applied.</span></span> <span data-ttu-id="14440-113">既定では、 `Message`です。</span><span class="sxs-lookup"><span data-stu-id="14440-113">The default is `Message`.</span></span><br /><span data-ttu-id="14440-114">-この属性の型は <xref:System.ServiceModel.SecurityMode> です。</span><span class="sxs-lookup"><span data-stu-id="14440-114">-   This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="14440-115">Mode 属性</span><span class="sxs-lookup"><span data-stu-id="14440-115">Mode Attribute</span></span>  
  
|<span data-ttu-id="14440-116">値</span><span class="sxs-lookup"><span data-stu-id="14440-116">Value</span></span>|<span data-ttu-id="14440-117">説明</span><span class="sxs-lookup"><span data-stu-id="14440-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="14440-118">None</span><span class="sxs-lookup"><span data-stu-id="14440-118">None</span></span>|<span data-ttu-id="14440-119">セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="14440-119">Security is disabled.</span></span>|  
|<span data-ttu-id="14440-120">トランスポート</span><span class="sxs-lookup"><span data-stu-id="14440-120">Transport</span></span>|<span data-ttu-id="14440-121">セキュリティは、HTTPS を使用して確保されます。</span><span class="sxs-lookup"><span data-stu-id="14440-121">Security is provided using HTTPS.</span></span> <span data-ttu-id="14440-122">サービスは、SSL 証明書を使用して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14440-122">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="14440-123">メッセージは、HTTPS を使用して完全にセキュリティで保護され、サービスの SSL 証明書を使用するクライアントによって認証されます。</span><span class="sxs-lookup"><span data-stu-id="14440-123">The message is entirely secured using HTTPS and is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="14440-124">クライアント認証は、`ClientCredentials` 属性を使用して制御されます。</span><span class="sxs-lookup"><span data-stu-id="14440-124">The client authentication is controlled through the `ClientCredentials` attribute.</span></span> <span data-ttu-id="14440-125">の [\<transport>](transport-of-wshttpbinding.md) 。</span><span class="sxs-lookup"><span data-stu-id="14440-125">of the [\<transport>](transport-of-wshttpbinding.md).</span></span>|  
|<span data-ttu-id="14440-126">Message</span><span class="sxs-lookup"><span data-stu-id="14440-126">Message</span></span>|<span data-ttu-id="14440-127">セキュリティは、SOAP メッセージ セキュリティを使用して確保されます。</span><span class="sxs-lookup"><span data-stu-id="14440-127">Security is provided using SOAP message security.</span></span> <span data-ttu-id="14440-128">既定では、SOAP 本文は暗号化および署名されます。</span><span class="sxs-lookup"><span data-stu-id="14440-128">By default, the SOAP body is Encrypted and Signed.</span></span> <span data-ttu-id="14440-129">このモードは、サービス資格情報をクライアントの帯域外で使用可能にするかどうか、使用するアルゴリズム スイート、Security.Message プロパティを使用してメッセージ本文に適用する保護レベルなど、さまざまな機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="14440-129">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the Security.Message property.</span></span> <span data-ttu-id="14440-130">クライアント認証はセッションごとに 1 回実行され、認証の結果はセッションの存続中にキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="14440-130">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="14440-131">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="14440-131">TransportWithMessageCredential</span></span>|<span data-ttu-id="14440-132">このモードでは、HTTPS は、整合性、機密性、およびサーバー認証を提供し、SOAP メッセージ セキュリティはクライアント認証を提供します。</span><span class="sxs-lookup"><span data-stu-id="14440-132">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="14440-133">既定では、クライアント認証はセッションごとに 1 回実行され、認証の結果はセッションの存続中にキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="14440-133">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="14440-134">子要素</span><span class="sxs-lookup"><span data-stu-id="14440-134">Child Elements</span></span>  
  
|<span data-ttu-id="14440-135">要素</span><span class="sxs-lookup"><span data-stu-id="14440-135">Element</span></span>|<span data-ttu-id="14440-136">説明</span><span class="sxs-lookup"><span data-stu-id="14440-136">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-wshttpbinding.md)|<span data-ttu-id="14440-137">トランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="14440-137">Defines the transport security settings.</span></span> <span data-ttu-id="14440-138">この要素は、<xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> 型に対応しています。</span><span class="sxs-lookup"><span data-stu-id="14440-138">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
|[\<message>](message-of-wshttpbinding.md)|<span data-ttu-id="14440-139">メッセージのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="14440-139">Defines the security settings for the message.</span></span> <span data-ttu-id="14440-140">この要素は、<xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> 型に対応しています。</span><span class="sxs-lookup"><span data-stu-id="14440-140">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="14440-141">親要素</span><span class="sxs-lookup"><span data-stu-id="14440-141">Parent Elements</span></span>  
  
|<span data-ttu-id="14440-142">要素</span><span class="sxs-lookup"><span data-stu-id="14440-142">Element</span></span>|<span data-ttu-id="14440-143">説明</span><span class="sxs-lookup"><span data-stu-id="14440-143">Description</span></span>|  
|-------------|-----------------|  
|[\<wsHttpBinding>](wshttpbinding.md)|<span data-ttu-id="14440-144">HTTP トランスポート アプリケーションのセキュリティで保護されたバインド。</span><span class="sxs-lookup"><span data-stu-id="14440-144">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14440-145">解説</span><span class="sxs-lookup"><span data-stu-id="14440-145">Remarks</span></span>  

 <span data-ttu-id="14440-146">WSHttpBinding クラスは、WS-\* 仕様を実装するサービスと相互運用するようにデザインされています。</span><span class="sxs-lookup"><span data-stu-id="14440-146">The WSHttpBinding class is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="14440-147">このバインディングのトランスポート セキュリティは、SSL (Secure Sockets Layer) over HTTP または HTTPS です。</span><span class="sxs-lookup"><span data-stu-id="14440-147">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14440-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="14440-148">See also</span></span>

- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- [<span data-ttu-id="14440-149">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="14440-149">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="14440-150">バインド</span><span class="sxs-lookup"><span data-stu-id="14440-150">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="14440-151">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="14440-151">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="14440-152">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="14440-152">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
