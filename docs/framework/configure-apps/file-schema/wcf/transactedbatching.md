---
title: <transactedBatching>
ms.date: 03/30/2017
ms.assetid: 2f790a0d-8f03-4b86-81b5-ce1bc1a6c575
ms.openlocfilehash: 6167a4ad56a9481a9f695b770605991a0a88d2d9
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399415"
---
# <a name="transactedbatching"></a><span data-ttu-id="efc70-101">\<transactedBatching ></span><span class="sxs-lookup"><span data-stu-id="efc70-101">\<transactedBatching></span></span>

<span data-ttu-id="efc70-102">受信操作でトランザクション バッチがサポートされるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="efc70-102">Specifies whether transaction batching is supported for receive operations.</span></span>

<span data-ttu-id="efc70-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="efc70-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="efc70-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="efc70-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="efc70-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="efc70-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="efc70-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="efc70-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="efc70-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="efc70-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="efc70-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<transactedBatching >**</span><span class="sxs-lookup"><span data-stu-id="efc70-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transactedBatching>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="efc70-109">構文</span><span class="sxs-lookup"><span data-stu-id="efc70-109">Syntax</span></span>

```xml
<transactedBatching maxBatchSize="Integer" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="efc70-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="efc70-110">Attributes and Elements</span></span>

<span data-ttu-id="efc70-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="efc70-111">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="efc70-112">属性</span><span class="sxs-lookup"><span data-stu-id="efc70-112">Attributes</span></span>

|<span data-ttu-id="efc70-113">属性</span><span class="sxs-lookup"><span data-stu-id="efc70-113">Attribute</span></span>|<span data-ttu-id="efc70-114">説明</span><span class="sxs-lookup"><span data-stu-id="efc70-114">Description</span></span>|
|---------------|-----------------|
|`maxBatchSize`|<span data-ttu-id="efc70-115">1 回のトランザクションでまとめてバッチ処理できる受信操作の最大数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="efc70-115">An integer that specifies the maximum number of receive operations that can be batched together in one transaction.</span></span> <span data-ttu-id="efc70-116">既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="efc70-116">The default is 0.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="efc70-117">子要素</span><span class="sxs-lookup"><span data-stu-id="efc70-117">Child Elements</span></span>

<span data-ttu-id="efc70-118">なし。</span><span class="sxs-lookup"><span data-stu-id="efc70-118">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="efc70-119">親要素</span><span class="sxs-lookup"><span data-stu-id="efc70-119">Parent Elements</span></span>

|<span data-ttu-id="efc70-120">要素</span><span class="sxs-lookup"><span data-stu-id="efc70-120">Element</span></span>|<span data-ttu-id="efc70-121">説明</span><span class="sxs-lookup"><span data-stu-id="efc70-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="efc70-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="efc70-122">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="efc70-123">エンドポイントの動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="efc70-123">Specifies an endpoint behavior.</span></span>|

## <a name="remarks"></a><span data-ttu-id="efc70-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="efc70-124">Remarks</span></span>

<span data-ttu-id="efc70-125">トランザクション バッチで構成されるトランスポートは、複数の受信操作を 1 つのトランザクションにバッチ処理しようとします。</span><span class="sxs-lookup"><span data-stu-id="efc70-125">A transport that is configured with transaction batching attempts to batch several receive operations into one transaction.</span></span> <span data-ttu-id="efc70-126">これを実行することにより、受信操作のたびに行うトランザクションの作成とそのコミットの比較的高いコストを回避できます。</span><span class="sxs-lookup"><span data-stu-id="efc70-126">By doing so, the relatively high cost of creating a transaction and committing it in every receive operation is avoided.</span></span>

## <a name="example"></a><span data-ttu-id="efc70-127">例</span><span class="sxs-lookup"><span data-stu-id="efc70-127">Example</span></span>

<span data-ttu-id="efc70-128">構成ファイル内でサービスにトランザクション バッチ動作を追加する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="efc70-128">The following example shows how to add the transacted batching behavior to a service in a configuration file.</span></span>

```xml
<system.serviceModel>
  <services>
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <host>
        <baseAddresses>
          <add baseAddress="http://localhost:8000/ServiceModelSamples/service" />
        </baseAddresses>
      </host>
      <!-- Define NetMsmqEndpoint -->
      <endpoint address="net.msmq://localhost/private/ServiceModelSamples"
                binding="netMsmqBinding"
                contract="Microsoft.ServiceModel.Samples.IQueueCalculator" />
      <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->
      <endpoint address="mex"
                binding="mexHttpBinding"
                contract="IMetadataExchange" />
    </service>
  </services>
  <behaviors>
    <endpointBehaviors>
      <behavior name="endpointBehavior">
        <transactedBatching maxBatchSize="10" />
      </behavior>
    </endpointBehaviors>
    <serviceBehaviors>
      <behavior name="CalculatorServiceBehavior">
        <serviceMetadata httpGetEnabled="true" />
      </behavior>
    </serviceBehaviors>
  </behaviors>
</system.serviceModel>
```

## <a name="see-also"></a><span data-ttu-id="efc70-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="efc70-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransactedBatchingElement>
- <xref:System.ServiceModel.Description.TransactedBatchingBehavior>
