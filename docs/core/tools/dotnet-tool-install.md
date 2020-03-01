---
title: dotnet tool install コマンド
description: dotnet tool install コマンドでは、お使いのコンピューター上に指定された .NET Core ツールをインストールします。
ms.date: 02/14/2020
ms.openlocfilehash: 641e6a2753b1cf3bfc334ba2495342f7c42421fc
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156975"
---
# <a name="dotnet-tool-install"></a><span data-ttu-id="05c65-103">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="05c65-103">dotnet tool install</span></span>

<span data-ttu-id="05c65-104">**この記事の対象:** ✔️ .NET Core 2.1 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="05c65-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="05c65-105">名前</span><span class="sxs-lookup"><span data-stu-id="05c65-105">Name</span></span>

<span data-ttu-id="05c65-106">`dotnet tool install` - お使いのコンピューター上に指定された [.NET Core ツール](global-tools.md)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="05c65-106">`dotnet tool install` - Installs the specified [.NET Core tool](global-tools.md) on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="05c65-107">構文</span><span class="sxs-lookup"><span data-stu-id="05c65-107">Synopsis</span></span>

```dotnetcli
dotnet tool install <PACKAGE_NAME> <-g|--global> [--add-source] [--configfile] [--framework] [-v|--verbosity] [--version]
dotnet tool install <PACKAGE_NAME> <--tool-path> [--add-source] [--configfile] [--framework] [-v|--verbosity] [--version]
dotnet tool install <PACKAGE_NAME> [--add-source] [--configfile] [--framework] [-v|--verbosity] [--version]
dotnet tool install <-h|--help>
```

## <a name="description"></a><span data-ttu-id="05c65-108">説明</span><span class="sxs-lookup"><span data-stu-id="05c65-108">Description</span></span>

<span data-ttu-id="05c65-109">`dotnet tool install` コマンドでは、お使いのコンピューター上に .NET Core ツールをインストールする方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="05c65-109">The `dotnet tool install` command provides a way for you to install .NET Core tools on your machine.</span></span> <span data-ttu-id="05c65-110">コマンドを使用するには、次のいずれかのインストール オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="05c65-110">To use the command, you specify one of the following installation options:</span></span>

* <span data-ttu-id="05c65-111">既定の場所にグローバル ツールをインストールするには、`--global` オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="05c65-111">To install a global tool in the default location, use the `--global` option.</span></span>
* <span data-ttu-id="05c65-112">カスタムの場所にグローバル ツールをインストールするには、`--tool-path` オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="05c65-112">To install a global tool in a custom location,  use the `--tool-path` option.</span></span>
* <span data-ttu-id="05c65-113">ローカル ツールをインストールするには、`--global` および `--tool-path` オプションを省略します。</span><span class="sxs-lookup"><span data-stu-id="05c65-113">To install a local tool, omit the `--global` and `--tool-path` options.</span></span>

<span data-ttu-id="05c65-114">**ローカル ツールは .NET Core SDK 3.0 以降で使用できます。**</span><span class="sxs-lookup"><span data-stu-id="05c65-114">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

<span data-ttu-id="05c65-115">グローバル ツールは、`-g` または `--global` オプションを指定した場合、既定で次のディレクトリにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="05c65-115">Global tools are installed in the following directories by default when you specify the `-g` or `--global` option:</span></span>

| <span data-ttu-id="05c65-116">OS</span><span class="sxs-lookup"><span data-stu-id="05c65-116">OS</span></span>          | <span data-ttu-id="05c65-117">パス</span><span class="sxs-lookup"><span data-stu-id="05c65-117">Path</span></span>                          |
|-------------|-------------------------------|
| <span data-ttu-id="05c65-118">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="05c65-118">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
| <span data-ttu-id="05c65-119">Windows</span><span class="sxs-lookup"><span data-stu-id="05c65-119">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

<span data-ttu-id="05c65-120">ローカル ツールは、現在のディレクトリ下にある *.config*ディレクトリ内の *tool-manifest.json* ファイルに追加されます。</span><span class="sxs-lookup"><span data-stu-id="05c65-120">Local tools are added to a *tool-manifest.json* file in a *.config* directory under the current directory.</span></span> <span data-ttu-id="05c65-121">マニフェスト ファイルがまだ存在しない場合は、次のコマンドを実行して作成します。</span><span class="sxs-lookup"><span data-stu-id="05c65-121">If a manifest file doesn't exist yet, create it by running the following command:</span></span>

```dotnetcli
dotnet new tool-manifest
```

