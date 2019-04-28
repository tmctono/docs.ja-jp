---
title: <performanceCounters> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounters element
- <performanceCounters> element
ms.assetid: a71f605b-c7d9-4501-a5c3-abcbb964a43f
ms.openlocfilehash: 6144bcbda69b2ba799e87c3e7fa2118fbe4d9bf6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673743"
---
# <a name="performancecounters-element"></a><span data-ttu-id="7453e-102">\<performanceCounters > 要素</span><span class="sxs-lookup"><span data-stu-id="7453e-102">\<performanceCounters> Element</span></span>

<span data-ttu-id="7453e-103">パフォーマンス カウンターが共有するグローバル メモリのサイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="7453e-103">Specifies the size of the global memory shared by performance counters.</span></span>

 <span data-ttu-id="7453e-104">\<configuration>\\</span><span class="sxs-lookup"><span data-stu-id="7453e-104">\<configuration>\\</span></span>
<span data-ttu-id="7453e-105">\<system.diagnostics>\\</span><span class="sxs-lookup"><span data-stu-id="7453e-105">\<system.diagnostics>\\</span></span>
<span data-ttu-id="7453e-106">\<performanceCounters></span><span class="sxs-lookup"><span data-stu-id="7453e-106">\<performanceCounters></span></span>

## <a name="syntax"></a><span data-ttu-id="7453e-107">構文</span><span class="sxs-lookup"><span data-stu-id="7453e-107">Syntax</span></span>

