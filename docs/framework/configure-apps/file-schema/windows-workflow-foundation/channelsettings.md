---
title: <channelSettings>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 94a4457f-f43f-458d-a47e-2d11103ee75e
ms.openlocfilehash: 9caf87bdf2029d273a9d6d7ac90b83ba72bafc7a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945831"
---
# <a name="channelsettings"></a><span data-ttu-id="fe2fe-101">\<channelSettings ></span><span class="sxs-lookup"><span data-stu-id="fe2fe-101">\<channelSettings></span></span>
<span data-ttu-id="fe2fe-102">チャネル キャッシュの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="fe2fe-102">Specifies the settings of the channel cache.</span></span>  
  
<span data-ttu-id="fe2fe-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="fe2fe-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="fe2fe-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="fe2fe-104">\<behaviors></span></span>  
<span data-ttu-id="fe2fe-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="fe2fe-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="fe2fe-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="fe2fe-106">\<behavior></span></span>  
<span data-ttu-id="fe2fe-107">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="fe2fe-107">\<sendMessageChannelCache></span></span>  
<span data-ttu-id="fe2fe-108">\<channelSettings ></span><span class="sxs-lookup"><span data-stu-id="fe2fe-108">\<channelSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe2fe-109">構文</span><span class="sxs-lookup"><span data-stu-id="fe2fe-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fe2fe-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="fe2fe-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fe2fe-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="fe2fe-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fe2fe-112">属性</span><span class="sxs-lookup"><span data-stu-id="fe2fe-112">Attributes</span></span>  
  
|<span data-ttu-id="fe2fe-113">属性</span><span class="sxs-lookup"><span data-stu-id="fe2fe-113">Attribute</span></span>|<span data-ttu-id="fe2fe-114">説明</span><span class="sxs-lookup"><span data-stu-id="fe2fe-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fe2fe-115">idleTimeout</span><span class="sxs-lookup"><span data-stu-id="fe2fe-115">idleTimeout</span></span>|<span data-ttu-id="fe2fe-116">オブジェクトが破棄されるまでにキャッシュ内でアイドル状態を維持できる最大時間を指定する TimeSpan 値。</span><span class="sxs-lookup"><span data-stu-id="fe2fe-116">A TimeSpan value that specifies the maximum interval of time for which the object can remain idle in the cache before being disposed.</span></span>|  
|<span data-ttu-id="fe2fe-117">leaseTimeout</span><span class="sxs-lookup"><span data-stu-id="fe2fe-117">leaseTimeout</span></span>|<span data-ttu-id="fe2fe-118">オブジェクトがキャッシュから削除されるまでの時間間隔を指定する TimeSpan 値です。</span><span class="sxs-lookup"><span data-stu-id="fe2fe-118">A TimeSpan value that specifies  the interval of time after which an object is removed from the cache.</span></span>|  
|<span data-ttu-id="fe2fe-119">maxItemsInCache</span><span class="sxs-lookup"><span data-stu-id="fe2fe-119">maxItemsInCache</span></span>|<span data-ttu-id="fe2fe-120">キャッシュに置くことができるオブジェクトの最大数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="fe2fe-120">An integer that specifies the maximum number of objects that can be in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fe2fe-121">子要素</span><span class="sxs-lookup"><span data-stu-id="fe2fe-121">Child Elements</span></span>  
 <span data-ttu-id="fe2fe-122">なし。</span><span class="sxs-lookup"><span data-stu-id="fe2fe-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fe2fe-123">親要素</span><span class="sxs-lookup"><span data-stu-id="fe2fe-123">Parent Elements</span></span>  
  
