---
title: <system.runtime.caching> 要素 (キャッシュ設定)
ms.date: 03/30/2017
helpviewer_keywords:
- <system.runtime.caching> element
- caching [.NET Framework], configuration
- system.runtime.caching element
ms.assetid: 9b44daee-874a-4bd1-954e-83bf53565590
ms.openlocfilehash: df4887c8801dcf8af06b3826673a03cbc7dbc9b5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153855"
---
# <a name="systemruntimecaching-element-cache-settings"></a><span data-ttu-id="65796-102">\<system.runtime.caching> 要素 (キャッシュ設定)</span><span class="sxs-lookup"><span data-stu-id="65796-102">\<system.runtime.caching> Element (Cache Settings)</span></span>

<span data-ttu-id="65796-103">構成ファイル内の <xref:System.Runtime.Caching.ObjectCache> エントリを使用して既定のメモリ内の `memoryCache` の実装の構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="65796-103">Provides configuration for the default in-memory <xref:System.Runtime.Caching.ObjectCache> implementation through the `memoryCache` entry in the configuration file.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.runtime.caching>**  
  
## <a name="syntax"></a><span data-ttu-id="65796-104">構文</span><span class="sxs-lookup"><span data-stu-id="65796-104">Syntax</span></span>  
  
```xml  
<system.runtime.caching >  
   <!-- child elements -->  
</system.runtime.caching >  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="65796-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="65796-105">Attributes and Elements</span></span>

<span data-ttu-id="65796-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="65796-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="65796-107">属性</span><span class="sxs-lookup"><span data-stu-id="65796-107">Attributes</span></span>

`None`  

### <a name="child-elements"></a><span data-ttu-id="65796-108">子要素</span><span class="sxs-lookup"><span data-stu-id="65796-108">Child Elements</span></span>

|<span data-ttu-id="65796-109">要素</span><span class="sxs-lookup"><span data-stu-id="65796-109">Element</span></span>|<span data-ttu-id="65796-110">説明</span><span class="sxs-lookup"><span data-stu-id="65796-110">Description</span></span>|  
|-------------|-----------------|  
|[\<memoryCache>](memorycache-element-cache-settings.md)|<span data-ttu-id="65796-111"><xref:System.Runtime.Caching.MemoryCache> クラスに基づくキャッシュを構成するために使用される要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="65796-111">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="65796-112">親要素</span><span class="sxs-lookup"><span data-stu-id="65796-112">Parent Elements</span></span>  
  
|<span data-ttu-id="65796-113">要素</span><span class="sxs-lookup"><span data-stu-id="65796-113">Element</span></span>|<span data-ttu-id="65796-114">説明</span><span class="sxs-lookup"><span data-stu-id="65796-114">Description</span></span>|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|<span data-ttu-id="65796-115">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="65796-115">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65796-116">解説</span><span class="sxs-lookup"><span data-stu-id="65796-116">Remarks</span></span>

<span data-ttu-id="65796-117">この名前空間のクラスは、ASP.NET のキャッシュ機能と同様のキャッシュ機能を使用する方法を提供しますが、 `System.Web` アセンブリに依存しません。</span><span class="sxs-lookup"><span data-stu-id="65796-117">The classes in this namespace provide a way to use caching facilities like those in ASP.NET, but without a dependency on the `System.Web` assembly.</span></span> <span data-ttu-id="65796-118">詳細については、「 [Caching in .NET Framework Applications](../../../performance/caching-in-net-framework-applications.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65796-118">For more information, see [Caching in .NET Framework Applications](../../../performance/caching-in-net-framework-applications.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="65796-119">名前空間の出力キャッシュ機能と型は <xref:System.Runtime.Caching> .NET Framework 4 で新たに追加されています。</span><span class="sxs-lookup"><span data-stu-id="65796-119">The output caching functionality and types in the <xref:System.Runtime.Caching> namespace are new in .NET Framework 4.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65796-120">例</span><span class="sxs-lookup"><span data-stu-id="65796-120">Example</span></span>

<span data-ttu-id="65796-121">次の例では、 <xref:System.Runtime.Caching.MemoryCache> クラスを元にしたキャッシュの構成方法を紹介します。</span><span class="sxs-lookup"><span data-stu-id="65796-121">The following example shows how to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span> <span data-ttu-id="65796-122">この例では、メモリ キャッシュ用の `namedCaches` エントリのインスタンスの構成を方法を示します。</span><span class="sxs-lookup"><span data-stu-id="65796-122">The example shows how to configure an instance of the `namedCaches` entry for memory cache.</span></span> <span data-ttu-id="65796-123">キャッシュの名前は、 `name` 属性を "default" に設定することによって、既定のキャッシュエントリ名に設定されます。</span><span class="sxs-lookup"><span data-stu-id="65796-123">The name of the cache is set to the default cache entry name by setting the `name` attribute to "Default".</span></span>  
  
<span data-ttu-id="65796-124">`cacheMemoryLimitMegabytes` 属性および `physicalMemoryPercentage` 属性はゼロに設定されます。</span><span class="sxs-lookup"><span data-stu-id="65796-124">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="65796-125">これらの属性をゼロに設定すると、 <xref:System.Runtime.Caching.MemoryCache> の自動サイズ調整ヒューリスティックが既定で使用されることになります。</span><span class="sxs-lookup"><span data-stu-id="65796-125">Setting these attributes to zero means that the <xref:System.Runtime.Caching.MemoryCache> autosizing heuristics are used by default.</span></span> <span data-ttu-id="65796-126">キャッシュの実装では、現在のメモリ負荷と絶対およびパーセントのメモリ制限を 2 分ごとに比較する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65796-126">The cache implementation should compare the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="65796-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="65796-127">See also</span></span>

- [<span data-ttu-id="65796-128">\<memoryCache>要素 (キャッシュ設定)</span><span class="sxs-lookup"><span data-stu-id="65796-128">\<memoryCache> Element (Cache Settings)</span></span>](memorycache-element-cache-settings.md)
