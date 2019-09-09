---
title: <namedCaches> の <add> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
ms.openlocfilehash: 076d940e0c15cf48013480fef68b8fac42cf76e9
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252884"
---
# <a name="add-element-for-namedcaches"></a><span data-ttu-id="43141-102">\<namedCaches> の \<add> 要素</span><span class="sxs-lookup"><span data-stu-id="43141-102">\<add> Element for \<namedCaches></span></span>
<span data-ttu-id="43141-103">メモリキャッシュ`namedCache`の`namedCaches`コレクションにエントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="43141-103">Adds a `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
<span data-ttu-id="43141-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="43141-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="43141-105">&nbsp;&nbsp;[ **\<system.runtime.caching>** ](system-runtime-caching-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="43141-105">&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)</span></span>\
<span data-ttu-id="43141-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<memoryCache>** ](memorycache-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="43141-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)</span></span>\
<span data-ttu-id="43141-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<namedCaches>** ](namedcaches-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="43141-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)</span></span>\
<span data-ttu-id="43141-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<add>**</span><span class="sxs-lookup"><span data-stu-id="43141-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43141-109">構文</span><span class="sxs-lookup"><span data-stu-id="43141-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <add name="Default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="43141-110">型</span><span class="sxs-lookup"><span data-stu-id="43141-110">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="43141-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="43141-111">Attributes and Elements</span></span>  
 <span data-ttu-id="43141-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="43141-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="43141-113">属性</span><span class="sxs-lookup"><span data-stu-id="43141-113">Attributes</span></span>  
  
|<span data-ttu-id="43141-114">属性</span><span class="sxs-lookup"><span data-stu-id="43141-114">Attribute</span></span>|<span data-ttu-id="43141-115">説明</span><span class="sxs-lookup"><span data-stu-id="43141-115">Description</span></span>|  
|-|-|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="43141-116">のインスタンスを拡張<xref:System.Runtime.Caching.MemoryCache>できる最大許容サイズ (メガバイト単位) を指定する整数値。</span><span class="sxs-lookup"><span data-stu-id="43141-116">An integer value that specifies the maximum allowed size (in megabytes) that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="43141-117">既定値は0です。これは、 <xref:System.Runtime.Caching.MemoryCache>クラスの自動サイズ調整ヒューリスティックが既定で使用されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="43141-117">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="43141-118">キャッシュの名前。</span><span class="sxs-lookup"><span data-stu-id="43141-118">The name of the cache.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="43141-119">物理的にインストールされたコンピューターメモリのうち、キャッシュで使用できる最大パーセンテージを指定する 0 ~ 100 の整数値。</span><span class="sxs-lookup"><span data-stu-id="43141-119">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="43141-120">既定値は0です。これは、 <xref:System.Runtime.Caching.MemoryCache>クラスの自動サイズ調整ヒューリスティックが既定で使用されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="43141-120">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="43141-121">時間間隔を示す値。この値を超えると、キャッシュの実装によりキャッシュ インスタンスに設定されている絶対およびパーセントのメモリ制限と現在のメモリ負荷が比較されます。</span><span class="sxs-lookup"><span data-stu-id="43141-121">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="43141-122">この値は、"HH: MM: SS" 形式で入力します。</span><span class="sxs-lookup"><span data-stu-id="43141-122">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="43141-123">子要素</span><span class="sxs-lookup"><span data-stu-id="43141-123">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="43141-124">親要素</span><span class="sxs-lookup"><span data-stu-id="43141-124">Parent Elements</span></span>  
  
|<span data-ttu-id="43141-125">要素</span><span class="sxs-lookup"><span data-stu-id="43141-125">Element</span></span>|<span data-ttu-id="43141-126">説明</span><span class="sxs-lookup"><span data-stu-id="43141-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="43141-127">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="43141-127">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="43141-128">名前付き<xref:System.Runtime.Caching.MemoryCache>インスタンスの構成設定のコレクションを格納します。</span><span class="sxs-lookup"><span data-stu-id="43141-128">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="43141-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="43141-129">Remarks</span></span>  
 <span data-ttu-id="43141-130">要素`add`は、メモリキャッシュの`namedCaches`コレクションにエントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="43141-130">The `add` element adds an entry to the `namedCaches` collection for a memory cache.</span></span> <span data-ttu-id="43141-131">`add`要素を使用する前に[clear](clear-element-for-namedcaches.md)要素を使用して、コレクション内に他の名前付きキャッシュが存在しないことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="43141-131">You can use the [clear](clear-element-for-namedcaches.md) element before you use the `add` element to be certain that there are no other named caches in the collection.</span></span> <span data-ttu-id="43141-132">この要素は、machine.config ファイルと web.config ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="43141-132">This element can be used in the machine.config file and in the Web.config file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="43141-133">例</span><span class="sxs-lookup"><span data-stu-id="43141-133">Example</span></span>  
 <span data-ttu-id="43141-134">次の例は、メモリキャッシュの`namedCache` `namedCaches`コレクションに対する既定のエントリの設定を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="43141-134">The following example shows how to define settings for the default `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
```xml  
<configuration>  
  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="Default"   
               cacheMemoryLimitMegabytes="0"   
               physicalMemoryPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="43141-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="43141-135">See also</span></span>

- [<span data-ttu-id="43141-136">\<namedCaches> 要素 (キャッシュ設定)</span><span class="sxs-lookup"><span data-stu-id="43141-136">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
