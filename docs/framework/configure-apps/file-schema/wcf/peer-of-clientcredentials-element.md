---
title: <peer><clientCredentials>要素の
ms.date: 03/30/2017
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
ms.openlocfilehash: 75d8543d7db5eee1345d54f934fc89c9593b85ac
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186992"
---
# <a name="peer-of-clientcredentials-element"></a><span data-ttu-id="a1bee-102">\<peer>\<clientCredentials>要素の</span><span class="sxs-lookup"><span data-stu-id="a1bee-102">\<peer> of \<clientCredentials> Element</span></span>

<span data-ttu-id="a1bee-103">ピアツーピア クライアントの認証時に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="a1bee-103">Specifies credentials used when authenticating peer-to-peer clients.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peer>**  
  
## <a name="syntax"></a><span data-ttu-id="a1bee-104">構文</span><span class="sxs-lookup"><span data-stu-id="a1bee-104">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a1bee-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a1bee-105">Attributes and Elements</span></span>  

 <span data-ttu-id="a1bee-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a1bee-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a1bee-107">属性</span><span class="sxs-lookup"><span data-stu-id="a1bee-107">Attributes</span></span>  

 <span data-ttu-id="a1bee-108">なし。</span><span class="sxs-lookup"><span data-stu-id="a1bee-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a1bee-109">子要素</span><span class="sxs-lookup"><span data-stu-id="a1bee-109">Child Elements</span></span>  
  
|<span data-ttu-id="a1bee-110">要素</span><span class="sxs-lookup"><span data-stu-id="a1bee-110">Element</span></span>|<span data-ttu-id="a1bee-111">説明</span><span class="sxs-lookup"><span data-stu-id="a1bee-111">Description</span></span>|  
|-------------|-----------------|  
|[\<certificate>](certificate-element.md)|<span data-ttu-id="a1bee-112">ピアツーピア クライアントのメッセージの署名と暗号化に使用する X.509 証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="a1bee-112">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span> <span data-ttu-id="a1bee-113">.</span><span class="sxs-lookup"><span data-stu-id="a1bee-113">.</span></span>|  
|[\<peerAuthentication>](peerauthentication-element.md)|<span data-ttu-id="a1bee-114">ピア クライアントの認証オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="a1bee-114">Specifies authentication options for peer clients.</span></span>|  
|[\<messageSenderAuthentication>](messagesenderauthentication-element.md)|<span data-ttu-id="a1bee-115">メッセージ送信者の認証オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="a1bee-115">Specifies authentication options for message senders.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a1bee-116">親要素</span><span class="sxs-lookup"><span data-stu-id="a1bee-116">Parent Elements</span></span>  
  
|<span data-ttu-id="a1bee-117">要素</span><span class="sxs-lookup"><span data-stu-id="a1bee-117">Element</span></span>|<span data-ttu-id="a1bee-118">説明</span><span class="sxs-lookup"><span data-stu-id="a1bee-118">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="a1bee-119">サービスに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="a1bee-119">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1bee-120">解説</span><span class="sxs-lookup"><span data-stu-id="a1bee-120">Remarks</span></span>  

 <span data-ttu-id="a1bee-121">この構成要素は、ピア ノードがメッシュ内の他のノードに対して自身を認証するために使用する資格情報と、ピア ノードが他のピア ノードを認証するために使用する認証設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="a1bee-121">This configuration element specifies the credentials that a peer node uses to authenticate itself to other nodes in the mesh, as well as authentication settings that a peer node uses to authenticate other peer nodes.</span></span> <span data-ttu-id="a1bee-122">詳細については、「 [ピアチャネルメッセージ認証](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) 」および「 [ピアチャネルアプリケーションのセキュリティ保護](../../../wcf/feature-details/securing-peer-channel-applications.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1bee-122">For more information, see [Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) and [Securing Peer Channel Applications](../../../wcf/feature-details/securing-peer-channel-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1bee-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1bee-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="a1bee-124">ピアツーピアネットワーク</span><span class="sxs-lookup"><span data-stu-id="a1bee-124">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- [<span data-ttu-id="a1bee-125">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="a1bee-125">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- <span data-ttu-id="a1bee-126">[ピア チャネル メッセージの認証](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="a1bee-126">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="a1bee-127">[ピア チャネル カスタム認証](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="a1bee-127">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="a1bee-128">セキュリティによるピア チャネル アプリケーションの保護</span><span class="sxs-lookup"><span data-stu-id="a1bee-128">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="a1bee-129">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="a1bee-129">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
