---
title: <memoryCache> 要素 (キャッシュ設定)
ms.date: 03/30/2017
helpviewer_keywords:
- <memoryCache> element
- caching [.NET Framework], configuration
- memoryCache element
ms.assetid: 182a622f-f7cf-472d-9d0b-451d2fd94525
ms.openlocfilehash: 94c21e0408b7616bf0c8a24267b72bfa7cc3aaa0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153985"
---
# <a name="memorycache-element-cache-settings"></a><span data-ttu-id="19b90-102">\<メモリキャッシュ>要素 (キャッシュ設定)</span><span class="sxs-lookup"><span data-stu-id="19b90-102">\<memoryCache> Element (Cache Settings)</span></span>
<span data-ttu-id="19b90-103"><xref:System.Runtime.Caching.MemoryCache> クラスに基づくキャッシュを構成するために使用される要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="19b90-103">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span> <span data-ttu-id="19b90-104"><xref:System.Runtime.Caching.Configuration.MemoryCacheElement> クラスは、キャッシュの構成に使用できる [memoryCache](memorycache-element-cache-settings.md) 要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="19b90-104">The <xref:System.Runtime.Caching.Configuration.MemoryCacheElement> class defines a [memoryCache](memorycache-element-cache-settings.md) element that you can use to configure the cache.</span></span> <span data-ttu-id="19b90-105"><xref:System.Runtime.Caching.MemoryCache> クラスの複数のインスタンスを、単一のアプリケーションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="19b90-105">Multiple instances of the <xref:System.Runtime.Caching.MemoryCache> class can be used in a single application.</span></span> <span data-ttu-id="19b90-106">構成ファイル内の各 `memoryCache` 要素には、指定した <xref:System.Runtime.Caching.MemoryCache> インスタンスの設定を含むことができます。</span><span class="sxs-lookup"><span data-stu-id="19b90-106">Each `memoryCache` element in the configuration file can contain settings for a named <xref:System.Runtime.Caching.MemoryCache> instance.</span></span>  
  
<span data-ttu-id="19b90-107">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="19b90-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="19b90-108">&nbsp;&nbsp;[**\<>のキャッシュ**](system-runtime-caching-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="19b90-108">&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)</span></span>\
<span data-ttu-id="19b90-109">&nbsp;&nbsp;&nbsp;&nbsp;**\<メモリキャッシュ>**</span><span class="sxs-lookup"><span data-stu-id="19b90-109">&nbsp;&nbsp;&nbsp;&nbsp;**\<memoryCache>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19b90-110">構文</span><span class="sxs-lookup"><span data-stu-id="19b90-110">Syntax</span></span>  
  
```xml  
<memoryCache>
    <namedCaches>  
        <!-- child elements -->  
    </namedCaches>
</memoryCache>  
```  
  
## <a name="type"></a><span data-ttu-id="19b90-111">Type</span><span class="sxs-lookup"><span data-stu-id="19b90-111">Type</span></span>  
 <span data-ttu-id="19b90-112"><xref:System.Runtime.Caching.MemoryCache> クラス。</span><span class="sxs-lookup"><span data-stu-id="19b90-112"><xref:System.Runtime.Caching.MemoryCache> class.</span></span>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="19b90-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="19b90-113">Attributes and Elements</span></span>  
 <span data-ttu-id="19b90-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="19b90-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="19b90-115">属性</span><span class="sxs-lookup"><span data-stu-id="19b90-115">Attributes</span></span>  
  
