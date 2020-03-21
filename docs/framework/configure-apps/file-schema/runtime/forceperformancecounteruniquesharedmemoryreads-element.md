---
title: <forcePerformanceCounterUniqueSharedMemoryReads> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
ms.openlocfilehash: 742b444c445ba67d6977b622e615a6a8f591826e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154141"
---
# <a name="forceperformancecounteruniquesharedmemoryreads-element"></a><span data-ttu-id="416b7-102">\<>要素を読み込みます。</span><span class="sxs-lookup"><span data-stu-id="416b7-102">\<forcePerformanceCounterUniqueSharedMemoryReads> Element</span></span>
<span data-ttu-id="416b7-103">PerfCounter.dll が、.NET Framework バージョン 1.1 のアプリケーションの CategoryOptions レジストリ設定を使用してするかどうかを指定して、カテゴリ別の共有メモリとグローバル メモリのどちらからパフォーマンス カウンター データを読み込むかを決定します。</span><span class="sxs-lookup"><span data-stu-id="416b7-103">Specifies whether PerfCounter.dll uses the CategoryOptions registry setting in a .NET Framework version 1.1 application to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>  
  
<span data-ttu-id="416b7-104">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="416b7-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="416b7-105">&nbsp;&nbsp;[**\<ランタイム>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="416b7-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="416b7-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<>を読み込む**</span><span class="sxs-lookup"><span data-stu-id="416b7-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<forcePerformanceCounterUniqueSharedMemoryReads>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="416b7-107">構文</span><span class="sxs-lookup"><span data-stu-id="416b7-107">Syntax</span></span>  
  
