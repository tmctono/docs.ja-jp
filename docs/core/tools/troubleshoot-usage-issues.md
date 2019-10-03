---
title: .NET Core ツールの使用に関する問題のトラブルシューティング
description: .NET Core ツールを実行するときの一般的な問題と考えられる解決策について説明します。
author: kdollard
ms.date: 09/23/2019
ms.openlocfilehash: eb769550493e5a25d4380cd543a3bbec880b38e9
ms.sourcegitcommit: 8b8dd14dde727026fd0b6ead1ec1df2e9d747a48
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "71332951"
---
# <a name="troubleshoot-net-core-tool-usage-issues"></a><span data-ttu-id="8ade3-103">.NET Core ツールの使用に関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="8ade3-103">Troubleshoot .NET Core tool usage issues</span></span>

<span data-ttu-id="8ade3-104">グローバル ツールまたはローカル ツールとして .NET Core ツールをインストールまたは実行しようとすると、問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="8ade3-104">You might come across issues when trying to install or run a .NET Core tool, which can be a global tool or a local tool.</span></span> <span data-ttu-id="8ade3-105">この記事では、一般的な根本原因と考えられる解決策について説明します。</span><span class="sxs-lookup"><span data-stu-id="8ade3-105">This article describes the common root causes and some possible solutions.</span></span>

## <a name="installed-net-core-tool-fails-to-run"></a><span data-ttu-id="8ade3-106">インストールされている .NET Core ツールを実行できない</span><span class="sxs-lookup"><span data-stu-id="8ade3-106">Installed .NET Core tool fails to run</span></span>

<span data-ttu-id="8ade3-107">.NET Core ツールの実行が失敗する場合、最も可能性が高いのは、次のいずれかの問題が発生していることです。</span><span class="sxs-lookup"><span data-stu-id="8ade3-107">When a .NET Core tool fails to run, most likely you ran into one of the following issues:</span></span>

* <span data-ttu-id="8ade3-108">ツールの実行可能ファイルが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="8ade3-108">The executable file for the tool wasn't found.</span></span>
* <span data-ttu-id="8ade3-109">正しいバージョンの .NET Core ランタイムが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="8ade3-109">The correct version of the .NET Core runtime wasn't found.</span></span> 

### <a name="executable-file-not-found"></a><span data-ttu-id="8ade3-110">実行可能ファイルが見つからない</span><span class="sxs-lookup"><span data-stu-id="8ade3-110">Executable file not found</span></span>

<span data-ttu-id="8ade3-111">実行可能ファイルが見つからない場合は、次のようなメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8ade3-111">If the executable file isn't found, you'll see a message similar to the following:</span></span>

```
Could not execute because the specified command or file was not found.
Possible reasons for this include:
  * You misspelled a built-in dotnet command.
  * You intended to execute a .NET Core program, but dotnet-xyz does not exist.
  * You intended to run a global tool, but a dotnet-prefixed executable with this name could not be found on the PATH.
```

<span data-ttu-id="8ade3-112">実行可能ファイルの名前によって、ツールの呼び出し方法が決まります。</span><span class="sxs-lookup"><span data-stu-id="8ade3-112">The name of the executable determines how you invoke the tool.</span></span> <span data-ttu-id="8ade3-113">次の表ではその形式について説明します。</span><span class="sxs-lookup"><span data-stu-id="8ade3-113">The following table describes the format:</span></span>

| <span data-ttu-id="8ade3-114">実行可能ファイル名の形式</span><span class="sxs-lookup"><span data-stu-id="8ade3-114">Executable name format</span></span>  | <span data-ttu-id="8ade3-115">呼び出し方式</span><span class="sxs-lookup"><span data-stu-id="8ade3-115">Invocation format</span></span>   |
|-------------------------|---------------------|
| `dotnet-<toolName>.exe` | `dotnet <toolName>` |
| `<toolName>.exe`        | `<toolName>`        |

