---
title: <security> の <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
ms.openlocfilehash: 788d49239b8b9161a35705295705e6d42eff7837
ms.sourcegitcommit: 7e129d879ddb42a8b4334eee35727afe3d437952
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2019
ms.locfileid: "66052162"
---
# <a name="security-of-webhttpbinding"></a><span data-ttu-id="14aff-102">\<セキュリティ > の\<webHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="14aff-102">\<security> of \<webHttpBinding></span></span>
<span data-ttu-id="14aff-103">構成されているエンドポイントのセキュリティ要件を指定します、 [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)します。</span><span class="sxs-lookup"><span data-stu-id="14aff-103">Specifies the security requirements for an endpoint configured with a [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md).</span></span>  
  
 <span data-ttu-id="14aff-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="14aff-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="14aff-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="14aff-105">\<bindings></span></span>  
<span data-ttu-id="14aff-106">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="14aff-106">\<webHttpBinding></span></span>  
<span data-ttu-id="14aff-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="14aff-107">\<binding></span></span>  
<span data-ttu-id="14aff-108">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="14aff-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14aff-109">構文</span><span class="sxs-lookup"><span data-stu-id="14aff-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14aff-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="14aff-110">Attributes and Elements</span></span>  
 <span data-ttu-id="14aff-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="14aff-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14aff-112">属性</span><span class="sxs-lookup"><span data-stu-id="14aff-112">Attributes</span></span>  
  
|<span data-ttu-id="14aff-113">属性</span><span class="sxs-lookup"><span data-stu-id="14aff-113">Attribute</span></span>|<span data-ttu-id="14aff-114">説明</span><span class="sxs-lookup"><span data-stu-id="14aff-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="14aff-115">モード</span><span class="sxs-lookup"><span data-stu-id="14aff-115">mode</span></span>|<span data-ttu-id="14aff-116">トランスポート レベルのセキュリティをエンドポイントで使用するか、セキュリティを使用しないかを指定します。</span><span class="sxs-lookup"><span data-stu-id="14aff-116">Specifies whether transport-level security or no security is used by an endpoint.</span></span> <span data-ttu-id="14aff-117">既定値は `None` です。</span><span class="sxs-lookup"><span data-stu-id="14aff-117">The default is `None`.</span></span> <span data-ttu-id="14aff-118">この属性は <xref:System.ServiceModel.WebHttpSecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="14aff-118">This attribute is of type <xref:System.ServiceModel.WebHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="14aff-119">Mode 属性</span><span class="sxs-lookup"><span data-stu-id="14aff-119">Mode Attribute</span></span>  
  
|<span data-ttu-id="14aff-120">値</span><span class="sxs-lookup"><span data-stu-id="14aff-120">Value</span></span>|<span data-ttu-id="14aff-121">説明</span><span class="sxs-lookup"><span data-stu-id="14aff-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="14aff-122">なし</span><span class="sxs-lookup"><span data-stu-id="14aff-122">None</span></span>|<span data-ttu-id="14aff-123">セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="14aff-123">Security is disabled.</span></span>|  
|<span data-ttu-id="14aff-124">Transport</span><span class="sxs-lookup"><span data-stu-id="14aff-124">Transport</span></span>|<span data-ttu-id="14aff-125">セキュリティは、HTTPS を使用して確保されます。</span><span class="sxs-lookup"><span data-stu-id="14aff-125">Security is provided using HTTPS.</span></span> <span data-ttu-id="14aff-126">サービスは、SSL 証明書を使用して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14aff-126">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="14aff-127">メッセージは、HTTPS およびサービスを使用して完全にセキュリティで保護され、サービスの SSL 証明書を使用するクライアントによって認証されます。</span><span class="sxs-lookup"><span data-stu-id="14aff-127">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="14aff-128">クライアント認証はによって制御されます、`ClientCredentialType`の属性、 [\<トランスポート >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md)します。</span><span class="sxs-lookup"><span data-stu-id="14aff-128">The client authentication is controlled through the `ClientCredentialType` attribute of the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md).</span></span>|  
|<span data-ttu-id="14aff-129">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="14aff-129">TransportCredentialOnly</span></span>|<span data-ttu-id="14aff-130">このモードは、メッセージの整合性と機密性を提供しません。</span><span class="sxs-lookup"><span data-stu-id="14aff-130">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="14aff-131">HTTP ベースのクライアント認証を提供します。</span><span class="sxs-lookup"><span data-stu-id="14aff-131">It provides HTTP-based client authentication.</span></span> <span data-ttu-id="14aff-132">このモードを使用するときは、十分に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14aff-132">This mode should be used with caution.</span></span> <span data-ttu-id="14aff-133">これは、トランスポート セキュリティ (IPSec) などの他の方法で提供されるされ、クライアント認証だけが、WCF インフラストラクチャによって提供される環境で使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14aff-133">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="14aff-134">子要素</span><span class="sxs-lookup"><span data-stu-id="14aff-134">Child Elements</span></span>  
  
|<span data-ttu-id="14aff-135">要素</span><span class="sxs-lookup"><span data-stu-id="14aff-135">Element</span></span>|<span data-ttu-id="14aff-136">説明</span><span class="sxs-lookup"><span data-stu-id="14aff-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="14aff-137">\<transport></span><span class="sxs-lookup"><span data-stu-id="14aff-137">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md)|<span data-ttu-id="14aff-138">トランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="14aff-138">Defines the transport security settings.</span></span> <span data-ttu-id="14aff-139">この要素は、<xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> 型に対応しています。</span><span class="sxs-lookup"><span data-stu-id="14aff-139">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="14aff-140">親要素</span><span class="sxs-lookup"><span data-stu-id="14aff-140">Parent Elements</span></span>  
  
|<span data-ttu-id="14aff-141">要素</span><span class="sxs-lookup"><span data-stu-id="14aff-141">Element</span></span>|<span data-ttu-id="14aff-142">説明</span><span class="sxs-lookup"><span data-stu-id="14aff-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="14aff-143">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="14aff-143">\<webHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)|<span data-ttu-id="14aff-144">Windows Communication Foundation (WCF) Web サービスの SOAP メッセージに代わって HTTP 要求に応答するエンドポイントを構成するために使用するバインド要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="14aff-144">A binding element that is used to configure endpoints for Windows Communication Foundation (WCF) Web services that respond to HTTP requests instead of SOAP messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="14aff-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="14aff-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpBindingElement>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.WebHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.WebHttpSecurity>
- [<span data-ttu-id="14aff-146">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="14aff-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="14aff-147">資格情報の種類の選択</span><span class="sxs-lookup"><span data-stu-id="14aff-147">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="14aff-148">バインディング</span><span class="sxs-lookup"><span data-stu-id="14aff-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="14aff-149">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="14aff-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="14aff-150">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="14aff-150">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="14aff-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="14aff-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
- [<span data-ttu-id="14aff-152">WCF Web HTTP プログラミング モデル</span><span class="sxs-lookup"><span data-stu-id="14aff-152">WCF Web HTTP Programming Model</span></span>](../../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
