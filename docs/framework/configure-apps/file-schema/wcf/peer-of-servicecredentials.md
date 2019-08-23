---
title: <peer> の <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: b134e21d-e5b5-458e-9309-626dbf8db4ed
ms.openlocfilehash: 50415cb9b35d2a2053efa3313a415de518b7e36e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933784"
---
# <a name="peer-of-servicecredentials"></a><span data-ttu-id="b8c9b-102">\<serviceCredentials > の\<ピア ></span><span class="sxs-lookup"><span data-stu-id="b8c9b-102">\<peer> of \<serviceCredentials></span></span>
<span data-ttu-id="b8c9b-103">ピア ノードの現在の資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="b8c9b-103">Specifies the current credentials for a peer node.</span></span>  
  
 <span data-ttu-id="b8c9b-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="b8c9b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b8c9b-105">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="b8c9b-105">\<behaviors></span></span>  
<span data-ttu-id="b8c9b-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="b8c9b-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="b8c9b-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="b8c9b-107">\<behavior></span></span>  
<span data-ttu-id="b8c9b-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="b8c9b-108">\<serviceCredentials></span></span>  
<span data-ttu-id="b8c9b-109">\<ピア ></span><span class="sxs-lookup"><span data-stu-id="b8c9b-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8c9b-110">構文</span><span class="sxs-lookup"><span data-stu-id="b8c9b-110">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b8c9b-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b8c9b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b8c9b-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b8c9b-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b8c9b-113">属性</span><span class="sxs-lookup"><span data-stu-id="b8c9b-113">Attributes</span></span>  
 <span data-ttu-id="b8c9b-114">なし。</span><span class="sxs-lookup"><span data-stu-id="b8c9b-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b8c9b-115">子要素</span><span class="sxs-lookup"><span data-stu-id="b8c9b-115">Child Elements</span></span>  
  
|<span data-ttu-id="b8c9b-116">要素</span><span class="sxs-lookup"><span data-stu-id="b8c9b-116">Element</span></span>|<span data-ttu-id="b8c9b-117">説明</span><span class="sxs-lookup"><span data-stu-id="b8c9b-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b8c9b-118">\<certificate></span><span class="sxs-lookup"><span data-stu-id="b8c9b-118">\<certificate></span></span>](certificate-of-peer.md)|<span data-ttu-id="b8c9b-119">ピアツーピア サービスのメッセージの署名と暗号化に使用する X.509 証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="b8c9b-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer services.</span></span> <span data-ttu-id="b8c9b-120">.</span><span class="sxs-lookup"><span data-stu-id="b8c9b-120">.</span></span>|  
|[<span data-ttu-id="b8c9b-121">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="b8c9b-121">\<messageSenderAuthentication></span></span>](messagesenderauthentication.md)|<span data-ttu-id="b8c9b-122">メッセージ送信者の認証オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="b8c9b-122">Specifies authentication options for message senders.</span></span>|  
|[<span data-ttu-id="b8c9b-123">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="b8c9b-123">\<peerAuthentication></span></span>](peerauthentication.md)|<span data-ttu-id="b8c9b-124">ピア サービスの認証オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="b8c9b-124">Specifies authentication options for peer services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b8c9b-125">親要素</span><span class="sxs-lookup"><span data-stu-id="b8c9b-125">Parent Elements</span></span>  
  
|<span data-ttu-id="b8c9b-126">要素</span><span class="sxs-lookup"><span data-stu-id="b8c9b-126">Element</span></span>|<span data-ttu-id="b8c9b-127">説明</span><span class="sxs-lookup"><span data-stu-id="b8c9b-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b8c9b-128">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="b8c9b-128">\<serviceCredentials></span></span>](servicecredentials.md)|<span data-ttu-id="b8c9b-129">サービスの認証に使用される資格情報と、クライアントの資格情報検証関連の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="b8c9b-129">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b8c9b-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="b8c9b-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="b8c9b-131">ピアツーピア ネットワーク</span><span class="sxs-lookup"><span data-stu-id="b8c9b-131">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="b8c9b-132">[ピアチャネルメッセージの認証](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="b8c9b-132">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="b8c9b-133">[ピアチャネルのカスタム認証](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="b8c9b-133">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="b8c9b-134">セキュリティによるピア チャネル アプリケーションの保護</span><span class="sxs-lookup"><span data-stu-id="b8c9b-134">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="b8c9b-135">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="b8c9b-135">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
