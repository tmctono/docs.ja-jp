---
title: <security> の <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: fdda0ff7-b462-4e26-af52-e87ddab71945
ms.openlocfilehash: a895df027bee7430e51e76c480136a49b6b2a0be
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936574"
---
# <a name="security-of-ws2007httpbinding"></a><span data-ttu-id="1a092-102">\<ws2007HttpBinding > の\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="1a092-102">\<security> of \<ws2007HttpBinding></span></span>
<span data-ttu-id="1a092-103">Ws2007HttpBinding > 要素で[ \<](ws2007httpbinding.md)使用されるセキュリティ設定を表します。</span><span class="sxs-lookup"><span data-stu-id="1a092-103">Represents the security settings used with the [\<ws2007HttpBinding>](ws2007httpbinding.md) element.</span></span>  
  
 <span data-ttu-id="1a092-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1a092-104">\<system.serviceModel></span></span>  
<span data-ttu-id="1a092-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="1a092-105">\<bindings></span></span>  
<span data-ttu-id="1a092-106">\<ws2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="1a092-106">\<ws2007HttpBinding></span></span>  
<span data-ttu-id="1a092-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="1a092-107">\<binding></span></span>  
<span data-ttu-id="1a092-108">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="1a092-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a092-109">構文</span><span class="sxs-lookup"><span data-stu-id="1a092-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1a092-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1a092-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1a092-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1a092-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1a092-112">属性</span><span class="sxs-lookup"><span data-stu-id="1a092-112">Attributes</span></span>  
  
|<span data-ttu-id="1a092-113">属性</span><span class="sxs-lookup"><span data-stu-id="1a092-113">Attribute</span></span>|<span data-ttu-id="1a092-114">説明</span><span class="sxs-lookup"><span data-stu-id="1a092-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="1a092-115">Optional.</span><span class="sxs-lookup"><span data-stu-id="1a092-115">-   Optional.</span></span> <span data-ttu-id="1a092-116">適用するセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="1a092-116">Specifies the type of security that is applied.</span></span> <span data-ttu-id="1a092-117">既定値は `Message` です。</span><span class="sxs-lookup"><span data-stu-id="1a092-117">The default is `Message`.</span></span><br /><br /> <span data-ttu-id="1a092-118">この属性は <xref:System.ServiceModel.SecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="1a092-118">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="1a092-119">Mode 属性</span><span class="sxs-lookup"><span data-stu-id="1a092-119">Mode Attribute</span></span>  
  
|<span data-ttu-id="1a092-120">値</span><span class="sxs-lookup"><span data-stu-id="1a092-120">Value</span></span>|<span data-ttu-id="1a092-121">説明</span><span class="sxs-lookup"><span data-stu-id="1a092-121">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="1a092-122">セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="1a092-122">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="1a092-123">セキュリティは、HTTPS を使用して確保されます。</span><span class="sxs-lookup"><span data-stu-id="1a092-123">Security is provided using HTTPS.</span></span> <span data-ttu-id="1a092-124">サービスは、Secure Sockets Layer (SSL) 証明書を使用して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a092-124">The service must be configured with Secure Sockets Layer (SSL) certificates.</span></span> <span data-ttu-id="1a092-125">メッセージは、HTTPS およびサービスを使用して完全にセキュリティで保護され、サービスの SSL 証明書を使用するクライアントによって認証されます。</span><span class="sxs-lookup"><span data-stu-id="1a092-125">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="1a092-126">クライアント認証は、 [ \<トランスポート >](transport-of-ws2007httpbinding.md)要素`ClientCredentials`の属性によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="1a092-126">The client authentication is controlled through the `ClientCredentials` attribute of the [\<transport>](transport-of-ws2007httpbinding.md) element.</span></span>|  
|`Message`|<span data-ttu-id="1a092-127">セキュリティは、SOAP メッセージ セキュリティを使用して確保されます。</span><span class="sxs-lookup"><span data-stu-id="1a092-127">Security is provided using SOAP message security.</span></span> <span data-ttu-id="1a092-128">既定では、SOAP 本文は暗号化および署名されます。</span><span class="sxs-lookup"><span data-stu-id="1a092-128">By default, the SOAP body is encrypted and signed.</span></span> <span data-ttu-id="1a092-129">このモードは、サービス資格情報をクライアントの帯域外で使用可能にするかどうか、使用するアルゴリズム スイート、<xref:System.ServiceModel.Security.SecurityMessageProperty> によってメッセージ本文に適用する保護レベルなど、さまざまな機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="1a092-129">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the <xref:System.ServiceModel.Security.SecurityMessageProperty>.</span></span> <span data-ttu-id="1a092-130">クライアント認証はセッションごとに 1 回実行され、認証の結果はセッションの存続中にキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="1a092-130">Client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="1a092-131">このモードでは、HTTPS は、整合性、機密性、およびサーバー認証を提供し、SOAP メッセージ セキュリティはクライアント認証を提供します。</span><span class="sxs-lookup"><span data-stu-id="1a092-131">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="1a092-132">既定では、クライアント認証はセッションごとに 1 回実行され、認証の結果はセッションの存続中にキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="1a092-132">By default, client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1a092-133">子要素</span><span class="sxs-lookup"><span data-stu-id="1a092-133">Child Elements</span></span>  
  
