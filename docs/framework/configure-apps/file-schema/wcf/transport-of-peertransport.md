---
title: <transport> の <peerTransport>
ms.date: 03/30/2017
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
ms.openlocfilehash: 9b6f548515afbba5068659bd5c6f7f2b33f80cda
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59076004"
---
# <a name="transport-of-peertransport"></a><span data-ttu-id="95e0e-102">\<トランスポート > の\<peerTransport ></span><span class="sxs-lookup"><span data-stu-id="95e0e-102">\<transport> of \<peerTransport></span></span>
<span data-ttu-id="95e0e-103">このバインドで構成されたピアが送信する、セキュリティで保護されたメッセージのトランスポートの型を指定します。</span><span class="sxs-lookup"><span data-stu-id="95e0e-103">Specifies the transport type for secured messages sent by peers configured with this binding.</span></span>  
  
 <span data-ttu-id="95e0e-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="95e0e-104">\<system.serviceModel></span></span>  
<span data-ttu-id="95e0e-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="95e0e-105">\<bindings></span></span>  
<span data-ttu-id="95e0e-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="95e0e-106">\<customBinding></span></span>  
<span data-ttu-id="95e0e-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="95e0e-107">\<binding></span></span>  
<span data-ttu-id="95e0e-108">\<peerTransport ></span><span class="sxs-lookup"><span data-stu-id="95e0e-108">\<peerTransport></span></span>  
<span data-ttu-id="95e0e-109">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="95e0e-109">\<security></span></span>  
<span data-ttu-id="95e0e-110">\<transport></span><span class="sxs-lookup"><span data-stu-id="95e0e-110">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95e0e-111">構文</span><span class="sxs-lookup"><span data-stu-id="95e0e-111">Syntax</span></span>  
  
```xml  
<security>
  <transport credentialType="Certificate/Password" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="95e0e-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="95e0e-112">Attributes and Elements</span></span>  
 <span data-ttu-id="95e0e-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="95e0e-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="95e0e-114">属性</span><span class="sxs-lookup"><span data-stu-id="95e0e-114">Attributes</span></span>  
  
|<span data-ttu-id="95e0e-115">属性</span><span class="sxs-lookup"><span data-stu-id="95e0e-115">Attribute</span></span>|<span data-ttu-id="95e0e-116">説明</span><span class="sxs-lookup"><span data-stu-id="95e0e-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="95e0e-117">credentialType</span><span class="sxs-lookup"><span data-stu-id="95e0e-117">credentialType</span></span>|<span data-ttu-id="95e0e-118">任意。</span><span class="sxs-lookup"><span data-stu-id="95e0e-118">Optional.</span></span> <span data-ttu-id="95e0e-119">ピア トランスポートにより送信されるメッセージの検証に使用される資格情報の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="95e0e-119">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="95e0e-120">この属性は <xref:System.ServiceModel.PeerTransportCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="95e0e-120">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="95e0e-121">credentialType 属性</span><span class="sxs-lookup"><span data-stu-id="95e0e-121">credentialType Attribute</span></span>  
  
|<span data-ttu-id="95e0e-122">[値]</span><span class="sxs-lookup"><span data-stu-id="95e0e-122">Value</span></span>|<span data-ttu-id="95e0e-123">説明</span><span class="sxs-lookup"><span data-stu-id="95e0e-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="95e0e-124">証明書</span><span class="sxs-lookup"><span data-stu-id="95e0e-124">Certificate</span></span>|<span data-ttu-id="95e0e-125">ピア チャネル トランスポートの認証には X 509 証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="95e0e-125">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="95e0e-126">[Password]</span><span class="sxs-lookup"><span data-stu-id="95e0e-126">Password</span></span>|<span data-ttu-id="95e0e-127">ピア チャネル トランスポートの認証には正しいパスワードが必要です。</span><span class="sxs-lookup"><span data-stu-id="95e0e-127">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="95e0e-128">子要素</span><span class="sxs-lookup"><span data-stu-id="95e0e-128">Child Elements</span></span>  
 <span data-ttu-id="95e0e-129">なし</span><span class="sxs-lookup"><span data-stu-id="95e0e-129">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="95e0e-130">親要素</span><span class="sxs-lookup"><span data-stu-id="95e0e-130">Parent Elements</span></span>  
  
|<span data-ttu-id="95e0e-131">要素</span><span class="sxs-lookup"><span data-stu-id="95e0e-131">Element</span></span>|<span data-ttu-id="95e0e-132">説明</span><span class="sxs-lookup"><span data-stu-id="95e0e-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="95e0e-133">\<security></span><span class="sxs-lookup"><span data-stu-id="95e0e-133">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md)|<span data-ttu-id="95e0e-134">ピア トランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="95e0e-134">Defines the security settings for a peer transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95e0e-135">Remarks</span><span class="sxs-lookup"><span data-stu-id="95e0e-135">Remarks</span></span>  
 <span data-ttu-id="95e0e-136">場合にのみこの要素は、設定の mode 属性[\<セキュリティ >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md)に設定されている`Transport`または`TransportWithMessageCredential`します。</span><span class="sxs-lookup"><span data-stu-id="95e0e-136">This element is set only if the mode attribute of [\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md) is set to `Transport` or `TransportWithMessageCredential`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95e0e-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="95e0e-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="95e0e-138">トランスポート セキュリティ</span><span class="sxs-lookup"><span data-stu-id="95e0e-138">Transport Security</span></span>](../../../../../docs/framework/wcf/feature-details/transport-security.md)
- [<span data-ttu-id="95e0e-139">トランスポート</span><span class="sxs-lookup"><span data-stu-id="95e0e-139">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="95e0e-140">トランスポートの選択</span><span class="sxs-lookup"><span data-stu-id="95e0e-140">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="95e0e-141">バインディング</span><span class="sxs-lookup"><span data-stu-id="95e0e-141">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="95e0e-142">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="95e0e-142">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="95e0e-143">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="95e0e-143">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="95e0e-144">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="95e0e-144">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
