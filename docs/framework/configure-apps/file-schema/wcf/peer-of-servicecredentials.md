---
title: <peer> の <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: b134e21d-e5b5-458e-9309-626dbf8db4ed
ms.openlocfilehash: 7f6669d3f53a6ee0d189786fa9ca3625fdedd127
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91162479"
---
# <a name="peer-of-servicecredentials"></a><span data-ttu-id="70a69-102">\<peer> の \<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="70a69-102">\<peer> of \<serviceCredentials></span></span>

<span data-ttu-id="70a69-103">ピア ノードの現在の資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="70a69-103">Specifies the current credentials for a peer node.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peer>**  
  
## <a name="syntax"></a><span data-ttu-id="70a69-104">構文</span><span class="sxs-lookup"><span data-stu-id="70a69-104">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="70a69-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="70a69-105">Attributes and Elements</span></span>  

 <span data-ttu-id="70a69-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="70a69-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="70a69-107">属性</span><span class="sxs-lookup"><span data-stu-id="70a69-107">Attributes</span></span>  

 <span data-ttu-id="70a69-108">なし。</span><span class="sxs-lookup"><span data-stu-id="70a69-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="70a69-109">子要素</span><span class="sxs-lookup"><span data-stu-id="70a69-109">Child Elements</span></span>  
  
|<span data-ttu-id="70a69-110">要素</span><span class="sxs-lookup"><span data-stu-id="70a69-110">Element</span></span>|<span data-ttu-id="70a69-111">説明</span><span class="sxs-lookup"><span data-stu-id="70a69-111">Description</span></span>|  
|-------------|-----------------|  
|[\<certificate>](certificate-of-peer.md)|<span data-ttu-id="70a69-112">ピアツーピア サービスのメッセージの署名と暗号化に使用する X.509 証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="70a69-112">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer services.</span></span> <span data-ttu-id="70a69-113">.</span><span class="sxs-lookup"><span data-stu-id="70a69-113">.</span></span>|  
|[\<messageSenderAuthentication>](messagesenderauthentication.md)|<span data-ttu-id="70a69-114">メッセージ送信者の認証オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="70a69-114">Specifies authentication options for message senders.</span></span>|  
|[\<peerAuthentication>](peerauthentication.md)|<span data-ttu-id="70a69-115">ピア サービスの認証オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="70a69-115">Specifies authentication options for peer services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="70a69-116">親要素</span><span class="sxs-lookup"><span data-stu-id="70a69-116">Parent Elements</span></span>  
  
|<span data-ttu-id="70a69-117">要素</span><span class="sxs-lookup"><span data-stu-id="70a69-117">Element</span></span>|<span data-ttu-id="70a69-118">説明</span><span class="sxs-lookup"><span data-stu-id="70a69-118">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="70a69-119">サービスの認証に使用される資格情報と、クライアントの資格情報検証関連の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="70a69-119">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="70a69-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="70a69-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="70a69-121">ピアツーピアネットワーク</span><span class="sxs-lookup"><span data-stu-id="70a69-121">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="70a69-122">[ピア チャネル メッセージの認証](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="70a69-122">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="70a69-123">[ピア チャネル カスタム認証](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="70a69-123">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="70a69-124">セキュリティによるピア チャネル アプリケーションの保護</span><span class="sxs-lookup"><span data-stu-id="70a69-124">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="70a69-125">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="70a69-125">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
