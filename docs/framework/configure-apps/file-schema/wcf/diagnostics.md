---
title: <diagnostics>
ms.date: 03/30/2017
ms.assetid: 0c2f95c4-cc12-4fb5-a70c-7fc6fa95db58
ms.openlocfilehash: 170cae5b328c86073c1d8e7710bb19e98ab5688c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925873"
---
# <a name="diagnostics"></a><span data-ttu-id="d7866-101">\<診断 ></span><span class="sxs-lookup"><span data-stu-id="d7866-101">\<diagnostics></span></span>
<span data-ttu-id="d7866-102">`diagnostics` 要素は、ランタイムの検査と管理を行う管理者が使用できる設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="d7866-102">The `diagnostics` element defines settings that can be used by an administrator for run-time inspection and control.</span></span>  
  
 <span data-ttu-id="d7866-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="d7866-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="d7866-104">\<診断 ></span><span class="sxs-lookup"><span data-stu-id="d7866-104">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7866-105">構文</span><span class="sxs-lookup"><span data-stu-id="d7866-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics etwProviderId="String"
               performanceCounters="Off/ServiceOnly/All/Default"
               wmiProviderEnabled="Boolean">
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
    <messageLogging logEntireMessage="Boolean"
                    logMalformedMessages="Boolean"
                    logMessagesAtServiceLevel="Boolean"
                    logMessagesAtTransportLevel="Boolean"
                    maxMessagesToLog="Integer"
                    maxSizeOfMessageToLog="Integer">
      <filters>
        <clear />
      </filters>
    </messageLogging>
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d7866-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d7866-106">Attributes and Elements</span></span>  
 <span data-ttu-id="d7866-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d7866-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d7866-108">属性</span><span class="sxs-lookup"><span data-stu-id="d7866-108">Attributes</span></span>  
  
|<span data-ttu-id="d7866-109">属性</span><span class="sxs-lookup"><span data-stu-id="d7866-109">Attribute</span></span>|<span data-ttu-id="d7866-110">説明</span><span class="sxs-lookup"><span data-stu-id="d7866-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d7866-111">etwProviderId</span><span class="sxs-lookup"><span data-stu-id="d7866-111">etwProviderId</span></span>|<span data-ttu-id="d7866-112">イベントを ETW セッションに書き込むイベント追跡プロバイダーの識別子を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="d7866-112">A string that specifies the identifier for the Event-Tracing provider, which writes events to ETW sessions.</span></span>|  
|<span data-ttu-id="d7866-113">performanceCounters</span><span class="sxs-lookup"><span data-stu-id="d7866-113">performanceCounters</span></span>|<span data-ttu-id="d7866-114">アセンブリのパフォーマンス カウンターが有効であるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d7866-114">Specifies whether performance counters for the assembly are enabled.</span></span> <span data-ttu-id="d7866-115">有効な値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d7866-115">Valid values are</span></span><br /><br /> <span data-ttu-id="d7866-116">オートパフォーマンス カウンターは無効です。</span><span class="sxs-lookup"><span data-stu-id="d7866-116">-   Off: Performance counters are disabled.</span></span><br /><span data-ttu-id="d7866-117">ServiceOnlyこのサービスに関連するパフォーマンス カウンターだけが有効です。</span><span class="sxs-lookup"><span data-stu-id="d7866-117">-   ServiceOnly: Only performance counters relevant to this service is enabled.</span></span><br /><span data-ttu-id="d7866-118">なパフォーマンス カウンターは実行時に表示できます。</span><span class="sxs-lookup"><span data-stu-id="d7866-118">-   All: Performance counters can be viewed at runtime.</span></span><br /><span data-ttu-id="d7866-119">標準単一のパフォーマンス カウンター インスタンス _WCF_Admin が作成されます。</span><span class="sxs-lookup"><span data-stu-id="d7866-119">-   Default: A single performance counter instance _WCF_Admin is created.</span></span> <span data-ttu-id="d7866-120">このインスタンスは、インフラストラクチャで使用される SQM データのコレクションを有効にするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d7866-120">This instance is used to enable the collection of SQM data for used by the infrastructure.</span></span> <span data-ttu-id="d7866-121">このインスタンスのカウンター値は更新されず、0 のままになります。</span><span class="sxs-lookup"><span data-stu-id="d7866-121">None of the counter values for this instance are updated and therefore will remain at zero.</span></span> <span data-ttu-id="d7866-122">WCF の構成が存在しない場合は、これが既定値になります。</span><span class="sxs-lookup"><span data-stu-id="d7866-122">This is the default value if no configuration is present for WCF.</span></span>|  
|<span data-ttu-id="d7866-123">wmiProviderEnabled</span><span class="sxs-lookup"><span data-stu-id="d7866-123">wmiProviderEnabled</span></span>|<span data-ttu-id="d7866-124">アセンブリの WMI プロバイダーが有効であるかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="d7866-124">A Boolean value that specifies whether the WMI provider for the assembly is enabled.</span></span> <span data-ttu-id="d7866-125">ユーザーが Windows Communication Foundation (WCF) の検査および制御機能に対する実行時アクセス権を取得するには、WMI プロバイダーが必要です。</span><span class="sxs-lookup"><span data-stu-id="d7866-125">The WMI provider is required for user to gain run-time access to the inspection and control features of Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="d7866-126">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="d7866-126">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d7866-127">子要素</span><span class="sxs-lookup"><span data-stu-id="d7866-127">Child Elements</span></span>  
  
