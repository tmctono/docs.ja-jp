---
title: デバッグとプロファイルの構成設定
description: .NET Core アプリのデバッグとプロファイルを構成するランタイム設定について説明します。
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: c57cfa7233f48def890ded3c9d589b7f268147df
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/04/2019
ms.locfileid: "74998859"
---
# <a name="run-time-configuration-options-for-debugging-and-profiling"></a><span data-ttu-id="d16ca-103">デバッグとプロファイルのランタイム構成オプション</span><span class="sxs-lookup"><span data-stu-id="d16ca-103">Run-time configuration options for debugging and profiling</span></span>

## <a name="enable-diagnostics"></a><span data-ttu-id="d16ca-104">診断を有効化する</span><span class="sxs-lookup"><span data-stu-id="d16ca-104">Enable diagnostics</span></span>

- <span data-ttu-id="d16ca-105">デバッガー、プロファイラー、EventPipe 診断を有効にするか、または無効にするかを構成します。</span><span class="sxs-lookup"><span data-stu-id="d16ca-105">Configures whether the debugger, the profiler, and EventPipe diagnostics are enabled or disabled.</span></span>
- <span data-ttu-id="d16ca-106">既定:有効 (`1`)。</span><span class="sxs-lookup"><span data-stu-id="d16ca-106">Default: Enabled (`1`).</span></span>

| | <span data-ttu-id="d16ca-107">設定の名前</span><span class="sxs-lookup"><span data-stu-id="d16ca-107">Setting name</span></span> | <span data-ttu-id="d16ca-108">値</span><span class="sxs-lookup"><span data-stu-id="d16ca-108">Values</span></span> |
| - | - | - |
| <span data-ttu-id="d16ca-109">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d16ca-109">**runtimeconfig.json**</span></span> | <span data-ttu-id="d16ca-110">N/A</span><span class="sxs-lookup"><span data-stu-id="d16ca-110">N/A</span></span> | <span data-ttu-id="d16ca-111">N/A</span><span class="sxs-lookup"><span data-stu-id="d16ca-111">N/A</span></span> |
| <span data-ttu-id="d16ca-112">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="d16ca-112">**Environment variable**</span></span> | `COMPlus_EnableDiagnostics` | <span data-ttu-id="d16ca-113">`1` - 有効</span><span class="sxs-lookup"><span data-stu-id="d16ca-113">`1` - enabled</span></span><br/><span data-ttu-id="d16ca-114">`0` - 無効</span><span class="sxs-lookup"><span data-stu-id="d16ca-114">`0` - disabled</span></span> |

## <a name="enable-profiling"></a><span data-ttu-id="d16ca-115">プロファイルを有効にする</span><span class="sxs-lookup"><span data-stu-id="d16ca-115">Enable profiling</span></span>

- <span data-ttu-id="d16ca-116">現在実行中のプロセスに対してプロファイルを有効にするかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="d16ca-116">Configures whether profiling is enabled for the currently running process.</span></span>
- <span data-ttu-id="d16ca-117">既定:無効 (`0`)。</span><span class="sxs-lookup"><span data-stu-id="d16ca-117">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="d16ca-118">設定の名前</span><span class="sxs-lookup"><span data-stu-id="d16ca-118">Setting name</span></span> | <span data-ttu-id="d16ca-119">値</span><span class="sxs-lookup"><span data-stu-id="d16ca-119">Values</span></span> |
| - | - | - |
| <span data-ttu-id="d16ca-120">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d16ca-120">**runtimeconfig.json**</span></span> | <span data-ttu-id="d16ca-121">N/A</span><span class="sxs-lookup"><span data-stu-id="d16ca-121">N/A</span></span> | <span data-ttu-id="d16ca-122">N/A</span><span class="sxs-lookup"><span data-stu-id="d16ca-122">N/A</span></span> |
| <span data-ttu-id="d16ca-123">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="d16ca-123">**Environment variable**</span></span> | `CORECLR_ENABLE_PROFILING` | <span data-ttu-id="d16ca-124">`0` - 無効</span><span class="sxs-lookup"><span data-stu-id="d16ca-124">`0` - disabled</span></span><br/><span data-ttu-id="d16ca-125">`1` - 有効</span><span class="sxs-lookup"><span data-stu-id="d16ca-125">`1` - enabled</span></span> |

