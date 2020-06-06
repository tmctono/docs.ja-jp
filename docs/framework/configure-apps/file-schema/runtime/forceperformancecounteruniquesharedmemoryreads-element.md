---
title: <forcePerformanceCounterUniqueSharedMemoryReads> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
ms.openlocfilehash: 742b444c445ba67d6977b622e615a6a8f591826e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154141"
---
# <a name="forceperformancecounteruniquesharedmemoryreads-element"></a><span data-ttu-id="9bf61-102">\<forcePerformanceCounterUniqueSharedMemoryReads> 要素</span><span class="sxs-lookup"><span data-stu-id="9bf61-102">\<forcePerformanceCounterUniqueSharedMemoryReads> Element</span></span>
<span data-ttu-id="9bf61-103">PerfCounter.dll が、.NET Framework バージョン 1.1 のアプリケーションの CategoryOptions レジストリ設定を使用してするかどうかを指定して、カテゴリ別の共有メモリとグローバル メモリのどちらからパフォーマンス カウンター データを読み込むかを決定します。</span><span class="sxs-lookup"><span data-stu-id="9bf61-103">Specifies whether PerfCounter.dll uses the CategoryOptions registry setting in a .NET Framework version 1.1 application to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<forcePerformanceCounterUniqueSharedMemoryReads>**  
  
## <a name="syntax"></a><span data-ttu-id="9bf61-104">構文</span><span class="sxs-lookup"><span data-stu-id="9bf61-104">Syntax</span></span>  
  
