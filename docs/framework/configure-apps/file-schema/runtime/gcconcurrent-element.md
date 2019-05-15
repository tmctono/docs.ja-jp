---
title: <gcConcurrent> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcConcurrent
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcConcurrent
helpviewer_keywords:
- container tags, <gcConcurrent> element
- gcConcurrent element
- <gcConcurrent> element
ms.assetid: 503f55ba-26ed-45ac-a2ea-caf994da04cd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e2be4d9384f1e1ef73ce6064184aa2621a517a8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674104"
---
# <a name="gcconcurrent-element"></a><span data-ttu-id="6912d-102">\<gcConcurrent > 要素</span><span class="sxs-lookup"><span data-stu-id="6912d-102">\<gcConcurrent> Element</span></span>

<span data-ttu-id="6912d-103">共通言語ランタイムがガベージ コレクションを別のスレッドで実行するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="6912d-103">Specifies whether the common language runtime runs garbage collection on a separate thread.</span></span>

<span data-ttu-id="6912d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="6912d-104">\<configuration>\\</span></span>
<span data-ttu-id="6912d-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="6912d-105">\<runtime>\\</span></span>
<span data-ttu-id="6912d-106">\<gcConcurrent></span><span class="sxs-lookup"><span data-stu-id="6912d-106">\<gcConcurrent></span></span>

## <a name="syntax"></a><span data-ttu-id="6912d-107">構文</span><span class="sxs-lookup"><span data-stu-id="6912d-107">Syntax</span></span>

