---
title: <channelSettings>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 94a4457f-f43f-458d-a47e-2d11103ee75e
ms.openlocfilehash: f70e30c903fa9bfc3f5d6054ef2ec34bf1b3cba1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790209"
---
# <a name="channelsettings"></a><span data-ttu-id="fe482-101">\<channelSettings></span><span class="sxs-lookup"><span data-stu-id="fe482-101">\<channelSettings></span></span>
<span data-ttu-id="fe482-102">チャネル キャッシュの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="fe482-102">Specifies the settings of the channel cache.</span></span>  
  
<span data-ttu-id="fe482-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="fe482-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="fe482-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="fe482-104">\<behaviors></span></span>  
<span data-ttu-id="fe482-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="fe482-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="fe482-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="fe482-106">\<behavior></span></span>  
<span data-ttu-id="fe482-107">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="fe482-107">\<sendMessageChannelCache></span></span>  
<span data-ttu-id="fe482-108">\<channelSettings></span><span class="sxs-lookup"><span data-stu-id="fe482-108">\<channelSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe482-109">構文</span><span class="sxs-lookup"><span data-stu-id="fe482-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fe482-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="fe482-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fe482-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="fe482-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fe482-112">属性</span><span class="sxs-lookup"><span data-stu-id="fe482-112">Attributes</span></span>  
  
|<span data-ttu-id="fe482-113">属性</span><span class="sxs-lookup"><span data-stu-id="fe482-113">Attribute</span></span>|<span data-ttu-id="fe482-114">説明</span><span class="sxs-lookup"><span data-stu-id="fe482-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fe482-115">idleTimeout</span><span class="sxs-lookup"><span data-stu-id="fe482-115">idleTimeout</span></span>|<span data-ttu-id="fe482-116">オブジェクトが破棄されるまでにキャッシュ内でアイドル状態を維持できる最大時間を指定する TimeSpan 値。</span><span class="sxs-lookup"><span data-stu-id="fe482-116">A TimeSpan value that specifies the maximum interval of time for which the object can remain idle in the cache before being disposed.</span></span>|  
|<span data-ttu-id="fe482-117">leaseTimeout</span><span class="sxs-lookup"><span data-stu-id="fe482-117">leaseTimeout</span></span>|<span data-ttu-id="fe482-118">キャッシュからオブジェクトが削除されるまでの期間を指定する TimeSpan 値。</span><span class="sxs-lookup"><span data-stu-id="fe482-118">A TimeSpan value that specifies  the interval of time after which an object is removed from the cache.</span></span>|  
|<span data-ttu-id="fe482-119">maxItemsInCache</span><span class="sxs-lookup"><span data-stu-id="fe482-119">maxItemsInCache</span></span>|<span data-ttu-id="fe482-120">キャッシュに置くことができるオブジェクトの最大数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="fe482-120">An integer that specifies the maximum number of objects that can be in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fe482-121">子要素</span><span class="sxs-lookup"><span data-stu-id="fe482-121">Child Elements</span></span>  
 <span data-ttu-id="fe482-122">なし。</span><span class="sxs-lookup"><span data-stu-id="fe482-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fe482-123">親要素</span><span class="sxs-lookup"><span data-stu-id="fe482-123">Parent Elements</span></span>  
  
|<span data-ttu-id="fe482-124">要素</span><span class="sxs-lookup"><span data-stu-id="fe482-124">Element</span></span>|<span data-ttu-id="fe482-125">説明</span><span class="sxs-lookup"><span data-stu-id="fe482-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fe482-126">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="fe482-126">\<sendMessageChannelCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sendmessagechannelcache.md)|<span data-ttu-id="fe482-127">キャッシュ共有レベル、チャネル ファクトリ キャッシュの設定、および送信メッセージング アクティビティを使用してサービス エンドポイントにメッセージを送信するワークフローのチャネル キャッシュの設定をカスタマイズするサービス動作。</span><span class="sxs-lookup"><span data-stu-id="fe482-127">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe482-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="fe482-128">Remarks</span></span>  
 <span data-ttu-id="fe482-129">このサービス動作は、サービス エンドポイントにメッセージを送信するワークフローを対象としています。</span><span class="sxs-lookup"><span data-stu-id="fe482-129">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="fe482-130">これらのワークフローは、通常はクライアント ワークフローですが、<xref:System.ServiceModel.WorkflowServiceHost> でホストされるワークフロー サービスである場合もあります。</span><span class="sxs-lookup"><span data-stu-id="fe482-130">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="fe482-131">既定では、<xref:System.ServiceModel.WorkflowServiceHost> によってホストされるワークフローでは、<xref:System.ServiceModel.Activities.Send> メッセージング アクティビティが使用するキャッシュは <xref:System.ServiceModel.WorkflowServiceHost> のすべてのワークフロー インスタンス間で共有されます (ホストレベルのキャッシュ)。</span><span class="sxs-lookup"><span data-stu-id="fe482-131">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="fe482-132"><xref:System.ServiceModel.WorkflowServiceHost> によってホストされないクライアント ワークフローの場合、キャッシュを使用できるのはワークフロー インスタンスだけです (インスタンスレベルのキャッシュ)。</span><span class="sxs-lookup"><span data-stu-id="fe482-132">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="fe482-133">構成でエンドポイントが定義されているワークフローに送信アクティビティがある場合、キャッシュは既定で無効になります。</span><span class="sxs-lookup"><span data-stu-id="fe482-133">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 <span data-ttu-id="fe482-134">既定のキャッシュ共有レベルとチャネル ファクトリおよびチャネル キャッシュのキャッシュ設定を変更する方法の詳細については、次を参照してください。 [Send アクティビティのキャッシュ共有レベルを変更する](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)します。</span><span class="sxs-lookup"><span data-stu-id="fe482-134">For more information about how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe482-135">例</span><span class="sxs-lookup"><span data-stu-id="fe482-135">Example</span></span>  
 <span data-ttu-id="fe482-136">ホストされたワークフロー サービスでは、ファクトリ キャッシュとチャネル キャッシュの設定をアプリケーション構成ファイルで指定できます。</span><span class="sxs-lookup"><span data-stu-id="fe482-136">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="fe482-137">これを行うには、ファクトリ キャッシュおよびチャネル キャッシュのキャッシュ設定を含むサービス動作を追加し、そのサービス動作をサービスに追加します。</span><span class="sxs-lookup"><span data-stu-id="fe482-137">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="fe482-138">次の例を含む構成ファイルの内容を示しています、 **MyChannelCacheBehavior**サービス動作、カスタム ファクトリ キャッシュおよびチャネル キャッシュの設定をします。</span><span class="sxs-lookup"><span data-stu-id="fe482-138">The following example shows the contents of a configuration file that contains the **MyChannelCacheBehavior**  service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="fe482-139">このサービス動作を介してサービスに追加されます、 **behaviorConfiguarion**属性。</span><span class="sxs-lookup"><span data-stu-id="fe482-139">This service behavior is added to the service through the **behaviorConfiguarion** attribute.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fe482-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="fe482-140">See also</span></span>

- <xref:System.ServiceModel.Activities.SendMessageChannelCache>
- <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>
- <xref:System.ServiceModel.Activities.Send>
- <xref:System.ServiceModel.Activities.ChannelCacheSettings>
- [<span data-ttu-id="fe482-141">Send アクティビティのキャッシュ共有レベルの変更</span><span class="sxs-lookup"><span data-stu-id="fe482-141">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)
