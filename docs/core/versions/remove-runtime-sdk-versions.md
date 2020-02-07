---
title: .NET Core ランタイムと SDK を削除する
description: この記事では、現在インストールされている .NET Core ランタイムと SDK のバージョンを確認する方法と、Windows、Mac、および Linux でそれらを削除する方法について説明します。
ms.date: 12/17/2019
author: billwagner
ms.author: wiwagn
ms.custom: updateeachrelease
ms.openlocfilehash: 82fbccdec0323b54d313960279fcbfeeb6033319
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920406"
---
# <a name="how-to-remove-the-net-core-runtime-and-sdk"></a><span data-ttu-id="aec18-103">.NET Core ランタイムと SDK を削除する方法</span><span class="sxs-lookup"><span data-stu-id="aec18-103">How to remove the .NET Core Runtime and SDK</span></span>

<span data-ttu-id="aec18-104">時間の経過に伴い、.NET Core ランタイムと SDK の更新バージョンをインストールした場合は、ご利用のコンピューターから古いバージョンの .NET Core を削除することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="aec18-104">Over time, as you install updated versions of the .NET Core runtime and SDK, you may want to remove outdated versions of .NET Core from your machine.</span></span> <span data-ttu-id="aec18-105">ランタイムの古いバージョンを削除すると、共有のフレームワーク アプリケーションを実行するように選択されているランタイムが変更される可能性があります。詳細については、「[.NET Core のバージョンの選択](selection.md)」の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aec18-105">Removing older versions of the runtime may change the runtime chosen to run shared framework applications, as detailed in the article on [.NET Core version selection](selection.md).</span></span>

## <a name="should-i-remove-a-version"></a><span data-ttu-id="aec18-106">バージョンを削除する必要はあるか</span><span class="sxs-lookup"><span data-stu-id="aec18-106">Should I remove a version?</span></span>

<span data-ttu-id="aec18-107">[.NET Core バージョン選択](selection.md)動作および更新プログラム間での .NET Core のランタイム互換性により、以前のバージョンを安全に削除することができます。</span><span class="sxs-lookup"><span data-stu-id="aec18-107">The [.NET Core version selection](selection.md) behaviors and the runtime compatibility of .NET Core across updates enables safe removal of previous versions.</span></span> <span data-ttu-id="aec18-108">1\.x や 2.x などのメジャー バージョン 'バンド' 内で .NET Core ランタイム更新プログラムは互換性があります。</span><span class="sxs-lookup"><span data-stu-id="aec18-108">.NET Core runtime updates are compatible within a major version 'band' such as 1.x and 2.x.</span></span> <span data-ttu-id="aec18-109">さらに、.NET Core SDK のより新しいリリースでは、通常、互換性を保ちながら、ランタイムの前バージョンを対象とするアプリケーションをビルドする機能が維持されます。</span><span class="sxs-lookup"><span data-stu-id="aec18-109">Additionally, newer releases of the .NET Core SDK generally maintain the ability to build applications that target previous versions of the runtime in a compatible manner.</span></span>

<span data-ttu-id="aec18-110">通常、必要なのは、ご自分のアプリケーションに必須である最新の SDK および最新のパッチ バージョンのランタイムのみです。</span><span class="sxs-lookup"><span data-stu-id="aec18-110">In general, you only need the latest SDK and latest patch version of the runtimes required for your application.</span></span> <span data-ttu-id="aec18-111">より古い SDK またはランタイムのバージョンが保持されるインスタンスでは、**project.json** ベースのアプリケーションを管理することも含まれます。</span><span class="sxs-lookup"><span data-stu-id="aec18-111">Instances where keeping older SDK or Runtime versions include maintaining **project.json**-based applications.</span></span> <span data-ttu-id="aec18-112">ご利用のアプリケーションには以前の SDK やランタイムを維持する特別な理由がない場合、以前のバージョンを安全に削除することができます。</span><span class="sxs-lookup"><span data-stu-id="aec18-112">Unless your application has specific reasons for earlier SDKs or runtimes, you may safely remove older versions.</span></span>

