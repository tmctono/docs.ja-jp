---
title: '方法: Probe 要求の探索バージョンを特定する'
ms.date: 03/30/2017
ms.assetid: b3c4e2e2-2957-4074-ae6a-776a5ca84278
ms.openlocfilehash: 2b7e42714ae1d16a84bcb6f0fc79cf5b376a7a16
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595415"
---
# <a name="how-todetermine-the-discovery-version-of-a-probe-request"></a><span data-ttu-id="58046-102">方法: Probe 要求の探索バージョンを特定する</span><span class="sxs-lookup"><span data-stu-id="58046-102">How to:Determine the Discovery Version of a Probe Request</span></span>

<span data-ttu-id="58046-103">探索プロキシでは、異なる探索バージョンを使用する複数の探索エンドポイントを公開する場合があります。</span><span class="sxs-lookup"><span data-stu-id="58046-103">A discovery proxy may expose multiple discovery endpoints using different discovery versions.</span></span> <span data-ttu-id="58046-104">UDP マルチキャストプローブ要求がプロキシに到着すると、プロキシはマルチキャスト抑制メッセージで応答する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58046-104">When a UDP multicast Probe request arrives at the proxy, the proxy should respond with a multicast suppression message.</span></span> <span data-ttu-id="58046-105">このためには、要求の探索バージョンを把握している必要があります。</span><span class="sxs-lookup"><span data-stu-id="58046-105">In order to do this, it would have to know the discovery version of the request.</span></span>

## <a name="to-determine-the-discovery-version-of-a-probe-request"></a><span data-ttu-id="58046-106">Probe 要求の探索バージョンを特定するには</span><span class="sxs-lookup"><span data-stu-id="58046-106">To Determine the Discovery Version of a Probe Request</span></span>

<span data-ttu-id="58046-107">プローブ要求に応答するメソッド (たとえば) では、 <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A?displayProperty=nameWithType> <xref:System.ServiceModel.OperationContext.Current%2A?displayProperty=nameWithType> 次のコードに示すように、静的プロパティを使用してを検索し <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension> ます。</span><span class="sxs-lookup"><span data-stu-id="58046-107">In the method that responds to a Probe request (for example <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A?displayProperty=nameWithType>) use the static <xref:System.ServiceModel.OperationContext.Current%2A?displayProperty=nameWithType> property to search for a <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension>, as shown in the following code.</span></span>

```csharp
DiscoveryOperationContextExtension doce = OperationContext.Current.Extensions.Find<DiscoveryOperationContextExtension>();
// Access the discovery version from the DiscoveryOperationContextExtension
doce.DiscoveryVersion;
```

## <a name="see-also"></a><span data-ttu-id="58046-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="58046-108">See also</span></span>

- <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion%2A>
- [<span data-ttu-id="58046-109">探索プロキシの実装</span><span class="sxs-lookup"><span data-stu-id="58046-109">Implementing a Discovery Proxy</span></span>](implementing-a-discovery-proxy.md)
