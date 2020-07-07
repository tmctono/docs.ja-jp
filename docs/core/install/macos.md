---
title: macOS に .NET Core をインストールする
description: .NET Core をインストールできる macOS のバージョンについて説明します。
author: adegeo
ms.author: adegeo
ms.date: 06/25/2020
ms.openlocfilehash: bb1a0fa24e2f6e8850cbe59378793ff846f04ba9
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85804453"
---
# <a name="install-net-core-on-macos"></a><span data-ttu-id="bf76a-103">macOS に .NET Core をインストールする</span><span class="sxs-lookup"><span data-stu-id="bf76a-103">Install .NET Core on macOS</span></span>

> [!div class="op_single_selector"]
>
> - [Windows へのインストール](windows.md)
> - [macOS へのインストール](macos.md)
> - [Linux にインストールする](linux.md)

<span data-ttu-id="bf76a-107">この記事では、macOS に .NET Core をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bf76a-107">In this article, you'll learn how to install .NET Core on macOS.</span></span> <span data-ttu-id="bf76a-108">.NET Core は、ランタイムと SDK で構成されています。</span><span class="sxs-lookup"><span data-stu-id="bf76a-108">.NET Core is made up of the runtime and the SDK.</span></span> <span data-ttu-id="bf76a-109">ランタイムは .NET Core アプリを実行するために使用され、アプリに含まれている場合と含まれていない場合があります。</span><span class="sxs-lookup"><span data-stu-id="bf76a-109">The runtime is used to run a .NET Core app and may or may not be included with the app.</span></span> <span data-ttu-id="bf76a-110">SDK は、.NET Core アプリとライブラリの作成に使用されます。</span><span class="sxs-lookup"><span data-stu-id="bf76a-110">The SDK is used to create .NET Core apps and libraries.</span></span> <span data-ttu-id="bf76a-111">.NET Core ランタイムは、常に SDK と共にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="bf76a-111">The .NET Core runtime is always installed with the SDK.</span></span>

<span data-ttu-id="bf76a-112">.NET Core の最新バージョンは 3.1 です。</span><span class="sxs-lookup"><span data-stu-id="bf76a-112">The latest version of .NET Core is 3.1.</span></span>

