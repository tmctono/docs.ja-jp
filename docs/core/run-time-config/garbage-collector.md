---
title: ガベージ コレクター構成の設定
description: ガベージ コレクターでの .NET Core アプリ用のメモリの管理方法を構成するための、実行時設定について学習します。
ms.date: 01/09/2020
ms.topic: reference
ms.openlocfilehash: dfb641eeda03d1acaa4771bd6253fcb33c4082a6
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/17/2020
ms.locfileid: "81607811"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a><span data-ttu-id="b8717-103">ガベージ コレクションの実行時構成オプション</span><span class="sxs-lookup"><span data-stu-id="b8717-103">Run-time configuration options for garbage collection</span></span>

<span data-ttu-id="b8717-104">このページには、実行時に変更できるガベージ コレクター (GC) の設定に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b8717-104">This page contains information about garbage collector (GC) settings that can be changed at run time.</span></span> <span data-ttu-id="b8717-105">実行中のアプリのピーク時のパフォーマンスを実現しようとしている場合は、これらの設定の使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="b8717-105">If you're trying to achieve peak performance of a running app, consider using these settings.</span></span> <span data-ttu-id="b8717-106">しかし、一般的な状況では、既定値でほとんどのアプリケーションに最適なパフォーマンスが得られます。</span><span class="sxs-lookup"><span data-stu-id="b8717-106">However, the defaults provide optimum performance for most applications in typical situations.</span></span>

<span data-ttu-id="b8717-107">このページでは、設定はグループにまとめられます。</span><span class="sxs-lookup"><span data-stu-id="b8717-107">Settings are arranged into groups on this page.</span></span> <span data-ttu-id="b8717-108">各グループ内の設定は一般的に、特定の結果を得るために相互に組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="b8717-108">The settings within each group are commonly used in conjunction with each other to achieve a specific result.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="b8717-109">これらの設定は、実行中にアプリで動的に変更することもできます。したがって、設定した実行時の設定が上書きされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b8717-109">These settings can also be changed dynamically by the app as it's running, so any run-time settings you set may be overridden.</span></span>
> - <span data-ttu-id="b8717-110">[待機時間レベル](../../standard/garbage-collection/latency.md)などの一部の設定は、通常、デザイン時に API を介してのみ設定されます。</span><span class="sxs-lookup"><span data-stu-id="b8717-110">Some settings, such as [latency level](../../standard/garbage-collection/latency.md), are typically set only through the API at design time.</span></span> <span data-ttu-id="b8717-111">このページでは、このような設定は省略されています。</span><span class="sxs-lookup"><span data-stu-id="b8717-111">Such settings are omitted from this page.</span></span>
> - <span data-ttu-id="b8717-112">数値の場合、*runtimeconfig.json* ファイルの設定には 10 進表記、環境変数の設定には 16 進表記を使用します。</span><span class="sxs-lookup"><span data-stu-id="b8717-112">For number values, use decimal notation for settings in the *runtimeconfig.json* file and hexadecimal notation for environment variable settings.</span></span> <span data-ttu-id="b8717-113">16 進値の場合は、プレフィックス "0x" を付けても付けなくても指定できます。</span><span class="sxs-lookup"><span data-stu-id="b8717-113">For hexadecimal values, you can specify them with or without the "0x" prefix.</span></span>

## <a name="flavors-of-garbage-collection"></a><span data-ttu-id="b8717-114">ガベージ コレクションのフレーバー</span><span class="sxs-lookup"><span data-stu-id="b8717-114">Flavors of garbage collection</span></span>

