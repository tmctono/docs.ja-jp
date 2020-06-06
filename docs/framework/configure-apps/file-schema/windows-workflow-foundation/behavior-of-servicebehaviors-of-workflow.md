---
title: <behavior><serviceBehaviors>ワークフローの
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a4b718a-1b40-4957-935a-f6122819ab3c
ms.openlocfilehash: 071cff8e9f6ec3fa0546a07d19160869d8b43f60
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152321"
---
# <a name="behavior-of-servicebehaviors-of-workflow"></a><span data-ttu-id="0a73a-102">\<behavior>\<serviceBehaviors>ワークフローの</span><span class="sxs-lookup"><span data-stu-id="0a73a-102">\<behavior> of \<serviceBehaviors> of workflow</span></span>
<span data-ttu-id="0a73a-103">**Behavior**要素には、サービスの動作に関する設定のコレクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0a73a-103">The **behavior** element contains a collection of settings for the behavior of a service.</span></span> <span data-ttu-id="0a73a-104">各動作は、**名前**によってインデックスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="0a73a-104">Each behavior is indexed by its **name**.</span></span> <span data-ttu-id="0a73a-105">サービスは、要素の**設定**属性を使用して、この名前を使用して各動作にリンクでき [\<endpoint>](../wcf/endpoint-element.md) ます。</span><span class="sxs-lookup"><span data-stu-id="0a73a-105">Services can link to each behavior through this name using the **behaviorConfiguration** attribute of the [\<endpoint>](../wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="0a73a-106">これにより、設定を再定義することなく、エンドポイント間で共通の動作構成を共有できます。</span><span class="sxs-lookup"><span data-stu-id="0a73a-106">This allows endpoints to share common behavior configurations without redefining the settings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<behavior>**  
  
## <a name="syntax"></a><span data-ttu-id="0a73a-107">構文</span><span class="sxs-lookup"><span data-stu-id="0a73a-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0a73a-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="0a73a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0a73a-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="0a73a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0a73a-110">属性</span><span class="sxs-lookup"><span data-stu-id="0a73a-110">Attributes</span></span>  
  
|<span data-ttu-id="0a73a-111">属性</span><span class="sxs-lookup"><span data-stu-id="0a73a-111">Attribute</span></span>|<span data-ttu-id="0a73a-112">説明</span><span class="sxs-lookup"><span data-stu-id="0a73a-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0a73a-113">name</span><span class="sxs-lookup"><span data-stu-id="0a73a-113">name</span></span>|<span data-ttu-id="0a73a-114">動作の構成名を含む一意の文字列。</span><span class="sxs-lookup"><span data-stu-id="0a73a-114">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="0a73a-115">この値は、要素の識別文字列として機能するため、一意のユーザー定義の文字列である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a73a-115">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0a73a-116">子要素</span><span class="sxs-lookup"><span data-stu-id="0a73a-116">Child Elements</span></span>  
  
|<span data-ttu-id="0a73a-117">要素</span><span class="sxs-lookup"><span data-stu-id="0a73a-117">Element</span></span>|<span data-ttu-id="0a73a-118">Description</span><span class="sxs-lookup"><span data-stu-id="0a73a-118">Description</span></span>|  
|-------------|-----------------|  
|[\<bufferReceive>](bufferreceive.md)|<span data-ttu-id="0a73a-119">サービスが、バッファーされた受信処理を使用するためのサービス動作。これにより、ワークフロー サービスは、順番を無視したメッセージを処理できます。</span><span class="sxs-lookup"><span data-stu-id="0a73a-119">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>|  
|[\<routing>](../wcf/routing-of-servicebehavior.md)|<span data-ttu-id="0a73a-120"><xref:System.Activities.Tracking.EtwTrackingParticipant> を使用して、サービスで ETW 追跡を利用するためのサービス動作。</span><span class="sxs-lookup"><span data-stu-id="0a73a-120">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>|  
|[\<sendMessageChannelCache>](sendmessagechannelcache.md)|<span data-ttu-id="0a73a-121">キャッシュの共有レベルのカスタマイズや、チャネル ファクトリ キャッシュの設定を可能にするほか、Send メッセージング アクティビティを使用してサービス エンドポイントにメッセージを送信するワークフローのチャネル キャッシュの設定も可能にするサービス動作。</span><span class="sxs-lookup"><span data-stu-id="0a73a-121">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
|[\<sqlWorkflowInstanceStore>](sqlworkflowinstancestore.md)|<span data-ttu-id="0a73a-122">ワークフロー サービス インスタンスの状態情報の永続化を SQL Server 2005 または SQL Server 2008 データベースでサポートする <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> 機能を構成するためのサービス動作。</span><span class="sxs-lookup"><span data-stu-id="0a73a-122">A service behavior that allows you to configure the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> feature, which supports persisting state information for workflow service instances into an SQL Server 2005 or SQL Server 2008 database.</span></span>|  
|[\<workflowIdle>](workflowidle.md)|<span data-ttu-id="0a73a-123">アイドル状態のワークフロー インスタンスのアンロードおよび永続化のタイミングを制御するサービス動作。</span><span class="sxs-lookup"><span data-stu-id="0a73a-123">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>|  
|[\<workflowInstanceManagement>](workflowinstancemanagement.md)|<span data-ttu-id="0a73a-124">ワークフロー インスタンスの実行方法を制御する設定を指定するためのサービス動作。これには、永続する未処理の例外動作やアイドル状態の動作が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0a73a-124">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>|  
|[\<workflowUnhandledException>](workflowunhandledexception.md)|<span data-ttu-id="0a73a-125">ワークフロー サービス内で未処理の例外が発生した場合のアクションを指定するためのサービス動作。</span><span class="sxs-lookup"><span data-stu-id="0a73a-125">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0a73a-126">親要素</span><span class="sxs-lookup"><span data-stu-id="0a73a-126">Parent Elements</span></span>  
  
|<span data-ttu-id="0a73a-127">要素</span><span class="sxs-lookup"><span data-stu-id="0a73a-127">Element</span></span>|<span data-ttu-id="0a73a-128">Description</span><span class="sxs-lookup"><span data-stu-id="0a73a-128">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceBehaviors>](servicebehaviors-of-workflow.md)|<span data-ttu-id="0a73a-129">サービス動作要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="0a73a-129">A collection of service behavior elements.</span></span>|