|<span data-ttu-id="19b90-116">属性</span><span class="sxs-lookup"><span data-stu-id="19b90-116">Attribute</span></span>|<span data-ttu-id="19b90-117">説明</span><span class="sxs-lookup"><span data-stu-id="19b90-117">Description</span></span>|  
|---------------|-----------------|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="19b90-118"><xref:System.Runtime.Caching.MemoryCache> オブジェクトのインスタンスを拡張できる最大メモリ サイズ (メガバイト)。</span><span class="sxs-lookup"><span data-stu-id="19b90-118">The maximum memory size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> object can grow to.</span></span> <span data-ttu-id="19b90-119">既定値は 0 であり、これは <xref:System.Runtime.Caching.MemoryCache> クラスの自動サイズ調整ヒューリスティックが既定で使用されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="19b90-119">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosize heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="19b90-120">キャッシュ構成の名前。</span><span class="sxs-lookup"><span data-stu-id="19b90-120">The name of the cache configuration.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="19b90-121">キャッシュが使用できる物理メモリの割合。</span><span class="sxs-lookup"><span data-stu-id="19b90-121">The percentage of physical memory that can be used by the cache.</span></span> <span data-ttu-id="19b90-122">既定値は 0 であり、これは <xref:System.Runtime.Caching.MemoryCache> クラスの自動サイズ調整ヒューリスティックが既定で使用されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="19b90-122">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosize heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="19b90-123">時間間隔を示す値。この値を超えると、キャッシュの実装によりキャッシュ インスタンスに設定されている絶対およびパーセントのメモリ制限と現在のメモリ負荷が比較されます。</span><span class="sxs-lookup"><span data-stu-id="19b90-123">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="19b90-124">値は "HH:MM:SS" 形式で入力します。</span><span class="sxs-lookup"><span data-stu-id="19b90-124">The value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="19b90-125">子要素</span><span class="sxs-lookup"><span data-stu-id="19b90-125">Child Elements</span></span>  
  
|<span data-ttu-id="19b90-126">要素</span><span class="sxs-lookup"><span data-stu-id="19b90-126">Element</span></span>|<span data-ttu-id="19b90-127">説明</span><span class="sxs-lookup"><span data-stu-id="19b90-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="19b90-128">\<名前付きキャッシュ></span><span class="sxs-lookup"><span data-stu-id="19b90-128">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="19b90-129">`namedCache` インスタンスの構成設定のコレクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="19b90-129">Contains a collection of configuration settings for the `namedCache` instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="19b90-130">親要素</span><span class="sxs-lookup"><span data-stu-id="19b90-130">Parent Elements</span></span>  
  
|<span data-ttu-id="19b90-131">要素</span><span class="sxs-lookup"><span data-stu-id="19b90-131">Element</span></span>|<span data-ttu-id="19b90-132">説明</span><span class="sxs-lookup"><span data-stu-id="19b90-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="19b90-133">\<構成></span><span class="sxs-lookup"><span data-stu-id="19b90-133">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="19b90-134">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="19b90-134">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="19b90-135">\<>のキャッシュ</span><span class="sxs-lookup"><span data-stu-id="19b90-135">\<system.runtime.caching></span></span>](system-runtime-caching-element-cache-settings.md)|<span data-ttu-id="19b90-136">.NET Framework に組み込まれているアプリケーションに出力キャッシュを実装するための型が含まれています。</span><span class="sxs-lookup"><span data-stu-id="19b90-136">Contains types that let you implement output caching in applications that are built into the .NET Framework.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19b90-137">解説</span><span class="sxs-lookup"><span data-stu-id="19b90-137">Remarks</span></span>  
 <span data-ttu-id="19b90-138"><xref:System.Runtime.Caching.MemoryCache> クラスは、抽象 <xref:System.Runtime.Caching.ObjectCache> クラスの具象実装です。</span><span class="sxs-lookup"><span data-stu-id="19b90-138">The <xref:System.Runtime.Caching.MemoryCache> class is a concrete implementation of the abstract <xref:System.Runtime.Caching.ObjectCache> class.</span></span> <span data-ttu-id="19b90-139"><xref:System.Runtime.Caching.MemoryCache> クラスのインスタンスには、アプリケーション構成ファイルの構成情報を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="19b90-139">Instances of the <xref:System.Runtime.Caching.MemoryCache> class can be supplied with configuration information from application configuration files.</span></span> <span data-ttu-id="19b90-140">[memoryCache](memorycache-element-cache-settings.md) 構成セクションには、 `namedCaches` の構成コレクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="19b90-140">The [memoryCache](memorycache-element-cache-settings.md) configuration section contains a `namedCaches` configuration collection.</span></span>  
  
 <span data-ttu-id="19b90-141">メモリ ベースのキャッシュ オブジェクトが初期化されると、まず、メモリ キャッシュ コンストラクターに渡されるパラメーターの名前と一致する `namedCaches` のエントリの検索が試行されます。</span><span class="sxs-lookup"><span data-stu-id="19b90-141">When a memory-based cache object is initialized, it first tries to find a `namedCaches` entry that matches the name in the parameter that is passed to the memory cache constructor.</span></span> <span data-ttu-id="19b90-142">`namedCaches` のエントリが見つかると、ポーリングとメモリ管理の情報が構成ファイルから取得されます。</span><span class="sxs-lookup"><span data-stu-id="19b90-142">If a `namedCaches` entry is found, the polling and memory-management information are retrieved from the configuration file.</span></span>  
  
 <span data-ttu-id="19b90-143">次に、初期化プロセスで、コンストラクターの構成情報にある名前/値ペアの任意のコレクションを使用して、構成エントリがオーバーライドされているかどうかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="19b90-143">The initialization process then determines whether any configuration entries were overridden, by using the optional collection of name/value pairs of configuration information in the constructor.</span></span> <span data-ttu-id="19b90-144">名前/値ペアのコレクションの、次の値のいずれかを渡すと、構成ファイルから取得した情報をその値がオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="19b90-144">If you pass any one of the following values in the name/value pair collection, these values override information obtained from the configuration file:</span></span>  
  