## <a name="profiler-guid"></a><span data-ttu-id="d16ca-126">プロファイラー GUID</span><span class="sxs-lookup"><span data-stu-id="d16ca-126">Profiler GUID</span></span>

- <span data-ttu-id="d16ca-127">現在実行中のプロセスに読み込むプロファイラーの GUID を指定します。</span><span class="sxs-lookup"><span data-stu-id="d16ca-127">Specifies the GUID of the profiler to load into the currently running process.</span></span>

| | <span data-ttu-id="d16ca-128">設定の名前</span><span class="sxs-lookup"><span data-stu-id="d16ca-128">Setting name</span></span> | <span data-ttu-id="d16ca-129">値</span><span class="sxs-lookup"><span data-stu-id="d16ca-129">Values</span></span> |
| - | - | - |
| <span data-ttu-id="d16ca-130">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d16ca-130">**runtimeconfig.json**</span></span> | <span data-ttu-id="d16ca-131">N/A</span><span class="sxs-lookup"><span data-stu-id="d16ca-131">N/A</span></span> | <span data-ttu-id="d16ca-132">N/A</span><span class="sxs-lookup"><span data-stu-id="d16ca-132">N/A</span></span> |
| <span data-ttu-id="d16ca-133">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="d16ca-133">**Environment variable**</span></span> | `CORECLR_PROFILER` | <span data-ttu-id="d16ca-134">*string-guid*</span><span class="sxs-lookup"><span data-stu-id="d16ca-134">*string-guid*</span></span> |

## <a name="profiler-location"></a><span data-ttu-id="d16ca-135">プロファイラーの場所</span><span class="sxs-lookup"><span data-stu-id="d16ca-135">Profiler location</span></span>

