---
title: <security> の <wsHttpBinding>
ms.date: 03/30/2017
ms.assetid: 8658b162-2ddf-4162-a869-aa517a42288a
ms.openlocfilehash: f7a4ef98637a7c966665fdd02ad26929bd4ba6ac
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399724"
---
# <a name="security-of-wshttpbinding"></a><span data-ttu-id="e88c6-102">\<wsHttpBinding の\<セキュリティ > ></span><span class="sxs-lookup"><span data-stu-id="e88c6-102">\<security> of \<wsHttpBinding></span></span>
<span data-ttu-id="e88c6-103">[ \<WsHttpBinding >](wshttpbinding.md)のセキュリティ機能を表します。</span><span class="sxs-lookup"><span data-stu-id="e88c6-103">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md).</span></span>  
  
<span data-ttu-id="e88c6-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e88c6-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e88c6-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e88c6-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e88c6-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<バインド >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="e88c6-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="e88c6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsHttpBinding >** ](wshttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="e88c6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsHttpBinding>**](wshttpbinding.md)</span></span>\
<span data-ttu-id="e88c6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<バインド >** </span><span class="sxs-lookup"><span data-stu-id="e88c6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="e88c6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<セキュリティ >**</span><span class="sxs-lookup"><span data-stu-id="e88c6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e88c6-110">構文</span><span class="sxs-lookup"><span data-stu-id="e88c6-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e88c6-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e88c6-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e88c6-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e88c6-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e88c6-113">属性</span><span class="sxs-lookup"><span data-stu-id="e88c6-113">Attributes</span></span>  
  
|<span data-ttu-id="e88c6-114">属性</span><span class="sxs-lookup"><span data-stu-id="e88c6-114">Attribute</span></span>|<span data-ttu-id="e88c6-115">説明</span><span class="sxs-lookup"><span data-stu-id="e88c6-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e88c6-116">モード</span><span class="sxs-lookup"><span data-stu-id="e88c6-116">mode</span></span>|<span data-ttu-id="e88c6-117">Optional.</span><span class="sxs-lookup"><span data-stu-id="e88c6-117">-   Optional.</span></span> <span data-ttu-id="e88c6-118">適用するセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="e88c6-118">Specifies the type of security that is applied.</span></span> <span data-ttu-id="e88c6-119">既定値は `Message` です。</span><span class="sxs-lookup"><span data-stu-id="e88c6-119">The default is `Message`.</span></span><br /><span data-ttu-id="e88c6-120">-この属性の型<xref:System.ServiceModel.SecurityMode>はです。</span><span class="sxs-lookup"><span data-stu-id="e88c6-120">-   This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="e88c6-121">Mode 属性</span><span class="sxs-lookup"><span data-stu-id="e88c6-121">Mode Attribute</span></span>  
  
|<span data-ttu-id="e88c6-122">値</span><span class="sxs-lookup"><span data-stu-id="e88c6-122">Value</span></span>|<span data-ttu-id="e88c6-123">説明</span><span class="sxs-lookup"><span data-stu-id="e88c6-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e88c6-124">なし</span><span class="sxs-lookup"><span data-stu-id="e88c6-124">None</span></span>|<span data-ttu-id="e88c6-125">セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="e88c6-125">Security is disabled.</span></span>|  
|<span data-ttu-id="e88c6-126">Transport</span><span class="sxs-lookup"><span data-stu-id="e88c6-126">Transport</span></span>|<span data-ttu-id="e88c6-127">セキュリティは、HTTPS を使用して確保されます。</span><span class="sxs-lookup"><span data-stu-id="e88c6-127">Security is provided using HTTPS.</span></span> <span data-ttu-id="e88c6-128">サービスは、SSL 証明書を使用して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e88c6-128">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="e88c6-129">メッセージは、HTTPS を使用して完全にセキュリティで保護され、サービスの SSL 証明書を使用するクライアントによって認証されます。</span><span class="sxs-lookup"><span data-stu-id="e88c6-129">The message is entirely secured using HTTPS and is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="e88c6-130">クライアント認証は、`ClientCredentials` 属性を使用して制御されます。</span><span class="sxs-lookup"><span data-stu-id="e88c6-130">The client authentication is controlled through the `ClientCredentials` attribute.</span></span> <span data-ttu-id="e88c6-131">トランスポート > [ \<](transport-of-wshttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="e88c6-131">of the [\<transport>](transport-of-wshttpbinding.md).</span></span>|  
|<span data-ttu-id="e88c6-132">Message</span><span class="sxs-lookup"><span data-stu-id="e88c6-132">Message</span></span>|<span data-ttu-id="e88c6-133">セキュリティは、SOAP メッセージ セキュリティを使用して確保されます。</span><span class="sxs-lookup"><span data-stu-id="e88c6-133">Security is provided using SOAP message security.</span></span> <span data-ttu-id="e88c6-134">既定では、SOAP 本文は暗号化および署名されます。</span><span class="sxs-lookup"><span data-stu-id="e88c6-134">By default, the SOAP body is Encrypted and Signed.</span></span> <span data-ttu-id="e88c6-135">このモードは、サービス資格情報をクライアントの帯域外で使用可能にするかどうか、使用するアルゴリズム スイート、Security.Message プロパティを使用してメッセージ本文に適用する保護レベルなど、さまざまな機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="e88c6-135">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the Security.Message property.</span></span> <span data-ttu-id="e88c6-136">クライアント認証はセッションごとに 1 回実行され、認証の結果はセッションの存続中にキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="e88c6-136">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="e88c6-137">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="e88c6-137">TransportWithMessageCredential</span></span>|<span data-ttu-id="e88c6-138">このモードでは、HTTPS は、整合性、機密性、およびサーバー認証を提供し、SOAP メッセージ セキュリティはクライアント認証を提供します。</span><span class="sxs-lookup"><span data-stu-id="e88c6-138">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="e88c6-139">既定では、クライアント認証はセッションごとに 1 回実行され、認証の結果はセッションの存続中にキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="e88c6-139">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e88c6-140">子要素</span><span class="sxs-lookup"><span data-stu-id="e88c6-140">Child Elements</span></span>  
  