<span data-ttu-id="05c65-122">詳細については、「[ローカル ツールのインストール](global-tools.md#install-a-local-tool)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05c65-122">For more information, see [Install a local tool](global-tools.md#install-a-local-tool).</span></span>

## <a name="arguments"></a><span data-ttu-id="05c65-123">引数</span><span class="sxs-lookup"><span data-stu-id="05c65-123">Arguments</span></span>

- **`PACKAGE_NAME`**

  <span data-ttu-id="05c65-124">インストールする .NET Core ツールが格納されている NuGet パッケージの名前または ID。</span><span class="sxs-lookup"><span data-stu-id="05c65-124">Name/ID of the NuGet package that contains the .NET Core tool to install.</span></span>

## <a name="options"></a><span data-ttu-id="05c65-125">オプション</span><span class="sxs-lookup"><span data-stu-id="05c65-125">Options</span></span>

- **`add-source <SOURCE>`**

  <span data-ttu-id="05c65-126">インストール時に使用するために追加の NuGet パッケージ ソースを追加します。</span><span class="sxs-lookup"><span data-stu-id="05c65-126">Adds an additional NuGet package source to use during installation.</span></span>

- **`configfile <FILE>`**

  <span data-ttu-id="05c65-127">使用する NuGet 構成 (*nuget.config*) ファイル。</span><span class="sxs-lookup"><span data-stu-id="05c65-127">The NuGet configuration (*nuget.config*) file to use.</span></span>

- **`framework <FRAMEWORK>`**

  <span data-ttu-id="05c65-128">ツールをインストールする[ターゲット フレームワーク](../../standard/frameworks.md)を指定します。</span><span class="sxs-lookup"><span data-stu-id="05c65-128">Specifies the [target framework](../../standard/frameworks.md) to install the tool for.</span></span> <span data-ttu-id="05c65-129">既定では、.NET Core SDK は最適なターゲット フレームワークの選択を試みます。</span><span class="sxs-lookup"><span data-stu-id="05c65-129">By default, the .NET Core SDK tries to choose the most appropriate target framework.</span></span>

- **`-g|--global`**

  <span data-ttu-id="05c65-130">ユーザー全体のインストールを指定します。</span><span class="sxs-lookup"><span data-stu-id="05c65-130">Specifies that the installation is user wide.</span></span> <span data-ttu-id="05c65-131">`--tool-path` オプションと組み合わせることはできません。</span><span class="sxs-lookup"><span data-stu-id="05c65-131">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="05c65-132">`--global` と `--tool-path` の両方を省略すると、ローカル ツールのインストールが指定されます。</span><span class="sxs-lookup"><span data-stu-id="05c65-132">Omitting both `--global` and `--tool-path` specifies a local tool installation.</span></span>

- **`-h|--help`**

  <span data-ttu-id="05c65-133">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="05c65-133">Prints out a short help for the command.</span></span>

- **`tool-path <PATH>`**

  <span data-ttu-id="05c65-134">グローバル ツールをインストールする場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="05c65-134">Specifies the location where to install the Global Tool.</span></span> <span data-ttu-id="05c65-135">PATH は絶対パスでも相対パスでもかまいません。</span><span class="sxs-lookup"><span data-stu-id="05c65-135">PATH can be absolute or relative.</span></span> <span data-ttu-id="05c65-136">PATH が存在しない場合、コマンドではパスの作成を試みます。</span><span class="sxs-lookup"><span data-stu-id="05c65-136">If PATH doesn't exist, the command tries to create it.</span></span> <span data-ttu-id="05c65-137">`--global` と `--tool-path` の両方を省略すると、ローカル ツールのインストールが指定されます。</span><span class="sxs-lookup"><span data-stu-id="05c65-137">Omitting both `--global` and `--tool-path` specifies a local tool installation.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="05c65-138">コマンドの詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="05c65-138">Sets the verbosity level of the command.</span></span> <span data-ttu-id="05c65-139">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="05c65-139">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

- **`--version <VERSION_NUMBER>`**

  <span data-ttu-id="05c65-140">インストールするツールのバージョン。</span><span class="sxs-lookup"><span data-stu-id="05c65-140">The version of the tool to install.</span></span> <span data-ttu-id="05c65-141">既定では、安定した最新バージョンのパッケージがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="05c65-141">By default, the latest stable package version is installed.</span></span> <span data-ttu-id="05c65-142">このオプションを使用して、プレビューまたは古いバージョンのツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="05c65-142">Use this option to install preview or older versions of the tool.</span></span>

## <a name="examples"></a><span data-ttu-id="05c65-143">使用例</span><span class="sxs-lookup"><span data-stu-id="05c65-143">Examples</span></span>

- **`dotnet tool install -g dotnetsay`**

  <span data-ttu-id="05c65-144">既定の場所に [dotnetsay](https://www.nuget.org/packages/dotnetsay/) をグローバル ツールとしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="05c65-144">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool in the default location.</span></span>

- **`dotnet tool install dotnetsay --tool-path c:\global-tools`**

  <span data-ttu-id="05c65-145">特定の Windows ディレクトリに [dotnetsay](https://www.nuget.org/packages/dotnetsay/) をグローバル ツールとしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="05c65-145">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool in a specific Windows directory.</span></span>

- **`dotnet tool install dotnetsay --tool-path ~/bin`**

  <span data-ttu-id="05c65-146">特定の Linux/macOS ディレクトリに [dotnetsay](https://www.nuget.org/packages/dotnetsay/) をグローバル ツールとしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="05c65-146">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool in a specific Linux/macOS directory.</span></span>

- **`dotnet tool install -g dotnetsay --version 2.0.0`**

  <span data-ttu-id="05c65-147">バージョン 2.0.0 の [dotnetsay](https://www.nuget.org/packages/dotnetsay/) をグローバル ツールとしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="05c65-147">Installs version 2.0.0 of [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool.</span></span>

- **`dotnet tool install dotnetsay`**

  <span data-ttu-id="05c65-148">現在のディレクトリに [dotnetsay](https://www.nuget.org/packages/dotnetsay/) をローカル ツールとしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="05c65-148">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a local tool for the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="05c65-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="05c65-149">See also</span></span>

- [<span data-ttu-id="05c65-150">.NET Core ツール</span><span class="sxs-lookup"><span data-stu-id="05c65-150">.NET Core tools</span></span>](global-tools.md)
