---
title: ガベージ コレクター構成の設定
description: ガベージ コレクターでの .NET Core アプリ用のメモリの管理方法を構成するための、実行時設定について学習します。
ms.date: 01/09/2020
ms.topic: reference
ms.openlocfilehash: 24e5c47de781e7eed5f76d2c551cac2dce1e8f05
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900097"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a><span data-ttu-id="9636d-103">ガベージ コレクションの実行時構成オプション</span><span class="sxs-lookup"><span data-stu-id="9636d-103">Run-time configuration options for garbage collection</span></span>

<span data-ttu-id="9636d-104">このページには、実行時に変更できるガベージ コレクター (GC) の設定に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9636d-104">This page contains information about garbage collector (GC) settings that can be changed at run time.</span></span> <span data-ttu-id="9636d-105">実行中のアプリのピーク時のパフォーマンスを実現しようとしている場合は、これらの設定の使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="9636d-105">If you're trying to achieve peak performance of a running app, consider using these settings.</span></span> <span data-ttu-id="9636d-106">しかし、一般的な状況では、既定値でほとんどのアプリケーションに最適なパフォーマンスが得られます。</span><span class="sxs-lookup"><span data-stu-id="9636d-106">However, the defaults provide optimum performance for most applications in typical situations.</span></span>

<span data-ttu-id="9636d-107">このページでは、設定はグループにまとめられます。</span><span class="sxs-lookup"><span data-stu-id="9636d-107">Settings are arranged into groups on this page.</span></span> <span data-ttu-id="9636d-108">各グループ内の設定は一般的に、特定の結果を得るために相互に組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="9636d-108">The settings within each group are commonly used in conjunction with each other to achieve a specific result.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="9636d-109">これらの設定は、実行中にアプリで動的に変更することもできます。したがって、設定した実行時の設定が上書きされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9636d-109">These settings can also be changed dynamically by the app as it's running, so any run-time settings you set may be overridden.</span></span>
> - <span data-ttu-id="9636d-110">[待機時間レベル](../../standard/garbage-collection/latency.md)などの一部の設定は、通常、デザイン時に API を介してのみ設定されます。</span><span class="sxs-lookup"><span data-stu-id="9636d-110">Some settings, such as [latency level](../../standard/garbage-collection/latency.md), are typically set only through the API at design time.</span></span> <span data-ttu-id="9636d-111">このページでは、このような設定は省略されています。</span><span class="sxs-lookup"><span data-stu-id="9636d-111">Such settings are omitted from this page.</span></span>
> - <span data-ttu-id="9636d-112">数値の場合、*runtimeconfig.json* ファイルの設定には 10 進表記、環境変数の設定には 16 進表記を使用します。</span><span class="sxs-lookup"><span data-stu-id="9636d-112">For number values, use decimal notation for settings in the *runtimeconfig.json* file and hexadecimal notation for environment variable settings.</span></span> <span data-ttu-id="9636d-113">16 進値の場合は、プレフィックス "0x" を付けても付けなくても指定できます。</span><span class="sxs-lookup"><span data-stu-id="9636d-113">For hexadecimal values, you can specify them with or without the "0x" prefix.</span></span>

## <a name="flavors-of-garbage-collection"></a><span data-ttu-id="9636d-114">ガベージ コレクションのフレーバー</span><span class="sxs-lookup"><span data-stu-id="9636d-114">Flavors of garbage collection</span></span>

