---
title: <namedCaches> の <clear> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
ms.openlocfilehash: bcc0e23f0c47ad3a98430e36da31d39612caa3c9
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252756"
---
# <a name="clear-element-for-namedcaches"></a><span data-ttu-id="bf0d8-102">\<namedCaches> の \<clear> 要素</span><span class="sxs-lookup"><span data-stu-id="bf0d8-102">\<clear> Element for \<namedCaches></span></span>
<span data-ttu-id="bf0d8-103">メモリキャッシュ`namedCache`の`namedCaches`コレクション内のすべてのエントリをクリアします。</span><span class="sxs-lookup"><span data-stu-id="bf0d8-103">Clears all `namedCache` entries in the `namedCaches` collection for a memory cache.</span></span>  
  
<span data-ttu-id="bf0d8-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="bf0d8-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="bf0d8-105">&nbsp;&nbsp;[ **\<> のキャッシュ**](system-runtime-caching-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="bf0d8-105">&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)</span></span>\
<span data-ttu-id="bf0d8-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<memoryCache >** ](memorycache-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="bf0d8-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)</span></span>\
<span data-ttu-id="bf0d8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<namedCaches >** ](namedcaches-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="bf0d8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)</span></span>\
<span data-ttu-id="bf0d8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<クリア >**</span><span class="sxs-lookup"><span data-stu-id="bf0d8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf0d8-109">構文</span><span class="sxs-lookup"><span data-stu-id="bf0d8-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <clear name="Default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="bf0d8-110">型</span><span class="sxs-lookup"><span data-stu-id="bf0d8-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bf0d8-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="bf0d8-111">Attributes and Elements</span></span>  
 <span data-ttu-id="bf0d8-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="bf0d8-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bf0d8-113">属性</span><span class="sxs-lookup"><span data-stu-id="bf0d8-113">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="bf0d8-114">子要素</span><span class="sxs-lookup"><span data-stu-id="bf0d8-114">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="bf0d8-115">親要素</span><span class="sxs-lookup"><span data-stu-id="bf0d8-115">Parent Elements</span></span>  
  
|<span data-ttu-id="bf0d8-116">要素</span><span class="sxs-lookup"><span data-stu-id="bf0d8-116">Element</span></span>|<span data-ttu-id="bf0d8-117">説明</span><span class="sxs-lookup"><span data-stu-id="bf0d8-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bf0d8-118">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="bf0d8-118">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="bf0d8-119">名前付き<xref:System.Runtime.Caching.MemoryCache>インスタンスの構成設定のコレクションを格納します。</span><span class="sxs-lookup"><span data-stu-id="bf0d8-119">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf0d8-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="bf0d8-120">Remarks</span></span>  
 <span data-ttu-id="bf0d8-121">要素`clear`は、メモリ`namedCache`キャッシュの名前付きキャッシュコレクション内のすべてのエントリをクリアします。</span><span class="sxs-lookup"><span data-stu-id="bf0d8-121">The `clear` element clears all `namedCache` entries in the named cache collection for a memory cache.</span></span> <span data-ttu-id="bf0d8-122">要素を使用し`clear`て、コレクション内に`add`他の名前付きキャッシュが存在しないことを特定するために、要素を使用して新しい名前付きキャッシュエントリを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="bf0d8-122">You can use the `clear` element before you use the `add` element to add a new named cache entry in order to be certain there are no other named caches in the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf0d8-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="bf0d8-123">See also</span></span>

- [<span data-ttu-id="bf0d8-124">\<namedCaches > 要素 (キャッシュ設定)</span><span class="sxs-lookup"><span data-stu-id="bf0d8-124">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
