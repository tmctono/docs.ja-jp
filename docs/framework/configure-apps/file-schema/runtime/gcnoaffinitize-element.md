---
title: GCNoAffinitize 要素
ms.date: 11/08/2019
helpviewer_keywords:
- gcNoAffinitize element
- <gcNoAffinitize> element
ms.openlocfilehash: 4031ff19131c905072696837d1622dbb6e54ae61
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73978415"
---
# <a name="gcnoaffinitize-element"></a><span data-ttu-id="faa30-102">\<GCNoAffinitize > 要素</span><span class="sxs-lookup"><span data-stu-id="faa30-102">\<GCNoAffinitize> element</span></span>

<span data-ttu-id="faa30-103">Cpu を使用してサーバー GC スレッドを関係付けするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="faa30-103">Specifies whether or not to affinitize server GC threads with CPUs.</span></span>

<span data-ttu-id="faa30-104">\<構成 > </span><span class="sxs-lookup"><span data-stu-id="faa30-104">\<configuration></span></span>\
<span data-ttu-id="faa30-105">&nbsp;&nbsp;\<ランタイム > </span><span class="sxs-lookup"><span data-stu-id="faa30-105">&nbsp;&nbsp;\<runtime></span></span>\
<span data-ttu-id="faa30-106">&nbsp;&nbsp;&nbsp;&nbsp;\<GCNoAffinitize ></span><span class="sxs-lookup"><span data-stu-id="faa30-106">&nbsp;&nbsp;&nbsp;&nbsp;\<GCNoAffinitize></span></span>

## <a name="syntax"></a><span data-ttu-id="faa30-107">構文</span><span class="sxs-lookup"><span data-stu-id="faa30-107">Syntax</span></span>