<span data-ttu-id="b8717-115">ガベージ コレクションの主な 2 つのフレーバーは、ワークステーション GC とサーバー GC です。</span><span class="sxs-lookup"><span data-stu-id="b8717-115">The two main flavors of garbage collection are workstation GC and server GC.</span></span> <span data-ttu-id="b8717-116">2 つの間の相違点について詳しくは、「[ガベージ コレクションの基礎](../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8717-116">For more information about differences between the two, see [Fundamentals of garbage collection](../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection).</span></span>

<span data-ttu-id="b8717-117">ガベージ コレクションのサブフレーバーは、バックグラウンドと非同時実行です。</span><span class="sxs-lookup"><span data-stu-id="b8717-117">The subflavors of garbage collection are background and non-concurrent.</span></span>

<span data-ttu-id="b8717-118">ガベージ コレクションのフレーバーを選択するには、以下の設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="b8717-118">Use the following settings to select flavors of garbage collection:</span></span>

### <a name="systemgcservercomplus_gcserver"></a><span data-ttu-id="b8717-119">System.GC.Server/COMPlus_gcServer</span><span class="sxs-lookup"><span data-stu-id="b8717-119">System.GC.Server/COMPlus_gcServer</span></span>

- <span data-ttu-id="b8717-120">アプリケーションで、ワークステーション ガベージ コレクションとサーバー ガベージ コレクションのどちらを使用するかを構成します。</span><span class="sxs-lookup"><span data-stu-id="b8717-120">Configures whether the application uses workstation garbage collection or server garbage collection.</span></span>
- <span data-ttu-id="b8717-121">既定:ワークステーション ガベージ コレクション (`false`)。</span><span class="sxs-lookup"><span data-stu-id="b8717-121">Default: Workstation garbage collection (`false`).</span></span>

| | <span data-ttu-id="b8717-122">設定の名前</span><span class="sxs-lookup"><span data-stu-id="b8717-122">Setting name</span></span> | <span data-ttu-id="b8717-123">値</span><span class="sxs-lookup"><span data-stu-id="b8717-123">Values</span></span> | <span data-ttu-id="b8717-124">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="b8717-124">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="b8717-125">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="b8717-125">**runtimeconfig.json**</span></span> | `System.GC.Server` | <span data-ttu-id="b8717-126">`false` - ワークステーション</span><span class="sxs-lookup"><span data-stu-id="b8717-126">`false` - workstation</span></span><br/><span data-ttu-id="b8717-127">`true` - サーバー</span><span class="sxs-lookup"><span data-stu-id="b8717-127">`true` - server</span></span> | <span data-ttu-id="b8717-128">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="b8717-128">.NET Core 1.0</span></span> |
| <span data-ttu-id="b8717-129">**MSBuild のプロパティ**</span><span class="sxs-lookup"><span data-stu-id="b8717-129">**MSBuild property**</span></span> | `ServerGarbageCollection` | <span data-ttu-id="b8717-130">`false` - ワークステーション</span><span class="sxs-lookup"><span data-stu-id="b8717-130">`false` - workstation</span></span><br/><span data-ttu-id="b8717-131">`true` - サーバー</span><span class="sxs-lookup"><span data-stu-id="b8717-131">`true` - server</span></span> | <span data-ttu-id="b8717-132">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="b8717-132">.NET Core 1.0</span></span> |
| <span data-ttu-id="b8717-133">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="b8717-133">**Environment variable**</span></span> | `COMPlus_gcServer` | <span data-ttu-id="b8717-134">`0` - ワークステーション</span><span class="sxs-lookup"><span data-stu-id="b8717-134">`0` - workstation</span></span><br/><span data-ttu-id="b8717-135">`1` - サーバー</span><span class="sxs-lookup"><span data-stu-id="b8717-135">`1` - server</span></span> | <span data-ttu-id="b8717-136">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="b8717-136">.NET Core 1.0</span></span> |
| <span data-ttu-id="b8717-137">**.NET Framework 用の app.config**</span><span class="sxs-lookup"><span data-stu-id="b8717-137">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="b8717-138">GCServer</span><span class="sxs-lookup"><span data-stu-id="b8717-138">GCServer</span></span>](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | <span data-ttu-id="b8717-139">`false` - ワークステーション</span><span class="sxs-lookup"><span data-stu-id="b8717-139">`false` - workstation</span></span><br/><span data-ttu-id="b8717-140">`true` - サーバー</span><span class="sxs-lookup"><span data-stu-id="b8717-140">`true` - server</span></span> |  |

### <a name="examples"></a><span data-ttu-id="b8717-141">使用例</span><span class="sxs-lookup"><span data-stu-id="b8717-141">Examples</span></span>

<span data-ttu-id="b8717-142">*runtimeconfig.json* ファイル:</span><span class="sxs-lookup"><span data-stu-id="b8717-142">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

<span data-ttu-id="b8717-143">プロジェクト ファイル:</span><span class="sxs-lookup"><span data-stu-id="b8717-143">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ServerGarbageCollection>true</ServerGarbageCollection>
  </PropertyGroup>

</Project>
```

### <a name="systemgcconcurrentcomplus_gcconcurrent"></a><span data-ttu-id="b8717-144">System.GC.Concurrent/COMPlus_gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="b8717-144">System.GC.Concurrent/COMPlus_gcConcurrent</span></span>

- <span data-ttu-id="b8717-145">バックグラウンド (同時実行) ガベージ コレクションを有効にするかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="b8717-145">Configures whether background (concurrent) garbage collection is enabled.</span></span>
- <span data-ttu-id="b8717-146">既定:有効 (`true`)。</span><span class="sxs-lookup"><span data-stu-id="b8717-146">Default: Enabled (`true`).</span></span>
- <span data-ttu-id="b8717-147">詳細については、[バックグラウンド ガベージ コレクション](../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection)に関する記事と、「[バックグラウンド サーバー ガベージ コレクション](../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8717-147">For more information, see [Background garbage collection](../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection) and [Background server garbage collection](../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection).</span></span>

| | <span data-ttu-id="b8717-148">設定の名前</span><span class="sxs-lookup"><span data-stu-id="b8717-148">Setting name</span></span> | <span data-ttu-id="b8717-149">値</span><span class="sxs-lookup"><span data-stu-id="b8717-149">Values</span></span> | <span data-ttu-id="b8717-150">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="b8717-150">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="b8717-151">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="b8717-151">**runtimeconfig.json**</span></span> | `System.GC.Concurrent` | <span data-ttu-id="b8717-152">`true` - バックグラウンド GC</span><span class="sxs-lookup"><span data-stu-id="b8717-152">`true` - background GC</span></span><br/><span data-ttu-id="b8717-153">`false` -非同時実行 GC</span><span class="sxs-lookup"><span data-stu-id="b8717-153">`false` - non-concurrent GC</span></span> | <span data-ttu-id="b8717-154">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="b8717-154">.NET Core 1.0</span></span> |
| <span data-ttu-id="b8717-155">**MSBuild のプロパティ**</span><span class="sxs-lookup"><span data-stu-id="b8717-155">**MSBuild property**</span></span> | `ConcurrentGarbageCollection` | <span data-ttu-id="b8717-156">`true` - バックグラウンド GC</span><span class="sxs-lookup"><span data-stu-id="b8717-156">`true` - background GC</span></span><br/><span data-ttu-id="b8717-157">`false` -非同時実行 GC</span><span class="sxs-lookup"><span data-stu-id="b8717-157">`false` - non-concurrent GC</span></span> | <span data-ttu-id="b8717-158">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="b8717-158">.NET Core 1.0</span></span> |
| <span data-ttu-id="b8717-159">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="b8717-159">**Environment variable**</span></span> | `COMPlus_gcConcurrent` | <span data-ttu-id="b8717-160">`true` - バックグラウンド GC</span><span class="sxs-lookup"><span data-stu-id="b8717-160">`true` - background GC</span></span><br/><span data-ttu-id="b8717-161">`false` -非同時実行 GC</span><span class="sxs-lookup"><span data-stu-id="b8717-161">`false` - non-concurrent GC</span></span> | <span data-ttu-id="b8717-162">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="b8717-162">.NET Core 1.0</span></span> |
| <span data-ttu-id="b8717-163">**.NET Framework 用の app.config**</span><span class="sxs-lookup"><span data-stu-id="b8717-163">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="b8717-164">gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="b8717-164">gcConcurrent</span></span>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | <span data-ttu-id="b8717-165">`true` - バックグラウンド GC</span><span class="sxs-lookup"><span data-stu-id="b8717-165">`true` - background GC</span></span><br/><span data-ttu-id="b8717-166">`false` -非同時実行 GC</span><span class="sxs-lookup"><span data-stu-id="b8717-166">`false` - non-concurrent GC</span></span> |  |

### <a name="examples"></a><span data-ttu-id="b8717-167">使用例</span><span class="sxs-lookup"><span data-stu-id="b8717-167">Examples</span></span>

<span data-ttu-id="b8717-168">*runtimeconfig.json* ファイル:</span><span class="sxs-lookup"><span data-stu-id="b8717-168">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

<span data-ttu-id="b8717-169">プロジェクト ファイル:</span><span class="sxs-lookup"><span data-stu-id="b8717-169">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="manage-resource-usage"></a><span data-ttu-id="b8717-170">リソース使用量を管理する</span><span class="sxs-lookup"><span data-stu-id="b8717-170">Manage resource usage</span></span>

<span data-ttu-id="b8717-171">このセクションで説明する設定を使用して、ガベージ コレクターのメモリとプロセッサの使用量を管理します。</span><span class="sxs-lookup"><span data-stu-id="b8717-171">Use the settings described in this section to manage the garbage collector's memory and processor usage.</span></span>

<span data-ttu-id="b8717-172">これらの設定のいくつかの詳細については、[ワークステーションおよびサーバー GC 間の妥協点](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/)に関するブログ エントリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8717-172">For more information about some of these settings, see the [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) blog entry.</span></span>

### <a name="systemgcheapcountcomplus_gcheapcount"></a><span data-ttu-id="b8717-173">System.GC.HeapCount/COMPlus_GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="b8717-173">System.GC.HeapCount/COMPlus_GCHeapCount</span></span>

- <span data-ttu-id="b8717-174">ガベージ コレクターによって作成されるヒープの数を制限します。</span><span class="sxs-lookup"><span data-stu-id="b8717-174">Limits the number of heaps created by the garbage collector.</span></span>
- <span data-ttu-id="b8717-175">サーバー ガベージ コレクションにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="b8717-175">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="b8717-176">[GC プロセッサの関係](#systemgcnoaffinitizecomplus_gcnoaffinitize)が有効になっている場合 (既定値)、ヒープ数の設定では、最初の `n` プロセッサに `n` GC ヒープやスレッドを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="b8717-176">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is enabled, which is the default, the heap count setting affinitizes `n` GC heaps/threads to the first `n` processors.</span></span> <span data-ttu-id="b8717-177">([関係付けマスク](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask)または[関係付け範囲](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges)の設定を使用して、関係付けるプロセッサを正確に指定します)。</span><span class="sxs-lookup"><span data-stu-id="b8717-177">(Use the [affinitize mask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) or [affinitize ranges](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges) settings to specify exactly which processors to affinitize.)</span></span>
- <span data-ttu-id="b8717-178">[GC プロセッサの関係](#systemgcnoaffinitizecomplus_gcnoaffinitize)が無効になっている場合、この設定によって GC ヒープの数が制限されます。</span><span class="sxs-lookup"><span data-stu-id="b8717-178">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting limits the number of GC heaps.</span></span>
- <span data-ttu-id="b8717-179">詳細については、[GCHeapCount の解説](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks)に関する記述を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8717-179">For more information, see the [GCHeapCount remarks](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span></span>

| | <span data-ttu-id="b8717-180">設定の名前</span><span class="sxs-lookup"><span data-stu-id="b8717-180">Setting name</span></span> | <span data-ttu-id="b8717-181">値</span><span class="sxs-lookup"><span data-stu-id="b8717-181">Values</span></span> | <span data-ttu-id="b8717-182">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="b8717-182">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="b8717-183">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="b8717-183">**runtimeconfig.json**</span></span> | `System.GC.HeapCount` | <span data-ttu-id="b8717-184">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="b8717-184">*decimal value*</span></span> | <span data-ttu-id="b8717-185">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="b8717-185">.NET Core 3.0</span></span> |
| <span data-ttu-id="b8717-186">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="b8717-186">**Environment variable**</span></span> | `COMPlus_GCHeapCount` | <span data-ttu-id="b8717-187">"*16 進値*"</span><span class="sxs-lookup"><span data-stu-id="b8717-187">*hexadecimal value*</span></span> | <span data-ttu-id="b8717-188">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="b8717-188">.NET Core 3.0</span></span> |
| <span data-ttu-id="b8717-189">**.NET Framework 用の app.config**</span><span class="sxs-lookup"><span data-stu-id="b8717-189">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="b8717-190">GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="b8717-190">GCHeapCount</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | <span data-ttu-id="b8717-191">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="b8717-191">*decimal value*</span></span> | <span data-ttu-id="b8717-192">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="b8717-192">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="b8717-193">例:</span><span class="sxs-lookup"><span data-stu-id="b8717-193">Example:</span></span>

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
> <span data-ttu-id="b8717-194">*runtimeconfig.json* でオプションを設定する場合は、10 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="b8717-194">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="b8717-195">環境変数としてオプションを設定する場合は、16 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="b8717-195">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="b8717-196">たとえば、ヒープの数を 16 に制限する場合、値は JSON ファイルでは 16、環境変数では 0x10 または 10 になります。</span><span class="sxs-lookup"><span data-stu-id="b8717-196">For example, to limit the number of heaps to 16, the values would be 16 for the JSON file and 0x10 or 10 for the environment variable.</span></span>

### <a name="systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask"></a><span data-ttu-id="b8717-197">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="b8717-197">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span></span>

- <span data-ttu-id="b8717-198">ガベージ コレクター スレッドで使用する必要がある正確なプロセッサを指定します。</span><span class="sxs-lookup"><span data-stu-id="b8717-198">Specifies the exact processors that garbage collector threads should use.</span></span>
- <span data-ttu-id="b8717-199">[GC プロセッサの関係](#systemgcnoaffinitizecomplus_gcnoaffinitize)が無効になっている場合、この設定は無視されます。</span><span class="sxs-lookup"><span data-stu-id="b8717-199">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="b8717-200">サーバー ガベージ コレクションにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="b8717-200">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="b8717-201">この値は、プロセスで使用できるプロセッサを定義するビット マスクです。</span><span class="sxs-lookup"><span data-stu-id="b8717-201">The value is a bit mask that defines the processors that are available to the process.</span></span> <span data-ttu-id="b8717-202">たとえば、10 進値の 1023 (環境変数を使用する場合は、16 進値の 0x3FF または 3FF) は、バイナリ表記では 0011 1111 1111 となります。</span><span class="sxs-lookup"><span data-stu-id="b8717-202">For example, a decimal value of 1023 (or a hexadecimal value of 0x3FF or 3FF if you're using the environment variable) is 0011 1111 1111 in binary notation.</span></span> <span data-ttu-id="b8717-203">これにより、最初の 10 プロセッサが使用されることが指定されます。</span><span class="sxs-lookup"><span data-stu-id="b8717-203">This specifies that the first 10 processors are to be used.</span></span> <span data-ttu-id="b8717-204">次の 10 プロセッサ (つまり、10 から 19 プロセッサ) を指定するには、10 進値の 1047552 (または 16 進値の 0xFFC00 または FFC00) を指定します。これは、バイナリ値の 1111 1111 1100 0000 0000 に相当します。</span><span class="sxs-lookup"><span data-stu-id="b8717-204">To specify the next 10 processors, that is, processors 10-19, specify a decimal value of 1047552 (or a hexadecimal value of 0xFFC00 or FFC00), which is equivalent to a binary value of 1111 1111 1100 0000 0000.</span></span>

| | <span data-ttu-id="b8717-205">設定の名前</span><span class="sxs-lookup"><span data-stu-id="b8717-205">Setting name</span></span> | <span data-ttu-id="b8717-206">値</span><span class="sxs-lookup"><span data-stu-id="b8717-206">Values</span></span> | <span data-ttu-id="b8717-207">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="b8717-207">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="b8717-208">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="b8717-208">**runtimeconfig.json**</span></span> | `System.GC.HeapAffinitizeMask` | <span data-ttu-id="b8717-209">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="b8717-209">*decimal value*</span></span> | <span data-ttu-id="b8717-210">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="b8717-210">.NET Core 3.0</span></span> |
| <span data-ttu-id="b8717-211">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="b8717-211">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeMask` | <span data-ttu-id="b8717-212">"*16 進値*"</span><span class="sxs-lookup"><span data-stu-id="b8717-212">*hexadecimal value*</span></span> | <span data-ttu-id="b8717-213">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="b8717-213">.NET Core 3.0</span></span> |
| <span data-ttu-id="b8717-214">**.NET Framework 用の app.config**</span><span class="sxs-lookup"><span data-stu-id="b8717-214">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="b8717-215">GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="b8717-215">GCHeapAffinitizeMask</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | <span data-ttu-id="b8717-216">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="b8717-216">*decimal value*</span></span> | <span data-ttu-id="b8717-217">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="b8717-217">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="b8717-218">例:</span><span class="sxs-lookup"><span data-stu-id="b8717-218">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges"></a><span data-ttu-id="b8717-219">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span><span class="sxs-lookup"><span data-stu-id="b8717-219">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span></span>

- <span data-ttu-id="b8717-220">ガベージ コレクター スレッドに使用するプロセッサのリストを指定します。</span><span class="sxs-lookup"><span data-stu-id="b8717-220">Specifies the list of processors to use for garbage collector threads.</span></span>
- <span data-ttu-id="b8717-221">この設定は [System.GC.HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) に似ていますが、64 を超えるプロセッサを指定できる点が異なります。</span><span class="sxs-lookup"><span data-stu-id="b8717-221">This setting is similar to [System.GC.HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask), except it allows you to specify more than 64 processors.</span></span>
- <span data-ttu-id="b8717-222">Windows オペレーティング システムの場合、プロセッサの番号または範囲の前に、対応する [CPU グループ](/windows/win32/procthread/processor-groups)を付けます。たとえば、"0:1-10,0:12,1:50-52,1:70" となります。</span><span class="sxs-lookup"><span data-stu-id="b8717-222">For Windows operating systems, prefix the processor number or range with the corresponding [CPU group](/windows/win32/procthread/processor-groups), for example, "0:1-10,0:12,1:50-52,1:70".</span></span>
- <span data-ttu-id="b8717-223">[GC プロセッサの関係](#systemgcnoaffinitizecomplus_gcnoaffinitize)が無効になっている場合、この設定は無視されます。</span><span class="sxs-lookup"><span data-stu-id="b8717-223">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="b8717-224">サーバー ガベージ コレクションにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="b8717-224">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="b8717-225">詳細については、Maoni Stephens のブログの「[CPU が 64 を超えるコンピューター上での GC のための CPU 構成の向上](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8717-225">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="b8717-226">設定の名前</span><span class="sxs-lookup"><span data-stu-id="b8717-226">Setting name</span></span> | <span data-ttu-id="b8717-227">値</span><span class="sxs-lookup"><span data-stu-id="b8717-227">Values</span></span> | <span data-ttu-id="b8717-228">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="b8717-228">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="b8717-229">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="b8717-229">**runtimeconfig.json**</span></span> | `System.GC.GCHeapAffinitizeRanges` | <span data-ttu-id="b8717-230">プロセッサ番号またはプロセッサ番号の範囲のコンマ区切りリスト。</span><span class="sxs-lookup"><span data-stu-id="b8717-230">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="b8717-231">Unix の例:"1-10,12,50-52,70"</span><span class="sxs-lookup"><span data-stu-id="b8717-231">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="b8717-232">Windows の例:"0:1-10,0:12,1:50-52,1:70"</span><span class="sxs-lookup"><span data-stu-id="b8717-232">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="b8717-233">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="b8717-233">.NET Core 3.0</span></span> |
| <span data-ttu-id="b8717-234">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="b8717-234">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeRanges` | <span data-ttu-id="b8717-235">プロセッサ番号またはプロセッサ番号の範囲のコンマ区切りリスト。</span><span class="sxs-lookup"><span data-stu-id="b8717-235">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="b8717-236">Unix の例:"1-10,12,50-52,70"</span><span class="sxs-lookup"><span data-stu-id="b8717-236">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="b8717-237">Windows の例:"0:1-10,0:12,1:50-52,1:70"</span><span class="sxs-lookup"><span data-stu-id="b8717-237">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="b8717-238">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="b8717-238">.NET Core 3.0</span></span> |

<span data-ttu-id="b8717-239">例:</span><span class="sxs-lookup"><span data-stu-id="b8717-239">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="complus_gccpugroup"></a><span data-ttu-id="b8717-240">COMPlus_GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="b8717-240">COMPlus_GCCpuGroup</span></span>

- <span data-ttu-id="b8717-241">ガベージ コレクターで [CPU グループ](/windows/win32/procthread/processor-groups)を使用するかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="b8717-241">Configures whether the garbage collector uses [CPU groups](/windows/win32/procthread/processor-groups) or not.</span></span>

  <span data-ttu-id="b8717-242">64 ビットの Windows コンピューターに複数の CPU グループがある (つまり、64 を超えるプロセッサがある) 場合、この要素を有効にすると、すべての CPU グループ全体にガベージ コレクションが拡張されます。</span><span class="sxs-lookup"><span data-stu-id="b8717-242">When a 64-bit Windows computer has multiple CPU groups, that is, there are more than 64 processors, enabling this element extends garbage collection across all CPU groups.</span></span> <span data-ttu-id="b8717-243">ガベージ コレクターではすべてのコアを使用し、ヒープを作成して分散させます。</span><span class="sxs-lookup"><span data-stu-id="b8717-243">The garbage collector uses all cores to create and balance heaps.</span></span>

- <span data-ttu-id="b8717-244">64 ビット Windows オペレーティング システムのみのサーバー ガベージ コレクションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="b8717-244">Applies to server garbage collection on 64-bit Windows operation systems only.</span></span>
- <span data-ttu-id="b8717-245">既定:無効 (`0`)。</span><span class="sxs-lookup"><span data-stu-id="b8717-245">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="b8717-246">詳細については、Maoni Stephens のブログの「[CPU が 64 を超えるコンピューター上での GC のための CPU 構成の向上](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8717-246">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="b8717-247">設定の名前</span><span class="sxs-lookup"><span data-stu-id="b8717-247">Setting name</span></span> | <span data-ttu-id="b8717-248">値</span><span class="sxs-lookup"><span data-stu-id="b8717-248">Values</span></span> | <span data-ttu-id="b8717-249">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="b8717-249">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="b8717-250">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="b8717-250">**runtimeconfig.json**</span></span> | <span data-ttu-id="b8717-251">N/A</span><span class="sxs-lookup"><span data-stu-id="b8717-251">N/A</span></span> | <span data-ttu-id="b8717-252">N/A</span><span class="sxs-lookup"><span data-stu-id="b8717-252">N/A</span></span> | <span data-ttu-id="b8717-253">N/A</span><span class="sxs-lookup"><span data-stu-id="b8717-253">N/A</span></span> |
| <span data-ttu-id="b8717-254">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="b8717-254">**Environment variable**</span></span> | `COMPlus_GCCpuGroup` | <span data-ttu-id="b8717-255">`0` - 無効</span><span class="sxs-lookup"><span data-stu-id="b8717-255">`0` - disabled</span></span><br/><span data-ttu-id="b8717-256">`1` - 有効</span><span class="sxs-lookup"><span data-stu-id="b8717-256">`1` - enabled</span></span> | <span data-ttu-id="b8717-257">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="b8717-257">.NET Core 1.0</span></span> |
| <span data-ttu-id="b8717-258">**.NET Framework 用の app.config**</span><span class="sxs-lookup"><span data-stu-id="b8717-258">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="b8717-259">GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="b8717-259">GCCpuGroup</span></span>](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | <span data-ttu-id="b8717-260">`false` - 無効</span><span class="sxs-lookup"><span data-stu-id="b8717-260">`false` - disabled</span></span><br/><span data-ttu-id="b8717-261">`true` - 有効</span><span class="sxs-lookup"><span data-stu-id="b8717-261">`true` - enabled</span></span> |  |

> [!NOTE]
> <span data-ttu-id="b8717-262">すべての CPU グループ全体にスレッド プールからのスレッドも分散するように共通言語ランタイム (CLR) を構成するには、[Thread_UseAllCpuGroups 要素](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md)オプションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="b8717-262">To configure the common language runtime (CLR) to also distribute threads from the thread pool across all CPU groups, enable the [Thread_UseAllCpuGroups element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) option.</span></span> <span data-ttu-id="b8717-263">.NET Core アプリの場合は、`COMPlus_Thread_UseAllCpuGroups` 環境変数の値を `1` に設定することによって、このオプションを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b8717-263">For .NET Core apps, you can enable this option by setting the value of the `COMPlus_Thread_UseAllCpuGroups` environment variable to `1`.</span></span>

### <a name="systemgcnoaffinitizecomplus_gcnoaffinitize"></a><span data-ttu-id="b8717-264">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="b8717-264">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span></span>

- <span data-ttu-id="b8717-265">ガベージ コレクション スレッドをプロセッサに "*関係付ける*" かどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="b8717-265">Specifies whether to *affinitize* garbage collection threads with processors.</span></span> <span data-ttu-id="b8717-266">GC スレッドを関係付けることは、その特定の CPU でのみ実行できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="b8717-266">To affinitize a GC thread means that it can only run on its specific CPU.</span></span> <span data-ttu-id="b8717-267">各 GC スレッドに対してヒープが作成されます。</span><span class="sxs-lookup"><span data-stu-id="b8717-267">A heap is created for each GC thread.</span></span>
- <span data-ttu-id="b8717-268">サーバー ガベージ コレクションにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="b8717-268">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="b8717-269">既定:ガベージ コレクション スレッドをプロセッサに関係付けます (`false`)。</span><span class="sxs-lookup"><span data-stu-id="b8717-269">Default: Affinitize garbage collection threads with processors (`false`).</span></span>

| | <span data-ttu-id="b8717-270">設定の名前</span><span class="sxs-lookup"><span data-stu-id="b8717-270">Setting name</span></span> | <span data-ttu-id="b8717-271">値</span><span class="sxs-lookup"><span data-stu-id="b8717-271">Values</span></span> | <span data-ttu-id="b8717-272">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="b8717-272">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="b8717-273">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="b8717-273">**runtimeconfig.json**</span></span> | `System.GC.NoAffinitize` | <span data-ttu-id="b8717-274">`false` -関係付ける</span><span class="sxs-lookup"><span data-stu-id="b8717-274">`false` - affinitize</span></span><br/><span data-ttu-id="b8717-275">`true` -関係付けない</span><span class="sxs-lookup"><span data-stu-id="b8717-275">`true` - don't affinitize</span></span> | <span data-ttu-id="b8717-276">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="b8717-276">.NET Core 3.0</span></span> |
| <span data-ttu-id="b8717-277">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="b8717-277">**Environment variable**</span></span> | `COMPlus_GCNoAffinitize` | <span data-ttu-id="b8717-278">`0` -関係付ける</span><span class="sxs-lookup"><span data-stu-id="b8717-278">`0` - affinitize</span></span><br/><span data-ttu-id="b8717-279">`1` -関係付けない</span><span class="sxs-lookup"><span data-stu-id="b8717-279">`1` - don't affinitize</span></span> | <span data-ttu-id="b8717-280">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="b8717-280">.NET Core 3.0</span></span> |
| <span data-ttu-id="b8717-281">**.NET Framework 用の app.config**</span><span class="sxs-lookup"><span data-stu-id="b8717-281">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="b8717-282">GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="b8717-282">GCNoAffinitize</span></span>](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | <span data-ttu-id="b8717-283">`false` -関係付ける</span><span class="sxs-lookup"><span data-stu-id="b8717-283">`false` - affinitize</span></span><br/><span data-ttu-id="b8717-284">`true` -関係付けない</span><span class="sxs-lookup"><span data-stu-id="b8717-284">`true` - don't affinitize</span></span> | <span data-ttu-id="b8717-285">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="b8717-285">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="b8717-286">例:</span><span class="sxs-lookup"><span data-stu-id="b8717-286">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="systemgcheaphardlimitcomplus_gcheaphardlimit"></a><span data-ttu-id="b8717-287">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span><span class="sxs-lookup"><span data-stu-id="b8717-287">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span></span>

- <span data-ttu-id="b8717-288">GC ヒープおよび GC ブックキーピングに対して、最大コミット サイズをバイト単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="b8717-288">Specifies the maximum commit size, in bytes, for the GC heap and GC bookkeeping.</span></span>
- <span data-ttu-id="b8717-289">この設定は 64 ビットのコンピューターにのみ該当します。</span><span class="sxs-lookup"><span data-stu-id="b8717-289">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="b8717-290">特定のケースにのみ該当する既定値は、20 MB 未満であるか、コンテナーのメモリ制限の 75% 未満です。</span><span class="sxs-lookup"><span data-stu-id="b8717-290">The default value, which only applies in certain cases, is the lesser of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="b8717-291">次の場合に既定値は該当します。</span><span class="sxs-lookup"><span data-stu-id="b8717-291">The default value applies if:</span></span>

  - <span data-ttu-id="b8717-292">プロセスが、メモリ制限が指定されたコンテナー内で実行されています。</span><span class="sxs-lookup"><span data-stu-id="b8717-292">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="b8717-293">[System.GC.HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent) が設定されていません。</span><span class="sxs-lookup"><span data-stu-id="b8717-293">[System.GC.HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent) is not set.</span></span>

| | <span data-ttu-id="b8717-294">設定の名前</span><span class="sxs-lookup"><span data-stu-id="b8717-294">Setting name</span></span> | <span data-ttu-id="b8717-295">値</span><span class="sxs-lookup"><span data-stu-id="b8717-295">Values</span></span> | <span data-ttu-id="b8717-296">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="b8717-296">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="b8717-297">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="b8717-297">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimit` | <span data-ttu-id="b8717-298">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="b8717-298">*decimal value*</span></span> | <span data-ttu-id="b8717-299">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="b8717-299">.NET Core 3.0</span></span> |
| <span data-ttu-id="b8717-300">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="b8717-300">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimit` | <span data-ttu-id="b8717-301">"*16 進値*"</span><span class="sxs-lookup"><span data-stu-id="b8717-301">*hexadecimal value*</span></span> | <span data-ttu-id="b8717-302">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="b8717-302">.NET Core 3.0</span></span> |

<span data-ttu-id="b8717-303">例:</span><span class="sxs-lookup"><span data-stu-id="b8717-303">Example:</span></span>

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
> <span data-ttu-id="b8717-304">*runtimeconfig.json* でオプションを設定する場合は、10 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="b8717-304">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="b8717-305">環境変数としてオプションを設定する場合は、16 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="b8717-305">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="b8717-306">たとえば、ヒープのハード制限を 200 メビバイト (MiB) に指定する場合、値は JSON ファイルでは 209715200、環境変数では 0xC800000 または C800000 になります。</span><span class="sxs-lookup"><span data-stu-id="b8717-306">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent"></a><span data-ttu-id="b8717-307">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span><span class="sxs-lookup"><span data-stu-id="b8717-307">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span></span>

- <span data-ttu-id="b8717-308">許容可能な GC ヒープの使用量を、物理メモリ合計に対する割合として指定します。</span><span class="sxs-lookup"><span data-stu-id="b8717-308">Specifies the allowable GC heap usage as a percentage of the total physical memory.</span></span>
- <span data-ttu-id="b8717-309">この設定は、[System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) も設定されている場合、無視されます。</span><span class="sxs-lookup"><span data-stu-id="b8717-309">If [System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) is also set, this setting is ignored.</span></span>
- <span data-ttu-id="b8717-310">この設定は 64 ビットのコンピューターにのみ該当します。</span><span class="sxs-lookup"><span data-stu-id="b8717-310">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="b8717-311">プロセスが、メモリ制限が指定されたコンテナー内で実行されている場合、パーセンテージはそのメモリ制限に対するパーセンテージとして計算されます。</span><span class="sxs-lookup"><span data-stu-id="b8717-311">If the process is running inside a container that has a specified memory limit, the percentage is calculated as a percentage of that memory limit.</span></span>
- <span data-ttu-id="b8717-312">特定のケースにのみ該当する既定値は、20 MB 未満であるか、コンテナーのメモリ制限の 75% 未満です。</span><span class="sxs-lookup"><span data-stu-id="b8717-312">The default value, which only applies in certain cases, is the lesser of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="b8717-313">次の場合に既定値は該当します。</span><span class="sxs-lookup"><span data-stu-id="b8717-313">The default value applies if:</span></span>

  - <span data-ttu-id="b8717-314">プロセスが、メモリ制限が指定されたコンテナー内で実行されています。</span><span class="sxs-lookup"><span data-stu-id="b8717-314">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="b8717-315">[System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) が設定されていません。</span><span class="sxs-lookup"><span data-stu-id="b8717-315">[System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) is not set.</span></span>

| | <span data-ttu-id="b8717-316">設定の名前</span><span class="sxs-lookup"><span data-stu-id="b8717-316">Setting name</span></span> | <span data-ttu-id="b8717-317">値</span><span class="sxs-lookup"><span data-stu-id="b8717-317">Values</span></span> | <span data-ttu-id="b8717-318">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="b8717-318">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="b8717-319">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="b8717-319">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPercent` | <span data-ttu-id="b8717-320">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="b8717-320">*decimal value*</span></span> | <span data-ttu-id="b8717-321">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="b8717-321">.NET Core 3.0</span></span> |
| <span data-ttu-id="b8717-322">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="b8717-322">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimitPercent` | <span data-ttu-id="b8717-323">"*16 進値*"</span><span class="sxs-lookup"><span data-stu-id="b8717-323">*hexadecimal value*</span></span> | <span data-ttu-id="b8717-324">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="b8717-324">.NET Core 3.0</span></span> |

<span data-ttu-id="b8717-325">例:</span><span class="sxs-lookup"><span data-stu-id="b8717-325">Example:</span></span>

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
> <span data-ttu-id="b8717-326">*runtimeconfig.json* でオプションを設定する場合は、10 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="b8717-326">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="b8717-327">環境変数としてオプションを設定する場合は、16 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="b8717-327">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="b8717-328">たとえば、ヒープの使用量を 30% に制限する場合、値は JSON ファイルでは 30、環境変数では 0x1E または 1E になります。</span><span class="sxs-lookup"><span data-stu-id="b8717-328">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="systemgcretainvmcomplus_gcretainvm"></a><span data-ttu-id="b8717-329">System.GC.RetainVM/COMPlus_GCRetainVM</span><span class="sxs-lookup"><span data-stu-id="b8717-329">System.GC.RetainVM/COMPlus_GCRetainVM</span></span>

- <span data-ttu-id="b8717-330">削除する必要があるセグメントを、後で使用するためにスタンバイ リストに配置するか、解放してオペレーティング システム (OS) に戻すかを構成します。</span><span class="sxs-lookup"><span data-stu-id="b8717-330">Configures whether segments that should be deleted are put on a standby list for future use or are released back to the operating system (OS).</span></span>
- <span data-ttu-id="b8717-331">既定:セグメントを解放してオペレーティング システムに戻します (`false`)。</span><span class="sxs-lookup"><span data-stu-id="b8717-331">Default: Release segments back to the operating system (`false`).</span></span>

| | <span data-ttu-id="b8717-332">設定の名前</span><span class="sxs-lookup"><span data-stu-id="b8717-332">Setting name</span></span> | <span data-ttu-id="b8717-333">値</span><span class="sxs-lookup"><span data-stu-id="b8717-333">Values</span></span> | <span data-ttu-id="b8717-334">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="b8717-334">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="b8717-335">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="b8717-335">**runtimeconfig.json**</span></span> | `System.GC.RetainVM` | <span data-ttu-id="b8717-336">`false` -OS に解放する</span><span class="sxs-lookup"><span data-stu-id="b8717-336">`false` - release to OS</span></span><br/><span data-ttu-id="b8717-337">`true` - スタンバイに配置する</span><span class="sxs-lookup"><span data-stu-id="b8717-337">`true` - put on standby</span></span> | <span data-ttu-id="b8717-338">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="b8717-338">.NET Core 1.0</span></span> |
| <span data-ttu-id="b8717-339">**MSBuild のプロパティ**</span><span class="sxs-lookup"><span data-stu-id="b8717-339">**MSBuild property**</span></span> | `RetainVMGarbageCollection` | <span data-ttu-id="b8717-340">`false` -OS に解放する</span><span class="sxs-lookup"><span data-stu-id="b8717-340">`false` - release to OS</span></span><br/><span data-ttu-id="b8717-341">`true` - スタンバイに配置する</span><span class="sxs-lookup"><span data-stu-id="b8717-341">`true` - put on standby</span></span> | <span data-ttu-id="b8717-342">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="b8717-342">.NET Core 1.0</span></span> |
| <span data-ttu-id="b8717-343">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="b8717-343">**Environment variable**</span></span> | `COMPlus_GCRetainVM` | <span data-ttu-id="b8717-344">`0` -OS に解放する</span><span class="sxs-lookup"><span data-stu-id="b8717-344">`0` - release to OS</span></span><br/><span data-ttu-id="b8717-345">`1` - スタンバイに配置する</span><span class="sxs-lookup"><span data-stu-id="b8717-345">`1` - put on standby</span></span> | <span data-ttu-id="b8717-346">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="b8717-346">.NET Core 1.0</span></span> |

### <a name="examples"></a><span data-ttu-id="b8717-347">使用例</span><span class="sxs-lookup"><span data-stu-id="b8717-347">Examples</span></span>

<span data-ttu-id="b8717-348">*runtimeconfig.json* ファイル:</span><span class="sxs-lookup"><span data-stu-id="b8717-348">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

<span data-ttu-id="b8717-349">プロジェクト ファイル:</span><span class="sxs-lookup"><span data-stu-id="b8717-349">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="large-pages"></a><span data-ttu-id="b8717-350">大きいページ</span><span class="sxs-lookup"><span data-stu-id="b8717-350">Large pages</span></span>

### <a name="complus_gclargepages"></a><span data-ttu-id="b8717-351">COMPlus_GCLargePages</span><span class="sxs-lookup"><span data-stu-id="b8717-351">COMPlus_GCLargePages</span></span>

- <span data-ttu-id="b8717-352">ヒープのハード制限が設定されている場合に、大きいページを使用する必要があるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="b8717-352">Specifies whether large pages should be used when a heap hard limit is set.</span></span>
- <span data-ttu-id="b8717-353">既定:無効 (`0`)。</span><span class="sxs-lookup"><span data-stu-id="b8717-353">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="b8717-354">これは試験段階の設定です。</span><span class="sxs-lookup"><span data-stu-id="b8717-354">This is an experimental setting.</span></span>

| | <span data-ttu-id="b8717-355">設定の名前</span><span class="sxs-lookup"><span data-stu-id="b8717-355">Setting name</span></span> | <span data-ttu-id="b8717-356">値</span><span class="sxs-lookup"><span data-stu-id="b8717-356">Values</span></span> | <span data-ttu-id="b8717-357">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="b8717-357">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="b8717-358">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="b8717-358">**runtimeconfig.json**</span></span> | <span data-ttu-id="b8717-359">N/A</span><span class="sxs-lookup"><span data-stu-id="b8717-359">N/A</span></span> | <span data-ttu-id="b8717-360">N/A</span><span class="sxs-lookup"><span data-stu-id="b8717-360">N/A</span></span> | <span data-ttu-id="b8717-361">N/A</span><span class="sxs-lookup"><span data-stu-id="b8717-361">N/A</span></span> |
| <span data-ttu-id="b8717-362">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="b8717-362">**Environment variable**</span></span> | `COMPlus_GCLargePages` | <span data-ttu-id="b8717-363">`0` - 無効</span><span class="sxs-lookup"><span data-stu-id="b8717-363">`0` - disabled</span></span><br/><span data-ttu-id="b8717-364">`1` - 有効</span><span class="sxs-lookup"><span data-stu-id="b8717-364">`1` - enabled</span></span> | <span data-ttu-id="b8717-365">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="b8717-365">.NET Core 3.0</span></span> |

## <a name="large-objects"></a><span data-ttu-id="b8717-366">大きなオブジェクト</span><span class="sxs-lookup"><span data-stu-id="b8717-366">Large objects</span></span>

### <a name="complus_gcallowverylargeobjects"></a><span data-ttu-id="b8717-367">COMPlus_gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="b8717-367">COMPlus_gcAllowVeryLargeObjects</span></span>

- <span data-ttu-id="b8717-368">合計サイズが 2 ギガバイト (GB) を超える配列に対して、64 ビット プラットフォームでのガベージ コレクター サポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="b8717-368">Configures garbage collector support on 64-bit platforms for arrays that are greater than 2 gigabytes (GB) in total size.</span></span>
- <span data-ttu-id="b8717-369">既定:有効 (`1`)。</span><span class="sxs-lookup"><span data-stu-id="b8717-369">Default: Enabled (`1`).</span></span>
- <span data-ttu-id="b8717-370">このオプションは、将来のバージョンの .NET で廃止される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b8717-370">This option may become obsolete in a future version of .NET.</span></span>

| | <span data-ttu-id="b8717-371">設定の名前</span><span class="sxs-lookup"><span data-stu-id="b8717-371">Setting name</span></span> | <span data-ttu-id="b8717-372">値</span><span class="sxs-lookup"><span data-stu-id="b8717-372">Values</span></span> | <span data-ttu-id="b8717-373">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="b8717-373">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="b8717-374">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="b8717-374">**runtimeconfig.json**</span></span> | <span data-ttu-id="b8717-375">N/A</span><span class="sxs-lookup"><span data-stu-id="b8717-375">N/A</span></span> | <span data-ttu-id="b8717-376">N/A</span><span class="sxs-lookup"><span data-stu-id="b8717-376">N/A</span></span> | <span data-ttu-id="b8717-377">N/A</span><span class="sxs-lookup"><span data-stu-id="b8717-377">N/A</span></span> |
| <span data-ttu-id="b8717-378">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="b8717-378">**Environment variable**</span></span> | `COMPlus_gcAllowVeryLargeObjects` | <span data-ttu-id="b8717-379">`1` - 有効</span><span class="sxs-lookup"><span data-stu-id="b8717-379">`1` - enabled</span></span><br/> <span data-ttu-id="b8717-380">`0` - 無効</span><span class="sxs-lookup"><span data-stu-id="b8717-380">`0` - disabled</span></span> | <span data-ttu-id="b8717-381">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="b8717-381">.NET Core 1.0</span></span> |
| <span data-ttu-id="b8717-382">**.NET Framework 用の app.config**</span><span class="sxs-lookup"><span data-stu-id="b8717-382">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="b8717-383">gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="b8717-383">gcAllowVeryLargeObjects</span></span>](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | <span data-ttu-id="b8717-384">`1` - 有効</span><span class="sxs-lookup"><span data-stu-id="b8717-384">`1` - enabled</span></span><br/> <span data-ttu-id="b8717-385">`0` - 無効</span><span class="sxs-lookup"><span data-stu-id="b8717-385">`0` - disabled</span></span> | <span data-ttu-id="b8717-386">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="b8717-386">.NET Framework 4.5</span></span> |

## <a name="large-object-heap-threshold"></a><span data-ttu-id="b8717-387">大きなオブジェクト ヒープのしきい値</span><span class="sxs-lookup"><span data-stu-id="b8717-387">Large object heap threshold</span></span>

### <a name="systemgclohthresholdcomplus_gclohthreshold"></a><span data-ttu-id="b8717-388">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="b8717-388">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span></span>

- <span data-ttu-id="b8717-389">オブジェクトが大きなオブジェクト ヒープ (LOH) に移る原因となる、しきい値のサイズ (バイト単位) を指定します。</span><span class="sxs-lookup"><span data-stu-id="b8717-389">Specifies the threshold size, in bytes, that causes objects to go on the large object heap (LOH).</span></span>
- <span data-ttu-id="b8717-390">既定のしきい値は 85,000 バイトです。</span><span class="sxs-lookup"><span data-stu-id="b8717-390">The default threshold is 85,000 bytes.</span></span>
- <span data-ttu-id="b8717-391">指定する値は、既定のしきい値より大きくする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8717-391">The value you specify must be larger than the default threshold.</span></span>

| | <span data-ttu-id="b8717-392">設定の名前</span><span class="sxs-lookup"><span data-stu-id="b8717-392">Setting name</span></span> | <span data-ttu-id="b8717-393">値</span><span class="sxs-lookup"><span data-stu-id="b8717-393">Values</span></span> | <span data-ttu-id="b8717-394">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="b8717-394">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="b8717-395">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="b8717-395">**runtimeconfig.json**</span></span> | `System.GC.LOHThreshold` | <span data-ttu-id="b8717-396">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="b8717-396">*decimal value*</span></span> | <span data-ttu-id="b8717-397">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="b8717-397">.NET Core 1.0</span></span> |
| <span data-ttu-id="b8717-398">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="b8717-398">**Environment variable**</span></span> | `COMPlus_GCLOHThreshold` | <span data-ttu-id="b8717-399">"*16 進値*"</span><span class="sxs-lookup"><span data-stu-id="b8717-399">*hexadecimal value*</span></span> | <span data-ttu-id="b8717-400">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="b8717-400">.NET Core 1.0</span></span> |
| <span data-ttu-id="b8717-401">**.NET Framework 用の app.config**</span><span class="sxs-lookup"><span data-stu-id="b8717-401">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="b8717-402">GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="b8717-402">GCLOHThreshold</span></span>](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | <span data-ttu-id="b8717-403">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="b8717-403">*decimal value*</span></span> | <span data-ttu-id="b8717-404">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="b8717-404">.NET Framework 4.8</span></span> |

<span data-ttu-id="b8717-405">例:</span><span class="sxs-lookup"><span data-stu-id="b8717-405">Example:</span></span>

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
> <span data-ttu-id="b8717-406">*runtimeconfig.json* でオプションを設定する場合は、10 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="b8717-406">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="b8717-407">環境変数としてオプションを設定する場合は、16 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="b8717-407">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="b8717-408">たとえば、しきい値のサイズを 120,000 バイトに設定する場合、値は JSON ファイルでは 120000、環境変数では 0x1D4C0 または 1D4C0 になります。</span><span class="sxs-lookup"><span data-stu-id="b8717-408">For example, to set a threshold size of 120,000 bytes, the values would be 120000 for the JSON file and 0x1D4C0 or 1D4C0 for the environment variable.</span></span>

## <a name="standalone-gc"></a><span data-ttu-id="b8717-409">スタンドアロン GC</span><span class="sxs-lookup"><span data-stu-id="b8717-409">Standalone GC</span></span>

### <a name="complus_gcname"></a><span data-ttu-id="b8717-410">COMPlus_GCName</span><span class="sxs-lookup"><span data-stu-id="b8717-410">COMPlus_GCName</span></span>

- <span data-ttu-id="b8717-411">ランタイムで読み込む対象となる、ガベージ コレクターを含むライブラリへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="b8717-411">Specifies a path to the library containing the garbage collector that the runtime intends to load.</span></span>
- <span data-ttu-id="b8717-412">詳細については、「[スタンドアロン GC ローダーの設計](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8717-412">For more information, see [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span></span>

| | <span data-ttu-id="b8717-413">設定の名前</span><span class="sxs-lookup"><span data-stu-id="b8717-413">Setting name</span></span> | <span data-ttu-id="b8717-414">値</span><span class="sxs-lookup"><span data-stu-id="b8717-414">Values</span></span> | <span data-ttu-id="b8717-415">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="b8717-415">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="b8717-416">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="b8717-416">**runtimeconfig.json**</span></span> | <span data-ttu-id="b8717-417">N/A</span><span class="sxs-lookup"><span data-stu-id="b8717-417">N/A</span></span> | <span data-ttu-id="b8717-418">N/A</span><span class="sxs-lookup"><span data-stu-id="b8717-418">N/A</span></span> | <span data-ttu-id="b8717-419">N/A</span><span class="sxs-lookup"><span data-stu-id="b8717-419">N/A</span></span> |
| <span data-ttu-id="b8717-420">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="b8717-420">**Environment variable**</span></span> | `COMPlus_GCName` | <span data-ttu-id="b8717-421">*string_path*</span><span class="sxs-lookup"><span data-stu-id="b8717-421">*string_path*</span></span> | <span data-ttu-id="b8717-422">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="b8717-422">.NET Core 2.0</span></span> |
