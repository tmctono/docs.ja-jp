---
title: dotnet tool update コマンド
description: dotnet tool update コマンドでは、お使いのコンピューター上の指定された .NET Core ツールを更新します。
ms.date: 02/14/2020
ms.openlocfilehash: 80e807a0fc06ad762334f888e701f6d9c448369a
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156947"
---
# <a name="dotnet-tool-update"></a><span data-ttu-id="d9e17-103">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="d9e17-103">dotnet tool update</span></span>

<span data-ttu-id="d9e17-104">**この記事の対象:** ✔️ .NET Core 2.1 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="d9e17-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="d9e17-105">名前</span><span class="sxs-lookup"><span data-stu-id="d9e17-105">Name</span></span>

<span data-ttu-id="d9e17-106">`dotnet tool update` - お使いのコンピューター上の指定された [.NET Core ツール](global-tools.md)を更新します。</span><span class="sxs-lookup"><span data-stu-id="d9e17-106">`dotnet tool update` - Updates the specified [.NET Core tool](global-tools.md) on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d9e17-107">構文</span><span class="sxs-lookup"><span data-stu-id="d9e17-107">Synopsis</span></span>

```dotnetcli
dotnet tool update <PACKAGE_NAME> <-g|--global> [--configfile] [--framework] [-v|--verbosity] [--add-source]
dotnet tool update <PACKAGE_NAME> <--tool-path> [--configfile] [--framework] [-v|--verbosity] [--add-source]
dotnet tool update <PACKAGE_NAME> [--configfile] [--framework] [-v|--verbosity] [--add-source]
dotnet tool update <-h|--help>
```

## <a name="description"></a><span data-ttu-id="d9e17-108">説明</span><span class="sxs-lookup"><span data-stu-id="d9e17-108">Description</span></span>

<span data-ttu-id="d9e17-109">`dotnet tool update` コマンドでは、お使いのコンピューター上の .NET Core ツールをパッケージの最新の安定バージョンに更新するための方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="d9e17-109">The `dotnet tool update` command provides a way for you to update .NET Core tools on your machine to the latest stable version of the package.</span></span> <span data-ttu-id="d9e17-110">このコマンドは、ツールをアンインストールして再インストールして、効果的に更新します。</span><span class="sxs-lookup"><span data-stu-id="d9e17-110">The command uninstalls and reinstalls a tool, effectively updating it.</span></span> <span data-ttu-id="d9e17-111">コマンドを使用するには、次のいずれかのオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="d9e17-111">To use the command, you specify one of the following options:</span></span>

* <span data-ttu-id="d9e17-112">既定の場所にインストールされたグローバル ツールを更新するには、`--global` オプションを使用します</span><span class="sxs-lookup"><span data-stu-id="d9e17-112">To update a global tool that was installed in the default location, use the `--global` option</span></span>
* <span data-ttu-id="d9e17-113">カスタムの場所にインストールされたグローバル ツールを更新するには、`--tool-path` オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="d9e17-113">To update a global tool that was installed in a custom location, use the `--tool-path` option.</span></span>
* <span data-ttu-id="d9e17-114">ローカル ツールを更新するには、`--global` および `--tool-path` オプションを省略します。</span><span class="sxs-lookup"><span data-stu-id="d9e17-114">To update a local tool, omit the `--global` and `--tool-path` options.</span></span>

<span data-ttu-id="d9e17-115">**ローカル ツールは .NET Core SDK 3.0 以降で使用できます。**</span><span class="sxs-lookup"><span data-stu-id="d9e17-115">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

## <a name="arguments"></a><span data-ttu-id="d9e17-116">引数</span><span class="sxs-lookup"><span data-stu-id="d9e17-116">Arguments</span></span>

- **`PACKAGE_NAME`**

  <span data-ttu-id="d9e17-117">更新する .NET Core グローバル ツールが格納されている NuGet パッケージの名前または ID。</span><span class="sxs-lookup"><span data-stu-id="d9e17-117">Name/ID of the NuGet package that contains the .NET Core global tool to update.</span></span> <span data-ttu-id="d9e17-118">パッケージを見つけるには、[dotnet tool list](dotnet-tool-list.md) コマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d9e17-118">You can find the package name using the [dotnet tool list](dotnet-tool-list.md) command.</span></span>

## <a name="options"></a><span data-ttu-id="d9e17-119">オプション</span><span class="sxs-lookup"><span data-stu-id="d9e17-119">Options</span></span>

