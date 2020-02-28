---
title: .NET Core ツール
description: .NET Core ツールをインストール、使用、更新、および削除する方法。 グローバル ツール、tool-path ツール、およびローカル ツールについて説明します。
author: KathleenDollard
ms.date: 02/12/2020
ms.openlocfilehash: d8ee30df3fe063fd41a85072d145b1b5eec7d0d0
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543392"
---
# <a name="how-to-manage-net-core-tools"></a><span data-ttu-id="266fd-104">.NET Core ツールの管理方法</span><span class="sxs-lookup"><span data-stu-id="266fd-104">How to manage .NET Core tools</span></span>

<span data-ttu-id="266fd-105">**この記事の対象:** ✔️ .NET Core 2.1 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="266fd-105">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="266fd-106">.NET Core ツールは、コンソール アプリケーションを含む特殊な NuGet パッケージです。</span><span class="sxs-lookup"><span data-stu-id="266fd-106">A .NET Core tool is a special NuGet package that contains a console application.</span></span> <span data-ttu-id="266fd-107">ツールは、次の方法でコンピューターにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="266fd-107">A tool can be installed on your machine in the following ways:</span></span>

* <span data-ttu-id="266fd-108">グローバル ツールとして。</span><span class="sxs-lookup"><span data-stu-id="266fd-108">As a global tool.</span></span>

  <span data-ttu-id="266fd-109">ツールのバイナリは、PATH 環境変数に追加された既定のディレクトリにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="266fd-109">The tool binaries are installed in a default directory that is added to the PATH environment variable.</span></span> <span data-ttu-id="266fd-110">その場所を指定しなくても、マシン上の任意のディレクトリからツールを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="266fd-110">You can invoke the tool from any directory on the machine without specifying its location.</span></span> <span data-ttu-id="266fd-111">1 つのバージョンのツールがマシン上のすべてのディレクトリに使用されます。</span><span class="sxs-lookup"><span data-stu-id="266fd-111">One version of a tool is used for all directories on the machine.</span></span>

