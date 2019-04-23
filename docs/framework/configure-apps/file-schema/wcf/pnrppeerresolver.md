---
title: <pnrpPeerResolver>
ms.date: 03/30/2017
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
ms.openlocfilehash: 2404f00b2a3ba03e89c1e21fb25e13cabb8feed3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59214054"
---
# <a name="pnrppeerresolver"></a><span data-ttu-id="35a0c-101">\<pnrpPeerResolver></span><span class="sxs-lookup"><span data-stu-id="35a0c-101">\<pnrpPeerResolver></span></span>
<span data-ttu-id="35a0c-102">リゾルバーとして PNRP (Peer Name Resolution Protocol) リゾルバーを使用することを指定します。</span><span class="sxs-lookup"><span data-stu-id="35a0c-102">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="35a0c-103">PNRP は既定のリゾルバーであるため、この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="35a0c-103">This element is optional because PNRP is the default resolver.</span></span>  
  
 <span data-ttu-id="35a0c-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="35a0c-104">\<system.serviceModel></span></span>  
<span data-ttu-id="35a0c-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="35a0c-105">\<bindings></span></span>  
<span data-ttu-id="35a0c-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="35a0c-106">\<customBinding></span></span>  
<span data-ttu-id="35a0c-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="35a0c-107">\<binding></span></span>  
<span data-ttu-id="35a0c-108">\<pnrpResolver ></span><span class="sxs-lookup"><span data-stu-id="35a0c-108">\<pnrpResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35a0c-109">構文</span><span class="sxs-lookup"><span data-stu-id="35a0c-109">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="35a0c-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="35a0c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="35a0c-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="35a0c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="35a0c-112">属性</span><span class="sxs-lookup"><span data-stu-id="35a0c-112">Attributes</span></span>  
  
|<span data-ttu-id="35a0c-113">属性</span><span class="sxs-lookup"><span data-stu-id="35a0c-113">Attribute</span></span>|<span data-ttu-id="35a0c-114">説明</span><span class="sxs-lookup"><span data-stu-id="35a0c-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="35a0c-115">resolverType</span><span class="sxs-lookup"><span data-stu-id="35a0c-115">resolverType</span></span>|<span data-ttu-id="35a0c-116">使用されるリゾルバーを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="35a0c-116">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="35a0c-117">この属性は省略できます。</span><span class="sxs-lookup"><span data-stu-id="35a0c-117">This attribute is optional.</span></span> <span data-ttu-id="35a0c-118">設定されていない場合、または空の文字列に設定されている場合は、PNRP が使用されます。</span><span class="sxs-lookup"><span data-stu-id="35a0c-118">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="35a0c-119">子要素</span><span class="sxs-lookup"><span data-stu-id="35a0c-119">Child Elements</span></span>  
 <span data-ttu-id="35a0c-120">なし</span><span class="sxs-lookup"><span data-stu-id="35a0c-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="35a0c-121">親要素</span><span class="sxs-lookup"><span data-stu-id="35a0c-121">Parent Elements</span></span>  
  
|<span data-ttu-id="35a0c-122">要素</span><span class="sxs-lookup"><span data-stu-id="35a0c-122">Element</span></span>|<span data-ttu-id="35a0c-123">説明</span><span class="sxs-lookup"><span data-stu-id="35a0c-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="35a0c-124">\<binding></span><span class="sxs-lookup"><span data-stu-id="35a0c-124">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="35a0c-125">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="35a0c-125">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="35a0c-126">例</span><span class="sxs-lookup"><span data-stu-id="35a0c-126">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="see-also"></a><span data-ttu-id="35a0c-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="35a0c-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>
- <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="35a0c-128">バインディング</span><span class="sxs-lookup"><span data-stu-id="35a0c-128">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="35a0c-129">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="35a0c-129">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="35a0c-130">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="35a0c-130">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="35a0c-131">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="35a0c-131">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="35a0c-132">ピア リゾルバー</span><span class="sxs-lookup"><span data-stu-id="35a0c-132">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)
