---
title: <security> の <netPeerBinding>
ms.date: 03/30/2017
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
ms.openlocfilehash: 88aa2898472c20c9e52cfd5830c0e41e8ea9ba21
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399817"
---
# <a name="security-of-netpeerbinding"></a><span data-ttu-id="097ee-102">\<netpeerbinding \<> のセキュリティ ></span><span class="sxs-lookup"><span data-stu-id="097ee-102">\<security> of \<netPeerBinding></span></span>
<span data-ttu-id="097ee-103">[ \<Netpeertcpbinding >](netpeertcpbinding.md)のセキュリティ設定を定義します。これには、使用する認証の種類や、メッセージトランスポートに使用するセキュリティなどが含まれます。</span><span class="sxs-lookup"><span data-stu-id="097ee-103">Defines the security settings of the [\<netPeerTcpBinding>](netpeertcpbinding.md), including the type of authentication used and the security used for the message transport.</span></span>  
  
<span data-ttu-id="097ee-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="097ee-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="097ee-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="097ee-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="097ee-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<バインド >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="097ee-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="097ee-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netPeerTcpBinding >** ](netpeertcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="097ee-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)</span></span>\
<span data-ttu-id="097ee-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<バインド >** </span><span class="sxs-lookup"><span data-stu-id="097ee-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="097ee-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<セキュリティ >**</span><span class="sxs-lookup"><span data-stu-id="097ee-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="097ee-110">構文</span><span class="sxs-lookup"><span data-stu-id="097ee-110">Syntax</span></span>  
  
```xml  
<netPeerBinding>
  <binding>
    <security mode="Message/None/Transport//TransportWithMessageCredential">
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="097ee-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="097ee-111">Attributes and Elements</span></span>  
 <span data-ttu-id="097ee-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="097ee-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="097ee-113">属性</span><span class="sxs-lookup"><span data-stu-id="097ee-113">Attributes</span></span>  
  
|<span data-ttu-id="097ee-114">属性</span><span class="sxs-lookup"><span data-stu-id="097ee-114">Attribute</span></span>|<span data-ttu-id="097ee-115">説明</span><span class="sxs-lookup"><span data-stu-id="097ee-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="097ee-116">モード</span><span class="sxs-lookup"><span data-stu-id="097ee-116">mode</span></span>|<span data-ttu-id="097ee-117">任意。</span><span class="sxs-lookup"><span data-stu-id="097ee-117">Optional.</span></span> <span data-ttu-id="097ee-118">このバインディングで構成されたピアが使用するセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="097ee-118">Specifies the type of security used by peers configured with this binding.</span></span> <span data-ttu-id="097ee-119">既定値は `Message` です。</span><span class="sxs-lookup"><span data-stu-id="097ee-119">The default value is `Message`.</span></span> <span data-ttu-id="097ee-120">この属性は <xref:System.ServiceModel.SecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="097ee-120">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="097ee-121">mode 属性</span><span class="sxs-lookup"><span data-stu-id="097ee-121">mode Attribute</span></span>  
  
|<span data-ttu-id="097ee-122">値</span><span class="sxs-lookup"><span data-stu-id="097ee-122">Value</span></span>|<span data-ttu-id="097ee-123">説明</span><span class="sxs-lookup"><span data-stu-id="097ee-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="097ee-124">Message</span><span class="sxs-lookup"><span data-stu-id="097ee-124">Message</span></span>|<span data-ttu-id="097ee-125">SOAP セキュリティにより、認証、整合性、および機密性が実現します。</span><span class="sxs-lookup"><span data-stu-id="097ee-125">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|<span data-ttu-id="097ee-126">なし</span><span class="sxs-lookup"><span data-stu-id="097ee-126">None</span></span>|<span data-ttu-id="097ee-127">セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="097ee-127">Security is disabled.</span></span>|  
|<span data-ttu-id="097ee-128">Transport</span><span class="sxs-lookup"><span data-stu-id="097ee-128">Transport</span></span>|<span data-ttu-id="097ee-129">セキュリティは、HTTPS を使用して確保されます。</span><span class="sxs-lookup"><span data-stu-id="097ee-129">Security is provided using HTTPS.</span></span>|  
|<span data-ttu-id="097ee-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="097ee-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="097ee-131">HTTPS により、認証および機密性が実現します。</span><span class="sxs-lookup"><span data-stu-id="097ee-131">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="097ee-132">SOAP メッセージには、豊富な資格情報の種類が用意されています。</span><span class="sxs-lookup"><span data-stu-id="097ee-132">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="097ee-133">子要素</span><span class="sxs-lookup"><span data-stu-id="097ee-133">Child Elements</span></span>  
  
|<span data-ttu-id="097ee-134">要素</span><span class="sxs-lookup"><span data-stu-id="097ee-134">Element</span></span>|<span data-ttu-id="097ee-135">説明</span><span class="sxs-lookup"><span data-stu-id="097ee-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="097ee-136">\<transport></span><span class="sxs-lookup"><span data-stu-id="097ee-136">\<transport></span></span>](transport-of-netpeertcpbinding.md)|<span data-ttu-id="097ee-137">このバインディングで構成されたピアが送信するセキュリティで保護されたメッセージのトランスポートの型を定義します。</span><span class="sxs-lookup"><span data-stu-id="097ee-137">Defines the transport type for secured messages sent by peers configured with this binding.</span></span> <span data-ttu-id="097ee-138">この要素は <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="097ee-138">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="097ee-139">親要素</span><span class="sxs-lookup"><span data-stu-id="097ee-139">Parent Elements</span></span>  
  
|<span data-ttu-id="097ee-140">要素</span><span class="sxs-lookup"><span data-stu-id="097ee-140">Element</span></span>|<span data-ttu-id="097ee-141">説明</span><span class="sxs-lookup"><span data-stu-id="097ee-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="097ee-142">\<binding></span><span class="sxs-lookup"><span data-stu-id="097ee-142">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="097ee-143">Netpeertcpbinding > のすべてのバインド機能を[ \<](netpeertcpbinding.md)定義します。</span><span class="sxs-lookup"><span data-stu-id="097ee-143">Defines all binding capabilities of the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="097ee-144">Remarks</span><span class="sxs-lookup"><span data-stu-id="097ee-144">Remarks</span></span>  
 <span data-ttu-id="097ee-145">セキュリティは、メッセージ固有にすることも、トランスポート固有にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="097ee-145">Security can be either message- or transport-specific.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="097ee-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="097ee-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.PeerSecuritySettings>
- [<span data-ttu-id="097ee-147">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="097ee-147">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="097ee-148">資格情報の種類の選択</span><span class="sxs-lookup"><span data-stu-id="097ee-148">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="097ee-149">バインディング</span><span class="sxs-lookup"><span data-stu-id="097ee-149">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="097ee-150">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="097ee-150">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="097ee-151">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="097ee-151">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="097ee-152">\<binding></span><span class="sxs-lookup"><span data-stu-id="097ee-152">\<binding></span></span>](../../../misc/binding.md)
