---
title: <channelSettings>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 94a4457f-f43f-458d-a47e-2d11103ee75e
ms.openlocfilehash: f6a57e2cc1e7c5e114fd38ee3534ab7c4e629b36
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152275"
---
# \<channelSettings>
<span data-ttu-id="45f91-101">チャネル キャッシュの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="45f91-101">Specifies the settings of the channel cache.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<sendMessageChannelCache>**](sendmessagechannelcache.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<channelSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="45f91-102">構文</span><span class="sxs-lookup"><span data-stu-id="45f91-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <sendMessageChannelCache allowUnsafeCaching="Boolean">
        <channelSettings idleTimeout="TimeSpan"
                         leaseTimeout="TimeSpan"
                         maxItemsInCache="Integer" />
      </sendMessageChannelCache>
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="45f91-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="45f91-103">Attributes and Elements</span></span>  
 <span data-ttu-id="45f91-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="45f91-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="45f91-105">属性</span><span class="sxs-lookup"><span data-stu-id="45f91-105">Attributes</span></span>  
  
|<span data-ttu-id="45f91-106">属性</span><span class="sxs-lookup"><span data-stu-id="45f91-106">Attribute</span></span>|<span data-ttu-id="45f91-107">説明</span><span class="sxs-lookup"><span data-stu-id="45f91-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="45f91-108">idleTimeout</span><span class="sxs-lookup"><span data-stu-id="45f91-108">idleTimeout</span></span>|<span data-ttu-id="45f91-109">オブジェクトが破棄されるまでにキャッシュ内でアイドル状態を維持できる最大時間を指定する TimeSpan 値。</span><span class="sxs-lookup"><span data-stu-id="45f91-109">A TimeSpan value that specifies the maximum interval of time for which the object can remain idle in the cache before being disposed.</span></span>|  
|<span data-ttu-id="45f91-110">leaseTimeout</span><span class="sxs-lookup"><span data-stu-id="45f91-110">leaseTimeout</span></span>|<span data-ttu-id="45f91-111">オブジェクトがキャッシュから削除されるまでの時間間隔を指定する TimeSpan 値。</span><span class="sxs-lookup"><span data-stu-id="45f91-111">A TimeSpan value that specifies  the interval of time after which an object is removed from the cache.</span></span>|  
|<span data-ttu-id="45f91-112">maxItemsInCache</span><span class="sxs-lookup"><span data-stu-id="45f91-112">maxItemsInCache</span></span>|<span data-ttu-id="45f91-113">キャッシュに置くことができるオブジェクトの最大数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="45f91-113">An integer that specifies the maximum number of objects that can be in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="45f91-114">子要素</span><span class="sxs-lookup"><span data-stu-id="45f91-114">Child Elements</span></span>  
 <span data-ttu-id="45f91-115">なし。</span><span class="sxs-lookup"><span data-stu-id="45f91-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="45f91-116">親要素</span><span class="sxs-lookup"><span data-stu-id="45f91-116">Parent Elements</span></span>  
  
|<span data-ttu-id="45f91-117">要素</span><span class="sxs-lookup"><span data-stu-id="45f91-117">Element</span></span>|<span data-ttu-id="45f91-118">Description</span><span class="sxs-lookup"><span data-stu-id="45f91-118">Description</span></span>|  
|-------------|-----------------|  
|[\<sendMessageChannelCache>](sendmessagechannelcache.md)|<span data-ttu-id="45f91-119">キャッシュの共有レベルのカスタマイズや、チャネル ファクトリ キャッシュの設定を可能にするほか、Send メッセージング アクティビティを使用してサービス エンドポイントにメッセージを送信するワークフローのチャネル キャッシュの設定も可能にするサービス動作。</span><span class="sxs-lookup"><span data-stu-id="45f91-119">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45f91-120">解説</span><span class="sxs-lookup"><span data-stu-id="45f91-120">Remarks</span></span>  
 <span data-ttu-id="45f91-121">このサービス動作は、サービス エンドポイントにメッセージを送信するワークフローを対象としています。</span><span class="sxs-lookup"><span data-stu-id="45f91-121">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="45f91-122">これらのワークフローは、通常はクライアント ワークフローですが、<xref:System.ServiceModel.WorkflowServiceHost> でホストされるワークフロー サービスである場合もあります。</span><span class="sxs-lookup"><span data-stu-id="45f91-122">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="45f91-123">既定では、<xref:System.ServiceModel.WorkflowServiceHost> によってホストされるワークフローでは、<xref:System.ServiceModel.Activities.Send> メッセージング アクティビティが使用するキャッシュは <xref:System.ServiceModel.WorkflowServiceHost> のすべてのワークフロー インスタンス間で共有されます (ホストレベルのキャッシュ)。</span><span class="sxs-lookup"><span data-stu-id="45f91-123">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="45f91-124"><xref:System.ServiceModel.WorkflowServiceHost> によってホストされないクライアント ワークフローの場合、キャッシュを使用できるのはワークフロー インスタンスだけです (インスタンスレベルのキャッシュ)。</span><span class="sxs-lookup"><span data-stu-id="45f91-124">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="45f91-125">構成でエンドポイントが定義されているワークフローに送信アクティビティがある場合、キャッシュは既定で無効になります。</span><span class="sxs-lookup"><span data-stu-id="45f91-125">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 <span data-ttu-id="45f91-126">チャネルファクトリおよびチャネルキャッシュの既定のキャッシュ共有レベルとキャッシュ設定を変更する方法の詳細については、「 [Send アクティビティのキャッシュ共有レベルの変更](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45f91-126">For more information about how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="45f91-127">例</span><span class="sxs-lookup"><span data-stu-id="45f91-127">Example</span></span>  
 <span data-ttu-id="45f91-128">ホストされたワークフロー サービスでは、ファクトリ キャッシュとチャネル キャッシュの設定をアプリケーション構成ファイルで指定できます。</span><span class="sxs-lookup"><span data-stu-id="45f91-128">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="45f91-129">これを行うには、ファクトリ キャッシュおよびチャネル キャッシュのキャッシュ設定を含むサービス動作を追加し、そのサービス動作をサービスに追加します。</span><span class="sxs-lookup"><span data-stu-id="45f91-129">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="45f91-130">次の例は、 `MyChannelCacheBehavior` カスタムファクトリキャッシュとチャネルキャッシュ設定を使用したサービス動作を含む構成ファイルの内容を示しています。</span><span class="sxs-lookup"><span data-stu-id="45f91-130">The following example shows the contents of a configuration file that contains the `MyChannelCacheBehavior`  service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="45f91-131">このサービス動作は、属性を通じてサービスに追加され `behaviorConfiguration` ます。</span><span class="sxs-lookup"><span data-stu-id="45f91-131">This service behavior is added to the service through the `behaviorConfiguration` attribute.</span></span>  
  
```xml  
<configuration>
  <system.serviceModel>  
    <!-- List of other config sections here -->
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="MyChannelCacheBehavior">  
          <sendMessageChannelCache allowUnsafeCaching ="false" >  
            <!-- Control only the host level settings -->
            <factorySettings maxItemsInCache = "8" idleTimeout = "00:05:00" leaseTimeout="10:00:00" />  
            <channelSettings maxItemsInCache = "32" idleTimeout = "00:05:00" leaseTimeout="00:06:00" />  
          </sendMessageChannelCache>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service name="MyService" behaviorConfiguration="MyChannelCacheBehavior" />  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="45f91-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="45f91-132">See also</span></span>

- <xref:System.ServiceModel.Activities.SendMessageChannelCache>
- <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>
- <xref:System.ServiceModel.Activities.Send>
- <xref:System.ServiceModel.Activities.ChannelCacheSettings>
- [<span data-ttu-id="45f91-133">Send アクティビティのキャッシュ共有レベルの変更</span><span class="sxs-lookup"><span data-stu-id="45f91-133">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)
