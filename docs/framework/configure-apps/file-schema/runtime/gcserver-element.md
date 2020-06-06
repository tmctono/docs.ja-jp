---
title: gcServer 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcServer
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcServer
helpviewer_keywords:
- gcServer element
- <gcServer> element
ms.assetid: 8d25b80e-2581-4803-bd87-a59528e3cb03
ms.openlocfilehash: 8eab5e36bab90510aff4f1a3e15328197ac59ed7
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "73968944"
---
# <a name="gcserver-element"></a><span data-ttu-id="edfef-102">\<gcServer> 要素</span><span class="sxs-lookup"><span data-stu-id="edfef-102">\<gcServer> element</span></span>

<span data-ttu-id="edfef-103">共通言語ランタイムがサーバーのガベージ コレクションを実行するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="edfef-103">Specifies whether the common language runtime runs server garbage collection.</span></span>

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;[\<runtime>](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<gcServer>

## <a name="syntax"></a><span data-ttu-id="edfef-104">構文</span><span class="sxs-lookup"><span data-stu-id="edfef-104">Syntax</span></span>

```xml
<gcServer
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="edfef-105">属性と要素</span><span class="sxs-lookup"><span data-stu-id="edfef-105">Attributes and elements</span></span>

<span data-ttu-id="edfef-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="edfef-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="edfef-107">属性</span><span class="sxs-lookup"><span data-stu-id="edfef-107">Attributes</span></span>

|<span data-ttu-id="edfef-108">属性</span><span class="sxs-lookup"><span data-stu-id="edfef-108">Attribute</span></span>|<span data-ttu-id="edfef-109">説明</span><span class="sxs-lookup"><span data-stu-id="edfef-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="edfef-110">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="edfef-110">Required attribute.</span></span><br /><br /><span data-ttu-id="edfef-111">ランタイムがサーバーのガベージ コレクションを実行するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="edfef-111">Specifies whether the runtime runs server garbage collection.</span></span>|

#### <a name="enabled-attribute"></a><span data-ttu-id="edfef-112">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="edfef-112">enabled attribute</span></span>

|<span data-ttu-id="edfef-113">値</span><span class="sxs-lookup"><span data-stu-id="edfef-113">Value</span></span>|<span data-ttu-id="edfef-114">Description</span><span class="sxs-lookup"><span data-stu-id="edfef-114">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="edfef-115">サーバーのガベージ コレクションを実行しません。</span><span class="sxs-lookup"><span data-stu-id="edfef-115">Does not run server garbage collection.</span></span> <span data-ttu-id="edfef-116">既定値です。</span><span class="sxs-lookup"><span data-stu-id="edfef-116">This is the default.</span></span>|
|`true`|<span data-ttu-id="edfef-117">サーバーのガベージ コレクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="edfef-117">Runs server garbage collection.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="edfef-118">子要素</span><span class="sxs-lookup"><span data-stu-id="edfef-118">Child elements</span></span>

<span data-ttu-id="edfef-119">なし。</span><span class="sxs-lookup"><span data-stu-id="edfef-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="edfef-120">親要素</span><span class="sxs-lookup"><span data-stu-id="edfef-120">Parent elements</span></span>

|<span data-ttu-id="edfef-121">要素</span><span class="sxs-lookup"><span data-stu-id="edfef-121">Element</span></span>|<span data-ttu-id="edfef-122">Description</span><span class="sxs-lookup"><span data-stu-id="edfef-122">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="edfef-123">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="edfef-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="edfef-124">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="edfef-124">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="edfef-125">解説</span><span class="sxs-lookup"><span data-stu-id="edfef-125">Remarks</span></span>

<span data-ttu-id="edfef-126">共通言語ランタイム (CLR) は、2 種類のガベージ コレクションをサポートしています。1 つはワークステーション ガベージ コレクションで、すべてのシステムで使用できるものです。もう 1 つはサーバー ガベージ コレクションで、マルチプロセッサ システムで使用できるものです。</span><span class="sxs-lookup"><span data-stu-id="edfef-126">The common language runtime (CLR) supports two types of garbage collection: workstation garbage collection, which is available on all systems, and server garbage collection, which is available on multiprocessor systems.</span></span> <span data-ttu-id="edfef-127">CLR が実行するガベージコレクションの種類を制御するには、 **gcServer**要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="edfef-127">Use the **gcServer** element to control the type of garbage collection the CLR performs.</span></span> <span data-ttu-id="edfef-128"><xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType> プロパティを使用して、サーバー ガベージ コレクションが有効かどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="edfef-128">Use the <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType> property to determine if server garbage collection is enabled.</span></span>

<span data-ttu-id="edfef-129">シングル プロセッサ コンピューターの場合、既定のワークステーション ガベージ コレクションが催促のオプションです。</span><span class="sxs-lookup"><span data-stu-id="edfef-129">For single-processor computers, the default workstation garbage collection should be the fastest option.</span></span> <span data-ttu-id="edfef-130">2 つのプロセッサを搭載するコンピューターで、ワークステーションかサーバーのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="edfef-130">Either workstation or server can be used for two-processor computers.</span></span> <span data-ttu-id="edfef-131">3 つ以上のプロセッサでは、サーバー ガベージ コレクションが最速のオプションです。</span><span class="sxs-lookup"><span data-stu-id="edfef-131">Server garbage collection should be the fastest option for more than two processors.</span></span> <span data-ttu-id="edfef-132">ほとんどの場合、マルチプロセッササーバーシステムはサーバー GC を無効にし、サーバーアプリの多くのインスタンスが同じコンピューターで実行されるときに、ワークステーション GC を使用します。</span><span class="sxs-lookup"><span data-stu-id="edfef-132">Most commonly, multiprocessor server systems disable server GC and use workstation GC instead when many instances of a server app run on the same machine.</span></span>

<span data-ttu-id="edfef-133">この要素は、アプリケーション構成ファイルでのみ使用できます。要素がマシン構成ファイルにある場合には無視されます。</span><span class="sxs-lookup"><span data-stu-id="edfef-133">This element can be used only in the application configuration file; it is ignored if it is in the machine configuration file.</span></span>

> [!NOTE]
> <span data-ttu-id="edfef-134">.NET Framework 4 以前のバージョンでは、サーバー ガベージ コレクションを有効にすると同時実行ガベージ コレクションが使用できません。</span><span class="sxs-lookup"><span data-stu-id="edfef-134">In the .NET Framework 4 and earlier versions, concurrent garbage collection is not available when server garbage collection is enabled.</span></span> <span data-ttu-id="edfef-135">.NET Framework 4.5 以降では、サーバーのガベージコレクションは同時に実行されます。</span><span class="sxs-lookup"><span data-stu-id="edfef-135">Starting with the .NET Framework 4.5, server garbage collection is concurrent.</span></span> <span data-ttu-id="edfef-136">非同時サーバーガベージコレクションを使用するには、 **gcServer**要素をに設定し、 `true` [gcConcurrent 要素](gcconcurrent-element.md)をに設定し `false` ます。</span><span class="sxs-lookup"><span data-stu-id="edfef-136">To use non-concurrent server garbage collection, set the **gcServer** element to `true` and the [gcConcurrent element](gcconcurrent-element.md) to `false`.</span></span>

<span data-ttu-id="edfef-137">.NET Framework 4.6.2 以降では、次の要素を使用してサーバー GC を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="edfef-137">Starting with .NET Framework 4.6.2, you can also use the following elements to configure server GC:</span></span>

- <span data-ttu-id="edfef-138">[GCNoAffinitize](gcnoaffinitize-element.md)。サーバー GC ヒープとプロセッサの間にアフィニティがあるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="edfef-138">[GCNoAffinitize](gcnoaffinitize-element.md), which specifies whether there is an affinity between server GC heaps and processors.</span></span> <span data-ttu-id="edfef-139">既定では、プロセッサごとに1つのサーバー GC ヒープがあります。</span><span class="sxs-lookup"><span data-stu-id="edfef-139">By default, there is one server GC heap for each processor.</span></span>

- <span data-ttu-id="edfef-140">"プロセスで使用されるヒープの[数を制限](gcheapcount-element.md)する"。</span><span class="sxs-lookup"><span data-stu-id="edfef-140">[GCHeapCount](gcheapcount-element.md), which limits the number of heaps used by a process.</span></span>

- <span data-ttu-id="edfef-141">[GCHeapAffinitizeMask](gcheapaffinitizemask-element.md)は、使用可能なサーバー GC ヒープと個々のプロセッサ間の関係を定義します。</span><span class="sxs-lookup"><span data-stu-id="edfef-141">[GCHeapAffinitizeMask](gcheapaffinitizemask-element.md), which defines the affinity between the available server GC heaps and individual processors.</span></span>

## <a name="example"></a><span data-ttu-id="edfef-142">例</span><span class="sxs-lookup"><span data-stu-id="edfef-142">Example</span></span>

<span data-ttu-id="edfef-143">次の例では、サーバーのガベージコレクションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="edfef-143">The following example enables server garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="edfef-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="edfef-144">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="edfef-145">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="edfef-145">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="edfef-146">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="edfef-146">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="edfef-147">同時実行ガベージコレクションを無効にするには</span><span class="sxs-lookup"><span data-stu-id="edfef-147">To disable concurrent garbage collection</span></span>](gcconcurrent-element.md#to-disable-background-garbage-collection)
