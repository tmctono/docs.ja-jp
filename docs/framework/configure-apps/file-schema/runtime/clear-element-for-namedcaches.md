---
title: <namedCaches> の <clear> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
ms.openlocfilehash: eb0a50919e163a795abc70d132bd45f1d05192ec
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59146862"
---
# <a name="clear-element-for-namedcaches"></a><span data-ttu-id="9e769-102">\<クリア > 要素の\<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="9e769-102">\<clear> Element for \<namedCaches></span></span>
<span data-ttu-id="9e769-103">すべてクリア`namedCache`内のエントリ、`namedCaches`メモリ キャッシュのコレクション。</span><span class="sxs-lookup"><span data-stu-id="9e769-103">Clears all `namedCache` entries in the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="9e769-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="9e769-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="9e769-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="9e769-105">\<memoryCache></span></span>  
<span data-ttu-id="9e769-106">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="9e769-106">\<namedCaches></span></span>  
<span data-ttu-id="9e769-107">\<add></span><span class="sxs-lookup"><span data-stu-id="9e769-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e769-108">構文</span><span class="sxs-lookup"><span data-stu-id="9e769-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <clear name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="9e769-109">型</span><span class="sxs-lookup"><span data-stu-id="9e769-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9e769-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9e769-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9e769-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9e769-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9e769-112">属性</span><span class="sxs-lookup"><span data-stu-id="9e769-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="9e769-113">子要素</span><span class="sxs-lookup"><span data-stu-id="9e769-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="9e769-114">親要素</span><span class="sxs-lookup"><span data-stu-id="9e769-114">Parent Elements</span></span>  
  
|<span data-ttu-id="9e769-115">要素</span><span class="sxs-lookup"><span data-stu-id="9e769-115">Element</span></span>|<span data-ttu-id="9e769-116">説明</span><span class="sxs-lookup"><span data-stu-id="9e769-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9e769-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="9e769-117">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="9e769-118">名前付きの構成設定のコレクションを含む<xref:System.Runtime.Caching.MemoryCache>インスタンス。</span><span class="sxs-lookup"><span data-stu-id="9e769-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e769-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="9e769-119">Remarks</span></span>  
 <span data-ttu-id="9e769-120">`clear`要素がすべてクリア`namedCache`メモリ キャッシュの名前付きキャッシュのコレクション内のエントリ。</span><span class="sxs-lookup"><span data-stu-id="9e769-120">The `clear` element clears all `namedCache` entries in the named cache collection for a memory cache.</span></span> <span data-ttu-id="9e769-121">使用することができます、`clear`要素を使用する前に、`add`が他にないを特定するためには新しい名前付きキャッシュ エントリを追加する要素がコレクション内のキャッシュをという名前です。</span><span class="sxs-lookup"><span data-stu-id="9e769-121">You can use the `clear` element before you use the `add` element to add a new named cache entry in order to be certain there are no other named caches in the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e769-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="9e769-122">See also</span></span>

- [<span data-ttu-id="9e769-123">\<namedCaches > 要素 (キャッシュ設定)</span><span class="sxs-lookup"><span data-stu-id="9e769-123">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
