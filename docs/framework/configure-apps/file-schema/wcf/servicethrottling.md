---
title: <serviceThrottling>
ms.date: 03/30/2017
ms.assetid: a337d064-1e64-4209-b4a9-db7fdb7e3eaf
ms.openlocfilehash: 995ff9979096757225c9241e977f86f755955945
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59158771"
---
# <a name="servicethrottling"></a><span data-ttu-id="587de-101">\<serviceThrottling></span><span class="sxs-lookup"><span data-stu-id="587de-101">\<serviceThrottling></span></span>
<span data-ttu-id="587de-102">WCF (Windows Communication Foundation) サービスの調整機構を指定します。</span><span class="sxs-lookup"><span data-stu-id="587de-102">Specifies the throttling mechanism of a Windows Communication Foundation (WCF) service.</span></span>  
  
 <span data-ttu-id="587de-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="587de-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="587de-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="587de-104">\<behaviors></span></span>  
<span data-ttu-id="587de-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="587de-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="587de-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="587de-106">\<behavior></span></span>  
<span data-ttu-id="587de-107">\<serviceThrottling></span><span class="sxs-lookup"><span data-stu-id="587de-107">\<serviceThrottling></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="587de-108">構文</span><span class="sxs-lookup"><span data-stu-id="587de-108">Syntax</span></span>  
  
