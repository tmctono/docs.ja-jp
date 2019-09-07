---
title: <peer> の <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: b134e21d-e5b5-458e-9309-626dbf8db4ed
ms.openlocfilehash: ca97be7b1ab562382895fea4f1d1fc716151b70b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397638"
---
# <a name="peer-of-servicecredentials"></a><span data-ttu-id="1da20-102">\<serviceCredentials > の\<ピア ></span><span class="sxs-lookup"><span data-stu-id="1da20-102">\<peer> of \<serviceCredentials></span></span>
<span data-ttu-id="1da20-103">ピア ノードの現在の資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="1da20-103">Specifies the current credentials for a peer node.</span></span>  
  
<span data-ttu-id="1da20-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1da20-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1da20-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="1da20-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="1da20-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="1da20-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="1da20-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="1da20-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="1da20-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="1da20-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="1da20-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCredentials >** ](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="1da20-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="1da20-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<ピア >**</span><span class="sxs-lookup"><span data-stu-id="1da20-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1da20-111">構文</span><span class="sxs-lookup"><span data-stu-id="1da20-111">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1da20-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1da20-112">Attributes and Elements</span></span>  
 <span data-ttu-id="1da20-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1da20-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1da20-114">属性</span><span class="sxs-lookup"><span data-stu-id="1da20-114">Attributes</span></span>  
 <span data-ttu-id="1da20-115">なし。</span><span class="sxs-lookup"><span data-stu-id="1da20-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1da20-116">子要素</span><span class="sxs-lookup"><span data-stu-id="1da20-116">Child Elements</span></span>  
  
|<span data-ttu-id="1da20-117">要素</span><span class="sxs-lookup"><span data-stu-id="1da20-117">Element</span></span>|<span data-ttu-id="1da20-118">説明</span><span class="sxs-lookup"><span data-stu-id="1da20-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1da20-119">\<certificate></span><span class="sxs-lookup"><span data-stu-id="1da20-119">\<certificate></span></span>](certificate-of-peer.md)|<span data-ttu-id="1da20-120">ピアツーピア サービスのメッセージの署名と暗号化に使用する X.509 証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="1da20-120">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer services.</span></span> <span data-ttu-id="1da20-121">.</span><span class="sxs-lookup"><span data-stu-id="1da20-121">.</span></span>|  
|[<span data-ttu-id="1da20-122">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="1da20-122">\<messageSenderAuthentication></span></span>](messagesenderauthentication.md)|<span data-ttu-id="1da20-123">メッセージ送信者の認証オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="1da20-123">Specifies authentication options for message senders.</span></span>|  
|[<span data-ttu-id="1da20-124">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="1da20-124">\<peerAuthentication></span></span>](peerauthentication.md)|<span data-ttu-id="1da20-125">ピア サービスの認証オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="1da20-125">Specifies authentication options for peer services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1da20-126">親要素</span><span class="sxs-lookup"><span data-stu-id="1da20-126">Parent Elements</span></span>  
  
|<span data-ttu-id="1da20-127">要素</span><span class="sxs-lookup"><span data-stu-id="1da20-127">Element</span></span>|<span data-ttu-id="1da20-128">説明</span><span class="sxs-lookup"><span data-stu-id="1da20-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1da20-129">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="1da20-129">\<serviceCredentials></span></span>](servicecredentials.md)|<span data-ttu-id="1da20-130">サービスの認証に使用される資格情報と、クライアントの資格情報検証関連の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="1da20-130">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1da20-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="1da20-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="1da20-132">ピアツーピア ネットワーク</span><span class="sxs-lookup"><span data-stu-id="1da20-132">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="1da20-133">[ピアチャネルメッセージの認証](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="1da20-133">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="1da20-134">[ピアチャネルのカスタム認証](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="1da20-134">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="1da20-135">セキュリティによるピア チャネル アプリケーションの保護</span><span class="sxs-lookup"><span data-stu-id="1da20-135">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="1da20-136">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="1da20-136">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
