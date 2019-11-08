---
title: <security> の <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: fdda0ff7-b462-4e26-af52-e87ddab71945
ms.openlocfilehash: e88f55f3651d1ccd55631dce13a0349ac2772624
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736391"
---
# <a name="security-of-ws2007httpbinding"></a><span data-ttu-id="e303e-102">\<ws2007HttpBinding > のセキュリティ > の \<</span><span class="sxs-lookup"><span data-stu-id="e303e-102">\<security> of \<ws2007HttpBinding></span></span>
<span data-ttu-id="e303e-103">[\<ws2007HttpBinding >](ws2007httpbinding.md)要素で使用されるセキュリティ設定を表します。</span><span class="sxs-lookup"><span data-stu-id="e303e-103">Represents the security settings used with the [\<ws2007HttpBinding>](ws2007httpbinding.md) element.</span></span>  
  
<span data-ttu-id="e303e-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e303e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e303e-105">&nbsp; &nbsp;[ **\<system >** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="e303e-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e303e-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**バインド**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="e303e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="e303e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ws2007HttpBinding >** ](ws2007httpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="e303e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007HttpBinding>**](ws2007httpbinding.md)</span></span>\
<span data-ttu-id="e303e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**バインド >** </span><span class="sxs-lookup"><span data-stu-id="e303e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="e303e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**セキュリティ >**</span><span class="sxs-lookup"><span data-stu-id="e303e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e303e-110">構文</span><span class="sxs-lookup"><span data-stu-id="e303e-110">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <bindings>
    <ws2007HttpBinding>
      <binding name = "String">
        <security mode="None/Message/Transport/TransportWithMessageCredential">
          <transport>
          </transport>
          <message>
          </message>
        </security>
      </binding>
    </ws2007HttpBinding>
  </bindings>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e303e-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e303e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e303e-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e303e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e303e-113">属性</span><span class="sxs-lookup"><span data-stu-id="e303e-113">Attributes</span></span>  
  
|<span data-ttu-id="e303e-114">属性</span><span class="sxs-lookup"><span data-stu-id="e303e-114">Attribute</span></span>|<span data-ttu-id="e303e-115">説明</span><span class="sxs-lookup"><span data-stu-id="e303e-115">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="e303e-116">Optional.</span><span class="sxs-lookup"><span data-stu-id="e303e-116">-   Optional.</span></span> <span data-ttu-id="e303e-117">適用するセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="e303e-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="e303e-118">既定値は、 `Message`です。</span><span class="sxs-lookup"><span data-stu-id="e303e-118">The default is `Message`.</span></span><br /><br /> <span data-ttu-id="e303e-119">この属性は <xref:System.ServiceModel.SecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="e303e-119">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="e303e-120">Mode 属性</span><span class="sxs-lookup"><span data-stu-id="e303e-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="e303e-121">[値]</span><span class="sxs-lookup"><span data-stu-id="e303e-121">Value</span></span>|<span data-ttu-id="e303e-122">説明</span><span class="sxs-lookup"><span data-stu-id="e303e-122">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="e303e-123">セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="e303e-123">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="e303e-124">セキュリティは、HTTPS を使用して確保されます。</span><span class="sxs-lookup"><span data-stu-id="e303e-124">Security is provided using HTTPS.</span></span> <span data-ttu-id="e303e-125">サービスは、Secure Sockets Layer (SSL) 証明書を使用して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e303e-125">The service must be configured with Secure Sockets Layer (SSL) certificates.</span></span> <span data-ttu-id="e303e-126">メッセージは、HTTPS およびサービスを使用して完全にセキュリティで保護され、サービスの SSL 証明書を使用するクライアントによって認証されます。</span><span class="sxs-lookup"><span data-stu-id="e303e-126">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="e303e-127">クライアント認証は、 [\<transport >](transport-of-ws2007httpbinding.md)要素の `ClientCredentials` 属性によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="e303e-127">The client authentication is controlled through the `ClientCredentials` attribute of the [\<transport>](transport-of-ws2007httpbinding.md) element.</span></span>|  
|`Message`|<span data-ttu-id="e303e-128">セキュリティは、SOAP メッセージ セキュリティを使用して確保されます。</span><span class="sxs-lookup"><span data-stu-id="e303e-128">Security is provided using SOAP message security.</span></span> <span data-ttu-id="e303e-129">既定では、SOAP 本文は暗号化および署名されます。</span><span class="sxs-lookup"><span data-stu-id="e303e-129">By default, the SOAP body is encrypted and signed.</span></span> <span data-ttu-id="e303e-130">このモードは、サービス資格情報をクライアントの帯域外で使用可能にするかどうか、使用するアルゴリズム スイート、<xref:System.ServiceModel.Security.SecurityMessageProperty> によってメッセージ本文に適用する保護レベルなど、さまざまな機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="e303e-130">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the <xref:System.ServiceModel.Security.SecurityMessageProperty>.</span></span> <span data-ttu-id="e303e-131">クライアント認証はセッションごとに 1 回実行され、認証の結果はセッションの存続中にキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="e303e-131">Client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="e303e-132">このモードでは、HTTPS は、整合性、機密性、およびサーバー認証を提供し、SOAP メッセージ セキュリティはクライアント認証を提供します。</span><span class="sxs-lookup"><span data-stu-id="e303e-132">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="e303e-133">既定では、クライアント認証はセッションごとに 1 回実行され、認証の結果はセッションの存続中にキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="e303e-133">By default, client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e303e-134">子要素</span><span class="sxs-lookup"><span data-stu-id="e303e-134">Child Elements</span></span>  
  
