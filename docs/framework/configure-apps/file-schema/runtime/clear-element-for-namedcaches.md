---
title: <namedCaches> の <clear> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
ms.openlocfilehash: a90970e468359714bbbb858f3f300c26b5757a4d
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69658859"
---
# <a name="clear-element-for-namedcaches"></a><span data-ttu-id="6a573-102">\<namedCaches> の \<clear> 要素</span><span class="sxs-lookup"><span data-stu-id="6a573-102">\<clear> Element for \<namedCaches></span></span>
<span data-ttu-id="6a573-103">メモリキャッシュ`namedCache`の`namedCaches`コレクション内のすべてのエントリをクリアします。</span><span class="sxs-lookup"><span data-stu-id="6a573-103">Clears all `namedCache` entries in the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="6a573-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="6a573-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="6a573-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="6a573-105">\<memoryCache></span></span>  
<span data-ttu-id="6a573-106">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="6a573-106">\<namedCaches></span></span>  
<span data-ttu-id="6a573-107">\<add></span><span class="sxs-lookup"><span data-stu-id="6a573-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a573-108">構文</span><span class="sxs-lookup"><span data-stu-id="6a573-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <clear name="Default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="6a573-109">型</span><span class="sxs-lookup"><span data-stu-id="6a573-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6a573-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="6a573-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6a573-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="6a573-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6a573-112">属性</span><span class="sxs-lookup"><span data-stu-id="6a573-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="6a573-113">子要素</span><span class="sxs-lookup"><span data-stu-id="6a573-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="6a573-114">親要素</span><span class="sxs-lookup"><span data-stu-id="6a573-114">Parent Elements</span></span>  
  
|<span data-ttu-id="6a573-115">要素</span><span class="sxs-lookup"><span data-stu-id="6a573-115">Element</span></span>|<span data-ttu-id="6a573-116">説明</span><span class="sxs-lookup"><span data-stu-id="6a573-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6a573-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="6a573-117">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="6a573-118">名前付き<xref:System.Runtime.Caching.MemoryCache>インスタンスの構成設定のコレクションを格納します。</span><span class="sxs-lookup"><span data-stu-id="6a573-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a573-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="6a573-119">Remarks</span></span>  
 <span data-ttu-id="6a573-120">要素`clear`は、メモリ`namedCache`キャッシュの名前付きキャッシュコレクション内のすべてのエントリをクリアします。</span><span class="sxs-lookup"><span data-stu-id="6a573-120">The `clear` element clears all `namedCache` entries in the named cache collection for a memory cache.</span></span> <span data-ttu-id="6a573-121">要素を使用し`clear`て、コレクション内に`add`他の名前付きキャッシュが存在しないことを特定するために、要素を使用して新しい名前付きキャッシュエントリを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="6a573-121">You can use the `clear` element before you use the `add` element to add a new named cache entry in order to be certain there are no other named caches in the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a573-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="6a573-122">See also</span></span>

- [<span data-ttu-id="6a573-123">\<namedCaches > 要素 (キャッシュ設定)</span><span class="sxs-lookup"><span data-stu-id="6a573-123">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
