---
title: コンパイルの構成設定
description: .NET Core アプリの JIT コンパイラの動作方法を構成するランタイム設定について説明します。
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: bcc445b6edc48d9432ee614b0b19c9c25621f4a0
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/04/2019
ms.locfileid: "74998877"
---
# <a name="run-time-configuration-options-for-compilation"></a><span data-ttu-id="bda60-103">コンパイルのランタイム構成オプション</span><span class="sxs-lookup"><span data-stu-id="bda60-103">Run-time configuration options for compilation</span></span>

## <a name="tiered-compilation"></a><span data-ttu-id="bda60-104">階層型コンパイル</span><span class="sxs-lookup"><span data-stu-id="bda60-104">Tiered compilation</span></span>

- <span data-ttu-id="bda60-105">JIT コンパイラで[階層型コンパイル](../whats-new/dotnet-core-3-0.md#tiered-compilation)を使用するかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="bda60-105">Configures whether the JIT compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span>
- <span data-ttu-id="bda60-106">.NET Core 3.0 以降、階層型コンパイルは既定で有効に設定されます。</span><span class="sxs-lookup"><span data-stu-id="bda60-106">In .NET Core 3.0 and later, tiered compilation is enabled by default.</span></span>
- <span data-ttu-id="bda60-107">.NET Core 2.1 および 2.2 では、階層型コンパイルは既定で無効に設定されます。</span><span class="sxs-lookup"><span data-stu-id="bda60-107">In .NET Core 2.1 and 2.2, tiered compilation is disabled by default.</span></span>

| | <span data-ttu-id="bda60-108">設定の名前</span><span class="sxs-lookup"><span data-stu-id="bda60-108">Setting name</span></span> | <span data-ttu-id="bda60-109">値</span><span class="sxs-lookup"><span data-stu-id="bda60-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="bda60-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="bda60-110">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation` | <span data-ttu-id="bda60-111">`true` - 有効</span><span class="sxs-lookup"><span data-stu-id="bda60-111">`true` - enabled</span></span><br/><span data-ttu-id="bda60-112">`false` - 無効</span><span class="sxs-lookup"><span data-stu-id="bda60-112">`false` - disabled</span></span> |
| <span data-ttu-id="bda60-113">**環境変数**</span><span class="sxs-lookup"><span data-stu-id="bda60-113">**Environment variable**</span></span> | `COMPlus_TieredCompilation` | <span data-ttu-id="bda60-114">`1` - 有効</span><span class="sxs-lookup"><span data-stu-id="bda60-114">`1` - enabled</span></span><br/><span data-ttu-id="bda60-115">`0` - 無効</span><span class="sxs-lookup"><span data-stu-id="bda60-115">`0` - disabled</span></span> |
