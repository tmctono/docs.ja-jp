---
title: <custom>
ms.date: 03/30/2017
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
ms.openlocfilehash: b5cc522604fa7aca8ca6eae787520265b36fef6f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925949"
---
# <a name="custom"></a><span data-ttu-id="2ca03-101">\<custom></span><span class="sxs-lookup"><span data-stu-id="2ca03-101">\<custom></span></span>
<span data-ttu-id="2ca03-102">ユーザー設定のピア リゾルバー サービスの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="2ca03-102">Specifies settings for a custom peer resolver service.</span></span>  
  
<span data-ttu-id="2ca03-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2ca03-103">\<system.serviceModel></span></span>  
<span data-ttu-id="2ca03-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="2ca03-104">\<bindings></span></span>  
<span data-ttu-id="2ca03-105">\<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="2ca03-105">\<netPeerBinding></span></span>  
<span data-ttu-id="2ca03-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="2ca03-106">\<binding></span></span>  
<span data-ttu-id="2ca03-107">\<resolver></span><span class="sxs-lookup"><span data-stu-id="2ca03-107">\<resolver></span></span>  
<span data-ttu-id="2ca03-108">\<custom></span><span class="sxs-lookup"><span data-stu-id="2ca03-108">\<custom></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ca03-109">構文</span><span class="sxs-lookup"><span data-stu-id="2ca03-109">Syntax</span></span>  
  
```xml  
<custom address="Uri"
        resolverType="String">
  <headers/>
  <identity/>
</custom>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2ca03-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="2ca03-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2ca03-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2ca03-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2ca03-112">属性</span><span class="sxs-lookup"><span data-stu-id="2ca03-112">Attributes</span></span>  
  
|<span data-ttu-id="2ca03-113">属性</span><span class="sxs-lookup"><span data-stu-id="2ca03-113">Attribute</span></span>|<span data-ttu-id="2ca03-114">説明</span><span class="sxs-lookup"><span data-stu-id="2ca03-114">Description</span></span>|  
|---------------|-----------------|  
|`address`|<span data-ttu-id="2ca03-115">カスタム ピア リゾルバー サービスをホストするピア ノードのエンドポイント アドレスを指定する URI。</span><span class="sxs-lookup"><span data-stu-id="2ca03-115">A URI that specifies the endpoint address of the peer node that hosts the custom peer resolver service.</span></span>|  
|`resolverType`|<span data-ttu-id="2ca03-116">カスタム ピア リゾルバー サービスの種類を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="2ca03-116">A string that specifies the type of the custom peer resolver service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2ca03-117">子要素</span><span class="sxs-lookup"><span data-stu-id="2ca03-117">Child Elements</span></span>  
  
|<span data-ttu-id="2ca03-118">要素</span><span class="sxs-lookup"><span data-stu-id="2ca03-118">Element</span></span>|<span data-ttu-id="2ca03-119">説明</span><span class="sxs-lookup"><span data-stu-id="2ca03-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2ca03-120">\<identity></span><span class="sxs-lookup"><span data-stu-id="2ca03-120">\<identity></span></span>](identity.md)|<span data-ttu-id="2ca03-121">この要素を使用して構成されたカスタム ピア リゾルバーの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="2ca03-121">Specifies the identity for custom peer resolvers configured with this element.</span></span> <span data-ttu-id="2ca03-122">この要素は <xref:System.ServiceModel.Configuration.IdentityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="2ca03-122">This element is of type <xref:System.ServiceModel.Configuration.IdentityElement>.</span></span>|  
|[<span data-ttu-id="2ca03-123">\<headers></span><span class="sxs-lookup"><span data-stu-id="2ca03-123">\<headers></span></span>](headers-element.md)|<span data-ttu-id="2ca03-124">カスタム ピア リゾルバーによって処理される SOAP メッセージに使用するアドレス ヘッダーのコレクション。</span><span class="sxs-lookup"><span data-stu-id="2ca03-124">A collection of address header used for SOAP messages handled by the custom peer resolver.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2ca03-125">親要素</span><span class="sxs-lookup"><span data-stu-id="2ca03-125">Parent Elements</span></span>  
  
|<span data-ttu-id="2ca03-126">要素</span><span class="sxs-lookup"><span data-stu-id="2ca03-126">Element</span></span>|<span data-ttu-id="2ca03-127">説明</span><span class="sxs-lookup"><span data-stu-id="2ca03-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2ca03-128">\<resolver></span><span class="sxs-lookup"><span data-stu-id="2ca03-128">\<resolver></span></span>](resolver.md)|<span data-ttu-id="2ca03-129">ピア メッシュ ID を解決してメッシュに参加する複数ノードを表すピア ノード アドレスのセットを取得するために使用されるピア リゾルバー。</span><span class="sxs-lookup"><span data-stu-id="2ca03-129">A peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ca03-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="2ca03-130">Remarks</span></span>  
 <span data-ttu-id="2ca03-131">この要素は、サービスをホストするピアのエンドポイント アドレスや特定のバインディング設定など、カスタム ピア リゾルバー サービスの基本設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="2ca03-131">This element defines the basic settings for a custom peer resolver service, including the endpoint address of the peer hosting the service and any specific binding settings.</span></span> <span data-ttu-id="2ca03-132">カスタム競合回避モジュールの作成の詳細については、「 [PeerChannel アプリケーションへのカスタム競合回避モジュールの追加](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ca03-132">For more information on creating a custom resolver, see [Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ca03-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ca03-133">See also</span></span>

- <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>
- <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>
- <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>
- <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>
- [<span data-ttu-id="2ca03-134">ピア リゾルバー</span><span class="sxs-lookup"><span data-stu-id="2ca03-134">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
- <span data-ttu-id="2ca03-135">[PeerChannel アプリケーションへのカスタム競合回避モジュールの追加](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="2ca03-135">[Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span></span>
