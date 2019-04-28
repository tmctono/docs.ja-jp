---
title: <security> の <peerTransport>
ms.date: 03/30/2017
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
ms.openlocfilehash: 1aff79bf5867a3a1ebe05e3f812475dac4b413e9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670496"
---
# <a name="security-of-peertransport"></a><span data-ttu-id="85653-102">\<セキュリティ > の\<peerTransport ></span><span class="sxs-lookup"><span data-stu-id="85653-102">\<security> of \<peerTransport></span></span>
<span data-ttu-id="85653-103">ピア チャネルに関連付けられたセキュリティ設定を格納します。使用される認証の種類とメッセージ トランスポートで使用されるセキュリティを含みます。</span><span class="sxs-lookup"><span data-stu-id="85653-103">Contains the security settings associated with a peer channel, including the type of authentication used and the security used for the message transport.</span></span>  
  
 <span data-ttu-id="85653-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="85653-104">\<system.serviceModel></span></span>  
<span data-ttu-id="85653-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="85653-105">\<bindings></span></span>  
<span data-ttu-id="85653-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="85653-106">\<customBinding></span></span>  
<span data-ttu-id="85653-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="85653-107">\<binding></span></span>  
<span data-ttu-id="85653-108">\<peerTransport ></span><span class="sxs-lookup"><span data-stu-id="85653-108">\<peerTransport></span></span>  
<span data-ttu-id="85653-109">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="85653-109">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85653-110">構文</span><span class="sxs-lookup"><span data-stu-id="85653-110">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/TransportWithMessageCredential">
  <transport clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="85653-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="85653-111">Attributes and Elements</span></span>  
 <span data-ttu-id="85653-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="85653-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="85653-113">属性</span><span class="sxs-lookup"><span data-stu-id="85653-113">Attributes</span></span>  
  
|<span data-ttu-id="85653-114">属性</span><span class="sxs-lookup"><span data-stu-id="85653-114">Attribute</span></span>|<span data-ttu-id="85653-115">説明</span><span class="sxs-lookup"><span data-stu-id="85653-115">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="85653-116">適用するセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="85653-116">Specifies the type of security to be applied.</span></span> <span data-ttu-id="85653-117">既定値は Message です。</span><span class="sxs-lookup"><span data-stu-id="85653-117">The default value is Message.</span></span> <span data-ttu-id="85653-118">この属性は <xref:System.ServiceModel.SecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="85653-118">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="85653-119">mode 属性</span><span class="sxs-lookup"><span data-stu-id="85653-119">mode Attribute</span></span>  
  
|<span data-ttu-id="85653-120">[値]</span><span class="sxs-lookup"><span data-stu-id="85653-120">Value</span></span>|<span data-ttu-id="85653-121">説明</span><span class="sxs-lookup"><span data-stu-id="85653-121">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="85653-122">セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="85653-122">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="85653-123">セキュリティは、HTTPS を使用して確保されます。</span><span class="sxs-lookup"><span data-stu-id="85653-123">Security is provided using HTTPS.</span></span>|  
|`Message`|<span data-ttu-id="85653-124">SOAP セキュリティにより、認証、整合性、および機密性が実現します。</span><span class="sxs-lookup"><span data-stu-id="85653-124">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="85653-125">HTTPS により、認証および機密性が実現します。</span><span class="sxs-lookup"><span data-stu-id="85653-125">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="85653-126">SOAP メッセージには、豊富な資格情報の種類が用意されています。</span><span class="sxs-lookup"><span data-stu-id="85653-126">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="85653-127">子要素</span><span class="sxs-lookup"><span data-stu-id="85653-127">Child Elements</span></span>  
  
|<span data-ttu-id="85653-128">要素</span><span class="sxs-lookup"><span data-stu-id="85653-128">Element</span></span>|<span data-ttu-id="85653-129">説明</span><span class="sxs-lookup"><span data-stu-id="85653-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="85653-130">\<transport></span><span class="sxs-lookup"><span data-stu-id="85653-130">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-peertransport.md)|<span data-ttu-id="85653-131">カスタム バインドのピア トランスポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="85653-131">Defines a peer transport for a custom binding.</span></span> <span data-ttu-id="85653-132">この要素には、サービスと対話するときに使用される資格情報を指定する `clientCredentialType` 属性があります。</span><span class="sxs-lookup"><span data-stu-id="85653-132">This element has a `clientCredentialType` attribute that specifies the credentials to be used when interacting with a service.</span></span> <span data-ttu-id="85653-133">この属性は <xref:System.ServiceModel.PeerTransportCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="85653-133">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span><br /><br /> <span data-ttu-id="85653-134">この要素は <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="85653-134">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="85653-135">親要素</span><span class="sxs-lookup"><span data-stu-id="85653-135">Parent Elements</span></span>  
  
|<span data-ttu-id="85653-136">要素</span><span class="sxs-lookup"><span data-stu-id="85653-136">Element</span></span>|<span data-ttu-id="85653-137">説明</span><span class="sxs-lookup"><span data-stu-id="85653-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="85653-138">\<peerTransport></span><span class="sxs-lookup"><span data-stu-id="85653-138">\<peerTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peertransport.md)|<span data-ttu-id="85653-139">カスタム バインドのピア トランスポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="85653-139">Defines a peer transport for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="85653-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="85653-140">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="85653-141">トランスポート セキュリティ</span><span class="sxs-lookup"><span data-stu-id="85653-141">Transport Security</span></span>](../../../../../docs/framework/wcf/feature-details/transport-security.md)
- [<span data-ttu-id="85653-142">トランスポート</span><span class="sxs-lookup"><span data-stu-id="85653-142">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="85653-143">トランスポートの選択</span><span class="sxs-lookup"><span data-stu-id="85653-143">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="85653-144">バインディング</span><span class="sxs-lookup"><span data-stu-id="85653-144">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="85653-145">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="85653-145">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="85653-146">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="85653-146">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="85653-147">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="85653-147">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
