---
title: <add> の <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
ms.openlocfilehash: d75142209ad8706d0cad5ce188d9d991a5e881bc
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850581"
---
# <a name="add-of-baseaddresses"></a><span data-ttu-id="2065d-102">\<baseaddresses の\<> を追加 ></span><span class="sxs-lookup"><span data-stu-id="2065d-102">\<add> of \<baseAddresses></span></span>
<span data-ttu-id="2065d-103">サービス ホストによって使用されるベース アドレスを指定する構成要素を表します。</span><span class="sxs-lookup"><span data-stu-id="2065d-103">Represents a configuration element that specifies the base addresses used by the service host.</span></span>  
  
<span data-ttu-id="2065d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2065d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2065d-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2065d-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2065d-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<サービス >** ](services.md)</span><span class="sxs-lookup"><span data-stu-id="2065d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)</span></span>\
<span data-ttu-id="2065d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<サービス >** ](service.md)</span><span class="sxs-lookup"><span data-stu-id="2065d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)</span></span>\
<span data-ttu-id="2065d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ホスト >** ](host.md)</span><span class="sxs-lookup"><span data-stu-id="2065d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)</span></span>\
<span data-ttu-id="2065d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<baseAddresses >** ](baseaddresses.md)</span><span class="sxs-lookup"><span data-stu-id="2065d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<baseAddresses>**](baseaddresses.md)</span></span>\
<span data-ttu-id="2065d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> の追加**</span><span class="sxs-lookup"><span data-stu-id="2065d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2065d-111">構文</span><span class="sxs-lookup"><span data-stu-id="2065d-111">Syntax</span></span>  
  
```xml  
<add baseAddress="string" />
```  
  
## <a name="type"></a><span data-ttu-id="2065d-112">型</span><span class="sxs-lookup"><span data-stu-id="2065d-112">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2065d-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="2065d-113">Attributes and Elements</span></span>  
 <span data-ttu-id="2065d-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2065d-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2065d-115">属性</span><span class="sxs-lookup"><span data-stu-id="2065d-115">Attributes</span></span>  
  
|<span data-ttu-id="2065d-116">属性</span><span class="sxs-lookup"><span data-stu-id="2065d-116">Attribute</span></span>|<span data-ttu-id="2065d-117">説明</span><span class="sxs-lookup"><span data-stu-id="2065d-117">Description</span></span>|  
|---------------|-----------------|  
|`baseAddress`|<span data-ttu-id="2065d-118">サービス ホストによって使用されるベース アドレスを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="2065d-118">A string that specifies a base address used by the service host.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2065d-119">子要素</span><span class="sxs-lookup"><span data-stu-id="2065d-119">Child Elements</span></span>  
 <span data-ttu-id="2065d-120">なし。</span><span class="sxs-lookup"><span data-stu-id="2065d-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2065d-121">親要素</span><span class="sxs-lookup"><span data-stu-id="2065d-121">Parent Elements</span></span>  
  
|<span data-ttu-id="2065d-122">要素</span><span class="sxs-lookup"><span data-stu-id="2065d-122">Element</span></span>|<span data-ttu-id="2065d-123">説明</span><span class="sxs-lookup"><span data-stu-id="2065d-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2065d-124">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="2065d-124">\<baseAddresses></span></span>](baseaddresses.md)|<span data-ttu-id="2065d-125">`baseAddress` 要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="2065d-125">A collection of `baseAddress` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2065d-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="2065d-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="2065d-127">ホスティング</span><span class="sxs-lookup"><span data-stu-id="2065d-127">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
