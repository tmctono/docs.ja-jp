---
title: <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 059ea4e637ab906d1fde9807a73ac8341f81c574
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926419"
---
# <a name="baseaddresses"></a><span data-ttu-id="33478-101">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="33478-101">\<baseAddresses></span></span>
<span data-ttu-id="33478-102">自己ホスト環境でのサービス ホストのベース アドレスである `baseAddress` 要素のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="33478-102">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="33478-103">ベース アドレスが存在すると、そのベース アドレスに関連したアドレスを使用してエンドポイントを構成できます。</span><span class="sxs-lookup"><span data-stu-id="33478-103">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
 <span data-ttu-id="33478-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="33478-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="33478-105">\<client></span><span class="sxs-lookup"><span data-stu-id="33478-105">\<client></span></span>  
<span data-ttu-id="33478-106">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="33478-106">\<endpoint></span></span>  
<span data-ttu-id="33478-107">\<ホスト ></span><span class="sxs-lookup"><span data-stu-id="33478-107">\<host></span></span>  
<span data-ttu-id="33478-108">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="33478-108">\<baseAddresses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33478-109">構文</span><span class="sxs-lookup"><span data-stu-id="33478-109">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="33478-110">型</span><span class="sxs-lookup"><span data-stu-id="33478-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="33478-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="33478-111">Attributes and Elements</span></span>  
 <span data-ttu-id="33478-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="33478-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="33478-113">属性</span><span class="sxs-lookup"><span data-stu-id="33478-113">Attributes</span></span>  
 <span data-ttu-id="33478-114">なし。</span><span class="sxs-lookup"><span data-stu-id="33478-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="33478-115">子要素</span><span class="sxs-lookup"><span data-stu-id="33478-115">Child Elements</span></span>  
  
|<span data-ttu-id="33478-116">要素</span><span class="sxs-lookup"><span data-stu-id="33478-116">Element</span></span>|<span data-ttu-id="33478-117">説明</span><span class="sxs-lookup"><span data-stu-id="33478-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="33478-118">\<add></span><span class="sxs-lookup"><span data-stu-id="33478-118">\<add></span></span>](add-of-baseaddresses.md)|<span data-ttu-id="33478-119">サービス ホストによって使用されるベース アドレスを指定する構成要素。</span><span class="sxs-lookup"><span data-stu-id="33478-119">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="33478-120">親要素</span><span class="sxs-lookup"><span data-stu-id="33478-120">Parent Elements</span></span>  
  
|<span data-ttu-id="33478-121">要素</span><span class="sxs-lookup"><span data-stu-id="33478-121">Element</span></span>|<span data-ttu-id="33478-122">説明</span><span class="sxs-lookup"><span data-stu-id="33478-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="33478-123">\<ホスト ></span><span class="sxs-lookup"><span data-stu-id="33478-123">\<host></span></span>](host.md)|<span data-ttu-id="33478-124">サービス ホストの設定を指定する構成要素です。</span><span class="sxs-lookup"><span data-stu-id="33478-124">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="33478-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="33478-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="33478-126">ホスティング</span><span class="sxs-lookup"><span data-stu-id="33478-126">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
