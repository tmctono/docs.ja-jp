---
title: <oneWay>
ms.date: 03/30/2017
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
ms.openlocfilehash: 92cd6b280305c223ee125a45724691c5205ce3c1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195013"
---
# \<oneWay>

<span data-ttu-id="c5b47-101">カスタム バインドのパケット ルーティングを有効にし、一方向メソッドを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="c5b47-101">Enables packet routing and the use of one-way methods for a custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oneWay>**  
  
## <a name="syntax"></a><span data-ttu-id="c5b47-102">構文</span><span class="sxs-lookup"><span data-stu-id="c5b47-102">Syntax</span></span>  
  
```xml  
<oneWay packetRoutable="Boolean">
  <channelPoolSettings idleTimeout="TimeSpan"
                       leaseTimeout="TimeSpan"
                       maxOutboundConnectionsPerEndpoint="Integer" />
</oneWay>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c5b47-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c5b47-103">Attributes and Elements</span></span>  

 <span data-ttu-id="c5b47-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c5b47-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c5b47-105">属性</span><span class="sxs-lookup"><span data-stu-id="c5b47-105">Attributes</span></span>  
  
|<span data-ttu-id="c5b47-106">属性</span><span class="sxs-lookup"><span data-stu-id="c5b47-106">Attribute</span></span>|<span data-ttu-id="c5b47-107">[説明]</span><span class="sxs-lookup"><span data-stu-id="c5b47-107">Description</span></span>|  
|---------------|-----------------|  
|`packetRoutable`|<span data-ttu-id="c5b47-108">パケット ルーティングが有効かどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="c5b47-108">A Boolean value that specifies whether packet routing is enabled.</span></span> <span data-ttu-id="c5b47-109">既定では、 `false`です。</span><span class="sxs-lookup"><span data-stu-id="c5b47-109">The default is `false`.</span></span>|  
|`MaxAcceptedChannels`|<span data-ttu-id="c5b47-110">許容できるチャネルの最大数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="c5b47-110">An integer that specifies the maximum number of channels that can be accepted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c5b47-111">子要素</span><span class="sxs-lookup"><span data-stu-id="c5b47-111">Child Elements</span></span>  
  
|<span data-ttu-id="c5b47-112">要素</span><span class="sxs-lookup"><span data-stu-id="c5b47-112">Element</span></span>|<span data-ttu-id="c5b47-113">説明</span><span class="sxs-lookup"><span data-stu-id="c5b47-113">Description</span></span>|  
|-------------|-----------------|  
|[\<channelPoolSettings>](channelpoolsettings.md)|<span data-ttu-id="c5b47-114">現在のチャネルのチャネル プールのプロパティを格納する <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c5b47-114">A <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> object that contains properties of the channel pool for the current channel.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c5b47-115">親要素</span><span class="sxs-lookup"><span data-stu-id="c5b47-115">Parent Elements</span></span>  
  
|<span data-ttu-id="c5b47-116">要素</span><span class="sxs-lookup"><span data-stu-id="c5b47-116">Element</span></span>|<span data-ttu-id="c5b47-117">説明</span><span class="sxs-lookup"><span data-stu-id="c5b47-117">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="c5b47-118">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="c5b47-118">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5b47-119">解説</span><span class="sxs-lookup"><span data-stu-id="c5b47-119">Remarks</span></span>  

 <span data-ttu-id="c5b47-120">パケット ルーティングを有効にするには、この要素が提供する "一方向の変換" 層が必要です。</span><span class="sxs-lookup"><span data-stu-id="c5b47-120">To enable packet routing, a one-way conversion layer is required, which this element provides.</span></span> <span data-ttu-id="c5b47-121">カスタム バインドを作成し、このバインディングをセッション対応または要求応答のトランスポートの上に重ねて、パケット ルーティング可能にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c5b47-121">A user can create a custom binding that layers this binding over a session-aware or request-reply transport to make it packet routable.</span></span> <span data-ttu-id="c5b47-122">この要素は、一方向メソッドをよりネイティブな形式で公開するときにも役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="c5b47-122">This element is also useful when you want to expose one-way methods in a more native fashion.</span></span> <span data-ttu-id="c5b47-123">複合二重や信頼できるメッセージ機能などのさらに大きい変換は、この層に対して適用できます。</span><span class="sxs-lookup"><span data-stu-id="c5b47-123">More transformations can be applied over this layer, such as Composite Duplex and Reliable Messaging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5b47-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="c5b47-124">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement>
- <xref:System.ServiceModel.Configuration.OneWayElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="c5b47-125">バインド</span><span class="sxs-lookup"><span data-stu-id="c5b47-125">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c5b47-126">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="c5b47-126">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="c5b47-127">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="c5b47-127">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
