---
title: '方法: Probe 要求の探索バージョンを特定する'
ms.date: 03/30/2017
ms.assetid: b3c4e2e2-2957-4074-ae6a-776a5ca84278
ms.openlocfilehash: 8fbc3936278a5c6f403f48b59390c69c64378004
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2019
ms.locfileid: "67425269"
---
# <a name="how-todetermine-the-discovery-version-of-a-probe-request"></a><span data-ttu-id="56451-102">方法: Probe 要求の探索バージョンを特定する</span><span class="sxs-lookup"><span data-stu-id="56451-102">How to:Determine the Discovery Version of a Probe Request</span></span>

<span data-ttu-id="56451-103">探索プロキシでは、異なる探索バージョンを使用する複数の探索エンドポイントを公開する場合があります。</span><span class="sxs-lookup"><span data-stu-id="56451-103">A discovery proxy may expose multiple discovery endpoints using different discovery versions.</span></span> <span data-ttu-id="56451-104">ときに、UDP マルチキャスト Probe 要求を受け取った、プロキシにプロキシがマルチキャスト抑制メッセージで応答する必要があります。</span><span class="sxs-lookup"><span data-stu-id="56451-104">When a UDP multicast Probe request arrives at the proxy, the proxy should respond with a multicast suppression message.</span></span> <span data-ttu-id="56451-105">これを行うには、要求の探索バージョンを把握することになります。</span><span class="sxs-lookup"><span data-stu-id="56451-105">In order to do this, it would have to know the discovery version of the request.</span></span>

## <a name="to-determine-the-discovery-version-of-a-probe-request"></a><span data-ttu-id="56451-106">Probe 要求の探索バージョンを特定するには</span><span class="sxs-lookup"><span data-stu-id="56451-106">To Determine the Discovery Version of a Probe Request</span></span>

<span data-ttu-id="56451-107">プローブ要求に応答するメソッドで (たとえば<xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A?displayProperty=nameWithType>)、静的なを使用して、<xref:System.ServiceModel.OperationContext.Current%2A?displayProperty=nameWithType>検索対象のプロパティを<xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension>次のコードに示すように、します。</span><span class="sxs-lookup"><span data-stu-id="56451-107">In the method that responds to a Probe request (for example <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A?displayProperty=nameWithType>) use the static <xref:System.ServiceModel.OperationContext.Current%2A?displayProperty=nameWithType> property to search for a <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension>, as shown in the following code.</span></span>

```csharp
DiscoveryOperationContextExtension doce = OperationContext.Current.Extensions.Find<DiscoveryOperationContextExtension>();
// Access the discovery version from the DiscoveryOperationContextExtension
doce.DiscoveryVersion;
```

## <a name="see-also"></a><span data-ttu-id="56451-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="56451-108">See also</span></span>

- <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion%2A>
- [<span data-ttu-id="56451-109">探索プロキシの実装</span><span class="sxs-lookup"><span data-stu-id="56451-109">Implementing a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)
