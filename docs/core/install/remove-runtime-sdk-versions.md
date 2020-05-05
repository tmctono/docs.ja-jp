---
title: .NET Core ランタイムと SDK を削除する
description: この記事では、現在インストールされている .NET Core ランタイムと SDK のバージョンを確認する方法と、Windows、Mac、および Linux でそれらを削除する方法について説明します。
author: thraka
ms.author: adegeo
ms.date: 04/28/2020
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: f1482c243ba22fa81c69ede847a0f6b36a9cb83c
ms.sourcegitcommit: d7666f6e49c57a769612602ea7857b927294ce47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2020
ms.locfileid: "82595763"
---
# <a name="how-to-remove-the-net-core-runtime-and-sdk"></a><span data-ttu-id="42e59-103">.NET Core ランタイムと SDK を削除する方法</span><span class="sxs-lookup"><span data-stu-id="42e59-103">How to remove the .NET Core Runtime and SDK</span></span>

<span data-ttu-id="42e59-104">時間の経過に伴い、.NET Core ランタイムと SDK の更新バージョンをインストールした場合は、ご利用のコンピューターから古いバージョンの .NET Core を削除することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="42e59-104">Over time, as you install updated versions of the .NET Core runtime and SDK, you may want to remove outdated versions of .NET Core from your machine.</span></span> <span data-ttu-id="42e59-105">ランタイムの古いバージョンを削除すると、共有のフレームワーク アプリケーションを実行するように選択されているランタイムが変更される可能性があります。詳細については、「[.NET Core のバージョンの選択](../versions/selection.md)」の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42e59-105">Removing older versions of the runtime may change the runtime chosen to run shared framework applications, as detailed in the article on [.NET Core version selection](../versions/selection.md).</span></span>

## <a name="should-i-remove-a-version"></a><span data-ttu-id="42e59-106">バージョンを削除する必要はあるか</span><span class="sxs-lookup"><span data-stu-id="42e59-106">Should I remove a version?</span></span>

<span data-ttu-id="42e59-107">[.NET Core バージョン選択](../versions/selection.md)動作および更新プログラム間での .NET Core のランタイム互換性により、以前のバージョンを安全に削除することができます。</span><span class="sxs-lookup"><span data-stu-id="42e59-107">The [.NET Core version selection](../versions/selection.md) behaviors and the runtime compatibility of .NET Core across updates enables safe removal of previous versions.</span></span> <span data-ttu-id="42e59-108">1\.x や 2.x などのメジャー バージョン 'バンド' 内で .NET Core ランタイム更新プログラムは互換性があります。</span><span class="sxs-lookup"><span data-stu-id="42e59-108">.NET Core runtime updates are compatible within a major version 'band' such as 1.x and 2.x.</span></span> <span data-ttu-id="42e59-109">さらに、.NET Core SDK のより新しいリリースでは、通常、互換性を保ちながら、ランタイムの前バージョンを対象とするアプリケーションをビルドする機能が維持されます。</span><span class="sxs-lookup"><span data-stu-id="42e59-109">Additionally, newer releases of the .NET Core SDK generally maintain the ability to build applications that target previous versions of the runtime in a compatible manner.</span></span>

<span data-ttu-id="42e59-110">通常、必要なのは、ご自分のアプリケーションに必須である最新の SDK および最新のパッチ バージョンのランタイムのみです。</span><span class="sxs-lookup"><span data-stu-id="42e59-110">In general, you only need the latest SDK and latest patch version of the runtimes required for your application.</span></span> <span data-ttu-id="42e59-111">たとえば、*project.json* ベースのアプリケーションを管理するとき、以前のバージョンの SDK またはランタイムを保持することがあります。</span><span class="sxs-lookup"><span data-stu-id="42e59-111">Instances where you might want to keep older SDK or runtime versions include maintaining *project.json*-based applications.</span></span> <span data-ttu-id="42e59-112">ご利用のアプリケーションには以前の SDK やランタイムを維持する特別な理由がない場合、以前のバージョンを安全に削除することができます。</span><span class="sxs-lookup"><span data-stu-id="42e59-112">Unless your application has specific reasons for earlier SDKs or runtimes, you may safely remove older versions.</span></span>

