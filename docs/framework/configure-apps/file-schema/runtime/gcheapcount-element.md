---
title: G不正 Apcount 要素
ms.date: 11/08/2019
helpviewer_keywords:
- gcHeapCount element
- <gcHeapCount> element
ms.openlocfilehash: 3d6cac4185af182758cb82e6bfd9d96ed24869b4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283070"
---
# <a name="gcheapcount-element"></a><span data-ttu-id="2af52-102">\<G> 要素</span><span class="sxs-lookup"><span data-stu-id="2af52-102">\<GCHeapCount> element</span></span>

<span data-ttu-id="2af52-103">サーバーのガベージコレクションに使用するヒープまたはスレッドの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="2af52-103">Specifies the number of heaps/threads to use for server garbage collection.</span></span>

<span data-ttu-id="2af52-104">\<構成 > </span><span class="sxs-lookup"><span data-stu-id="2af52-104">\<configuration></span></span>\
<span data-ttu-id="2af52-105">&nbsp;&nbsp;\<ランタイム > </span><span class="sxs-lookup"><span data-stu-id="2af52-105">&nbsp;&nbsp;\<runtime></span></span>\
<span data-ttu-id="2af52-106">&nbsp;&nbsp;&nbsp;&nbsp;\<></span><span class="sxs-lookup"><span data-stu-id="2af52-106">&nbsp;&nbsp;&nbsp;&nbsp;\<GCHeapCount></span></span>

## <a name="syntax"></a><span data-ttu-id="2af52-107">構文</span><span class="sxs-lookup"><span data-stu-id="2af52-107">Syntax</span></span>

