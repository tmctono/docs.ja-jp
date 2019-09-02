---
title: dotnet build-server コマンド
description: dotnet build-server コマンドは、ビルドによって起動されたサーバーとやり取りします。
ms.date: 04/24/2019
ms.openlocfilehash: b2dfd5f317466f18d9246bd1fb281a92c42f6d9d
ms.sourcegitcommit: 1b020356e421a9314dd525539da12463d980ce7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2019
ms.locfileid: "70168109"
---
# <a name="dotnet-build-server"></a><span data-ttu-id="060eb-103">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="060eb-103">dotnet build-server</span></span>

<span data-ttu-id="060eb-104">**この記事の対象: ✓** .NET Core 2.1 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="060eb-104">**This article applies to: ✓** .NET Core 2.1 SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]
-->

## <a name="name"></a><span data-ttu-id="060eb-105">name</span><span class="sxs-lookup"><span data-stu-id="060eb-105">Name</span></span>

<span data-ttu-id="060eb-106">`dotnet build-server` - ビルドによって起動されたサーバーとやり取りします。</span><span class="sxs-lookup"><span data-stu-id="060eb-106">`dotnet build-server` - Interacts with servers started by a build.</span></span>

## <a name="synopsis"></a><span data-ttu-id="060eb-107">構文</span><span class="sxs-lookup"><span data-stu-id="060eb-107">Synopsis</span></span>

```console
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a><span data-ttu-id="060eb-108">コマンド</span><span class="sxs-lookup"><span data-stu-id="060eb-108">Commands</span></span>

* **`shutdown`**

  <span data-ttu-id="060eb-109">dotnet から起動されるビルド サーバーをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="060eb-109">Shuts down build servers that are started from dotnet.</span></span> <span data-ttu-id="060eb-110">既定では、すべてのサーバーがシャットダウンされます。</span><span class="sxs-lookup"><span data-stu-id="060eb-110">By default, all servers are shut down.</span></span>

## <a name="options"></a><span data-ttu-id="060eb-111">オプション</span><span class="sxs-lookup"><span data-stu-id="060eb-111">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="060eb-112">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="060eb-112">Prints out a short help for the command.</span></span>

* **`--msbuild`**

  <span data-ttu-id="060eb-113">MSBuild ビルド サーバーをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="060eb-113">Shuts down the MSBuild build server.</span></span>

* **`--razor`**

  <span data-ttu-id="060eb-114">Razor ビルド サーバーをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="060eb-114">Shuts down the Razor build server.</span></span>

* **`--vbcscompiler`**

  <span data-ttu-id="060eb-115">VB/C# コンパイラ ビルド サーバーをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="060eb-115">Shuts down the VB/C# compiler build server.</span></span>
