---
title: <security> の <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: fdda0ff7-b462-4e26-af52-e87ddab71945
ms.openlocfilehash: e88f55f3651d1ccd55631dce13a0349ac2772624
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736391"
---
# <a name="security-of-ws2007httpbinding"></a><span data-ttu-id="20240-102">\<security> の \<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="20240-102">\<security> of \<ws2007HttpBinding></span></span>
<span data-ttu-id="20240-103">要素で使用されるセキュリティ設定を表し [\<ws2007HttpBinding>](ws2007httpbinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="20240-103">Represents the security settings used with the [\<ws2007HttpBinding>](ws2007httpbinding.md) element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007HttpBinding>**](ws2007httpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="20240-104">構文</span><span class="sxs-lookup"><span data-stu-id="20240-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="20240-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="20240-105">Attributes and Elements</span></span>  
 <span data-ttu-id="20240-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="20240-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="20240-107">属性</span><span class="sxs-lookup"><span data-stu-id="20240-107">Attributes</span></span>  
  
|<span data-ttu-id="20240-108">属性</span><span class="sxs-lookup"><span data-stu-id="20240-108">Attribute</span></span>|<span data-ttu-id="20240-109">説明</span><span class="sxs-lookup"><span data-stu-id="20240-109">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="20240-110">Optional.</span><span class="sxs-lookup"><span data-stu-id="20240-110">-   Optional.</span></span> <span data-ttu-id="20240-111">適用するセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="20240-111">Specifies the type of security that is applied.</span></span> <span data-ttu-id="20240-112">既定値は、`Message` です。</span><span class="sxs-lookup"><span data-stu-id="20240-112">The default is `Message`.</span></span><br /><br /> <span data-ttu-id="20240-113">この属性は <xref:System.ServiceModel.SecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="20240-113">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="20240-114">Mode 属性</span><span class="sxs-lookup"><span data-stu-id="20240-114">Mode Attribute</span></span>  
  
|<span data-ttu-id="20240-115">値</span><span class="sxs-lookup"><span data-stu-id="20240-115">Value</span></span>|<span data-ttu-id="20240-116">Description</span><span class="sxs-lookup"><span data-stu-id="20240-116">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="20240-117">セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="20240-117">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="20240-118">セキュリティは、HTTPS を使用して確保されます。</span><span class="sxs-lookup"><span data-stu-id="20240-118">Security is provided using HTTPS.</span></span> <span data-ttu-id="20240-119">サービスは、Secure Sockets Layer (SSL) 証明書を使用して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20240-119">The service must be configured with Secure Sockets Layer (SSL) certificates.</span></span> <span data-ttu-id="20240-120">メッセージは、HTTPS およびサービスを使用して完全にセキュリティで保護され、サービスの SSL 証明書を使用するクライアントによって認証されます。</span><span class="sxs-lookup"><span data-stu-id="20240-120">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="20240-121">クライアント認証は、要素の属性によって制御され `ClientCredentials` [\<transport>](transport-of-ws2007httpbinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="20240-121">The client authentication is controlled through the `ClientCredentials` attribute of the [\<transport>](transport-of-ws2007httpbinding.md) element.</span></span>|  
|`Message`|<span data-ttu-id="20240-122">セキュリティは、SOAP メッセージ セキュリティを使用して確保されます。</span><span class="sxs-lookup"><span data-stu-id="20240-122">Security is provided using SOAP message security.</span></span> <span data-ttu-id="20240-123">既定では、SOAP 本文は暗号化および署名されます。</span><span class="sxs-lookup"><span data-stu-id="20240-123">By default, the SOAP body is encrypted and signed.</span></span> <span data-ttu-id="20240-124">このモードは、サービス資格情報をクライアントの帯域外で使用可能にするかどうか、使用するアルゴリズム スイート、<xref:System.ServiceModel.Security.SecurityMessageProperty> によってメッセージ本文に適用する保護レベルなど、さまざまな機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="20240-124">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the <xref:System.ServiceModel.Security.SecurityMessageProperty>.</span></span> <span data-ttu-id="20240-125">クライアント認証はセッションごとに 1 回実行され、認証の結果はセッションの存続中にキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="20240-125">Client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="20240-126">このモードでは、HTTPS は、整合性、機密性、およびサーバー認証を提供し、SOAP メッセージ セキュリティはクライアント認証を提供します。</span><span class="sxs-lookup"><span data-stu-id="20240-126">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="20240-127">既定では、クライアント認証はセッションごとに 1 回実行され、認証の結果はセッションの存続中にキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="20240-127">By default, client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="20240-128">子要素</span><span class="sxs-lookup"><span data-stu-id="20240-128">Child Elements</span></span>  
  
|<span data-ttu-id="20240-129">要素</span><span class="sxs-lookup"><span data-stu-id="20240-129">Element</span></span>|<span data-ttu-id="20240-130">Description</span><span class="sxs-lookup"><span data-stu-id="20240-130">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-ws2007httpbinding.md)|<span data-ttu-id="20240-131">トランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="20240-131">Defines the transport security settings.</span></span> <span data-ttu-id="20240-132">この要素は、<xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> 型に対応しています。</span><span class="sxs-lookup"><span data-stu-id="20240-132">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span> <span data-ttu-id="20240-133">これらの設定は、モードが Transport に設定されている場合のみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="20240-133">These settings are applied only when the mode is set to Transport.</span></span>|  
|[\<message>](message-of-ws2007httpbinding.md)|<span data-ttu-id="20240-134">メッセージのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="20240-134">Defines the security settings for the message.</span></span> <span data-ttu-id="20240-135">この要素は、<xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> 型に対応しています。</span><span class="sxs-lookup"><span data-stu-id="20240-135">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span> <span data-ttu-id="20240-136">これらの設定は、モードが Transport に設定されている場合は適用されません。</span><span class="sxs-lookup"><span data-stu-id="20240-136">These settings are not applied when the mode is set to Transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="20240-137">親要素</span><span class="sxs-lookup"><span data-stu-id="20240-137">Parent Elements</span></span>  
  
|<span data-ttu-id="20240-138">要素</span><span class="sxs-lookup"><span data-stu-id="20240-138">Element</span></span>|<span data-ttu-id="20240-139">Description</span><span class="sxs-lookup"><span data-stu-id="20240-139">Description</span></span>|  
|-------------|-----------------|  
|[\<ws2007HttpBinding>](ws2007httpbinding.md)|<span data-ttu-id="20240-140">HTTP トランスポート アプリケーションのセキュリティで保護されたバインド。</span><span class="sxs-lookup"><span data-stu-id="20240-140">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20240-141">解説</span><span class="sxs-lookup"><span data-stu-id="20240-141">Remarks</span></span>  
 <span data-ttu-id="20240-142">この要素は、WS-\* 仕様を実装するサービスと相互運用するようにデザインされています。</span><span class="sxs-lookup"><span data-stu-id="20240-142">This element is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="20240-143">このバインディングのトランスポート セキュリティは、SSL (Secure Sockets Layer) over HTTP または HTTPS です。</span><span class="sxs-lookup"><span data-stu-id="20240-143">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20240-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="20240-144">See also</span></span>

- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="20240-145">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="20240-145">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="20240-146">バインド</span><span class="sxs-lookup"><span data-stu-id="20240-146">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="20240-147">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="20240-147">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="20240-148">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="20240-148">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