```xml  
<forcePerformanceCounterUniqueSharedMemoryReads
enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="416b7-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="416b7-108">Attributes and Elements</span></span>  
 <span data-ttu-id="416b7-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="416b7-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="416b7-110">属性</span><span class="sxs-lookup"><span data-stu-id="416b7-110">Attributes</span></span>  
  
|<span data-ttu-id="416b7-111">属性</span><span class="sxs-lookup"><span data-stu-id="416b7-111">Attribute</span></span>|<span data-ttu-id="416b7-112">説明</span><span class="sxs-lookup"><span data-stu-id="416b7-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="416b7-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="416b7-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="416b7-114">PerfCounter.dll が CategoryOptions レジストリ設定を使用して、カテゴリ固有の共有メモリまたはグローバル メモリからパフォーマンス カウンタ データを読み込むかどうかを指定するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="416b7-114">Indicates whether PerfCounter.dll uses the CategoryOptions registry setting to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="416b7-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="416b7-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="416b7-116">Value</span><span class="sxs-lookup"><span data-stu-id="416b7-116">Value</span></span>|<span data-ttu-id="416b7-117">説明</span><span class="sxs-lookup"><span data-stu-id="416b7-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="416b7-118">PerfCounter.dll は、カテゴリ オプションレジストリ設定を使用しませんこれは既定です。</span><span class="sxs-lookup"><span data-stu-id="416b7-118">PerfCounter.dll does not use the CategoryOptions registry setting This is the default.</span></span>|  
|`true`|<span data-ttu-id="416b7-119">PerfCounter.dll は、カテゴリ オプションのレジストリ設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="416b7-119">PerfCounter.dll does use the CategoryOptions registry setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="416b7-120">子要素</span><span class="sxs-lookup"><span data-stu-id="416b7-120">Child Elements</span></span>  
 <span data-ttu-id="416b7-121">[なし] :</span><span class="sxs-lookup"><span data-stu-id="416b7-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="416b7-122">親要素</span><span class="sxs-lookup"><span data-stu-id="416b7-122">Parent Elements</span></span>  
  
|<span data-ttu-id="416b7-123">要素</span><span class="sxs-lookup"><span data-stu-id="416b7-123">Element</span></span>|<span data-ttu-id="416b7-124">説明</span><span class="sxs-lookup"><span data-stu-id="416b7-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="416b7-125">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="416b7-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="416b7-126">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="416b7-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="416b7-127">解説</span><span class="sxs-lookup"><span data-stu-id="416b7-127">Remarks</span></span>  
 <span data-ttu-id="416b7-128">NET Framework 4 より前のバージョンの .NET Framework では、読み込まれた PerfCounter.dll のバージョンは、プロセスに読み込まれたランタイムに対応していました。</span><span class="sxs-lookup"><span data-stu-id="416b7-128">In versions of the .NET Framework before the .NET Framework 4, the version of PerfCounter.dll that was loaded corresponded to the runtime that was loaded in the process.</span></span> <span data-ttu-id="416b7-129">コンピューターに .NET Framework バージョン 1.1 と .NET Framework 2.0 の両方がインストールされている場合、.NET Framework 1.1 アプリケーションは .NET Framework 1.1 バージョンの PerfCounter.dll を読み込みます。</span><span class="sxs-lookup"><span data-stu-id="416b7-129">If a computer had both the .NET Framework version 1.1 and the .NET Framework 2.0 installed, a .NET Framework 1.1 application would load the .NET Framework 1.1 version of PerfCounter.dll.</span></span> <span data-ttu-id="416b7-130">NET Framework 4 以降、最新のインストールバージョンの PerfCounter.dll が読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="416b7-130">Starting with the .NET Framework 4, the newest installed version of PerfCounter.dll is loaded.</span></span> <span data-ttu-id="416b7-131">つまり、.NET Framework 4 がコンピュータにインストールされている場合、.NET Framework 1.1 アプリケーションは.NET Framework 4 バージョンの PerfCounter.dll を読み込みます。</span><span class="sxs-lookup"><span data-stu-id="416b7-131">This means that a .NET Framework 1.1 application will load the .NET Framework 4 version of PerfCounter.dll if the .NET Framework 4 is installed on the computer.</span></span>  
  
 <span data-ttu-id="416b7-132">パフォーマンス カウンターを使用する場合、.NET Framework 4 以降、PerfCounter.dll は、カテゴリ固有の共有メモリまたはグローバル共有メモリから読み取る必要があるかどうかを判断する各プロバイダーの CategoryOptions レジストリ エントリを確認します。</span><span class="sxs-lookup"><span data-stu-id="416b7-132">Starting with the .NET Framework 4, when consuming performance counters, PerfCounter.dll checks the CategoryOptions registry entry for each provider to determine whether it should read from category-specific shared memory or global shared memory.</span></span> <span data-ttu-id="416b7-133">.NET Framework 1.1 PerfCounter.dll は、カテゴリ固有の共有メモリを認識していないため、レジストリ エントリを読み取りません。常にグローバル共有メモリから読み取ります。</span><span class="sxs-lookup"><span data-stu-id="416b7-133">The .NET Framework 1.1 PerfCounter.dll does not read that registry entry, because it is not aware of category-specific shared memory; it always reads from global shared memory.</span></span>  
  
 <span data-ttu-id="416b7-134">下位互換性を維持するために、.NET Framework 1.1 アプリケーションで実行している場合、.NET Framework 4 PerfCounter.dll はカテゴリ オプションのレジストリ エントリをチェックしません。</span><span class="sxs-lookup"><span data-stu-id="416b7-134">For backward compatibility, the .NET Framework 4 PerfCounter.dll does not check the CategoryOptions registry entry when running in a .NET Framework 1.1 application.</span></span> <span data-ttu-id="416b7-135">単に.NET Framework 1.1 PerfCounter.dll と同じように、グローバル共有メモリを使用します。</span><span class="sxs-lookup"><span data-stu-id="416b7-135">It simply uses global shared memory, just like the .NET Framework 1.1 PerfCounter.dll.</span></span> <span data-ttu-id="416b7-136">ただし、.NET Framework 4 PerfCounter.dll に対して、要素を有効に`<forcePerformanceCounterUniqueSharedMemoryReads>`することでレジストリ設定を確認するように指示できます。</span><span class="sxs-lookup"><span data-stu-id="416b7-136">However, you can instruct the .NET Framework 4 PerfCounter.dll to check the registry setting by enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="416b7-137">要素を`<forcePerformanceCounterUniqueSharedMemoryReads>`有効にしても、カテゴリ固有の共有メモリが使用されるとは保証されません。</span><span class="sxs-lookup"><span data-stu-id="416b7-137">Enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element does not guarantee that category-specific shared memory will be used.</span></span> <span data-ttu-id="416b7-138">設定を有効`true`にした場合にのみ、PerfCounter.dll がカテゴリ オプションレジストリ設定を参照します。</span><span class="sxs-lookup"><span data-stu-id="416b7-138">Setting enabled to `true` only causes PerfCounter.dll to reference the CategoryOptions registry setting.</span></span> <span data-ttu-id="416b7-139">カテゴリ オプションの既定の設定では、カテゴリ固有の共有メモリを使用します。ただし、グローバル共有メモリを使用することを示すように CategoryOptions を変更できます。</span><span class="sxs-lookup"><span data-stu-id="416b7-139">The default setting for CategoryOptions is to use category-specific shared memory; however, you can change CategoryOptions to indicate that global shared memory should be used.</span></span>  
  
 <span data-ttu-id="416b7-140">カテゴリオプション設定を含むレジストリ キーは、カテゴリ名\\\>\パフォーマンスHKEY_LOCAL_MACHINE\システム\現在のコントロール セット\サービス<です。</span><span class="sxs-lookup"><span data-stu-id="416b7-140">The registry key that contains the CategoryOptions setting is HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\<categoryName\>\Performance.</span></span> <span data-ttu-id="416b7-141">既定では、カテゴリ オプションは 3 に設定され、カテゴリ固有の共有メモリを使用するように PerfCounter.dll に指示します。</span><span class="sxs-lookup"><span data-stu-id="416b7-141">By default, CategoryOptions is set to 3, which instructs PerfCounter.dll to use category-specific shared memory.</span></span> <span data-ttu-id="416b7-142">カテゴリ オプションが 0 に設定されている場合、PerfCounter.dll はグローバル共有メモリを使用します。</span><span class="sxs-lookup"><span data-stu-id="416b7-142">If CategoryOptions is set to 0, PerfCounter.dll uses global shared memory.</span></span> <span data-ttu-id="416b7-143">インスタンスデータは、作成されるインスタンスの名前が再利用されるインスタンスと同じ場合にのみ再利用されます。</span><span class="sxs-lookup"><span data-stu-id="416b7-143">Instance data will be reused only if the name of the instance being created is identical to the instance being reused.</span></span> <span data-ttu-id="416b7-144">すべてのバージョンは、カテゴリに書き込むことができるでしょう。</span><span class="sxs-lookup"><span data-stu-id="416b7-144">All versions will be able to write to the category.</span></span> <span data-ttu-id="416b7-145">CategoryOptions を 1 に設定すると、グローバル共有メモリが使用されますが、カテゴリ名が再利用されるカテゴリと同じ長さであればインスタンス データを再利用できます。</span><span class="sxs-lookup"><span data-stu-id="416b7-145">If CategoryOptions is set to 1, global shared memory is used, but instance data can be reused if the category name is the same length as the category being reused.</span></span>  
  
 <span data-ttu-id="416b7-146">設定 0 と 1 は、メモリ リークやパフォーマンス カウンタ メモリの不足につながる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="416b7-146">The settings 0 and 1 can lead to memory leaks and the filling up of performance counter memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="416b7-147">例</span><span class="sxs-lookup"><span data-stu-id="416b7-147">Example</span></span>  
 <span data-ttu-id="416b7-148">次の例では、PerfCounter.dll がカテゴリ固有の共有メモリを使用するかどうかを判断するために CategoryOptions レジストリ エントリを参照するように指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="416b7-148">The following example shows how to specify that PerfCounter.dll should reference the CategoryOptions registry entry to determine whether it should use category-specific shared memory.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="416b7-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="416b7-149">See also</span></span>

- [<span data-ttu-id="416b7-150">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="416b7-150">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="416b7-151">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="416b7-151">Configuration File Schema</span></span>](../index.md)
