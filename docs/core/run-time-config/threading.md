---
title: スレッドの構成設定
description: .NET Core アプリのスレッドを構成するランタイム設定について説明します。
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 1c7c16993a07ef95223481791153b75ab2f61533
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2020
ms.locfileid: "83761929"
---
# <a name="run-time-configuration-options-for-threading"></a><span data-ttu-id="430be-103">スレッドのランタイム構成オプション</span><span class="sxs-lookup"><span data-stu-id="430be-103">Run-time configuration options for threading</span></span>

## <a name="cpu-groups"></a><span data-ttu-id="430be-104">CPU グループ</span><span class="sxs-lookup"><span data-stu-id="430be-104">CPU groups</span></span>

- <span data-ttu-id="430be-105">CPU グループ全体にスレッドを自動的に配布するかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="430be-105">Configures whether threads are automatically distributed across CPU groups.</span></span>
- <span data-ttu-id="430be-106">この設定を省略した場合、スレッドは CPU グループ間に分散されません。</span><span class="sxs-lookup"><span data-stu-id="430be-106">If you omit this setting, threads are not distributed across CPU groups.</span></span> <span data-ttu-id="430be-107">これは、値を `0` に設定した場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="430be-107">This is equivalent to setting the value to `0`.</span></span>

| | <span data-ttu-id="430be-108">設定の名前</span><span class="sxs-lookup"><span data-stu-id="430be-108">Setting name</span></span> | <span data-ttu-id="430be-109">値</span><span class="sxs-lookup"><span data-stu-id="430be-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="430be-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="430be-110">**runtimeconfig.json**</span></span> | <span data-ttu-id="430be-111">N/A</span><span class="sxs-lookup"><span data-stu-id="430be-111">N/A</span></span> | <span data-ttu-id="430be-112">N/A</span><span class="sxs-lookup"><span data-stu-id="430be-112">N/A</span></span> |
| <span data-ttu-id="430be-113">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="430be-113">**Environment variable**</span></span> | `COMPlus_Thread_UseAllCpuGroups` | <span data-ttu-id="430be-114">`0` - 無効</span><span class="sxs-lookup"><span data-stu-id="430be-114">`0` - disabled</span></span><br/><span data-ttu-id="430be-115">`1` - 有効</span><span class="sxs-lookup"><span data-stu-id="430be-115">`1` - enabled</span></span> |

## <a name="minimum-threads"></a><span data-ttu-id="430be-116">最小スレッド数</span><span class="sxs-lookup"><span data-stu-id="430be-116">Minimum threads</span></span>

- <span data-ttu-id="430be-117">ワーカー スレッド プールの最小スレッド数を指定します。</span><span class="sxs-lookup"><span data-stu-id="430be-117">Specifies the minimum number of threads for the worker thread pool.</span></span>
- <span data-ttu-id="430be-118"><xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> メソッドに対応します。</span><span class="sxs-lookup"><span data-stu-id="430be-118">Corresponds to the <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="430be-119">設定の名前</span><span class="sxs-lookup"><span data-stu-id="430be-119">Setting name</span></span> | <span data-ttu-id="430be-120">値</span><span class="sxs-lookup"><span data-stu-id="430be-120">Values</span></span> |
| - | - | - |
| <span data-ttu-id="430be-121">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="430be-121">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MinThreads` | <span data-ttu-id="430be-122">最小スレッド数を表す整数</span><span class="sxs-lookup"><span data-stu-id="430be-122">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="430be-123">**MSBuild のプロパティ**</span><span class="sxs-lookup"><span data-stu-id="430be-123">**MSBuild property**</span></span> | `ThreadPoolMinThreads` | <span data-ttu-id="430be-124">最小スレッド数を表す整数</span><span class="sxs-lookup"><span data-stu-id="430be-124">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="430be-125">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="430be-125">**Environment variable**</span></span> | <span data-ttu-id="430be-126">N/A</span><span class="sxs-lookup"><span data-stu-id="430be-126">N/A</span></span> | <span data-ttu-id="430be-127">N/A</span><span class="sxs-lookup"><span data-stu-id="430be-127">N/A</span></span> |

### <a name="examples"></a><span data-ttu-id="430be-128">使用例</span><span class="sxs-lookup"><span data-stu-id="430be-128">Examples</span></span>

<span data-ttu-id="430be-129">*runtimeconfig.json* ファイル:</span><span class="sxs-lookup"><span data-stu-id="430be-129">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MinThreads": 4
      }
   }
}
```

<span data-ttu-id="430be-130">プロジェクト ファイル:</span><span class="sxs-lookup"><span data-stu-id="430be-130">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
  </PropertyGroup>

</Project>
```

## <a name="maximum-threads"></a><span data-ttu-id="430be-131">最大スレッド数</span><span class="sxs-lookup"><span data-stu-id="430be-131">Maximum threads</span></span>

- <span data-ttu-id="430be-132">ワーカー スレッド プールの最大スレッド数を指定します。</span><span class="sxs-lookup"><span data-stu-id="430be-132">Specifies the maximum number of threads for the worker thread pool.</span></span>
- <span data-ttu-id="430be-133"><xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> メソッドに対応します。</span><span class="sxs-lookup"><span data-stu-id="430be-133">Corresponds to the <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="430be-134">設定の名前</span><span class="sxs-lookup"><span data-stu-id="430be-134">Setting name</span></span> | <span data-ttu-id="430be-135">値</span><span class="sxs-lookup"><span data-stu-id="430be-135">Values</span></span> |
| - | - | - |
| <span data-ttu-id="430be-136">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="430be-136">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MaxThreads` | <span data-ttu-id="430be-137">最大スレッド数を表す整数</span><span class="sxs-lookup"><span data-stu-id="430be-137">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="430be-138">**MSBuild のプロパティ**</span><span class="sxs-lookup"><span data-stu-id="430be-138">**MSBuild property**</span></span> | `ThreadPoolMaxThreads` | <span data-ttu-id="430be-139">最大スレッド数を表す整数</span><span class="sxs-lookup"><span data-stu-id="430be-139">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="430be-140">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="430be-140">**Environment variable**</span></span> | <span data-ttu-id="430be-141">N/A</span><span class="sxs-lookup"><span data-stu-id="430be-141">N/A</span></span> | <span data-ttu-id="430be-142">N/A</span><span class="sxs-lookup"><span data-stu-id="430be-142">N/A</span></span> |

### <a name="examples"></a><span data-ttu-id="430be-143">使用例</span><span class="sxs-lookup"><span data-stu-id="430be-143">Examples</span></span>

<span data-ttu-id="430be-144">*runtimeconfig.json* ファイル:</span><span class="sxs-lookup"><span data-stu-id="430be-144">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MaxThreads": 20
      }
   }
}
```

<span data-ttu-id="430be-145">プロジェクト ファイル:</span><span class="sxs-lookup"><span data-stu-id="430be-145">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
  </PropertyGroup>

</Project>
```
