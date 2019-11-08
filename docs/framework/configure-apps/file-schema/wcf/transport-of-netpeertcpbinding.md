---
title: <transport> の <netPeerTcpBinding>
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: 49b31a889d192d190125214e89ba09305114eb7f
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73735978"
---
# <a name="transport-of-netpeertcpbinding"></a><span data-ttu-id="70afe-102">\<netPeerTcpBinding の \<トランスポート > ></span><span class="sxs-lookup"><span data-stu-id="70afe-102">\<transport> of \<netPeerTcpBinding></span></span>
<span data-ttu-id="70afe-103">[\<netPeerTcpBinding >](netpeertcpbinding.md)を使用する場合のトランスポートレベルのセキュリティ設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="70afe-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>  
  
<span data-ttu-id="70afe-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="70afe-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="70afe-105">&nbsp; &nbsp;[ **\<system >** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="70afe-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="70afe-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**バインド**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="70afe-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="70afe-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**netPeerTcpBinding\<** ](netpeertcpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="70afe-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)\</span></span>
<span data-ttu-id="70afe-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**バインド >** </span><span class="sxs-lookup"><span data-stu-id="70afe-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="70afe-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**セキュリティ >** ](security-of-netpeerbinding.md)</span><span class="sxs-lookup"><span data-stu-id="70afe-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netpeerbinding.md)</span></span>\
<span data-ttu-id="70afe-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**トランスポート >**</span><span class="sxs-lookup"><span data-stu-id="70afe-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70afe-111">構文</span><span class="sxs-lookup"><span data-stu-id="70afe-111">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>
  <binding>
    <security>
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="70afe-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="70afe-112">Attributes and Elements</span></span>  
 <span data-ttu-id="70afe-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="70afe-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="70afe-114">属性</span><span class="sxs-lookup"><span data-stu-id="70afe-114">Attributes</span></span>  
  
|<span data-ttu-id="70afe-115">属性</span><span class="sxs-lookup"><span data-stu-id="70afe-115">Attribute</span></span>|<span data-ttu-id="70afe-116">説明</span><span class="sxs-lookup"><span data-stu-id="70afe-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="70afe-117">credentialType</span><span class="sxs-lookup"><span data-stu-id="70afe-117">credentialType</span></span>|<span data-ttu-id="70afe-118">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="70afe-118">Optional.</span></span> <span data-ttu-id="70afe-119">ピア トランスポートにより送信されるメッセージの検証に使用される資格情報の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="70afe-119">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="70afe-120">この属性は <xref:System.ServiceModel.PeerTransportCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="70afe-120">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="70afe-121">credentialType 属性</span><span class="sxs-lookup"><span data-stu-id="70afe-121">credentialType Attribute</span></span>  
  
|<span data-ttu-id="70afe-122">[値]</span><span class="sxs-lookup"><span data-stu-id="70afe-122">Value</span></span>|<span data-ttu-id="70afe-123">説明</span><span class="sxs-lookup"><span data-stu-id="70afe-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="70afe-124">証明書</span><span class="sxs-lookup"><span data-stu-id="70afe-124">Certificate</span></span>|<span data-ttu-id="70afe-125">ピア チャネル トランスポートの認証には X 509 証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="70afe-125">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="70afe-126">パスワード</span><span class="sxs-lookup"><span data-stu-id="70afe-126">Password</span></span>|<span data-ttu-id="70afe-127">ピア チャネル トランスポートの認証には正しいパスワードが必要です。</span><span class="sxs-lookup"><span data-stu-id="70afe-127">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="70afe-128">子要素</span><span class="sxs-lookup"><span data-stu-id="70afe-128">Child Elements</span></span>  
 <span data-ttu-id="70afe-129">None</span><span class="sxs-lookup"><span data-stu-id="70afe-129">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="70afe-130">親要素</span><span class="sxs-lookup"><span data-stu-id="70afe-130">Parent Elements</span></span>  
  
|<span data-ttu-id="70afe-131">要素</span><span class="sxs-lookup"><span data-stu-id="70afe-131">Element</span></span>|<span data-ttu-id="70afe-132">説明</span><span class="sxs-lookup"><span data-stu-id="70afe-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="70afe-133">\< セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="70afe-133">\<security></span></span>](security-of-netpeerbinding.md)|<span data-ttu-id="70afe-134">[\<netPeerTcpBinding >](netpeertcpbinding.md)のセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="70afe-134">Defines the security settings for the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="70afe-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="70afe-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- [<span data-ttu-id="70afe-136">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="70afe-136">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="70afe-137">バインディング</span><span class="sxs-lookup"><span data-stu-id="70afe-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="70afe-138">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="70afe-138">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="70afe-139">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="70afe-139">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="70afe-140">\<binding ></span><span class="sxs-lookup"><span data-stu-id="70afe-140">\<binding></span></span>](bindings.md)
