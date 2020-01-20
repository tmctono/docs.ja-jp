---
title: .NET Core グローバル ツール
description: .NET Core グローバル ツールとそれらに使用できる .NET Core CLI コマンドの概要。
author: KathleenDollard
ms.date: 05/29/2018
ms.openlocfilehash: 0df3c1b615adfeaaf41542dc8252a8f14f49f6f9
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899867"
---
# <a name="net-core-global-tools-overview"></a><span data-ttu-id="4eb66-103">.NET core グローバル ツールの概要</span><span class="sxs-lookup"><span data-stu-id="4eb66-103">.NET Core Global Tools overview</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

<span data-ttu-id="4eb66-104">.NET Core グローバル ツールは、コンソール アプリケーションを含む特殊な NuGet パッケージです。</span><span class="sxs-lookup"><span data-stu-id="4eb66-104">A .NET Core Global Tool is a special NuGet package that contains a console application.</span></span> <span data-ttu-id="4eb66-105">グローバル ツールは、PATH 環境変数に含まれている既定の場所またはカスタムの場所のマシンにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="4eb66-105">A Global Tool can be installed on your machine on a default location that is included in the PATH environment variable or on a custom location.</span></span>

<span data-ttu-id="4eb66-106">.NET Core グローバル ツールを使用する場合は、次のことを行います。</span><span class="sxs-lookup"><span data-stu-id="4eb66-106">If you want to use a .NET Core Global Tool:</span></span>

* <span data-ttu-id="4eb66-107">ツールに関する情報を検索します (通常は Web サイトまたは GitHub ページ)。</span><span class="sxs-lookup"><span data-stu-id="4eb66-107">Find information about the tool (usually a website or GitHub page).</span></span>
* <span data-ttu-id="4eb66-108">フィードのホーム (通常は NuGet.org) で作成者と統計情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="4eb66-108">Check the author and statistics in the home for the feed (usually NuGet.org).</span></span>
* <span data-ttu-id="4eb66-109">ツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="4eb66-109">Install the tool.</span></span>
* <span data-ttu-id="4eb66-110">ツールを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4eb66-110">Call the tool.</span></span>
* <span data-ttu-id="4eb66-111">ツールを更新します。</span><span class="sxs-lookup"><span data-stu-id="4eb66-111">Update the tool.</span></span>
* <span data-ttu-id="4eb66-112">ツールをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="4eb66-112">Uninstall the tool.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4eb66-113">.NET Core グローバル ツールは、パス上に表示され、完全な信頼で実行されます。</span><span class="sxs-lookup"><span data-stu-id="4eb66-113">.NET Core Global Tools appear on your path and run in full trust.</span></span> <span data-ttu-id="4eb66-114">作成者が信頼できる場合を除き、.NET Core グローバル ツールをインストールしないでください。</span><span class="sxs-lookup"><span data-stu-id="4eb66-114">Do not install .NET Core Global Tools unless you trust the author.</span></span>

## <a name="find-a-net-core-global-tool"></a><span data-ttu-id="4eb66-115">.NET Core グローバル ツールの検索</span><span class="sxs-lookup"><span data-stu-id="4eb66-115">Find a .NET Core Global Tool</span></span>

<span data-ttu-id="4eb66-116">現時点では、.NET Core コマンド ライン インターフェイス (CLI) には、グローバル ツールの検索機能はありません。</span><span class="sxs-lookup"><span data-stu-id="4eb66-116">Currently, there isn't a Global Tool search feature in the .NET Core Command-line Interface (CLI).</span></span> <span data-ttu-id="4eb66-117">次に、ツールの検索方法に関する推奨事項をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="4eb66-117">The following are some recommendations on how to find tools:</span></span>

