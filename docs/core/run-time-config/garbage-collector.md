---
title: ガベージ コレクター構成の設定
description: ガベージ コレクターでの .NET Core アプリ用のメモリの管理方法を構成するための、実行時設定について学習します。
ms.date: 07/10/2020
ms.topic: reference
ms.openlocfilehash: 6ae5b7447fb0df4978ea9dcaa5e76fcc7a6cc4ca
ms.sourcegitcommit: 2543a78be6e246aa010a01decf58889de53d1636
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/17/2020
ms.locfileid: "86441409"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a><span data-ttu-id="9c66e-103">ガベージ コレクションの実行時構成オプション</span><span class="sxs-lookup"><span data-stu-id="9c66e-103">Run-time configuration options for garbage collection</span></span>

<span data-ttu-id="9c66e-104">このページには、実行時に変更できるガベージ コレクター (GC) の設定に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9c66e-104">This page contains information about garbage collector (GC) settings that can be changed at run time.</span></span> <span data-ttu-id="9c66e-105">実行中のアプリのピーク時のパフォーマンスを実現しようとしている場合は、これらの設定の使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="9c66e-105">If you're trying to achieve peak performance of a running app, consider using these settings.</span></span> <span data-ttu-id="9c66e-106">しかし、一般的な状況では、既定値でほとんどのアプリケーションに最適なパフォーマンスが得られます。</span><span class="sxs-lookup"><span data-stu-id="9c66e-106">However, the defaults provide optimum performance for most applications in typical situations.</span></span>

<span data-ttu-id="9c66e-107">このページでは、設定はグループにまとめられます。</span><span class="sxs-lookup"><span data-stu-id="9c66e-107">Settings are arranged into groups on this page.</span></span> <span data-ttu-id="9c66e-108">各グループ内の設定は一般的に、特定の結果を得るために相互に組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="9c66e-108">The settings within each group are commonly used in conjunction with each other to achieve a specific result.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="9c66e-109">これらの設定は、実行中にアプリで動的に変更することもできます。したがって、設定した実行時の設定が上書きされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9c66e-109">These settings can also be changed dynamically by the app as it's running, so any run-time settings you set may be overridden.</span></span>
> - <span data-ttu-id="9c66e-110">[待機時間レベル](../../standard/garbage-collection/latency.md)などの一部の設定は、通常、デザイン時に API を介してのみ設定されます。</span><span class="sxs-lookup"><span data-stu-id="9c66e-110">Some settings, such as [latency level](../../standard/garbage-collection/latency.md), are typically set only through the API at design time.</span></span> <span data-ttu-id="9c66e-111">このページでは、このような設定は省略されています。</span><span class="sxs-lookup"><span data-stu-id="9c66e-111">Such settings are omitted from this page.</span></span>
> - <span data-ttu-id="9c66e-112">数値の場合、*runtimeconfig.json* ファイルの設定には 10 進表記、環境変数の設定には 16 進表記を使用します。</span><span class="sxs-lookup"><span data-stu-id="9c66e-112">For number values, use decimal notation for settings in the *runtimeconfig.json* file and hexadecimal notation for environment variable settings.</span></span> <span data-ttu-id="9c66e-113">16 進値の場合は、プレフィックス "0x" を付けても付けなくても指定できます。</span><span class="sxs-lookup"><span data-stu-id="9c66e-113">For hexadecimal values, you can specify them with or without the "0x" prefix.</span></span>

## <a name="flavors-of-garbage-collection"></a><span data-ttu-id="9c66e-114">ガベージ コレクションのフレーバー</span><span class="sxs-lookup"><span data-stu-id="9c66e-114">Flavors of garbage collection</span></span>

