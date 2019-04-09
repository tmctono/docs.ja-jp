---
title: <add> (行中)  <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
ms.openlocfilehash: fbcb3a07bf40c96a4cd1b2ec87277b6fefdfb89d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59164477"
---
# <a name="add-of-baseaddresses"></a><span data-ttu-id="1c7b8-102">\<add> of \<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="1c7b8-102">\<add> of \<baseAddresses></span></span>
<span data-ttu-id="1c7b8-103">サービス ホストによって使用されるベース アドレスを指定する構成要素を表します。</span><span class="sxs-lookup"><span data-stu-id="1c7b8-103">Represents a configuration element that specifies the base addresses used by the service host.</span></span>  
  
 <span data-ttu-id="1c7b8-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="1c7b8-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1c7b8-105">\<client></span><span class="sxs-lookup"><span data-stu-id="1c7b8-105">\<client></span></span>  
<span data-ttu-id="1c7b8-106">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="1c7b8-106">\<endpoint></span></span>  
<span data-ttu-id="1c7b8-107">\<host></span><span class="sxs-lookup"><span data-stu-id="1c7b8-107">\<host></span></span>  
<span data-ttu-id="1c7b8-108">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="1c7b8-108">\<baseAddresses></span></span>  
<span data-ttu-id="1c7b8-109">\<baseAddress></span><span class="sxs-lookup"><span data-stu-id="1c7b8-109">\<baseAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c7b8-110">構文</span><span class="sxs-lookup"><span data-stu-id="1c7b8-110">Syntax</span></span>  
  
```xml  
<add baseAddress="string" />
```  
  
## <a name="type"></a><span data-ttu-id="1c7b8-111">型</span><span class="sxs-lookup"><span data-stu-id="1c7b8-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1c7b8-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1c7b8-112">Attributes and Elements</span></span>  
 <span data-ttu-id="1c7b8-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1c7b8-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1c7b8-114">属性</span><span class="sxs-lookup"><span data-stu-id="1c7b8-114">Attributes</span></span>  
  
|<span data-ttu-id="1c7b8-115">属性</span><span class="sxs-lookup"><span data-stu-id="1c7b8-115">Attribute</span></span>|<span data-ttu-id="1c7b8-116">説明</span><span class="sxs-lookup"><span data-stu-id="1c7b8-116">Description</span></span>|  
|---------------|-----------------|  
|`baseAddress`|<span data-ttu-id="1c7b8-117">サービス ホストによって使用されるベース アドレスを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="1c7b8-117">A string that specifies a base address used by the service host.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1c7b8-118">子要素</span><span class="sxs-lookup"><span data-stu-id="1c7b8-118">Child Elements</span></span>  
 <span data-ttu-id="1c7b8-119">なし。</span><span class="sxs-lookup"><span data-stu-id="1c7b8-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1c7b8-120">親要素</span><span class="sxs-lookup"><span data-stu-id="1c7b8-120">Parent Elements</span></span>  
  
|<span data-ttu-id="1c7b8-121">要素</span><span class="sxs-lookup"><span data-stu-id="1c7b8-121">Element</span></span>|<span data-ttu-id="1c7b8-122">説明</span><span class="sxs-lookup"><span data-stu-id="1c7b8-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1c7b8-123">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="1c7b8-123">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="1c7b8-124">`baseAddress` 要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="1c7b8-124">A collection of `baseAddress` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1c7b8-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="1c7b8-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="1c7b8-126">ホスト</span><span class="sxs-lookup"><span data-stu-id="1c7b8-126">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
