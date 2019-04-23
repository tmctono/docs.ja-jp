---
title: <oneWay>
ms.date: 03/30/2017
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
ms.openlocfilehash: bfda2b9d7b3aa5219a3e4c344347d3b10419a7bd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59102415"
---
# <a name="oneway"></a><span data-ttu-id="b5b90-101">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="b5b90-101">\<oneWay></span></span>
<span data-ttu-id="b5b90-102">カスタム バインドのパケット ルーティングを有効にし、一方向メソッドを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="b5b90-102">Enables packet routing and the use of one-way methods for a custom binding.</span></span>  
  
 <span data-ttu-id="b5b90-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b5b90-103">\<system.serviceModel></span></span>  
<span data-ttu-id="b5b90-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="b5b90-104">\<bindings></span></span>  
<span data-ttu-id="b5b90-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="b5b90-105">\<customBinding></span></span>  
<span data-ttu-id="b5b90-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="b5b90-106">\<binding></span></span>  
<span data-ttu-id="b5b90-107">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="b5b90-107">\<oneWay></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5b90-108">構文</span><span class="sxs-lookup"><span data-stu-id="b5b90-108">Syntax</span></span>  
  
```xml  
<oneWay packetRoutable="Boolean">
  <channelPoolSettings idleTimeout="TimeSpan"
                       leaseTimeout="TimeSpan"
                       maxOutboundConnectionsPerEndpopint="Integer" />
</oneWay>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b5b90-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b5b90-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b5b90-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b5b90-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b5b90-111">属性</span><span class="sxs-lookup"><span data-stu-id="b5b90-111">Attributes</span></span>  
  
|<span data-ttu-id="b5b90-112">属性</span><span class="sxs-lookup"><span data-stu-id="b5b90-112">Attribute</span></span>|<span data-ttu-id="b5b90-113">説明</span><span class="sxs-lookup"><span data-stu-id="b5b90-113">Description</span></span>|  
|---------------|-----------------|  
|`packetRoutable`|<span data-ttu-id="b5b90-114">パケット ルーティングが有効かどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="b5b90-114">A Boolean value that specifies whether packet routing is enabled.</span></span> <span data-ttu-id="b5b90-115">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="b5b90-115">The default is `false`.</span></span>|  
|`MaxAcceptedChannels`|<span data-ttu-id="b5b90-116">許容できるチャネルの最大数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="b5b90-116">An integer that specifies the maximum number of channels that can be accepted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b5b90-117">子要素</span><span class="sxs-lookup"><span data-stu-id="b5b90-117">Child Elements</span></span>  
  
|<span data-ttu-id="b5b90-118">要素</span><span class="sxs-lookup"><span data-stu-id="b5b90-118">Element</span></span>|<span data-ttu-id="b5b90-119">説明</span><span class="sxs-lookup"><span data-stu-id="b5b90-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b5b90-120">\<channelPoolSettings></span><span class="sxs-lookup"><span data-stu-id="b5b90-120">\<channelPoolSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/channelpoolsettings.md)|<span data-ttu-id="b5b90-121">現在のチャネルのチャネル プールのプロパティを格納する <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="b5b90-121">A <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> object that contains properties of the channel pool for the current channel.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b5b90-122">親要素</span><span class="sxs-lookup"><span data-stu-id="b5b90-122">Parent Elements</span></span>  
  
|<span data-ttu-id="b5b90-123">要素</span><span class="sxs-lookup"><span data-stu-id="b5b90-123">Element</span></span>|<span data-ttu-id="b5b90-124">説明</span><span class="sxs-lookup"><span data-stu-id="b5b90-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b5b90-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="b5b90-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="b5b90-126">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="b5b90-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b5b90-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="b5b90-127">Remarks</span></span>  
 <span data-ttu-id="b5b90-128">パケット ルーティングを有効にするには、この要素が提供する "一方向の変換" 層が必要です。</span><span class="sxs-lookup"><span data-stu-id="b5b90-128">To enable packet routing, a one-way conversion layer is required, which this element provides.</span></span> <span data-ttu-id="b5b90-129">カスタム バインドを作成し、このバインディングをセッション対応または要求応答のトランスポートの上に重ねて、パケット ルーティング可能にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b5b90-129">A user can create a custom binding that layers this binding over a session-aware or request-reply transport to make it packet routable.</span></span> <span data-ttu-id="b5b90-130">この要素は、一方向メソッドをよりネイティブな形式で公開するときにも役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="b5b90-130">This element is also useful when you want to expose one-way methods in a more native fashion.</span></span> <span data-ttu-id="b5b90-131">複合二重や信頼できるメッセージ機能などのさらに大きい変換は、この層に対して適用できます。</span><span class="sxs-lookup"><span data-stu-id="b5b90-131">More transformations can be applied over this layer, such as Composite Duplex and Reliable Messaging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5b90-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="b5b90-132">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement>
- <xref:System.ServiceModel.Configuration.OneWayElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="b5b90-133">バインディング</span><span class="sxs-lookup"><span data-stu-id="b5b90-133">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="b5b90-134">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="b5b90-134">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="b5b90-135">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="b5b90-135">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="b5b90-136">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="b5b90-136">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
