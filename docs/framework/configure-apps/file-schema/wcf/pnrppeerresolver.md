---
title: <pnrpPeerResolver>
ms.date: 03/30/2017
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
ms.openlocfilehash: d3e88d7f2dd991091d3d7abdc715e125ddc9ac56
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738777"
---
# <a name="pnrppeerresolver"></a><span data-ttu-id="e8d08-101">\<の ></span><span class="sxs-lookup"><span data-stu-id="e8d08-101">\<pnrpPeerResolver></span></span>
<span data-ttu-id="e8d08-102">リゾルバーとして PNRP (Peer Name Resolution Protocol) リゾルバーを使用することを指定します。</span><span class="sxs-lookup"><span data-stu-id="e8d08-102">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="e8d08-103">PNRP は既定のリゾルバーであるため、この要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e8d08-103">This element is optional because PNRP is the default resolver.</span></span>  
  
<span data-ttu-id="e8d08-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e8d08-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e8d08-105">&nbsp; &nbsp;[ **\<system >** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="e8d08-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e8d08-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**バインド**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="e8d08-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="e8d08-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="e8d08-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="e8d08-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**バインド >** </span><span class="sxs-lookup"><span data-stu-id="e8d08-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="e8d08-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**pnrpResolver >**</span><span class="sxs-lookup"><span data-stu-id="e8d08-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<pnrpResolver>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8d08-110">構文</span><span class="sxs-lookup"><span data-stu-id="e8d08-110">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e8d08-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e8d08-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e8d08-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e8d08-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e8d08-113">属性</span><span class="sxs-lookup"><span data-stu-id="e8d08-113">Attributes</span></span>  
  
|<span data-ttu-id="e8d08-114">属性</span><span class="sxs-lookup"><span data-stu-id="e8d08-114">Attribute</span></span>|<span data-ttu-id="e8d08-115">説明</span><span class="sxs-lookup"><span data-stu-id="e8d08-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e8d08-116">resolverType</span><span class="sxs-lookup"><span data-stu-id="e8d08-116">resolverType</span></span>|<span data-ttu-id="e8d08-117">使用されるリゾルバーを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="e8d08-117">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="e8d08-118">この属性は省略できます。</span><span class="sxs-lookup"><span data-stu-id="e8d08-118">This attribute is optional.</span></span> <span data-ttu-id="e8d08-119">設定されていない場合、または空の文字列に設定されている場合は、PNRP が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e8d08-119">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e8d08-120">子要素</span><span class="sxs-lookup"><span data-stu-id="e8d08-120">Child Elements</span></span>  
 <span data-ttu-id="e8d08-121">None</span><span class="sxs-lookup"><span data-stu-id="e8d08-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e8d08-122">親要素</span><span class="sxs-lookup"><span data-stu-id="e8d08-122">Parent Elements</span></span>  
  
|<span data-ttu-id="e8d08-123">要素</span><span class="sxs-lookup"><span data-stu-id="e8d08-123">Element</span></span>|<span data-ttu-id="e8d08-124">説明</span><span class="sxs-lookup"><span data-stu-id="e8d08-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e8d08-125">\<binding ></span><span class="sxs-lookup"><span data-stu-id="e8d08-125">\<binding></span></span>](bindings.md)|<span data-ttu-id="e8d08-126">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="e8d08-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e8d08-127">例</span><span class="sxs-lookup"><span data-stu-id="e8d08-127">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="see-also"></a><span data-ttu-id="e8d08-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="e8d08-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>
- <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="e8d08-129">バインディング</span><span class="sxs-lookup"><span data-stu-id="e8d08-129">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e8d08-130">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="e8d08-130">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="e8d08-131">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="e8d08-131">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="e8d08-132">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="e8d08-132">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="e8d08-133">ピア リゾルバー</span><span class="sxs-lookup"><span data-stu-id="e8d08-133">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
