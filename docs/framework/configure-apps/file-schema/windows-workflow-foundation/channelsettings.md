---
title: <channelSettings>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 94a4457f-f43f-458d-a47e-2d11103ee75e
ms.openlocfilehash: f6a57e2cc1e7c5e114fd38ee3534ab7c4e629b36
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152275"
---
# <a name="channelsettings"></a><span data-ttu-id="4fdd0-101">\<チャンネル設定></span><span class="sxs-lookup"><span data-stu-id="4fdd0-101">\<channelSettings></span></span>
<span data-ttu-id="4fdd0-102">チャネル キャッシュの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="4fdd0-102">Specifies the settings of the channel cache.</span></span>  
  
<span data-ttu-id="4fdd0-103">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4fdd0-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4fdd0-104">&nbsp;&nbsp;[**\<システム。サービスモデル>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="4fdd0-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="4fdd0-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<動作>**](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="4fdd0-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="4fdd0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<サービス動作>**](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="4fdd0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="4fdd0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<動作>**](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="4fdd0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="4fdd0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>を送信します。**](sendmessagechannelcache.md)</span><span class="sxs-lookup"><span data-stu-id="4fdd0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<sendMessageChannelCache>**](sendmessagechannelcache.md)</span></span>\
<span data-ttu-id="4fdd0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<チャンネル設定>**</span><span class="sxs-lookup"><span data-stu-id="4fdd0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<channelSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fdd0-110">構文</span><span class="sxs-lookup"><span data-stu-id="4fdd0-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4fdd0-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4fdd0-111">Attributes and Elements</span></span>  
 <span data-ttu-id="4fdd0-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4fdd0-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4fdd0-113">属性</span><span class="sxs-lookup"><span data-stu-id="4fdd0-113">Attributes</span></span>  
  
|<span data-ttu-id="4fdd0-114">属性</span><span class="sxs-lookup"><span data-stu-id="4fdd0-114">Attribute</span></span>|<span data-ttu-id="4fdd0-115">説明</span><span class="sxs-lookup"><span data-stu-id="4fdd0-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4fdd0-116">idleTimeout</span><span class="sxs-lookup"><span data-stu-id="4fdd0-116">idleTimeout</span></span>|<span data-ttu-id="4fdd0-117">オブジェクトが破棄されるまでにキャッシュ内でアイドル状態を維持できる最大時間を指定する TimeSpan 値。</span><span class="sxs-lookup"><span data-stu-id="4fdd0-117">A TimeSpan value that specifies the maximum interval of time for which the object can remain idle in the cache before being disposed.</span></span>|  
|<span data-ttu-id="4fdd0-118">leaseTimeout</span><span class="sxs-lookup"><span data-stu-id="4fdd0-118">leaseTimeout</span></span>|<span data-ttu-id="4fdd0-119">オブジェクトがキャッシュから削除されるまでの時間間隔を指定する TimeSpan 値。</span><span class="sxs-lookup"><span data-stu-id="4fdd0-119">A TimeSpan value that specifies  the interval of time after which an object is removed from the cache.</span></span>|  
|<span data-ttu-id="4fdd0-120">maxItemsInCache</span><span class="sxs-lookup"><span data-stu-id="4fdd0-120">maxItemsInCache</span></span>|<span data-ttu-id="4fdd0-121">キャッシュに置くことができるオブジェクトの最大数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="4fdd0-121">An integer that specifies the maximum number of objects that can be in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4fdd0-122">子要素</span><span class="sxs-lookup"><span data-stu-id="4fdd0-122">Child Elements</span></span>  
 <span data-ttu-id="4fdd0-123">[なし] :</span><span class="sxs-lookup"><span data-stu-id="4fdd0-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4fdd0-124">親要素</span><span class="sxs-lookup"><span data-stu-id="4fdd0-124">Parent Elements</span></span>  
  
