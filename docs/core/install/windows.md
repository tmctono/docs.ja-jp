---
title: Windows に .NET Core をインストールする
description: .NET Core をインストールできる Windows のバージョンについて説明します。
author: adegeo
ms.author: adegeo
ms.date: 06/22/2020
ms.openlocfilehash: e26494de7e9246b241cb965d8d735a781aab5478
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85804456"
---
# <a name="install-net-core-on-windows"></a><span data-ttu-id="517e4-103">Windows に .NET Core をインストールする</span><span class="sxs-lookup"><span data-stu-id="517e4-103">Install .NET Core on Windows</span></span>

> [!div class="op_single_selector"]
>
> - [Windows へのインストール](windows.md)
> - [macOS へのインストール](macos.md)
> - [Linux へのインストール](linux.md)

<span data-ttu-id="517e4-107">この記事では、Windows に .NET Core をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="517e4-107">In this article, you'll learn how to install .NET Core on Windows.</span></span> <span data-ttu-id="517e4-108">.NET Core は、ランタイムと SDK で構成されています。</span><span class="sxs-lookup"><span data-stu-id="517e4-108">.NET Core is made up of the runtime and the SDK.</span></span> <span data-ttu-id="517e4-109">ランタイムは .NET Core アプリを実行するために使用され、アプリに含まれている場合と含まれていない場合があります。</span><span class="sxs-lookup"><span data-stu-id="517e4-109">The runtime is used to run a .NET Core app and may or may not be included with the app.</span></span> <span data-ttu-id="517e4-110">SDK は、.NET Core アプリとライブラリの作成に使用されます。</span><span class="sxs-lookup"><span data-stu-id="517e4-110">The SDK is used to create .NET Core apps and libraries.</span></span> <span data-ttu-id="517e4-111">.NET Core ランタイムは、常に SDK と共にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="517e4-111">The .NET Core runtime is always installed with the SDK.</span></span>

<span data-ttu-id="517e4-112">.NET Core の最新バージョンは 3.1 です。</span><span class="sxs-lookup"><span data-stu-id="517e4-112">The latest version of .NET Core is 3.1.</span></span>

[<span data-ttu-id="517e4-113">.NET Core をダウンロードする。</span><span class="sxs-lookup"><span data-stu-id="517e4-113">Download .NET Core.</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="supported-releases"></a><span data-ttu-id="517e4-114">サポートされているリリース</span><span class="sxs-lookup"><span data-stu-id="517e4-114">Supported releases</span></span>

<span data-ttu-id="517e4-115">次の表に、現在サポートされている .NET Core リリースと、それらがサポートされている Windows のバージョンの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="517e4-115">The following table is a list of currently supported .NET Core releases and the versions of Windows they're supported on.</span></span> <span data-ttu-id="517e4-116">これらのバージョンは、[.NET Core のバージョンがサポート終了](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)するか、[Windows のバージョンの有効期限が切れるまで](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)サポートされます。</span><span class="sxs-lookup"><span data-stu-id="517e4-116">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Windows reaches end-of-life](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

<span data-ttu-id="517e4-117">Windows 10 のバージョンのサービス終了日は、エディションごとに分かれています。</span><span class="sxs-lookup"><span data-stu-id="517e4-117">Windows 10 versions end-of-service dates are segmented by edition.</span></span> <span data-ttu-id="517e4-118">次の表では、**Home**、**Pro**、**Pro Education**、**Pro for Workstations** の各エディションだけが考慮されています。</span><span class="sxs-lookup"><span data-stu-id="517e4-118">Only **Home**, **Pro**, **Pro Education**, and **Pro for Workstations** editions are considered in the following table.</span></span> <span data-ttu-id="517e4-119">具体的な詳細については、「[Windows ライフサイクルのファクト シート](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)」を確認してください。</span><span class="sxs-lookup"><span data-stu-id="517e4-119">Check the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet) for specific details.</span></span>