## <a name="determine-what-is-installed"></a><span data-ttu-id="aec18-113">インストールされている内容を確認する</span><span class="sxs-lookup"><span data-stu-id="aec18-113">Determine what is installed</span></span>

<span data-ttu-id="aec18-114">.NET Core 2.1 以降、ご利用のコンピューターにインストールされている SDK とランタイムのバージョンを一覧表示するのに使用できるオプションが .NET CLI に用意されています。</span><span class="sxs-lookup"><span data-stu-id="aec18-114">Starting with .NET Core 2.1, the .NET CLI has options you can use to list the versions of the SDK and runtime that are installed on your machine.</span></span>  <span data-ttu-id="aec18-115">ご利用のコンピューターにインストールされている SDK を一覧表示するには、[`dotnet --list-sdks`](../tools/dotnet.md#options) を使用します。</span><span class="sxs-lookup"><span data-stu-id="aec18-115">Use [`dotnet --list-sdks`](../tools/dotnet.md#options) to see the list of SDKs installed on your machine.</span></span> <span data-ttu-id="aec18-116">ご利用のコンピューターにインストールされているランタイムを一覧表示するには、[`dotnet --list-runtimes`](../tools/dotnet.md#options) を使用します。</span><span class="sxs-lookup"><span data-stu-id="aec18-116">Use [`dotnet --list-runtimes`](../tools/dotnet.md#options) to see the list of runtimes installed on your machine.</span></span> <span data-ttu-id="aec18-117">次のテキストでは、Windows、macOS、または Linux の典型的な出力が示されています。</span><span class="sxs-lookup"><span data-stu-id="aec18-117">The following text shows typical output for Windows, macOS, or Linux:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="windowstabwindows"></a>[<span data-ttu-id="aec18-118">Windows</span><span class="sxs-lookup"><span data-stu-id="aec18-118">Windows</span></span>](#tab/windows)

```console
C:\> dotnet --list-sdks
2.1.200-preview-007474 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007480 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007509 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007570 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007576 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007587 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007589 [C:\Program Files\dotnet\sdk]
2.1.200 [C:\Program Files\dotnet\sdk]
2.1.201 [C:\Program Files\dotnet\sdk]
2.1.202 [C:\Program Files\dotnet\sdk]
2.1.300-preview2-008533 [C:\Program Files\dotnet\sdk]
2.1.300 [C:\Program Files\dotnet\sdk]
2.1.400-preview-009063 [C:\Program Files\dotnet\sdk]
2.1.400-preview-009088 [C:\Program Files\dotnet\sdk]
2.1.400-preview-009171 [C:\Program Files\dotnet\sdk]

C:\> dotnet --list-runtimes
Microsoft.AspNetCore.All 2.1.0-preview2-final [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.0 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.1 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.2 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.0-preview2-final [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.0 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.1 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.2 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.NETCore.App 2.0.6 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.7 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.9 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0-preview2-26406-04 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.1 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.2 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
```

# <a name="linuxtablinux"></a>[<span data-ttu-id="aec18-119">Linux</span><span class="sxs-lookup"><span data-stu-id="aec18-119">Linux</span></span>](#tab/linux)

```console
$ dotnet --list-sdks
1.0.1 [/usr/share/dotnet/sdk]
1.0.4 [/usr/share/dotnet/sdk]
2.0.0-preview1-005977 [/usr/share/dotnet/sdk]
2.0.0-preview2-006497 [/usr/share/dotnet/sdk]
2.0.0 [/usr/share/dotnet/sdk]
2.1.4 [/usr/share/dotnet/sdk]
2.1.300-preview2-008530 [/usr/share/dotnet/sdk]
2.1.300 [/usr/share/dotnet/sdk]
2.1.301 [/usr/share/dotnet/sdk]

$ dotnet --list-runtimes
Microsoft.AspNetCore.All 2.1.0-preview2-final [/usr/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.0 [/usr/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.1 [/usr/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.0-preview2-final [/usr/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.0 [/usr/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.1 [/usr/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.NETCore.App 1.0.4 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.0.5 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.1.1 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.1.2 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0-preview1-002111-00 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0-preview2-25407-01 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.5 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0-preview2-26406-04 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.1 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
```

# <a name="macostabmacos"></a>[<span data-ttu-id="aec18-120">macOS</span><span class="sxs-lookup"><span data-stu-id="aec18-120">macOS</span></span>](#tab/macos)

```console
$ dotnet --list-sdks
1.0.1 [/usr/local/share/dotnet/sdk]
1.0.4 [/usr/local/share/dotnet/sdk]
2.0.0-preview1-005977 [/usr/local/share/dotnet/sdk]
2.0.0-preview2-006497 [/usr/local/share/dotnet/sdk]
2.0.0 [/usr/local/share/dotnet/sdk]
2.1.4 [/usr/local/share/dotnet/sdk]
2.1.300-preview2-008530 [/usr/local/share/dotnet/sdk]
2.1.300 [/usr/local/share/dotnet/sdk]
2.1.301 [/usr/local/share/dotnet/sdk]

$ dotnet --list-runtimes
Microsoft.AspNetCore.All 2.1.0-preview2-final [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.1 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.0-preview2-final [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.1 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.NETCore.App 1.0.4 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.0.5 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.1.1 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.1.2 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0-preview1-002111-00 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0-preview2-25407-01 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.5 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0-preview2-26406-04 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.1 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
```

---

## <a name="uninstall-net-core"></a><span data-ttu-id="aec18-121">.NET Core のアンインストール</span><span class="sxs-lookup"><span data-stu-id="aec18-121">Uninstall .NET Core</span></span>

# <a name="windowstabwindows"></a>[<span data-ttu-id="aec18-122">Windows</span><span class="sxs-lookup"><span data-stu-id="aec18-122">Windows</span></span>](#tab/windows)

<span data-ttu-id="aec18-123">.NET Core では、Windows の **[プログラムの追加と削除]** ダイアログを使用して .NET Core ランタイムと SDK のバージョンを削除できます。</span><span class="sxs-lookup"><span data-stu-id="aec18-123">.NET Core uses the Windows **Add/Remove Programs** dialog to remove versions of the .NET Core runtime and SDK.</span></span> <span data-ttu-id="aec18-124">次の図では、 **[プログラムの追加と削除]** ダイアログに、インストールされている .NET ランタイムと SDK の複数のバージョンが表示されています。</span><span class="sxs-lookup"><span data-stu-id="aec18-124">The following figure shows the **Add/Remove Programs** dialog with several versions of the .NET runtime and SDK installed.</span></span>

![.NET Core を削除するための [プログラムの追加と削除]](./media/remove-runtime-sdk-versions/programs-and-features.png)

<span data-ttu-id="aec18-126">ご利用のコンピューターから削除する任意のバージョンを選択して、 **[アンインストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aec18-126">Select any versions you want to remove from your machine and click **Uninstall**.</span></span>

# <a name="linuxtablinux"></a>[<span data-ttu-id="aec18-127">Linux</span><span class="sxs-lookup"><span data-stu-id="aec18-127">Linux</span></span>](#tab/linux)

<span data-ttu-id="aec18-128">さらに Linux 上で .NET Core (SDK またはランタイムのいずれか) をアンインストールするオプションもあります。</span><span class="sxs-lookup"><span data-stu-id="aec18-128">There are more options to uninstall .NET Core (either SDK or runtime) on Linux.</span></span> <span data-ttu-id="aec18-129">.NET Core をアンインストールするには、.NET Core をインストールするときに使用したアクションをミラー化することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="aec18-129">The best way for you to uninstall .NET Core is to mirror the action you used to install .NET Core.</span></span> <span data-ttu-id="aec18-130">詳細は、選択した配布方法とインストール方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="aec18-130">The specifics depend on your chosen distribution and the installation method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aec18-131">Red Hat インストールの場合、.NET Core のインストールとアンインストールについては、[Red Hat ファースト ステップ ガイド](https://access.redhat.com/documentation/en-us/net_core/2.0/html/getting_started_guide/gs_install_dotnet#install_register_rehel) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aec18-131">For Red Hat installations, consult the [Red Hat Getting Started Guide](https://access.redhat.com/documentation/en-us/net_core/2.0/html/getting_started_guide/gs_install_dotnet#install_register_rehel) for information on installing and uninstalling .NET Core.</span></span>

<span data-ttu-id="aec18-132">.NET Core 2.1 以降では、パッケージ マネージャーを使用して .NET Core SDK をアップグレードする場合、それをアンインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="aec18-132">Starting with .NET Core 2.1, there's no need to uninstall the .NET Core SDK when upgrading it using a package manager.</span></span> <span data-ttu-id="aec18-133">パッケージ マネージャーの `update` または `refresh` コマンドでは、新しいバージョンが正常にインストールされると、古いバージョンが自動的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="aec18-133">The package manager `update` or `refresh` commands will automatically remove the older version upon the successful installation of a newer version.</span></span>

<span data-ttu-id="aec18-134">パッケージ マネージャーを使用して .NET Core をインストールした場合は、それと同じパッケージ マネージャーを使用して .NET SDK またはランタイムをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="aec18-134">If you installed .NET Core using a package manager, you use that same package manager to uninstall .NET SDK or runtime.</span></span> <span data-ttu-id="aec18-135">.NET Core インストールでは、最も一般的なパッケージ マネージャーがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="aec18-135">.NET Core installations support most popular package managers.</span></span> <span data-ttu-id="aec18-136">ご利用の環境内での正確な構文については、ご利用の配布のパッケージ マネージャーのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="aec18-136">Consult the documentation for your distribution's package manager for the precise syntax on your environment:</span></span>

- <span data-ttu-id="aec18-137">[apt-get(8)](https://linux.die.net/man/8/apt-get) は、Ubuntu などの Debian ベースのシステムによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="aec18-137">[apt-get(8)](https://linux.die.net/man/8/apt-get) is used by Debian based systems, including Ubuntu.</span></span>
- <span data-ttu-id="aec18-138">[yum(8)](https://linux.die.net/man/8/yum) は、Fedora、CentOS、Oracle Linux 上で使用されます。</span><span class="sxs-lookup"><span data-stu-id="aec18-138">[yum(8)](https://linux.die.net/man/8/yum) is used on Fedora, CentOS, and Oracle Linux.</span></span>
- <span data-ttu-id="aec18-139">[zypper(8)](https://en.opensuse.org/SDB:Zypper_manual_(plain)) は、openSUSE および SUSE Linux Enterprise System (SLES) 上で使用されます。</span><span class="sxs-lookup"><span data-stu-id="aec18-139">[zypper(8)](https://en.opensuse.org/SDB:Zypper_manual_(plain)) is used on openSUSE and SUSE Linux Enterprise System (SLES).</span></span>
- <span data-ttu-id="aec18-140">[dnf(8)](https://dnf.readthedocs.io/en/latest/command_ref.html) は、Fedora 上で使用されます。</span><span class="sxs-lookup"><span data-stu-id="aec18-140">[dnf(8)](https://dnf.readthedocs.io/en/latest/command_ref.html) is used on Fedora.</span></span>

<span data-ttu-id="aec18-141">ほとんどの場合、パッケージを削除するコマンドは `remove` となります。</span><span class="sxs-lookup"><span data-stu-id="aec18-141">In almost all cases, the command to remove a package is `remove`.</span></span>

<span data-ttu-id="aec18-142">ほとんどのパッケージ マネージャーの場合、.NET Core SDK インストールのパッケージ名は `dotnet-sdk` であり、その後にバージョン番号が続きます。</span><span class="sxs-lookup"><span data-stu-id="aec18-142">The package name for the .NET Core SDK installation for most package managers is `dotnet-sdk`, followed by the version number.</span></span> <span data-ttu-id="aec18-143">.NET Core SDK のバージョン 2.1.300 およびランタイムのバージョン `2.1` 以降は、メジャーおよびマイナーのバージョン番号のみ必要です。たとえば、.NET Core SDK バージョン 2.1.300 は、パッケージ `dotnet-sdk-2.1` として参照できます。</span><span class="sxs-lookup"><span data-stu-id="aec18-143">Starting with the version 2.1.300 of the .NET Core SDK and version `2.1` of the runtime, only the major and minor version numbers are necessary: for example, the .NET Core SDK version 2.1.300 can be referenced as the package `dotnet-sdk-2.1`.</span></span> <span data-ttu-id="aec18-144">以前のバージョンでは、バージョン文字列全体が必須です。たとえば、.NET Core SDK のバージョン 2.1.200 の場合は `dotnet-sdk-2.1.200` が必須となります。</span><span class="sxs-lookup"><span data-stu-id="aec18-144">Prior versions require the entire version string: for example, `dotnet-sdk-2.1.200` would be required for version 2.1.200 of the .NET Core SDK.</span></span>

<span data-ttu-id="aec18-145">ランタイムのみがインストールされ、SDK はインストールされていないコンピューターの場合、.NET Core ランタイムのパッケージ名は `dotnet-runtime-<version>` となり、ランタイム スタック全体のパッケージ名は `aspnetcore-runtime-<version>` となります。</span><span class="sxs-lookup"><span data-stu-id="aec18-145">For machines that have installed only the runtime, and not the SDK, the package name is `dotnet-runtime-<version>` for the .NET Core runtime, and `aspnetcore-runtime-<version>` for the entire runtime stack.</span></span>

<span data-ttu-id="aec18-146">2\.0 より前の .NET Core インストールでは、パッケージ マネージャーを使用して SDK をアンインストールしたとき、ホスト アプリケーションはアンインストールされませんでした。</span><span class="sxs-lookup"><span data-stu-id="aec18-146">.NET Core installations earlier than 2.0 didn't uninstall the host application when the SDK was uninstalled using the package manager.</span></span> <span data-ttu-id="aec18-147">`apt-get` を使用する場合、コマンドは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="aec18-147">Using `apt-get`, the command is:</span></span>

```bash
apt-get remove dotnet-host
```

<span data-ttu-id="aec18-148">`dotnet-host` にはバージョンが添えられていないことに注目してください。</span><span class="sxs-lookup"><span data-stu-id="aec18-148">Note that there's no version attached to `dotnet-host`.</span></span>

<span data-ttu-id="aec18-149">tarball を使用してインストールした場合、.NET Core の削除は手動で行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="aec18-149">If you installed using a tarball, you must remove .NET Core using the manual method.</span></span>

<span data-ttu-id="aec18-150">SDK とランタイムを別々に削除するには、該当するバージョンを含むディレクトリを削除します。</span><span class="sxs-lookup"><span data-stu-id="aec18-150">You remove the SDKs and runtimes separately, by removing the directory that contains that version.</span></span> <span data-ttu-id="aec18-151">たとえば、1.0.1 SDK とランタイムを削除するには、次の bash コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="aec18-151">For example, to remove the 1.0.1 SDK and runtime, you would use the following bash commands:</span></span>

```bash
sudo rm -rf /usr/share/dotnet/sdk/1.0.1
sudo rm -rf /usr/share/dotnet/shared/Microsoft.NETCore.App/1.0.1
sudo rm -rf /usr/share/dotnet/shared/Microsoft.AspNetCore.App/1.0.1
sudo rm -rf /usr/share/dotnet/host/fxr/1.0.1
```

<span data-ttu-id="aec18-152">上記の表に示したように、SDK とランタイムの親ディレクトリは、`dotnet --list-sdks` コマンドおよび `dotnet --list-runtimes` コマンドからの出力に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="aec18-152">The parent directories for the SDK and runtime are listed in the output from the `dotnet --list-sdks` and `dotnet --list-runtimes` command, as shown in the earlier table.</span></span>

# <a name="macostabmacos"></a>[<span data-ttu-id="aec18-153">macOS</span><span class="sxs-lookup"><span data-stu-id="aec18-153">macOS</span></span>](#tab/macos)

<span data-ttu-id="aec18-154">Mac 上では、SDK とランタイムを別々に削除する必要があります。そのためには、該当するバージョンを含むディレクトリを削除します。</span><span class="sxs-lookup"><span data-stu-id="aec18-154">On Mac, you must remove the SDKs and runtimes separately, by removing the directory that contains that version.</span></span> <span data-ttu-id="aec18-155">たとえば、1.0.1 SDK とランタイムを削除するには、次の bash コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="aec18-155">For example, to remove the 1.0.1 SDK and runtime, you would use the following bash commands:</span></span>

```bash
sudo rm -rf /usr/local/share/dotnet/sdk/1.0.1
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.NETCore.App/1.0.1
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.AspNetCore.App/1.0.1
sudo rm -rf /usr/local/share/dotnet/host/fxr/1.0.1
```

<span data-ttu-id="aec18-156">上記の表に示したように、SDK とランタイムの親ディレクトリは、`dotnet --list-sdks` コマンドおよび `dotnet --list-runtimes` コマンドからの出力に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="aec18-156">The parent directories for the SDK and runtime are listed in the output from the `dotnet --list-sdks` and `dotnet --list-runtimes` command, as shown in the earlier table.</span></span>

---

## <a name="net-core-uninstall-tool"></a><span data-ttu-id="aec18-157">.NET Core アンインストール ツール</span><span class="sxs-lookup"><span data-stu-id="aec18-157">.NET Core Uninstall Tool</span></span>

<span data-ttu-id="aec18-158">[.NET Core アンインストール ツール](../additional-tools/uninstall-tool.md) (`dotnet-core-uninstall`) を使用すると、.NET Core SDK とランタイムをシステムから削除できます。</span><span class="sxs-lookup"><span data-stu-id="aec18-158">The [.NET Core Uninstall Tool](../additional-tools/uninstall-tool.md) (`dotnet-core-uninstall`) lets you remove .NET Core SDKs and runtimes from a system.</span></span> <span data-ttu-id="aec18-159">一連のオプションを使用して、アンインストールするバージョンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="aec18-159">A collection of options is available to specify which versions should be uninstalled.</span></span>

## <a name="visual-studio-dependency-on-net-core-sdk-versions"></a><span data-ttu-id="aec18-160">.NET Core SDK バージョンに対する Visual Studio の依存関係</span><span class="sxs-lookup"><span data-stu-id="aec18-160">Visual Studio dependency on .NET Core SDK versions</span></span>

<span data-ttu-id="aec18-161">Visual Studio 2019 バージョン 16.3 より前では、Visual Studio インストーラーはスタンドアロンの .NET Core SDK インストーラーを呼び出しました。</span><span class="sxs-lookup"><span data-stu-id="aec18-161">Before Visual Studio 2019 version 16.3, Visual Studio installers called the standalone .NET Core SDK installer.</span></span> <span data-ttu-id="aec18-162">その結果、Windows の **[プログラムの追加と削除]** ダイアログに SDK のバージョンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="aec18-162">As a result, the SDK versions appear in the Windows **Add/Remove Programs** dialog.</span></span> <span data-ttu-id="aec18-163">スタンドアロン インストーラーを使用して Visual Studio によってインストールされた .NET Core SDK を削除すると、Visual Studio が破損する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="aec18-163">Removing .NET Core SDKs that were installed by Visual Studio using the standalone installer may break Visual Studio.</span></span> <span data-ttu-id="aec18-164">SDK をアンインストールした後に Visual Studio で問題が発生した場合は、その特定のバージョンの Visual Studio で [修復] を実行します。</span><span class="sxs-lookup"><span data-stu-id="aec18-164">If Visual Studio has problems after you uninstall SDKs, run Repair on that specific version of Visual Studio.</span></span> <span data-ttu-id="aec18-165">次の表に、.NET Core SDK バージョンに対する Visual Studio の依存関係の一部を示します。</span><span class="sxs-lookup"><span data-stu-id="aec18-165">The following table shows some of the Visual Studio dependencies on .NET Core SDK versions:</span></span>

| <span data-ttu-id="aec18-166">Visual Studio のバージョン</span><span class="sxs-lookup"><span data-stu-id="aec18-166">Visual Studio version</span></span> | <span data-ttu-id="aec18-167">.NET Core SDK のバージョン</span><span class="sxs-lookup"><span data-stu-id="aec18-167">.NET Core SDK version</span></span> |
| -- | -- |
| <span data-ttu-id="aec18-168">Visual Studio 2019 バージョン 16.2</span><span class="sxs-lookup"><span data-stu-id="aec18-168">Visual Studio 2019 version 16.2</span></span> | <span data-ttu-id="aec18-169">.NET Core SDK 2.2.4xx、2.1.8xx</span><span class="sxs-lookup"><span data-stu-id="aec18-169">.NET Core SDK 2.2.4xx, 2.1.8xx</span></span> |
| <span data-ttu-id="aec18-170">Visual Studio 2019 バージョン 16.1</span><span class="sxs-lookup"><span data-stu-id="aec18-170">Visual Studio 2019 version 16.1</span></span> | <span data-ttu-id="aec18-171">.NET Core SDK 2.2.3xx、2.1.7xx</span><span class="sxs-lookup"><span data-stu-id="aec18-171">.NET Core SDK 2.2.3xx, 2.1.7xx</span></span> |
| <span data-ttu-id="aec18-172">Visual Studio 2019 バージョン 16.0</span><span class="sxs-lookup"><span data-stu-id="aec18-172">Visual Studio 2019 version 16.0</span></span> | <span data-ttu-id="aec18-173">.NET Core SDK 2.2.2xx、2.1.6xx</span><span class="sxs-lookup"><span data-stu-id="aec18-173">.NET Core SDK 2.2.2xx, 2.1.6xx</span></span> |
| <span data-ttu-id="aec18-174">Visual Studio 2017 バージョン 15.9</span><span class="sxs-lookup"><span data-stu-id="aec18-174">Visual Studio 2017 version 15.9</span></span> | <span data-ttu-id="aec18-175">.NET Core SDK 2.2.1xx、2.1.5xx</span><span class="sxs-lookup"><span data-stu-id="aec18-175">.NET Core SDK 2.2.1xx, 2.1.5xx</span></span> |
| <span data-ttu-id="aec18-176">Visual Studio 2017 バージョン 15.8</span><span class="sxs-lookup"><span data-stu-id="aec18-176">Visual Studio 2017 version 15.8</span></span> | <span data-ttu-id="aec18-177">.NET Core SDK 2.1.4xx</span><span class="sxs-lookup"><span data-stu-id="aec18-177">.NET Core SDK 2.1.4xx</span></span> |

<span data-ttu-id="aec18-178">Visual Studio 2019 バージョン 16.3 以降では、Visual Studio によって .NET Core SDK の独自のコピーが管理されます。</span><span class="sxs-lookup"><span data-stu-id="aec18-178">Starting with Visual Studio 2019 version 16.3, Visual Studio is in charge of its own copy of the .NET Core SDK.</span></span> <span data-ttu-id="aec18-179">そのため、 **[プログラムの追加と削除]** ダイアログにこれらの SDK バージョンが表示されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="aec18-179">For that reason, you no longer see those SDK versions in the **Add/Remove Programs** dialog.</span></span>

## <a name="remove-the-nuget-fallback-folder"></a><span data-ttu-id="aec18-180">NuGet フォールバック フォルダーの削除</span><span class="sxs-lookup"><span data-stu-id="aec18-180">Remove the NuGet fallback folder</span></span>

<span data-ttu-id="aec18-181">.NET Core 3.0 SDK より前では、.NET Core SDK インストーラーは *NuGetFallbackFolder* を使用して、NuGet パッケージのキャッシュを格納していました。</span><span class="sxs-lookup"><span data-stu-id="aec18-181">Before .NET Core 3.0 SDK, the .NET Core SDK installers used the *NuGetFallbackFolder* to store a cache of NuGet packages.</span></span> <span data-ttu-id="aec18-182">このキャッシュは、`dotnet restore` や `dotnet build /t:Restore` などの操作中に使用されました。</span><span class="sxs-lookup"><span data-stu-id="aec18-182">This cache was used during operations such as `dotnet restore` or `dotnet build /t:Restore`.</span></span> <span data-ttu-id="aec18-183">`NuGetFallbackFolder` は、Windows では *C:\Program Files\dotnet\sdk* に、macOS では */usr/local/share/dotnet/sdk* にあります。</span><span class="sxs-lookup"><span data-stu-id="aec18-183">The `NuGetFallbackFolder` is located at *C:\Program Files\dotnet\sdk* on Windows and at */usr/local/share/dotnet/sdk* on macOS.</span></span>

<span data-ttu-id="aec18-184">次の場合は、このフォルダーを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="aec18-184">You may want to remove this folder, if:</span></span>

* <span data-ttu-id="aec18-185">.NET Core 3.0 SDK 以降のバージョンのみを使用して開発している。</span><span class="sxs-lookup"><span data-stu-id="aec18-185">You're only developing using .NET Core 3.0 SDK or later versions.</span></span>
* <span data-ttu-id="aec18-186">3\.0 より前の .NET Core SDK のバージョンを使用して開発しているが、オンラインで作業することができ、処理が遅くなることがある。</span><span class="sxs-lookup"><span data-stu-id="aec18-186">You're developing using .NET Core SDK versions earlier than 3.0, but you can work online and things can be slower once.</span></span>

<span data-ttu-id="aec18-187">NuGet フォールバック フォルダーを削除する場合は、管理者特権が必要になります。</span><span class="sxs-lookup"><span data-stu-id="aec18-187">If you want to remove the NuGet fallback folder, you can delete it, but you'll need admin privileges to do so.</span></span>

<span data-ttu-id="aec18-188">*dotnet* フォルダーの削除はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="aec18-188">It's not recommended to delete the *dotnet* folder.</span></span> <span data-ttu-id="aec18-189">これを行うと、以前にインストールしたグローバル ツールがすべて削除されます。</span><span class="sxs-lookup"><span data-stu-id="aec18-189">Doing so would remove any global tools you've previously installed.</span></span> <span data-ttu-id="aec18-190">また、Windows の場合は、次のことが発生します。</span><span class="sxs-lookup"><span data-stu-id="aec18-190">Also, on Windows:</span></span>

- <span data-ttu-id="aec18-191">Visual Studio 2019 バージョン 16.3 以降のバージョンが破損します。</span><span class="sxs-lookup"><span data-stu-id="aec18-191">You'll break Visual Studio 2019 version 16.3 and later versions.</span></span> <span data-ttu-id="aec18-192">**[修復]** を実行して回復できます。</span><span class="sxs-lookup"><span data-stu-id="aec18-192">You can run **Repair** to recover.</span></span>
- <span data-ttu-id="aec18-193">**[プログラムの追加と削除]** ダイアログに .NET Core SDK エントリがある場合、それらは孤立状態になります。</span><span class="sxs-lookup"><span data-stu-id="aec18-193">If there are .NET Core SDK entries in the **Add/Remove Programs** dialog, they'll be orphaned.</span></span>
