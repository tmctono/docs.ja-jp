---
title: <sendMessageChannelCache>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 241e428e-5030-4b13-8a0a-69f05288d3d9
ms.openlocfilehash: 60847f423c61b9e7f49a4a7594c965fb75354714
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61794382"
---
# <a name="sendmessagechannelcache"></a><span data-ttu-id="3c8b5-101">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="3c8b5-101">\<sendMessageChannelCache></span></span>
<span data-ttu-id="3c8b5-102">キャッシュ共有レベル、チャネル ファクトリ キャッシュの設定、および送信メッセージング アクティビティを使用してサービス エンドポイントにメッセージを送信するワークフローのチャネル キャッシュの設定をカスタマイズするサービス動作。</span><span class="sxs-lookup"><span data-stu-id="3c8b5-102">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>  
  
<span data-ttu-id="3c8b5-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="3c8b5-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="3c8b5-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="3c8b5-104">\<behaviors></span></span>  
<span data-ttu-id="3c8b5-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="3c8b5-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="3c8b5-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="3c8b5-106">\<behavior></span></span>  
<span data-ttu-id="3c8b5-107">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="3c8b5-107">\<sendMessageChannelCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c8b5-108">構文</span><span class="sxs-lookup"><span data-stu-id="3c8b5-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3c8b5-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3c8b5-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3c8b5-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3c8b5-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3c8b5-111">属性</span><span class="sxs-lookup"><span data-stu-id="3c8b5-111">Attributes</span></span>  
  
|<span data-ttu-id="3c8b5-112">属性</span><span class="sxs-lookup"><span data-stu-id="3c8b5-112">Attribute</span></span>|<span data-ttu-id="3c8b5-113">説明</span><span class="sxs-lookup"><span data-stu-id="3c8b5-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3c8b5-114">allowUnsafeCaching</span><span class="sxs-lookup"><span data-stu-id="3c8b5-114">allowUnsafeCaching</span></span>|<span data-ttu-id="3c8b5-115">キャッシュをオンにするかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="3c8b5-115">A Boolean value that indicates whether to turn caching on.</span></span> <span data-ttu-id="3c8b5-116">ワークフロー サービスにカスタムのバインディングまたは動作がある場合は、キャッシュが安全性を損う可能性があるため、既定では無効になります。</span><span class="sxs-lookup"><span data-stu-id="3c8b5-116">If your workflow service has custom bindings or custom behaviors, caching could be unsecure and therefore is disabled by default.</span></span> <span data-ttu-id="3c8b5-117">ただし、有効にする場合のキャッシュでこのプロパティを設定**true**します。</span><span class="sxs-lookup"><span data-stu-id="3c8b5-117">However, if you want to turn caching on set this property to **true**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3c8b5-118">子要素</span><span class="sxs-lookup"><span data-stu-id="3c8b5-118">Child Elements</span></span>  
  
|<span data-ttu-id="3c8b5-119">要素</span><span class="sxs-lookup"><span data-stu-id="3c8b5-119">Element</span></span>|<span data-ttu-id="3c8b5-120">説明</span><span class="sxs-lookup"><span data-stu-id="3c8b5-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3c8b5-121">\<channelSettings></span><span class="sxs-lookup"><span data-stu-id="3c8b5-121">\<channelSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/channelsettings.md)|<span data-ttu-id="3c8b5-122">チャネル キャッシュの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="3c8b5-122">Specifies the settings of the channel cache.</span></span>|  
|[<span data-ttu-id="3c8b5-123">\<factorySettings></span><span class="sxs-lookup"><span data-stu-id="3c8b5-123">\<factorySettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/factorysettings.md)|<span data-ttu-id="3c8b5-124">チャネル ファクトリ キャッシュの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="3c8b5-124">Specifies the settings of the channel factory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3c8b5-125">親要素</span><span class="sxs-lookup"><span data-stu-id="3c8b5-125">Parent Elements</span></span>  
  
