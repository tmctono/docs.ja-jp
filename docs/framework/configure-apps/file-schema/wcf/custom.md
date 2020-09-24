---
title: <custom>
ms.date: 03/30/2017
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
ms.openlocfilehash: c208a6c7305ccbbe8efb10d071de29cf1bd2cc10
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91165144"
---
# \<custom>

<span data-ttu-id="56850-101">ユーザー設定のピア リゾルバー サービスの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="56850-101">Specifies settings for a custom peer resolver service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<resolver>**](resolver.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<custom>**  
  
## <a name="syntax"></a><span data-ttu-id="56850-102">構文</span><span class="sxs-lookup"><span data-stu-id="56850-102">Syntax</span></span>  
  
```xml  
<custom address="Uri"
        resolverType="String">
  <headers/>
  <identity/>
</custom>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="56850-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="56850-103">Attributes and Elements</span></span>  

 <span data-ttu-id="56850-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="56850-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="56850-105">属性</span><span class="sxs-lookup"><span data-stu-id="56850-105">Attributes</span></span>  
  
|<span data-ttu-id="56850-106">属性</span><span class="sxs-lookup"><span data-stu-id="56850-106">Attribute</span></span>|<span data-ttu-id="56850-107">[説明]</span><span class="sxs-lookup"><span data-stu-id="56850-107">Description</span></span>|  
|---------------|-----------------|  
|`address`|<span data-ttu-id="56850-108">カスタム ピア リゾルバー サービスをホストするピア ノードのエンドポイント アドレスを指定する URI。</span><span class="sxs-lookup"><span data-stu-id="56850-108">A URI that specifies the endpoint address of the peer node that hosts the custom peer resolver service.</span></span>|  
|`resolverType`|<span data-ttu-id="56850-109">カスタム ピア リゾルバー サービスの種類を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="56850-109">A string that specifies the type of the custom peer resolver service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="56850-110">子要素</span><span class="sxs-lookup"><span data-stu-id="56850-110">Child Elements</span></span>  
  
|<span data-ttu-id="56850-111">要素</span><span class="sxs-lookup"><span data-stu-id="56850-111">Element</span></span>|<span data-ttu-id="56850-112">説明</span><span class="sxs-lookup"><span data-stu-id="56850-112">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="56850-113">この要素を使用して構成されたカスタム ピア リゾルバーの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="56850-113">Specifies the identity for custom peer resolvers configured with this element.</span></span> <span data-ttu-id="56850-114">この要素は <xref:System.ServiceModel.Configuration.IdentityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="56850-114">This element is of type <xref:System.ServiceModel.Configuration.IdentityElement>.</span></span>|  
|[\<headers>](headers-element.md)|<span data-ttu-id="56850-115">カスタム ピア リゾルバーによって処理される SOAP メッセージに使用するアドレス ヘッダーのコレクション。</span><span class="sxs-lookup"><span data-stu-id="56850-115">A collection of address header used for SOAP messages handled by the custom peer resolver.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="56850-116">親要素</span><span class="sxs-lookup"><span data-stu-id="56850-116">Parent Elements</span></span>  
  
|<span data-ttu-id="56850-117">要素</span><span class="sxs-lookup"><span data-stu-id="56850-117">Element</span></span>|<span data-ttu-id="56850-118">説明</span><span class="sxs-lookup"><span data-stu-id="56850-118">Description</span></span>|  
|-------------|-----------------|  
|[\<resolver>](resolver.md)|<span data-ttu-id="56850-119">ピア メッシュ ID を解決してメッシュに参加する複数ノードを表すピア ノード アドレスのセットを取得するために使用されるピア リゾルバー。</span><span class="sxs-lookup"><span data-stu-id="56850-119">A peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="56850-120">解説</span><span class="sxs-lookup"><span data-stu-id="56850-120">Remarks</span></span>  

 <span data-ttu-id="56850-121">この要素は、サービスをホストするピアのエンドポイント アドレスや特定のバインディング設定など、カスタム ピア リゾルバー サービスの基本設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="56850-121">This element defines the basic settings for a custom peer resolver service, including the endpoint address of the peer hosting the service and any specific binding settings.</span></span> <span data-ttu-id="56850-122">カスタム競合回避モジュールの作成の詳細については、「 [PeerChannel アプリケーションへのカスタム競合回避モジュールの追加](/previous-versions/ms730105(v=vs.90))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56850-122">For more information on creating a custom resolver, see [Adding a Custom Resolver to a PeerChannel Application](/previous-versions/ms730105(v=vs.90)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56850-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="56850-123">See also</span></span>

- <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>
- <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>
- <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>
- <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>
- [<span data-ttu-id="56850-124">ピア リゾルバー</span><span class="sxs-lookup"><span data-stu-id="56850-124">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
- <span data-ttu-id="56850-125">[PeerChannel アプリケーションへのカスタム リゾルバーの追加](/previous-versions/ms730105(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="56850-125">[Adding a Custom Resolver to a PeerChannel Application](/previous-versions/ms730105(v=vs.90))</span></span>
