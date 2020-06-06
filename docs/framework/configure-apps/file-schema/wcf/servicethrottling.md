---
title: <serviceThrottling>
ms.date: 03/30/2017
ms.assetid: a337d064-1e64-4209-b4a9-db7fdb7e3eaf
ms.openlocfilehash: ad87a5876381a7224341babdb076c85edcd1dd87
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399562"
---
# \<serviceThrottling>
<span data-ttu-id="0e934-101">WCF (Windows Communication Foundation) サービスの調整機構を指定します。</span><span class="sxs-lookup"><span data-stu-id="0e934-101">Specifies the throttling mechanism of a Windows Communication Foundation (WCF) service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceThrottling>**  
  
## <a name="syntax"></a><span data-ttu-id="0e934-102">構文</span><span class="sxs-lookup"><span data-stu-id="0e934-102">Syntax</span></span>  
  
```xml  
<serviceThrottling maxConcurrentCalls="Integer"
                   maxConcurrentInstances="Integer"
                   maxConcurrentSessions="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0e934-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="0e934-103">Attributes and Elements</span></span>  
 <span data-ttu-id="0e934-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="0e934-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0e934-105">属性</span><span class="sxs-lookup"><span data-stu-id="0e934-105">Attributes</span></span>  
  
|<span data-ttu-id="0e934-106">属性</span><span class="sxs-lookup"><span data-stu-id="0e934-106">Attribute</span></span>|<span data-ttu-id="0e934-107">説明</span><span class="sxs-lookup"><span data-stu-id="0e934-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0e934-108">maxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="0e934-108">maxConcurrentCalls</span></span>|<span data-ttu-id="0e934-109"><xref:System.ServiceModel.ServiceHost> で同時に処理できるメッセージ数を制限する正の整数。</span><span class="sxs-lookup"><span data-stu-id="0e934-109">A positive integer that limits the number of messages that currently process across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="0e934-110">制限を超える呼び出しはキューに格納されます。</span><span class="sxs-lookup"><span data-stu-id="0e934-110">Calls in excess of the limit are queued.</span></span> <span data-ttu-id="0e934-111">この値を 0 に設定することは、Int32.MaxValue に設定することと同じです。</span><span class="sxs-lookup"><span data-stu-id="0e934-111">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="0e934-112">既定値は 16 x プロセッサ数です。</span><span class="sxs-lookup"><span data-stu-id="0e934-112">The default is 16 \* processor count.</span></span>|  
|<span data-ttu-id="0e934-113">maxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="0e934-113">maxConcurrentInstances</span></span>|<span data-ttu-id="0e934-114"><xref:System.ServiceModel.InstanceContext> で同時に実行できる <xref:System.ServiceModel.ServiceHost> オブジェクト数を制限する正の整数。</span><span class="sxs-lookup"><span data-stu-id="0e934-114">A positive integer that limits the number of <xref:System.ServiceModel.InstanceContext> objects that execute at one time across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="0e934-115">追加インスタンスの作成要求は、キューに置かれ、制限下のスロットが利用できるようになったときに完了されます。</span><span class="sxs-lookup"><span data-stu-id="0e934-115">Requests to create additional instances are queued and complete when a slot below the limit becomes available.</span></span> <span data-ttu-id="0e934-116">既定値は maxConcurrentSessions と MaxConcurrentCalls の合計です。</span><span class="sxs-lookup"><span data-stu-id="0e934-116">The default is the sum of maxConcurrentSessions and MaxConcurrentCalls</span></span>|  
|<span data-ttu-id="0e934-117">maxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="0e934-117">maxConcurrentSessions</span></span>|<span data-ttu-id="0e934-118"><xref:System.ServiceModel.ServiceHost> オブジェクトが受け入れることのできるセッション数を制限する正の整数。</span><span class="sxs-lookup"><span data-stu-id="0e934-118">A positive integer that limits the number of sessions a <xref:System.ServiceModel.ServiceHost> object can accept.</span></span><br /><br /> <span data-ttu-id="0e934-119">サービスは制限を超える接続を受け入れますが、制限内のチャネルだけがアクティブです (メッセージがチャネルから読み取られます)。</span><span class="sxs-lookup"><span data-stu-id="0e934-119">The service will accept connections in excess of the limit, but only the channels below the limit are active (messages are read from the channel).</span></span> <span data-ttu-id="0e934-120">この値を 0 に設定することは、Int32.MaxValue に設定することと同じです。</span><span class="sxs-lookup"><span data-stu-id="0e934-120">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="0e934-121">既定値は 100 x プロセッサ数です。</span><span class="sxs-lookup"><span data-stu-id="0e934-121">The default is 100 \* processor count.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0e934-122">子要素</span><span class="sxs-lookup"><span data-stu-id="0e934-122">Child Elements</span></span>  
 <span data-ttu-id="0e934-123">なし。</span><span class="sxs-lookup"><span data-stu-id="0e934-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0e934-124">親要素</span><span class="sxs-lookup"><span data-stu-id="0e934-124">Parent Elements</span></span>  
  
|<span data-ttu-id="0e934-125">要素</span><span class="sxs-lookup"><span data-stu-id="0e934-125">Element</span></span>|<span data-ttu-id="0e934-126">Description</span><span class="sxs-lookup"><span data-stu-id="0e934-126">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="0e934-127">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="0e934-127">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e934-128">解説</span><span class="sxs-lookup"><span data-stu-id="0e934-128">Remarks</span></span>  
 <span data-ttu-id="0e934-129">調整コントロールは、同時呼び出し、同時インスタンス、または同時セッションの数を制限して、リソースの過剰消費を防ぎます。</span><span class="sxs-lookup"><span data-stu-id="0e934-129">Throttling controls place limits on the number of concurrent calls, instances, or sessions to prevent over-consumption of resources.</span></span>  
  
 <span data-ttu-id="0e934-130">属性の値に到達するたびにトレースが出力されます。</span><span class="sxs-lookup"><span data-stu-id="0e934-130">A trace is written every time the value of attributes is reached.</span></span> <span data-ttu-id="0e934-131">最初のトレースは警告として出力されます。</span><span class="sxs-lookup"><span data-stu-id="0e934-131">The first trace is written as a warning.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e934-132">例</span><span class="sxs-lookup"><span data-stu-id="0e934-132">Example</span></span>  
 <span data-ttu-id="0e934-133">次の構成例では、サービスで同時呼び出しの最大数を 2 に、同時インスタンスの最大数を 10 に制限することを指定しています。</span><span class="sxs-lookup"><span data-stu-id="0e934-133">The following configuration example specifies that the service limits the maximum concurrent calls to 2, and the maximum number of concurrent instances to 10.</span></span> <span data-ttu-id="0e934-134">この例の実行例の詳細については、「[調整](../../../wcf/samples/throttling.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e934-134">For a detailed example of running this example, see [Throttling](../../../wcf/samples/throttling.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0e934-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="0e934-135">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
- <xref:System.ServiceModel.Configuration.ServiceThrottlingElement>
- [<span data-ttu-id="0e934-136">WCF サービス パフォーマンスを制御するための ServiceThrottlingBehavior の使用</span><span class="sxs-lookup"><span data-stu-id="0e934-136">Using ServiceThrottlingBehavior to Control WCF Service Performance</span></span>](../../../wcf/feature-details/using-servicethrottlingbehavior-to-control-wcf-service-performance.md)
