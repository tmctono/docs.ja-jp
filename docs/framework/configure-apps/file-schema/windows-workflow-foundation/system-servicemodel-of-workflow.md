---
title: ワークフローの <system.serviceModel>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a8eb2bf-f925-40e1-ba5c-a49b1d3a3ac6
ms.openlocfilehash: faa8154c4d7ac5c6aa2f9f1707cf8f0d39eefad5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947360"
---
# <a name="systemservicemodel-of-workflow"></a><span data-ttu-id="d8576-102">\<ワークフローの System.servicemodel ></span><span class="sxs-lookup"><span data-stu-id="d8576-102">\<system.serviceModel> of workflow</span></span>
<span data-ttu-id="d8576-103">この構成セクションには、すべてのワークフロー構成要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d8576-103">This configuration section contains all the workflow configuration elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8576-104">構文</span><span class="sxs-lookup"><span data-stu-id="d8576-104">Syntax</span></span>  
  
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
          hostLockRenewalPeriod="TimeSpan"  
          instanceCompletionAction="DeleteNothing/DeleteAll"  
          instanceEncodingAction="None/GZip"  
          instanceLockedExceptionAction="NoRetry/BasicRetry/AggressiveRetry"  
          runnableInstancesDetectionPeriod="TimeSpan" />  
      <workflowIdle timeToPersist="TimeSpan"  
          timeToUnload="TimeSpan" />  
      <workflowUnhandledExceptionAction="Abandon/AbandonAndSuspend/Cancel/Terminate" />  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d8576-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d8576-105">Attributes and Elements</span></span>  
 <span data-ttu-id="d8576-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d8576-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d8576-107">属性</span><span class="sxs-lookup"><span data-stu-id="d8576-107">Attributes</span></span>  
 <span data-ttu-id="d8576-108">なし</span><span class="sxs-lookup"><span data-stu-id="d8576-108">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d8576-109">子要素</span><span class="sxs-lookup"><span data-stu-id="d8576-109">Child Elements</span></span>  
  
|<span data-ttu-id="d8576-110">要素</span><span class="sxs-lookup"><span data-stu-id="d8576-110">Element</span></span>|<span data-ttu-id="d8576-111">説明</span><span class="sxs-lookup"><span data-stu-id="d8576-111">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d8576-112">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="d8576-112">\<behaviors></span></span>](behaviors-of-workflow.md)|<span data-ttu-id="d8576-113">このセクションでは、 **Servicebehaviors**コレクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="d8576-113">This section defines the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="d8576-114">各コレクション内の要素は、サービスによって使用されるそれぞれの動作要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="d8576-114">Each element in the collection defines behavior elements consumed by services.</span></span> <span data-ttu-id="d8576-115">各動作要素は、一意の**name**属性によって識別されます。</span><span class="sxs-lookup"><span data-stu-id="d8576-115">Each behavior element is identified by its unique **name** attribute.</span></span>|  
|[<span data-ttu-id="d8576-116">\<tracking></span><span class="sxs-lookup"><span data-stu-id="d8576-116">\<tracking></span></span>](tracking.md)|<span data-ttu-id="d8576-117">ワークフロー サービスの追跡設定を定義する構成セクションを表します。</span><span class="sxs-lookup"><span data-stu-id="d8576-117">Represents a configuration section for defining tracking settings for a workflow service.</span></span><br /><br /> <span data-ttu-id="d8576-118">ワークフロー追跡とその構成の詳細については、「ワークフローの[追跡とトレース](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)」と「ワークフロー[の追跡の構成](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8576-118">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d8576-119">親要素</span><span class="sxs-lookup"><span data-stu-id="d8576-119">Parent Elements</span></span>  
  
|<span data-ttu-id="d8576-120">要素</span><span class="sxs-lookup"><span data-stu-id="d8576-120">Element</span></span>|<span data-ttu-id="d8576-121">説明</span><span class="sxs-lookup"><span data-stu-id="d8576-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d8576-122">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d8576-122">\<configuration></span></span>|<span data-ttu-id="d8576-123">.NET 構成ファイルのすべての構成要素のルート要素。</span><span class="sxs-lookup"><span data-stu-id="d8576-123">The root element for all configuration elements in a .NET configuration file.</span></span>|
