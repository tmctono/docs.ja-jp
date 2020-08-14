---
title: ガベージ コレクター構成の設定
description: ガベージ コレクターでの .NET Core アプリ用のメモリの管理方法を構成するための、実行時設定について学習します。
ms.date: 07/10/2020
ms.topic: reference
ms.openlocfilehash: 91d155b638c7e69b3d2c0216266a7c0c0410db4c
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2020
ms.locfileid: "87915991"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a><span data-ttu-id="f7f96-103">ガベージ コレクションの実行時構成オプション</span><span class="sxs-lookup"><span data-stu-id="f7f96-103">Run-time configuration options for garbage collection</span></span>

<span data-ttu-id="f7f96-104">このページには、実行時に変更できるガベージ コレクター (GC) の設定に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f7f96-104">This page contains information about garbage collector (GC) settings that can be changed at run time.</span></span> <span data-ttu-id="f7f96-105">実行中のアプリのピーク時のパフォーマンスを実現しようとしている場合は、これらの設定の使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="f7f96-105">If you're trying to achieve peak performance of a running app, consider using these settings.</span></span> <span data-ttu-id="f7f96-106">しかし、一般的な状況では、既定値でほとんどのアプリケーションに最適なパフォーマンスが得られます。</span><span class="sxs-lookup"><span data-stu-id="f7f96-106">However, the defaults provide optimum performance for most applications in typical situations.</span></span>

<span data-ttu-id="f7f96-107">このページでは、設定はグループにまとめられます。</span><span class="sxs-lookup"><span data-stu-id="f7f96-107">Settings are arranged into groups on this page.</span></span> <span data-ttu-id="f7f96-108">各グループ内の設定は一般的に、特定の結果を得るために相互に組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="f7f96-108">The settings within each group are commonly used in conjunction with each other to achieve a specific result.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="f7f96-109">これらの設定は、実行中にアプリで動的に変更することもできます。したがって、設定した実行時の設定が上書きされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f7f96-109">These settings can also be changed dynamically by the app as it's running, so any run-time settings you set may be overridden.</span></span>
> - <span data-ttu-id="f7f96-110">[待機時間レベル](../../standard/garbage-collection/latency.md)などの一部の設定は、通常、デザイン時に API を介してのみ設定されます。</span><span class="sxs-lookup"><span data-stu-id="f7f96-110">Some settings, such as [latency level](../../standard/garbage-collection/latency.md), are typically set only through the API at design time.</span></span> <span data-ttu-id="f7f96-111">このページでは、このような設定は省略されています。</span><span class="sxs-lookup"><span data-stu-id="f7f96-111">Such settings are omitted from this page.</span></span>
> - <span data-ttu-id="f7f96-112">数値の場合、*runtimeconfig.json* ファイルの設定には 10 進表記、環境変数の設定には 16 進表記を使用します。</span><span class="sxs-lookup"><span data-stu-id="f7f96-112">For number values, use decimal notation for settings in the *runtimeconfig.json* file and hexadecimal notation for environment variable settings.</span></span> <span data-ttu-id="f7f96-113">16 進値の場合は、プレフィックス "0x" を付けても付けなくても指定できます。</span><span class="sxs-lookup"><span data-stu-id="f7f96-113">For hexadecimal values, you can specify them with or without the "0x" prefix.</span></span>

## <a name="flavors-of-garbage-collection"></a><span data-ttu-id="f7f96-114">ガベージ コレクションのフレーバー</span><span class="sxs-lookup"><span data-stu-id="f7f96-114">Flavors of garbage collection</span></span>

