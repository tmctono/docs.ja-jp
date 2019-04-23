---
title: <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 7d0afd638e9a311b69ff47b6789d5fde093945ba
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59212103"
---
# <a name="baseaddresses"></a><span data-ttu-id="6c591-101">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="6c591-101">\<baseAddresses></span></span>
<span data-ttu-id="6c591-102">自己ホスト環境でのサービス ホストのベース アドレスである `baseAddress` 要素のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="6c591-102">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="6c591-103">ベース アドレスが存在すると、そのベース アドレスに関連したアドレスを使用してエンドポイントを構成できます。</span><span class="sxs-lookup"><span data-stu-id="6c591-103">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
 <span data-ttu-id="6c591-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="6c591-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="6c591-105">\<client></span><span class="sxs-lookup"><span data-stu-id="6c591-105">\<client></span></span>  
<span data-ttu-id="6c591-106">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="6c591-106">\<endpoint></span></span>  
<span data-ttu-id="6c591-107">\<host></span><span class="sxs-lookup"><span data-stu-id="6c591-107">\<host></span></span>  
<span data-ttu-id="6c591-108">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="6c591-108">\<baseAddresses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c591-109">構文</span><span class="sxs-lookup"><span data-stu-id="6c591-109">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="6c591-110">型</span><span class="sxs-lookup"><span data-stu-id="6c591-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6c591-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="6c591-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6c591-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="6c591-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6c591-113">属性</span><span class="sxs-lookup"><span data-stu-id="6c591-113">Attributes</span></span>  
 <span data-ttu-id="6c591-114">なし。</span><span class="sxs-lookup"><span data-stu-id="6c591-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6c591-115">子要素</span><span class="sxs-lookup"><span data-stu-id="6c591-115">Child Elements</span></span>  
  
|<span data-ttu-id="6c591-116">要素</span><span class="sxs-lookup"><span data-stu-id="6c591-116">Element</span></span>|<span data-ttu-id="6c591-117">説明</span><span class="sxs-lookup"><span data-stu-id="6c591-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6c591-118">\<add></span><span class="sxs-lookup"><span data-stu-id="6c591-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md)|<span data-ttu-id="6c591-119">サービス ホストによって使用されるベース アドレスを指定する構成要素。</span><span class="sxs-lookup"><span data-stu-id="6c591-119">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6c591-120">親要素</span><span class="sxs-lookup"><span data-stu-id="6c591-120">Parent Elements</span></span>  
  
|<span data-ttu-id="6c591-121">要素</span><span class="sxs-lookup"><span data-stu-id="6c591-121">Element</span></span>|<span data-ttu-id="6c591-122">説明</span><span class="sxs-lookup"><span data-stu-id="6c591-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6c591-123">\<host></span><span class="sxs-lookup"><span data-stu-id="6c591-123">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="6c591-124">サービス ホストの設定を指定する構成要素です。</span><span class="sxs-lookup"><span data-stu-id="6c591-124">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6c591-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="6c591-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="6c591-126">ホスティング</span><span class="sxs-lookup"><span data-stu-id="6c591-126">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
