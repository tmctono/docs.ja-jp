---
title: dotnet build-server コマンド
description: dotnet build-server コマンドは、ビルドによって起動されたサーバーとやり取りします。
ms.date: 02/14/2020
ms.openlocfilehash: a6a9cd6de66371caef66d1101b3f844dffc771ef
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503781"
---
# <a name="dotnet-build-server"></a><span data-ttu-id="05393-103">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="05393-103">dotnet build-server</span></span>

<span data-ttu-id="05393-104">**この記事の対象:** ✔️ .NET Core 2.1 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="05393-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="05393-105">名前</span><span class="sxs-lookup"><span data-stu-id="05393-105">Name</span></span>

<span data-ttu-id="05393-106">`dotnet build-server` - ビルドによって起動されたサーバーとやり取りします。</span><span class="sxs-lookup"><span data-stu-id="05393-106">`dotnet build-server` - Interacts with servers started by a build.</span></span>

## <a name="synopsis"></a><span data-ttu-id="05393-107">構文</span><span class="sxs-lookup"><span data-stu-id="05393-107">Synopsis</span></span>

```dotnetcli
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a><span data-ttu-id="05393-108">コマンド</span><span class="sxs-lookup"><span data-stu-id="05393-108">Commands</span></span>

- **`shutdown`**

  <span data-ttu-id="05393-109">dotnet から起動されるビルド サーバーをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="05393-109">Shuts down build servers that are started from dotnet.</span></span> <span data-ttu-id="05393-110">既定では、すべてのサーバーがシャットダウンされます。</span><span class="sxs-lookup"><span data-stu-id="05393-110">By default, all servers are shut down.</span></span>

## <a name="options"></a><span data-ttu-id="05393-111">オプション</span><span class="sxs-lookup"><span data-stu-id="05393-111">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="05393-112">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="05393-112">Prints out a short help for the command.</span></span>

- **`--msbuild`**

  <span data-ttu-id="05393-113">MSBuild ビルド サーバーをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="05393-113">Shuts down the MSBuild build server.</span></span>

- **`--razor`**

  <span data-ttu-id="05393-114">Razor ビルド サーバーをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="05393-114">Shuts down the Razor build server.</span></span>

- **`--vbcscompiler`**

  <span data-ttu-id="05393-115">VB/C# コンパイラ ビルド サーバーをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="05393-115">Shuts down the VB/C# compiler build server.</span></span>
