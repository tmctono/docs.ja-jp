---
title: <participants>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 560dd0bb-f9fb-423c-8857-2101a3654b06
ms.openlocfilehash: ffc16f78b266b69e80023f177f10ad6f367b5623
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61794473"
---
# <a name="participants"></a><span data-ttu-id="e4176-101">\<参加者 ></span><span class="sxs-lookup"><span data-stu-id="e4176-101">\<participants></span></span>
<span data-ttu-id="e4176-102">ランタイムから直接出力される追跡レコードをリッスンし、追跡レコードの構成方法に従って処理を行う追跡参加要素の一覧を構成します。</span><span class="sxs-lookup"><span data-stu-id="e4176-102">Configure a list of tracking participants that listen to the tracking records being emitted from the runtime directly and process them in whatever way they are configured.</span></span> <span data-ttu-id="e4176-103">これには、特定の出力 (ファイル、コンソール、ETW など) への書き込み、レコードの処理や集計、またはその他の必要な組み合わせが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e4176-103">This includes writing to a specific output (e.g., file, Console, ETW), processing/aggregating the records, or any other combination that might be required.</span></span>  
  
 <span data-ttu-id="e4176-104">ワークフロー追跡と追跡参加要素の詳細については、次を参照してください。[ワークフロー追跡とトレース](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)と[追跡参加要素](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md)します。</span><span class="sxs-lookup"><span data-stu-id="e4176-104">For more information in workflow tracking and tracking participants, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Participants](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md).</span></span>  
  
<span data-ttu-id="e4176-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e4176-105">\<system.serviceModel></span></span>  
<span data-ttu-id="e4176-106">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="e4176-106">\<tracking></span></span>  
<span data-ttu-id="e4176-107">\<参加者 ></span><span class="sxs-lookup"><span data-stu-id="e4176-107">\<participants></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4176-108">構文</span><span class="sxs-lookup"><span data-stu-id="e4176-108">Syntax</span></span>  
  
```xml
<tracking>
  <participants>
    <add name="String" 
         profileName="String" 
         type="String" />
  </participants>
</tracking>   
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e4176-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e4176-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e4176-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e4176-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e4176-111">属性</span><span class="sxs-lookup"><span data-stu-id="e4176-111">Attributes</span></span>  
 <span data-ttu-id="e4176-112">なし。</span><span class="sxs-lookup"><span data-stu-id="e4176-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e4176-113">子要素</span><span class="sxs-lookup"><span data-stu-id="e4176-113">Child Elements</span></span>  
  
|<span data-ttu-id="e4176-114">要素</span><span class="sxs-lookup"><span data-stu-id="e4176-114">Element</span></span>|<span data-ttu-id="e4176-115">説明</span><span class="sxs-lookup"><span data-stu-id="e4176-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e4176-116">\<add></span><span class="sxs-lookup"><span data-stu-id="e4176-116">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/add-of-participants.md)|<span data-ttu-id="e4176-117">追跡参加要素を処理するための設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e4176-117">Contains settings for a tracking participant.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e4176-118">親要素</span><span class="sxs-lookup"><span data-stu-id="e4176-118">Parent Elements</span></span>  
  
|<span data-ttu-id="e4176-119">要素</span><span class="sxs-lookup"><span data-stu-id="e4176-119">Element</span></span>|<span data-ttu-id="e4176-120">説明</span><span class="sxs-lookup"><span data-stu-id="e4176-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e4176-121">\<tracking></span><span class="sxs-lookup"><span data-stu-id="e4176-121">\<tracking></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/tracking.md)|<span data-ttu-id="e4176-122">ワークフロー サービスの追跡設定を定義する構成セクションを表します。</span><span class="sxs-lookup"><span data-stu-id="e4176-122">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4176-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="e4176-123">Remarks</span></span>  
 <span data-ttu-id="e4176-124">追跡参加要素は、ワークフローから生成される追跡データを取得し、それを別のメディアに保存するために使用します。</span><span class="sxs-lookup"><span data-stu-id="e4176-124">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="e4176-125">同様に、追跡レコードの後処理はすべて、追跡参加要素内でも実行できます。</span><span class="sxs-lookup"><span data-stu-id="e4176-125">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
 <span data-ttu-id="e4176-126">複数の追跡参加要素が追跡イベントを同時に使用することができます。</span><span class="sxs-lookup"><span data-stu-id="e4176-126">Multiple tracking participants can consume the tracking events simultaneously.</span></span> <span data-ttu-id="e4176-127">各追跡参加要素は、それぞれ別の追跡プロファイルと関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="e4176-127">Each tracking participant can be associated with a different tracking profile.</span></span>  
  
 <span data-ttu-id="e4176-128">追跡レコードを ETW セッションに書き込む、標準の追跡参加要素が用意されています。</span><span class="sxs-lookup"><span data-stu-id="e4176-128">A standard tracking participant is provided which writes the tracking records to an ETW session.</span></span> <span data-ttu-id="e4176-129">参加要素は、追跡固有の動作を構成ファイルに追加することによって、ワークフロー サービスで構成されます。</span><span class="sxs-lookup"><span data-stu-id="e4176-129">The participant is configured on a workflow service by adding a tracking-specific behavior in a configuration file.</span></span> <span data-ttu-id="e4176-130">ETW 追跡参加要素を有効にすると、追跡レコードをイベント ビューアーで表示できます。</span><span class="sxs-lookup"><span data-stu-id="e4176-130">Enabling an ETW tracking participant allows tracking records to be viewed in the event viewer.</span></span> <span data-ttu-id="e4176-131">これで要件が満たされない場合は、カスタムの追跡参加要素を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="e4176-131">If that does not meet your requirements, you can also write a custom tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4176-132">例</span><span class="sxs-lookup"><span data-stu-id="e4176-132">Example</span></span>  
 <span data-ttu-id="e4176-133">次の構成例は、Web.config ファイルで構成されている標準の ETW 追跡参加要素を示します。</span><span class="sxs-lookup"><span data-stu-id="e4176-133">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="e4176-134">ETW 追跡参加要素が追跡レコードを ETW に書き込むために使用するプロバイダー Id が定義されている、 **\<診断 >** セクション。</span><span class="sxs-lookup"><span data-stu-id="e4176-134">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="e4176-135">追跡参加要素には、その要素が定期受信した追跡レコードを指定するためのプロファイルが関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="e4176-135">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="e4176-136">これは、 **profileName**の属性、 **\<追加 >** 要素。</span><span class="sxs-lookup"><span data-stu-id="e4176-136">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="e4176-137">これらが定義に追跡参加要素が追加、  **\<etwTracking >** サービス動作。</span><span class="sxs-lookup"><span data-stu-id="e4176-137">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="e4176-138">これにより、選択した追跡参加要素がワークフロー インスタンスの拡張機能に追加され、追跡レコードの受信が開始されます。</span><span class="sxs-lookup"><span data-stu-id="e4176-138">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e4176-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="e4176-139">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>
- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="e4176-140">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="e4176-140">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="e4176-141">追跡参加要素</span><span class="sxs-lookup"><span data-stu-id="e4176-141">Tracking Participants</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md)
