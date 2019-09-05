---
title: <forcePerformanceCounterUniqueSharedMemoryReads> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 54bccd134a2f77925e80bfc681770b28c05f77a1
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252604"
---
# <a name="forceperformancecounteruniquesharedmemoryreads-element"></a><span data-ttu-id="279b6-102">\<forcePerformanceCounterUniqueSharedMemoryReads > 要素</span><span class="sxs-lookup"><span data-stu-id="279b6-102">\<forcePerformanceCounterUniqueSharedMemoryReads> Element</span></span>
<span data-ttu-id="279b6-103">PerfCounter.dll が、.NET Framework バージョン 1.1 のアプリケーションの CategoryOptions レジストリ設定を使用してするかどうかを指定して、カテゴリ別の共有メモリとグローバル メモリのどちらからパフォーマンス カウンター データを読み込むかを決定します。</span><span class="sxs-lookup"><span data-stu-id="279b6-103">Specifies whether PerfCounter.dll uses the CategoryOptions registry setting in a .NET Framework version 1.1 application to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>  
  
<span data-ttu-id="279b6-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="279b6-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="279b6-105">&nbsp;&nbsp;[ **\<ランタイム >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="279b6-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="279b6-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<forcePerformanceCounterUniqueSharedMemoryReads >**</span><span class="sxs-lookup"><span data-stu-id="279b6-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<forcePerformanceCounterUniqueSharedMemoryReads>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="279b6-107">構文</span><span class="sxs-lookup"><span data-stu-id="279b6-107">Syntax</span></span>  
  
```xml  
<forcePerformanceCounterUniqueSharedMemoryReads   
enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="279b6-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="279b6-108">Attributes and Elements</span></span>  
 <span data-ttu-id="279b6-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="279b6-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="279b6-110">属性</span><span class="sxs-lookup"><span data-stu-id="279b6-110">Attributes</span></span>  
  
|<span data-ttu-id="279b6-111">属性</span><span class="sxs-lookup"><span data-stu-id="279b6-111">Attribute</span></span>|<span data-ttu-id="279b6-112">説明</span><span class="sxs-lookup"><span data-stu-id="279b6-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="279b6-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="279b6-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="279b6-114">PerfCounter .dll が category Options レジストリ設定を使用して、カテゴリ固有の共有メモリまたはグローバルメモリからパフォーマンスカウンターデータを読み込むかどうかを決定するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="279b6-114">Indicates whether PerfCounter.dll uses the CategoryOptions registry setting to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="279b6-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="279b6-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="279b6-116">値</span><span class="sxs-lookup"><span data-stu-id="279b6-116">Value</span></span>|<span data-ttu-id="279b6-117">説明</span><span class="sxs-lookup"><span data-stu-id="279b6-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="279b6-118">PerfCounter .dll は、カテゴリオプションのレジストリ設定を使用しません。これが既定値です。</span><span class="sxs-lookup"><span data-stu-id="279b6-118">PerfCounter.dll does not use the CategoryOptions registry setting This is the default.</span></span>|  
|`true`|<span data-ttu-id="279b6-119">PerfCounter .dll は、カテゴリオプションのレジストリ設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="279b6-119">PerfCounter.dll does use the CategoryOptions registry setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="279b6-120">子要素</span><span class="sxs-lookup"><span data-stu-id="279b6-120">Child Elements</span></span>  
 <span data-ttu-id="279b6-121">なし。</span><span class="sxs-lookup"><span data-stu-id="279b6-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="279b6-122">親要素</span><span class="sxs-lookup"><span data-stu-id="279b6-122">Parent Elements</span></span>  
  
|<span data-ttu-id="279b6-123">要素</span><span class="sxs-lookup"><span data-stu-id="279b6-123">Element</span></span>|<span data-ttu-id="279b6-124">説明</span><span class="sxs-lookup"><span data-stu-id="279b6-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="279b6-125">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="279b6-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="279b6-126">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="279b6-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="279b6-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="279b6-127">Remarks</span></span>  
 <span data-ttu-id="279b6-128">.NET Framework 4 より前の .NET Framework のバージョンでは、これに読み込まれたバージョンの PerfCounter が、プロセスに読み込まれたランタイムに読み込まれていました。</span><span class="sxs-lookup"><span data-stu-id="279b6-128">In versions of the .NET Framework before the .NET Framework 4, the version of PerfCounter.dll that was loaded corresponded to the runtime that was loaded in the process.</span></span> <span data-ttu-id="279b6-129">コンピューターに .NET Framework バージョン1.1 と .NET Framework 2.0 の両方がインストールされている場合、.NET Framework 1.1 アプリケーションは .NET Framework 1.1 バージョンの PerfCounter を読み込みます。</span><span class="sxs-lookup"><span data-stu-id="279b6-129">If a computer had both the .NET Framework version 1.1 and the .NET Framework 2.0 installed, a .NET Framework 1.1 application would load the .NET Framework 1.1 version of PerfCounter.dll.</span></span> <span data-ttu-id="279b6-130">.NET Framework 4 以降では、インストールされている最新バージョンの PerfCounter が読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="279b6-130">Starting with the .NET Framework 4, the newest installed version of PerfCounter.dll is loaded.</span></span> <span data-ttu-id="279b6-131">これは、.NET Framework 4 がコンピューターにインストールされている場合、.NET Framework 1.1 アプリケーションが .NET Framework 4 バージョンの PerfCounter を読み込むことを意味します。</span><span class="sxs-lookup"><span data-stu-id="279b6-131">This means that a .NET Framework 1.1 application will load the .NET Framework 4 version of PerfCounter.dll if the .NET Framework 4 is installed on the computer.</span></span>  
  
 <span data-ttu-id="279b6-132">.NET Framework 4 以降では、パフォーマンスカウンターを使用するときに、PerfCounter によって各プロバイダーのカテゴリオプションのレジストリエントリがチェックされ、カテゴリ固有の共有メモリとグローバル共有メモリのどちらから読み取る必要があるかが判断されます。</span><span class="sxs-lookup"><span data-stu-id="279b6-132">Starting with the .NET Framework 4, when consuming performance counters, PerfCounter.dll checks the CategoryOptions registry entry for each provider to determine whether it should read from category-specific shared memory or global shared memory.</span></span> <span data-ttu-id="279b6-133">.NET Framework 1.1 PerfCounter は、カテゴリ固有の共有メモリを認識しないため、そのレジストリエントリを読み取りません。常に、グローバルな共有メモリから読み取ります。</span><span class="sxs-lookup"><span data-stu-id="279b6-133">The .NET Framework 1.1 PerfCounter.dll does not read that registry entry, because it is not aware of category-specific shared memory; it always reads from global shared memory.</span></span>  
  
 <span data-ttu-id="279b6-134">旧バージョンとの互換性のために、.NET Framework 4 PerfCounter .dll は、.NET Framework 1.1 アプリケーションで実行されているときに、カテゴリオプションのレジストリエントリをチェックしません。</span><span class="sxs-lookup"><span data-stu-id="279b6-134">For backward compatibility, the .NET Framework 4 PerfCounter.dll does not check the CategoryOptions registry entry when running in a .NET Framework 1.1 application.</span></span> <span data-ttu-id="279b6-135">.NET Framework 1.1 と同様に、グローバルな共有メモリを使用します。</span><span class="sxs-lookup"><span data-stu-id="279b6-135">It simply uses global shared memory, just like the .NET Framework 1.1 PerfCounter.dll.</span></span> <span data-ttu-id="279b6-136">ただし、 `<forcePerformanceCounterUniqueSharedMemoryReads>`要素を有効にすることで、レジストリ設定をチェックするように .NET Framework 4 perfcounter .dll に指示できます。</span><span class="sxs-lookup"><span data-stu-id="279b6-136">However, you can instruct the .NET Framework 4 PerfCounter.dll to check the registry setting by enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="279b6-137">要素を`<forcePerformanceCounterUniqueSharedMemoryReads>`有効にしても、カテゴリ固有の共有メモリが使用されることは保証されません。</span><span class="sxs-lookup"><span data-stu-id="279b6-137">Enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element does not guarantee that category-specific shared memory will be used.</span></span> <span data-ttu-id="279b6-138">をに`true`設定すると、perfcounter .dll がカテゴリオプションのレジストリ設定を参照することになります。</span><span class="sxs-lookup"><span data-stu-id="279b6-138">Setting enabled to `true` only causes PerfCounter.dll to reference the CategoryOptions registry setting.</span></span> <span data-ttu-id="279b6-139">カテゴリのオプションの既定の設定では、カテゴリ固有の共有メモリを使用します。ただし、カテゴリのオプションを変更して、グローバルな共有メモリを使用する必要があることを示すことができます。</span><span class="sxs-lookup"><span data-stu-id="279b6-139">The default setting for CategoryOptions is to use category-specific shared memory; however, you can change CategoryOptions to indicate that global shared memory should be used.</span></span>  
  
 <span data-ttu-id="279b6-140">カテゴリオプションの設定を含むレジストリキーは、HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\< の\>[区分名] \ [パフォーマンス] です。</span><span class="sxs-lookup"><span data-stu-id="279b6-140">The registry key that contains the CategoryOptions setting is HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\<categoryName\>\Performance.</span></span> <span data-ttu-id="279b6-141">既定では、CategoryOptions は設定を 3 にどちら カテゴリ固有の共有メモリを使用します。</span><span class="sxs-lookup"><span data-stu-id="279b6-141">By default, CategoryOptions is set to 3, which instructs PerfCounter.dll to use category-specific shared memory.</span></span> <span data-ttu-id="279b6-142">[カテゴリ] オプションが0に設定されている場合、PerfCounter .dll はグローバル共有メモリを使用します。</span><span class="sxs-lookup"><span data-stu-id="279b6-142">If CategoryOptions is set to 0, PerfCounter.dll uses global shared memory.</span></span> <span data-ttu-id="279b6-143">インスタンスデータが再利用されるのは、作成されるインスタンスの名前が再利用されるインスタンスと同一である場合だけです。</span><span class="sxs-lookup"><span data-stu-id="279b6-143">Instance data will be reused only if the name of the instance being created is identical to the instance being reused.</span></span> <span data-ttu-id="279b6-144">すべてのバージョンがカテゴリに書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="279b6-144">All versions will be able to write to the category.</span></span> <span data-ttu-id="279b6-145">Category オプションが1に設定されている場合、グローバル共有メモリが使用されますが、カテゴリ名が再利用されるカテゴリと同じ長さの場合は、インスタンスデータを再利用できます。</span><span class="sxs-lookup"><span data-stu-id="279b6-145">If CategoryOptions is set to 1, global shared memory is used, but instance data can be reused if the category name is the same length as the category being reused.</span></span>  
  
 <span data-ttu-id="279b6-146">設定0および1を使用すると、メモリリークが発生し、パフォーマンスカウンターのメモリがいっぱいになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="279b6-146">The settings 0 and 1 can lead to memory leaks and the filling up of performance counter memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="279b6-147">例</span><span class="sxs-lookup"><span data-stu-id="279b6-147">Example</span></span>  
 <span data-ttu-id="279b6-148">次の例では、PerfCounter .dll が category Options レジストリエントリを参照して、カテゴリ固有の共有メモリを使用するかどうかを判断するように指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="279b6-148">The following example shows how to specify that PerfCounter.dll should reference the CategoryOptions registry entry to determine whether it should use category-specific shared memory.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="279b6-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="279b6-149">See also</span></span>

- [<span data-ttu-id="279b6-150">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="279b6-150">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="279b6-151">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="279b6-151">Configuration File Schema</span></span>](../index.md)
