---
title: <transport> の <peerTransport>
ms.date: 03/30/2017
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
ms.openlocfilehash: 5dbc55db25c0c49d72ec2cd8dd1041a3f8705d8e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940644"
---
# <a name="transport-of-peertransport"></a><span data-ttu-id="f7a34-102">\<peertransport > \<のトランスポート ></span><span class="sxs-lookup"><span data-stu-id="f7a34-102">\<transport> of \<peerTransport></span></span>
<span data-ttu-id="f7a34-103">このバインドで構成されたピアが送信する、セキュリティで保護されたメッセージのトランスポートの型を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7a34-103">Specifies the transport type for secured messages sent by peers configured with this binding.</span></span>  
  
 <span data-ttu-id="f7a34-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f7a34-104">\<system.serviceModel></span></span>  
<span data-ttu-id="f7a34-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="f7a34-105">\<bindings></span></span>  
<span data-ttu-id="f7a34-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="f7a34-106">\<customBinding></span></span>  
<span data-ttu-id="f7a34-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="f7a34-107">\<binding></span></span>  
<span data-ttu-id="f7a34-108">\<peerTransport ></span><span class="sxs-lookup"><span data-stu-id="f7a34-108">\<peerTransport></span></span>  
<span data-ttu-id="f7a34-109">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="f7a34-109">\<security></span></span>  
<span data-ttu-id="f7a34-110">\<transport></span><span class="sxs-lookup"><span data-stu-id="f7a34-110">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7a34-111">構文</span><span class="sxs-lookup"><span data-stu-id="f7a34-111">Syntax</span></span>  
  
```xml  
<security>
  <transport credentialType="Certificate/Password" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f7a34-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f7a34-112">Attributes and Elements</span></span>  
 <span data-ttu-id="f7a34-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f7a34-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f7a34-114">属性</span><span class="sxs-lookup"><span data-stu-id="f7a34-114">Attributes</span></span>  
  
|<span data-ttu-id="f7a34-115">属性</span><span class="sxs-lookup"><span data-stu-id="f7a34-115">Attribute</span></span>|<span data-ttu-id="f7a34-116">説明</span><span class="sxs-lookup"><span data-stu-id="f7a34-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f7a34-117">credentialType</span><span class="sxs-lookup"><span data-stu-id="f7a34-117">credentialType</span></span>|<span data-ttu-id="f7a34-118">任意。</span><span class="sxs-lookup"><span data-stu-id="f7a34-118">Optional.</span></span> <span data-ttu-id="f7a34-119">ピア トランスポートにより送信されるメッセージの検証に使用される資格情報の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7a34-119">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="f7a34-120">この属性は <xref:System.ServiceModel.PeerTransportCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="f7a34-120">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="f7a34-121">credentialType 属性</span><span class="sxs-lookup"><span data-stu-id="f7a34-121">credentialType Attribute</span></span>  
  
|<span data-ttu-id="f7a34-122">値</span><span class="sxs-lookup"><span data-stu-id="f7a34-122">Value</span></span>|<span data-ttu-id="f7a34-123">説明</span><span class="sxs-lookup"><span data-stu-id="f7a34-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f7a34-124">証明書</span><span class="sxs-lookup"><span data-stu-id="f7a34-124">Certificate</span></span>|<span data-ttu-id="f7a34-125">ピア チャネル トランスポートの認証には X 509 証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="f7a34-125">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="f7a34-126">Password</span><span class="sxs-lookup"><span data-stu-id="f7a34-126">Password</span></span>|<span data-ttu-id="f7a34-127">ピア チャネル トランスポートの認証には正しいパスワードが必要です。</span><span class="sxs-lookup"><span data-stu-id="f7a34-127">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f7a34-128">子要素</span><span class="sxs-lookup"><span data-stu-id="f7a34-128">Child Elements</span></span>  
 <span data-ttu-id="f7a34-129">なし</span><span class="sxs-lookup"><span data-stu-id="f7a34-129">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f7a34-130">親要素</span><span class="sxs-lookup"><span data-stu-id="f7a34-130">Parent Elements</span></span>  
  
|<span data-ttu-id="f7a34-131">要素</span><span class="sxs-lookup"><span data-stu-id="f7a34-131">Element</span></span>|<span data-ttu-id="f7a34-132">説明</span><span class="sxs-lookup"><span data-stu-id="f7a34-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f7a34-133">\<security></span><span class="sxs-lookup"><span data-stu-id="f7a34-133">\<security></span></span>](security-of-peertransport.md)|<span data-ttu-id="f7a34-134">ピア トランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="f7a34-134">Defines the security settings for a peer transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7a34-135">Remarks</span><span class="sxs-lookup"><span data-stu-id="f7a34-135">Remarks</span></span>  
 <span data-ttu-id="f7a34-136">この要素は、 [ \<security >](security-of-peertransport.md)の mode 属性がまたは`TransportWithMessageCredential`に`Transport`設定されている場合にのみ設定されます。</span><span class="sxs-lookup"><span data-stu-id="f7a34-136">This element is set only if the mode attribute of [\<security>](security-of-peertransport.md) is set to `Transport` or `TransportWithMessageCredential`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7a34-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7a34-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="f7a34-138">トランスポート セキュリティ</span><span class="sxs-lookup"><span data-stu-id="f7a34-138">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
- [<span data-ttu-id="f7a34-139">トランスポート</span><span class="sxs-lookup"><span data-stu-id="f7a34-139">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="f7a34-140">トランスポートの選択</span><span class="sxs-lookup"><span data-stu-id="f7a34-140">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="f7a34-141">バインディング</span><span class="sxs-lookup"><span data-stu-id="f7a34-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="f7a34-142">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="f7a34-142">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="f7a34-143">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="f7a34-143">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="f7a34-144">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="f7a34-144">\<customBinding></span></span>](custombinding.md)
