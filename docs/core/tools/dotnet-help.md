---
title: dotnet help コマンド
description: dotnet help コマンドでは、指定したコマンドについてより詳細なドキュメントがオンラインで表示されます。
ms.date: 02/14/2020
ms.openlocfilehash: a59e74a318118b6fd39d1895df02d76daa6fc9e1
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463692"
---
# <a name="dotnet-help-reference"></a><span data-ttu-id="63d37-103">dotnet help リファレンス</span><span class="sxs-lookup"><span data-stu-id="63d37-103">dotnet help reference</span></span>

<span data-ttu-id="63d37-104">**この記事の対象:** ✔️ .NET Core 2.0 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="63d37-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="63d37-105">name</span><span class="sxs-lookup"><span data-stu-id="63d37-105">Name</span></span>

<span data-ttu-id="63d37-106">`dotnet help` - 指定したコマンドについて、より詳細なドキュメントがオンラインで表示されます。</span><span class="sxs-lookup"><span data-stu-id="63d37-106">`dotnet help` - Shows more detailed documentation online for the specified command.</span></span>

## <a name="synopsis"></a><span data-ttu-id="63d37-107">構文</span><span class="sxs-lookup"><span data-stu-id="63d37-107">Synopsis</span></span>

```dotnetcli
dotnet help <COMMAND_NAME> [-h|--help]
```

## <a name="description"></a><span data-ttu-id="63d37-108">[説明]</span><span class="sxs-lookup"><span data-stu-id="63d37-108">Description</span></span>

<span data-ttu-id="63d37-109">`dotnet help` コマンドは、docs.microsoft.com で、指定したコマンドに関する詳細情報のリファレンス ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="63d37-109">The `dotnet help` command opens up the reference page for more detailed information about the specified command at docs.microsoft.com.</span></span>

## <a name="arguments"></a><span data-ttu-id="63d37-110">引数</span><span class="sxs-lookup"><span data-stu-id="63d37-110">Arguments</span></span>

- **`COMMAND_NAME`**

  <span data-ttu-id="63d37-111">.NET Core CLI コマンドの名前です。</span><span class="sxs-lookup"><span data-stu-id="63d37-111">Name of the .NET Core CLI command.</span></span> <span data-ttu-id="63d37-112">有効な CLI コマンドの一覧については、[CLI コマンド](index.md#cli-commands)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63d37-112">For a list of the valid CLI commands, see [CLI commands](index.md#cli-commands).</span></span>

## <a name="options"></a><span data-ttu-id="63d37-113">オプション</span><span class="sxs-lookup"><span data-stu-id="63d37-113">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="63d37-114">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="63d37-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="63d37-115">例</span><span class="sxs-lookup"><span data-stu-id="63d37-115">Examples</span></span>

- <span data-ttu-id="63d37-116">ドキュメントの [dotnet new](dotnet-new.md) コマンドに関するページを開きます。</span><span class="sxs-lookup"><span data-stu-id="63d37-116">Opens the documentation page for the [dotnet new](dotnet-new.md) command:</span></span>

  ```dotnetcli
  dotnet help new
  ```
