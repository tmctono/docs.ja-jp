---
title: ガベージ コレクター構成の設定
description: ガベージ コレクターでの .NET Core アプリ用のメモリの管理方法を構成するための、実行時設定について学習します。
ms.date: 01/09/2020
ms.topic: reference
ms.openlocfilehash: d7e3d040cd634eeb020beff806c60f834cc02585
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2020
ms.locfileid: "83761981"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a><span data-ttu-id="16b0c-103">ガベージ コレクションの実行時構成オプション</span><span class="sxs-lookup"><span data-stu-id="16b0c-103">Run-time configuration options for garbage collection</span></span>

<span data-ttu-id="16b0c-104">このページには、実行時に変更できるガベージ コレクター (GC) の設定に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="16b0c-104">This page contains information about garbage collector (GC) settings that can be changed at run time.</span></span> <span data-ttu-id="16b0c-105">実行中のアプリのピーク時のパフォーマンスを実現しようとしている場合は、これらの設定の使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="16b0c-105">If you're trying to achieve peak performance of a running app, consider using these settings.</span></span> <span data-ttu-id="16b0c-106">しかし、一般的な状況では、既定値でほとんどのアプリケーションに最適なパフォーマンスが得られます。</span><span class="sxs-lookup"><span data-stu-id="16b0c-106">However, the defaults provide optimum performance for most applications in typical situations.</span></span>

<span data-ttu-id="16b0c-107">このページでは、設定はグループにまとめられます。</span><span class="sxs-lookup"><span data-stu-id="16b0c-107">Settings are arranged into groups on this page.</span></span> <span data-ttu-id="16b0c-108">各グループ内の設定は一般的に、特定の結果を得るために相互に組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="16b0c-108">The settings within each group are commonly used in conjunction with each other to achieve a specific result.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="16b0c-109">これらの設定は、実行中にアプリで動的に変更することもできます。したがって、設定した実行時の設定が上書きされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="16b0c-109">These settings can also be changed dynamically by the app as it's running, so any run-time settings you set may be overridden.</span></span>
> - <span data-ttu-id="16b0c-110">[待機時間レベル](../../standard/garbage-collection/latency.md)などの一部の設定は、通常、デザイン時に API を介してのみ設定されます。</span><span class="sxs-lookup"><span data-stu-id="16b0c-110">Some settings, such as [latency level](../../standard/garbage-collection/latency.md), are typically set only through the API at design time.</span></span> <span data-ttu-id="16b0c-111">このページでは、このような設定は省略されています。</span><span class="sxs-lookup"><span data-stu-id="16b0c-111">Such settings are omitted from this page.</span></span>
> - <span data-ttu-id="16b0c-112">数値の場合、*runtimeconfig.json* ファイルの設定には 10 進表記、環境変数の設定には 16 進表記を使用します。</span><span class="sxs-lookup"><span data-stu-id="16b0c-112">For number values, use decimal notation for settings in the *runtimeconfig.json* file and hexadecimal notation for environment variable settings.</span></span> <span data-ttu-id="16b0c-113">16 進値の場合は、プレフィックス "0x" を付けても付けなくても指定できます。</span><span class="sxs-lookup"><span data-stu-id="16b0c-113">For hexadecimal values, you can specify them with or without the "0x" prefix.</span></span>

## <a name="flavors-of-garbage-collection"></a><span data-ttu-id="16b0c-114">ガベージ コレクションのフレーバー</span><span class="sxs-lookup"><span data-stu-id="16b0c-114">Flavors of garbage collection</span></span>