|<span data-ttu-id="e303e-135">要素</span><span class="sxs-lookup"><span data-stu-id="e303e-135">Element</span></span>|<span data-ttu-id="e303e-136">説明</span><span class="sxs-lookup"><span data-stu-id="e303e-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e303e-137">\<transport ></span><span class="sxs-lookup"><span data-stu-id="e303e-137">\<transport></span></span>](transport-of-ws2007httpbinding.md)|<span data-ttu-id="e303e-138">トランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="e303e-138">Defines the transport security settings.</span></span> <span data-ttu-id="e303e-139">この要素は、<xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> 型に対応しています。</span><span class="sxs-lookup"><span data-stu-id="e303e-139">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span> <span data-ttu-id="e303e-140">これらの設定は、モードが Transport に設定されている場合のみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="e303e-140">These settings are applied only when the mode is set to Transport.</span></span>|  
|[<span data-ttu-id="e303e-141">\< メッセージ ></span><span class="sxs-lookup"><span data-stu-id="e303e-141">\<message></span></span>](message-of-ws2007httpbinding.md)|<span data-ttu-id="e303e-142">メッセージのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="e303e-142">Defines the security settings for the message.</span></span> <span data-ttu-id="e303e-143">この要素は、<xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> 型に対応しています。</span><span class="sxs-lookup"><span data-stu-id="e303e-143">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span> <span data-ttu-id="e303e-144">これらの設定は、モードが Transport に設定されている場合は適用されません。</span><span class="sxs-lookup"><span data-stu-id="e303e-144">These settings are not applied when the mode is set to Transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e303e-145">親要素</span><span class="sxs-lookup"><span data-stu-id="e303e-145">Parent Elements</span></span>  
  
|<span data-ttu-id="e303e-146">要素</span><span class="sxs-lookup"><span data-stu-id="e303e-146">Element</span></span>|<span data-ttu-id="e303e-147">説明</span><span class="sxs-lookup"><span data-stu-id="e303e-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e303e-148">\<ws2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="e303e-148">\<ws2007HttpBinding></span></span>](ws2007httpbinding.md)|<span data-ttu-id="e303e-149">HTTP トランスポート アプリケーションのセキュリティで保護されたバインド。</span><span class="sxs-lookup"><span data-stu-id="e303e-149">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e303e-150">Remarks</span><span class="sxs-lookup"><span data-stu-id="e303e-150">Remarks</span></span>  
 <span data-ttu-id="e303e-151">この要素は、WS-\* 仕様を実装するサービスと相互運用するようにデザインされています。</span><span class="sxs-lookup"><span data-stu-id="e303e-151">This element is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="e303e-152">このバインディングのトランスポート セキュリティは、SSL (Secure Sockets Layer) over HTTP または HTTPS です。</span><span class="sxs-lookup"><span data-stu-id="e303e-152">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e303e-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="e303e-153">See also</span></span>

- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="e303e-154">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="e303e-154">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="e303e-155">バインディング</span><span class="sxs-lookup"><span data-stu-id="e303e-155">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e303e-156">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="e303e-156">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e303e-157">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="e303e-157">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="e303e-158">\<binding ></span><span class="sxs-lookup"><span data-stu-id="e303e-158">\<binding></span></span>](bindings.md)
