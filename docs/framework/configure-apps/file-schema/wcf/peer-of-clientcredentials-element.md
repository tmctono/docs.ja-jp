---
title: <peer><clientCredentials>要素の
ms.date: 03/30/2017
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
ms.openlocfilehash: dce7ef64de1e3eb248e3553c97cbce8e9b205b4c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400098"
---
# <a name="peer-of-clientcredentials-element"></a><span data-ttu-id="84321-102">\<peer>\<clientCredentials>要素の</span><span class="sxs-lookup"><span data-stu-id="84321-102">\<peer> of \<clientCredentials> Element</span></span>
<span data-ttu-id="84321-103">ピアツーピア クライアントの認証時に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="84321-103">Specifies credentials used when authenticating peer-to-peer clients.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peer>**  
  
## <a name="syntax"></a><span data-ttu-id="84321-104">構文</span><span class="sxs-lookup"><span data-stu-id="84321-104">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="84321-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="84321-105">Attributes and Elements</span></span>  
 <span data-ttu-id="84321-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="84321-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="84321-107">属性</span><span class="sxs-lookup"><span data-stu-id="84321-107">Attributes</span></span>  
 <span data-ttu-id="84321-108">なし。</span><span class="sxs-lookup"><span data-stu-id="84321-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="84321-109">子要素</span><span class="sxs-lookup"><span data-stu-id="84321-109">Child Elements</span></span>  
  
|<span data-ttu-id="84321-110">要素</span><span class="sxs-lookup"><span data-stu-id="84321-110">Element</span></span>|<span data-ttu-id="84321-111">説明</span><span class="sxs-lookup"><span data-stu-id="84321-111">Description</span></span>|  
|-------------|-----------------|  
|[\<certificate>](certificate-element.md)|<span data-ttu-id="84321-112">ピアツーピア クライアントのメッセージの署名と暗号化に使用する X.509 証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="84321-112">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span> <span data-ttu-id="84321-113">.</span><span class="sxs-lookup"><span data-stu-id="84321-113">.</span></span>|  
|[\<peerAuthentication>](peerauthentication-element.md)|<span data-ttu-id="84321-114">ピア クライアントの認証オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="84321-114">Specifies authentication options for peer clients.</span></span>|  
|[\<messageSenderAuthentication>](messagesenderauthentication-element.md)|<span data-ttu-id="84321-115">メッセージ送信者の認証オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="84321-115">Specifies authentication options for message senders.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="84321-116">親要素</span><span class="sxs-lookup"><span data-stu-id="84321-116">Parent Elements</span></span>  
  
|<span data-ttu-id="84321-117">要素</span><span class="sxs-lookup"><span data-stu-id="84321-117">Element</span></span>|<span data-ttu-id="84321-118">説明</span><span class="sxs-lookup"><span data-stu-id="84321-118">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="84321-119">サービスに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="84321-119">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84321-120">解説</span><span class="sxs-lookup"><span data-stu-id="84321-120">Remarks</span></span>  
 <span data-ttu-id="84321-121">この構成要素は、ピア ノードがメッシュ内の他のノードに対して自身を認証するために使用する資格情報と、ピア ノードが他のピア ノードを認証するために使用する認証設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="84321-121">This configuration element specifies the credentials that a peer node uses to authenticate itself to other nodes in the mesh, as well as authentication settings that a peer node uses to authenticate other peer nodes.</span></span> <span data-ttu-id="84321-122">詳細については、「[ピアチャネルメッセージ認証](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))」および「[ピアチャネルアプリケーションのセキュリティ保護](../../../wcf/feature-details/securing-peer-channel-applications.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84321-122">For more information, see [Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) and [Securing Peer Channel Applications](../../../wcf/feature-details/securing-peer-channel-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84321-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="84321-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="84321-124">ピアツーピア ネットワーク</span><span class="sxs-lookup"><span data-stu-id="84321-124">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- [<span data-ttu-id="84321-125">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="84321-125">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- <span data-ttu-id="84321-126">[ピア チャネル メッセージの認証](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="84321-126">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="84321-127">[ピア チャネル カスタム認証](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="84321-127">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="84321-128">セキュリティによるピア チャネル アプリケーションの保護</span><span class="sxs-lookup"><span data-stu-id="84321-128">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="84321-129">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="84321-129">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
