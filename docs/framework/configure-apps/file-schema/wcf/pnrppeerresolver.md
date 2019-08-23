---
title: <pnrpPeerResolver>
ms.date: 03/30/2017
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
ms.openlocfilehash: e7e82117304ac133e5e84c0fc36b987560bcef96
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933810"
---
# <a name="pnrppeerresolver"></a><span data-ttu-id="2823b-101">\<> のための Pnrpq Peerresolver</span><span class="sxs-lookup"><span data-stu-id="2823b-101">\<pnrpPeerResolver></span></span>
<span data-ttu-id="2823b-102">リゾルバーとして PNRP (Peer Name Resolution Protocol) リゾルバーを使用することを指定します。</span><span class="sxs-lookup"><span data-stu-id="2823b-102">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="2823b-103">PNRP は既定のリゾルバーであるため、この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="2823b-103">This element is optional because PNRP is the default resolver.</span></span>  
  
 <span data-ttu-id="2823b-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2823b-104">\<system.serviceModel></span></span>  
<span data-ttu-id="2823b-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="2823b-105">\<bindings></span></span>  
<span data-ttu-id="2823b-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="2823b-106">\<customBinding></span></span>  
<span data-ttu-id="2823b-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="2823b-107">\<binding></span></span>  
<span data-ttu-id="2823b-108">\<pnrpResolver ></span><span class="sxs-lookup"><span data-stu-id="2823b-108">\<pnrpResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2823b-109">構文</span><span class="sxs-lookup"><span data-stu-id="2823b-109">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2823b-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="2823b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2823b-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2823b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2823b-112">属性</span><span class="sxs-lookup"><span data-stu-id="2823b-112">Attributes</span></span>  
  
|<span data-ttu-id="2823b-113">属性</span><span class="sxs-lookup"><span data-stu-id="2823b-113">Attribute</span></span>|<span data-ttu-id="2823b-114">説明</span><span class="sxs-lookup"><span data-stu-id="2823b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2823b-115">resolverType</span><span class="sxs-lookup"><span data-stu-id="2823b-115">resolverType</span></span>|<span data-ttu-id="2823b-116">使用されるリゾルバーを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="2823b-116">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="2823b-117">この属性は省略できます。</span><span class="sxs-lookup"><span data-stu-id="2823b-117">This attribute is optional.</span></span> <span data-ttu-id="2823b-118">設定されていない場合、または空の文字列に設定されている場合は、PNRP が使用されます。</span><span class="sxs-lookup"><span data-stu-id="2823b-118">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2823b-119">子要素</span><span class="sxs-lookup"><span data-stu-id="2823b-119">Child Elements</span></span>  
 <span data-ttu-id="2823b-120">なし</span><span class="sxs-lookup"><span data-stu-id="2823b-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2823b-121">親要素</span><span class="sxs-lookup"><span data-stu-id="2823b-121">Parent Elements</span></span>  
  
|<span data-ttu-id="2823b-122">要素</span><span class="sxs-lookup"><span data-stu-id="2823b-122">Element</span></span>|<span data-ttu-id="2823b-123">説明</span><span class="sxs-lookup"><span data-stu-id="2823b-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2823b-124">\<binding></span><span class="sxs-lookup"><span data-stu-id="2823b-124">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="2823b-125">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="2823b-125">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2823b-126">例</span><span class="sxs-lookup"><span data-stu-id="2823b-126">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="see-also"></a><span data-ttu-id="2823b-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="2823b-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>
- <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="2823b-128">バインディング</span><span class="sxs-lookup"><span data-stu-id="2823b-128">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="2823b-129">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="2823b-129">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="2823b-130">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="2823b-130">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="2823b-131">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="2823b-131">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="2823b-132">ピア リゾルバー</span><span class="sxs-lookup"><span data-stu-id="2823b-132">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
