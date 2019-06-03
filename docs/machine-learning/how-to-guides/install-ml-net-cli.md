---
title: ML.NET コマンドライン インターフェイス (CLI) ツールをインストールする方法
description: ML.NET コマンドライン インターフェイス (CLI) ツールの概要とインストール。
ms.date: 04/16/2019
ms.custom: ''
ms.openlocfilehash: 9560aa846a1aefabadbd7d4faf8bd306ba72e0de
ms.sourcegitcommit: 682c64df0322c7bda016f8bfea8954e9b31f1990
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2019
ms.locfileid: "65557859"
---
# <a name="how-to-install-the-mlnet-command-line-interface-cli-tool"></a><span data-ttu-id="3ec00-103">ML.NET コマンドライン インターフェイス (CLI) ツールをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="3ec00-103">How to install the ML.NET Command-Line Interface (CLI) tool</span></span>

<span data-ttu-id="3ec00-104">ML.NET CLI (コマンドライン インターフェイス) は、用意したトレーニング データセットに基づいて高品質の ML.NET モデルとソース コードを生成するための、コマンドプロンプト (Windows、Mac、または Linux) 上で実行できるツールです。</span><span class="sxs-lookup"><span data-stu-id="3ec00-104">The ML.NET CLI (command-line interface) is a tool you can run on any command-prompt (Windows, Mac, or Linux) for generating good quality ML.NET models and source code based on training datasets you provide.</span></span>

> [!NOTE]
> <span data-ttu-id="3ec00-105">このトピックは、現在プレビュー段階の ML.NET CLI と ML.NET AutoML について述べており、内容が変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="3ec00-105">This topic refers to ML.NET CLI and ML.NET AutoML, which are currently in Preview, and material may be subject to change.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="3ec00-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="3ec00-106">Pre-requisites</span></span>

- [<span data-ttu-id="3ec00-107">.NET Core 2.2 SDK</span><span class="sxs-lookup"><span data-stu-id="3ec00-107">.NET Core 2.2 SDK</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)