<span data-ttu-id="f7f96-115">ガベージ コレクションの主な 2 つのフレーバーは、ワークステーション GC とサーバー GC です。</span><span class="sxs-lookup"><span data-stu-id="f7f96-115">The two main flavors of garbage collection are workstation GC and server GC.</span></span> <span data-ttu-id="f7f96-116">2 つの間の相違点について詳しくは、「[ワークステーションとサーバーのガベージ コレクション](../../standard/garbage-collection/workstation-server-gc.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f7f96-116">For more information about differences between the two, see [Workstation and server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span>

<span data-ttu-id="f7f96-117">ガベージ コレクションのサブフレーバーは、バックグラウンドと非同時実行です。</span><span class="sxs-lookup"><span data-stu-id="f7f96-117">The subflavors of garbage collection are background and non-concurrent.</span></span>

<span data-ttu-id="f7f96-118">ガベージ コレクションのフレーバーを選択するには、以下の設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="f7f96-118">Use the following settings to select flavors of garbage collection:</span></span>

- [<span data-ttu-id="f7f96-119">ワークステーションとサーバーの GC</span><span class="sxs-lookup"><span data-stu-id="f7f96-119">Workstation vs. server GC</span></span>](#workstation-vs-server)
- [<span data-ttu-id="f7f96-120">バックグラウンド GC</span><span class="sxs-lookup"><span data-stu-id="f7f96-120">Background GC</span></span>](#background-gc)

### <a name="workstation-vs-server"></a><span data-ttu-id="f7f96-121">ワークステーションとサーバー</span><span class="sxs-lookup"><span data-stu-id="f7f96-121">Workstation vs. server</span></span>

- <span data-ttu-id="f7f96-122">アプリケーションで、ワークステーション ガベージ コレクションとサーバー ガベージ コレクションのどちらを使用するかを構成します。</span><span class="sxs-lookup"><span data-stu-id="f7f96-122">Configures whether the application uses workstation garbage collection or server garbage collection.</span></span>
- <span data-ttu-id="f7f96-123">既定:ワークステーション ガベージ コレクション。</span><span class="sxs-lookup"><span data-stu-id="f7f96-123">Default: Workstation garbage collection.</span></span> <span data-ttu-id="f7f96-124">これは、値を `false` に設定した場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="f7f96-124">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="f7f96-125">設定の名前</span><span class="sxs-lookup"><span data-stu-id="f7f96-125">Setting name</span></span> | <span data-ttu-id="f7f96-126">値</span><span class="sxs-lookup"><span data-stu-id="f7f96-126">Values</span></span> | <span data-ttu-id="f7f96-127">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="f7f96-127">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="f7f96-128">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f7f96-128">**runtimeconfig.json**</span></span> | `System.GC.Server` | <span data-ttu-id="f7f96-129">`false` - ワークステーション</span><span class="sxs-lookup"><span data-stu-id="f7f96-129">`false` - workstation</span></span><br/><span data-ttu-id="f7f96-130">`true` - サーバー</span><span class="sxs-lookup"><span data-stu-id="f7f96-130">`true` - server</span></span> | <span data-ttu-id="f7f96-131">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="f7f96-131">.NET Core 1.0</span></span> |
| <span data-ttu-id="f7f96-132">**MSBuild のプロパティ**</span><span class="sxs-lookup"><span data-stu-id="f7f96-132">**MSBuild property**</span></span> | `ServerGarbageCollection` | <span data-ttu-id="f7f96-133">`false` - ワークステーション</span><span class="sxs-lookup"><span data-stu-id="f7f96-133">`false` - workstation</span></span><br/><span data-ttu-id="f7f96-134">`true` - サーバー</span><span class="sxs-lookup"><span data-stu-id="f7f96-134">`true` - server</span></span> | <span data-ttu-id="f7f96-135">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="f7f96-135">.NET Core 1.0</span></span> |
| <span data-ttu-id="f7f96-136">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="f7f96-136">**Environment variable**</span></span> | `COMPlus_gcServer` | <span data-ttu-id="f7f96-137">`0` - ワークステーション</span><span class="sxs-lookup"><span data-stu-id="f7f96-137">`0` - workstation</span></span><br/><span data-ttu-id="f7f96-138">`1` - サーバー</span><span class="sxs-lookup"><span data-stu-id="f7f96-138">`1` - server</span></span> | <span data-ttu-id="f7f96-139">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="f7f96-139">.NET Core 1.0</span></span> |
| <span data-ttu-id="f7f96-140">**.NET Framework 用の app.config**</span><span class="sxs-lookup"><span data-stu-id="f7f96-140">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="f7f96-141">GCServer</span><span class="sxs-lookup"><span data-stu-id="f7f96-141">GCServer</span></span>](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | <span data-ttu-id="f7f96-142">`false` - ワークステーション</span><span class="sxs-lookup"><span data-stu-id="f7f96-142">`false` - workstation</span></span><br/><span data-ttu-id="f7f96-143">`true` - サーバー</span><span class="sxs-lookup"><span data-stu-id="f7f96-143">`true` - server</span></span> |  |

#### <a name="examples"></a><span data-ttu-id="f7f96-144">使用例</span><span class="sxs-lookup"><span data-stu-id="f7f96-144">Examples</span></span>

<span data-ttu-id="f7f96-145">*runtimeconfig.json* ファイル:</span><span class="sxs-lookup"><span data-stu-id="f7f96-145">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

<span data-ttu-id="f7f96-146">プロジェクト ファイル:</span><span class="sxs-lookup"><span data-stu-id="f7f96-146">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ServerGarbageCollection>true</ServerGarbageCollection>
  </PropertyGroup>

</Project>
```

### <a name="background-gc"></a><span data-ttu-id="f7f96-147">バックグラウンド GC</span><span class="sxs-lookup"><span data-stu-id="f7f96-147">Background GC</span></span>

- <span data-ttu-id="f7f96-148">バックグラウンド (同時実行) ガベージ コレクションを有効にするかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="f7f96-148">Configures whether background (concurrent) garbage collection is enabled.</span></span>
- <span data-ttu-id="f7f96-149">既定:バックグラウンド GC を使用します。</span><span class="sxs-lookup"><span data-stu-id="f7f96-149">Default: Use background GC.</span></span> <span data-ttu-id="f7f96-150">これは、値を `true` に設定した場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="f7f96-150">This is equivalent to setting the value to `true`.</span></span>
- <span data-ttu-id="f7f96-151">詳しくは、「[バックグラウンド ガベージ コレクション](../../standard/garbage-collection/background-gc.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f7f96-151">For more information, see [Background garbage collection](../../standard/garbage-collection/background-gc.md).</span></span>

| | <span data-ttu-id="f7f96-152">設定の名前</span><span class="sxs-lookup"><span data-stu-id="f7f96-152">Setting name</span></span> | <span data-ttu-id="f7f96-153">値</span><span class="sxs-lookup"><span data-stu-id="f7f96-153">Values</span></span> | <span data-ttu-id="f7f96-154">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="f7f96-154">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="f7f96-155">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f7f96-155">**runtimeconfig.json**</span></span> | `System.GC.Concurrent` | <span data-ttu-id="f7f96-156">`true` - バックグラウンド GC</span><span class="sxs-lookup"><span data-stu-id="f7f96-156">`true` - background GC</span></span><br/><span data-ttu-id="f7f96-157">`false` -非同時実行 GC</span><span class="sxs-lookup"><span data-stu-id="f7f96-157">`false` - non-concurrent GC</span></span> | <span data-ttu-id="f7f96-158">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="f7f96-158">.NET Core 1.0</span></span> |
| <span data-ttu-id="f7f96-159">**MSBuild のプロパティ**</span><span class="sxs-lookup"><span data-stu-id="f7f96-159">**MSBuild property**</span></span> | `ConcurrentGarbageCollection` | <span data-ttu-id="f7f96-160">`true` - バックグラウンド GC</span><span class="sxs-lookup"><span data-stu-id="f7f96-160">`true` - background GC</span></span><br/><span data-ttu-id="f7f96-161">`false` -非同時実行 GC</span><span class="sxs-lookup"><span data-stu-id="f7f96-161">`false` - non-concurrent GC</span></span> | <span data-ttu-id="f7f96-162">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="f7f96-162">.NET Core 1.0</span></span> |
| <span data-ttu-id="f7f96-163">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="f7f96-163">**Environment variable**</span></span> | `COMPlus_gcConcurrent` | <span data-ttu-id="f7f96-164">`1` - バックグラウンド GC</span><span class="sxs-lookup"><span data-stu-id="f7f96-164">`1` - background GC</span></span><br/><span data-ttu-id="f7f96-165">`0` -非同時実行 GC</span><span class="sxs-lookup"><span data-stu-id="f7f96-165">`0` - non-concurrent GC</span></span> | <span data-ttu-id="f7f96-166">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="f7f96-166">.NET Core 1.0</span></span> |
| <span data-ttu-id="f7f96-167">**.NET Framework 用の app.config**</span><span class="sxs-lookup"><span data-stu-id="f7f96-167">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="f7f96-168">gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="f7f96-168">gcConcurrent</span></span>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | <span data-ttu-id="f7f96-169">`true` - バックグラウンド GC</span><span class="sxs-lookup"><span data-stu-id="f7f96-169">`true` - background GC</span></span><br/><span data-ttu-id="f7f96-170">`false` -非同時実行 GC</span><span class="sxs-lookup"><span data-stu-id="f7f96-170">`false` - non-concurrent GC</span></span> |  |

#### <a name="examples"></a><span data-ttu-id="f7f96-171">使用例</span><span class="sxs-lookup"><span data-stu-id="f7f96-171">Examples</span></span>

<span data-ttu-id="f7f96-172">*runtimeconfig.json* ファイル:</span><span class="sxs-lookup"><span data-stu-id="f7f96-172">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

<span data-ttu-id="f7f96-173">プロジェクト ファイル:</span><span class="sxs-lookup"><span data-stu-id="f7f96-173">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="manage-resource-usage"></a><span data-ttu-id="f7f96-174">リソース使用量を管理する</span><span class="sxs-lookup"><span data-stu-id="f7f96-174">Manage resource usage</span></span>

<span data-ttu-id="f7f96-175">次の設定を使用して、ガベージ コレクターのメモリとプロセッサの使用量を管理します。</span><span class="sxs-lookup"><span data-stu-id="f7f96-175">Use the following settings to manage the garbage collector's memory and processor usage:</span></span>

- [<span data-ttu-id="f7f96-176">関係付け</span><span class="sxs-lookup"><span data-stu-id="f7f96-176">Affinitize</span></span>](#affinitize)
- [<span data-ttu-id="f7f96-177">関係付けマスク</span><span class="sxs-lookup"><span data-stu-id="f7f96-177">Affinitize mask</span></span>](#affinitize-mask)
- [<span data-ttu-id="f7f96-178">関係付け範囲</span><span class="sxs-lookup"><span data-stu-id="f7f96-178">Affinitize ranges</span></span>](#affinitize-ranges)
- [<span data-ttu-id="f7f96-179">CPU グループ</span><span class="sxs-lookup"><span data-stu-id="f7f96-179">CPU groups</span></span>](#cpu-groups)
- [<span data-ttu-id="f7f96-180">ヒープ数</span><span class="sxs-lookup"><span data-stu-id="f7f96-180">Heap count</span></span>](#heap-count)
- [<span data-ttu-id="f7f96-181">ヒープの制限</span><span class="sxs-lookup"><span data-stu-id="f7f96-181">Heap limit</span></span>](#heap-limit)
- [<span data-ttu-id="f7f96-182">ヒープの制限の割合</span><span class="sxs-lookup"><span data-stu-id="f7f96-182">Heap limit percent</span></span>](#heap-limit-percent)
- [<span data-ttu-id="f7f96-183">使用率の高いメモリの割合</span><span class="sxs-lookup"><span data-stu-id="f7f96-183">High memory percent</span></span>](#high-memory-percent)
- [<span data-ttu-id="f7f96-184">オブジェクトごとのヒープの制限</span><span class="sxs-lookup"><span data-stu-id="f7f96-184">Per-object-heap limits</span></span>](#per-object-heap-limits)
- [<span data-ttu-id="f7f96-185">オブジェクトごとのヒープの制限の割合</span><span class="sxs-lookup"><span data-stu-id="f7f96-185">Per-object-heap limit percents</span></span>](#per-object-heap-limit-percents)
- [<span data-ttu-id="f7f96-186">VM の保持</span><span class="sxs-lookup"><span data-stu-id="f7f96-186">Retain VM</span></span>](#retain-vm)

<span data-ttu-id="f7f96-187">これらの設定のいくつかの詳細については、[ワークステーションおよびサーバー GC 間の妥協点](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/)に関するブログ エントリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7f96-187">For more information about some of these settings, see the [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) blog entry.</span></span>

### <a name="heap-count"></a><span data-ttu-id="f7f96-188">ヒープ数</span><span class="sxs-lookup"><span data-stu-id="f7f96-188">Heap count</span></span>

- <span data-ttu-id="f7f96-189">ガベージ コレクターによって作成されるヒープの数を制限します。</span><span class="sxs-lookup"><span data-stu-id="f7f96-189">Limits the number of heaps created by the garbage collector.</span></span>
- <span data-ttu-id="f7f96-190">サーバー ガベージ コレクションにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="f7f96-190">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="f7f96-191">[GC プロセッサの関係](#affinitize)が有効になっている場合 (既定値)、ヒープ数の設定では、最初の `n` プロセッサに `n` GC ヒープやスレッドを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="f7f96-191">If [GC processor affinity](#affinitize) is enabled, which is the default, the heap count setting affinitizes `n` GC heaps/threads to the first `n` processors.</span></span> <span data-ttu-id="f7f96-192">([関係付けマスク](#affinitize-mask)または[関係付け範囲](#affinitize-ranges)の設定を使用して、関係付けるプロセッサを正確に指定します)。</span><span class="sxs-lookup"><span data-stu-id="f7f96-192">(Use the [affinitize mask](#affinitize-mask) or [affinitize ranges](#affinitize-ranges) settings to specify exactly which processors to affinitize.)</span></span>
- <span data-ttu-id="f7f96-193">[GC プロセッサの関係](#affinitize)が無効になっている場合、この設定によって GC ヒープの数が制限されます。</span><span class="sxs-lookup"><span data-stu-id="f7f96-193">If [GC processor affinity](#affinitize) is disabled, this setting limits the number of GC heaps.</span></span>
- <span data-ttu-id="f7f96-194">詳細については、[GCHeapCount の解説](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks)に関する記述を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7f96-194">For more information, see the [GCHeapCount remarks](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span></span>

| | <span data-ttu-id="f7f96-195">設定の名前</span><span class="sxs-lookup"><span data-stu-id="f7f96-195">Setting name</span></span> | <span data-ttu-id="f7f96-196">値</span><span class="sxs-lookup"><span data-stu-id="f7f96-196">Values</span></span> | <span data-ttu-id="f7f96-197">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="f7f96-197">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="f7f96-198">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f7f96-198">**runtimeconfig.json**</span></span> | `System.GC.HeapCount` | <span data-ttu-id="f7f96-199">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="f7f96-199">*decimal value*</span></span> | <span data-ttu-id="f7f96-200">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="f7f96-200">.NET Core 3.0</span></span> |
| <span data-ttu-id="f7f96-201">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="f7f96-201">**Environment variable**</span></span> | `COMPlus_GCHeapCount` | <span data-ttu-id="f7f96-202">"*16 進値*"</span><span class="sxs-lookup"><span data-stu-id="f7f96-202">*hexadecimal value*</span></span> | <span data-ttu-id="f7f96-203">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="f7f96-203">.NET Core 3.0</span></span> |
| <span data-ttu-id="f7f96-204">**.NET Framework 用の app.config**</span><span class="sxs-lookup"><span data-stu-id="f7f96-204">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="f7f96-205">GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="f7f96-205">GCHeapCount</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | <span data-ttu-id="f7f96-206">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="f7f96-206">*decimal value*</span></span> | <span data-ttu-id="f7f96-207">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="f7f96-207">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="f7f96-208">例:</span><span class="sxs-lookup"><span data-stu-id="f7f96-208">Example:</span></span>

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
> <span data-ttu-id="f7f96-209">*runtimeconfig.json* でオプションを設定する場合は、10 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7f96-209">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="f7f96-210">環境変数としてオプションを設定する場合は、16 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7f96-210">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="f7f96-211">たとえば、ヒープの数を 16 に制限する場合、値は JSON ファイルでは 16、環境変数では 0x10 または 10 になります。</span><span class="sxs-lookup"><span data-stu-id="f7f96-211">For example, to limit the number of heaps to 16, the values would be 16 for the JSON file and 0x10 or 10 for the environment variable.</span></span>

### <a name="affinitize-mask"></a><span data-ttu-id="f7f96-212">関係付けマスク</span><span class="sxs-lookup"><span data-stu-id="f7f96-212">Affinitize mask</span></span>

- <span data-ttu-id="f7f96-213">ガベージ コレクター スレッドで使用する必要がある正確なプロセッサを指定します。</span><span class="sxs-lookup"><span data-stu-id="f7f96-213">Specifies the exact processors that garbage collector threads should use.</span></span>
- <span data-ttu-id="f7f96-214">[GC プロセッサの関係](#affinitize)が無効になっている場合、この設定は無視されます。</span><span class="sxs-lookup"><span data-stu-id="f7f96-214">If [GC processor affinity](#affinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="f7f96-215">サーバー ガベージ コレクションにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="f7f96-215">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="f7f96-216">この値は、プロセスで使用できるプロセッサを定義するビット マスクです。</span><span class="sxs-lookup"><span data-stu-id="f7f96-216">The value is a bit mask that defines the processors that are available to the process.</span></span> <span data-ttu-id="f7f96-217">たとえば、10 進値の 1023 (環境変数を使用する場合は、16 進値の 0x3FF または 3FF) は、バイナリ表記では 0011 1111 1111 となります。</span><span class="sxs-lookup"><span data-stu-id="f7f96-217">For example, a decimal value of 1023 (or a hexadecimal value of 0x3FF or 3FF if you're using the environment variable) is 0011 1111 1111 in binary notation.</span></span> <span data-ttu-id="f7f96-218">これにより、最初の 10 プロセッサが使用されることが指定されます。</span><span class="sxs-lookup"><span data-stu-id="f7f96-218">This specifies that the first 10 processors are to be used.</span></span> <span data-ttu-id="f7f96-219">次の 10 プロセッサ (つまり、10 から 19 プロセッサ) を指定するには、10 進値の 1047552 (または 16 進値の 0xFFC00 または FFC00) を指定します。これは、バイナリ値の 1111 1111 1100 0000 0000 に相当します。</span><span class="sxs-lookup"><span data-stu-id="f7f96-219">To specify the next 10 processors, that is, processors 10-19, specify a decimal value of 1047552 (or a hexadecimal value of 0xFFC00 or FFC00), which is equivalent to a binary value of 1111 1111 1100 0000 0000.</span></span>

| | <span data-ttu-id="f7f96-220">設定の名前</span><span class="sxs-lookup"><span data-stu-id="f7f96-220">Setting name</span></span> | <span data-ttu-id="f7f96-221">値</span><span class="sxs-lookup"><span data-stu-id="f7f96-221">Values</span></span> | <span data-ttu-id="f7f96-222">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="f7f96-222">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="f7f96-223">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f7f96-223">**runtimeconfig.json**</span></span> | `System.GC.HeapAffinitizeMask` | <span data-ttu-id="f7f96-224">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="f7f96-224">*decimal value*</span></span> | <span data-ttu-id="f7f96-225">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="f7f96-225">.NET Core 3.0</span></span> |
| <span data-ttu-id="f7f96-226">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="f7f96-226">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeMask` | <span data-ttu-id="f7f96-227">"*16 進値*"</span><span class="sxs-lookup"><span data-stu-id="f7f96-227">*hexadecimal value*</span></span> | <span data-ttu-id="f7f96-228">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="f7f96-228">.NET Core 3.0</span></span> |
| <span data-ttu-id="f7f96-229">**.NET Framework 用の app.config**</span><span class="sxs-lookup"><span data-stu-id="f7f96-229">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="f7f96-230">GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="f7f96-230">GCHeapAffinitizeMask</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | <span data-ttu-id="f7f96-231">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="f7f96-231">*decimal value*</span></span> | <span data-ttu-id="f7f96-232">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="f7f96-232">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="f7f96-233">例:</span><span class="sxs-lookup"><span data-stu-id="f7f96-233">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="affinitize-ranges"></a><span data-ttu-id="f7f96-234">関係付け範囲</span><span class="sxs-lookup"><span data-stu-id="f7f96-234">Affinitize ranges</span></span>

- <span data-ttu-id="f7f96-235">ガベージ コレクター スレッドに使用するプロセッサのリストを指定します。</span><span class="sxs-lookup"><span data-stu-id="f7f96-235">Specifies the list of processors to use for garbage collector threads.</span></span>
- <span data-ttu-id="f7f96-236">この設定は [System.GC.HeapAffinitizeMask](#affinitize-mask) に似ていますが、64 を超えるプロセッサを指定できる点が異なります。</span><span class="sxs-lookup"><span data-stu-id="f7f96-236">This setting is similar to [System.GC.HeapAffinitizeMask](#affinitize-mask), except it allows you to specify more than 64 processors.</span></span>
- <span data-ttu-id="f7f96-237">Windows オペレーティング システムの場合、プロセッサの番号または範囲の前に、対応する [CPU グループ](/windows/win32/procthread/processor-groups)を付けます。たとえば、"0:1-10,0:12,1:50-52,1:70" となります。</span><span class="sxs-lookup"><span data-stu-id="f7f96-237">For Windows operating systems, prefix the processor number or range with the corresponding [CPU group](/windows/win32/procthread/processor-groups), for example, "0:1-10,0:12,1:50-52,1:70".</span></span>
- <span data-ttu-id="f7f96-238">[GC プロセッサの関係](#affinitize)が無効になっている場合、この設定は無視されます。</span><span class="sxs-lookup"><span data-stu-id="f7f96-238">If [GC processor affinity](#affinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="f7f96-239">サーバー ガベージ コレクションにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="f7f96-239">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="f7f96-240">詳細については、Maoni Stephens のブログの「[CPU が 64 を超えるコンピューター上での GC のための CPU 構成の向上](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7f96-240">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="f7f96-241">設定の名前</span><span class="sxs-lookup"><span data-stu-id="f7f96-241">Setting name</span></span> | <span data-ttu-id="f7f96-242">値</span><span class="sxs-lookup"><span data-stu-id="f7f96-242">Values</span></span> | <span data-ttu-id="f7f96-243">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="f7f96-243">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="f7f96-244">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f7f96-244">**runtimeconfig.json**</span></span> | `System.GC.GCHeapAffinitizeRanges` | <span data-ttu-id="f7f96-245">プロセッサ番号またはプロセッサ番号の範囲のコンマ区切りリスト。</span><span class="sxs-lookup"><span data-stu-id="f7f96-245">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="f7f96-246">Unix の例:"1-10,12,50-52,70"</span><span class="sxs-lookup"><span data-stu-id="f7f96-246">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="f7f96-247">Windows の例:"0:1-10,0:12,1:50-52,1:70"</span><span class="sxs-lookup"><span data-stu-id="f7f96-247">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="f7f96-248">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="f7f96-248">.NET Core 3.0</span></span> |
| <span data-ttu-id="f7f96-249">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="f7f96-249">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeRanges` | <span data-ttu-id="f7f96-250">プロセッサ番号またはプロセッサ番号の範囲のコンマ区切りリスト。</span><span class="sxs-lookup"><span data-stu-id="f7f96-250">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="f7f96-251">Unix の例:"1-10,12,50-52,70"</span><span class="sxs-lookup"><span data-stu-id="f7f96-251">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="f7f96-252">Windows の例:"0:1-10,0:12,1:50-52,1:70"</span><span class="sxs-lookup"><span data-stu-id="f7f96-252">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="f7f96-253">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="f7f96-253">.NET Core 3.0</span></span> |

<span data-ttu-id="f7f96-254">例:</span><span class="sxs-lookup"><span data-stu-id="f7f96-254">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="cpu-groups"></a><span data-ttu-id="f7f96-255">CPU グループ</span><span class="sxs-lookup"><span data-stu-id="f7f96-255">CPU groups</span></span>

- <span data-ttu-id="f7f96-256">ガベージ コレクターで [CPU グループ](/windows/win32/procthread/processor-groups)を使用するかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="f7f96-256">Configures whether the garbage collector uses [CPU groups](/windows/win32/procthread/processor-groups) or not.</span></span>

  <span data-ttu-id="f7f96-257">64 ビットの Windows コンピューターに複数の CPU グループがある (つまり、64 を超えるプロセッサがある) 場合、この要素を有効にすると、すべての CPU グループ全体にガベージ コレクションが拡張されます。</span><span class="sxs-lookup"><span data-stu-id="f7f96-257">When a 64-bit Windows computer has multiple CPU groups, that is, there are more than 64 processors, enabling this element extends garbage collection across all CPU groups.</span></span> <span data-ttu-id="f7f96-258">ガベージ コレクターではすべてのコアを使用し、ヒープを作成して分散させます。</span><span class="sxs-lookup"><span data-stu-id="f7f96-258">The garbage collector uses all cores to create and balance heaps.</span></span>

- <span data-ttu-id="f7f96-259">64 ビット Windows オペレーティング システムのみのサーバー ガベージ コレクションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="f7f96-259">Applies to server garbage collection on 64-bit Windows operation systems only.</span></span>
- <span data-ttu-id="f7f96-260">既定:GC は複数の CPU グループに拡張されません。</span><span class="sxs-lookup"><span data-stu-id="f7f96-260">Default: GC does not extend across CPU groups.</span></span> <span data-ttu-id="f7f96-261">これは、値を `0` に設定した場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="f7f96-261">This is equivalent to setting the value to `0`.</span></span>
- <span data-ttu-id="f7f96-262">詳細については、Maoni Stephens のブログの「[CPU が 64 を超えるコンピューター上での GC のための CPU 構成の向上](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7f96-262">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="f7f96-263">設定の名前</span><span class="sxs-lookup"><span data-stu-id="f7f96-263">Setting name</span></span> | <span data-ttu-id="f7f96-264">値</span><span class="sxs-lookup"><span data-stu-id="f7f96-264">Values</span></span> | <span data-ttu-id="f7f96-265">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="f7f96-265">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="f7f96-266">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f7f96-266">**runtimeconfig.json**</span></span> | `System.GC.CpuGroup` | <span data-ttu-id="f7f96-267">`0` - 無効</span><span class="sxs-lookup"><span data-stu-id="f7f96-267">`0` - disabled</span></span><br/><span data-ttu-id="f7f96-268">`1` - 有効</span><span class="sxs-lookup"><span data-stu-id="f7f96-268">`1` - enabled</span></span> | <span data-ttu-id="f7f96-269">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="f7f96-269">.NET 5.0</span></span> |
| <span data-ttu-id="f7f96-270">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="f7f96-270">**Environment variable**</span></span> | `COMPlus_GCCpuGroup` | <span data-ttu-id="f7f96-271">`0` - 無効</span><span class="sxs-lookup"><span data-stu-id="f7f96-271">`0` - disabled</span></span><br/><span data-ttu-id="f7f96-272">`1` - 有効</span><span class="sxs-lookup"><span data-stu-id="f7f96-272">`1` - enabled</span></span> | <span data-ttu-id="f7f96-273">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="f7f96-273">.NET Core 1.0</span></span> |
| <span data-ttu-id="f7f96-274">**.NET Framework 用の app.config**</span><span class="sxs-lookup"><span data-stu-id="f7f96-274">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="f7f96-275">GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="f7f96-275">GCCpuGroup</span></span>](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | <span data-ttu-id="f7f96-276">`false` - 無効</span><span class="sxs-lookup"><span data-stu-id="f7f96-276">`false` - disabled</span></span><br/><span data-ttu-id="f7f96-277">`true` - 有効</span><span class="sxs-lookup"><span data-stu-id="f7f96-277">`true` - enabled</span></span> |  |

> [!NOTE]
> <span data-ttu-id="f7f96-278">すべての CPU グループ全体にスレッド プールからのスレッドも分散するように共通言語ランタイム (CLR) を構成するには、[Thread_UseAllCpuGroups 要素](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md)オプションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="f7f96-278">To configure the common language runtime (CLR) to also distribute threads from the thread pool across all CPU groups, enable the [Thread_UseAllCpuGroups element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) option.</span></span> <span data-ttu-id="f7f96-279">.NET Core アプリの場合は、`COMPlus_Thread_UseAllCpuGroups` 環境変数の値を `1` に設定することによって、このオプションを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="f7f96-279">For .NET Core apps, you can enable this option by setting the value of the `COMPlus_Thread_UseAllCpuGroups` environment variable to `1`.</span></span>

### <a name="affinitize"></a><span data-ttu-id="f7f96-280">関係付け</span><span class="sxs-lookup"><span data-stu-id="f7f96-280">Affinitize</span></span>

- <span data-ttu-id="f7f96-281">ガベージ コレクション スレッドをプロセッサに "*関係付ける*" かどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f7f96-281">Specifies whether to *affinitize* garbage collection threads with processors.</span></span> <span data-ttu-id="f7f96-282">GC スレッドを関係付けることは、その特定の CPU でのみ実行できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="f7f96-282">To affinitize a GC thread means that it can only run on its specific CPU.</span></span> <span data-ttu-id="f7f96-283">各 GC スレッドに対してヒープが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f7f96-283">A heap is created for each GC thread.</span></span>
- <span data-ttu-id="f7f96-284">サーバー ガベージ コレクションにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="f7f96-284">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="f7f96-285">既定:ガベージ コレクション スレッドをプロセッサに関係付けます。</span><span class="sxs-lookup"><span data-stu-id="f7f96-285">Default: Affinitize garbage collection threads with processors.</span></span> <span data-ttu-id="f7f96-286">これは、値を `false` に設定した場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="f7f96-286">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="f7f96-287">設定の名前</span><span class="sxs-lookup"><span data-stu-id="f7f96-287">Setting name</span></span> | <span data-ttu-id="f7f96-288">値</span><span class="sxs-lookup"><span data-stu-id="f7f96-288">Values</span></span> | <span data-ttu-id="f7f96-289">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="f7f96-289">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="f7f96-290">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f7f96-290">**runtimeconfig.json**</span></span> | `System.GC.NoAffinitize` | <span data-ttu-id="f7f96-291">`false` -関係付ける</span><span class="sxs-lookup"><span data-stu-id="f7f96-291">`false` - affinitize</span></span><br/><span data-ttu-id="f7f96-292">`true` -関係付けない</span><span class="sxs-lookup"><span data-stu-id="f7f96-292">`true` - don't affinitize</span></span> | <span data-ttu-id="f7f96-293">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="f7f96-293">.NET Core 3.0</span></span> |
| <span data-ttu-id="f7f96-294">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="f7f96-294">**Environment variable**</span></span> | `COMPlus_GCNoAffinitize` | <span data-ttu-id="f7f96-295">`0` -関係付ける</span><span class="sxs-lookup"><span data-stu-id="f7f96-295">`0` - affinitize</span></span><br/><span data-ttu-id="f7f96-296">`1` -関係付けない</span><span class="sxs-lookup"><span data-stu-id="f7f96-296">`1` - don't affinitize</span></span> | <span data-ttu-id="f7f96-297">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="f7f96-297">.NET Core 3.0</span></span> |
| <span data-ttu-id="f7f96-298">**.NET Framework 用の app.config**</span><span class="sxs-lookup"><span data-stu-id="f7f96-298">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="f7f96-299">GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="f7f96-299">GCNoAffinitize</span></span>](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | <span data-ttu-id="f7f96-300">`false` -関係付ける</span><span class="sxs-lookup"><span data-stu-id="f7f96-300">`false` - affinitize</span></span><br/><span data-ttu-id="f7f96-301">`true` -関係付けない</span><span class="sxs-lookup"><span data-stu-id="f7f96-301">`true` - don't affinitize</span></span> | <span data-ttu-id="f7f96-302">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="f7f96-302">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="f7f96-303">例:</span><span class="sxs-lookup"><span data-stu-id="f7f96-303">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="heap-limit"></a><span data-ttu-id="f7f96-304">ヒープの制限</span><span class="sxs-lookup"><span data-stu-id="f7f96-304">Heap limit</span></span>

- <span data-ttu-id="f7f96-305">GC ヒープおよび GC ブックキーピングに対して、最大コミット サイズをバイト単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="f7f96-305">Specifies the maximum commit size, in bytes, for the GC heap and GC bookkeeping.</span></span>
- <span data-ttu-id="f7f96-306">この設定は 64 ビットのコンピューターにのみ該当します。</span><span class="sxs-lookup"><span data-stu-id="f7f96-306">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="f7f96-307">[オブジェクトごとのヒープの制限](#per-object-heap-limits)が構成されている場合、この設定は無視されます。</span><span class="sxs-lookup"><span data-stu-id="f7f96-307">This setting is ignored if the [Per-object-heap limits](#per-object-heap-limits) are configured.</span></span>
- <span data-ttu-id="f7f96-308">特定のケースにのみ該当する既定値は、20 MB より大、またはコンテナーのメモリ制限の 75% より大です。</span><span class="sxs-lookup"><span data-stu-id="f7f96-308">The default value, which only applies in certain cases, is the greater of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="f7f96-309">次の場合に既定値は該当します。</span><span class="sxs-lookup"><span data-stu-id="f7f96-309">The default value applies if:</span></span>

  - <span data-ttu-id="f7f96-310">プロセスが、メモリ制限が指定されたコンテナー内で実行されています。</span><span class="sxs-lookup"><span data-stu-id="f7f96-310">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="f7f96-311">[System.GC.HeapHardLimitPercent](#heap-limit-percent) が設定されていません。</span><span class="sxs-lookup"><span data-stu-id="f7f96-311">[System.GC.HeapHardLimitPercent](#heap-limit-percent) is not set.</span></span>

| | <span data-ttu-id="f7f96-312">設定の名前</span><span class="sxs-lookup"><span data-stu-id="f7f96-312">Setting name</span></span> | <span data-ttu-id="f7f96-313">値</span><span class="sxs-lookup"><span data-stu-id="f7f96-313">Values</span></span> | <span data-ttu-id="f7f96-314">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="f7f96-314">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="f7f96-315">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f7f96-315">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimit` | <span data-ttu-id="f7f96-316">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="f7f96-316">*decimal value*</span></span> | <span data-ttu-id="f7f96-317">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="f7f96-317">.NET Core 3.0</span></span> |
| <span data-ttu-id="f7f96-318">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="f7f96-318">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimit` | <span data-ttu-id="f7f96-319">"*16 進値*"</span><span class="sxs-lookup"><span data-stu-id="f7f96-319">*hexadecimal value*</span></span> | <span data-ttu-id="f7f96-320">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="f7f96-320">.NET Core 3.0</span></span> |

<span data-ttu-id="f7f96-321">例:</span><span class="sxs-lookup"><span data-stu-id="f7f96-321">Example:</span></span>

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
> <span data-ttu-id="f7f96-322">*runtimeconfig.json* でオプションを設定する場合は、10 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7f96-322">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="f7f96-323">環境変数としてオプションを設定する場合は、16 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7f96-323">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="f7f96-324">たとえば、ヒープのハード制限を 200 メビバイト (MiB) に指定する場合、値は JSON ファイルでは 209715200、環境変数では 0xC800000 または C800000 になります。</span><span class="sxs-lookup"><span data-stu-id="f7f96-324">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="heap-limit-percent"></a><span data-ttu-id="f7f96-325">ヒープの制限の割合</span><span class="sxs-lookup"><span data-stu-id="f7f96-325">Heap limit percent</span></span>

- <span data-ttu-id="f7f96-326">許容可能な GC ヒープの使用量を、物理メモリ合計に対する割合として指定します。</span><span class="sxs-lookup"><span data-stu-id="f7f96-326">Specifies the allowable GC heap usage as a percentage of the total physical memory.</span></span>
- <span data-ttu-id="f7f96-327">この設定は、[System.GC.HeapHardLimit](#heap-limit) も設定されている場合、無視されます。</span><span class="sxs-lookup"><span data-stu-id="f7f96-327">If [System.GC.HeapHardLimit](#heap-limit) is also set, this setting is ignored.</span></span>
- <span data-ttu-id="f7f96-328">この設定は 64 ビットのコンピューターにのみ該当します。</span><span class="sxs-lookup"><span data-stu-id="f7f96-328">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="f7f96-329">プロセスが、メモリ制限が指定されたコンテナー内で実行されている場合、パーセンテージはそのメモリ制限に対するパーセンテージとして計算されます。</span><span class="sxs-lookup"><span data-stu-id="f7f96-329">If the process is running inside a container that has a specified memory limit, the percentage is calculated as a percentage of that memory limit.</span></span>
- <span data-ttu-id="f7f96-330">[オブジェクトごとのヒープの制限](#per-object-heap-limits)が構成されている場合、この設定は無視されます。</span><span class="sxs-lookup"><span data-stu-id="f7f96-330">This setting is ignored if the [Per-object-heap limits](#per-object-heap-limits) are configured.</span></span>
- <span data-ttu-id="f7f96-331">特定のケースにのみ該当する既定値は、20 MB 未満であるか、コンテナーのメモリ制限の 75% 未満です。</span><span class="sxs-lookup"><span data-stu-id="f7f96-331">The default value, which only applies in certain cases, is the lesser of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="f7f96-332">次の場合に既定値は該当します。</span><span class="sxs-lookup"><span data-stu-id="f7f96-332">The default value applies if:</span></span>

  - <span data-ttu-id="f7f96-333">プロセスが、メモリ制限が指定されたコンテナー内で実行されています。</span><span class="sxs-lookup"><span data-stu-id="f7f96-333">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="f7f96-334">[System.GC.HeapHardLimit](#heap-limit) が設定されていません。</span><span class="sxs-lookup"><span data-stu-id="f7f96-334">[System.GC.HeapHardLimit](#heap-limit) is not set.</span></span>

| | <span data-ttu-id="f7f96-335">設定の名前</span><span class="sxs-lookup"><span data-stu-id="f7f96-335">Setting name</span></span> | <span data-ttu-id="f7f96-336">値</span><span class="sxs-lookup"><span data-stu-id="f7f96-336">Values</span></span> | <span data-ttu-id="f7f96-337">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="f7f96-337">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="f7f96-338">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f7f96-338">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPercent` | <span data-ttu-id="f7f96-339">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="f7f96-339">*decimal value*</span></span> | <span data-ttu-id="f7f96-340">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="f7f96-340">.NET Core 3.0</span></span> |
| <span data-ttu-id="f7f96-341">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="f7f96-341">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimitPercent` | <span data-ttu-id="f7f96-342">"*16 進値*"</span><span class="sxs-lookup"><span data-stu-id="f7f96-342">*hexadecimal value*</span></span> | <span data-ttu-id="f7f96-343">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="f7f96-343">.NET Core 3.0</span></span> |

<span data-ttu-id="f7f96-344">例:</span><span class="sxs-lookup"><span data-stu-id="f7f96-344">Example:</span></span>

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
> <span data-ttu-id="f7f96-345">*runtimeconfig.json* でオプションを設定する場合は、10 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7f96-345">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="f7f96-346">環境変数としてオプションを設定する場合は、16 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7f96-346">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="f7f96-347">たとえば、ヒープの使用量を 30% に制限する場合、値は JSON ファイルでは 30、環境変数では 0x1E または 1E になります。</span><span class="sxs-lookup"><span data-stu-id="f7f96-347">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="per-object-heap-limits"></a><span data-ttu-id="f7f96-348">オブジェクトごとのヒープの制限</span><span class="sxs-lookup"><span data-stu-id="f7f96-348">Per-object-heap limits</span></span>

<span data-ttu-id="f7f96-349">オブジェクトごとのヒープに基づいて、GC で許容されるヒープ使用量を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f7f96-349">You can specify the GC's allowable heap usage on a per-object-heap basis.</span></span> <span data-ttu-id="f7f96-350">ヒープには、大きなオブジェクト ヒープ (LOH)、小さなオブジェクト ヒープ (SOH)、固定オブジェクト ヒープ (POH) があります。</span><span class="sxs-lookup"><span data-stu-id="f7f96-350">The different heaps are the large object heap (LOH), small object heap (SOH), and pinned object heap (POH).</span></span>

- <span data-ttu-id="f7f96-351">`COMPLUS_GCHeapHardLimitSOH`、`COMPLUS_GCHeapHardLimitLOH`、`COMPLUS_GCHeapHardLimitPOH` 設定のいずれかの値を指定する場合、`COMPLUS_GCHeapHardLimitSOH` と `COMPLUS_GCHeapHardLimitLOH` の値も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7f96-351">If you specify a value for any of the `COMPLUS_GCHeapHardLimitSOH`, `COMPLUS_GCHeapHardLimitLOH`, or `COMPLUS_GCHeapHardLimitPOH` settings, you must also specify a value for `COMPLUS_GCHeapHardLimitSOH` and `COMPLUS_GCHeapHardLimitLOH`.</span></span> <span data-ttu-id="f7f96-352">そうしないと、ランタイムでの初期化が失敗します。</span><span class="sxs-lookup"><span data-stu-id="f7f96-352">If you don't, the runtime will fail to initialize.</span></span>
- <span data-ttu-id="f7f96-353">`COMPLUS_GCHeapHardLimitPOH` の既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="f7f96-353">The default value for `COMPLUS_GCHeapHardLimitPOH` is 0.</span></span> <span data-ttu-id="f7f96-354">`COMPLUS_GCHeapHardLimitSOH` と `COMPLUS_GCHeapHardLimitLOH` には既定値はありません。</span><span class="sxs-lookup"><span data-stu-id="f7f96-354">`COMPLUS_GCHeapHardLimitSOH` and `COMPLUS_GCHeapHardLimitLOH` don't have default values.</span></span>

| | <span data-ttu-id="f7f96-355">設定の名前</span><span class="sxs-lookup"><span data-stu-id="f7f96-355">Setting name</span></span> | <span data-ttu-id="f7f96-356">値</span><span class="sxs-lookup"><span data-stu-id="f7f96-356">Values</span></span> | <span data-ttu-id="f7f96-357">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="f7f96-357">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="f7f96-358">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f7f96-358">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitSOH` | <span data-ttu-id="f7f96-359">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="f7f96-359">*decimal value*</span></span> | <span data-ttu-id="f7f96-360">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="f7f96-360">.NET 5.0</span></span> |
| <span data-ttu-id="f7f96-361">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="f7f96-361">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitSOH` | <span data-ttu-id="f7f96-362">"*16 進値*"</span><span class="sxs-lookup"><span data-stu-id="f7f96-362">*hexadecimal value*</span></span> | <span data-ttu-id="f7f96-363">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="f7f96-363">.NET 5.0</span></span> |

| | <span data-ttu-id="f7f96-364">設定の名前</span><span class="sxs-lookup"><span data-stu-id="f7f96-364">Setting name</span></span> | <span data-ttu-id="f7f96-365">値</span><span class="sxs-lookup"><span data-stu-id="f7f96-365">Values</span></span> | <span data-ttu-id="f7f96-366">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="f7f96-366">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="f7f96-367">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f7f96-367">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitLOH` | <span data-ttu-id="f7f96-368">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="f7f96-368">*decimal value*</span></span> | <span data-ttu-id="f7f96-369">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="f7f96-369">.NET 5.0</span></span> |
| <span data-ttu-id="f7f96-370">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="f7f96-370">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitLOH` | <span data-ttu-id="f7f96-371">"*16 進値*"</span><span class="sxs-lookup"><span data-stu-id="f7f96-371">*hexadecimal value*</span></span> | <span data-ttu-id="f7f96-372">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="f7f96-372">.NET 5.0</span></span> |

| | <span data-ttu-id="f7f96-373">設定の名前</span><span class="sxs-lookup"><span data-stu-id="f7f96-373">Setting name</span></span> | <span data-ttu-id="f7f96-374">値</span><span class="sxs-lookup"><span data-stu-id="f7f96-374">Values</span></span> | <span data-ttu-id="f7f96-375">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="f7f96-375">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="f7f96-376">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f7f96-376">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPOH` | <span data-ttu-id="f7f96-377">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="f7f96-377">*decimal value*</span></span> | <span data-ttu-id="f7f96-378">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="f7f96-378">.NET 5.0</span></span> |
| <span data-ttu-id="f7f96-379">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="f7f96-379">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitPOH` | <span data-ttu-id="f7f96-380">"*16 進値*"</span><span class="sxs-lookup"><span data-stu-id="f7f96-380">*hexadecimal value*</span></span> | <span data-ttu-id="f7f96-381">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="f7f96-381">.NET 5.0</span></span> |

> [!TIP]
> <span data-ttu-id="f7f96-382">*runtimeconfig.json* でオプションを設定する場合は、10 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7f96-382">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="f7f96-383">環境変数としてオプションを設定する場合は、16 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7f96-383">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="f7f96-384">たとえば、ヒープのハード制限を 200 メビバイト (MiB) に指定する場合、値は JSON ファイルでは 209715200、環境変数では 0xC800000 または C800000 になります。</span><span class="sxs-lookup"><span data-stu-id="f7f96-384">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="per-object-heap-limit-percents"></a><span data-ttu-id="f7f96-385">オブジェクトごとのヒープの制限の割合</span><span class="sxs-lookup"><span data-stu-id="f7f96-385">Per-object-heap limit percents</span></span>

<span data-ttu-id="f7f96-386">オブジェクトごとのヒープに基づいて、GC で許容されるヒープ使用量を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f7f96-386">You can specify the GC's allowable heap usage on a per-object-heap basis.</span></span> <span data-ttu-id="f7f96-387">ヒープには、大きなオブジェクト ヒープ (LOH)、小さなオブジェクト ヒープ (SOH)、固定オブジェクト ヒープ (POH) があります。</span><span class="sxs-lookup"><span data-stu-id="f7f96-387">The different heaps are the large object heap (LOH), small object heap (SOH), and pinned object heap (POH).</span></span>

- <span data-ttu-id="f7f96-388">`COMPLUS_GCHeapHardLimitSOHPercent`、`COMPLUS_GCHeapHardLimitLOHPercent`、`COMPLUS_GCHeapHardLimitPOHPercent` 設定のいずれかの値を指定する場合、`COMPLUS_GCHeapHardLimitSOHPercent` と `COMPLUS_GCHeapHardLimitLOHPercent` の値も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7f96-388">If you specify a value for any of the `COMPLUS_GCHeapHardLimitSOHPercent`, `COMPLUS_GCHeapHardLimitLOHPercent`, or `COMPLUS_GCHeapHardLimitPOHPercent` settings, you must also specify a value for `COMPLUS_GCHeapHardLimitSOHPercent` and `COMPLUS_GCHeapHardLimitLOHPercent`.</span></span> <span data-ttu-id="f7f96-389">そうしないと、ランタイムでの初期化が失敗します。</span><span class="sxs-lookup"><span data-stu-id="f7f96-389">If you don't, the runtime will fail to initialize.</span></span>
- <span data-ttu-id="f7f96-390">`COMPLUS_GCHeapHardLimitSOH`、`COMPLUS_GCHeapHardLimitLOH`、および `COMPLUS_GCHeapHardLimitPOH` が指定されている場合、これらの設定は無視されます。</span><span class="sxs-lookup"><span data-stu-id="f7f96-390">These settings are ignored if `COMPLUS_GCHeapHardLimitSOH`, `COMPLUS_GCHeapHardLimitLOH`, and `COMPLUS_GCHeapHardLimitPOH` are specified.</span></span>
- <span data-ttu-id="f7f96-391">値 1 は、GC によって合計物理メモリの 1% がそのオブジェクト ヒープに使用されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="f7f96-391">A value of 1 means that GC uses 1% of total physical memory for that object heap.</span></span>
- <span data-ttu-id="f7f96-392">各値は、ゼロより大きく、100 未満である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7f96-392">Each value must be greater than zero and less than 100.</span></span> <span data-ttu-id="f7f96-393">また、3 つのパーセンテージ値の合計は、100 未満である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7f96-393">Additionally, the sum of the three percentage values must be less than 100.</span></span> <span data-ttu-id="f7f96-394">それ以外の場合、ランタイムでの初期化が失敗します。</span><span class="sxs-lookup"><span data-stu-id="f7f96-394">Otherwise, the runtime will fail to initialize.</span></span>

| | <span data-ttu-id="f7f96-395">設定の名前</span><span class="sxs-lookup"><span data-stu-id="f7f96-395">Setting name</span></span> | <span data-ttu-id="f7f96-396">値</span><span class="sxs-lookup"><span data-stu-id="f7f96-396">Values</span></span> | <span data-ttu-id="f7f96-397">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="f7f96-397">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="f7f96-398">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f7f96-398">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitSOHPercent` | <span data-ttu-id="f7f96-399">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="f7f96-399">*decimal value*</span></span> | <span data-ttu-id="f7f96-400">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="f7f96-400">.NET 5.0</span></span> |
| <span data-ttu-id="f7f96-401">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="f7f96-401">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitSOHPercent` | <span data-ttu-id="f7f96-402">"*16 進値*"</span><span class="sxs-lookup"><span data-stu-id="f7f96-402">*hexadecimal value*</span></span> | <span data-ttu-id="f7f96-403">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="f7f96-403">.NET 5.0</span></span> |

| | <span data-ttu-id="f7f96-404">設定の名前</span><span class="sxs-lookup"><span data-stu-id="f7f96-404">Setting name</span></span> | <span data-ttu-id="f7f96-405">値</span><span class="sxs-lookup"><span data-stu-id="f7f96-405">Values</span></span> | <span data-ttu-id="f7f96-406">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="f7f96-406">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="f7f96-407">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f7f96-407">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitLOHPercent` | <span data-ttu-id="f7f96-408">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="f7f96-408">*decimal value*</span></span> | <span data-ttu-id="f7f96-409">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="f7f96-409">.NET 5.0</span></span> |
| <span data-ttu-id="f7f96-410">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="f7f96-410">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitLOHPercent` | <span data-ttu-id="f7f96-411">"*16 進値*"</span><span class="sxs-lookup"><span data-stu-id="f7f96-411">*hexadecimal value*</span></span> | <span data-ttu-id="f7f96-412">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="f7f96-412">.NET 5.0</span></span> |

| | <span data-ttu-id="f7f96-413">設定の名前</span><span class="sxs-lookup"><span data-stu-id="f7f96-413">Setting name</span></span> | <span data-ttu-id="f7f96-414">値</span><span class="sxs-lookup"><span data-stu-id="f7f96-414">Values</span></span> | <span data-ttu-id="f7f96-415">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="f7f96-415">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="f7f96-416">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f7f96-416">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPOHPercent` | <span data-ttu-id="f7f96-417">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="f7f96-417">*decimal value*</span></span> | <span data-ttu-id="f7f96-418">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="f7f96-418">.NET 5.0</span></span> |
| <span data-ttu-id="f7f96-419">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="f7f96-419">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitPOHPercent` | <span data-ttu-id="f7f96-420">"*16 進値*"</span><span class="sxs-lookup"><span data-stu-id="f7f96-420">*hexadecimal value*</span></span> | <span data-ttu-id="f7f96-421">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="f7f96-421">.NET 5.0</span></span> |

> [!TIP]
> <span data-ttu-id="f7f96-422">*runtimeconfig.json* でオプションを設定する場合は、10 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7f96-422">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="f7f96-423">環境変数としてオプションを設定する場合は、16 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7f96-423">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="f7f96-424">たとえば、ヒープの使用量を 30% に制限する場合、値は JSON ファイルでは 30、環境変数では 0x1E または 1E になります。</span><span class="sxs-lookup"><span data-stu-id="f7f96-424">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="high-memory-percent"></a><span data-ttu-id="f7f96-425">使用率の高いメモリの割合</span><span class="sxs-lookup"><span data-stu-id="f7f96-425">High memory percent</span></span>

<span data-ttu-id="f7f96-426">メモリの負荷は、使用されている物理メモリの割合によって示されます。</span><span class="sxs-lookup"><span data-stu-id="f7f96-426">Memory load is indicated by the percentage of physical memory in use.</span></span> <span data-ttu-id="f7f96-427">既定では、物理メモリの負荷が **90%** に達すると、ガベージコレクションがより積極的に完全に実行され、ガベージ コレクションが圧縮されてページングが回避されるようになります。</span><span class="sxs-lookup"><span data-stu-id="f7f96-427">By default, when the physical memory load reaches **90%**, garbage collection becomes more aggressive about doing full, compacting garbage collections to avoid paging.</span></span> <span data-ttu-id="f7f96-428">メモリの負荷が 90% 未満の場合、GC によって、フル ガベージ コレクションに対するバックグラウンド コレクションが優先されます。一時停止は短くなりますが、ヒープ サイズの合計はそれほど小さくなりません。</span><span class="sxs-lookup"><span data-stu-id="f7f96-428">When memory load is below 90%, GC favors background collections for full garbage collections, which have shorter pauses but don't reduce the total heap size by much.</span></span> <span data-ttu-id="f7f96-429">大量のメモリ (80 GB 以上) が搭載されたコンピューターでは、負荷のしきい値は 90% から 97% が既定値です。</span><span class="sxs-lookup"><span data-stu-id="f7f96-429">On machines with a significant amount of memory (80GB or more), the default load threshold is between 90% and 97%.</span></span>

<span data-ttu-id="f7f96-430">使用率の高いメモリの負荷のしきい値は、`COMPlus_GCHighMemPercent` 環境変数、または `System.GC.HighMemoryPercent` JSON 構成設定によって調整できます。</span><span class="sxs-lookup"><span data-stu-id="f7f96-430">The high memory load threshold can be adjusted by the `COMPlus_GCHighMemPercent` environment variable or `System.GC.HighMemoryPercent` JSON configuration setting.</span></span> <span data-ttu-id="f7f96-431">ヒープ サイズを制御する場合は、しきい値の調整を検討してください。</span><span class="sxs-lookup"><span data-stu-id="f7f96-431">Consider adjusting the threshold if you want to control heap size.</span></span> <span data-ttu-id="f7f96-432">たとえば、64 GB のメモリを搭載したコンピューター上で最も優先度の高いプロセスでは、使用可能なメモリが 10% あれば、GC が反応を開始するのが妥当です。</span><span class="sxs-lookup"><span data-stu-id="f7f96-432">For example, for the dominant process on a machine with 64GB of memory, it's reasonable for GC to start reacting when there's 10% of memory available.</span></span> <span data-ttu-id="f7f96-433">ただし、サイズの小さいプロセス、たとえば 1 GB のメモリしか消費しないプロセスでは、使用可能なメモリが 10% 未満でも、GC を快適に実行できます。</span><span class="sxs-lookup"><span data-stu-id="f7f96-433">But for smaller processes, for example, a process that only consumes 1GB of memory, GC can comfortably run with less than 10% of memory available.</span></span> <span data-ttu-id="f7f96-434">このような小さいプロセスでは、しきい値を高く設定することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="f7f96-434">For these smaller processes, consider setting the threshold higher.</span></span> <span data-ttu-id="f7f96-435">一方、大きなプロセスでヒープ サイズを小さくする場合は、使用可能な物理メモリが十分にあったとしても、このしきい値を低くすると、GC がすぐに反応してヒープを圧縮できるため、方法としては効率的です。</span><span class="sxs-lookup"><span data-stu-id="f7f96-435">On the other hand, if you want larger processes to have smaller heap sizes (even when there's plenty of physical memory available), lowering this threshold is an effective way for GC to react sooner to compact the heap down.</span></span>

> [!NOTE]
> <span data-ttu-id="f7f96-436">コンテナーで実行されているプロセスの場合、GC によって、コンテナーの制限に基づいて物理メモリが考慮されます。</span><span class="sxs-lookup"><span data-stu-id="f7f96-436">For processes running in a container, GC considers the physical memory based on the container limit.</span></span>

| | <span data-ttu-id="f7f96-437">設定の名前</span><span class="sxs-lookup"><span data-stu-id="f7f96-437">Setting name</span></span> | <span data-ttu-id="f7f96-438">値</span><span class="sxs-lookup"><span data-stu-id="f7f96-438">Values</span></span> | <span data-ttu-id="f7f96-439">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="f7f96-439">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="f7f96-440">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f7f96-440">**runtimeconfig.json**</span></span> | `System.GC.HighMemoryPercent` | <span data-ttu-id="f7f96-441">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="f7f96-441">*decimal value*</span></span> | <span data-ttu-id="f7f96-442">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="f7f96-442">.NET 5.0</span></span> |
| <span data-ttu-id="f7f96-443">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="f7f96-443">**Environment variable**</span></span> | `COMPlus_GCHighMemPercent` | <span data-ttu-id="f7f96-444">"*16 進値*"</span><span class="sxs-lookup"><span data-stu-id="f7f96-444">*hexadecimal value*</span></span> | |

> [!TIP]
> <span data-ttu-id="f7f96-445">*runtimeconfig.json* でオプションを設定する場合は、10 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7f96-445">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="f7f96-446">環境変数としてオプションを設定する場合は、16 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7f96-446">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="f7f96-447">たとえば、使用率の高いメモリのしきい値を 75% に設定するための値は、JSON ファイルに対しては 75、環境変数に対しては 0x4B または 4B となります。</span><span class="sxs-lookup"><span data-stu-id="f7f96-447">For example, to set the high memory threshold to 75%, the values would be 75 for the JSON file and 0x4B or 4B for the environment variable.</span></span>

### <a name="retain-vm"></a><span data-ttu-id="f7f96-448">VM の保持</span><span class="sxs-lookup"><span data-stu-id="f7f96-448">Retain VM</span></span>

- <span data-ttu-id="f7f96-449">削除する必要があるセグメントを、後で使用するためにスタンバイ リストに配置するか、解放してオペレーティング システム (OS) に戻すかを構成します。</span><span class="sxs-lookup"><span data-stu-id="f7f96-449">Configures whether segments that should be deleted are put on a standby list for future use or are released back to the operating system (OS).</span></span>
- <span data-ttu-id="f7f96-450">既定:セグメントを解放してオペレーティング システムに戻します。</span><span class="sxs-lookup"><span data-stu-id="f7f96-450">Default: Release segments back to the operating system.</span></span> <span data-ttu-id="f7f96-451">これは、値を `false` に設定した場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="f7f96-451">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="f7f96-452">設定の名前</span><span class="sxs-lookup"><span data-stu-id="f7f96-452">Setting name</span></span> | <span data-ttu-id="f7f96-453">値</span><span class="sxs-lookup"><span data-stu-id="f7f96-453">Values</span></span> | <span data-ttu-id="f7f96-454">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="f7f96-454">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="f7f96-455">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f7f96-455">**runtimeconfig.json**</span></span> | `System.GC.RetainVM` | <span data-ttu-id="f7f96-456">`false` -OS に解放する</span><span class="sxs-lookup"><span data-stu-id="f7f96-456">`false` - release to OS</span></span><br/><span data-ttu-id="f7f96-457">`true` - スタンバイに配置する</span><span class="sxs-lookup"><span data-stu-id="f7f96-457">`true` - put on standby</span></span> | <span data-ttu-id="f7f96-458">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="f7f96-458">.NET Core 1.0</span></span> |
| <span data-ttu-id="f7f96-459">**MSBuild のプロパティ**</span><span class="sxs-lookup"><span data-stu-id="f7f96-459">**MSBuild property**</span></span> | `RetainVMGarbageCollection` | <span data-ttu-id="f7f96-460">`false` -OS に解放する</span><span class="sxs-lookup"><span data-stu-id="f7f96-460">`false` - release to OS</span></span><br/><span data-ttu-id="f7f96-461">`true` - スタンバイに配置する</span><span class="sxs-lookup"><span data-stu-id="f7f96-461">`true` - put on standby</span></span> | <span data-ttu-id="f7f96-462">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="f7f96-462">.NET Core 1.0</span></span> |
| <span data-ttu-id="f7f96-463">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="f7f96-463">**Environment variable**</span></span> | `COMPlus_GCRetainVM` | <span data-ttu-id="f7f96-464">`0` -OS に解放する</span><span class="sxs-lookup"><span data-stu-id="f7f96-464">`0` - release to OS</span></span><br/><span data-ttu-id="f7f96-465">`1` - スタンバイに配置する</span><span class="sxs-lookup"><span data-stu-id="f7f96-465">`1` - put on standby</span></span> | <span data-ttu-id="f7f96-466">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="f7f96-466">.NET Core 1.0</span></span> |

#### <a name="examples"></a><span data-ttu-id="f7f96-467">使用例</span><span class="sxs-lookup"><span data-stu-id="f7f96-467">Examples</span></span>

<span data-ttu-id="f7f96-468">*runtimeconfig.json* ファイル:</span><span class="sxs-lookup"><span data-stu-id="f7f96-468">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

<span data-ttu-id="f7f96-469">プロジェクト ファイル:</span><span class="sxs-lookup"><span data-stu-id="f7f96-469">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="large-pages"></a><span data-ttu-id="f7f96-470">大きいページ</span><span class="sxs-lookup"><span data-stu-id="f7f96-470">Large pages</span></span>

- <span data-ttu-id="f7f96-471">ヒープのハード制限が設定されている場合に、大きいページを使用する必要があるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f7f96-471">Specifies whether large pages should be used when a heap hard limit is set.</span></span>
- <span data-ttu-id="f7f96-472">既定:ヒープのハード制限が設定されている場合は、大きいページを使用しません。</span><span class="sxs-lookup"><span data-stu-id="f7f96-472">Default: Don't use large pages when a heap hard limit is set.</span></span> <span data-ttu-id="f7f96-473">これは、値を `0` に設定した場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="f7f96-473">This is equivalent to setting the value to `0`.</span></span>
- <span data-ttu-id="f7f96-474">これは試験段階の設定です。</span><span class="sxs-lookup"><span data-stu-id="f7f96-474">This is an experimental setting.</span></span>

| | <span data-ttu-id="f7f96-475">設定の名前</span><span class="sxs-lookup"><span data-stu-id="f7f96-475">Setting name</span></span> | <span data-ttu-id="f7f96-476">値</span><span class="sxs-lookup"><span data-stu-id="f7f96-476">Values</span></span> | <span data-ttu-id="f7f96-477">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="f7f96-477">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="f7f96-478">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f7f96-478">**runtimeconfig.json**</span></span> | <span data-ttu-id="f7f96-479">N/A</span><span class="sxs-lookup"><span data-stu-id="f7f96-479">N/A</span></span> | <span data-ttu-id="f7f96-480">該当なし</span><span class="sxs-lookup"><span data-stu-id="f7f96-480">N/A</span></span> | <span data-ttu-id="f7f96-481">N/A</span><span class="sxs-lookup"><span data-stu-id="f7f96-481">N/A</span></span> |
| <span data-ttu-id="f7f96-482">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="f7f96-482">**Environment variable**</span></span> | `COMPlus_GCLargePages` | <span data-ttu-id="f7f96-483">`0` - 無効</span><span class="sxs-lookup"><span data-stu-id="f7f96-483">`0` - disabled</span></span><br/><span data-ttu-id="f7f96-484">`1` - 有効</span><span class="sxs-lookup"><span data-stu-id="f7f96-484">`1` - enabled</span></span> | <span data-ttu-id="f7f96-485">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="f7f96-485">.NET Core 3.0</span></span> |

## <a name="allow-large-objects"></a><span data-ttu-id="f7f96-486">大きなオブジェクトを許可する</span><span class="sxs-lookup"><span data-stu-id="f7f96-486">Allow large objects</span></span>

- <span data-ttu-id="f7f96-487">合計サイズが 2 ギガバイト (GB) を超える配列に対して、64 ビット プラットフォームでのガベージ コレクター サポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="f7f96-487">Configures garbage collector support on 64-bit platforms for arrays that are greater than 2 gigabytes (GB) in total size.</span></span>
- <span data-ttu-id="f7f96-488">既定:GC では、2 GB を超える配列がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="f7f96-488">Default: GC supports arrays greater than 2-GB.</span></span> <span data-ttu-id="f7f96-489">これは、値を `1` に設定した場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="f7f96-489">This is equivalent to setting the value to `1`.</span></span>
- <span data-ttu-id="f7f96-490">このオプションは、将来のバージョンの .NET で廃止される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f7f96-490">This option may become obsolete in a future version of .NET.</span></span>

| | <span data-ttu-id="f7f96-491">設定の名前</span><span class="sxs-lookup"><span data-stu-id="f7f96-491">Setting name</span></span> | <span data-ttu-id="f7f96-492">値</span><span class="sxs-lookup"><span data-stu-id="f7f96-492">Values</span></span> | <span data-ttu-id="f7f96-493">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="f7f96-493">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="f7f96-494">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f7f96-494">**runtimeconfig.json**</span></span> | <span data-ttu-id="f7f96-495">N/A</span><span class="sxs-lookup"><span data-stu-id="f7f96-495">N/A</span></span> | <span data-ttu-id="f7f96-496">該当なし</span><span class="sxs-lookup"><span data-stu-id="f7f96-496">N/A</span></span> | <span data-ttu-id="f7f96-497">N/A</span><span class="sxs-lookup"><span data-stu-id="f7f96-497">N/A</span></span> |
| <span data-ttu-id="f7f96-498">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="f7f96-498">**Environment variable**</span></span> | `COMPlus_gcAllowVeryLargeObjects` | <span data-ttu-id="f7f96-499">`1` - 有効</span><span class="sxs-lookup"><span data-stu-id="f7f96-499">`1` - enabled</span></span><br/> <span data-ttu-id="f7f96-500">`0` - 無効</span><span class="sxs-lookup"><span data-stu-id="f7f96-500">`0` - disabled</span></span> | <span data-ttu-id="f7f96-501">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="f7f96-501">.NET Core 1.0</span></span> |
| <span data-ttu-id="f7f96-502">**.NET Framework 用の app.config**</span><span class="sxs-lookup"><span data-stu-id="f7f96-502">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="f7f96-503">gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="f7f96-503">gcAllowVeryLargeObjects</span></span>](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | <span data-ttu-id="f7f96-504">`1` - 有効</span><span class="sxs-lookup"><span data-stu-id="f7f96-504">`1` - enabled</span></span><br/> <span data-ttu-id="f7f96-505">`0` - 無効</span><span class="sxs-lookup"><span data-stu-id="f7f96-505">`0` - disabled</span></span> | <span data-ttu-id="f7f96-506">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="f7f96-506">.NET Framework 4.5</span></span> |

## <a name="large-object-heap-threshold"></a><span data-ttu-id="f7f96-507">大きなオブジェクト ヒープのしきい値</span><span class="sxs-lookup"><span data-stu-id="f7f96-507">Large object heap threshold</span></span>

- <span data-ttu-id="f7f96-508">オブジェクトが大きなオブジェクト ヒープ (LOH) に移る原因となる、しきい値のサイズ (バイト単位) を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7f96-508">Specifies the threshold size, in bytes, that causes objects to go on the large object heap (LOH).</span></span>
- <span data-ttu-id="f7f96-509">既定のしきい値は 85,000 バイトです。</span><span class="sxs-lookup"><span data-stu-id="f7f96-509">The default threshold is 85,000 bytes.</span></span>
- <span data-ttu-id="f7f96-510">指定する値は、既定のしきい値より大きくする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7f96-510">The value you specify must be larger than the default threshold.</span></span>

| | <span data-ttu-id="f7f96-511">設定の名前</span><span class="sxs-lookup"><span data-stu-id="f7f96-511">Setting name</span></span> | <span data-ttu-id="f7f96-512">値</span><span class="sxs-lookup"><span data-stu-id="f7f96-512">Values</span></span> | <span data-ttu-id="f7f96-513">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="f7f96-513">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="f7f96-514">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f7f96-514">**runtimeconfig.json**</span></span> | `System.GC.LOHThreshold` | <span data-ttu-id="f7f96-515">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="f7f96-515">*decimal value*</span></span> | <span data-ttu-id="f7f96-516">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="f7f96-516">.NET Core 1.0</span></span> |
| <span data-ttu-id="f7f96-517">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="f7f96-517">**Environment variable**</span></span> | `COMPlus_GCLOHThreshold` | <span data-ttu-id="f7f96-518">"*16 進値*"</span><span class="sxs-lookup"><span data-stu-id="f7f96-518">*hexadecimal value*</span></span> | <span data-ttu-id="f7f96-519">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="f7f96-519">.NET Core 1.0</span></span> |
| <span data-ttu-id="f7f96-520">**.NET Framework 用の app.config**</span><span class="sxs-lookup"><span data-stu-id="f7f96-520">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="f7f96-521">GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="f7f96-521">GCLOHThreshold</span></span>](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | <span data-ttu-id="f7f96-522">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="f7f96-522">*decimal value*</span></span> | <span data-ttu-id="f7f96-523">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="f7f96-523">.NET Framework 4.8</span></span> |

<span data-ttu-id="f7f96-524">例:</span><span class="sxs-lookup"><span data-stu-id="f7f96-524">Example:</span></span>

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
> <span data-ttu-id="f7f96-525">*runtimeconfig.json* でオプションを設定する場合は、10 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7f96-525">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="f7f96-526">環境変数としてオプションを設定する場合は、16 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7f96-526">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="f7f96-527">たとえば、しきい値のサイズを 120,000 バイトに設定する場合、値は JSON ファイルでは 120000、環境変数では 0x1D4C0 または 1D4C0 になります。</span><span class="sxs-lookup"><span data-stu-id="f7f96-527">For example, to set a threshold size of 120,000 bytes, the values would be 120000 for the JSON file and 0x1D4C0 or 1D4C0 for the environment variable.</span></span>

## <a name="standalone-gc"></a><span data-ttu-id="f7f96-528">スタンドアロン GC</span><span class="sxs-lookup"><span data-stu-id="f7f96-528">Standalone GC</span></span>

- <span data-ttu-id="f7f96-529">ランタイムで読み込む対象となる、ガベージ コレクターを含むライブラリへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="f7f96-529">Specifies a path to the library containing the garbage collector that the runtime intends to load.</span></span>
- <span data-ttu-id="f7f96-530">詳細については、「[スタンドアロン GC ローダーの設計](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7f96-530">For more information, see [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span></span>

| | <span data-ttu-id="f7f96-531">設定の名前</span><span class="sxs-lookup"><span data-stu-id="f7f96-531">Setting name</span></span> | <span data-ttu-id="f7f96-532">値</span><span class="sxs-lookup"><span data-stu-id="f7f96-532">Values</span></span> | <span data-ttu-id="f7f96-533">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="f7f96-533">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="f7f96-534">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f7f96-534">**runtimeconfig.json**</span></span> | <span data-ttu-id="f7f96-535">N/A</span><span class="sxs-lookup"><span data-stu-id="f7f96-535">N/A</span></span> | <span data-ttu-id="f7f96-536">該当なし</span><span class="sxs-lookup"><span data-stu-id="f7f96-536">N/A</span></span> | <span data-ttu-id="f7f96-537">N/A</span><span class="sxs-lookup"><span data-stu-id="f7f96-537">N/A</span></span> |
| <span data-ttu-id="f7f96-538">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="f7f96-538">**Environment variable**</span></span> | `COMPlus_GCName` | <span data-ttu-id="f7f96-539">*string_path*</span><span class="sxs-lookup"><span data-stu-id="f7f96-539">*string_path*</span></span> | <span data-ttu-id="f7f96-540">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="f7f96-540">.NET Core 2.0</span></span> |
