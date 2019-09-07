---
title: <custom>
ms.date: 03/30/2017
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
ms.openlocfilehash: 598b341e8b09acd11ba215e6add3adf9e44b2b81
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400460"
---
# <a name="custom"></a><span data-ttu-id="ba1e0-101">\<custom></span><span class="sxs-lookup"><span data-stu-id="ba1e0-101">\<custom></span></span>
<span data-ttu-id="ba1e0-102">ユーザー設定のピア リゾルバー サービスの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="ba1e0-102">Specifies settings for a custom peer resolver service.</span></span>  
  
<span data-ttu-id="ba1e0-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ba1e0-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ba1e0-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ba1e0-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ba1e0-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<バインド >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="ba1e0-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="ba1e0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netPeerTcpBinding >** ](netpeertcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="ba1e0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)</span></span>\
<span data-ttu-id="ba1e0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<バインド >** </span><span class="sxs-lookup"><span data-stu-id="ba1e0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="ba1e0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<リゾルバー >** ](resolver.md)</span><span class="sxs-lookup"><span data-stu-id="ba1e0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<resolver>**](resolver.md)</span></span>\
<span data-ttu-id="ba1e0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<カスタム >**</span><span class="sxs-lookup"><span data-stu-id="ba1e0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<custom>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba1e0-110">構文</span><span class="sxs-lookup"><span data-stu-id="ba1e0-110">Syntax</span></span>  
  
```xml  
<custom address="Uri"
        resolverType="String">
  <headers/>
  <identity/>
</custom>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba1e0-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ba1e0-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ba1e0-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ba1e0-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba1e0-113">属性</span><span class="sxs-lookup"><span data-stu-id="ba1e0-113">Attributes</span></span>  
  
|<span data-ttu-id="ba1e0-114">属性</span><span class="sxs-lookup"><span data-stu-id="ba1e0-114">Attribute</span></span>|<span data-ttu-id="ba1e0-115">説明</span><span class="sxs-lookup"><span data-stu-id="ba1e0-115">Description</span></span>|  
|---------------|-----------------|  
|`address`|<span data-ttu-id="ba1e0-116">カスタム ピア リゾルバー サービスをホストするピア ノードのエンドポイント アドレスを指定する URI。</span><span class="sxs-lookup"><span data-stu-id="ba1e0-116">A URI that specifies the endpoint address of the peer node that hosts the custom peer resolver service.</span></span>|  
|`resolverType`|<span data-ttu-id="ba1e0-117">カスタム ピア リゾルバー サービスの種類を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="ba1e0-117">A string that specifies the type of the custom peer resolver service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ba1e0-118">子要素</span><span class="sxs-lookup"><span data-stu-id="ba1e0-118">Child Elements</span></span>  
  
|<span data-ttu-id="ba1e0-119">要素</span><span class="sxs-lookup"><span data-stu-id="ba1e0-119">Element</span></span>|<span data-ttu-id="ba1e0-120">説明</span><span class="sxs-lookup"><span data-stu-id="ba1e0-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ba1e0-121">\<identity></span><span class="sxs-lookup"><span data-stu-id="ba1e0-121">\<identity></span></span>](identity.md)|<span data-ttu-id="ba1e0-122">この要素を使用して構成されたカスタム ピア リゾルバーの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="ba1e0-122">Specifies the identity for custom peer resolvers configured with this element.</span></span> <span data-ttu-id="ba1e0-123">この要素は <xref:System.ServiceModel.Configuration.IdentityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="ba1e0-123">This element is of type <xref:System.ServiceModel.Configuration.IdentityElement>.</span></span>|  
|[<span data-ttu-id="ba1e0-124">\<headers></span><span class="sxs-lookup"><span data-stu-id="ba1e0-124">\<headers></span></span>](headers-element.md)|<span data-ttu-id="ba1e0-125">カスタム ピア リゾルバーによって処理される SOAP メッセージに使用するアドレス ヘッダーのコレクション。</span><span class="sxs-lookup"><span data-stu-id="ba1e0-125">A collection of address header used for SOAP messages handled by the custom peer resolver.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ba1e0-126">親要素</span><span class="sxs-lookup"><span data-stu-id="ba1e0-126">Parent Elements</span></span>  
  
|<span data-ttu-id="ba1e0-127">要素</span><span class="sxs-lookup"><span data-stu-id="ba1e0-127">Element</span></span>|<span data-ttu-id="ba1e0-128">説明</span><span class="sxs-lookup"><span data-stu-id="ba1e0-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ba1e0-129">\<resolver></span><span class="sxs-lookup"><span data-stu-id="ba1e0-129">\<resolver></span></span>](resolver.md)|<span data-ttu-id="ba1e0-130">ピア メッシュ ID を解決してメッシュに参加する複数ノードを表すピア ノード アドレスのセットを取得するために使用されるピア リゾルバー。</span><span class="sxs-lookup"><span data-stu-id="ba1e0-130">A peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba1e0-131">Remarks</span><span class="sxs-lookup"><span data-stu-id="ba1e0-131">Remarks</span></span>  
 <span data-ttu-id="ba1e0-132">この要素は、サービスをホストするピアのエンドポイント アドレスや特定のバインディング設定など、カスタム ピア リゾルバー サービスの基本設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="ba1e0-132">This element defines the basic settings for a custom peer resolver service, including the endpoint address of the peer hosting the service and any specific binding settings.</span></span> <span data-ttu-id="ba1e0-133">カスタム競合回避モジュールの作成の詳細については、「 [PeerChannel アプリケーションへのカスタム競合回避モジュールの追加](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba1e0-133">For more information on creating a custom resolver, see [Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba1e0-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="ba1e0-134">See also</span></span>

- <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>
- <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>
- <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>
- <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>
- [<span data-ttu-id="ba1e0-135">ピア リゾルバー</span><span class="sxs-lookup"><span data-stu-id="ba1e0-135">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
- <span data-ttu-id="ba1e0-136">[PeerChannel アプリケーションへのカスタム競合回避モジュールの追加](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="ba1e0-136">[Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span></span>