```xml
<GCHeapCount
   enabled="nn"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2af52-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="2af52-108">Attributes and elements</span></span>

<span data-ttu-id="2af52-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2af52-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="2af52-110">属性</span><span class="sxs-lookup"><span data-stu-id="2af52-110">Attributes</span></span>

|<span data-ttu-id="2af52-111">属性</span><span class="sxs-lookup"><span data-stu-id="2af52-111">Attribute</span></span>|<span data-ttu-id="2af52-112">説明</span><span class="sxs-lookup"><span data-stu-id="2af52-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="2af52-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="2af52-113">Required attribute.</span></span><br /><br /><span data-ttu-id="2af52-114">サーバーのガベージコレクションに使用するヒープの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="2af52-114">Specifies the number of heaps to use for server garbage collection.</span></span> <span data-ttu-id="2af52-115">実際のヒープ数は、指定するヒープの数とプロセスで使用できるプロセッサの数の最小値です。</span><span class="sxs-lookup"><span data-stu-id="2af52-115">The actual number of heaps is the minimum of the number of heaps you specify and the number of processors your process is allowed to use.</span></span> |

#### <a name="enabled-attribute"></a><span data-ttu-id="2af52-116">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="2af52-116">enabled attribute</span></span>

|<span data-ttu-id="2af52-117">値</span><span class="sxs-lookup"><span data-stu-id="2af52-117">Value</span></span>|<span data-ttu-id="2af52-118">説明</span><span class="sxs-lookup"><span data-stu-id="2af52-118">Description</span></span>|
|-----------|-----------------|
|`nn`|<span data-ttu-id="2af52-119">サーバー GC に使用するヒープの数。</span><span class="sxs-lookup"><span data-stu-id="2af52-119">The number of heaps to use for server GC.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="2af52-120">子要素</span><span class="sxs-lookup"><span data-stu-id="2af52-120">Child elements</span></span>

<span data-ttu-id="2af52-121">なし。</span><span class="sxs-lookup"><span data-stu-id="2af52-121">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2af52-122">親要素</span><span class="sxs-lookup"><span data-stu-id="2af52-122">Parent elements</span></span>

|<span data-ttu-id="2af52-123">要素</span><span class="sxs-lookup"><span data-stu-id="2af52-123">Element</span></span>|<span data-ttu-id="2af52-124">説明</span><span class="sxs-lookup"><span data-stu-id="2af52-124">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="2af52-125">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="2af52-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="2af52-126">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2af52-126">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="2af52-127">コメント</span><span class="sxs-lookup"><span data-stu-id="2af52-127">Remarks</span></span>

<span data-ttu-id="2af52-128">既定では、サーバー GC スレッドはそれぞれの CPU とハード関係があるため、1つの GC ヒープ、1つのサーバー GC スレッド、および各プロセッサにつき1つのバックグラウンドサーバー GC スレッドが存在するようになります。</span><span class="sxs-lookup"><span data-stu-id="2af52-128">By default, server GC threads are hard-affinitized with their respective CPU so that there is one GC heap, one server GC thread, and one background server GC thread for each processor.</span></span> <span data-ttu-id="2af52-129">.NET Framework 4.6.2 以降では、 **g Apcount**要素を使用して、アプリケーションでサーバー GC に使用されるヒープの数を制限することができます。</span><span class="sxs-lookup"><span data-stu-id="2af52-129">Starting with .NET Framework 4.6.2, you can use the **GCHeapCount** element to limit the number of heaps used by your application for server GC.</span></span> <span data-ttu-id="2af52-130">サーバー GC に使用されるヒープの数を制限することは、サーバーアプリケーションの複数のインスタンスを実行するシステムに特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2af52-130">Limiting the number of heaps used for server GC is particularly useful for systems that run multiple instances of a server application.</span></span>

<span data-ttu-id="2af52-131">通常は、次の2つのフラグと共に使用**されます**。</span><span class="sxs-lookup"><span data-stu-id="2af52-131">**GCHeapCount** is typically used along with two other flags:</span></span>

- <span data-ttu-id="2af52-132">[GCNoAffinitize](gcnoaffinitize-element.md)。サーバー GC スレッド/ヒープが cpu と関連付けられているかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="2af52-132">[GCNoAffinitize](gcnoaffinitize-element.md), which controls whether server GC threads/heaps are affinitized with CPUs.</span></span>

- <span data-ttu-id="2af52-133">[GCHeapAffinitizeMask](gcheapaffinitizemask-element.md)。 cpu との GC スレッド/ヒープの関係を制御します。</span><span class="sxs-lookup"><span data-stu-id="2af52-133">[GCHeapAffinitizeMask](gcheapaffinitizemask-element.md), which controls the affinity of GC threads/heaps with CPUs.</span></span>

<span data-ttu-id="2af52-134">**GGCNoAffinitize**が設定されていて、が無効になっている場合 (既定の設定)、 *nn* GC スレッド/ヒープと最初の*nn*プロセッサの間に関係があります。</span><span class="sxs-lookup"><span data-stu-id="2af52-134">If **GCHeapCount** is set and **GCNoAffinitize** is disabled (its default setting), there is an affinity between the *nn* GC threads/heaps and the first *nn* processors.</span></span> <span data-ttu-id="2af52-135">**GCHeapAffinitizeMask**要素を使用して、プロセスのサーバー GC ヒープによって使用されるプロセッサを指定できます。</span><span class="sxs-lookup"><span data-stu-id="2af52-135">You can use the **GCHeapAffinitizeMask** element to specify which processors are used by the process's server GC heaps.</span></span> <span data-ttu-id="2af52-136">それ以外の場合、システムで複数のサーバープロセスが実行されていると、プロセッサの使用率が重複します。</span><span class="sxs-lookup"><span data-stu-id="2af52-136">Otherwise, if multiple server processes are running on a system, their processor usage will overlap.</span></span>

<span data-ttu-id="2af52-137">**GGCNoAffinitize**が有効になっている場合、ガベージコレクターはサーバー gc に使用されるプロセッサの数を制限しますが、gc ヒープとプロセッサを関係付けしません。</span><span class="sxs-lookup"><span data-stu-id="2af52-137">If **GCHeapCount** is set and **GCNoAffinitize** is enabled, the garbage collector limits the number of processors used for server GC but does not affinitize GC heaps and processors.</span></span>

## <a name="example"></a><span data-ttu-id="2af52-138">例</span><span class="sxs-lookup"><span data-stu-id="2af52-138">Example</span></span>

<span data-ttu-id="2af52-139">次の例は、アプリケーションが10個のヒープ/スレッドを持つサーバー GC を使用することを示しています。</span><span class="sxs-lookup"><span data-stu-id="2af52-139">The following example indicates that an application uses server GC with 10 heaps/threads.</span></span> <span data-ttu-id="2af52-140">これらのヒープは、システムで実行されている他のアプリケーションのヒープと重複しないようにするため、 **GCHeapAffinitizeMask**を使用して、プロセスで cpu 0 ~ 9 を使用するように指定します。</span><span class="sxs-lookup"><span data-stu-id="2af52-140">Since you don't want those heaps to overlap with heaps from other applications running on the system, you use the **GCHeapAffinitizeMask** to specify that the process should use CPUs 0 through 9.</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCHeapAffinitizeMask enabled="1023"/>
   </runtime>
</configuration>
```

<span data-ttu-id="2af52-141">次の例では、サーバー GC スレッドを関係付け、GC ヒープ/スレッドの数を10に制限していません。</span><span class="sxs-lookup"><span data-stu-id="2af52-141">The following example does not affinitize server GC threads and limits the number of GC heaps/threads to 10.</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="2af52-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="2af52-142">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="2af52-143">GCNoAffinitize 要素</span><span class="sxs-lookup"><span data-stu-id="2af52-143">GCNoAffinitize element</span></span>](gcnoaffinitize-element.md)
- [<span data-ttu-id="2af52-144">GCHeapAffinitizeMask 要素</span><span class="sxs-lookup"><span data-stu-id="2af52-144">GCHeapAffinitizeMask element</span></span>](gcheapaffinitizemask-element.md)
- [<span data-ttu-id="2af52-145">ガベージ コレクションの基礎</span><span class="sxs-lookup"><span data-stu-id="2af52-145">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="2af52-146">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="2af52-146">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="2af52-147">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="2af52-147">Configuration File Schema</span></span>](../index.md)
