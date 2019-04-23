---
title: <host>
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: 3d1f7774f61060880a5c3b0327bdd6c2cc4dd74e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59103000"
---
# <a name="host"></a><span data-ttu-id="8ed6a-101">\<host></span><span class="sxs-lookup"><span data-stu-id="8ed6a-101">\<host></span></span>
<span data-ttu-id="8ed6a-102">サービス ホストの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ed6a-102">Specifies settings for a service host.</span></span>  
  
 <span data-ttu-id="8ed6a-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="8ed6a-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="8ed6a-104">\<services></span><span class="sxs-lookup"><span data-stu-id="8ed6a-104">\<services></span></span>  
<span data-ttu-id="8ed6a-105">\<service></span><span class="sxs-lookup"><span data-stu-id="8ed6a-105">\<service></span></span>  
<span data-ttu-id="8ed6a-106">\<host></span><span class="sxs-lookup"><span data-stu-id="8ed6a-106">\<host></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ed6a-107">構文</span><span class="sxs-lookup"><span data-stu-id="8ed6a-107">Syntax</span></span>  
  
```xml  
<host>
  <baseAddresses>
    <add baseAddress="string" />
  </baseAddresses>
  <timeOuts closeTimeout="TimeSpan"
            openTimeout="TimeSpan" />
</host>
```  
  
## <a name="type"></a><span data-ttu-id="8ed6a-108">型</span><span class="sxs-lookup"><span data-stu-id="8ed6a-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8ed6a-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8ed6a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8ed6a-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8ed6a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8ed6a-111">属性</span><span class="sxs-lookup"><span data-stu-id="8ed6a-111">Attributes</span></span>  
 <span data-ttu-id="8ed6a-112">なし。</span><span class="sxs-lookup"><span data-stu-id="8ed6a-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8ed6a-113">子要素</span><span class="sxs-lookup"><span data-stu-id="8ed6a-113">Child Elements</span></span>  
  
|<span data-ttu-id="8ed6a-114">要素</span><span class="sxs-lookup"><span data-stu-id="8ed6a-114">Element</span></span>|<span data-ttu-id="8ed6a-115">説明</span><span class="sxs-lookup"><span data-stu-id="8ed6a-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8ed6a-116">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="8ed6a-116">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="8ed6a-117">サービス ホストによって使用されるベース アドレスを指定する `baseAddress` 要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="8ed6a-117">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="8ed6a-118">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="8ed6a-118">\<timeOuts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/timeouts.md)|<span data-ttu-id="8ed6a-119">サービス ホストを開くまたは閉じるまでに待機できる期間を指定する構成要素。</span><span class="sxs-lookup"><span data-stu-id="8ed6a-119">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8ed6a-120">親要素</span><span class="sxs-lookup"><span data-stu-id="8ed6a-120">Parent Elements</span></span>  
  
|<span data-ttu-id="8ed6a-121">要素</span><span class="sxs-lookup"><span data-stu-id="8ed6a-121">Element</span></span>|<span data-ttu-id="8ed6a-122">説明</span><span class="sxs-lookup"><span data-stu-id="8ed6a-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8ed6a-123">\<service></span><span class="sxs-lookup"><span data-stu-id="8ed6a-123">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="8ed6a-124">Windows Communication Foundation (WCF) サービスの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ed6a-124">Specifies the settings for a Windows Communication Foundation (WCF) service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8ed6a-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="8ed6a-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="8ed6a-126">ホスティング</span><span class="sxs-lookup"><span data-stu-id="8ed6a-126">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
