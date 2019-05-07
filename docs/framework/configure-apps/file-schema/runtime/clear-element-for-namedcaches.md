---
title: <namedCaches> の <clear> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
ms.openlocfilehash: eb0a50919e163a795abc70d132bd45f1d05192ec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674169"
---
# <a name="clear-element-for-namedcaches"></a><span data-ttu-id="2f366-102">\<namedCaches> の \<clear> 要素</span><span class="sxs-lookup"><span data-stu-id="2f366-102">\<clear> Element for \<namedCaches></span></span>
<span data-ttu-id="2f366-103">すべてクリア`namedCache`内のエントリ、`namedCaches`メモリ キャッシュのコレクション。</span><span class="sxs-lookup"><span data-stu-id="2f366-103">Clears all `namedCache` entries in the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="2f366-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="2f366-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="2f366-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="2f366-105">\<memoryCache></span></span>  
<span data-ttu-id="2f366-106">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="2f366-106">\<namedCaches></span></span>  
<span data-ttu-id="2f366-107">\<add></span><span class="sxs-lookup"><span data-stu-id="2f366-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f366-108">構文</span><span class="sxs-lookup"><span data-stu-id="2f366-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <clear name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="2f366-109">型</span><span class="sxs-lookup"><span data-stu-id="2f366-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2f366-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="2f366-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2f366-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2f366-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2f366-112">属性</span><span class="sxs-lookup"><span data-stu-id="2f366-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="2f366-113">子要素</span><span class="sxs-lookup"><span data-stu-id="2f366-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="2f366-114">親要素</span><span class="sxs-lookup"><span data-stu-id="2f366-114">Parent Elements</span></span>  
  
|<span data-ttu-id="2f366-115">要素</span><span class="sxs-lookup"><span data-stu-id="2f366-115">Element</span></span>|<span data-ttu-id="2f366-116">説明</span><span class="sxs-lookup"><span data-stu-id="2f366-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2f366-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="2f366-117">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="2f366-118">名前付きの構成設定のコレクションを含む<xref:System.Runtime.Caching.MemoryCache>インスタンス。</span><span class="sxs-lookup"><span data-stu-id="2f366-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f366-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="2f366-119">Remarks</span></span>  
 <span data-ttu-id="2f366-120">`clear`要素がすべてクリア`namedCache`メモリ キャッシュの名前付きキャッシュのコレクション内のエントリ。</span><span class="sxs-lookup"><span data-stu-id="2f366-120">The `clear` element clears all `namedCache` entries in the named cache collection for a memory cache.</span></span> <span data-ttu-id="2f366-121">使用することができます、`clear`要素を使用する前に、`add`が他にないを特定するためには新しい名前付きキャッシュ エントリを追加する要素がコレクション内のキャッシュをという名前です。</span><span class="sxs-lookup"><span data-stu-id="2f366-121">You can use the `clear` element before you use the `add` element to add a new named cache entry in order to be certain there are no other named caches in the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f366-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="2f366-122">See also</span></span>

- [<span data-ttu-id="2f366-123">\<namedCaches > 要素 (キャッシュ設定)</span><span class="sxs-lookup"><span data-stu-id="2f366-123">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
