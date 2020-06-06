---
title: <namedCaches> 要素 (キャッシュ設定)
ms.date: 03/30/2017
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
ms.openlocfilehash: e0640ca18d386141f3c03135019eb4fe959b5bf8
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153959"
---
# <a name="namedcaches-element-cache-settings"></a><span data-ttu-id="9648e-102">\<namedCaches> 要素 (キャッシュ設定)</span><span class="sxs-lookup"><span data-stu-id="9648e-102">\<namedCaches> Element (Cache Settings)</span></span>
<span data-ttu-id="9648e-103">名前付きインスタンスの構成設定のコレクションを指定し <xref:System.Runtime.Caching.MemoryCache> ます。</span><span class="sxs-lookup"><span data-stu-id="9648e-103">Specifies a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span> <span data-ttu-id="9648e-104">プロパティは、構成 <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> ファイルの1つ以上の要素から構成設定のコレクションを参照し `namedCaches` ます。</span><span class="sxs-lookup"><span data-stu-id="9648e-104">The <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> property references the collection of configuration settings from one or more `namedCaches` elements of the configuration file.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<namedCaches>**  
  
## <a name="syntax"></a><span data-ttu-id="9648e-105">構文</span><span class="sxs-lookup"><span data-stu-id="9648e-105">Syntax</span></span>  
  
