---
title: <oneWay>
ms.date: 03/30/2017
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
ms.openlocfilehash: a5c773ea91de882920775ac8dc0ecc1da68a6c9f
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738792"
---
# <a name="oneway"></a><span data-ttu-id="e9926-101">\<oneWay ></span><span class="sxs-lookup"><span data-stu-id="e9926-101">\<oneWay></span></span>
<span data-ttu-id="e9926-102">カスタム バインドのパケット ルーティングを有効にし、一方向メソッドを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e9926-102">Enables packet routing and the use of one-way methods for a custom binding.</span></span>  
  
<span data-ttu-id="e9926-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e9926-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e9926-104">&nbsp; &nbsp;[ **\<system >** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="e9926-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e9926-105">&nbsp;&nbsp;&nbsp;&nbsp;\<[**バインド**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="e9926-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="e9926-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="e9926-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="e9926-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**バインド >** </span><span class="sxs-lookup"><span data-stu-id="e9926-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="e9926-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**oneWay >**</span><span class="sxs-lookup"><span data-stu-id="e9926-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oneWay>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9926-109">構文</span><span class="sxs-lookup"><span data-stu-id="e9926-109">Syntax</span></span>  
  
```xml  
<oneWay packetRoutable="Boolean">
  <channelPoolSettings idleTimeout="TimeSpan"
                       leaseTimeout="TimeSpan"
                       maxOutboundConnectionsPerEndpoint="Integer" />
</oneWay>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9926-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e9926-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e9926-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e9926-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9926-112">属性</span><span class="sxs-lookup"><span data-stu-id="e9926-112">Attributes</span></span>  
  
|<span data-ttu-id="e9926-113">属性</span><span class="sxs-lookup"><span data-stu-id="e9926-113">Attribute</span></span>|<span data-ttu-id="e9926-114">説明</span><span class="sxs-lookup"><span data-stu-id="e9926-114">Description</span></span>|  
|---------------|-----------------|  
|`packetRoutable`|<span data-ttu-id="e9926-115">パケット ルーティングが有効かどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="e9926-115">A Boolean value that specifies whether packet routing is enabled.</span></span> <span data-ttu-id="e9926-116">既定値は、 `false`です。</span><span class="sxs-lookup"><span data-stu-id="e9926-116">The default is `false`.</span></span>|  
|`MaxAcceptedChannels`|<span data-ttu-id="e9926-117">許容できるチャネルの最大数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="e9926-117">An integer that specifies the maximum number of channels that can be accepted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e9926-118">子要素</span><span class="sxs-lookup"><span data-stu-id="e9926-118">Child Elements</span></span>  
  
|<span data-ttu-id="e9926-119">要素</span><span class="sxs-lookup"><span data-stu-id="e9926-119">Element</span></span>|<span data-ttu-id="e9926-120">説明</span><span class="sxs-lookup"><span data-stu-id="e9926-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e9926-121">\<channelPoolSettings ></span><span class="sxs-lookup"><span data-stu-id="e9926-121">\<channelPoolSettings></span></span>](channelpoolsettings.md)|<span data-ttu-id="e9926-122">現在のチャネルのチャネル プールのプロパティを格納する <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="e9926-122">A <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> object that contains properties of the channel pool for the current channel.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e9926-123">親要素</span><span class="sxs-lookup"><span data-stu-id="e9926-123">Parent Elements</span></span>  
  
|<span data-ttu-id="e9926-124">要素</span><span class="sxs-lookup"><span data-stu-id="e9926-124">Element</span></span>|<span data-ttu-id="e9926-125">説明</span><span class="sxs-lookup"><span data-stu-id="e9926-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e9926-126">\<binding ></span><span class="sxs-lookup"><span data-stu-id="e9926-126">\<binding></span></span>](bindings.md)|<span data-ttu-id="e9926-127">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="e9926-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9926-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="e9926-128">Remarks</span></span>  
 <span data-ttu-id="e9926-129">パケット ルーティングを有効にするには、この要素が提供する "一方向の変換" 層が必要です。</span><span class="sxs-lookup"><span data-stu-id="e9926-129">To enable packet routing, a one-way conversion layer is required, which this element provides.</span></span> <span data-ttu-id="e9926-130">カスタム バインドを作成し、このバインディングをセッション対応または要求応答のトランスポートの上に重ねて、パケット ルーティング可能にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e9926-130">A user can create a custom binding that layers this binding over a session-aware or request-reply transport to make it packet routable.</span></span> <span data-ttu-id="e9926-131">この要素は、一方向メソッドをよりネイティブな形式で公開するときにも役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="e9926-131">This element is also useful when you want to expose one-way methods in a more native fashion.</span></span> <span data-ttu-id="e9926-132">複合二重や信頼できるメッセージ機能などのさらに大きい変換は、この層に対して適用できます。</span><span class="sxs-lookup"><span data-stu-id="e9926-132">More transformations can be applied over this layer, such as Composite Duplex and Reliable Messaging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9926-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="e9926-133">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement>
- <xref:System.ServiceModel.Configuration.OneWayElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="e9926-134">バインディング</span><span class="sxs-lookup"><span data-stu-id="e9926-134">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e9926-135">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="e9926-135">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="e9926-136">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="e9926-136">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="e9926-137">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="e9926-137">\<customBinding></span></span>](custombinding.md)
