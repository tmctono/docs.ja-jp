---
title: スレッドの構成設定
description: .NET Core アプリのスレッドを構成するランタイム設定について説明します。
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 68b8e93ca6ec3f708a7a627307655ada1955500a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789847"
---
# <a name="run-time-configuration-options-for-threading"></a><span data-ttu-id="fbc1c-103">スレッドのランタイム構成オプション</span><span class="sxs-lookup"><span data-stu-id="fbc1c-103">Run-time configuration options for threading</span></span>

## <a name="cpu-groups"></a><span data-ttu-id="fbc1c-104">CPU グループ</span><span class="sxs-lookup"><span data-stu-id="fbc1c-104">CPU groups</span></span>

- <span data-ttu-id="fbc1c-105">CPU グループ全体にスレッドを自動的に配布するかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="fbc1c-105">Configures whether threads are automatically distributed across CPU groups.</span></span>
- <span data-ttu-id="fbc1c-106">既定:無効 (`0`)。</span><span class="sxs-lookup"><span data-stu-id="fbc1c-106">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="fbc1c-107">設定の名前</span><span class="sxs-lookup"><span data-stu-id="fbc1c-107">Setting name</span></span> | <span data-ttu-id="fbc1c-108">値</span><span class="sxs-lookup"><span data-stu-id="fbc1c-108">Values</span></span> |
| - | - | - |
| <span data-ttu-id="fbc1c-109">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="fbc1c-109">**runtimeconfig.json**</span></span> | <span data-ttu-id="fbc1c-110">N/A</span><span class="sxs-lookup"><span data-stu-id="fbc1c-110">N/A</span></span> | <span data-ttu-id="fbc1c-111">N/A</span><span class="sxs-lookup"><span data-stu-id="fbc1c-111">N/A</span></span> |
| <span data-ttu-id="fbc1c-112">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="fbc1c-112">**Environment variable**</span></span> | `COMPlus_Thread_UseAllCpuGroups` | <span data-ttu-id="fbc1c-113">`0` - 無効</span><span class="sxs-lookup"><span data-stu-id="fbc1c-113">`0` - disabled</span></span><br/><span data-ttu-id="fbc1c-114">`1` - 有効</span><span class="sxs-lookup"><span data-stu-id="fbc1c-114">`1` - enabled</span></span> |

## <a name="minimum-threads"></a><span data-ttu-id="fbc1c-115">最小スレッド数</span><span class="sxs-lookup"><span data-stu-id="fbc1c-115">Minimum threads</span></span>

- <span data-ttu-id="fbc1c-116">ワーカー スレッド プールの最小スレッド数を指定します。</span><span class="sxs-lookup"><span data-stu-id="fbc1c-116">Specifies the minimum number of threads for the worker thread pool.</span></span>
- <span data-ttu-id="fbc1c-117"><xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> メソッドに対応します。</span><span class="sxs-lookup"><span data-stu-id="fbc1c-117">Corresponds to the <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="fbc1c-118">設定の名前</span><span class="sxs-lookup"><span data-stu-id="fbc1c-118">Setting name</span></span> | <span data-ttu-id="fbc1c-119">値</span><span class="sxs-lookup"><span data-stu-id="fbc1c-119">Values</span></span> |
| - | - | - |
| <span data-ttu-id="fbc1c-120">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="fbc1c-120">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MinThreads` | <span data-ttu-id="fbc1c-121">最小スレッド数を表す整数</span><span class="sxs-lookup"><span data-stu-id="fbc1c-121">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="fbc1c-122">**MSBuild のプロパティ**</span><span class="sxs-lookup"><span data-stu-id="fbc1c-122">**MSBuild property**</span></span> | `ThreadPoolMinThreads` | <span data-ttu-id="fbc1c-123">最小スレッド数を表す整数</span><span class="sxs-lookup"><span data-stu-id="fbc1c-123">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="fbc1c-124">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="fbc1c-124">**Environment variable**</span></span> | <span data-ttu-id="fbc1c-125">N/A</span><span class="sxs-lookup"><span data-stu-id="fbc1c-125">N/A</span></span> | <span data-ttu-id="fbc1c-126">N/A</span><span class="sxs-lookup"><span data-stu-id="fbc1c-126">N/A</span></span> |

### <a name="examples"></a><span data-ttu-id="fbc1c-127">使用例</span><span class="sxs-lookup"><span data-stu-id="fbc1c-127">Examples</span></span>

<span data-ttu-id="fbc1c-128">*runtimeconfig.json* ファイル:</span><span class="sxs-lookup"><span data-stu-id="fbc1c-128">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MinThreads": 4
      }
   }
}
```

<span data-ttu-id="fbc1c-129">プロジェクト ファイル:</span><span class="sxs-lookup"><span data-stu-id="fbc1c-129">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
  </PropertyGroup>

</Project>
```

## <a name="maximum-threads"></a><span data-ttu-id="fbc1c-130">最大スレッド数</span><span class="sxs-lookup"><span data-stu-id="fbc1c-130">Maximum threads</span></span>

- <span data-ttu-id="fbc1c-131">ワーカー スレッド プールの最大スレッド数を指定します。</span><span class="sxs-lookup"><span data-stu-id="fbc1c-131">Specifies the maximum number of threads for the worker thread pool.</span></span>
- <span data-ttu-id="fbc1c-132"><xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> メソッドに対応します。</span><span class="sxs-lookup"><span data-stu-id="fbc1c-132">Corresponds to the <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="fbc1c-133">設定の名前</span><span class="sxs-lookup"><span data-stu-id="fbc1c-133">Setting name</span></span> | <span data-ttu-id="fbc1c-134">値</span><span class="sxs-lookup"><span data-stu-id="fbc1c-134">Values</span></span> |
| - | - | - |
| <span data-ttu-id="fbc1c-135">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="fbc1c-135">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MaxThreads` | <span data-ttu-id="fbc1c-136">最大スレッド数を表す整数</span><span class="sxs-lookup"><span data-stu-id="fbc1c-136">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="fbc1c-137">**MSBuild のプロパティ**</span><span class="sxs-lookup"><span data-stu-id="fbc1c-137">**MSBuild property**</span></span> | `ThreadPoolMaxThreads` | <span data-ttu-id="fbc1c-138">最大スレッド数を表す整数</span><span class="sxs-lookup"><span data-stu-id="fbc1c-138">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="fbc1c-139">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="fbc1c-139">**Environment variable**</span></span> | <span data-ttu-id="fbc1c-140">N/A</span><span class="sxs-lookup"><span data-stu-id="fbc1c-140">N/A</span></span> | <span data-ttu-id="fbc1c-141">N/A</span><span class="sxs-lookup"><span data-stu-id="fbc1c-141">N/A</span></span> |

### <a name="examples"></a><span data-ttu-id="fbc1c-142">使用例</span><span class="sxs-lookup"><span data-stu-id="fbc1c-142">Examples</span></span>

<span data-ttu-id="fbc1c-143">*runtimeconfig.json* ファイル:</span><span class="sxs-lookup"><span data-stu-id="fbc1c-143">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MaxThreads": 20
      }
   }
}
```

<span data-ttu-id="fbc1c-144">プロジェクト ファイル:</span><span class="sxs-lookup"><span data-stu-id="fbc1c-144">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
  </PropertyGroup>

</Project>
```