```xml  
<namedCaches>  
  <add name="default"/>
</namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="9648e-106">Type</span><span class="sxs-lookup"><span data-stu-id="9648e-106">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9648e-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9648e-107">Attributes and Elements</span></span>  
 <span data-ttu-id="9648e-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9648e-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9648e-109">属性</span><span class="sxs-lookup"><span data-stu-id="9648e-109">Attributes</span></span>  
  
|<span data-ttu-id="9648e-110">属性</span><span class="sxs-lookup"><span data-stu-id="9648e-110">Attribute</span></span>|<span data-ttu-id="9648e-111">説明</span><span class="sxs-lookup"><span data-stu-id="9648e-111">Description</span></span>|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|<span data-ttu-id="9648e-112">のインスタンスを拡張できる最大許容サイズを mb 単位で指定する整数値 <xref:System.Runtime.Caching.MemoryCache> 。</span><span class="sxs-lookup"><span data-stu-id="9648e-112">An integer value that specifies the maximum allowable size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="9648e-113">既定値は0です。これは、クラスの自動サイズ調整ヒューリスティックが <xref:System.Runtime.Caching.MemoryCache> 既定で使用されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="9648e-113">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`name`|<span data-ttu-id="9648e-114">キャッシュの名前。</span><span class="sxs-lookup"><span data-stu-id="9648e-114">The name of the cache.</span></span>|  
|`physicalMemoryLimitPercentage`|<span data-ttu-id="9648e-115">物理的にインストールされたコンピューターメモリのうち、キャッシュで使用できる最大パーセンテージを指定する 0 ~ 100 の整数値。</span><span class="sxs-lookup"><span data-stu-id="9648e-115">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="9648e-116">既定値は0です。これは、クラスの自動サイズ調整ヒューリスティックが <xref:System.Runtime.Caching.MemoryCache> 既定で使用されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="9648e-116">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`pollingInterval`|<span data-ttu-id="9648e-117">時間間隔を示す値。この値を超えると、キャッシュの実装によりキャッシュ インスタンスに設定されている絶対およびパーセントのメモリ制限と現在のメモリ負荷が比較されます。</span><span class="sxs-lookup"><span data-stu-id="9648e-117">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="9648e-118">この値は、"HH: MM: SS" 形式で入力します。</span><span class="sxs-lookup"><span data-stu-id="9648e-118">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9648e-119">子要素</span><span class="sxs-lookup"><span data-stu-id="9648e-119">Child Elements</span></span>  
  
|<span data-ttu-id="9648e-120">要素</span><span class="sxs-lookup"><span data-stu-id="9648e-120">Element</span></span>|<span data-ttu-id="9648e-121">Description</span><span class="sxs-lookup"><span data-stu-id="9648e-121">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-element-for-namedcaches.md)|<span data-ttu-id="9648e-122">名前付きキャッシュを、メモリ キャッシュの `namedCaches` コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="9648e-122">Adds a named cache to the `namedCaches` collection for a memory cache.</span></span>|  
|[\<clear>](clear-element-for-namedcaches.md)|<span data-ttu-id="9648e-123">メモリ キャッシュの `namedCaches` コレクションを消去します。</span><span class="sxs-lookup"><span data-stu-id="9648e-123">Clears the `namedCaches` collection for a memory cache.</span></span>|  
|[\<remove>](remove-element-for-namedcaches.md)|<span data-ttu-id="9648e-124">名前付きキャッシュ エントリを、メモリ キャッシュの `namedCaches` コレクションから削除します。</span><span class="sxs-lookup"><span data-stu-id="9648e-124">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9648e-125">親要素</span><span class="sxs-lookup"><span data-stu-id="9648e-125">Parent Elements</span></span>  
  
|<span data-ttu-id="9648e-126">要素</span><span class="sxs-lookup"><span data-stu-id="9648e-126">Element</span></span>|<span data-ttu-id="9648e-127">Description</span><span class="sxs-lookup"><span data-stu-id="9648e-127">Description</span></span>|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|<span data-ttu-id="9648e-128">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="9648e-128">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[\<memoryCache>](memorycache-element-cache-settings.md)|<span data-ttu-id="9648e-129"><xref:System.Runtime.Caching.MemoryCache> クラスに基づくキャッシュを構成するために使用される要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="9648e-129">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
|[\<system.runtime.caching>](system-runtime-caching-element-cache-settings.md)|<span data-ttu-id="9648e-130">.NET Framework に組み込まれているアプリケーションに出力キャッシュを実装できる型が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9648e-130">Contains types that let you implement output caching in applications that are built into the .NET Framework.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9648e-131">解説</span><span class="sxs-lookup"><span data-stu-id="9648e-131">Remarks</span></span>  
 <span data-ttu-id="9648e-132">Web.config ファイルのメモリキャッシュ構成セクションには `add` 、コレクションの、、の各属性を含めることができ `remove` `clear` `namedCaches` ます。</span><span class="sxs-lookup"><span data-stu-id="9648e-132">The memory cache configuration section of the Web.config file can contain `add`, `remove`, and `clear` attributes for the `namedCaches` collection.</span></span> <span data-ttu-id="9648e-133">各 `namedCaches` エントリは、属性によって一意に識別され `name` ます。</span><span class="sxs-lookup"><span data-stu-id="9648e-133">Each `namedCaches` entry is uniquely identified by the `name` attribute.</span></span>  
  
 <span data-ttu-id="9648e-134">メモリキャッシュエントリのインスタンスを取得するには、アプリケーション構成ファイル内の情報を参照します。</span><span class="sxs-lookup"><span data-stu-id="9648e-134">You can retrieve instances of memory cache entries by referencing the information in the application configuration files.</span></span> <span data-ttu-id="9648e-135">既定では、構成ファイルにエントリが存在するのは既定のキャッシュインスタンスだけです。</span><span class="sxs-lookup"><span data-stu-id="9648e-135">By default, only the default cache instance has an entry in the configuration file.</span></span> <span data-ttu-id="9648e-136">既定のキャッシュインスタンスは、プロパティから返されるインスタンスです <xref:System.Runtime.Caching.MemoryCache.Default%2A> 。</span><span class="sxs-lookup"><span data-stu-id="9648e-136">The default cache instance is the instance that is returned from the <xref:System.Runtime.Caching.MemoryCache.Default%2A> property.</span></span>  
  
 <span data-ttu-id="9648e-137">Name 属性を "default" に設定した場合、要素は既定のメモリキャッシュインスタンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="9648e-137">If you set the name attribute to "default", the element uses the default memory cache instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9648e-138">例</span><span class="sxs-lookup"><span data-stu-id="9648e-138">Example</span></span>  
 <span data-ttu-id="9648e-139">次の例は、属性を "default" に設定することによって、キャッシュの名前を既定のキャッシュエントリ名に設定する方法を示して `name` います。</span><span class="sxs-lookup"><span data-stu-id="9648e-139">The following example shows how to set the name of the cache to the default cache entry name by setting the `name` attribute to "default".</span></span>  
  
 <span data-ttu-id="9648e-140">`cacheMemoryLimitMegabytes` 属性および `physicalMemoryPercentage` 属性はゼロに設定されます。</span><span class="sxs-lookup"><span data-stu-id="9648e-140">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="9648e-141">これらの属性を0に設定すると、クラスの自動サイズ調整ヒューリスティックが <xref:System.Runtime.Caching.MemoryCache> 使用されます。</span><span class="sxs-lookup"><span data-stu-id="9648e-141">Setting these attributes to zero means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used.</span></span> <span data-ttu-id="9648e-142">キャッシュの実装では、現在のメモリ負荷と、絶対値および割合に基づくメモリ制限を2分ごとに比較します。</span><span class="sxs-lookup"><span data-stu-id="9648e-142">The cache implementation compares the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9648e-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="9648e-143">See also</span></span>

- [<span data-ttu-id="9648e-144">\<memoryCache>要素 (キャッシュ設定)</span><span class="sxs-lookup"><span data-stu-id="9648e-144">\<memoryCache> Element (Cache Settings)</span></span>](memorycache-element-cache-settings.md)
