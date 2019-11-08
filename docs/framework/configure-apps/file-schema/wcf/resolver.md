---
title: <resolver>
ms.date: 03/30/2017
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
ms.openlocfilehash: 0dc667f392595d895bd4f2773ab69777d7369446
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738740"
---
# <a name="resolver"></a><span data-ttu-id="553a0-101">\<リゾルバー ></span><span class="sxs-lookup"><span data-stu-id="553a0-101">\<resolver></span></span>
<span data-ttu-id="553a0-102">ピア メッシュ ID を解決してメッシュに参加する複数ノードを表すピア アドレス セットを取得するためにピア リゾルバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="553a0-102">Specifies a peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>  
  
<span data-ttu-id="553a0-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="553a0-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="553a0-104">&nbsp; &nbsp;[ **\<system >** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="553a0-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="553a0-105">&nbsp;&nbsp;&nbsp;&nbsp;\<[**バインド**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="553a0-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="553a0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**netPeerTcpBinding\<** ](netpeertcpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="553a0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)\</span></span>
<span data-ttu-id="553a0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**バインド >** </span><span class="sxs-lookup"><span data-stu-id="553a0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="553a0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**リゾルバー >**</span><span class="sxs-lookup"><span data-stu-id="553a0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<resolver>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="553a0-109">構文</span><span class="sxs-lookup"><span data-stu-id="553a0-109">Syntax</span></span>  
  
```xml  
<resolver mode="Auto/Custom/Pnrp"
          referralPolicy="DoNotShare/Service/Share">
</resolver>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="553a0-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="553a0-110">Attributes and Elements</span></span>  
 <span data-ttu-id="553a0-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="553a0-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="553a0-112">属性</span><span class="sxs-lookup"><span data-stu-id="553a0-112">Attributes</span></span>  
  
|<span data-ttu-id="553a0-113">属性</span><span class="sxs-lookup"><span data-stu-id="553a0-113">Attribute</span></span>|<span data-ttu-id="553a0-114">説明</span><span class="sxs-lookup"><span data-stu-id="553a0-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="553a0-115">このサービスに関連付けられるピア リゾルバー インスタンスが PNRP 固有、カスタム リゾルバー、自動的に決定されるのいずれであるかを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="553a0-115">A string that specifies whether the peer resolver instance associated with this service is either PNRP-specific, a custom resolver, or automatically determined.</span></span> <span data-ttu-id="553a0-116">この属性は <xref:System.ServiceModel.PeerResolvers.PeerResolverMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="553a0-116">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span></span>|  
|`referralPolicy`|<span data-ttu-id="553a0-117">ピア間で参照を共有する方法を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="553a0-117">A string that specifies the way referrals are shared among peers.</span></span> <span data-ttu-id="553a0-118">この属性は <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy> 型です。</span><span class="sxs-lookup"><span data-stu-id="553a0-118">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="553a0-119">子要素</span><span class="sxs-lookup"><span data-stu-id="553a0-119">Child Elements</span></span>  
  
|<span data-ttu-id="553a0-120">要素</span><span class="sxs-lookup"><span data-stu-id="553a0-120">Element</span></span>|<span data-ttu-id="553a0-121">説明</span><span class="sxs-lookup"><span data-stu-id="553a0-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="553a0-122">\<ヘッダー ></span><span class="sxs-lookup"><span data-stu-id="553a0-122">\<headers></span></span>](headers.md)|<span data-ttu-id="553a0-123">ユーザー設定のピア リゾルバー サービスの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="553a0-123">Specifies settings for a custom peer resolver service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="553a0-124">親要素</span><span class="sxs-lookup"><span data-stu-id="553a0-124">Parent Elements</span></span>  
  
|<span data-ttu-id="553a0-125">要素</span><span class="sxs-lookup"><span data-stu-id="553a0-125">Element</span></span>|<span data-ttu-id="553a0-126">説明</span><span class="sxs-lookup"><span data-stu-id="553a0-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="553a0-127">\<binding ></span><span class="sxs-lookup"><span data-stu-id="553a0-127">\<binding></span></span>](bindings.md)|<span data-ttu-id="553a0-128">[\<netPeerTcpBinding >](netpeertcpbinding.md)のすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="553a0-128">Defines all binding capabilities of the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="553a0-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="553a0-129">Remarks</span></span>  
 <span data-ttu-id="553a0-130">ピア名リゾルバーは、ピア メッシュに参加するピア ノードを検索するためにピア チャネルにより使用される探索サービスです。</span><span class="sxs-lookup"><span data-stu-id="553a0-130">A peer name resolver is a discovery service used by peer channels to find peer nodes that participate in a peer mesh.</span></span> <span data-ttu-id="553a0-131">またピア名リゾルバーは、ノードをピア メッシュに登録するために使用されます。ピア メッシュは、ピア メッシュからピア ノードを認識し、使用可能にするための機構です。</span><span class="sxs-lookup"><span data-stu-id="553a0-131">It is also used to "register" a node with a peer mesh, the mechanism by which the peer node becomes known and available from the peer mesh.</span></span> <span data-ttu-id="553a0-132">ピアリゾルバーの詳細については、「[ピアリゾルバー](../../../wcf/feature-details/peer-resolvers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="553a0-132">For more information on peer resolvers, see [Peer Resolvers](../../../wcf/feature-details/peer-resolvers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="553a0-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="553a0-133">See also</span></span>

- <xref:System.ServiceModel.PeerResolver>
- <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>
- <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>
- <xref:System.ServiceModel.Configuration.PeerResolverElement>
- [<span data-ttu-id="553a0-134">ピア リゾルバー</span><span class="sxs-lookup"><span data-stu-id="553a0-134">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
- <span data-ttu-id="553a0-135">[PeerChannel アプリケーションへのカスタム競合回避モジュールの追加](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="553a0-135">[Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span></span>
