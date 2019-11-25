---
title: GCHeapAffinitizeMask 要素
ms.date: 11/08/2019
helpviewer_keywords:
- gcHeapCount element
- <gcHeapCount> element
ms.openlocfilehash: 09d6523fb10692dd3617a3827d5bccf112bc632b
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73978421"
---
# <a name="gcheapaffinitizemask-element"></a><span data-ttu-id="07b4c-102">\<GCHeapAffinitizeMask > 要素</span><span class="sxs-lookup"><span data-stu-id="07b4c-102">\<GCHeapAffinitizeMask> element</span></span>

<span data-ttu-id="07b4c-103">GC ヒープと個々のプロセッサ間の関係を定義します。</span><span class="sxs-lookup"><span data-stu-id="07b4c-103">Defines the affinity between GC heaps and individual processors.</span></span>

<span data-ttu-id="07b4c-104">\<構成 > </span><span class="sxs-lookup"><span data-stu-id="07b4c-104">\<configuration></span></span>\
<span data-ttu-id="07b4c-105">&nbsp;&nbsp;\<ランタイム > </span><span class="sxs-lookup"><span data-stu-id="07b4c-105">&nbsp;&nbsp;\<runtime></span></span>\
<span data-ttu-id="07b4c-106">&nbsp;&nbsp;&nbsp;&nbsp;\<GCHeapAffinitizeMask ></span><span class="sxs-lookup"><span data-stu-id="07b4c-106">&nbsp;&nbsp;&nbsp;&nbsp;\<GCHeapAffinitizeMask></span></span>

## <a name="syntax"></a><span data-ttu-id="07b4c-107">構文</span><span class="sxs-lookup"><span data-stu-id="07b4c-107">Syntax</span></span>

