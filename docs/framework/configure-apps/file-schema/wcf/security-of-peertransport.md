---
title: <security> の <peerTransport>
ms.date: 03/30/2017
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
ms.openlocfilehash: f37c336b0e42993e1eef3f06e2f919705f425a2e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169961"
---
# <a name="security-of-peertransport"></a><span data-ttu-id="b0d96-102">\<security> の \<peerTransport></span><span class="sxs-lookup"><span data-stu-id="b0d96-102">\<security> of \<peerTransport></span></span>

<span data-ttu-id="b0d96-103">ピア チャネルに関連付けられたセキュリティ設定を格納します。使用される認証の種類とメッセージ トランスポートで使用されるセキュリティを含みます。</span><span class="sxs-lookup"><span data-stu-id="b0d96-103">Contains the security settings associated with a peer channel, including the type of authentication used and the security used for the message transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peerTransport>**](peertransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="b0d96-104">構文</span><span class="sxs-lookup"><span data-stu-id="b0d96-104">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/TransportWithMessageCredential">
  <transport clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b0d96-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b0d96-105">Attributes and Elements</span></span>  

 <span data-ttu-id="b0d96-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b0d96-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b0d96-107">属性</span><span class="sxs-lookup"><span data-stu-id="b0d96-107">Attributes</span></span>  
  
|<span data-ttu-id="b0d96-108">属性</span><span class="sxs-lookup"><span data-stu-id="b0d96-108">Attribute</span></span>|<span data-ttu-id="b0d96-109">[説明]</span><span class="sxs-lookup"><span data-stu-id="b0d96-109">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="b0d96-110">適用するセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="b0d96-110">Specifies the type of security to be applied.</span></span> <span data-ttu-id="b0d96-111">既定値は Message です。</span><span class="sxs-lookup"><span data-stu-id="b0d96-111">The default value is Message.</span></span> <span data-ttu-id="b0d96-112">この属性は <xref:System.ServiceModel.SecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="b0d96-112">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="b0d96-113">mode 属性</span><span class="sxs-lookup"><span data-stu-id="b0d96-113">mode Attribute</span></span>  
  
|<span data-ttu-id="b0d96-114">値</span><span class="sxs-lookup"><span data-stu-id="b0d96-114">Value</span></span>|<span data-ttu-id="b0d96-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="b0d96-115">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="b0d96-116">セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="b0d96-116">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="b0d96-117">セキュリティは、HTTPS を使用して確保されます。</span><span class="sxs-lookup"><span data-stu-id="b0d96-117">Security is provided using HTTPS.</span></span>|  
|`Message`|<span data-ttu-id="b0d96-118">SOAP セキュリティにより、認証、整合性、および機密性が実現します。</span><span class="sxs-lookup"><span data-stu-id="b0d96-118">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="b0d96-119">HTTPS により、認証および機密性が実現します。</span><span class="sxs-lookup"><span data-stu-id="b0d96-119">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="b0d96-120">SOAP メッセージには、豊富な資格情報の種類が用意されています。</span><span class="sxs-lookup"><span data-stu-id="b0d96-120">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b0d96-121">子要素</span><span class="sxs-lookup"><span data-stu-id="b0d96-121">Child Elements</span></span>  
  
|<span data-ttu-id="b0d96-122">要素</span><span class="sxs-lookup"><span data-stu-id="b0d96-122">Element</span></span>|<span data-ttu-id="b0d96-123">説明</span><span class="sxs-lookup"><span data-stu-id="b0d96-123">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-peertransport.md)|<span data-ttu-id="b0d96-124">カスタム バインドのピア トランスポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="b0d96-124">Defines a peer transport for a custom binding.</span></span> <span data-ttu-id="b0d96-125">この要素には、サービスと対話するときに使用される資格情報を指定する `clientCredentialType` 属性があります。</span><span class="sxs-lookup"><span data-stu-id="b0d96-125">This element has a `clientCredentialType` attribute that specifies the credentials to be used when interacting with a service.</span></span> <span data-ttu-id="b0d96-126">この属性は <xref:System.ServiceModel.PeerTransportCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="b0d96-126">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span><br /><br /> <span data-ttu-id="b0d96-127">この要素は <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="b0d96-127">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b0d96-128">親要素</span><span class="sxs-lookup"><span data-stu-id="b0d96-128">Parent Elements</span></span>  
  
|<span data-ttu-id="b0d96-129">要素</span><span class="sxs-lookup"><span data-stu-id="b0d96-129">Element</span></span>|<span data-ttu-id="b0d96-130">説明</span><span class="sxs-lookup"><span data-stu-id="b0d96-130">Description</span></span>|  
|-------------|-----------------|  
|[\<peerTransport>](peertransport.md)|<span data-ttu-id="b0d96-131">カスタム バインドのピア トランスポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="b0d96-131">Defines a peer transport for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b0d96-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="b0d96-132">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="b0d96-133">トランスポートセキュリティ</span><span class="sxs-lookup"><span data-stu-id="b0d96-133">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
- [<span data-ttu-id="b0d96-134">トランスポート</span><span class="sxs-lookup"><span data-stu-id="b0d96-134">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="b0d96-135">トランスポートの選択</span><span class="sxs-lookup"><span data-stu-id="b0d96-135">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="b0d96-136">バインド</span><span class="sxs-lookup"><span data-stu-id="b0d96-136">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b0d96-137">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="b0d96-137">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="b0d96-138">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="b0d96-138">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