## <a name="determine-what-is-installed"></a><span data-ttu-id="42e59-113">インストールされている内容を確認する</span><span class="sxs-lookup"><span data-stu-id="42e59-113">Determine what is installed</span></span>

<span data-ttu-id="42e59-114">.NET Core 2.1 以降、ご利用のコンピューターにインストールされている SDK とランタイムのバージョンを一覧表示するのに使用できるオプションが .NET CLI に用意されています。</span><span class="sxs-lookup"><span data-stu-id="42e59-114">Starting with .NET Core 2.1, the .NET CLI has options you can use to list the versions of the SDK and runtime that are installed on your machine.</span></span>  <span data-ttu-id="42e59-115">ご利用のコンピューターにインストールされている SDK を一覧表示するには、[`dotnet --list-sdks`](../tools/dotnet.md#options) を使用します。</span><span class="sxs-lookup"><span data-stu-id="42e59-115">Use [`dotnet --list-sdks`](../tools/dotnet.md#options) to see the list of SDKs installed on your machine.</span></span> <span data-ttu-id="42e59-116">ご利用のコンピューターにインストールされているランタイムを一覧表示するには、[`dotnet --list-runtimes`](../tools/dotnet.md#options) を使用します。</span><span class="sxs-lookup"><span data-stu-id="42e59-116">Use [`dotnet --list-runtimes`](../tools/dotnet.md#options) to see the list of runtimes installed on your machine.</span></span> <span data-ttu-id="42e59-117">詳細については、「[.NET Core が既にインストールされていることを確認する方法](how-to-detect-installed-versions.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="42e59-117">For more information, see [How to check that .NET Core is already installed](how-to-detect-installed-versions.md).</span></span>

## <a name="uninstall-net-core"></a><span data-ttu-id="42e59-118">.NET Core のアンインストール</span><span class="sxs-lookup"><span data-stu-id="42e59-118">Uninstall .NET Core</span></span>

::: zone pivot="os-windows"

<span data-ttu-id="42e59-119">.NET Core では、Windows の **[アプリと機能]** ダイアログを使用して .NET Core ランタイムと SDK のバージョンを削除できます。</span><span class="sxs-lookup"><span data-stu-id="42e59-119">.NET Core uses the Windows **Apps & features** dialog to remove versions of the .NET Core runtime and SDK.</span></span> <span data-ttu-id="42e59-120">**[アプリと機能]** ダイアログ ボックスを次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="42e59-120">The following figure shows the **Apps & features** dialog.</span></span> <span data-ttu-id="42e59-121">.NET Core のインストールされているバージョンをフィルタリングしたり、表示したりする目的で「**core sdk**」を検索できます。</span><span class="sxs-lookup"><span data-stu-id="42e59-121">You can search for **core sdk** to filter and show installed versions of .NET Core.</span></span>

![.NET Core を削除するための [プログラムの追加と削除]](./media/remove-runtime-sdk-versions/programs-and-features.png)

<span data-ttu-id="42e59-123">ご利用のコンピューターから削除する任意のバージョンを選択して、 **[アンインストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="42e59-123">Select any versions you want to remove from your machine and click **Uninstall**.</span></span>

::: zone-end

::: zone pivot="os-linux"

<span data-ttu-id="42e59-124">さらに Linux 上で .NET Core (SDK またはランタイムのいずれか) をアンインストールするオプションもあります。</span><span class="sxs-lookup"><span data-stu-id="42e59-124">There are more options to uninstall .NET Core (either SDK or runtime) on Linux.</span></span> <span data-ttu-id="42e59-125">.NET Core をアンインストールするには、.NET Core をインストールするときに使用したアクションをミラー化することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="42e59-125">The best way for you to uninstall .NET Core is to mirror the action you used to install .NET Core.</span></span> <span data-ttu-id="42e59-126">詳細は、選択した配布方法とインストール方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="42e59-126">The specifics depend on your chosen distribution and the installation method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="42e59-127">Red Hat インストールの場合、.NET Core のインストールとアンインストールについては、[Red Hat ファースト ステップ ガイド](https://access.redhat.com/documentation/en-us/net_core/2.0/html/getting_started_guide/gs_install_dotnet#install_register_rehel) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42e59-127">For Red Hat installations, consult the [Red Hat Getting Started Guide](https://access.redhat.com/documentation/en-us/net_core/2.0/html/getting_started_guide/gs_install_dotnet#install_register_rehel) for information on installing and uninstalling .NET Core.</span></span>

<span data-ttu-id="42e59-128">.NET Core 2.1 以降では、パッケージ マネージャーを使用して .NET Core SDK をアップグレードする場合、それをアンインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="42e59-128">Starting with .NET Core 2.1, there's no need to uninstall the .NET Core SDK when upgrading it using a package manager.</span></span> <span data-ttu-id="42e59-129">パッケージ マネージャーの `update` または `refresh` コマンドでは、新しいバージョンが正常にインストールされると、古いバージョンが自動的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="42e59-129">The package manager `update` or `refresh` commands will automatically remove the older version upon the successful installation of a newer version.</span></span>

<span data-ttu-id="42e59-130">パッケージ マネージャーを使用して .NET Core をインストールした場合は、それと同じパッケージ マネージャーを使用して .NET SDK またはランタイムをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="42e59-130">If you installed .NET Core using a package manager, you use that same package manager to uninstall .NET SDK or runtime.</span></span> <span data-ttu-id="42e59-131">.NET Core インストールでは、最も一般的なパッケージ マネージャーがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="42e59-131">.NET Core installations support most popular package managers.</span></span> <span data-ttu-id="42e59-132">ご利用の環境内での正確な構文については、ご利用の配布のパッケージ マネージャーのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="42e59-132">Consult the documentation for your distribution's package manager for the precise syntax in your environment:</span></span>

- <span data-ttu-id="42e59-133">[apt-get(8)](https://linux.die.net/man/8/apt-get) は、Ubuntu などの Debian ベースのシステムによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="42e59-133">[apt-get(8)](https://linux.die.net/man/8/apt-get) is used by Debian based systems, including Ubuntu.</span></span>
- <span data-ttu-id="42e59-134">[yum(8)](https://linux.die.net/man/8/yum) は、Fedora、CentOS、Oracle Linux 上で使用されます。</span><span class="sxs-lookup"><span data-stu-id="42e59-134">[yum(8)](https://linux.die.net/man/8/yum) is used on Fedora, CentOS, and Oracle Linux.</span></span>
- <span data-ttu-id="42e59-135">[zypper(8)](https://en.opensuse.org/SDB:Zypper_manual_(plain)) は、openSUSE および SUSE Linux Enterprise System (SLES) 上で使用されます。</span><span class="sxs-lookup"><span data-stu-id="42e59-135">[zypper(8)](https://en.opensuse.org/SDB:Zypper_manual_(plain)) is used on openSUSE and SUSE Linux Enterprise System (SLES).</span></span>
- <span data-ttu-id="42e59-136">[dnf(8)](https://dnf.readthedocs.io/en/latest/command_ref.html) は、Fedora 上で使用されます。</span><span class="sxs-lookup"><span data-stu-id="42e59-136">[dnf(8)](https://dnf.readthedocs.io/en/latest/command_ref.html) is used on Fedora.</span></span>

<span data-ttu-id="42e59-137">ほとんどの場合、パッケージを削除するコマンドは `remove` となります。</span><span class="sxs-lookup"><span data-stu-id="42e59-137">In almost all cases, the command to remove a package is `remove`.</span></span>

<span data-ttu-id="42e59-138">ほとんどのパッケージ マネージャーの場合、.NET Core SDK インストールのパッケージ名は `dotnet-sdk` であり、その後にバージョン番号が続きます。</span><span class="sxs-lookup"><span data-stu-id="42e59-138">The package name for the .NET Core SDK installation for most package managers is `dotnet-sdk`, followed by the version number.</span></span> <span data-ttu-id="42e59-139">.NET Core SDK のバージョン 2.1.300 およびランタイムのバージョン `2.1` 以降は、メジャーおよびマイナーのバージョン番号のみ必要です。たとえば、.NET Core SDK バージョン 2.1.300 は、パッケージ `dotnet-sdk-2.1` として参照できます。</span><span class="sxs-lookup"><span data-stu-id="42e59-139">Starting with the version 2.1.300 of the .NET Core SDK and version `2.1` of the runtime, only the major and minor version numbers are necessary: for example, the .NET Core SDK version 2.1.300 can be referenced as the package `dotnet-sdk-2.1`.</span></span> <span data-ttu-id="42e59-140">以前のバージョンでは、バージョン文字列全体が必須です。たとえば、.NET Core SDK のバージョン 2.1.200 の場合は `dotnet-sdk-2.1.200` が必須となります。</span><span class="sxs-lookup"><span data-stu-id="42e59-140">Prior versions require the entire version string: for example, `dotnet-sdk-2.1.200` would be required for version 2.1.200 of the .NET Core SDK.</span></span>

<span data-ttu-id="42e59-141">ランタイムのみがインストールされ、SDK はインストールされていないコンピューターの場合、.NET Core ランタイムのパッケージ名は `dotnet-runtime-<version>` となり、ランタイム スタック全体のパッケージ名は `aspnetcore-runtime-<version>` となります。</span><span class="sxs-lookup"><span data-stu-id="42e59-141">For machines that have installed only the runtime, and not the SDK, the package name is `dotnet-runtime-<version>` for the .NET Core runtime, and `aspnetcore-runtime-<version>` for the entire runtime stack.</span></span>

<span data-ttu-id="42e59-142">2\.0 より前の .NET Core インストールでは、パッケージ マネージャーを使用して SDK をアンインストールしたとき、ホスト アプリケーションはアンインストールされませんでした。</span><span class="sxs-lookup"><span data-stu-id="42e59-142">.NET Core installations earlier than 2.0 didn't uninstall the host application when the SDK was uninstalled using the package manager.</span></span> <span data-ttu-id="42e59-143">`apt-get` を使用する場合、コマンドは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="42e59-143">Using `apt-get`, the command is:</span></span>

```bash
apt-get remove dotnet-host
```

<span data-ttu-id="42e59-144">`dotnet-host` にはバージョンが添えられていないことに注目してください。</span><span class="sxs-lookup"><span data-stu-id="42e59-144">Note that there's no version attached to `dotnet-host`.</span></span>

<span data-ttu-id="42e59-145">tarball を使用してインストールした場合、.NET Core の削除は手動で行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="42e59-145">If you installed using a tarball, you must remove .NET Core using the manual method.</span></span>

<span data-ttu-id="42e59-146">Linux では、バージョン管理されているディレクトリを削除し、SDK とランタイムを別々に削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42e59-146">On Linux, you must remove the SDKs and runtimes separately, by removing the versioned directories.</span></span> <span data-ttu-id="42e59-147">これを削除すると、SDK とランタイムがディスクから削除されます。</span><span class="sxs-lookup"><span data-stu-id="42e59-147">Removing them deletes the SDK and runtime from disk.</span></span> <span data-ttu-id="42e59-148">たとえば、1.0.1 SDK とランタイムを削除するには、次の bash コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="42e59-148">For example, to remove the 1.0.1 SDK and runtime, you would use the following bash commands:</span></span>

```bash
version="1.0.1"
sudo rm -rf /usr/local/share/dotnet/sdk/$version
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.NETCore.App/$version
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.AspNetCore.All/$version
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.AspNetCore.App/$version
sudo rm -rf /usr/local/share/dotnet/host/fxr/$version
```

<span data-ttu-id="42e59-149">上記の表に示したように、SDK とランタイムの親ディレクトリは、`dotnet --list-sdks` コマンドおよび `dotnet --list-runtimes` コマンドからの出力に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="42e59-149">The parent directories for the SDK and runtime are listed in the output from the `dotnet --list-sdks` and `dotnet --list-runtimes` command, as shown in the earlier table.</span></span>

::: zone-end

::: zone pivot="os-macos"

<span data-ttu-id="42e59-150">Mac では、バージョン管理されているディレクトリを削除し、SDK とランタイムを別々に削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42e59-150">On Mac, you must remove the SDKs and runtimes separately, by removing the versioned directories.</span></span> <span data-ttu-id="42e59-151">これを削除すると、SDK とランタイムがディスクから削除されます。</span><span class="sxs-lookup"><span data-stu-id="42e59-151">Removing them deletes the SDK and runtime from disk.</span></span> <span data-ttu-id="42e59-152">たとえば、1.0.1 SDK とランタイムを削除するには、次の bash コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="42e59-152">For example, to remove the 1.0.1 SDK and runtime, you would use the following bash commands:</span></span>

```bash
version="1.0.1"
sudo rm -rf /usr/local/share/dotnet/sdk/$version
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.NETCore.App/$version
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.AspNetCore.All/$version
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.AspNetCore.App/$version
sudo rm -rf /usr/local/share/dotnet/host/fxr/$version
```

<span data-ttu-id="42e59-153">上記の表に示したように、SDK とランタイムの親ディレクトリは、`dotnet --list-sdks` コマンドおよび `dotnet --list-runtimes` コマンドからの出力に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="42e59-153">The parent directories for the SDK and runtime are listed in the output from the `dotnet --list-sdks` and `dotnet --list-runtimes` command, as shown in the earlier table.</span></span>

::: zone-end

## <a name="net-core-uninstall-tool"></a><span data-ttu-id="42e59-154">.NET Core アンインストール ツール</span><span class="sxs-lookup"><span data-stu-id="42e59-154">.NET Core Uninstall Tool</span></span>

<span data-ttu-id="42e59-155">[.NET Core アンインストール ツール](../additional-tools/uninstall-tool.md) (`dotnet-core-uninstall`) を使用すると、.NET Core SDK とランタイムをシステムから削除できます。</span><span class="sxs-lookup"><span data-stu-id="42e59-155">The [.NET Core Uninstall Tool](../additional-tools/uninstall-tool.md) (`dotnet-core-uninstall`) lets you remove .NET Core SDKs and runtimes from a system.</span></span> <span data-ttu-id="42e59-156">一連のオプションを使用して、アンインストールするバージョンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="42e59-156">A collection of options is available to specify which versions should be uninstalled.</span></span>

## <a name="visual-studio-dependency-on-net-core-sdk-versions"></a><span data-ttu-id="42e59-157">.NET Core SDK バージョンに対する Visual Studio の依存関係</span><span class="sxs-lookup"><span data-stu-id="42e59-157">Visual Studio dependency on .NET Core SDK versions</span></span>

<span data-ttu-id="42e59-158">Visual Studio 2019 バージョン 16.3 より前では、Visual Studio インストーラーはスタンドアロンの .NET Core SDK インストーラーを呼び出しました。</span><span class="sxs-lookup"><span data-stu-id="42e59-158">Before Visual Studio 2019 version 16.3, Visual Studio installers called the standalone .NET Core SDK installer.</span></span> <span data-ttu-id="42e59-159">その結果、Windows の **[アプリと機能]** ダイアログに SDK のバージョンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="42e59-159">As a result, the SDK versions appear in the Windows **Apps & features** dialog.</span></span> <span data-ttu-id="42e59-160">スタンドアロン インストーラーを使用して Visual Studio によってインストールされた .NET Core SDK を削除すると、Visual Studio が破損する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="42e59-160">Removing .NET Core SDKs that were installed by Visual Studio using the standalone installer may break Visual Studio.</span></span> <span data-ttu-id="42e59-161">SDK をアンインストールした後に Visual Studio で問題が発生した場合は、その特定のバージョンの Visual Studio で [修復] を実行します。</span><span class="sxs-lookup"><span data-stu-id="42e59-161">If Visual Studio has problems after you uninstall SDKs, run Repair on that specific version of Visual Studio.</span></span> <span data-ttu-id="42e59-162">次の表に、.NET Core SDK バージョンに対する Visual Studio の依存関係の一部を示します。</span><span class="sxs-lookup"><span data-stu-id="42e59-162">The following table shows some of the Visual Studio dependencies on .NET Core SDK versions:</span></span>

| <span data-ttu-id="42e59-163">Visual Studio のバージョン</span><span class="sxs-lookup"><span data-stu-id="42e59-163">Visual Studio version</span></span>           | <span data-ttu-id="42e59-164">.NET Core SDK のバージョン</span><span class="sxs-lookup"><span data-stu-id="42e59-164">.NET Core SDK version</span></span>          |
|---------------------------------|--------------------------------|
| <span data-ttu-id="42e59-165">Visual Studio 2019 バージョン 16.2</span><span class="sxs-lookup"><span data-stu-id="42e59-165">Visual Studio 2019 version 16.2</span></span> | <span data-ttu-id="42e59-166">.NET Core SDK 2.2.4xx、2.1.8xx</span><span class="sxs-lookup"><span data-stu-id="42e59-166">.NET Core SDK 2.2.4xx, 2.1.8xx</span></span> |
| <span data-ttu-id="42e59-167">Visual Studio 2019 バージョン 16.1</span><span class="sxs-lookup"><span data-stu-id="42e59-167">Visual Studio 2019 version 16.1</span></span> | <span data-ttu-id="42e59-168">.NET Core SDK 2.2.3xx、2.1.7xx</span><span class="sxs-lookup"><span data-stu-id="42e59-168">.NET Core SDK 2.2.3xx, 2.1.7xx</span></span> |
| <span data-ttu-id="42e59-169">Visual Studio 2019 バージョン 16.0</span><span class="sxs-lookup"><span data-stu-id="42e59-169">Visual Studio 2019 version 16.0</span></span> | <span data-ttu-id="42e59-170">.NET Core SDK 2.2.2xx、2.1.6xx</span><span class="sxs-lookup"><span data-stu-id="42e59-170">.NET Core SDK 2.2.2xx, 2.1.6xx</span></span> |
| <span data-ttu-id="42e59-171">Visual Studio 2017 バージョン 15.9</span><span class="sxs-lookup"><span data-stu-id="42e59-171">Visual Studio 2017 version 15.9</span></span> | <span data-ttu-id="42e59-172">.NET Core SDK 2.2.1xx、2.1.5xx</span><span class="sxs-lookup"><span data-stu-id="42e59-172">.NET Core SDK 2.2.1xx, 2.1.5xx</span></span> |
| <span data-ttu-id="42e59-173">Visual Studio 2017 バージョン 15.8</span><span class="sxs-lookup"><span data-stu-id="42e59-173">Visual Studio 2017 version 15.8</span></span> | <span data-ttu-id="42e59-174">.NET Core SDK 2.1.4xx</span><span class="sxs-lookup"><span data-stu-id="42e59-174">.NET Core SDK 2.1.4xx</span></span>          |

<span data-ttu-id="42e59-175">Visual Studio 2019 バージョン 16.3 以降では、Visual Studio によって .NET Core SDK の独自のコピーが管理されます。</span><span class="sxs-lookup"><span data-stu-id="42e59-175">Starting with Visual Studio 2019 version 16.3, Visual Studio is in charge of its own copy of the .NET Core SDK.</span></span> <span data-ttu-id="42e59-176">そのため、 **[アプリと機能]** ダイアログにこれらの SDK バージョンが表示されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="42e59-176">For that reason, you no longer see those SDK versions in the **Apps & features** dialog.</span></span>

## <a name="remove-the-nuget-fallback-folder"></a><span data-ttu-id="42e59-177">NuGet フォールバック フォルダーの削除</span><span class="sxs-lookup"><span data-stu-id="42e59-177">Remove the NuGet fallback folder</span></span>

<span data-ttu-id="42e59-178">.NET Core 3.0 SDK より前では、.NET Core SDK インストーラーでは *NuGetFallbackFolder* という名前のフォルダーを使用して NuGet パッケージのキャッシュを格納していました。</span><span class="sxs-lookup"><span data-stu-id="42e59-178">Before .NET Core 3.0 SDK, the .NET Core SDK installers used a folder named *NuGetFallbackFolder* to store a cache of NuGet packages.</span></span> <span data-ttu-id="42e59-179">このキャッシュは、`dotnet restore` や `dotnet build /t:Restore` などの操作中に使用されました。</span><span class="sxs-lookup"><span data-stu-id="42e59-179">This cache was used during operations such as `dotnet restore` or `dotnet build /t:Restore`.</span></span> <span data-ttu-id="42e59-180">*NuGetFallbackFolder* は、Windows では *C:\Program Files\dotnet\sdk* に、macOS では */usr/local/share/dotnet/sdk* にあります。</span><span class="sxs-lookup"><span data-stu-id="42e59-180">The *NuGetFallbackFolder* is located at *C:\Program Files\dotnet\sdk* on Windows and at */usr/local/share/dotnet/sdk* on macOS.</span></span>

<span data-ttu-id="42e59-181">次の場合は、このフォルダーを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="42e59-181">You may want to remove this folder, if:</span></span>

- <span data-ttu-id="42e59-182">.NET Core 3.0 SDK 以降のバージョンのみを使用して開発している。</span><span class="sxs-lookup"><span data-stu-id="42e59-182">You're only developing using .NET Core 3.0 SDK or later versions.</span></span>
- <span data-ttu-id="42e59-183">3\.0 より前の .NET Core SDK のバージョンを使用して開発しているが、オンラインで作業できる。</span><span class="sxs-lookup"><span data-stu-id="42e59-183">You're developing using .NET Core SDK versions earlier than 3.0, but you can work online.</span></span>

<span data-ttu-id="42e59-184">NuGet フォールバック フォルダーを削除する場合は、管理者特権が必要になります。</span><span class="sxs-lookup"><span data-stu-id="42e59-184">If you want to remove the NuGet fallback folder, you can delete it, but you'll need admin privileges to do so.</span></span>

<span data-ttu-id="42e59-185">*dotnet* フォルダーの削除はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="42e59-185">It's not recommended to delete the *dotnet* folder.</span></span> <span data-ttu-id="42e59-186">これを行うと、以前にインストールしたグローバル ツールがすべて削除されます。</span><span class="sxs-lookup"><span data-stu-id="42e59-186">Doing so would remove any global tools you've previously installed.</span></span> <span data-ttu-id="42e59-187">また、Windows の場合は、次のことが発生します。</span><span class="sxs-lookup"><span data-stu-id="42e59-187">Also, on Windows:</span></span>

- <span data-ttu-id="42e59-188">Visual Studio 2019 バージョン 16.3 以降のバージョンが破損します。</span><span class="sxs-lookup"><span data-stu-id="42e59-188">You'll break Visual Studio 2019 version 16.3 and later versions.</span></span> <span data-ttu-id="42e59-189">**[修復]** を実行して回復できます。</span><span class="sxs-lookup"><span data-stu-id="42e59-189">You can run **Repair** to recover.</span></span>
- <span data-ttu-id="42e59-190">**[アプリと機能]** ダイアログに .NET Core SDK エントリがある場合、それらは孤立状態になります。</span><span class="sxs-lookup"><span data-stu-id="42e59-190">If there are .NET Core SDK entries in the **Apps & features** dialog, they'll be orphaned.</span></span>