|<span data-ttu-id="e88c6-141">要素</span><span class="sxs-lookup"><span data-stu-id="e88c6-141">Element</span></span>|<span data-ttu-id="e88c6-142">説明</span><span class="sxs-lookup"><span data-stu-id="e88c6-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e88c6-143">\<transport></span><span class="sxs-lookup"><span data-stu-id="e88c6-143">\<transport></span></span>](transport-of-wshttpbinding.md)|<span data-ttu-id="e88c6-144">トランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="e88c6-144">Defines the transport security settings.</span></span> <span data-ttu-id="e88c6-145">この要素は、<xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> 型に対応しています。</span><span class="sxs-lookup"><span data-stu-id="e88c6-145">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
|[<span data-ttu-id="e88c6-146">\<message></span><span class="sxs-lookup"><span data-stu-id="e88c6-146">\<message></span></span>](message-of-wshttpbinding.md)|<span data-ttu-id="e88c6-147">メッセージのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="e88c6-147">Defines the security settings for the message.</span></span> <span data-ttu-id="e88c6-148">この要素は、<xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> 型に対応しています。</span><span class="sxs-lookup"><span data-stu-id="e88c6-148">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e88c6-149">親要素</span><span class="sxs-lookup"><span data-stu-id="e88c6-149">Parent Elements</span></span>  
  
|<span data-ttu-id="e88c6-150">要素</span><span class="sxs-lookup"><span data-stu-id="e88c6-150">Element</span></span>|<span data-ttu-id="e88c6-151">説明</span><span class="sxs-lookup"><span data-stu-id="e88c6-151">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e88c6-152">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="e88c6-152">\<wsHttpBinding></span></span>](wshttpbinding.md)|<span data-ttu-id="e88c6-153">HTTP トランスポート アプリケーションのセキュリティで保護されたバインド。</span><span class="sxs-lookup"><span data-stu-id="e88c6-153">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e88c6-154">Remarks</span><span class="sxs-lookup"><span data-stu-id="e88c6-154">Remarks</span></span>  
 <span data-ttu-id="e88c6-155">WSHttpBinding クラスは、WS-\* 仕様を実装するサービスと相互運用するようにデザインされています。</span><span class="sxs-lookup"><span data-stu-id="e88c6-155">The WSHttpBinding class is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="e88c6-156">このバインディングのトランスポート セキュリティは、SSL (Secure Sockets Layer) over HTTP または HTTPS です。</span><span class="sxs-lookup"><span data-stu-id="e88c6-156">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e88c6-157">関連項目</span><span class="sxs-lookup"><span data-stu-id="e88c6-157">See also</span></span>

- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- [<span data-ttu-id="e88c6-158">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="e88c6-158">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="e88c6-159">バインディング</span><span class="sxs-lookup"><span data-stu-id="e88c6-159">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e88c6-160">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="e88c6-160">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e88c6-161">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="e88c6-161">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="e88c6-162">\<binding></span><span class="sxs-lookup"><span data-stu-id="e88c6-162">\<binding></span></span>](../../../misc/binding.md)