|<span data-ttu-id="d7866-128">要素</span><span class="sxs-lookup"><span data-stu-id="d7866-128">Element</span></span>|<span data-ttu-id="d7866-129">説明</span><span class="sxs-lookup"><span data-stu-id="d7866-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d7866-130">\<endToEndTracing ></span><span class="sxs-lookup"><span data-stu-id="d7866-130">\<endToEndTracing></span></span>](endtoendtracing.md)|<span data-ttu-id="d7866-131">サービス アプリケーションの実行中にエンドツーエンドのトレースのさまざまな側面を有効または無効にするための構成要素。</span><span class="sxs-lookup"><span data-stu-id="d7866-131">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>|  
|[<span data-ttu-id="d7866-132">\<messageLogging ></span><span class="sxs-lookup"><span data-stu-id="d7866-132">\<messageLogging></span></span>](messagelogging.md)|<span data-ttu-id="d7866-133">WCF メッセージ ログの設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="d7866-133">Describes the settings for WCF message logging.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d7866-134">親要素</span><span class="sxs-lookup"><span data-stu-id="d7866-134">Parent Elements</span></span>  
  
|<span data-ttu-id="d7866-135">要素</span><span class="sxs-lookup"><span data-stu-id="d7866-135">Element</span></span>|<span data-ttu-id="d7866-136">説明</span><span class="sxs-lookup"><span data-stu-id="d7866-136">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d7866-137">serviceModel</span><span class="sxs-lookup"><span data-stu-id="d7866-137">serviceModel</span></span>|<span data-ttu-id="d7866-138">すべての WCF 構成要素のルート要素です。</span><span class="sxs-lookup"><span data-stu-id="d7866-138">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7866-139">Remarks</span><span class="sxs-lookup"><span data-stu-id="d7866-139">Remarks</span></span>  
 <span data-ttu-id="d7866-140">`diagnostics` セクションは、アセンブリに配置されるすべてのサービスの診断設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="d7866-140">The `diagnostics` section defines the diagnostics settings for all services located in an assembly.</span></span> <span data-ttu-id="d7866-141">アセンブリ内のサービスが 1 つでない限り、サービス レベル別に診断設定を定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="d7866-141">It is not possible to define separate diagnostics settings at the service level unless there is only one service in the assembly.</span></span> <span data-ttu-id="d7866-142">属性は、セクションの要件に応じて設定されます。</span><span class="sxs-lookup"><span data-stu-id="d7866-142">Attributes are set according to the requirements of the section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7866-143">例</span><span class="sxs-lookup"><span data-stu-id="d7866-143">Example</span></span>  
  
```xml  
<diagnostics wmiProviderEnabled="false"
             performanceCounters="all">
  <messageLogging logEntireMessage="true"
                  logMalformedMessages="true"
                  logMessagesAtServiceLevel="true"
                  logMessagesAtTransportLevel="true"
                  maxMessagesToLog="42"
                  maxSizeOfMessageToLog="42">
    <filters>
      <clear />
    </filters>
  </messageLogging>
</diagnostics>
```  
  
## <a name="see-also"></a><span data-ttu-id="d7866-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="d7866-144">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
