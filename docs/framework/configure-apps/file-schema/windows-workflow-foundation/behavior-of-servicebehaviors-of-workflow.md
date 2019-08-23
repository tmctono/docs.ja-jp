---
title: <behavior>ワークフロー <serviceBehaviors>の
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a4b718a-1b40-4957-935a-f6122819ab3c
ms.openlocfilehash: 91883c42aa7bc0aa8fa0c63c3c45184ba69225d0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946077"
---
# <a name="behavior-of-servicebehaviors-of-workflow"></a><span data-ttu-id="34bfb-102">\<ワークフローの servicebehaviors > の\<動作 ></span><span class="sxs-lookup"><span data-stu-id="34bfb-102">\<behavior> of \<serviceBehaviors> of workflow</span></span>
<span data-ttu-id="34bfb-103">**Behavior**要素には、サービスの動作に関する設定のコレクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="34bfb-103">The **behavior** element contains a collection of settings for the behavior of a service.</span></span> <span data-ttu-id="34bfb-104">各動作は、**名前**によってインデックスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="34bfb-104">Each behavior is indexed by its **name**.</span></span> <span data-ttu-id="34bfb-105">サービスは、 [ \<エンドポイント >](../wcf/endpoint-element.md)要素の**設定**属性を使用して、この名前を使用して各動作にリンクできます。</span><span class="sxs-lookup"><span data-stu-id="34bfb-105">Services can link to each behavior through this name using the **behaviorConfiguration** attribute of the [\<endpoint>](../wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="34bfb-106">これにより、設定を再定義することなく、エンドポイント間で共通の動作構成を共有できます。</span><span class="sxs-lookup"><span data-stu-id="34bfb-106">This allows endpoints to share common behavior configurations without redefining the settings.</span></span>  
  
<span data-ttu-id="34bfb-107">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="34bfb-107">\<system.ServiceModel></span></span>  
<span data-ttu-id="34bfb-108">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="34bfb-108">\<behaviors></span></span>  
<span data-ttu-id="34bfb-109">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="34bfb-109">\<serviceBehaviors></span></span>  
<span data-ttu-id="34bfb-110">\<behavior></span><span class="sxs-lookup"><span data-stu-id="34bfb-110">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34bfb-111">構文</span><span class="sxs-lookup"><span data-stu-id="34bfb-111">Syntax</span></span>  
  
```xml  
<system.ServiceModel>  
  <behaviors>  
    <serviceBehaviors>  
      <behavior name="String">
        <bufferReceive maxPendingMessagesPerChannel="Integer" />
        <etwTracking profileName="String" />
        <sendMessageChannelCache allowUnsafeCaching="Boolean">
          <channelSettings idleTimeout="TimeSpan" 
                           leaseTimeout="TimeSpan" 
                           maxItemsInCache="Integer" />
          <factorySettings idleTimeout="TimeSpan" 
                           leaseTimeout="TimeSpan" 
                           maxItemsInCache="Integer" />
        </sendMessageChannelCache>
        <sqlWorkflowInstanceStore connectionStringName="String" 
                                  hostLockRenewalPeriod="TimeSpan" 
                                  instanceCompletionAction="DeleteNothing/DeleteAll" 
                                  instanceEncodingAction="None/GZip" 
                                  instanceLockedExceptionAction="NoRetry/BasicRetry/AggressiveRetry" 
                                  runnableInstancesDetectionPeriod="TimeSpan" />
        <workflowIdle timeToPersist="TimeSpan" 
                      timeToUnload="TimeSpan" />
        <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
      </behavior>
    </serviceBehaviors>  
  </behaviors>  
</system.ServiceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34bfb-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="34bfb-112">Attributes and Elements</span></span>  
 <span data-ttu-id="34bfb-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="34bfb-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34bfb-114">属性</span><span class="sxs-lookup"><span data-stu-id="34bfb-114">Attributes</span></span>  
  
|<span data-ttu-id="34bfb-115">属性</span><span class="sxs-lookup"><span data-stu-id="34bfb-115">Attribute</span></span>|<span data-ttu-id="34bfb-116">説明</span><span class="sxs-lookup"><span data-stu-id="34bfb-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="34bfb-117">name</span><span class="sxs-lookup"><span data-stu-id="34bfb-117">name</span></span>|<span data-ttu-id="34bfb-118">動作の構成名を含む一意の文字列。</span><span class="sxs-lookup"><span data-stu-id="34bfb-118">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="34bfb-119">この値は、要素の識別文字列として機能するため、一意のユーザー定義の文字列である必要があります。</span><span class="sxs-lookup"><span data-stu-id="34bfb-119">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="34bfb-120">子要素</span><span class="sxs-lookup"><span data-stu-id="34bfb-120">Child Elements</span></span>  
  
|<span data-ttu-id="34bfb-121">要素</span><span class="sxs-lookup"><span data-stu-id="34bfb-121">Element</span></span>|<span data-ttu-id="34bfb-122">説明</span><span class="sxs-lookup"><span data-stu-id="34bfb-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="34bfb-123">\<bufferReceive ></span><span class="sxs-lookup"><span data-stu-id="34bfb-123">\<bufferReceive></span></span>](bufferreceive.md)|<span data-ttu-id="34bfb-124">サービスが、バッファーされた受信処理を使用するためのサービス動作。これにより、ワークフロー サービスは、順番を無視したメッセージを処理できます。</span><span class="sxs-lookup"><span data-stu-id="34bfb-124">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>|  
|[<span data-ttu-id="34bfb-125">\<ルーティング ></span><span class="sxs-lookup"><span data-stu-id="34bfb-125">\<routing></span></span>](../wcf/routing-of-servicebehavior.md)|<span data-ttu-id="34bfb-126">サービスがを使用して<xref:System.Activities.Tracking.EtwTrackingParticipant>ETW 追跡を利用できるようにするサービス動作。</span><span class="sxs-lookup"><span data-stu-id="34bfb-126">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>|  
|[<span data-ttu-id="34bfb-127">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="34bfb-127">\<sendMessageChannelCache></span></span>](sendmessagechannelcache.md)|<span data-ttu-id="34bfb-128">キャッシュ共有レベルのカスタマイズ、チャネルファクトリキャッシュの設定、およびメッセージを送信するアクティビティを使用してサービスエンドポイントにメッセージを送信するワークフローのチャネルキャッシュの設定を可能にするサービス動作。</span><span class="sxs-lookup"><span data-stu-id="34bfb-128">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
|[<span data-ttu-id="34bfb-129">\<sqlWorkflowInstanceStore></span><span class="sxs-lookup"><span data-stu-id="34bfb-129">\<sqlWorkflowInstanceStore></span></span>](sqlworkflowinstancestore.md)|<span data-ttu-id="34bfb-130">ワークフローサービスインスタンスの状態情報の SQL Server 2005 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>または SQL Server 2008 データベースへの永続化をサポートする機能を構成できるようにするサービス動作。</span><span class="sxs-lookup"><span data-stu-id="34bfb-130">A service behavior that allows you to configure the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> feature, which supports persisting state information for workflow service instances into an SQL Server 2005 or SQL Server 2008 database.</span></span>|  
|[<span data-ttu-id="34bfb-131">\<workflowIdle ></span><span class="sxs-lookup"><span data-stu-id="34bfb-131">\<workflowIdle></span></span>](workflowidle.md)|<span data-ttu-id="34bfb-132">アイドル状態のワークフロー インスタンスのアンロードおよび永続化のタイミングを制御するサービス動作。</span><span class="sxs-lookup"><span data-stu-id="34bfb-132">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>|  
|[<span data-ttu-id="34bfb-133">\<workflowInstanceManagement ></span><span class="sxs-lookup"><span data-stu-id="34bfb-133">\<workflowInstanceManagement></span></span>](workflowinstancemanagement.md)|<span data-ttu-id="34bfb-134">ワークフロー インスタンスの実行方法を制御する設定を指定するためのサービス動作。これには、永続する未処理の例外動作やアイドル状態の動作が含まれます。</span><span class="sxs-lookup"><span data-stu-id="34bfb-134">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>|  
|[<span data-ttu-id="34bfb-135">\<workflowUnhandledException ></span><span class="sxs-lookup"><span data-stu-id="34bfb-135">\<workflowUnhandledException></span></span>](workflowunhandledexception.md)|<span data-ttu-id="34bfb-136">ワークフロー サービス内で未処理の例外が発生した場合のアクションを指定するためのサービス動作。</span><span class="sxs-lookup"><span data-stu-id="34bfb-136">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="34bfb-137">親要素</span><span class="sxs-lookup"><span data-stu-id="34bfb-137">Parent Elements</span></span>  
  
|<span data-ttu-id="34bfb-138">要素</span><span class="sxs-lookup"><span data-stu-id="34bfb-138">Element</span></span>|<span data-ttu-id="34bfb-139">説明</span><span class="sxs-lookup"><span data-stu-id="34bfb-139">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="34bfb-140">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="34bfb-140">\<serviceBehaviors></span></span>](servicebehaviors-of-workflow.md)|<span data-ttu-id="34bfb-141">サービス動作要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="34bfb-141">A collection of service behavior elements.</span></span>|
