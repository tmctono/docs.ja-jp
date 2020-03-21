---
title: <namedCaches> 要素 (キャッシュ設定)
ms.date: 03/30/2017
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
ms.openlocfilehash: e0640ca18d386141f3c03135019eb4fe959b5bf8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153959"
---
# <a name="namedcaches-element-cache-settings"></a><span data-ttu-id="de88f-102">\<名前付きキャッシュ>要素 (キャッシュ設定)</span><span class="sxs-lookup"><span data-stu-id="de88f-102">\<namedCaches> Element (Cache Settings)</span></span>
<span data-ttu-id="de88f-103">名前付き<xref:System.Runtime.Caching.MemoryCache>インスタンスの構成設定のコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="de88f-103">Specifies a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span> <span data-ttu-id="de88f-104">この<xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A>プロパティは、構成ファイルの 1 つ以上`namedCaches`の要素から構成設定のコレクションを参照します。</span><span class="sxs-lookup"><span data-stu-id="de88f-104">The <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> property references the collection of configuration settings from one or more `namedCaches` elements of the configuration file.</span></span>  
  
<span data-ttu-id="de88f-105">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="de88f-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="de88f-106">&nbsp;&nbsp;[**\<>のキャッシュ**](system-runtime-caching-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="de88f-106">&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)</span></span>\
<span data-ttu-id="de88f-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<メモリキャッシュ>**](memorycache-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="de88f-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)</span></span>\
<span data-ttu-id="de88f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<名前付きキャッシュ>**</span><span class="sxs-lookup"><span data-stu-id="de88f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<namedCaches>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de88f-109">構文</span><span class="sxs-lookup"><span data-stu-id="de88f-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
  <add name="default"/>
</namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="de88f-110">Type</span><span class="sxs-lookup"><span data-stu-id="de88f-110">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="de88f-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="de88f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="de88f-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="de88f-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="de88f-113">属性</span><span class="sxs-lookup"><span data-stu-id="de88f-113">Attributes</span></span>  
  
|<span data-ttu-id="de88f-114">属性</span><span class="sxs-lookup"><span data-stu-id="de88f-114">Attribute</span></span>|<span data-ttu-id="de88f-115">説明</span><span class="sxs-lookup"><span data-stu-id="de88f-115">Description</span></span>|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|<span data-ttu-id="de88f-116">インスタンスの拡張可能な最大許容サイズを<xref:System.Runtime.Caching.MemoryCache>メガバイト単位で指定する整数値。</span><span class="sxs-lookup"><span data-stu-id="de88f-116">An integer value that specifies the maximum allowable size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="de88f-117">既定値は 0 で、<xref:System.Runtime.Caching.MemoryCache>クラスの自動サイズ設定ヒューリスティックが既定で使用されます。</span><span class="sxs-lookup"><span data-stu-id="de88f-117">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`name`|<span data-ttu-id="de88f-118">キャッシュの名前。</span><span class="sxs-lookup"><span data-stu-id="de88f-118">The name of the cache.</span></span>|  
|`physicalMemoryLimitPercentage`|<span data-ttu-id="de88f-119">キャッシュで使用できる物理的にインストールされたコンピュータ メモリの最大パーセントを指定する 0 ~ 100 の整数値。</span><span class="sxs-lookup"><span data-stu-id="de88f-119">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="de88f-120">既定値は 0 で、<xref:System.Runtime.Caching.MemoryCache>クラスの自動サイズ設定ヒューリスティックが既定で使用されます。</span><span class="sxs-lookup"><span data-stu-id="de88f-120">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`pollingInterval`|<span data-ttu-id="de88f-121">時間間隔を示す値。この値を超えると、キャッシュの実装によりキャッシュ インスタンスに設定されている絶対およびパーセントのメモリ制限と現在のメモリ負荷が比較されます。</span><span class="sxs-lookup"><span data-stu-id="de88f-121">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="de88f-122">この値は"HH:MM:SS"形式で入力されます。</span><span class="sxs-lookup"><span data-stu-id="de88f-122">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="de88f-123">子要素</span><span class="sxs-lookup"><span data-stu-id="de88f-123">Child Elements</span></span>  
  
|<span data-ttu-id="de88f-124">要素</span><span class="sxs-lookup"><span data-stu-id="de88f-124">Element</span></span>|<span data-ttu-id="de88f-125">説明</span><span class="sxs-lookup"><span data-stu-id="de88f-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="de88f-126">\<>を追加する</span><span class="sxs-lookup"><span data-stu-id="de88f-126">\<add></span></span>](add-element-for-namedcaches.md)|<span data-ttu-id="de88f-127">名前付きキャッシュを、メモリ キャッシュの `namedCaches` コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="de88f-127">Adds a named cache to the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="de88f-128">\<クリア></span><span class="sxs-lookup"><span data-stu-id="de88f-128">\<clear></span></span>](clear-element-for-namedcaches.md)|<span data-ttu-id="de88f-129">メモリ キャッシュの `namedCaches` コレクションを消去します。</span><span class="sxs-lookup"><span data-stu-id="de88f-129">Clears the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="de88f-130">\<>を削除する</span><span class="sxs-lookup"><span data-stu-id="de88f-130">\<remove></span></span>](remove-element-for-namedcaches.md)|<span data-ttu-id="de88f-131">名前付きキャッシュ エントリを、メモリ キャッシュの `namedCaches` コレクションから削除します。</span><span class="sxs-lookup"><span data-stu-id="de88f-131">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="de88f-132">親要素</span><span class="sxs-lookup"><span data-stu-id="de88f-132">Parent Elements</span></span>  
  
|<span data-ttu-id="de88f-133">要素</span><span class="sxs-lookup"><span data-stu-id="de88f-133">Element</span></span>|<span data-ttu-id="de88f-134">説明</span><span class="sxs-lookup"><span data-stu-id="de88f-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="de88f-135">\<構成></span><span class="sxs-lookup"><span data-stu-id="de88f-135">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="de88f-136">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="de88f-136">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="de88f-137">\<メモリキャッシュ></span><span class="sxs-lookup"><span data-stu-id="de88f-137">\<memoryCache></span></span>](memorycache-element-cache-settings.md)|<span data-ttu-id="de88f-138"><xref:System.Runtime.Caching.MemoryCache> クラスに基づくキャッシュを構成するために使用される要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="de88f-138">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
|[<span data-ttu-id="de88f-139">\<>のキャッシュ</span><span class="sxs-lookup"><span data-stu-id="de88f-139">\<system.runtime.caching></span></span>](system-runtime-caching-element-cache-settings.md)|<span data-ttu-id="de88f-140">.NET Framework に組み込まれているアプリケーションに出力キャッシュを実装するための型が含まれています。</span><span class="sxs-lookup"><span data-stu-id="de88f-140">Contains types that let you implement output caching in applications that are built into the .NET Framework.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de88f-141">解説</span><span class="sxs-lookup"><span data-stu-id="de88f-141">Remarks</span></span>  
 <span data-ttu-id="de88f-142">Web.config ファイルのメモリ キャッシュ構成セクションには、`add`コレクション`remove`の`clear`属性 、、および 属性を`namedCaches`含めることができます。</span><span class="sxs-lookup"><span data-stu-id="de88f-142">The memory cache configuration section of the Web.config file can contain `add`, `remove`, and `clear` attributes for the `namedCaches` collection.</span></span> <span data-ttu-id="de88f-143">各`namedCaches`エントリは、属性によって一意`name`に識別されます。</span><span class="sxs-lookup"><span data-stu-id="de88f-143">Each `namedCaches` entry is uniquely identified by the `name` attribute.</span></span>  
  
 <span data-ttu-id="de88f-144">アプリケーション構成ファイルの情報を参照することにより、メモリ キャッシュ エントリのインスタンスを取得できます。</span><span class="sxs-lookup"><span data-stu-id="de88f-144">You can retrieve instances of memory cache entries by referencing the information in the application configuration files.</span></span> <span data-ttu-id="de88f-145">デフォルトでは、デフォルトのキャッシュ・インスタンスのみが構成ファイルにエントリーを持っています。</span><span class="sxs-lookup"><span data-stu-id="de88f-145">By default, only the default cache instance has an entry in the configuration file.</span></span> <span data-ttu-id="de88f-146">既定のキャッシュ インスタンスは、プロパティから返されるインスタンス<xref:System.Runtime.Caching.MemoryCache.Default%2A>です。</span><span class="sxs-lookup"><span data-stu-id="de88f-146">The default cache instance is the instance that is returned from the <xref:System.Runtime.Caching.MemoryCache.Default%2A> property.</span></span>  
  
 <span data-ttu-id="de88f-147">name 属性を "default" に設定すると、要素は既定のメモリ キャッシュ インスタンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="de88f-147">If you set the name attribute to "default", the element uses the default memory cache instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="de88f-148">例</span><span class="sxs-lookup"><span data-stu-id="de88f-148">Example</span></span>  
 <span data-ttu-id="de88f-149">属性を "default" に設定して、キャッシュの名前を既定のキャッシュ エントリ名`name`に設定する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="de88f-149">The following example shows how to set the name of the cache to the default cache entry name by setting the `name` attribute to "default".</span></span>  
  
 <span data-ttu-id="de88f-150">`cacheMemoryLimitMegabytes` 属性および `physicalMemoryPercentage` 属性はゼロに設定されます。</span><span class="sxs-lookup"><span data-stu-id="de88f-150">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="de88f-151">これらの属性をゼロに設定すると、<xref:System.Runtime.Caching.MemoryCache>クラスの自動サイズ設定ヒューリスティックが使用されます。</span><span class="sxs-lookup"><span data-stu-id="de88f-151">Setting these attributes to zero means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used.</span></span> <span data-ttu-id="de88f-152">キャッシュの実装では、現在のメモリ負荷と 2 分ごとの絶対および割合ベースのメモリ制限を比較します。</span><span class="sxs-lookup"><span data-stu-id="de88f-152">The cache implementation compares the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="de88f-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="de88f-153">See also</span></span>

- [<span data-ttu-id="de88f-154">\<メモリキャッシュ>要素 (キャッシュ設定)</span><span class="sxs-lookup"><span data-stu-id="de88f-154">\<memoryCache> Element (Cache Settings)</span></span>](memorycache-element-cache-settings.md)