<span data-ttu-id="9c66e-115">ガベージ コレクションの主な 2 つのフレーバーは、ワークステーション GC とサーバー GC です。</span><span class="sxs-lookup"><span data-stu-id="9c66e-115">The two main flavors of garbage collection are workstation GC and server GC.</span></span> <span data-ttu-id="9c66e-116">2 つの間の相違点について詳しくは、「[ワークステーションとサーバーのガベージ コレクション](../../standard/garbage-collection/workstation-server-gc.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9c66e-116">For more information about differences between the two, see [Workstation and server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span>

<span data-ttu-id="9c66e-117">ガベージ コレクションのサブフレーバーは、バックグラウンドと非同時実行です。</span><span class="sxs-lookup"><span data-stu-id="9c66e-117">The subflavors of garbage collection are background and non-concurrent.</span></span>

<span data-ttu-id="9c66e-118">ガベージ コレクションのフレーバーを選択するには、以下の設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="9c66e-118">Use the following settings to select flavors of garbage collection:</span></span>

### <a name="systemgcservercomplus_gcserver"></a><span data-ttu-id="9c66e-119">System.GC.Server/COMPlus_gcServer</span><span class="sxs-lookup"><span data-stu-id="9c66e-119">System.GC.Server/COMPlus_gcServer</span></span>

- <span data-ttu-id="9c66e-120">アプリケーションで、ワークステーション ガベージ コレクションとサーバー ガベージ コレクションのどちらを使用するかを構成します。</span><span class="sxs-lookup"><span data-stu-id="9c66e-120">Configures whether the application uses workstation garbage collection or server garbage collection.</span></span>
- <span data-ttu-id="9c66e-121">既定:ワークステーション ガベージ コレクション。</span><span class="sxs-lookup"><span data-stu-id="9c66e-121">Default: Workstation garbage collection.</span></span> <span data-ttu-id="9c66e-122">これは、値を `false` に設定した場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="9c66e-122">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="9c66e-123">設定の名前</span><span class="sxs-lookup"><span data-stu-id="9c66e-123">Setting name</span></span> | <span data-ttu-id="9c66e-124">値</span><span class="sxs-lookup"><span data-stu-id="9c66e-124">Values</span></span> | <span data-ttu-id="9c66e-125">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="9c66e-125">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9c66e-126">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9c66e-126">**runtimeconfig.json**</span></span> | `System.GC.Server` | <span data-ttu-id="9c66e-127">`false` - ワークステーション</span><span class="sxs-lookup"><span data-stu-id="9c66e-127">`false` - workstation</span></span><br/><span data-ttu-id="9c66e-128">`true` - サーバー</span><span class="sxs-lookup"><span data-stu-id="9c66e-128">`true` - server</span></span> | <span data-ttu-id="9c66e-129">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="9c66e-129">.NET Core 1.0</span></span> |
| <span data-ttu-id="9c66e-130">**MSBuild のプロパティ**</span><span class="sxs-lookup"><span data-stu-id="9c66e-130">**MSBuild property**</span></span> | `ServerGarbageCollection` | <span data-ttu-id="9c66e-131">`false` - ワークステーション</span><span class="sxs-lookup"><span data-stu-id="9c66e-131">`false` - workstation</span></span><br/><span data-ttu-id="9c66e-132">`true` - サーバー</span><span class="sxs-lookup"><span data-stu-id="9c66e-132">`true` - server</span></span> | <span data-ttu-id="9c66e-133">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="9c66e-133">.NET Core 1.0</span></span> |
| <span data-ttu-id="9c66e-134">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="9c66e-134">**Environment variable**</span></span> | `COMPlus_gcServer` | <span data-ttu-id="9c66e-135">`0` - ワークステーション</span><span class="sxs-lookup"><span data-stu-id="9c66e-135">`0` - workstation</span></span><br/><span data-ttu-id="9c66e-136">`1` - サーバー</span><span class="sxs-lookup"><span data-stu-id="9c66e-136">`1` - server</span></span> | <span data-ttu-id="9c66e-137">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="9c66e-137">.NET Core 1.0</span></span> |
| <span data-ttu-id="9c66e-138">**.NET Framework 用の app.config**</span><span class="sxs-lookup"><span data-stu-id="9c66e-138">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="9c66e-139">GCServer</span><span class="sxs-lookup"><span data-stu-id="9c66e-139">GCServer</span></span>](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | <span data-ttu-id="9c66e-140">`false` - ワークステーション</span><span class="sxs-lookup"><span data-stu-id="9c66e-140">`false` - workstation</span></span><br/><span data-ttu-id="9c66e-141">`true` - サーバー</span><span class="sxs-lookup"><span data-stu-id="9c66e-141">`true` - server</span></span> |  |

### <a name="examples"></a><span data-ttu-id="9c66e-142">使用例</span><span class="sxs-lookup"><span data-stu-id="9c66e-142">Examples</span></span>

<span data-ttu-id="9c66e-143">*runtimeconfig.json* ファイル:</span><span class="sxs-lookup"><span data-stu-id="9c66e-143">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

<span data-ttu-id="9c66e-144">プロジェクト ファイル:</span><span class="sxs-lookup"><span data-stu-id="9c66e-144">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ServerGarbageCollection>true</ServerGarbageCollection>
  </PropertyGroup>

</Project>
```

### <a name="systemgcconcurrentcomplus_gcconcurrent"></a><span data-ttu-id="9c66e-145">System.GC.Concurrent/COMPlus_gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="9c66e-145">System.GC.Concurrent/COMPlus_gcConcurrent</span></span>

- <span data-ttu-id="9c66e-146">バックグラウンド (同時実行) ガベージ コレクションを有効にするかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="9c66e-146">Configures whether background (concurrent) garbage collection is enabled.</span></span>
- <span data-ttu-id="9c66e-147">既定:バックグラウンド GC を使用します。</span><span class="sxs-lookup"><span data-stu-id="9c66e-147">Default: Use background GC.</span></span> <span data-ttu-id="9c66e-148">これは、値を `true` に設定した場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="9c66e-148">This is equivalent to setting the value to `true`.</span></span>
- <span data-ttu-id="9c66e-149">詳しくは、「[バックグラウンド ガベージ コレクション](../../standard/garbage-collection/background-gc.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9c66e-149">For more information, see [Background garbage collection](../../standard/garbage-collection/background-gc.md).</span></span>

| | <span data-ttu-id="9c66e-150">設定の名前</span><span class="sxs-lookup"><span data-stu-id="9c66e-150">Setting name</span></span> | <span data-ttu-id="9c66e-151">値</span><span class="sxs-lookup"><span data-stu-id="9c66e-151">Values</span></span> | <span data-ttu-id="9c66e-152">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="9c66e-152">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9c66e-153">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9c66e-153">**runtimeconfig.json**</span></span> | `System.GC.Concurrent` | <span data-ttu-id="9c66e-154">`true` - バックグラウンド GC</span><span class="sxs-lookup"><span data-stu-id="9c66e-154">`true` - background GC</span></span><br/><span data-ttu-id="9c66e-155">`false` -非同時実行 GC</span><span class="sxs-lookup"><span data-stu-id="9c66e-155">`false` - non-concurrent GC</span></span> | <span data-ttu-id="9c66e-156">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="9c66e-156">.NET Core 1.0</span></span> |
| <span data-ttu-id="9c66e-157">**MSBuild のプロパティ**</span><span class="sxs-lookup"><span data-stu-id="9c66e-157">**MSBuild property**</span></span> | `ConcurrentGarbageCollection` | <span data-ttu-id="9c66e-158">`true` - バックグラウンド GC</span><span class="sxs-lookup"><span data-stu-id="9c66e-158">`true` - background GC</span></span><br/><span data-ttu-id="9c66e-159">`false` -非同時実行 GC</span><span class="sxs-lookup"><span data-stu-id="9c66e-159">`false` - non-concurrent GC</span></span> | <span data-ttu-id="9c66e-160">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="9c66e-160">.NET Core 1.0</span></span> |
| <span data-ttu-id="9c66e-161">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="9c66e-161">**Environment variable**</span></span> | `COMPlus_gcConcurrent` | <span data-ttu-id="9c66e-162">`1` - バックグラウンド GC</span><span class="sxs-lookup"><span data-stu-id="9c66e-162">`1` - background GC</span></span><br/><span data-ttu-id="9c66e-163">`0` -非同時実行 GC</span><span class="sxs-lookup"><span data-stu-id="9c66e-163">`0` - non-concurrent GC</span></span> | <span data-ttu-id="9c66e-164">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="9c66e-164">.NET Core 1.0</span></span> |
| <span data-ttu-id="9c66e-165">**.NET Framework 用の app.config**</span><span class="sxs-lookup"><span data-stu-id="9c66e-165">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="9c66e-166">gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="9c66e-166">gcConcurrent</span></span>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | <span data-ttu-id="9c66e-167">`true` - バックグラウンド GC</span><span class="sxs-lookup"><span data-stu-id="9c66e-167">`true` - background GC</span></span><br/><span data-ttu-id="9c66e-168">`false` -非同時実行 GC</span><span class="sxs-lookup"><span data-stu-id="9c66e-168">`false` - non-concurrent GC</span></span> |  |

### <a name="examples"></a><span data-ttu-id="9c66e-169">使用例</span><span class="sxs-lookup"><span data-stu-id="9c66e-169">Examples</span></span>

<span data-ttu-id="9c66e-170">*runtimeconfig.json* ファイル:</span><span class="sxs-lookup"><span data-stu-id="9c66e-170">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

<span data-ttu-id="9c66e-171">プロジェクト ファイル:</span><span class="sxs-lookup"><span data-stu-id="9c66e-171">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="manage-resource-usage"></a><span data-ttu-id="9c66e-172">リソース使用量を管理する</span><span class="sxs-lookup"><span data-stu-id="9c66e-172">Manage resource usage</span></span>

<span data-ttu-id="9c66e-173">このセクションで説明する設定を使用して、ガベージ コレクターのメモリとプロセッサの使用量を管理します。</span><span class="sxs-lookup"><span data-stu-id="9c66e-173">Use the settings described in this section to manage the garbage collector's memory and processor usage.</span></span>

<span data-ttu-id="9c66e-174">これらの設定のいくつかの詳細については、[ワークステーションおよびサーバー GC 間の妥協点](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/)に関するブログ エントリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c66e-174">For more information about some of these settings, see the [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) blog entry.</span></span>

### <a name="systemgcheapcountcomplus_gcheapcount"></a><span data-ttu-id="9c66e-175">System.GC.HeapCount/COMPlus_GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="9c66e-175">System.GC.HeapCount/COMPlus_GCHeapCount</span></span>

- <span data-ttu-id="9c66e-176">ガベージ コレクターによって作成されるヒープの数を制限します。</span><span class="sxs-lookup"><span data-stu-id="9c66e-176">Limits the number of heaps created by the garbage collector.</span></span>
- <span data-ttu-id="9c66e-177">サーバー ガベージ コレクションにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="9c66e-177">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="9c66e-178">[GC プロセッサの関係](#systemgcnoaffinitizecomplus_gcnoaffinitize)が有効になっている場合 (既定値)、ヒープ数の設定では、最初の `n` プロセッサに `n` GC ヒープやスレッドを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="9c66e-178">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is enabled, which is the default, the heap count setting affinitizes `n` GC heaps/threads to the first `n` processors.</span></span> <span data-ttu-id="9c66e-179">([関係付けマスク](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask)または[関係付け範囲](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges)の設定を使用して、関係付けるプロセッサを正確に指定します)。</span><span class="sxs-lookup"><span data-stu-id="9c66e-179">(Use the [affinitize mask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) or [affinitize ranges](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges) settings to specify exactly which processors to affinitize.)</span></span>
- <span data-ttu-id="9c66e-180">[GC プロセッサの関係](#systemgcnoaffinitizecomplus_gcnoaffinitize)が無効になっている場合、この設定によって GC ヒープの数が制限されます。</span><span class="sxs-lookup"><span data-stu-id="9c66e-180">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting limits the number of GC heaps.</span></span>
- <span data-ttu-id="9c66e-181">詳細については、[GCHeapCount の解説](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks)に関する記述を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c66e-181">For more information, see the [GCHeapCount remarks](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span></span>

| | <span data-ttu-id="9c66e-182">設定の名前</span><span class="sxs-lookup"><span data-stu-id="9c66e-182">Setting name</span></span> | <span data-ttu-id="9c66e-183">値</span><span class="sxs-lookup"><span data-stu-id="9c66e-183">Values</span></span> | <span data-ttu-id="9c66e-184">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="9c66e-184">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9c66e-185">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9c66e-185">**runtimeconfig.json**</span></span> | `System.GC.HeapCount` | <span data-ttu-id="9c66e-186">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="9c66e-186">*decimal value*</span></span> | <span data-ttu-id="9c66e-187">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9c66e-187">.NET Core 3.0</span></span> |
| <span data-ttu-id="9c66e-188">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="9c66e-188">**Environment variable**</span></span> | `COMPlus_GCHeapCount` | <span data-ttu-id="9c66e-189">"*16 進値*"</span><span class="sxs-lookup"><span data-stu-id="9c66e-189">*hexadecimal value*</span></span> | <span data-ttu-id="9c66e-190">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9c66e-190">.NET Core 3.0</span></span> |
| <span data-ttu-id="9c66e-191">**.NET Framework 用の app.config**</span><span class="sxs-lookup"><span data-stu-id="9c66e-191">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="9c66e-192">GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="9c66e-192">GCHeapCount</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | <span data-ttu-id="9c66e-193">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="9c66e-193">*decimal value*</span></span> | <span data-ttu-id="9c66e-194">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="9c66e-194">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="9c66e-195">例:</span><span class="sxs-lookup"><span data-stu-id="9c66e-195">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapCount": 16
      }
   }
}
```

> [!TIP]
> <span data-ttu-id="9c66e-196">*runtimeconfig.json* でオプションを設定する場合は、10 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="9c66e-196">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="9c66e-197">環境変数としてオプションを設定する場合は、16 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="9c66e-197">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="9c66e-198">たとえば、ヒープの数を 16 に制限する場合、値は JSON ファイルでは 16、環境変数では 0x10 または 10 になります。</span><span class="sxs-lookup"><span data-stu-id="9c66e-198">For example, to limit the number of heaps to 16, the values would be 16 for the JSON file and 0x10 or 10 for the environment variable.</span></span>

### <a name="systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask"></a><span data-ttu-id="9c66e-199">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="9c66e-199">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span></span>

- <span data-ttu-id="9c66e-200">ガベージ コレクター スレッドで使用する必要がある正確なプロセッサを指定します。</span><span class="sxs-lookup"><span data-stu-id="9c66e-200">Specifies the exact processors that garbage collector threads should use.</span></span>
- <span data-ttu-id="9c66e-201">[GC プロセッサの関係](#systemgcnoaffinitizecomplus_gcnoaffinitize)が無効になっている場合、この設定は無視されます。</span><span class="sxs-lookup"><span data-stu-id="9c66e-201">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="9c66e-202">サーバー ガベージ コレクションにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="9c66e-202">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="9c66e-203">この値は、プロセスで使用できるプロセッサを定義するビット マスクです。</span><span class="sxs-lookup"><span data-stu-id="9c66e-203">The value is a bit mask that defines the processors that are available to the process.</span></span> <span data-ttu-id="9c66e-204">たとえば、10 進値の 1023 (環境変数を使用する場合は、16 進値の 0x3FF または 3FF) は、バイナリ表記では 0011 1111 1111 となります。</span><span class="sxs-lookup"><span data-stu-id="9c66e-204">For example, a decimal value of 1023 (or a hexadecimal value of 0x3FF or 3FF if you're using the environment variable) is 0011 1111 1111 in binary notation.</span></span> <span data-ttu-id="9c66e-205">これにより、最初の 10 プロセッサが使用されることが指定されます。</span><span class="sxs-lookup"><span data-stu-id="9c66e-205">This specifies that the first 10 processors are to be used.</span></span> <span data-ttu-id="9c66e-206">次の 10 プロセッサ (つまり、10 から 19 プロセッサ) を指定するには、10 進値の 1047552 (または 16 進値の 0xFFC00 または FFC00) を指定します。これは、バイナリ値の 1111 1111 1100 0000 0000 に相当します。</span><span class="sxs-lookup"><span data-stu-id="9c66e-206">To specify the next 10 processors, that is, processors 10-19, specify a decimal value of 1047552 (or a hexadecimal value of 0xFFC00 or FFC00), which is equivalent to a binary value of 1111 1111 1100 0000 0000.</span></span>

| | <span data-ttu-id="9c66e-207">設定の名前</span><span class="sxs-lookup"><span data-stu-id="9c66e-207">Setting name</span></span> | <span data-ttu-id="9c66e-208">値</span><span class="sxs-lookup"><span data-stu-id="9c66e-208">Values</span></span> | <span data-ttu-id="9c66e-209">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="9c66e-209">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9c66e-210">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9c66e-210">**runtimeconfig.json**</span></span> | `System.GC.HeapAffinitizeMask` | <span data-ttu-id="9c66e-211">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="9c66e-211">*decimal value*</span></span> | <span data-ttu-id="9c66e-212">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9c66e-212">.NET Core 3.0</span></span> |
| <span data-ttu-id="9c66e-213">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="9c66e-213">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeMask` | <span data-ttu-id="9c66e-214">"*16 進値*"</span><span class="sxs-lookup"><span data-stu-id="9c66e-214">*hexadecimal value*</span></span> | <span data-ttu-id="9c66e-215">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9c66e-215">.NET Core 3.0</span></span> |
| <span data-ttu-id="9c66e-216">**.NET Framework 用の app.config**</span><span class="sxs-lookup"><span data-stu-id="9c66e-216">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="9c66e-217">GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="9c66e-217">GCHeapAffinitizeMask</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | <span data-ttu-id="9c66e-218">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="9c66e-218">*decimal value*</span></span> | <span data-ttu-id="9c66e-219">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="9c66e-219">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="9c66e-220">例:</span><span class="sxs-lookup"><span data-stu-id="9c66e-220">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges"></a><span data-ttu-id="9c66e-221">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span><span class="sxs-lookup"><span data-stu-id="9c66e-221">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span></span>

- <span data-ttu-id="9c66e-222">ガベージ コレクター スレッドに使用するプロセッサのリストを指定します。</span><span class="sxs-lookup"><span data-stu-id="9c66e-222">Specifies the list of processors to use for garbage collector threads.</span></span>
- <span data-ttu-id="9c66e-223">この設定は [System.GC.HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) に似ていますが、64 を超えるプロセッサを指定できる点が異なります。</span><span class="sxs-lookup"><span data-stu-id="9c66e-223">This setting is similar to [System.GC.HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask), except it allows you to specify more than 64 processors.</span></span>
- <span data-ttu-id="9c66e-224">Windows オペレーティング システムの場合、プロセッサの番号または範囲の前に、対応する [CPU グループ](/windows/win32/procthread/processor-groups)を付けます。たとえば、"0:1-10,0:12,1:50-52,1:70" となります。</span><span class="sxs-lookup"><span data-stu-id="9c66e-224">For Windows operating systems, prefix the processor number or range with the corresponding [CPU group](/windows/win32/procthread/processor-groups), for example, "0:1-10,0:12,1:50-52,1:70".</span></span>
- <span data-ttu-id="9c66e-225">[GC プロセッサの関係](#systemgcnoaffinitizecomplus_gcnoaffinitize)が無効になっている場合、この設定は無視されます。</span><span class="sxs-lookup"><span data-stu-id="9c66e-225">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="9c66e-226">サーバー ガベージ コレクションにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="9c66e-226">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="9c66e-227">詳細については、Maoni Stephens のブログの「[CPU が 64 を超えるコンピューター上での GC のための CPU 構成の向上](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c66e-227">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="9c66e-228">設定の名前</span><span class="sxs-lookup"><span data-stu-id="9c66e-228">Setting name</span></span> | <span data-ttu-id="9c66e-229">値</span><span class="sxs-lookup"><span data-stu-id="9c66e-229">Values</span></span> | <span data-ttu-id="9c66e-230">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="9c66e-230">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9c66e-231">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9c66e-231">**runtimeconfig.json**</span></span> | `System.GC.GCHeapAffinitizeRanges` | <span data-ttu-id="9c66e-232">プロセッサ番号またはプロセッサ番号の範囲のコンマ区切りリスト。</span><span class="sxs-lookup"><span data-stu-id="9c66e-232">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="9c66e-233">Unix の例:"1-10,12,50-52,70"</span><span class="sxs-lookup"><span data-stu-id="9c66e-233">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="9c66e-234">Windows の例:"0:1-10,0:12,1:50-52,1:70"</span><span class="sxs-lookup"><span data-stu-id="9c66e-234">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="9c66e-235">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9c66e-235">.NET Core 3.0</span></span> |
| <span data-ttu-id="9c66e-236">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="9c66e-236">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeRanges` | <span data-ttu-id="9c66e-237">プロセッサ番号またはプロセッサ番号の範囲のコンマ区切りリスト。</span><span class="sxs-lookup"><span data-stu-id="9c66e-237">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="9c66e-238">Unix の例:"1-10,12,50-52,70"</span><span class="sxs-lookup"><span data-stu-id="9c66e-238">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="9c66e-239">Windows の例:"0:1-10,0:12,1:50-52,1:70"</span><span class="sxs-lookup"><span data-stu-id="9c66e-239">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="9c66e-240">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9c66e-240">.NET Core 3.0</span></span> |

<span data-ttu-id="9c66e-241">例:</span><span class="sxs-lookup"><span data-stu-id="9c66e-241">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="complus_gccpugroup"></a><span data-ttu-id="9c66e-242">COMPlus_GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="9c66e-242">COMPlus_GCCpuGroup</span></span>

- <span data-ttu-id="9c66e-243">ガベージ コレクターで [CPU グループ](/windows/win32/procthread/processor-groups)を使用するかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="9c66e-243">Configures whether the garbage collector uses [CPU groups](/windows/win32/procthread/processor-groups) or not.</span></span>

  <span data-ttu-id="9c66e-244">64 ビットの Windows コンピューターに複数の CPU グループがある (つまり、64 を超えるプロセッサがある) 場合、この要素を有効にすると、すべての CPU グループ全体にガベージ コレクションが拡張されます。</span><span class="sxs-lookup"><span data-stu-id="9c66e-244">When a 64-bit Windows computer has multiple CPU groups, that is, there are more than 64 processors, enabling this element extends garbage collection across all CPU groups.</span></span> <span data-ttu-id="9c66e-245">ガベージ コレクターではすべてのコアを使用し、ヒープを作成して分散させます。</span><span class="sxs-lookup"><span data-stu-id="9c66e-245">The garbage collector uses all cores to create and balance heaps.</span></span>

- <span data-ttu-id="9c66e-246">64 ビット Windows オペレーティング システムのみのサーバー ガベージ コレクションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="9c66e-246">Applies to server garbage collection on 64-bit Windows operation systems only.</span></span>
- <span data-ttu-id="9c66e-247">既定:GC は複数の CPU グループに拡張されません。</span><span class="sxs-lookup"><span data-stu-id="9c66e-247">Default: GC does not extend across CPU groups.</span></span> <span data-ttu-id="9c66e-248">これは、値を `0` に設定した場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="9c66e-248">This is equivalent to setting the value to `0`.</span></span>
- <span data-ttu-id="9c66e-249">詳細については、Maoni Stephens のブログの「[CPU が 64 を超えるコンピューター上での GC のための CPU 構成の向上](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c66e-249">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="9c66e-250">設定の名前</span><span class="sxs-lookup"><span data-stu-id="9c66e-250">Setting name</span></span> | <span data-ttu-id="9c66e-251">値</span><span class="sxs-lookup"><span data-stu-id="9c66e-251">Values</span></span> | <span data-ttu-id="9c66e-252">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="9c66e-252">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9c66e-253">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9c66e-253">**runtimeconfig.json**</span></span> | <span data-ttu-id="9c66e-254">N/A</span><span class="sxs-lookup"><span data-stu-id="9c66e-254">N/A</span></span> | <span data-ttu-id="9c66e-255">N/A</span><span class="sxs-lookup"><span data-stu-id="9c66e-255">N/A</span></span> | <span data-ttu-id="9c66e-256">N/A</span><span class="sxs-lookup"><span data-stu-id="9c66e-256">N/A</span></span> |
| <span data-ttu-id="9c66e-257">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="9c66e-257">**Environment variable**</span></span> | `COMPlus_GCCpuGroup` | <span data-ttu-id="9c66e-258">`0` - 無効</span><span class="sxs-lookup"><span data-stu-id="9c66e-258">`0` - disabled</span></span><br/><span data-ttu-id="9c66e-259">`1` - 有効</span><span class="sxs-lookup"><span data-stu-id="9c66e-259">`1` - enabled</span></span> | <span data-ttu-id="9c66e-260">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="9c66e-260">.NET Core 1.0</span></span> |
| <span data-ttu-id="9c66e-261">**.NET Framework 用の app.config**</span><span class="sxs-lookup"><span data-stu-id="9c66e-261">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="9c66e-262">GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="9c66e-262">GCCpuGroup</span></span>](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | <span data-ttu-id="9c66e-263">`false` - 無効</span><span class="sxs-lookup"><span data-stu-id="9c66e-263">`false` - disabled</span></span><br/><span data-ttu-id="9c66e-264">`true` - 有効</span><span class="sxs-lookup"><span data-stu-id="9c66e-264">`true` - enabled</span></span> |  |

> [!NOTE]
> <span data-ttu-id="9c66e-265">すべての CPU グループ全体にスレッド プールからのスレッドも分散するように共通言語ランタイム (CLR) を構成するには、[Thread_UseAllCpuGroups 要素](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md)オプションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="9c66e-265">To configure the common language runtime (CLR) to also distribute threads from the thread pool across all CPU groups, enable the [Thread_UseAllCpuGroups element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) option.</span></span> <span data-ttu-id="9c66e-266">.NET Core アプリの場合は、`COMPlus_Thread_UseAllCpuGroups` 環境変数の値を `1` に設定することによって、このオプションを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="9c66e-266">For .NET Core apps, you can enable this option by setting the value of the `COMPlus_Thread_UseAllCpuGroups` environment variable to `1`.</span></span>

### <a name="systemgcnoaffinitizecomplus_gcnoaffinitize"></a><span data-ttu-id="9c66e-267">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="9c66e-267">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span></span>

- <span data-ttu-id="9c66e-268">ガベージ コレクション スレッドをプロセッサに "*関係付ける*" かどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="9c66e-268">Specifies whether to *affinitize* garbage collection threads with processors.</span></span> <span data-ttu-id="9c66e-269">GC スレッドを関係付けることは、その特定の CPU でのみ実行できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="9c66e-269">To affinitize a GC thread means that it can only run on its specific CPU.</span></span> <span data-ttu-id="9c66e-270">各 GC スレッドに対してヒープが作成されます。</span><span class="sxs-lookup"><span data-stu-id="9c66e-270">A heap is created for each GC thread.</span></span>
- <span data-ttu-id="9c66e-271">サーバー ガベージ コレクションにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="9c66e-271">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="9c66e-272">既定:ガベージ コレクション スレッドをプロセッサに関係付けます。</span><span class="sxs-lookup"><span data-stu-id="9c66e-272">Default: Affinitize garbage collection threads with processors.</span></span> <span data-ttu-id="9c66e-273">これは、値を `false` に設定した場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="9c66e-273">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="9c66e-274">設定の名前</span><span class="sxs-lookup"><span data-stu-id="9c66e-274">Setting name</span></span> | <span data-ttu-id="9c66e-275">値</span><span class="sxs-lookup"><span data-stu-id="9c66e-275">Values</span></span> | <span data-ttu-id="9c66e-276">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="9c66e-276">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9c66e-277">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9c66e-277">**runtimeconfig.json**</span></span> | `System.GC.NoAffinitize` | <span data-ttu-id="9c66e-278">`false` -関係付ける</span><span class="sxs-lookup"><span data-stu-id="9c66e-278">`false` - affinitize</span></span><br/><span data-ttu-id="9c66e-279">`true` -関係付けない</span><span class="sxs-lookup"><span data-stu-id="9c66e-279">`true` - don't affinitize</span></span> | <span data-ttu-id="9c66e-280">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9c66e-280">.NET Core 3.0</span></span> |
| <span data-ttu-id="9c66e-281">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="9c66e-281">**Environment variable**</span></span> | `COMPlus_GCNoAffinitize` | <span data-ttu-id="9c66e-282">`0` -関係付ける</span><span class="sxs-lookup"><span data-stu-id="9c66e-282">`0` - affinitize</span></span><br/><span data-ttu-id="9c66e-283">`1` -関係付けない</span><span class="sxs-lookup"><span data-stu-id="9c66e-283">`1` - don't affinitize</span></span> | <span data-ttu-id="9c66e-284">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9c66e-284">.NET Core 3.0</span></span> |
| <span data-ttu-id="9c66e-285">**.NET Framework 用の app.config**</span><span class="sxs-lookup"><span data-stu-id="9c66e-285">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="9c66e-286">GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="9c66e-286">GCNoAffinitize</span></span>](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | <span data-ttu-id="9c66e-287">`false` -関係付ける</span><span class="sxs-lookup"><span data-stu-id="9c66e-287">`false` - affinitize</span></span><br/><span data-ttu-id="9c66e-288">`true` -関係付けない</span><span class="sxs-lookup"><span data-stu-id="9c66e-288">`true` - don't affinitize</span></span> | <span data-ttu-id="9c66e-289">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="9c66e-289">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="9c66e-290">例:</span><span class="sxs-lookup"><span data-stu-id="9c66e-290">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="systemgcheaphardlimitcomplus_gcheaphardlimit"></a><span data-ttu-id="9c66e-291">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span><span class="sxs-lookup"><span data-stu-id="9c66e-291">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span></span>

- <span data-ttu-id="9c66e-292">GC ヒープおよび GC ブックキーピングに対して、最大コミット サイズをバイト単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="9c66e-292">Specifies the maximum commit size, in bytes, for the GC heap and GC bookkeeping.</span></span>
- <span data-ttu-id="9c66e-293">この設定は 64 ビットのコンピューターにのみ該当します。</span><span class="sxs-lookup"><span data-stu-id="9c66e-293">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="9c66e-294">[オブジェクトごとのヒープの制限](#per-object-heap-limits)が構成されている場合、この設定は無視されます。</span><span class="sxs-lookup"><span data-stu-id="9c66e-294">This setting is ignored if the [Per-object-heap limits](#per-object-heap-limits) are configured.</span></span>
- <span data-ttu-id="9c66e-295">特定のケースにのみ該当する既定値は、20 MB より大、またはコンテナーのメモリ制限の 75% より大です。</span><span class="sxs-lookup"><span data-stu-id="9c66e-295">The default value, which only applies in certain cases, is the greater of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="9c66e-296">次の場合に既定値は該当します。</span><span class="sxs-lookup"><span data-stu-id="9c66e-296">The default value applies if:</span></span>

  - <span data-ttu-id="9c66e-297">プロセスが、メモリ制限が指定されたコンテナー内で実行されています。</span><span class="sxs-lookup"><span data-stu-id="9c66e-297">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="9c66e-298">[System.GC.HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent) が設定されていません。</span><span class="sxs-lookup"><span data-stu-id="9c66e-298">[System.GC.HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent) is not set.</span></span>

| | <span data-ttu-id="9c66e-299">設定の名前</span><span class="sxs-lookup"><span data-stu-id="9c66e-299">Setting name</span></span> | <span data-ttu-id="9c66e-300">値</span><span class="sxs-lookup"><span data-stu-id="9c66e-300">Values</span></span> | <span data-ttu-id="9c66e-301">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="9c66e-301">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9c66e-302">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9c66e-302">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimit` | <span data-ttu-id="9c66e-303">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="9c66e-303">*decimal value*</span></span> | <span data-ttu-id="9c66e-304">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9c66e-304">.NET Core 3.0</span></span> |
| <span data-ttu-id="9c66e-305">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="9c66e-305">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimit` | <span data-ttu-id="9c66e-306">"*16 進値*"</span><span class="sxs-lookup"><span data-stu-id="9c66e-306">*hexadecimal value*</span></span> | <span data-ttu-id="9c66e-307">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9c66e-307">.NET Core 3.0</span></span> |

<span data-ttu-id="9c66e-308">例:</span><span class="sxs-lookup"><span data-stu-id="9c66e-308">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapHardLimit": 209715200
      }
   }
}
```

> [!TIP]
> <span data-ttu-id="9c66e-309">*runtimeconfig.json* でオプションを設定する場合は、10 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="9c66e-309">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="9c66e-310">環境変数としてオプションを設定する場合は、16 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="9c66e-310">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="9c66e-311">たとえば、ヒープのハード制限を 200 メビバイト (MiB) に指定する場合、値は JSON ファイルでは 209715200、環境変数では 0xC800000 または C800000 になります。</span><span class="sxs-lookup"><span data-stu-id="9c66e-311">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent"></a><span data-ttu-id="9c66e-312">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span><span class="sxs-lookup"><span data-stu-id="9c66e-312">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span></span>

- <span data-ttu-id="9c66e-313">許容可能な GC ヒープの使用量を、物理メモリ合計に対する割合として指定します。</span><span class="sxs-lookup"><span data-stu-id="9c66e-313">Specifies the allowable GC heap usage as a percentage of the total physical memory.</span></span>
- <span data-ttu-id="9c66e-314">この設定は、[System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) も設定されている場合、無視されます。</span><span class="sxs-lookup"><span data-stu-id="9c66e-314">If [System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) is also set, this setting is ignored.</span></span>
- <span data-ttu-id="9c66e-315">この設定は 64 ビットのコンピューターにのみ該当します。</span><span class="sxs-lookup"><span data-stu-id="9c66e-315">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="9c66e-316">プロセスが、メモリ制限が指定されたコンテナー内で実行されている場合、パーセンテージはそのメモリ制限に対するパーセンテージとして計算されます。</span><span class="sxs-lookup"><span data-stu-id="9c66e-316">If the process is running inside a container that has a specified memory limit, the percentage is calculated as a percentage of that memory limit.</span></span>
- <span data-ttu-id="9c66e-317">[オブジェクトごとのヒープの制限](#per-object-heap-limits)が構成されている場合、この設定は無視されます。</span><span class="sxs-lookup"><span data-stu-id="9c66e-317">This setting is ignored if the [Per-object-heap limits](#per-object-heap-limits) are configured.</span></span>
- <span data-ttu-id="9c66e-318">特定のケースにのみ該当する既定値は、20 MB 未満であるか、コンテナーのメモリ制限の 75% 未満です。</span><span class="sxs-lookup"><span data-stu-id="9c66e-318">The default value, which only applies in certain cases, is the lesser of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="9c66e-319">次の場合に既定値は該当します。</span><span class="sxs-lookup"><span data-stu-id="9c66e-319">The default value applies if:</span></span>

  - <span data-ttu-id="9c66e-320">プロセスが、メモリ制限が指定されたコンテナー内で実行されています。</span><span class="sxs-lookup"><span data-stu-id="9c66e-320">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="9c66e-321">[System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) が設定されていません。</span><span class="sxs-lookup"><span data-stu-id="9c66e-321">[System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) is not set.</span></span>

| | <span data-ttu-id="9c66e-322">設定の名前</span><span class="sxs-lookup"><span data-stu-id="9c66e-322">Setting name</span></span> | <span data-ttu-id="9c66e-323">値</span><span class="sxs-lookup"><span data-stu-id="9c66e-323">Values</span></span> | <span data-ttu-id="9c66e-324">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="9c66e-324">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9c66e-325">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9c66e-325">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPercent` | <span data-ttu-id="9c66e-326">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="9c66e-326">*decimal value*</span></span> | <span data-ttu-id="9c66e-327">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9c66e-327">.NET Core 3.0</span></span> |
| <span data-ttu-id="9c66e-328">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="9c66e-328">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimitPercent` | <span data-ttu-id="9c66e-329">"*16 進値*"</span><span class="sxs-lookup"><span data-stu-id="9c66e-329">*hexadecimal value*</span></span> | <span data-ttu-id="9c66e-330">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9c66e-330">.NET Core 3.0</span></span> |

<span data-ttu-id="9c66e-331">例:</span><span class="sxs-lookup"><span data-stu-id="9c66e-331">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapHardLimitPercent": 30
      }
   }
}
```

> [!TIP]
> <span data-ttu-id="9c66e-332">*runtimeconfig.json* でオプションを設定する場合は、10 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="9c66e-332">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="9c66e-333">環境変数としてオプションを設定する場合は、16 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="9c66e-333">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="9c66e-334">たとえば、ヒープの使用量を 30% に制限する場合、値は JSON ファイルでは 30、環境変数では 0x1E または 1E になります。</span><span class="sxs-lookup"><span data-stu-id="9c66e-334">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="per-object-heap-limits"></a><span data-ttu-id="9c66e-335">オブジェクトごとのヒープの制限</span><span class="sxs-lookup"><span data-stu-id="9c66e-335">Per-object-heap limits</span></span>

<span data-ttu-id="9c66e-336">オブジェクトごとのヒープに基づいて、GC で許容されるヒープ使用量を指定できます。</span><span class="sxs-lookup"><span data-stu-id="9c66e-336">You can specify the GC's allowable heap usage on a per-object-heap basis.</span></span> <span data-ttu-id="9c66e-337">ヒープには、大きなオブジェクト ヒープ (LOH)、小さなオブジェクト ヒープ (SOH)、固定オブジェクト ヒープ (POH) があります。</span><span class="sxs-lookup"><span data-stu-id="9c66e-337">The different heaps are the large object heap (LOH), small object heap (SOH), and pinned object heap (POH).</span></span>

#### <a name="complus_gcheaphardlimitsoh-complus_gcheaphardlimitloh-complus_gcheaphardlimitpoh"></a><span data-ttu-id="9c66e-338">COMPLUS_GCHeapHardLimitSOH、COMPLUS_GCHeapHardLimitLOH、COMPLUS_GCHeapHardLimitPOH</span><span class="sxs-lookup"><span data-stu-id="9c66e-338">COMPLUS_GCHeapHardLimitSOH, COMPLUS_GCHeapHardLimitLOH, COMPLUS_GCHeapHardLimitPOH</span></span>

- <span data-ttu-id="9c66e-339">`COMPLUS_GCHeapHardLimitSOH`、`COMPLUS_GCHeapHardLimitLOH`、`COMPLUS_GCHeapHardLimitPOH` 設定のいずれかの値を指定する場合、`COMPLUS_GCHeapHardLimitSOH` と `COMPLUS_GCHeapHardLimitLOH` の値も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c66e-339">If you specify a value for any of the `COMPLUS_GCHeapHardLimitSOH`, `COMPLUS_GCHeapHardLimitLOH`, or `COMPLUS_GCHeapHardLimitPOH` settings, you must also specify a value for `COMPLUS_GCHeapHardLimitSOH` and `COMPLUS_GCHeapHardLimitLOH`.</span></span> <span data-ttu-id="9c66e-340">そうしないと、ランタイムでの初期化が失敗します。</span><span class="sxs-lookup"><span data-stu-id="9c66e-340">If you don't, the runtime will fail to initialize.</span></span>
- <span data-ttu-id="9c66e-341">`COMPLUS_GCHeapHardLimitPOH` の既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="9c66e-341">The default value for `COMPLUS_GCHeapHardLimitPOH` is 0.</span></span> <span data-ttu-id="9c66e-342">`COMPLUS_GCHeapHardLimitSOH` と `COMPLUS_GCHeapHardLimitLOH` には既定値はありません。</span><span class="sxs-lookup"><span data-stu-id="9c66e-342">`COMPLUS_GCHeapHardLimitSOH` and `COMPLUS_GCHeapHardLimitLOH` don't have default values.</span></span>

| | <span data-ttu-id="9c66e-343">設定の名前</span><span class="sxs-lookup"><span data-stu-id="9c66e-343">Setting name</span></span> | <span data-ttu-id="9c66e-344">値</span><span class="sxs-lookup"><span data-stu-id="9c66e-344">Values</span></span> | <span data-ttu-id="9c66e-345">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="9c66e-345">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9c66e-346">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="9c66e-346">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitSOH` | <span data-ttu-id="9c66e-347">"*16 進値*"</span><span class="sxs-lookup"><span data-stu-id="9c66e-347">*hexadecimal value*</span></span> | <span data-ttu-id="9c66e-348">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="9c66e-348">.NET 5.0</span></span> |
| <span data-ttu-id="9c66e-349">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="9c66e-349">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitLOH` | <span data-ttu-id="9c66e-350">"*16 進値*"</span><span class="sxs-lookup"><span data-stu-id="9c66e-350">*hexadecimal value*</span></span> | <span data-ttu-id="9c66e-351">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="9c66e-351">.NET 5.0</span></span> |
| <span data-ttu-id="9c66e-352">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="9c66e-352">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitPOH` | <span data-ttu-id="9c66e-353">"*16 進値*"</span><span class="sxs-lookup"><span data-stu-id="9c66e-353">*hexadecimal value*</span></span> | <span data-ttu-id="9c66e-354">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="9c66e-354">.NET 5.0</span></span> |

> [!TIP]
> <span data-ttu-id="9c66e-355">環境変数としてオプションを設定する場合は、16 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="9c66e-355">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="9c66e-356">たとえば、ヒープのハード制限を 200 メビバイト (MiB) に指定する場合、値は 0xC800000 または C800000 になります。</span><span class="sxs-lookup"><span data-stu-id="9c66e-356">For example, to specify a heap hard limit of 200 mebibytes (MiB), the value would be 0xC800000 or C800000.</span></span>

#### <a name="complus_gcheaphardlimitsohpercent-complus_gcheaphardlimitlohpercent-complus_gcheaphardlimitpohpercent"></a><span data-ttu-id="9c66e-357">COMPLUS_GCHeapHardLimitSOHPercent、COMPLUS_GCHeapHardLimitLOHPercent、COMPLUS_GCHeapHardLimitPOHPercent</span><span class="sxs-lookup"><span data-stu-id="9c66e-357">COMPLUS_GCHeapHardLimitSOHPercent, COMPLUS_GCHeapHardLimitLOHPercent, COMPLUS_GCHeapHardLimitPOHPercent</span></span>

- <span data-ttu-id="9c66e-358">`COMPLUS_GCHeapHardLimitSOHPercent`、`COMPLUS_GCHeapHardLimitLOHPercent`、`COMPLUS_GCHeapHardLimitPOHPercent` 設定のいずれかの値を指定する場合、`COMPLUS_GCHeapHardLimitSOHPercent` と `COMPLUS_GCHeapHardLimitLOHPercent` の値も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c66e-358">If you specify a value for any of the `COMPLUS_GCHeapHardLimitSOHPercent`, `COMPLUS_GCHeapHardLimitLOHPercent`, or `COMPLUS_GCHeapHardLimitPOHPercent` settings, you must also specify a value for `COMPLUS_GCHeapHardLimitSOHPercent` and `COMPLUS_GCHeapHardLimitLOHPercent`.</span></span> <span data-ttu-id="9c66e-359">そうしないと、ランタイムでの初期化が失敗します。</span><span class="sxs-lookup"><span data-stu-id="9c66e-359">If you don't, the runtime will fail to initialize.</span></span>
- <span data-ttu-id="9c66e-360">`COMPLUS_GCHeapHardLimitSOH`、`COMPLUS_GCHeapHardLimitLOH`、および `COMPLUS_GCHeapHardLimitPOH` が指定されている場合、これらの設定は無視されます。</span><span class="sxs-lookup"><span data-stu-id="9c66e-360">These settings are ignored if `COMPLUS_GCHeapHardLimitSOH`, `COMPLUS_GCHeapHardLimitLOH`, and `COMPLUS_GCHeapHardLimitPOH` are specified.</span></span>
- <span data-ttu-id="9c66e-361">値 1 は、GC によって合計物理メモリの 1% がそのオブジェクト ヒープに使用されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="9c66e-361">A value of 1 means that GC uses 1% of total physical memory for that object heap.</span></span>
- <span data-ttu-id="9c66e-362">各値は、ゼロより大きく、100 未満である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c66e-362">Each value must be greater than zero and less than 100.</span></span> <span data-ttu-id="9c66e-363">また、3 つのパーセンテージ値の合計は、100 未満である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c66e-363">Additionally, the sum of the three percentage values must be less than 100.</span></span> <span data-ttu-id="9c66e-364">それ以外の場合、ランタイムでの初期化が失敗します。</span><span class="sxs-lookup"><span data-stu-id="9c66e-364">Otherwise, the runtime will fail to initialize.</span></span>

| | <span data-ttu-id="9c66e-365">設定の名前</span><span class="sxs-lookup"><span data-stu-id="9c66e-365">Setting name</span></span> | <span data-ttu-id="9c66e-366">値</span><span class="sxs-lookup"><span data-stu-id="9c66e-366">Values</span></span> | <span data-ttu-id="9c66e-367">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="9c66e-367">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9c66e-368">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="9c66e-368">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitSOHPercent` | <span data-ttu-id="9c66e-369">"*16 進値*"</span><span class="sxs-lookup"><span data-stu-id="9c66e-369">*hexadecimal value*</span></span> | <span data-ttu-id="9c66e-370">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="9c66e-370">.NET 5.0</span></span> |
| <span data-ttu-id="9c66e-371">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="9c66e-371">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitLOHPercent` | <span data-ttu-id="9c66e-372">"*16 進値*"</span><span class="sxs-lookup"><span data-stu-id="9c66e-372">*hexadecimal value*</span></span> | <span data-ttu-id="9c66e-373">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="9c66e-373">.NET 5.0</span></span> |
| <span data-ttu-id="9c66e-374">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="9c66e-374">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitPOHPercent` | <span data-ttu-id="9c66e-375">"*16 進値*"</span><span class="sxs-lookup"><span data-stu-id="9c66e-375">*hexadecimal value*</span></span> | <span data-ttu-id="9c66e-376">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="9c66e-376">.NET 5.0</span></span> |

> [!TIP]
> <span data-ttu-id="9c66e-377">環境変数としてオプションを設定する場合は、16 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="9c66e-377">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="9c66e-378">たとえば、ヒープの使用量を 30% に制限する場合、値は 0x1E または 1E になります。</span><span class="sxs-lookup"><span data-stu-id="9c66e-378">For example, to limit the heap usage to 30%, the value would be 0x1E or 1E.</span></span>

### <a name="systemgcretainvmcomplus_gcretainvm"></a><span data-ttu-id="9c66e-379">System.GC.RetainVM/COMPlus_GCRetainVM</span><span class="sxs-lookup"><span data-stu-id="9c66e-379">System.GC.RetainVM/COMPlus_GCRetainVM</span></span>

- <span data-ttu-id="9c66e-380">削除する必要があるセグメントを、後で使用するためにスタンバイ リストに配置するか、解放してオペレーティング システム (OS) に戻すかを構成します。</span><span class="sxs-lookup"><span data-stu-id="9c66e-380">Configures whether segments that should be deleted are put on a standby list for future use or are released back to the operating system (OS).</span></span>
- <span data-ttu-id="9c66e-381">既定:セグメントを解放してオペレーティング システムに戻します。</span><span class="sxs-lookup"><span data-stu-id="9c66e-381">Default: Release segments back to the operating system.</span></span> <span data-ttu-id="9c66e-382">これは、値を `false` に設定した場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="9c66e-382">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="9c66e-383">設定の名前</span><span class="sxs-lookup"><span data-stu-id="9c66e-383">Setting name</span></span> | <span data-ttu-id="9c66e-384">値</span><span class="sxs-lookup"><span data-stu-id="9c66e-384">Values</span></span> | <span data-ttu-id="9c66e-385">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="9c66e-385">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9c66e-386">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9c66e-386">**runtimeconfig.json**</span></span> | `System.GC.RetainVM` | <span data-ttu-id="9c66e-387">`false` -OS に解放する</span><span class="sxs-lookup"><span data-stu-id="9c66e-387">`false` - release to OS</span></span><br/><span data-ttu-id="9c66e-388">`true` - スタンバイに配置する</span><span class="sxs-lookup"><span data-stu-id="9c66e-388">`true` - put on standby</span></span> | <span data-ttu-id="9c66e-389">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="9c66e-389">.NET Core 1.0</span></span> |
| <span data-ttu-id="9c66e-390">**MSBuild のプロパティ**</span><span class="sxs-lookup"><span data-stu-id="9c66e-390">**MSBuild property**</span></span> | `RetainVMGarbageCollection` | <span data-ttu-id="9c66e-391">`false` -OS に解放する</span><span class="sxs-lookup"><span data-stu-id="9c66e-391">`false` - release to OS</span></span><br/><span data-ttu-id="9c66e-392">`true` - スタンバイに配置する</span><span class="sxs-lookup"><span data-stu-id="9c66e-392">`true` - put on standby</span></span> | <span data-ttu-id="9c66e-393">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="9c66e-393">.NET Core 1.0</span></span> |
| <span data-ttu-id="9c66e-394">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="9c66e-394">**Environment variable**</span></span> | `COMPlus_GCRetainVM` | <span data-ttu-id="9c66e-395">`0` -OS に解放する</span><span class="sxs-lookup"><span data-stu-id="9c66e-395">`0` - release to OS</span></span><br/><span data-ttu-id="9c66e-396">`1` - スタンバイに配置する</span><span class="sxs-lookup"><span data-stu-id="9c66e-396">`1` - put on standby</span></span> | <span data-ttu-id="9c66e-397">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="9c66e-397">.NET Core 1.0</span></span> |

### <a name="examples"></a><span data-ttu-id="9c66e-398">使用例</span><span class="sxs-lookup"><span data-stu-id="9c66e-398">Examples</span></span>

<span data-ttu-id="9c66e-399">*runtimeconfig.json* ファイル:</span><span class="sxs-lookup"><span data-stu-id="9c66e-399">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

<span data-ttu-id="9c66e-400">プロジェクト ファイル:</span><span class="sxs-lookup"><span data-stu-id="9c66e-400">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="large-pages"></a><span data-ttu-id="9c66e-401">大きいページ</span><span class="sxs-lookup"><span data-stu-id="9c66e-401">Large pages</span></span>

### <a name="complus_gclargepages"></a><span data-ttu-id="9c66e-402">COMPlus_GCLargePages</span><span class="sxs-lookup"><span data-stu-id="9c66e-402">COMPlus_GCLargePages</span></span>

- <span data-ttu-id="9c66e-403">ヒープのハード制限が設定されている場合に、大きいページを使用する必要があるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="9c66e-403">Specifies whether large pages should be used when a heap hard limit is set.</span></span>
- <span data-ttu-id="9c66e-404">既定:ヒープのハード制限が設定されている場合は、大きいページを使用しません。</span><span class="sxs-lookup"><span data-stu-id="9c66e-404">Default: Don't use large pages when a heap hard limit is set.</span></span> <span data-ttu-id="9c66e-405">これは、値を `0` に設定した場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="9c66e-405">This is equivalent to setting the value to `0`.</span></span>
- <span data-ttu-id="9c66e-406">これは試験段階の設定です。</span><span class="sxs-lookup"><span data-stu-id="9c66e-406">This is an experimental setting.</span></span>

| | <span data-ttu-id="9c66e-407">設定の名前</span><span class="sxs-lookup"><span data-stu-id="9c66e-407">Setting name</span></span> | <span data-ttu-id="9c66e-408">値</span><span class="sxs-lookup"><span data-stu-id="9c66e-408">Values</span></span> | <span data-ttu-id="9c66e-409">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="9c66e-409">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9c66e-410">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9c66e-410">**runtimeconfig.json**</span></span> | <span data-ttu-id="9c66e-411">N/A</span><span class="sxs-lookup"><span data-stu-id="9c66e-411">N/A</span></span> | <span data-ttu-id="9c66e-412">N/A</span><span class="sxs-lookup"><span data-stu-id="9c66e-412">N/A</span></span> | <span data-ttu-id="9c66e-413">N/A</span><span class="sxs-lookup"><span data-stu-id="9c66e-413">N/A</span></span> |
| <span data-ttu-id="9c66e-414">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="9c66e-414">**Environment variable**</span></span> | `COMPlus_GCLargePages` | <span data-ttu-id="9c66e-415">`0` - 無効</span><span class="sxs-lookup"><span data-stu-id="9c66e-415">`0` - disabled</span></span><br/><span data-ttu-id="9c66e-416">`1` - 有効</span><span class="sxs-lookup"><span data-stu-id="9c66e-416">`1` - enabled</span></span> | <span data-ttu-id="9c66e-417">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9c66e-417">.NET Core 3.0</span></span> |

## <a name="large-objects"></a><span data-ttu-id="9c66e-418">大きなオブジェクト</span><span class="sxs-lookup"><span data-stu-id="9c66e-418">Large objects</span></span>

### <a name="complus_gcallowverylargeobjects"></a><span data-ttu-id="9c66e-419">COMPlus_gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="9c66e-419">COMPlus_gcAllowVeryLargeObjects</span></span>

- <span data-ttu-id="9c66e-420">合計サイズが 2 ギガバイト (GB) を超える配列に対して、64 ビット プラットフォームでのガベージ コレクター サポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="9c66e-420">Configures garbage collector support on 64-bit platforms for arrays that are greater than 2 gigabytes (GB) in total size.</span></span>
- <span data-ttu-id="9c66e-421">既定:GC では、2 GB を超える配列がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="9c66e-421">Default: GC supports arrays greater than 2-GB.</span></span> <span data-ttu-id="9c66e-422">これは、値を `1` に設定した場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="9c66e-422">This is equivalent to setting the value to `1`.</span></span>
- <span data-ttu-id="9c66e-423">このオプションは、将来のバージョンの .NET で廃止される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9c66e-423">This option may become obsolete in a future version of .NET.</span></span>

| | <span data-ttu-id="9c66e-424">設定の名前</span><span class="sxs-lookup"><span data-stu-id="9c66e-424">Setting name</span></span> | <span data-ttu-id="9c66e-425">値</span><span class="sxs-lookup"><span data-stu-id="9c66e-425">Values</span></span> | <span data-ttu-id="9c66e-426">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="9c66e-426">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9c66e-427">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9c66e-427">**runtimeconfig.json**</span></span> | <span data-ttu-id="9c66e-428">N/A</span><span class="sxs-lookup"><span data-stu-id="9c66e-428">N/A</span></span> | <span data-ttu-id="9c66e-429">N/A</span><span class="sxs-lookup"><span data-stu-id="9c66e-429">N/A</span></span> | <span data-ttu-id="9c66e-430">N/A</span><span class="sxs-lookup"><span data-stu-id="9c66e-430">N/A</span></span> |
| <span data-ttu-id="9c66e-431">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="9c66e-431">**Environment variable**</span></span> | `COMPlus_gcAllowVeryLargeObjects` | <span data-ttu-id="9c66e-432">`1` - 有効</span><span class="sxs-lookup"><span data-stu-id="9c66e-432">`1` - enabled</span></span><br/> <span data-ttu-id="9c66e-433">`0` - 無効</span><span class="sxs-lookup"><span data-stu-id="9c66e-433">`0` - disabled</span></span> | <span data-ttu-id="9c66e-434">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="9c66e-434">.NET Core 1.0</span></span> |
| <span data-ttu-id="9c66e-435">**.NET Framework 用の app.config**</span><span class="sxs-lookup"><span data-stu-id="9c66e-435">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="9c66e-436">gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="9c66e-436">gcAllowVeryLargeObjects</span></span>](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | <span data-ttu-id="9c66e-437">`1` - 有効</span><span class="sxs-lookup"><span data-stu-id="9c66e-437">`1` - enabled</span></span><br/> <span data-ttu-id="9c66e-438">`0` - 無効</span><span class="sxs-lookup"><span data-stu-id="9c66e-438">`0` - disabled</span></span> | <span data-ttu-id="9c66e-439">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="9c66e-439">.NET Framework 4.5</span></span> |

## <a name="large-object-heap-threshold"></a><span data-ttu-id="9c66e-440">大きなオブジェクト ヒープのしきい値</span><span class="sxs-lookup"><span data-stu-id="9c66e-440">Large object heap threshold</span></span>

### <a name="systemgclohthresholdcomplus_gclohthreshold"></a><span data-ttu-id="9c66e-441">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="9c66e-441">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span></span>

- <span data-ttu-id="9c66e-442">オブジェクトが大きなオブジェクト ヒープ (LOH) に移る原因となる、しきい値のサイズ (バイト単位) を指定します。</span><span class="sxs-lookup"><span data-stu-id="9c66e-442">Specifies the threshold size, in bytes, that causes objects to go on the large object heap (LOH).</span></span>
- <span data-ttu-id="9c66e-443">既定のしきい値は 85,000 バイトです。</span><span class="sxs-lookup"><span data-stu-id="9c66e-443">The default threshold is 85,000 bytes.</span></span>
- <span data-ttu-id="9c66e-444">指定する値は、既定のしきい値より大きくする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c66e-444">The value you specify must be larger than the default threshold.</span></span>

| | <span data-ttu-id="9c66e-445">設定の名前</span><span class="sxs-lookup"><span data-stu-id="9c66e-445">Setting name</span></span> | <span data-ttu-id="9c66e-446">値</span><span class="sxs-lookup"><span data-stu-id="9c66e-446">Values</span></span> | <span data-ttu-id="9c66e-447">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="9c66e-447">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9c66e-448">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9c66e-448">**runtimeconfig.json**</span></span> | `System.GC.LOHThreshold` | <span data-ttu-id="9c66e-449">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="9c66e-449">*decimal value*</span></span> | <span data-ttu-id="9c66e-450">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="9c66e-450">.NET Core 1.0</span></span> |
| <span data-ttu-id="9c66e-451">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="9c66e-451">**Environment variable**</span></span> | `COMPlus_GCLOHThreshold` | <span data-ttu-id="9c66e-452">"*16 進値*"</span><span class="sxs-lookup"><span data-stu-id="9c66e-452">*hexadecimal value*</span></span> | <span data-ttu-id="9c66e-453">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="9c66e-453">.NET Core 1.0</span></span> |
| <span data-ttu-id="9c66e-454">**.NET Framework 用の app.config**</span><span class="sxs-lookup"><span data-stu-id="9c66e-454">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="9c66e-455">GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="9c66e-455">GCLOHThreshold</span></span>](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | <span data-ttu-id="9c66e-456">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="9c66e-456">*decimal value*</span></span> | <span data-ttu-id="9c66e-457">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="9c66e-457">.NET Framework 4.8</span></span> |

<span data-ttu-id="9c66e-458">例:</span><span class="sxs-lookup"><span data-stu-id="9c66e-458">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.LOHThreshold": 120000
      }
   }
}
```

> [!TIP]
> <span data-ttu-id="9c66e-459">*runtimeconfig.json* でオプションを設定する場合は、10 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="9c66e-459">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="9c66e-460">環境変数としてオプションを設定する場合は、16 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="9c66e-460">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="9c66e-461">たとえば、しきい値のサイズを 120,000 バイトに設定する場合、値は JSON ファイルでは 120000、環境変数では 0x1D4C0 または 1D4C0 になります。</span><span class="sxs-lookup"><span data-stu-id="9c66e-461">For example, to set a threshold size of 120,000 bytes, the values would be 120000 for the JSON file and 0x1D4C0 or 1D4C0 for the environment variable.</span></span>

## <a name="standalone-gc"></a><span data-ttu-id="9c66e-462">スタンドアロン GC</span><span class="sxs-lookup"><span data-stu-id="9c66e-462">Standalone GC</span></span>

### <a name="complus_gcname"></a><span data-ttu-id="9c66e-463">COMPlus_GCName</span><span class="sxs-lookup"><span data-stu-id="9c66e-463">COMPlus_GCName</span></span>

- <span data-ttu-id="9c66e-464">ランタイムで読み込む対象となる、ガベージ コレクターを含むライブラリへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="9c66e-464">Specifies a path to the library containing the garbage collector that the runtime intends to load.</span></span>
- <span data-ttu-id="9c66e-465">詳細については、「[スタンドアロン GC ローダーの設計](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c66e-465">For more information, see [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span></span>

| | <span data-ttu-id="9c66e-466">設定の名前</span><span class="sxs-lookup"><span data-stu-id="9c66e-466">Setting name</span></span> | <span data-ttu-id="9c66e-467">値</span><span class="sxs-lookup"><span data-stu-id="9c66e-467">Values</span></span> | <span data-ttu-id="9c66e-468">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="9c66e-468">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9c66e-469">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9c66e-469">**runtimeconfig.json**</span></span> | <span data-ttu-id="9c66e-470">N/A</span><span class="sxs-lookup"><span data-stu-id="9c66e-470">N/A</span></span> | <span data-ttu-id="9c66e-471">N/A</span><span class="sxs-lookup"><span data-stu-id="9c66e-471">N/A</span></span> | <span data-ttu-id="9c66e-472">N/A</span><span class="sxs-lookup"><span data-stu-id="9c66e-472">N/A</span></span> |
| <span data-ttu-id="9c66e-473">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="9c66e-473">**Environment variable**</span></span> | `COMPlus_GCName` | <span data-ttu-id="9c66e-474">*string_path*</span><span class="sxs-lookup"><span data-stu-id="9c66e-474">*string_path*</span></span> | <span data-ttu-id="9c66e-475">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="9c66e-475">.NET Core 2.0</span></span> |
