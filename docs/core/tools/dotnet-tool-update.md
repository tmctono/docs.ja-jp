---
title: dotnet tool update コマンド
description: dotnet tool update コマンドは、マシン上の指定された .NET Core グローバル ツールを更新します。
ms.date: 05/29/2018
ms.openlocfilehash: b10ce39c8b9d4df23243bcf672454a455e34eec1
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117529"
---
# <a name="dotnet-tool-update"></a><span data-ttu-id="f7f0c-103">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="f7f0c-103">dotnet tool update</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a><span data-ttu-id="f7f0c-104">name</span><span class="sxs-lookup"><span data-stu-id="f7f0c-104">Name</span></span>

<span data-ttu-id="f7f0c-105">`dotnet tool update` - マシン上の指定された [.NET Core グローバル ツール](global-tools.md) を更新します。</span><span class="sxs-lookup"><span data-stu-id="f7f0c-105">`dotnet tool update` - Updates the specified [.NET Core Global Tool](global-tools.md) on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="f7f0c-106">構文</span><span class="sxs-lookup"><span data-stu-id="f7f0c-106">Synopsis</span></span>

```dotnetcli
dotnet tool update <PACKAGE_NAME> <-g|--global> [--configfile] [--framework] [-v|--verbosity]
dotnet tool update <PACKAGE_NAME> <--tool-path> [--configfile] [--framework] [-v|--verbosity]
dotnet tool update <-h|--help>
```

## <a name="description"></a><span data-ttu-id="f7f0c-107">説明</span><span class="sxs-lookup"><span data-stu-id="f7f0c-107">Description</span></span>

<span data-ttu-id="f7f0c-108">`dotnet tool update` コマンドは、マシン上の指定された .NET Core グローバル ツールをパッケージの最新の安定バージョンに更新するための手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="f7f0c-108">The `dotnet tool update` command provides a way for you to update .NET Core Global Tools on your machine to the latest stable version of the package.</span></span> <span data-ttu-id="f7f0c-109">このコマンドは、ツールをアンインストールして再インストールして、効果的に更新します。</span><span class="sxs-lookup"><span data-stu-id="f7f0c-109">The command uninstalls and reinstalls a tool, effectively updating it.</span></span> <span data-ttu-id="f7f0c-110">コマンドを使用するには、`--global` オプションを使用してユーザー全体のインストールからツールを更新することを指定するか、`--tool-path` オプションを使用してツールがインストールされている場所へのパスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7f0c-110">To use the command, you either have to specify that you want to update a tool from a user-wide installation using the `--global` option or specify a path to where the tool is installed using the `--tool-path` option.</span></span>

## <a name="arguments"></a><span data-ttu-id="f7f0c-111">引数</span><span class="sxs-lookup"><span data-stu-id="f7f0c-111">Arguments</span></span>

`PACKAGE_NAME`

<span data-ttu-id="f7f0c-112">更新する .NET Core グローバル ツールが格納されている NuGet パッケージの名前または ID。</span><span class="sxs-lookup"><span data-stu-id="f7f0c-112">Name/ID of the NuGet package that contains the .NET Core Global Tool to update.</span></span> <span data-ttu-id="f7f0c-113">パッケージを見つけるには、[dotnet tool list](dotnet-tool-list.md) コマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f7f0c-113">You can find the package name using the [dotnet tool list](dotnet-tool-list.md) command.</span></span>

## <a name="options"></a><span data-ttu-id="f7f0c-114">オプション</span><span class="sxs-lookup"><span data-stu-id="f7f0c-114">Options</span></span>

`--add-source <SOURCE>`

<span data-ttu-id="f7f0c-115">インストール時に使用するために追加の NuGet パッケージ ソースを追加します。</span><span class="sxs-lookup"><span data-stu-id="f7f0c-115">Adds an additional NuGet package source to use during installation.</span></span>

`--configfile <FILE>`

<span data-ttu-id="f7f0c-116">使用する NuGet 構成 (*nuget.config*) ファイル。</span><span class="sxs-lookup"><span data-stu-id="f7f0c-116">The NuGet configuration (*nuget.config*) file to use.</span></span>

`--framework <FRAMEWORK>`

<span data-ttu-id="f7f0c-117">ツールを更新する[ターゲット フレームワーク](../../standard/frameworks.md)を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7f0c-117">Specifies the [target framework](../../standard/frameworks.md) to update the tool for.</span></span>

`-g|--global`

<span data-ttu-id="f7f0c-118">更新プログラムがユーザー全体のツール用であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="f7f0c-118">Specifies that the update is for a user-wide tool.</span></span> <span data-ttu-id="f7f0c-119">`--tool-path` オプションと組み合わせることはできません。</span><span class="sxs-lookup"><span data-stu-id="f7f0c-119">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="f7f0c-120">このオプションを指定しない場合は、`--tool-path` オプションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7f0c-120">If you don't specify this option, you must specify the `--tool-path` option.</span></span>

`-h|--help`

<span data-ttu-id="f7f0c-121">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="f7f0c-121">Prints out a short help for the command.</span></span>

`--tool-path <PATH>`

<span data-ttu-id="f7f0c-122">グローバル ツールがインストールされている場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7f0c-122">Specifies the location where the Global Tool is installed.</span></span> <span data-ttu-id="f7f0c-123">パスは絶対パスでも相対パスでもかまいません。</span><span class="sxs-lookup"><span data-stu-id="f7f0c-123">PATH can be absolute or relative.</span></span> <span data-ttu-id="f7f0c-124">`--global` オプションと組み合わせることはできません。</span><span class="sxs-lookup"><span data-stu-id="f7f0c-124">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="f7f0c-125">このオプションを指定しない場合は、`--global` オプションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7f0c-125">If you don't specify this option, you must specify the `--global` option.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="f7f0c-126">コマンドの詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="f7f0c-126">Sets the verbosity level of the command.</span></span> <span data-ttu-id="f7f0c-127">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="f7f0c-127">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="f7f0c-128">使用例</span><span class="sxs-lookup"><span data-stu-id="f7f0c-128">Examples</span></span>

<span data-ttu-id="f7f0c-129">[dotnetsay](https://www.nuget.org/packages/dotnetsay/) グローバル ツールを更新します。</span><span class="sxs-lookup"><span data-stu-id="f7f0c-129">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool:</span></span>

`dotnet tool update -g dotnetsay`

<span data-ttu-id="f7f0c-130">特定の Windows フォルダーに配置されている [dotnetsay](https://www.nuget.org/packages/dotnetsay/) グローバル ツールを更新します。</span><span class="sxs-lookup"><span data-stu-id="f7f0c-130">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool located on a specific Windows folder:</span></span>

`dotnet tool update dotnetsay --tool-path c:\global-tools`

<span data-ttu-id="f7f0c-131">特定の Linux/macOS フォルダーに配置されている [dotnetsay](https://www.nuget.org/packages/dotnetsay/) グローバル ツールを更新します。</span><span class="sxs-lookup"><span data-stu-id="f7f0c-131">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool located on a specific Linux/macOS folder:</span></span>

`dotnet tool update dotnetsay --tool-path ~/bin`

## <a name="see-also"></a><span data-ttu-id="f7f0c-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7f0c-132">See also</span></span>

- [<span data-ttu-id="f7f0c-133">.NET Core グローバル ツール</span><span class="sxs-lookup"><span data-stu-id="f7f0c-133">.NET Core Global Tools</span></span>](global-tools.md)
