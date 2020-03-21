---
title: ワークフローの>を<します。
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a8eb2bf-f925-40e1-ba5c-a49b1d3a3ac6
ms.openlocfilehash: 9aa2bf0fdfd6fe4528a3fda4d05b3ba8f23637d3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151950"
---
# <a name="systemservicemodel-of-workflow"></a><span data-ttu-id="09dba-102">\<ワークフローの></span><span class="sxs-lookup"><span data-stu-id="09dba-102">\<system.serviceModel> of workflow</span></span>
<span data-ttu-id="09dba-103">この構成セクションには、すべてのワークフロー構成要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="09dba-103">This configuration section contains all the workflow configuration elements.</span></span>  

<span data-ttu-id="09dba-104">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="09dba-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="09dba-105">&nbsp;&nbsp;**\<システム。サービスモデル>**</span><span class="sxs-lookup"><span data-stu-id="09dba-105">&nbsp;&nbsp;**\<system.ServiceModel>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09dba-106">構文</span><span class="sxs-lookup"><span data-stu-id="09dba-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="09dba-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="09dba-107">Attributes and Elements</span></span>  
 <span data-ttu-id="09dba-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="09dba-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="09dba-109">属性</span><span class="sxs-lookup"><span data-stu-id="09dba-109">Attributes</span></span>  
 <span data-ttu-id="09dba-110">なし</span><span class="sxs-lookup"><span data-stu-id="09dba-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="09dba-111">子要素</span><span class="sxs-lookup"><span data-stu-id="09dba-111">Child Elements</span></span>  
  
|<span data-ttu-id="09dba-112">要素</span><span class="sxs-lookup"><span data-stu-id="09dba-112">Element</span></span>|<span data-ttu-id="09dba-113">説明</span><span class="sxs-lookup"><span data-stu-id="09dba-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="09dba-114">\<動作></span><span class="sxs-lookup"><span data-stu-id="09dba-114">\<behaviors></span></span>](behaviors-of-workflow.md)|<span data-ttu-id="09dba-115">このセクションでは、**サービスBehaviorsコレクションを**定義します。</span><span class="sxs-lookup"><span data-stu-id="09dba-115">This section defines the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="09dba-116">各コレクション内の要素は、サービスによって使用されるそれぞれの動作要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="09dba-116">Each element in the collection defines behavior elements consumed by services.</span></span> <span data-ttu-id="09dba-117">各動作要素は、その一意の**name**属性によって識別されます。</span><span class="sxs-lookup"><span data-stu-id="09dba-117">Each behavior element is identified by its unique **name** attribute.</span></span>|  
|[<span data-ttu-id="09dba-118">\<追跡></span><span class="sxs-lookup"><span data-stu-id="09dba-118">\<tracking></span></span>](tracking.md)|<span data-ttu-id="09dba-119">ワークフロー サービスの追跡設定を定義する構成セクションを表します。</span><span class="sxs-lookup"><span data-stu-id="09dba-119">Represents a configuration section for defining tracking settings for a workflow service.</span></span><br /><br /> <span data-ttu-id="09dba-120">ワークフロー追跡とその構成の詳細については、「[ワークフローの追跡と追跡と](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)[追跡の構成](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09dba-120">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="09dba-121">親要素</span><span class="sxs-lookup"><span data-stu-id="09dba-121">Parent Elements</span></span>  
  
|<span data-ttu-id="09dba-122">要素</span><span class="sxs-lookup"><span data-stu-id="09dba-122">Element</span></span>|<span data-ttu-id="09dba-123">説明</span><span class="sxs-lookup"><span data-stu-id="09dba-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="09dba-124">\<構成></span><span class="sxs-lookup"><span data-stu-id="09dba-124">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="09dba-125">.NET 構成ファイルのすべての構成要素のルート要素。</span><span class="sxs-lookup"><span data-stu-id="09dba-125">The root element for all configuration elements in a .NET configuration file.</span></span>|
