---
title: <diagnostics>
ms.date: 03/30/2017
ms.assetid: 0c2f95c4-cc12-4fb5-a70c-7fc6fa95db58
ms.openlocfilehash: 2749bc6c66d491a8a160d98b508fb43aa027b806
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398038"
---
# \<diagnostics>
<span data-ttu-id="a780f-101">`diagnostics` 要素は、ランタイムの検査と管理を行う管理者が使用できる設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="a780f-101">The `diagnostics` element defines settings that can be used by an administrator for run-time inspection and control.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<diagnostics>**  
  
## <a name="syntax"></a><span data-ttu-id="a780f-102">構文</span><span class="sxs-lookup"><span data-stu-id="a780f-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a780f-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a780f-103">Attributes and Elements</span></span>  
 <span data-ttu-id="a780f-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a780f-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a780f-105">属性</span><span class="sxs-lookup"><span data-stu-id="a780f-105">Attributes</span></span>  
  
|<span data-ttu-id="a780f-106">属性</span><span class="sxs-lookup"><span data-stu-id="a780f-106">Attribute</span></span>|<span data-ttu-id="a780f-107">説明</span><span class="sxs-lookup"><span data-stu-id="a780f-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a780f-108">etwProviderId</span><span class="sxs-lookup"><span data-stu-id="a780f-108">etwProviderId</span></span>|<span data-ttu-id="a780f-109">イベントを ETW セッションに書き込むイベント追跡プロバイダーの識別子を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="a780f-109">A string that specifies the identifier for the Event-Tracing provider, which writes events to ETW sessions.</span></span>|  
|<span data-ttu-id="a780f-110">performanceCounters</span><span class="sxs-lookup"><span data-stu-id="a780f-110">performanceCounters</span></span>|<span data-ttu-id="a780f-111">アセンブリのパフォーマンス カウンターが有効であるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="a780f-111">Specifies whether performance counters for the assembly are enabled.</span></span> <span data-ttu-id="a780f-112">有効な値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a780f-112">Valid values are</span></span><br /><br /> <span data-ttu-id="a780f-113">-Off: パフォーマンスカウンターが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="a780f-113">-   Off: Performance counters are disabled.</span></span><br /><span data-ttu-id="a780f-114">-ServiceOnly: このサービスに関連するパフォーマンスカウンターのみが有効になっています。</span><span class="sxs-lookup"><span data-stu-id="a780f-114">-   ServiceOnly: Only performance counters relevant to this service is enabled.</span></span><br /><span data-ttu-id="a780f-115">-All: パフォーマンスカウンターは実行時に表示できます。</span><span class="sxs-lookup"><span data-stu-id="a780f-115">-   All: Performance counters can be viewed at runtime.</span></span><br /><span data-ttu-id="a780f-116">-Default: 1 つのパフォーマンスカウンターインスタンス _WCF_Admin が作成されます。</span><span class="sxs-lookup"><span data-stu-id="a780f-116">-   Default: A single performance counter instance _WCF_Admin is created.</span></span> <span data-ttu-id="a780f-117">このインスタンスは、インフラストラクチャで使用される SQM データのコレクションを有効にするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="a780f-117">This instance is used to enable the collection of SQM data for used by the infrastructure.</span></span> <span data-ttu-id="a780f-118">このインスタンスのカウンター値は更新されず、0 のままになります。</span><span class="sxs-lookup"><span data-stu-id="a780f-118">None of the counter values for this instance are updated and therefore will remain at zero.</span></span> <span data-ttu-id="a780f-119">WCF の構成が存在しない場合は、これが既定値になります。</span><span class="sxs-lookup"><span data-stu-id="a780f-119">This is the default value if no configuration is present for WCF.</span></span>|  
|<span data-ttu-id="a780f-120">wmiProviderEnabled</span><span class="sxs-lookup"><span data-stu-id="a780f-120">wmiProviderEnabled</span></span>|<span data-ttu-id="a780f-121">アセンブリの WMI プロバイダーが有効であるかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="a780f-121">A Boolean value that specifies whether the WMI provider for the assembly is enabled.</span></span> <span data-ttu-id="a780f-122">ユーザーが Windows Communication Foundation (WCF) の検査および制御機能に対する実行時アクセス権を取得するには、WMI プロバイダーが必要です。</span><span class="sxs-lookup"><span data-stu-id="a780f-122">The WMI provider is required for user to gain run-time access to the inspection and control features of Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="a780f-123">既定値は、`false` です。</span><span class="sxs-lookup"><span data-stu-id="a780f-123">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a780f-124">子要素</span><span class="sxs-lookup"><span data-stu-id="a780f-124">Child Elements</span></span>  
  
|<span data-ttu-id="a780f-125">要素</span><span class="sxs-lookup"><span data-stu-id="a780f-125">Element</span></span>|<span data-ttu-id="a780f-126">Description</span><span class="sxs-lookup"><span data-stu-id="a780f-126">Description</span></span>|  
|-------------|-----------------|  
|[\<endToEndTracing>](endtoendtracing.md)|<span data-ttu-id="a780f-127">サービス アプリケーションの実行中にエンドツーエンドのトレースのさまざまな側面を有効または無効にするための構成要素。</span><span class="sxs-lookup"><span data-stu-id="a780f-127">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>|  
|[\<messageLogging>](messagelogging.md)|<span data-ttu-id="a780f-128">WCF メッセージ ログの設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="a780f-128">Describes the settings for WCF message logging.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a780f-129">親要素</span><span class="sxs-lookup"><span data-stu-id="a780f-129">Parent Elements</span></span>  
  
|<span data-ttu-id="a780f-130">要素</span><span class="sxs-lookup"><span data-stu-id="a780f-130">Element</span></span>|<span data-ttu-id="a780f-131">Description</span><span class="sxs-lookup"><span data-stu-id="a780f-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a780f-132">serviceModel</span><span class="sxs-lookup"><span data-stu-id="a780f-132">serviceModel</span></span>|<span data-ttu-id="a780f-133">すべての WCF 構成要素のルート要素です。</span><span class="sxs-lookup"><span data-stu-id="a780f-133">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a780f-134">解説</span><span class="sxs-lookup"><span data-stu-id="a780f-134">Remarks</span></span>  
 <span data-ttu-id="a780f-135">`diagnostics` セクションは、アセンブリに配置されるすべてのサービスの診断設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="a780f-135">The `diagnostics` section defines the diagnostics settings for all services located in an assembly.</span></span> <span data-ttu-id="a780f-136">アセンブリ内のサービスが 1 つでない限り、サービス レベル別に診断設定を定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="a780f-136">It is not possible to define separate diagnostics settings at the service level unless there is only one service in the assembly.</span></span> <span data-ttu-id="a780f-137">属性は、セクションの要件に応じて設定されます。</span><span class="sxs-lookup"><span data-stu-id="a780f-137">Attributes are set according to the requirements of the section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a780f-138">例</span><span class="sxs-lookup"><span data-stu-id="a780f-138">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a780f-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="a780f-139">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