- <span data-ttu-id="d16ca-136">現在実行中のプロセス (32 ビット プロセスまたは 64 ビット プロセス) に読み込むプロファイラー DLL へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="d16ca-136">Specifies the path to the profiler DLL to load into the currently running process (or 32-bit or 64-bit process).</span></span>
- <span data-ttu-id="d16ca-137">複数の変数が設定されている場合、ビット固有の変数が優先されます。</span><span class="sxs-lookup"><span data-stu-id="d16ca-137">If more than one variable is set, the bitness-specific variables take precedence.</span></span> <span data-ttu-id="d16ca-138">これらは、ロードするプロファイラーのビットを指定します。</span><span class="sxs-lookup"><span data-stu-id="d16ca-138">They specify which bitness of profiler to load.</span></span>
- <span data-ttu-id="d16ca-139">詳細については、「[プロファイラー ライブラリを検索する](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/profiling/Profiler%20Loading.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d16ca-139">For more information, see [Finding the profiler library](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/profiling/Profiler%20Loading.md).</span></span>

| | <span data-ttu-id="d16ca-140">設定の名前</span><span class="sxs-lookup"><span data-stu-id="d16ca-140">Setting name</span></span> | <span data-ttu-id="d16ca-141">値</span><span class="sxs-lookup"><span data-stu-id="d16ca-141">Values</span></span> |
| - | - | - |
| <span data-ttu-id="d16ca-142">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="d16ca-142">**Environment variable**</span></span> | `CORECLR_PROFILER_PATH` | <span data-ttu-id="d16ca-143">*string-path*</span><span class="sxs-lookup"><span data-stu-id="d16ca-143">*string-path*</span></span> |
| <span data-ttu-id="d16ca-144">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="d16ca-144">**Environment variable**</span></span> | `CORECLR_PROFILER_PATH_32` | <span data-ttu-id="d16ca-145">*string-path*</span><span class="sxs-lookup"><span data-stu-id="d16ca-145">*string-path*</span></span> |
| <span data-ttu-id="d16ca-146">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="d16ca-146">**Environment variable**</span></span> | `CORECLR_PROFILER_PATH_64` | <span data-ttu-id="d16ca-147">*string-path*</span><span class="sxs-lookup"><span data-stu-id="d16ca-147">*string-path*</span></span> |

## <a name="write-perf-map"></a><span data-ttu-id="d16ca-148">パフォーマンス マップの作成</span><span class="sxs-lookup"><span data-stu-id="d16ca-148">Write perf map</span></span>

- <span data-ttu-id="d16ca-149">Linux システムでの */tmp/perf-$pid.map* の作成を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="d16ca-149">Enables or disables writing */tmp/perf-$pid.map* on Linux systems.</span></span>
- <span data-ttu-id="d16ca-150">既定:無効 (`0`)。</span><span class="sxs-lookup"><span data-stu-id="d16ca-150">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="d16ca-151">設定の名前</span><span class="sxs-lookup"><span data-stu-id="d16ca-151">Setting name</span></span> | <span data-ttu-id="d16ca-152">値</span><span class="sxs-lookup"><span data-stu-id="d16ca-152">Values</span></span> |
| - | - | - |
| <span data-ttu-id="d16ca-153">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d16ca-153">**runtimeconfig.json**</span></span> | <span data-ttu-id="d16ca-154">N/A</span><span class="sxs-lookup"><span data-stu-id="d16ca-154">N/A</span></span> | <span data-ttu-id="d16ca-155">N/A</span><span class="sxs-lookup"><span data-stu-id="d16ca-155">N/A</span></span> |
| <span data-ttu-id="d16ca-156">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="d16ca-156">**Environment variable**</span></span> | `COMPlus_PerfMapEnabled` | <span data-ttu-id="d16ca-157">`0` - 無効</span><span class="sxs-lookup"><span data-stu-id="d16ca-157">`0` - disabled</span></span><br/><span data-ttu-id="d16ca-158">`1` - 有効</span><span class="sxs-lookup"><span data-stu-id="d16ca-158">`1` - enabled</span></span> |

## <a name="perf-log-markers"></a><span data-ttu-id="d16ca-159">パフォーマンス ログのマーカー</span><span class="sxs-lookup"><span data-stu-id="d16ca-159">Perf log markers</span></span>

- <span data-ttu-id="d16ca-160">`COMPlus_PerfMapEnabled` が `1` に設定されている場合、指定されたシグナルを有効または無効にして、パフォーマンス ログのマーカーとして受け入れて無視します。</span><span class="sxs-lookup"><span data-stu-id="d16ca-160">When `COMPlus_PerfMapEnabled` is set to `1`, enables or disables the specified signal to be accepted and ignored as a marker in the perf logs.</span></span>
- <span data-ttu-id="d16ca-161">既定:無効 (`0`)。</span><span class="sxs-lookup"><span data-stu-id="d16ca-161">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="d16ca-162">設定の名前</span><span class="sxs-lookup"><span data-stu-id="d16ca-162">Setting name</span></span> | <span data-ttu-id="d16ca-163">値</span><span class="sxs-lookup"><span data-stu-id="d16ca-163">Values</span></span> |
| - | - | - |
| <span data-ttu-id="d16ca-164">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d16ca-164">**runtimeconfig.json**</span></span> | <span data-ttu-id="d16ca-165">N/A</span><span class="sxs-lookup"><span data-stu-id="d16ca-165">N/A</span></span> | <span data-ttu-id="d16ca-166">N/A</span><span class="sxs-lookup"><span data-stu-id="d16ca-166">N/A</span></span> |
| <span data-ttu-id="d16ca-167">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="d16ca-167">**Environment variable**</span></span> | `COMPlus_PerfMapIgnoreSignal` | <span data-ttu-id="d16ca-168">`0` - 無効</span><span class="sxs-lookup"><span data-stu-id="d16ca-168">`0` - disabled</span></span><br/><span data-ttu-id="d16ca-169">`1` - 有効</span><span class="sxs-lookup"><span data-stu-id="d16ca-169">`1` - enabled</span></span> |
