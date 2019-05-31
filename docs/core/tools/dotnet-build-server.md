---
title: dotnet build-server コマンド
description: dotnet build-server コマンドは、ビルドによって起動されたサーバーとやり取りします。
ms.date: 04/24/2019
ms.openlocfilehash: fa663bc045e8abfc3375a0226be7d16331b49740
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632097"
---
# <a name="dotnet-build-server"></a><span data-ttu-id="4b6b0-103">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="4b6b0-103">dotnet build-server</span></span>

<span data-ttu-id="4b6b0-104">**この記事の対象: ✓** .NET Core 2.1 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="4b6b0-104">**This article applies to: ✓** .NET Core 2.1 SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]
-->

## <a name="name"></a><span data-ttu-id="4b6b0-105">name</span><span class="sxs-lookup"><span data-stu-id="4b6b0-105">Name</span></span>

<span data-ttu-id="4b6b0-106">`dotnet build-server` - ビルドによって起動されたサーバーとやり取りします。</span><span class="sxs-lookup"><span data-stu-id="4b6b0-106">`dotnet build-server` - Interacts with servers started by a build.</span></span>

## <a name="synopsis"></a><span data-ttu-id="4b6b0-107">構文</span><span class="sxs-lookup"><span data-stu-id="4b6b0-107">Synopsis</span></span>

```
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a><span data-ttu-id="4b6b0-108">コマンド</span><span class="sxs-lookup"><span data-stu-id="4b6b0-108">Commands</span></span>

* **`shutdown`**

  <span data-ttu-id="4b6b0-109">dotnet から起動されるビルド サーバーをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="4b6b0-109">Shuts down build servers that are started from dotnet.</span></span> <span data-ttu-id="4b6b0-110">既定では、すべてのサーバーがシャットダウンされます。</span><span class="sxs-lookup"><span data-stu-id="4b6b0-110">By default, all servers are shut down.</span></span>

## <a name="options"></a><span data-ttu-id="4b6b0-111">オプション</span><span class="sxs-lookup"><span data-stu-id="4b6b0-111">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="4b6b0-112">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="4b6b0-112">Prints out a short help for the command.</span></span>

* **`--msbuild`**

  <span data-ttu-id="4b6b0-113">MSBuild ビルド サーバーをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="4b6b0-113">Shuts down the MSBuild build server.</span></span>

* **`--razor`**

  <span data-ttu-id="4b6b0-114">Razor ビルド サーバーをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="4b6b0-114">Shuts down the Razor build server.</span></span>

* **`--vbcscompiler`**

  <span data-ttu-id="4b6b0-115">VB/C# コンパイラ ビルド サーバーをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="4b6b0-115">Shuts down the VB/C# compiler build server.</span></span>
