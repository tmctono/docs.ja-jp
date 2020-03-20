---
title: dotnet tool restore コマンド
description: dotnet tool restore コマンドでは、現在のディレクトリのスコープ内にある .NET Core ローカル ツールをお使いのコンピューター上にインストールします。
ms.date: 02/14/2020
ms.openlocfilehash: cb46f70afb58e482b6aedfddfbf5f3a0c40674f4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79146438"
---
# <a name="dotnet-tool-restore"></a><span data-ttu-id="81725-103">dotnet tool restore</span><span class="sxs-lookup"><span data-stu-id="81725-103">dotnet tool restore</span></span>

<span data-ttu-id="81725-104">**この記事の対象:** ✔️ .NET Core 3.0 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="81725-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="81725-105">名前</span><span class="sxs-lookup"><span data-stu-id="81725-105">Name</span></span>

<span data-ttu-id="81725-106">`dotnet tool restore` - 現在のディレクトリのスコープ内にある .NET Core ローカル ツールをお使いのコンピューター上にインストールします。</span><span class="sxs-lookup"><span data-stu-id="81725-106">`dotnet tool restore` - Installs on your machine the .NET Core local tools that are in scope for the current directory.</span></span>

## <a name="synopsis"></a><span data-ttu-id="81725-107">構文</span><span class="sxs-lookup"><span data-stu-id="81725-107">Synopsis</span></span>

```dotnetcli
dotnet tool restore <PACKAGE_NAME>
    [--configfile] [--add-source] [tool-manifest]
    [--disable-parallel] [--ignore-failed-sources]
    [--no-cache] [-interactive] [-v|--verbosity]

dotnet tool restore <-h|--help>
```

## <a name="description"></a><span data-ttu-id="81725-108">説明</span><span class="sxs-lookup"><span data-stu-id="81725-108">Description</span></span>

<span data-ttu-id="81725-109">`dotnet tool restore` コマンドでは、現在のディレクトリのスコープ内にあるツール マニフェスト ファイルを検索し、そこに一覧表示されたツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="81725-109">The `dotnet tool restore` command finds the tool manifest file that is in scope for the current directory and installs the tools that are listed in it.</span></span> <span data-ttu-id="81725-110">マニフェスト ファイルの詳細については、「[ローカル ツールのインストール](global-tools.md#install-a-local-tool)」および「[ローカル ツールの起動](global-tools.md#invoke-a-local-tool)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81725-110">For information about manifest files, see [Install a local tool](global-tools.md#install-a-local-tool) and [Invoke a local tool](global-tools.md#invoke-a-local-tool).</span></span>

## <a name="arguments"></a><span data-ttu-id="81725-111">引数</span><span class="sxs-lookup"><span data-stu-id="81725-111">Arguments</span></span>

- **`PACKAGE_NAME`**

<span data-ttu-id="81725-112">インストールする .NET Core ツールが格納されている NuGet パッケージの名前または ID。</span><span class="sxs-lookup"><span data-stu-id="81725-112">Name/ID of the NuGet package that contains the .NET Core tool to install.</span></span>

## <a name="options"></a><span data-ttu-id="81725-113">オプション</span><span class="sxs-lookup"><span data-stu-id="81725-113">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="81725-114">使用する NuGet 構成 (*nuget.config*) ファイル。</span><span class="sxs-lookup"><span data-stu-id="81725-114">The NuGet configuration (*nuget.config*) file to use.</span></span>

- **`--add-source <SOURCE>`**

  <span data-ttu-id="81725-115">インストール時に使用するために追加の NuGet パッケージ ソースを追加します。</span><span class="sxs-lookup"><span data-stu-id="81725-115">Adds an additional NuGet package source to use during installation.</span></span>

- **`--tool-manifest <PATH>`**

  <span data-ttu-id="81725-116">マニフェスト ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="81725-116">Path to the manifest file.</span></span>

- **`--disable-parallel`**

  <span data-ttu-id="81725-117">複数のプロジェクトを並行して復元できないようにします。</span><span class="sxs-lookup"><span data-stu-id="81725-117">Prevent restoring multiple projects in parallel.</span></span>

- **`--ignore-failed-sources`**

  <span data-ttu-id="81725-118">パッケージ ソース エラーを警告として処理します。</span><span class="sxs-lookup"><span data-stu-id="81725-118">Treat package source failures as warnings.</span></span>

- **`--no-cache`**

  <span data-ttu-id="81725-119">パッケージと HTTP 要求をキャッシュしません。</span><span class="sxs-lookup"><span data-stu-id="81725-119">Do not cache packages and http requests.</span></span>

- **`--interactive`**

  <span data-ttu-id="81725-120">コマンドを停止して、ユーザーの入力または操作のために待機させることができます (たとえば、認証を完了する場合)。</span><span class="sxs-lookup"><span data-stu-id="81725-120">Allows the command to stop and wait for user input or action (for example to complete authentication).</span></span>

- **`-h|--help`**

  <span data-ttu-id="81725-121">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="81725-121">Prints out a short help for the command.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="81725-122">コマンドの詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="81725-122">Sets the verbosity level of the command.</span></span> <span data-ttu-id="81725-123">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="81725-123">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="example"></a><span data-ttu-id="81725-124">例</span><span class="sxs-lookup"><span data-stu-id="81725-124">Example</span></span>

- **`dotnet tool restore`**

  <span data-ttu-id="81725-125">現在のディレクトリのローカル ツールを復元します。</span><span class="sxs-lookup"><span data-stu-id="81725-125">Restores local tools for the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="81725-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="81725-126">See also</span></span>

- [<span data-ttu-id="81725-127">.NET Core ツール</span><span class="sxs-lookup"><span data-stu-id="81725-127">.NET Core tools</span></span>](global-tools.md)
- [<span data-ttu-id="81725-128">チュートリアル: .NET Core CLI を使って .NET Core ローカル ツールをインストールして使用する</span><span class="sxs-lookup"><span data-stu-id="81725-128">Tutorial: Install and use a .NET Core local tool using the .NET Core CLI</span></span>](local-tools-how-to-use.md)
