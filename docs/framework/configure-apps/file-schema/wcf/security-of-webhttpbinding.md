---
title: <security> の <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
ms.openlocfilehash: 77009dc950a608da9e0db3a7d09be67e1ed46137
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738640"
---
# <a name="security-of-webhttpbinding"></a><span data-ttu-id="f4969-102">\<security> の \<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="f4969-102">\<security> of \<webHttpBinding></span></span>
<span data-ttu-id="f4969-103">で構成されるエンドポイントのセキュリティ要件を指定し [\<webHttpBinding>](webhttpbinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="f4969-103">Specifies the security requirements for an endpoint configured with a [\<webHttpBinding>](webhttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<webHttpBinding>**](webhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="f4969-104">構文</span><span class="sxs-lookup"><span data-stu-id="f4969-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f4969-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f4969-105">Attributes and Elements</span></span>  
 <span data-ttu-id="f4969-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f4969-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f4969-107">属性</span><span class="sxs-lookup"><span data-stu-id="f4969-107">Attributes</span></span>  
  
|<span data-ttu-id="f4969-108">属性</span><span class="sxs-lookup"><span data-stu-id="f4969-108">Attribute</span></span>|<span data-ttu-id="f4969-109">説明</span><span class="sxs-lookup"><span data-stu-id="f4969-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f4969-110">mode</span><span class="sxs-lookup"><span data-stu-id="f4969-110">mode</span></span>|<span data-ttu-id="f4969-111">トランスポート レベルのセキュリティをエンドポイントで使用するか、セキュリティを使用しないかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f4969-111">Specifies whether transport-level security or no security is used by an endpoint.</span></span> <span data-ttu-id="f4969-112">既定値は、`None` です。</span><span class="sxs-lookup"><span data-stu-id="f4969-112">The default is `None`.</span></span> <span data-ttu-id="f4969-113">この属性は <xref:System.ServiceModel.WebHttpSecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="f4969-113">This attribute is of type <xref:System.ServiceModel.WebHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="f4969-114">Mode 属性</span><span class="sxs-lookup"><span data-stu-id="f4969-114">Mode Attribute</span></span>  
  
|<span data-ttu-id="f4969-115">値</span><span class="sxs-lookup"><span data-stu-id="f4969-115">Value</span></span>|<span data-ttu-id="f4969-116">説明</span><span class="sxs-lookup"><span data-stu-id="f4969-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f4969-117">なし</span><span class="sxs-lookup"><span data-stu-id="f4969-117">None</span></span>|<span data-ttu-id="f4969-118">セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="f4969-118">Security is disabled.</span></span>|  
|<span data-ttu-id="f4969-119">トランスポート</span><span class="sxs-lookup"><span data-stu-id="f4969-119">Transport</span></span>|<span data-ttu-id="f4969-120">セキュリティは、HTTPS を使用して確保されます。</span><span class="sxs-lookup"><span data-stu-id="f4969-120">Security is provided using HTTPS.</span></span> <span data-ttu-id="f4969-121">サービスは、SSL 証明書を使用して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4969-121">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="f4969-122">メッセージは、HTTPS およびサービスを使用して完全にセキュリティで保護され、サービスの SSL 証明書を使用するクライアントによって認証されます。</span><span class="sxs-lookup"><span data-stu-id="f4969-122">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="f4969-123">クライアント認証は、の属性によって制御され `ClientCredentialType` [\<transport>](transport-of-webhttpbinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="f4969-123">The client authentication is controlled through the `ClientCredentialType` attribute of the [\<transport>](transport-of-webhttpbinding.md).</span></span>|  
|<span data-ttu-id="f4969-124">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="f4969-124">TransportCredentialOnly</span></span>|<span data-ttu-id="f4969-125">このモードは、メッセージの整合性と機密性を提供しません。</span><span class="sxs-lookup"><span data-stu-id="f4969-125">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="f4969-126">HTTP ベースのクライアント認証を提供します。</span><span class="sxs-lookup"><span data-stu-id="f4969-126">It provides HTTP-based client authentication.</span></span> <span data-ttu-id="f4969-127">このモードを使用するときは、十分に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4969-127">This mode should be used with caution.</span></span> <span data-ttu-id="f4969-128">トランスポートセキュリティが他の方法 (IPSec など) によって提供され、WCF インフラストラクチャによってクライアント認証のみが提供される環境で使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4969-128">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f4969-129">子要素</span><span class="sxs-lookup"><span data-stu-id="f4969-129">Child Elements</span></span>  
  
|<span data-ttu-id="f4969-130">要素</span><span class="sxs-lookup"><span data-stu-id="f4969-130">Element</span></span>|<span data-ttu-id="f4969-131">Description</span><span class="sxs-lookup"><span data-stu-id="f4969-131">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-webhttpbinding.md)|<span data-ttu-id="f4969-132">トランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="f4969-132">Defines the transport security settings.</span></span> <span data-ttu-id="f4969-133">この要素は、<xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> 型に対応しています。</span><span class="sxs-lookup"><span data-stu-id="f4969-133">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f4969-134">親要素</span><span class="sxs-lookup"><span data-stu-id="f4969-134">Parent Elements</span></span>  
  
|<span data-ttu-id="f4969-135">要素</span><span class="sxs-lookup"><span data-stu-id="f4969-135">Element</span></span>|<span data-ttu-id="f4969-136">Description</span><span class="sxs-lookup"><span data-stu-id="f4969-136">Description</span></span>|  
|-------------|-----------------|  
|[\<webHttpBinding>](webhttpbinding.md)|<span data-ttu-id="f4969-137">SOAP メッセージではなく HTTP 要求に応答する Windows Communication Foundation (WCF) Web サービスのエンドポイントを構成するために使用されるバインド要素。</span><span class="sxs-lookup"><span data-stu-id="f4969-137">A binding element that is used to configure endpoints for Windows Communication Foundation (WCF) Web services that respond to HTTP requests instead of SOAP messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f4969-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="f4969-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpBindingElement>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.WebHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.WebHttpSecurity>
- [<span data-ttu-id="f4969-139">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="f4969-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="f4969-140">資格情報の種類の選択</span><span class="sxs-lookup"><span data-stu-id="f4969-140">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="f4969-141">バインド</span><span class="sxs-lookup"><span data-stu-id="f4969-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="f4969-142">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="f4969-142">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="f4969-143">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="f4969-143">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- [<span data-ttu-id="f4969-144">WCF Web HTTP プログラミング モデル</span><span class="sxs-lookup"><span data-stu-id="f4969-144">WCF Web HTTP Programming Model</span></span>](../../../wcf/feature-details/wcf-web-http-programming-model.md)
