---
title: ワークフローの System.servicemodel> を <する
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a8eb2bf-f925-40e1-ba5c-a49b1d3a3ac6
ms.openlocfilehash: c18cc4886d3e7a19b750a005b27d00a841b9fc5d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194857"
---
# <a name="systemservicemodel-of-workflow"></a><span data-ttu-id="624a3-102">\<system.serviceModel> ワークフローの</span><span class="sxs-lookup"><span data-stu-id="624a3-102">\<system.serviceModel> of workflow</span></span>

<span data-ttu-id="624a3-103">この構成セクションには、すべてのワークフロー構成要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="624a3-103">This configuration section contains all the workflow configuration elements.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.ServiceModel>**  
  
## <a name="syntax"></a><span data-ttu-id="624a3-104">構文</span><span class="sxs-lookup"><span data-stu-id="624a3-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="624a3-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="624a3-105">Attributes and Elements</span></span>  

 <span data-ttu-id="624a3-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="624a3-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="624a3-107">属性</span><span class="sxs-lookup"><span data-stu-id="624a3-107">Attributes</span></span>  

 <span data-ttu-id="624a3-108">None</span><span class="sxs-lookup"><span data-stu-id="624a3-108">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="624a3-109">子要素</span><span class="sxs-lookup"><span data-stu-id="624a3-109">Child Elements</span></span>  
  
|<span data-ttu-id="624a3-110">要素</span><span class="sxs-lookup"><span data-stu-id="624a3-110">Element</span></span>|<span data-ttu-id="624a3-111">説明</span><span class="sxs-lookup"><span data-stu-id="624a3-111">Description</span></span>|  
|-------------|-----------------|  
|[\<behaviors>](behaviors-of-workflow.md)|<span data-ttu-id="624a3-112">このセクションでは、 **Servicebehaviors** コレクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="624a3-112">This section defines the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="624a3-113">各コレクション内の要素は、サービスによって使用されるそれぞれの動作要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="624a3-113">Each element in the collection defines behavior elements consumed by services.</span></span> <span data-ttu-id="624a3-114">各動作要素は、一意の **name** 属性によって識別されます。</span><span class="sxs-lookup"><span data-stu-id="624a3-114">Each behavior element is identified by its unique **name** attribute.</span></span>|  
|[\<tracking>](tracking.md)|<span data-ttu-id="624a3-115">ワークフロー サービスの追跡設定を定義する構成セクションを表します。</span><span class="sxs-lookup"><span data-stu-id="624a3-115">Represents a configuration section for defining tracking settings for a workflow service.</span></span><br /><br /> <span data-ttu-id="624a3-116">ワークフロー追跡とその構成の詳細については、「ワークフローの [追跡とトレース](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) 」と「ワークフロー [の追跡の構成](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="624a3-116">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="624a3-117">親要素</span><span class="sxs-lookup"><span data-stu-id="624a3-117">Parent Elements</span></span>  
  
|<span data-ttu-id="624a3-118">要素</span><span class="sxs-lookup"><span data-stu-id="624a3-118">Element</span></span>|<span data-ttu-id="624a3-119">説明</span><span class="sxs-lookup"><span data-stu-id="624a3-119">Description</span></span>|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|<span data-ttu-id="624a3-120">.NET 構成ファイルのすべての構成要素のルート要素。</span><span class="sxs-lookup"><span data-stu-id="624a3-120">The root element for all configuration elements in a .NET configuration file.</span></span>|