- <span data-ttu-id="3ec00-108">(省略可能) [Visual Studio 2017 または 2019](https://visualstudio.microsoft.com/vs/)</span><span class="sxs-lookup"><span data-stu-id="3ec00-108">(Optional) [Visual Studio 2017 or 2019](https://visualstudio.microsoft.com/vs/)</span></span>

<span data-ttu-id="3ec00-109">生成された C# コード プロジェクトは、Visual Studio で F5 キーまたは `dotnet run` (.NET Core CLI) を使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="3ec00-109">You can either run the generated C# code projects with Visual Studio F5 or with `dotnet run` (.NET Core CLI).</span></span>

<span data-ttu-id="3ec00-110">メモ:[.NET Core 2.2 SDK](https://dotnet.microsoft.com/download/dotnet-core/2.2) のインストール後に `dotnet tool` コマンドが機能しない場合は、Windows からサインアウトしてから再度サインインします。</span><span class="sxs-lookup"><span data-stu-id="3ec00-110">Note: If after installing [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download/dotnet-core/2.2) the `dotnet tool` command is not working, sign out from Windows and sign in again.</span></span>

## <a name="install"></a><span data-ttu-id="3ec00-111">インストール</span><span class="sxs-lookup"><span data-stu-id="3ec00-111">Install</span></span>

<span data-ttu-id="3ec00-112">ML.NET CLI のインストール方法は他の .NET グローバル ツールと同様です。</span><span class="sxs-lookup"><span data-stu-id="3ec00-112">The ML.NET CLI is installed like any other dotnet Global Tool.</span></span> <span data-ttu-id="3ec00-113">`dotnet tool install` .NET Core CLI コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="3ec00-113">You use the `dotnet tool install` .NET Core CLI command.</span></span> 

<span data-ttu-id="3ec00-114">次の例は、既定の NuGet フィードの場所に ML.NET CLI をインストールする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="3ec00-114">The following example shows how to install the ML.NET CLI in the default NuGet feed location:</span></span>

```console
> dotnet tool install -g mlnet
```

<span data-ttu-id="3ec00-115">ツールをインストールできない場合 (つまり、既定の NuGet フィードで利用できない場合) は、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ec00-115">If the tool can't be installed (that is, if it is not available at the default NuGet feed), error messages are displayed.</span></span> <span data-ttu-id="3ec00-116">予定していたフィードがチェックされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3ec00-116">Check that the feeds you expected are being checked.</span></span>

<span data-ttu-id="3ec00-117">インストールが成功すると、ツールの呼び出しに使用したコマンドとインストールされたバージョンを示す、次の例のようなメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ec00-117">If installation is successful, a message is displayed showing the command used to call the tool and the version installed, similar to the following example:</span></span>

```console
You can invoke the tool using the following command: mlnet
Tool 'mlnet' (version 'X.X.X') was successfully installed.
```

<span data-ttu-id="3ec00-118">インストールが成功したことを確認するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="3ec00-118">You can confirm the installation was successful by typing the following command:</span></span>

```console
> mlnet
```

<span data-ttu-id="3ec00-119">"auto-train" コマンドなど、mlnet ツールに利用できるコマンドのヘルプを参照することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3ec00-119">You should see the help for available commands for the mlnet tool such as the 'auto-train' command.</span></span>

## <a name="install-a-specific-release-version"></a><span data-ttu-id="3ec00-120">特定のリリース バージョンをインストールする</span><span class="sxs-lookup"><span data-stu-id="3ec00-120">Install a specific release version</span></span>

<span data-ttu-id="3ec00-121">ツールのプレリリース バージョンまたは特定のバージョンをインストールしようとしている場合は、次の形式を使用して、[フレームワーク](../../standard/frameworks.md)を指定できます。</span><span class="sxs-lookup"><span data-stu-id="3ec00-121">If you're trying to install a pre-release version or a specific version of the tool, you can specify the [framework](../../standard/frameworks.md) using the following format:</span></span>

```console
> dotnet tool install -g mlnet --framework <FRAMEWORK>
```

<span data-ttu-id="3ec00-122">次のコマンドを入力して、パッケージが正しくインストールされているかどうかを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="3ec00-122">You can also check if the package is properly installed by typing the following command:</span></span>

```console
> dotnet tool list -g
```

## <a name="uninstall-the-cli-package"></a><span data-ttu-id="3ec00-123">CLI パッケージをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="3ec00-123">Uninstall the CLI package</span></span>

<span data-ttu-id="3ec00-124">ローカル コンピューターからパッケージをアンインストールするには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="3ec00-124">Type the following command to uninstall the package from your local machine:</span></span>

```console
> dotnet tool uninstall mlnet -g
```

## <a name="update-the-cli-package"></a><span data-ttu-id="3ec00-125">CLI パッケージを更新する</span><span class="sxs-lookup"><span data-stu-id="3ec00-125">Update the CLI package</span></span>

<span data-ttu-id="3ec00-126">ローカル コンピューターからパッケージを更新するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="3ec00-126">Type the following command to update the package from your local machine:</span></span>

```console
> dotnet tool update -g mlnet
```

## <a name="set-up-cli-suggestions-tab-based-auto-completion"></a><span data-ttu-id="3ec00-127">CLI の候補を設定する (タブベースのオートコンプリート)</span><span class="sxs-lookup"><span data-stu-id="3ec00-127">Set up CLI suggestions (tab-based auto-completion)</span></span>

<span data-ttu-id="3ec00-128">ML.NET CLI は `System.CommandLine` に基づいているので、タブ補完のサポートが組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="3ec00-128">Since the ML.NET CLI is based on `System.CommandLine`, it has built-in support for tab completion.</span></span>

<span data-ttu-id="3ec00-129">次のアニメーションでタブのオートコンプリートのしくみの例を示します。</span><span class="sxs-lookup"><span data-stu-id="3ec00-129">An example of how tab auto completion works is shown in the following animation:</span></span>

![イメージ](./media/cli-tab-completion.gif)

<span data-ttu-id="3ec00-131">"タブベースのオートコンプリート" (パラメーターの候補) は *Windows PowerShell* と *macOS/Linux bash* では機能しますが、*Windows CMD* では機能しません。</span><span class="sxs-lookup"><span data-stu-id="3ec00-131">'Tab-based auto-completion' (parameter suggestions) works on *Windows PowerShell* and *macOS/Linux bash* but it won't work on *Windows CMD*.</span></span>

<span data-ttu-id="3ec00-132">これを有効にするには、現在のプレビュー バージョンでは、エンド ユーザーが、シェルごとに 1 回、以下に示すいくつかの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ec00-132">To enable it, in the current preview version, the end user has to take a few steps once per shell, outlined below.</span></span> <span data-ttu-id="3ec00-133">これが完了すると、ML.NET CLI などの `System.CommandLine` を使用して作成されるすべてのアプリに対して補完が機能するようになります。</span><span class="sxs-lookup"><span data-stu-id="3ec00-133">Once this is done, completions will work for all apps written using `System.CommandLine` such as the ML.NET CLI.</span></span>

<span data-ttu-id="3ec00-134">補完を有効にするマシンでは、2 つのことを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ec00-134">On the machine where you'd like to enable completion, you'll need to do two things.</span></span>

1. <span data-ttu-id="3ec00-135">次のコマンドを実行して、`dotnet-suggest` グローバル ツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="3ec00-135">Install the `dotnet-suggest` global tool by running the following command:</span></span>

    ```console
    > dotnet tool install dotnet-suggest -g
    ```

2. <span data-ttu-id="3ec00-136">適切な shim スクリプトをシェル プロファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="3ec00-136">Add the appropriate shim script to your shell profile.</span></span> <span data-ttu-id="3ec00-137">必要に応じてシェル プロファイル ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="3ec00-137">You may have to create a shell profile file.</span></span> <span data-ttu-id="3ec00-138">shim スクリプトによって、シェルからの完了要求が `dotnet-suggest` ツールに転送され、適切な `System.CommandLine` ベースのアプリに委任されます。</span><span class="sxs-lookup"><span data-stu-id="3ec00-138">The shim script will forward completion requests from your shell to the `dotnet-suggest` tool, which delegates to the appropriate `System.CommandLine`-based app.</span></span>

    * <span data-ttu-id="3ec00-139">bash の場合、[dotnet-suggest-shim.bash](https://github.com/dotnet/System.CommandLine/blob/master/src/System.CommandLine.Suggest/dotnet-suggest-shim.bash) の内容を `~/.bash_profile` に追加します。</span><span class="sxs-lookup"><span data-stu-id="3ec00-139">For bash, add the contents of [dotnet-suggest-shim.bash](https://github.com/dotnet/System.CommandLine/blob/master/src/System.CommandLine.Suggest/dotnet-suggest-shim.bash) to `~/.bash_profile`.</span></span>

    * <span data-ttu-id="3ec00-140">PowerShell の場合は、[dotnet-recommend-shim.ps1](https://github.com/dotnet/System.CommandLine/blob/master/src/System.CommandLine.Suggest/dotnet-suggest-shim.ps1) の内容を PowerShell プロファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="3ec00-140">For PowerShell, add the contents of [dotnet-suggest-shim.ps1](https://github.com/dotnet/System.CommandLine/blob/master/src/System.CommandLine.Suggest/dotnet-suggest-shim.ps1) to your PowerShell profile.</span></span> <span data-ttu-id="3ec00-141">コンソールで次のコマンドを実行して、PowerShell プロファイルへの予想されるパスを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="3ec00-141">You can find the expected path to your PowerShell profile by running the following command in your console:</span></span>

    ```console
    > echo $profile
    ``` 

<span data-ttu-id="3ec00-142">(他のシェルについては、[検索する](https://github.com/dotnet/System.CommandLine/issues?q=is%3Aissue+is%3Aopen+label%3A%22shell+suggestion%22)か、[問題](https://github.com/dotnet/System.CommandLine/issues)を開いてください。)</span><span class="sxs-lookup"><span data-stu-id="3ec00-142">(For other shells, [look for](https://github.com/dotnet/System.CommandLine/issues?q=is%3Aissue+is%3Aopen+label%3A%22shell+suggestion%22) or open an [issue](https://github.com/dotnet/System.CommandLine/issues).)</span></span>

## <a name="installation-directory"></a><span data-ttu-id="3ec00-143">インストール ディレクトリ</span><span class="sxs-lookup"><span data-stu-id="3ec00-143">Installation directory</span></span>

<span data-ttu-id="3ec00-144">ML.NET CLI は、既定のディレクトリまたは特定の場所にインストールできます。</span><span class="sxs-lookup"><span data-stu-id="3ec00-144">The ML.NET CLI can be installed in the default directory or in a specific location.</span></span> <span data-ttu-id="3ec00-145">既定のディレクトリは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3ec00-145">The default directories are:</span></span>

| <span data-ttu-id="3ec00-146">OS</span><span class="sxs-lookup"><span data-stu-id="3ec00-146">OS</span></span>          | <span data-ttu-id="3ec00-147">パス</span><span class="sxs-lookup"><span data-stu-id="3ec00-147">Path</span></span>                          |
|-------------|-------------------------------|
| <span data-ttu-id="3ec00-148">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="3ec00-148">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
| <span data-ttu-id="3ec00-149">Windows</span><span class="sxs-lookup"><span data-stu-id="3ec00-149">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

<span data-ttu-id="3ec00-150">これらの場所は、そこにインストールされたグローバル ツールを直接呼び出せるように、SDK が最初に実行されるときにユーザーのパスに追加されます。</span><span class="sxs-lookup"><span data-stu-id="3ec00-150">These locations are added to the user's path when the SDK is first run, so Global Tools installed there can be called directly.</span></span>

<span data-ttu-id="3ec00-151">注: グローバル ツールは、マシン全体ではなく、ユーザー固有のものです。</span><span class="sxs-lookup"><span data-stu-id="3ec00-151">Note: the Global Tools are user-specific, not machine global.</span></span> <span data-ttu-id="3ec00-152">ユーザーに固有であることは、そのマシンのすべてのユーザーが使用できるグローバル ツールをインストールできないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="3ec00-152">Being user-specific means you cannot install a Global Tool that is available to all users of the machine.</span></span> <span data-ttu-id="3ec00-153">このツールは、ツールがインストールされた各ユーザー プロファイルでしか使用できません。</span><span class="sxs-lookup"><span data-stu-id="3ec00-153">The tool is only available for each user profile where the tool was installed.</span></span>

<span data-ttu-id="3ec00-154">グローバル ツールは、特定のディレクトリにインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="3ec00-154">Global Tools can also be installed in a specific directory.</span></span> <span data-ttu-id="3ec00-155">特定のディレクトリにインストールした場合は、ユーザーはコマンドが使用できることを確認する必要があります。それには、そのディレクトリをパスに含めるか、指定されたディレクトリでコマンドを呼び出すか、指定したディレクトリ内からツールを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="3ec00-155">When installed in a specific directory, the user must ensure the command is available, by including that directory in the path, by calling the command with the directory specified, or calling the tool from within the specified directory.</span></span>
<span data-ttu-id="3ec00-156">この場合、.NET Core CLI によりこの場所が PATH 環境変数に自動的に追加されることはありません。</span><span class="sxs-lookup"><span data-stu-id="3ec00-156">In this case, the .NET Core CLI doesn't add this location automatically to the PATH environment variable.</span></span>

## <a name="see-also"></a><span data-ttu-id="3ec00-157">関連項目</span><span class="sxs-lookup"><span data-stu-id="3ec00-157">See also</span></span>

- [<span data-ttu-id="3ec00-158">"ML.NET CLI ツールの概要" のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="3ec00-158">Tutorial on 'Getting Started with ML.NET CLI tool'</span></span>](../tutorials/mlnet-cli.md)
- [<span data-ttu-id="3ec00-159">ML.NET CLI ツールを使用してモデルを自動的にトレーニングする方法</span><span class="sxs-lookup"><span data-stu-id="3ec00-159">How to automatically train models with the ML.NET CLI tool</span></span>](../automate-training-with-cli.md)
- [<span data-ttu-id="3ec00-160">ML.NET CLI auto-train コマンド リファレンス ガイド</span><span class="sxs-lookup"><span data-stu-id="3ec00-160">ML.NET CLI auto-train command reference guide</span></span>](../reference/ml-net-cli-reference.md) 
- [<span data-ttu-id="3ec00-161">ML.NET CLI のテレメトリ</span><span class="sxs-lookup"><span data-stu-id="3ec00-161">Telemetry in ML.NET CLI</span></span>](../resources/ml-net-cli-telemetry.md)
