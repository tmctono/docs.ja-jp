---
title: <security> の <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
ms.openlocfilehash: 60b863a0a2a846a60dde2e4b323a305b5096b1cc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169896"
---
# <a name="security-of-webhttpbinding"></a><span data-ttu-id="9ab6b-102">\<security> の \<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="9ab6b-102">\<security> of \<webHttpBinding></span></span>

<span data-ttu-id="9ab6b-103">で構成されるエンドポイントのセキュリティ要件を指定し [\<webHttpBinding>](webhttpbinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-103">Specifies the security requirements for an endpoint configured with a [\<webHttpBinding>](webhttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<webHttpBinding>**](webhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="9ab6b-104">構文</span><span class="sxs-lookup"><span data-stu-id="9ab6b-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9ab6b-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9ab6b-105">Attributes and Elements</span></span>  

 <span data-ttu-id="9ab6b-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9ab6b-107">属性</span><span class="sxs-lookup"><span data-stu-id="9ab6b-107">Attributes</span></span>  
  
|<span data-ttu-id="9ab6b-108">属性</span><span class="sxs-lookup"><span data-stu-id="9ab6b-108">Attribute</span></span>|<span data-ttu-id="9ab6b-109">[説明]</span><span class="sxs-lookup"><span data-stu-id="9ab6b-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9ab6b-110">mode</span><span class="sxs-lookup"><span data-stu-id="9ab6b-110">mode</span></span>|<span data-ttu-id="9ab6b-111">トランスポート レベルのセキュリティをエンドポイントで使用するか、セキュリティを使用しないかを指定します。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-111">Specifies whether transport-level security or no security is used by an endpoint.</span></span> <span data-ttu-id="9ab6b-112">既定では、 `None`です。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-112">The default is `None`.</span></span> <span data-ttu-id="9ab6b-113">この属性は <xref:System.ServiceModel.WebHttpSecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-113">This attribute is of type <xref:System.ServiceModel.WebHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="9ab6b-114">Mode 属性</span><span class="sxs-lookup"><span data-stu-id="9ab6b-114">Mode Attribute</span></span>  
  
|<span data-ttu-id="9ab6b-115">値</span><span class="sxs-lookup"><span data-stu-id="9ab6b-115">Value</span></span>|<span data-ttu-id="9ab6b-116">説明</span><span class="sxs-lookup"><span data-stu-id="9ab6b-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9ab6b-117">None</span><span class="sxs-lookup"><span data-stu-id="9ab6b-117">None</span></span>|<span data-ttu-id="9ab6b-118">セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-118">Security is disabled.</span></span>|  
|<span data-ttu-id="9ab6b-119">トランスポート</span><span class="sxs-lookup"><span data-stu-id="9ab6b-119">Transport</span></span>|<span data-ttu-id="9ab6b-120">セキュリティは、HTTPS を使用して確保されます。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-120">Security is provided using HTTPS.</span></span> <span data-ttu-id="9ab6b-121">サービスは、SSL 証明書を使用して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-121">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="9ab6b-122">メッセージは、HTTPS およびサービスを使用して完全にセキュリティで保護され、サービスの SSL 証明書を使用するクライアントによって認証されます。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-122">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="9ab6b-123">クライアント認証は、の属性によって制御され `ClientCredentialType` [\<transport>](transport-of-webhttpbinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-123">The client authentication is controlled through the `ClientCredentialType` attribute of the [\<transport>](transport-of-webhttpbinding.md).</span></span>|  
|<span data-ttu-id="9ab6b-124">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="9ab6b-124">TransportCredentialOnly</span></span>|<span data-ttu-id="9ab6b-125">このモードは、メッセージの整合性と機密性を提供しません。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-125">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="9ab6b-126">HTTP ベースのクライアント認証を提供します。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-126">It provides HTTP-based client authentication.</span></span> <span data-ttu-id="9ab6b-127">このモードを使用するときは、十分に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-127">This mode should be used with caution.</span></span> <span data-ttu-id="9ab6b-128">トランスポートセキュリティが他の方法 (IPSec など) によって提供され、WCF インフラストラクチャによってクライアント認証のみが提供される環境で使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-128">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9ab6b-129">子要素</span><span class="sxs-lookup"><span data-stu-id="9ab6b-129">Child Elements</span></span>  
  
|<span data-ttu-id="9ab6b-130">要素</span><span class="sxs-lookup"><span data-stu-id="9ab6b-130">Element</span></span>|<span data-ttu-id="9ab6b-131">説明</span><span class="sxs-lookup"><span data-stu-id="9ab6b-131">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-webhttpbinding.md)|<span data-ttu-id="9ab6b-132">トランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-132">Defines the transport security settings.</span></span> <span data-ttu-id="9ab6b-133">この要素は、<xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> 型に対応しています。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-133">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9ab6b-134">親要素</span><span class="sxs-lookup"><span data-stu-id="9ab6b-134">Parent Elements</span></span>  
  
|<span data-ttu-id="9ab6b-135">要素</span><span class="sxs-lookup"><span data-stu-id="9ab6b-135">Element</span></span>|<span data-ttu-id="9ab6b-136">説明</span><span class="sxs-lookup"><span data-stu-id="9ab6b-136">Description</span></span>|  
|-------------|-----------------|  
|[\<webHttpBinding>](webhttpbinding.md)|<span data-ttu-id="9ab6b-137">SOAP メッセージではなく HTTP 要求に応答する Windows Communication Foundation (WCF) Web サービスのエンドポイントを構成するために使用されるバインド要素。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-137">A binding element that is used to configure endpoints for Windows Communication Foundation (WCF) Web services that respond to HTTP requests instead of SOAP messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9ab6b-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="9ab6b-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpBindingElement>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.WebHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.WebHttpSecurity>
- [<span data-ttu-id="9ab6b-139">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="9ab6b-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="9ab6b-140">資格情報の種類の選択</span><span class="sxs-lookup"><span data-stu-id="9ab6b-140">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="9ab6b-141">バインド</span><span class="sxs-lookup"><span data-stu-id="9ab6b-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="9ab6b-142">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="9ab6b-142">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="9ab6b-143">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="9ab6b-143">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- [<span data-ttu-id="9ab6b-144">WCF Web HTTP プログラミング モデル</span><span class="sxs-lookup"><span data-stu-id="9ab6b-144">WCF Web HTTP Programming Model</span></span>](../../../wcf/feature-details/wcf-web-http-programming-model.md)
