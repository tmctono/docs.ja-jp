---
title: <resolver>
ms.date: 03/30/2017
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
ms.openlocfilehash: 6b1fd8e916aef2425377c45a0c85e37773f3ca28
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150896"
---
# \<resolver>

<span data-ttu-id="f0310-101">ピア メッシュ ID を解決してメッシュに参加する複数ノードを表すピア アドレス セットを取得するためにピア リゾルバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="f0310-101">Specifies a peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<resolver>**  
  
## <a name="syntax"></a><span data-ttu-id="f0310-102">構文</span><span class="sxs-lookup"><span data-stu-id="f0310-102">Syntax</span></span>  
  
```xml  
<resolver mode="Auto/Custom/Pnrp"
          referralPolicy="DoNotShare/Service/Share">
</resolver>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f0310-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f0310-103">Attributes and Elements</span></span>  

 <span data-ttu-id="f0310-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f0310-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f0310-105">属性</span><span class="sxs-lookup"><span data-stu-id="f0310-105">Attributes</span></span>  
  
|<span data-ttu-id="f0310-106">属性</span><span class="sxs-lookup"><span data-stu-id="f0310-106">Attribute</span></span>|<span data-ttu-id="f0310-107">[説明]</span><span class="sxs-lookup"><span data-stu-id="f0310-107">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="f0310-108">このサービスに関連付けられるピア リゾルバー インスタンスが PNRP 固有、カスタム リゾルバー、自動的に決定されるのいずれであるかを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="f0310-108">A string that specifies whether the peer resolver instance associated with this service is either PNRP-specific, a custom resolver, or automatically determined.</span></span> <span data-ttu-id="f0310-109">この属性は <xref:System.ServiceModel.PeerResolvers.PeerResolverMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="f0310-109">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span></span>|  
|`referralPolicy`|<span data-ttu-id="f0310-110">ピア間で参照を共有する方法を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="f0310-110">A string that specifies the way referrals are shared among peers.</span></span> <span data-ttu-id="f0310-111">この属性は <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy> 型です。</span><span class="sxs-lookup"><span data-stu-id="f0310-111">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f0310-112">子要素</span><span class="sxs-lookup"><span data-stu-id="f0310-112">Child Elements</span></span>  
  
|<span data-ttu-id="f0310-113">要素</span><span class="sxs-lookup"><span data-stu-id="f0310-113">Element</span></span>|<span data-ttu-id="f0310-114">説明</span><span class="sxs-lookup"><span data-stu-id="f0310-114">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers.md)|<span data-ttu-id="f0310-115">ユーザー設定のピア リゾルバー サービスの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="f0310-115">Specifies settings for a custom peer resolver service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f0310-116">親要素</span><span class="sxs-lookup"><span data-stu-id="f0310-116">Parent Elements</span></span>  
  
|<span data-ttu-id="f0310-117">要素</span><span class="sxs-lookup"><span data-stu-id="f0310-117">Element</span></span>|<span data-ttu-id="f0310-118">説明</span><span class="sxs-lookup"><span data-stu-id="f0310-118">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="f0310-119">のすべてのバインディング機能を定義 [\<netPeerTcpBinding>](netpeertcpbinding.md) します。</span><span class="sxs-lookup"><span data-stu-id="f0310-119">Defines all binding capabilities of the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0310-120">解説</span><span class="sxs-lookup"><span data-stu-id="f0310-120">Remarks</span></span>  

 <span data-ttu-id="f0310-121">ピア名リゾルバーは、ピア メッシュに参加するピア ノードを検索するためにピア チャネルにより使用される探索サービスです。</span><span class="sxs-lookup"><span data-stu-id="f0310-121">A peer name resolver is a discovery service used by peer channels to find peer nodes that participate in a peer mesh.</span></span> <span data-ttu-id="f0310-122">またピア名リゾルバーは、ノードをピア メッシュに登録するために使用されます。ピア メッシュは、ピア メッシュからピア ノードを認識し、使用可能にするための機構です。</span><span class="sxs-lookup"><span data-stu-id="f0310-122">It is also used to "register" a node with a peer mesh, the mechanism by which the peer node becomes known and available from the peer mesh.</span></span> <span data-ttu-id="f0310-123">ピアリゾルバーの詳細については、「 [ピアリゾルバー](../../../wcf/feature-details/peer-resolvers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0310-123">For more information on peer resolvers, see [Peer Resolvers](../../../wcf/feature-details/peer-resolvers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0310-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="f0310-124">See also</span></span>

- <xref:System.ServiceModel.PeerResolver>
- <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>
- <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>
- <xref:System.ServiceModel.Configuration.PeerResolverElement>
- [<span data-ttu-id="f0310-125">ピア リゾルバー</span><span class="sxs-lookup"><span data-stu-id="f0310-125">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
- <span data-ttu-id="f0310-126">[PeerChannel アプリケーションへのカスタム リゾルバーの追加](/previous-versions/ms730105(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="f0310-126">[Adding a Custom Resolver to a PeerChannel Application](/previous-versions/ms730105(v=vs.90))</span></span>