- <span data-ttu-id="517e4-120">✔️ は、Windows または .NET Core のバージョンがまだサポートされていることを示します。</span><span class="sxs-lookup"><span data-stu-id="517e4-120">A ✔️ indicates that the version of Windows or .NET Core is still supported.</span></span>
- <span data-ttu-id="517e4-121">❌ は、Windows または .NET Core のバージョンがその Windows のリリースではサポートされていないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="517e4-121">A ❌ indicates that the version of Windows or .NET Core isn't supported on that Windows release.</span></span>
- <span data-ttu-id="517e4-122">Windows のバージョンと .NET Core のバージョンの両方に ✔️ が付いている場合、その OS と .NET の組み合わせはサポートされています。</span><span class="sxs-lookup"><span data-stu-id="517e4-122">When both a version of Windows and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="517e4-123">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="517e4-123">Operating System</span></span>                      | <span data-ttu-id="517e4-124">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="517e4-124">.NET Core 2.1</span></span> | <span data-ttu-id="517e4-125">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="517e4-125">.NET Core 3.1</span></span> | <span data-ttu-id="517e4-126">.NET 5 Preview</span><span class="sxs-lookup"><span data-stu-id="517e4-126">.NET 5 Preview</span></span> |
|-----------------------------|---------------|---------------|----------------|
| <span data-ttu-id="517e4-127">✔️ Windows 10 バージョン 2004</span><span class="sxs-lookup"><span data-stu-id="517e4-127">✔️ Windows 10, Version 2004</span></span> | <span data-ttu-id="517e4-128">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="517e4-128">✔️ 2.1</span></span>        | <span data-ttu-id="517e4-129">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="517e4-129">✔️ 3.1</span></span>        | <span data-ttu-id="517e4-130">✔️ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="517e4-130">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="517e4-131">✔️ Windows 10 バージョン 1909</span><span class="sxs-lookup"><span data-stu-id="517e4-131">✔️ Windows 10, Version 1909</span></span> | <span data-ttu-id="517e4-132">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="517e4-132">✔️ 2.1</span></span>        | <span data-ttu-id="517e4-133">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="517e4-133">✔️ 3.1</span></span>        | <span data-ttu-id="517e4-134">✔️ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="517e4-134">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="517e4-135">✔️ Windows 10 バージョン 1903</span><span class="sxs-lookup"><span data-stu-id="517e4-135">✔️ Windows 10, Version 1903</span></span> | <span data-ttu-id="517e4-136">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="517e4-136">✔️ 2.1</span></span>        | <span data-ttu-id="517e4-137">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="517e4-137">✔️ 3.1</span></span>        | <span data-ttu-id="517e4-138">✔️ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="517e4-138">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="517e4-139">✔️ Windows 10 バージョン 1809</span><span class="sxs-lookup"><span data-stu-id="517e4-139">✔️ Windows 10, Version 1809</span></span> | <span data-ttu-id="517e4-140">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="517e4-140">✔️ 2.1</span></span>        | <span data-ttu-id="517e4-141">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="517e4-141">✔️ 3.1</span></span>        | <span data-ttu-id="517e4-142">✔️ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="517e4-142">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="517e4-143">❌ Windows 10 バージョン 1803</span><span class="sxs-lookup"><span data-stu-id="517e4-143">❌ Windows 10, Version 1803</span></span> | <span data-ttu-id="517e4-144">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="517e4-144">✔️ 2.1</span></span>        | <span data-ttu-id="517e4-145">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="517e4-145">❌ 3.1</span></span>        | <span data-ttu-id="517e4-146">❌ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="517e4-146">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="517e4-147">❌ Windows 10 バージョン 1709</span><span class="sxs-lookup"><span data-stu-id="517e4-147">❌ Windows 10, Version 1709</span></span> | <span data-ttu-id="517e4-148">❌ 2.1</span><span class="sxs-lookup"><span data-stu-id="517e4-148">❌ 2.1</span></span>        | <span data-ttu-id="517e4-149">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="517e4-149">❌ 3.1</span></span>        | <span data-ttu-id="517e4-150">❌ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="517e4-150">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="517e4-151">❌ Windows 10 バージョン 1703</span><span class="sxs-lookup"><span data-stu-id="517e4-151">❌ Windows 10, Version 1703</span></span> | <span data-ttu-id="517e4-152">❌ 2.1</span><span class="sxs-lookup"><span data-stu-id="517e4-152">❌ 2.1</span></span>        | <span data-ttu-id="517e4-153">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="517e4-153">❌ 3.1</span></span>        | <span data-ttu-id="517e4-154">❌ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="517e4-154">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="517e4-155">❌ Windows 10 バージョン 1607</span><span class="sxs-lookup"><span data-stu-id="517e4-155">❌ Windows 10, Version 1607</span></span> | <span data-ttu-id="517e4-156">❌ 2.1</span><span class="sxs-lookup"><span data-stu-id="517e4-156">❌ 2.1</span></span>        | <span data-ttu-id="517e4-157">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="517e4-157">❌ 3.1</span></span>        | <span data-ttu-id="517e4-158">❌ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="517e4-158">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="517e4-159">❌ Windows 10 バージョン 1511</span><span class="sxs-lookup"><span data-stu-id="517e4-159">❌ Windows 10, Version 1511</span></span> | <span data-ttu-id="517e4-160">❌ 2.1</span><span class="sxs-lookup"><span data-stu-id="517e4-160">❌ 2.1</span></span>        | <span data-ttu-id="517e4-161">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="517e4-161">❌ 3.1</span></span>        | <span data-ttu-id="517e4-162">❌ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="517e4-162">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="517e4-163">❌ Windows 10 バージョン 1507</span><span class="sxs-lookup"><span data-stu-id="517e4-163">❌ Windows 10, Version 1507</span></span> | <span data-ttu-id="517e4-164">❌ 2.1</span><span class="sxs-lookup"><span data-stu-id="517e4-164">❌ 2.1</span></span>        | <span data-ttu-id="517e4-165">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="517e4-165">❌ 3.1</span></span>        | <span data-ttu-id="517e4-166">❌ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="517e4-166">❌ 5.0 Preview</span></span> |

## <a name="unsupported-releases"></a><span data-ttu-id="517e4-167">サポートされていないリリース</span><span class="sxs-lookup"><span data-stu-id="517e4-167">Unsupported releases</span></span>

<span data-ttu-id="517e4-168">次のバージョンの .NET Core は ❌ サポート対象外となりました。</span><span class="sxs-lookup"><span data-stu-id="517e4-168">The following versions of .NET Core are ❌ no longer supported.</span></span> <span data-ttu-id="517e4-169">これらのダウンロードは、まだ公開されています。</span><span class="sxs-lookup"><span data-stu-id="517e4-169">The downloads for these still remain published:</span></span>

- <span data-ttu-id="517e4-170">3.0</span><span class="sxs-lookup"><span data-stu-id="517e4-170">3.0</span></span>
- <span data-ttu-id="517e4-171">2.2</span><span class="sxs-lookup"><span data-stu-id="517e4-171">2.2</span></span>
- <span data-ttu-id="517e4-172">2.0</span><span class="sxs-lookup"><span data-stu-id="517e4-172">2.0</span></span>

## <a name="runtime-information"></a><span data-ttu-id="517e4-173">ランタイムに関する情報</span><span class="sxs-lookup"><span data-stu-id="517e4-173">Runtime information</span></span>

<span data-ttu-id="517e4-174">ランタイムは、.NET Core で作成されたアプリを実行するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="517e4-174">The runtime is used to run apps created with .NET Core.</span></span> <span data-ttu-id="517e4-175">アプリの作成者は、アプリを公開するとき、アプリにランタイムを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="517e4-175">When an app author publishes an app, they can include the runtime with their app.</span></span> <span data-ttu-id="517e4-176">ランタイムが含まれていない場合は、ユーザーがランタイムをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="517e4-176">If they don't include the runtime, it's up to the user to install the runtime.</span></span>

<span data-ttu-id="517e4-177">Windows には、3 つの異なるランタイムをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="517e4-177">There are three different runtimes you can install on Windows:</span></span>

