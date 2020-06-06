---
title: <transactedBatching>
ms.date: 03/30/2017
ms.assetid: 2f790a0d-8f03-4b86-81b5-ce1bc1a6c575
ms.openlocfilehash: 6167a4ad56a9481a9f695b770605991a0a88d2d9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399415"
---
# \<transactedBatching>

<span data-ttu-id="9d67c-101">受信操作でトランザクション バッチがサポートされるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d67c-101">Specifies whether transaction batching is supported for receive operations.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transactedBatching>**  

## <a name="syntax"></a><span data-ttu-id="9d67c-102">構文</span><span class="sxs-lookup"><span data-stu-id="9d67c-102">Syntax</span></span>

```xml
<transactedBatching maxBatchSize="Integer" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9d67c-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9d67c-103">Attributes and Elements</span></span>

<span data-ttu-id="9d67c-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9d67c-104">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="9d67c-105">属性</span><span class="sxs-lookup"><span data-stu-id="9d67c-105">Attributes</span></span>

|<span data-ttu-id="9d67c-106">属性</span><span class="sxs-lookup"><span data-stu-id="9d67c-106">Attribute</span></span>|<span data-ttu-id="9d67c-107">説明</span><span class="sxs-lookup"><span data-stu-id="9d67c-107">Description</span></span>|
|---------------|-----------------|
|`maxBatchSize`|<span data-ttu-id="9d67c-108">1 回のトランザクションでまとめてバッチ処理できる受信操作の最大数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="9d67c-108">An integer that specifies the maximum number of receive operations that can be batched together in one transaction.</span></span> <span data-ttu-id="9d67c-109">既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="9d67c-109">The default is 0.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="9d67c-110">子要素</span><span class="sxs-lookup"><span data-stu-id="9d67c-110">Child Elements</span></span>

<span data-ttu-id="9d67c-111">なし。</span><span class="sxs-lookup"><span data-stu-id="9d67c-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9d67c-112">親要素</span><span class="sxs-lookup"><span data-stu-id="9d67c-112">Parent Elements</span></span>

|<span data-ttu-id="9d67c-113">要素</span><span class="sxs-lookup"><span data-stu-id="9d67c-113">Element</span></span>|<span data-ttu-id="9d67c-114">Description</span><span class="sxs-lookup"><span data-stu-id="9d67c-114">Description</span></span>|
|-------------|-----------------|
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="9d67c-115">エンドポイントの動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="9d67c-115">Specifies an endpoint behavior.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9d67c-116">解説</span><span class="sxs-lookup"><span data-stu-id="9d67c-116">Remarks</span></span>

<span data-ttu-id="9d67c-117">トランザクション バッチで構成されるトランスポートは、複数の受信操作を 1 つのトランザクションにバッチ処理しようとします。</span><span class="sxs-lookup"><span data-stu-id="9d67c-117">A transport that is configured with transaction batching attempts to batch several receive operations into one transaction.</span></span> <span data-ttu-id="9d67c-118">これを実行することにより、受信操作のたびに行うトランザクションの作成とそのコミットの比較的高いコストを回避できます。</span><span class="sxs-lookup"><span data-stu-id="9d67c-118">By doing so, the relatively high cost of creating a transaction and committing it in every receive operation is avoided.</span></span>

## <a name="example"></a><span data-ttu-id="9d67c-119">例</span><span class="sxs-lookup"><span data-stu-id="9d67c-119">Example</span></span>

<span data-ttu-id="9d67c-120">構成ファイル内でサービスにトランザクション バッチ動作を追加する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="9d67c-120">The following example shows how to add the transacted batching behavior to a service in a configuration file.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="9d67c-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="9d67c-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransactedBatchingElement>
- <xref:System.ServiceModel.Description.TransactedBatchingBehavior>
