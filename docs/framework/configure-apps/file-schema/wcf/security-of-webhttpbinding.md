---
title: <security> の <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
ms.openlocfilehash: 77009dc950a608da9e0db3a7d09be67e1ed46137
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738640"
---
# <a name="security-of-webhttpbinding"></a><span data-ttu-id="44200-102">\<webHttpBinding > のセキュリティ > の \<</span><span class="sxs-lookup"><span data-stu-id="44200-102">\<security> of \<webHttpBinding></span></span>
<span data-ttu-id="44200-103">[\<webHttpBinding >](webhttpbinding.md)で構成されたエンドポイントのセキュリティ要件を指定します。</span><span class="sxs-lookup"><span data-stu-id="44200-103">Specifies the security requirements for an endpoint configured with a [\<webHttpBinding>](webhttpbinding.md).</span></span>  
  
<span data-ttu-id="44200-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="44200-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="44200-105">&nbsp; &nbsp;[ **\<system >** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="44200-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="44200-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**バインド**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="44200-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="44200-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<webHttpBinding >** ](webhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="44200-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<webHttpBinding>**](webhttpbinding.md)</span></span>\
<span data-ttu-id="44200-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**バインド >** </span><span class="sxs-lookup"><span data-stu-id="44200-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="44200-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**セキュリティ >**</span><span class="sxs-lookup"><span data-stu-id="44200-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44200-110">構文</span><span class="sxs-lookup"><span data-stu-id="44200-110">Syntax</span></span>  
  
```xml  
<system.ServiceModel>
  <bindings>
    <webHttpBinding>
      <binding name = "String">
        <security mode="None/Transport/TransportCredentialOnly">
          <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
                     proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
                     realm="String" />
        </security>
      </binding>
    </webHttpBinding>
  </bindings>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="44200-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="44200-111">Attributes and Elements</span></span>  
 <span data-ttu-id="44200-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="44200-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="44200-113">属性</span><span class="sxs-lookup"><span data-stu-id="44200-113">Attributes</span></span>  
  
|<span data-ttu-id="44200-114">属性</span><span class="sxs-lookup"><span data-stu-id="44200-114">Attribute</span></span>|<span data-ttu-id="44200-115">説明</span><span class="sxs-lookup"><span data-stu-id="44200-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="44200-116">モード</span><span class="sxs-lookup"><span data-stu-id="44200-116">mode</span></span>|<span data-ttu-id="44200-117">トランスポート レベルのセキュリティをエンドポイントで使用するか、セキュリティを使用しないかを指定します。</span><span class="sxs-lookup"><span data-stu-id="44200-117">Specifies whether transport-level security or no security is used by an endpoint.</span></span> <span data-ttu-id="44200-118">既定値は、 `None`です。</span><span class="sxs-lookup"><span data-stu-id="44200-118">The default is `None`.</span></span> <span data-ttu-id="44200-119">この属性は <xref:System.ServiceModel.WebHttpSecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="44200-119">This attribute is of type <xref:System.ServiceModel.WebHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="44200-120">Mode 属性</span><span class="sxs-lookup"><span data-stu-id="44200-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="44200-121">[値]</span><span class="sxs-lookup"><span data-stu-id="44200-121">Value</span></span>|<span data-ttu-id="44200-122">説明</span><span class="sxs-lookup"><span data-stu-id="44200-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="44200-123">None</span><span class="sxs-lookup"><span data-stu-id="44200-123">None</span></span>|<span data-ttu-id="44200-124">セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="44200-124">Security is disabled.</span></span>|  
|<span data-ttu-id="44200-125">Transport</span><span class="sxs-lookup"><span data-stu-id="44200-125">Transport</span></span>|<span data-ttu-id="44200-126">セキュリティは、HTTPS を使用して確保されます。</span><span class="sxs-lookup"><span data-stu-id="44200-126">Security is provided using HTTPS.</span></span> <span data-ttu-id="44200-127">サービスは、SSL 証明書を使用して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="44200-127">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="44200-128">メッセージは、HTTPS およびサービスを使用して完全にセキュリティで保護され、サービスの SSL 証明書を使用するクライアントによって認証されます。</span><span class="sxs-lookup"><span data-stu-id="44200-128">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="44200-129">クライアント認証は、 [\<トランスポート >](transport-of-webhttpbinding.md)の `ClientCredentialType` 属性によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="44200-129">The client authentication is controlled through the `ClientCredentialType` attribute of the [\<transport>](transport-of-webhttpbinding.md).</span></span>|  
|<span data-ttu-id="44200-130">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="44200-130">TransportCredentialOnly</span></span>|<span data-ttu-id="44200-131">このモードは、メッセージの整合性と機密性を提供しません。</span><span class="sxs-lookup"><span data-stu-id="44200-131">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="44200-132">HTTP ベースのクライアント認証を提供します。</span><span class="sxs-lookup"><span data-stu-id="44200-132">It provides HTTP-based client authentication.</span></span> <span data-ttu-id="44200-133">このモードを使用するときは、十分に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="44200-133">This mode should be used with caution.</span></span> <span data-ttu-id="44200-134">トランスポートセキュリティが他の方法 (IPSec など) によって提供され、WCF インフラストラクチャによってクライアント認証のみが提供される環境で使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="44200-134">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="44200-135">子要素</span><span class="sxs-lookup"><span data-stu-id="44200-135">Child Elements</span></span>  
  
|<span data-ttu-id="44200-136">要素</span><span class="sxs-lookup"><span data-stu-id="44200-136">Element</span></span>|<span data-ttu-id="44200-137">説明</span><span class="sxs-lookup"><span data-stu-id="44200-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="44200-138">\<transport ></span><span class="sxs-lookup"><span data-stu-id="44200-138">\<transport></span></span>](transport-of-webhttpbinding.md)|<span data-ttu-id="44200-139">トランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="44200-139">Defines the transport security settings.</span></span> <span data-ttu-id="44200-140">この要素は、<xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> 型に対応しています。</span><span class="sxs-lookup"><span data-stu-id="44200-140">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="44200-141">親要素</span><span class="sxs-lookup"><span data-stu-id="44200-141">Parent Elements</span></span>  
  
|<span data-ttu-id="44200-142">要素</span><span class="sxs-lookup"><span data-stu-id="44200-142">Element</span></span>|<span data-ttu-id="44200-143">説明</span><span class="sxs-lookup"><span data-stu-id="44200-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="44200-144">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="44200-144">\<webHttpBinding></span></span>](webhttpbinding.md)|<span data-ttu-id="44200-145">SOAP メッセージではなく HTTP 要求に応答する Windows Communication Foundation (WCF) Web サービスのエンドポイントを構成するために使用されるバインド要素。</span><span class="sxs-lookup"><span data-stu-id="44200-145">A binding element that is used to configure endpoints for Windows Communication Foundation (WCF) Web services that respond to HTTP requests instead of SOAP messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="44200-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="44200-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpBindingElement>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.WebHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.WebHttpSecurity>
- [<span data-ttu-id="44200-147">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="44200-147">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="44200-148">資格情報の種類の選択</span><span class="sxs-lookup"><span data-stu-id="44200-148">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="44200-149">バインディング</span><span class="sxs-lookup"><span data-stu-id="44200-149">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="44200-150">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="44200-150">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="44200-151">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="44200-151">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="44200-152">\<binding ></span><span class="sxs-lookup"><span data-stu-id="44200-152">\<binding></span></span>](bindings.md)
- [<span data-ttu-id="44200-153">WCF Web HTTP プログラミング モデル</span><span class="sxs-lookup"><span data-stu-id="44200-153">WCF Web HTTP Programming Model</span></span>](../../../wcf/feature-details/wcf-web-http-programming-model.md)
