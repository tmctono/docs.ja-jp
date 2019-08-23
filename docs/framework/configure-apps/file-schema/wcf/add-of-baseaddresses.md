---
title: <add> の <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
ms.openlocfilehash: a94c5144d907c26e6f5eef09b1a17b17eb6c9e0f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920216"
---
# <a name="add-of-baseaddresses"></a><span data-ttu-id="721f2-102">\<baseaddresses の\<> を追加 ></span><span class="sxs-lookup"><span data-stu-id="721f2-102">\<add> of \<baseAddresses></span></span>
<span data-ttu-id="721f2-103">サービス ホストによって使用されるベース アドレスを指定する構成要素を表します。</span><span class="sxs-lookup"><span data-stu-id="721f2-103">Represents a configuration element that specifies the base addresses used by the service host.</span></span>  
  
 <span data-ttu-id="721f2-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="721f2-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="721f2-105">\<client></span><span class="sxs-lookup"><span data-stu-id="721f2-105">\<client></span></span>  
<span data-ttu-id="721f2-106">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="721f2-106">\<endpoint></span></span>  
<span data-ttu-id="721f2-107">\<ホスト ></span><span class="sxs-lookup"><span data-stu-id="721f2-107">\<host></span></span>  
<span data-ttu-id="721f2-108">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="721f2-108">\<baseAddresses></span></span>  
<span data-ttu-id="721f2-109">\<baseAddress></span><span class="sxs-lookup"><span data-stu-id="721f2-109">\<baseAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="721f2-110">構文</span><span class="sxs-lookup"><span data-stu-id="721f2-110">Syntax</span></span>  
  
```xml  
<add baseAddress="string" />
```  
  
## <a name="type"></a><span data-ttu-id="721f2-111">型</span><span class="sxs-lookup"><span data-stu-id="721f2-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="721f2-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="721f2-112">Attributes and Elements</span></span>  
 <span data-ttu-id="721f2-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="721f2-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="721f2-114">属性</span><span class="sxs-lookup"><span data-stu-id="721f2-114">Attributes</span></span>  
  
|<span data-ttu-id="721f2-115">属性</span><span class="sxs-lookup"><span data-stu-id="721f2-115">Attribute</span></span>|<span data-ttu-id="721f2-116">説明</span><span class="sxs-lookup"><span data-stu-id="721f2-116">Description</span></span>|  
|---------------|-----------------|  
|`baseAddress`|<span data-ttu-id="721f2-117">サービス ホストによって使用されるベース アドレスを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="721f2-117">A string that specifies a base address used by the service host.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="721f2-118">子要素</span><span class="sxs-lookup"><span data-stu-id="721f2-118">Child Elements</span></span>  
 <span data-ttu-id="721f2-119">なし。</span><span class="sxs-lookup"><span data-stu-id="721f2-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="721f2-120">親要素</span><span class="sxs-lookup"><span data-stu-id="721f2-120">Parent Elements</span></span>  
  
|<span data-ttu-id="721f2-121">要素</span><span class="sxs-lookup"><span data-stu-id="721f2-121">Element</span></span>|<span data-ttu-id="721f2-122">説明</span><span class="sxs-lookup"><span data-stu-id="721f2-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="721f2-123">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="721f2-123">\<baseAddresses></span></span>](baseaddresses.md)|<span data-ttu-id="721f2-124">`baseAddress` 要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="721f2-124">A collection of `baseAddress` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="721f2-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="721f2-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="721f2-126">ホスティング</span><span class="sxs-lookup"><span data-stu-id="721f2-126">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
