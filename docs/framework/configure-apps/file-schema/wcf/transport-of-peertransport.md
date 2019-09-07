---
title: <transport> の <peerTransport>
ms.date: 03/30/2017
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
ms.openlocfilehash: 3b2c7716727f58abb81bf4d58b13189ac170cf7c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399289"
---
# <a name="transport-of-peertransport"></a><span data-ttu-id="3ce8c-102">\<peertransport > \<のトランスポート ></span><span class="sxs-lookup"><span data-stu-id="3ce8c-102">\<transport> of \<peerTransport></span></span>
<span data-ttu-id="3ce8c-103">このバインドで構成されたピアが送信する、セキュリティで保護されたメッセージのトランスポートの型を指定します。</span><span class="sxs-lookup"><span data-stu-id="3ce8c-103">Specifies the transport type for secured messages sent by peers configured with this binding.</span></span>  
  
<span data-ttu-id="3ce8c-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3ce8c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3ce8c-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="3ce8c-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="3ce8c-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<バインド >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="3ce8c-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="3ce8c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="3ce8c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="3ce8c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<バインド >** </span><span class="sxs-lookup"><span data-stu-id="3ce8c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="3ce8c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<peerTransport >** ](peertransport.md)</span><span class="sxs-lookup"><span data-stu-id="3ce8c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peerTransport>**](peertransport.md)</span></span>\
<span data-ttu-id="3ce8c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<セキュリティ >** ](security-of-peertransport.md)</span><span class="sxs-lookup"><span data-stu-id="3ce8c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-peertransport.md)</span></span>\
<span data-ttu-id="3ce8c-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<トランスポート >**</span><span class="sxs-lookup"><span data-stu-id="3ce8c-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ce8c-112">構文</span><span class="sxs-lookup"><span data-stu-id="3ce8c-112">Syntax</span></span>  
  
```xml  
<security>
  <transport credentialType="Certificate/Password" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3ce8c-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3ce8c-113">Attributes and Elements</span></span>  
 <span data-ttu-id="3ce8c-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3ce8c-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3ce8c-115">属性</span><span class="sxs-lookup"><span data-stu-id="3ce8c-115">Attributes</span></span>  
  
|<span data-ttu-id="3ce8c-116">属性</span><span class="sxs-lookup"><span data-stu-id="3ce8c-116">Attribute</span></span>|<span data-ttu-id="3ce8c-117">説明</span><span class="sxs-lookup"><span data-stu-id="3ce8c-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3ce8c-118">credentialType</span><span class="sxs-lookup"><span data-stu-id="3ce8c-118">credentialType</span></span>|<span data-ttu-id="3ce8c-119">任意。</span><span class="sxs-lookup"><span data-stu-id="3ce8c-119">Optional.</span></span> <span data-ttu-id="3ce8c-120">ピア トランスポートにより送信されるメッセージの検証に使用される資格情報の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="3ce8c-120">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="3ce8c-121">この属性は <xref:System.ServiceModel.PeerTransportCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="3ce8c-121">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="3ce8c-122">credentialType 属性</span><span class="sxs-lookup"><span data-stu-id="3ce8c-122">credentialType Attribute</span></span>  
  
|<span data-ttu-id="3ce8c-123">値</span><span class="sxs-lookup"><span data-stu-id="3ce8c-123">Value</span></span>|<span data-ttu-id="3ce8c-124">説明</span><span class="sxs-lookup"><span data-stu-id="3ce8c-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3ce8c-125">証明書</span><span class="sxs-lookup"><span data-stu-id="3ce8c-125">Certificate</span></span>|<span data-ttu-id="3ce8c-126">ピア チャネル トランスポートの認証には X 509 証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="3ce8c-126">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="3ce8c-127">Password</span><span class="sxs-lookup"><span data-stu-id="3ce8c-127">Password</span></span>|<span data-ttu-id="3ce8c-128">ピア チャネル トランスポートの認証には正しいパスワードが必要です。</span><span class="sxs-lookup"><span data-stu-id="3ce8c-128">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3ce8c-129">子要素</span><span class="sxs-lookup"><span data-stu-id="3ce8c-129">Child Elements</span></span>  
 <span data-ttu-id="3ce8c-130">なし</span><span class="sxs-lookup"><span data-stu-id="3ce8c-130">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3ce8c-131">親要素</span><span class="sxs-lookup"><span data-stu-id="3ce8c-131">Parent Elements</span></span>  
  
|<span data-ttu-id="3ce8c-132">要素</span><span class="sxs-lookup"><span data-stu-id="3ce8c-132">Element</span></span>|<span data-ttu-id="3ce8c-133">説明</span><span class="sxs-lookup"><span data-stu-id="3ce8c-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3ce8c-134">\<security></span><span class="sxs-lookup"><span data-stu-id="3ce8c-134">\<security></span></span>](security-of-peertransport.md)|<span data-ttu-id="3ce8c-135">ピア トランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="3ce8c-135">Defines the security settings for a peer transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ce8c-136">Remarks</span><span class="sxs-lookup"><span data-stu-id="3ce8c-136">Remarks</span></span>  
 <span data-ttu-id="3ce8c-137">この要素は、 [ \<security >](security-of-peertransport.md)の mode 属性がまたは`TransportWithMessageCredential`に`Transport`設定されている場合にのみ設定されます。</span><span class="sxs-lookup"><span data-stu-id="3ce8c-137">This element is set only if the mode attribute of [\<security>](security-of-peertransport.md) is set to `Transport` or `TransportWithMessageCredential`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ce8c-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="3ce8c-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="3ce8c-139">トランスポート セキュリティ</span><span class="sxs-lookup"><span data-stu-id="3ce8c-139">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
- [<span data-ttu-id="3ce8c-140">トランスポート</span><span class="sxs-lookup"><span data-stu-id="3ce8c-140">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="3ce8c-141">トランスポートの選択</span><span class="sxs-lookup"><span data-stu-id="3ce8c-141">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="3ce8c-142">バインディング</span><span class="sxs-lookup"><span data-stu-id="3ce8c-142">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="3ce8c-143">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="3ce8c-143">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="3ce8c-144">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="3ce8c-144">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="3ce8c-145">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="3ce8c-145">\<customBinding></span></span>](custombinding.md)
