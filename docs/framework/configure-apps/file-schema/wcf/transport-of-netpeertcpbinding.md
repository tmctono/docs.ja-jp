---
title: <transport> の <netPeerTcpBinding>
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: 08be5d752f8422ebe6442b295195f21b16a274c0
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399311"
---
# <a name="transport-of-netpeertcpbinding"></a><span data-ttu-id="8f547-102">\<netpeertcpbinding > の\<トランスポート ></span><span class="sxs-lookup"><span data-stu-id="8f547-102">\<transport> of \<netPeerTcpBinding></span></span>
<span data-ttu-id="8f547-103">Netpeertcpbinding > を使用[ \<](netpeertcpbinding.md)する場合のトランスポートレベルのセキュリティ設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="8f547-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>  
  
<span data-ttu-id="8f547-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8f547-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8f547-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="8f547-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="8f547-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<バインド >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="8f547-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="8f547-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netPeerTcpBinding >** ](netpeertcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="8f547-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)</span></span>\
<span data-ttu-id="8f547-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<バインド >** </span><span class="sxs-lookup"><span data-stu-id="8f547-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="8f547-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<セキュリティ >** ](security-of-netpeerbinding.md)</span><span class="sxs-lookup"><span data-stu-id="8f547-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netpeerbinding.md)</span></span>\
<span data-ttu-id="8f547-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<トランスポート >**</span><span class="sxs-lookup"><span data-stu-id="8f547-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f547-111">構文</span><span class="sxs-lookup"><span data-stu-id="8f547-111">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>
  <binding>
    <security>
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8f547-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8f547-112">Attributes and Elements</span></span>  
 <span data-ttu-id="8f547-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8f547-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8f547-114">属性</span><span class="sxs-lookup"><span data-stu-id="8f547-114">Attributes</span></span>  
  
|<span data-ttu-id="8f547-115">属性</span><span class="sxs-lookup"><span data-stu-id="8f547-115">Attribute</span></span>|<span data-ttu-id="8f547-116">説明</span><span class="sxs-lookup"><span data-stu-id="8f547-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8f547-117">credentialType</span><span class="sxs-lookup"><span data-stu-id="8f547-117">credentialType</span></span>|<span data-ttu-id="8f547-118">任意。</span><span class="sxs-lookup"><span data-stu-id="8f547-118">Optional.</span></span> <span data-ttu-id="8f547-119">ピア トランスポートにより送信されるメッセージの検証に使用される資格情報の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="8f547-119">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="8f547-120">この属性は <xref:System.ServiceModel.PeerTransportCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="8f547-120">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="8f547-121">credentialType 属性</span><span class="sxs-lookup"><span data-stu-id="8f547-121">credentialType Attribute</span></span>  
  
|<span data-ttu-id="8f547-122">値</span><span class="sxs-lookup"><span data-stu-id="8f547-122">Value</span></span>|<span data-ttu-id="8f547-123">説明</span><span class="sxs-lookup"><span data-stu-id="8f547-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8f547-124">証明書</span><span class="sxs-lookup"><span data-stu-id="8f547-124">Certificate</span></span>|<span data-ttu-id="8f547-125">ピア チャネル トランスポートの認証には X 509 証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="8f547-125">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="8f547-126">Password</span><span class="sxs-lookup"><span data-stu-id="8f547-126">Password</span></span>|<span data-ttu-id="8f547-127">ピア チャネル トランスポートの認証には正しいパスワードが必要です。</span><span class="sxs-lookup"><span data-stu-id="8f547-127">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8f547-128">子要素</span><span class="sxs-lookup"><span data-stu-id="8f547-128">Child Elements</span></span>  
 <span data-ttu-id="8f547-129">なし</span><span class="sxs-lookup"><span data-stu-id="8f547-129">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8f547-130">親要素</span><span class="sxs-lookup"><span data-stu-id="8f547-130">Parent Elements</span></span>  
  
|<span data-ttu-id="8f547-131">要素</span><span class="sxs-lookup"><span data-stu-id="8f547-131">Element</span></span>|<span data-ttu-id="8f547-132">説明</span><span class="sxs-lookup"><span data-stu-id="8f547-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8f547-133">\<security></span><span class="sxs-lookup"><span data-stu-id="8f547-133">\<security></span></span>](security-of-netpeerbinding.md)|<span data-ttu-id="8f547-134">Netpeertcpbinding > のセキュリティ設定を[ \<](netpeertcpbinding.md)定義します。</span><span class="sxs-lookup"><span data-stu-id="8f547-134">Defines the security settings for the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8f547-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="8f547-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- [<span data-ttu-id="8f547-136">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="8f547-136">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="8f547-137">バインディング</span><span class="sxs-lookup"><span data-stu-id="8f547-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="8f547-138">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="8f547-138">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="8f547-139">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="8f547-139">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="8f547-140">\<binding></span><span class="sxs-lookup"><span data-stu-id="8f547-140">\<binding></span></span>](../../../misc/binding.md)
