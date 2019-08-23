---
title: <host>
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: 21d53df12c2b2d703b771e2b9cb5ee87dafc410e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918707"
---
# <a name="host"></a><span data-ttu-id="19cf2-101">\<ホスト ></span><span class="sxs-lookup"><span data-stu-id="19cf2-101">\<host></span></span>
<span data-ttu-id="19cf2-102">サービス ホストの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="19cf2-102">Specifies settings for a service host.</span></span>  
  
 <span data-ttu-id="19cf2-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="19cf2-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="19cf2-104">\<services></span><span class="sxs-lookup"><span data-stu-id="19cf2-104">\<services></span></span>  
<span data-ttu-id="19cf2-105">\<サービス ></span><span class="sxs-lookup"><span data-stu-id="19cf2-105">\<service></span></span>  
<span data-ttu-id="19cf2-106">\<ホスト ></span><span class="sxs-lookup"><span data-stu-id="19cf2-106">\<host></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19cf2-107">構文</span><span class="sxs-lookup"><span data-stu-id="19cf2-107">Syntax</span></span>  
  
```xml  
<host>
  <baseAddresses>
    <add baseAddress="string" />
  </baseAddresses>
  <timeOuts closeTimeout="TimeSpan"
            openTimeout="TimeSpan" />
</host>
```  
  
## <a name="type"></a><span data-ttu-id="19cf2-108">型</span><span class="sxs-lookup"><span data-stu-id="19cf2-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="19cf2-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="19cf2-109">Attributes and Elements</span></span>  
 <span data-ttu-id="19cf2-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="19cf2-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="19cf2-111">属性</span><span class="sxs-lookup"><span data-stu-id="19cf2-111">Attributes</span></span>  
 <span data-ttu-id="19cf2-112">なし。</span><span class="sxs-lookup"><span data-stu-id="19cf2-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="19cf2-113">子要素</span><span class="sxs-lookup"><span data-stu-id="19cf2-113">Child Elements</span></span>  
  
|<span data-ttu-id="19cf2-114">要素</span><span class="sxs-lookup"><span data-stu-id="19cf2-114">Element</span></span>|<span data-ttu-id="19cf2-115">説明</span><span class="sxs-lookup"><span data-stu-id="19cf2-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="19cf2-116">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="19cf2-116">\<baseAddresses></span></span>](baseaddresses.md)|<span data-ttu-id="19cf2-117">サービス ホストによって使用されるベース アドレスを指定する `baseAddress` 要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="19cf2-117">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="19cf2-118">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="19cf2-118">\<timeOuts></span></span>](timeouts.md)|<span data-ttu-id="19cf2-119">サービス ホストを開くまたは閉じるまでに待機できる期間を指定する構成要素。</span><span class="sxs-lookup"><span data-stu-id="19cf2-119">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="19cf2-120">親要素</span><span class="sxs-lookup"><span data-stu-id="19cf2-120">Parent Elements</span></span>  
  
|<span data-ttu-id="19cf2-121">要素</span><span class="sxs-lookup"><span data-stu-id="19cf2-121">Element</span></span>|<span data-ttu-id="19cf2-122">説明</span><span class="sxs-lookup"><span data-stu-id="19cf2-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="19cf2-123">\<service></span><span class="sxs-lookup"><span data-stu-id="19cf2-123">\<service></span></span>](service.md)|<span data-ttu-id="19cf2-124">Windows Communication Foundation (WCF) サービスの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="19cf2-124">Specifies the settings for a Windows Communication Foundation (WCF) service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="19cf2-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="19cf2-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="19cf2-126">ホスティング</span><span class="sxs-lookup"><span data-stu-id="19cf2-126">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