```xml
<gcConcurrent
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6912d-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="6912d-108">Attributes and elements</span></span>

<span data-ttu-id="6912d-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="6912d-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="6912d-110">属性</span><span class="sxs-lookup"><span data-stu-id="6912d-110">Attributes</span></span>

|<span data-ttu-id="6912d-111">属性</span><span class="sxs-lookup"><span data-stu-id="6912d-111">Attribute</span></span>|<span data-ttu-id="6912d-112">説明</span><span class="sxs-lookup"><span data-stu-id="6912d-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="6912d-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="6912d-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="6912d-114">ランタイムがガベージ コレクションを並列に実行するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="6912d-114">Specifies whether the runtime runs garbage collection concurrently.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="6912d-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="6912d-115">enabled attribute</span></span>

|<span data-ttu-id="6912d-116">[値]</span><span class="sxs-lookup"><span data-stu-id="6912d-116">Value</span></span>|<span data-ttu-id="6912d-117">説明</span><span class="sxs-lookup"><span data-stu-id="6912d-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="6912d-118">ガベージ コレクションは同時に実行されません。</span><span class="sxs-lookup"><span data-stu-id="6912d-118">Doesn't run garbage collection concurrently.</span></span>|
|`true`|<span data-ttu-id="6912d-119">ガベージ コレクションを並列に実行します。</span><span class="sxs-lookup"><span data-stu-id="6912d-119">Runs garbage collection concurrently.</span></span> <span data-ttu-id="6912d-120">既定値です。</span><span class="sxs-lookup"><span data-stu-id="6912d-120">This is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="6912d-121">子要素</span><span class="sxs-lookup"><span data-stu-id="6912d-121">Child elements</span></span>

<span data-ttu-id="6912d-122">なし。</span><span class="sxs-lookup"><span data-stu-id="6912d-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="6912d-123">親要素</span><span class="sxs-lookup"><span data-stu-id="6912d-123">Parent elements</span></span>

|<span data-ttu-id="6912d-124">要素</span><span class="sxs-lookup"><span data-stu-id="6912d-124">Element</span></span>|<span data-ttu-id="6912d-125">説明</span><span class="sxs-lookup"><span data-stu-id="6912d-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="6912d-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="6912d-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="6912d-127">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6912d-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6912d-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="6912d-128">Remarks</span></span>

<span data-ttu-id="6912d-129">.NET Framework 4 より前の場合、ワークステーション ガベージ コレクションは、同時実行ガベージ コレクションをサポートしており、別個のスレッドでバックグラウンドでガベージ コレクションを実行していました。</span><span class="sxs-lookup"><span data-stu-id="6912d-129">Prior to the .NET Framework 4, workstation garbage collection supported concurrent garbage collection, which performed garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="6912d-130">.NET Framework 4 では同時実行ガベージ コレクションはバックグラウンド GC に置き換えられており、これも別個のスレッドでバックグラウンドでガベージ コレクションを実行していました。</span><span class="sxs-lookup"><span data-stu-id="6912d-130">In the .NET Framework 4, concurrent garbage collection was replaced by background GC, which also performs garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="6912d-131">.NET Framework 4.5 以降では、バックグラウンド コレクションをサーバー ガベージ コレクションで使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="6912d-131">Starting with the .NET Framework 4.5, background collection became available in server garbage collection.</span></span> <span data-ttu-id="6912d-132">`<gcConcurrent>`要素はいずれかの同時実行ランタイムによって実行されるかどうかを制御またはバック グラウンドのガベージ コレクションがある場合、またはフォア グラウンドでガベージ コレクションを実行するかどうか。</span><span class="sxs-lookup"><span data-stu-id="6912d-132">The `<gcConcurrent>` element controls whether the runtime performs either concurrent or background garbage collection, if it's available, or whether it performs garbage collection in the foreground.</span></span>

### <a name="to-disable-background-garbage-collection"></a><span data-ttu-id="6912d-133">バック グラウンド ガベージ コレクションを無効にするには</span><span class="sxs-lookup"><span data-stu-id="6912d-133">To disable background garbage collection</span></span>

> [!WARNING]
> <span data-ttu-id="6912d-134">.NET Framework 4 以降では、同時実行ガベージ コレクションはバックグラウンド ガベージ コレクションに置き換えられています。</span><span class="sxs-lookup"><span data-stu-id="6912d-134">Starting with the .NET Framework 4, concurrent garbage collection is replaced by background garbage collection.</span></span> <span data-ttu-id="6912d-135">条件*同時*と*バック グラウンド*.NET Framework のドキュメントでは、同義です。</span><span class="sxs-lookup"><span data-stu-id="6912d-135">The terms *concurrent* and *background* are used interchangeably in the .NET Framework documentation.</span></span> <span data-ttu-id="6912d-136">バックグラウンド ガベージ コレクションを無効にするには、この記事説明されているように `<gcConcurrent>` 要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="6912d-136">To disable background garbage collection, use the `<gcConcurrent>` element, as discussed in this article.</span></span>

<span data-ttu-id="6912d-137">既定では、ランタイムは同時実行ガベージ コレクションまたはバックグラウンド ガベージ コレクションを使用します。これは待機時間について最適化されています。</span><span class="sxs-lookup"><span data-stu-id="6912d-137">By default, the runtime uses concurrent or background garbage collection, which is optimized for latency.</span></span> <span data-ttu-id="6912d-138">アプリケーションでユーザーとのやり取りが多い場合は、同時実行ガベージ コレクションを有効にして、ガベージ コレクションを実行するためのアプリケーションの停止時間を最小限に抑えます。</span><span class="sxs-lookup"><span data-stu-id="6912d-138">If your application involves heavy user interaction, leave concurrent garbage collection enabled to minimize the application's pause time to perform garbage collection.</span></span> <span data-ttu-id="6912d-139">`<gcConcurrent>` 要素の `enabled` 属性を `false` に設定すると、ランタイムは非同時実行ガベージ コレクションを使用します。これはスループットについて最適化されています。</span><span class="sxs-lookup"><span data-stu-id="6912d-139">If you set the `enabled` attribute of the `<gcConcurrent>` element to `false`, the runtime uses non-concurrent garbage collection, which is optimized for throughput.</span></span> <span data-ttu-id="6912d-140">次の構成ファイルはバック グラウンド ガベージ コレクションを無効にします。</span><span class="sxs-lookup"><span data-stu-id="6912d-140">The following configuration file disables background garbage collection.</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="false"/>
   </runtime>
</configuration>
```

 <span data-ttu-id="6912d-141">存在する場合、`<gcConcurrentSetting>`マシン構成ファイルで設定すると、すべての .NET Framework アプリケーションの既定値を定義します。</span><span class="sxs-lookup"><span data-stu-id="6912d-141">If there's a `<gcConcurrentSetting>` setting in the machine configuration file, it defines the default value for all .NET Framework applications.</span></span> <span data-ttu-id="6912d-142">マシン構成ファイルの設定は、アプリケーション構成ファイルの設定をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="6912d-142">The machine configuration file setting overrides the application configuration file setting.</span></span>

 <span data-ttu-id="6912d-143">詳細については同時実行とバック グラウンド ガベージ コレクションを参照してください、[同時実行ガベージ コレクション](../../../../standard/garbage-collection/fundamentals.md#concurrent-garbage-collection)セクション、[ガベージ コレクションの基礎](../../../../standard/garbage-collection/fundamentals.md)記事。</span><span class="sxs-lookup"><span data-stu-id="6912d-143">For more information on concurrent and background garbage collection, see the [Concurrent garbage collection](../../../../standard/garbage-collection/fundamentals.md#concurrent-garbage-collection) section in the [Fundamentals of Garbage Collection](../../../../standard/garbage-collection/fundamentals.md) article.</span></span>

## <a name="example"></a><span data-ttu-id="6912d-144">例</span><span class="sxs-lookup"><span data-stu-id="6912d-144">Example</span></span>

<span data-ttu-id="6912d-145">次の例では、同時実行ガベージ コレクションが有効。 にします。</span><span class="sxs-lookup"><span data-stu-id="6912d-145">The following example enables concurrent garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="6912d-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="6912d-146">See also</span></span>

- [<span data-ttu-id="6912d-147">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="6912d-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="6912d-148">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="6912d-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="6912d-149">ガベージ コレクションの基礎</span><span class="sxs-lookup"><span data-stu-id="6912d-149">Fundamentals of Garbage Collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
