---
title: <custom>
ms.date: 03/30/2017
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
ms.openlocfilehash: 5ff066c32f7d08ec989d6cd04e16c89f0a36f6fa
ms.sourcegitcommit: b8ace47d839f943f785b89e2fff8092b0bf8f565
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "55675024"
---
# <a name="custom"></a><span data-ttu-id="8c376-101">\<custom></span><span class="sxs-lookup"><span data-stu-id="8c376-101">\<custom></span></span>
<span data-ttu-id="8c376-102">ユーザー設定のピア リゾルバー サービスの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="8c376-102">Specifies settings for a custom peer resolver service.</span></span>  
  
<span data-ttu-id="8c376-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="8c376-103">\<system.serviceModel></span></span>  
<span data-ttu-id="8c376-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="8c376-104">\<bindings></span></span>  
<span data-ttu-id="8c376-105">\<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="8c376-105">\<netPeerBinding></span></span>  
<span data-ttu-id="8c376-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="8c376-106">\<binding></span></span>  
<span data-ttu-id="8c376-107">\<resolver></span><span class="sxs-lookup"><span data-stu-id="8c376-107">\<resolver></span></span>  
<span data-ttu-id="8c376-108">\<custom></span><span class="sxs-lookup"><span data-stu-id="8c376-108">\<custom></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c376-109">構文</span><span class="sxs-lookup"><span data-stu-id="8c376-109">Syntax</span></span>  
  
```xml  
<custom address="Uri"
        resolverType="String">
  <headers/>
  <identity/>
</custom>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c376-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8c376-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8c376-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8c376-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8c376-112">属性</span><span class="sxs-lookup"><span data-stu-id="8c376-112">Attributes</span></span>  
  
|<span data-ttu-id="8c376-113">属性</span><span class="sxs-lookup"><span data-stu-id="8c376-113">Attribute</span></span>|<span data-ttu-id="8c376-114">説明</span><span class="sxs-lookup"><span data-stu-id="8c376-114">Description</span></span>|  
|---------------|-----------------|  
|`address`|<span data-ttu-id="8c376-115">カスタム ピア リゾルバー サービスをホストするピア ノードのエンドポイント アドレスを指定する URI。</span><span class="sxs-lookup"><span data-stu-id="8c376-115">A URI that specifies the endpoint address of the peer node that hosts the custom peer resolver service.</span></span>|  
|`resolverType`|<span data-ttu-id="8c376-116">カスタム ピア リゾルバー サービスの種類を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="8c376-116">A string that specifies the type of the custom peer resolver service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8c376-117">子要素</span><span class="sxs-lookup"><span data-stu-id="8c376-117">Child Elements</span></span>  
  
|<span data-ttu-id="8c376-118">要素</span><span class="sxs-lookup"><span data-stu-id="8c376-118">Element</span></span>|<span data-ttu-id="8c376-119">説明</span><span class="sxs-lookup"><span data-stu-id="8c376-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c376-120">\<identity></span><span class="sxs-lookup"><span data-stu-id="8c376-120">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="8c376-121">この要素を使用して構成されたカスタム ピア リゾルバーの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="8c376-121">Specifies the identity for custom peer resolvers configured with this element.</span></span> <span data-ttu-id="8c376-122">この要素は <xref:System.ServiceModel.Configuration.IdentityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="8c376-122">This element is of type <xref:System.ServiceModel.Configuration.IdentityElement>.</span></span>|  
|[<span data-ttu-id="8c376-123">\<headers></span><span class="sxs-lookup"><span data-stu-id="8c376-123">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="8c376-124">カスタム ピア リゾルバーによって処理される SOAP メッセージに使用するアドレス ヘッダーのコレクション。</span><span class="sxs-lookup"><span data-stu-id="8c376-124">A collection of address header used for SOAP messages handled by the custom peer resolver.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8c376-125">親要素</span><span class="sxs-lookup"><span data-stu-id="8c376-125">Parent Elements</span></span>  
  
|<span data-ttu-id="8c376-126">要素</span><span class="sxs-lookup"><span data-stu-id="8c376-126">Element</span></span>|<span data-ttu-id="8c376-127">説明</span><span class="sxs-lookup"><span data-stu-id="8c376-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c376-128">\<resolver></span><span class="sxs-lookup"><span data-stu-id="8c376-128">\<resolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/resolver.md)|<span data-ttu-id="8c376-129">ピア メッシュ ID を解決してメッシュに参加する複数ノードを表すピア ノード アドレスのセットを取得するために使用されるピア リゾルバー。</span><span class="sxs-lookup"><span data-stu-id="8c376-129">A peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c376-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="8c376-130">Remarks</span></span>  
 <span data-ttu-id="8c376-131">この要素は、サービスをホストするピアのエンドポイント アドレスや特定のバインディング設定など、カスタム ピア リゾルバー サービスの基本設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="8c376-131">This element defines the basic settings for a custom peer resolver service, including the endpoint address of the peer hosting the service and any specific binding settings.</span></span> <span data-ttu-id="8c376-132">カスタム競合回避モジュールを作成する方法の詳細については、[PeerChannel アプリケーションへのカスタム競合回避モジュールの追加](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c376-132">For more information on creating a custom resolver, see [Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c376-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="8c376-133">See also</span></span>
- <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>
- <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>
- <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>
- <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>
- [<span data-ttu-id="8c376-134">ピア リゾルバー</span><span class="sxs-lookup"><span data-stu-id="8c376-134">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)
- <span data-ttu-id="8c376-135">[PeerChannel アプリケーションへのカスタム競合回避モジュールの追加](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="8c376-135">[Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span></span>
