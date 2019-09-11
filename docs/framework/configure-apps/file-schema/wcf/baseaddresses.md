---
title: <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 9b3ed6b39f1743249925d5b6d9a47845c87983bc
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850208"
---
# <a name="baseaddresses"></a><span data-ttu-id="4e9b0-101">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="4e9b0-101">\<baseAddresses></span></span>
<span data-ttu-id="4e9b0-102">自己ホスト環境でのサービス ホストのベース アドレスである `baseAddress` 要素のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="4e9b0-102">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="4e9b0-103">ベース アドレスが存在すると、そのベース アドレスに関連したアドレスを使用してエンドポイントを構成できます。</span><span class="sxs-lookup"><span data-stu-id="4e9b0-103">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
<span data-ttu-id="4e9b0-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4e9b0-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4e9b0-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="4e9b0-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="4e9b0-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<サービス >** ](services.md)</span><span class="sxs-lookup"><span data-stu-id="4e9b0-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)</span></span>\
<span data-ttu-id="4e9b0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<サービス >** ](service.md)</span><span class="sxs-lookup"><span data-stu-id="4e9b0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)</span></span>\
<span data-ttu-id="4e9b0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ホスト >** ](host.md)</span><span class="sxs-lookup"><span data-stu-id="4e9b0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)</span></span>\
<span data-ttu-id="4e9b0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<baseAddresses >**</span><span class="sxs-lookup"><span data-stu-id="4e9b0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<baseAddresses>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e9b0-110">構文</span><span class="sxs-lookup"><span data-stu-id="4e9b0-110">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="4e9b0-111">型</span><span class="sxs-lookup"><span data-stu-id="4e9b0-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4e9b0-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4e9b0-112">Attributes and Elements</span></span>  
 <span data-ttu-id="4e9b0-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4e9b0-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4e9b0-114">属性</span><span class="sxs-lookup"><span data-stu-id="4e9b0-114">Attributes</span></span>  
 <span data-ttu-id="4e9b0-115">なし。</span><span class="sxs-lookup"><span data-stu-id="4e9b0-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4e9b0-116">子要素</span><span class="sxs-lookup"><span data-stu-id="4e9b0-116">Child Elements</span></span>  
  
|<span data-ttu-id="4e9b0-117">要素</span><span class="sxs-lookup"><span data-stu-id="4e9b0-117">Element</span></span>|<span data-ttu-id="4e9b0-118">説明</span><span class="sxs-lookup"><span data-stu-id="4e9b0-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4e9b0-119">\<add></span><span class="sxs-lookup"><span data-stu-id="4e9b0-119">\<add></span></span>](add-of-baseaddresses.md)|<span data-ttu-id="4e9b0-120">サービス ホストによって使用されるベース アドレスを指定する構成要素。</span><span class="sxs-lookup"><span data-stu-id="4e9b0-120">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4e9b0-121">親要素</span><span class="sxs-lookup"><span data-stu-id="4e9b0-121">Parent Elements</span></span>  
  
|<span data-ttu-id="4e9b0-122">要素</span><span class="sxs-lookup"><span data-stu-id="4e9b0-122">Element</span></span>|<span data-ttu-id="4e9b0-123">説明</span><span class="sxs-lookup"><span data-stu-id="4e9b0-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4e9b0-124">\<ホスト ></span><span class="sxs-lookup"><span data-stu-id="4e9b0-124">\<host></span></span>](host.md)|<span data-ttu-id="4e9b0-125">サービス ホストの設定を指定する構成要素です。</span><span class="sxs-lookup"><span data-stu-id="4e9b0-125">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4e9b0-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="4e9b0-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="4e9b0-127">ホスティング</span><span class="sxs-lookup"><span data-stu-id="4e9b0-127">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
