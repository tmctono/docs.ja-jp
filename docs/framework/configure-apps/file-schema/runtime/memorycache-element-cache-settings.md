---
title: <memoryCache> 要素 (キャッシュ設定)
ms.date: 03/30/2017
helpviewer_keywords:
- <memoryCache> element
- caching [.NET Framework], configuration
- memoryCache element
ms.assetid: 182a622f-f7cf-472d-9d0b-451d2fd94525
ms.openlocfilehash: 14480682c5d221216df5da3844897855d1d92a0d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192426"
---
# <a name="memorycache-element-cache-settings"></a><span data-ttu-id="861d2-102">\<memoryCache> 要素 (キャッシュ設定)</span><span class="sxs-lookup"><span data-stu-id="861d2-102">\<memoryCache> Element (Cache Settings)</span></span>

<span data-ttu-id="861d2-103"><xref:System.Runtime.Caching.MemoryCache> クラスに基づくキャッシュを構成するために使用される要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="861d2-103">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span> <span data-ttu-id="861d2-104"><xref:System.Runtime.Caching.Configuration.MemoryCacheElement> クラスは、キャッシュの構成に使用できる [memoryCache](memorycache-element-cache-settings.md) 要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="861d2-104">The <xref:System.Runtime.Caching.Configuration.MemoryCacheElement> class defines a [memoryCache](memorycache-element-cache-settings.md) element that you can use to configure the cache.</span></span> <span data-ttu-id="861d2-105"><xref:System.Runtime.Caching.MemoryCache> クラスの複数のインスタンスを、単一のアプリケーションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="861d2-105">Multiple instances of the <xref:System.Runtime.Caching.MemoryCache> class can be used in a single application.</span></span> <span data-ttu-id="861d2-106">構成ファイル内の各 `memoryCache` 要素には、指定した <xref:System.Runtime.Caching.MemoryCache> インスタンスの設定を含むことができます。</span><span class="sxs-lookup"><span data-stu-id="861d2-106">Each `memoryCache` element in the configuration file can contain settings for a named <xref:System.Runtime.Caching.MemoryCache> instance.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<memoryCache>**  
  
## <a name="syntax"></a><span data-ttu-id="861d2-107">構文</span><span class="sxs-lookup"><span data-stu-id="861d2-107">Syntax</span></span>  
  
```xml  
<memoryCache>
    <namedCaches>  
        <!-- child elements -->  
    </namedCaches>
</memoryCache>  
```  
  
## <a name="type"></a><span data-ttu-id="861d2-108">種類</span><span class="sxs-lookup"><span data-stu-id="861d2-108">Type</span></span>  

 <span data-ttu-id="861d2-109"><xref:System.Runtime.Caching.MemoryCache> クラス。</span><span class="sxs-lookup"><span data-stu-id="861d2-109"><xref:System.Runtime.Caching.MemoryCache> class.</span></span>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="861d2-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="861d2-110">Attributes and Elements</span></span>  

 <span data-ttu-id="861d2-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="861d2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="861d2-112">属性</span><span class="sxs-lookup"><span data-stu-id="861d2-112">Attributes</span></span>  
  
|<span data-ttu-id="861d2-113">属性</span><span class="sxs-lookup"><span data-stu-id="861d2-113">Attribute</span></span>|<span data-ttu-id="861d2-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="861d2-114">Description</span></span>|  
|---------------|-----------------|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="861d2-115"><xref:System.Runtime.Caching.MemoryCache> オブジェクトのインスタンスを拡張できる最大メモリ サイズ (メガバイト)。</span><span class="sxs-lookup"><span data-stu-id="861d2-115">The maximum memory size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> object can grow to.</span></span> <span data-ttu-id="861d2-116">既定値は 0 であり、これは <xref:System.Runtime.Caching.MemoryCache> クラスの自動サイズ調整ヒューリスティックが既定で使用されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="861d2-116">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosize heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="861d2-117">キャッシュ構成の名前。</span><span class="sxs-lookup"><span data-stu-id="861d2-117">The name of the cache configuration.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="861d2-118">キャッシュが使用できる物理メモリの割合。</span><span class="sxs-lookup"><span data-stu-id="861d2-118">The percentage of physical memory that can be used by the cache.</span></span> <span data-ttu-id="861d2-119">既定値は 0 であり、これは <xref:System.Runtime.Caching.MemoryCache> クラスの自動サイズ調整ヒューリスティックが既定で使用されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="861d2-119">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosize heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="861d2-120">時間間隔を示す値。この値を超えると、キャッシュの実装によりキャッシュ インスタンスに設定されている絶対およびパーセントのメモリ制限と現在のメモリ負荷が比較されます。</span><span class="sxs-lookup"><span data-stu-id="861d2-120">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="861d2-121">値は "HH:MM:SS" 形式で入力します。</span><span class="sxs-lookup"><span data-stu-id="861d2-121">The value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="861d2-122">子要素</span><span class="sxs-lookup"><span data-stu-id="861d2-122">Child Elements</span></span>  
  
|<span data-ttu-id="861d2-123">要素</span><span class="sxs-lookup"><span data-stu-id="861d2-123">Element</span></span>|<span data-ttu-id="861d2-124">説明</span><span class="sxs-lookup"><span data-stu-id="861d2-124">Description</span></span>|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|<span data-ttu-id="861d2-125">`namedCache` インスタンスの構成設定のコレクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="861d2-125">Contains a collection of configuration settings for the `namedCache` instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="861d2-126">親要素</span><span class="sxs-lookup"><span data-stu-id="861d2-126">Parent Elements</span></span>  
  
