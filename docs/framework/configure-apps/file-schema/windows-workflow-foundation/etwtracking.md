---
title: <etwTracking>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: cb45c82e-6ea1-4c4d-924c-118a25ae1f35
ms.openlocfilehash: d562bd4e3d46a1bdf41fc4065fee926850a49aa1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152172"
---
# <a name="etwtracking"></a><span data-ttu-id="59796-101">\<追跡></span><span class="sxs-lookup"><span data-stu-id="59796-101">\<etwTracking></span></span>
<span data-ttu-id="59796-102"><xref:System.Activities.Tracking.EtwTrackingParticipant> を使用して、サービスで ETW 追跡を利用するためのサービス動作。</span><span class="sxs-lookup"><span data-stu-id="59796-102">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>  
  
<span data-ttu-id="59796-103">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="59796-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="59796-104">&nbsp;&nbsp;[**\<システム。サービスモデル>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="59796-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="59796-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<動作>**](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="59796-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="59796-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<サービス動作>**](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="59796-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="59796-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<動作>**](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="59796-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="59796-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>追跡**</span><span class="sxs-lookup"><span data-stu-id="59796-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<etwTracking>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59796-109">構文</span><span class="sxs-lookup"><span data-stu-id="59796-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <etwTracking profileName="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59796-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="59796-110">Attributes and Elements</span></span>  
 <span data-ttu-id="59796-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="59796-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59796-112">属性</span><span class="sxs-lookup"><span data-stu-id="59796-112">Attributes</span></span>  
  
|<span data-ttu-id="59796-113">属性</span><span class="sxs-lookup"><span data-stu-id="59796-113">Attribute</span></span>|<span data-ttu-id="59796-114">説明</span><span class="sxs-lookup"><span data-stu-id="59796-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="59796-115">profileName</span><span class="sxs-lookup"><span data-stu-id="59796-115">profileName</span></span>|<span data-ttu-id="59796-116">この動作に関連付けられた追跡プロファイルの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="59796-116">A string that specifies the name of the tracking profile associated with this behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="59796-117">子要素</span><span class="sxs-lookup"><span data-stu-id="59796-117">Child Elements</span></span>  
 <span data-ttu-id="59796-118">[なし] :</span><span class="sxs-lookup"><span data-stu-id="59796-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="59796-119">親要素</span><span class="sxs-lookup"><span data-stu-id="59796-119">Parent Elements</span></span>  
  
|<span data-ttu-id="59796-120">要素</span><span class="sxs-lookup"><span data-stu-id="59796-120">Element</span></span>|<span data-ttu-id="59796-121">説明</span><span class="sxs-lookup"><span data-stu-id="59796-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="59796-122">\<サービスの\<動作>></span><span class="sxs-lookup"><span data-stu-id="59796-122">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="59796-123">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="59796-123">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59796-124">解説</span><span class="sxs-lookup"><span data-stu-id="59796-124">Remarks</span></span>  
 <span data-ttu-id="59796-125">サービスの動作構成に追加すると、この構成要素により、ワークフロー サービスの追跡参加要素が構成されます。</span><span class="sxs-lookup"><span data-stu-id="59796-125">When added to the service’s behavior configuration, this configuration element configures a tracking participant on a workflow service.</span></span>  
  
 <span data-ttu-id="59796-126">追跡参加要素は、ワークフローから生成される追跡データを取得し、それを別のメディアに保存するために使用します。</span><span class="sxs-lookup"><span data-stu-id="59796-126">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="59796-127">同様に、追跡レコードの後処理はすべて、追跡参加要素内でも実行できます。</span><span class="sxs-lookup"><span data-stu-id="59796-127">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59796-128">例</span><span class="sxs-lookup"><span data-stu-id="59796-128">Example</span></span>  
 <span data-ttu-id="59796-129">次の構成例は、Web.config ファイルで構成されている標準の ETW 追跡参加要素を示します。</span><span class="sxs-lookup"><span data-stu-id="59796-129">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="59796-130">ETW 追跡参加要素が追跡レコードを ETW に書き込むために使用するプロバイダー ID は、**\<診断>** セクションで定義されます。</span><span class="sxs-lookup"><span data-stu-id="59796-130">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="59796-131">追跡参加要素には、その要素が定期受信した追跡レコードを指定するためのプロファイルが関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="59796-131">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="59796-132">これは、要素の追加の**profileName**属性**\<によって定義>。**</span><span class="sxs-lookup"><span data-stu-id="59796-132">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="59796-133">これらの定義が完了すると、追跡参加要素が**\<etwTracking>** サービス動作に追加されます。</span><span class="sxs-lookup"><span data-stu-id="59796-133">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="59796-134">これにより、選択した追跡参加要素がワークフロー インスタンスの拡張機能に追加され、追跡レコードの受信が開始されます。</span><span class="sxs-lookup"><span data-stu-id="59796-134">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
```xml  
<configuration>
  <system.web>
    <compilation targetFrameworkMoniker=".NETFramework,Version=v4.0"/>
  </system.web>
  <system.serviceModel>
    <diagnostics etwProviderId="52A3165D-4AD9-405C-B1E8-7D9A257EAC9F" />
    <tracking>
      <participants>
        <add name="EtwTrackingParticipant"
             type="System.Activities.Tracking.EtwTrackingParticipant, System.Activities, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
             profileName="HealthMonitoring_Tracking_Profile"/>
      </participants>
    </tracking>
    <behaviors>
      <serviceBehaviors>
        <behavior>
          <etwTracking profileName="Sample Tracking Profile"/>  
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="59796-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="59796-135">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="59796-136">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="59796-136">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="59796-137">参加者の追跡</span><span class="sxs-lookup"><span data-stu-id="59796-137">Tracking Participants</span></span>](../../../windows-workflow-foundation/tracking-participants.md)
