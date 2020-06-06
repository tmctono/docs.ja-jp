---
title: <security> の <peerTransport>
ms.date: 03/30/2017
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
ms.openlocfilehash: 270ca844f586be256b6483653c868d1cc4396657
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399778"
---
# <a name="security-of-peertransport"></a><span data-ttu-id="4dc5e-102">\<security> の \<peerTransport></span><span class="sxs-lookup"><span data-stu-id="4dc5e-102">\<security> of \<peerTransport></span></span>
<span data-ttu-id="4dc5e-103">ピア チャネルに関連付けられたセキュリティ設定を格納します。使用される認証の種類とメッセージ トランスポートで使用されるセキュリティを含みます。</span><span class="sxs-lookup"><span data-stu-id="4dc5e-103">Contains the security settings associated with a peer channel, including the type of authentication used and the security used for the message transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peerTransport>**](peertransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="4dc5e-104">構文</span><span class="sxs-lookup"><span data-stu-id="4dc5e-104">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/TransportWithMessageCredential">
  <transport clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4dc5e-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4dc5e-105">Attributes and Elements</span></span>  
 <span data-ttu-id="4dc5e-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4dc5e-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4dc5e-107">属性</span><span class="sxs-lookup"><span data-stu-id="4dc5e-107">Attributes</span></span>  
  
|<span data-ttu-id="4dc5e-108">属性</span><span class="sxs-lookup"><span data-stu-id="4dc5e-108">Attribute</span></span>|<span data-ttu-id="4dc5e-109">説明</span><span class="sxs-lookup"><span data-stu-id="4dc5e-109">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="4dc5e-110">適用するセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="4dc5e-110">Specifies the type of security to be applied.</span></span> <span data-ttu-id="4dc5e-111">既定値は Message です。</span><span class="sxs-lookup"><span data-stu-id="4dc5e-111">The default value is Message.</span></span> <span data-ttu-id="4dc5e-112">この属性は <xref:System.ServiceModel.SecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="4dc5e-112">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="4dc5e-113">mode 属性</span><span class="sxs-lookup"><span data-stu-id="4dc5e-113">mode Attribute</span></span>  
  
|<span data-ttu-id="4dc5e-114">値</span><span class="sxs-lookup"><span data-stu-id="4dc5e-114">Value</span></span>|<span data-ttu-id="4dc5e-115">Description</span><span class="sxs-lookup"><span data-stu-id="4dc5e-115">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="4dc5e-116">セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="4dc5e-116">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="4dc5e-117">セキュリティは、HTTPS を使用して確保されます。</span><span class="sxs-lookup"><span data-stu-id="4dc5e-117">Security is provided using HTTPS.</span></span>|  
|`Message`|<span data-ttu-id="4dc5e-118">SOAP セキュリティにより、認証、整合性、および機密性が実現します。</span><span class="sxs-lookup"><span data-stu-id="4dc5e-118">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="4dc5e-119">HTTPS により、認証および機密性が実現します。</span><span class="sxs-lookup"><span data-stu-id="4dc5e-119">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="4dc5e-120">SOAP メッセージには、豊富な資格情報の種類が用意されています。</span><span class="sxs-lookup"><span data-stu-id="4dc5e-120">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4dc5e-121">子要素</span><span class="sxs-lookup"><span data-stu-id="4dc5e-121">Child Elements</span></span>  
  
|<span data-ttu-id="4dc5e-122">要素</span><span class="sxs-lookup"><span data-stu-id="4dc5e-122">Element</span></span>|<span data-ttu-id="4dc5e-123">Description</span><span class="sxs-lookup"><span data-stu-id="4dc5e-123">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-peertransport.md)|<span data-ttu-id="4dc5e-124">カスタム バインドのピア トランスポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="4dc5e-124">Defines a peer transport for a custom binding.</span></span> <span data-ttu-id="4dc5e-125">この要素には、サービスと対話するときに使用される資格情報を指定する `clientCredentialType` 属性があります。</span><span class="sxs-lookup"><span data-stu-id="4dc5e-125">This element has a `clientCredentialType` attribute that specifies the credentials to be used when interacting with a service.</span></span> <span data-ttu-id="4dc5e-126">この属性は <xref:System.ServiceModel.PeerTransportCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="4dc5e-126">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span><br /><br /> <span data-ttu-id="4dc5e-127">この要素は <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="4dc5e-127">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4dc5e-128">親要素</span><span class="sxs-lookup"><span data-stu-id="4dc5e-128">Parent Elements</span></span>  
  
|<span data-ttu-id="4dc5e-129">要素</span><span class="sxs-lookup"><span data-stu-id="4dc5e-129">Element</span></span>|<span data-ttu-id="4dc5e-130">Description</span><span class="sxs-lookup"><span data-stu-id="4dc5e-130">Description</span></span>|  
|-------------|-----------------|  
|[\<peerTransport>](peertransport.md)|<span data-ttu-id="4dc5e-131">カスタム バインドのピア トランスポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="4dc5e-131">Defines a peer transport for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4dc5e-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="4dc5e-132">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="4dc5e-133">トランスポートセキュリティ</span><span class="sxs-lookup"><span data-stu-id="4dc5e-133">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
- [<span data-ttu-id="4dc5e-134">トランスポート</span><span class="sxs-lookup"><span data-stu-id="4dc5e-134">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="4dc5e-135">トランスポートの選択</span><span class="sxs-lookup"><span data-stu-id="4dc5e-135">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="4dc5e-136">バインド</span><span class="sxs-lookup"><span data-stu-id="4dc5e-136">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="4dc5e-137">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="4dc5e-137">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="4dc5e-138">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="4dc5e-138">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