<span data-ttu-id="9636d-115">ガベージ コレクションの主な 2 つのフレーバーは、ワークステーション GC とサーバー GC です。</span><span class="sxs-lookup"><span data-stu-id="9636d-115">The two main flavors of garbage collection are workstation GC and server GC.</span></span> <span data-ttu-id="9636d-116">2 つの間の相違点について詳しくは、「[ガベージ コレクションの基礎](../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9636d-116">For more information about differences between the two, see [Fundamentals of garbage collection](../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection).</span></span>

<span data-ttu-id="9636d-117">ガベージ コレクションのサブフレーバーは、バックグラウンドと非同時実行です。</span><span class="sxs-lookup"><span data-stu-id="9636d-117">The subflavors of garbage collection are background and non-concurrent.</span></span>

<span data-ttu-id="9636d-118">ガベージ コレクションのフレーバーを選択するには、以下の設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="9636d-118">Use the following settings to select flavors of garbage collection:</span></span>

### <a name="systemgcservercomplus_gcserver"></a><span data-ttu-id="9636d-119">System.GC.Server/COMPlus_gcServer</span><span class="sxs-lookup"><span data-stu-id="9636d-119">System.GC.Server/COMPlus_gcServer</span></span>

- <span data-ttu-id="9636d-120">アプリケーションで、ワークステーション ガベージ コレクションとサーバー ガベージ コレクションのどちらを使用するかを構成します。</span><span class="sxs-lookup"><span data-stu-id="9636d-120">Configures whether the application uses workstation garbage collection or server garbage collection.</span></span>
- <span data-ttu-id="9636d-121">既定:ワークステーション ガベージ コレクション (`false`)。</span><span class="sxs-lookup"><span data-stu-id="9636d-121">Default: Workstation garbage collection (`false`).</span></span>

| | <span data-ttu-id="9636d-122">設定の名前</span><span class="sxs-lookup"><span data-stu-id="9636d-122">Setting name</span></span> | <span data-ttu-id="9636d-123">値</span><span class="sxs-lookup"><span data-stu-id="9636d-123">Values</span></span> | <span data-ttu-id="9636d-124">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="9636d-124">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9636d-125">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9636d-125">**runtimeconfig.json**</span></span> | `System.GC.Server` | <span data-ttu-id="9636d-126">`false` - ワークステーション</span><span class="sxs-lookup"><span data-stu-id="9636d-126">`false` - workstation</span></span><br/><span data-ttu-id="9636d-127">`true` - サーバー</span><span class="sxs-lookup"><span data-stu-id="9636d-127">`true` - server</span></span> | <span data-ttu-id="9636d-128">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="9636d-128">.NET Core 1.0</span></span> |
| <span data-ttu-id="9636d-129">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="9636d-129">**Environment variable**</span></span> | `COMPlus_gcServer` | <span data-ttu-id="9636d-130">`0` - ワークステーション</span><span class="sxs-lookup"><span data-stu-id="9636d-130">`0` - workstation</span></span><br/><span data-ttu-id="9636d-131">`1` - サーバー</span><span class="sxs-lookup"><span data-stu-id="9636d-131">`1` - server</span></span> | <span data-ttu-id="9636d-132">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="9636d-132">.NET Core 1.0</span></span> |
| <span data-ttu-id="9636d-133">**.NET Framework 用の app.config**</span><span class="sxs-lookup"><span data-stu-id="9636d-133">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="9636d-134">GCServer</span><span class="sxs-lookup"><span data-stu-id="9636d-134">GCServer</span></span>](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | <span data-ttu-id="9636d-135">`false` - ワークステーション</span><span class="sxs-lookup"><span data-stu-id="9636d-135">`false` - workstation</span></span><br/><span data-ttu-id="9636d-136">`true` - サーバー</span><span class="sxs-lookup"><span data-stu-id="9636d-136">`true` - server</span></span> |  |

<span data-ttu-id="9636d-137">例:</span><span class="sxs-lookup"><span data-stu-id="9636d-137">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

### <a name="systemgcconcurrentcomplus_gcconcurrent"></a><span data-ttu-id="9636d-138">System.GC.Concurrent/COMPlus_gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="9636d-138">System.GC.Concurrent/COMPlus_gcConcurrent</span></span>

- <span data-ttu-id="9636d-139">バックグラウンド (同時実行) ガベージ コレクションを有効にするかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="9636d-139">Configures whether background (concurrent) garbage collection is enabled.</span></span>
- <span data-ttu-id="9636d-140">既定:有効 (`true`)。</span><span class="sxs-lookup"><span data-stu-id="9636d-140">Default: Enabled (`true`).</span></span>
- <span data-ttu-id="9636d-141">詳細については、[バックグラウンド ガベージ コレクション](../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection)に関する記事と、「[バックグラウンド サーバー ガベージ コレクション](../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9636d-141">For more information, see [Background garbage collection](../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection) and [Background server garbage collection](../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection).</span></span>

| | <span data-ttu-id="9636d-142">設定の名前</span><span class="sxs-lookup"><span data-stu-id="9636d-142">Setting name</span></span> | <span data-ttu-id="9636d-143">値</span><span class="sxs-lookup"><span data-stu-id="9636d-143">Values</span></span> | <span data-ttu-id="9636d-144">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="9636d-144">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9636d-145">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9636d-145">**runtimeconfig.json**</span></span> | `System.GC.Concurrent` | <span data-ttu-id="9636d-146">`true` - バックグラウンド GC</span><span class="sxs-lookup"><span data-stu-id="9636d-146">`true` - background GC</span></span><br/><span data-ttu-id="9636d-147">`false` -非同時実行 GC</span><span class="sxs-lookup"><span data-stu-id="9636d-147">`false` - non-concurrent GC</span></span> | <span data-ttu-id="9636d-148">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="9636d-148">.NET Core 1.0</span></span> |
| <span data-ttu-id="9636d-149">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="9636d-149">**Environment variable**</span></span> | `COMPlus_gcConcurrent` | <span data-ttu-id="9636d-150">`true` - バックグラウンド GC</span><span class="sxs-lookup"><span data-stu-id="9636d-150">`true` - background GC</span></span><br/><span data-ttu-id="9636d-151">`false` -非同時実行 GC</span><span class="sxs-lookup"><span data-stu-id="9636d-151">`false` - non-concurrent GC</span></span> | <span data-ttu-id="9636d-152">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="9636d-152">.NET Core 1.0</span></span> |
| <span data-ttu-id="9636d-153">**.NET Framework 用の app.config**</span><span class="sxs-lookup"><span data-stu-id="9636d-153">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="9636d-154">gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="9636d-154">gcConcurrent</span></span>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | <span data-ttu-id="9636d-155">`true` - バックグラウンド GC</span><span class="sxs-lookup"><span data-stu-id="9636d-155">`true` - background GC</span></span><br/><span data-ttu-id="9636d-156">`false` -非同時実行 GC</span><span class="sxs-lookup"><span data-stu-id="9636d-156">`false` - non-concurrent GC</span></span> |  |

<span data-ttu-id="9636d-157">例:</span><span class="sxs-lookup"><span data-stu-id="9636d-157">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

## <a name="manage-resource-usage"></a><span data-ttu-id="9636d-158">リソース使用量を管理する</span><span class="sxs-lookup"><span data-stu-id="9636d-158">Manage resource usage</span></span>

<span data-ttu-id="9636d-159">このセクションで説明する設定を使用して、ガベージ コレクターのメモリとプロセッサの使用量を管理します。</span><span class="sxs-lookup"><span data-stu-id="9636d-159">Use the settings described in this section to manage the garbage collector's memory and processor usage.</span></span>

<span data-ttu-id="9636d-160">これらの設定のいくつかの詳細については、[ワークステーションおよびサーバー GC 間の妥協点](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/)に関するブログ エントリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9636d-160">For more information about some of these settings, see the [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) blog entry.</span></span>

### <a name="systemgcheapcountcomplus_gcheapcount"></a><span data-ttu-id="9636d-161">System.GC.HeapCount/COMPlus_GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="9636d-161">System.GC.HeapCount/COMPlus_GCHeapCount</span></span>

- <span data-ttu-id="9636d-162">ガベージ コレクターによって作成されるヒープの数を制限します。</span><span class="sxs-lookup"><span data-stu-id="9636d-162">Limits the number of heaps created by the garbage collector.</span></span>
- <span data-ttu-id="9636d-163">サーバー ガベージ コレクションにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="9636d-163">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="9636d-164">GC プロセッサの関係が有効になっている場合 (既定値)、ヒープ数の設定では、最初の `n` プロセッサに `n` GC ヒープやスレッドを関連付けます</span><span class="sxs-lookup"><span data-stu-id="9636d-164">If GC processor affinity is enabled, which is the default, the heap count setting affinitizes `n` GC heaps/threads to the first `n` processors.</span></span> <span data-ttu-id="9636d-165">(関係付けマスクまたは関係付け範囲の設定を使用して、関係付けるプロセッサを正確に指定します)。</span><span class="sxs-lookup"><span data-stu-id="9636d-165">(Use the affinitize mask or affinitize ranges settings to specify exactly which processors to affinitize.)</span></span>
- <span data-ttu-id="9636d-166">GC プロセッサの関係が無効になっている場合、この設定によって GC ヒープの数が制限されます。</span><span class="sxs-lookup"><span data-stu-id="9636d-166">If GC processor affinity is disabled, this setting limits the number of GC heaps.</span></span>
- <span data-ttu-id="9636d-167">詳細については、[GCHeapCount の解説](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks)に関する記述を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9636d-167">For more information, see the [GCHeapCount remarks](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span></span>

| | <span data-ttu-id="9636d-168">設定の名前</span><span class="sxs-lookup"><span data-stu-id="9636d-168">Setting name</span></span> | <span data-ttu-id="9636d-169">値</span><span class="sxs-lookup"><span data-stu-id="9636d-169">Values</span></span> | <span data-ttu-id="9636d-170">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="9636d-170">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9636d-171">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9636d-171">**runtimeconfig.json**</span></span> | `System.GC.HeapCount` | <span data-ttu-id="9636d-172">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="9636d-172">*decimal value*</span></span> | <span data-ttu-id="9636d-173">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9636d-173">.NET Core 3.0</span></span> |
| <span data-ttu-id="9636d-174">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="9636d-174">**Environment variable**</span></span> | `COMPlus_GCHeapCount` | <span data-ttu-id="9636d-175">"*16 進値*"</span><span class="sxs-lookup"><span data-stu-id="9636d-175">*hexadecimal value*</span></span> | <span data-ttu-id="9636d-176">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9636d-176">.NET Core 3.0</span></span> |
| <span data-ttu-id="9636d-177">**.NET Framework 用の app.config**</span><span class="sxs-lookup"><span data-stu-id="9636d-177">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="9636d-178">GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="9636d-178">GCHeapCount</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | <span data-ttu-id="9636d-179">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="9636d-179">*decimal value*</span></span> | <span data-ttu-id="9636d-180">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="9636d-180">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="9636d-181">例:</span><span class="sxs-lookup"><span data-stu-id="9636d-181">Example:</span></span>

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
> <span data-ttu-id="9636d-182">*runtimeconfig.json* でオプションを設定する場合は、10 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="9636d-182">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="9636d-183">環境変数としてオプションを設定する場合は、16 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="9636d-183">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="9636d-184">たとえば、ヒープの数を 16 に制限する場合、値は JSON ファイルでは 16、環境変数では 0x10 または 10 になります。</span><span class="sxs-lookup"><span data-stu-id="9636d-184">For example, to limit the number of heaps to 16, the values would be 16 for the JSON file and 0x10 or 10 for the environment variable.</span></span>

### <a name="systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask"></a><span data-ttu-id="9636d-185">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="9636d-185">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span></span>

- <span data-ttu-id="9636d-186">ガベージ コレクター スレッドで使用する必要がある正確なプロセッサを指定します。</span><span class="sxs-lookup"><span data-stu-id="9636d-186">Specifies the exact processors that garbage collector threads should use.</span></span>
- <span data-ttu-id="9636d-187">`System.GC.NoAffinitize` を `true` に設定してプロセッサの関係を無効にした場合、この設定は無視されます。</span><span class="sxs-lookup"><span data-stu-id="9636d-187">If processor affinity is disabled by setting `System.GC.NoAffinitize` to `true`, this setting is ignored.</span></span>
- <span data-ttu-id="9636d-188">サーバー ガベージ コレクションにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="9636d-188">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="9636d-189">この値は、プロセスで使用できるプロセッサを定義するビット マスクです。</span><span class="sxs-lookup"><span data-stu-id="9636d-189">The value is a bit mask that defines the processors that are available to the process.</span></span> <span data-ttu-id="9636d-190">たとえば、10 進値の 1023 (環境変数を使用する場合は、16 進値の 0x3FF または 3FF) は、バイナリ表記では 0011 1111 1111 となります。</span><span class="sxs-lookup"><span data-stu-id="9636d-190">For example, a decimal value of 1023 (or a hexadecimal value of 0x3FF or 3FF if you're using the environment variable) is 0011 1111 1111 in binary notation.</span></span> <span data-ttu-id="9636d-191">これにより、最初の 10 プロセッサが使用されることが指定されます。</span><span class="sxs-lookup"><span data-stu-id="9636d-191">This specifies that the first 10 processors are to be used.</span></span> <span data-ttu-id="9636d-192">次の 10 プロセッサ (つまり、10 から 19 プロセッサ) を指定するには、10 進値の 1047552 (または 16 進値の 0xFFC00 または FFC00) を指定します。これは、バイナリ値の 1111 1111 1100 0000 0000 に相当します。</span><span class="sxs-lookup"><span data-stu-id="9636d-192">To specify the next 10 processors, that is, processors 10-19, specify a decimal value of 1047552 (or a hexadecimal value of 0xFFC00 or FFC00), which is equivalent to a binary value of 1111 1111 1100 0000 0000.</span></span>

| | <span data-ttu-id="9636d-193">設定の名前</span><span class="sxs-lookup"><span data-stu-id="9636d-193">Setting name</span></span> | <span data-ttu-id="9636d-194">値</span><span class="sxs-lookup"><span data-stu-id="9636d-194">Values</span></span> | <span data-ttu-id="9636d-195">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="9636d-195">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9636d-196">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9636d-196">**runtimeconfig.json**</span></span> | `System.GC.HeapAffinitizeMask` | <span data-ttu-id="9636d-197">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="9636d-197">*decimal value*</span></span> | <span data-ttu-id="9636d-198">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9636d-198">.NET Core 3.0</span></span> |
| <span data-ttu-id="9636d-199">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="9636d-199">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeMask` | <span data-ttu-id="9636d-200">"*16 進値*"</span><span class="sxs-lookup"><span data-stu-id="9636d-200">*hexadecimal value*</span></span> | <span data-ttu-id="9636d-201">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9636d-201">.NET Core 3.0</span></span> |
| <span data-ttu-id="9636d-202">**.NET Framework 用の app.config**</span><span class="sxs-lookup"><span data-stu-id="9636d-202">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="9636d-203">GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="9636d-203">GCHeapAffinitizeMask</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | <span data-ttu-id="9636d-204">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="9636d-204">*decimal value*</span></span> | <span data-ttu-id="9636d-205">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="9636d-205">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="9636d-206">例:</span><span class="sxs-lookup"><span data-stu-id="9636d-206">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges"></a><span data-ttu-id="9636d-207">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span><span class="sxs-lookup"><span data-stu-id="9636d-207">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span></span>

- <span data-ttu-id="9636d-208">ガベージ コレクター スレッドに使用するプロセッサのリストを指定します。</span><span class="sxs-lookup"><span data-stu-id="9636d-208">Specifies the list of processors to use for garbage collector threads.</span></span>
- <span data-ttu-id="9636d-209">この設定は `System.GC.HeapAffinitizeMask` に似ていますが、64 を超えるプロセッサを指定できる点が異なります。</span><span class="sxs-lookup"><span data-stu-id="9636d-209">This setting is similar to `System.GC.HeapAffinitizeMask`, except it allows you to specify more than 64 processors.</span></span>
- <span data-ttu-id="9636d-210">Windows オペレーティング システムの場合、プロセッサの番号または範囲の前に、対応する [CPU グループ](/windows/win32/procthread/processor-groups)を付けます。たとえば、"0:1-10,0:12,1:50-52,1:70" となります。</span><span class="sxs-lookup"><span data-stu-id="9636d-210">For Windows operating systems, prefix the processor number or range with the corresponding [CPU group](/windows/win32/procthread/processor-groups), for example, "0:1-10,0:12,1:50-52,1:70".</span></span>
- <span data-ttu-id="9636d-211">`System.GC.NoAffinitize` を `true` に設定してプロセッサの関係を無効にした場合、この設定は無視されます。</span><span class="sxs-lookup"><span data-stu-id="9636d-211">If processor affinity is disabled by setting `System.GC.NoAffinitize` to `true`, this setting is ignored.</span></span>
- <span data-ttu-id="9636d-212">サーバー ガベージ コレクションにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="9636d-212">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="9636d-213">詳細については、Maoni Stephens のブログの「[CPU が 64 を超えるコンピューター上での GC のための CPU 構成の向上](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9636d-213">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="9636d-214">設定の名前</span><span class="sxs-lookup"><span data-stu-id="9636d-214">Setting name</span></span> | <span data-ttu-id="9636d-215">値</span><span class="sxs-lookup"><span data-stu-id="9636d-215">Values</span></span> | <span data-ttu-id="9636d-216">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="9636d-216">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9636d-217">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9636d-217">**runtimeconfig.json**</span></span> | `System.GC.GCHeapAffinitizeRanges` | <span data-ttu-id="9636d-218">プロセッサ番号またはプロセッサ番号の範囲のコンマ区切りリスト。</span><span class="sxs-lookup"><span data-stu-id="9636d-218">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="9636d-219">Unix の例:"1-10,12,50-52,70"</span><span class="sxs-lookup"><span data-stu-id="9636d-219">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="9636d-220">Windows の例:"0:1-10,0:12,1:50-52,1:70"</span><span class="sxs-lookup"><span data-stu-id="9636d-220">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="9636d-221">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9636d-221">.NET Core 3.0</span></span> |
| <span data-ttu-id="9636d-222">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="9636d-222">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeRanges` | <span data-ttu-id="9636d-223">プロセッサ番号またはプロセッサ番号の範囲のコンマ区切りリスト。</span><span class="sxs-lookup"><span data-stu-id="9636d-223">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="9636d-224">Unix の例:"1-10,12,50-52,70"</span><span class="sxs-lookup"><span data-stu-id="9636d-224">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="9636d-225">Windows の例:"0:1-10,0:12,1:50-52,1:70"</span><span class="sxs-lookup"><span data-stu-id="9636d-225">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="9636d-226">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9636d-226">.NET Core 3.0</span></span> |

<span data-ttu-id="9636d-227">例:</span><span class="sxs-lookup"><span data-stu-id="9636d-227">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="complus_gccpugroup"></a><span data-ttu-id="9636d-228">COMPlus_GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="9636d-228">COMPlus_GCCpuGroup</span></span>

- <span data-ttu-id="9636d-229">ガベージ コレクターで [CPU グループ](/windows/win32/procthread/processor-groups)を使用するかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="9636d-229">Configures whether the garbage collector uses [CPU groups](/windows/win32/procthread/processor-groups) or not.</span></span>

  <span data-ttu-id="9636d-230">64 ビットの Windows コンピューターに複数の CPU グループがある (つまり、64 を超えるプロセッサがある) 場合、この要素を有効にすると、すべての CPU グループ全体にガベージ コレクションが拡張されます。</span><span class="sxs-lookup"><span data-stu-id="9636d-230">When a 64-bit Windows computer has multiple CPU groups, that is, there are more than 64 processors, enabling this element extends garbage collection across all CPU groups.</span></span> <span data-ttu-id="9636d-231">ガベージ コレクターではすべてのコアを使用し、ヒープを作成して分散させます。</span><span class="sxs-lookup"><span data-stu-id="9636d-231">The garbage collector uses all cores to create and balance heaps.</span></span>

- <span data-ttu-id="9636d-232">64 ビット Windows オペレーティング システムのみのサーバー ガベージ コレクションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="9636d-232">Applies to server garbage collection on 64-bit Windows operation systems only.</span></span>
- <span data-ttu-id="9636d-233">既定:無効 (`0`)。</span><span class="sxs-lookup"><span data-stu-id="9636d-233">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="9636d-234">詳細については、Maoni Stephens のブログの「[CPU が 64 を超えるコンピューター上での GC のための CPU 構成の向上](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9636d-234">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="9636d-235">設定の名前</span><span class="sxs-lookup"><span data-stu-id="9636d-235">Setting name</span></span> | <span data-ttu-id="9636d-236">値</span><span class="sxs-lookup"><span data-stu-id="9636d-236">Values</span></span> | <span data-ttu-id="9636d-237">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="9636d-237">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9636d-238">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9636d-238">**runtimeconfig.json**</span></span> | <span data-ttu-id="9636d-239">N/A</span><span class="sxs-lookup"><span data-stu-id="9636d-239">N/A</span></span> | <span data-ttu-id="9636d-240">N/A</span><span class="sxs-lookup"><span data-stu-id="9636d-240">N/A</span></span> | <span data-ttu-id="9636d-241">N/A</span><span class="sxs-lookup"><span data-stu-id="9636d-241">N/A</span></span> |
| <span data-ttu-id="9636d-242">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="9636d-242">**Environment variable**</span></span> | `COMPlus_GCCpuGroup` | <span data-ttu-id="9636d-243">`0` - 無効</span><span class="sxs-lookup"><span data-stu-id="9636d-243">`0` - disabled</span></span><br/><span data-ttu-id="9636d-244">`1` - 有効</span><span class="sxs-lookup"><span data-stu-id="9636d-244">`1` - enabled</span></span> | <span data-ttu-id="9636d-245">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="9636d-245">.NET Core 1.0</span></span> |
| <span data-ttu-id="9636d-246">**.NET Framework 用の app.config**</span><span class="sxs-lookup"><span data-stu-id="9636d-246">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="9636d-247">GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="9636d-247">GCCpuGroup</span></span>](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | <span data-ttu-id="9636d-248">`false` - 無効</span><span class="sxs-lookup"><span data-stu-id="9636d-248">`false` - disabled</span></span><br/><span data-ttu-id="9636d-249">`true` - 有効</span><span class="sxs-lookup"><span data-stu-id="9636d-249">`true` - enabled</span></span> |  |

> [!NOTE]
> <span data-ttu-id="9636d-250">すべての CPU グループ全体にスレッド プールからのスレッドも分散するように共通言語ランタイム (CLR) を構成するには、[Thread_UseAllCpuGroups 要素](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md)オプションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="9636d-250">To configure the common language runtime (CLR) to also distribute threads from the thread pool across all CPU groups, enable the [Thread_UseAllCpuGroups element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) option.</span></span> <span data-ttu-id="9636d-251">.NET Core アプリの場合は、`COMPlus_Thread_UseAllCpuGroups` 環境変数の値を `1` に設定することによって、このオプションを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="9636d-251">For .NET Core apps, you can enable this option by setting the value of the `COMPlus_Thread_UseAllCpuGroups` environment variable to `1`.</span></span>

### <a name="systemgcnoaffinitizecomplus_gcnoaffinitize"></a><span data-ttu-id="9636d-252">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="9636d-252">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span></span>

- <span data-ttu-id="9636d-253">ガベージ コレクション スレッドをプロセッサに "*関係付ける*" かどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="9636d-253">Specifies whether to *affinitize* garbage collection threads with processors.</span></span> <span data-ttu-id="9636d-254">GC スレッドを関係付けることは、その特定の CPU でのみ実行できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="9636d-254">To affinitize a GC thread means that it can only run on its specific CPU.</span></span> <span data-ttu-id="9636d-255">各 GC スレッドに対してヒープが作成されます。</span><span class="sxs-lookup"><span data-stu-id="9636d-255">A heap is created for each GC thread.</span></span>
- <span data-ttu-id="9636d-256">サーバー ガベージ コレクションにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="9636d-256">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="9636d-257">既定:ガベージ コレクション スレッドをプロセッサに関係付けます (`false`)。</span><span class="sxs-lookup"><span data-stu-id="9636d-257">Default: Affinitize garbage collection threads with processors (`false`).</span></span>

| | <span data-ttu-id="9636d-258">設定の名前</span><span class="sxs-lookup"><span data-stu-id="9636d-258">Setting name</span></span> | <span data-ttu-id="9636d-259">値</span><span class="sxs-lookup"><span data-stu-id="9636d-259">Values</span></span> | <span data-ttu-id="9636d-260">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="9636d-260">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9636d-261">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9636d-261">**runtimeconfig.json**</span></span> | `System.GC.NoAffinitize` | <span data-ttu-id="9636d-262">`false` -関係付ける</span><span class="sxs-lookup"><span data-stu-id="9636d-262">`false` - affinitize</span></span><br/><span data-ttu-id="9636d-263">`true` -関係付けない</span><span class="sxs-lookup"><span data-stu-id="9636d-263">`true` - don't affinitize</span></span> | <span data-ttu-id="9636d-264">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9636d-264">.NET Core 3.0</span></span> |
| <span data-ttu-id="9636d-265">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="9636d-265">**Environment variable**</span></span> | `COMPlus_GCNoAffinitize` | <span data-ttu-id="9636d-266">`0` -関係付ける</span><span class="sxs-lookup"><span data-stu-id="9636d-266">`0` - affinitize</span></span><br/><span data-ttu-id="9636d-267">`1` -関係付けない</span><span class="sxs-lookup"><span data-stu-id="9636d-267">`1` - don't affinitize</span></span> | <span data-ttu-id="9636d-268">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9636d-268">.NET Core 3.0</span></span> |
| <span data-ttu-id="9636d-269">**.NET Framework 用の app.config**</span><span class="sxs-lookup"><span data-stu-id="9636d-269">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="9636d-270">GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="9636d-270">GCNoAffinitize</span></span>](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | <span data-ttu-id="9636d-271">`false` -関係付ける</span><span class="sxs-lookup"><span data-stu-id="9636d-271">`false` - affinitize</span></span><br/><span data-ttu-id="9636d-272">`true` -関係付けない</span><span class="sxs-lookup"><span data-stu-id="9636d-272">`true` - don't affinitize</span></span> | <span data-ttu-id="9636d-273">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="9636d-273">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="9636d-274">例:</span><span class="sxs-lookup"><span data-stu-id="9636d-274">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="systemgcheaphardlimitcomplus_gcheaphardlimit"></a><span data-ttu-id="9636d-275">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span><span class="sxs-lookup"><span data-stu-id="9636d-275">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span></span>

- <span data-ttu-id="9636d-276">GC ヒープおよび GC ブックキーピングに対して、最大コミット サイズをバイト単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="9636d-276">Specifies the maximum commit size, in bytes, for the GC heap and GC bookkeeping.</span></span>

| | <span data-ttu-id="9636d-277">設定の名前</span><span class="sxs-lookup"><span data-stu-id="9636d-277">Setting name</span></span> | <span data-ttu-id="9636d-278">値</span><span class="sxs-lookup"><span data-stu-id="9636d-278">Values</span></span> | <span data-ttu-id="9636d-279">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="9636d-279">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9636d-280">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9636d-280">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimit` | <span data-ttu-id="9636d-281">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="9636d-281">*decimal value*</span></span> | <span data-ttu-id="9636d-282">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9636d-282">.NET Core 3.0</span></span> |
| <span data-ttu-id="9636d-283">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="9636d-283">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimit` | <span data-ttu-id="9636d-284">"*16 進値*"</span><span class="sxs-lookup"><span data-stu-id="9636d-284">*hexadecimal value*</span></span> | <span data-ttu-id="9636d-285">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9636d-285">.NET Core 3.0</span></span> |

<span data-ttu-id="9636d-286">例:</span><span class="sxs-lookup"><span data-stu-id="9636d-286">Example:</span></span>

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
> <span data-ttu-id="9636d-287">*runtimeconfig.json* でオプションを設定する場合は、10 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="9636d-287">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="9636d-288">環境変数としてオプションを設定する場合は、16 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="9636d-288">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="9636d-289">たとえば、ヒープのハード制限を 200 メビバイト (MiB) に指定する場合、値は JSON ファイルでは 209715200、環境変数では 0xC800000 または C800000 になります。</span><span class="sxs-lookup"><span data-stu-id="9636d-289">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent"></a><span data-ttu-id="9636d-290">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span><span class="sxs-lookup"><span data-stu-id="9636d-290">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span></span>

- <span data-ttu-id="9636d-291">GC ヒープ使用量を、合計メモリに対する割合として指定します。</span><span class="sxs-lookup"><span data-stu-id="9636d-291">Specifies the GC heap usage as a percentage of the total memory.</span></span>

| | <span data-ttu-id="9636d-292">設定の名前</span><span class="sxs-lookup"><span data-stu-id="9636d-292">Setting name</span></span> | <span data-ttu-id="9636d-293">値</span><span class="sxs-lookup"><span data-stu-id="9636d-293">Values</span></span> | <span data-ttu-id="9636d-294">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="9636d-294">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9636d-295">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9636d-295">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPercent` | <span data-ttu-id="9636d-296">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="9636d-296">*decimal value*</span></span> | <span data-ttu-id="9636d-297">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9636d-297">.NET Core 3.0</span></span> |
| <span data-ttu-id="9636d-298">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="9636d-298">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimitPercent` | <span data-ttu-id="9636d-299">"*16 進値*"</span><span class="sxs-lookup"><span data-stu-id="9636d-299">*hexadecimal value*</span></span> | <span data-ttu-id="9636d-300">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9636d-300">.NET Core 3.0</span></span> |

<span data-ttu-id="9636d-301">例:</span><span class="sxs-lookup"><span data-stu-id="9636d-301">Example:</span></span>

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
> <span data-ttu-id="9636d-302">*runtimeconfig.json* でオプションを設定する場合は、10 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="9636d-302">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="9636d-303">環境変数としてオプションを設定する場合は、16 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="9636d-303">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="9636d-304">たとえば、ヒープの使用量を 30% に制限する場合、値は JSON ファイルでは 30、環境変数では 0x1E または 1E になります。</span><span class="sxs-lookup"><span data-stu-id="9636d-304">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="systemgcretainvmcomplus_gcretainvm"></a><span data-ttu-id="9636d-305">System.GC.RetainVM/COMPlus_GCRetainVM</span><span class="sxs-lookup"><span data-stu-id="9636d-305">System.GC.RetainVM/COMPlus_GCRetainVM</span></span>

- <span data-ttu-id="9636d-306">削除する必要があるセグメントを、後で使用するためにスタンバイ リストに配置するか、解放してオペレーティング システム (OS) に戻すかを構成します。</span><span class="sxs-lookup"><span data-stu-id="9636d-306">Configures whether segments that should be deleted are put on a standby list for future use or are released back to the operating system (OS).</span></span>
- <span data-ttu-id="9636d-307">既定:セグメントを解放してオペレーティング システムに戻します (`false`)。</span><span class="sxs-lookup"><span data-stu-id="9636d-307">Default: Release segments back to the operating system (`false`).</span></span>

| | <span data-ttu-id="9636d-308">設定の名前</span><span class="sxs-lookup"><span data-stu-id="9636d-308">Setting name</span></span> | <span data-ttu-id="9636d-309">値</span><span class="sxs-lookup"><span data-stu-id="9636d-309">Values</span></span> | <span data-ttu-id="9636d-310">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="9636d-310">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9636d-311">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9636d-311">**runtimeconfig.json**</span></span> | `System.GC.RetainVM` | <span data-ttu-id="9636d-312">`false` -OS に解放する</span><span class="sxs-lookup"><span data-stu-id="9636d-312">`false` - release to OS</span></span><br/><span data-ttu-id="9636d-313">`true` - スタンバイに配置する</span><span class="sxs-lookup"><span data-stu-id="9636d-313">`true` - put on standby</span></span>| <span data-ttu-id="9636d-314">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="9636d-314">.NET Core 1.0</span></span> |
| <span data-ttu-id="9636d-315">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="9636d-315">**Environment variable**</span></span> | `COMPlus_GCRetainVM` | <span data-ttu-id="9636d-316">`0` -OS に解放する</span><span class="sxs-lookup"><span data-stu-id="9636d-316">`0` - release to OS</span></span><br/><span data-ttu-id="9636d-317">`1` - スタンバイに配置する</span><span class="sxs-lookup"><span data-stu-id="9636d-317">`1` - put on standby</span></span> | <span data-ttu-id="9636d-318">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="9636d-318">.NET Core 1.0</span></span> |

<span data-ttu-id="9636d-319">例:</span><span class="sxs-lookup"><span data-stu-id="9636d-319">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

## <a name="large-pages"></a><span data-ttu-id="9636d-320">大きいページ</span><span class="sxs-lookup"><span data-stu-id="9636d-320">Large pages</span></span>

### <a name="complus_gclargepages"></a><span data-ttu-id="9636d-321">COMPlus_GCLargePages</span><span class="sxs-lookup"><span data-stu-id="9636d-321">COMPlus_GCLargePages</span></span>

- <span data-ttu-id="9636d-322">ヒープのハード制限が設定されている場合に、大きいページを使用する必要があるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="9636d-322">Specifies whether large pages should be used when a heap hard limit is set.</span></span>
- <span data-ttu-id="9636d-323">既定:無効 (`0`)。</span><span class="sxs-lookup"><span data-stu-id="9636d-323">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="9636d-324">これは試験段階の設定です。</span><span class="sxs-lookup"><span data-stu-id="9636d-324">This is an experimental setting.</span></span>

| | <span data-ttu-id="9636d-325">設定の名前</span><span class="sxs-lookup"><span data-stu-id="9636d-325">Setting name</span></span> | <span data-ttu-id="9636d-326">値</span><span class="sxs-lookup"><span data-stu-id="9636d-326">Values</span></span> | <span data-ttu-id="9636d-327">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="9636d-327">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9636d-328">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9636d-328">**runtimeconfig.json**</span></span> | <span data-ttu-id="9636d-329">N/A</span><span class="sxs-lookup"><span data-stu-id="9636d-329">N/A</span></span> | <span data-ttu-id="9636d-330">N/A</span><span class="sxs-lookup"><span data-stu-id="9636d-330">N/A</span></span> | <span data-ttu-id="9636d-331">N/A</span><span class="sxs-lookup"><span data-stu-id="9636d-331">N/A</span></span> |
| <span data-ttu-id="9636d-332">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="9636d-332">**Environment variable**</span></span> | `COMPlus_GCLargePages` | <span data-ttu-id="9636d-333">`0` - 無効</span><span class="sxs-lookup"><span data-stu-id="9636d-333">`0` - disabled</span></span><br/><span data-ttu-id="9636d-334">`1` - 有効</span><span class="sxs-lookup"><span data-stu-id="9636d-334">`1` - enabled</span></span> | <span data-ttu-id="9636d-335">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9636d-335">.NET Core 3.0</span></span> |

## <a name="large-objects"></a><span data-ttu-id="9636d-336">大きなオブジェクト</span><span class="sxs-lookup"><span data-stu-id="9636d-336">Large objects</span></span>

### <a name="complus_gcallowverylargeobjects"></a><span data-ttu-id="9636d-337">COMPlus_gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="9636d-337">COMPlus_gcAllowVeryLargeObjects</span></span>

- <span data-ttu-id="9636d-338">合計サイズが 2 ギガバイト (GB) を超える配列に対して、64 ビット プラットフォームでのガベージ コレクター サポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="9636d-338">Configures garbage collector support on 64-bit platforms for arrays that are greater than 2 gigabytes (GB) in total size.</span></span>
- <span data-ttu-id="9636d-339">既定:有効 (`1`)。</span><span class="sxs-lookup"><span data-stu-id="9636d-339">Default: Enabled (`1`).</span></span>
- <span data-ttu-id="9636d-340">このオプションは、将来のバージョンの .NET で廃止される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9636d-340">This option may become obsolete in a future version of .NET.</span></span>

| | <span data-ttu-id="9636d-341">設定の名前</span><span class="sxs-lookup"><span data-stu-id="9636d-341">Setting name</span></span> | <span data-ttu-id="9636d-342">値</span><span class="sxs-lookup"><span data-stu-id="9636d-342">Values</span></span> | <span data-ttu-id="9636d-343">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="9636d-343">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9636d-344">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9636d-344">**runtimeconfig.json**</span></span> | <span data-ttu-id="9636d-345">N/A</span><span class="sxs-lookup"><span data-stu-id="9636d-345">N/A</span></span> | <span data-ttu-id="9636d-346">N/A</span><span class="sxs-lookup"><span data-stu-id="9636d-346">N/A</span></span> | <span data-ttu-id="9636d-347">N/A</span><span class="sxs-lookup"><span data-stu-id="9636d-347">N/A</span></span> |
| <span data-ttu-id="9636d-348">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="9636d-348">**Environment variable**</span></span> | `COMPlus_gcAllowVeryLargeObjects` | <span data-ttu-id="9636d-349">`1` - 有効</span><span class="sxs-lookup"><span data-stu-id="9636d-349">`1` - enabled</span></span><br/> <span data-ttu-id="9636d-350">`0` - 無効</span><span class="sxs-lookup"><span data-stu-id="9636d-350">`0` - disabled</span></span> | <span data-ttu-id="9636d-351">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="9636d-351">.NET Core 1.0</span></span> |
| <span data-ttu-id="9636d-352">**.NET Framework 用の app.config**</span><span class="sxs-lookup"><span data-stu-id="9636d-352">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="9636d-353">gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="9636d-353">gcAllowVeryLargeObjects</span></span>](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | <span data-ttu-id="9636d-354">`1` - 有効</span><span class="sxs-lookup"><span data-stu-id="9636d-354">`1` - enabled</span></span><br/> <span data-ttu-id="9636d-355">`0` - 無効</span><span class="sxs-lookup"><span data-stu-id="9636d-355">`0` - disabled</span></span> | <span data-ttu-id="9636d-356">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="9636d-356">.NET Framework 4.5</span></span> |

## <a name="large-object-heap-threshold"></a><span data-ttu-id="9636d-357">大きなオブジェクト ヒープのしきい値</span><span class="sxs-lookup"><span data-stu-id="9636d-357">Large object heap threshold</span></span>

### <a name="systemgclohthresholdcomplus_gclohthreshold"></a><span data-ttu-id="9636d-358">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="9636d-358">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span></span>

- <span data-ttu-id="9636d-359">オブジェクトが大きなオブジェクト ヒープ (LOH) に移る原因となる、しきい値のサイズ (バイト単位) を指定します。</span><span class="sxs-lookup"><span data-stu-id="9636d-359">Specifies the threshold size, in bytes, that causes objects to go on the large object heap (LOH).</span></span>
- <span data-ttu-id="9636d-360">既定のしきい値は 85,000 バイトです。</span><span class="sxs-lookup"><span data-stu-id="9636d-360">The default threshold is 85,000 bytes.</span></span>
- <span data-ttu-id="9636d-361">指定する値は、既定のしきい値より大きくする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9636d-361">The value you specify must be larger than the default threshold.</span></span>

| | <span data-ttu-id="9636d-362">設定の名前</span><span class="sxs-lookup"><span data-stu-id="9636d-362">Setting name</span></span> | <span data-ttu-id="9636d-363">値</span><span class="sxs-lookup"><span data-stu-id="9636d-363">Values</span></span> | <span data-ttu-id="9636d-364">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="9636d-364">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9636d-365">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9636d-365">**runtimeconfig.json**</span></span> | `System.GC.LOHThreshold` | <span data-ttu-id="9636d-366">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="9636d-366">*decimal value*</span></span> | <span data-ttu-id="9636d-367">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="9636d-367">.NET Core 1.0</span></span> |
| <span data-ttu-id="9636d-368">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="9636d-368">**Environment variable**</span></span> | `COMPlus_GCLOHThreshold` | <span data-ttu-id="9636d-369">"*16 進値*"</span><span class="sxs-lookup"><span data-stu-id="9636d-369">*hexadecimal value*</span></span> | <span data-ttu-id="9636d-370">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="9636d-370">.NET Core 1.0</span></span> |
| <span data-ttu-id="9636d-371">**.NET Framework 用の app.config**</span><span class="sxs-lookup"><span data-stu-id="9636d-371">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="9636d-372">GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="9636d-372">GCLOHThreshold</span></span>](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | <span data-ttu-id="9636d-373">"*10 進値*"</span><span class="sxs-lookup"><span data-stu-id="9636d-373">*decimal value*</span></span> | <span data-ttu-id="9636d-374">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="9636d-374">.NET Framework 4.8</span></span> |

<span data-ttu-id="9636d-375">例:</span><span class="sxs-lookup"><span data-stu-id="9636d-375">Example:</span></span>

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
> <span data-ttu-id="9636d-376">*runtimeconfig.json* でオプションを設定する場合は、10 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="9636d-376">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="9636d-377">環境変数としてオプションを設定する場合は、16 進値を指定します。</span><span class="sxs-lookup"><span data-stu-id="9636d-377">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="9636d-378">たとえば、しきい値のサイズを 120,000 バイトに設定する場合、値は JSON ファイルでは 120000、環境変数では 0x1D4C0 または 1D4C0 になります。</span><span class="sxs-lookup"><span data-stu-id="9636d-378">For example, to set a threshold size of 120,000 bytes, the values would be 120000 for the JSON file and 0x1D4C0 or 1D4C0 for the environment variable.</span></span>

## <a name="standalone-gc"></a><span data-ttu-id="9636d-379">スタンドアロン GC</span><span class="sxs-lookup"><span data-stu-id="9636d-379">Standalone GC</span></span>

### <a name="complus_gcname"></a><span data-ttu-id="9636d-380">COMPlus_GCName</span><span class="sxs-lookup"><span data-stu-id="9636d-380">COMPlus_GCName</span></span>

- <span data-ttu-id="9636d-381">ランタイムで読み込む対象となる、ガベージ コレクターを含むライブラリへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="9636d-381">Specifies a path to the library containing the garbage collector that the runtime intends to load.</span></span>
- <span data-ttu-id="9636d-382">詳細については、「[スタンドアロン GC ローダーの設計](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9636d-382">For more information, see [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span></span>

| | <span data-ttu-id="9636d-383">設定の名前</span><span class="sxs-lookup"><span data-stu-id="9636d-383">Setting name</span></span> | <span data-ttu-id="9636d-384">値</span><span class="sxs-lookup"><span data-stu-id="9636d-384">Values</span></span> | <span data-ttu-id="9636d-385">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="9636d-385">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="9636d-386">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="9636d-386">**runtimeconfig.json**</span></span> | <span data-ttu-id="9636d-387">N/A</span><span class="sxs-lookup"><span data-stu-id="9636d-387">N/A</span></span> | <span data-ttu-id="9636d-388">N/A</span><span class="sxs-lookup"><span data-stu-id="9636d-388">N/A</span></span> | <span data-ttu-id="9636d-389">N/A</span><span class="sxs-lookup"><span data-stu-id="9636d-389">N/A</span></span> |
| <span data-ttu-id="9636d-390">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="9636d-390">**Environment variable**</span></span> | `COMPlus_GCName` | <span data-ttu-id="9636d-391">*string_path*</span><span class="sxs-lookup"><span data-stu-id="9636d-391">*string_path*</span></span> | <span data-ttu-id="9636d-392">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="9636d-392">.NET Core 2.0</span></span> |
