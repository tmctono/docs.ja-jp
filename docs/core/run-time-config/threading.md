---
title: スレッドの構成設定
description: .NET Core アプリのスレッドを構成するランタイム設定について説明します。
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 6a920dbc301830e3f4c95bf637ff3de6d4f464ff
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/04/2019
ms.locfileid: "74998829"
---
# <a name="run-time-configuration-options-for-threading"></a><span data-ttu-id="e12c3-103">スレッドのランタイム構成オプション</span><span class="sxs-lookup"><span data-stu-id="e12c3-103">Run-time configuration options for threading</span></span>

## <a name="cpu-groups"></a><span data-ttu-id="e12c3-104">CPU グループ</span><span class="sxs-lookup"><span data-stu-id="e12c3-104">CPU groups</span></span>

- <span data-ttu-id="e12c3-105">CPU グループ全体にスレッドを自動的に配布するかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="e12c3-105">Configures whether threads are automatically distributed across CPU groups.</span></span>
- <span data-ttu-id="e12c3-106">既定:無効 (`0`)。</span><span class="sxs-lookup"><span data-stu-id="e12c3-106">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="e12c3-107">設定の名前</span><span class="sxs-lookup"><span data-stu-id="e12c3-107">Setting name</span></span> | <span data-ttu-id="e12c3-108">値</span><span class="sxs-lookup"><span data-stu-id="e12c3-108">Values</span></span> |
| - | - | - |
| <span data-ttu-id="e12c3-109">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="e12c3-109">**runtimeconfig.json**</span></span> | <span data-ttu-id="e12c3-110">N/A</span><span class="sxs-lookup"><span data-stu-id="e12c3-110">N/A</span></span> | <span data-ttu-id="e12c3-111">N/A</span><span class="sxs-lookup"><span data-stu-id="e12c3-111">N/A</span></span> |
| <span data-ttu-id="e12c3-112">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="e12c3-112">**Environment variable**</span></span> | `COMPlus_Thread_UseAllCpuGroups` | <span data-ttu-id="e12c3-113">`0` - 無効</span><span class="sxs-lookup"><span data-stu-id="e12c3-113">`0` - disabled</span></span><br/><span data-ttu-id="e12c3-114">`1` - 有効</span><span class="sxs-lookup"><span data-stu-id="e12c3-114">`1` - enabled</span></span> |

## <a name="minimum-threads"></a><span data-ttu-id="e12c3-115">最小スレッド数</span><span class="sxs-lookup"><span data-stu-id="e12c3-115">Minimum threads</span></span>

- <span data-ttu-id="e12c3-116">ワーカー スレッドプールの最小スレッド数を指定します。</span><span class="sxs-lookup"><span data-stu-id="e12c3-116">Specifies the minimum number of threads for the worker threadpool.</span></span>
- <span data-ttu-id="e12c3-117"><xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> メソッドに対応します。</span><span class="sxs-lookup"><span data-stu-id="e12c3-117">Corresponds to the <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="e12c3-118">設定の名前</span><span class="sxs-lookup"><span data-stu-id="e12c3-118">Setting name</span></span> | <span data-ttu-id="e12c3-119">値</span><span class="sxs-lookup"><span data-stu-id="e12c3-119">Values</span></span> |
| - | - | - |
| <span data-ttu-id="e12c3-120">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="e12c3-120">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MinThreads` | <span data-ttu-id="e12c3-121">最小スレッド数を表す整数</span><span class="sxs-lookup"><span data-stu-id="e12c3-121">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="e12c3-122">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="e12c3-122">**Environment variable**</span></span> | <span data-ttu-id="e12c3-123">N/A</span><span class="sxs-lookup"><span data-stu-id="e12c3-123">N/A</span></span> | <span data-ttu-id="e12c3-124">N/A</span><span class="sxs-lookup"><span data-stu-id="e12c3-124">N/A</span></span> |

## <a name="maximum-threads"></a><span data-ttu-id="e12c3-125">最大スレッド数</span><span class="sxs-lookup"><span data-stu-id="e12c3-125">Maximum threads</span></span>

- <span data-ttu-id="e12c3-126">ワーカー スレッドプールの最大スレッド数を指定します。</span><span class="sxs-lookup"><span data-stu-id="e12c3-126">Specifies the maximum number of threads for the worker threadpool.</span></span>
- <span data-ttu-id="e12c3-127"><xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> メソッドに対応します。</span><span class="sxs-lookup"><span data-stu-id="e12c3-127">Corresponds to the <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="e12c3-128">設定の名前</span><span class="sxs-lookup"><span data-stu-id="e12c3-128">Setting name</span></span> | <span data-ttu-id="e12c3-129">値</span><span class="sxs-lookup"><span data-stu-id="e12c3-129">Values</span></span> |
| - | - | - |
| <span data-ttu-id="e12c3-130">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="e12c3-130">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MaxThreads` | <span data-ttu-id="e12c3-131">最大スレッド数を表す整数</span><span class="sxs-lookup"><span data-stu-id="e12c3-131">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="e12c3-132">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="e12c3-132">**Environment variable**</span></span> | <span data-ttu-id="e12c3-133">N/A</span><span class="sxs-lookup"><span data-stu-id="e12c3-133">N/A</span></span> | <span data-ttu-id="e12c3-134">N/A</span><span class="sxs-lookup"><span data-stu-id="e12c3-134">N/A</span></span> |