* <span data-ttu-id="4eb66-118">.NET Core グローバル ツールは、[NuGet](https://www.nuget.org) で見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="4eb66-118">You can find .NET Core Global Tools on [NuGet](https://www.nuget.org).</span></span> <span data-ttu-id="4eb66-119">ただし、NuGet では、具体的に .NET Core グローバル ツールを検索することはまだできません。</span><span class="sxs-lookup"><span data-stu-id="4eb66-119">However, NuGet doesn't yet allow you to search specifically for .NET Core Global Tools.</span></span>
* <span data-ttu-id="4eb66-120">ブログの投稿や [natemcmaster/dotnet-tools](https://github.com/natemcmaster/dotnet-tools) GitHub リポジトリで、ツールの推奨事項を検索することができます。</span><span class="sxs-lookup"><span data-stu-id="4eb66-120">You may find tool recommendations in blog posts or in the [natemcmaster/dotnet-tools](https://github.com/natemcmaster/dotnet-tools) GitHub repository.</span></span>
* <span data-ttu-id="4eb66-121">[dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/tree/master/src/Tools) GitHub リポジトリでは、ASP.NET チームによって作成されたグローバル ツールのソース コードを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="4eb66-121">You can see the source code for the Global Tools created by the ASP.NET team at the [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/tree/master/src/Tools) GitHub repository.</span></span>
* <span data-ttu-id="4eb66-122">診断ツールの詳細については、「[.NET Core dotnet 診断グローバル ツール](../diagnostics/index.md#net-core-dotnet-diagnostic-global-tools)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4eb66-122">You can learn about diagnostic tools at [.NET Core dotnet diagnostic Global Tools](../diagnostics/index.md#net-core-dotnet-diagnostic-global-tools).</span></span>

## <a name="check-the-author-and-statistics"></a><span data-ttu-id="4eb66-123">作成者と統計情報の確認</span><span class="sxs-lookup"><span data-stu-id="4eb66-123">Check the author and statistics</span></span>

<span data-ttu-id="4eb66-124">.NET Core グローバル ツールは、完全な信頼で実行され、通常はパス上にインストールされるため、非常に強力です。</span><span class="sxs-lookup"><span data-stu-id="4eb66-124">Since .NET Core Global Tools run in full trust and are generally installed on your path, they can be very powerful.</span></span> <span data-ttu-id="4eb66-125">信頼できないユーザーからツールをダウンロードしないでください。</span><span class="sxs-lookup"><span data-stu-id="4eb66-125">Don't download tools from people you don't trust.</span></span>

<span data-ttu-id="4eb66-126">ツールが NuGet でホストされている場合は、ツールを検索することで作成者と統計情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="4eb66-126">If the tool is hosted on NuGet, you can check the author and statistics by searching for the tool.</span></span>

## <a name="install-a-global-tool"></a><span data-ttu-id="4eb66-127">グローバル ツールのインストール</span><span class="sxs-lookup"><span data-stu-id="4eb66-127">Install a Global Tool</span></span>

<span data-ttu-id="4eb66-128">グローバル ツールをインストールするには、[dotnet tool install](dotnet-tool-install.md) .NET Core CLI コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="4eb66-128">To install a Global Tool, you use the [dotnet tool install](dotnet-tool-install.md) .NET Core CLI command.</span></span> <span data-ttu-id="4eb66-129">次の例では、既定の場所にグローバル ツールをインストールする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="4eb66-129">The following example shows how to install a Global Tool in the default location:</span></span>

```dotnetcli
dotnet tool install -g dotnetsay
```

<span data-ttu-id="4eb66-130">ツールがインストールできない場合は、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4eb66-130">If the tool can't be installed, error messages are displayed.</span></span> <span data-ttu-id="4eb66-131">予定していたフィードがチェックされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4eb66-131">Check that the feeds you expected are being checked.</span></span>

<span data-ttu-id="4eb66-132">ツールのプレリリース バージョンまたは特定のバージョンをインストールしようとしている場合は、次の形式を使用してバージョン番号を指定できます。</span><span class="sxs-lookup"><span data-stu-id="4eb66-132">If you're trying to install a pre-release version or a specific version of the tool, you can specify the version number using the following format:</span></span>

```dotnetcli
dotnet tool install -g <package-name> --version <version-number>
```

<span data-ttu-id="4eb66-133">インストールが成功すると、ツールの呼び出しに使用したコマンドとインストールされたバージョンを示す、次の例のようなメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4eb66-133">If installation is successful, a message is displayed showing the command used to call the tool and the version installed, similar to the following example:</span></span>

```output
You can invoke the tool using the following command: dotnetsay
Tool 'dotnetsay' (version '2.0.0') was successfully installed.
```

<span data-ttu-id="4eb66-134">グローバル ツールは、既定のディレクトリ内または特定の場所にインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="4eb66-134">Global Tools can be installed in the default directory or in a specific location.</span></span> <span data-ttu-id="4eb66-135">既定のディレクトリは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4eb66-135">The default directories are:</span></span>

| <span data-ttu-id="4eb66-136">OS</span><span class="sxs-lookup"><span data-stu-id="4eb66-136">OS</span></span>          | <span data-ttu-id="4eb66-137">パス</span><span class="sxs-lookup"><span data-stu-id="4eb66-137">Path</span></span>                          |
|-------------|-------------------------------|
| <span data-ttu-id="4eb66-138">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="4eb66-138">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
| <span data-ttu-id="4eb66-139">Windows</span><span class="sxs-lookup"><span data-stu-id="4eb66-139">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

<span data-ttu-id="4eb66-140">これらの場所は、そこにインストールされたグローバル ツールを直接呼び出せるように、SDK が最初に実行されるときにユーザーのパスに追加されます。</span><span class="sxs-lookup"><span data-stu-id="4eb66-140">These locations are added to the user's path when the SDK is first run, so Global Tools installed there can be called directly.</span></span>

<span data-ttu-id="4eb66-141">グローバル ツールは、マシン全体ではなく、ユーザーに固有であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4eb66-141">Note that the Global Tools are user-specific, not machine global.</span></span> <span data-ttu-id="4eb66-142">ユーザーに固有であることは、そのマシンのすべてのユーザーが使用できるグローバル ツールをインストールできないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="4eb66-142">Being user-specific means you cannot install a Global Tool that is available to all users of the machine.</span></span> <span data-ttu-id="4eb66-143">このツールは、ツールがインストールされた各ユーザー プロファイルでしか使用できません。</span><span class="sxs-lookup"><span data-stu-id="4eb66-143">The tool is only available for each user profile where the tool was installed.</span></span>

<span data-ttu-id="4eb66-144">グローバル ツールは、特定のディレクトリにインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="4eb66-144">Global Tools can also be installed in a specific directory.</span></span> <span data-ttu-id="4eb66-145">特定のディレクトリにインストールした場合は、ユーザーはコマンドが使用できることを確認する必要があります。それには、そのディレクトリをパスに含めるか、指定されたディレクトリでコマンドを呼び出すか、指定したディレクトリ内からツールを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4eb66-145">When installed in a specific directory, the user must ensure the command is available, by including that directory in the path, by calling the command with the directory specified, or calling the tool from within the specified directory.</span></span>
<span data-ttu-id="4eb66-146">この場合、.NET Core CLI によりこの場所が PATH 環境変数に自動的に追加されることはありません。</span><span class="sxs-lookup"><span data-stu-id="4eb66-146">In this case, the .NET Core CLI doesn't add this location automatically to the PATH environment variable.</span></span>

## <a name="use-the-tool"></a><span data-ttu-id="4eb66-147">ツールの使用</span><span class="sxs-lookup"><span data-stu-id="4eb66-147">Use the tool</span></span>

<span data-ttu-id="4eb66-148">ツールをインストールすると、そのコマンドを使用してツールを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="4eb66-148">Once the tool is installed, you can call it by using its command.</span></span> <span data-ttu-id="4eb66-149">コマンドが、パッケージ名と異なる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4eb66-149">Note that the command may not be the same as the package name.</span></span>

<span data-ttu-id="4eb66-150">コマンドが `dotnetsay` の場合、次を使用して呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4eb66-150">If the command is `dotnetsay`, you call it with:</span></span>

```console
dotnetsay
```

<span data-ttu-id="4eb66-151">ツールの作成者が `dotnet` プロンプトのコンテキストにツールを表示するようにした場合は、次のように、`dotnet <command>` として呼び出す方法でツールを記述している場合があります。</span><span class="sxs-lookup"><span data-stu-id="4eb66-151">If the tool author wanted the tool to appear in the context of the `dotnet` prompt, they may have written it in a way that you call it as `dotnet <command>`, such as:</span></span>

```dotnetcli
dotnet doc
```

<span data-ttu-id="4eb66-152">インストールしたグローバル ツール パッケージに含まれているツールを確認するには、[dotnet tool list](dotnet-tool-list.md) コマンドを使用してインストールされているパッケージを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="4eb66-152">You can find which tools are included in an installed Global Tool package by listing the installed packages using the [dotnet tool list](dotnet-tool-list.md) command.</span></span>

<span data-ttu-id="4eb66-153">ツールの使用方法については、ツールの Web サイトで検索するか、次のいずれかのコマンドを入力して検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="4eb66-153">You can also look for usage instructions at the tool's website or by typing one of the following commands:</span></span>

```console
<command> --help
dotnet <command> --help
```

## <a name="other-cli-commands"></a><span data-ttu-id="4eb66-154">その他の CLI コマンド</span><span class="sxs-lookup"><span data-stu-id="4eb66-154">Other CLI commands</span></span>

<span data-ttu-id="4eb66-155">.NET Core SDK には、.NET Core グローバル ツールをサポートするその他のコマンドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4eb66-155">The .NET Core SDK contains other commands that support .NET Core Global Tools.</span></span> <span data-ttu-id="4eb66-156">次のいずれかのオプションを使用して、任意の `dotnet tool` コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="4eb66-156">Use any of the `dotnet tool` commands with one of the following options:</span></span>

* <span data-ttu-id="4eb66-157">`--global` または `-g` は、コマンドがユーザー全体のグローバル ツールに適用可能なことを指定します。</span><span class="sxs-lookup"><span data-stu-id="4eb66-157">`--global` or `-g` specifies that the command is applicable to user-wide Global Tools.</span></span>
* <span data-ttu-id="4eb66-158">`--tool-path` は、グローバル ツールのカスタムの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="4eb66-158">`--tool-path` specifies a custom location for Global Tools.</span></span>

<span data-ttu-id="4eb66-159">グローバル ツールで使用できるコマンドを調べるには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="4eb66-159">To find out which commands are available for Global Tools:</span></span>

```dotnetcli
dotnet tool --help
```

<span data-ttu-id="4eb66-160">グローバル ツールを更新するには、ツールをアンインストールしてから、最新の安定バージョンで再インストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4eb66-160">Updating a Global Tool involves uninstalling and reinstalling it with the latest stable version.</span></span> <span data-ttu-id="4eb66-161">グローバル ツールを更新するには、[dotnet tool update](dotnet-tool-update.md) コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="4eb66-161">To update a Global Tool, use the [dotnet tool update](dotnet-tool-update.md) command:</span></span>

```dotnetcli
dotnet tool update -g <packagename>
```

<span data-ttu-id="4eb66-162">[dotnet tool uninstall](dotnet-tool-uninstall.md) を使用してグローバル ツールを削除します。</span><span class="sxs-lookup"><span data-stu-id="4eb66-162">Remove a Global Tool using the [dotnet tool uninstall](dotnet-tool-uninstall.md):</span></span>

```dotnetcli
dotnet tool uninstall -g <packagename>
```

<span data-ttu-id="4eb66-163">マシンに現在インストールされているすべてのグローバル ツールと、それらのバージョンとコマンドを表示するには、[dotnet tool list](dotnet-tool-list.md) コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="4eb66-163">To display all of the Global Tools currently installed on the machine, along with their version and commands, use the [dotnet tool list](dotnet-tool-list.md) command:</span></span>

```dotnetcli
dotnet tool list -g
```

## <a name="see-also"></a><span data-ttu-id="4eb66-164">関連項目</span><span class="sxs-lookup"><span data-stu-id="4eb66-164">See also</span></span>

* [<span data-ttu-id="4eb66-165">.NET Core ツールの使用に関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="4eb66-165">Troubleshoot .NET Core tool usage issues</span></span>](troubleshoot-usage-issues.md)
