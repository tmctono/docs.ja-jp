---
title: <transport> の <peerTransport>
ms.date: 03/30/2017
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
ms.openlocfilehash: 3b2c7716727f58abb81bf4d58b13189ac170cf7c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399289"
---
# <a name="transport-of-peertransport"></a><span data-ttu-id="1abf1-102">\<transport> の \<peerTransport></span><span class="sxs-lookup"><span data-stu-id="1abf1-102">\<transport> of \<peerTransport></span></span>
<span data-ttu-id="1abf1-103">このバインドで構成されたピアが送信する、セキュリティで保護されたメッセージのトランスポートの型を指定します。</span><span class="sxs-lookup"><span data-stu-id="1abf1-103">Specifies the transport type for secured messages sent by peers configured with this binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peerTransport>**](peertransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-peertransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="1abf1-104">構文</span><span class="sxs-lookup"><span data-stu-id="1abf1-104">Syntax</span></span>  
  
```xml  
<security>
  <transport credentialType="Certificate/Password" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1abf1-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1abf1-105">Attributes and Elements</span></span>  
 <span data-ttu-id="1abf1-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1abf1-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1abf1-107">属性</span><span class="sxs-lookup"><span data-stu-id="1abf1-107">Attributes</span></span>  
  
|<span data-ttu-id="1abf1-108">属性</span><span class="sxs-lookup"><span data-stu-id="1abf1-108">Attribute</span></span>|<span data-ttu-id="1abf1-109">説明</span><span class="sxs-lookup"><span data-stu-id="1abf1-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1abf1-110">credentialType</span><span class="sxs-lookup"><span data-stu-id="1abf1-110">credentialType</span></span>|<span data-ttu-id="1abf1-111">省略可能。</span><span class="sxs-lookup"><span data-stu-id="1abf1-111">Optional.</span></span> <span data-ttu-id="1abf1-112">ピア トランスポートにより送信されるメッセージの検証に使用される資格情報の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="1abf1-112">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="1abf1-113">この属性は <xref:System.ServiceModel.PeerTransportCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="1abf1-113">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="1abf1-114">credentialType 属性</span><span class="sxs-lookup"><span data-stu-id="1abf1-114">credentialType Attribute</span></span>  
  
|<span data-ttu-id="1abf1-115">値</span><span class="sxs-lookup"><span data-stu-id="1abf1-115">Value</span></span>|<span data-ttu-id="1abf1-116">Description</span><span class="sxs-lookup"><span data-stu-id="1abf1-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1abf1-117">Certificate</span><span class="sxs-lookup"><span data-stu-id="1abf1-117">Certificate</span></span>|<span data-ttu-id="1abf1-118">ピア チャネル トランスポートの認証には X 509 証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="1abf1-118">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="1abf1-119">Password</span><span class="sxs-lookup"><span data-stu-id="1abf1-119">Password</span></span>|<span data-ttu-id="1abf1-120">ピア チャネル トランスポートの認証には正しいパスワードが必要です。</span><span class="sxs-lookup"><span data-stu-id="1abf1-120">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1abf1-121">子要素</span><span class="sxs-lookup"><span data-stu-id="1abf1-121">Child Elements</span></span>  
 <span data-ttu-id="1abf1-122">なし</span><span class="sxs-lookup"><span data-stu-id="1abf1-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1abf1-123">親要素</span><span class="sxs-lookup"><span data-stu-id="1abf1-123">Parent Elements</span></span>  
  
|<span data-ttu-id="1abf1-124">要素</span><span class="sxs-lookup"><span data-stu-id="1abf1-124">Element</span></span>|<span data-ttu-id="1abf1-125">Description</span><span class="sxs-lookup"><span data-stu-id="1abf1-125">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-peertransport.md)|<span data-ttu-id="1abf1-126">ピア トランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="1abf1-126">Defines the security settings for a peer transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1abf1-127">解説</span><span class="sxs-lookup"><span data-stu-id="1abf1-127">Remarks</span></span>  
 <span data-ttu-id="1abf1-128">この要素は、の mode 属性 [\<security>](security-of-peertransport.md) がまたはに設定されている場合にのみ設定され `Transport` `TransportWithMessageCredential` ます。</span><span class="sxs-lookup"><span data-stu-id="1abf1-128">This element is set only if the mode attribute of [\<security>](security-of-peertransport.md) is set to `Transport` or `TransportWithMessageCredential`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1abf1-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="1abf1-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="1abf1-130">トランスポートセキュリティ</span><span class="sxs-lookup"><span data-stu-id="1abf1-130">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
- [<span data-ttu-id="1abf1-131">トランスポート</span><span class="sxs-lookup"><span data-stu-id="1abf1-131">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="1abf1-132">トランスポートの選択</span><span class="sxs-lookup"><span data-stu-id="1abf1-132">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="1abf1-133">バインド</span><span class="sxs-lookup"><span data-stu-id="1abf1-133">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="1abf1-134">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="1abf1-134">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="1abf1-135">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="1abf1-135">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
