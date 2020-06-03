---
title: アンインストール ツール
description: .NET CORE アンインストール ツールの概要です。これは、.NET Core SKD とランタイムの制御されたクリーンアップを可能にするガイド付きツールです。
author: sfoslund
ms.date: 05/27/2020
ms.openlocfilehash: 1ad31cd42d8f8f87e3501b422fc4298c643e2067
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144514"
---
# <a name="net-core-uninstall-tool"></a><span data-ttu-id="7b1da-103">.NET Core アンインストール ツール</span><span class="sxs-lookup"><span data-stu-id="7b1da-103">.NET Core Uninstall Tool</span></span>

<span data-ttu-id="7b1da-104">[.NET Core アンインストール ツール](https://aka.ms/dotnet-core-uninstall-tool) (`dotnet-core-uninstall`) を使用すると、.NET Core SDK とランタイムをシステムから削除できます。</span><span class="sxs-lookup"><span data-stu-id="7b1da-104">The [.NET Core Uninstall Tool](https://aka.ms/dotnet-core-uninstall-tool) (`dotnet-core-uninstall`) lets you remove .NET Core SDKs and Runtimes from a system.</span></span> <span data-ttu-id="7b1da-105">一連のオプションを使用して、アンインストールするバージョンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="7b1da-105">A collection of options is available to specify which versions you want to uninstall.</span></span>

<span data-ttu-id="7b1da-106">このツールでは、Windows と macOS がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7b1da-106">The tool supports Windows and macOS.</span></span> <span data-ttu-id="7b1da-107">Linux は現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7b1da-107">Linux is currently not supported.</span></span>

<span data-ttu-id="7b1da-108">Windows では、ツールは次のいずれかのインストーラーを使用してインストールされた SDK とランタイムのみをアンインストールできます。</span><span class="sxs-lookup"><span data-stu-id="7b1da-108">On Windows, the tool can only uninstall SDKs and Runtimes that were installed using one of the following installers:</span></span>

- <span data-ttu-id="7b1da-109">.NET Core SDK およびランタイム インストーラー。</span><span class="sxs-lookup"><span data-stu-id="7b1da-109">The .NET Core SDK and runtime installer.</span></span>
- <span data-ttu-id="7b1da-110">Visual Studio 2019 バージョン 16.3 より前のバージョンの Visual Studio インストーラー。</span><span class="sxs-lookup"><span data-stu-id="7b1da-110">The Visual Studio installer in versions earlier than Visual Studio 2019 version 16.3.</span></span>

<span data-ttu-id="7b1da-111">macOS では、このツールでアンインストールできるのは */usr/local/share/dotnet* フォルダーにある SDK とランタイムのみです。</span><span class="sxs-lookup"><span data-stu-id="7b1da-111">On macOS, the tool can only uninstall SDKs and runtimes located in the */usr/local/share/dotnet* folder.</span></span>

<span data-ttu-id="7b1da-112">これらの制限のため、このツールでは、コンピューター上の一部の .NET Core SDK とランタイムをアンインストールできない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7b1da-112">Because of these limitations, the tool may not be able to uninstall all of the .NET Core SDKs and runtimes on your machine.</span></span> <span data-ttu-id="7b1da-113">`dotnet --info` コマンドを使用して、インストールされているすべての .NET Core SDK とランタイム (このツールで削除できない SDK やランタイムを含む) を検出できます。</span><span class="sxs-lookup"><span data-stu-id="7b1da-113">You can use the `dotnet --info` command to find all of the .NET Core SDKs and runtimes installed, including those SDKs and runtimes that this tool can't remove.</span></span> <span data-ttu-id="7b1da-114">`dotnet-core-uninstall list` コマンドを実行すると、このツールでアンインストールできる SDK が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7b1da-114">The `dotnet-core-uninstall list` command displays which SDKs can be uninstalled with the tool.</span></span>

## <a name="install-the-tool"></a><span data-ttu-id="7b1da-115">ツールをインストールする</span><span class="sxs-lookup"><span data-stu-id="7b1da-115">Install the tool</span></span>

<span data-ttu-id="7b1da-116">.NET Core アンインストール ツールは、[ここ](https://aka.ms/dotnet-core-uninstall-tool)からダウンロードできます。また、ソース コードは、[dotnet/cli-lab](https://github.com/dotnet/cli-lab) GitHub リポジトリにあります。</span><span class="sxs-lookup"><span data-stu-id="7b1da-116">You can download the .NET Core Uninstall Tool from [here](https://aka.ms/dotnet-core-uninstall-tool) and find the source code at the [dotnet/cli-lab](https://github.com/dotnet/cli-lab) GitHub repository.</span></span>

> [!NOTE]
> <span data-ttu-id="7b1da-117">このツールでは、.NET Core SDK とランタイムをアンインストールするために昇格が必要です。</span><span class="sxs-lookup"><span data-stu-id="7b1da-117">The tool requires elevation to uninstall .NET Core SDKs and runtimes.</span></span> <span data-ttu-id="7b1da-118">そのため、Windows では *C:\Program Files*、macOS では */usr/local/bin* などの書き込み保護されたディレクトリにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b1da-118">Therefore, it should be installed in a write-protected directory such as *C:\Program Files* on Windows or */usr/local/bin* on macOS.</span></span> <span data-ttu-id="7b1da-119">「[dotnet コマンドの特権アクセス](../tools/elevated-access.md)」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b1da-119">See also [Elevated access for dotnet commands](../tools/elevated-access.md).</span></span> <span data-ttu-id="7b1da-120">詳細については、[詳細なインストール手順](https://aka.ms/dotnet-core-uninstall-tool)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b1da-120">For more information, see the [detailed installation instructions](https://aka.ms/dotnet-core-uninstall-tool).</span></span>

## <a name="run-the-tool"></a><span data-ttu-id="7b1da-121">ツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-121">Run the tool</span></span>

<span data-ttu-id="7b1da-122">次の手順は、アンインストール ツールを実行するための推奨方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="7b1da-122">The following steps show the recommended approach for running the uninstall tool:</span></span>

- [<span data-ttu-id="7b1da-123">手順 1 - インストールされている .NET Core SDK とランタイムを表示する</span><span class="sxs-lookup"><span data-stu-id="7b1da-123">Step 1 - Display installed .NET Core SDKs and runtimes</span></span>](#step-1---display-installed-net-core-sdks-and-runtimes)
- [<span data-ttu-id="7b1da-124">手順 2 - ドライ ランを実行する</span><span class="sxs-lookup"><span data-stu-id="7b1da-124">Step 2 - Do a dry run</span></span>](#step-2---do-a-dry-run)
- [<span data-ttu-id="7b1da-125">手順 3 - .NET Core SDK とランタイムをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="7b1da-125">Step 3 - Uninstall .NET Core SDKs and Runtimes</span></span>](#step-3---uninstall-net-core-sdks-and-runtimes)
- [<span data-ttu-id="7b1da-126">手順 4 - NuGet フォールバック フォルダーを削除する (省略可能)</span><span class="sxs-lookup"><span data-stu-id="7b1da-126">Step 4 - Delete the NuGet fallback folder (optional)</span></span>](#step-4---delete-the-nuget-fallback-folder-optional)

### <a name="step-1---display-installed-net-core-sdks-and-runtimes"></a><span data-ttu-id="7b1da-127">手順 1 - インストールされている .NET Core SDK とランタイムを表示する</span><span class="sxs-lookup"><span data-stu-id="7b1da-127">Step 1 - Display installed .NET Core SDKs and runtimes</span></span>

<span data-ttu-id="7b1da-128">`dotnet-core-uninstall list` コマンドを実行すると、このツールで削除できる、インストールされている .NET Core SDK とランタイムが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="7b1da-128">The `dotnet-core-uninstall list` command lists the installed .NET Core SDKs and runtimes that can be removed with this tool.</span></span> <span data-ttu-id="7b1da-129">一部の SDK とランタイムは、Visual Studio で必要な場合があり、それらのアンインストールが推奨されない理由を示す注釈と共に表示されます。</span><span class="sxs-lookup"><span data-stu-id="7b1da-129">Some SDKs and runtimes may be required by Visual Studio and they're displayed with a note of why it isn't recommended to uninstall them.</span></span>

> [!NOTE]
> <span data-ttu-id="7b1da-130">`dotnet-core-uninstall list` コマンドの出力は、ほとんどの場合、`dotnet --info` で出力されるインストールされているバージョンの一覧と一致しません。</span><span class="sxs-lookup"><span data-stu-id="7b1da-130">The output of the `dotnet-core-uninstall list` command will not match the list of installed versions in the output of `dotnet --info` in most cases.</span></span> <span data-ttu-id="7b1da-131">具体的には、このツールでは、zip ファイルによってインストールされたバージョンや、Visual Studio によって管理されているバージョン (Visual Studio 2019 16.3 以降を使用してインストールされたバージョン) は表示されません。</span><span class="sxs-lookup"><span data-stu-id="7b1da-131">Specifically, this tool will not display versions installed by zip files or managed by Visual Studio (any version installed with Visual Studio 2019 16.3 or later).</span></span> <span data-ttu-id="7b1da-132">バージョンが Visual Studio によって管理されているかどうかを確認する方法の 1 つは、これを `Add or Remove Programs` で表示することです。そこでは、Visual Studio によって管理されているバージョンの表示名にそれを示すマークが付きます。</span><span class="sxs-lookup"><span data-stu-id="7b1da-132">One way to check if a version is managed by Visual Studio is to view it in `Add or Remove Programs`, where Visual Studio managed versions are marked as such in their display names.</span></span>

<span data-ttu-id="7b1da-133">**dotnet-core-uninstall list**</span><span class="sxs-lookup"><span data-stu-id="7b1da-133">**dotnet-core-uninstall list**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="7b1da-134">構文</span><span class="sxs-lookup"><span data-stu-id="7b1da-134">Synopsis</span></span>

```console
dotnet-core-uninstall list [options]
```

#### <a name="options"></a><span data-ttu-id="7b1da-135">オプション</span><span class="sxs-lookup"><span data-stu-id="7b1da-135">Options</span></span>

## <a name="windows"></a>[<span data-ttu-id="7b1da-136">Windows</span><span class="sxs-lookup"><span data-stu-id="7b1da-136">Windows</span></span>](#tab/windows)

* **`--aspnet-runtime`**

  <span data-ttu-id="7b1da-137">このツールでアンインストールできるすべての ASP.NET Core ランタイムを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-137">Lists all the ASP.NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="7b1da-138">このツールでアンインストールできるすべての .NET Core ホスティング バンドルを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-138">Lists all the .NET Core hosting bundles that can be uninstalled with this tool.</span></span>

* **`--runtime`**

  <span data-ttu-id="7b1da-139">このツールでアンインストールできるすべての .NET Core ランタイムを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-139">Lists all .NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--sdk`**

  <span data-ttu-id="7b1da-140">このツールでアンインストールできるすべての .NET Core SDK を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-140">Lists all .NET Core SDKs that can be uninstalled with this tool.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="7b1da-141">詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-141">Sets the verbosity level.</span></span> <span data-ttu-id="7b1da-142">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="7b1da-142">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="7b1da-143">既定値は `normal` です。</span><span class="sxs-lookup"><span data-stu-id="7b1da-143">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="7b1da-144">このツールでアンインストールできるすべての x64 .NET Core SDK とランタイムを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-144">Lists all x64 .NET Core SDKs and runtimes that can be uninstalled with this tool.</span></span>

* **`--x86`**

  <span data-ttu-id="7b1da-145">このツールでアンインストールできるすべての x86 .NET Core SDK とランタイムを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-145">Lists all x86 .NET Core SDKs and runtimes that can be uninstalled with this tool.</span></span>

## <a name="macos"></a>[<span data-ttu-id="7b1da-146">macOS</span><span class="sxs-lookup"><span data-stu-id="7b1da-146">macOS</span></span>](#tab/macos)

* **`--runtime`**

  <span data-ttu-id="7b1da-147">このツールでアンインストールできるすべての .NET Core ランタイムを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-147">Lists all .NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--sdk`**

  <span data-ttu-id="7b1da-148">このツールでアンインストールできるすべての .NET Core SDK を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-148">Lists all .NET Core SDKs that can be uninstalled with this tool.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="7b1da-149">詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-149">Sets the verbosity level.</span></span> <span data-ttu-id="7b1da-150">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="7b1da-150">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="7b1da-151">既定値は `normal` です。</span><span class="sxs-lookup"><span data-stu-id="7b1da-151">The default value is `normal`.</span></span>
  
---

#### <a name="examples"></a><span data-ttu-id="7b1da-152">使用例</span><span class="sxs-lookup"><span data-stu-id="7b1da-152">Examples</span></span>

* <span data-ttu-id="7b1da-153">このツールで削除できるすべての .NET Core SDK とランタイムを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-153">List all .NET Core SDKs and runtimes that can be removed with this tool:</span></span>

  ```console
  dotnet-core-uninstall list
  ```

* <span data-ttu-id="7b1da-154">すべての x64 .NET Core SDK とランタイムを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-154">List all x64 .NET Core SDKs and runtimes:</span></span>

  ```console
  dotnet-core-uninstall list --x64
  ```

* <span data-ttu-id="7b1da-155">すべての x86 .NET Core SDK を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-155">List all x86 .NET Core SDKs:</span></span>

  ```console
  dotnet-core-uninstall list --sdk --x86
  ```

### <a name="step-2---do-a-dry-run"></a><span data-ttu-id="7b1da-156">手順 2 - ドライ ランを実行する</span><span class="sxs-lookup"><span data-stu-id="7b1da-156">Step 2 - Do a dry run</span></span>

<span data-ttu-id="7b1da-157">`dotnet-core-uninstall dry-run` および `dotnet-core-uninstall whatif` コマンドは、アンインストールを実行せずに指定されたオプションに基づいて削除される .NET Core SDK とランタイムを表示します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-157">The `dotnet-core-uninstall dry-run` and `dotnet-core-uninstall whatif` commands display the .NET Core SDKs and runtimes that will be removed based on the options provided without performing the uninstall.</span></span> <span data-ttu-id="7b1da-158">これらのコマンドはシノニムです。</span><span class="sxs-lookup"><span data-stu-id="7b1da-158">These commands are synonyms.</span></span>

<span data-ttu-id="7b1da-159">**dotnet-core-uninstall dry-run and dotnet-core-uninstall whatif**</span><span class="sxs-lookup"><span data-stu-id="7b1da-159">**dotnet-core-uninstall dry-run and dotnet-core-uninstall whatif**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="7b1da-160">構文</span><span class="sxs-lookup"><span data-stu-id="7b1da-160">Synopsis</span></span>

```console
dotnet-core-uninstall dry-run [options] [<VERSION>...]

dotnet-core-uninstall whatif [options] [<VERSION>...]
```

#### <a name="arguments"></a><span data-ttu-id="7b1da-161">引数</span><span class="sxs-lookup"><span data-stu-id="7b1da-161">Arguments</span></span>

* **`VERSION`**

  <span data-ttu-id="7b1da-162">アンインストールする指定されたバージョン。</span><span class="sxs-lookup"><span data-stu-id="7b1da-162">The specified version to uninstall.</span></span> <span data-ttu-id="7b1da-163">スペースで区切って、複数のバージョンを順々に指定できます。</span><span class="sxs-lookup"><span data-stu-id="7b1da-163">You may list several versions one after the other, separated by spaces.</span></span> <span data-ttu-id="7b1da-164">応答ファイルもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7b1da-164">Response files are also supported.</span></span>

  > [!TIP]
  > <span data-ttu-id="7b1da-165">すべてのバージョンをコマンド ラインに指定する代わりに応答ファイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7b1da-165">Response files are an alternative to placing all the versions on the command line.</span></span>
  > <span data-ttu-id="7b1da-166">それらはテキスト ファイルで、通常、\*.rsp 拡張子が付いています。各バージョンは別々の行に指定されます。</span><span class="sxs-lookup"><span data-stu-id="7b1da-166">They're text files, typically with a \*.rsp extension, and each version is listed on a separate line.</span></span>
  > <span data-ttu-id="7b1da-167">`VERSION` 引数の応答ファイルを指定するには、\@ 文字を使用し、そのすぐ後に応答ファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-167">To specify a response file for the `VERSION` argument, use the \@ character immediately followed by the response file name.</span></span>

#### <a name="options"></a><span data-ttu-id="7b1da-168">オプション</span><span class="sxs-lookup"><span data-stu-id="7b1da-168">Options</span></span>

## <a name="windows"></a>[<span data-ttu-id="7b1da-169">Windows</span><span class="sxs-lookup"><span data-stu-id="7b1da-169">Windows</span></span>](#tab/windows)

* **`--all`**

  <span data-ttu-id="7b1da-170">すべての .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-170">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="7b1da-171">指定したバージョンよりも小さいバージョンの .NET Core SDK とランタイムのみを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-171">Removes only the .NET Core SDKs and runtimes with a version smaller than the specified version.</span></span> <span data-ttu-id="7b1da-172">指定したバージョンはインストールされたままになります。</span><span class="sxs-lookup"><span data-stu-id="7b1da-172">The specified version remains installed.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="7b1da-173">指定したバージョンを除く、すべての .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-173">Removes all .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="7b1da-174">最上位の 1 つのバージョンを除く、すべての .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-174">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="7b1da-175">上位の修正プログラムによって置き換えられた .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-175">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="7b1da-176">このオプションは、global. json を保護します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-176">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="7b1da-177">プレビューとしてマークされている .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-177">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="7b1da-178">最上位の 1 つのプレビューを除き、プレビューとしてマークされているすべての .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-178">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--aspnet-runtime`**

  <span data-ttu-id="7b1da-179">ASP.NET Core ランタイムのみを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-179">Removes ASP.NET Core runtimes only.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="7b1da-180">.NET Core ランタイムとホスティングのバンドルのみを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-180">Removes .NET Core runtime and hosting bundles only.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="7b1da-181">指定した `major.minor` バージョンに一致する .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-181">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="7b1da-182">.NET Core ランタイムのみを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-182">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="7b1da-183">.NET Core SDK のみを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-183">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="7b1da-184">詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-184">Sets the verbosity level.</span></span> <span data-ttu-id="7b1da-185">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="7b1da-185">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="7b1da-186">既定値は `normal` です。</span><span class="sxs-lookup"><span data-stu-id="7b1da-186">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="7b1da-187">x64 SDK またはランタイムを削除するには、`--sdk`、`--runtime`、および `--aspnet-runtime` と共に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b1da-187">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x64 SDKs or runtimes.</span></span>

* **`--x86`**

  <span data-ttu-id="7b1da-188">x86 SDK またはランタイムを削除するには、`--sdk`、`--runtime`、および `--aspnet-runtime` と共に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b1da-188">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x86 SDKs or runtimes.</span></span>

* <span data-ttu-id="7b1da-189">**`--force`** Visual Studio によって使用される可能性があるバージョンを強制的に削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-189">**`--force`** Forces removal of versions that might be used by Visual Studio.</span></span>

<span data-ttu-id="7b1da-190">メモ:</span><span class="sxs-lookup"><span data-stu-id="7b1da-190">Notes:</span></span>

1. <span data-ttu-id="7b1da-191">`--sdk`、`--runtime`、`--aspnet-runtime`、および `--hosting-bundle` の 1 つだけが必要です。</span><span class="sxs-lookup"><span data-stu-id="7b1da-191">Exactly one of `--sdk`, `--runtime`, `--aspnet-runtime`, and `--hosting-bundle` is required.</span></span>
2. <span data-ttu-id="7b1da-192">`--all`、`--all-below`、`--all-but`、`--all-but-latest`、`--all-lower-patches`、`--all-previews`、`--all-previews-but-latest`、`--major-minor`、および `[<VERSION>...]` は排他的です。</span><span class="sxs-lookup"><span data-stu-id="7b1da-192">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>
3. <span data-ttu-id="7b1da-193">`--x64` または `--x86` が指定されていない場合は、x64 と x86 の両方が削除されます。</span><span class="sxs-lookup"><span data-stu-id="7b1da-193">If `--x64` or `--x86` aren't specified, then both x64 and x86 will be removed.</span></span>

## <a name="macos"></a>[<span data-ttu-id="7b1da-194">macOS</span><span class="sxs-lookup"><span data-stu-id="7b1da-194">macOS</span></span>](#tab/macos)

* **`--all`**

  <span data-ttu-id="7b1da-195">すべての .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-195">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="7b1da-196">指定したバージョンより下の .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-196">Removes .NET Core SDKs and runtimes below the specified version.</span></span> <span data-ttu-id="7b1da-197">指定したバージョンはそのまま残ります。</span><span class="sxs-lookup"><span data-stu-id="7b1da-197">The specified version will remain.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="7b1da-198">指定したバージョンを除き、.NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-198">Removes .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="7b1da-199">最上位の 1 つのバージョンを除く、すべての .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-199">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="7b1da-200">上位の修正プログラムによって置き換えられた .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-200">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="7b1da-201">このオプションは、global. json を保護します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-201">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="7b1da-202">プレビューとしてマークされている .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-202">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="7b1da-203">最上位の 1 つのプレビューを除き、プレビューとしてマークされているすべての .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-203">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="7b1da-204">指定した `major.minor` バージョンに一致する .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-204">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="7b1da-205">.NET Core ランタイムのみを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-205">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="7b1da-206">.NET Core SDK のみを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-206">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="7b1da-207">詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-207">Sets the verbosity level.</span></span> <span data-ttu-id="7b1da-208">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="7b1da-208">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="7b1da-209">既定値は `normal` です。</span><span class="sxs-lookup"><span data-stu-id="7b1da-209">The default value is `normal`.</span></span>
  
* <span data-ttu-id="7b1da-210">**`--force`** Visual Studio または SDK によって使用される可能性があるバージョンを強制的に削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-210">**`--force`** Forces removal of versions that might be used by Visual Studio or SDKs.</span></span>

<span data-ttu-id="7b1da-211">メモ:</span><span class="sxs-lookup"><span data-stu-id="7b1da-211">Notes:</span></span>

1. <span data-ttu-id="7b1da-212">`--sdk` と `--runtime` のうち 1 つだけが必要です。</span><span class="sxs-lookup"><span data-stu-id="7b1da-212">Exactly one of `--sdk` and `--runtime` is required.</span></span>
2. <span data-ttu-id="7b1da-213">`--all`、`--all-below`、`--all-but`、`--all-but-latest`、`--all-lower-patches`、`--all-previews`、`--all-previews-but-latest`、`--major-minor`、および `[<VERSION>...]` は排他的です。</span><span class="sxs-lookup"><span data-stu-id="7b1da-213">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>

---

#### <a name="examples"></a><span data-ttu-id="7b1da-214">使用例</span><span class="sxs-lookup"><span data-stu-id="7b1da-214">Examples</span></span>

> [!NOTE]
> <span data-ttu-id="7b1da-215">既定で、Visual Studio またはその他の SDK に必要な可能性がある .NET Core SDK とランタイムは `dotnet-core-uninstall dry-run` 出力には含まれません。</span><span class="sxs-lookup"><span data-stu-id="7b1da-215">By default, .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs are not included in `dotnet-core-uninstall dry-run` output.</span></span> <span data-ttu-id="7b1da-216">次の例では、コンピューターの状態によっては、指定された SDK とランタイムの一部が出力に含まれない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7b1da-216">In the following examples, some of the specified SDKs and runtimes may not be included in the output, depending on the state of the machine.</span></span> <span data-ttu-id="7b1da-217">すべての SDK とランタイムを含めるには、それらを引数として明示的に指定するか、`--force` オプションを使用してください。</span><span class="sxs-lookup"><span data-stu-id="7b1da-217">To include all SDKs and runtimes, list them explicitly as arguments or use the `--force` option.</span></span>

* <span data-ttu-id="7b1da-218">上位の修正プログラムによって置き換えられたすべての .NET Core ランタイムを削除するドライ ラン。</span><span class="sxs-lookup"><span data-stu-id="7b1da-218">Dry run of removing all .NET Core runtimes that have been superseded by higher patches:</span></span>

  ```console
  dotnet-core-uninstall dry-run --all-lower-patches --runtime
  ```

* <span data-ttu-id="7b1da-219">バージョン `2.2.301` より下のすべての .NET Core SDK を削除するドライ ラン。</span><span class="sxs-lookup"><span data-stu-id="7b1da-219">Dry run of removing all .NET Core SDKs below the version `2.2.301`:</span></span>

  ```console
  dotnet-core-uninstall whatif --all-below 2.2.301 --sdk
  ```

### <a name="step-3---uninstall-net-core-sdks-and-runtimes"></a><span data-ttu-id="7b1da-220">手順 3 - .NET Core SDK とランタイムをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="7b1da-220">Step 3 - Uninstall .NET Core SDKs and Runtimes</span></span>

<span data-ttu-id="7b1da-221">`dotnet-core-uninstall remove` は、一連のオプションによって指定された .NET Core SDK とランタイムをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="7b1da-221">`dotnet-core-uninstall remove` uninstalls .NET Core SDKs and Runtimes that are specified by a collection of options.</span></span> <span data-ttu-id="7b1da-222">このツールを使用して、バージョン 5.0 以上の SDK とランタイムをアンインストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7b1da-222">The tool can't be used to uninstall SDKs and Runtimes with version 5.0 or above.</span></span>

<span data-ttu-id="7b1da-223">このツールには破壊的動作があるため、remove コマンドを実行する前に、ドライ ランを実行することを**強く**お勧めします。</span><span class="sxs-lookup"><span data-stu-id="7b1da-223">Since this tool has a destructive behavior, it's **highly** recommended that you do a dry run before running the remove command.</span></span> <span data-ttu-id="7b1da-224">ドライランにより、`remove` コマンドを使用したときに削除される .NET Core SDK とランタイムが示されます。</span><span class="sxs-lookup"><span data-stu-id="7b1da-224">The dry run will show you what .NET Core SDKs and runtimes will be removed when you use the `remove` command.</span></span> <span data-ttu-id="7b1da-225">削除しても安全な SDK とランタイムを確認するには、「[バージョンを削除する必要はあるか](../install/remove-runtime-sdk-versions.md#should-i-remove-a-version)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b1da-225">Refer to [Should I remove a version?](../install/remove-runtime-sdk-versions.md#should-i-remove-a-version) to learn which SDKs and runtimes are safe to remove.</span></span>

> [!CAUTION]
> <span data-ttu-id="7b1da-226">次の注意事項に留意してください。</span><span class="sxs-lookup"><span data-stu-id="7b1da-226">Keep in mind the following caveats:</span></span>
>
>- <span data-ttu-id="7b1da-227">このツールは、コンピューター上の `global.json` ファイルに必要な .NET Core SDK のバージョンをアンインストールできます。</span><span class="sxs-lookup"><span data-stu-id="7b1da-227">This tool can uninstall versions of the .NET Core SDK that are required by `global.json` files on your machine.</span></span> <span data-ttu-id="7b1da-228">.NET Core SDK は、「[.NET Core のダウンロード](https://dotnet.microsoft.com/download/dotnet-core)」ページから再インストールできます。</span><span class="sxs-lookup"><span data-stu-id="7b1da-228">You can reinstall .NET Core SDKs from the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>
>- <span data-ttu-id="7b1da-229">このツールは、コンピューター上のフレームワークに依存するアプリケーションに必要な .NET Core ランタイムのバージョンをアンインストールできます。</span><span class="sxs-lookup"><span data-stu-id="7b1da-229">This tool can uninstall versions of the .NET Core runtime that are required by framework dependent applications on your machine.</span></span> <span data-ttu-id="7b1da-230">.NET Core ランタイムは、「[.NET Core のダウンロード](https://dotnet.microsoft.com/download/dotnet-core)」ページから再インストールできます。</span><span class="sxs-lookup"><span data-stu-id="7b1da-230">You can reinstall .NET Core runtimes from the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>
>- <span data-ttu-id="7b1da-231">このツールは、Visual Studio が依存する .NET Core SDK とランタイムのバージョンをアンインストールできます。</span><span class="sxs-lookup"><span data-stu-id="7b1da-231">This tool can uninstall versions of the .NET Core SDK and runtime that Visual Studio relies on.</span></span> <span data-ttu-id="7b1da-232">Visual Studio のインストールを中断した場合は、Visual Studio インストーラーで [修復] を実行すると稼働状態に戻ります。</span><span class="sxs-lookup"><span data-stu-id="7b1da-232">If you break your Visual Studio installation, run "Repair" in the Visual Studio installer to get back to a working state.</span></span>

<span data-ttu-id="7b1da-233">既定で、すべてのコマンドは、Visual Studio またはその他の SDK に必要な可能性がある .NET Core SDK とランタイムを保持します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-233">By default, all commands keep the .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs.</span></span> <span data-ttu-id="7b1da-234">これらの SDK とランタイムは、引数として明示的に指定するか、`--force` オプションを使用することによってアンインストールできます。</span><span class="sxs-lookup"><span data-stu-id="7b1da-234">These SDKs and runtimes can be uninstalled by listing them explicitly as arguments or by using the `--force` option.</span></span>

<span data-ttu-id="7b1da-235">このツールでは、.NET Core SDK とランタイムをアンインストールするために昇格が必要です。</span><span class="sxs-lookup"><span data-stu-id="7b1da-235">The tool requires elevation to uninstall .NET Core SDKs and runtimes.</span></span> <span data-ttu-id="7b1da-236">Windows では管理者コマンド プロンプトで、macOS では `sudo` を使用してツールを実行してください。</span><span class="sxs-lookup"><span data-stu-id="7b1da-236">Run the tool in an Administrator command prompt on Windows and with `sudo` on macOS.</span></span> <span data-ttu-id="7b1da-237">`dry-run` および `whatif` コマンドには、昇格は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="7b1da-237">The `dry-run` and `whatif` commands don't require elevation.</span></span>

<span data-ttu-id="7b1da-238">**dotnet-core-uninstall remove**</span><span class="sxs-lookup"><span data-stu-id="7b1da-238">**dotnet-core-uninstall remove**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="7b1da-239">構文</span><span class="sxs-lookup"><span data-stu-id="7b1da-239">Synopsis</span></span>

```console
dotnet-core-uninstall remove [options] [<VERSION>...]
```

#### <a name="arguments"></a><span data-ttu-id="7b1da-240">引数</span><span class="sxs-lookup"><span data-stu-id="7b1da-240">Arguments</span></span>

* **`VERSION`**

  <span data-ttu-id="7b1da-241">アンインストールする指定されたバージョン。</span><span class="sxs-lookup"><span data-stu-id="7b1da-241">The specified version to uninstall.</span></span> <span data-ttu-id="7b1da-242">スペースで区切って、複数のバージョンを順々に指定できます。</span><span class="sxs-lookup"><span data-stu-id="7b1da-242">You may list several versions one after the other, separated by spaces.</span></span> <span data-ttu-id="7b1da-243">応答ファイルもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7b1da-243">Response files are also supported.</span></span>

  > [!TIP]
  > <span data-ttu-id="7b1da-244">すべてのバージョンをコマンド ラインに指定する代わりに応答ファイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7b1da-244">Response files are an alternative to placing all the versions on the command line.</span></span>
  > <span data-ttu-id="7b1da-245">それらはテキスト ファイルで、通常、\*.rsp 拡張子が付いています。各バージョンは別々の行に指定されます。</span><span class="sxs-lookup"><span data-stu-id="7b1da-245">They're text files, typically with a \*.rsp extension, and each version is listed on a separate line.</span></span>
  > <span data-ttu-id="7b1da-246">`VERSION` 引数の応答ファイルを指定するには、\@ 文字を使用し、そのすぐ後に応答ファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-246">To specify a response file for the `VERSION` argument, use the \@ character immediately followed by the response file name.</span></span>

#### <a name="options"></a><span data-ttu-id="7b1da-247">オプション</span><span class="sxs-lookup"><span data-stu-id="7b1da-247">Options</span></span>

## <a name="windows"></a>[<span data-ttu-id="7b1da-248">Windows</span><span class="sxs-lookup"><span data-stu-id="7b1da-248">Windows</span></span>](#tab/windows)

* **`--all`**

  <span data-ttu-id="7b1da-249">すべての .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-249">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="7b1da-250">指定したバージョンよりも小さいバージョンの .NET Core SDK とランタイムのみを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-250">Removes only the .NET Core SDKs and runtimes with a version smaller than the specified version.</span></span> <span data-ttu-id="7b1da-251">指定したバージョンはインストールされたままになります。</span><span class="sxs-lookup"><span data-stu-id="7b1da-251">The specified version remains installed.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="7b1da-252">指定したバージョンを除く、すべての .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-252">Removes all .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="7b1da-253">最上位の 1 つのバージョンを除く、すべての .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-253">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="7b1da-254">上位の修正プログラムによって置き換えられた .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-254">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="7b1da-255">このオプションは、global. json を保護します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-255">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="7b1da-256">プレビューとしてマークされている .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-256">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="7b1da-257">最上位の 1 つのプレビューを除き、プレビューとしてマークされているすべての .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-257">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--aspnet-runtime`**

  <span data-ttu-id="7b1da-258">ASP.NET Core ランタイムのみを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-258">Removes ASP.NET Core runtimes only.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="7b1da-259">.NET Core ランタイムとホスティングのバンドルのみを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-259">Removes .NET Core runtime and hosting bundles only.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="7b1da-260">指定した `major.minor` バージョンに一致する .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-260">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="7b1da-261">.NET Core ランタイムのみを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-261">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="7b1da-262">.NET Core SDK のみを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-262">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="7b1da-263">詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-263">Sets the verbosity level.</span></span> <span data-ttu-id="7b1da-264">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="7b1da-264">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="7b1da-265">既定値は `normal` です。</span><span class="sxs-lookup"><span data-stu-id="7b1da-265">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="7b1da-266">x64 SDK またはランタイムを削除するには、`--sdk`、`--runtime`、および `--aspnet-runtime` と共に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b1da-266">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x64 SDKs or runtimes.</span></span>

* **`--x86`**

  <span data-ttu-id="7b1da-267">x86 SDK またはランタイムを削除するには、`--sdk`、`--runtime`、および `--aspnet-runtime` と共に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b1da-267">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x86 SDKs or runtimes.</span></span>

* <span data-ttu-id="7b1da-268">**`-y, --yes`** Yes または No の確認を要求せずにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-268">**`-y, --yes`** Executes the command without requiring a yes or no confirmation.</span></span>

* <span data-ttu-id="7b1da-269">**`--force`** Visual Studio によって使用される可能性があるバージョンを強制的に削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-269">**`--force`** Forces removal of versions that might be used by Visual Studio.</span></span>

<span data-ttu-id="7b1da-270">メモ:</span><span class="sxs-lookup"><span data-stu-id="7b1da-270">Notes:</span></span>

1. <span data-ttu-id="7b1da-271">`--sdk`、`--runtime`、`--aspnet-runtime`、および `--hosting-bundle` の 1 つだけが必要です。</span><span class="sxs-lookup"><span data-stu-id="7b1da-271">Exactly one of `--sdk`, `--runtime`, `--aspnet-runtime`, and `--hosting-bundle` is required.</span></span>
2. <span data-ttu-id="7b1da-272">`--all`、`--all-below`、`--all-but`、`--all-but-latest`、`--all-lower-patches`、`--all-previews`、`--all-previews-but-latest`、`--major-minor`、および `[<VERSION>...]` は排他的です。</span><span class="sxs-lookup"><span data-stu-id="7b1da-272">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>
3. <span data-ttu-id="7b1da-273">`--x64` または `--x86` が指定されていない場合は、x64 と x86 の両方が削除されます。</span><span class="sxs-lookup"><span data-stu-id="7b1da-273">If `--x64` or `--x86` aren't specified, then both x64 and x86 will be removed.</span></span>

## <a name="macos"></a>[<span data-ttu-id="7b1da-274">macOS</span><span class="sxs-lookup"><span data-stu-id="7b1da-274">macOS</span></span>](#tab/macos)

* **`--all`**

  <span data-ttu-id="7b1da-275">すべての .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-275">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="7b1da-276">指定したバージョンより下の .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-276">Removes .NET Core SDKs and runtimes below the specified version.</span></span> <span data-ttu-id="7b1da-277">指定したバージョンはそのまま残ります。</span><span class="sxs-lookup"><span data-stu-id="7b1da-277">The specified version will remain.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="7b1da-278">指定したバージョンを除き、.NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-278">Removes .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="7b1da-279">最上位の 1 つのバージョンを除く、すべての .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-279">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="7b1da-280">上位の修正プログラムによって置き換えられた .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-280">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="7b1da-281">このオプションは、global. json を保護します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-281">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="7b1da-282">プレビューとしてマークされている .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-282">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="7b1da-283">最上位の 1 つのプレビューを除き、プレビューとしてマークされているすべての .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-283">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="7b1da-284">指定した `major.minor` バージョンに一致する .NET Core SDK とランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-284">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="7b1da-285">.NET Core ランタイムのみを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-285">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="7b1da-286">.NET Core SDK のみを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-286">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="7b1da-287">詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-287">Sets the verbosity level.</span></span> <span data-ttu-id="7b1da-288">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="7b1da-288">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="7b1da-289">既定値は `normal` です。</span><span class="sxs-lookup"><span data-stu-id="7b1da-289">The default value is `normal`.</span></span>

* <span data-ttu-id="7b1da-290">**`-y, --yes`** Y/N の確認を要求せずにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-290">**`-y, --yes`** Executes the command without requiring Y/N confirmation.</span></span>
  
* <span data-ttu-id="7b1da-291">**`--force`** Visual Studio または SDK によって使用される可能性があるバージョンを強制的に削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-291">**`--force`** Forces removal of versions that might be used by Visual Studio or SDKs.</span></span>

<span data-ttu-id="7b1da-292">メモ:</span><span class="sxs-lookup"><span data-stu-id="7b1da-292">Notes:</span></span>

1. <span data-ttu-id="7b1da-293">`--sdk` と `--runtime` のうち 1 つだけが必要です。</span><span class="sxs-lookup"><span data-stu-id="7b1da-293">Exactly one of `--sdk` and `--runtime` is required.</span></span>
2. <span data-ttu-id="7b1da-294">`--all`、`--all-below`、`--all-but`、`--all-but-latest`、`--all-lower-patches`、`--all-previews`、`--all-previews-but-latest`、`--major-minor`、および `[<VERSION>...]` は排他的です。</span><span class="sxs-lookup"><span data-stu-id="7b1da-294">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>

---

#### <a name="examples"></a><span data-ttu-id="7b1da-295">使用例</span><span class="sxs-lookup"><span data-stu-id="7b1da-295">Examples</span></span>

> [!NOTE]
> <span data-ttu-id="7b1da-296">既定で、Visual Studio またはその他の SDK に必要な可能性がある .NET Core SDK とランタイムは保持されます。</span><span class="sxs-lookup"><span data-stu-id="7b1da-296">By default, .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs are kept.</span></span> <span data-ttu-id="7b1da-297">次の例では、コンピューターの状態によっては、指定された SDK とランタイムの一部が保持される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7b1da-297">In the following examples, some of the specified SDKs and runtimes may remain, depending on the state of the machine.</span></span> <span data-ttu-id="7b1da-298">すべての SDK とランタイムを削除するには、それらを引数として明示的に指定するか、`--force` オプションを使用してください。</span><span class="sxs-lookup"><span data-stu-id="7b1da-298">To remove all SDKs and runtimes, list them explicitly as arguments or use the `--force` option.</span></span>

* <span data-ttu-id="7b1da-299">Y/N の確認を要求せずに、バージョン `3.0.0-preview6-27804-01` を除くすべての .NET Core ランタイムを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-299">Remove all .NET Core runtimes except the version `3.0.0-preview6-27804-01` without requiring Y/N confirmation:</span></span>

  ```console
  dotnet-core-uninstall remove --all-but 3.0.0-preview6-27804-01 --runtime --yes
  ```

* <span data-ttu-id="7b1da-300">Y/N の確認を要求せずに、すべての .NET Core 1.1 SDK を削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-300">Remove all .NET Core 1.1 SDKs without requiring Y/n confirmation:</span></span>

  ```console
  dotnet-core-uninstall remove --sdk --major-minor 1.1 -y
  ```

* <span data-ttu-id="7b1da-301">コンソールに出力せずに、.NET Core 1.1.11 SDK を削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-301">Remove the .NET Core 1.1.11 SDK with no console output:</span></span>

  ```console
  dotnet-core-uninstall remove 1.1.11 --sdk --yes --verbosity q
  ```

* <span data-ttu-id="7b1da-302">このツールで安全に削除できるすべての .NET Core SDK を削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-302">Remove all .NET Core SDKs that can safely be removed by this tool:</span></span>

  ```console
  dotnet-core-uninstall remove --all --sdk
  ```

* <span data-ttu-id="7b1da-303">Visual Studio で必要な可能性がある SDK を含め、このツールで削除できるすべての .NET Core SDK を削除します (推奨されません)。</span><span class="sxs-lookup"><span data-stu-id="7b1da-303">Remove all .NET Core SDKs that can be removed by this tool, including those SDKs that may be required by Visual Studio (not recommended):</span></span>

  ```console
  dotnet-core-uninstall remove --all --sdk --force
  ```

* <span data-ttu-id="7b1da-304">応答ファイル `versions.rsp` に指定されたすべての .NET Core SDK を削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-304">Remove all .NET Core SDKs that are specified in the response file `versions.rsp`</span></span>

  ```console
  dotnet-core-uninstall remove --sdk @versions.rsp
  ```

  <span data-ttu-id="7b1da-305">*versions.rsp* の内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7b1da-305">The content of *versions.rsp* is as follows:</span></span>
  
  ```text
  2.2.300
  2.1.700
  ```

### <a name="step-4---delete-the-nuget-fallback-folder-optional"></a><span data-ttu-id="7b1da-306">手順 4 - NuGet フォールバック フォルダーを削除する (省略可能)</span><span class="sxs-lookup"><span data-stu-id="7b1da-306">Step 4 - Delete the NuGet fallback folder (optional)</span></span>

<span data-ttu-id="7b1da-307">場合によっては、`NuGetFallbackFolder` が不要になり、削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="7b1da-307">In some cases, you no longer need the `NuGetFallbackFolder` and may wish to delete it.</span></span> <span data-ttu-id="7b1da-308">このフォルダーの削除の詳細については、[NuGetFallbackFolder の削除](../install/remove-runtime-sdk-versions.md#remove-the-nuget-fallback-folder)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b1da-308">For more information about deleting this folder, see [Remove the NuGetFallbackFolder](../install/remove-runtime-sdk-versions.md#remove-the-nuget-fallback-folder).</span></span>

## <a name="uninstall-the-tool"></a><span data-ttu-id="7b1da-309">ツールをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="7b1da-309">Uninstall the tool</span></span>

## <a name="windows"></a>[<span data-ttu-id="7b1da-310">Windows</span><span class="sxs-lookup"><span data-stu-id="7b1da-310">Windows</span></span>](#tab/windows)

1. <span data-ttu-id="7b1da-311">**[プログラムの追加と削除]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="7b1da-311">Open **Add or Remove Programs**.</span></span>
2. <span data-ttu-id="7b1da-312">`Microsoft .NET Core SDK Uninstall Tool` を検索します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-312">Search for `Microsoft .NET Core SDK Uninstall Tool`.</span></span>
3. <span data-ttu-id="7b1da-313">**[アンインストール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-313">Select **Uninstall**.</span></span>

## <a name="macos"></a>[<span data-ttu-id="7b1da-314">macOS</span><span class="sxs-lookup"><span data-stu-id="7b1da-314">macOS</span></span>](#tab/macos)

<span data-ttu-id="7b1da-315">ダウンロードした *dotnet-core-uninstall.tar.gz* ファイルをインストールしたディレクトリから削除します。</span><span class="sxs-lookup"><span data-stu-id="7b1da-315">Delete the downloaded *dotnet-core-uninstall.tar.gz* file from the directory where it was installed.</span></span> <span data-ttu-id="7b1da-316">このファイルの内容を別のディレクトリに解凍した場合は、必ずその内容も削除してください。</span><span class="sxs-lookup"><span data-stu-id="7b1da-316">If you unzipped the contents of this file into another directory, be sure to delete that content as well.</span></span>

---
