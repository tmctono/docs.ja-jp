---
title: <namedCaches> の <clear> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
ms.openlocfilehash: bcc0e23f0c47ad3a98430e36da31d39612caa3c9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252756"
---
# <a name="clear-element-for-namedcaches"></a><span data-ttu-id="d2dd9-102">\<namedCaches> の \<clear> 要素</span><span class="sxs-lookup"><span data-stu-id="d2dd9-102">\<clear> Element for \<namedCaches></span></span>
<span data-ttu-id="d2dd9-103">`namedCache`メモリキャッシュのコレクション内のすべてのエントリをクリア `namedCaches` します。</span><span class="sxs-lookup"><span data-stu-id="d2dd9-103">Clears all `namedCache` entries in the `namedCaches` collection for a memory cache.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**  
  
## <a name="syntax"></a><span data-ttu-id="d2dd9-104">構文</span><span class="sxs-lookup"><span data-stu-id="d2dd9-104">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <clear name="Default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="d2dd9-105">Type</span><span class="sxs-lookup"><span data-stu-id="d2dd9-105">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d2dd9-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d2dd9-106">Attributes and Elements</span></span>  
 <span data-ttu-id="d2dd9-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d2dd9-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d2dd9-108">属性</span><span class="sxs-lookup"><span data-stu-id="d2dd9-108">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="d2dd9-109">子要素</span><span class="sxs-lookup"><span data-stu-id="d2dd9-109">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="d2dd9-110">親要素</span><span class="sxs-lookup"><span data-stu-id="d2dd9-110">Parent Elements</span></span>  
  
|<span data-ttu-id="d2dd9-111">要素</span><span class="sxs-lookup"><span data-stu-id="d2dd9-111">Element</span></span>|<span data-ttu-id="d2dd9-112">説明</span><span class="sxs-lookup"><span data-stu-id="d2dd9-112">Description</span></span>|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|<span data-ttu-id="d2dd9-113">名前付きインスタンスの構成設定のコレクションを格納 <xref:System.Runtime.Caching.MemoryCache> します。</span><span class="sxs-lookup"><span data-stu-id="d2dd9-113">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2dd9-114">解説</span><span class="sxs-lookup"><span data-stu-id="d2dd9-114">Remarks</span></span>  
 <span data-ttu-id="d2dd9-115">要素は、 `clear` `namedCache` メモリキャッシュの名前付きキャッシュコレクション内のすべてのエントリをクリアします。</span><span class="sxs-lookup"><span data-stu-id="d2dd9-115">The `clear` element clears all `namedCache` entries in the named cache collection for a memory cache.</span></span> <span data-ttu-id="d2dd9-116">要素を使用して、 `clear` `add` コレクション内に他の名前付きキャッシュが存在しないことを特定するために、要素を使用して新しい名前付きキャッシュエントリを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="d2dd9-116">You can use the `clear` element before you use the `add` element to add a new named cache entry in order to be certain there are no other named caches in the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2dd9-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="d2dd9-117">See also</span></span>

- [<span data-ttu-id="d2dd9-118">\<namedCaches>要素 (キャッシュ設定)</span><span class="sxs-lookup"><span data-stu-id="d2dd9-118">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
