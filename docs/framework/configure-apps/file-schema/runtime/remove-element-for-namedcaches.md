---
title: <namedCaches> の <remove> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
ms.openlocfilehash: e9b126cee83bc8109606d915ea48549beea970c9
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663468"
---
# <a name="remove-element-for-namedcaches"></a><span data-ttu-id="bb359-102">\<namedCaches> の \<remove> 要素</span><span class="sxs-lookup"><span data-stu-id="bb359-102">\<remove> Element for \<namedCaches></span></span>
<span data-ttu-id="bb359-103">名前付きキャッシュ エントリを、メモリ キャッシュの `namedCaches` コレクションから削除します。</span><span class="sxs-lookup"><span data-stu-id="bb359-103">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="bb359-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="bb359-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="bb359-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="bb359-105">\<memoryCache></span></span>  
<span data-ttu-id="bb359-106">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="bb359-106">\<namedCaches></span></span>  
<span data-ttu-id="bb359-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="bb359-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb359-108">構文</span><span class="sxs-lookup"><span data-stu-id="bb359-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="bb359-109">型</span><span class="sxs-lookup"><span data-stu-id="bb359-109">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bb359-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="bb359-110">Attributes and Elements</span></span>  
 <span data-ttu-id="bb359-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="bb359-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bb359-112">属性</span><span class="sxs-lookup"><span data-stu-id="bb359-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="bb359-113">子要素</span><span class="sxs-lookup"><span data-stu-id="bb359-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="bb359-114">親要素</span><span class="sxs-lookup"><span data-stu-id="bb359-114">Parent Elements</span></span>  
  
|<span data-ttu-id="bb359-115">要素</span><span class="sxs-lookup"><span data-stu-id="bb359-115">Element</span></span>|<span data-ttu-id="bb359-116">説明</span><span class="sxs-lookup"><span data-stu-id="bb359-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bb359-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="bb359-117">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="bb359-118">名前付き<xref:System.Runtime.Caching.MemoryCache>インスタンスの構成設定のコレクションを格納します。</span><span class="sxs-lookup"><span data-stu-id="bb359-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb359-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="bb359-119">Remarks</span></span>  
 <span data-ttu-id="bb359-120">要素`remove`は、メモリ`namedCache`キャッシュの名前付きキャッシュコレクションからエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="bb359-120">The `remove` element removes a `namedCache` entry from the named cache collection for a memory cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb359-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="bb359-121">See also</span></span>

- [<span data-ttu-id="bb359-122">\<namedCaches > 要素 (キャッシュ設定)</span><span class="sxs-lookup"><span data-stu-id="bb359-122">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
