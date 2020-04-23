---
title: gcコンカレント要素
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
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102919"
---
# <a name="gcconcurrent-element"></a><span data-ttu-id="706fc-102">\<gcコンカレント>要素</span><span class="sxs-lookup"><span data-stu-id="706fc-102">\<gcConcurrent> element</span></span>

<span data-ttu-id="706fc-103">共通言語ランタイムがガベージ コレクションを別のスレッドで実行するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="706fc-103">Specifies whether the common language runtime runs garbage collection on a separate thread.</span></span>

<span data-ttu-id="706fc-104">[\<構成>](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="706fc-104">[\<configuration>](../configuration-element.md)</span></span>\
<span data-ttu-id="706fc-105">&nbsp;&nbsp;[\<ランタイム>](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="706fc-105">&nbsp;&nbsp;[\<runtime>](runtime-element.md)</span></span>\
<span data-ttu-id="706fc-106">&nbsp;&nbsp;&nbsp;&nbsp;\<gc同時実行></span><span class="sxs-lookup"><span data-stu-id="706fc-106">&nbsp;&nbsp;&nbsp;&nbsp;\<gcConcurrent></span></span>

## <a name="syntax"></a><span data-ttu-id="706fc-107">構文</span><span class="sxs-lookup"><span data-stu-id="706fc-107">Syntax</span></span>

```xml
<gcConcurrent
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="706fc-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="706fc-108">Attributes and elements</span></span>

<span data-ttu-id="706fc-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="706fc-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="706fc-110">属性</span><span class="sxs-lookup"><span data-stu-id="706fc-110">Attributes</span></span>

|<span data-ttu-id="706fc-111">属性</span><span class="sxs-lookup"><span data-stu-id="706fc-111">Attribute</span></span>|<span data-ttu-id="706fc-112">説明</span><span class="sxs-lookup"><span data-stu-id="706fc-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="706fc-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="706fc-113">Required attribute.</span></span><br /><br /><span data-ttu-id="706fc-114">ランタイムがガベージ コレクションを並列に実行するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="706fc-114">Specifies whether the runtime runs garbage collection concurrently.</span></span>|

#### <a name="enabled-attribute"></a><span data-ttu-id="706fc-115">有効な属性</span><span class="sxs-lookup"><span data-stu-id="706fc-115">enabled attribute</span></span>

|<span data-ttu-id="706fc-116">値</span><span class="sxs-lookup"><span data-stu-id="706fc-116">Value</span></span>|<span data-ttu-id="706fc-117">説明</span><span class="sxs-lookup"><span data-stu-id="706fc-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="706fc-118">ガベージ コレクションを同時に実行しません。</span><span class="sxs-lookup"><span data-stu-id="706fc-118">Doesn't run garbage collection concurrently.</span></span>|
|`true`|<span data-ttu-id="706fc-119">ガベージ コレクションを並列に実行します。</span><span class="sxs-lookup"><span data-stu-id="706fc-119">Runs garbage collection concurrently.</span></span> <span data-ttu-id="706fc-120">これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="706fc-120">This is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="706fc-121">子要素</span><span class="sxs-lookup"><span data-stu-id="706fc-121">Child elements</span></span>

<span data-ttu-id="706fc-122">[なし] :</span><span class="sxs-lookup"><span data-stu-id="706fc-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="706fc-123">親要素</span><span class="sxs-lookup"><span data-stu-id="706fc-123">Parent elements</span></span>

|<span data-ttu-id="706fc-124">要素</span><span class="sxs-lookup"><span data-stu-id="706fc-124">Element</span></span>|<span data-ttu-id="706fc-125">説明</span><span class="sxs-lookup"><span data-stu-id="706fc-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="706fc-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="706fc-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="706fc-127">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="706fc-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="706fc-128">解説</span><span class="sxs-lookup"><span data-stu-id="706fc-128">Remarks</span></span>

<span data-ttu-id="706fc-129">.NET Framework 4 より前のバージョンでは、ワークステーションのガベージ コレクションは、別のスレッドでバックグラウンドでガベージ コレクションを実行する同時実行ガベージ コレクションをサポートしました。</span><span class="sxs-lookup"><span data-stu-id="706fc-129">Prior to .NET Framework 4, workstation garbage collection supported concurrent garbage collection, which performed garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="706fc-130">NET Framework 4 では、同時実行ガベージ コレクションはバックグラウンド GC に置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="706fc-130">In .NET Framework 4, concurrent garbage collection was replaced by background GC, which also performs garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="706fc-131">NET Framework 4.5 以降、サーバー のガベージ コレクションでバックグラウンド コレクションを使用で使用するようになりました。</span><span class="sxs-lookup"><span data-stu-id="706fc-131">Starting with .NET Framework 4.5, background collection became available in server garbage collection.</span></span> <span data-ttu-id="706fc-132">**gcConcurrent**要素は、ランタイムが同時実行ガベージ コレクションとバックグラウンド ガベージ コレクションのどちらを実行するか (使用可能な場合)、またはフォアグラウンドでガベージ コレクションを実行するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="706fc-132">The **gcConcurrent** element controls whether the runtime performs either concurrent or background garbage collection, if it's available, or whether it performs garbage collection in the foreground.</span></span>

### <a name="to-disable-background-garbage-collection"></a><span data-ttu-id="706fc-133">バックグラウンド ガベージ コレクションを無効にするには</span><span class="sxs-lookup"><span data-stu-id="706fc-133">To disable background garbage collection</span></span>

> [!WARNING]
> <span data-ttu-id="706fc-134">NET Framework 4 以降、同時実行ガベージ コレクションはバックグラウンド ガベージ コレクションに置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="706fc-134">Starting with .NET Framework 4, concurrent garbage collection is replaced by background garbage collection.</span></span> <span data-ttu-id="706fc-135">*同時実行*と*背景*という用語は、.NET Framework ドキュメントで同じ意味で使用されます。</span><span class="sxs-lookup"><span data-stu-id="706fc-135">The terms *concurrent* and *background* are used interchangeably in the .NET Framework documentation.</span></span> <span data-ttu-id="706fc-136">バックグラウンド ガベージ コレクションを無効にするには、この記事で説明するように**gcConcurrent**要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="706fc-136">To disable background garbage collection, use the **gcConcurrent** element, as discussed in this article.</span></span>

<span data-ttu-id="706fc-137">既定では、ランタイムは同時実行ガベージ コレクションまたはバックグラウンド ガベージ コレクションを使用します。これは待機時間について最適化されています。</span><span class="sxs-lookup"><span data-stu-id="706fc-137">By default, the runtime uses concurrent or background garbage collection, which is optimized for latency.</span></span> <span data-ttu-id="706fc-138">アプリケーションでユーザーとのやり取りが多い場合は、同時実行ガベージ コレクションを有効にして、ガベージ コレクションを実行するためのアプリケーションの停止時間を最小限に抑えます。</span><span class="sxs-lookup"><span data-stu-id="706fc-138">If your application involves heavy user interaction, leave concurrent garbage collection enabled to minimize the application's pause time to perform garbage collection.</span></span> <span data-ttu-id="706fc-139">**gcConcurrent**要素`enabled`の属性を に`false`設定すると、ランタイムはスループットに最適化された非同時実行ガベージ コレクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="706fc-139">If you set the `enabled` attribute of the **gcConcurrent** element to `false`, the runtime uses non-concurrent garbage collection, which is optimized for throughput.</span></span>

<span data-ttu-id="706fc-140">次の構成ファイルは、バックグラウンド ガベージ コレクションを無効にします。</span><span class="sxs-lookup"><span data-stu-id="706fc-140">The following configuration file disables background garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="false"/>
   </runtime>
</configuration>
```

<span data-ttu-id="706fc-141">マシン構成ファイルに**gcConcurrentSetting 設定**がある場合は、すべての .NET Framework アプリケーションの既定値が定義されます。</span><span class="sxs-lookup"><span data-stu-id="706fc-141">If there's a **gcConcurrentSetting** setting in the machine configuration file, it defines the default value for all .NET Framework applications.</span></span> <span data-ttu-id="706fc-142">マシン構成ファイルの設定は、アプリケーション構成ファイルの設定をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="706fc-142">The machine configuration file setting overrides the application configuration file setting.</span></span>

<span data-ttu-id="706fc-143">同時実行ガベージ コレクションとバックグラウンド ガベージ コレクションの詳細については、「[バックグラウンド ガベージ コレクション](../../../../standard/garbage-collection/background-gc.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="706fc-143">For more information on concurrent and background garbage collection, see [Background garbage collection](../../../../standard/garbage-collection/background-gc.md).</span></span>

## <a name="example"></a><span data-ttu-id="706fc-144">例</span><span class="sxs-lookup"><span data-stu-id="706fc-144">Example</span></span>

<span data-ttu-id="706fc-145">次の例では、バックグラウンド ガベージ コレクションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="706fc-145">The following example enables background garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="706fc-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="706fc-146">See also</span></span>

- [<span data-ttu-id="706fc-147">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="706fc-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="706fc-148">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="706fc-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="706fc-149">ガベージ コレクションの基礎</span><span class="sxs-lookup"><span data-stu-id="706fc-149">Fundamentals of Garbage Collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
