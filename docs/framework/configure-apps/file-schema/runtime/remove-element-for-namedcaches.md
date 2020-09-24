---
title: <namedCaches> の <remove> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
ms.openlocfilehash: c8ad5a0ce6d7a3059943b3962b9255385cea6e15
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183989"
---
# <a name="remove-element-for-namedcaches"></a><span data-ttu-id="a124a-102">\<namedCaches> の \<remove> 要素</span><span class="sxs-lookup"><span data-stu-id="a124a-102">\<remove> Element for \<namedCaches></span></span>

<span data-ttu-id="a124a-103">名前付きキャッシュ エントリを、メモリ キャッシュの `namedCaches` コレクションから削除します。</span><span class="sxs-lookup"><span data-stu-id="a124a-103">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**  
  
## <a name="syntax"></a><span data-ttu-id="a124a-104">構文</span><span class="sxs-lookup"><span data-stu-id="a124a-104">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="a124a-105">種類</span><span class="sxs-lookup"><span data-stu-id="a124a-105">Type</span></span>  

 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a124a-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a124a-106">Attributes and Elements</span></span>  

 <span data-ttu-id="a124a-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a124a-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a124a-108">属性</span><span class="sxs-lookup"><span data-stu-id="a124a-108">Attributes</span></span>  

 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="a124a-109">子要素</span><span class="sxs-lookup"><span data-stu-id="a124a-109">Child Elements</span></span>  

 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="a124a-110">親要素</span><span class="sxs-lookup"><span data-stu-id="a124a-110">Parent Elements</span></span>  
  
|<span data-ttu-id="a124a-111">要素</span><span class="sxs-lookup"><span data-stu-id="a124a-111">Element</span></span>|<span data-ttu-id="a124a-112">説明</span><span class="sxs-lookup"><span data-stu-id="a124a-112">Description</span></span>|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|<span data-ttu-id="a124a-113">名前付きインスタンスの構成設定のコレクションを格納 <xref:System.Runtime.Caching.MemoryCache> します。</span><span class="sxs-lookup"><span data-stu-id="a124a-113">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a124a-114">解説</span><span class="sxs-lookup"><span data-stu-id="a124a-114">Remarks</span></span>  

 <span data-ttu-id="a124a-115">要素は、 `remove` `namedCache` メモリキャッシュの名前付きキャッシュコレクションからエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="a124a-115">The `remove` element removes a `namedCache` entry from the named cache collection for a memory cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a124a-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="a124a-116">See also</span></span>

- [<span data-ttu-id="a124a-117">\<namedCaches> 要素 (キャッシュ設定)</span><span class="sxs-lookup"><span data-stu-id="a124a-117">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
