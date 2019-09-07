---
title: <security> の <peerTransport>
ms.date: 03/30/2017
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
ms.openlocfilehash: 270ca844f586be256b6483653c868d1cc4396657
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399778"
---
# <a name="security-of-peertransport"></a><span data-ttu-id="4250b-102">\<peertransport > \<のセキュリティ ></span><span class="sxs-lookup"><span data-stu-id="4250b-102">\<security> of \<peerTransport></span></span>
<span data-ttu-id="4250b-103">ピア チャネルに関連付けられたセキュリティ設定を格納します。使用される認証の種類とメッセージ トランスポートで使用されるセキュリティを含みます。</span><span class="sxs-lookup"><span data-stu-id="4250b-103">Contains the security settings associated with a peer channel, including the type of authentication used and the security used for the message transport.</span></span>  
  
<span data-ttu-id="4250b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4250b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4250b-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="4250b-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="4250b-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<バインド >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="4250b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="4250b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="4250b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="4250b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<バインド >** </span><span class="sxs-lookup"><span data-stu-id="4250b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="4250b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<peerTransport >** ](peertransport.md)</span><span class="sxs-lookup"><span data-stu-id="4250b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peerTransport>**](peertransport.md)</span></span>\
<span data-ttu-id="4250b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<セキュリティ >**</span><span class="sxs-lookup"><span data-stu-id="4250b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4250b-111">構文</span><span class="sxs-lookup"><span data-stu-id="4250b-111">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/TransportWithMessageCredential">
  <transport clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4250b-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4250b-112">Attributes and Elements</span></span>  
 <span data-ttu-id="4250b-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4250b-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4250b-114">属性</span><span class="sxs-lookup"><span data-stu-id="4250b-114">Attributes</span></span>  
  
|<span data-ttu-id="4250b-115">属性</span><span class="sxs-lookup"><span data-stu-id="4250b-115">Attribute</span></span>|<span data-ttu-id="4250b-116">説明</span><span class="sxs-lookup"><span data-stu-id="4250b-116">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="4250b-117">適用するセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="4250b-117">Specifies the type of security to be applied.</span></span> <span data-ttu-id="4250b-118">既定値は Message です。</span><span class="sxs-lookup"><span data-stu-id="4250b-118">The default value is Message.</span></span> <span data-ttu-id="4250b-119">この属性は <xref:System.ServiceModel.SecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="4250b-119">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="4250b-120">mode 属性</span><span class="sxs-lookup"><span data-stu-id="4250b-120">mode Attribute</span></span>  
  
|<span data-ttu-id="4250b-121">値</span><span class="sxs-lookup"><span data-stu-id="4250b-121">Value</span></span>|<span data-ttu-id="4250b-122">説明</span><span class="sxs-lookup"><span data-stu-id="4250b-122">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="4250b-123">セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="4250b-123">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="4250b-124">セキュリティは、HTTPS を使用して確保されます。</span><span class="sxs-lookup"><span data-stu-id="4250b-124">Security is provided using HTTPS.</span></span>|  
|`Message`|<span data-ttu-id="4250b-125">SOAP セキュリティにより、認証、整合性、および機密性が実現します。</span><span class="sxs-lookup"><span data-stu-id="4250b-125">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="4250b-126">HTTPS により、認証および機密性が実現します。</span><span class="sxs-lookup"><span data-stu-id="4250b-126">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="4250b-127">SOAP メッセージには、豊富な資格情報の種類が用意されています。</span><span class="sxs-lookup"><span data-stu-id="4250b-127">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4250b-128">子要素</span><span class="sxs-lookup"><span data-stu-id="4250b-128">Child Elements</span></span>  
  
|<span data-ttu-id="4250b-129">要素</span><span class="sxs-lookup"><span data-stu-id="4250b-129">Element</span></span>|<span data-ttu-id="4250b-130">説明</span><span class="sxs-lookup"><span data-stu-id="4250b-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4250b-131">\<transport></span><span class="sxs-lookup"><span data-stu-id="4250b-131">\<transport></span></span>](transport-of-peertransport.md)|<span data-ttu-id="4250b-132">カスタム バインドのピア トランスポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="4250b-132">Defines a peer transport for a custom binding.</span></span> <span data-ttu-id="4250b-133">この要素には、サービスと対話するときに使用される資格情報を指定する `clientCredentialType` 属性があります。</span><span class="sxs-lookup"><span data-stu-id="4250b-133">This element has a `clientCredentialType` attribute that specifies the credentials to be used when interacting with a service.</span></span> <span data-ttu-id="4250b-134">この属性は <xref:System.ServiceModel.PeerTransportCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="4250b-134">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span><br /><br /> <span data-ttu-id="4250b-135">この要素は <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="4250b-135">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4250b-136">親要素</span><span class="sxs-lookup"><span data-stu-id="4250b-136">Parent Elements</span></span>  
  
|<span data-ttu-id="4250b-137">要素</span><span class="sxs-lookup"><span data-stu-id="4250b-137">Element</span></span>|<span data-ttu-id="4250b-138">説明</span><span class="sxs-lookup"><span data-stu-id="4250b-138">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4250b-139">\<peerTransport ></span><span class="sxs-lookup"><span data-stu-id="4250b-139">\<peerTransport></span></span>](peertransport.md)|<span data-ttu-id="4250b-140">カスタム バインドのピア トランスポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="4250b-140">Defines a peer transport for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4250b-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="4250b-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="4250b-142">トランスポート セキュリティ</span><span class="sxs-lookup"><span data-stu-id="4250b-142">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
- [<span data-ttu-id="4250b-143">トランスポート</span><span class="sxs-lookup"><span data-stu-id="4250b-143">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="4250b-144">トランスポートの選択</span><span class="sxs-lookup"><span data-stu-id="4250b-144">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="4250b-145">バインディング</span><span class="sxs-lookup"><span data-stu-id="4250b-145">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="4250b-146">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="4250b-146">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="4250b-147">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="4250b-147">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="4250b-148">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="4250b-148">\<customBinding></span></span>](custombinding.md)