* <span data-ttu-id="266fd-112">カスタムの場所のグローバル ツールとして (tool-path ツールとも呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="266fd-112">As a global tool in a custom location (also known as a tool-path tool).</span></span>

  <span data-ttu-id="266fd-113">ツールのバイナリは、指定した場所にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="266fd-113">The tool binaries are installed in a location that you specify.</span></span> <span data-ttu-id="266fd-114">ツールを呼び出すには、インストール ディレクトリから実行するか、コマンド名と共にディレクトリを指定するか、ディレクトリを PATH 環境変数に追加します。</span><span class="sxs-lookup"><span data-stu-id="266fd-114">You can invoke the tool from the installation directory or by providing the directory with the command name or by adding the directory to the PATH environment variable.</span></span> <span data-ttu-id="266fd-115">1 つのバージョンのツールがマシン上のすべてのディレクトリに使用されます。</span><span class="sxs-lookup"><span data-stu-id="266fd-115">One version of a tool is used for all directories on the machine.</span></span>

* <span data-ttu-id="266fd-116">ローカル ツールとして (.NET Core SDK 3.0 以降に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="266fd-116">As a local tool (applies to .NET Core SDK 3.0 and later).</span></span>

  <span data-ttu-id="266fd-117">ツールのバイナリは、既定のディレクトリにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="266fd-117">The tool binaries are installed in a default directory.</span></span> <span data-ttu-id="266fd-118">ツールは、インストール ディレクトリまたはそのいずれかのサブディレクトリから起動します。</span><span class="sxs-lookup"><span data-stu-id="266fd-118">You invoke the tool from the installation directory or any of its subdirectories.</span></span> <span data-ttu-id="266fd-119">ディレクトリごとに、同じツールの異なるバージョンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="266fd-119">Different directories can use different versions of the same tool.</span></span>
  
  <span data-ttu-id="266fd-120">.NET CLI では、マニフェスト ファイルを使用して、ディレクトリにローカルとしてインストールされているツールを追跡します。</span><span class="sxs-lookup"><span data-stu-id="266fd-120">The .NET CLI uses manifest files to keep track of which tools are installed as local to a directory.</span></span> <span data-ttu-id="266fd-121">マニフェスト ファイルがソース コード リポジトリのルート ディレクトリに保存されると、共同作成者は、リポジトリを複製し、1 つの .NET Core CLI コマンドを呼び出して、マニフェスト ファイルに一覧表示されているすべてのツールがインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="266fd-121">When the manifest file is saved in the root directory of a source code repository, a contributor can clone the repository and invoke a single .NET Core CLI command that installs all of the tools listed in the manifest files.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="266fd-122">.NET Core ツールは完全な信頼で実行されます。</span><span class="sxs-lookup"><span data-stu-id="266fd-122">.NET Core tools run in full trust.</span></span> <span data-ttu-id="266fd-123">作成者を信頼していない場合は、その .NET Core ツールをインストールしないでください。</span><span class="sxs-lookup"><span data-stu-id="266fd-123">Do not install a .NET Core tool unless you trust the author.</span></span>

## <a name="find-a-tool"></a><span data-ttu-id="266fd-124">ツールを検索する</span><span class="sxs-lookup"><span data-stu-id="266fd-124">Find a tool</span></span>

<span data-ttu-id="266fd-125">現在、.NET Core にはツールの検索機能がありません。</span><span class="sxs-lookup"><span data-stu-id="266fd-125">Currently, .NET Core doesn't have a tool search feature.</span></span> <span data-ttu-id="266fd-126">ツールを見つける方法をいくつか紹介します。</span><span class="sxs-lookup"><span data-stu-id="266fd-126">Here are some ways to find tools:</span></span>

* <span data-ttu-id="266fd-127">ツールの一覧については、[natemcmaster/dotnet-tools](https://github.com/natemcmaster/dotnet-tools) GitHub リポジトリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="266fd-127">See the list of tools in the [natemcmaster/dotnet-tools](https://github.com/natemcmaster/dotnet-tools) GitHub repository.</span></span>
* <span data-ttu-id="266fd-128">[ToolGet](https://www.toolget.net/) を使用して .NET ツールを検索します。</span><span class="sxs-lookup"><span data-stu-id="266fd-128">Use [ToolGet](https://www.toolget.net/) to search for .NET tools.</span></span>
* <span data-ttu-id="266fd-129">ASP.NET Core チームが作成したツールのソース コードについては、[dotnet/aspnetcore GitHub リポジトリの Tools ディレクトリ](https://github.com/dotnet/aspnetcore/tree/master/src/Tools)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="266fd-129">See the source code for the tools created by the ASP.NET Core team in the [Tools directory of the dotnet/aspnetcore GitHub repository](https://github.com/dotnet/aspnetcore/tree/master/src/Tools).</span></span>
* <span data-ttu-id="266fd-130">診断ツールについては、[.NET Core dotnet 診断ツール](../diagnostics/index.md#net-core-dotnet-diagnostic-global-tools)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="266fd-130">Learn about diagnostic tools at [.NET Core dotnet diagnostic tools](../diagnostics/index.md#net-core-dotnet-diagnostic-global-tools).</span></span>
* <span data-ttu-id="266fd-131">[NuGet](https://www.nuget.org) Web サイトを検索します。</span><span class="sxs-lookup"><span data-stu-id="266fd-131">Search the [NuGet](https://www.nuget.org) website.</span></span> <span data-ttu-id="266fd-132">ただし、NuGet サイトには、ツール パッケージのみを検索できる機能はまだありません。</span><span class="sxs-lookup"><span data-stu-id="266fd-132">However, the NuGet site doesn't yet have a feature that lets you search only for tool packages.</span></span>

## <a name="check-the-author-and-statistics"></a><span data-ttu-id="266fd-133">作成者と統計情報の確認</span><span class="sxs-lookup"><span data-stu-id="266fd-133">Check the author and statistics</span></span>

<span data-ttu-id="266fd-134">.NET Core ツールは完全な信頼で実行され、グローバル ツールが PATH 環境変数に追加されるため、非常に強力です。</span><span class="sxs-lookup"><span data-stu-id="266fd-134">Since .NET Core tools run in full trust, and global tools are added to the PATH environment variable, they can be very powerful.</span></span> <span data-ttu-id="266fd-135">信頼できないユーザーからツールをダウンロードしないでください。</span><span class="sxs-lookup"><span data-stu-id="266fd-135">Don't download tools from people you don't trust.</span></span>

<span data-ttu-id="266fd-136">ツールが NuGet でホストされている場合は、ツールを検索することで作成者と統計情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="266fd-136">If the tool is hosted on NuGet, you can check the author and statistics by searching for the tool.</span></span>

## <a name="install-a-global-tool"></a><span data-ttu-id="266fd-137">グローバル ツールをインストールする</span><span class="sxs-lookup"><span data-stu-id="266fd-137">Install a global tool</span></span>

<span data-ttu-id="266fd-138">ツールをグローバル ツールとしてインストールするには、次の例に示すように、[dotnet tool install](dotnet-tool-install.md) の `-g` または `--global` オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="266fd-138">To install a tool as a global tool, use the `-g` or `--global` option of [dotnet tool install](dotnet-tool-install.md), as shown in the following example:</span></span>

```dotnetcli
dotnet tool install -g dotnetsay
```

<span data-ttu-id="266fd-139">出力には、次の例のように、ツールの起動に使用されたコマンドとインストールされているバージョンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="266fd-139">The output shows the command used to invoke the tool and the version installed, similar to the following example:</span></span>

```output
You can invoke the tool using the following command: dotnetsay
Tool 'dotnetsay' (version '2.1.4') was successfully installed.
```

<span data-ttu-id="266fd-140">ツールのバイナリの既定の場所は、オペレーティング システムによって異なります。</span><span class="sxs-lookup"><span data-stu-id="266fd-140">The default location for a tool's binaries depends on the operating system:</span></span>

| <span data-ttu-id="266fd-141">OS</span><span class="sxs-lookup"><span data-stu-id="266fd-141">OS</span></span>          | <span data-ttu-id="266fd-142">パス</span><span class="sxs-lookup"><span data-stu-id="266fd-142">Path</span></span>                          |
|-------------|-------------------------------|
| <span data-ttu-id="266fd-143">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="266fd-143">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
| <span data-ttu-id="266fd-144">Windows</span><span class="sxs-lookup"><span data-stu-id="266fd-144">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

<span data-ttu-id="266fd-145">この場所は、SDK を初めて実行したときにユーザーのパスに追加されるため、ツールの場所を指定せずに任意のディレクトリからグローバル ツールを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="266fd-145">This location is added to the user's path when the SDK is first run, so global tools can be invoked from any directory without specifying the tool location.</span></span>

<span data-ttu-id="266fd-146">ツールへのアクセスはユーザー固有であり、マシン グローバルではありません。</span><span class="sxs-lookup"><span data-stu-id="266fd-146">Tool access is user-specific, not machine global.</span></span> <span data-ttu-id="266fd-147">グローバル ツールは、ツールをインストールしたユーザーのみが使用できます。</span><span class="sxs-lookup"><span data-stu-id="266fd-147">A global tool is only available to the user that installed the tool.</span></span>

### <a name="install-a-global-tool-in-a-custom-location"></a><span data-ttu-id="266fd-148">カスタムの場所にグローバル ツールをインストールする</span><span class="sxs-lookup"><span data-stu-id="266fd-148">Install a global tool in a custom location</span></span>

<span data-ttu-id="266fd-149">カスタムの場所にグローバル ツールとしてツールをインストールするには、次の例に示すように、[dotnet tool install](dotnet-tool-install.md) の `--tool-path` オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="266fd-149">To install a tool as a global tool in a custom location, use the `--tool-path` option of [dotnet tool install](dotnet-tool-install.md), as shown in the following examples.</span></span>

<span data-ttu-id="266fd-150">Windows の場合:</span><span class="sxs-lookup"><span data-stu-id="266fd-150">On Windows:</span></span>

```dotnetcli
dotnet tool install dotnetsay --tool-path c:\dotnet-tools
```

<span data-ttu-id="266fd-151">Linux または macOS の場合:</span><span class="sxs-lookup"><span data-stu-id="266fd-151">On Linux or macOS:</span></span>

```dotnetcli
dotnet tool install dotnetsay --tool-path ~/bin
```

<span data-ttu-id="266fd-152">この場所は、.NET Core SDK によって PATH 環境変数に自動的に追加されません。</span><span class="sxs-lookup"><span data-stu-id="266fd-152">The .NET Core SDK doesn't add this location automatically to the PATH environment variable.</span></span> <span data-ttu-id="266fd-153">[tool-path ツールを呼び出す](#invoke-a-tool-path-tool)には、次のいずれかの方法を使用して、コマンドを使用できることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="266fd-153">To [invoke a tool-path tool](#invoke-a-tool-path-tool), you have to make sure the command is available by using one of the following methods:</span></span>

* <span data-ttu-id="266fd-154">インストール ディレクトリを PATH 環境変数に追加します。</span><span class="sxs-lookup"><span data-stu-id="266fd-154">Add the installation directory to the PATH environment variable.</span></span>
* <span data-ttu-id="266fd-155">ツールを起動するときは完全なパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="266fd-155">Specify the full path to the tool when you invoke it.</span></span>
* <span data-ttu-id="266fd-156">インストール ディレクトリ内からツールを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="266fd-156">Invoke the tool from within the installation directory.</span></span>

## <a name="install-a-local-tool"></a><span data-ttu-id="266fd-157">ローカル ツールをインストールする</span><span class="sxs-lookup"><span data-stu-id="266fd-157">Install a local tool</span></span>

<span data-ttu-id="266fd-158">**.NET Core 3.0 SDK 以降に適用されます。**</span><span class="sxs-lookup"><span data-stu-id="266fd-158">**Applies to .NET Core 3.0 SDK and later.**</span></span>

<span data-ttu-id="266fd-159">ローカル アクセス専用のツール (現在のディレクトリとサブディレクトリ用) をインストールするには、ツール マニフェスト ファイルに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="266fd-159">To install a tool for local access only (for the current directory and subdirectories), it has to be added to a tool manifest file.</span></span> <span data-ttu-id="266fd-160">ツール マニフェスト ファイルを作成するには、`dotnet new tool-manifest` コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="266fd-160">To create a tool manifest file, run the `dotnet new tool-manifest` command:</span></span>

```dotnetcli
dotnet new tool-manifest
```

<span data-ttu-id="266fd-161">このコマンドにより、 *.config* ディレクトリ以下に *dotnet-tools.json* というマニフェスト ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="266fd-161">This command creates a manifest file named *dotnet-tools.json* under the *.config* directory.</span></span> <span data-ttu-id="266fd-162">ローカル ツールをマニフェスト ファイルに追加するには、次の例に示すように、[dotnet tool install](dotnet-tool-install.md) コマンドを使用し、`--global` および `--tool-path` オプションを**省略**します。</span><span class="sxs-lookup"><span data-stu-id="266fd-162">To add a local tool to the manifest file, use the [dotnet tool install](dotnet-tool-install.md) command and **omit** the `--global` and `--tool-path` options, as shown in the following example:</span></span>

```dotnetcli
dotnet tool install dotnetsay
```

<span data-ttu-id="266fd-163">コマンド出力には、次の例のように、新しくインストールされたツールが含まれるマニフェスト ファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="266fd-163">The command output shows which manifest file the newly installed tool is in, similar to the following example:</span></span>

```console
You can invoke the tool from this directory using the following command:
dotnet tool run dotnetsay
Tool 'dotnetsay' (version '2.1.4') was successfully installed.
Entry is added to the manifest file /home/name/botsay/.config/dotnet-tools.json.
```

<span data-ttu-id="266fd-164">2 つのローカル ツールがインストールされたマニフェスト ファイルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="266fd-164">The following example shows a manifest file with two local tools installed:</span></span>

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {
    "botsay": {
      "version": "1.0.0",
      "commands": [
        "botsay"
      ]
    },
    "dotnetsay": {
      "version": "2.1.3",
      "commands": [
        "dotnetsay"
      ]
    }
  }
}
```

<span data-ttu-id="266fd-165">通常、ローカル ツールは、リポジトリのルート ディレクトリに追加します。</span><span class="sxs-lookup"><span data-stu-id="266fd-165">You typically add a local tool to the root directory of the repository.</span></span> <span data-ttu-id="266fd-166">マニフェスト ファイルをリポジトリにチェックインした後は、リポジトリからコードをチェック アウトした開発者が最新のマニフェスト ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="266fd-166">After you check in the manifest file to the repository, developers who check out code from the repository get the latest manifest file.</span></span> <span data-ttu-id="266fd-167">マニフェスト ファイルに記載されているすべてのツールをインストールするには、`dotnet tool restore` コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="266fd-167">To install all of the tools listed in the manifest file, they run the `dotnet tool restore` command:</span></span>

```dotnetcli
dotnet tool restore
```

<span data-ttu-id="266fd-168">出力には、復元されたツールが示されます。</span><span class="sxs-lookup"><span data-stu-id="266fd-168">The output indicates which tools were restored:</span></span>

```console
Tool 'botsay' (version '1.0.0') was restored. Available commands: botsay
Tool 'dotnetsay' (version '2.1.3') was restored. Available commands: dotnetsay
Restore was successful.
```

## <a name="install-a-specific-tool-version"></a><span data-ttu-id="266fd-169">特定のツールバー ジョンをインストールする</span><span class="sxs-lookup"><span data-stu-id="266fd-169">Install a specific tool version</span></span>

<span data-ttu-id="266fd-170">プレリリース バージョンまたは特定バージョンのツールをインストールするには、次の例に示すように、`--version` オプションを使用してバージョン番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="266fd-170">To install a pre-release version or a specific version of a tool, specify the version number by using the `--version` option, as shown in the following example:</span></span>

```dotnetcli
dotnet tool install dotnetsay --version 2.1.3
```

## <a name="use-a-tool"></a><span data-ttu-id="266fd-171">ツールを使用する</span><span class="sxs-lookup"><span data-stu-id="266fd-171">Use a tool</span></span>

<span data-ttu-id="266fd-172">ツールを呼び出すために使用するコマンドは、インストールするパッケージの名前と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="266fd-172">The command that you use to invoke a tool may be different from the name of the package that you install.</span></span> <span data-ttu-id="266fd-173">現在のユーザーのマシンに現在インストールされているすべてのツールを表示するには、[dotnet tool list](dotnet-tool-list.md) コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="266fd-173">To display all of the tools currently installed on the machine for the current user, use the [dotnet tool list](dotnet-tool-list.md) command:</span></span>

```dotnetcli
dotnet tool list
```

<span data-ttu-id="266fd-174">出力には、次の例のように、各ツールのバージョンとコマンドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="266fd-174">The output shows each tool's version and command, similar to the following example:</span></span>

```console
Package Id      Version      Commands       Manifest
-------------------------------------------------------------------------------------------
botsay          1.0.0        botsay         /home/name/repository/.config/dotnet-tools.json
dotnetsay       2.1.3        dotnetsay      /home/name/repository/.config/dotnet-tools.json
```

<span data-ttu-id="266fd-175">この例に示すように、一覧にはローカル ツールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="266fd-175">As shown in this example, the list shows local tools.</span></span> <span data-ttu-id="266fd-176">グローバル ツールを表示するには、`--global` オプションを使用します。また、tool-path ツールを表示するには、`--tool-path` オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="266fd-176">To see global tools, use the `--global` option, and to see tool-path tools, use the `--tool-path` option.</span></span>

### <a name="invoke-a-global-tool"></a><span data-ttu-id="266fd-177">グローバル ツールを呼び出す</span><span class="sxs-lookup"><span data-stu-id="266fd-177">Invoke a global tool</span></span>

<span data-ttu-id="266fd-178">グローバル ツールの場合は、ツール コマンドを単独で使用します。</span><span class="sxs-lookup"><span data-stu-id="266fd-178">For global tools, use the tool command by itself.</span></span> <span data-ttu-id="266fd-179">たとえば、コマンドが `dotnetsay` または `dotnet-doc` の場合は、そのコマンドを使用してコマンドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="266fd-179">For example, if the command is `dotnetsay` or `dotnet-doc`, that's what you use to invoke the command:</span></span>

```console
dotnetsay
dotnet-doc
```

<span data-ttu-id="266fd-180">コマンドがプレフィックス `dotnet-` で始まる場合、ツールを呼び出すもう 1 つの方法は、`dotnet` コマンドを使用して、ツール コマンド プレフィックスを省略することです。</span><span class="sxs-lookup"><span data-stu-id="266fd-180">If the command begins with the prefix `dotnet-`, an alternative way to invoke the tool is to use the `dotnet` command and omit the tool command prefix.</span></span> <span data-ttu-id="266fd-181">たとえば、コマンドが `dotnet-doc` の場合、次のコマンドを使ってツールを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="266fd-181">For example, if the command is `dotnet-doc`, the following command invokes the tool:</span></span>

```dotnetcli
dotnet doc
```

<span data-ttu-id="266fd-182">ただし、次のシナリオでは、`dotnet` コマンドを使ってグローバル ツールを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="266fd-182">However, in the following scenario you can't use the `dotnet` command to invoke a global tool:</span></span>

* <span data-ttu-id="266fd-183">グローバル ツールとローカル ツールには、同じコマンドの先頭に `dotnet-` が付きます。</span><span class="sxs-lookup"><span data-stu-id="266fd-183">A global tool and a local tool have the same command prefixed by `dotnet-`.</span></span>
* <span data-ttu-id="266fd-184">ローカル ツールのスコープ内にあるディレクトリからグローバル ツールを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="266fd-184">You want to invoke the global tool from a directory that is in scope for the local tool.</span></span>

<span data-ttu-id="266fd-185">このシナリオでは、`dotnet doc` および `dotnet dotnet-doc` によってローカル ツールが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="266fd-185">In this scenario, `dotnet doc` and `dotnet dotnet-doc` invoke the local tool.</span></span> <span data-ttu-id="266fd-186">グローバル ツールを呼び出すには、コマンドを単独で使用します。</span><span class="sxs-lookup"><span data-stu-id="266fd-186">To invoke the global tool, use the command by itself:</span></span>

```dotnetcli
dotnet-doc
```

### <a name="invoke-a-tool-path-tool"></a><span data-ttu-id="266fd-187">tool-path ツールを呼び出す</span><span class="sxs-lookup"><span data-stu-id="266fd-187">Invoke a tool-path tool</span></span>

<span data-ttu-id="266fd-188">`tool-path` オプションを使用してインストールされたグローバル ツールを呼び出すには、[この記事で前述](#install-a-global-tool-in-a-custom-location)したように、コマンドを使用できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="266fd-188">To invoke a global tool that is installed by using the `tool-path` option, make sure the command is available, as explained [earlier in this article](#install-a-global-tool-in-a-custom-location).</span></span>

### <a name="invoke-a-local-tool"></a><span data-ttu-id="266fd-189">ローカル ツールを呼び出す</span><span class="sxs-lookup"><span data-stu-id="266fd-189">Invoke a local tool</span></span>

<span data-ttu-id="266fd-190">ローカル ツールを呼び出すには、インストール ディレクトリ内から `dotnet` コマンドを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="266fd-190">To invoke a local tool, you have to use the `dotnet` command from within the installation directory.</span></span> <span data-ttu-id="266fd-191">次の例に示すように、長い形式 (`dotnet tool run <COMMAND_NAME>`) または短い形式 (`dotnet <COMMAND_NAME>`) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="266fd-191">You can use the long form (`dotnet tool run <COMMAND_NAME>`) or the short form (`dotnet <COMMAND_NAME>`), as shown in the following examples:</span></span>

```dotnetcli
dotnet tool run dotnetsay
dotnet dotnetsay
```

<span data-ttu-id="266fd-192">コマンドの先頭に `dotnet-` が付いている場合、ツールを呼び出すときにプレフィックスを含めるか省略することができます。</span><span class="sxs-lookup"><span data-stu-id="266fd-192">If the command is prefixed by `dotnet-`, you can include or omit the prefix when you invoke the tool.</span></span> <span data-ttu-id="266fd-193">たとえば、コマンドが `dotnet-doc` の場合、次の例のいずれかを使ってローカル ツールを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="266fd-193">For example, if the command is `dotnet-doc`, any of the following examples invokes the local tool:</span></span>

```dotnetcli
dotnet tool run dotnet-doc
dotnet dotnet-doc
dotnet doc
```

## <a name="update-a-tool"></a><span data-ttu-id="266fd-194">ツールを更新する</span><span class="sxs-lookup"><span data-stu-id="266fd-194">Update a tool</span></span>

<span data-ttu-id="266fd-195">ツールを更新するには、ツールをアンインストールしてから、最新の安定バージョンで再インストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="266fd-195">Updating a tool involves uninstalling and reinstalling it with the latest stable version.</span></span> <span data-ttu-id="266fd-196">ツールを更新するには、ツールのインストールに使用したものと同じオプションを指定して [dotnet tool update](dotnet-tool-update.md) コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="266fd-196">To update a tool, use the [dotnet tool update](dotnet-tool-update.md) command with the same option that you used to install the tool:</span></span>

```dotnetcli
dotnet tool update --global <packagename>
dotnet tool update --tool-path <packagename>
dotnet tool update <packagename>
```

<span data-ttu-id="266fd-197">ローカル ツールの場合、SDK を使うと、現在のディレクトリと親ディレクトリを検索してパッケージ ID を含む最初のマニフェスト ファイルを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="266fd-197">For a local tool, the SDK finds the first manifest file that contains the package ID by looking in the current directory and parent directories.</span></span> <span data-ttu-id="266fd-198">マニフェスト ファイルにそのようなパッケージ ID がない場合は、SDK によって、最も近いマニフェスト ファイルに新しいエントリが追加されます。</span><span class="sxs-lookup"><span data-stu-id="266fd-198">If there is no such package ID in any manifest file, the SDK adds a new entry to the closest manifest file.</span></span>

## <a name="uninstall-a-tool"></a><span data-ttu-id="266fd-199">ツールをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="266fd-199">Uninstall a tool</span></span>

<span data-ttu-id="266fd-200">[dotnet tool uninstall](dotnet-tool-uninstall.md) コマンドを使用して、ツールのインストールに使用したものと同じオプションを使用してツールを削除します。</span><span class="sxs-lookup"><span data-stu-id="266fd-200">Remove a tool by using the [dotnet tool uninstall](dotnet-tool-uninstall.md) command with the same option that you used to install the tool:</span></span>

```dotnetcli
dotnet tool uninstall --global <packagename>
dotnet tool uninstall --tool-path<packagename>
dotnet tool uninstall <packagename>
```

<span data-ttu-id="266fd-201">ローカル ツールの場合、SDK を使うと、現在のディレクトリと親ディレクトリを検索してパッケージ ID を含む最初のマニフェスト ファイルを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="266fd-201">For a local tool, the SDK finds the first manifest file that contains the package ID by looking in the current directory and parent directories.</span></span>

## <a name="get-help-and-troubleshoot"></a><span data-ttu-id="266fd-202">ヘルプとトラブルシューティングを取得する</span><span class="sxs-lookup"><span data-stu-id="266fd-202">Get help and troubleshoot</span></span>

<span data-ttu-id="266fd-203">使用できる `dotnet tool` コマンドの一覧を取得するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="266fd-203">To get a list of available `dotnet tool` commands, enter the following command:</span></span>

```dotnetcli
dotnet tool --help
```

<span data-ttu-id="266fd-204">ツールの使用手順を取得するには、次のコマンドのいずれかを入力するか、ツールの Web サイトを参照してください。</span><span class="sxs-lookup"><span data-stu-id="266fd-204">To get tool usage instructions, enter one of the following commands or see the tool's website:</span></span>

```dotnetcli
<command> --help
dotnet <command> --help
```

<span data-ttu-id="266fd-205">ツールのインストールまたは実行に失敗した場合は、「[.NET Core ツールの使用に関する問題のトラブルシューティング](troubleshoot-usage-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="266fd-205">If a tool fails to install or run, see [Troubleshoot .NET Core tool usage issues](troubleshoot-usage-issues.md).</span></span>
