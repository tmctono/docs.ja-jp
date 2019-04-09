---
title: <peer> <clientCredentials>要素
ms.date: 03/30/2017
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
ms.openlocfilehash: 7074ee992755557d7e5503035c89bdbefd678792
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107238"
---
# <a name="peer-of-clientcredentials-element"></a><span data-ttu-id="adb43-102">\<ピア > の\<clientCredentials > 要素</span><span class="sxs-lookup"><span data-stu-id="adb43-102">\<peer> of \<clientCredentials> Element</span></span>
<span data-ttu-id="adb43-103">ピアツーピア クライアントの認証時に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="adb43-103">Specifies credentials used when authenticating peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="adb43-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="adb43-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="adb43-105">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="adb43-105">\<behaviors></span></span>  
<span data-ttu-id="adb43-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="adb43-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="adb43-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="adb43-107">\<behavior></span></span>  
<span data-ttu-id="adb43-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="adb43-108">\<clientCredentials></span></span>  
<span data-ttu-id="adb43-109">\<ピア ></span><span class="sxs-lookup"><span data-stu-id="adb43-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adb43-110">構文</span><span class="sxs-lookup"><span data-stu-id="adb43-110">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="adb43-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="adb43-111">Attributes and Elements</span></span>  
 <span data-ttu-id="adb43-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="adb43-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="adb43-113">属性</span><span class="sxs-lookup"><span data-stu-id="adb43-113">Attributes</span></span>  
 <span data-ttu-id="adb43-114">なし。</span><span class="sxs-lookup"><span data-stu-id="adb43-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="adb43-115">子要素</span><span class="sxs-lookup"><span data-stu-id="adb43-115">Child Elements</span></span>  
  
|<span data-ttu-id="adb43-116">要素</span><span class="sxs-lookup"><span data-stu-id="adb43-116">Element</span></span>|<span data-ttu-id="adb43-117">説明</span><span class="sxs-lookup"><span data-stu-id="adb43-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="adb43-118">\<証明書></span><span class="sxs-lookup"><span data-stu-id="adb43-118">\<certificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md)|<span data-ttu-id="adb43-119">ピアツーピア クライアントのメッセージの署名と暗号化に使用する X.509 証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="adb43-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span> <span data-ttu-id="adb43-120">.</span><span class="sxs-lookup"><span data-stu-id="adb43-120">.</span></span>|  
|[<span data-ttu-id="adb43-121">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="adb43-121">\<peerAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication-element.md)|<span data-ttu-id="adb43-122">ピア クライアントの認証オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="adb43-122">Specifies authentication options for peer clients.</span></span>|  
|[<span data-ttu-id="adb43-123">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="adb43-123">\<messageSenderAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication-element.md)|<span data-ttu-id="adb43-124">メッセージ送信者の認証オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="adb43-124">Specifies authentication options for message senders.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="adb43-125">親要素</span><span class="sxs-lookup"><span data-stu-id="adb43-125">Parent Elements</span></span>  
  
|<span data-ttu-id="adb43-126">要素</span><span class="sxs-lookup"><span data-stu-id="adb43-126">Element</span></span>|<span data-ttu-id="adb43-127">説明</span><span class="sxs-lookup"><span data-stu-id="adb43-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="adb43-128">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="adb43-128">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="adb43-129">サービスに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="adb43-129">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="adb43-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="adb43-130">Remarks</span></span>  
 <span data-ttu-id="adb43-131">この構成要素は、ピア ノードがメッシュ内の他のノードに対して自身を認証するために使用する資格情報と、ピア ノードが他のピア ノードを認証するために使用する認証設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="adb43-131">This configuration element specifies the credentials that a peer node uses to authenticate itself to other nodes in the mesh, as well as authentication settings that a peer node uses to authenticate other peer nodes.</span></span> <span data-ttu-id="adb43-132">詳細については、次を参照してください。[ピア チャネル メッセージ認証](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))と[ピア チャネル アプリケーションのセキュリティで保護する](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)します。</span><span class="sxs-lookup"><span data-stu-id="adb43-132">For more information, see [Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) and [Securing Peer Channel Applications](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adb43-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="adb43-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="adb43-134">ピアツーピア ネットワーク</span><span class="sxs-lookup"><span data-stu-id="adb43-134">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- [<span data-ttu-id="adb43-135">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="adb43-135">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="adb43-136">ピア チャネル メッセージの認証</span><span class="sxs-lookup"><span data-stu-id="adb43-136">Peer Channel Message Authentication</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))
- [<span data-ttu-id="adb43-137">ピア チャネル カスタム認証</span><span class="sxs-lookup"><span data-stu-id="adb43-137">Peer Channel Custom Authentication</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))
- [<span data-ttu-id="adb43-138">セキュリティによるピア チャネル アプリケーションの保護</span><span class="sxs-lookup"><span data-stu-id="adb43-138">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="adb43-139">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="adb43-139">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
