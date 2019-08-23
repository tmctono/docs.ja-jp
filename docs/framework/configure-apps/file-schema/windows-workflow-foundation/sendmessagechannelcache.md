---
title: <sendMessageChannelCache>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 241e428e-5030-4b13-8a0a-69f05288d3d9
ms.openlocfilehash: de53eb16d53d1e37209e36f2f6bfdc4bdfd84465
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947546"
---
# <a name="sendmessagechannelcache"></a><span data-ttu-id="acb0c-101">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="acb0c-101">\<sendMessageChannelCache></span></span>
<span data-ttu-id="acb0c-102">キャッシュ共有レベルのカスタマイズ、チャネルファクトリキャッシュの設定、およびメッセージを送信するアクティビティを使用してサービスエンドポイントにメッセージを送信するワークフローのチャネルキャッシュの設定を可能にするサービス動作。</span><span class="sxs-lookup"><span data-stu-id="acb0c-102">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>  
  
<span data-ttu-id="acb0c-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="acb0c-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="acb0c-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="acb0c-104">\<behaviors></span></span>  
<span data-ttu-id="acb0c-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="acb0c-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="acb0c-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="acb0c-106">\<behavior></span></span>  
<span data-ttu-id="acb0c-107">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="acb0c-107">\<sendMessageChannelCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acb0c-108">構文</span><span class="sxs-lookup"><span data-stu-id="acb0c-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <sendMessageChannelCache allowUnsafeCaching="Boolean">
        <channelSettings idleTimeout="TimeSpan"
                         leaseTimeout="TimeSpan" 
                         maxItemsInCache="Integer" />
        <factorySettings idleTimeout="TimeSpan" 
                         leaseTimeout="TimeSpan" 
                         maxItemsInCache="Integer" />
      </sendMessageChannelCache>
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="acb0c-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="acb0c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="acb0c-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="acb0c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="acb0c-111">属性</span><span class="sxs-lookup"><span data-stu-id="acb0c-111">Attributes</span></span>  
  
|<span data-ttu-id="acb0c-112">属性</span><span class="sxs-lookup"><span data-stu-id="acb0c-112">Attribute</span></span>|<span data-ttu-id="acb0c-113">説明</span><span class="sxs-lookup"><span data-stu-id="acb0c-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="acb0c-114">allowUnsafeCaching</span><span class="sxs-lookup"><span data-stu-id="acb0c-114">allowUnsafeCaching</span></span>|<span data-ttu-id="acb0c-115">キャッシュをオンにするかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="acb0c-115">A Boolean value that indicates whether to turn caching on.</span></span> <span data-ttu-id="acb0c-116">ワークフロー サービスにカスタムのバインディングまたは動作がある場合は、キャッシュが安全性を損う可能性があるため、既定では無効になります。</span><span class="sxs-lookup"><span data-stu-id="acb0c-116">If your workflow service has custom bindings or custom behaviors, caching could be unsecure and therefore is disabled by default.</span></span> <span data-ttu-id="acb0c-117">ただし、キャッシュを有効にする場合は、このプロパティを**true**に設定します。</span><span class="sxs-lookup"><span data-stu-id="acb0c-117">However, if you want to turn caching on set this property to **true**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="acb0c-118">子要素</span><span class="sxs-lookup"><span data-stu-id="acb0c-118">Child Elements</span></span>  
  
|<span data-ttu-id="acb0c-119">要素</span><span class="sxs-lookup"><span data-stu-id="acb0c-119">Element</span></span>|<span data-ttu-id="acb0c-120">説明</span><span class="sxs-lookup"><span data-stu-id="acb0c-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="acb0c-121">\<channelSettings></span><span class="sxs-lookup"><span data-stu-id="acb0c-121">\<channelSettings></span></span>](channelsettings.md)|<span data-ttu-id="acb0c-122">チャネル キャッシュの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="acb0c-122">Specifies the settings of the channel cache.</span></span>|  
|[<span data-ttu-id="acb0c-123">\<factorySettings ></span><span class="sxs-lookup"><span data-stu-id="acb0c-123">\<factorySettings></span></span>](factorysettings.md)|<span data-ttu-id="acb0c-124">チャネル ファクトリ キャッシュの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="acb0c-124">Specifies the settings of the channel factory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="acb0c-125">親要素</span><span class="sxs-lookup"><span data-stu-id="acb0c-125">Parent Elements</span></span>  
  