- **`--add-source <SOURCE>`**

  <span data-ttu-id="d9e17-120">インストール時に使用するために追加の NuGet パッケージ ソースを追加します。</span><span class="sxs-lookup"><span data-stu-id="d9e17-120">Adds an additional NuGet package source to use during installation.</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="d9e17-121">使用する NuGet 構成 (*nuget.config*) ファイル。</span><span class="sxs-lookup"><span data-stu-id="d9e17-121">The NuGet configuration (*nuget.config*) file to use.</span></span>

- **`--framework <FRAMEWORK>`**

  <span data-ttu-id="d9e17-122">ツールを更新する[ターゲット フレームワーク](../../standard/frameworks.md)を指定します。</span><span class="sxs-lookup"><span data-stu-id="d9e17-122">Specifies the [target framework](../../standard/frameworks.md) to update the tool for.</span></span>

- **`-g|--global`**

  <span data-ttu-id="d9e17-123">更新プログラムがユーザー全体のツール用であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="d9e17-123">Specifies that the update is for a user-wide tool.</span></span> <span data-ttu-id="d9e17-124">`--tool-path` オプションと組み合わせることはできません。</span><span class="sxs-lookup"><span data-stu-id="d9e17-124">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="d9e17-125">`--global` と `--tool-path` の両方を省略すると、更新されるツールはローカル ツールであると指定されます。</span><span class="sxs-lookup"><span data-stu-id="d9e17-125">Omitting both `--global` and `--tool-path` specifies that the tool to be updated is a local tool.</span></span>

- **`-h|--help`**

  <span data-ttu-id="d9e17-126">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="d9e17-126">Prints out a short help for the command.</span></span>

- **`--tool-path <PATH>`**

  <span data-ttu-id="d9e17-127">グローバル ツールがインストールされている場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="d9e17-127">Specifies the location where the global tool is installed.</span></span> <span data-ttu-id="d9e17-128">PATH は絶対パスでも相対パスでもかまいません。</span><span class="sxs-lookup"><span data-stu-id="d9e17-128">PATH can be absolute or relative.</span></span> <span data-ttu-id="d9e17-129">`--global` オプションと組み合わせることはできません。</span><span class="sxs-lookup"><span data-stu-id="d9e17-129">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="d9e17-130">`--global` と `--tool-path` の両方を省略すると、更新されるツールはローカル ツールであると指定されます。</span><span class="sxs-lookup"><span data-stu-id="d9e17-130">Omitting both `--global` and `--tool-path` specifies that the tool to be updated is a local tool.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="d9e17-131">コマンドの詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="d9e17-131">Sets the verbosity level of the command.</span></span> <span data-ttu-id="d9e17-132">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="d9e17-132">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="d9e17-133">使用例</span><span class="sxs-lookup"><span data-stu-id="d9e17-133">Examples</span></span>

- **`dotnet tool update -g dotnetsay`**

  <span data-ttu-id="d9e17-134">[dotnetsay](https://www.nuget.org/packages/dotnetsay/) グローバル ツールを更新します。</span><span class="sxs-lookup"><span data-stu-id="d9e17-134">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool.</span></span>

- **`dotnet tool update dotnetsay --tool-path c:\global-tools`**

  <span data-ttu-id="d9e17-135">特定の Windows ディレクトリに配置されている [dotnetsay](https://www.nuget.org/packages/dotnetsay/) グローバル ツールを更新します。</span><span class="sxs-lookup"><span data-stu-id="d9e17-135">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool located in a specific Windows directory.</span></span>

- **`dotnet tool update dotnetsay --tool-path ~/bin`**

  <span data-ttu-id="d9e17-136">特定の Linux/macOS ディレクトリに配置されている [dotnetsay](https://www.nuget.org/packages/dotnetsay/) グローバル ツールを更新します。</span><span class="sxs-lookup"><span data-stu-id="d9e17-136">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool located in a specific Linux/macOS directory.</span></span>

- **`dotnet tool update dotnetsay`**

  <span data-ttu-id="d9e17-137">現在のディレクトリに対してインストールされている [dotnetsay](https://www.nuget.org/packages/dotnetsay/) ローカル ツールを更新します。</span><span class="sxs-lookup"><span data-stu-id="d9e17-137">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) local tool installed for the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="d9e17-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="d9e17-138">See also</span></span>

- [<span data-ttu-id="d9e17-139">.NET Core ツール</span><span class="sxs-lookup"><span data-stu-id="d9e17-139">.NET Core tools</span></span>](global-tools.md)
