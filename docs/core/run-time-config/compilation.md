---
title: コンパイルの構成設定
description: .NET Core アプリの JIT コンパイラの動作方法を構成するランタイム設定について説明します。
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: ac51aa13254b2f2b1fdd8d1dd9c52559831a1659
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989117"
---
# <a name="run-time-configuration-options-for-compilation"></a><span data-ttu-id="d7747-103">コンパイルのランタイム構成オプション</span><span class="sxs-lookup"><span data-stu-id="d7747-103">Run-time configuration options for compilation</span></span>

## <a name="tiered-compilation"></a><span data-ttu-id="d7747-104">階層型コンパイル</span><span class="sxs-lookup"><span data-stu-id="d7747-104">Tiered compilation</span></span>

- <span data-ttu-id="d7747-105">Just-In-Time (JIT) コンパイラで[階層型コンパイル](../whats-new/dotnet-core-3-0.md#tiered-compilation)を使用するかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="d7747-105">Configures whether the just-in-time (JIT) compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span> <span data-ttu-id="d7747-106">階層型コンパイルでは、2 つの階層を使用して手法を切り替えます。</span><span class="sxs-lookup"><span data-stu-id="d7747-106">Tiered compilation transitions methods through two tiers:</span></span>
  - <span data-ttu-id="d7747-107">最初の階層では、コードの生成を高速化 ([クイック JIT](#quick-jit)) するか、プリコンパイル済みコード ([ReadyToRun](#readytorun)) を読み込みます。</span><span class="sxs-lookup"><span data-stu-id="d7747-107">The first tier generates code more quickly ([quick JIT](#quick-jit)) or loads pre-compiled code ([ReadyToRun](#readytorun)).</span></span>
  - <span data-ttu-id="d7747-108">2 番目の階層では、最適化されたコードをバックグラウンドで生成します ("JIT の最適化")。</span><span class="sxs-lookup"><span data-stu-id="d7747-108">The second tier generates optimized code in the background ("optimizing JIT").</span></span>
- <span data-ttu-id="d7747-109">.NET Core 3.0 以降、階層型コンパイルは既定で有効に設定されます。</span><span class="sxs-lookup"><span data-stu-id="d7747-109">In .NET Core 3.0 and later, tiered compilation is enabled by default.</span></span>
- <span data-ttu-id="d7747-110">.NET Core 2.1 および 2.2 では、階層型コンパイルは既定で無効に設定されます。</span><span class="sxs-lookup"><span data-stu-id="d7747-110">In .NET Core 2.1 and 2.2, tiered compilation is disabled by default.</span></span>
- <span data-ttu-id="d7747-111">詳細については、「[階層型コンパイル ガイド](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7747-111">For more information, see the [Tiered compilation guide](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation.md).</span></span>

| | <span data-ttu-id="d7747-112">設定の名前</span><span class="sxs-lookup"><span data-stu-id="d7747-112">Setting name</span></span> | <span data-ttu-id="d7747-113">値</span><span class="sxs-lookup"><span data-stu-id="d7747-113">Values</span></span> |
| - | - | - |
| <span data-ttu-id="d7747-114">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d7747-114">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation` | <span data-ttu-id="d7747-115">`true` - 有効</span><span class="sxs-lookup"><span data-stu-id="d7747-115">`true` - enabled</span></span><br/><span data-ttu-id="d7747-116">`false` - 無効</span><span class="sxs-lookup"><span data-stu-id="d7747-116">`false` - disabled</span></span> |
| <span data-ttu-id="d7747-117">**MSBuild のプロパティ**</span><span class="sxs-lookup"><span data-stu-id="d7747-117">**MSBuild property**</span></span> | `TieredCompilation` | <span data-ttu-id="d7747-118">`true` - 有効</span><span class="sxs-lookup"><span data-stu-id="d7747-118">`true` - enabled</span></span><br/><span data-ttu-id="d7747-119">`false` - 無効</span><span class="sxs-lookup"><span data-stu-id="d7747-119">`false` - disabled</span></span> |
| <span data-ttu-id="d7747-120">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="d7747-120">**Environment variable**</span></span> | `COMPlus_TieredCompilation` | <span data-ttu-id="d7747-121">`1` - 有効</span><span class="sxs-lookup"><span data-stu-id="d7747-121">`1` - enabled</span></span><br/><span data-ttu-id="d7747-122">`0` - 無効</span><span class="sxs-lookup"><span data-stu-id="d7747-122">`0` - disabled</span></span> |

### <a name="examples"></a><span data-ttu-id="d7747-123">使用例</span><span class="sxs-lookup"><span data-stu-id="d7747-123">Examples</span></span>

<span data-ttu-id="d7747-124">*runtimeconfig.json* ファイル:</span><span class="sxs-lookup"><span data-stu-id="d7747-124">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation": false
      }
   }
}
```

<span data-ttu-id="d7747-125">プロジェクト ファイル:</span><span class="sxs-lookup"><span data-stu-id="d7747-125">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilation>false</TieredCompilation>
  </PropertyGroup>

</Project>
```

## <a name="quick-jit"></a><span data-ttu-id="d7747-126">クイック JIT</span><span class="sxs-lookup"><span data-stu-id="d7747-126">Quick JIT</span></span>

- <span data-ttu-id="d7747-127">JIT コンパイラで "*クイック JIT*" を使用するかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="d7747-127">Configures whether the JIT compiler uses *quick JIT*.</span></span> <span data-ttu-id="d7747-128">ループを含まず、事前コンパイル済みのコードを使用できないメソッドの場合、クイック JIT では最適化を行わずに高速にコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="d7747-128">For methods that don't contain loops and for which pre-compiled code is not available, quick JIT compiles them more quickly but without optimizations.</span></span>
- <span data-ttu-id="d7747-129">クイック JIT を有効にすると、起動時間が短縮されますが、パフォーマンス特性が低下したコードが生成される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d7747-129">Enabling quick JIT decreases startup time but can produce code with degraded performance characteristics.</span></span> <span data-ttu-id="d7747-130">たとえば、コードによって、より多くのスタック領域が使用され、より多くのメモリが割り当てられて、コードの実行速度が低下することがあります。</span><span class="sxs-lookup"><span data-stu-id="d7747-130">For example, the code may use more stack space, allocate more memory, and run slower.</span></span>
- <span data-ttu-id="d7747-131">クイック JIT を無効にして "[階層化コンパイル](#tiered-compilation)" を有効にした場合は、プリコンパイル済みのコードのみが階層型コンパイルの対象になります。</span><span class="sxs-lookup"><span data-stu-id="d7747-131">If quick JIT is disabled but [tiered compilation](#tiered-compilation) is enabled, only pre-compiled code participates in tiered compilation.</span></span> <span data-ttu-id="d7747-132">メソッドが [ReadyToRun](#readytorun) を使用してプリコンパイルされていない場合、JIT の動作は[階層型コンパイル](#tiered-compilation)が無効になっている場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="d7747-132">If a method is not pre-compiled with [ReadyToRun](#readytorun), the JIT behavior is the same as if [tiered compilation](#tiered-compilation) were disabled.</span></span>
- <span data-ttu-id="d7747-133">.NET Core 3.0 以降、クリック JIT は既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="d7747-133">In .NET Core 3.0 and later, quick JIT is enabled by default.</span></span>
- <span data-ttu-id="d7747-134">.NET Core 2.1 および 2.2 では、クイック JIT は既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="d7747-134">In .NET Core 2.1 and 2.2, quick JIT is disabled by default.</span></span>

| | <span data-ttu-id="d7747-135">設定の名前</span><span class="sxs-lookup"><span data-stu-id="d7747-135">Setting name</span></span> | <span data-ttu-id="d7747-136">値</span><span class="sxs-lookup"><span data-stu-id="d7747-136">Values</span></span> |
| - | - | - |
| <span data-ttu-id="d7747-137">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d7747-137">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation.QuickJit` | <span data-ttu-id="d7747-138">`true` - 有効</span><span class="sxs-lookup"><span data-stu-id="d7747-138">`true` - enabled</span></span><br/><span data-ttu-id="d7747-139">`false` - 無効</span><span class="sxs-lookup"><span data-stu-id="d7747-139">`false` - disabled</span></span> |
| <span data-ttu-id="d7747-140">**MSBuild のプロパティ**</span><span class="sxs-lookup"><span data-stu-id="d7747-140">**MSBuild property**</span></span> | `TieredCompilationQuickJit` | <span data-ttu-id="d7747-141">`true` - 有効</span><span class="sxs-lookup"><span data-stu-id="d7747-141">`true` - enabled</span></span><br/><span data-ttu-id="d7747-142">`false` - 無効</span><span class="sxs-lookup"><span data-stu-id="d7747-142">`false` - disabled</span></span> |
| <span data-ttu-id="d7747-143">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="d7747-143">**Environment variable**</span></span> | `COMPlus_TC_QuickJit` | <span data-ttu-id="d7747-144">`1` - 有効</span><span class="sxs-lookup"><span data-stu-id="d7747-144">`1` - enabled</span></span><br/><span data-ttu-id="d7747-145">`0` - 無効</span><span class="sxs-lookup"><span data-stu-id="d7747-145">`0` - disabled</span></span> |

### <a name="examples"></a><span data-ttu-id="d7747-146">使用例</span><span class="sxs-lookup"><span data-stu-id="d7747-146">Examples</span></span>

<span data-ttu-id="d7747-147">*runtimeconfig.json* ファイル:</span><span class="sxs-lookup"><span data-stu-id="d7747-147">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation.QuickJit": false
      }
   }
}
```

<span data-ttu-id="d7747-148">プロジェクト ファイル:</span><span class="sxs-lookup"><span data-stu-id="d7747-148">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
  </PropertyGroup>

</Project>
```