|<span data-ttu-id="1a092-134">要素</span><span class="sxs-lookup"><span data-stu-id="1a092-134">Element</span></span>|<span data-ttu-id="1a092-135">説明</span><span class="sxs-lookup"><span data-stu-id="1a092-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1a092-136">\<transport></span><span class="sxs-lookup"><span data-stu-id="1a092-136">\<transport></span></span>](transport-of-ws2007httpbinding.md)|<span data-ttu-id="1a092-137">トランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="1a092-137">Defines the transport security settings.</span></span> <span data-ttu-id="1a092-138">この要素は、<xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> 型に対応しています。</span><span class="sxs-lookup"><span data-stu-id="1a092-138">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span> <span data-ttu-id="1a092-139">これらの設定は、モードが Transport に設定されている場合のみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="1a092-139">These settings are applied only when the mode is set to Transport.</span></span>|  
|[<span data-ttu-id="1a092-140">\<message></span><span class="sxs-lookup"><span data-stu-id="1a092-140">\<message></span></span>](message-of-ws2007httpbinding.md)|<span data-ttu-id="1a092-141">メッセージのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="1a092-141">Defines the security settings for the message.</span></span> <span data-ttu-id="1a092-142">この要素は、<xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> 型に対応しています。</span><span class="sxs-lookup"><span data-stu-id="1a092-142">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span> <span data-ttu-id="1a092-143">これらの設定は、モードが Transport に設定されている場合は適用されません。</span><span class="sxs-lookup"><span data-stu-id="1a092-143">These settings are not applied when the mode is set to Transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1a092-144">親要素</span><span class="sxs-lookup"><span data-stu-id="1a092-144">Parent Elements</span></span>  
  
|<span data-ttu-id="1a092-145">要素</span><span class="sxs-lookup"><span data-stu-id="1a092-145">Element</span></span>|<span data-ttu-id="1a092-146">説明</span><span class="sxs-lookup"><span data-stu-id="1a092-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1a092-147">\<ws2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="1a092-147">\<ws2007HttpBinding></span></span>](ws2007httpbinding.md)|<span data-ttu-id="1a092-148">HTTP トランスポート アプリケーションのセキュリティで保護されたバインド。</span><span class="sxs-lookup"><span data-stu-id="1a092-148">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1a092-149">Remarks</span><span class="sxs-lookup"><span data-stu-id="1a092-149">Remarks</span></span>  
 <span data-ttu-id="1a092-150">この要素は、WS-\* 仕様を実装するサービスと相互運用するようにデザインされています。</span><span class="sxs-lookup"><span data-stu-id="1a092-150">This element is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="1a092-151">このバインディングのトランスポート セキュリティは、SSL (Secure Sockets Layer) over HTTP または HTTPS です。</span><span class="sxs-lookup"><span data-stu-id="1a092-151">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a092-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="1a092-152">See also</span></span>

- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="1a092-153">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="1a092-153">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="1a092-154">バインディング</span><span class="sxs-lookup"><span data-stu-id="1a092-154">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="1a092-155">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="1a092-155">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="1a092-156">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="1a092-156">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="1a092-157">\<binding></span><span class="sxs-lookup"><span data-stu-id="1a092-157">\<binding></span></span>](../../../misc/binding.md)