<span data-ttu-id="517e4-178">*ASP.NET Core ランタイム*</span><span class="sxs-lookup"><span data-stu-id="517e4-178">*ASP.NET Core runtime*</span></span>\
<span data-ttu-id="517e4-179">ASP.NET Core アプリを実行します。</span><span class="sxs-lookup"><span data-stu-id="517e4-179">Runs ASP.NET Core apps.</span></span> <span data-ttu-id="517e4-180">.NET Core ランタイムが含まれます。</span><span class="sxs-lookup"><span data-stu-id="517e4-180">Includes the .NET Core runtime.</span></span>

<span data-ttu-id="517e4-181">*Desktop ランタイム*</span><span class="sxs-lookup"><span data-stu-id="517e4-181">*Desktop runtime*</span></span>\
<span data-ttu-id="517e4-182">Windows 用の .NET Core WPF デスクトップ アプリおよび .NET Core Windows フォーム デスクトップ アプリを実行します。</span><span class="sxs-lookup"><span data-stu-id="517e4-182">Runs .NET Core WPF and .NET Core Windows Forms desktop apps for Windows.</span></span> <span data-ttu-id="517e4-183">.NET Core ランタイムが含まれます。</span><span class="sxs-lookup"><span data-stu-id="517e4-183">Includes the .NET Core runtime.</span></span>

<span data-ttu-id="517e4-184">*.NET Core ランタイム*</span><span class="sxs-lookup"><span data-stu-id="517e4-184">*.NET Core runtime*</span></span>\
<span data-ttu-id="517e4-185">このランタイムは最も単純なランタイムであり、他のランタイムは含まれていません。</span><span class="sxs-lookup"><span data-stu-id="517e4-185">This runtime is the simplest runtime and doesn't include any other runtime.</span></span> <span data-ttu-id="517e4-186">.NET Core アプリとの互換性を最善にするには、"*ASP.NET Core ランタイム*" と "*Desktop ランタイム*" の両方をインストールすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="517e4-186">It's highly recommended that you install both *ASP.NET Core runtime* and *Desktop runtime* for the best compatibility with .NET Core apps.</span></span>