|<span data-ttu-id="acb0c-126">要素</span><span class="sxs-lookup"><span data-stu-id="acb0c-126">Element</span></span>|<span data-ttu-id="acb0c-127">説明</span><span class="sxs-lookup"><span data-stu-id="acb0c-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="acb0c-128">\<servicebehaviors の\<動作 > ></span><span class="sxs-lookup"><span data-stu-id="acb0c-128">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="acb0c-129">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="acb0c-129">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="acb0c-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="acb0c-130">Remarks</span></span>  
 <span data-ttu-id="acb0c-131">このサービス動作は、サービス エンドポイントにメッセージを送信するワークフローを対象としています。</span><span class="sxs-lookup"><span data-stu-id="acb0c-131">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="acb0c-132">これらのワークフローは、通常はクライアント ワークフローですが、<xref:System.ServiceModel.WorkflowServiceHost> でホストされるワークフロー サービスである場合もあります。</span><span class="sxs-lookup"><span data-stu-id="acb0c-132">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="acb0c-133">既定では、<xref:System.ServiceModel.WorkflowServiceHost> によってホストされるワークフローでは、<xref:System.ServiceModel.Activities.Send> メッセージング アクティビティが使用するキャッシュは <xref:System.ServiceModel.WorkflowServiceHost> のすべてのワークフロー インスタンス間で共有されます (ホストレベルのキャッシュ)。</span><span class="sxs-lookup"><span data-stu-id="acb0c-133">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="acb0c-134"><xref:System.ServiceModel.WorkflowServiceHost> によってホストされないクライアント ワークフローの場合、キャッシュを使用できるのはワークフロー インスタンスだけです (インスタンスレベルのキャッシュ)。</span><span class="sxs-lookup"><span data-stu-id="acb0c-134">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="acb0c-135">構成でエンドポイントが定義されているワークフローに送信アクティビティがある場合、キャッシュは既定で無効になります。</span><span class="sxs-lookup"><span data-stu-id="acb0c-135">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 <span data-ttu-id="acb0c-136">チャネルファクトリおよびチャネルキャッシュの既定のキャッシュ共有レベルとキャッシュ設定を変更する方法の詳細については、「 [Send アクティビティのキャッシュ共有レベルの変更](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="acb0c-136">For more information about how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="acb0c-137">例</span><span class="sxs-lookup"><span data-stu-id="acb0c-137">Example</span></span>  
 <span data-ttu-id="acb0c-138">ホストされたワークフロー サービスでは、ファクトリ キャッシュとチャネル キャッシュの設定をアプリケーション構成ファイルで指定できます。</span><span class="sxs-lookup"><span data-stu-id="acb0c-138">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="acb0c-139">これを行うには、ファクトリ キャッシュおよびチャネル キャッシュのキャッシュ設定を含むサービス動作を追加し、そのサービス動作をサービスに追加します。</span><span class="sxs-lookup"><span data-stu-id="acb0c-139">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="acb0c-140">次の例は、カスタムファクトリキャッシュとチャネルキャッシュ設定を`MyChannelCacheBehavior`使用したサービス動作を含む構成ファイルの内容を示しています。</span><span class="sxs-lookup"><span data-stu-id="acb0c-140">The following example shows the contents of a configuration file that contains the `MyChannelCacheBehavior`  service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="acb0c-141">このサービス動作は、 `behaviorConfiguration`属性を通じてサービスに追加されます。</span><span class="sxs-lookup"><span data-stu-id="acb0c-141">This service behavior is added to the service through the `behaviorConfiguration` attribute.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="acb0c-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="acb0c-142">See also</span></span>

- <xref:System.ServiceModel.Activities.SendMessageChannelCache>
- <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>
- <xref:System.ServiceModel.Activities.Send>
- [<span data-ttu-id="acb0c-143">Send アクティビティのキャッシュ共有レベルの変更</span><span class="sxs-lookup"><span data-stu-id="acb0c-143">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)
