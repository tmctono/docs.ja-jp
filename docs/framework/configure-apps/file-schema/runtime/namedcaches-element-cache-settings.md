---
title: <namedCaches> 要素 (キャッシュ設定)
ms.date: 03/30/2017
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
ms.openlocfilehash: 9cedd462aa539745ddab844dff158912914cb024
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663576"
---
# <a name="namedcaches-element-cache-settings"></a><span data-ttu-id="d6a04-102">\<namedCaches > 要素 (キャッシュ設定)</span><span class="sxs-lookup"><span data-stu-id="d6a04-102">\<namedCaches> Element (Cache Settings)</span></span>
<span data-ttu-id="d6a04-103">名前付き<xref:System.Runtime.Caching.MemoryCache>インスタンスの構成設定のコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="d6a04-103">Specifies a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span> <span data-ttu-id="d6a04-104">プロパティ<xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A>は、構成ファイルの1つ`namedCaches`以上の要素から構成設定のコレクションを参照します。</span><span class="sxs-lookup"><span data-stu-id="d6a04-104">The <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> property references the collection of configuration settings from one or more `namedCaches` elements of the configuration file.</span></span>  
  
 <span data-ttu-id="d6a04-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d6a04-105">\<configuration></span></span>  
<span data-ttu-id="d6a04-106">\<> のキャッシュ</span><span class="sxs-lookup"><span data-stu-id="d6a04-106">\< system.runtime.caching></span></span>  
<span data-ttu-id="d6a04-107">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="d6a04-107">\<memoryCache></span></span>  
<span data-ttu-id="d6a04-108">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="d6a04-108">\<namedCaches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6a04-109">構文</span><span class="sxs-lookup"><span data-stu-id="d6a04-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
  <add name="default"/>   
</namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="d6a04-110">型</span><span class="sxs-lookup"><span data-stu-id="d6a04-110">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d6a04-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d6a04-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d6a04-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d6a04-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d6a04-113">属性</span><span class="sxs-lookup"><span data-stu-id="d6a04-113">Attributes</span></span>  
  
|<span data-ttu-id="d6a04-114">属性</span><span class="sxs-lookup"><span data-stu-id="d6a04-114">Attribute</span></span>|<span data-ttu-id="d6a04-115">説明</span><span class="sxs-lookup"><span data-stu-id="d6a04-115">Description</span></span>|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|<span data-ttu-id="d6a04-116">のインスタンスを拡張<xref:System.Runtime.Caching.MemoryCache>できる最大許容サイズを mb 単位で指定する整数値。</span><span class="sxs-lookup"><span data-stu-id="d6a04-116">An integer value that specifies the maximum allowable size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="d6a04-117">既定値は0です。これは、 <xref:System.Runtime.Caching.MemoryCache>クラスの自動サイズ調整ヒューリスティックが既定で使用されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="d6a04-117">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`name`|<span data-ttu-id="d6a04-118">キャッシュの名前。</span><span class="sxs-lookup"><span data-stu-id="d6a04-118">The name of the cache.</span></span>|  
|`physicalMemoryLimitPercentage`|<span data-ttu-id="d6a04-119">物理的にインストールされたコンピューターメモリのうち、キャッシュで使用できる最大パーセンテージを指定する 0 ~ 100 の整数値。</span><span class="sxs-lookup"><span data-stu-id="d6a04-119">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="d6a04-120">既定値は0です。これは、 <xref:System.Runtime.Caching.MemoryCache>クラスの自動サイズ調整ヒューリスティックが既定で使用されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="d6a04-120">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`pollingInterval`|<span data-ttu-id="d6a04-121">時間間隔を示す値。この値を超えると、キャッシュの実装によりキャッシュ インスタンスに設定されている絶対およびパーセントのメモリ制限と現在のメモリ負荷が比較されます。</span><span class="sxs-lookup"><span data-stu-id="d6a04-121">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="d6a04-122">この値は、"HH: MM: SS" 形式で入力します。</span><span class="sxs-lookup"><span data-stu-id="d6a04-122">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d6a04-123">子要素</span><span class="sxs-lookup"><span data-stu-id="d6a04-123">Child Elements</span></span>  
  
