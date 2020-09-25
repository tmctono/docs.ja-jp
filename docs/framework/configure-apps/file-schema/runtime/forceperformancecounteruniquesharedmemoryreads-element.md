---
title: <forcePerformanceCounterUniqueSharedMemoryReads> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
ms.openlocfilehash: 719448ba3de2aca0621fc17b9fadbdd3b8588f2e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178243"
---
# <a name="forceperformancecounteruniquesharedmemoryreads-element"></a><span data-ttu-id="9f44a-102">\<forcePerformanceCounterUniqueSharedMemoryReads> 要素</span><span class="sxs-lookup"><span data-stu-id="9f44a-102">\<forcePerformanceCounterUniqueSharedMemoryReads> Element</span></span>

<span data-ttu-id="9f44a-103">PerfCounter.dll が、.NET Framework バージョン 1.1 のアプリケーションの CategoryOptions レジストリ設定を使用してするかどうかを指定して、カテゴリ別の共有メモリとグローバル メモリのどちらからパフォーマンス カウンター データを読み込むかを決定します。</span><span class="sxs-lookup"><span data-stu-id="9f44a-103">Specifies whether PerfCounter.dll uses the CategoryOptions registry setting in a .NET Framework version 1.1 application to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<forcePerformanceCounterUniqueSharedMemoryReads>**  
  
## <a name="syntax"></a><span data-ttu-id="9f44a-104">構文</span><span class="sxs-lookup"><span data-stu-id="9f44a-104">Syntax</span></span>  
  
