---
title: Windows、Linux、および macOS に .NET Core ランタイムをインストールする - .NET Core
description: Windows、Linux、および macOS に .NET Core をインストールする方法について説明します。 .NET Core アプリの実行に必要な依存関係を確認します。
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 8f4a895ad66dea3063a32f785e4c521196266978
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74998889"
---
# <a name="install-the-net-core-runtime"></a><span data-ttu-id="bb036-104">.NET Core ランタイムのインストール</span><span class="sxs-lookup"><span data-stu-id="bb036-104">Install the .NET Core Runtime</span></span>

<span data-ttu-id="bb036-105">この記事では、.NET Core ランタイムをダウンロードしてインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bb036-105">In this article, you'll learn how to download and install the .NET Core runtime.</span></span> <span data-ttu-id="bb036-106">.Net Core ランタイムは、.NET Core で作成されたアプリを実行するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="bb036-106">The .NET Core runtime is used to run apps created with .NET Core.</span></span>

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a><span data-ttu-id="bb036-107">インストーラーを使用したインストール</span><span class="sxs-lookup"><span data-stu-id="bb036-107">Install with an installer</span></span>

<span data-ttu-id="bb036-108">Windows には、.NET Core 3.1 ランタイムのインストールに使用できるスタンドアロン インストーラーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="bb036-108">Windows has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="bb036-109">x64 (64 ビット) CPU</span><span class="sxs-lookup"><span data-stu-id="bb036-109">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="bb036-110">x86 (32 ビット) CPU</span><span class="sxs-lookup"><span data-stu-id="bb036-110">x86 (32-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="bb036-111">インストーラーを使用したインストール</span><span class="sxs-lookup"><span data-stu-id="bb036-111">Install with an installer</span></span>

<span data-ttu-id="bb036-112">macOS には、.NET Core 3.1 ランタイムのインストールに使用できるスタンドアロン インストーラーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="bb036-112">macOS has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="bb036-113">x64 (64 ビット) CPU</span><span class="sxs-lookup"><span data-stu-id="bb036-113">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a><span data-ttu-id="bb036-114">パッケージ マネージャーを使用したインストール</span><span class="sxs-lookup"><span data-stu-id="bb036-114">Install with a package manager</span></span>

<span data-ttu-id="bb036-115">多くの一般的な Linux パッケージ マネージャーを使用して .NET Core ランタイムをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="bb036-115">You can install the .NET Core Runtime with many of the common Linux package managers.</span></span> <span data-ttu-id="bb036-116">詳細については、[Linux パッケージ マネージャー - .NET Core のインストール](linux-package-manager-rhel7.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb036-116">For more information, see [Linux Package Manager - Install .NET Core](linux-package-manager-rhel7.md).</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="bb036-117">PowerShell オートメーションを使用したインストール</span><span class="sxs-lookup"><span data-stu-id="bb036-117">Install with PowerShell automation</span></span>

<span data-ttu-id="bb036-118">[dotnet-install スクリプト](../tools/dotnet-install-script.md)は、ランタイムの自動化および管理者以外によるインストールに使用されます。</span><span class="sxs-lookup"><span data-stu-id="bb036-118">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="bb036-119">スクリプトは、[dotnet-install スクリプト参照ページ](../tools/dotnet-install-script.md)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="bb036-119">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="bb036-120">スクリプトでは、既定で最新の [長期サポート (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) バージョン (.NET Core 3.1) がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="bb036-120">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="bb036-121">`Channel` スイッチを指定することで、特定のリリースを選択できます。</span><span class="sxs-lookup"><span data-stu-id="bb036-121">You can choose a specific release by specifying the `Channel` switch.</span></span> <span data-ttu-id="bb036-122">ランタイムをインストールするには、`Runtime` スイッチを含めます。</span><span class="sxs-lookup"><span data-stu-id="bb036-122">Include the `Runtime` switch to install a runtime.</span></span> <span data-ttu-id="bb036-123">それ以外の場合は、スクリプトによって [SDK](sdk.md) がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="bb036-123">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```powershell
dotnet-install.ps1 -Channel 3.1 -Runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="bb036-124">上のコマンドでは、互換性を最大限に高めるために ASP.NET Core ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="bb036-124">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="bb036-125">ASP.NET Core ランタイムには、標準の .NET Core ランタイムも含まれています。</span><span class="sxs-lookup"><span data-stu-id="bb036-125">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="bb036-126">bash オートメーションを使用したインストール</span><span class="sxs-lookup"><span data-stu-id="bb036-126">Install with bash automation</span></span>

<span data-ttu-id="bb036-127">[dotnet-install スクリプト](../tools/dotnet-install-script.md)は、ランタイムの自動化および管理者以外によるインストールに使用されます。</span><span class="sxs-lookup"><span data-stu-id="bb036-127">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="bb036-128">スクリプトは、[dotnet-install スクリプト参照ページ](../tools/dotnet-install-script.md)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="bb036-128">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="bb036-129">スクリプトでは、既定で最新の [長期サポート (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) バージョン (.NET Core 3.1) がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="bb036-129">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="bb036-130">`current` スイッチを指定することで、特定のリリースを選択できます。</span><span class="sxs-lookup"><span data-stu-id="bb036-130">You can choose a specific release by specifying the `current` switch.</span></span> <span data-ttu-id="bb036-131">ランタイムをインストールするには、`runtime` スイッチを含めます。</span><span class="sxs-lookup"><span data-stu-id="bb036-131">Include the `runtime` switch to install a runtime.</span></span> <span data-ttu-id="bb036-132">それ以外の場合は、スクリプトによって [SDK](sdk.md) がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="bb036-132">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```bash
./dotnet-install.sh --current 3.1 --runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="bb036-133">上のコマンドでは、互換性を最大限に高めるために ASP.NET Core ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="bb036-133">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="bb036-134">ASP.NET Core ランタイムには、標準の .NET Core ランタイムも含まれています。</span><span class="sxs-lookup"><span data-stu-id="bb036-134">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="bb036-135">すべての .NET Core のダウンロード</span><span class="sxs-lookup"><span data-stu-id="bb036-135">All .NET Core downloads</span></span>

<span data-ttu-id="bb036-136">次のいずれかのリンクを使用して、.NET Core を直接ダウンロードしてインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="bb036-136">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="bb036-137">.NET Core 3.1 のダウンロード</span><span class="sxs-lookup"><span data-stu-id="bb036-137">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="bb036-138">.NET Core 3.0 のダウンロード</span><span class="sxs-lookup"><span data-stu-id="bb036-138">.NET Core 3.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [<span data-ttu-id="bb036-139">.NET Core 2.2 のダウンロード</span><span class="sxs-lookup"><span data-stu-id="bb036-139">.NET Core 2.2 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [<span data-ttu-id="bb036-140">.NET Core 2.1 のダウンロード</span><span class="sxs-lookup"><span data-stu-id="bb036-140">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="bb036-141">Docker</span><span class="sxs-lookup"><span data-stu-id="bb036-141">Docker</span></span>

<span data-ttu-id="bb036-142">コンテナーを使用すると、アプリケーションをホスト システムの他の部分から簡単に分離できます。</span><span class="sxs-lookup"><span data-stu-id="bb036-142">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="bb036-143">同じコンピューター上のコンテナーでは、カーネルだけが共有され、アプリケーションに提供されたリソースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="bb036-143">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="bb036-144">.NET Core は Docker コンテナー内で実行できます。</span><span class="sxs-lookup"><span data-stu-id="bb036-144">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="bb036-145">公式の .NET Core Docker イメージは Microsoft Container Registry (MCR) に公開され、[Microsoft .NET Core の Docker Hub リポジトリ](https://hub.docker.com/_/microsoft-dotnet-core/)で見つけられます。</span><span class="sxs-lookup"><span data-stu-id="bb036-145">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="bb036-146">各リポジトリには、.NET (SDK またはランタイム) と自分が使用できる OS のさまざまな組み合わせのイメージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bb036-146">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="bb036-147">Microsoft は、特定のシナリオに対応したイメージを用意しています。</span><span class="sxs-lookup"><span data-stu-id="bb036-147">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="bb036-148">たとえば、[ASP.NET Core リポジトリ](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/)には、運用環境での ASP.NET Core アプリの実行用にビルドされたイメージが用意されています。</span><span class="sxs-lookup"><span data-stu-id="bb036-148">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="bb036-149">Docker コンテナー内で .NET Core を使用する方法の詳細については、「[.NET および Docker の概要](../docker/introduction.md)」と[サンプル](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb036-149">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="bb036-150">次の手順</span><span class="sxs-lookup"><span data-stu-id="bb036-150">Next steps</span></span>

- <span data-ttu-id="bb036-151">[.NET Core が既にインストールされているかどうかを確認する方法](how-to-detect-installed-versions.md)。</span><span class="sxs-lookup"><span data-stu-id="bb036-151">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md).</span></span>