```xml
<performanceCounters filemappingsize="524288" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7453e-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7453e-108">Attributes and Elements</span></span>

<span data-ttu-id="7453e-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7453e-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="7453e-110">属性</span><span class="sxs-lookup"><span data-stu-id="7453e-110">Attributes</span></span>

|<span data-ttu-id="7453e-111">属性</span><span class="sxs-lookup"><span data-stu-id="7453e-111">Attribute</span></span>|<span data-ttu-id="7453e-112">説明</span><span class="sxs-lookup"><span data-stu-id="7453e-112">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="7453e-113">filemappingsize</span><span class="sxs-lookup"><span data-stu-id="7453e-113">filemappingsize</span></span>|<span data-ttu-id="7453e-114">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="7453e-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="7453e-115">パフォーマンス カウンターが共有するグローバル メモリのバイト単位のサイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="7453e-115">Specifies the size, in bytes, of the global memory shared by performance counters.</span></span> <span data-ttu-id="7453e-116">既定値は 524288 です。</span><span class="sxs-lookup"><span data-stu-id="7453e-116">The default is 524288.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="7453e-117">子要素</span><span class="sxs-lookup"><span data-stu-id="7453e-117">Child Elements</span></span>

<span data-ttu-id="7453e-118">なし。</span><span class="sxs-lookup"><span data-stu-id="7453e-118">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7453e-119">親要素</span><span class="sxs-lookup"><span data-stu-id="7453e-119">Parent Elements</span></span>

|<span data-ttu-id="7453e-120">要素</span><span class="sxs-lookup"><span data-stu-id="7453e-120">Element</span></span>|<span data-ttu-id="7453e-121">説明</span><span class="sxs-lookup"><span data-stu-id="7453e-121">Description</span></span>|
|-------------|-----------------|
|`Configuration`|<span data-ttu-id="7453e-122">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="7453e-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`system.diagnostics`|<span data-ttu-id="7453e-123">ASP.NET 構成セクションのルート要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="7453e-123">Specifies the root element for the ASP.NET configuration section.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7453e-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="7453e-124">Remarks</span></span>

<span data-ttu-id="7453e-125">パフォーマンス カウンターでは、メモリ マップ ファイル、または共有メモリを使用して、パフォーマンス データを公開します。</span><span class="sxs-lookup"><span data-stu-id="7453e-125">Performance counters use a memory mapped file, or shared memory, to publish performance data.</span></span>  <span data-ttu-id="7453e-126">インスタンスの数を一度に使用できる共有メモリのサイズを決定します。</span><span class="sxs-lookup"><span data-stu-id="7453e-126">The size of the shared memory determines how many instances can be used at once.</span></span>  <span data-ttu-id="7453e-127">共有メモリの 2 種類があります。 グローバルの共有メモリと個別の共有メモリです。</span><span class="sxs-lookup"><span data-stu-id="7453e-127">There are two types of shared memory: global shared memory and separate shared memory.</span></span>  <span data-ttu-id="7453e-128">グローバル共有メモリは、.NET Framework バージョン 1.0 または 1.1 と共にインストールされるすべてのパフォーマンス カウンター カテゴリによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="7453e-128">The global shared memory is used by all performance counter categories installed with the .NET Framework versions 1.0 or 1.1.</span></span>  <span data-ttu-id="7453e-129">.NET Framework version 2.0 にインストールされているパフォーマンス カウンター カテゴリは、独自のメモリを持っている各パフォーマンス カウンター カテゴリ別の共有メモリを使用します。</span><span class="sxs-lookup"><span data-stu-id="7453e-129">Performance counter categories installed with the .NET Framework version 2.0 use separate shared memory, with each performance counter category having its own memory.</span></span>

<span data-ttu-id="7453e-130">グローバル共有メモリのサイズは、構成ファイルでのみ設定できます。</span><span class="sxs-lookup"><span data-stu-id="7453e-130">The size of global shared memory can be set only with a configuration file.</span></span>  <span data-ttu-id="7453e-131">既定のサイズは 524, 288 バイト、最大サイズは 33,554, 432 バイト、および最小のサイズは 32,768 バイトです。</span><span class="sxs-lookup"><span data-stu-id="7453e-131">The default size is 524,288 byes, the maximum size is 33,554,432 bytes, and the minimum size is 32,768 bytes.</span></span>  <span data-ttu-id="7453e-132">グローバル共有メモリは、すべてのプロセスとカテゴリが共有しているために、最初の作成者は、サイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="7453e-132">Since the global shared memory is shared by all processes and categories, the first creator specifies the size.</span></span>  <span data-ttu-id="7453e-133">アプリケーション構成ファイルのサイズを定義すると、のみには、そのサイズは、アプリケーションが最初のアプリケーションを実行するパフォーマンス カウンターを原因となる場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="7453e-133">If you define the size in your application configuration file, that size is only used if your application is the first application that causes the performance counters to execute.</span></span>  <span data-ttu-id="7453e-134">正しい場所を指定するため、`filemappingsize`値は、Machine.config ファイルです。</span><span class="sxs-lookup"><span data-stu-id="7453e-134">Therefore the correct location to specify the `filemappingsize` value is the Machine.config file.</span></span>  <span data-ttu-id="7453e-135">個々 のパフォーマンス カウンターによって、最終的に多数の異なる名前を持つパフォーマンス カウンター インスタンスが作成されている場合、グローバル共有メモリが使い果たされるグローバル共有メモリ内のメモリを解放できません。</span><span class="sxs-lookup"><span data-stu-id="7453e-135">Memory in the global shared memory cannot be released by individual performance counters, so eventually global shared memory is exhausted if a large number of performance counter instances with different names are created.</span></span>

<span data-ttu-id="7453e-136">別の共有メモリのサイズが、レジストリの DWORD FileMappingSize 値キーの hkey_local_machine \system\currentcontrolset\services\\*\<カテゴリ名 >* \Performance が参照されています。最初に、構成ファイルのグローバル共有メモリに指定された値に続きます。</span><span class="sxs-lookup"><span data-stu-id="7453e-136">For the size of separate shared memory, the DWORD FileMappingSize value in the registry key HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\\*\<category name>* \Performance is referenced first, followed by the value specified for the global shared memory in the configuration file.</span></span> <span data-ttu-id="7453e-137">FileMappingSize 値が存在しないかどうかは、別の共有メモリのサイズが 4 分の 1 に設定されて (1/4)、構成ファイルのグローバル設定です。</span><span class="sxs-lookup"><span data-stu-id="7453e-137">If the FileMappingSize value does not exist, then the separate shared memory size is set to one fourth (1/4) the global setting in the configuration file.</span></span>

## <a name="see-also"></a><span data-ttu-id="7453e-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="7453e-138">See also</span></span>

- <xref:System.Diagnostics.PerformanceCounter>
- <xref:System.Diagnostics.PerformanceCounterCategory>
- <xref:System.Diagnostics.PerformanceCounter.InstanceLifetime%2A>
- <xref:System.Diagnostics.PerformanceCounterInstanceLifetime>
