---
title: dotnet tool run コマンド
description: dotnet tool run コマンドでは、ローカル ツールを起動します。
ms.date: 02/14/2020
ms.openlocfilehash: 05b21c0f5ea86f4b99b220f556c61bf83f464114
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543828"
---
# <a name="dotnet-tool-run"></a><span data-ttu-id="5b911-103">dotnet tool run</span><span class="sxs-lookup"><span data-stu-id="5b911-103">dotnet tool run</span></span>

<span data-ttu-id="5b911-104">**この記事の対象:** ✔️ .NET Core 3.0 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="5b911-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="5b911-105">名前</span><span class="sxs-lookup"><span data-stu-id="5b911-105">Name</span></span>

<span data-ttu-id="5b911-106">`dotnet tool run` - ローカル ツールを起動します。</span><span class="sxs-lookup"><span data-stu-id="5b911-106">`dotnet tool run` - Invokes a local tool.</span></span>

## <a name="synopsis"></a><span data-ttu-id="5b911-107">構文</span><span class="sxs-lookup"><span data-stu-id="5b911-107">Synopsis</span></span>

```dotnetcli
dotnet tool run <COMMAND NAME> 
dotnet tool run <-h|--help>
```

## <a name="description"></a><span data-ttu-id="5b911-108">説明</span><span class="sxs-lookup"><span data-stu-id="5b911-108">Description</span></span>

<span data-ttu-id="5b911-109">`dotnet tool run` コマンドでは、現在のディレクトリのスコープ内にあるツール マニフェスト ファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="5b911-109">The `dotnet tool run` command searches tool manifest files that are in scope for the current directory.</span></span> <span data-ttu-id="5b911-110">指定されたツールへの参照が見つかると、そのツールが実行されます。</span><span class="sxs-lookup"><span data-stu-id="5b911-110">When it finds a reference to the specified tool, it runs the tool.</span></span> <span data-ttu-id="5b911-111">詳細については、「[ローカル ツールの起動](global-tools.md#invoke-a-local-tool)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b911-111">For more information, see [Invoke a local tool](global-tools.md#invoke-a-local-tool).</span></span>

## <a name="arguments"></a><span data-ttu-id="5b911-112">引数</span><span class="sxs-lookup"><span data-stu-id="5b911-112">Arguments</span></span>

- **`COMMAND_NAME`**

  <span data-ttu-id="5b911-113">実行するツールのコマンド名。</span><span class="sxs-lookup"><span data-stu-id="5b911-113">The command name of the tool to run.</span></span>

## <a name="options"></a><span data-ttu-id="5b911-114">オプション</span><span class="sxs-lookup"><span data-stu-id="5b911-114">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="5b911-115">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="5b911-115">Prints out a short help for the command.</span></span>

## <a name="example"></a><span data-ttu-id="5b911-116">例</span><span class="sxs-lookup"><span data-stu-id="5b911-116">Example</span></span>

- **`dotnet tool run dotnetsay`**

  <span data-ttu-id="5b911-117">`dotnetsay` ローカル ツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="5b911-117">Runs the `dotnetsay` local tool.</span></span>

## <a name="see-also"></a><span data-ttu-id="5b911-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="5b911-118">See also</span></span>

- [<span data-ttu-id="5b911-119">.NET Core ツール</span><span class="sxs-lookup"><span data-stu-id="5b911-119">.NET Core tools</span></span>](global-tools.md)