## <a name="quick-jit-for-loops"></a><span data-ttu-id="d7747-149">ループに対するクイック JIT</span><span class="sxs-lookup"><span data-stu-id="d7747-149">Quick JIT for loops</span></span>

- <span data-ttu-id="d7747-150">ループを含むメソッドに対して JIT コンパイラでクリック JIT を使用するかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="d7747-150">Configures whether the JIT compiler uses quick JIT on methods that contain loops.</span></span>
- <span data-ttu-id="d7747-151">ループに対するクイック JIT を有効にすると、起動時のパフォーマンスが向上する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d7747-151">Enabling quick JIT for loops may improve startup performance.</span></span> <span data-ttu-id="d7747-152">ただし、長時間にわたって実行されるループでは、長期間にわたってあまり最適化されていないコードでスタックする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d7747-152">However, long-running loops can get stuck in less-optimized code for long periods.</span></span>
- <span data-ttu-id="d7747-153">[クイック JIT](#quick-jit) が無効になっている場合、この設定は効果がありません。</span><span class="sxs-lookup"><span data-stu-id="d7747-153">If [quick JIT](#quick-jit) is disabled, this setting has no effect.</span></span>
- <span data-ttu-id="d7747-154">既定:無効 (`false`)。</span><span class="sxs-lookup"><span data-stu-id="d7747-154">Default: Disabled (`false`).</span></span>

| | <span data-ttu-id="d7747-155">設定の名前</span><span class="sxs-lookup"><span data-stu-id="d7747-155">Setting name</span></span> | <span data-ttu-id="d7747-156">値</span><span class="sxs-lookup"><span data-stu-id="d7747-156">Values</span></span> |
| - | - | - |
| <span data-ttu-id="d7747-157">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d7747-157">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation.QuickJitForLoops` | <span data-ttu-id="d7747-158">`false` - 無効</span><span class="sxs-lookup"><span data-stu-id="d7747-158">`false` - disabled</span></span><br/><span data-ttu-id="d7747-159">`true` - 有効</span><span class="sxs-lookup"><span data-stu-id="d7747-159">`true` - enabled</span></span> |
| <span data-ttu-id="d7747-160">**MSBuild のプロパティ**</span><span class="sxs-lookup"><span data-stu-id="d7747-160">**MSBuild property**</span></span> | `TieredCompilationQuickJitForLoops` | <span data-ttu-id="d7747-161">`false` - 無効</span><span class="sxs-lookup"><span data-stu-id="d7747-161">`false` - disabled</span></span><br/><span data-ttu-id="d7747-162">`true` - 有効</span><span class="sxs-lookup"><span data-stu-id="d7747-162">`true` - enabled</span></span> |
| <span data-ttu-id="d7747-163">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="d7747-163">**Environment variable**</span></span> | `COMPlus_TC_QuickJitForLoops` | <span data-ttu-id="d7747-164">`0` - 無効</span><span class="sxs-lookup"><span data-stu-id="d7747-164">`0` - disabled</span></span><br/><span data-ttu-id="d7747-165">`1` - 有効</span><span class="sxs-lookup"><span data-stu-id="d7747-165">`1` - enabled</span></span> |

### <a name="examples"></a><span data-ttu-id="d7747-166">使用例</span><span class="sxs-lookup"><span data-stu-id="d7747-166">Examples</span></span>

<span data-ttu-id="d7747-167">*runtimeconfig.json* ファイル:</span><span class="sxs-lookup"><span data-stu-id="d7747-167">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation.QuickJitForLoops": false
      }
   }
}
```

<span data-ttu-id="d7747-168">プロジェクト ファイル:</span><span class="sxs-lookup"><span data-stu-id="d7747-168">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilationQuickJitForLoops>false</TieredCompilationQuickJitForLoops>
  </PropertyGroup>

</Project>
```