|<span data-ttu-id="fe2fe-124">要素</span><span class="sxs-lookup"><span data-stu-id="fe2fe-124">Element</span></span>|<span data-ttu-id="fe2fe-125">説明</span><span class="sxs-lookup"><span data-stu-id="fe2fe-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fe2fe-126">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="fe2fe-126">\<sendMessageChannelCache></span></span>](sendmessagechannelcache.md)|<span data-ttu-id="fe2fe-127">キャッシュ共有レベルのカスタマイズ、チャネルファクトリキャッシュの設定、およびメッセージを送信するアクティビティを使用してサービスエンドポイントにメッセージを送信するワークフローのチャネルキャッシュの設定を可能にするサービス動作。</span><span class="sxs-lookup"><span data-stu-id="fe2fe-127">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe2fe-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="fe2fe-128">Remarks</span></span>  
 <span data-ttu-id="fe2fe-129">このサービス動作は、サービス エンドポイントにメッセージを送信するワークフローを対象としています。</span><span class="sxs-lookup"><span data-stu-id="fe2fe-129">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="fe2fe-130">これらのワークフローは、通常はクライアント ワークフローですが、<xref:System.ServiceModel.WorkflowServiceHost> でホストされるワークフロー サービスである場合もあります。</span><span class="sxs-lookup"><span data-stu-id="fe2fe-130">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="fe2fe-131">既定では、<xref:System.ServiceModel.WorkflowServiceHost> によってホストされるワークフローでは、<xref:System.ServiceModel.Activities.Send> メッセージング アクティビティが使用するキャッシュは <xref:System.ServiceModel.WorkflowServiceHost> のすべてのワークフロー インスタンス間で共有されます (ホストレベルのキャッシュ)。</span><span class="sxs-lookup"><span data-stu-id="fe2fe-131">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="fe2fe-132"><xref:System.ServiceModel.WorkflowServiceHost> によってホストされないクライアント ワークフローの場合、キャッシュを使用できるのはワークフロー インスタンスだけです (インスタンスレベルのキャッシュ)。</span><span class="sxs-lookup"><span data-stu-id="fe2fe-132">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="fe2fe-133">構成でエンドポイントが定義されているワークフローに送信アクティビティがある場合、キャッシュは既定で無効になります。</span><span class="sxs-lookup"><span data-stu-id="fe2fe-133">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 <span data-ttu-id="fe2fe-134">チャネルファクトリおよびチャネルキャッシュの既定のキャッシュ共有レベルとキャッシュ設定を変更する方法の詳細については、「 [Send アクティビティのキャッシュ共有レベルの変更](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe2fe-134">For more information about how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe2fe-135">例</span><span class="sxs-lookup"><span data-stu-id="fe2fe-135">Example</span></span>  
 <span data-ttu-id="fe2fe-136">ホストされたワークフロー サービスでは、ファクトリ キャッシュとチャネル キャッシュの設定をアプリケーション構成ファイルで指定できます。</span><span class="sxs-lookup"><span data-stu-id="fe2fe-136">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="fe2fe-137">これを行うには、ファクトリ キャッシュおよびチャネル キャッシュのキャッシュ設定を含むサービス動作を追加し、そのサービス動作をサービスに追加します。</span><span class="sxs-lookup"><span data-stu-id="fe2fe-137">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="fe2fe-138">次の例は、カスタムファクトリキャッシュとチャネルキャッシュ設定を`MyChannelCacheBehavior`使用したサービス動作を含む構成ファイルの内容を示しています。</span><span class="sxs-lookup"><span data-stu-id="fe2fe-138">The following example shows the contents of a configuration file that contains the `MyChannelCacheBehavior`  service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="fe2fe-139">このサービス動作は、 `behaviorConfiguration`属性を通じてサービスに追加されます。</span><span class="sxs-lookup"><span data-stu-id="fe2fe-139">This service behavior is added to the service through the `behaviorConfiguration` attribute.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fe2fe-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="fe2fe-140">See also</span></span>

- <xref:System.ServiceModel.Activities.SendMessageChannelCache>
- <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>
- <xref:System.ServiceModel.Activities.Send>
- <xref:System.ServiceModel.Activities.ChannelCacheSettings>
- [<span data-ttu-id="fe2fe-141">Send アクティビティのキャッシュ共有レベルの変更</span><span class="sxs-lookup"><span data-stu-id="fe2fe-141">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)