[<span data-ttu-id="517e4-187">.NET Core ランタイムをダウンロードする。</span><span class="sxs-lookup"><span data-stu-id="517e4-187">Download .NET Core Runtime.</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="sdk-information"></a><span data-ttu-id="517e4-188">SDK に関する情報</span><span class="sxs-lookup"><span data-stu-id="517e4-188">SDK information</span></span>

<span data-ttu-id="517e4-189">SDK は、.NET Core アプリとライブラリを作成して公開するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="517e4-189">The SDK is used to build and publish .NET Core apps and libraries.</span></span> <span data-ttu-id="517e4-190">SDK のインストールには、次の 3 つの[ランタイム](#runtime-information)が含まれます: ASP.NET Core、Desktop、.NET Core。</span><span class="sxs-lookup"><span data-stu-id="517e4-190">Installing the SDK includes all three [runtimes](#runtime-information): ASP.NET Core, Desktop, and .NET Core.</span></span>

[<span data-ttu-id="517e4-191">.NET Core SDK をダウンロードする。</span><span class="sxs-lookup"><span data-stu-id="517e4-191">Download .NET Core SDK.</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="dependencies"></a><span data-ttu-id="517e4-192">依存関係</span><span class="sxs-lookup"><span data-stu-id="517e4-192">Dependencies</span></span>

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31"></a>[<span data-ttu-id="517e4-193">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="517e4-193">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="517e4-194">.NET Core 3.1 では以下の Windows のバージョンがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="517e4-194">The following Windows versions are supported with .NET Core 3.1:</span></span>

> [!NOTE]
> <span data-ttu-id="517e4-195">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="517e4-195">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="517e4-196">OS</span><span class="sxs-lookup"><span data-stu-id="517e4-196">OS</span></span>                            | <span data-ttu-id="517e4-197">バージョン</span><span class="sxs-lookup"><span data-stu-id="517e4-197">Version</span></span>                        | <span data-ttu-id="517e4-198">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="517e4-198">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="517e4-199">Windows クライアント</span><span class="sxs-lookup"><span data-stu-id="517e4-199">Windows Client</span></span>                | <span data-ttu-id="517e4-200">8.1</span><span class="sxs-lookup"><span data-stu-id="517e4-200">8.1</span></span>                            | <span data-ttu-id="517e4-201">x64、x86</span><span class="sxs-lookup"><span data-stu-id="517e4-201">x64, x86</span></span>        |
| <span data-ttu-id="517e4-202">Windows 10 クライアント</span><span class="sxs-lookup"><span data-stu-id="517e4-202">Windows 10 Client</span></span>             | <span data-ttu-id="517e4-203">バージョン 1609+</span><span class="sxs-lookup"><span data-stu-id="517e4-203">Version 1609+</span></span>                  | <span data-ttu-id="517e4-204">x64、x86</span><span class="sxs-lookup"><span data-stu-id="517e4-204">x64, x86</span></span>        |
| <span data-ttu-id="517e4-205">Windows Server</span><span class="sxs-lookup"><span data-stu-id="517e4-205">Windows Server</span></span>                | <span data-ttu-id="517e4-206">2012 R2+</span><span class="sxs-lookup"><span data-stu-id="517e4-206">2012 R2+</span></span>                       | <span data-ttu-id="517e4-207">x64、x86</span><span class="sxs-lookup"><span data-stu-id="517e4-207">x64, x86</span></span>        |
| <span data-ttu-id="517e4-208">Nano Server</span><span class="sxs-lookup"><span data-stu-id="517e4-208">Nano Server</span></span>                   | <span data-ttu-id="517e4-209">バージョン 1803+</span><span class="sxs-lookup"><span data-stu-id="517e4-209">Version 1803+</span></span>                  | <span data-ttu-id="517e4-210">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="517e4-210">x64, ARM32</span></span>      |

<span data-ttu-id="517e4-211">.NET Core 3.1 でサポートされているオペレーティング システム、ディストリビューション、ライフサイクル ポリシーの詳細については、「[.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md)」(.NET Core 3.1 でサポートされている OS バージョン) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="517e4-211">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="517e4-212">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="517e4-212">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="517e4-213">" *.NET Core 3.0 は現在サポートされていません。詳細については、「[.NET Core のサポート ポリシー](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)」をご覧ください。* "</span><span class="sxs-lookup"><span data-stu-id="517e4-213">*.NET Core 3.0 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="517e4-214">.NET Core 3.0 では以下の Windows のバージョンがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="517e4-214">The following Windows versions are supported with .NET Core 3.0:</span></span>

> [!NOTE]
> <span data-ttu-id="517e4-215">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="517e4-215">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="517e4-216">OS</span><span class="sxs-lookup"><span data-stu-id="517e4-216">OS</span></span>                            | <span data-ttu-id="517e4-217">バージョン</span><span class="sxs-lookup"><span data-stu-id="517e4-217">Version</span></span>                        | <span data-ttu-id="517e4-218">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="517e4-218">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="517e4-219">Windows クライアント</span><span class="sxs-lookup"><span data-stu-id="517e4-219">Windows Client</span></span>                | <span data-ttu-id="517e4-220">7 SP1+、8.1</span><span class="sxs-lookup"><span data-stu-id="517e4-220">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="517e4-221">x64、x86</span><span class="sxs-lookup"><span data-stu-id="517e4-221">x64, x86</span></span>        |
| <span data-ttu-id="517e4-222">Windows 10 クライアント</span><span class="sxs-lookup"><span data-stu-id="517e4-222">Windows 10 Client</span></span>             | <span data-ttu-id="517e4-223">バージョン 1607+</span><span class="sxs-lookup"><span data-stu-id="517e4-223">Version 1607+</span></span>                  | <span data-ttu-id="517e4-224">x64、x86</span><span class="sxs-lookup"><span data-stu-id="517e4-224">x64, x86</span></span>        |
| <span data-ttu-id="517e4-225">Windows Server</span><span class="sxs-lookup"><span data-stu-id="517e4-225">Windows Server</span></span>                | <span data-ttu-id="517e4-226">2012 R2+</span><span class="sxs-lookup"><span data-stu-id="517e4-226">2012 R2+</span></span>                       | <span data-ttu-id="517e4-227">x64、x86</span><span class="sxs-lookup"><span data-stu-id="517e4-227">x64, x86</span></span>        |
| <span data-ttu-id="517e4-228">Nano Server</span><span class="sxs-lookup"><span data-stu-id="517e4-228">Nano Server</span></span>                   | <span data-ttu-id="517e4-229">バージョン 1803+</span><span class="sxs-lookup"><span data-stu-id="517e4-229">Version 1803+</span></span>                  | <span data-ttu-id="517e4-230">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="517e4-230">x64, ARM32</span></span>      |

<span data-ttu-id="517e4-231">.NET Core 3.0 でサポートされているオペレーティング システム、ディストリビューション、ライフサイクル ポリシーの詳細については、「[.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)」(.NET Core 3.0 でサポートされている OS バージョン) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="517e4-231">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="517e4-232">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="517e4-232">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="517e4-233">" *.NET Core 2.2 は現在サポートされていません。詳細については、「[.NET Core のサポート ポリシー](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)」をご覧ください。* "</span><span class="sxs-lookup"><span data-stu-id="517e4-233">*.NET Core 2.2 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="517e4-234">.NET Core 2.2 では以下の Windows のバージョンがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="517e4-234">The following Windows versions are supported with .NET Core 2.2:</span></span>

> [!NOTE]
> <span data-ttu-id="517e4-235">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="517e4-235">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="517e4-236">OS</span><span class="sxs-lookup"><span data-stu-id="517e4-236">OS</span></span>                            | <span data-ttu-id="517e4-237">バージョン</span><span class="sxs-lookup"><span data-stu-id="517e4-237">Version</span></span>                        | <span data-ttu-id="517e4-238">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="517e4-238">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="517e4-239">Windows クライアント</span><span class="sxs-lookup"><span data-stu-id="517e4-239">Windows Client</span></span>                | <span data-ttu-id="517e4-240">7 SP1+、8.1</span><span class="sxs-lookup"><span data-stu-id="517e4-240">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="517e4-241">x64、x86</span><span class="sxs-lookup"><span data-stu-id="517e4-241">x64, x86</span></span>        |
| <span data-ttu-id="517e4-242">Windows 10 クライアント</span><span class="sxs-lookup"><span data-stu-id="517e4-242">Windows 10 Client</span></span>             | <span data-ttu-id="517e4-243">バージョン 1607+</span><span class="sxs-lookup"><span data-stu-id="517e4-243">Version 1607+</span></span>                  | <span data-ttu-id="517e4-244">x64、x86</span><span class="sxs-lookup"><span data-stu-id="517e4-244">x64, x86</span></span>        |
| <span data-ttu-id="517e4-245">Windows Server</span><span class="sxs-lookup"><span data-stu-id="517e4-245">Windows Server</span></span>                | <span data-ttu-id="517e4-246">2008 R2 SP1+</span><span class="sxs-lookup"><span data-stu-id="517e4-246">2008 R2 SP1+</span></span>                   | <span data-ttu-id="517e4-247">x64、x86</span><span class="sxs-lookup"><span data-stu-id="517e4-247">x64, x86</span></span>        |
| <span data-ttu-id="517e4-248">Nano Server</span><span class="sxs-lookup"><span data-stu-id="517e4-248">Nano Server</span></span>                   | <span data-ttu-id="517e4-249">バージョン 1803+</span><span class="sxs-lookup"><span data-stu-id="517e4-249">Version 1803+</span></span>                   | <span data-ttu-id="517e4-250">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="517e4-250">x64, ARM32</span></span>      |

<span data-ttu-id="517e4-251">.NET Core 2.2 でサポートされているオペレーティング システム、ディストリビューション、ライフサイクル ポリシーの詳細については、「[.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)」(.NET Core 2.2 でサポートされている OS バージョン) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="517e4-251">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="517e4-252">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="517e4-252">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="517e4-253">.NET Core 2.1 では以下の Windows のバージョンがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="517e4-253">The following Windows versions are supported with .NET Core 2.1:</span></span>

> [!NOTE]
> <span data-ttu-id="517e4-254">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="517e4-254">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="517e4-255">OS</span><span class="sxs-lookup"><span data-stu-id="517e4-255">OS</span></span>                            | <span data-ttu-id="517e4-256">バージョン</span><span class="sxs-lookup"><span data-stu-id="517e4-256">Version</span></span>                        | <span data-ttu-id="517e4-257">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="517e4-257">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="517e4-258">Windows クライアント</span><span class="sxs-lookup"><span data-stu-id="517e4-258">Windows Client</span></span>                | <span data-ttu-id="517e4-259">7 SP1+、8.1</span><span class="sxs-lookup"><span data-stu-id="517e4-259">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="517e4-260">x64、x86</span><span class="sxs-lookup"><span data-stu-id="517e4-260">x64, x86</span></span>        |
| <span data-ttu-id="517e4-261">Windows 10 クライアント</span><span class="sxs-lookup"><span data-stu-id="517e4-261">Windows 10 Client</span></span>             | <span data-ttu-id="517e4-262">バージョン 1607+</span><span class="sxs-lookup"><span data-stu-id="517e4-262">Version 1607+</span></span>                  | <span data-ttu-id="517e4-263">x64、x86</span><span class="sxs-lookup"><span data-stu-id="517e4-263">x64, x86</span></span>        |
| <span data-ttu-id="517e4-264">Windows Server</span><span class="sxs-lookup"><span data-stu-id="517e4-264">Windows Server</span></span>                | <span data-ttu-id="517e4-265">2008 R2 SP1+</span><span class="sxs-lookup"><span data-stu-id="517e4-265">2008 R2 SP1+</span></span>                   | <span data-ttu-id="517e4-266">x64、x86</span><span class="sxs-lookup"><span data-stu-id="517e4-266">x64, x86</span></span>        |
| <span data-ttu-id="517e4-267">Nano Server</span><span class="sxs-lookup"><span data-stu-id="517e4-267">Nano Server</span></span>                   | <span data-ttu-id="517e4-268">バージョン 1803+</span><span class="sxs-lookup"><span data-stu-id="517e4-268">Version 1803+</span></span>                  | <span data-ttu-id="517e4-269">x64、</span><span class="sxs-lookup"><span data-stu-id="517e4-269">x64,</span></span>            |

<span data-ttu-id="517e4-270">.NET Core 2.1 でサポートされているオペレーティング システム、ディストリビューション、ライフサイクル ポリシーの詳細については、「[.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)」(.NET Core 2.1 でサポートされている OS バージョン) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="517e4-270">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2--server-2012-r2"></a><a name="additional-deps"></a> <span data-ttu-id="517e4-271">Windows 7 / Vista / 8.1 / Server 2008 R2 / Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="517e4-271">Windows 7 / Vista / 8.1 / Server 2008 R2 / Server 2012 R2</span></span>

<span data-ttu-id="517e4-272">次の Windows のバージョンに .NET SDK またはランタイムをインストールする場合は、追加の依存関係が必要です。</span><span class="sxs-lookup"><span data-stu-id="517e4-272">Additional dependencies are required if you're installing the .NET SDK or runtime on the following Windows versions:</span></span>

- <span data-ttu-id="517e4-273">❌ Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="517e4-273">❌ Windows 7 SP1</span></span>
- <span data-ttu-id="517e4-274">❌ Windows Vista SP 2</span><span class="sxs-lookup"><span data-stu-id="517e4-274">❌ Windows Vista SP 2</span></span>
- <span data-ttu-id="517e4-275">✔️ Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="517e4-275">✔️ Windows 8.1</span></span>
- <span data-ttu-id="517e4-276">✔️ Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="517e4-276">✔️ Windows Server 2008 R2</span></span>
- <span data-ttu-id="517e4-277">✔️ Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="517e4-277">✔️ Windows Server 2012 R2</span></span>

<span data-ttu-id="517e4-278">以下をインストールします。</span><span class="sxs-lookup"><span data-stu-id="517e4-278">Install the following:</span></span>

- <span data-ttu-id="517e4-279">[Microsoft Visual C++ 2015 再頒布可能パッケージ Update 3](https://www.microsoft.com/download/details.aspx?id=52685)。</span><span class="sxs-lookup"><span data-stu-id="517e4-279">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span></span>
- [<span data-ttu-id="517e4-280">KB2533623</span><span class="sxs-lookup"><span data-stu-id="517e4-280">KB2533623</span></span>](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

<span data-ttu-id="517e4-281">上記の要件は、次のいずれかのエラーが発生した場合にも必要です。</span><span class="sxs-lookup"><span data-stu-id="517e4-281">The requirements above are also required if you come across one of the following errors:</span></span>

> <span data-ttu-id="517e4-282">お使いのコンピューターに *api-ms-win-crt-runtime-l1-1-0.dll* が見つからず、プログラムを開始できない。</span><span class="sxs-lookup"><span data-stu-id="517e4-282">The program can't start because *api-ms-win-crt-runtime-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="517e4-283">この問題を解決するには、プログラムを再インストールしてください。</span><span class="sxs-lookup"><span data-stu-id="517e4-283">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="517e4-284">\- または</span><span class="sxs-lookup"><span data-stu-id="517e4-284">\- or -</span></span>
>
> <span data-ttu-id="517e4-285">お使いのコンピューターに *api-ms-win-cor-timezone-l1-1-0.dll* が見つからず、プログラムを開始できない。</span><span class="sxs-lookup"><span data-stu-id="517e4-285">The program can't start because *api-ms-win-cor-timezone-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="517e4-286">この問題を解決するには、プログラムを再インストールしてください。</span><span class="sxs-lookup"><span data-stu-id="517e4-286">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="517e4-287">\- または</span><span class="sxs-lookup"><span data-stu-id="517e4-287">\- or -</span></span>
>
> <span data-ttu-id="517e4-288">ライブラリ *hostfxr.dll* は見つかったが、その *C:\\\<path_to_app>\\hostfxr.dll* からの読み込みに失敗した。</span><span class="sxs-lookup"><span data-stu-id="517e4-288">The library *hostfxr.dll* was found, but loading it from *C:\\\<path_to_app>\\hostfxr.dll* failed.</span></span>

## <a name="install-with-powershell-automation"></a><span data-ttu-id="517e4-289">PowerShell オートメーションを使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="517e4-289">Install with PowerShell automation</span></span>

<span data-ttu-id="517e4-290">[dotnet-install スクリプト](../tools/dotnet-install-script.md)は、ランタイムの CI 自動化および管理者以外によるインストールに使用されます。</span><span class="sxs-lookup"><span data-stu-id="517e4-290">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for CI automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="517e4-291">スクリプトは、[dotnet-install スクリプト参照ページ](../tools/dotnet-install-script.md)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="517e4-291">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="517e4-292">スクリプトでは、既定で最新の [長期サポート (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) バージョン (.NET Core 3.1) がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="517e4-292">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="517e4-293">`Channel` スイッチを指定することで、特定のリリースを選択できます。</span><span class="sxs-lookup"><span data-stu-id="517e4-293">You can choose a specific release by specifying the `Channel` switch.</span></span> <span data-ttu-id="517e4-294">ランタイムをインストールするには、`Runtime` スイッチを含めます。</span><span class="sxs-lookup"><span data-stu-id="517e4-294">Include the `Runtime` switch to install a runtime.</span></span> <span data-ttu-id="517e4-295">それ以外の場合は、スクリプトによって [SDK](sdk.md) がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="517e4-295">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```powershell
dotnet-install.ps1 -Channel 3.1 -Runtime aspnetcore
```

<span data-ttu-id="517e4-296">`-Runtime` スイッチを省略して SDK をインストールします。</span><span class="sxs-lookup"><span data-stu-id="517e4-296">Install the SDK by omitting the `-Runtime` switch.</span></span> <span data-ttu-id="517e4-297">この例では、`-Channel` スイッチが `Current` に設定されているため、サポートされている最新バージョンがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="517e4-297">The `-Channel` switch is set in this example to `Current`, which installs the latest supported version.</span></span>

```powershell
dotnet-install.ps1 -Channel Current
```

## <a name="install-with-visual-studio"></a><span data-ttu-id="517e4-298">Visual Studio を使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="517e4-298">Install with Visual Studio</span></span>

<span data-ttu-id="517e4-299">次の表では、Visual Studio を使用して .NET Core アプリを開発している場合に、ターゲットの .NET Core SDK バージョンに基づいて最低限必要な Visual Studio のバージョンを説明します。</span><span class="sxs-lookup"><span data-stu-id="517e4-299">If you're using Visual Studio to develop .NET Core apps, the following table describes the minimum required version of Visual Studio based on the target .NET Core SDK version.</span></span>

| <span data-ttu-id="517e4-300">.NET Core SDK のバージョン</span><span class="sxs-lookup"><span data-stu-id="517e4-300">.NET Core SDK version</span></span> | <span data-ttu-id="517e4-301">Visual Studio のバージョン</span><span class="sxs-lookup"><span data-stu-id="517e4-301">Visual Studio version</span></span>                      |
| --------------------- | ------------------------------------------ |
| <span data-ttu-id="517e4-302">3.1</span><span class="sxs-lookup"><span data-stu-id="517e4-302">3.1</span></span>                   | <span data-ttu-id="517e4-303">Visual Studio 2019 バージョン 16.4 以降。</span><span class="sxs-lookup"><span data-stu-id="517e4-303">Visual Studio 2019 version 16.4 or higher.</span></span> |
| <span data-ttu-id="517e4-304">3.0</span><span class="sxs-lookup"><span data-stu-id="517e4-304">3.0</span></span>                   | <span data-ttu-id="517e4-305">Visual Studio 2019 バージョン 16.3 以降。</span><span class="sxs-lookup"><span data-stu-id="517e4-305">Visual Studio 2019 version 16.3 or higher.</span></span> |
| <span data-ttu-id="517e4-306">2.2</span><span class="sxs-lookup"><span data-stu-id="517e4-306">2.2</span></span>                   | <span data-ttu-id="517e4-307">Visual Studio 2017 バージョン 15.9 以降。</span><span class="sxs-lookup"><span data-stu-id="517e4-307">Visual Studio 2017 version 15.9 or higher.</span></span> |
| <span data-ttu-id="517e4-308">2.1</span><span class="sxs-lookup"><span data-stu-id="517e4-308">2.1</span></span>                   | <span data-ttu-id="517e4-309">Visual Studio 2017 バージョン 15.7 以降。</span><span class="sxs-lookup"><span data-stu-id="517e4-309">Visual Studio 2017 version 15.7 or higher.</span></span> |

<span data-ttu-id="517e4-310">Visual Studio を既にインストールしてある場合は、次の手順でバージョンを確認できます。</span><span class="sxs-lookup"><span data-stu-id="517e4-310">If you already have Visual Studio installed, you can check your version with the following steps.</span></span>

01. <span data-ttu-id="517e4-311">Visual Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="517e4-311">Open Visual Studio.</span></span>
01. <span data-ttu-id="517e4-312">**[ヘルプ]**  >  **[Microsoft Visual Studio のバージョン情報]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="517e4-312">Select **Help** > **About Microsoft Visual Studio**.</span></span>
01. <span data-ttu-id="517e4-313">**[バージョン情報]** ダイアログで、バージョン番号を確認します。</span><span class="sxs-lookup"><span data-stu-id="517e4-313">Read the version number from the **About** dialog.</span></span>

<span data-ttu-id="517e4-314">Visual Studio では、最新の .NET Core SDK とランタイムをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="517e4-314">Visual Studio can install the latest .NET Core SDK and runtime.</span></span>

- <span data-ttu-id="517e4-315">[Visual Studio をダウンロードします](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)。</span><span class="sxs-lookup"><span data-stu-id="517e4-315">[Download Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019).</span></span>

### <a name="select-a-workload"></a><span data-ttu-id="517e4-316">ワークロードを選択する</span><span class="sxs-lookup"><span data-stu-id="517e4-316">Select a workload</span></span>

<span data-ttu-id="517e4-317">Visual Studio をインストールまたは変更するときは、ビルドするアプリケーションの種類に応じて、次の 1 つ以上のワークロードを選択します。</span><span class="sxs-lookup"><span data-stu-id="517e4-317">When installing or modifying Visual Studio, select one or more of the following workloads, depending on the kind of application you're building:</span></span>

- <span data-ttu-id="517e4-318">**[他のツールセット]** セクションの **[.NET Core クロスプラットフォームの開発]** ワークロード。</span><span class="sxs-lookup"><span data-stu-id="517e4-318">The **.NET Core cross-platform development** workload in the **Other Toolsets** section.</span></span>
- <span data-ttu-id="517e4-319">**[Web クラウド]** セクションの **[ASP.NET と Web 開発]** ワークロード。</span><span class="sxs-lookup"><span data-stu-id="517e4-319">The **ASP.NET and web development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="517e4-320">**[Web クラウド]** セクションの **[Azure の開発]** ワークロード。</span><span class="sxs-lookup"><span data-stu-id="517e4-320">The **Azure development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="517e4-321">**[デスクトップとモバイル]** セクションの **[.NET デスクトップ開発]** ワークロード。</span><span class="sxs-lookup"><span data-stu-id="517e4-321">The **.NET desktop development** workload in the **Desktop & Mobile** section.</span></span>

<span data-ttu-id="517e4-322">[![Windows Visual Studio 2019 と .NET Core ワークロード](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="517e4-322">[![Windows Visual Studio 2019 with .NET Core workload](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span></span>

## <a name="install-alongside-visual-studio-code"></a><span data-ttu-id="517e4-323">Visual Studio Code と共にインストールする</span><span class="sxs-lookup"><span data-stu-id="517e4-323">Install alongside Visual Studio Code</span></span>

<span data-ttu-id="517e4-324">Visual Studio Code は、デスクトップ上で動作する強力で軽量なソース コード エディターです。</span><span class="sxs-lookup"><span data-stu-id="517e4-324">Visual Studio Code is a powerful and lightweight source code editor that runs on your desktop.</span></span> <span data-ttu-id="517e4-325">Visual Studio Code は、Windows、macOS、Linux で利用できます。</span><span class="sxs-lookup"><span data-stu-id="517e4-325">Visual Studio Code is available for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="517e4-326">Visual Studio Code には、Visual Studio のような自動化された .NET Core インストーラーは付属していませんが、.NET Core のサポートを簡単に追加できます。</span><span class="sxs-lookup"><span data-stu-id="517e4-326">While Visual Studio Code doesn't come with an automated .NET Core installer like Visual Studio does, adding .NET Core support is simple.</span></span>

01. <span data-ttu-id="517e4-327">[Visual Studio Code をダウンロードしてインストールします](https://code.visualstudio.com/Download)。</span><span class="sxs-lookup"><span data-stu-id="517e4-327">[Download and install Visual Studio Code](https://code.visualstudio.com/Download).</span></span>
01. <span data-ttu-id="517e4-328">[.NET Core SDK をダウンロードしてインストールします](https://dotnet.microsoft.com/download/dotnet-core)。</span><span class="sxs-lookup"><span data-stu-id="517e4-328">[Download and install the .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core).</span></span>
01. <span data-ttu-id="517e4-329">[Visual Studio Code マーケットプレースから C# 拡張機能をインストールします](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)。</span><span class="sxs-lookup"><span data-stu-id="517e4-329">[Install the C# extension from the Visual Studio Code marketplace](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="517e4-330">手動でダウンロードしてインストールする</span><span class="sxs-lookup"><span data-stu-id="517e4-330">Download and manually install</span></span>

<span data-ttu-id="517e4-331">.NET Core 用 Windows インストーラーの代わりに、SDK またはランタイムをダウンロードして手動でインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="517e4-331">As an alternative to the Windows installers for .NET Core, you can download and manually install the SDK or runtime.</span></span> <span data-ttu-id="517e4-332">手動インストールは、通常、継続的インテグレーション テストの一環として実行されます。</span><span class="sxs-lookup"><span data-stu-id="517e4-332">Manual install is usually performed as part of continuous integration testing.</span></span> <span data-ttu-id="517e4-333">開発者またはユーザーの場合、通常は[インストーラー](https://dotnet.microsoft.com/download/dotnet-core)を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="517e4-333">For a developer or user, it's generally better to use an [installer](https://dotnet.microsoft.com/download/dotnet-core).</span></span>

<span data-ttu-id="517e4-334">.NET Core SDK と .NET Core ランタイムはどちらも、ダウンロード後に手動でインストールできます。</span><span class="sxs-lookup"><span data-stu-id="517e4-334">Both .NET Core SDK and .NET Core Runtime can be manually installed after they've been downloaded.</span></span> <span data-ttu-id="517e4-335">.NET Core SDK をインストールする場合、対応するランタイムをインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="517e4-335">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="517e4-336">まず、次のいずれかのサイトから SDK またはランタイムのバイナリ リリースをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="517e4-336">First, download a binary release for either the SDK or the runtime from one of the following sites:</span></span>

- <span data-ttu-id="517e4-337">✔️ [.NET 5.0 preview のダウンロード](https://dotnet.microsoft.com/download/dotnet/5.0)</span><span class="sxs-lookup"><span data-stu-id="517e4-337">✔️ [.NET 5.0 preview downloads](https://dotnet.microsoft.com/download/dotnet/5.0)</span></span>
- <span data-ttu-id="517e4-338">✔️ [.NET Core 3.1 のダウンロード](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span><span class="sxs-lookup"><span data-stu-id="517e4-338">✔️ [.NET Core 3.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span></span>
- <span data-ttu-id="517e4-339">✔️ [.NET Core 2.1 のダウンロード](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span><span class="sxs-lookup"><span data-stu-id="517e4-339">✔️ [.NET Core 2.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span></span>
- [<span data-ttu-id="517e4-340">すべての .NET Core のダウンロード</span><span class="sxs-lookup"><span data-stu-id="517e4-340">All .NET Core downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

<span data-ttu-id="517e4-341">.NET を抽出するためのディレクトリを作成します (`%USERPROFILE%\dotnet` など)。</span><span class="sxs-lookup"><span data-stu-id="517e4-341">Create a directory to extract .NET to, for example `%USERPROFILE%\dotnet`.</span></span> <span data-ttu-id="517e4-342">次に、ダウンロードした zip ファイルをそのディレクトリに抽出します。</span><span class="sxs-lookup"><span data-stu-id="517e4-342">Then, extract the downloaded zip file into that directory.</span></span>

<span data-ttu-id="517e4-343">既定では、.NET Core CLI コマンドおよびアプリでは、この方法でインストールされた .NET Core は使用されません。使用することを明示的に選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="517e4-343">By default, .NET Core CLI commands and apps won't use .NET Core installed in this way and you must explicitly choose to use it.</span></span> <span data-ttu-id="517e4-344">これを行うには、アプリケーションの起動に使用する環境変数を変更します。</span><span class="sxs-lookup"><span data-stu-id="517e4-344">To do so, change the environment variables with which an application is started:</span></span>

```console
set DOTNET_ROOT=%USERPROFILE%\dotnet
set PATH=%USERPROFILE%\dotnet;%PATH%
set DOTNET_MULTILEVEL_LOOKUP=0
```

<span data-ttu-id="517e4-345">この方法では、複数のバージョンを別々の場所にインストールして、その場所を参照する環境変数を使ってアプリケーションを実行することで、アプリケーションによって使用されるインストール場所を明示的に選択できます。</span><span class="sxs-lookup"><span data-stu-id="517e4-345">This approach lets you install multiple versions into separate locations, then explicitly choose which install location an application should use by running the application with environment variables pointing at that location.</span></span>

<span data-ttu-id="517e4-346">`DOTNET_MULTILEVEL_LOOKUP` が `0` に設定されている場合、.NET Core ではグローバルにインストールされている .NET Core のバージョンは無視されます。</span><span class="sxs-lookup"><span data-stu-id="517e4-346">When `DOTNET_MULTILEVEL_LOOKUP` is set to `0`, .NET Core ignores any globally installed .NET Core version.</span></span> <span data-ttu-id="517e4-347">.NET Core で、アプリケーションを実行するための最適なフレームワークを選択するときに、既定のグローバル インストールの場所が考慮されるようにするには、その環境設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="517e4-347">Remove that environment setting to let .NET Core consider the default global install location when selecting the best framework for running the application.</span></span> <span data-ttu-id="517e4-348">通常、既定値は `C:\Program Files\dotnet` です。これは、インストーラーによって .NET Core がインストールされる場所です。</span><span class="sxs-lookup"><span data-stu-id="517e4-348">The default is typically `C:\Program Files\dotnet`, which is where the installers install .NET Core.</span></span>

## <a name="docker"></a><span data-ttu-id="517e4-349">Docker</span><span class="sxs-lookup"><span data-stu-id="517e4-349">Docker</span></span>

<span data-ttu-id="517e4-350">コンテナーを使用すると、アプリケーションをホスト システムの他の部分から簡単に分離できます。</span><span class="sxs-lookup"><span data-stu-id="517e4-350">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="517e4-351">同じコンピューター上のコンテナーでは、カーネルだけが共有され、アプリケーションに提供されたリソースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="517e4-351">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="517e4-352">.NET Core は Docker コンテナー内で実行できます。</span><span class="sxs-lookup"><span data-stu-id="517e4-352">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="517e4-353">公式の .NET Core Docker イメージは Microsoft Container Registry (MCR) に公開され、[Microsoft .NET Core の Docker Hub リポジトリ](https://hub.docker.com/_/microsoft-dotnet-core/)で見つけられます。</span><span class="sxs-lookup"><span data-stu-id="517e4-353">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="517e4-354">各リポジトリには、.NET (SDK またはランタイム) と自分が使用できる OS のさまざまな組み合わせのイメージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="517e4-354">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="517e4-355">Microsoft は、特定のシナリオに対応したイメージを用意しています。</span><span class="sxs-lookup"><span data-stu-id="517e4-355">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="517e4-356">たとえば、[ASP.NET Core リポジトリ](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/)には、運用環境での ASP.NET Core アプリの実行用にビルドされたイメージが用意されています。</span><span class="sxs-lookup"><span data-stu-id="517e4-356">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="517e4-357">Docker コンテナー内で .NET Core を使用する方法の詳細については、「[.NET および Docker の概要](../docker/introduction.md)」と[サンプル](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="517e4-357">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="517e4-358">次の手順</span><span class="sxs-lookup"><span data-stu-id="517e4-358">Next steps</span></span>

- <span data-ttu-id="517e4-359">[.NET Core が既にインストールされているかどうかを確認する方法](how-to-detect-installed-versions.md?pivots=os-windows)。</span><span class="sxs-lookup"><span data-stu-id="517e4-359">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md?pivots=os-windows).</span></span>
- <span data-ttu-id="517e4-360">[チュートリアル: Hello World チュートリアル](../tutorials/with-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="517e4-360">[Tutorial: Hello World tutorial](../tutorials/with-visual-studio.md).</span></span>
- <span data-ttu-id="517e4-361">[チュートリアル: Visual Studio Code を使用して新しいアプリを作成する](../tutorials/with-visual-studio-code.md)。</span><span class="sxs-lookup"><span data-stu-id="517e4-361">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="517e4-362">[チュートリアル: NET Core アプリをコンテナー化する](../docker/build-container.md)。</span><span class="sxs-lookup"><span data-stu-id="517e4-362">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>
