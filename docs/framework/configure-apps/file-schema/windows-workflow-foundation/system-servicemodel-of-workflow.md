---
title: ワークフローの <system.serviceModel>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a8eb2bf-f925-40e1-ba5c-a49b1d3a3ac6
ms.openlocfilehash: 005a274df9e9ab99227a3748b7a25c9d465d020f
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2019
ms.locfileid: "55271131"
---
# <a name="systemservicemodel-of-workflow"></a><span data-ttu-id="3d707-102">\<system.serviceModel > のワークフロー</span><span class="sxs-lookup"><span data-stu-id="3d707-102">\<system.serviceModel> of workflow</span></span>
<span data-ttu-id="3d707-103">この構成セクションには、すべてのワークフロー構成要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3d707-103">This configuration section contains all the workflow configuration elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d707-104">構文</span><span class="sxs-lookup"><span data-stu-id="3d707-104">Syntax</span></span>  
  
```xml  
<system.ServiceModel>  
  <behaviors>  
    <serviceBehaviors>  
    <behavior name="String">  
      <bufferReceive maxPendingMessagesPerChannel="Integer" />  
      <etwTracking profileName="String" />  
     <sendMessageChannelCache allowUnsafeCaching="Boolean" >          
        <channelSettings idleTimeout="TimeSpan" leaseTimeout="TimeSpan" maxItemsInCache="Integer" />  
        <factorySettings idleTimeout="TimeSpan" leaseTimeout="TimeSpan" maxItemsInCache="Integer" />  
     </sendMessageChannelCache>  
      <sqlWorkflowInstanceStore   
          connectionStringName="String"   
          honstLockRenewalPeriod="TimeSpan"  
          instanceCompletionAction="DeleteNothing/DeleteAll"  
          instanceEncodingAction="None/GZip"  
          instanceLockedExceptionAction="NoRetry/BasicRetry/AggressiveRetry"  
          runnableInstancesDetectionPeriod="TimeSpan" />  
      <workflowIdle timeToPersist="TimeSpan"  
          timeToUnload="TimeSpan" />  
      <workflowUnhandledExceptionaction="Abandon/AbandonAndSuspend/Cancel/Terminate" />  
    </behavior>  
    </serviceBehaviors>  
  </behaviors>  
  <tracking>    
     <participants>   
      <add name="String"   
           profileName="String"  
           type="String" />   
     </participants>   
    <trackingProfile name="String">  
      <workflow activityDefinitionId="String">  
          <activityScheduledQueries>  
             <activityScheduledQuery activityName="String"  
                 childActivityName="String"/>  
          </activityScheduledQueries>  
             <activityStateQuery activityName="String" />  
                <arguments>  
                   <argument name="String"/>  
                </arguments>  
                <states>  
                   <state name="String"/>  
                </states>  
                <variables>  
                   <variable name="String"/>  
                </variables>  
          </activityStateQueries>  
          <bookmarkResumptionQueries>  
             <bookmarkResumptionQuery name="String" />  
          </bookmarkResumptionQueries>  
          <cancelRequestQueries>  
             <cancelRequestQuery activityName="String"  
                 childActivityName="String"/>  
          </cancelRequestQueries>  
          <customTrackingQueries>  
             <customTrackingQuery activityName="String"  
                 name="String"/>  
          </customTrackingQueries>  
          <faultPropagationQueries>  
             <faultPropagationQuery activityName="String"  
                 faultHandlerActivityName="String"/>  
          </faultPropagationQueries>  
         <workflowInstanceQueries>  
            <workflowInstanceQuery>  
              <states>  
                 <state name="String"/>  
              </states>  
          </workflowInstanceQuery>  
        </workflowInstanceQueries>  
      </workflow>  
    </trackingProfile>          
   </profiles>  
  </tracking>  
</system.ServiceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3d707-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3d707-105">Attributes and Elements</span></span>  
 <span data-ttu-id="3d707-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3d707-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3d707-107">属性</span><span class="sxs-lookup"><span data-stu-id="3d707-107">Attributes</span></span>  
 <span data-ttu-id="3d707-108">なし</span><span class="sxs-lookup"><span data-stu-id="3d707-108">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3d707-109">子要素</span><span class="sxs-lookup"><span data-stu-id="3d707-109">Child Elements</span></span>  
  
|<span data-ttu-id="3d707-110">要素</span><span class="sxs-lookup"><span data-stu-id="3d707-110">Element</span></span>|<span data-ttu-id="3d707-111">説明</span><span class="sxs-lookup"><span data-stu-id="3d707-111">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3d707-112">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="3d707-112">\<behaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behaviors-of-workflow.md)|<span data-ttu-id="3d707-113">このセクションで定義、 **serviceBehaviors**コレクション。</span><span class="sxs-lookup"><span data-stu-id="3d707-113">This section defines the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="3d707-114">各コレクション内の要素は、サービスによって使用されるそれぞれの動作要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="3d707-114">Each element in the collection defines behavior elements consumed by services.</span></span> <span data-ttu-id="3d707-115">各動作要素が、一意で識別される**名前**属性。</span><span class="sxs-lookup"><span data-stu-id="3d707-115">Each behavior element is identified by its unique **name** attribute.</span></span>|  
|[<span data-ttu-id="3d707-116">\<tracking></span><span class="sxs-lookup"><span data-stu-id="3d707-116">\<tracking></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/tracking.md)|<span data-ttu-id="3d707-117">ワークフロー サービスの追跡設定を定義する構成セクションを表します。</span><span class="sxs-lookup"><span data-stu-id="3d707-117">Represents a configuration section for defining tracking settings for a workflow service.</span></span><br /><br /> <span data-ttu-id="3d707-118">ワークフロー追跡とその構成の詳細については、[ワークフロー追跡とトレース](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)と[ワークフローの追跡を構成する](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d707-118">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3d707-119">親要素</span><span class="sxs-lookup"><span data-stu-id="3d707-119">Parent Elements</span></span>  
  
|<span data-ttu-id="3d707-120">要素</span><span class="sxs-lookup"><span data-stu-id="3d707-120">Element</span></span>|<span data-ttu-id="3d707-121">説明</span><span class="sxs-lookup"><span data-stu-id="3d707-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3d707-122">\<configuration></span><span class="sxs-lookup"><span data-stu-id="3d707-122">\<configuration></span></span>|<span data-ttu-id="3d707-123">.NET 構成ファイルのすべての構成要素のルート要素。</span><span class="sxs-lookup"><span data-stu-id="3d707-123">The root element for all configuration elements in a .NET configuration file.</span></span>|
