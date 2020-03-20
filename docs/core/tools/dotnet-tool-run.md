---
title: dotnet tool run コマンド
description: dotnet tool run コマンドでは、ローカル ツールを起動します。
ms.date: 02/14/2020
ms.openlocfilehash: a088cd0b7f4bba014234a8189a42a63aa6d88f4e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "78847847"
---
# <a name="dotnet-tool-run"></a><span data-ttu-id="522ea-103">dotnet tool run</span><span class="sxs-lookup"><span data-stu-id="522ea-103">dotnet tool run</span></span>

<span data-ttu-id="522ea-104">**この記事の対象:** ✔️ .NET Core 3.0 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="522ea-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="522ea-105">名前</span><span class="sxs-lookup"><span data-stu-id="522ea-105">Name</span></span>

<span data-ttu-id="522ea-106">`dotnet tool run` - ローカル ツールを起動します。</span><span class="sxs-lookup"><span data-stu-id="522ea-106">`dotnet tool run` - Invokes a local tool.</span></span>

## <a name="synopsis"></a><span data-ttu-id="522ea-107">構文</span><span class="sxs-lookup"><span data-stu-id="522ea-107">Synopsis</span></span>

```dotnetcli
dotnet tool run <COMMAND NAME>

dotnet tool run <-h|--help>
```

## <a name="description"></a><span data-ttu-id="522ea-108">説明</span><span class="sxs-lookup"><span data-stu-id="522ea-108">Description</span></span>

<span data-ttu-id="522ea-109">`dotnet tool run` コマンドでは、現在のディレクトリのスコープ内にあるツール マニフェスト ファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="522ea-109">The `dotnet tool run` command searches tool manifest files that are in scope for the current directory.</span></span> <span data-ttu-id="522ea-110">指定されたツールへの参照が見つかると、そのツールが実行されます。</span><span class="sxs-lookup"><span data-stu-id="522ea-110">When it finds a reference to the specified tool, it runs the tool.</span></span> <span data-ttu-id="522ea-111">詳細については、「[ローカル ツールの起動](global-tools.md#invoke-a-local-tool)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="522ea-111">For more information, see [Invoke a local tool](global-tools.md#invoke-a-local-tool).</span></span>

## <a name="arguments"></a><span data-ttu-id="522ea-112">引数</span><span class="sxs-lookup"><span data-stu-id="522ea-112">Arguments</span></span>

- **`COMMAND_NAME`**

  <span data-ttu-id="522ea-113">実行するツールのコマンド名。</span><span class="sxs-lookup"><span data-stu-id="522ea-113">The command name of the tool to run.</span></span>

## <a name="options"></a><span data-ttu-id="522ea-114">オプション</span><span class="sxs-lookup"><span data-stu-id="522ea-114">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="522ea-115">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="522ea-115">Prints out a short help for the command.</span></span>

## <a name="example"></a><span data-ttu-id="522ea-116">例</span><span class="sxs-lookup"><span data-stu-id="522ea-116">Example</span></span>

- **`dotnet tool run dotnetsay`**

  <span data-ttu-id="522ea-117">`dotnetsay` ローカル ツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="522ea-117">Runs the `dotnetsay` local tool.</span></span>

## <a name="see-also"></a><span data-ttu-id="522ea-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="522ea-118">See also</span></span>

- [<span data-ttu-id="522ea-119">.NET Core ツール</span><span class="sxs-lookup"><span data-stu-id="522ea-119">.NET Core tools</span></span>](global-tools.md)
- [<span data-ttu-id="522ea-120">チュートリアル: .NET Core CLI を使って .NET Core ローカル ツールをインストールして使用する</span><span class="sxs-lookup"><span data-stu-id="522ea-120">Tutorial: Install and use a .NET Core local tool using the .NET Core CLI</span></span>](local-tools-how-to-use.md)