<span data-ttu-id="16b0c-115">ガベージ コレクションの主な 2 つのフレーバーは、ワークステーション GC とサーバー GC です。</span><span class="sxs-lookup"><span data-stu-id="16b0c-115">The two main flavors of garbage collection are workstation GC and server GC.</span></span> <span data-ttu-id="16b0c-116">2 つの間の相違点について詳しくは、「[ワークステーションとサーバーのガベージ コレクション](../../standard/garbage-collection/workstation-server-gc.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="16b0c-116">For more information about differences between the two, see [Workstation and server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span>

<span data-ttu-id="16b0c-117">ガベージ コレクションのサブフレーバーは、バックグラウンドと非同時実行です。</span><span class="sxs-lookup"><span data-stu-id="16b0c-117">The subflavors of garbage collection are background and non-concurrent.</span></span>

<span data-ttu-id="16b0c-118">ガベージ コレクションのフレーバーを選択するには、以下の設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="16b0c-118">Use the following settings to select flavors of garbage collection:</span></span>

### <a name="systemgcservercomplus_gcserver"></a><span data-ttu-id="16b0c-119">System.GC.Server/COMPlus_gcServer</span><span class="sxs-lookup"><span data-stu-id="16b0c-119">System.GC.Server/COMPlus_gcServer</span></span>

- <span data-ttu-id="16b0c-120">アプリケーションで、ワークステーション ガベージ コレクションとサーバー ガベージ コレクションのどちらを使用するかを構成します。</span><span class="sxs-lookup"><span data-stu-id="16b0c-120">Configures whether the application uses workstation garbage collection or server garbage collection.</span></span>
- <span data-ttu-id="16b0c-121">既定:ワークステーション ガベージ コレクション。</span><span class="sxs-lookup"><span data-stu-id="16b0c-121">Default: Workstation garbage collection.</span></span> <span data-ttu-id="16b0c-122">これは、値を `false` に設定した場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="16b0c-122">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="16b0c-123">設定の名前</span><span class="sxs-lookup"><span data-stu-id="16b0c-123">Setting name</span></span> | <span data-ttu-id="16b0c-124">値</span><span class="sxs-lookup"><span data-stu-id="16b0c-124">Values</span></span> | <span data-ttu-id="16b0c-125">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="16b0c-125">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="16b0c-126">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="16b0c-126">**runtimeconfig.json**</span></span> | `System.GC.Server` | <span data-ttu-id="16b0c-127">`false` - ワークステーション</span><span class="sxs-lookup"><span data-stu-id="16b0c-127">`false` - workstation</span></span><br/><span data-ttu-id="16b0c-128">`true` - サーバー</span><span class="sxs-lookup"><span data-stu-id="16b0c-128">`true` - server</span></span> | <span data-ttu-id="16b0c-129">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="16b0c-129">.NET Core 1.0</span></span> |
| <span data-ttu-id="16b0c-130">**MSBuild のプロパティ**</span><span class="sxs-lookup"><span data-stu-id="16b0c-130">**MSBuild property**</span></span> | `ServerGarbageCollection` | <span data-ttu-id="16b0c-131">`false` - ワークステーション</span><span class="sxs-lookup"><span data-stu-id="16b0c-131">`false` - workstation</span></span><br/><span data-ttu-id="16b0c-132">`true` - サーバー</span><span class="sxs-lookup"><span data-stu-id="16b0c-132">`true` - server</span></span> | <span data-ttu-id="16b0c-133">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="16b0c-133">.NET Core 1.0</span></span> |
| <span data-ttu-id="16b0c-134">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="16b0c-134">**Environment variable**</span></span> | `COMPlus_gcServer` | <span data-ttu-id="16b0c-135">`0` - ワークステーション</span><span class="sxs-lookup"><span data-stu-id="16b0c-135">`0` - workstation</span></span><br/><span data-ttu-id="16b0c-136">`1` - サーバー</span><span class="sxs-lookup"><span data-stu-id="16b0c-136">`1` - server</span></span> | <span data-ttu-id="16b0c-137">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="16b0c-137">.NET Core 1.0</span></span> |
| <span data-ttu-id="16b0c-138">**.NET Framework 用の app.config**</span><span class="sxs-lookup"><span data-stu-id="16b0c-138">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="16b0c-139">GCServer</span><span class="sxs-lookup"><span data-stu-id="16b0c-139">GCServer</span></span>](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | <span data-ttu-id="16b0c-140">`false` - ワークステーション</span><span class="sxs-lookup"><span data-stu-id="16b0c-140">`false` - workstation</span></span><br/><span data-ttu-id="16b0c-141">`true` - サーバー</span><span class="sxs-lookup"><span data-stu-id="16b0c-141">`true` - server</span></span> |  |

### <a name="examples"></a><span data-ttu-id="16b0c-142">使用例</span><span class="sxs-lookup"><span data-stu-id="16b0c-142">Examples</span></span>

<span data-ttu-id="16b0c-143">*runtimeconfig.json* ファイル:</span><span class="sxs-lookup"><span data-stu-id="16b0c-143">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

<span data-ttu-id="16b0c-144">プロジェクト ファイル:</span><span class="sxs-lookup"><span data-stu-id="16b0c-144">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ServerGarbageCollection>true</ServerGarbageCollection>
  </PropertyGroup>

</Project>
```

### <a name="systemgcconcurrentcomplus_gcconcurrent"></a><span data-ttu-id="16b0c-145">System.GC.Concurrent/COMPlus_gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="16b0c-145">System.GC.Concurrent/COMPlus_gcConcurrent</span></span>

- <span data-ttu-id="16b0c-146">バックグラウンド (同時実行) ガベージ コレクションを有効にするかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="16b0c-146">Configures whether background (concurrent) garbage collection is enabled.</span></span>
- <span data-ttu-id="16b0c-147">既定:バックグラウンド GC を使用します。</span><span class="sxs-lookup"><span data-stu-id="16b0c-147">Default: Use background GC.</span></span> <span data-ttu-id="16b0c-148">これは、値を `true` に設定した場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="16b0c-148">This is equivalent to setting the value to `true`.</span></span>
- <span data-ttu-id="16b0c-149">詳しくは、「[バックグラウンド ガベージ コレクション](../../standard/garbage-collection/background-gc.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="16b0c-149">For more information, see [Background garbage collection](../../standard/garbage-collection/background-gc.md).</span></span>

| | <span data-ttu-id="16b0c-150">設定の名前</span><span class="sxs-lookup"><span data-stu-id="16b0c-150">Setting name</span></span> | <span data-ttu-id="16b0c-151">値</span><span class="sxs-lookup"><span data-stu-id="16b0c-151">Values</span></span> | <span data-ttu-id="16b0c-152">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="16b0c-152">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="16b0c-153">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="16b0c-153">**runtimeconfig.json**</span></span> | `System.GC.Concurrent` | <span data-ttu-id="16b0c-154">`true` - バックグラウンド GC</span><span class="sxs-lookup"><span data-stu-id="16b0c-154">`true` - background GC</span></span><br/><span data-ttu-id="16b0c-155">`false` -非同時実行 GC</span><span class="sxs-lookup"><span data-stu-id="16b0c-155">`false` - non-concurrent GC</span></span> | <span data-ttu-id="16b0c-156">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="16b0c-156">.NET Core 1.0</span></span> |
| <span data-ttu-id="16b0c-157">**MSBuild のプロパティ**</span><span class="sxs-lookup"><span data-stu-id="16b0c-157">**MSBuild property**</span></span> | `ConcurrentGarbageCollection` | <span data-ttu-id="16b0c-158">`true` - バックグラウンド GC</span><span class="sxs-lookup"><span data-stu-id="16b0c-158">`true` - background GC</span></span><br/><span data-ttu-id="16b0c-159">`false` -非同時実行 GC</span><span class="sxs-lookup"><span data-stu-id="16b0c-159">`false` - non-concurrent GC</span></span> | <span data-ttu-id="16b0c-160">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="16b0c-160">.NET Core 1.0</span></span> |
| <span data-ttu-id="16b0c-161">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="16b0c-161">**Environment variable**</span></span> | `COMPlus_gcConcurrent` | <span data-ttu-id="16b0c-162">`true` - バックグラウンド GC</span><span class="sxs-lookup"><span data-stu-id="16b0c-162">`true` - background GC</span></span><br/><span data-ttu-id="16b0c-163">`false` -非同時実行 GC</span><span class="sxs-lookup"><span data-stu-id="16b0c-163">`false` - non-concurrent GC</span></span> | <span data-ttu-id="16b0c-164">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="16b0c-164">.NET Core 1.0</span></span> |
| <span data-ttu-id="16b0c-165">**.NET Framework 用の app.config**</span><span class="sxs-lookup"><span data-stu-id="16b0c-165">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="16b0c-166">gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="16b0c-166">gcConcurrent</span></span>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | <span data-ttu-id="16b0c-167">`true` - バックグラウンド GC</span><span class="sxs-lookup"><span data-stu-id="16b0c-167">`true` - background GC</span></span><br/><span data-ttu-id="16b0c-168">`false` -非同時実行 GC</span><span class="sxs-lookup"><span data-stu-id="16b0c-168">`false` - non-concurrent GC</span></span> |  |

### <a name="examples"></a><span data-ttu-id="16b0c-169">使用例</span><span class="sxs-lookup"><span data-stu-id="16b0c-169">Examples</span></span>

<span data-ttu-id="16b0c-170">*runtimeconfig.json* ファイル:</span><span class="sxs-lookup"><span data-stu-id="16b0c-170">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

<span data-ttu-id="16b0c-171">プロジェクト ファイル:</span><span class="sxs-lookup"><span data-stu-id="16b0c-171">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="manage-resource-usage"></a><span data-ttu-id="16b0c-172">リソース使用量を管理する</span><span class="sxs-lookup"><span data-stu-id="16b0c-172">Manage resource usage</span></span>

<span data-ttu-id="16b0c-173">このセクションで説明する設定を使用して、ガベージ コレクターのメモリとプロセッサの使用量を管理します。</span><span class="sxs-lookup"><span data-stu-id="16b0c-173">Use the settings described in this section to manage the garbage collector's memory and processor usage.</span></span>

<span data-ttu-id="16b0c-174">これらの設定のいくつかの詳細については、[ワークステーションおよびサーバー GC 間の妥協点](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/)に関するブログ エントリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="16b0c-174">For more information about some of these settings, see the [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) blog entry.</span></span>

### <a name="systemgcheapcountcomplus_gcheapcount"></a><span data-ttu-id="16b0c-175">System.GC.HeapCount/COMPlus_GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="16b0c-175">System.GC.HeapCount/COMPlus_GCHeapCount</span></span>

- <span data-ttu-id="16b0c-176">ガベージ コレクターによって作成されるヒープの数を制限します。</span><span class="sxs-lookup"><span data-stu-id="16b0c-176">Limits the number of heaps created by the garbage collector.</span></span>
- <span data-ttu-id="16b0c-177">サーバー ガベージ コレクションにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="16b0c-177">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="16b0c-178">[GC プロセッサの関係](#systemgcnoaffinitizecomplus_gcnoaffinitize)が有効になっている場合 (既定値)、ヒープ数の設定では、最初の `n` プロセッサに `n` GC ヒープやスレッドを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="16b0c-178">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is enabled, which is the default, the heap count setting affinitizes `n` GC heaps/threads to the first `n` processors.</span></span> <span data-ttu-id="16b0c-179">([関係付けマスク](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask)または[関係付け範囲](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges)の設定を使用して、関係付けるプロセッサを正確に指定します)。</span><span class="sxs-lookup"><span data-stu-id="16b0c-179">(Use the [affinitize mask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) or [affinitize ranges](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges) settings to specify exactly which processors to affinitize.)</span></span>
- <span data-ttu-id="16b0c-180">[GC プロセッサの関係](#systemgcnoaffinitizecomplus_gcnoaffinitize)が無効になっている場合、この設定によって GC ヒープの数が制限されます。</span><span class="sxs-lookup"><span data-stu-id="16b0c-180">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting limits the number of GC heaps.</span></span>
- <span data-ttu-id="16b0c-181">詳細については、[GCHeapCount の解説](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks)に関する記述を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16b0c-181">For more information, see the [GCHeapCount remarks](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span></span>

| | <span data-ttu-id="16b0c-182">設定の名前</span><span class="sxs-lookup"><span data-stu-id="16b0c-182">Setting name</span></span> | <span data-ttu-id="16b0c-183">値</span><span class="sxs-lookup"><span data-stu-id="16b0c-183">Values</span></span> | <span data-ttu-id="16b0c-184">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="16b0c-184">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="16b0c-185">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="16b0c-185">**runtimeconfig.json**</span></span> | `System.GC.HeapCount` | <span data-ttu-id="16b0c-186">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="16b0c-186">*decimal value*</span></span> | <span data-ttu-id="16b0c-187">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="16b0c-187">.NET Core 3.0</span></span> |
| <span data-ttu-id="16b0c-188">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="16b0c-188">**Environment variable**</span></span> | `COMPlus_GCHeapCount` | <span data-ttu-id="16b0c-189">"*16 進値*"</span><span class="sxs-lookup"><span data-stu-id="16b0c-189">*hexadecimal value*</span></span> | <span data-ttu-id="16b0c-190">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="16b0c-190">.NET Core 3.0</span></span> |
| <span data-ttu-id="16b0c-191">**.NET Framework 用の app.config**</span><span class="sxs-lookup"><span data-stu-id="16b0c-191">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="16b0c-192">GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="16b0c-192">GCHeapCount</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | <span data-ttu-id="16b0c-193">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="16b0c-193">*decimal value*</span></span> | <span data-ttu-id="16b0c-194">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="16b0c-194">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="16b0c-195">例:</span><span class="sxs-lookup"><span data-stu-id="16b0c-195">Example:</span></span>

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
> <span data-ttu-id="16b0c-196">*runtimeconfig.json* でオプションを設定する場合は、10 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="16b0c-196">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="16b0c-197">環境変数としてオプションを設定する場合は、16 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="16b0c-197">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="16b0c-198">たとえば、ヒープの数を 16 に制限する場合、値は JSON ファイルでは 16、環境変数では 0x10 または 10 になります。</span><span class="sxs-lookup"><span data-stu-id="16b0c-198">For example, to limit the number of heaps to 16, the values would be 16 for the JSON file and 0x10 or 10 for the environment variable.</span></span>

### <a name="systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask"></a><span data-ttu-id="16b0c-199">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="16b0c-199">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span></span>

- <span data-ttu-id="16b0c-200">ガベージ コレクター スレッドで使用する必要がある正確なプロセッサを指定します。</span><span class="sxs-lookup"><span data-stu-id="16b0c-200">Specifies the exact processors that garbage collector threads should use.</span></span>
- <span data-ttu-id="16b0c-201">[GC プロセッサの関係](#systemgcnoaffinitizecomplus_gcnoaffinitize)が無効になっている場合、この設定は無視されます。</span><span class="sxs-lookup"><span data-stu-id="16b0c-201">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="16b0c-202">サーバー ガベージ コレクションにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="16b0c-202">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="16b0c-203">この値は、プロセスで使用できるプロセッサを定義するビット マスクです。</span><span class="sxs-lookup"><span data-stu-id="16b0c-203">The value is a bit mask that defines the processors that are available to the process.</span></span> <span data-ttu-id="16b0c-204">たとえば、10 進値の 1023 (環境変数を使用する場合は、16 進値の 0x3FF または 3FF) は、バイナリ表記では 0011 1111 1111 となります。</span><span class="sxs-lookup"><span data-stu-id="16b0c-204">For example, a decimal value of 1023 (or a hexadecimal value of 0x3FF or 3FF if you're using the environment variable) is 0011 1111 1111 in binary notation.</span></span> <span data-ttu-id="16b0c-205">これにより、最初の 10 プロセッサが使用されることが指定されます。</span><span class="sxs-lookup"><span data-stu-id="16b0c-205">This specifies that the first 10 processors are to be used.</span></span> <span data-ttu-id="16b0c-206">次の 10 プロセッサ (つまり、10 から 19 プロセッサ) を指定するには、10 進値の 1047552 (または 16 進値の 0xFFC00 または FFC00) を指定します。これは、バイナリ値の 1111 1111 1100 0000 0000 に相当します。</span><span class="sxs-lookup"><span data-stu-id="16b0c-206">To specify the next 10 processors, that is, processors 10-19, specify a decimal value of 1047552 (or a hexadecimal value of 0xFFC00 or FFC00), which is equivalent to a binary value of 1111 1111 1100 0000 0000.</span></span>

| | <span data-ttu-id="16b0c-207">設定の名前</span><span class="sxs-lookup"><span data-stu-id="16b0c-207">Setting name</span></span> | <span data-ttu-id="16b0c-208">値</span><span class="sxs-lookup"><span data-stu-id="16b0c-208">Values</span></span> | <span data-ttu-id="16b0c-209">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="16b0c-209">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="16b0c-210">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="16b0c-210">**runtimeconfig.json**</span></span> | `System.GC.HeapAffinitizeMask` | <span data-ttu-id="16b0c-211">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="16b0c-211">*decimal value*</span></span> | <span data-ttu-id="16b0c-212">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="16b0c-212">.NET Core 3.0</span></span> |
| <span data-ttu-id="16b0c-213">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="16b0c-213">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeMask` | <span data-ttu-id="16b0c-214">"*16 進値*"</span><span class="sxs-lookup"><span data-stu-id="16b0c-214">*hexadecimal value*</span></span> | <span data-ttu-id="16b0c-215">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="16b0c-215">.NET Core 3.0</span></span> |
| <span data-ttu-id="16b0c-216">**.NET Framework 用の app.config**</span><span class="sxs-lookup"><span data-stu-id="16b0c-216">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="16b0c-217">GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="16b0c-217">GCHeapAffinitizeMask</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | <span data-ttu-id="16b0c-218">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="16b0c-218">*decimal value*</span></span> | <span data-ttu-id="16b0c-219">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="16b0c-219">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="16b0c-220">例:</span><span class="sxs-lookup"><span data-stu-id="16b0c-220">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges"></a><span data-ttu-id="16b0c-221">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span><span class="sxs-lookup"><span data-stu-id="16b0c-221">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span></span>

- <span data-ttu-id="16b0c-222">ガベージ コレクター スレッドに使用するプロセッサのリストを指定します。</span><span class="sxs-lookup"><span data-stu-id="16b0c-222">Specifies the list of processors to use for garbage collector threads.</span></span>
- <span data-ttu-id="16b0c-223">この設定は [System.GC.HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) に似ていますが、64 を超えるプロセッサを指定できる点が異なります。</span><span class="sxs-lookup"><span data-stu-id="16b0c-223">This setting is similar to [System.GC.HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask), except it allows you to specify more than 64 processors.</span></span>
- <span data-ttu-id="16b0c-224">Windows オペレーティング システムの場合、プロセッサの番号または範囲の前に、対応する [CPU グループ](/windows/win32/procthread/processor-groups)を付けます。たとえば、"0:1-10,0:12,1:50-52,1:70" となります。</span><span class="sxs-lookup"><span data-stu-id="16b0c-224">For Windows operating systems, prefix the processor number or range with the corresponding [CPU group](/windows/win32/procthread/processor-groups), for example, "0:1-10,0:12,1:50-52,1:70".</span></span>
- <span data-ttu-id="16b0c-225">[GC プロセッサの関係](#systemgcnoaffinitizecomplus_gcnoaffinitize)が無効になっている場合、この設定は無視されます。</span><span class="sxs-lookup"><span data-stu-id="16b0c-225">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="16b0c-226">サーバー ガベージ コレクションにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="16b0c-226">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="16b0c-227">詳細については、Maoni Stephens のブログの「[CPU が 64 を超えるコンピューター上での GC のための CPU 構成の向上](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16b0c-227">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="16b0c-228">設定の名前</span><span class="sxs-lookup"><span data-stu-id="16b0c-228">Setting name</span></span> | <span data-ttu-id="16b0c-229">値</span><span class="sxs-lookup"><span data-stu-id="16b0c-229">Values</span></span> | <span data-ttu-id="16b0c-230">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="16b0c-230">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="16b0c-231">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="16b0c-231">**runtimeconfig.json**</span></span> | `System.GC.GCHeapAffinitizeRanges` | <span data-ttu-id="16b0c-232">プロセッサ番号またはプロセッサ番号の範囲のコンマ区切りリスト。</span><span class="sxs-lookup"><span data-stu-id="16b0c-232">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="16b0c-233">Unix の例:"1-10,12,50-52,70"</span><span class="sxs-lookup"><span data-stu-id="16b0c-233">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="16b0c-234">Windows の例:"0:1-10,0:12,1:50-52,1:70"</span><span class="sxs-lookup"><span data-stu-id="16b0c-234">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="16b0c-235">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="16b0c-235">.NET Core 3.0</span></span> |
| <span data-ttu-id="16b0c-236">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="16b0c-236">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeRanges` | <span data-ttu-id="16b0c-237">プロセッサ番号またはプロセッサ番号の範囲のコンマ区切りリスト。</span><span class="sxs-lookup"><span data-stu-id="16b0c-237">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="16b0c-238">Unix の例:"1-10,12,50-52,70"</span><span class="sxs-lookup"><span data-stu-id="16b0c-238">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="16b0c-239">Windows の例:"0:1-10,0:12,1:50-52,1:70"</span><span class="sxs-lookup"><span data-stu-id="16b0c-239">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="16b0c-240">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="16b0c-240">.NET Core 3.0</span></span> |

<span data-ttu-id="16b0c-241">例:</span><span class="sxs-lookup"><span data-stu-id="16b0c-241">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="complus_gccpugroup"></a><span data-ttu-id="16b0c-242">COMPlus_GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="16b0c-242">COMPlus_GCCpuGroup</span></span>

- <span data-ttu-id="16b0c-243">ガベージ コレクターで [CPU グループ](/windows/win32/procthread/processor-groups)を使用するかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="16b0c-243">Configures whether the garbage collector uses [CPU groups](/windows/win32/procthread/processor-groups) or not.</span></span>

  <span data-ttu-id="16b0c-244">64 ビットの Windows コンピューターに複数の CPU グループがある (つまり、64 を超えるプロセッサがある) 場合、この要素を有効にすると、すべての CPU グループ全体にガベージ コレクションが拡張されます。</span><span class="sxs-lookup"><span data-stu-id="16b0c-244">When a 64-bit Windows computer has multiple CPU groups, that is, there are more than 64 processors, enabling this element extends garbage collection across all CPU groups.</span></span> <span data-ttu-id="16b0c-245">ガベージ コレクターではすべてのコアを使用し、ヒープを作成して分散させます。</span><span class="sxs-lookup"><span data-stu-id="16b0c-245">The garbage collector uses all cores to create and balance heaps.</span></span>

- <span data-ttu-id="16b0c-246">64 ビット Windows オペレーティング システムのみのサーバー ガベージ コレクションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="16b0c-246">Applies to server garbage collection on 64-bit Windows operation systems only.</span></span>
- <span data-ttu-id="16b0c-247">既定:GC は複数の CPU グループに拡張されません。</span><span class="sxs-lookup"><span data-stu-id="16b0c-247">Default: GC does not extend across CPU groups.</span></span> <span data-ttu-id="16b0c-248">これは、値を `0` に設定した場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="16b0c-248">This is equivalent to setting the value to `0`.</span></span>
- <span data-ttu-id="16b0c-249">詳細については、Maoni Stephens のブログの「[CPU が 64 を超えるコンピューター上での GC のための CPU 構成の向上](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16b0c-249">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="16b0c-250">設定の名前</span><span class="sxs-lookup"><span data-stu-id="16b0c-250">Setting name</span></span> | <span data-ttu-id="16b0c-251">値</span><span class="sxs-lookup"><span data-stu-id="16b0c-251">Values</span></span> | <span data-ttu-id="16b0c-252">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="16b0c-252">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="16b0c-253">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="16b0c-253">**runtimeconfig.json**</span></span> | <span data-ttu-id="16b0c-254">N/A</span><span class="sxs-lookup"><span data-stu-id="16b0c-254">N/A</span></span> | <span data-ttu-id="16b0c-255">N/A</span><span class="sxs-lookup"><span data-stu-id="16b0c-255">N/A</span></span> | <span data-ttu-id="16b0c-256">N/A</span><span class="sxs-lookup"><span data-stu-id="16b0c-256">N/A</span></span> |
| <span data-ttu-id="16b0c-257">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="16b0c-257">**Environment variable**</span></span> | `COMPlus_GCCpuGroup` | <span data-ttu-id="16b0c-258">`0` - 無効</span><span class="sxs-lookup"><span data-stu-id="16b0c-258">`0` - disabled</span></span><br/><span data-ttu-id="16b0c-259">`1` - 有効</span><span class="sxs-lookup"><span data-stu-id="16b0c-259">`1` - enabled</span></span> | <span data-ttu-id="16b0c-260">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="16b0c-260">.NET Core 1.0</span></span> |
| <span data-ttu-id="16b0c-261">**.NET Framework 用の app.config**</span><span class="sxs-lookup"><span data-stu-id="16b0c-261">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="16b0c-262">GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="16b0c-262">GCCpuGroup</span></span>](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | <span data-ttu-id="16b0c-263">`false` - 無効</span><span class="sxs-lookup"><span data-stu-id="16b0c-263">`false` - disabled</span></span><br/><span data-ttu-id="16b0c-264">`true` - 有効</span><span class="sxs-lookup"><span data-stu-id="16b0c-264">`true` - enabled</span></span> |  |

> [!NOTE]
> <span data-ttu-id="16b0c-265">すべての CPU グループ全体にスレッド プールからのスレッドも分散するように共通言語ランタイム (CLR) を構成するには、[Thread_UseAllCpuGroups 要素](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md)オプションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="16b0c-265">To configure the common language runtime (CLR) to also distribute threads from the thread pool across all CPU groups, enable the [Thread_UseAllCpuGroups element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) option.</span></span> <span data-ttu-id="16b0c-266">.NET Core アプリの場合は、`COMPlus_Thread_UseAllCpuGroups` 環境変数の値を `1` に設定することによって、このオプションを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="16b0c-266">For .NET Core apps, you can enable this option by setting the value of the `COMPlus_Thread_UseAllCpuGroups` environment variable to `1`.</span></span>

### <a name="systemgcnoaffinitizecomplus_gcnoaffinitize"></a><span data-ttu-id="16b0c-267">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="16b0c-267">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span></span>

- <span data-ttu-id="16b0c-268">ガベージ コレクション スレッドをプロセッサに "*関係付ける*" かどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="16b0c-268">Specifies whether to *affinitize* garbage collection threads with processors.</span></span> <span data-ttu-id="16b0c-269">GC スレッドを関係付けることは、その特定の CPU でのみ実行できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="16b0c-269">To affinitize a GC thread means that it can only run on its specific CPU.</span></span> <span data-ttu-id="16b0c-270">各 GC スレッドに対してヒープが作成されます。</span><span class="sxs-lookup"><span data-stu-id="16b0c-270">A heap is created for each GC thread.</span></span>
- <span data-ttu-id="16b0c-271">サーバー ガベージ コレクションにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="16b0c-271">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="16b0c-272">既定:ガベージ コレクション スレッドをプロセッサに関係付けます。</span><span class="sxs-lookup"><span data-stu-id="16b0c-272">Default: Affinitize garbage collection threads with processors.</span></span> <span data-ttu-id="16b0c-273">これは、値を `false` に設定した場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="16b0c-273">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="16b0c-274">設定の名前</span><span class="sxs-lookup"><span data-stu-id="16b0c-274">Setting name</span></span> | <span data-ttu-id="16b0c-275">値</span><span class="sxs-lookup"><span data-stu-id="16b0c-275">Values</span></span> | <span data-ttu-id="16b0c-276">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="16b0c-276">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="16b0c-277">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="16b0c-277">**runtimeconfig.json**</span></span> | `System.GC.NoAffinitize` | <span data-ttu-id="16b0c-278">`false` -関係付ける</span><span class="sxs-lookup"><span data-stu-id="16b0c-278">`false` - affinitize</span></span><br/><span data-ttu-id="16b0c-279">`true` -関係付けない</span><span class="sxs-lookup"><span data-stu-id="16b0c-279">`true` - don't affinitize</span></span> | <span data-ttu-id="16b0c-280">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="16b0c-280">.NET Core 3.0</span></span> |
| <span data-ttu-id="16b0c-281">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="16b0c-281">**Environment variable**</span></span> | `COMPlus_GCNoAffinitize` | <span data-ttu-id="16b0c-282">`0` -関係付ける</span><span class="sxs-lookup"><span data-stu-id="16b0c-282">`0` - affinitize</span></span><br/><span data-ttu-id="16b0c-283">`1` -関係付けない</span><span class="sxs-lookup"><span data-stu-id="16b0c-283">`1` - don't affinitize</span></span> | <span data-ttu-id="16b0c-284">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="16b0c-284">.NET Core 3.0</span></span> |
| <span data-ttu-id="16b0c-285">**.NET Framework 用の app.config**</span><span class="sxs-lookup"><span data-stu-id="16b0c-285">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="16b0c-286">GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="16b0c-286">GCNoAffinitize</span></span>](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | <span data-ttu-id="16b0c-287">`false` -関係付ける</span><span class="sxs-lookup"><span data-stu-id="16b0c-287">`false` - affinitize</span></span><br/><span data-ttu-id="16b0c-288">`true` -関係付けない</span><span class="sxs-lookup"><span data-stu-id="16b0c-288">`true` - don't affinitize</span></span> | <span data-ttu-id="16b0c-289">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="16b0c-289">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="16b0c-290">例:</span><span class="sxs-lookup"><span data-stu-id="16b0c-290">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="systemgcheaphardlimitcomplus_gcheaphardlimit"></a><span data-ttu-id="16b0c-291">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span><span class="sxs-lookup"><span data-stu-id="16b0c-291">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span></span>

- <span data-ttu-id="16b0c-292">GC ヒープおよび GC ブックキーピングに対して、最大コミット サイズをバイト単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="16b0c-292">Specifies the maximum commit size, in bytes, for the GC heap and GC bookkeeping.</span></span>
- <span data-ttu-id="16b0c-293">この設定は 64 ビットのコンピューターにのみ該当します。</span><span class="sxs-lookup"><span data-stu-id="16b0c-293">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="16b0c-294">特定のケースにのみ該当する既定値は、20 MB より大、またはコンテナーのメモリ制限の 75% より大です。</span><span class="sxs-lookup"><span data-stu-id="16b0c-294">The default value, which only applies in certain cases, is the greater of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="16b0c-295">次の場合に既定値は該当します。</span><span class="sxs-lookup"><span data-stu-id="16b0c-295">The default value applies if:</span></span>

  - <span data-ttu-id="16b0c-296">プロセスが、メモリ制限が指定されたコンテナー内で実行されています。</span><span class="sxs-lookup"><span data-stu-id="16b0c-296">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="16b0c-297">[System.GC.HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent) が設定されていません。</span><span class="sxs-lookup"><span data-stu-id="16b0c-297">[System.GC.HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent) is not set.</span></span>

| | <span data-ttu-id="16b0c-298">設定の名前</span><span class="sxs-lookup"><span data-stu-id="16b0c-298">Setting name</span></span> | <span data-ttu-id="16b0c-299">値</span><span class="sxs-lookup"><span data-stu-id="16b0c-299">Values</span></span> | <span data-ttu-id="16b0c-300">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="16b0c-300">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="16b0c-301">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="16b0c-301">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimit` | <span data-ttu-id="16b0c-302">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="16b0c-302">*decimal value*</span></span> | <span data-ttu-id="16b0c-303">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="16b0c-303">.NET Core 3.0</span></span> |
| <span data-ttu-id="16b0c-304">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="16b0c-304">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimit` | <span data-ttu-id="16b0c-305">"*16 進値*"</span><span class="sxs-lookup"><span data-stu-id="16b0c-305">*hexadecimal value*</span></span> | <span data-ttu-id="16b0c-306">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="16b0c-306">.NET Core 3.0</span></span> |

<span data-ttu-id="16b0c-307">例:</span><span class="sxs-lookup"><span data-stu-id="16b0c-307">Example:</span></span>

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
> <span data-ttu-id="16b0c-308">*runtimeconfig.json* でオプションを設定する場合は、10 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="16b0c-308">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="16b0c-309">環境変数としてオプションを設定する場合は、16 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="16b0c-309">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="16b0c-310">たとえば、ヒープのハード制限を 200 メビバイト (MiB) に指定する場合、値は JSON ファイルでは 209715200、環境変数では 0xC800000 または C800000 になります。</span><span class="sxs-lookup"><span data-stu-id="16b0c-310">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent"></a><span data-ttu-id="16b0c-311">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span><span class="sxs-lookup"><span data-stu-id="16b0c-311">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span></span>

- <span data-ttu-id="16b0c-312">許容可能な GC ヒープの使用量を、物理メモリ合計に対する割合として指定します。</span><span class="sxs-lookup"><span data-stu-id="16b0c-312">Specifies the allowable GC heap usage as a percentage of the total physical memory.</span></span>
- <span data-ttu-id="16b0c-313">この設定は、[System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) も設定されている場合、無視されます。</span><span class="sxs-lookup"><span data-stu-id="16b0c-313">If [System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) is also set, this setting is ignored.</span></span>
- <span data-ttu-id="16b0c-314">この設定は 64 ビットのコンピューターにのみ該当します。</span><span class="sxs-lookup"><span data-stu-id="16b0c-314">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="16b0c-315">プロセスが、メモリ制限が指定されたコンテナー内で実行されている場合、パーセンテージはそのメモリ制限に対するパーセンテージとして計算されます。</span><span class="sxs-lookup"><span data-stu-id="16b0c-315">If the process is running inside a container that has a specified memory limit, the percentage is calculated as a percentage of that memory limit.</span></span>
- <span data-ttu-id="16b0c-316">特定のケースにのみ該当する既定値は、20 MB 未満であるか、コンテナーのメモリ制限の 75% 未満です。</span><span class="sxs-lookup"><span data-stu-id="16b0c-316">The default value, which only applies in certain cases, is the lesser of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="16b0c-317">次の場合に既定値は該当します。</span><span class="sxs-lookup"><span data-stu-id="16b0c-317">The default value applies if:</span></span>

  - <span data-ttu-id="16b0c-318">プロセスが、メモリ制限が指定されたコンテナー内で実行されています。</span><span class="sxs-lookup"><span data-stu-id="16b0c-318">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="16b0c-319">[System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) が設定されていません。</span><span class="sxs-lookup"><span data-stu-id="16b0c-319">[System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) is not set.</span></span>

| | <span data-ttu-id="16b0c-320">設定の名前</span><span class="sxs-lookup"><span data-stu-id="16b0c-320">Setting name</span></span> | <span data-ttu-id="16b0c-321">値</span><span class="sxs-lookup"><span data-stu-id="16b0c-321">Values</span></span> | <span data-ttu-id="16b0c-322">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="16b0c-322">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="16b0c-323">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="16b0c-323">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPercent` | <span data-ttu-id="16b0c-324">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="16b0c-324">*decimal value*</span></span> | <span data-ttu-id="16b0c-325">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="16b0c-325">.NET Core 3.0</span></span> |
| <span data-ttu-id="16b0c-326">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="16b0c-326">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimitPercent` | <span data-ttu-id="16b0c-327">"*16 進値*"</span><span class="sxs-lookup"><span data-stu-id="16b0c-327">*hexadecimal value*</span></span> | <span data-ttu-id="16b0c-328">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="16b0c-328">.NET Core 3.0</span></span> |

<span data-ttu-id="16b0c-329">例:</span><span class="sxs-lookup"><span data-stu-id="16b0c-329">Example:</span></span>

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
> <span data-ttu-id="16b0c-330">*runtimeconfig.json* でオプションを設定する場合は、10 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="16b0c-330">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="16b0c-331">環境変数としてオプションを設定する場合は、16 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="16b0c-331">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="16b0c-332">たとえば、ヒープの使用量を 30% に制限する場合、値は JSON ファイルでは 30、環境変数では 0x1E または 1E になります。</span><span class="sxs-lookup"><span data-stu-id="16b0c-332">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="systemgcretainvmcomplus_gcretainvm"></a><span data-ttu-id="16b0c-333">System.GC.RetainVM/COMPlus_GCRetainVM</span><span class="sxs-lookup"><span data-stu-id="16b0c-333">System.GC.RetainVM/COMPlus_GCRetainVM</span></span>

- <span data-ttu-id="16b0c-334">削除する必要があるセグメントを、後で使用するためにスタンバイ リストに配置するか、解放してオペレーティング システム (OS) に戻すかを構成します。</span><span class="sxs-lookup"><span data-stu-id="16b0c-334">Configures whether segments that should be deleted are put on a standby list for future use or are released back to the operating system (OS).</span></span>
- <span data-ttu-id="16b0c-335">既定:セグメントを解放してオペレーティング システムに戻します。</span><span class="sxs-lookup"><span data-stu-id="16b0c-335">Default: Release segments back to the operating system.</span></span> <span data-ttu-id="16b0c-336">これは、値を `false` に設定した場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="16b0c-336">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="16b0c-337">設定の名前</span><span class="sxs-lookup"><span data-stu-id="16b0c-337">Setting name</span></span> | <span data-ttu-id="16b0c-338">値</span><span class="sxs-lookup"><span data-stu-id="16b0c-338">Values</span></span> | <span data-ttu-id="16b0c-339">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="16b0c-339">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="16b0c-340">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="16b0c-340">**runtimeconfig.json**</span></span> | `System.GC.RetainVM` | <span data-ttu-id="16b0c-341">`false` -OS に解放する</span><span class="sxs-lookup"><span data-stu-id="16b0c-341">`false` - release to OS</span></span><br/><span data-ttu-id="16b0c-342">`true` - スタンバイに配置する</span><span class="sxs-lookup"><span data-stu-id="16b0c-342">`true` - put on standby</span></span> | <span data-ttu-id="16b0c-343">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="16b0c-343">.NET Core 1.0</span></span> |
| <span data-ttu-id="16b0c-344">**MSBuild のプロパティ**</span><span class="sxs-lookup"><span data-stu-id="16b0c-344">**MSBuild property**</span></span> | `RetainVMGarbageCollection` | <span data-ttu-id="16b0c-345">`false` -OS に解放する</span><span class="sxs-lookup"><span data-stu-id="16b0c-345">`false` - release to OS</span></span><br/><span data-ttu-id="16b0c-346">`true` - スタンバイに配置する</span><span class="sxs-lookup"><span data-stu-id="16b0c-346">`true` - put on standby</span></span> | <span data-ttu-id="16b0c-347">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="16b0c-347">.NET Core 1.0</span></span> |
| <span data-ttu-id="16b0c-348">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="16b0c-348">**Environment variable**</span></span> | `COMPlus_GCRetainVM` | <span data-ttu-id="16b0c-349">`0` -OS に解放する</span><span class="sxs-lookup"><span data-stu-id="16b0c-349">`0` - release to OS</span></span><br/><span data-ttu-id="16b0c-350">`1` - スタンバイに配置する</span><span class="sxs-lookup"><span data-stu-id="16b0c-350">`1` - put on standby</span></span> | <span data-ttu-id="16b0c-351">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="16b0c-351">.NET Core 1.0</span></span> |

### <a name="examples"></a><span data-ttu-id="16b0c-352">使用例</span><span class="sxs-lookup"><span data-stu-id="16b0c-352">Examples</span></span>

<span data-ttu-id="16b0c-353">*runtimeconfig.json* ファイル:</span><span class="sxs-lookup"><span data-stu-id="16b0c-353">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

<span data-ttu-id="16b0c-354">プロジェクト ファイル:</span><span class="sxs-lookup"><span data-stu-id="16b0c-354">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="large-pages"></a><span data-ttu-id="16b0c-355">大きいページ</span><span class="sxs-lookup"><span data-stu-id="16b0c-355">Large pages</span></span>

### <a name="complus_gclargepages"></a><span data-ttu-id="16b0c-356">COMPlus_GCLargePages</span><span class="sxs-lookup"><span data-stu-id="16b0c-356">COMPlus_GCLargePages</span></span>

- <span data-ttu-id="16b0c-357">ヒープのハード制限が設定されている場合に、大きいページを使用する必要があるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="16b0c-357">Specifies whether large pages should be used when a heap hard limit is set.</span></span>
- <span data-ttu-id="16b0c-358">既定:ヒープのハード制限が設定されている場合は、大きいページを使用しません。</span><span class="sxs-lookup"><span data-stu-id="16b0c-358">Default: Don't use large pages when a heap hard limit is set.</span></span> <span data-ttu-id="16b0c-359">これは、値を `0` に設定した場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="16b0c-359">This is equivalent to setting the value to `0`.</span></span>
- <span data-ttu-id="16b0c-360">これは試験段階の設定です。</span><span class="sxs-lookup"><span data-stu-id="16b0c-360">This is an experimental setting.</span></span>

| | <span data-ttu-id="16b0c-361">設定の名前</span><span class="sxs-lookup"><span data-stu-id="16b0c-361">Setting name</span></span> | <span data-ttu-id="16b0c-362">値</span><span class="sxs-lookup"><span data-stu-id="16b0c-362">Values</span></span> | <span data-ttu-id="16b0c-363">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="16b0c-363">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="16b0c-364">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="16b0c-364">**runtimeconfig.json**</span></span> | <span data-ttu-id="16b0c-365">N/A</span><span class="sxs-lookup"><span data-stu-id="16b0c-365">N/A</span></span> | <span data-ttu-id="16b0c-366">N/A</span><span class="sxs-lookup"><span data-stu-id="16b0c-366">N/A</span></span> | <span data-ttu-id="16b0c-367">N/A</span><span class="sxs-lookup"><span data-stu-id="16b0c-367">N/A</span></span> |
| <span data-ttu-id="16b0c-368">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="16b0c-368">**Environment variable**</span></span> | `COMPlus_GCLargePages` | <span data-ttu-id="16b0c-369">`0` - 無効</span><span class="sxs-lookup"><span data-stu-id="16b0c-369">`0` - disabled</span></span><br/><span data-ttu-id="16b0c-370">`1` - 有効</span><span class="sxs-lookup"><span data-stu-id="16b0c-370">`1` - enabled</span></span> | <span data-ttu-id="16b0c-371">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="16b0c-371">.NET Core 3.0</span></span> |

## <a name="large-objects"></a><span data-ttu-id="16b0c-372">大きなオブジェクト</span><span class="sxs-lookup"><span data-stu-id="16b0c-372">Large objects</span></span>

### <a name="complus_gcallowverylargeobjects"></a><span data-ttu-id="16b0c-373">COMPlus_gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="16b0c-373">COMPlus_gcAllowVeryLargeObjects</span></span>

- <span data-ttu-id="16b0c-374">合計サイズが 2 ギガバイト (GB) を超える配列に対して、64 ビット プラットフォームでのガベージ コレクター サポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="16b0c-374">Configures garbage collector support on 64-bit platforms for arrays that are greater than 2 gigabytes (GB) in total size.</span></span>
- <span data-ttu-id="16b0c-375">既定:GC では、2 GB を超える配列がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="16b0c-375">Default: GC supports arrays greater than 2-GB.</span></span> <span data-ttu-id="16b0c-376">これは、値を `1` に設定した場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="16b0c-376">This is equivalent to setting the value to `1`.</span></span>
- <span data-ttu-id="16b0c-377">このオプションは、将来のバージョンの .NET で廃止される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="16b0c-377">This option may become obsolete in a future version of .NET.</span></span>

| | <span data-ttu-id="16b0c-378">設定の名前</span><span class="sxs-lookup"><span data-stu-id="16b0c-378">Setting name</span></span> | <span data-ttu-id="16b0c-379">値</span><span class="sxs-lookup"><span data-stu-id="16b0c-379">Values</span></span> | <span data-ttu-id="16b0c-380">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="16b0c-380">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="16b0c-381">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="16b0c-381">**runtimeconfig.json**</span></span> | <span data-ttu-id="16b0c-382">N/A</span><span class="sxs-lookup"><span data-stu-id="16b0c-382">N/A</span></span> | <span data-ttu-id="16b0c-383">N/A</span><span class="sxs-lookup"><span data-stu-id="16b0c-383">N/A</span></span> | <span data-ttu-id="16b0c-384">N/A</span><span class="sxs-lookup"><span data-stu-id="16b0c-384">N/A</span></span> |
| <span data-ttu-id="16b0c-385">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="16b0c-385">**Environment variable**</span></span> | `COMPlus_gcAllowVeryLargeObjects` | <span data-ttu-id="16b0c-386">`1` - 有効</span><span class="sxs-lookup"><span data-stu-id="16b0c-386">`1` - enabled</span></span><br/> <span data-ttu-id="16b0c-387">`0` - 無効</span><span class="sxs-lookup"><span data-stu-id="16b0c-387">`0` - disabled</span></span> | <span data-ttu-id="16b0c-388">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="16b0c-388">.NET Core 1.0</span></span> |
| <span data-ttu-id="16b0c-389">**.NET Framework 用の app.config**</span><span class="sxs-lookup"><span data-stu-id="16b0c-389">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="16b0c-390">gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="16b0c-390">gcAllowVeryLargeObjects</span></span>](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | <span data-ttu-id="16b0c-391">`1` - 有効</span><span class="sxs-lookup"><span data-stu-id="16b0c-391">`1` - enabled</span></span><br/> <span data-ttu-id="16b0c-392">`0` - 無効</span><span class="sxs-lookup"><span data-stu-id="16b0c-392">`0` - disabled</span></span> | <span data-ttu-id="16b0c-393">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="16b0c-393">.NET Framework 4.5</span></span> |

## <a name="large-object-heap-threshold"></a><span data-ttu-id="16b0c-394">大きなオブジェクト ヒープのしきい値</span><span class="sxs-lookup"><span data-stu-id="16b0c-394">Large object heap threshold</span></span>

### <a name="systemgclohthresholdcomplus_gclohthreshold"></a><span data-ttu-id="16b0c-395">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="16b0c-395">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span></span>

- <span data-ttu-id="16b0c-396">オブジェクトが大きなオブジェクト ヒープ (LOH) に移る原因となる、しきい値のサイズ (バイト単位) を指定します。</span><span class="sxs-lookup"><span data-stu-id="16b0c-396">Specifies the threshold size, in bytes, that causes objects to go on the large object heap (LOH).</span></span>
- <span data-ttu-id="16b0c-397">既定のしきい値は 85,000 バイトです。</span><span class="sxs-lookup"><span data-stu-id="16b0c-397">The default threshold is 85,000 bytes.</span></span>
- <span data-ttu-id="16b0c-398">指定する値は、既定のしきい値より大きくする必要があります。</span><span class="sxs-lookup"><span data-stu-id="16b0c-398">The value you specify must be larger than the default threshold.</span></span>

| | <span data-ttu-id="16b0c-399">設定の名前</span><span class="sxs-lookup"><span data-stu-id="16b0c-399">Setting name</span></span> | <span data-ttu-id="16b0c-400">値</span><span class="sxs-lookup"><span data-stu-id="16b0c-400">Values</span></span> | <span data-ttu-id="16b0c-401">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="16b0c-401">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="16b0c-402">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="16b0c-402">**runtimeconfig.json**</span></span> | `System.GC.LOHThreshold` | <span data-ttu-id="16b0c-403">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="16b0c-403">*decimal value*</span></span> | <span data-ttu-id="16b0c-404">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="16b0c-404">.NET Core 1.0</span></span> |
| <span data-ttu-id="16b0c-405">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="16b0c-405">**Environment variable**</span></span> | `COMPlus_GCLOHThreshold` | <span data-ttu-id="16b0c-406">"*16 進値*"</span><span class="sxs-lookup"><span data-stu-id="16b0c-406">*hexadecimal value*</span></span> | <span data-ttu-id="16b0c-407">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="16b0c-407">.NET Core 1.0</span></span> |
| <span data-ttu-id="16b0c-408">**.NET Framework 用の app.config**</span><span class="sxs-lookup"><span data-stu-id="16b0c-408">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="16b0c-409">GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="16b0c-409">GCLOHThreshold</span></span>](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | <span data-ttu-id="16b0c-410">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="16b0c-410">*decimal value*</span></span> | <span data-ttu-id="16b0c-411">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="16b0c-411">.NET Framework 4.8</span></span> |

<span data-ttu-id="16b0c-412">例:</span><span class="sxs-lookup"><span data-stu-id="16b0c-412">Example:</span></span>

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
> <span data-ttu-id="16b0c-413">*runtimeconfig.json* でオプションを設定する場合は、10 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="16b0c-413">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="16b0c-414">環境変数としてオプションを設定する場合は、16 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="16b0c-414">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="16b0c-415">たとえば、しきい値のサイズを 120,000 バイトに設定する場合、値は JSON ファイルでは 120000、環境変数では 0x1D4C0 または 1D4C0 になります。</span><span class="sxs-lookup"><span data-stu-id="16b0c-415">For example, to set a threshold size of 120,000 bytes, the values would be 120000 for the JSON file and 0x1D4C0 or 1D4C0 for the environment variable.</span></span>

## <a name="standalone-gc"></a><span data-ttu-id="16b0c-416">スタンドアロン GC</span><span class="sxs-lookup"><span data-stu-id="16b0c-416">Standalone GC</span></span>

### <a name="complus_gcname"></a><span data-ttu-id="16b0c-417">COMPlus_GCName</span><span class="sxs-lookup"><span data-stu-id="16b0c-417">COMPlus_GCName</span></span>

- <span data-ttu-id="16b0c-418">ランタイムで読み込む対象となる、ガベージ コレクターを含むライブラリへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="16b0c-418">Specifies a path to the library containing the garbage collector that the runtime intends to load.</span></span>
- <span data-ttu-id="16b0c-419">詳細については、「[スタンドアロン GC ローダーの設計](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16b0c-419">For more information, see [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span></span>

| | <span data-ttu-id="16b0c-420">設定の名前</span><span class="sxs-lookup"><span data-stu-id="16b0c-420">Setting name</span></span> | <span data-ttu-id="16b0c-421">値</span><span class="sxs-lookup"><span data-stu-id="16b0c-421">Values</span></span> | <span data-ttu-id="16b0c-422">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="16b0c-422">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="16b0c-423">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="16b0c-423">**runtimeconfig.json**</span></span> | <span data-ttu-id="16b0c-424">N/A</span><span class="sxs-lookup"><span data-stu-id="16b0c-424">N/A</span></span> | <span data-ttu-id="16b0c-425">N/A</span><span class="sxs-lookup"><span data-stu-id="16b0c-425">N/A</span></span> | <span data-ttu-id="16b0c-426">N/A</span><span class="sxs-lookup"><span data-stu-id="16b0c-426">N/A</span></span> |
| <span data-ttu-id="16b0c-427">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="16b0c-427">**Environment variable**</span></span> | `COMPlus_GCName` | <span data-ttu-id="16b0c-428">*string_path*</span><span class="sxs-lookup"><span data-stu-id="16b0c-428">*string_path*</span></span> | <span data-ttu-id="16b0c-429">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="16b0c-429">.NET Core 2.0</span></span> |
