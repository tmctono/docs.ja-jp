---
title: <security> の <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
ms.openlocfilehash: 806cf8524ed1a1439ca85a4b918e8e486e5dc94b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936584"
---
# <a name="security-of-webhttpbinding"></a><span data-ttu-id="4873a-102">\<webHttpBinding > の\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="4873a-102">\<security> of \<webHttpBinding></span></span>
<span data-ttu-id="4873a-103">[ \<WebHttpBinding >](webhttpbinding.md)で構成されたエンドポイントのセキュリティ要件を指定します。</span><span class="sxs-lookup"><span data-stu-id="4873a-103">Specifies the security requirements for an endpoint configured with a [\<webHttpBinding>](webhttpbinding.md).</span></span>  
  
 <span data-ttu-id="4873a-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="4873a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="4873a-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="4873a-105">\<bindings></span></span>  
<span data-ttu-id="4873a-106">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="4873a-106">\<webHttpBinding></span></span>  
<span data-ttu-id="4873a-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="4873a-107">\<binding></span></span>  
<span data-ttu-id="4873a-108">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="4873a-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4873a-109">構文</span><span class="sxs-lookup"><span data-stu-id="4873a-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4873a-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4873a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4873a-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4873a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4873a-112">属性</span><span class="sxs-lookup"><span data-stu-id="4873a-112">Attributes</span></span>  
  
|<span data-ttu-id="4873a-113">属性</span><span class="sxs-lookup"><span data-stu-id="4873a-113">Attribute</span></span>|<span data-ttu-id="4873a-114">説明</span><span class="sxs-lookup"><span data-stu-id="4873a-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4873a-115">モード</span><span class="sxs-lookup"><span data-stu-id="4873a-115">mode</span></span>|<span data-ttu-id="4873a-116">トランスポート レベルのセキュリティをエンドポイントで使用するか、セキュリティを使用しないかを指定します。</span><span class="sxs-lookup"><span data-stu-id="4873a-116">Specifies whether transport-level security or no security is used by an endpoint.</span></span> <span data-ttu-id="4873a-117">既定値は `None` です。</span><span class="sxs-lookup"><span data-stu-id="4873a-117">The default is `None`.</span></span> <span data-ttu-id="4873a-118">この属性は <xref:System.ServiceModel.WebHttpSecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="4873a-118">This attribute is of type <xref:System.ServiceModel.WebHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="4873a-119">Mode 属性</span><span class="sxs-lookup"><span data-stu-id="4873a-119">Mode Attribute</span></span>  
  
|<span data-ttu-id="4873a-120">値</span><span class="sxs-lookup"><span data-stu-id="4873a-120">Value</span></span>|<span data-ttu-id="4873a-121">説明</span><span class="sxs-lookup"><span data-stu-id="4873a-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4873a-122">なし</span><span class="sxs-lookup"><span data-stu-id="4873a-122">None</span></span>|<span data-ttu-id="4873a-123">セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="4873a-123">Security is disabled.</span></span>|  
|<span data-ttu-id="4873a-124">Transport</span><span class="sxs-lookup"><span data-stu-id="4873a-124">Transport</span></span>|<span data-ttu-id="4873a-125">セキュリティは、HTTPS を使用して確保されます。</span><span class="sxs-lookup"><span data-stu-id="4873a-125">Security is provided using HTTPS.</span></span> <span data-ttu-id="4873a-126">サービスは、SSL 証明書を使用して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4873a-126">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="4873a-127">メッセージは、HTTPS およびサービスを使用して完全にセキュリティで保護され、サービスの SSL 証明書を使用するクライアントによって認証されます。</span><span class="sxs-lookup"><span data-stu-id="4873a-127">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="4873a-128">クライアント認証は、 [ \<トランスポート >](transport-of-webhttpbinding.md)の`ClientCredentialType`属性によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="4873a-128">The client authentication is controlled through the `ClientCredentialType` attribute of the [\<transport>](transport-of-webhttpbinding.md).</span></span>|  
|<span data-ttu-id="4873a-129">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="4873a-129">TransportCredentialOnly</span></span>|<span data-ttu-id="4873a-130">このモードは、メッセージの整合性と機密性を提供しません。</span><span class="sxs-lookup"><span data-stu-id="4873a-130">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="4873a-131">HTTP ベースのクライアント認証が提供されます。</span><span class="sxs-lookup"><span data-stu-id="4873a-131">It provides HTTP-based client authentication.</span></span> <span data-ttu-id="4873a-132">このモードは注意して使用してください。</span><span class="sxs-lookup"><span data-stu-id="4873a-132">This mode should be used with caution.</span></span> <span data-ttu-id="4873a-133">トランスポートセキュリティが他の方法 (IPSec など) によって提供され、WCF インフラストラクチャによってクライアント認証のみが提供される環境で使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4873a-133">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4873a-134">子要素</span><span class="sxs-lookup"><span data-stu-id="4873a-134">Child Elements</span></span>  
  
|<span data-ttu-id="4873a-135">要素</span><span class="sxs-lookup"><span data-stu-id="4873a-135">Element</span></span>|<span data-ttu-id="4873a-136">説明</span><span class="sxs-lookup"><span data-stu-id="4873a-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4873a-137">\<transport></span><span class="sxs-lookup"><span data-stu-id="4873a-137">\<transport></span></span>](transport-of-webhttpbinding.md)|<span data-ttu-id="4873a-138">トランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="4873a-138">Defines the transport security settings.</span></span> <span data-ttu-id="4873a-139">この要素は、<xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> 型に対応しています。</span><span class="sxs-lookup"><span data-stu-id="4873a-139">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4873a-140">親要素</span><span class="sxs-lookup"><span data-stu-id="4873a-140">Parent Elements</span></span>  
  
|<span data-ttu-id="4873a-141">要素</span><span class="sxs-lookup"><span data-stu-id="4873a-141">Element</span></span>|<span data-ttu-id="4873a-142">説明</span><span class="sxs-lookup"><span data-stu-id="4873a-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4873a-143">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="4873a-143">\<webHttpBinding></span></span>](webhttpbinding.md)|<span data-ttu-id="4873a-144">SOAP メッセージではなく HTTP 要求に応答する Windows Communication Foundation (WCF) Web サービスのエンドポイントを構成するために使用されるバインド要素。</span><span class="sxs-lookup"><span data-stu-id="4873a-144">A binding element that is used to configure endpoints for Windows Communication Foundation (WCF) Web services that respond to HTTP requests instead of SOAP messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4873a-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="4873a-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpBindingElement>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.WebHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.WebHttpSecurity>
- [<span data-ttu-id="4873a-146">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="4873a-146">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="4873a-147">資格情報の種類の選択</span><span class="sxs-lookup"><span data-stu-id="4873a-147">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="4873a-148">バインディング</span><span class="sxs-lookup"><span data-stu-id="4873a-148">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="4873a-149">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="4873a-149">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="4873a-150">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="4873a-150">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="4873a-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="4873a-151">\<binding></span></span>](../../../misc/binding.md)
- [<span data-ttu-id="4873a-152">WCF Web HTTP プログラミング モデル</span><span class="sxs-lookup"><span data-stu-id="4873a-152">WCF Web HTTP Programming Model</span></span>](../../../wcf/feature-details/wcf-web-http-programming-model.md)