```xml
<GCNoAffinitize
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="faa30-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="faa30-108">Attributes and elements</span></span>

<span data-ttu-id="faa30-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="faa30-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="faa30-110">属性</span><span class="sxs-lookup"><span data-stu-id="faa30-110">Attributes</span></span>

|<span data-ttu-id="faa30-111">属性</span><span class="sxs-lookup"><span data-stu-id="faa30-111">Attribute</span></span>|<span data-ttu-id="faa30-112">説明</span><span class="sxs-lookup"><span data-stu-id="faa30-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="faa30-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="faa30-113">Required attribute.</span></span><br /><br /><span data-ttu-id="faa30-114">サーバー GC スレッド/ヒープをコンピューターで使用可能なプロセッサと関連付けるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="faa30-114">Specifies whether server GC threads/heaps are affinitized with the processors available on the machine.</span></span>|

#### <a name="enabled-attribute"></a><span data-ttu-id="faa30-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="faa30-115">enabled attribute</span></span>

|<span data-ttu-id="faa30-116">[値]</span><span class="sxs-lookup"><span data-stu-id="faa30-116">Value</span></span>|<span data-ttu-id="faa30-117">説明</span><span class="sxs-lookup"><span data-stu-id="faa30-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="faa30-118">アフィニティ化する server GC スレッドと Cpu。</span><span class="sxs-lookup"><span data-stu-id="faa30-118">Affinitizes server GC threads with CPUs.</span></span> <span data-ttu-id="faa30-119">既定値です。</span><span class="sxs-lookup"><span data-stu-id="faa30-119">This is the default.</span></span>|
|`true`|<span data-ttu-id="faa30-120">では、Cpu を使用してサーバー GC スレッドを関係付けません。</span><span class="sxs-lookup"><span data-stu-id="faa30-120">Does not affinitize server GC threads with CPUs.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="faa30-121">子要素</span><span class="sxs-lookup"><span data-stu-id="faa30-121">Child elements</span></span>

<span data-ttu-id="faa30-122">なし。</span><span class="sxs-lookup"><span data-stu-id="faa30-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="faa30-123">親要素</span><span class="sxs-lookup"><span data-stu-id="faa30-123">Parent elements</span></span>

|<span data-ttu-id="faa30-124">要素</span><span class="sxs-lookup"><span data-stu-id="faa30-124">Element</span></span>|<span data-ttu-id="faa30-125">説明</span><span class="sxs-lookup"><span data-stu-id="faa30-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="faa30-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="faa30-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="faa30-127">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="faa30-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="faa30-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="faa30-128">Remarks</span></span>

<span data-ttu-id="faa30-129">既定では、サーバー GC スレッドはそれぞれの Cpu とハード関係があります。</span><span class="sxs-lookup"><span data-stu-id="faa30-129">By default, server GC threads are hard-affinitized with their respective CPUs.</span></span> <span data-ttu-id="faa30-130">システムの使用可能な各プロセッサには、独自の GC ヒープとスレッドがあります。</span><span class="sxs-lookup"><span data-stu-id="faa30-130">Each of the system's available processors has its own GC heap and thread.</span></span> <span data-ttu-id="faa30-131">これは、キャッシュの使用を最適化するため、通常は推奨される設定です。</span><span class="sxs-lookup"><span data-stu-id="faa30-131">This is typically the preferred setting since it optimizes cache usage.</span></span> <span data-ttu-id="faa30-132">.NET Framework 4.6.2 以降では、 **GCNoAffinitize**要素の `enabled` 属性を `false`に設定することにより、サーバー GC スレッドと cpu を密結合しないように指定できます。</span><span class="sxs-lookup"><span data-stu-id="faa30-132">Starting with .NET Framework 4.6.2, by setting the **GCNoAffinitize** element's `enabled` attribute to `false`, you can specify that server GC threads and CPUs should not be tightly coupled.</span></span>

<span data-ttu-id="faa30-133">Cpu を使用してサーバー GC スレッドを関係付けしないように、 **GCNoAffinitize**構成要素のみを指定できます。</span><span class="sxs-lookup"><span data-stu-id="faa30-133">You can specify the **GCNoAffinitize** configuration element alone to not affinitize server GC threads with CPUs.</span></span> <span data-ttu-id="faa30-134">また、アプリケーションで使用される GC ヒープとスレッドの数を制御するために、この要素を[Gの Apcount](gcheapcount-element.md)要素と共に使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="faa30-134">You can also use it along with the [GCHeapCount](gcheapcount-element.md) element to control the number of GC heaps and threads used by an application.</span></span>

<span data-ttu-id="faa30-135">**GCNoAffinitize**要素の `enabled` 属性が `false` (既定値) の場合は、 [g apcount](gcheapcount-element.md)要素を使用して gc スレッドとヒープの数を指定することもできます。また、 [GCHeapAffinitizeMask](gcheapaffinitizemask-element.md)要素を使用して、gc スレッドとヒープが関連付けられるプロセッサを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="faa30-135">If the `enabled` attribute of the **GCNoAffinitize** element is `false` (its default value), you can also use the [GCHeapCount](gcheapcount-element.md) element to specify the number of GC threads and heaps, along with the [GCHeapAffinitizeMask](gcheapaffinitizemask-element.md) element to specify the processors to which the GC threads and heaps are affinitized.</span></span>

## <a name="example"></a><span data-ttu-id="faa30-136">例</span><span class="sxs-lookup"><span data-stu-id="faa30-136">Example</span></span>

<span data-ttu-id="faa30-137">次の例では、サーバー GC スレッドをハード関係付けしていません。</span><span class="sxs-lookup"><span data-stu-id="faa30-137">The following example does not hard-affinitize server GC threads:</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

<span data-ttu-id="faa30-138">次の例では、サーバー GC スレッドを関係付けせず、GC ヒープ/スレッドの数を10に制限しています。</span><span class="sxs-lookup"><span data-stu-id="faa30-138">The following example does not affinitize server GC threads and limits the number of GC heaps/threads to 10:</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="faa30-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="faa30-139">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="faa30-140">GCHeapAffinitizeMask 要素</span><span class="sxs-lookup"><span data-stu-id="faa30-140">GCHeapAffinitizeMask element</span></span>](gcheapaffinitizemask-element.md)
- [<span data-ttu-id="faa30-141">G不正 Apcount 要素</span><span class="sxs-lookup"><span data-stu-id="faa30-141">GCHeapCount element</span></span>](gcheapcount-element.md)
- [<span data-ttu-id="faa30-142">ガベージ コレクションの基礎</span><span class="sxs-lookup"><span data-stu-id="faa30-142">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="faa30-143">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="faa30-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="faa30-144">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="faa30-144">Configuration File Schema</span></span>](../index.md)
