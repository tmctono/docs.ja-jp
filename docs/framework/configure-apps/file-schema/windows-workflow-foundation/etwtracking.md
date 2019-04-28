---
title: <etwTracking>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: cb45c82e-6ea1-4c4d-924c-118a25ae1f35
ms.openlocfilehash: e7614f158826e3522ac8e17d60c1ea65fefc8612
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790196"
---
# <a name="etwtracking"></a><span data-ttu-id="d759d-101">\<etwTracking ></span><span class="sxs-lookup"><span data-stu-id="d759d-101">\<etwTracking></span></span>
<span data-ttu-id="d759d-102">サービスを使用して ETW 追跡を利用できるサービス動作、<xref:System.Activities.Tracking.EtwTrackingParticipant>します。</span><span class="sxs-lookup"><span data-stu-id="d759d-102">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>  
  
<span data-ttu-id="d759d-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="d759d-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="d759d-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="d759d-104">\<behaviors></span></span>  
<span data-ttu-id="d759d-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="d759d-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="d759d-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="d759d-106">\<behavior></span></span>  
<span data-ttu-id="d759d-107">\<etwTracking ></span><span class="sxs-lookup"><span data-stu-id="d759d-107">\<etwTracking></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d759d-108">構文</span><span class="sxs-lookup"><span data-stu-id="d759d-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <etwTracking profileName="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d759d-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d759d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d759d-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d759d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d759d-111">属性</span><span class="sxs-lookup"><span data-stu-id="d759d-111">Attributes</span></span>  
  
|<span data-ttu-id="d759d-112">属性</span><span class="sxs-lookup"><span data-stu-id="d759d-112">Attribute</span></span>|<span data-ttu-id="d759d-113">説明</span><span class="sxs-lookup"><span data-stu-id="d759d-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d759d-114">profileName</span><span class="sxs-lookup"><span data-stu-id="d759d-114">profileName</span></span>|<span data-ttu-id="d759d-115">この動作に関連付けられた追跡プロファイルの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="d759d-115">A string that specifies the name of the tracking profile associated with this behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d759d-116">子要素</span><span class="sxs-lookup"><span data-stu-id="d759d-116">Child Elements</span></span>  
 <span data-ttu-id="d759d-117">なし。</span><span class="sxs-lookup"><span data-stu-id="d759d-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d759d-118">親要素</span><span class="sxs-lookup"><span data-stu-id="d759d-118">Parent Elements</span></span>  
  
|<span data-ttu-id="d759d-119">要素</span><span class="sxs-lookup"><span data-stu-id="d759d-119">Element</span></span>|<span data-ttu-id="d759d-120">説明</span><span class="sxs-lookup"><span data-stu-id="d759d-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d759d-121">\<動作 > の\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="d759d-121">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="d759d-122">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="d759d-122">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d759d-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="d759d-123">Remarks</span></span>  
 <span data-ttu-id="d759d-124">サービスの動作構成に追加すると、この構成要素により、ワークフロー サービスの追跡参加要素が構成されます。</span><span class="sxs-lookup"><span data-stu-id="d759d-124">When added to the service’s behavior configuration, this configuration element configures a tracking participant on a workflow service.</span></span>  
  
 <span data-ttu-id="d759d-125">追跡参加要素は、ワークフローから生成される追跡データを取得し、それを別のメディアに保存するために使用します。</span><span class="sxs-lookup"><span data-stu-id="d759d-125">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="d759d-126">同様に、追跡レコードの後処理はすべて、追跡参加要素内でも実行できます。</span><span class="sxs-lookup"><span data-stu-id="d759d-126">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d759d-127">例</span><span class="sxs-lookup"><span data-stu-id="d759d-127">Example</span></span>  
 <span data-ttu-id="d759d-128">次の構成例は、Web.config ファイルで構成されている標準の ETW 追跡参加要素を示します。</span><span class="sxs-lookup"><span data-stu-id="d759d-128">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="d759d-129">ETW 追跡参加要素が追跡レコードを ETW に書き込むために使用するプロバイダー Id が定義されている、 **\<診断 >** セクション。</span><span class="sxs-lookup"><span data-stu-id="d759d-129">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="d759d-130">追跡参加要素には、その要素が定期受信した追跡レコードを指定するためのプロファイルが関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="d759d-130">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="d759d-131">これは、 **profileName**の属性、 **\<追加 >** 要素。</span><span class="sxs-lookup"><span data-stu-id="d759d-131">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="d759d-132">これらが定義に追跡参加要素が追加、  **\<etwTracking >** サービス動作。</span><span class="sxs-lookup"><span data-stu-id="d759d-132">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="d759d-133">これにより、選択した追跡参加要素がワークフロー インスタンスの拡張機能に追加され、追跡レコードの受信が開始されます。</span><span class="sxs-lookup"><span data-stu-id="d759d-133">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d759d-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="d759d-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="d759d-135">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="d759d-135">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d759d-136">追跡参加要素</span><span class="sxs-lookup"><span data-stu-id="d759d-136">Tracking Participants</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md)
