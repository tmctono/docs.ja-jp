---
title: <namedCaches> の <remove> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
ms.openlocfilehash: 991ad0eb9c04c27ded4d566115107ac7b47a71e1
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252337"
---
# <a name="remove-element-for-namedcaches"></a><span data-ttu-id="641c6-102">\<namedCaches> の \<remove> 要素</span><span class="sxs-lookup"><span data-stu-id="641c6-102">\<remove> Element for \<namedCaches></span></span>
<span data-ttu-id="641c6-103">名前付きキャッシュ エントリを、メモリ キャッシュの `namedCaches` コレクションから削除します。</span><span class="sxs-lookup"><span data-stu-id="641c6-103">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>  
  
<span data-ttu-id="641c6-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="641c6-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="641c6-105">&nbsp;&nbsp;[ **\<> のキャッシュ**](system-runtime-caching-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="641c6-105">&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)</span></span>\
<span data-ttu-id="641c6-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<memoryCache >** ](memorycache-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="641c6-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)</span></span>\
<span data-ttu-id="641c6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<namedCaches >** ](namedcaches-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="641c6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)</span></span>\
<span data-ttu-id="641c6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> の削除**</span><span class="sxs-lookup"><span data-stu-id="641c6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="641c6-109">構文</span><span class="sxs-lookup"><span data-stu-id="641c6-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="641c6-110">型</span><span class="sxs-lookup"><span data-stu-id="641c6-110">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="641c6-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="641c6-111">Attributes and Elements</span></span>  
 <span data-ttu-id="641c6-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="641c6-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="641c6-113">属性</span><span class="sxs-lookup"><span data-stu-id="641c6-113">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="641c6-114">子要素</span><span class="sxs-lookup"><span data-stu-id="641c6-114">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="641c6-115">親要素</span><span class="sxs-lookup"><span data-stu-id="641c6-115">Parent Elements</span></span>  
  
|<span data-ttu-id="641c6-116">要素</span><span class="sxs-lookup"><span data-stu-id="641c6-116">Element</span></span>|<span data-ttu-id="641c6-117">説明</span><span class="sxs-lookup"><span data-stu-id="641c6-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="641c6-118">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="641c6-118">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="641c6-119">名前付き<xref:System.Runtime.Caching.MemoryCache>インスタンスの構成設定のコレクションを格納します。</span><span class="sxs-lookup"><span data-stu-id="641c6-119">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="641c6-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="641c6-120">Remarks</span></span>  
 <span data-ttu-id="641c6-121">要素`remove`は、メモリ`namedCache`キャッシュの名前付きキャッシュコレクションからエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="641c6-121">The `remove` element removes a `namedCache` entry from the named cache collection for a memory cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="641c6-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="641c6-122">See also</span></span>

- [<span data-ttu-id="641c6-123">\<namedCaches > 要素 (キャッシュ設定)</span><span class="sxs-lookup"><span data-stu-id="641c6-123">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
