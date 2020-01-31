---
title: dotnet build-server コマンド
description: dotnet build-server コマンドは、ビルドによって起動されたサーバーとやり取りします。
ms.date: 04/24/2019
ms.openlocfilehash: e77a4d9f49f555ac847bb13380380599eef881b1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734380"
---
# <a name="dotnet-build-server"></a><span data-ttu-id="c450c-103">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="c450c-103">dotnet build-server</span></span>

<span data-ttu-id="c450c-104">**この記事の対象:** ✔️ .NET Core 2.1 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="c450c-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]
-->

## <a name="name"></a><span data-ttu-id="c450c-105">名前</span><span class="sxs-lookup"><span data-stu-id="c450c-105">Name</span></span>

<span data-ttu-id="c450c-106">`dotnet build-server` - ビルドによって起動されたサーバーとやり取りします。</span><span class="sxs-lookup"><span data-stu-id="c450c-106">`dotnet build-server` - Interacts with servers started by a build.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c450c-107">構文</span><span class="sxs-lookup"><span data-stu-id="c450c-107">Synopsis</span></span>

```dotnetcli
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a><span data-ttu-id="c450c-108">コマンド</span><span class="sxs-lookup"><span data-stu-id="c450c-108">Commands</span></span>

- **`shutdown`**

  <span data-ttu-id="c450c-109">dotnet から起動されるビルド サーバーをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="c450c-109">Shuts down build servers that are started from dotnet.</span></span> <span data-ttu-id="c450c-110">既定では、すべてのサーバーがシャットダウンされます。</span><span class="sxs-lookup"><span data-stu-id="c450c-110">By default, all servers are shut down.</span></span>

## <a name="options"></a><span data-ttu-id="c450c-111">オプション</span><span class="sxs-lookup"><span data-stu-id="c450c-111">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="c450c-112">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="c450c-112">Prints out a short help for the command.</span></span>

- **`--msbuild`**

  <span data-ttu-id="c450c-113">MSBuild ビルド サーバーをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="c450c-113">Shuts down the MSBuild build server.</span></span>

- **`--razor`**

  <span data-ttu-id="c450c-114">Razor ビルド サーバーをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="c450c-114">Shuts down the Razor build server.</span></span>

- **`--vbcscompiler`**

  <span data-ttu-id="c450c-115">VB/C# コンパイラ ビルド サーバーをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="c450c-115">Shuts down the VB/C# compiler build server.</span></span>
