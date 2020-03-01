---
title: dotnet tool uninstall コマンド
description: dotnet tool uninstall コマンドでは、お使いのコンピューター上から指定された .NET Core ツールをアンインストールします。
ms.date: 02/14/2020
ms.openlocfilehash: 7a15c169c73cf5a743e0fa6f47645d6bccedbde3
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157046"
---
# <a name="dotnet-tool-uninstall"></a><span data-ttu-id="49ec1-103">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="49ec1-103">dotnet tool uninstall</span></span>

<span data-ttu-id="49ec1-104">**この記事の対象:** ✔️ .NET Core 2.1 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="49ec1-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="49ec1-105">名前</span><span class="sxs-lookup"><span data-stu-id="49ec1-105">Name</span></span>

<span data-ttu-id="49ec1-106">`dotnet tool uninstall` - お使いのコンピューター上から指定された [.NET Core ツール](global-tools.md)をアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="49ec1-106">`dotnet tool uninstall` - Uninstalls the specified [.NET Core tool](global-tools.md) from your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="49ec1-107">構文</span><span class="sxs-lookup"><span data-stu-id="49ec1-107">Synopsis</span></span>

```dotnetcli
dotnet tool uninstall <PACKAGE_NAME> <-g|--global>
dotnet tool uninstall <PACKAGE_NAME> <--tool-path>
dotnet tool uninstall <PACKAGE_NAME>
dotnet tool uninstall <-h|--help>
```

## <a name="description"></a><span data-ttu-id="49ec1-108">説明</span><span class="sxs-lookup"><span data-stu-id="49ec1-108">Description</span></span>

<span data-ttu-id="49ec1-109">`dotnet tool uninstall` コマンドでは、お使いのコンピューター上から .NET Core ツールをアンインストールするための方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="49ec1-109">The `dotnet tool uninstall` command provides a way for you to uninstall .NET Core tools from your machine.</span></span> <span data-ttu-id="49ec1-110">コマンドを使用するには、次のいずれかのオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="49ec1-110">To use the command, you specify one of the following options:</span></span>

* <span data-ttu-id="49ec1-111">既定の場所にインストールされたグローバル ツールをアンインストールするには、`--global` オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="49ec1-111">To uninstall a global tool that was installed in the default location, use the `--global` option.</span></span>
* <span data-ttu-id="49ec1-112">カスタムの場所にインストールされたグローバル ツールをアンインストールするには、`--tool-path` オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="49ec1-112">To uninstall a global tool that was installed in a custom location,  use the `--tool-path` option.</span></span>
* <span data-ttu-id="49ec1-113">ローカル ツールをアンインストールするには、`--global` および `--tool-path` オプションを省略します。</span><span class="sxs-lookup"><span data-stu-id="49ec1-113">To uninstall a local tool, omit the `--global` and `--tool-path` options.</span></span>

<span data-ttu-id="49ec1-114">**ローカル ツールは .NET Core SDK 3.0 以降で使用できます。**</span><span class="sxs-lookup"><span data-stu-id="49ec1-114">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

## <a name="arguments"></a><span data-ttu-id="49ec1-115">引数</span><span class="sxs-lookup"><span data-stu-id="49ec1-115">Arguments</span></span>

- **`PACKAGE_NAME`**

  <span data-ttu-id="49ec1-116">アンインストールする .NET Core ツールが格納されている NuGet パッケージの名前または ID。</span><span class="sxs-lookup"><span data-stu-id="49ec1-116">Name/ID of the NuGet package that contains the .NET Core tool to uninstall.</span></span> <span data-ttu-id="49ec1-117">パッケージを見つけるには、[dotnet tool list](dotnet-tool-list.md) コマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="49ec1-117">You can find the package name using the [dotnet tool list](dotnet-tool-list.md) command.</span></span>

## <a name="options"></a><span data-ttu-id="49ec1-118">オプション</span><span class="sxs-lookup"><span data-stu-id="49ec1-118">Options</span></span>

- **`-g|--global`**

  <span data-ttu-id="49ec1-119">ツールがユーザー全体のインストールから削除されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="49ec1-119">Specifies that the tool to be removed is from a user-wide installation.</span></span> <span data-ttu-id="49ec1-120">`--tool-path` オプションと組み合わせることはできません。</span><span class="sxs-lookup"><span data-stu-id="49ec1-120">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="49ec1-121">`--global` と `--tool-path` の両方を省略すると、削除されるツールはローカル ツールであると指定されます。</span><span class="sxs-lookup"><span data-stu-id="49ec1-121">Omitting both `--global` and `--tool-path` specifies that the tool to be removed is a local tool.</span></span>

- **`-h|--help`**

  <span data-ttu-id="49ec1-122">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="49ec1-122">Prints out a short help for the command.</span></span>

- **`--tool-path <PATH>`**

  <span data-ttu-id="49ec1-123">ツールをアンインストールする場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="49ec1-123">Specifies the location where to uninstall the tool.</span></span> <span data-ttu-id="49ec1-124">PATH は絶対パスでも相対パスでもかまいません。</span><span class="sxs-lookup"><span data-stu-id="49ec1-124">PATH can be absolute or relative.</span></span> <span data-ttu-id="49ec1-125">`--global` オプションと組み合わせることはできません。</span><span class="sxs-lookup"><span data-stu-id="49ec1-125">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="49ec1-126">`--global` と `--tool-path` の両方を省略すると、削除されるツールはローカル ツールであると指定されます。</span><span class="sxs-lookup"><span data-stu-id="49ec1-126">Omitting both `--global` and `--tool-path` specifies that the tool to be removed is a local tool.</span></span>

## <a name="examples"></a><span data-ttu-id="49ec1-127">使用例</span><span class="sxs-lookup"><span data-stu-id="49ec1-127">Examples</span></span>

- **`dotnet tool uninstall -g dotnetsay`**

  <span data-ttu-id="49ec1-128">[dotnetsay](https://www.nuget.org/packages/dotnetsay/) グローバル ツールをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="49ec1-128">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool.</span></span>

- **`dotnet tool uninstall dotnetsay --tool-path c:\global-tools`**

  <span data-ttu-id="49ec1-129">特定の Windows ディレクトリから [dotnetsay](https://www.nuget.org/packages/dotnetsay/) グローバル ツールをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="49ec1-129">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool from a specific Windows directory.</span></span>

- **`dotnet tool uninstall dotnetsay --tool-path ~/bin`**

  <span data-ttu-id="49ec1-130">特定の Linux/macOS ディレクトリから [dotnetsay](https://www.nuget.org/packages/dotnetsay/) グローバル ツールをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="49ec1-130">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool from a specific Linux/macOS directory.</span></span>

- **`dotnet tool uninstall dotnetsay`**

  <span data-ttu-id="49ec1-131">現在のディレクトリから [dotnetsay](https://www.nuget.org/packages/dotnetsay/) ローカル ツールをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="49ec1-131">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) local tool from the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="49ec1-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="49ec1-132">See also</span></span>

- [<span data-ttu-id="49ec1-133">.NET Core ツール</span><span class="sxs-lookup"><span data-stu-id="49ec1-133">.NET Core tools</span></span>](global-tools.md)
