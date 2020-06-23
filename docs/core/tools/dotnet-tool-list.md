---
title: dotnet tool list コマンド
description: dotnet tool list コマンドでは、お使いのコンピューターにインストールされている .NET Core ツールの一覧を表示します。
ms.date: 02/14/2020
ms.openlocfilehash: 7ca894ab0f5daf0118ff92fb39e0118b952b3d83
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768275"
---
# <a name="dotnet-tool-list"></a><span data-ttu-id="b0357-103">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="b0357-103">dotnet tool list</span></span>

<span data-ttu-id="b0357-104">**この記事の対象:** ✔️ .NET Core 2.1 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="b0357-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="b0357-105">名前</span><span class="sxs-lookup"><span data-stu-id="b0357-105">Name</span></span>

<span data-ttu-id="b0357-106">`dotnet tool list` - お使いのコンピューター上に現在インストールされている指定した種類のすべての [.NET Core ツール](global-tools.md)を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="b0357-106">`dotnet tool list` - Lists all [.NET Core tools](global-tools.md) of the specified type currently installed on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b0357-107">構文</span><span class="sxs-lookup"><span data-stu-id="b0357-107">Synopsis</span></span>

```dotnetcli
dotnet tool list -g|--global

dotnet tool list --tool-path <PATH>

dotnet tool list --local

dotnet tool list

dotnet tool list -h|--help
```

## <a name="description"></a><span data-ttu-id="b0357-108">説明</span><span class="sxs-lookup"><span data-stu-id="b0357-108">Description</span></span>

<span data-ttu-id="b0357-109">`dotnet tool list` コマンドでは、お使いのコンピューターにインストールされている .NET Core グローバル、ツールパス、またはローカルのすべてのツールを一覧表示できます。</span><span class="sxs-lookup"><span data-stu-id="b0357-109">The `dotnet tool list` command provides a way for you to list all .NET Core global, tool-path, or local tools installed on your machine.</span></span> <span data-ttu-id="b0357-110">コマンドでは、パッケージ名、インストールされているバージョン、およびツール コマンドを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="b0357-110">The command lists the package name, version installed, and the tool command.</span></span>  <span data-ttu-id="b0357-111">コマンドを使用するには、次のいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="b0357-111">To use the command, you specify one of the following:</span></span>

* <span data-ttu-id="b0357-112">既定の場所にインストールされているグローバル ツールを一覧表示するには、`--global` オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="b0357-112">To list global tools installed in the default location, use the `--global` option</span></span>
* <span data-ttu-id="b0357-113">ユーザー指定の場所にインストールされているグローバル ツールを一覧表示するには、`--tool-path` オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="b0357-113">To list global tools installed in a custom location, use the `--tool-path` option.</span></span>
* <span data-ttu-id="b0357-114">A ローカル ツールというローカル ツールを一覧表示するには、</span><span class="sxs-lookup"><span data-stu-id="b0357-114">To list local tools, A local tool.</span></span> <span data-ttu-id="b0357-115">`--local` オプションを使用するか、`--global`、`--tool-path`、および `--local` オプションを省略します。</span><span class="sxs-lookup"><span data-stu-id="b0357-115">use the `--local` option or omit the `--global`, `--tool-path`, and `--local` options.</span></span>

<span data-ttu-id="b0357-116">**ローカル ツールは .NET Core SDK 3.0 以降で使用できます。**</span><span class="sxs-lookup"><span data-stu-id="b0357-116">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

## <a name="options"></a><span data-ttu-id="b0357-117">オプション</span><span class="sxs-lookup"><span data-stu-id="b0357-117">Options</span></span>

- **`-g|--global`**

  <span data-ttu-id="b0357-118">ユーザー全体のグローバル ツールを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="b0357-118">Lists user-wide global tools.</span></span> <span data-ttu-id="b0357-119">`--tool-path` オプションと組み合わせることはできません。</span><span class="sxs-lookup"><span data-stu-id="b0357-119">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="b0357-120">`--global` と `--tool-path` の両方を省略すると、ローカル ツールが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0357-120">Omitting both `--global` and `--tool-path` lists local tools.</span></span>

