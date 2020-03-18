---
title: スレッドの構成設定
description: .NET Core アプリのスレッドを構成するランタイム設定について説明します。
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 68b8e93ca6ec3f708a7a627307655ada1955500a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "76789847"
---
# <a name="run-time-configuration-options-for-threading"></a><span data-ttu-id="4ddac-103">スレッドのランタイム構成オプション</span><span class="sxs-lookup"><span data-stu-id="4ddac-103">Run-time configuration options for threading</span></span>

## <a name="cpu-groups"></a><span data-ttu-id="4ddac-104">CPU グループ</span><span class="sxs-lookup"><span data-stu-id="4ddac-104">CPU groups</span></span>

- <span data-ttu-id="4ddac-105">CPU グループ全体にスレッドを自動的に配布するかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="4ddac-105">Configures whether threads are automatically distributed across CPU groups.</span></span>
- <span data-ttu-id="4ddac-106">既定:無効 (`0`)。</span><span class="sxs-lookup"><span data-stu-id="4ddac-106">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="4ddac-107">設定の名前</span><span class="sxs-lookup"><span data-stu-id="4ddac-107">Setting name</span></span> | <span data-ttu-id="4ddac-108">値</span><span class="sxs-lookup"><span data-stu-id="4ddac-108">Values</span></span> |
| - | - | - |
| <span data-ttu-id="4ddac-109">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="4ddac-109">**runtimeconfig.json**</span></span> | <span data-ttu-id="4ddac-110">N/A</span><span class="sxs-lookup"><span data-stu-id="4ddac-110">N/A</span></span> | <span data-ttu-id="4ddac-111">N/A</span><span class="sxs-lookup"><span data-stu-id="4ddac-111">N/A</span></span> |
| <span data-ttu-id="4ddac-112">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="4ddac-112">**Environment variable**</span></span> | `COMPlus_Thread_UseAllCpuGroups` | <span data-ttu-id="4ddac-113">`0` - 無効</span><span class="sxs-lookup"><span data-stu-id="4ddac-113">`0` - disabled</span></span><br/><span data-ttu-id="4ddac-114">`1` - 有効</span><span class="sxs-lookup"><span data-stu-id="4ddac-114">`1` - enabled</span></span> |

## <a name="minimum-threads"></a><span data-ttu-id="4ddac-115">最小スレッド数</span><span class="sxs-lookup"><span data-stu-id="4ddac-115">Minimum threads</span></span>

- <span data-ttu-id="4ddac-116">ワーカー スレッド プールの最小スレッド数を指定します。</span><span class="sxs-lookup"><span data-stu-id="4ddac-116">Specifies the minimum number of threads for the worker thread pool.</span></span>
- <span data-ttu-id="4ddac-117"><xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> メソッドに対応します。</span><span class="sxs-lookup"><span data-stu-id="4ddac-117">Corresponds to the <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="4ddac-118">設定の名前</span><span class="sxs-lookup"><span data-stu-id="4ddac-118">Setting name</span></span> | <span data-ttu-id="4ddac-119">値</span><span class="sxs-lookup"><span data-stu-id="4ddac-119">Values</span></span> |
| - | - | - |
| <span data-ttu-id="4ddac-120">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="4ddac-120">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MinThreads` | <span data-ttu-id="4ddac-121">最小スレッド数を表す整数</span><span class="sxs-lookup"><span data-stu-id="4ddac-121">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="4ddac-122">**MSBuild のプロパティ**</span><span class="sxs-lookup"><span data-stu-id="4ddac-122">**MSBuild property**</span></span> | `ThreadPoolMinThreads` | <span data-ttu-id="4ddac-123">最小スレッド数を表す整数</span><span class="sxs-lookup"><span data-stu-id="4ddac-123">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="4ddac-124">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="4ddac-124">**Environment variable**</span></span> | <span data-ttu-id="4ddac-125">N/A</span><span class="sxs-lookup"><span data-stu-id="4ddac-125">N/A</span></span> | <span data-ttu-id="4ddac-126">N/A</span><span class="sxs-lookup"><span data-stu-id="4ddac-126">N/A</span></span> |

### <a name="examples"></a><span data-ttu-id="4ddac-127">使用例</span><span class="sxs-lookup"><span data-stu-id="4ddac-127">Examples</span></span>

<span data-ttu-id="4ddac-128">*runtimeconfig.json* ファイル:</span><span class="sxs-lookup"><span data-stu-id="4ddac-128">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MinThreads": 4
      }
   }
}
```

<span data-ttu-id="4ddac-129">プロジェクト ファイル:</span><span class="sxs-lookup"><span data-stu-id="4ddac-129">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
  </PropertyGroup>

</Project>
```

## <a name="maximum-threads"></a><span data-ttu-id="4ddac-130">最大スレッド数</span><span class="sxs-lookup"><span data-stu-id="4ddac-130">Maximum threads</span></span>

- <span data-ttu-id="4ddac-131">ワーカー スレッド プールの最大スレッド数を指定します。</span><span class="sxs-lookup"><span data-stu-id="4ddac-131">Specifies the maximum number of threads for the worker thread pool.</span></span>
- <span data-ttu-id="4ddac-132"><xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> メソッドに対応します。</span><span class="sxs-lookup"><span data-stu-id="4ddac-132">Corresponds to the <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="4ddac-133">設定の名前</span><span class="sxs-lookup"><span data-stu-id="4ddac-133">Setting name</span></span> | <span data-ttu-id="4ddac-134">値</span><span class="sxs-lookup"><span data-stu-id="4ddac-134">Values</span></span> |
| - | - | - |
| <span data-ttu-id="4ddac-135">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="4ddac-135">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MaxThreads` | <span data-ttu-id="4ddac-136">最大スレッド数を表す整数</span><span class="sxs-lookup"><span data-stu-id="4ddac-136">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="4ddac-137">**MSBuild のプロパティ**</span><span class="sxs-lookup"><span data-stu-id="4ddac-137">**MSBuild property**</span></span> | `ThreadPoolMaxThreads` | <span data-ttu-id="4ddac-138">最大スレッド数を表す整数</span><span class="sxs-lookup"><span data-stu-id="4ddac-138">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="4ddac-139">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="4ddac-139">**Environment variable**</span></span> | <span data-ttu-id="4ddac-140">N/A</span><span class="sxs-lookup"><span data-stu-id="4ddac-140">N/A</span></span> | <span data-ttu-id="4ddac-141">N/A</span><span class="sxs-lookup"><span data-stu-id="4ddac-141">N/A</span></span> |

### <a name="examples"></a><span data-ttu-id="4ddac-142">使用例</span><span class="sxs-lookup"><span data-stu-id="4ddac-142">Examples</span></span>

<span data-ttu-id="4ddac-143">*runtimeconfig.json* ファイル:</span><span class="sxs-lookup"><span data-stu-id="4ddac-143">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MaxThreads": 20
      }
   }
}
```

<span data-ttu-id="4ddac-144">プロジェクト ファイル:</span><span class="sxs-lookup"><span data-stu-id="4ddac-144">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
  </PropertyGroup>

</Project>
```
