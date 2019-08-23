---
title: <security> の <netPeerBinding>
ms.date: 03/30/2017
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
ms.openlocfilehash: be5ebacec466caf8d8a77bf552f42da1861e77a1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936625"
---
# <a name="security-of-netpeerbinding"></a><span data-ttu-id="a9c47-102">\<netpeerbinding \<> のセキュリティ ></span><span class="sxs-lookup"><span data-stu-id="a9c47-102">\<security> of \<netPeerBinding></span></span>
<span data-ttu-id="a9c47-103">[ \<Netpeertcpbinding >](netpeertcpbinding.md)のセキュリティ設定を定義します。これには、使用する認証の種類や、メッセージトランスポートに使用するセキュリティなどが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a9c47-103">Defines the security settings of the [\<netPeerTcpBinding>](netpeertcpbinding.md), including the type of authentication used and the security used for the message transport.</span></span>  
  
 <span data-ttu-id="a9c47-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a9c47-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a9c47-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="a9c47-105">\<bindings></span></span>  
<span data-ttu-id="a9c47-106">\<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="a9c47-106">\<netPeerBinding></span></span>  
<span data-ttu-id="a9c47-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="a9c47-107">\<binding></span></span>  
<span data-ttu-id="a9c47-108">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="a9c47-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9c47-109">構文</span><span class="sxs-lookup"><span data-stu-id="a9c47-109">Syntax</span></span>  
  
```xml  
<netPeerBinding>
  <binding>
    <security mode="Message/None/Transport//TransportWithMessageCredential">
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a9c47-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a9c47-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a9c47-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a9c47-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a9c47-112">属性</span><span class="sxs-lookup"><span data-stu-id="a9c47-112">Attributes</span></span>  
  
|<span data-ttu-id="a9c47-113">属性</span><span class="sxs-lookup"><span data-stu-id="a9c47-113">Attribute</span></span>|<span data-ttu-id="a9c47-114">説明</span><span class="sxs-lookup"><span data-stu-id="a9c47-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a9c47-115">モード</span><span class="sxs-lookup"><span data-stu-id="a9c47-115">mode</span></span>|<span data-ttu-id="a9c47-116">任意。</span><span class="sxs-lookup"><span data-stu-id="a9c47-116">Optional.</span></span> <span data-ttu-id="a9c47-117">このバインディングで構成されたピアが使用するセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="a9c47-117">Specifies the type of security used by peers configured with this binding.</span></span> <span data-ttu-id="a9c47-118">既定値は `Message` です。</span><span class="sxs-lookup"><span data-stu-id="a9c47-118">The default value is `Message`.</span></span> <span data-ttu-id="a9c47-119">この属性は <xref:System.ServiceModel.SecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="a9c47-119">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="a9c47-120">mode 属性</span><span class="sxs-lookup"><span data-stu-id="a9c47-120">mode Attribute</span></span>  
  
|<span data-ttu-id="a9c47-121">値</span><span class="sxs-lookup"><span data-stu-id="a9c47-121">Value</span></span>|<span data-ttu-id="a9c47-122">説明</span><span class="sxs-lookup"><span data-stu-id="a9c47-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a9c47-123">Message</span><span class="sxs-lookup"><span data-stu-id="a9c47-123">Message</span></span>|<span data-ttu-id="a9c47-124">SOAP セキュリティにより、認証、整合性、および機密性が実現します。</span><span class="sxs-lookup"><span data-stu-id="a9c47-124">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|<span data-ttu-id="a9c47-125">なし</span><span class="sxs-lookup"><span data-stu-id="a9c47-125">None</span></span>|<span data-ttu-id="a9c47-126">セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="a9c47-126">Security is disabled.</span></span>|  
|<span data-ttu-id="a9c47-127">Transport</span><span class="sxs-lookup"><span data-stu-id="a9c47-127">Transport</span></span>|<span data-ttu-id="a9c47-128">セキュリティは、HTTPS を使用して確保されます。</span><span class="sxs-lookup"><span data-stu-id="a9c47-128">Security is provided using HTTPS.</span></span>|  
|<span data-ttu-id="a9c47-129">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="a9c47-129">TransportWithMessageCredential</span></span>|<span data-ttu-id="a9c47-130">HTTPS により、認証および機密性が実現します。</span><span class="sxs-lookup"><span data-stu-id="a9c47-130">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="a9c47-131">SOAP メッセージには、豊富な資格情報の種類が用意されています。</span><span class="sxs-lookup"><span data-stu-id="a9c47-131">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a9c47-132">子要素</span><span class="sxs-lookup"><span data-stu-id="a9c47-132">Child Elements</span></span>  
  
|<span data-ttu-id="a9c47-133">要素</span><span class="sxs-lookup"><span data-stu-id="a9c47-133">Element</span></span>|<span data-ttu-id="a9c47-134">説明</span><span class="sxs-lookup"><span data-stu-id="a9c47-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a9c47-135">\<transport></span><span class="sxs-lookup"><span data-stu-id="a9c47-135">\<transport></span></span>](transport-of-netpeertcpbinding.md)|<span data-ttu-id="a9c47-136">このバインディングで構成されたピアが送信するセキュリティで保護されたメッセージのトランスポートの型を定義します。</span><span class="sxs-lookup"><span data-stu-id="a9c47-136">Defines the transport type for secured messages sent by peers configured with this binding.</span></span> <span data-ttu-id="a9c47-137">この要素は <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="a9c47-137">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a9c47-138">親要素</span><span class="sxs-lookup"><span data-stu-id="a9c47-138">Parent Elements</span></span>  
  
|<span data-ttu-id="a9c47-139">要素</span><span class="sxs-lookup"><span data-stu-id="a9c47-139">Element</span></span>|<span data-ttu-id="a9c47-140">説明</span><span class="sxs-lookup"><span data-stu-id="a9c47-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a9c47-141">\<binding></span><span class="sxs-lookup"><span data-stu-id="a9c47-141">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="a9c47-142">Netpeertcpbinding > のすべてのバインド機能を[ \<](netpeertcpbinding.md)定義します。</span><span class="sxs-lookup"><span data-stu-id="a9c47-142">Defines all binding capabilities of the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9c47-143">Remarks</span><span class="sxs-lookup"><span data-stu-id="a9c47-143">Remarks</span></span>  
 <span data-ttu-id="a9c47-144">セキュリティは、メッセージ固有にすることも、トランスポート固有にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a9c47-144">Security can be either message- or transport-specific.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9c47-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="a9c47-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.PeerSecuritySettings>
- [<span data-ttu-id="a9c47-146">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="a9c47-146">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="a9c47-147">資格情報の種類の選択</span><span class="sxs-lookup"><span data-stu-id="a9c47-147">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="a9c47-148">バインディング</span><span class="sxs-lookup"><span data-stu-id="a9c47-148">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a9c47-149">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="a9c47-149">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="a9c47-150">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="a9c47-150">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="a9c47-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="a9c47-151">\<binding></span></span>](../../../misc/binding.md)