## <a name="readytorun"></a><span data-ttu-id="d7747-169">ReadyToRun</span><span class="sxs-lookup"><span data-stu-id="d7747-169">ReadyToRun</span></span>

- <span data-ttu-id="d7747-170">使用可能な ReadyToRun データを含むイメージに対して、.NET Core ランタイムでプリコンパイル済みコードを使用するかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="d7747-170">Configures whether the .NET Core runtime uses pre-compiled code for images with available ReadyToRun data.</span></span> <span data-ttu-id="d7747-171">このオプションを無効にすると、ランタイムでフレームワーク コードが JIT コンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="d7747-171">Disabling this option forces the runtime to JIT-compile framework code.</span></span>
- <span data-ttu-id="d7747-172">詳細については、「[ReadyToRun](../whats-new/dotnet-core-3-0.md#readytorun-images)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7747-172">For more information, see [ReadyToRun](../whats-new/dotnet-core-3-0.md#readytorun-images).</span></span>
- <span data-ttu-id="d7747-173">既定:有効 (`1`)。</span><span class="sxs-lookup"><span data-stu-id="d7747-173">Default: Enabled (`1`).</span></span>

| | <span data-ttu-id="d7747-174">設定の名前</span><span class="sxs-lookup"><span data-stu-id="d7747-174">Setting name</span></span> | <span data-ttu-id="d7747-175">値</span><span class="sxs-lookup"><span data-stu-id="d7747-175">Values</span></span> |
| - | - | - |
| <span data-ttu-id="d7747-176">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="d7747-176">**Environment variable**</span></span> | `COMPlus_ReadyToRun` | <span data-ttu-id="d7747-177">`1` - 有効</span><span class="sxs-lookup"><span data-stu-id="d7747-177">`1` - enabled</span></span><br/><span data-ttu-id="d7747-178">`0` - 無効</span><span class="sxs-lookup"><span data-stu-id="d7747-178">`0` - disabled</span></span> |