|<span data-ttu-id="d6a04-124">要素</span><span class="sxs-lookup"><span data-stu-id="d6a04-124">Element</span></span>|<span data-ttu-id="d6a04-125">説明</span><span class="sxs-lookup"><span data-stu-id="d6a04-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d6a04-126">\<add></span><span class="sxs-lookup"><span data-stu-id="d6a04-126">\<add></span></span>](add-element-for-namedcaches.md)|<span data-ttu-id="d6a04-127">名前付きキャッシュを、メモリ キャッシュの `namedCaches` コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="d6a04-127">Adds a named cache to the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="d6a04-128">\<clear></span><span class="sxs-lookup"><span data-stu-id="d6a04-128">\<clear></span></span>](clear-element-for-namedcaches.md)|<span data-ttu-id="d6a04-129">メモリ キャッシュの `namedCaches` コレクションを消去します。</span><span class="sxs-lookup"><span data-stu-id="d6a04-129">Clears the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="d6a04-130">\<remove></span><span class="sxs-lookup"><span data-stu-id="d6a04-130">\<remove></span></span>](remove-element-for-namedcaches.md)|<span data-ttu-id="d6a04-131">名前付きキャッシュ エントリを、メモリ キャッシュの `namedCaches` コレクションから削除します。</span><span class="sxs-lookup"><span data-stu-id="d6a04-131">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d6a04-132">親要素</span><span class="sxs-lookup"><span data-stu-id="d6a04-132">Parent Elements</span></span>  
  
|<span data-ttu-id="d6a04-133">要素</span><span class="sxs-lookup"><span data-stu-id="d6a04-133">Element</span></span>|<span data-ttu-id="d6a04-134">説明</span><span class="sxs-lookup"><span data-stu-id="d6a04-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d6a04-135">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="d6a04-135">\<memoryCache></span></span>](memorycache-element-cache-settings.md)|<span data-ttu-id="d6a04-136"><xref:System.Runtime.Caching.MemoryCache> クラスに基づくキャッシュを構成するために使用される要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="d6a04-136">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6a04-137">Remarks</span><span class="sxs-lookup"><span data-stu-id="d6a04-137">Remarks</span></span>  
 <span data-ttu-id="d6a04-138">Web.config ファイルのメモリキャッシュ構成セクションに`add`は、 `namedCaches`コレクションの、 `remove`、 `clear`の各属性を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d6a04-138">The memory cache configuration section of the Web.config file can contain `add`, `remove`, and `clear` attributes for the `namedCaches` collection.</span></span> <span data-ttu-id="d6a04-139">各`namedCaches`エントリは、 `name`属性によって一意に識別されます。</span><span class="sxs-lookup"><span data-stu-id="d6a04-139">Each `namedCaches` entry is uniquely identified by the `name` attribute.</span></span>  
  
 <span data-ttu-id="d6a04-140">メモリキャッシュエントリのインスタンスを取得するには、アプリケーション構成ファイル内の情報を参照します。</span><span class="sxs-lookup"><span data-stu-id="d6a04-140">You can retrieve instances of memory cache entries by referencing the information in the application configuration files.</span></span> <span data-ttu-id="d6a04-141">既定では、構成ファイルにエントリが存在するのは既定のキャッシュインスタンスだけです。</span><span class="sxs-lookup"><span data-stu-id="d6a04-141">By default, only the default cache instance has an entry in the configuration file.</span></span> <span data-ttu-id="d6a04-142">既定のキャッシュインスタンスは、 <xref:System.Runtime.Caching.MemoryCache.Default%2A>プロパティから返されるインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="d6a04-142">The default cache instance is the instance that is returned from the <xref:System.Runtime.Caching.MemoryCache.Default%2A> property.</span></span>  
  
 <span data-ttu-id="d6a04-143">Name 属性を "default" に設定した場合、要素は既定のメモリキャッシュインスタンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="d6a04-143">If you set the name attribute to "default", the element uses the default memory cache instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6a04-144">例</span><span class="sxs-lookup"><span data-stu-id="d6a04-144">Example</span></span>  
 <span data-ttu-id="d6a04-145">次の例は、 `name`属性を "default" に設定することによって、キャッシュの名前を既定のキャッシュエントリ名に設定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d6a04-145">The following example shows how to set the name of the cache to the default cache entry name by setting the `name` attribute to "default".</span></span>  
  
 <span data-ttu-id="d6a04-146">`cacheMemoryLimitMegabytes` 属性および `physicalMemoryPercentage` 属性はゼロに設定されます。</span><span class="sxs-lookup"><span data-stu-id="d6a04-146">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="d6a04-147">これらの属性を0に設定すると、 <xref:System.Runtime.Caching.MemoryCache>クラスの自動サイズ調整ヒューリスティックが使用されます。</span><span class="sxs-lookup"><span data-stu-id="d6a04-147">Setting these attributes to zero means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used.</span></span> <span data-ttu-id="d6a04-148">キャッシュの実装では、現在のメモリ負荷と、絶対値および割合に基づくメモリ制限を2分ごとに比較します。</span><span class="sxs-lookup"><span data-stu-id="d6a04-148">The cache implementation compares the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
```xml  
<configuration>  
  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="default"   
               cacheMemoryLimitMegabytes="0"   
               physicalMemoryLimitPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d6a04-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="d6a04-149">See also</span></span>

- [<span data-ttu-id="d6a04-150">\<memoryCache > 要素 (キャッシュ設定)</span><span class="sxs-lookup"><span data-stu-id="d6a04-150">\<memoryCache> Element (Cache Settings)</span></span>](memorycache-element-cache-settings.md)
