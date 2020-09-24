---
title: <sendMessageChannelCache>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 241e428e-5030-4b13-8a0a-69f05288d3d9
ms.openlocfilehash: c1775ddabffda58c7529a64b89c9c53ff3da7b99
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164923"
---
# \<sendMessageChannelCache>

<span data-ttu-id="afa13-101">キャッシュの共有レベルのカスタマイズや、チャネル ファクトリ キャッシュの設定を可能にするほか、Send メッセージング アクティビティを使用してサービス エンドポイントにメッセージを送信するワークフローのチャネル キャッシュの設定も可能にするサービス動作。</span><span class="sxs-lookup"><span data-stu-id="afa13-101">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sendMessageChannelCache>**  
  
## <a name="syntax"></a><span data-ttu-id="afa13-102">構文</span><span class="sxs-lookup"><span data-stu-id="afa13-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="afa13-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="afa13-103">Attributes and Elements</span></span>  

 <span data-ttu-id="afa13-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="afa13-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="afa13-105">属性</span><span class="sxs-lookup"><span data-stu-id="afa13-105">Attributes</span></span>  
  
|<span data-ttu-id="afa13-106">属性</span><span class="sxs-lookup"><span data-stu-id="afa13-106">Attribute</span></span>|<span data-ttu-id="afa13-107">[説明]</span><span class="sxs-lookup"><span data-stu-id="afa13-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="afa13-108">allowUnsafeCaching</span><span class="sxs-lookup"><span data-stu-id="afa13-108">allowUnsafeCaching</span></span>|<span data-ttu-id="afa13-109">キャッシュをオンにするかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="afa13-109">A Boolean value that indicates whether to turn caching on.</span></span> <span data-ttu-id="afa13-110">ワークフロー サービスにカスタムのバインディングまたは動作がある場合は、キャッシュが安全性を損う可能性があるため、既定では無効になります。</span><span class="sxs-lookup"><span data-stu-id="afa13-110">If your workflow service has custom bindings or custom behaviors, caching could be unsecure and therefore is disabled by default.</span></span> <span data-ttu-id="afa13-111">ただし、キャッシュを有効にする場合は、このプロパティを **true**に設定します。</span><span class="sxs-lookup"><span data-stu-id="afa13-111">However, if you want to turn caching on set this property to **true**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="afa13-112">子要素</span><span class="sxs-lookup"><span data-stu-id="afa13-112">Child Elements</span></span>  
  
|<span data-ttu-id="afa13-113">要素</span><span class="sxs-lookup"><span data-stu-id="afa13-113">Element</span></span>|<span data-ttu-id="afa13-114">説明</span><span class="sxs-lookup"><span data-stu-id="afa13-114">Description</span></span>|  
|-------------|-----------------|  
|[\<channelSettings>](channelsettings.md)|<span data-ttu-id="afa13-115">チャネル キャッシュの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="afa13-115">Specifies the settings of the channel cache.</span></span>|  
|[\<factorySettings>](factorysettings.md)|<span data-ttu-id="afa13-116">チャネル ファクトリ キャッシュの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="afa13-116">Specifies the settings of the channel factory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="afa13-117">親要素</span><span class="sxs-lookup"><span data-stu-id="afa13-117">Parent Elements</span></span>  
  
|<span data-ttu-id="afa13-118">要素</span><span class="sxs-lookup"><span data-stu-id="afa13-118">Element</span></span>|<span data-ttu-id="afa13-119">説明</span><span class="sxs-lookup"><span data-stu-id="afa13-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="afa13-120">\<serviceBehaviors> の \<behavior></span><span class="sxs-lookup"><span data-stu-id="afa13-120">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="afa13-121">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="afa13-121">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="afa13-122">解説</span><span class="sxs-lookup"><span data-stu-id="afa13-122">Remarks</span></span>  

 <span data-ttu-id="afa13-123">このサービス動作は、サービス エンドポイントにメッセージを送信するワークフローを対象としています。</span><span class="sxs-lookup"><span data-stu-id="afa13-123">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="afa13-124">これらのワークフローは、通常はクライアント ワークフローですが、<xref:System.ServiceModel.WorkflowServiceHost> でホストされるワークフロー サービスである場合もあります。</span><span class="sxs-lookup"><span data-stu-id="afa13-124">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="afa13-125">既定では、<xref:System.ServiceModel.WorkflowServiceHost> によってホストされるワークフローでは、<xref:System.ServiceModel.Activities.Send> メッセージング アクティビティが使用するキャッシュは <xref:System.ServiceModel.WorkflowServiceHost> のすべてのワークフロー インスタンス間で共有されます (ホストレベルのキャッシュ)。</span><span class="sxs-lookup"><span data-stu-id="afa13-125">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="afa13-126"><xref:System.ServiceModel.WorkflowServiceHost> によってホストされないクライアント ワークフローの場合、キャッシュを使用できるのはワークフロー インスタンスだけです (インスタンスレベルのキャッシュ)。</span><span class="sxs-lookup"><span data-stu-id="afa13-126">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="afa13-127">構成でエンドポイントが定義されているワークフローに送信アクティビティがある場合、キャッシュは既定で無効になります。</span><span class="sxs-lookup"><span data-stu-id="afa13-127">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 <span data-ttu-id="afa13-128">チャネルファクトリおよびチャネルキャッシュの既定のキャッシュ共有レベルとキャッシュ設定を変更する方法の詳細については、「 [Send アクティビティのキャッシュ共有レベルの変更](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="afa13-128">For more information about how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="afa13-129">例</span><span class="sxs-lookup"><span data-stu-id="afa13-129">Example</span></span>  

 <span data-ttu-id="afa13-130">ホストされたワークフロー サービスでは、ファクトリ キャッシュとチャネル キャッシュの設定をアプリケーション構成ファイルで指定できます。</span><span class="sxs-lookup"><span data-stu-id="afa13-130">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="afa13-131">これを行うには、ファクトリ キャッシュおよびチャネル キャッシュのキャッシュ設定を含むサービス動作を追加し、そのサービス動作をサービスに追加します。</span><span class="sxs-lookup"><span data-stu-id="afa13-131">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="afa13-132">次の例は、 `MyChannelCacheBehavior`  カスタムファクトリキャッシュとチャネルキャッシュ設定を使用したサービス動作を含む構成ファイルの内容を示しています。</span><span class="sxs-lookup"><span data-stu-id="afa13-132">The following example shows the contents of a configuration file that contains the `MyChannelCacheBehavior`  service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="afa13-133">このサービス動作は、属性を通じてサービスに追加され `behaviorConfiguration` ます。</span><span class="sxs-lookup"><span data-stu-id="afa13-133">This service behavior is added to the service through the `behaviorConfiguration` attribute.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="afa13-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="afa13-134">See also</span></span>

- <xref:System.ServiceModel.Activities.SendMessageChannelCache>
- <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>
- <xref:System.ServiceModel.Activities.Send>
- [<span data-ttu-id="afa13-135">Send アクティビティのキャッシュ共有レベルの変更</span><span class="sxs-lookup"><span data-stu-id="afa13-135">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)
