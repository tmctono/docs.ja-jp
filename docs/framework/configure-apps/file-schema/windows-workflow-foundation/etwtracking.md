---
title: <etwTracking>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: cb45c82e-6ea1-4c4d-924c-118a25ae1f35
ms.openlocfilehash: e1048cf3a9f56e4177f3ffe2dcd561a1babadacd
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198770"
---
# \<etwTracking>

<span data-ttu-id="314c2-101"><xref:System.Activities.Tracking.EtwTrackingParticipant> を使用して、サービスで ETW 追跡を利用するためのサービス動作。</span><span class="sxs-lookup"><span data-stu-id="314c2-101">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<etwTracking>**  
  
## <a name="syntax"></a><span data-ttu-id="314c2-102">構文</span><span class="sxs-lookup"><span data-stu-id="314c2-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <etwTracking profileName="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="314c2-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="314c2-103">Attributes and Elements</span></span>  

 <span data-ttu-id="314c2-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="314c2-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="314c2-105">属性</span><span class="sxs-lookup"><span data-stu-id="314c2-105">Attributes</span></span>  
  
|<span data-ttu-id="314c2-106">属性</span><span class="sxs-lookup"><span data-stu-id="314c2-106">Attribute</span></span>|<span data-ttu-id="314c2-107">[説明]</span><span class="sxs-lookup"><span data-stu-id="314c2-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="314c2-108">profileName</span><span class="sxs-lookup"><span data-stu-id="314c2-108">profileName</span></span>|<span data-ttu-id="314c2-109">この動作に関連付けられた追跡プロファイルの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="314c2-109">A string that specifies the name of the tracking profile associated with this behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="314c2-110">子要素</span><span class="sxs-lookup"><span data-stu-id="314c2-110">Child Elements</span></span>  

 <span data-ttu-id="314c2-111">なし。</span><span class="sxs-lookup"><span data-stu-id="314c2-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="314c2-112">親要素</span><span class="sxs-lookup"><span data-stu-id="314c2-112">Parent Elements</span></span>  
  
|<span data-ttu-id="314c2-113">要素</span><span class="sxs-lookup"><span data-stu-id="314c2-113">Element</span></span>|<span data-ttu-id="314c2-114">説明</span><span class="sxs-lookup"><span data-stu-id="314c2-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="314c2-115">\<serviceBehaviors> の \<behavior></span><span class="sxs-lookup"><span data-stu-id="314c2-115">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="314c2-116">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="314c2-116">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="314c2-117">解説</span><span class="sxs-lookup"><span data-stu-id="314c2-117">Remarks</span></span>  

 <span data-ttu-id="314c2-118">サービスの動作構成に追加すると、この構成要素により、ワークフロー サービスの追跡参加要素が構成されます。</span><span class="sxs-lookup"><span data-stu-id="314c2-118">When added to the service’s behavior configuration, this configuration element configures a tracking participant on a workflow service.</span></span>  
  
 <span data-ttu-id="314c2-119">追跡参加要素は、ワークフローから生成される追跡データを取得し、それを別のメディアに保存するために使用します。</span><span class="sxs-lookup"><span data-stu-id="314c2-119">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="314c2-120">同様に、追跡レコードの後処理はすべて、追跡参加要素内でも実行できます。</span><span class="sxs-lookup"><span data-stu-id="314c2-120">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="314c2-121">例</span><span class="sxs-lookup"><span data-stu-id="314c2-121">Example</span></span>  

 <span data-ttu-id="314c2-122">次の構成例は、Web.config ファイルで構成されている標準の ETW 追跡参加要素を示します。</span><span class="sxs-lookup"><span data-stu-id="314c2-122">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="314c2-123">Etw 追跡参加要素が追跡レコードを ETW に書き込むために使用するプロバイダー Id は、セクションで定義され **\<diagnostics>** ます。</span><span class="sxs-lookup"><span data-stu-id="314c2-123">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="314c2-124">追跡参加要素には、その要素が定期受信した追跡レコードを指定するためのプロファイルが関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="314c2-124">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="314c2-125">これは、要素の **profileName** 属性によって定義され **\<add>** ます。</span><span class="sxs-lookup"><span data-stu-id="314c2-125">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="314c2-126">これらが定義されると、サービスの動作に追跡参加要素が追加され **\<etwTracking>** ます。</span><span class="sxs-lookup"><span data-stu-id="314c2-126">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="314c2-127">これにより、選択した追跡参加要素がワークフロー インスタンスの拡張機能に追加され、追跡レコードの受信が開始されます。</span><span class="sxs-lookup"><span data-stu-id="314c2-127">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="314c2-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="314c2-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="314c2-129">ワークフロー追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="314c2-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="314c2-130">追跡参加要素</span><span class="sxs-lookup"><span data-stu-id="314c2-130">Tracking Participants</span></span>](../../../windows-workflow-foundation/tracking-participants.md)