* <span data-ttu-id="8ade3-116">グローバル ツール</span><span class="sxs-lookup"><span data-stu-id="8ade3-116">Global tools</span></span>

    <span data-ttu-id="8ade3-117">グローバル ツールは、既定のディレクトリ内または特定の場所にインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="8ade3-117">Global tools can be installed in the default directory or in a specific location.</span></span> <span data-ttu-id="8ade3-118">既定のディレクトリは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8ade3-118">The default directories are:</span></span>

    | <span data-ttu-id="8ade3-119">OS</span><span class="sxs-lookup"><span data-stu-id="8ade3-119">OS</span></span>          | <span data-ttu-id="8ade3-120">パス</span><span class="sxs-lookup"><span data-stu-id="8ade3-120">Path</span></span>                          |
    |-------------|-------------------------------|
    | <span data-ttu-id="8ade3-121">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="8ade3-121">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
    | <span data-ttu-id="8ade3-122">Windows</span><span class="sxs-lookup"><span data-stu-id="8ade3-122">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

    <span data-ttu-id="8ade3-123">グローバル ツールを実行しようとしている場合は、コンピューター上の `PATH` 環境変数にグローバル ツールをインストールしたパスが含まれること、およびそのパスに実行可能ファイルが存在することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8ade3-123">If you're trying to run a global tool, check that the `PATH` environment variable on your machine contains the path where you installed the global tool and that the executable is in that path.</span></span>

    <span data-ttu-id="8ade3-124">.NET Core CLI は、初めて使用したときに既定の場所を PATH 環境変数に追加しようとします。</span><span class="sxs-lookup"><span data-stu-id="8ade3-124">The .NET Core CLI tries to add the default locations to the PATH environment variable on its first usage.</span></span> <span data-ttu-id="8ade3-125">ただし、場所が PATH に自動的に追加されないシナリオがいくつかあるため、次のような場合は PATH を編集して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ade3-125">However, there are a couple of scenarios where the location might not be added to PATH automatically, so you'll have to edit PATH to configure it for the following cases:</span></span>

  * <span data-ttu-id="8ade3-126">Linux を使用していて、apt-get または rpm ではなく *.tar.gz* ファイルを使用して .NET Core SDK をインストールしている場合。</span><span class="sxs-lookup"><span data-stu-id="8ade3-126">If you're using Linux and you've installed the .NET Core SDK using *.tar.gz* files and not apt-get or rpm.</span></span>
  * <span data-ttu-id="8ade3-127">macOS 10.15 "Catalina" またはそれ以降のバージョンを使用している場合。</span><span class="sxs-lookup"><span data-stu-id="8ade3-127">If you're using macOS 10.15 "Catalina" or later versions.</span></span>
  * <span data-ttu-id="8ade3-128">macOS 10.14 "Mojave" 以前のバージョンを使用していて、 *.pkg* ではなく *.tar.gz* ファイルを使用して .NET Core SDK をインストールしている場合。</span><span class="sxs-lookup"><span data-stu-id="8ade3-128">If you're using macOS 10.14 "Mojave" or earlier versions, and you've installed the .NET Core SDK using *.tar.gz* files and not *.pkg*.</span></span>
  * <span data-ttu-id="8ade3-129">.NET Core 3.0 SDK をインストールしてあり、`DOTNET_ADD_GLOBAL_TOOLS_TO_PATH` 環境変数を `false` に設定している場合。</span><span class="sxs-lookup"><span data-stu-id="8ade3-129">If you've installed the .NET Core 3.0 SDK and you've set the `DOTNET_ADD_GLOBAL_TOOLS_TO_PATH` environment variable to `false`.</span></span>
  * <span data-ttu-id="8ade3-130">.NET Core 2.2 SDK 以前のバージョンをインストールしてあり、`DOTNET_SKIP_FIRST_TIME_EXPERIENCE` 環境変数を `true` に設定している場合。</span><span class="sxs-lookup"><span data-stu-id="8ade3-130">If you've installed .NET Core 2.2 SDK or earlier versions, and you've set the `DOTNET_SKIP_FIRST_TIME_EXPERIENCE` environment variable to `true`.</span></span>
  
  <span data-ttu-id="8ade3-131">グローバル ツールの詳細については、「[.NET Core グローバル ツールの概要](global-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ade3-131">For more information about global tools, see [.NET Core Global Tools overview](global-tools.md).</span></span>

* <span data-ttu-id="8ade3-132">ローカル ツール</span><span class="sxs-lookup"><span data-stu-id="8ade3-132">Local tools</span></span>

  <span data-ttu-id="8ade3-133">ローカル ツールを実行しようとしている場合は、*dotnet-tools.json* という名前のマニフェストファイルが、現在のディレクトリまたはそのいずれかの親ディレクトリにあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8ade3-133">If you're trying to run a local tool, verify that there's a manifest file called *dotnet-tools.json* in the current directory or any of its parent directories.</span></span> <span data-ttu-id="8ade3-134">このファイルは、ルート フォルダーではなく、プロジェクト フォルダー階層のどこかにある *.config* という名前のフォルダーに存在することもあります。</span><span class="sxs-lookup"><span data-stu-id="8ade3-134">This file can also live under a folder named *.config* anywhere in the project folder hierarchy, instead of the root folder.</span></span> <span data-ttu-id="8ade3-135">*dotnet-tools.json* が存在する場合は、それを開き、実行しようとしているツールを確認します。</span><span class="sxs-lookup"><span data-stu-id="8ade3-135">If *dotnet-tools.json* exists, open it and check for the tool you're trying to run.</span></span> <span data-ttu-id="8ade3-136">ファイルに `"isRoot": true` のエントリが含まれていない場合は、さらに上のファイル階層で他のツール マニフェスト ファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="8ade3-136">If the file doesn't contain an entry for `"isRoot": true`, then also check further up the file hierarchy for additional tool manifest files.</span></span>

    <span data-ttu-id="8ade3-137">指定されたパスにインストールされている .NET Core ツールを実行しようとしている場合は、ツールを使用するときにそのパスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ade3-137">If you're trying to run a .NET Core tool that was installed with a specified path, you need to include that path when using the tool.</span></span> <span data-ttu-id="8ade3-138">ツールパスにインストールされたツールを使用する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8ade3-138">An example of using a tool-path installed tool is:</span></span>

   ```console
   ..\<toolDirectory>\dotnet-<toolName>
    ```

### <a name="runtime-not-found"></a><span data-ttu-id="8ade3-139">ランタイムが見つからない</span><span class="sxs-lookup"><span data-stu-id="8ade3-139">Runtime not found</span></span>

<span data-ttu-id="8ade3-140">.NET Core ツールは、[フレームワークに依存するアプリケーション](../deploying/index.md#framework-dependent-deployments-fdd)です。つまり、お使いのマシンにインストールされている .NET Core ランタイムに依存します。</span><span class="sxs-lookup"><span data-stu-id="8ade3-140">.NET Core tools are [framework-dependent applications](../deploying/index.md#framework-dependent-deployments-fdd), which means they rely on a .NET Core runtime installed on your machine.</span></span> <span data-ttu-id="8ade3-141">予定していたランタイムが見つからない場合、ツールは次のような通常の .NET Core ランタイムのロール フォワード ルールに従います。</span><span class="sxs-lookup"><span data-stu-id="8ade3-141">If the expected runtime isn't found, they follow normal .NET Core runtime roll-forward rules such as:</span></span>

* <span data-ttu-id="8ade3-142">アプリケーションは、指定されたメジャー バージョンおよびマイナー バージョンの最上位の修正プログラム リリースにロール フォワードされます。</span><span class="sxs-lookup"><span data-stu-id="8ade3-142">An application rolls forward to the highest patch release of the specified major and minor version.</span></span>
* <span data-ttu-id="8ade3-143">一致するメジャー バージョン番号とマイナー バージョン番号と一致するランタイムがない場合は、次に高いマイナー バージョンが使用されます。</span><span class="sxs-lookup"><span data-stu-id="8ade3-143">If there's no matching runtime with a matching major and minor version number, the next higher minor version is used.</span></span>
* <span data-ttu-id="8ade3-144">ランタイムのプレビュー バージョン間、またはプレビュー バージョンとリリース バージョン間では、ロール フォワードは発生しません。</span><span class="sxs-lookup"><span data-stu-id="8ade3-144">Roll forward doesn't occur between preview versions of the runtime or between preview versions and release versions.</span></span> <span data-ttu-id="8ade3-145">したがって、プレビュー バージョンを使用して作成された .NET Core ツールは、作成者がリビルドして再パブリッシュしてから再インストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ade3-145">So, .NET Core tools created using preview versions must be rebuilt and republished by the author and reinstalled.</span></span>

<span data-ttu-id="8ade3-146">次の 2 つの一般的なシナリオでは、ロールフォワードは既定では実行されません。</span><span class="sxs-lookup"><span data-stu-id="8ade3-146">Roll-forward won't occur by default in two common scenarios:</span></span>

* <span data-ttu-id="8ade3-147">使用できるのが古いバージョンのランタイムだけの場合。</span><span class="sxs-lookup"><span data-stu-id="8ade3-147">Only lower versions of the runtime are available.</span></span> <span data-ttu-id="8ade3-148">ロールフォワードでは、ランタイムの新しいバージョンのみが選択されます。</span><span class="sxs-lookup"><span data-stu-id="8ade3-148">Roll-forward only selects later versions of the runtime.</span></span>
* <span data-ttu-id="8ade3-149">使用できるのが高いメジャー バージョンのランタイムだけの場合。</span><span class="sxs-lookup"><span data-stu-id="8ade3-149">Only higher major versions of the runtime are available.</span></span> <span data-ttu-id="8ade3-150">ロールフォワードでは、メジャー バージョンの境界を越えることはありません。</span><span class="sxs-lookup"><span data-stu-id="8ade3-150">Roll-forward doesn't cross major version boundaries.</span></span>

<span data-ttu-id="8ade3-151">アプリケーションで適切なランタイムが見つからない場合は、実行が失敗し、エラーが報告されます。</span><span class="sxs-lookup"><span data-stu-id="8ade3-151">If an application can't find an appropriate runtime, it fails to run and reports an error.</span></span>

<span data-ttu-id="8ade3-152">次のいずれかのコマンドを使用して、お使いのコンピューターにインストールされている .NET Core ランタイムを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="8ade3-152">You can find out which .NET Core runtimes are installed on your machine using one of the following commands:</span></span>

```dotnetcli
dotnet --list-runtimes
dotnet --info
```

<span data-ttu-id="8ade3-153">現在インストールされているランタイム バージョンがツールでサポートされている必要があると思われる場合は、ツールの作成者に連絡して、バージョン番号またはマルチターゲットを更新できるかどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8ade3-153">If you think the tool should support the runtime version you currently have installed, you can contact the tool author and see if they can update the version number or multi-target.</span></span> <span data-ttu-id="8ade3-154">更新されたバージョン番号でツール パッケージが再コンパイルされて NuGet に再発行された後、コピーを更新することができます。</span><span class="sxs-lookup"><span data-stu-id="8ade3-154">Once they've recompiled and republished their tool package to NuGet with an updated version number, you can update your copy.</span></span> <span data-ttu-id="8ade3-155">それまでの間の最も簡単な解決策は、実行しようとしているツールで動作するランタイムのバージョンをインストールすることです。</span><span class="sxs-lookup"><span data-stu-id="8ade3-155">While that doesn't happen, the quickest solution for you is to install a version of the runtime that would work with the tool you're trying to run.</span></span> <span data-ttu-id="8ade3-156">特定の .NET Core ランタイム バージョンをダウンロードするには、[.NET Core ダウンロード ページ](https://dotnet.microsoft.com/download/dotnet-core)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ade3-156">To download a specific .NET Core runtime version, visit the [.NET Core download page](https://dotnet.microsoft.com/download/dotnet-core).</span></span>

<span data-ttu-id="8ade3-157">既定以外の場所に .NET Core SDK をインストールする場合は、`dotnet` 実行可能ファイルが格納されているディレクトリに、環境変数 `DOTNET_ROOT` を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ade3-157">If you install the .NET Core SDK to a non-default location, you need to set the environment variable `DOTNET_ROOT` to the directory that contains the `dotnet` executable.</span></span>

## <a name="net-core-tool-installation-fails"></a><span data-ttu-id="8ade3-158">.NET Core ツールのインストールが失敗する</span><span class="sxs-lookup"><span data-stu-id="8ade3-158">.NET Core tool installation fails</span></span>

<span data-ttu-id="8ade3-159">いろいろな理由で、.NET Core のグローバル ツールまたはローカル ツールのインストールが失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8ade3-159">There are a number of reasons the installation of a .NET Core global or local tool may fail.</span></span> <span data-ttu-id="8ade3-160">ツールのインストールが失敗すると、次のようなメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8ade3-160">When the tool installation fails, you'll see a message similar to following one:</span></span>

```
Tool '{0}' failed to install. This failure may have been caused by:

* You are attempting to install a preview release and did not use the --version option to specify the version.
* A package by this name was found, but it was not a .NET Core tool.
* The required NuGet feed cannot be accessed, perhaps because of an Internet connection problem.
* You mistyped the name of the tool.

For more reasons, including package naming enforcement, visit https://aka.ms/failure-installing-tool
```

<span data-ttu-id="8ade3-161">これらのエラーの診断に役立つよう、上のメッセージと共に、NuGet のメッセージがユーザーに直接表示されます。</span><span class="sxs-lookup"><span data-stu-id="8ade3-161">To help diagnose these failures, NuGet messages are shown directly to the user, along with the previous message.</span></span> <span data-ttu-id="8ade3-162">NuGet のメッセージは、問題の特定に役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="8ade3-162">The NuGet message may help you identify the problem.</span></span>

### <a name="package-naming-enforcement"></a><span data-ttu-id="8ade3-163">パッケージの名前付けの適用</span><span class="sxs-lookup"><span data-stu-id="8ade3-163">Package naming enforcement</span></span>

<span data-ttu-id="8ade3-164">Microsoft では、ツールのパッケージ ID に関するガイダンスを変更したため、いくつかのツールが予測される名前で見つからなくなっています。</span><span class="sxs-lookup"><span data-stu-id="8ade3-164">Microsoft has changed its guidance on the Package ID for tools, resulting in a number of tools not being found with the predicted name.</span></span> <span data-ttu-id="8ade3-165">新しいガイダンスでは、すべての Microsoft ツールに "Microsoft" というプレフィックスが付いています。</span><span class="sxs-lookup"><span data-stu-id="8ade3-165">The new guidance is that all Microsoft tools be prefixed with "Microsoft."</span></span> <span data-ttu-id="8ade3-166">このプレフィックスは予約されており、Microsoft が承認した証明書で署名されたパッケージにのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="8ade3-166">This prefix is reserved and can only be used for packages signed with a Microsoft authorized certificate.</span></span>

<span data-ttu-id="8ade3-167">移行の間は、古い形式のパッケージ ID を持つ Microsoft ツールと、新しい形式を持つツールが混在します。</span><span class="sxs-lookup"><span data-stu-id="8ade3-167">During the transition, some Microsoft tools will have the old form of the package ID, while others will have the new form:</span></span>

```dotnetcli
dotnet tool install -g Microsoft.<toolName>
dotnet tool install -g <toolName>
```

<span data-ttu-id="8ade3-168">パッケージ ID が更新されると、最新の更新プログラムを取得するには、新しいパッケージ ID に変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ade3-168">As package IDs are updated, you'll need to change to the new package ID to get the latest updates.</span></span> <span data-ttu-id="8ade3-169">ツール名が簡略化されているパッケージは非推奨となります。</span><span class="sxs-lookup"><span data-stu-id="8ade3-169">Packages with the simplified tool name will be deprecated.</span></span>

### <a name="preview-releases"></a><span data-ttu-id="8ade3-170">プレビュー リリース</span><span class="sxs-lookup"><span data-stu-id="8ade3-170">Preview releases</span></span>

* <span data-ttu-id="8ade3-171">プレビュー リリースをインストールしようとして、`--version` オプションを使用してバージョンを指定しませんでした。</span><span class="sxs-lookup"><span data-stu-id="8ade3-171">You're attempting to install a preview release and didn't use the `--version` option to specify the version.</span></span>

<span data-ttu-id="8ade3-172">プレビュー段階にある .NET Core ツールは、プレビュー段階であることを、名前の一部で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ade3-172">.NET Core tools that are in preview must be specified with a portion of the name to indicate that they are in preview.</span></span> <span data-ttu-id="8ade3-173">プレビュー全体を含める必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8ade3-173">You don't need to include the entire preview.</span></span> <span data-ttu-id="8ade3-174">バージョン番号が想定される形式であると仮定すると、次の例のようなものを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8ade3-174">Assuming the version numbers are in the expected format, you can use something like the following example:</span></span>

```dotnetcli
dotnet tool install -g --version 1.1.0-pre <toolName>
```

> [!NOTE]
> <span data-ttu-id="8ade3-175">.NET Core CLI チームは、これを簡単にするために、今後のリリースで `--preview` スイッチを追加することを計画しています。</span><span class="sxs-lookup"><span data-stu-id="8ade3-175">The .NET Core CLI team is planning to add a `--preview` switch in a future release to make this easier.</span></span>

### <a name="package-isnt-a-net-core-tool"></a><span data-ttu-id="8ade3-176">パッケージが .NET Core ツールではない</span><span class="sxs-lookup"><span data-stu-id="8ade3-176">Package isn't a .NET Core tool</span></span>

* <span data-ttu-id="8ade3-177">この名前の NuGet パッケージは見つかりましたが、.NET Core ツールではありませんでした。</span><span class="sxs-lookup"><span data-stu-id="8ade3-177">A NuGet package by this name was found, but it wasn't a .NET Core tool.</span></span>

<span data-ttu-id="8ade3-178">.NET Core ツールではなく、通常の NuGet パッケージである NuGet パッケージをインストールしようとすると、次のようなエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8ade3-178">If you try to install a NuGet package that is a regular NuGet package and not a .NET Core tool, you'll see an error similar to the following:</span></span>

`NU1212: Invalid project-package combination for `<ToolName>`. DotnetToolReference project style can only contain references of the DotnetTool type.`

### <a name="nuget-feed-cant-be-accessed"></a><span data-ttu-id="8ade3-179">NuGet フィードにアクセスできない</span><span class="sxs-lookup"><span data-stu-id="8ade3-179">NuGet feed can't be accessed</span></span>

* <span data-ttu-id="8ade3-180">おそらくインターネット接続に問題があるため、必要な NuGet フィードにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="8ade3-180">The required NuGet feed can't be accessed, perhaps because of an Internet connection problem.</span></span>

<span data-ttu-id="8ade3-181">ツールをインストールするには、ツール パッケージが含まれている NuGet フィードにアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ade3-181">Tool installation requires access to the NuGet feed that contains the tool package.</span></span> <span data-ttu-id="8ade3-182">フィードが使用できない場合は失敗します。</span><span class="sxs-lookup"><span data-stu-id="8ade3-182">It fails if the feed isn't available.</span></span> <span data-ttu-id="8ade3-183">`nuget.config` でフィードを変更するか、特定の `nuget.config` ファイルを要求するか、`--add-source` スイッチを使用して追加のフィードを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="8ade3-183">You can alter feeds with `nuget.config`, request a specific `nuget.config` file, or specify additional feeds with the `--add-source` switch.</span></span> <span data-ttu-id="8ade3-184">既定では、NuGet では接続できないフィードに対してエラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="8ade3-184">By default, NuGet throws an error for any feed that can't connect.</span></span> <span data-ttu-id="8ade3-185">フラグ `--ignore-failed-sources` を指定すると、これらの到達できないソースをスキップできます。</span><span class="sxs-lookup"><span data-stu-id="8ade3-185">The flag `--ignore-failed-sources` can skip these non-reachable sources.</span></span>

### <a name="package-id-incorrect"></a><span data-ttu-id="8ade3-186">パッケージ ID が正しくない</span><span class="sxs-lookup"><span data-stu-id="8ade3-186">Package ID incorrect</span></span>

* <span data-ttu-id="8ade3-187">ツールの名前が間違って入力されています。</span><span class="sxs-lookup"><span data-stu-id="8ade3-187">You mistyped the name of the tool.</span></span>

<span data-ttu-id="8ade3-188">失敗でよくある理由は、ツール名が正しくないことです。</span><span class="sxs-lookup"><span data-stu-id="8ade3-188">A common reason for failure is that the tool name isn't correct.</span></span> <span data-ttu-id="8ade3-189">これは、入力ミスや、ツールが移動されたか非推奨になったために、発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8ade3-189">This can happen because of mistyping, or because the tool has moved or been deprecated.</span></span> <span data-ttu-id="8ade3-190">NuGet.org のツールで、確実に正しい名前を使用する方法の 1 つは、NuGet.org でツールを検索し、インストール コマンドをコピーすることです。</span><span class="sxs-lookup"><span data-stu-id="8ade3-190">For tools on NuGet.org, one way to ensure you have the name correct is to search for the tool at NuGet.org and copy the installation command.</span></span>

## <a name="see-also"></a><span data-ttu-id="8ade3-191">関連項目</span><span class="sxs-lookup"><span data-stu-id="8ade3-191">See also</span></span>
* [<span data-ttu-id="8ade3-192">.NET Core グローバル ツールの概要</span><span class="sxs-lookup"><span data-stu-id="8ade3-192">.NET Core Global Tools overview</span></span>](global-tools.md)