- **`-h|--help`**

  <span data-ttu-id="b0357-121">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="b0357-121">Prints out a short help for the command.</span></span>

- **`--local`**

  <span data-ttu-id="b0357-122">現在のディレクトリのローカル ツールを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="b0357-122">Lists local tools for the current directory.</span></span> <span data-ttu-id="b0357-123">`--global` または `--tool-path` オプションとは組み合わせることはできません。</span><span class="sxs-lookup"><span data-stu-id="b0357-123">Can't be combined with the `--global` or `--tool-path` options.</span></span> <span data-ttu-id="b0357-124">`--global` と `--tool-path` の両方を省略すると、`--local` が指定されていない場合でも、ローカル ツールが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0357-124">Omitting both `--global` and `--tool-path` lists local tools even if `--local` is not specified.</span></span>

- **`--tool-path <PATH>`**

  <span data-ttu-id="b0357-125">グローバル ツールを検索するカスタムの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="b0357-125">Specifies a custom location where to find global tools.</span></span> <span data-ttu-id="b0357-126">PATH は絶対パスでも相対パスでもかまいません。</span><span class="sxs-lookup"><span data-stu-id="b0357-126">PATH can be absolute or relative.</span></span> <span data-ttu-id="b0357-127">`--global` オプションと組み合わせることはできません。</span><span class="sxs-lookup"><span data-stu-id="b0357-127">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="b0357-128">`--global` と `--tool-path` の両方を省略すると、ローカル ツールが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0357-128">Omitting both `--global` and `--tool-path` lists local tools.</span></span>

## <a name="examples"></a><span data-ttu-id="b0357-129">使用例</span><span class="sxs-lookup"><span data-stu-id="b0357-129">Examples</span></span>

- **`dotnet tool list -g`**

  <span data-ttu-id="b0357-130">お使いのコンピューター (現在のユーザー プロファイル) 上でユーザー全体にインストールされているすべてのグローバル ツールを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="b0357-130">Lists all global tools installed user-wide on your machine (current user profile).</span></span>

- **`dotnet tool list --tool-path c:\global-tools`**

  <span data-ttu-id="b0357-131">特定の Windows ディレクトリからグローバル ツールを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="b0357-131">Lists the global tools from a specific Windows directory.</span></span>

- **`dotnet tool list --tool-path ~/bin`**

  <span data-ttu-id="b0357-132">特定の Linux/macOS ディレクトリからグローバル ツールを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="b0357-132">Lists the global tools from a specific Linux/macOS directory.</span></span>

- <span data-ttu-id="b0357-133">**`dotnet tool list`** または **`dotnet tool list --local`**</span><span class="sxs-lookup"><span data-stu-id="b0357-133">**`dotnet tool list`** or **`dotnet tool list --local`**</span></span>

  <span data-ttu-id="b0357-134">現在のディレクトリで使用可能なすべてのローカル ツールを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="b0357-134">Lists all local tools available in the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="b0357-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="b0357-135">See also</span></span>

- [<span data-ttu-id="b0357-136">.NET Core ツール</span><span class="sxs-lookup"><span data-stu-id="b0357-136">.NET Core tools</span></span>](global-tools.md)
- [<span data-ttu-id="b0357-137">チュートリアル: .NET Core CLI を使って .NET Core グローバル ツールをインストールして使用する</span><span class="sxs-lookup"><span data-stu-id="b0357-137">Tutorial: Install and use a .NET Core global tool using the .NET Core CLI</span></span>](global-tools-how-to-use.md)
- [<span data-ttu-id="b0357-138">チュートリアル: .NET Core CLI を使って .NET Core ローカル ツールをインストールして使用する</span><span class="sxs-lookup"><span data-stu-id="b0357-138">Tutorial: Install and use a .NET Core local tool using the .NET Core CLI</span></span>](local-tools-how-to-use.md)
