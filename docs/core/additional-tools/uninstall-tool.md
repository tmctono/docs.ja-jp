---
title: アンインストール ツール
description: .NET CORE アンインストール ツールの概要です。これは、.NET Core SKD とランタイムの制御されたクリーンアップを可能にするガイド付きツールです。
author: sfoslund
ms.date: 01/06/2020
ms.openlocfilehash: 4944c983cbd02b456c3a09a1b03bc28ba6e458cc
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714552"
---
# <a name="net-core-uninstall-tool"></a><span data-ttu-id="63212-103">.NET Core アンインストール ツール</span><span class="sxs-lookup"><span data-stu-id="63212-103">.NET Core Uninstall Tool</span></span>

<span data-ttu-id="63212-104">[.NET Core アンインストール ツール](https://github.com/dotnet/cli-lab/releases) (`dotnet-core-uninstall`) を使用すると、.NET Core SDK とランタイムをシステムから削除できます。</span><span class="sxs-lookup"><span data-stu-id="63212-104">The [.NET Core Uninstall Tool](https://github.com/dotnet/cli-lab/releases) (`dotnet-core-uninstall`) lets you remove .NET Core SDKs and Runtimes from a system.</span></span> <span data-ttu-id="63212-105">一連のオプションを使用して、アンインストールするバージョンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="63212-105">A collection of options is available to specify which versions you want to uninstall.</span></span>

<span data-ttu-id="63212-106">このツールでは、Windows と macOS がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="63212-106">The tool supports Windows and macOS.</span></span> <span data-ttu-id="63212-107">Linux は現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="63212-107">Linux is currently not supported.</span></span>

<span data-ttu-id="63212-108">Windows では、ツールは次のいずれかのインストーラーを使用してインストールされた SDK とランタイムのみをアンインストールできます。</span><span class="sxs-lookup"><span data-stu-id="63212-108">On Windows, the tool can only uninstall SDKs and Runtimes that were installed using one of the following installers:</span></span>

- <span data-ttu-id="63212-109">.NET Core SDK およびランタイム インストーラー。</span><span class="sxs-lookup"><span data-stu-id="63212-109">The .NET Core SDK and runtime installer.</span></span>
- <span data-ttu-id="63212-110">Visual Studio 2019 バージョン 16.3 より前のバージョンの Visual Studio インストーラー。</span><span class="sxs-lookup"><span data-stu-id="63212-110">The Visual Studio installer in versions earlier than Visual Studio 2019 version 16.3.</span></span>

<span data-ttu-id="63212-111">macOS では、このツールでアンインストールできるのは */usr/local/share/dotnet* フォルダーにある SDK とランタイムのみです。</span><span class="sxs-lookup"><span data-stu-id="63212-111">On macOS, the tool can only uninstall SDKs and runtimes located in the */usr/local/share/dotnet* folder.</span></span>

<span data-ttu-id="63212-112">これらの制限のため、このツールでは、コンピューター上の一部の .NET Core SDK とランタイムをアンインストールできない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="63212-112">Because of these limitations, the tool may not be able to uninstall all of the .NET Core SDKs and runtimes on your machine.</span></span> <span data-ttu-id="63212-113">`dotnet --info` コマンドを使用して、インストールされているすべての .NET Core SDK とランタイム (このツールで削除できない SDK やランタイムを含む) を検出できます。</span><span class="sxs-lookup"><span data-stu-id="63212-113">You can use the `dotnet --info` command to find all of the .NET Core SDKs and runtimes installed, including those SDKs and runtimes that this tool can't remove.</span></span> <span data-ttu-id="63212-114">`dotnet-core-uninstall list` コマンドを実行すると、このツールでアンインストールできる SDK が表示されます。</span><span class="sxs-lookup"><span data-stu-id="63212-114">The `dotnet-core-uninstall list` command displays which SDKs can be uninstalled with the tool.</span></span>

## <a name="install-the-tool"></a><span data-ttu-id="63212-115">ツールをインストールする</span><span class="sxs-lookup"><span data-stu-id="63212-115">Install the tool</span></span>

<span data-ttu-id="63212-116">.NET Core アンインストール ツールは、[dotnet/cli-lab](https://github.com/dotnet/cli-lab/releases) GitHub リポジトリからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="63212-116">You can download the .NET Core Uninstall Tool from the [dotnet/cli-lab](https://github.com/dotnet/cli-lab/releases) GitHub repository.</span></span>

> [!NOTE]
> <span data-ttu-id="63212-117">このツールでは、.NET Core SDK とランタイムをアンインストールするために昇格が必要です。</span><span class="sxs-lookup"><span data-stu-id="63212-117">The tool requires elevation to uninstall .NET Core SDKs and runtimes.</span></span> <span data-ttu-id="63212-118">そのため、Windows では *C:\Program Files*、macOS では */usr/local/bin* などの書き込み保護されたディレクトリにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="63212-118">Therefore, it should be installed in a write-protected directory such as *C:\Program Files* on Windows or */usr/local/bin* on macOS.</span></span> <span data-ttu-id="63212-119">「[dotnet コマンドの特権アクセス](../tools/elevated-access.md)」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="63212-119">See also [Elevated access for dotnet commands](../tools/elevated-access.md).</span></span> <span data-ttu-id="63212-120">詳細なインストール手順については、[GitHub リリース ページ](https://github.com/dotnet/cli-lab/releases)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="63212-120">Detailed installation instructions are available on the [GitHub Releases page](https://github.com/dotnet/cli-lab/releases).</span></span>

## <a name="run-the-tool"></a><span data-ttu-id="63212-121">ツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="63212-121">Run the tool</span></span>

<span data-ttu-id="63212-122">次の手順は、アンインストール ツールを実行するための推奨方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="63212-122">The following steps show the recommended approach for running the uninstall tool:</span></span>

- [<span data-ttu-id="63212-123">手順 1 - インストールされている .NET Core SDK とランタイムを表示する</span><span class="sxs-lookup"><span data-stu-id="63212-123">Step 1 - Display installed .NET Core SDKs and runtimes</span></span>](#step-1---display-installed-net-core-sdks-and-runtimes)
- [<span data-ttu-id="63212-124">手順 2 - ドライ ランを実行する</span><span class="sxs-lookup"><span data-stu-id="63212-124">Step 2 - Do a dry run</span></span>](#step-2---do-a-dry-run)
- [<span data-ttu-id="63212-125">手順 3 - .NET Core SDK とランタイムをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="63212-125">Step 3 - Uninstall .NET Core SDKs and Runtimes</span></span>](#step-3---uninstall-net-core-sdks-and-runtimes)
- [<span data-ttu-id="63212-126">手順 4 - NuGet フォールバック フォルダーを削除する (省略可能)</span><span class="sxs-lookup"><span data-stu-id="63212-126">Step 4 - Delete the NuGet fallback folder (optional)</span></span>](#step-4---delete-the-nuget-fallback-folder-optional)

### <a name="step-1---display-installed-net-core-sdks-and-runtimes"></a><span data-ttu-id="63212-127">手順 1 - インストールされている .NET Core SDK とランタイムを表示する</span><span class="sxs-lookup"><span data-stu-id="63212-127">Step 1 - Display installed .NET Core SDKs and runtimes</span></span>

<span data-ttu-id="63212-128">`dotnet-core-uninstall list` コマンドを実行すると、このツールで削除できる、インストールされている .NET Core SDK とランタイムが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="63212-128">The `dotnet-core-uninstall list` command lists the installed .NET Core SDKs and runtimes that can be removed with this tool.</span></span> <span data-ttu-id="63212-129">一部の SDK とランタイムは、Visual Studio で必要な場合があり、それらのアンインストールが推奨されない理由を示す注釈と共に表示されます。</span><span class="sxs-lookup"><span data-stu-id="63212-129">Some SDKs and runtimes may be required by Visual Studio and they're displayed with a note of why it isn't recommended to uninstall them.</span></span>

<span data-ttu-id="63212-130">**dotnet-core-uninstall list**</span><span class="sxs-lookup"><span data-stu-id="63212-130">**dotnet-core-uninstall list**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="63212-131">構文</span><span class="sxs-lookup"><span data-stu-id="63212-131">Synopsis</span></span>

```console
dotnet-core-uninstall list [options]
```

#### <a name="options"></a><span data-ttu-id="63212-132">オプション</span><span class="sxs-lookup"><span data-stu-id="63212-132">Options</span></span>

## <a name="windows"></a>[<span data-ttu-id="63212-133">Windows</span><span class="sxs-lookup"><span data-stu-id="63212-133">Windows</span></span>](#tab/windows)

* **`--aspnet-runtime`**

  <span data-ttu-id="63212-134">このツールでアンインストールできるすべての ASP.NET Core ランタイムを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="63212-134">Lists all the ASP.NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="63212-135">このツールでアンインストールできるすべての .NET Core ランタイムとホスティングのバンドルを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="63212-135">Lists all the .NET Core runtime and hosting bundles that can be uninstalled with this tool.</span></span>

* **`--runtime`**

  <span data-ttu-id="63212-136">このツールでアンインストールできるすべての .NET Core ランタイムを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="63212-136">Lists all .NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--sdk`**

  <span data-ttu-id="63212-137">このツールでアンインストールできるすべての .NET Core SDK を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="63212-137">Lists all .NET Core SDKs that can be uninstalled with this tool.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="63212-138">詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="63212-138">Sets the verbosity level.</span></span> <span data-ttu-id="63212-139">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="63212-139">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="63212-140">既定値は `normal` です。</span><span class="sxs-lookup"><span data-stu-id="63212-140">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="63212-141">このツールでアンインストールできるすべての x64 .NET Core SDK とランタイムを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="63212-141">Lists all x64 .NET Core SDKs and runtimes that can be uninstalled with this tool.</span></span>

* **`--x86`**

  <span data-ttu-id="63212-142">このツールでアンインストールできるすべての x86 .NET Core SDK とランタイムを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="63212-142">Lists all x86 .NET Core SDKs and runtimes that can be uninstalled with this tool.</span></span>

## <a name="macos"></a>[<span data-ttu-id="63212-143">macOS</span><span class="sxs-lookup"><span data-stu-id="63212-143">macOS</span></span>](#tab/macos)

* **`--runtime`**

  <span data-ttu-id="63212-144">このツールでアンインストールできるすべての .NET Core ランタイムを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="63212-144">Lists all .NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--sdk`**

  <span data-ttu-id="63212-145">このツールでアンインストールできるすべての .NET Core SDK を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="63212-145">Lists all .NET Core SDKs that can be uninstalled with this tool.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="63212-146">詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="63212-146">Sets the verbosity level.</span></span> <span data-ttu-id="63212-147">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="63212-147">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="63212-148">既定値は `normal` です。</span><span class="sxs-lookup"><span data-stu-id="63212-148">The default value is `normal`.</span></span>
  
---

#### <a name="examples"></a><span data-ttu-id="63212-149">使用例</span><span class="sxs-lookup"><span data-stu-id="63212-149">Examples</span></span>

* <span data-ttu-id="63212-150">このツールで削除できるすべての .NET Core SDK とランタイムを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="63212-150">List all .NET Core SDKs and runtimes that can be removed with this tool:</span></span>

  ```console
  dotnet-core-uninstall list
  ```

* <span data-ttu-id="63212-151">すべての x64 .NET Core SDK とランタイムを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="63212-151">List all x64 .NET Core SDKs and runtimes:</span></span>

  ```console
  dotnet-core-uninstall list --x64
  ```

* <span data-ttu-id="63212-152">すべての x86 .NET Core SDK を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="63212-152">List all x86 .NET Core SDKs:</span></span>

  ```console
  dotnet-core-uninstall list --sdk --x86
  ```

### <a name="step-2---do-a-dry-run"></a><span data-ttu-id="63212-153">手順 2 - ドライ ランを実行する</span><span class="sxs-lookup"><span data-stu-id="63212-153">Step 2 - Do a dry run</span></span>

<span data-ttu-id="63212-154">`dotnet-core-uninstall dry-run` および `dotnet-core-uninstall whatif` コマンドは、アンインストールを実行せずに指定されたオプションに基づいて削除される .NET Core SDK とランタイムを表示します。</span><span class="sxs-lookup"><span data-stu-id="63212-154">The `dotnet-core-uninstall dry-run` and `dotnet-core-uninstall whatif` commands display the .NET Core SDKs and runtimes that will be removed based on the options provided without performing the uninstall.</span></span> <span data-ttu-id="63212-155">これらのコマンドはシノニムです。</span><span class="sxs-lookup"><span data-stu-id="63212-155">These commands are synonyms.</span></span>

<span data-ttu-id="63212-156">**dotnet-core-uninstall dry-run and dotnet-core-uninstall whatif**</span><span class="sxs-lookup"><span data-stu-id="63212-156">**dotnet-core-uninstall dry-run and dotnet-core-uninstall whatif**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="63212-157">構文</span><span class="sxs-lookup"><span data-stu-id="63212-157">Synopsis</span></span>

```console
dotnet-core-uninstall dry-run [options] [<VERSION>...]

dotnet-core-uninstall whatif [options] [<VERSION>...]
```

#### <a name="arguments"></a><span data-ttu-id="63212-158">引数</span><span class="sxs-lookup"><span data-stu-id="63212-158">Arguments</span></span>

* **`VERSION`**

  <span data-ttu-id="63212-159">アンインストールする指定されたバージョン。</span><span class="sxs-lookup"><span data-stu-id="63212-159">The specified version to uninstall.</span></span> <span data-ttu-id="63212-160">スペースで区切って、複数のバージョンを順々に指定できます。</span><span class="sxs-lookup"><span data-stu-id="63212-160">You may list several versions one after the other, separated by spaces.</span></span> <span data-ttu-id="63212-161">応答ファイルもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="63212-161">Response files are also supported.</span></span>

  > [!TIP]
  > <span data-ttu-id="63212-162">すべてのバージョンをコマンド ラインに指定する代わりに応答ファイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="63212-162">Response files are an alternative to placing all the versions on the command line.</span></span>
  > <span data-ttu-id="63212-163">それらはテキスト ファイルで、通常、\*.rsp 拡張子が付いています。各バージョンは別々の行に指定されます。</span><span class="sxs-lookup"><span data-stu-id="63212-163">They're text files, typically with a \*.rsp extension, and each version is listed on a separate line.</span></span>
  > <span data-ttu-id="63212-164">`VERSION` 引数の応答ファイルを指定するには、\@ 文字を使用し、そのすぐ後に応答ファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="63212-164">To specify a response file for the `VERSION` argument, use the \@ character immediately followed by the response file name.</span></span>

#### <a name="options"></a><span data-ttu-id="63212-165">オプション</span><span class="sxs-lookup"><span data-stu-id="63212-165">Options</span></span>

## <a name="windows"></a>[<span data-ttu-id="63212-166">Windows</span><span class="sxs-lookup"><span data-stu-id="63212-166">Windows</span></span>](#tab/windows)

* **`--all`**

  <span data-ttu-id="63212-167">すべての .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-167">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="63212-168">指定したバージョンよりも小さいバージョンの .NET Core SDK とランタイムのみを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-168">Removes only the .NET Core SDKs and runtimes with a version smaller than the specified version.</span></span> <span data-ttu-id="63212-169">指定したバージョンはインストールされたままになります。</span><span class="sxs-lookup"><span data-stu-id="63212-169">The specified version remains installed.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="63212-170">指定したバージョンを除く、すべての .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-170">Removes all .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="63212-171">最上位の 1 つのバージョンを除く、すべての .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-171">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="63212-172">上位の修正プログラムによって置き換えられた .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-172">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="63212-173">このオプションは、global. json を保護します。</span><span class="sxs-lookup"><span data-stu-id="63212-173">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="63212-174">プレビューとしてマークされている .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-174">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="63212-175">最上位の 1 つのプレビューを除き、プレビューとしてマークされているすべての .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-175">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--aspnet-runtime`**

  <span data-ttu-id="63212-176">ASP.NET Core ランタイムのみを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-176">Removes ASP.NET Core runtimes only.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="63212-177">.NET Core ランタイムとホスティングのバンドルのみを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-177">Removes .NET Core runtime and hosting bundles only.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="63212-178">指定した `major.minor` バージョンに一致する .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-178">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="63212-179">.NET Core ランタイムのみを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-179">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="63212-180">.NET Core SDK のみを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-180">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="63212-181">詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="63212-181">Sets the verbosity level.</span></span> <span data-ttu-id="63212-182">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="63212-182">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="63212-183">既定値は `normal` です。</span><span class="sxs-lookup"><span data-stu-id="63212-183">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="63212-184">x64 SDK またはランタイムを削除するには、`--sdk`、`--runtime`、および `--aspnet-runtime` と共に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63212-184">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x64 SDKs or runtimes.</span></span>

* **`--x86`**

  <span data-ttu-id="63212-185">x86 SDK またはランタイムを削除するには、`--sdk`、`--runtime`、および `--aspnet-runtime` と共に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63212-185">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x86 SDKs or runtimes.</span></span>

* <span data-ttu-id="63212-186">**`--force`** Visual Studio によって使用される可能性があるバージョンを強制的に削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-186">**`--force`** Forces removal of versions that might be used by Visual Studio.</span></span>

<span data-ttu-id="63212-187">メモ:</span><span class="sxs-lookup"><span data-stu-id="63212-187">Notes:</span></span>

1. <span data-ttu-id="63212-188">`--sdk`、`--runtime`、`--aspnet-runtime`、および `--hosting-bundle` の 1 つだけが必要です。</span><span class="sxs-lookup"><span data-stu-id="63212-188">Exactly one of `--sdk`, `--runtime`, `--aspnet-runtime`, and `--hosting-bundle` is required.</span></span>
2. <span data-ttu-id="63212-189">`--all`、`--all-below`、`--all-but`、`--all-but-latest`、`--all-lower-patches`、`--all-previews`、`--all-previews-but-latest`、`--major-minor`、および `[<VERSION>...]` は排他的です。</span><span class="sxs-lookup"><span data-stu-id="63212-189">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>
3. <span data-ttu-id="63212-190">`--x64` または `--x86` が指定されていない場合は、x64 と x86 の両方が削除されます。</span><span class="sxs-lookup"><span data-stu-id="63212-190">If `--x64` or `--x86` aren't specified, then both x64 and x86 will be removed.</span></span>

## <a name="macos"></a>[<span data-ttu-id="63212-191">macOS</span><span class="sxs-lookup"><span data-stu-id="63212-191">macOS</span></span>](#tab/macos)

* **`--all`**

  <span data-ttu-id="63212-192">すべての .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-192">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="63212-193">指定したバージョンより下の .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-193">Removes .NET Core SDKs and runtimes below the specified version.</span></span> <span data-ttu-id="63212-194">指定したバージョンはそのまま残ります。</span><span class="sxs-lookup"><span data-stu-id="63212-194">The specified version will remain.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="63212-195">指定したバージョンを除き、.NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-195">Removes .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="63212-196">最上位の 1 つのバージョンを除く、すべての .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-196">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="63212-197">上位の修正プログラムによって置き換えられた .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-197">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="63212-198">このオプションは、global. json を保護します。</span><span class="sxs-lookup"><span data-stu-id="63212-198">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="63212-199">プレビューとしてマークされている .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-199">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="63212-200">最上位の 1 つのプレビューを除き、プレビューとしてマークされているすべての .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-200">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="63212-201">指定した `major.minor` バージョンに一致する .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-201">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="63212-202">.NET Core ランタイムのみを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-202">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="63212-203">.NET Core SDK のみを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-203">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="63212-204">詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="63212-204">Sets the verbosity level.</span></span> <span data-ttu-id="63212-205">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="63212-205">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="63212-206">既定値は `normal` です。</span><span class="sxs-lookup"><span data-stu-id="63212-206">The default value is `normal`.</span></span>
  
* <span data-ttu-id="63212-207">**`--force`** Visual Studio または SDK によって使用される可能性があるバージョンを強制的に削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-207">**`--force`** Forces removal of versions that might be used by Visual Studio or SDKs.</span></span>

<span data-ttu-id="63212-208">メモ:</span><span class="sxs-lookup"><span data-stu-id="63212-208">Notes:</span></span>

1. <span data-ttu-id="63212-209">`--sdk` と `--runtime` のうち 1 つだけが必要です。</span><span class="sxs-lookup"><span data-stu-id="63212-209">Exactly one of `--sdk` and `--runtime` is required.</span></span>
2. <span data-ttu-id="63212-210">`--all`、`--all-below`、`--all-but`、`--all-but-latest`、`--all-lower-patches`、`--all-previews`、`--all-previews-but-latest`、`--major-minor`、および `[<VERSION>...]` は排他的です。</span><span class="sxs-lookup"><span data-stu-id="63212-210">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>

---

#### <a name="examples"></a><span data-ttu-id="63212-211">使用例</span><span class="sxs-lookup"><span data-stu-id="63212-211">Examples</span></span>

> [!NOTE]
> <span data-ttu-id="63212-212">既定で、Visual Studio またはその他の SDK に必要な可能性がある .NET Core SDK とランタイムは `dotnet-core-uninstall dry-run` 出力には含まれません。</span><span class="sxs-lookup"><span data-stu-id="63212-212">By default, .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs are not included in `dotnet-core-uninstall dry-run` output.</span></span> <span data-ttu-id="63212-213">次の例では、コンピューターの状態によっては、指定された SDK とランタイムの一部が出力に含まれない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="63212-213">In the following examples, some of the specified SDKs and runtimes may not be included in the output, depending on the state of the machine.</span></span> <span data-ttu-id="63212-214">すべての SDK とランタイムを含めるには、それらを引数として明示的に指定するか、`--force` オプションを使用してください。</span><span class="sxs-lookup"><span data-stu-id="63212-214">To include all SDKs and runtimes, list them explicitly as arguments or use the `--force` option.</span></span>

* <span data-ttu-id="63212-215">上位の修正プログラムによって置き換えられたすべての .NET Core ランタイムを削除するドライ ラン。</span><span class="sxs-lookup"><span data-stu-id="63212-215">Dry run of removing all .NET Core runtimes that have been superseded by higher patches:</span></span>

  ```console
  dotnet-core-uninstall dry-run --all-lower-patches --runtime
  ```

* <span data-ttu-id="63212-216">バージョン `2.2.301` より下のすべての .NET Core SDK を削除するドライ ラン。</span><span class="sxs-lookup"><span data-stu-id="63212-216">Dry run of removing all .NET Core SDKs below the version `2.2.301`:</span></span>

  ```console
  dotnet-core-uninstall whatif --all-below 2.2.301 --sdk
  ```

### <a name="step-3---uninstall-net-core-sdks-and-runtimes"></a><span data-ttu-id="63212-217">手順 3 - .NET Core SDK とランタイムをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="63212-217">Step 3 - Uninstall .NET Core SDKs and Runtimes</span></span>

<span data-ttu-id="63212-218">`dotnet-core-uninstall remove` は、一連のオプションによって指定された .NET Core SDK とランタイムをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="63212-218">`dotnet-core-uninstall remove` uninstalls .NET Core SDKs and Runtimes that are specified by a collection of options.</span></span> <span data-ttu-id="63212-219">このツールを使用して、バージョン 5.0 以上の SDK とランタイムをアンインストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="63212-219">The tool can't be used to uninstall SDKs and Runtimes with version 5.0 or above.</span></span>

<span data-ttu-id="63212-220">このツールには破壊的動作があるため、remove コマンドを実行する前に、ドライ ランを実行することを**強く**お勧めします。</span><span class="sxs-lookup"><span data-stu-id="63212-220">Since this tool has a destructive behavior, it's **highly** recommended that you do a dry run before running the remove command.</span></span> <span data-ttu-id="63212-221">ドライランにより、`remove` コマンドを使用したときに削除される .NET Core SDK とランタイムが示されます。</span><span class="sxs-lookup"><span data-stu-id="63212-221">The dry run will show you what .NET Core SDKs and runtimes will be removed when you use the `remove` command.</span></span> <span data-ttu-id="63212-222">削除しても安全な SDK とランタイムを確認するには、「[バージョンを削除する必要はあるか](../versions/remove-runtime-sdk-versions.md#should-i-remove-a-version)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63212-222">Refer to [Should I remove a version?](../versions/remove-runtime-sdk-versions.md#should-i-remove-a-version) to learn which SDKs and runtimes are safe to remove.</span></span>

> [!CAUTION]
> <span data-ttu-id="63212-223">次の注意事項に留意してください。</span><span class="sxs-lookup"><span data-stu-id="63212-223">Keep in mind the following caveats:</span></span>
>
>- <span data-ttu-id="63212-224">このツールは、コンピューター上の `global.json` ファイルに必要な .NET Core SDK のバージョンをアンインストールできます。</span><span class="sxs-lookup"><span data-stu-id="63212-224">This tool can uninstall versions of the .NET Core SDK that are required by `global.json` files on your machine.</span></span> <span data-ttu-id="63212-225">.NET Core SDK は、「[.NET Core のダウンロード](https://dotnet.microsoft.com/download/dotnet-core)」ページから再インストールできます。</span><span class="sxs-lookup"><span data-stu-id="63212-225">You can reinstall .NET Core SDKs from the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>
>- <span data-ttu-id="63212-226">このツールは、コンピューター上のフレームワークに依存するアプリケーションに必要な .NET Core ランタイムのバージョンをアンインストールできます。</span><span class="sxs-lookup"><span data-stu-id="63212-226">This tool can uninstall versions of the .NET Core runtime that are required by framework dependent applications on your machine.</span></span> <span data-ttu-id="63212-227">.NET Core ランタイムは、「[.NET Core のダウンロード](https://dotnet.microsoft.com/download/dotnet-core)」ページから再インストールできます。</span><span class="sxs-lookup"><span data-stu-id="63212-227">You can reinstall .NET Core runtimes from the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>
>- <span data-ttu-id="63212-228">このツールは、Visual Studio が依存する .NET Core SDK とランタイムのバージョンをアンインストールできます。</span><span class="sxs-lookup"><span data-stu-id="63212-228">This tool can uninstall versions of the .NET Core SDK and runtime that Visual Studio relies on.</span></span> <span data-ttu-id="63212-229">Visual Studio のインストールを中断した場合は、Visual Studio インストーラーで [修復] を実行すると稼働状態に戻ります。</span><span class="sxs-lookup"><span data-stu-id="63212-229">If you break your Visual Studio installation, run "Repair" in the Visual Studio installer to get back to a working state.</span></span>

<span data-ttu-id="63212-230">既定で、すべてのコマンドは、Visual Studio またはその他の SDK に必要な可能性がある .NET Core SDK とランタイムを保持します。</span><span class="sxs-lookup"><span data-stu-id="63212-230">By default, all commands keep the .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs.</span></span> <span data-ttu-id="63212-231">これらの SDK とランタイムは、引数として明示的に指定するか、`--force` オプションを使用することによってアンインストールできます。</span><span class="sxs-lookup"><span data-stu-id="63212-231">These SDKs and runtimes can be uninstalled by listing them explicitly as arguments or by using the `--force` option.</span></span>

<span data-ttu-id="63212-232">このツールでは、.NET Core SDK とランタイムをアンインストールするために昇格が必要です。</span><span class="sxs-lookup"><span data-stu-id="63212-232">The tool requires elevation to uninstall .NET Core SDKs and runtimes.</span></span> <span data-ttu-id="63212-233">Windows では管理者コマンド プロンプトで、macOS では `sudo` を使用してツールを実行してください。</span><span class="sxs-lookup"><span data-stu-id="63212-233">Run the tool in an Administrator command prompt on Windows and with `sudo` on macOS.</span></span> <span data-ttu-id="63212-234">`dry-run` および `whatif` コマンドには、昇格は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="63212-234">The `dry-run` and `whatif` commands don't require elevation.</span></span>

<span data-ttu-id="63212-235">**dotnet-core-uninstall remove**</span><span class="sxs-lookup"><span data-stu-id="63212-235">**dotnet-core-uninstall remove**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="63212-236">構文</span><span class="sxs-lookup"><span data-stu-id="63212-236">Synopsis</span></span>

```console
dotnet-core-uninstall remove [options] [<VERSION>...]
```

#### <a name="arguments"></a><span data-ttu-id="63212-237">引数</span><span class="sxs-lookup"><span data-stu-id="63212-237">Arguments</span></span>

* **`VERSION`**

  <span data-ttu-id="63212-238">アンインストールする指定されたバージョン。</span><span class="sxs-lookup"><span data-stu-id="63212-238">The specified version to uninstall.</span></span> <span data-ttu-id="63212-239">スペースで区切って、複数のバージョンを順々に指定できます。</span><span class="sxs-lookup"><span data-stu-id="63212-239">You may list several versions one after the other, separated by spaces.</span></span> <span data-ttu-id="63212-240">応答ファイルもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="63212-240">Response files are also supported.</span></span>

  > [!TIP]
  > <span data-ttu-id="63212-241">すべてのバージョンをコマンド ラインに指定する代わりに応答ファイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="63212-241">Response files are an alternative to placing all the versions on the command line.</span></span>
  > <span data-ttu-id="63212-242">それらはテキスト ファイルで、通常、\*.rsp 拡張子が付いています。各バージョンは別々の行に指定されます。</span><span class="sxs-lookup"><span data-stu-id="63212-242">They're text files, typically with a \*.rsp extension, and each version is listed on a separate line.</span></span>
  > <span data-ttu-id="63212-243">`VERSION` 引数の応答ファイルを指定するには、\@ 文字を使用し、そのすぐ後に応答ファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="63212-243">To specify a response file for the `VERSION` argument, use the \@ character immediately followed by the response file name.</span></span>

#### <a name="options"></a><span data-ttu-id="63212-244">オプション</span><span class="sxs-lookup"><span data-stu-id="63212-244">Options</span></span>

## <a name="windows"></a>[<span data-ttu-id="63212-245">Windows</span><span class="sxs-lookup"><span data-stu-id="63212-245">Windows</span></span>](#tab/windows)

* **`--all`**

  <span data-ttu-id="63212-246">すべての .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-246">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="63212-247">指定したバージョンよりも小さいバージョンの .NET Core SDK とランタイムのみを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-247">Removes only the .NET Core SDKs and runtimes with a version smaller than the specified version.</span></span> <span data-ttu-id="63212-248">指定したバージョンはインストールされたままになります。</span><span class="sxs-lookup"><span data-stu-id="63212-248">The specified version remains installed.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="63212-249">指定したバージョンを除く、すべての .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-249">Removes all .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="63212-250">最上位の 1 つのバージョンを除く、すべての .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-250">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="63212-251">上位の修正プログラムによって置き換えられた .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-251">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="63212-252">このオプションは、global. json を保護します。</span><span class="sxs-lookup"><span data-stu-id="63212-252">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="63212-253">プレビューとしてマークされている .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-253">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="63212-254">最上位の 1 つのプレビューを除き、プレビューとしてマークされているすべての .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-254">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--aspnet-runtime`**

  <span data-ttu-id="63212-255">ASP.NET Core ランタイムのみを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-255">Removes ASP.NET Core runtimes only.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="63212-256">.NET Core ランタイムとホスティングのバンドルのみを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-256">Removes .NET Core runtime and hosting bundles only.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="63212-257">指定した `major.minor` バージョンに一致する .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-257">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="63212-258">.NET Core ランタイムのみを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-258">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="63212-259">.NET Core SDK のみを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-259">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="63212-260">詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="63212-260">Sets the verbosity level.</span></span> <span data-ttu-id="63212-261">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="63212-261">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="63212-262">既定値は `normal` です。</span><span class="sxs-lookup"><span data-stu-id="63212-262">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="63212-263">x64 SDK またはランタイムを削除するには、`--sdk`、`--runtime`、および `--aspnet-runtime` と共に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63212-263">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x64 SDKs or runtimes.</span></span>

* **`--x86`**

  <span data-ttu-id="63212-264">x86 SDK またはランタイムを削除するには、`--sdk`、`--runtime`、および `--aspnet-runtime` と共に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63212-264">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x86 SDKs or runtimes.</span></span>

* <span data-ttu-id="63212-265">**`-y, --yes`** Yes または No の確認を要求せずにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="63212-265">**`-y, --yes`** Executes the command without requiring a yes or no confirmation.</span></span>

* <span data-ttu-id="63212-266">**`--force`** Visual Studio によって使用される可能性があるバージョンを強制的に削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-266">**`--force`** Forces removal of versions that might be used by Visual Studio.</span></span>

<span data-ttu-id="63212-267">メモ:</span><span class="sxs-lookup"><span data-stu-id="63212-267">Notes:</span></span>

1. <span data-ttu-id="63212-268">`--sdk`、`--runtime`、`--aspnet-runtime`、および `--hosting-bundle` の 1 つだけが必要です。</span><span class="sxs-lookup"><span data-stu-id="63212-268">Exactly one of `--sdk`, `--runtime`, `--aspnet-runtime`, and `--hosting-bundle` is required.</span></span>
2. <span data-ttu-id="63212-269">`--all`、`--all-below`、`--all-but`、`--all-but-latest`、`--all-lower-patches`、`--all-previews`、`--all-previews-but-latest`、`--major-minor`、および `[<VERSION>...]` は排他的です。</span><span class="sxs-lookup"><span data-stu-id="63212-269">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>
3. <span data-ttu-id="63212-270">`--x64` または `--x86` が指定されていない場合は、x64 と x86 の両方が削除されます。</span><span class="sxs-lookup"><span data-stu-id="63212-270">If `--x64` or `--x86` aren't specified, then both x64 and x86 will be removed.</span></span>

## <a name="macos"></a>[<span data-ttu-id="63212-271">macOS</span><span class="sxs-lookup"><span data-stu-id="63212-271">macOS</span></span>](#tab/macos)

* **`--all`**

  <span data-ttu-id="63212-272">すべての .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-272">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="63212-273">指定したバージョンより下の .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-273">Removes .NET Core SDKs and runtimes below the specified version.</span></span> <span data-ttu-id="63212-274">指定したバージョンはそのまま残ります。</span><span class="sxs-lookup"><span data-stu-id="63212-274">The specified version will remain.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="63212-275">指定したバージョンを除き、.NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-275">Removes .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="63212-276">最上位の 1 つのバージョンを除く、すべての .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-276">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="63212-277">上位の修正プログラムによって置き換えられた .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-277">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="63212-278">このオプションは、global. json を保護します。</span><span class="sxs-lookup"><span data-stu-id="63212-278">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="63212-279">プレビューとしてマークされている .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-279">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="63212-280">最上位の 1 つのプレビューを除き、プレビューとしてマークされているすべての .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-280">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="63212-281">指定した `major.minor` バージョンに一致する .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-281">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="63212-282">.NET Core ランタイムのみを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-282">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="63212-283">.NET Core SDK のみを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-283">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="63212-284">詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="63212-284">Sets the verbosity level.</span></span> <span data-ttu-id="63212-285">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="63212-285">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="63212-286">既定値は `normal` です。</span><span class="sxs-lookup"><span data-stu-id="63212-286">The default value is `normal`.</span></span>

* <span data-ttu-id="63212-287">**`-y, --yes`** Y/N の確認を要求せずにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="63212-287">**`-y, --yes`** Executes the command without requiring Y/N confirmation.</span></span>
  
* <span data-ttu-id="63212-288">**`--force`** Visual Studio または SDK によって使用される可能性があるバージョンを強制的に削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-288">**`--force`** Forces removal of versions that might be used by Visual Studio or SDKs.</span></span>

<span data-ttu-id="63212-289">メモ:</span><span class="sxs-lookup"><span data-stu-id="63212-289">Notes:</span></span>

1. <span data-ttu-id="63212-290">`--sdk` と `--runtime` のうち 1 つだけが必要です。</span><span class="sxs-lookup"><span data-stu-id="63212-290">Exactly one of `--sdk` and `--runtime` is required.</span></span>
2. <span data-ttu-id="63212-291">`--all`、`--all-below`、`--all-but`、`--all-but-latest`、`--all-lower-patches`、`--all-previews`、`--all-previews-but-latest`、`--major-minor`、および `[<VERSION>...]` は排他的です。</span><span class="sxs-lookup"><span data-stu-id="63212-291">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>

---

#### <a name="examples"></a><span data-ttu-id="63212-292">使用例</span><span class="sxs-lookup"><span data-stu-id="63212-292">Examples</span></span>

> [!NOTE]
> <span data-ttu-id="63212-293">既定で、Visual Studio またはその他の SDK に必要な可能性がある .NET Core SDK とランタイムは保持されます。</span><span class="sxs-lookup"><span data-stu-id="63212-293">By default, .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs are kept.</span></span> <span data-ttu-id="63212-294">次の例では、コンピューターの状態によっては、指定された SDK とランタイムの一部が保持される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="63212-294">In the following examples, some of the specified SDKs and runtimes may remain, depending on the state of the machine.</span></span> <span data-ttu-id="63212-295">すべての SDK とランタイムを削除するには、それらを引数として明示的に指定するか、`--force` オプションを使用してください。</span><span class="sxs-lookup"><span data-stu-id="63212-295">To remove all SDKs and runtimes, list them explicitly as arguments or use the `--force` option.</span></span>

* <span data-ttu-id="63212-296">Y/N の確認を要求せずに、バージョン `3.0.0-preview6-27804-01` を除くすべての .NET Core ランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-296">Remove all .NET Core runtimes except the version `3.0.0-preview6-27804-01` without requiring Y/N confirmation:</span></span>

  ```console
  dotnet-core-uninstall remove --all-but 3.0.0-preview6-27804-01 --runtime --yes
  ```

* <span data-ttu-id="63212-297">Y/N の確認を要求せずに、すべての .NET Core 1.1 SDK を削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-297">Remove all .NET Core 1.1 SDKs without requiring Y/n confirmation:</span></span>

  ```console
  dotnet-core-uninstall remove --sdk --major-minor 1.1 -y
  ```

* <span data-ttu-id="63212-298">コンソールに出力せずに、.NET Core 1.1.11 SDK を削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-298">Remove the .NET Core 1.1.11 SDK with no console output:</span></span>

  ```console
  dotnet-core-uninstall remove 1.1.11 --sdk --yes --verbosity q
  ```

* <span data-ttu-id="63212-299">このツールで安全に削除できるすべての .NET Core SDK を削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-299">Remove all .NET Core SDKs that can safely be removed by this tool:</span></span>

  ```console
  dotnet-core-uninstall remove --all --sdk
  ```

* <span data-ttu-id="63212-300">Visual Studio で必要な可能性がある SDK を含め、このツールで削除できるすべての .NET Core SDK を削除します (推奨されません)。</span><span class="sxs-lookup"><span data-stu-id="63212-300">Remove all .NET Core SDKs that can be removed by this tool, including those SDKs that may be required by Visual Studio (not recommended):</span></span>

  ```console
  dotnet-core-uninstall remove --all --sdk --force
  ```

* <span data-ttu-id="63212-301">応答ファイル `versions.rsp` に指定されたすべての .NET Core SDK を削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-301">Remove all .NET Core SDKs that are specified in the response file `versions.rsp`</span></span>

  ```console
  dotnet-core-uninstall remove --sdk @versions.rsp
  ```

  <span data-ttu-id="63212-302">*versions.rsp* の内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="63212-302">The content of *versions.rsp* is as follows:</span></span>
  
  ```text
  2.2.300
  2.1.700
  ```

### <a name="step-4---delete-the-nuget-fallback-folder-optional"></a><span data-ttu-id="63212-303">手順 4 - NuGet フォールバック フォルダーを削除する (省略可能)</span><span class="sxs-lookup"><span data-stu-id="63212-303">Step 4 - Delete the NuGet fallback folder (optional)</span></span>

<span data-ttu-id="63212-304">場合によっては、`NuGetFallbackFolder` が不要になり、削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="63212-304">In some cases, you no longer need the `NuGetFallbackFolder` and may wish to delete it.</span></span> <span data-ttu-id="63212-305">このフォルダーの削除の詳細については、[NuGetFallbackFolder の削除](../versions/remove-runtime-sdk-versions.md#remove-the-nuget-fallback-folder)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63212-305">For more information about deleting this folder, see [Remove the NuGetFallbackFolder](../versions/remove-runtime-sdk-versions.md#remove-the-nuget-fallback-folder).</span></span>

## <a name="uninstall-the-tool"></a><span data-ttu-id="63212-306">ツールをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="63212-306">Uninstall the tool</span></span>

## <a name="windows"></a>[<span data-ttu-id="63212-307">Windows</span><span class="sxs-lookup"><span data-stu-id="63212-307">Windows</span></span>](#tab/windows)

1. <span data-ttu-id="63212-308">**[プログラムの追加と削除]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="63212-308">Open **Add or Remove Programs**.</span></span>
2. <span data-ttu-id="63212-309">`Microsoft .NET Core SDK Uninstall Tool` を検索します。</span><span class="sxs-lookup"><span data-stu-id="63212-309">Search for `Microsoft .NET Core SDK Uninstall Tool`.</span></span>
3. <span data-ttu-id="63212-310">**[アンインストール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="63212-310">Select **Uninstall**.</span></span>

## <a name="macos"></a>[<span data-ttu-id="63212-311">macOS</span><span class="sxs-lookup"><span data-stu-id="63212-311">macOS</span></span>](#tab/macos)

<span data-ttu-id="63212-312">ダウンロードした *dotnet-core-uninstall.tar.gz* ファイルをインストールしたディレクトリから削除します。</span><span class="sxs-lookup"><span data-stu-id="63212-312">Delete the downloaded *dotnet-core-uninstall.tar.gz* file from the directory where it was installed.</span></span> <span data-ttu-id="63212-313">このファイルの内容を別のディレクトリに解凍した場合は、必ずその内容も削除してください。</span><span class="sxs-lookup"><span data-stu-id="63212-313">If you unzipped the contents of this file into another directory, be sure to delete that content as well.</span></span>

---