|<span data-ttu-id="3c8b5-126">要素</span><span class="sxs-lookup"><span data-stu-id="3c8b5-126">Element</span></span>|<span data-ttu-id="3c8b5-127">説明</span><span class="sxs-lookup"><span data-stu-id="3c8b5-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3c8b5-128">\<動作 > の\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="3c8b5-128">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="3c8b5-129">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="3c8b5-129">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c8b5-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="3c8b5-130">Remarks</span></span>  
 <span data-ttu-id="3c8b5-131">このサービス動作は、サービス エンドポイントにメッセージを送信するワークフローを対象としています。</span><span class="sxs-lookup"><span data-stu-id="3c8b5-131">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="3c8b5-132">これらのワークフローは、通常はクライアント ワークフローですが、<xref:System.ServiceModel.WorkflowServiceHost> でホストされるワークフロー サービスである場合もあります。</span><span class="sxs-lookup"><span data-stu-id="3c8b5-132">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="3c8b5-133">既定では、<xref:System.ServiceModel.WorkflowServiceHost> によってホストされるワークフローでは、<xref:System.ServiceModel.Activities.Send> メッセージング アクティビティが使用するキャッシュは <xref:System.ServiceModel.WorkflowServiceHost> のすべてのワークフロー インスタンス間で共有されます (ホストレベルのキャッシュ)。</span><span class="sxs-lookup"><span data-stu-id="3c8b5-133">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="3c8b5-134"><xref:System.ServiceModel.WorkflowServiceHost> によってホストされないクライアント ワークフローの場合、キャッシュを使用できるのはワークフロー インスタンスだけです (インスタンスレベルのキャッシュ)。</span><span class="sxs-lookup"><span data-stu-id="3c8b5-134">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="3c8b5-135">構成でエンドポイントが定義されているワークフローに送信アクティビティがある場合、キャッシュは既定で無効になります。</span><span class="sxs-lookup"><span data-stu-id="3c8b5-135">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 <span data-ttu-id="3c8b5-136">既定のキャッシュ共有レベルとチャネル ファクトリおよびチャネル キャッシュのキャッシュ設定を変更する方法の詳細については、次を参照してください。 [Send アクティビティのキャッシュ共有レベルを変更する](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)します。</span><span class="sxs-lookup"><span data-stu-id="3c8b5-136">For more information about how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c8b5-137">例</span><span class="sxs-lookup"><span data-stu-id="3c8b5-137">Example</span></span>  
 <span data-ttu-id="3c8b5-138">ホストされたワークフロー サービスでは、ファクトリ キャッシュとチャネル キャッシュの設定をアプリケーション構成ファイルで指定できます。</span><span class="sxs-lookup"><span data-stu-id="3c8b5-138">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="3c8b5-139">これを行うには、ファクトリ キャッシュおよびチャネル キャッシュのキャッシュ設定を含むサービス動作を追加し、そのサービス動作をサービスに追加します。</span><span class="sxs-lookup"><span data-stu-id="3c8b5-139">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="3c8b5-140">次の例を含む構成ファイルの内容を示しています、 **MyChannelCacheBehavior**サービス動作、カスタム ファクトリ キャッシュおよびチャネル キャッシュの設定をします。</span><span class="sxs-lookup"><span data-stu-id="3c8b5-140">The following example shows the contents of a configuration file that contains the **MyChannelCacheBehavior**  service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="3c8b5-141">このサービス動作を介してサービスに追加されます、 **behaviorConfiguarion**属性。</span><span class="sxs-lookup"><span data-stu-id="3c8b5-141">This service behavior is added to the service through the **behaviorConfiguarion** attribute.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3c8b5-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="3c8b5-142">See also</span></span>

- <xref:System.ServiceModel.Activities.SendMessageChannelCache>
- <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>
- <xref:System.ServiceModel.Activities.Send>
- [<span data-ttu-id="3c8b5-143">Send アクティビティのキャッシュ共有レベルの変更</span><span class="sxs-lookup"><span data-stu-id="3c8b5-143">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)