```xml  
<serviceThrottling maxConcurrentCalls="Integer"
                   maxConcurrentInstances="Integer"
                   maxConcurrentSessions="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="587de-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="587de-109">Attributes and Elements</span></span>  
 <span data-ttu-id="587de-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="587de-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="587de-111">属性</span><span class="sxs-lookup"><span data-stu-id="587de-111">Attributes</span></span>  
  
|<span data-ttu-id="587de-112">属性</span><span class="sxs-lookup"><span data-stu-id="587de-112">Attribute</span></span>|<span data-ttu-id="587de-113">説明</span><span class="sxs-lookup"><span data-stu-id="587de-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="587de-114">maxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="587de-114">maxConcurrentCalls</span></span>|<span data-ttu-id="587de-115"><xref:System.ServiceModel.ServiceHost> で同時に処理できるメッセージ数を制限する正の整数。</span><span class="sxs-lookup"><span data-stu-id="587de-115">A positive integer that limits the number of messages that currently process across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="587de-116">制限を超えた呼び出しはキューに置かれます。</span><span class="sxs-lookup"><span data-stu-id="587de-116">Calls in excess of the limit are queued.</span></span> <span data-ttu-id="587de-117">この値を 0 に設定することは、Int32.MaxValue に設定することと同じです。</span><span class="sxs-lookup"><span data-stu-id="587de-117">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="587de-118">既定値は 16 x プロセッサ数です。</span><span class="sxs-lookup"><span data-stu-id="587de-118">The default is 16 \* processor count.</span></span>|  
|<span data-ttu-id="587de-119">maxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="587de-119">maxConcurrentInstances</span></span>|<span data-ttu-id="587de-120"><xref:System.ServiceModel.InstanceContext> で同時に実行できる <xref:System.ServiceModel.ServiceHost> オブジェクト数を制限する正の整数。</span><span class="sxs-lookup"><span data-stu-id="587de-120">A positive integer that limits the number of <xref:System.ServiceModel.InstanceContext> objects that execute at one time across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="587de-121">追加インスタンスの作成要求は、キューに置かれ、制限下のスロットが利用できるようになったときに完了されます。</span><span class="sxs-lookup"><span data-stu-id="587de-121">Requests to create additional instances are queued and complete when a slot below the limit becomes available.</span></span> <span data-ttu-id="587de-122">既定値は maxConcurrentSessions と MaxConcurrentCalls の合計です。</span><span class="sxs-lookup"><span data-stu-id="587de-122">The default is the sum of maxConcurrentSessions and MaxConcurrentCalls</span></span>|  
|<span data-ttu-id="587de-123">maxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="587de-123">maxConcurrentSessions</span></span>|<span data-ttu-id="587de-124"><xref:System.ServiceModel.ServiceHost> オブジェクトが受け入れることのできるセッション数を制限する正の整数。</span><span class="sxs-lookup"><span data-stu-id="587de-124">A positive integer that limits the number of sessions a <xref:System.ServiceModel.ServiceHost> object can accept.</span></span><br /><br /> <span data-ttu-id="587de-125">サービスは制限を超える接続を受け入れますが、制限内のチャネルだけがアクティブです (メッセージがチャネルから読み取られます)。</span><span class="sxs-lookup"><span data-stu-id="587de-125">The service will accept connections in excess of the limit, but only the channels below the limit are active (messages are read from the channel).</span></span> <span data-ttu-id="587de-126">この値を 0 に設定することは、Int32.MaxValue に設定することと同じです。</span><span class="sxs-lookup"><span data-stu-id="587de-126">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="587de-127">既定値は 100 x プロセッサ数です。</span><span class="sxs-lookup"><span data-stu-id="587de-127">The default is 100 \* processor count.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="587de-128">子要素</span><span class="sxs-lookup"><span data-stu-id="587de-128">Child Elements</span></span>  
 <span data-ttu-id="587de-129">なし。</span><span class="sxs-lookup"><span data-stu-id="587de-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="587de-130">親要素</span><span class="sxs-lookup"><span data-stu-id="587de-130">Parent Elements</span></span>  
  
|<span data-ttu-id="587de-131">要素</span><span class="sxs-lookup"><span data-stu-id="587de-131">Element</span></span>|<span data-ttu-id="587de-132">説明</span><span class="sxs-lookup"><span data-stu-id="587de-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="587de-133">\<behavior></span><span class="sxs-lookup"><span data-stu-id="587de-133">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="587de-134">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="587de-134">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="587de-135">Remarks</span><span class="sxs-lookup"><span data-stu-id="587de-135">Remarks</span></span>  
 <span data-ttu-id="587de-136">調整コントロールは、同時呼び出し、同時インスタンス、または同時セッションの数を制限して、リソースの過剰消費を防ぎます。</span><span class="sxs-lookup"><span data-stu-id="587de-136">Throttling controls place limits on the number of concurrent calls, instances, or sessions to prevent over-consumption of resources.</span></span>  
  
 <span data-ttu-id="587de-137">属性の値に到達するたびにトレースが出力されます。</span><span class="sxs-lookup"><span data-stu-id="587de-137">A trace is written every time the value of attributes is reached.</span></span> <span data-ttu-id="587de-138">最初のトレースは警告として出力されます。</span><span class="sxs-lookup"><span data-stu-id="587de-138">The first trace is written as a warning.</span></span>  
  
## <a name="example"></a><span data-ttu-id="587de-139">例</span><span class="sxs-lookup"><span data-stu-id="587de-139">Example</span></span>  
 <span data-ttu-id="587de-140">次の構成例では、サービスで同時呼び出しの最大数を 2 に、同時インスタンスの最大数を 10 に制限することを指定しています。</span><span class="sxs-lookup"><span data-stu-id="587de-140">The following configuration example specifies that the service limits the maximum concurrent calls to 2, and the maximum number of concurrent instances to 10.</span></span> <span data-ttu-id="587de-141">この例の実行の詳細な例を参照してください。[スロットル](../../../../../docs/framework/wcf/samples/throttling.md)します。</span><span class="sxs-lookup"><span data-stu-id="587de-141">For a detailed example of running this example, see [Throttling](../../../../../docs/framework/wcf/samples/throttling.md).</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
      <serviceDebug includeExceptionDetailInFaults="False" />
      <serviceMetadata httpGetEnabled="True" />
      <!-- Specify throttling behavior -->
      <serviceThrottling maxConcurrentCalls="2"
                         maxConcurrentInstances="10" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="587de-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="587de-142">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
- <xref:System.ServiceModel.Configuration.ServiceThrottlingElement>
- [<span data-ttu-id="587de-143">WCF サービス パフォーマンスを制御するための ServiceThrottlingBehavior の使用</span><span class="sxs-lookup"><span data-stu-id="587de-143">Using ServiceThrottlingBehavior to Control WCF Service Performance</span></span>](../../../../../docs/framework/wcf/feature-details/using-servicethrottlingbehavior-to-control-wcf-service-performance.md)
