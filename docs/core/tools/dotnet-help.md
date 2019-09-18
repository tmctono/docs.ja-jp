---
title: dotnet help コマンド
description: dotnet help コマンドでは、指定したコマンドについてより詳細なドキュメントがオンラインで表示されます。
ms.date: 08/08/2019
ms.openlocfilehash: e76f858f2529afc50646473f1aab9d52730cff16
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2019
ms.locfileid: "70990460"
---
# <a name="dotnet-help-reference"></a><span data-ttu-id="d52ed-103">dotnet help reference</span><span class="sxs-lookup"><span data-stu-id="d52ed-103">dotnet help reference</span></span>

<span data-ttu-id="d52ed-104">**この記事の対象: ✓** .NET Core 2.0 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="d52ed-104">**This article applies to: ✓** .NET Core 2.0 SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]
-->

## <a name="name"></a><span data-ttu-id="d52ed-105">name</span><span class="sxs-lookup"><span data-stu-id="d52ed-105">Name</span></span>

<span data-ttu-id="d52ed-106">`dotnet help` - 指定したコマンドについて、より詳細なドキュメントがオンラインで表示されます。</span><span class="sxs-lookup"><span data-stu-id="d52ed-106">`dotnet help` - Shows more detailed documentation online for the specified command.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d52ed-107">構文</span><span class="sxs-lookup"><span data-stu-id="d52ed-107">Synopsis</span></span>

`dotnet help <COMMAND_NAME> [-h|--help]`

## <a name="description"></a><span data-ttu-id="d52ed-108">説明</span><span class="sxs-lookup"><span data-stu-id="d52ed-108">Description</span></span>

<span data-ttu-id="d52ed-109">`dotnet help` コマンドは、docs.microsoft.com で、指定したコマンドに関する詳細情報のリファレンス ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="d52ed-109">The `dotnet help` command opens up the reference page for more detailed information about the specified command at docs.microsoft.com.</span></span>

## <a name="arguments"></a><span data-ttu-id="d52ed-110">引数</span><span class="sxs-lookup"><span data-stu-id="d52ed-110">Arguments</span></span>

* **`COMMAND_NAME`**

  <span data-ttu-id="d52ed-111">.NET Core CLI コマンドの名前です。</span><span class="sxs-lookup"><span data-stu-id="d52ed-111">Name of the .NET Core CLI command.</span></span> <span data-ttu-id="d52ed-112">有効な CLI コマンドの一覧については、[CLI コマンド](index.md#cli-commands)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d52ed-112">For a list of the valid CLI commands, see [CLI commands](index.md#cli-commands).</span></span>

## <a name="options"></a><span data-ttu-id="d52ed-113">オプション</span><span class="sxs-lookup"><span data-stu-id="d52ed-113">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="d52ed-114">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="d52ed-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="d52ed-115">使用例</span><span class="sxs-lookup"><span data-stu-id="d52ed-115">Examples</span></span>

* <span data-ttu-id="d52ed-116">ドキュメントの [dotnet new](dotnet-new.md) コマンドに関するページを開きます。</span><span class="sxs-lookup"><span data-stu-id="d52ed-116">Opens the documentation page for the [dotnet new](dotnet-new.md) command:</span></span>

  ```console
  dotnet help new
  ```
