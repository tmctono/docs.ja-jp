---
title: <peer> <clientCredentials>要素
ms.date: 03/30/2017
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
ms.openlocfilehash: dce7ef64de1e3eb248e3553c97cbce8e9b205b4c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400098"
---
# <a name="peer-of-clientcredentials-element"></a><span data-ttu-id="032fb-102">\<clientCredentials > 要素\<のピア ></span><span class="sxs-lookup"><span data-stu-id="032fb-102">\<peer> of \<clientCredentials> Element</span></span>
<span data-ttu-id="032fb-103">ピアツーピア クライアントの認証時に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="032fb-103">Specifies credentials used when authenticating peer-to-peer clients.</span></span>  
  
<span data-ttu-id="032fb-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="032fb-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="032fb-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="032fb-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="032fb-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="032fb-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="032fb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="032fb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="032fb-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="032fb-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="032fb-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="032fb-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="032fb-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<ピア >**</span><span class="sxs-lookup"><span data-stu-id="032fb-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="032fb-111">構文</span><span class="sxs-lookup"><span data-stu-id="032fb-111">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="032fb-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="032fb-112">Attributes and Elements</span></span>  
 <span data-ttu-id="032fb-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="032fb-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="032fb-114">属性</span><span class="sxs-lookup"><span data-stu-id="032fb-114">Attributes</span></span>  
 <span data-ttu-id="032fb-115">なし。</span><span class="sxs-lookup"><span data-stu-id="032fb-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="032fb-116">子要素</span><span class="sxs-lookup"><span data-stu-id="032fb-116">Child Elements</span></span>  
  
|<span data-ttu-id="032fb-117">要素</span><span class="sxs-lookup"><span data-stu-id="032fb-117">Element</span></span>|<span data-ttu-id="032fb-118">説明</span><span class="sxs-lookup"><span data-stu-id="032fb-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="032fb-119">\<certificate></span><span class="sxs-lookup"><span data-stu-id="032fb-119">\<certificate></span></span>](certificate-element.md)|<span data-ttu-id="032fb-120">ピアツーピア クライアントのメッセージの署名と暗号化に使用する X.509 証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="032fb-120">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span> <span data-ttu-id="032fb-121">.</span><span class="sxs-lookup"><span data-stu-id="032fb-121">.</span></span>|  
|[<span data-ttu-id="032fb-122">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="032fb-122">\<peerAuthentication></span></span>](peerauthentication-element.md)|<span data-ttu-id="032fb-123">ピア クライアントの認証オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="032fb-123">Specifies authentication options for peer clients.</span></span>|  
|[<span data-ttu-id="032fb-124">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="032fb-124">\<messageSenderAuthentication></span></span>](messagesenderauthentication-element.md)|<span data-ttu-id="032fb-125">メッセージ送信者の認証オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="032fb-125">Specifies authentication options for message senders.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="032fb-126">親要素</span><span class="sxs-lookup"><span data-stu-id="032fb-126">Parent Elements</span></span>  
  
|<span data-ttu-id="032fb-127">要素</span><span class="sxs-lookup"><span data-stu-id="032fb-127">Element</span></span>|<span data-ttu-id="032fb-128">説明</span><span class="sxs-lookup"><span data-stu-id="032fb-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="032fb-129">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="032fb-129">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="032fb-130">サービスに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="032fb-130">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="032fb-131">Remarks</span><span class="sxs-lookup"><span data-stu-id="032fb-131">Remarks</span></span>  
 <span data-ttu-id="032fb-132">この構成要素は、ピア ノードがメッシュ内の他のノードに対して自身を認証するために使用する資格情報と、ピア ノードが他のピア ノードを認証するために使用する認証設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="032fb-132">This configuration element specifies the credentials that a peer node uses to authenticate itself to other nodes in the mesh, as well as authentication settings that a peer node uses to authenticate other peer nodes.</span></span> <span data-ttu-id="032fb-133">詳細については、「[ピアチャネルメッセージ認証](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))」および「[ピアチャネルアプリケーションのセキュリティ保護](../../../wcf/feature-details/securing-peer-channel-applications.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="032fb-133">For more information, see [Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) and [Securing Peer Channel Applications](../../../wcf/feature-details/securing-peer-channel-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="032fb-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="032fb-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="032fb-135">ピアツーピア ネットワーク</span><span class="sxs-lookup"><span data-stu-id="032fb-135">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- [<span data-ttu-id="032fb-136">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="032fb-136">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- <span data-ttu-id="032fb-137">[ピアチャネルメッセージの認証](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="032fb-137">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="032fb-138">[ピアチャネルのカスタム認証](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="032fb-138">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="032fb-139">セキュリティによるピア チャネル アプリケーションの保護</span><span class="sxs-lookup"><span data-stu-id="032fb-139">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="032fb-140">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="032fb-140">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