|<span data-ttu-id="861d2-127">要素</span><span class="sxs-lookup"><span data-stu-id="861d2-127">Element</span></span>|<span data-ttu-id="861d2-128">説明</span><span class="sxs-lookup"><span data-stu-id="861d2-128">Description</span></span>|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|<span data-ttu-id="861d2-129">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="861d2-129">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[\<system.runtime.caching>](system-runtime-caching-element-cache-settings.md)|<span data-ttu-id="861d2-130">.NET Framework に組み込まれているアプリケーションに出力キャッシュを実装できる型が含まれています。</span><span class="sxs-lookup"><span data-stu-id="861d2-130">Contains types that let you implement output caching in applications that are built into the .NET Framework.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="861d2-131">解説</span><span class="sxs-lookup"><span data-stu-id="861d2-131">Remarks</span></span>  

 <span data-ttu-id="861d2-132"><xref:System.Runtime.Caching.MemoryCache> クラスは、抽象 <xref:System.Runtime.Caching.ObjectCache> クラスの具象実装です。</span><span class="sxs-lookup"><span data-stu-id="861d2-132">The <xref:System.Runtime.Caching.MemoryCache> class is a concrete implementation of the abstract <xref:System.Runtime.Caching.ObjectCache> class.</span></span> <span data-ttu-id="861d2-133"><xref:System.Runtime.Caching.MemoryCache> クラスのインスタンスには、アプリケーション構成ファイルの構成情報を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="861d2-133">Instances of the <xref:System.Runtime.Caching.MemoryCache> class can be supplied with configuration information from application configuration files.</span></span> <span data-ttu-id="861d2-134">[memoryCache](memorycache-element-cache-settings.md) 構成セクションには、 `namedCaches` の構成コレクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="861d2-134">The [memoryCache](memorycache-element-cache-settings.md) configuration section contains a `namedCaches` configuration collection.</span></span>  
  
 <span data-ttu-id="861d2-135">メモリ ベースのキャッシュ オブジェクトが初期化されると、まず、メモリ キャッシュ コンストラクターに渡されるパラメーターの名前と一致する `namedCaches` のエントリの検索が試行されます。</span><span class="sxs-lookup"><span data-stu-id="861d2-135">When a memory-based cache object is initialized, it first tries to find a `namedCaches` entry that matches the name in the parameter that is passed to the memory cache constructor.</span></span> <span data-ttu-id="861d2-136">`namedCaches` のエントリが見つかると、ポーリングとメモリ管理の情報が構成ファイルから取得されます。</span><span class="sxs-lookup"><span data-stu-id="861d2-136">If a `namedCaches` entry is found, the polling and memory-management information are retrieved from the configuration file.</span></span>  
  
 <span data-ttu-id="861d2-137">次に、初期化プロセスで、コンストラクターの構成情報にある名前/値ペアの任意のコレクションを使用して、構成エントリがオーバーライドされているかどうかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="861d2-137">The initialization process then determines whether any configuration entries were overridden, by using the optional collection of name/value pairs of configuration information in the constructor.</span></span> <span data-ttu-id="861d2-138">名前/値ペアのコレクションの、次の値のいずれかを渡すと、構成ファイルから取得した情報をその値がオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="861d2-138">If you pass any one of the following values in the name/value pair collection, these values override information obtained from the configuration file:</span></span>  
  
- <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.CacheMemoryLimitMegabytes%2A>  
  
- <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.PhysicalMemoryLimitPercentage%2A>  
  
- <xref:System.Runtime.Caching.MemoryCache.PollingInterval%2A>  
  
## <a name="example"></a><span data-ttu-id="861d2-139">例</span><span class="sxs-lookup"><span data-stu-id="861d2-139">Example</span></span>  

 <span data-ttu-id="861d2-140">次の例は、 <xref:System.Runtime.Caching.MemoryCache> 属性を "default" に設定することによって、オブジェクトの名前を既定のキャッシュオブジェクト名に設定する方法を示して `name` います。</span><span class="sxs-lookup"><span data-stu-id="861d2-140">The following example shows how to set the name of the <xref:System.Runtime.Caching.MemoryCache> object to the default cache object name by setting the `name` attribute to "Default".</span></span>  
  
 <span data-ttu-id="861d2-141">`cacheMemoryLimitMegabytes` 属性および `physicalMemoryLimitPercentage` 属性はゼロに設定されます。</span><span class="sxs-lookup"><span data-stu-id="861d2-141">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryLimitPercentage` attribute are set to zero.</span></span> <span data-ttu-id="861d2-142">これらの属性をゼロに設定すると、 <xref:System.Runtime.Caching.MemoryCache> の自動サイズ調整ヒューリスティックが既定で使用されることになります。</span><span class="sxs-lookup"><span data-stu-id="861d2-142">Setting these attributes to zero means that the <xref:System.Runtime.Caching.MemoryCache> autosizing heuristics are used by default.</span></span> <span data-ttu-id="861d2-143">キャッシュの実装では、現在のメモリ負荷と絶対およびパーセントのメモリ制限を 2 分ごとに比較する必要があります。</span><span class="sxs-lookup"><span data-stu-id="861d2-143">The cache implementation should compare the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
```xml  
<configuration>  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="Default"
               cacheMemoryLimitMegabytes="0"
               physicalMemoryLimitPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="861d2-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="861d2-144">See also</span></span>

- <xref:System.Runtime.Caching.MemoryCache>
- [<span data-ttu-id="861d2-145">\<system.runtime.caching> 要素 (キャッシュ設定)</span><span class="sxs-lookup"><span data-stu-id="861d2-145">\<system.runtime.caching> Element (Cache Settings)</span></span>](system-runtime-caching-element-cache-settings.md)
- [<span data-ttu-id="861d2-146">\<namedCaches> 要素 (キャッシュ設定)</span><span class="sxs-lookup"><span data-stu-id="861d2-146">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
