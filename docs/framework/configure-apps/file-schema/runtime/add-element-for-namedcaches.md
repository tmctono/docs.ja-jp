---
title: <namedCaches> の <add> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
ms.openlocfilehash: fd6668a551663470a97b07ff131710dbe92a91f5
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659027"
---
# <a name="add-element-for-namedcaches"></a><span data-ttu-id="e3a26-102">\<namedCaches> の \<add> 要素</span><span class="sxs-lookup"><span data-stu-id="e3a26-102">\<add> Element for \<namedCaches></span></span>
<span data-ttu-id="e3a26-103">メモリキャッシュ`namedCache`の`namedCaches`コレクションにエントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="e3a26-103">Adds a `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="e3a26-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="e3a26-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="e3a26-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="e3a26-105">\<memoryCache></span></span>  
<span data-ttu-id="e3a26-106">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="e3a26-106">\<namedCaches></span></span>  
<span data-ttu-id="e3a26-107">\<add></span><span class="sxs-lookup"><span data-stu-id="e3a26-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3a26-108">構文</span><span class="sxs-lookup"><span data-stu-id="e3a26-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <add name="Default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="e3a26-109">型</span><span class="sxs-lookup"><span data-stu-id="e3a26-109">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e3a26-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e3a26-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e3a26-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e3a26-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e3a26-112">属性</span><span class="sxs-lookup"><span data-stu-id="e3a26-112">Attributes</span></span>  
  
|<span data-ttu-id="e3a26-113">属性</span><span class="sxs-lookup"><span data-stu-id="e3a26-113">Attribute</span></span>|<span data-ttu-id="e3a26-114">説明</span><span class="sxs-lookup"><span data-stu-id="e3a26-114">Description</span></span>|  
|-|-|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="e3a26-115">のインスタンスを拡張<xref:System.Runtime.Caching.MemoryCache>できる最大許容サイズ (メガバイト単位) を指定する整数値。</span><span class="sxs-lookup"><span data-stu-id="e3a26-115">An integer value that specifies the maximum allowed size (in megabytes) that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="e3a26-116">既定値は0です。これは、 <xref:System.Runtime.Caching.MemoryCache>クラスの自動サイズ調整ヒューリスティックが既定で使用されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="e3a26-116">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="e3a26-117">キャッシュの名前。</span><span class="sxs-lookup"><span data-stu-id="e3a26-117">The name of the cache.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="e3a26-118">物理的にインストールされたコンピューターメモリのうち、キャッシュで使用できる最大パーセンテージを指定する 0 ~ 100 の整数値。</span><span class="sxs-lookup"><span data-stu-id="e3a26-118">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="e3a26-119">既定値は0です。これは、 <xref:System.Runtime.Caching.MemoryCache>クラスの自動サイズ調整ヒューリスティックが既定で使用されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="e3a26-119">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="e3a26-120">時間間隔を示す値。この値を超えると、キャッシュの実装によりキャッシュ インスタンスに設定されている絶対およびパーセントのメモリ制限と現在のメモリ負荷が比較されます。</span><span class="sxs-lookup"><span data-stu-id="e3a26-120">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="e3a26-121">この値は、"HH: MM: SS" 形式で入力します。</span><span class="sxs-lookup"><span data-stu-id="e3a26-121">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e3a26-122">子要素</span><span class="sxs-lookup"><span data-stu-id="e3a26-122">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="e3a26-123">親要素</span><span class="sxs-lookup"><span data-stu-id="e3a26-123">Parent Elements</span></span>  
  
|<span data-ttu-id="e3a26-124">要素</span><span class="sxs-lookup"><span data-stu-id="e3a26-124">Element</span></span>|<span data-ttu-id="e3a26-125">説明</span><span class="sxs-lookup"><span data-stu-id="e3a26-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e3a26-126">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="e3a26-126">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="e3a26-127">名前付き<xref:System.Runtime.Caching.MemoryCache>インスタンスの構成設定のコレクションを格納します。</span><span class="sxs-lookup"><span data-stu-id="e3a26-127">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e3a26-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="e3a26-128">Remarks</span></span>  
 <span data-ttu-id="e3a26-129">要素`add`は、メモリキャッシュの`namedCaches`コレクションにエントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="e3a26-129">The `add` element adds an entry to the `namedCaches` collection for a memory cache.</span></span> <span data-ttu-id="e3a26-130">`add`要素を使用する前に[clear](clear-element-for-namedcaches.md)要素を使用して、コレクション内に他の名前付きキャッシュが存在しないことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="e3a26-130">You can use the [clear](clear-element-for-namedcaches.md) element before you use the `add` element to be certain that there are no other named caches in the collection.</span></span> <span data-ttu-id="e3a26-131">この要素は、machine.config ファイルと web.config ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="e3a26-131">This element can be used in the machine.config file and in the Web.config file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e3a26-132">例</span><span class="sxs-lookup"><span data-stu-id="e3a26-132">Example</span></span>  
 <span data-ttu-id="e3a26-133">次の例は、メモリキャッシュの`namedCache` `namedCaches`コレクションに対する既定のエントリの設定を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e3a26-133">The following example shows how to define settings for the default `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e3a26-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="e3a26-134">See also</span></span>

- [<span data-ttu-id="e3a26-135">\<namedCaches > 要素 (キャッシュ設定)</span><span class="sxs-lookup"><span data-stu-id="e3a26-135">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
