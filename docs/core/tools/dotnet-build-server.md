---
title: dotnet build-server コマンド
description: dotnet build-server コマンドは、ビルドによって起動されたサーバーとやり取りします。
ms.date: 02/14/2020
ms.openlocfilehash: 882b697c07aac0e20266f3ad4e6c11888a0b7acc
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463722"
---
# <a name="dotnet-build-server"></a><span data-ttu-id="498c5-103">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="498c5-103">dotnet build-server</span></span>

<span data-ttu-id="498c5-104">**この記事の対象:** ✔️ .NET Core 2.1 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="498c5-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="498c5-105">name</span><span class="sxs-lookup"><span data-stu-id="498c5-105">Name</span></span>

<span data-ttu-id="498c5-106">`dotnet build-server` - ビルドによって起動されたサーバーとやり取りします。</span><span class="sxs-lookup"><span data-stu-id="498c5-106">`dotnet build-server` - Interacts with servers started by a build.</span></span>

## <a name="synopsis"></a><span data-ttu-id="498c5-107">構文</span><span class="sxs-lookup"><span data-stu-id="498c5-107">Synopsis</span></span>

```dotnetcli
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]

dotnet build-server shutdown -h|--help

dotnet build-server -h|--help
```

## <a name="commands"></a><span data-ttu-id="498c5-108">コマンド</span><span class="sxs-lookup"><span data-stu-id="498c5-108">Commands</span></span>

- **`shutdown`**

  <span data-ttu-id="498c5-109">dotnet から起動されるビルド サーバーをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="498c5-109">Shuts down build servers that are started from dotnet.</span></span> <span data-ttu-id="498c5-110">既定では、すべてのサーバーがシャットダウンされます。</span><span class="sxs-lookup"><span data-stu-id="498c5-110">By default, all servers are shut down.</span></span>

## <a name="options"></a><span data-ttu-id="498c5-111">オプション</span><span class="sxs-lookup"><span data-stu-id="498c5-111">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="498c5-112">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="498c5-112">Prints out a short help for the command.</span></span>

- **`--msbuild`**

  <span data-ttu-id="498c5-113">MSBuild ビルド サーバーをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="498c5-113">Shuts down the MSBuild build server.</span></span>

- **`--razor`**

  <span data-ttu-id="498c5-114">Razor ビルド サーバーをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="498c5-114">Shuts down the Razor build server.</span></span>

- **`--vbcscompiler`**

  <span data-ttu-id="498c5-115">VB/C# コンパイラ ビルド サーバーをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="498c5-115">Shuts down the VB/C# compiler build server.</span></span>