```xml  
<forcePerformanceCounterUniqueSharedMemoryReads
enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9bf61-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9bf61-105">Attributes and Elements</span></span>  
 <span data-ttu-id="9bf61-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9bf61-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9bf61-107">属性</span><span class="sxs-lookup"><span data-stu-id="9bf61-107">Attributes</span></span>  
  
|<span data-ttu-id="9bf61-108">属性</span><span class="sxs-lookup"><span data-stu-id="9bf61-108">Attribute</span></span>|<span data-ttu-id="9bf61-109">説明</span><span class="sxs-lookup"><span data-stu-id="9bf61-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="9bf61-110">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="9bf61-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="9bf61-111">PerfCounter .dll が category Options レジストリ設定を使用して、カテゴリ固有の共有メモリまたはグローバルメモリからパフォーマンスカウンターデータを読み込むかどうかを決定するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="9bf61-111">Indicates whether PerfCounter.dll uses the CategoryOptions registry setting to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="9bf61-112">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="9bf61-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="9bf61-113">値</span><span class="sxs-lookup"><span data-stu-id="9bf61-113">Value</span></span>|<span data-ttu-id="9bf61-114">Description</span><span class="sxs-lookup"><span data-stu-id="9bf61-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="9bf61-115">PerfCounter .dll は、カテゴリオプションのレジストリ設定を使用しません。これが既定値です。</span><span class="sxs-lookup"><span data-stu-id="9bf61-115">PerfCounter.dll does not use the CategoryOptions registry setting This is the default.</span></span>|  
|`true`|<span data-ttu-id="9bf61-116">PerfCounter .dll は、カテゴリオプションのレジストリ設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="9bf61-116">PerfCounter.dll does use the CategoryOptions registry setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9bf61-117">子要素</span><span class="sxs-lookup"><span data-stu-id="9bf61-117">Child Elements</span></span>  
 <span data-ttu-id="9bf61-118">なし。</span><span class="sxs-lookup"><span data-stu-id="9bf61-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9bf61-119">親要素</span><span class="sxs-lookup"><span data-stu-id="9bf61-119">Parent Elements</span></span>  
  
|<span data-ttu-id="9bf61-120">要素</span><span class="sxs-lookup"><span data-stu-id="9bf61-120">Element</span></span>|<span data-ttu-id="9bf61-121">Description</span><span class="sxs-lookup"><span data-stu-id="9bf61-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9bf61-122">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="9bf61-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="9bf61-123">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9bf61-123">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9bf61-124">解説</span><span class="sxs-lookup"><span data-stu-id="9bf61-124">Remarks</span></span>  
 <span data-ttu-id="9bf61-125">.NET Framework 4 より前の .NET Framework のバージョンでは、これに読み込まれたバージョンの PerfCounter が、プロセスに読み込まれたランタイムに読み込まれていました。</span><span class="sxs-lookup"><span data-stu-id="9bf61-125">In versions of the .NET Framework before the .NET Framework 4, the version of PerfCounter.dll that was loaded corresponded to the runtime that was loaded in the process.</span></span> <span data-ttu-id="9bf61-126">コンピューターに .NET Framework バージョン1.1 と .NET Framework 2.0 の両方がインストールされている場合、.NET Framework 1.1 アプリケーションは .NET Framework 1.1 バージョンの PerfCounter を読み込みます。</span><span class="sxs-lookup"><span data-stu-id="9bf61-126">If a computer had both the .NET Framework version 1.1 and the .NET Framework 2.0 installed, a .NET Framework 1.1 application would load the .NET Framework 1.1 version of PerfCounter.dll.</span></span> <span data-ttu-id="9bf61-127">.NET Framework 4 以降では、インストールされている最新バージョンの PerfCounter が読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="9bf61-127">Starting with the .NET Framework 4, the newest installed version of PerfCounter.dll is loaded.</span></span> <span data-ttu-id="9bf61-128">これは、.NET Framework 4 がコンピューターにインストールされている場合、.NET Framework 1.1 アプリケーションが .NET Framework 4 バージョンの PerfCounter を読み込むことを意味します。</span><span class="sxs-lookup"><span data-stu-id="9bf61-128">This means that a .NET Framework 1.1 application will load the .NET Framework 4 version of PerfCounter.dll if the .NET Framework 4 is installed on the computer.</span></span>  
  
 <span data-ttu-id="9bf61-129">.NET Framework 4 以降では、パフォーマンスカウンターを使用するときに、PerfCounter によって各プロバイダーのカテゴリオプションのレジストリエントリがチェックされ、カテゴリ固有の共有メモリとグローバル共有メモリのどちらから読み取る必要があるかが判断されます。</span><span class="sxs-lookup"><span data-stu-id="9bf61-129">Starting with the .NET Framework 4, when consuming performance counters, PerfCounter.dll checks the CategoryOptions registry entry for each provider to determine whether it should read from category-specific shared memory or global shared memory.</span></span> <span data-ttu-id="9bf61-130">.NET Framework 1.1 PerfCounter は、カテゴリ固有の共有メモリを認識しないため、そのレジストリエントリを読み取りません。常に、グローバルな共有メモリから読み取ります。</span><span class="sxs-lookup"><span data-stu-id="9bf61-130">The .NET Framework 1.1 PerfCounter.dll does not read that registry entry, because it is not aware of category-specific shared memory; it always reads from global shared memory.</span></span>  
  
 <span data-ttu-id="9bf61-131">旧バージョンとの互換性のために、.NET Framework 4 PerfCounter .dll は、.NET Framework 1.1 アプリケーションで実行されているときに、カテゴリオプションのレジストリエントリをチェックしません。</span><span class="sxs-lookup"><span data-stu-id="9bf61-131">For backward compatibility, the .NET Framework 4 PerfCounter.dll does not check the CategoryOptions registry entry when running in a .NET Framework 1.1 application.</span></span> <span data-ttu-id="9bf61-132">.NET Framework 1.1 と同様に、グローバルな共有メモリを使用します。</span><span class="sxs-lookup"><span data-stu-id="9bf61-132">It simply uses global shared memory, just like the .NET Framework 1.1 PerfCounter.dll.</span></span> <span data-ttu-id="9bf61-133">ただし、要素を有効にすることで、レジストリ設定をチェックするように .NET Framework 4 PerfCounter .dll に指示でき `<forcePerformanceCounterUniqueSharedMemoryReads>` ます。</span><span class="sxs-lookup"><span data-stu-id="9bf61-133">However, you can instruct the .NET Framework 4 PerfCounter.dll to check the registry setting by enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9bf61-134">要素を有効 `<forcePerformanceCounterUniqueSharedMemoryReads>` にしても、カテゴリ固有の共有メモリが使用されることは保証されません。</span><span class="sxs-lookup"><span data-stu-id="9bf61-134">Enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element does not guarantee that category-specific shared memory will be used.</span></span> <span data-ttu-id="9bf61-135">をに設定する `true` と、PerfCounter .dll がカテゴリオプションのレジストリ設定を参照することになります。</span><span class="sxs-lookup"><span data-stu-id="9bf61-135">Setting enabled to `true` only causes PerfCounter.dll to reference the CategoryOptions registry setting.</span></span> <span data-ttu-id="9bf61-136">カテゴリのオプションの既定の設定では、カテゴリ固有の共有メモリを使用します。ただし、カテゴリのオプションを変更して、グローバルな共有メモリを使用する必要があることを示すことができます。</span><span class="sxs-lookup"><span data-stu-id="9bf61-136">The default setting for CategoryOptions is to use category-specific shared memory; however, you can change CategoryOptions to indicate that global shared memory should be used.</span></span>  
  
 <span data-ttu-id="9bf61-137">[カテゴリオプション] 設定が含まれているレジストリキーは、HKEY_LOCAL_MACHINE \System\CurrentControlSet\Services \\<の区分名 \> \ パフォーマンスです。</span><span class="sxs-lookup"><span data-stu-id="9bf61-137">The registry key that contains the CategoryOptions setting is HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\<categoryName\>\Performance.</span></span> <span data-ttu-id="9bf61-138">既定では、カテゴリのオプションは3に設定されています。これにより、PerfCounter は、カテゴリ固有の共有メモリを使用するように指示します。</span><span class="sxs-lookup"><span data-stu-id="9bf61-138">By default, CategoryOptions is set to 3, which instructs PerfCounter.dll to use category-specific shared memory.</span></span> <span data-ttu-id="9bf61-139">[カテゴリ] オプションが0に設定されている場合、PerfCounter .dll はグローバル共有メモリを使用します。</span><span class="sxs-lookup"><span data-stu-id="9bf61-139">If CategoryOptions is set to 0, PerfCounter.dll uses global shared memory.</span></span> <span data-ttu-id="9bf61-140">インスタンスデータが再利用されるのは、作成されるインスタンスの名前が再利用されるインスタンスと同一である場合だけです。</span><span class="sxs-lookup"><span data-stu-id="9bf61-140">Instance data will be reused only if the name of the instance being created is identical to the instance being reused.</span></span> <span data-ttu-id="9bf61-141">すべてのバージョンがカテゴリに書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="9bf61-141">All versions will be able to write to the category.</span></span> <span data-ttu-id="9bf61-142">Category オプションが1に設定されている場合、グローバル共有メモリが使用されますが、カテゴリ名が再利用されるカテゴリと同じ長さの場合は、インスタンスデータを再利用できます。</span><span class="sxs-lookup"><span data-stu-id="9bf61-142">If CategoryOptions is set to 1, global shared memory is used, but instance data can be reused if the category name is the same length as the category being reused.</span></span>  
  
 <span data-ttu-id="9bf61-143">設定0および1を使用すると、メモリリークが発生し、パフォーマンスカウンターのメモリがいっぱいになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9bf61-143">The settings 0 and 1 can lead to memory leaks and the filling up of performance counter memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9bf61-144">例</span><span class="sxs-lookup"><span data-stu-id="9bf61-144">Example</span></span>  
 <span data-ttu-id="9bf61-145">次の例では、PerfCounter .dll が category Options レジストリエントリを参照して、カテゴリ固有の共有メモリを使用するかどうかを判断するように指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9bf61-145">The following example shows how to specify that PerfCounter.dll should reference the CategoryOptions registry entry to determine whether it should use category-specific shared memory.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9bf61-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="9bf61-146">See also</span></span>

- [<span data-ttu-id="9bf61-147">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="9bf61-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="9bf61-148">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="9bf61-148">Configuration File Schema</span></span>](../index.md)
