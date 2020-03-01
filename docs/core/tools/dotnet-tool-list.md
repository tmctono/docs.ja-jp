---
title: dotnet tool list コマンド
description: dotnet tool list コマンドでは、お使いのコンピューターにインストールされている .NET Core ツールの一覧を表示します。
ms.date: 02/14/2020
ms.openlocfilehash: f231dcfe64a925f75f948d508e7a2d83befd9a00
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156986"
---
# <a name="dotnet-tool-list"></a><span data-ttu-id="0fb96-103">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="0fb96-103">dotnet tool list</span></span>

<span data-ttu-id="0fb96-104">**この記事の対象:** ✔️ .NET Core 2.1 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="0fb96-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="0fb96-105">名前</span><span class="sxs-lookup"><span data-stu-id="0fb96-105">Name</span></span>

<span data-ttu-id="0fb96-106">`dotnet tool list` - お使いのコンピューター上に現在インストールされている指定した種類のすべての [.NET Core ツール](global-tools.md)を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="0fb96-106">`dotnet tool list` - Lists all [.NET Core tools](global-tools.md) of the specified type currently installed on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="0fb96-107">構文</span><span class="sxs-lookup"><span data-stu-id="0fb96-107">Synopsis</span></span>

```dotnetcli
dotnet tool list <-g|--global>
dotnet tool list <--tool-path>
dotnet tool list
dotnet tool list <-h|--help>
```

## <a name="description"></a><span data-ttu-id="0fb96-108">説明</span><span class="sxs-lookup"><span data-stu-id="0fb96-108">Description</span></span>

<span data-ttu-id="0fb96-109">`dotnet tool list` コマンドでは、お使いのコンピューター上にインストールされている .NET Core グローバル、ツールパス、またはローカルのすべてのツールを一覧表示する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="0fb96-109">The `dotnet tool list` command provides a way for you to list all .NET Core global, tool-path, or local Tools installed on your machine.</span></span> <span data-ttu-id="0fb96-110">コマンドでは、パッケージ名、インストールされているバージョン、およびツール コマンドを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="0fb96-110">The command lists the package name, version installed, and the tool command.</span></span>  <span data-ttu-id="0fb96-111">コマンドを使用するには、次のいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="0fb96-111">To use the command, you specify one of the following:</span></span>

* <span data-ttu-id="0fb96-112">既定の場所にインストールされているグローバル ツール。</span><span class="sxs-lookup"><span data-stu-id="0fb96-112">A global tool installed in the default location.</span></span> <span data-ttu-id="0fb96-113">`--global` オプションを使用します</span><span class="sxs-lookup"><span data-stu-id="0fb96-113">Use the `--global` option</span></span>
* <span data-ttu-id="0fb96-114">カスタムの場所にインストールされているグローバル ツール。</span><span class="sxs-lookup"><span data-stu-id="0fb96-114">A global tool installed in a custom location.</span></span> <span data-ttu-id="0fb96-115">`--tool-path` オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="0fb96-115">Use the `--tool-path` option.</span></span>
* <span data-ttu-id="0fb96-116">ローカル ツール。</span><span class="sxs-lookup"><span data-stu-id="0fb96-116">A local tool.</span></span> <span data-ttu-id="0fb96-117">`--global` および `--tool-path` オプションを省略します。</span><span class="sxs-lookup"><span data-stu-id="0fb96-117">Omit the `--global` and `--tool-path` options.</span></span>

<span data-ttu-id="0fb96-118">**ローカル ツールは .NET Core SDK 3.0 以降で使用できます。**</span><span class="sxs-lookup"><span data-stu-id="0fb96-118">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

## <a name="options"></a><span data-ttu-id="0fb96-119">オプション</span><span class="sxs-lookup"><span data-stu-id="0fb96-119">Options</span></span>

- **`-g|--global`**

  <span data-ttu-id="0fb96-120">ユーザー全体のグローバル ツールを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="0fb96-120">Lists user-wide global tools.</span></span> <span data-ttu-id="0fb96-121">`--tool-path` オプションと組み合わせることはできません。</span><span class="sxs-lookup"><span data-stu-id="0fb96-121">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="0fb96-122">`--global` と `--tool-path` の両方を省略すると、ローカル ツールが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="0fb96-122">Omitting both `--global` and `--tool-path` lists local tools.</span></span>

- **`-h|--help`**

  <span data-ttu-id="0fb96-123">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="0fb96-123">Prints out a short help for the command.</span></span>

- **`--tool-path <PATH>`**

  <span data-ttu-id="0fb96-124">グローバル ツールを検索するカスタムの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="0fb96-124">Specifies a custom location where to find global tools.</span></span> <span data-ttu-id="0fb96-125">PATH は絶対パスでも相対パスでもかまいません。</span><span class="sxs-lookup"><span data-stu-id="0fb96-125">PATH can be absolute or relative.</span></span> <span data-ttu-id="0fb96-126">`--global` オプションと組み合わせることはできません。</span><span class="sxs-lookup"><span data-stu-id="0fb96-126">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="0fb96-127">`--global` と `--tool-path` の両方を省略すると、ローカル ツールが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="0fb96-127">Omitting both `--global` and `--tool-path` lists local tools.</span></span>

## <a name="examples"></a><span data-ttu-id="0fb96-128">使用例</span><span class="sxs-lookup"><span data-stu-id="0fb96-128">Examples</span></span>

- **`dotnet tool list -g`**

  <span data-ttu-id="0fb96-129">お使いのコンピューター (現在のユーザー プロファイル) 上でユーザー全体にインストールされているすべてのグローバル ツールを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="0fb96-129">Lists all global tools installed user-wide on your machine (current user profile).</span></span>

- **`dotnet tool list --tool-path c:\global-tools`**

  <span data-ttu-id="0fb96-130">特定の Windows ディレクトリからグローバル ツールを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="0fb96-130">Lists the global tools from a specific Windows directory.</span></span>

- **`dotnet tool list --tool-path ~/bin`**

  <span data-ttu-id="0fb96-131">特定の Linux/macOS ディレクトリからグローバル ツールを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="0fb96-131">Lists the global tools from a specific Linux/macOS directory.</span></span>

- **`dotnet tool list`**

  <span data-ttu-id="0fb96-132">現在のディレクトリで使用可能なすべてのローカル ツールを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="0fb96-132">Lists all local tools available in the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="0fb96-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="0fb96-133">See also</span></span>

- [<span data-ttu-id="0fb96-134">.NET Core ツール</span><span class="sxs-lookup"><span data-stu-id="0fb96-134">.NET Core tools</span></span>](global-tools.md)
