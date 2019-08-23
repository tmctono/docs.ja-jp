---
title: <resolver>
ms.date: 03/30/2017
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
ms.openlocfilehash: e3a9ee00aab6ab48a1ba891565b63824e62b20fe
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934225"
---
# <a name="resolver"></a><span data-ttu-id="67ab5-101">\<resolver></span><span class="sxs-lookup"><span data-stu-id="67ab5-101">\<resolver></span></span>
<span data-ttu-id="67ab5-102">ピア メッシュ ID を解決してメッシュに参加する複数ノードを表すピア アドレス セットを取得するためにピア リゾルバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="67ab5-102">Specifies a peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>  
  
 <span data-ttu-id="67ab5-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="67ab5-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="67ab5-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="67ab5-104">\<bindings></span></span>  
<span data-ttu-id="67ab5-105">\<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="67ab5-105">\<netPeerBinding></span></span>  
<span data-ttu-id="67ab5-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="67ab5-106">\<binding></span></span>  
<span data-ttu-id="67ab5-107">\<resolver></span><span class="sxs-lookup"><span data-stu-id="67ab5-107">\<resolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67ab5-108">構文</span><span class="sxs-lookup"><span data-stu-id="67ab5-108">Syntax</span></span>  
  
```xml  
<resolver mode="Auto/Custom/Pnrp"
          referralPolicy="DoNotShare/Service/Share">
</resolver>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="67ab5-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="67ab5-109">Attributes and Elements</span></span>  
 <span data-ttu-id="67ab5-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="67ab5-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="67ab5-111">属性</span><span class="sxs-lookup"><span data-stu-id="67ab5-111">Attributes</span></span>  
  
|<span data-ttu-id="67ab5-112">属性</span><span class="sxs-lookup"><span data-stu-id="67ab5-112">Attribute</span></span>|<span data-ttu-id="67ab5-113">説明</span><span class="sxs-lookup"><span data-stu-id="67ab5-113">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="67ab5-114">このサービスに関連付けられるピア リゾルバー インスタンスが PNRP 固有、カスタム リゾルバー、自動的に決定されるのいずれであるかを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="67ab5-114">A string that specifies whether the peer resolver instance associated with this service is either PNRP-specific, a custom resolver, or automatically determined.</span></span> <span data-ttu-id="67ab5-115">この属性は <xref:System.ServiceModel.PeerResolvers.PeerResolverMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="67ab5-115">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span></span>|  
|`referralPolicy`|<span data-ttu-id="67ab5-116">ピア間で参照を共有する方法を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="67ab5-116">A string that specifies the way referrals are shared among peers.</span></span> <span data-ttu-id="67ab5-117">この属性は <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy> 型です。</span><span class="sxs-lookup"><span data-stu-id="67ab5-117">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="67ab5-118">子要素</span><span class="sxs-lookup"><span data-stu-id="67ab5-118">Child Elements</span></span>  
  
|<span data-ttu-id="67ab5-119">要素</span><span class="sxs-lookup"><span data-stu-id="67ab5-119">Element</span></span>|<span data-ttu-id="67ab5-120">説明</span><span class="sxs-lookup"><span data-stu-id="67ab5-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="67ab5-121">\<headers></span><span class="sxs-lookup"><span data-stu-id="67ab5-121">\<headers></span></span>](headers.md)|<span data-ttu-id="67ab5-122">ユーザー設定のピア リゾルバー サービスの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="67ab5-122">Specifies settings for a custom peer resolver service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="67ab5-123">親要素</span><span class="sxs-lookup"><span data-stu-id="67ab5-123">Parent Elements</span></span>  
  
|<span data-ttu-id="67ab5-124">要素</span><span class="sxs-lookup"><span data-stu-id="67ab5-124">Element</span></span>|<span data-ttu-id="67ab5-125">説明</span><span class="sxs-lookup"><span data-stu-id="67ab5-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="67ab5-126">\<binding></span><span class="sxs-lookup"><span data-stu-id="67ab5-126">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="67ab5-127">Netpeertcpbinding > のすべてのバインド機能を[ \<](netpeertcpbinding.md)定義します。</span><span class="sxs-lookup"><span data-stu-id="67ab5-127">Defines all binding capabilities of the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67ab5-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="67ab5-128">Remarks</span></span>  
 <span data-ttu-id="67ab5-129">ピア名リゾルバーは、ピア メッシュに参加するピア ノードを検索するためにピア チャネルにより使用される探索サービスです。</span><span class="sxs-lookup"><span data-stu-id="67ab5-129">A peer name resolver is a discovery service used by peer channels to find peer nodes that participate in a peer mesh.</span></span> <span data-ttu-id="67ab5-130">またピア名リゾルバーは、ノードをピア メッシュに登録するために使用されます。ピア メッシュは、ピア メッシュからピア ノードを認識し、使用可能にするための機構です。</span><span class="sxs-lookup"><span data-stu-id="67ab5-130">It is also used to "register" a node with a peer mesh, the mechanism by which the peer node becomes known and available from the peer mesh.</span></span> <span data-ttu-id="67ab5-131">ピアリゾルバーの詳細については、「[ピアリゾルバー](../../../wcf/feature-details/peer-resolvers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67ab5-131">For more information on peer resolvers, see [Peer Resolvers](../../../wcf/feature-details/peer-resolvers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67ab5-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="67ab5-132">See also</span></span>

- <xref:System.ServiceModel.PeerResolver>
- <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>
- <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>
- <xref:System.ServiceModel.Configuration.PeerResolverElement>
- [<span data-ttu-id="67ab5-133">ピア リゾルバー</span><span class="sxs-lookup"><span data-stu-id="67ab5-133">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
- <span data-ttu-id="67ab5-134">[PeerChannel アプリケーションへのカスタム競合回避モジュールの追加](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="67ab5-134">[Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span></span>