```xml
<GCHeapAffinitizeMask
   enabled="nnnn"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="07b4c-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="07b4c-108">Attributes and elements</span></span>

<span data-ttu-id="07b4c-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="07b4c-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="07b4c-110">属性</span><span class="sxs-lookup"><span data-stu-id="07b4c-110">Attributes</span></span>

|<span data-ttu-id="07b4c-111">属性</span><span class="sxs-lookup"><span data-stu-id="07b4c-111">Attribute</span></span>|<span data-ttu-id="07b4c-112">説明</span><span class="sxs-lookup"><span data-stu-id="07b4c-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="07b4c-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="07b4c-113">Required attribute.</span></span><br /><br /><span data-ttu-id="07b4c-114">GC ヒープと個々のプロセッサ間の関係を指定します。</span><span class="sxs-lookup"><span data-stu-id="07b4c-114">Specifies the affinity between GC heaps and individual processors.</span></span> |

#### <a name="enabled-attribute"></a><span data-ttu-id="07b4c-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="07b4c-115">enabled attribute</span></span>

|<span data-ttu-id="07b4c-116">[値]</span><span class="sxs-lookup"><span data-stu-id="07b4c-116">Value</span></span>|<span data-ttu-id="07b4c-117">説明</span><span class="sxs-lookup"><span data-stu-id="07b4c-117">Description</span></span>|
|-----------|-----------------|
|`nnnn`|<span data-ttu-id="07b4c-118">サーバー GC ヒープと個々のプロセッサ間の関係を定義するビットマスクを形成する10進値。</span><span class="sxs-lookup"><span data-stu-id="07b4c-118">A decimal value that forms a bitmask defining the affinity between server GC heaps and individual processors.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="07b4c-119">子要素</span><span class="sxs-lookup"><span data-stu-id="07b4c-119">Child elements</span></span>

<span data-ttu-id="07b4c-120">なし。</span><span class="sxs-lookup"><span data-stu-id="07b4c-120">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="07b4c-121">親要素</span><span class="sxs-lookup"><span data-stu-id="07b4c-121">Parent elements</span></span>

|<span data-ttu-id="07b4c-122">要素</span><span class="sxs-lookup"><span data-stu-id="07b4c-122">Element</span></span>|<span data-ttu-id="07b4c-123">説明</span><span class="sxs-lookup"><span data-stu-id="07b4c-123">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="07b4c-124">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="07b4c-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="07b4c-125">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="07b4c-125">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="07b4c-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="07b4c-126">Remarks</span></span>

<span data-ttu-id="07b4c-127">既定では、サーバー GC スレッドはそれぞれの CPU とハード関係があるため、1つの GC ヒープ、1つのサーバー GC スレッド、および各プロセッサにつき1つのバックグラウンドサーバー GC スレッドが存在するようになります。</span><span class="sxs-lookup"><span data-stu-id="07b4c-127">By default, server GC threads are hard-affinitized with their respective CPU so that there is one GC heap, one server GC thread, and one background server GC thread for each processor.</span></span> <span data-ttu-id="07b4c-128">4\.6.2 .NET Framework 以降では、ヒープの数が**g Apcount**要素によって制限されている場合に、 **GCHeapAffinitizeMask**要素を使用して、サーバー GC ヒープとプロセッサ間の関係を制御できます。</span><span class="sxs-lookup"><span data-stu-id="07b4c-128">Starting with .NET Framework 4.6.2, you can use the **GCHeapAffinitizeMask** element to control the affinity between server GC heaps and processors when the number of heaps is limited by the **GCHeapCount** element.</span></span>

<span data-ttu-id="07b4c-129">**GCHeapAffinitizeMask**は通常、次の2つのフラグと共に使用されます。</span><span class="sxs-lookup"><span data-stu-id="07b4c-129">**GCHeapAffinitizeMask** is typically used along with two other flags:</span></span>

- <span data-ttu-id="07b4c-130">[GCNoAffinitize](gcnoaffinitize-element.md)。サーバー GC スレッド/ヒープが cpu と関連付けられているかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="07b4c-130">[GCNoAffinitize](gcnoaffinitize-element.md), which controls whether server GC threads/heaps are affinitized with CPUs.</span></span> <span data-ttu-id="07b4c-131">[GCNoAffinitize](gcnoaffinitize-element.md)要素の `enabled` 属性は、 **GCHeapAffinitizeMask**設定が使用されるように `false` (既定値) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="07b4c-131">The `enabled` attribute of the [GCNoAffinitize](gcnoaffinitize-element.md) element must be `false` (its default value) for the **GCHeapAffinitizeMask** setting to be used.</span></span>

- <span data-ttu-id="07b4c-132">"サーバー GC のプロセスで使用されるヒープの[数を制限](gcheapcount-element.md)する"。</span><span class="sxs-lookup"><span data-stu-id="07b4c-132">[GCHeapCount](gcheapcount-element.md), which limits the number of heaps used by the process for server GC.</span></span> <span data-ttu-id="07b4c-133">既定では、プロセッサごとに1つのヒープがあります。</span><span class="sxs-lookup"><span data-stu-id="07b4c-133">By default, there is one heap for each processor.</span></span>

<span data-ttu-id="07b4c-134">**nnnn**は、10進値として表現されるビットマスクです。</span><span class="sxs-lookup"><span data-stu-id="07b4c-134">**nnnn** is a bit mask expressed as a decimal value.</span></span> <span data-ttu-id="07b4c-135">バイト0のビット0はプロセッサ0を表し、バイト0のビット1はプロセッサ1を表します。</span><span class="sxs-lookup"><span data-stu-id="07b4c-135">Bit 0 of byte 0 represents processor 0, bit 1 of byte 0 represents processor 1, and so on.</span></span> <span data-ttu-id="07b4c-136">(例:</span><span class="sxs-lookup"><span data-stu-id="07b4c-136">For example:</span></span>

```xml
<GCHeapAffinitizeMask enabled="1023"/>
```

<span data-ttu-id="07b4c-137">値1023は、0x3FF または 0011 1111 1111b です。</span><span class="sxs-lookup"><span data-stu-id="07b4c-137">A value of 1023 is 0x3FF or 0011 1111 1111b.</span></span> <span data-ttu-id="07b4c-138">このプロセスでは、プロセッサ0からプロセッサ9までの10個のプロセッサが使用されます。</span><span class="sxs-lookup"><span data-stu-id="07b4c-138">The process uses 10 processors, from processor 0 through processor 9.</span></span>

## <a name="example"></a><span data-ttu-id="07b4c-139">例</span><span class="sxs-lookup"><span data-stu-id="07b4c-139">Example</span></span>

<span data-ttu-id="07b4c-140">次の例は、アプリケーションが10個のヒープ/スレッドを持つサーバー GC を使用することを示しています。</span><span class="sxs-lookup"><span data-stu-id="07b4c-140">The following example indicates that an application uses server GC with 10 heaps/threads.</span></span> <span data-ttu-id="07b4c-141">これらのヒープは、システムで実行されている他のアプリケーションのヒープと重複しないようにするため、 **GCHeapAffinitizeMask**を使用して、プロセスで cpu 0 ~ 9 を使用するように指定します。</span><span class="sxs-lookup"><span data-stu-id="07b4c-141">Since you don't want those heaps to overlap with heaps from other applications running on the system, use **GCHeapAffinitizeMask** to specify that the process should use CPUs 0 through 9.</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCHeapAffinitizeMask enabled="1023"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="07b4c-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="07b4c-142">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="07b4c-143">GCNoAffinitize 要素</span><span class="sxs-lookup"><span data-stu-id="07b4c-143">GCNoAffinitize element</span></span>](gcnoaffinitize-element.md)
- [<span data-ttu-id="07b4c-144">G不正 Apcount 要素</span><span class="sxs-lookup"><span data-stu-id="07b4c-144">GCHeapCount element</span></span>](gcheapcount-element.md)
- [<span data-ttu-id="07b4c-145">ガベージ コレクションの基礎</span><span class="sxs-lookup"><span data-stu-id="07b4c-145">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="07b4c-146">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="07b4c-146">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="07b4c-147">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="07b4c-147">Configuration File Schema</span></span>](../index.md)