- <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.CacheMemoryLimitMegabytes%2A>  
  
- <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.PhysicalMemoryLimitPercentage%2A>  
  
- <xref:System.Runtime.Caching.MemoryCache.PollingInterval%2A>  
  
## <a name="example"></a><span data-ttu-id="19b90-145">例</span><span class="sxs-lookup"><span data-stu-id="19b90-145">Example</span></span>  
 <span data-ttu-id="19b90-146">次の例は、属性を "Default"<xref:System.Runtime.Caching.MemoryCache>に設定して、オブジェクトの名前を既定`name`のキャッシュ オブジェクト名に設定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="19b90-146">The following example shows how to set the name of the <xref:System.Runtime.Caching.MemoryCache> object to the default cache object name by setting the `name` attribute to "Default".</span></span>  
  
 <span data-ttu-id="19b90-147">`cacheMemoryLimitMegabytes` 属性および `physicalMemoryLimitPercentage` 属性はゼロに設定されます。</span><span class="sxs-lookup"><span data-stu-id="19b90-147">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryLimitPercentage` attribute are set to zero.</span></span> <span data-ttu-id="19b90-148">これらの属性をゼロに設定すると、 <xref:System.Runtime.Caching.MemoryCache> の自動サイズ調整ヒューリスティックが既定で使用されることになります。</span><span class="sxs-lookup"><span data-stu-id="19b90-148">Setting these attributes to zero means that the <xref:System.Runtime.Caching.MemoryCache> autosizing heuristics are used by default.</span></span> <span data-ttu-id="19b90-149">キャッシュの実装では、現在のメモリ負荷と絶対およびパーセントのメモリ制限を 2 分ごとに比較する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19b90-149">The cache implementation should compare the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="19b90-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="19b90-150">See also</span></span>

- <xref:System.Runtime.Caching.MemoryCache>
- [<span data-ttu-id="19b90-151">\<要素の>キャッシュ (キャッシュ設定)</span><span class="sxs-lookup"><span data-stu-id="19b90-151">\<system.runtime.caching> Element (Cache Settings)</span></span>](system-runtime-caching-element-cache-settings.md)
- [<span data-ttu-id="19b90-152">\<名前付きキャッシュ>要素 (キャッシュ設定)</span><span class="sxs-lookup"><span data-stu-id="19b90-152">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