```xml  
<forcePerformanceCounterUniqueSharedMemoryReads
enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9f44a-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9f44a-105">Attributes and Elements</span></span>  

 <span data-ttu-id="9f44a-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9f44a-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9f44a-107">属性</span><span class="sxs-lookup"><span data-stu-id="9f44a-107">Attributes</span></span>  
  
|<span data-ttu-id="9f44a-108">属性</span><span class="sxs-lookup"><span data-stu-id="9f44a-108">Attribute</span></span>|<span data-ttu-id="9f44a-109">説明</span><span class="sxs-lookup"><span data-stu-id="9f44a-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="9f44a-110">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="9f44a-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="9f44a-111">PerfCounter.dll が category Options レジストリ設定を使用して、カテゴリ固有の共有メモリまたはグローバルメモリのパフォーマンスカウンターデータを読み込むかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="9f44a-111">Indicates whether PerfCounter.dll uses the CategoryOptions registry setting to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="9f44a-112">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="9f44a-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="9f44a-113">値</span><span class="sxs-lookup"><span data-stu-id="9f44a-113">Value</span></span>|<span data-ttu-id="9f44a-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="9f44a-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="9f44a-115">PerfCounter.dll では、[カテゴリオプション] レジストリ設定を使用しません。これが既定値です。</span><span class="sxs-lookup"><span data-stu-id="9f44a-115">PerfCounter.dll does not use the CategoryOptions registry setting This is the default.</span></span>|  
|`true`|<span data-ttu-id="9f44a-116">PerfCounter.dll では、[カテゴリオプション] レジストリ設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="9f44a-116">PerfCounter.dll does use the CategoryOptions registry setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9f44a-117">子要素</span><span class="sxs-lookup"><span data-stu-id="9f44a-117">Child Elements</span></span>  

 <span data-ttu-id="9f44a-118">なし。</span><span class="sxs-lookup"><span data-stu-id="9f44a-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9f44a-119">親要素</span><span class="sxs-lookup"><span data-stu-id="9f44a-119">Parent Elements</span></span>  
  
|<span data-ttu-id="9f44a-120">要素</span><span class="sxs-lookup"><span data-stu-id="9f44a-120">Element</span></span>|<span data-ttu-id="9f44a-121">説明</span><span class="sxs-lookup"><span data-stu-id="9f44a-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9f44a-122">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="9f44a-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="9f44a-123">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9f44a-123">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9f44a-124">解説</span><span class="sxs-lookup"><span data-stu-id="9f44a-124">Remarks</span></span>  

 <span data-ttu-id="9f44a-125">.NET Framework 4 より前の .NET Framework のバージョンでは、読み込まれた PerfCounter.dll のバージョンは、プロセスに読み込まれたランタイムにこれされています。</span><span class="sxs-lookup"><span data-stu-id="9f44a-125">In versions of the .NET Framework before the .NET Framework 4, the version of PerfCounter.dll that was loaded corresponded to the runtime that was loaded in the process.</span></span> <span data-ttu-id="9f44a-126">コンピューターに .NET Framework バージョン1.1 と .NET Framework 2.0 の両方がインストールされている場合、.NET Framework 1.1 アプリケーションは .NET Framework 1.1 バージョンの PerfCounter.dll を読み込みます。</span><span class="sxs-lookup"><span data-stu-id="9f44a-126">If a computer had both the .NET Framework version 1.1 and the .NET Framework 2.0 installed, a .NET Framework 1.1 application would load the .NET Framework 1.1 version of PerfCounter.dll.</span></span> <span data-ttu-id="9f44a-127">.NET Framework 4 以降では、インストールされている PerfCounter.dll の最新バージョンが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="9f44a-127">Starting with the .NET Framework 4, the newest installed version of PerfCounter.dll is loaded.</span></span> <span data-ttu-id="9f44a-128">これは、コンピューターに .NET Framework 4 がインストールされている場合に、.NET Framework 1.1 アプリケーションによって .NET Framework 4 バージョンの PerfCounter.dll が読み込まれることを意味します。</span><span class="sxs-lookup"><span data-stu-id="9f44a-128">This means that a .NET Framework 1.1 application will load the .NET Framework 4 version of PerfCounter.dll if the .NET Framework 4 is installed on the computer.</span></span>  
  
 <span data-ttu-id="9f44a-129">.NET Framework 4 以降では、パフォーマンスカウンターを使用する場合、PerfCounter.dll は各プロバイダーの [カテゴリオプション] レジストリエントリを確認して、カテゴリ固有の共有メモリまたはグローバル共有メモリから読み取るかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="9f44a-129">Starting with the .NET Framework 4, when consuming performance counters, PerfCounter.dll checks the CategoryOptions registry entry for each provider to determine whether it should read from category-specific shared memory or global shared memory.</span></span> <span data-ttu-id="9f44a-130">.NET Framework 1.1 PerfCounter.dll は、カテゴリ固有の共有メモリを認識しないため、そのレジストリエントリを読み取りません。常に、グローバルな共有メモリから読み取ります。</span><span class="sxs-lookup"><span data-stu-id="9f44a-130">The .NET Framework 1.1 PerfCounter.dll does not read that registry entry, because it is not aware of category-specific shared memory; it always reads from global shared memory.</span></span>  
  
 <span data-ttu-id="9f44a-131">旧バージョンとの互換性のために、.NET Framework 4 PerfCounter.dll は .NET Framework 1.1 アプリケーションで実行されているときに、カテゴリオプションのレジストリエントリをチェックしません。</span><span class="sxs-lookup"><span data-stu-id="9f44a-131">For backward compatibility, the .NET Framework 4 PerfCounter.dll does not check the CategoryOptions registry entry when running in a .NET Framework 1.1 application.</span></span> <span data-ttu-id="9f44a-132">.NET Framework 1.1 PerfCounter.dll と同様に、グローバルな共有メモリを使用するだけです。</span><span class="sxs-lookup"><span data-stu-id="9f44a-132">It simply uses global shared memory, just like the .NET Framework 1.1 PerfCounter.dll.</span></span> <span data-ttu-id="9f44a-133">ただし、要素を有効にすることで、レジストリ設定を確認するように .NET Framework 4 PerfCounter.dll に指示でき `<forcePerformanceCounterUniqueSharedMemoryReads>` ます。</span><span class="sxs-lookup"><span data-stu-id="9f44a-133">However, you can instruct the .NET Framework 4 PerfCounter.dll to check the registry setting by enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9f44a-134">要素を有効 `<forcePerformanceCounterUniqueSharedMemoryReads>` にしても、カテゴリ固有の共有メモリが使用されることは保証されません。</span><span class="sxs-lookup"><span data-stu-id="9f44a-134">Enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element does not guarantee that category-specific shared memory will be used.</span></span> <span data-ttu-id="9f44a-135">を有効に設定する `true` と、PerfCounter.dll がカテゴリオプションのレジストリ設定を参照するだけになります。</span><span class="sxs-lookup"><span data-stu-id="9f44a-135">Setting enabled to `true` only causes PerfCounter.dll to reference the CategoryOptions registry setting.</span></span> <span data-ttu-id="9f44a-136">カテゴリのオプションの既定の設定では、カテゴリ固有の共有メモリを使用します。ただし、カテゴリのオプションを変更して、グローバルな共有メモリを使用する必要があることを示すことができます。</span><span class="sxs-lookup"><span data-stu-id="9f44a-136">The default setting for CategoryOptions is to use category-specific shared memory; however, you can change CategoryOptions to indicate that global shared memory should be used.</span></span>  
  
 <span data-ttu-id="9f44a-137">[カテゴリオプション] 設定が含まれているレジストリキーは、HKEY_LOCAL_MACHINE \System\CurrentControlSet\Services \\<の区分名 \> \ パフォーマンスです。</span><span class="sxs-lookup"><span data-stu-id="9f44a-137">The registry key that contains the CategoryOptions setting is HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\<categoryName\>\Performance.</span></span> <span data-ttu-id="9f44a-138">既定では、カテゴリのオプションは3に設定されています。これは、PerfCounter.dll がカテゴリ固有の共有メモリを使用するように指示します。</span><span class="sxs-lookup"><span data-stu-id="9f44a-138">By default, CategoryOptions is set to 3, which instructs PerfCounter.dll to use category-specific shared memory.</span></span> <span data-ttu-id="9f44a-139">[カテゴリ] オプションが0に設定されている場合、PerfCounter.dll はグローバル共有メモリを使用します。</span><span class="sxs-lookup"><span data-stu-id="9f44a-139">If CategoryOptions is set to 0, PerfCounter.dll uses global shared memory.</span></span> <span data-ttu-id="9f44a-140">インスタンスデータが再利用されるのは、作成されるインスタンスの名前が再利用されるインスタンスと同一である場合だけです。</span><span class="sxs-lookup"><span data-stu-id="9f44a-140">Instance data will be reused only if the name of the instance being created is identical to the instance being reused.</span></span> <span data-ttu-id="9f44a-141">すべてのバージョンがカテゴリに書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="9f44a-141">All versions will be able to write to the category.</span></span> <span data-ttu-id="9f44a-142">Category オプションが1に設定されている場合、グローバル共有メモリが使用されますが、カテゴリ名が再利用されるカテゴリと同じ長さの場合は、インスタンスデータを再利用できます。</span><span class="sxs-lookup"><span data-stu-id="9f44a-142">If CategoryOptions is set to 1, global shared memory is used, but instance data can be reused if the category name is the same length as the category being reused.</span></span>  
  
 <span data-ttu-id="9f44a-143">設定0および1を使用すると、メモリリークが発生し、パフォーマンスカウンターのメモリがいっぱいになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9f44a-143">The settings 0 and 1 can lead to memory leaks and the filling up of performance counter memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f44a-144">例</span><span class="sxs-lookup"><span data-stu-id="9f44a-144">Example</span></span>  

 <span data-ttu-id="9f44a-145">次の例は、カテゴリ固有の共有メモリを使用する必要があるかどうかを判断するために、PerfCounter.dll が category Options レジストリエントリを参照するように指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="9f44a-145">The following example shows how to specify that PerfCounter.dll should reference the CategoryOptions registry entry to determine whether it should use category-specific shared memory.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9f44a-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="9f44a-146">See also</span></span>

- [<span data-ttu-id="9f44a-147">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="9f44a-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="9f44a-148">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="9f44a-148">Configuration File Schema</span></span>](../index.md)
