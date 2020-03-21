---
title: <namedCaches> の <add> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
ms.openlocfilehash: c1345022b79df371ad9c89a39a0a8b625e26608c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154506"
---
# <a name="add-element-for-namedcaches"></a><span data-ttu-id="d6820-102">\<名前付きキャッシュ\<>の>要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="d6820-102">\<add> Element for \<namedCaches></span></span>
<span data-ttu-id="d6820-103">メモリ`namedCache`キャッシュのコレクション`namedCaches`にエントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="d6820-103">Adds a `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
<span data-ttu-id="d6820-104">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d6820-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d6820-105">&nbsp;&nbsp;[**\<>のキャッシュ**](system-runtime-caching-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="d6820-105">&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)</span></span>\
<span data-ttu-id="d6820-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<メモリキャッシュ>**](memorycache-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="d6820-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)</span></span>\
<span data-ttu-id="d6820-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<名前付きキャッシュ>**](namedcaches-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="d6820-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)</span></span>\
<span data-ttu-id="d6820-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>を追加する**</span><span class="sxs-lookup"><span data-stu-id="d6820-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6820-109">構文</span><span class="sxs-lookup"><span data-stu-id="d6820-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <add name="Default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="d6820-110">Type</span><span class="sxs-lookup"><span data-stu-id="d6820-110">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d6820-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d6820-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d6820-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d6820-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d6820-113">属性</span><span class="sxs-lookup"><span data-stu-id="d6820-113">Attributes</span></span>  
  
|<span data-ttu-id="d6820-114">属性</span><span class="sxs-lookup"><span data-stu-id="d6820-114">Attribute</span></span>|<span data-ttu-id="d6820-115">説明</span><span class="sxs-lookup"><span data-stu-id="d6820-115">Description</span></span>|  
|-|-|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="d6820-116">インスタンスの拡張可能な最大許容サイズ (MB 単位) を指定する<xref:System.Runtime.Caching.MemoryCache>整数値。</span><span class="sxs-lookup"><span data-stu-id="d6820-116">An integer value that specifies the maximum allowed size (in megabytes) that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="d6820-117">既定値は 0 で、<xref:System.Runtime.Caching.MemoryCache>クラスの自動サイズ設定ヒューリスティックが既定で使用されます。</span><span class="sxs-lookup"><span data-stu-id="d6820-117">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="d6820-118">キャッシュの名前。</span><span class="sxs-lookup"><span data-stu-id="d6820-118">The name of the cache.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="d6820-119">キャッシュで使用できる物理的にインストールされたコンピュータ メモリの最大パーセントを指定する 0 ~ 100 の整数値。</span><span class="sxs-lookup"><span data-stu-id="d6820-119">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="d6820-120">既定値は 0 で、<xref:System.Runtime.Caching.MemoryCache>クラスの自動サイズ設定ヒューリスティックが既定で使用されます。</span><span class="sxs-lookup"><span data-stu-id="d6820-120">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="d6820-121">時間間隔を示す値。この値を超えると、キャッシュの実装によりキャッシュ インスタンスに設定されている絶対およびパーセントのメモリ制限と現在のメモリ負荷が比較されます。</span><span class="sxs-lookup"><span data-stu-id="d6820-121">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="d6820-122">この値は"HH:MM:SS"形式で入力されます。</span><span class="sxs-lookup"><span data-stu-id="d6820-122">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d6820-123">子要素</span><span class="sxs-lookup"><span data-stu-id="d6820-123">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="d6820-124">親要素</span><span class="sxs-lookup"><span data-stu-id="d6820-124">Parent Elements</span></span>  
  
|<span data-ttu-id="d6820-125">要素</span><span class="sxs-lookup"><span data-stu-id="d6820-125">Element</span></span>|<span data-ttu-id="d6820-126">説明</span><span class="sxs-lookup"><span data-stu-id="d6820-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d6820-127">\<名前付きキャッシュ></span><span class="sxs-lookup"><span data-stu-id="d6820-127">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="d6820-128">名前付き<xref:System.Runtime.Caching.MemoryCache>インスタンスの構成設定のコレクションを格納します。</span><span class="sxs-lookup"><span data-stu-id="d6820-128">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6820-129">解説</span><span class="sxs-lookup"><span data-stu-id="d6820-129">Remarks</span></span>  
 <span data-ttu-id="d6820-130">要素`add`は、メモリ キャッシュの`namedCaches`コレクションにエントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="d6820-130">The `add` element adds an entry to the `namedCaches` collection for a memory cache.</span></span> <span data-ttu-id="d6820-131">要素を使用する前に[clear](clear-element-for-namedcaches.md)要素`add`を使用して、コレクション内に他の名前付きキャッシュがないことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="d6820-131">You can use the [clear](clear-element-for-namedcaches.md) element before you use the `add` element to be certain that there are no other named caches in the collection.</span></span> <span data-ttu-id="d6820-132">この要素は、machine.config ファイルおよび Web.config ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="d6820-132">This element can be used in the machine.config file and in the Web.config file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6820-133">例</span><span class="sxs-lookup"><span data-stu-id="d6820-133">Example</span></span>  
 <span data-ttu-id="d6820-134">メモリ キャッシュのコレクションに既定`namedCache`のエントリの設定を定義する`namedCaches`方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="d6820-134">The following example shows how to define settings for the default `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d6820-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="d6820-135">See also</span></span>

- [<span data-ttu-id="d6820-136">\<名前付きキャッシュ>要素 (キャッシュ設定)</span><span class="sxs-lookup"><span data-stu-id="d6820-136">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