[<span data-ttu-id="bf76a-113">.NET Core をダウンロードする。</span><span class="sxs-lookup"><span data-stu-id="bf76a-113">Download .NET Core.</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="supported-releases"></a><span data-ttu-id="bf76a-114">サポートされているリリース</span><span class="sxs-lookup"><span data-stu-id="bf76a-114">Supported releases</span></span>

<span data-ttu-id="bf76a-115">次の表に、現在サポートされている .NET Core リリースと、それらがサポートされている macOS のバージョンの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="bf76a-115">The following table is a list of currently supported .NET Core releases and the versions of macOS they're supported on.</span></span> <span data-ttu-id="bf76a-116">これらのバージョンは、いずれかのバージョンの [.NET Core がサポート終了に達する](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)まで、サポートされています。</span><span class="sxs-lookup"><span data-stu-id="bf76a-116">These versions remain supported either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span></span>

- <span data-ttu-id="bf76a-117">✔️ は、.NET Core のバージョンがまだサポートされていることを示します。</span><span class="sxs-lookup"><span data-stu-id="bf76a-117">A ✔️ indicates that the version of .NET Core is still supported.</span></span>
- <span data-ttu-id="bf76a-118">❌ は、.NET Core のバージョンがサポートされていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="bf76a-118">A ❌ indicates that the version of .NET Core isn't supported.</span></span>

| <span data-ttu-id="bf76a-119">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="bf76a-119">Operating System</span></span>          | <span data-ttu-id="bf76a-120">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="bf76a-120">.NET Core 2.1</span></span> | <span data-ttu-id="bf76a-121">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="bf76a-121">.NET Core 3.1</span></span> | <span data-ttu-id="bf76a-122">.NET 5 Preview</span><span class="sxs-lookup"><span data-stu-id="bf76a-122">.NET 5 Preview</span></span> |
|---------------------------|---------------|---------------|----------------|
| <span data-ttu-id="bf76a-123">macOS 10.15 "Catalina"</span><span class="sxs-lookup"><span data-stu-id="bf76a-123">macOS 10.15 "Catalina"</span></span>    | <span data-ttu-id="bf76a-124">✔️ 2.1 ([リリース ノート][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="bf76a-124">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="bf76a-125">✔️ 3.1 ([リリース ノート][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="bf76a-125">✔️ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="bf76a-126">✔️ 5.0 Preview ([リリース ノート][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="bf76a-126">✔️ 5.0 Preview ([Release notes][release-notes-50])</span></span> |
| <span data-ttu-id="bf76a-127">macOS 10.14 "Mojave"</span><span class="sxs-lookup"><span data-stu-id="bf76a-127">macOS 10.14 "Mojave"</span></span>      | <span data-ttu-id="bf76a-128">✔️ 2.1 ([リリース ノート][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="bf76a-128">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="bf76a-129">✔️ 3.1 ([リリース ノート][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="bf76a-129">✔️ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="bf76a-130">✔️ 5.0 Preview ([リリース ノート][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="bf76a-130">✔️ 5.0 Preview ([Release notes][release-notes-50])</span></span> |
| <span data-ttu-id="bf76a-131">macOS 10.13 "High Sierra"</span><span class="sxs-lookup"><span data-stu-id="bf76a-131">macOS 10.13 "High Sierra"</span></span> | <span data-ttu-id="bf76a-132">✔️ 2.1 ([リリース ノート][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="bf76a-132">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="bf76a-133">✔️ 3.1 ([リリース ノート][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="bf76a-133">✔️ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="bf76a-134">✔️ 5.0 Preview ([リリース ノート][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="bf76a-134">✔️ 5.0 Preview ([Release notes][release-notes-50])</span></span> |
| <span data-ttu-id="bf76a-135">macOS 10.12 "Sierra"</span><span class="sxs-lookup"><span data-stu-id="bf76a-135">macOS 10.12 "Sierra"</span></span>      | <span data-ttu-id="bf76a-136">✔️ 2.1 ([リリース ノート][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="bf76a-136">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="bf76a-137">❌ 3.1 ([リリース ノート][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="bf76a-137">❌ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="bf76a-138">❌ 5.0 Preview ([リリース ノート][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="bf76a-138">❌ 5.0 Preview ([Release notes][release-notes-50])</span></span> |

## <a name="unsupported-releases"></a><span data-ttu-id="bf76a-139">サポートされていないリリース</span><span class="sxs-lookup"><span data-stu-id="bf76a-139">Unsupported releases</span></span>

<span data-ttu-id="bf76a-140">次のバージョンの .NET Core は ❌ サポート対象外となりました。</span><span class="sxs-lookup"><span data-stu-id="bf76a-140">The following versions of .NET Core are ❌ no longer supported.</span></span> <span data-ttu-id="bf76a-141">これらのダウンロードは、まだ公開されています。</span><span class="sxs-lookup"><span data-stu-id="bf76a-141">The downloads for these still remain published:</span></span>

- <span data-ttu-id="bf76a-142">3.0 ([リリース ノート][release-notes-30])</span><span class="sxs-lookup"><span data-stu-id="bf76a-142">3.0 ([Release notes][release-notes-30])</span></span>
- <span data-ttu-id="bf76a-143">2.2 ([リリース ノート][release-notes-22])</span><span class="sxs-lookup"><span data-stu-id="bf76a-143">2.2 ([Release notes][release-notes-22])</span></span>
- <span data-ttu-id="bf76a-144">2.0 ([リリース ノート][release-notes-20])</span><span class="sxs-lookup"><span data-stu-id="bf76a-144">2.0 ([Release notes][release-notes-20])</span></span>

## <a name="runtime-information"></a><span data-ttu-id="bf76a-145">ランタイムに関する情報</span><span class="sxs-lookup"><span data-stu-id="bf76a-145">Runtime information</span></span>

<span data-ttu-id="bf76a-146">ランタイムは、.NET Core で作成されたアプリを実行するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="bf76a-146">The runtime is used to run apps created with .NET Core.</span></span> <span data-ttu-id="bf76a-147">アプリの作成者は、アプリを公開するとき、アプリにランタイムを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="bf76a-147">When an app author publishes an app, they can include the runtime with their app.</span></span> <span data-ttu-id="bf76a-148">ランタイムが含まれていない場合は、ユーザーがランタイムをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf76a-148">If they don't include the runtime, it's up to the user to install the runtime.</span></span>

<span data-ttu-id="bf76a-149">macOS には、3 つの異なるランタイムをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="bf76a-149">There are three different runtimes you can install on macOS:</span></span>

<span data-ttu-id="bf76a-150">*ASP.NET Core ランタイム*</span><span class="sxs-lookup"><span data-stu-id="bf76a-150">*ASP.NET Core runtime*</span></span>\
<span data-ttu-id="bf76a-151">ASP.NET Core アプリを実行します。</span><span class="sxs-lookup"><span data-stu-id="bf76a-151">Runs ASP.NET Core apps.</span></span> <span data-ttu-id="bf76a-152">.NET Core ランタイムが含まれます。</span><span class="sxs-lookup"><span data-stu-id="bf76a-152">Includes the .NET Core runtime.</span></span>

<span data-ttu-id="bf76a-153">*.NET Core ランタイム*</span><span class="sxs-lookup"><span data-stu-id="bf76a-153">*.NET Core runtime*</span></span>\
<span data-ttu-id="bf76a-154">このランタイムは最も単純なランタイムであり、他のランタイムは含まれていません。</span><span class="sxs-lookup"><span data-stu-id="bf76a-154">This runtime is the simplest runtime and doesn't include any other runtime.</span></span> <span data-ttu-id="bf76a-155">.NET Core アプリとの互換性を最善にするには、"*ASP.NET Core ランタイム*" をインストールすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bf76a-155">It's highly recommended that you install *ASP.NET Core runtime* for the best compatibility with .NET Core apps.</span></span>

[<span data-ttu-id="bf76a-156">.NET Core ランタイムをダウンロードする。</span><span class="sxs-lookup"><span data-stu-id="bf76a-156">Download .NET Core Runtime.</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="sdk-information"></a><span data-ttu-id="bf76a-157">SDK に関する情報</span><span class="sxs-lookup"><span data-stu-id="bf76a-157">SDK information</span></span>

<span data-ttu-id="bf76a-158">SDK は、.NET Core アプリとライブラリを作成して公開するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="bf76a-158">The SDK is used to build and publish .NET Core apps and libraries.</span></span> <span data-ttu-id="bf76a-159">SDK のインストールには、次の両方の[ランタイム](#runtime-information)が含まれます: ASP.NET Core と .NET Core。</span><span class="sxs-lookup"><span data-stu-id="bf76a-159">Installing the SDK includes both [runtimes](#runtime-information): ASP.NET Core and .NET Core.</span></span>

[<span data-ttu-id="bf76a-160">.NET Core SDK をダウンロードする。</span><span class="sxs-lookup"><span data-stu-id="bf76a-160">Download .NET Core SDK.</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="dependencies"></a><span data-ttu-id="bf76a-161">依存関係</span><span class="sxs-lookup"><span data-stu-id="bf76a-161">Dependencies</span></span>

<span data-ttu-id="bf76a-162">.NET Core は、次の macOS のリリースでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="bf76a-162">.NET Core is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="bf76a-163">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="bf76a-163">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="bf76a-164">.NET Core のバージョン</span><span class="sxs-lookup"><span data-stu-id="bf76a-164">.NET Core Version</span></span> | <span data-ttu-id="bf76a-165">macOS</span><span class="sxs-lookup"><span data-stu-id="bf76a-165">macOS</span></span>                 | <span data-ttu-id="bf76a-166">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="bf76a-166">Architectures</span></span> |     |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="bf76a-167">3.1</span><span class="sxs-lookup"><span data-stu-id="bf76a-167">3.1</span></span>               | <span data-ttu-id="bf76a-168">High Sierra (10.13+)</span><span class="sxs-lookup"><span data-stu-id="bf76a-168">High Sierra (10.13+)</span></span>  | <span data-ttu-id="bf76a-169">X64</span><span class="sxs-lookup"><span data-stu-id="bf76a-169">x64</span></span> | [<span data-ttu-id="bf76a-170">詳細情報</span><span class="sxs-lookup"><span data-stu-id="bf76a-170">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="bf76a-171">3.0</span><span class="sxs-lookup"><span data-stu-id="bf76a-171">3.0</span></span>               | <span data-ttu-id="bf76a-172">High Sierra (10.13+)</span><span class="sxs-lookup"><span data-stu-id="bf76a-172">High Sierra (10.13+)</span></span>  | <span data-ttu-id="bf76a-173">X64</span><span class="sxs-lookup"><span data-stu-id="bf76a-173">x64</span></span> | [<span data-ttu-id="bf76a-174">詳細情報</span><span class="sxs-lookup"><span data-stu-id="bf76a-174">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="bf76a-175">2.2</span><span class="sxs-lookup"><span data-stu-id="bf76a-175">2.2</span></span>               | <span data-ttu-id="bf76a-176">Sierra (10.12+)</span><span class="sxs-lookup"><span data-stu-id="bf76a-176">Sierra (10.12+)</span></span>       | <span data-ttu-id="bf76a-177">X64</span><span class="sxs-lookup"><span data-stu-id="bf76a-177">x64</span></span> | [<span data-ttu-id="bf76a-178">詳細情報</span><span class="sxs-lookup"><span data-stu-id="bf76a-178">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="bf76a-179">2.1</span><span class="sxs-lookup"><span data-stu-id="bf76a-179">2.1</span></span>               | <span data-ttu-id="bf76a-180">Sierra (10.12+)</span><span class="sxs-lookup"><span data-stu-id="bf76a-180">Sierra (10.12+)</span></span>       | <span data-ttu-id="bf76a-181">X64</span><span class="sxs-lookup"><span data-stu-id="bf76a-181">x64</span></span> | [<span data-ttu-id="bf76a-182">詳細情報</span><span class="sxs-lookup"><span data-stu-id="bf76a-182">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

<span data-ttu-id="bf76a-183">macOS Catalina (バージョン 10.15) 以降では、2019 年 6 月 1 日より後に作成され、Developer ID と共に配布されたすべてのソフトウェアは公証される必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf76a-183">Beginning with macOS Catalina (version 10.15), all software built after June 1, 2019 that is distributed with Developer ID, must be notarized.</span></span> <span data-ttu-id="bf76a-184">この要件は、.NET Core ランタイム、.NET Core SDK、および .NET Core を使用して作成されたソフトウェアに適用されます。</span><span class="sxs-lookup"><span data-stu-id="bf76a-184">This requirement applies to the .NET Core runtime, .NET Core SDK, and software created with .NET Core.</span></span>

<span data-ttu-id="bf76a-185">.NET Core (ランタイムと SDK の両方) バージョン 3.1、3.0、2.1 のインストーラーは、2020 年 2 月 18 日から公証されています。</span><span class="sxs-lookup"><span data-stu-id="bf76a-185">The installers for .NET Core (both runtime and SDK) versions 3.1, 3.0, and 2.1, have been notarized since February 18, 2020.</span></span> <span data-ttu-id="bf76a-186">それより前にリリースされたバージョンは、公証されていません。</span><span class="sxs-lookup"><span data-stu-id="bf76a-186">Prior released versions aren't notarized.</span></span> <span data-ttu-id="bf76a-187">公証されていないアプリを実行すると、次のイメージのようなエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bf76a-187">If you run a non-notarized app, you'll see an error similar to the following image:</span></span>

![macOS Catalina の公証に関するアラート](media/dependencies/macos-notarized-pkg-warning.png)

<span data-ttu-id="bf76a-189">公証の強制が .NET Core (および .NET Core アプリ) に与える影響の詳細については、[macOS Catalina の公証への対応](macos-notarization-issues.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf76a-189">For more information about how enforced-notarization affects .NET Core (and your .NET Core apps), see [Working with macOS Catalina Notarization](macos-notarization-issues.md).</span></span>

## <a name="libgdiplus"></a><span data-ttu-id="bf76a-190">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="bf76a-190">libgdiplus</span></span>

<span data-ttu-id="bf76a-191">*System.Drawing.Common* アセンブリを使用する .NET Core アプリケーションでは、libgdiplus をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf76a-191">.NET Core applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="bf76a-192">libgdiplus を取得する簡単な方法は、macOS の [Homebrew ("brew")](https://brew.sh/) パッケージ マネージャーを使用することです。</span><span class="sxs-lookup"><span data-stu-id="bf76a-192">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="bf76a-193">*brew* をインストールしたら、端末 (コマンド) プロンプトで次のコマンドを実行して libgdiplus をインストールします。</span><span class="sxs-lookup"><span data-stu-id="bf76a-193">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

## <a name="install-with-an-installer"></a><span data-ttu-id="bf76a-194">インストーラーを使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="bf76a-194">Install with an installer</span></span>

<span data-ttu-id="bf76a-195">macOS には、.NET Core 3.1 SDK のインストールに使用できるスタンドアロン インストーラーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="bf76a-195">macOS has standalone installers that can be used to install the .NET Core 3.1 SDK:</span></span>

- [<span data-ttu-id="bf76a-196">x64 (64 ビット) CPU</span><span class="sxs-lookup"><span data-stu-id="bf76a-196">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

## <a name="download-and-manually-install"></a><span data-ttu-id="bf76a-197">手動でダウンロードしてインストールする</span><span class="sxs-lookup"><span data-stu-id="bf76a-197">Download and manually install</span></span>

<!-- Note, this content is taken from includes/linux-install-manual.md but changed for macOS. Any fixes should be applied there too, though content may be different -->

<span data-ttu-id="bf76a-198">.NET Core 用 macOS インストーラーの代わりに、SDK とランタイムをダウンロードして手動でインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="bf76a-198">As an alternative to the macOS installers for .NET Core, you can download and manually install the SDK and runtime.</span></span> <span data-ttu-id="bf76a-199">手動インストールは、通常、継続的インテグレーション テストの一環として実行されます。</span><span class="sxs-lookup"><span data-stu-id="bf76a-199">Manual install is usually performed as part of continuous integration testing.</span></span> <span data-ttu-id="bf76a-200">開発者またはユーザーの場合、通常は[インストーラー](https://dotnet.microsoft.com/download/dotnet-core)を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bf76a-200">For a developer or user, it's generally better to use an [installer](https://dotnet.microsoft.com/download/dotnet-core).</span></span>

<span data-ttu-id="bf76a-201">.NET Core SDK をインストールする場合、対応するランタイムをインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="bf76a-201">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="bf76a-202">まず、次のいずれかのサイトから SDK またはランタイムの**バイナリ** リリースをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="bf76a-202">First, download a **binary** release for either the SDK or the runtime from one of the following sites:</span></span>

- <span data-ttu-id="bf76a-203">✔️ [.NET 5.0 preview のダウンロード](https://dotnet.microsoft.com/download/dotnet/5.0)</span><span class="sxs-lookup"><span data-stu-id="bf76a-203">✔️ [.NET 5.0 preview downloads](https://dotnet.microsoft.com/download/dotnet/5.0)</span></span>
- <span data-ttu-id="bf76a-204">✔️ [.NET Core 3.1 のダウンロード](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span><span class="sxs-lookup"><span data-stu-id="bf76a-204">✔️ [.NET Core 3.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span></span>
- <span data-ttu-id="bf76a-205">✔️ [.NET Core 2.1 のダウンロード](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span><span class="sxs-lookup"><span data-stu-id="bf76a-205">✔️ [.NET Core 2.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span></span>
- [<span data-ttu-id="bf76a-206">すべての .NET Core のダウンロード</span><span class="sxs-lookup"><span data-stu-id="bf76a-206">All .NET Core downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

<span data-ttu-id="bf76a-207">次に、ダウンロードしたファイルを抽出し、`export` コマンドを使用して .NET Core で使用される変数を設定してから、.NET Core が PATH に含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bf76a-207">Next, extract the downloaded file and use the `export` command to set variables used by .NET Core and then ensure .NET Core is in PATH.</span></span>

<span data-ttu-id="bf76a-208">ランタイムを抽出し、.NET Core CLI コマンドをターミナルで使用できるようにするには、最初に .NET Core のバイナリ リリースをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="bf76a-208">To extract the runtime and make the .NET Core CLI commands available at the terminal, first download a .NET Core binary release.</span></span> <span data-ttu-id="bf76a-209">次に、ターミナルを開き、ファイルが保存されているディレクトリから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bf76a-209">Then, open a terminal and run the following commands from the directory where the file was saved.</span></span> <span data-ttu-id="bf76a-210">アーカイブ ファイル名は、ダウンロードした内容によって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="bf76a-210">The archive file name may be different depending on what you downloaded.</span></span>

<span data-ttu-id="bf76a-211">**次のコマンドを使用して、ランタイムを抽出します**。</span><span class="sxs-lookup"><span data-stu-id="bf76a-211">**Use the following command to extract the runtime**:</span></span>

```bash
mkdir -p "$HOME/dotnet" && tar zxf aspnetcore-runtime-3.1.5-osx-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

<span data-ttu-id="bf76a-212">**次のコマンドを使用して、SDK を抽出します**。</span><span class="sxs-lookup"><span data-stu-id="bf76a-212">**Use the following command to extract the SDK**:</span></span>

```bash
mkdir -p "$HOME/dotnet" && tar zxf dotnet-sdk-3.1.301-osx-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="bf76a-213">上記の `export` コマンドでは、それを実行したターミナル セッションでのみ .NET Core CLI コマンドを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="bf76a-213">The preceding `export` commands only make the .NET Core CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="bf76a-214">シェル プロファイルを編集して、コマンドを永続的に追加することができます。</span><span class="sxs-lookup"><span data-stu-id="bf76a-214">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="bf76a-215">Linux ではさまざまなシェルを使用でき、それぞれに異なるプロファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="bf76a-215">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="bf76a-216">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bf76a-216">For example:</span></span>
>
> - <span data-ttu-id="bf76a-217">**Bash シェル**: *~/.bash_profile*、 *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="bf76a-217">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="bf76a-218">**Korn シェル**: *~/.kshrc* または *.profile*</span><span class="sxs-lookup"><span data-stu-id="bf76a-218">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="bf76a-219">**Z シェル**: *~/.zshrc* または *.zprofile*</span><span class="sxs-lookup"><span data-stu-id="bf76a-219">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
>
> <span data-ttu-id="bf76a-220">シェルの適切なソース ファイルを編集し、既存の `PATH` ステートメントの末尾に `:$HOME/dotnet` を追加します。</span><span class="sxs-lookup"><span data-stu-id="bf76a-220">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="bf76a-221">`PATH` ステートメントが含まれていない場合は、`export PATH=$PATH:$HOME/dotnet` を含む新しい行を追加します。</span><span class="sxs-lookup"><span data-stu-id="bf76a-221">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="bf76a-222">また、ファイルの末尾に `export DOTNET_ROOT=$HOME/dotnet` を追加します。</span><span class="sxs-lookup"><span data-stu-id="bf76a-222">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

<span data-ttu-id="bf76a-223">この方法では、別々の場所に異なるバージョンをインストールして、どのアプリケーションにどれを使用するかを明示的に選択できます。</span><span class="sxs-lookup"><span data-stu-id="bf76a-223">This approach lets you install different versions into separate locations and choose explicitly which one to use by which application.</span></span>

## <a name="install-with-visual-studio-for-mac"></a><span data-ttu-id="bf76a-224">Visual Studio for Mac を使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="bf76a-224">Install with Visual Studio for Mac</span></span>

<span data-ttu-id="bf76a-225">Visual Studio for Mac では、 **[.NET Core]** ワークロードを選択すると、.NET Core SDK がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="bf76a-225">Visual Studio for Mac installs the .NET Core SDK when the **.NET Core** workload is selected.</span></span> <span data-ttu-id="bf76a-226">macOS で .NET Core の開発を始めるには、「[Visual Studio 2019 for Mac をインストールする](/visualstudio/mac/installation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf76a-226">To get started with .NET Core development on macOS, see [Install Visual Studio 2019 for Mac](/visualstudio/mac/installation).</span></span> <span data-ttu-id="bf76a-227">最新リリースである .NET Core 3.1 の場合は、Visual Studio for Mac 8.4 Preview を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf76a-227">For the latest release, .NET Core 3.1, you must use the Visual Studio for Mac 8.4 Preview.</span></span>

<span data-ttu-id="bf76a-228">[![macOS Visual Studio 2019 for Mac と .NET Core ワークロード機能](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="bf76a-228">[![macOS Visual Studio 2019 for Mac with .NET Core workload feature](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span></span>

## <a name="install-alongside-visual-studio-code"></a><span data-ttu-id="bf76a-229">Visual Studio Code と共にインストールする</span><span class="sxs-lookup"><span data-stu-id="bf76a-229">Install alongside Visual Studio Code</span></span>

<span data-ttu-id="bf76a-230">Visual Studio Code は、デスクトップ上で動作する強力で軽量なソース コード エディターです。</span><span class="sxs-lookup"><span data-stu-id="bf76a-230">Visual Studio Code is a powerful and lightweight source code editor that runs on your desktop.</span></span> <span data-ttu-id="bf76a-231">Visual Studio Code は、Windows、macOS、Linux で利用できます。</span><span class="sxs-lookup"><span data-stu-id="bf76a-231">Visual Studio Code is available for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="bf76a-232">Visual Studio Code には、Visual Studio のような自動化された .NET Core インストーラーは付属していませんが、.NET Core のサポートを簡単に追加できます。</span><span class="sxs-lookup"><span data-stu-id="bf76a-232">While Visual Studio Code doesn't come with an automated .NET Core installer like Visual Studio does, adding .NET Core support is simple.</span></span>

01. <span data-ttu-id="bf76a-233">[Visual Studio Code をダウンロードしてインストールします](https://code.visualstudio.com/Download)。</span><span class="sxs-lookup"><span data-stu-id="bf76a-233">[Download and install Visual Studio Code](https://code.visualstudio.com/Download).</span></span>
01. <span data-ttu-id="bf76a-234">[.NET Core SDK をダウンロードしてインストールします](https://dotnet.microsoft.com/download/dotnet-core)。</span><span class="sxs-lookup"><span data-stu-id="bf76a-234">[Download and install the .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core).</span></span>
01. <span data-ttu-id="bf76a-235">[Visual Studio Code マーケットプレースから C# 拡張機能をインストールします](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)。</span><span class="sxs-lookup"><span data-stu-id="bf76a-235">[Install the C# extension from the Visual Studio Code marketplace](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span></span>

## <a name="install-with-bash-automation"></a><span data-ttu-id="bf76a-236">bash オートメーションを使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="bf76a-236">Install with bash automation</span></span>

<span data-ttu-id="bf76a-237">[dotnet-install スクリプト](../tools/dotnet-install-script.md)は、ランタイムの自動化および管理者以外によるインストールに使用されます。</span><span class="sxs-lookup"><span data-stu-id="bf76a-237">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="bf76a-238">スクリプトは、[dotnet-install スクリプト参照ページ](../tools/dotnet-install-script.md)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="bf76a-238">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="bf76a-239">スクリプトでは、既定で最新の [長期サポート (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) バージョン (.NET Core 3.1) がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="bf76a-239">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="bf76a-240">`current` スイッチを指定することで、特定のリリースを選択できます。</span><span class="sxs-lookup"><span data-stu-id="bf76a-240">You can choose a specific release by specifying the `current` switch.</span></span> <span data-ttu-id="bf76a-241">ランタイムをインストールするには、`runtime` スイッチを含めます。</span><span class="sxs-lookup"><span data-stu-id="bf76a-241">Include the `runtime` switch to install a runtime.</span></span> <span data-ttu-id="bf76a-242">それ以外の場合は、スクリプトによって [SDK](sdk.md) がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="bf76a-242">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```bash
./dotnet-install.sh --channel 3.1 --runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="bf76a-243">上のコマンドでは、互換性を最大限に高めるために ASP.NET Core ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="bf76a-243">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="bf76a-244">ASP.NET Core ランタイムには、標準の .NET Core ランタイムも含まれています。</span><span class="sxs-lookup"><span data-stu-id="bf76a-244">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

## <a name="docker"></a><span data-ttu-id="bf76a-245">Docker</span><span class="sxs-lookup"><span data-stu-id="bf76a-245">Docker</span></span>

<span data-ttu-id="bf76a-246">コンテナーを使用すると、アプリケーションをホスト システムの他の部分から簡単に分離できます。</span><span class="sxs-lookup"><span data-stu-id="bf76a-246">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="bf76a-247">同じコンピューター上のコンテナーでは、カーネルだけが共有され、アプリケーションに提供されたリソースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="bf76a-247">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="bf76a-248">.NET Core は Docker コンテナー内で実行できます。</span><span class="sxs-lookup"><span data-stu-id="bf76a-248">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="bf76a-249">公式の .NET Core Docker イメージは Microsoft Container Registry (MCR) に公開され、[Microsoft .NET Core の Docker Hub リポジトリ](https://hub.docker.com/_/microsoft-dotnet-core/)で見つけられます。</span><span class="sxs-lookup"><span data-stu-id="bf76a-249">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="bf76a-250">各リポジトリには、.NET (SDK またはランタイム) と自分が使用できる OS のさまざまな組み合わせのイメージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bf76a-250">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="bf76a-251">Microsoft は、特定のシナリオに対応したイメージを用意しています。</span><span class="sxs-lookup"><span data-stu-id="bf76a-251">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="bf76a-252">たとえば、[ASP.NET Core リポジトリ](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/)には、運用環境での ASP.NET Core アプリの実行用にビルドされたイメージが用意されています。</span><span class="sxs-lookup"><span data-stu-id="bf76a-252">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="bf76a-253">Docker コンテナー内で .NET Core を使用する方法の詳細については、「[.NET および Docker の概要](../docker/introduction.md)」と[サンプル](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf76a-253">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="bf76a-254">次の手順</span><span class="sxs-lookup"><span data-stu-id="bf76a-254">Next steps</span></span>

- <span data-ttu-id="bf76a-255">[.NET Core が既にインストールされているかどうかを確認する方法](how-to-detect-installed-versions.md?pivots=os-macos)。</span><span class="sxs-lookup"><span data-stu-id="bf76a-255">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md?pivots=os-macos).</span></span>
- <span data-ttu-id="bf76a-256">[macOS Catalina の公証に対応する](macos-notarization-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="bf76a-256">[Working with macOS Catalina notarization](macos-notarization-issues.md).</span></span>
- <span data-ttu-id="bf76a-257">[チュートリアル: macOS での作業を始める](../tutorials/using-on-mac-vs.md).</span><span class="sxs-lookup"><span data-stu-id="bf76a-257">[Tutorial: Get started on macOS](../tutorials/using-on-mac-vs.md).</span></span>
- <span data-ttu-id="bf76a-258">[チュートリアル: Visual Studio Code を使用して新しいアプリを作成する](../tutorials/with-visual-studio-code.md)。</span><span class="sxs-lookup"><span data-stu-id="bf76a-258">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="bf76a-259">[チュートリアル: NET Core アプリをコンテナー化する](../docker/build-container.md)。</span><span class="sxs-lookup"><span data-stu-id="bf76a-259">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

[release-notes-21]: https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md
[release-notes-31]: https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md
[release-notes-50]: https://github.com/dotnet/core/blob/master/release-notes/5.0/5.0-supported-os.md
[release-notes-20]: https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md
[release-notes-22]: https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md
[release-notes-30]: https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md
