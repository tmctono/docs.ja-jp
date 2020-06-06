---
title: gcConcurrent 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcConcurrent
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcConcurrent
helpviewer_keywords:
- container tags, <gcConcurrent> element
- gcConcurrent element
- <gcConcurrent> element
ms.assetid: 503f55ba-26ed-45ac-a2ea-caf994da04cd
ms.openlocfilehash: 249518ae7477d284d50f9010757db83b7752c657
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "82102919"
---
# <a name="gcconcurrent-element"></a><span data-ttu-id="2c03d-102">\<gcConcurrent> 要素</span><span class="sxs-lookup"><span data-stu-id="2c03d-102">\<gcConcurrent> element</span></span>

<span data-ttu-id="2c03d-103">共通言語ランタイムがガベージ コレクションを別のスレッドで実行するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="2c03d-103">Specifies whether the common language runtime runs garbage collection on a separate thread.</span></span>

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;[\<runtime>](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<gcConcurrent>

## <a name="syntax"></a><span data-ttu-id="2c03d-104">構文</span><span class="sxs-lookup"><span data-stu-id="2c03d-104">Syntax</span></span>

```xml
<gcConcurrent
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2c03d-105">属性と要素</span><span class="sxs-lookup"><span data-stu-id="2c03d-105">Attributes and elements</span></span>

<span data-ttu-id="2c03d-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2c03d-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="2c03d-107">属性</span><span class="sxs-lookup"><span data-stu-id="2c03d-107">Attributes</span></span>

|<span data-ttu-id="2c03d-108">属性</span><span class="sxs-lookup"><span data-stu-id="2c03d-108">Attribute</span></span>|<span data-ttu-id="2c03d-109">説明</span><span class="sxs-lookup"><span data-stu-id="2c03d-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="2c03d-110">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="2c03d-110">Required attribute.</span></span><br /><br /><span data-ttu-id="2c03d-111">ランタイムがガベージ コレクションを並列に実行するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="2c03d-111">Specifies whether the runtime runs garbage collection concurrently.</span></span>|

#### <a name="enabled-attribute"></a><span data-ttu-id="2c03d-112">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="2c03d-112">enabled attribute</span></span>

|<span data-ttu-id="2c03d-113">値</span><span class="sxs-lookup"><span data-stu-id="2c03d-113">Value</span></span>|<span data-ttu-id="2c03d-114">Description</span><span class="sxs-lookup"><span data-stu-id="2c03d-114">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="2c03d-115">ガベージコレクションを同時に実行しません。</span><span class="sxs-lookup"><span data-stu-id="2c03d-115">Doesn't run garbage collection concurrently.</span></span>|
|`true`|<span data-ttu-id="2c03d-116">ガベージ コレクションを並列に実行します。</span><span class="sxs-lookup"><span data-stu-id="2c03d-116">Runs garbage collection concurrently.</span></span> <span data-ttu-id="2c03d-117">既定値です。</span><span class="sxs-lookup"><span data-stu-id="2c03d-117">This is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="2c03d-118">子要素</span><span class="sxs-lookup"><span data-stu-id="2c03d-118">Child elements</span></span>

<span data-ttu-id="2c03d-119">なし。</span><span class="sxs-lookup"><span data-stu-id="2c03d-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2c03d-120">親要素</span><span class="sxs-lookup"><span data-stu-id="2c03d-120">Parent elements</span></span>

|<span data-ttu-id="2c03d-121">要素</span><span class="sxs-lookup"><span data-stu-id="2c03d-121">Element</span></span>|<span data-ttu-id="2c03d-122">Description</span><span class="sxs-lookup"><span data-stu-id="2c03d-122">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="2c03d-123">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="2c03d-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="2c03d-124">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2c03d-124">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="2c03d-125">解説</span><span class="sxs-lookup"><span data-stu-id="2c03d-125">Remarks</span></span>

<span data-ttu-id="2c03d-126">.NET Framework 4 より前では、ワークステーションのガベージコレクションは同時実行ガベージコレクションをサポートしていました。これにより、別のスレッドでバックグラウンドでガベージコレクションが実行されました。</span><span class="sxs-lookup"><span data-stu-id="2c03d-126">Prior to .NET Framework 4, workstation garbage collection supported concurrent garbage collection, which performed garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="2c03d-127">.NET Framework 4 では、同時実行ガベージコレクションがバックグラウンド GC に置き換えられました。これにより、別のスレッドでバックグラウンドでガベージコレクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="2c03d-127">In .NET Framework 4, concurrent garbage collection was replaced by background GC, which also performs garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="2c03d-128">.NET Framework 4.5 以降では、サーバーのガベージコレクションでバックグラウンドコレクションを使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="2c03d-128">Starting with .NET Framework 4.5, background collection became available in server garbage collection.</span></span> <span data-ttu-id="2c03d-129">**GcConcurrent**要素は、ランタイムが同時実行ガベージコレクションとバックグラウンドガベージコレクションのどちらを実行するか、またはフォアグラウンドでガベージコレクションを実行するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="2c03d-129">The **gcConcurrent** element controls whether the runtime performs either concurrent or background garbage collection, if it's available, or whether it performs garbage collection in the foreground.</span></span>

### <a name="to-disable-background-garbage-collection"></a><span data-ttu-id="2c03d-130">バックグラウンドガベージコレクションを無効にするには</span><span class="sxs-lookup"><span data-stu-id="2c03d-130">To disable background garbage collection</span></span>

> [!WARNING]
> <span data-ttu-id="2c03d-131">.NET Framework 4 以降では、同時実行ガベージコレクションはバックグラウンドガベージコレクションに置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="2c03d-131">Starting with .NET Framework 4, concurrent garbage collection is replaced by background garbage collection.</span></span> <span data-ttu-id="2c03d-132">.NET Framework のドキュメントでは、*同時実行*と*背景*という用語が同じ意味で使用されます。</span><span class="sxs-lookup"><span data-stu-id="2c03d-132">The terms *concurrent* and *background* are used interchangeably in the .NET Framework documentation.</span></span> <span data-ttu-id="2c03d-133">バックグラウンドガベージコレクションを無効にするには、この記事で説明されているように、 **gcConcurrent**要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="2c03d-133">To disable background garbage collection, use the **gcConcurrent** element, as discussed in this article.</span></span>

<span data-ttu-id="2c03d-134">既定では、ランタイムは同時実行ガベージ コレクションまたはバックグラウンド ガベージ コレクションを使用します。これは待機時間について最適化されています。</span><span class="sxs-lookup"><span data-stu-id="2c03d-134">By default, the runtime uses concurrent or background garbage collection, which is optimized for latency.</span></span> <span data-ttu-id="2c03d-135">アプリケーションでユーザーとのやり取りが多い場合は、同時実行ガベージ コレクションを有効にして、ガベージ コレクションを実行するためのアプリケーションの停止時間を最小限に抑えます。</span><span class="sxs-lookup"><span data-stu-id="2c03d-135">If your application involves heavy user interaction, leave concurrent garbage collection enabled to minimize the application's pause time to perform garbage collection.</span></span> <span data-ttu-id="2c03d-136">`enabled` **GcConcurrent**要素の属性をに設定すると `false` 、ランタイムは非同時実行ガベージコレクションを使用します。これは、スループットのために最適化されています。</span><span class="sxs-lookup"><span data-stu-id="2c03d-136">If you set the `enabled` attribute of the **gcConcurrent** element to `false`, the runtime uses non-concurrent garbage collection, which is optimized for throughput.</span></span>

<span data-ttu-id="2c03d-137">次の構成ファイルは、バックグラウンドガベージコレクションを無効にします。</span><span class="sxs-lookup"><span data-stu-id="2c03d-137">The following configuration file disables background garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="false"/>
   </runtime>
</configuration>
```

<span data-ttu-id="2c03d-138">マシン構成ファイルに**gcConcurrentSetting**設定がある場合は、すべての .NET Framework アプリケーションの既定値が定義されます。</span><span class="sxs-lookup"><span data-stu-id="2c03d-138">If there's a **gcConcurrentSetting** setting in the machine configuration file, it defines the default value for all .NET Framework applications.</span></span> <span data-ttu-id="2c03d-139">マシン構成ファイルの設定は、アプリケーション構成ファイルの設定をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="2c03d-139">The machine configuration file setting overrides the application configuration file setting.</span></span>

<span data-ttu-id="2c03d-140">同時実行ガベージコレクションとバックグラウンドガベージコレクションの詳細については、「[バックグラウンドガベージコレクション](../../../../standard/garbage-collection/background-gc.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c03d-140">For more information on concurrent and background garbage collection, see [Background garbage collection](../../../../standard/garbage-collection/background-gc.md).</span></span>

## <a name="example"></a><span data-ttu-id="2c03d-141">例</span><span class="sxs-lookup"><span data-stu-id="2c03d-141">Example</span></span>

<span data-ttu-id="2c03d-142">次の例では、バックグラウンドガベージコレクションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="2c03d-142">The following example enables background garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="2c03d-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="2c03d-143">See also</span></span>

- [<span data-ttu-id="2c03d-144">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="2c03d-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="2c03d-145">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="2c03d-145">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="2c03d-146">ガベージ コレクションの基礎</span><span class="sxs-lookup"><span data-stu-id="2c03d-146">Fundamentals of Garbage Collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
