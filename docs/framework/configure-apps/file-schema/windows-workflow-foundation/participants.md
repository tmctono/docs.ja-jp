---
title: <participants>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 560dd0bb-f9fb-423c-8857-2101a3654b06
ms.openlocfilehash: 368b37f3ff10b660260ddd5735c70b8d72063e11
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398712"
---
# <a name="participants"></a><span data-ttu-id="e6296-101">\<参加者 ></span><span class="sxs-lookup"><span data-stu-id="e6296-101">\<participants></span></span>
<span data-ttu-id="e6296-102">ランタイムから直接出力される追跡レコードをリッスンし、追跡レコードの構成方法に従って処理を行う追跡参加要素の一覧を構成します。</span><span class="sxs-lookup"><span data-stu-id="e6296-102">Configure a list of tracking participants that listen to the tracking records being emitted from the runtime directly and process them in whatever way they are configured.</span></span> <span data-ttu-id="e6296-103">これには、特定の出力 (ファイル、コンソール、ETW など) への書き込み、レコードの処理や集計、またはその他の必要な組み合わせが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e6296-103">This includes writing to a specific output (e.g., file, Console, ETW), processing/aggregating the records, or any other combination that might be required.</span></span>  
  
 <span data-ttu-id="e6296-104">ワークフロー追跡と追跡参加要素の詳細については、「[ワークフローの追跡とトレース](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)」と「[追跡参加要素](../../../windows-workflow-foundation/tracking-participants.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6296-104">For more information in workflow tracking and tracking participants, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Participants](../../../windows-workflow-foundation/tracking-participants.md).</span></span>  
  
<span data-ttu-id="e6296-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e6296-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e6296-106">&nbsp;&nbsp;[ **\<system.ServiceModel >** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="e6296-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="e6296-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<追跡 >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="e6296-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="e6296-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<参加者 >**</span><span class="sxs-lookup"><span data-stu-id="e6296-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<participants>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6296-109">構文</span><span class="sxs-lookup"><span data-stu-id="e6296-109">Syntax</span></span>  
  
```xml
<tracking>
  <participants>
    <add name="String" 
         profileName="String" 
         type="String" />
  </participants>
</tracking>   
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e6296-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e6296-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e6296-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e6296-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e6296-112">属性</span><span class="sxs-lookup"><span data-stu-id="e6296-112">Attributes</span></span>  
 <span data-ttu-id="e6296-113">なし。</span><span class="sxs-lookup"><span data-stu-id="e6296-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e6296-114">子要素</span><span class="sxs-lookup"><span data-stu-id="e6296-114">Child Elements</span></span>  
  
|<span data-ttu-id="e6296-115">要素</span><span class="sxs-lookup"><span data-stu-id="e6296-115">Element</span></span>|<span data-ttu-id="e6296-116">説明</span><span class="sxs-lookup"><span data-stu-id="e6296-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e6296-117">\<add></span><span class="sxs-lookup"><span data-stu-id="e6296-117">\<add></span></span>](add-of-participants.md)|<span data-ttu-id="e6296-118">追跡参加要素を処理するための設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e6296-118">Contains settings for a tracking participant.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e6296-119">親要素</span><span class="sxs-lookup"><span data-stu-id="e6296-119">Parent Elements</span></span>  
  
|<span data-ttu-id="e6296-120">要素</span><span class="sxs-lookup"><span data-stu-id="e6296-120">Element</span></span>|<span data-ttu-id="e6296-121">説明</span><span class="sxs-lookup"><span data-stu-id="e6296-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e6296-122">\<tracking></span><span class="sxs-lookup"><span data-stu-id="e6296-122">\<tracking></span></span>](tracking.md)|<span data-ttu-id="e6296-123">ワークフロー サービスの追跡設定を定義する構成セクションを表します。</span><span class="sxs-lookup"><span data-stu-id="e6296-123">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6296-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="e6296-124">Remarks</span></span>  
 <span data-ttu-id="e6296-125">追跡参加要素は、ワークフローから生成される追跡データを取得し、それを別のメディアに保存するために使用します。</span><span class="sxs-lookup"><span data-stu-id="e6296-125">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="e6296-126">同様に、追跡レコードの後処理はすべて、追跡参加要素内でも実行できます。</span><span class="sxs-lookup"><span data-stu-id="e6296-126">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
 <span data-ttu-id="e6296-127">複数の追跡参加要素が追跡イベントを同時に使用することができます。</span><span class="sxs-lookup"><span data-stu-id="e6296-127">Multiple tracking participants can consume the tracking events simultaneously.</span></span> <span data-ttu-id="e6296-128">各追跡参加要素は、それぞれ別の追跡プロファイルと関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="e6296-128">Each tracking participant can be associated with a different tracking profile.</span></span>  
  
 <span data-ttu-id="e6296-129">追跡レコードを ETW セッションに書き込む、標準の追跡参加要素が用意されています。</span><span class="sxs-lookup"><span data-stu-id="e6296-129">A standard tracking participant is provided which writes the tracking records to an ETW session.</span></span> <span data-ttu-id="e6296-130">参加要素は、追跡固有の動作を構成ファイルに追加することによって、ワークフロー サービスで構成されます。</span><span class="sxs-lookup"><span data-stu-id="e6296-130">The participant is configured on a workflow service by adding a tracking-specific behavior in a configuration file.</span></span> <span data-ttu-id="e6296-131">ETW 追跡参加要素を有効にすると、追跡レコードをイベント ビューアーで表示できます。</span><span class="sxs-lookup"><span data-stu-id="e6296-131">Enabling an ETW tracking participant allows tracking records to be viewed in the event viewer.</span></span> <span data-ttu-id="e6296-132">これで要件が満たされない場合は、カスタムの追跡参加要素を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="e6296-132">If that does not meet your requirements, you can also write a custom tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6296-133">例</span><span class="sxs-lookup"><span data-stu-id="e6296-133">Example</span></span>  
 <span data-ttu-id="e6296-134">次の構成例は、Web.config ファイルで構成されている標準の ETW 追跡参加要素を示します。</span><span class="sxs-lookup"><span data-stu-id="e6296-134">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="e6296-135">Etw 追跡参加要素が追跡レコードを etw に書き込むために使用するプロバイダー Id は、[  **\<診断 >** ] セクションで定義されます。</span><span class="sxs-lookup"><span data-stu-id="e6296-135">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="e6296-136">追跡参加要素には、その要素が定期受信した追跡レコードを指定するためのプロファイルが関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="e6296-136">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="e6296-137">これは、  **\<add >** 要素の**profileName**属性によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="e6296-137">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="e6296-138">これらが定義されると、追跡参加要素は **\<etwtracking >** サービスの動作に追加されます。</span><span class="sxs-lookup"><span data-stu-id="e6296-138">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="e6296-139">これにより、選択した追跡参加要素がワークフロー インスタンスの拡張機能に追加され、追跡レコードの受信が開始されます。</span><span class="sxs-lookup"><span data-stu-id="e6296-139">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e6296-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="e6296-140">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>
- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="e6296-141">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="e6296-141">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="e6296-142">追跡参加要素</span><span class="sxs-lookup"><span data-stu-id="e6296-142">Tracking Participants</span></span>](../../../windows-workflow-foundation/tracking-participants.md)
