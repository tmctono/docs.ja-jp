---
title: <participants>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 560dd0bb-f9fb-423c-8857-2101a3654b06
ms.openlocfilehash: f04a5ee3940986cabc08895452c12ebcfd631694
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947570"
---
# <a name="participants"></a><span data-ttu-id="fd7b6-101">\<参加者 ></span><span class="sxs-lookup"><span data-stu-id="fd7b6-101">\<participants></span></span>
<span data-ttu-id="fd7b6-102">ランタイムから直接出力される追跡レコードをリッスンし、追跡レコードの構成方法に従って処理を行う追跡参加要素の一覧を構成します。</span><span class="sxs-lookup"><span data-stu-id="fd7b6-102">Configure a list of tracking participants that listen to the tracking records being emitted from the runtime directly and process them in whatever way they are configured.</span></span> <span data-ttu-id="fd7b6-103">これには、特定の出力 (ファイル、コンソール、ETW など) への書き込み、レコードの処理や集計、またはその他の必要な組み合わせが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fd7b6-103">This includes writing to a specific output (e.g., file, Console, ETW), processing/aggregating the records, or any other combination that might be required.</span></span>  
  
 <span data-ttu-id="fd7b6-104">ワークフロー追跡と追跡参加要素の詳細については、「[ワークフローの追跡とトレース](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)」と「[追跡参加要素](../../../windows-workflow-foundation/tracking-participants.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd7b6-104">For more information in workflow tracking and tracking participants, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Participants](../../../windows-workflow-foundation/tracking-participants.md).</span></span>  
  
<span data-ttu-id="fd7b6-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="fd7b6-105">\<system.serviceModel></span></span>  
<span data-ttu-id="fd7b6-106">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="fd7b6-106">\<tracking></span></span>  
<span data-ttu-id="fd7b6-107">\<参加者 ></span><span class="sxs-lookup"><span data-stu-id="fd7b6-107">\<participants></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd7b6-108">構文</span><span class="sxs-lookup"><span data-stu-id="fd7b6-108">Syntax</span></span>  
  
```xml
<tracking>
  <participants>
    <add name="String" 
         profileName="String" 
         type="String" />
  </participants>
</tracking>   
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fd7b6-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="fd7b6-109">Attributes and Elements</span></span>  
 <span data-ttu-id="fd7b6-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="fd7b6-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fd7b6-111">属性</span><span class="sxs-lookup"><span data-stu-id="fd7b6-111">Attributes</span></span>  
 <span data-ttu-id="fd7b6-112">なし。</span><span class="sxs-lookup"><span data-stu-id="fd7b6-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fd7b6-113">子要素</span><span class="sxs-lookup"><span data-stu-id="fd7b6-113">Child Elements</span></span>  
  
|<span data-ttu-id="fd7b6-114">要素</span><span class="sxs-lookup"><span data-stu-id="fd7b6-114">Element</span></span>|<span data-ttu-id="fd7b6-115">説明</span><span class="sxs-lookup"><span data-stu-id="fd7b6-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fd7b6-116">\<add></span><span class="sxs-lookup"><span data-stu-id="fd7b6-116">\<add></span></span>](add-of-participants.md)|<span data-ttu-id="fd7b6-117">追跡参加要素を処理するための設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="fd7b6-117">Contains settings for a tracking participant.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fd7b6-118">親要素</span><span class="sxs-lookup"><span data-stu-id="fd7b6-118">Parent Elements</span></span>  
  
|<span data-ttu-id="fd7b6-119">要素</span><span class="sxs-lookup"><span data-stu-id="fd7b6-119">Element</span></span>|<span data-ttu-id="fd7b6-120">説明</span><span class="sxs-lookup"><span data-stu-id="fd7b6-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fd7b6-121">\<tracking></span><span class="sxs-lookup"><span data-stu-id="fd7b6-121">\<tracking></span></span>](tracking.md)|<span data-ttu-id="fd7b6-122">ワークフロー サービスの追跡設定を定義する構成セクションを表します。</span><span class="sxs-lookup"><span data-stu-id="fd7b6-122">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd7b6-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="fd7b6-123">Remarks</span></span>  
 <span data-ttu-id="fd7b6-124">追跡参加要素は、ワークフローから生成される追跡データを取得し、それを別のメディアに保存するために使用します。</span><span class="sxs-lookup"><span data-stu-id="fd7b6-124">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="fd7b6-125">同様に、追跡レコードの後処理はすべて、追跡参加要素内でも実行できます。</span><span class="sxs-lookup"><span data-stu-id="fd7b6-125">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
 <span data-ttu-id="fd7b6-126">複数の追跡参加要素が追跡イベントを同時に使用することができます。</span><span class="sxs-lookup"><span data-stu-id="fd7b6-126">Multiple tracking participants can consume the tracking events simultaneously.</span></span> <span data-ttu-id="fd7b6-127">各追跡参加要素は、それぞれ別の追跡プロファイルと関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="fd7b6-127">Each tracking participant can be associated with a different tracking profile.</span></span>  
  
 <span data-ttu-id="fd7b6-128">追跡レコードを ETW セッションに書き込む、標準の追跡参加要素が用意されています。</span><span class="sxs-lookup"><span data-stu-id="fd7b6-128">A standard tracking participant is provided which writes the tracking records to an ETW session.</span></span> <span data-ttu-id="fd7b6-129">参加要素は、追跡固有の動作を構成ファイルに追加することによって、ワークフロー サービスで構成されます。</span><span class="sxs-lookup"><span data-stu-id="fd7b6-129">The participant is configured on a workflow service by adding a tracking-specific behavior in a configuration file.</span></span> <span data-ttu-id="fd7b6-130">ETW 追跡参加要素を有効にすると、追跡レコードをイベント ビューアーで表示できます。</span><span class="sxs-lookup"><span data-stu-id="fd7b6-130">Enabling an ETW tracking participant allows tracking records to be viewed in the event viewer.</span></span> <span data-ttu-id="fd7b6-131">これで要件が満たされない場合は、カスタムの追跡参加要素を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="fd7b6-131">If that does not meet your requirements, you can also write a custom tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd7b6-132">例</span><span class="sxs-lookup"><span data-stu-id="fd7b6-132">Example</span></span>  
 <span data-ttu-id="fd7b6-133">次の構成例は、Web.config ファイルで構成されている標準の ETW 追跡参加要素を示します。</span><span class="sxs-lookup"><span data-stu-id="fd7b6-133">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="fd7b6-134">Etw 追跡参加要素が追跡レコードを etw に書き込むために使用するプロバイダー Id は、[  **\<診断 >** ] セクションで定義されます。</span><span class="sxs-lookup"><span data-stu-id="fd7b6-134">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="fd7b6-135">追跡参加要素には、その要素が定期受信した追跡レコードを指定するためのプロファイルが関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="fd7b6-135">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="fd7b6-136">これは、  **\<add >** 要素の**profileName**属性によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="fd7b6-136">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="fd7b6-137">これらが定義されると、追跡参加要素は **\<etwtracking >** サービスの動作に追加されます。</span><span class="sxs-lookup"><span data-stu-id="fd7b6-137">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="fd7b6-138">これにより、選択した追跡参加要素がワークフロー インスタンスの拡張機能に追加され、追跡レコードの受信が開始されます。</span><span class="sxs-lookup"><span data-stu-id="fd7b6-138">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fd7b6-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="fd7b6-139">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>
- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="fd7b6-140">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="fd7b6-140">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="fd7b6-141">追跡参加要素</span><span class="sxs-lookup"><span data-stu-id="fd7b6-141">Tracking Participants</span></span>](../../../windows-workflow-foundation/tracking-participants.md)