|<span data-ttu-id="4fdd0-125">要素</span><span class="sxs-lookup"><span data-stu-id="4fdd0-125">Element</span></span>|<span data-ttu-id="4fdd0-126">説明</span><span class="sxs-lookup"><span data-stu-id="4fdd0-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4fdd0-127">\<>を送信します。</span><span class="sxs-lookup"><span data-stu-id="4fdd0-127">\<sendMessageChannelCache></span></span>](sendmessagechannelcache.md)|<span data-ttu-id="4fdd0-128">キャッシュの共有レベルのカスタマイズや、チャネル ファクトリ キャッシュの設定を可能にするほか、Send メッセージング アクティビティを使用してサービス エンドポイントにメッセージを送信するワークフローのチャネル キャッシュの設定も可能にするサービス動作。</span><span class="sxs-lookup"><span data-stu-id="4fdd0-128">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4fdd0-129">解説</span><span class="sxs-lookup"><span data-stu-id="4fdd0-129">Remarks</span></span>  
 <span data-ttu-id="4fdd0-130">このサービス動作は、サービス エンドポイントにメッセージを送信するワークフローを対象としています。</span><span class="sxs-lookup"><span data-stu-id="4fdd0-130">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="4fdd0-131">これらのワークフローは、通常はクライアント ワークフローですが、<xref:System.ServiceModel.WorkflowServiceHost> でホストされるワークフロー サービスである場合もあります。</span><span class="sxs-lookup"><span data-stu-id="4fdd0-131">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="4fdd0-132">既定では、<xref:System.ServiceModel.WorkflowServiceHost> によってホストされるワークフローでは、<xref:System.ServiceModel.Activities.Send> メッセージング アクティビティが使用するキャッシュは <xref:System.ServiceModel.WorkflowServiceHost> のすべてのワークフロー インスタンス間で共有されます (ホストレベルのキャッシュ)。</span><span class="sxs-lookup"><span data-stu-id="4fdd0-132">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="4fdd0-133"><xref:System.ServiceModel.WorkflowServiceHost> によってホストされないクライアント ワークフローの場合、キャッシュを使用できるのはワークフロー インスタンスだけです (インスタンスレベルのキャッシュ)。</span><span class="sxs-lookup"><span data-stu-id="4fdd0-133">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="4fdd0-134">構成でエンドポイントが定義されているワークフローに送信アクティビティがある場合、キャッシュは既定で無効になります。</span><span class="sxs-lookup"><span data-stu-id="4fdd0-134">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 <span data-ttu-id="4fdd0-135">チャネル ファクトリとチャネル キャッシュの既定のキャッシュ共有レベルとキャッシュ設定を変更する方法の詳細については[、「Send アクティビティのキャッシュ共有レベルを変更する](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4fdd0-135">For more information about how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4fdd0-136">例</span><span class="sxs-lookup"><span data-stu-id="4fdd0-136">Example</span></span>  
 <span data-ttu-id="4fdd0-137">ホストされたワークフロー サービスでは、ファクトリ キャッシュとチャネル キャッシュの設定をアプリケーション構成ファイルで指定できます。</span><span class="sxs-lookup"><span data-stu-id="4fdd0-137">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="4fdd0-138">これを行うには、ファクトリ キャッシュおよびチャネル キャッシュのキャッシュ設定を含むサービス動作を追加し、そのサービス動作をサービスに追加します。</span><span class="sxs-lookup"><span data-stu-id="4fdd0-138">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="4fdd0-139">次の例は、カスタム ファクトリ キャッシュとチャネル`MyChannelCacheBehavior`キャッシュ設定を使用したサービス動作を含む構成ファイルの内容を示しています。</span><span class="sxs-lookup"><span data-stu-id="4fdd0-139">The following example shows the contents of a configuration file that contains the `MyChannelCacheBehavior`  service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="4fdd0-140">このサービス動作は、 属性を介して`behaviorConfiguration`サービスに追加されます。</span><span class="sxs-lookup"><span data-stu-id="4fdd0-140">This service behavior is added to the service through the `behaviorConfiguration` attribute.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4fdd0-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="4fdd0-141">See also</span></span>

- <xref:System.ServiceModel.Activities.SendMessageChannelCache>
- <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>
- <xref:System.ServiceModel.Activities.Send>
- <xref:System.ServiceModel.Activities.ChannelCacheSettings>
- [<span data-ttu-id="4fdd0-142">Send アクティビティのキャッシュ共有レベルの変更</span><span class="sxs-lookup"><span data-stu-id="4fdd0-142">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)
