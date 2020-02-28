---
title: .NET Core ランタイムと SDK を削除する
description: この記事では、現在インストールされている .NET Core ランタイムと SDK のバージョンを確認する方法と、Windows、Mac、および Linux でそれらを削除する方法について説明します。
ms.date: 12/17/2019
author: billwagner
ms.author: wiwagn
ms.custom: updateeachrelease
ms.openlocfilehash: 71c11825981c6259a779e1ac8f947a41618e922d
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503469"
---
# <a name="how-to-remove-the-net-core-runtime-and-sdk"></a><span data-ttu-id="bfcf6-103">.NET Core ランタイムと SDK を削除する方法</span><span class="sxs-lookup"><span data-stu-id="bfcf6-103">How to remove the .NET Core Runtime and SDK</span></span>

<span data-ttu-id="bfcf6-104">時間の経過に伴い、.NET Core ランタイムと SDK の更新バージョンをインストールした場合は、ご利用のコンピューターから古いバージョンの .NET Core を削除することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-104">Over time, as you install updated versions of the .NET Core runtime and SDK, you may want to remove outdated versions of .NET Core from your machine.</span></span> <span data-ttu-id="bfcf6-105">ランタイムの古いバージョンを削除すると、共有のフレームワーク アプリケーションを実行するように選択されているランタイムが変更される可能性があります。詳細については、「[.NET Core のバージョンの選択](selection.md)」の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-105">Removing older versions of the runtime may change the runtime chosen to run shared framework applications, as detailed in the article on [.NET Core version selection](selection.md).</span></span>

## <a name="should-i-remove-a-version"></a><span data-ttu-id="bfcf6-106">バージョンを削除する必要はあるか</span><span class="sxs-lookup"><span data-stu-id="bfcf6-106">Should I remove a version?</span></span>

<span data-ttu-id="bfcf6-107">[.NET Core バージョン選択](selection.md)動作および更新プログラム間での .NET Core のランタイム互換性により、以前のバージョンを安全に削除することができます。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-107">The [.NET Core version selection](selection.md) behaviors and the runtime compatibility of .NET Core across updates enables safe removal of previous versions.</span></span> <span data-ttu-id="bfcf6-108">1\.x や 2.x などのメジャー バージョン 'バンド' 内で .NET Core ランタイム更新プログラムは互換性があります。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-108">.NET Core runtime updates are compatible within a major version 'band' such as 1.x and 2.x.</span></span> <span data-ttu-id="bfcf6-109">さらに、.NET Core SDK のより新しいリリースでは、通常、互換性を保ちながら、ランタイムの前バージョンを対象とするアプリケーションをビルドする機能が維持されます。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-109">Additionally, newer releases of the .NET Core SDK generally maintain the ability to build applications that target previous versions of the runtime in a compatible manner.</span></span>

<span data-ttu-id="bfcf6-110">通常、必要なのは、ご自分のアプリケーションに必須である最新の SDK および最新のパッチ バージョンのランタイムのみです。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-110">In general, you only need the latest SDK and latest patch version of the runtimes required for your application.</span></span> <span data-ttu-id="bfcf6-111">より古い SDK またはランタイムのバージョンが保持されるインスタンスでは、**project.json** ベースのアプリケーションを管理することも含まれます。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-111">Instances where keeping older SDK or Runtime versions include maintaining **project.json**-based applications.</span></span> <span data-ttu-id="bfcf6-112">ご利用のアプリケーションには以前の SDK やランタイムを維持する特別な理由がない場合、以前のバージョンを安全に削除することができます。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-112">Unless your application has specific reasons for earlier SDKs or runtimes, you may safely remove older versions.</span></span>

## <a name="determine-what-is-installed"></a><span data-ttu-id="bfcf6-113">インストールされている内容を確認する</span><span class="sxs-lookup"><span data-stu-id="bfcf6-113">Determine what is installed</span></span>

<span data-ttu-id="bfcf6-114">.NET Core 2.1 以降、ご利用のコンピューターにインストールされている SDK とランタイムのバージョンを一覧表示するのに使用できるオプションが .NET CLI に用意されています。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-114">Starting with .NET Core 2.1, the .NET CLI has options you can use to list the versions of the SDK and runtime that are installed on your machine.</span></span>  <span data-ttu-id="bfcf6-115">ご利用のコンピューターにインストールされている SDK を一覧表示するには、[`dotnet --list-sdks`](../tools/dotnet.md#options) を使用します。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-115">Use [`dotnet --list-sdks`](../tools/dotnet.md#options) to see the list of SDKs installed on your machine.</span></span> <span data-ttu-id="bfcf6-116">ご利用のコンピューターにインストールされているランタイムを一覧表示するには、[`dotnet --list-runtimes`](../tools/dotnet.md#options) を使用します。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-116">Use [`dotnet --list-runtimes`](../tools/dotnet.md#options) to see the list of runtimes installed on your machine.</span></span> <span data-ttu-id="bfcf6-117">次のテキストでは、Windows、macOS、または Linux の典型的な出力が示されています。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-117">The following text shows typical output for Windows, macOS, or Linux:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="windows"></a>[<span data-ttu-id="bfcf6-118">Windows</span><span class="sxs-lookup"><span data-stu-id="bfcf6-118">Windows</span></span>](#tab/windows)

<span data-ttu-id="bfcf6-119">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-119">By running the following command:</span></span>

```dotnetcli
dotnet --list-sdks
```

<span data-ttu-id="bfcf6-120">次のような出力が得られます。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-120">You get output similar to the following:</span></span>

```console
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
```

<span data-ttu-id="bfcf6-121">または、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-121">And by running the following command:</span></span>

```dotnetcli
dotnet --list-runtimes
```

<span data-ttu-id="bfcf6-122">次のような出力が得られます。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-122">You get output similar to the following:</span></span>

```console
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

# <a name="linux"></a>[<span data-ttu-id="bfcf6-123">Linux</span><span class="sxs-lookup"><span data-stu-id="bfcf6-123">Linux</span></span>](#tab/linux)

<span data-ttu-id="bfcf6-124">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-124">By running the following command:</span></span>

```dotnetcli
dotnet --list-sdks
```

<span data-ttu-id="bfcf6-125">次のような出力が得られます。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-125">You get output similar to the following:</span></span>

```console
1.0.1 [/usr/share/dotnet/sdk]
1.0.4 [/usr/share/dotnet/sdk]
2.0.0-preview1-005977 [/usr/share/dotnet/sdk]
2.0.0-preview2-006497 [/usr/share/dotnet/sdk]
2.0.0 [/usr/share/dotnet/sdk]
2.1.4 [/usr/share/dotnet/sdk]
2.1.300-preview2-008530 [/usr/share/dotnet/sdk]
2.1.300 [/usr/share/dotnet/sdk]
2.1.301 [/usr/share/dotnet/sdk]
```

<span data-ttu-id="bfcf6-126">または、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-126">And by running the following command:</span></span>

```dotnetcli
dotnet --list-runtimes
```

<span data-ttu-id="bfcf6-127">次のような出力が得られます。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-127">You get output similar to the following:</span></span>

```console
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

# <a name="macos"></a>[<span data-ttu-id="bfcf6-128">macOS</span><span class="sxs-lookup"><span data-stu-id="bfcf6-128">macOS</span></span>](#tab/macos)

<span data-ttu-id="bfcf6-129">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-129">By running the following command:</span></span>

```dotnetcli
dotnet --list-sdks
```

<span data-ttu-id="bfcf6-130">次のような出力が得られます。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-130">You get output similar to the following:</span></span>

```console
1.0.1 [/usr/local/share/dotnet/sdk]
1.0.4 [/usr/local/share/dotnet/sdk]
2.0.0-preview1-005977 [/usr/local/share/dotnet/sdk]
2.0.0-preview2-006497 [/usr/local/share/dotnet/sdk]
2.0.0 [/usr/local/share/dotnet/sdk]
2.1.4 [/usr/local/share/dotnet/sdk]
2.1.300-preview2-008530 [/usr/local/share/dotnet/sdk]
2.1.300 [/usr/local/share/dotnet/sdk]
2.1.301 [/usr/local/share/dotnet/sdk]
```

<span data-ttu-id="bfcf6-131">または、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-131">And by running the following command:</span></span>

```dotnetcli
dotnet --list-runtimes
```

<span data-ttu-id="bfcf6-132">次のような出力が得られます。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-132">You get output similar to the following:</span></span>

```console
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

## <a name="uninstall-net-core"></a><span data-ttu-id="bfcf6-133">.NET Core のアンインストール</span><span class="sxs-lookup"><span data-stu-id="bfcf6-133">Uninstall .NET Core</span></span>

# <a name="windows"></a>[<span data-ttu-id="bfcf6-134">Windows</span><span class="sxs-lookup"><span data-stu-id="bfcf6-134">Windows</span></span>](#tab/windows)

<span data-ttu-id="bfcf6-135">.NET Core では、Windows の **[プログラムの追加と削除]** ダイアログを使用して .NET Core ランタイムと SDK のバージョンを削除できます。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-135">.NET Core uses the Windows **Add/Remove Programs** dialog to remove versions of the .NET Core runtime and SDK.</span></span> <span data-ttu-id="bfcf6-136">次の図では、 **[プログラムの追加と削除]** ダイアログに、インストールされている .NET ランタイムと SDK の複数のバージョンが表示されています。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-136">The following figure shows the **Add/Remove Programs** dialog with several versions of the .NET runtime and SDK installed.</span></span>

![.NET Core を削除するための [プログラムの追加と削除]](./media/remove-runtime-sdk-versions/programs-and-features.png)

<span data-ttu-id="bfcf6-138">ご利用のコンピューターから削除する任意のバージョンを選択して、 **[アンインストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-138">Select any versions you want to remove from your machine and click **Uninstall**.</span></span>

# <a name="linux"></a>[<span data-ttu-id="bfcf6-139">Linux</span><span class="sxs-lookup"><span data-stu-id="bfcf6-139">Linux</span></span>](#tab/linux)

<span data-ttu-id="bfcf6-140">さらに Linux 上で .NET Core (SDK またはランタイムのいずれか) をアンインストールするオプションもあります。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-140">There are more options to uninstall .NET Core (either SDK or runtime) on Linux.</span></span> <span data-ttu-id="bfcf6-141">.NET Core をアンインストールするには、.NET Core をインストールするときに使用したアクションをミラー化することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-141">The best way for you to uninstall .NET Core is to mirror the action you used to install .NET Core.</span></span> <span data-ttu-id="bfcf6-142">詳細は、選択した配布方法とインストール方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-142">The specifics depend on your chosen distribution and the installation method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bfcf6-143">Red Hat インストールの場合、.NET Core のインストールとアンインストールについては、[Red Hat ファースト ステップ ガイド](https://access.redhat.com/documentation/en-us/net_core/2.0/html/getting_started_guide/gs_install_dotnet#install_register_rehel) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-143">For Red Hat installations, consult the [Red Hat Getting Started Guide](https://access.redhat.com/documentation/en-us/net_core/2.0/html/getting_started_guide/gs_install_dotnet#install_register_rehel) for information on installing and uninstalling .NET Core.</span></span>

<span data-ttu-id="bfcf6-144">.NET Core 2.1 以降では、パッケージ マネージャーを使用して .NET Core SDK をアップグレードする場合、それをアンインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-144">Starting with .NET Core 2.1, there's no need to uninstall the .NET Core SDK when upgrading it using a package manager.</span></span> <span data-ttu-id="bfcf6-145">パッケージ マネージャーの `update` または `refresh` コマンドでは、新しいバージョンが正常にインストールされると、古いバージョンが自動的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-145">The package manager `update` or `refresh` commands will automatically remove the older version upon the successful installation of a newer version.</span></span>

<span data-ttu-id="bfcf6-146">パッケージ マネージャーを使用して .NET Core をインストールした場合は、それと同じパッケージ マネージャーを使用して .NET SDK またはランタイムをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-146">If you installed .NET Core using a package manager, you use that same package manager to uninstall .NET SDK or runtime.</span></span> <span data-ttu-id="bfcf6-147">.NET Core インストールでは、最も一般的なパッケージ マネージャーがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-147">.NET Core installations support most popular package managers.</span></span> <span data-ttu-id="bfcf6-148">ご利用の環境内での正確な構文については、ご利用の配布のパッケージ マネージャーのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-148">Consult the documentation for your distribution's package manager for the precise syntax on your environment:</span></span>

- <span data-ttu-id="bfcf6-149">[apt-get(8)](https://linux.die.net/man/8/apt-get) は、Ubuntu などの Debian ベースのシステムによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-149">[apt-get(8)](https://linux.die.net/man/8/apt-get) is used by Debian based systems, including Ubuntu.</span></span>
- <span data-ttu-id="bfcf6-150">[yum(8)](https://linux.die.net/man/8/yum) は、Fedora、CentOS、Oracle Linux 上で使用されます。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-150">[yum(8)](https://linux.die.net/man/8/yum) is used on Fedora, CentOS, and Oracle Linux.</span></span>
- <span data-ttu-id="bfcf6-151">[zypper(8)](https://en.opensuse.org/SDB:Zypper_manual_(plain)) は、openSUSE および SUSE Linux Enterprise System (SLES) 上で使用されます。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-151">[zypper(8)](https://en.opensuse.org/SDB:Zypper_manual_(plain)) is used on openSUSE and SUSE Linux Enterprise System (SLES).</span></span>
- <span data-ttu-id="bfcf6-152">[dnf(8)](https://dnf.readthedocs.io/en/latest/command_ref.html) は、Fedora 上で使用されます。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-152">[dnf(8)](https://dnf.readthedocs.io/en/latest/command_ref.html) is used on Fedora.</span></span>

<span data-ttu-id="bfcf6-153">ほとんどの場合、パッケージを削除するコマンドは `remove` となります。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-153">In almost all cases, the command to remove a package is `remove`.</span></span>

<span data-ttu-id="bfcf6-154">ほとんどのパッケージ マネージャーの場合、.NET Core SDK インストールのパッケージ名は `dotnet-sdk` であり、その後にバージョン番号が続きます。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-154">The package name for the .NET Core SDK installation for most package managers is `dotnet-sdk`, followed by the version number.</span></span> <span data-ttu-id="bfcf6-155">.NET Core SDK のバージョン 2.1.300 およびランタイムのバージョン `2.1` 以降は、メジャーおよびマイナーのバージョン番号のみ必要です。たとえば、.NET Core SDK バージョン 2.1.300 は、パッケージ `dotnet-sdk-2.1` として参照できます。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-155">Starting with the version 2.1.300 of the .NET Core SDK and version `2.1` of the runtime, only the major and minor version numbers are necessary: for example, the .NET Core SDK version 2.1.300 can be referenced as the package `dotnet-sdk-2.1`.</span></span> <span data-ttu-id="bfcf6-156">以前のバージョンでは、バージョン文字列全体が必須です。たとえば、.NET Core SDK のバージョン 2.1.200 の場合は `dotnet-sdk-2.1.200` が必須となります。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-156">Prior versions require the entire version string: for example, `dotnet-sdk-2.1.200` would be required for version 2.1.200 of the .NET Core SDK.</span></span>

<span data-ttu-id="bfcf6-157">ランタイムのみがインストールされ、SDK はインストールされていないコンピューターの場合、.NET Core ランタイムのパッケージ名は `dotnet-runtime-<version>` となり、ランタイム スタック全体のパッケージ名は `aspnetcore-runtime-<version>` となります。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-157">For machines that have installed only the runtime, and not the SDK, the package name is `dotnet-runtime-<version>` for the .NET Core runtime, and `aspnetcore-runtime-<version>` for the entire runtime stack.</span></span>

<span data-ttu-id="bfcf6-158">2\.0 より前の .NET Core インストールでは、パッケージ マネージャーを使用して SDK をアンインストールしたとき、ホスト アプリケーションはアンインストールされませんでした。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-158">.NET Core installations earlier than 2.0 didn't uninstall the host application when the SDK was uninstalled using the package manager.</span></span> <span data-ttu-id="bfcf6-159">`apt-get` を使用する場合、コマンドは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-159">Using `apt-get`, the command is:</span></span>

```bash
apt-get remove dotnet-host
```

<span data-ttu-id="bfcf6-160">`dotnet-host` にはバージョンが添えられていないことに注目してください。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-160">Note that there's no version attached to `dotnet-host`.</span></span>

<span data-ttu-id="bfcf6-161">tarball を使用してインストールした場合、.NET Core の削除は手動で行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-161">If you installed using a tarball, you must remove .NET Core using the manual method.</span></span>

<span data-ttu-id="bfcf6-162">SDK とランタイムを別々に削除するには、該当するバージョンを含むディレクトリを削除します。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-162">You remove the SDKs and runtimes separately, by removing the directory that contains that version.</span></span> <span data-ttu-id="bfcf6-163">たとえば、1.0.1 SDK とランタイムを削除するには、次の bash コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-163">For example, to remove the 1.0.1 SDK and runtime, you would use the following bash commands:</span></span>

```bash
sudo rm -rf /usr/share/dotnet/sdk/1.0.1
sudo rm -rf /usr/share/dotnet/shared/Microsoft.NETCore.App/1.0.1
sudo rm -rf /usr/share/dotnet/shared/Microsoft.AspNetCore.App/1.0.1
sudo rm -rf /usr/share/dotnet/host/fxr/1.0.1
```

<span data-ttu-id="bfcf6-164">上記の表に示したように、SDK とランタイムの親ディレクトリは、`dotnet --list-sdks` コマンドおよび `dotnet --list-runtimes` コマンドからの出力に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-164">The parent directories for the SDK and runtime are listed in the output from the `dotnet --list-sdks` and `dotnet --list-runtimes` command, as shown in the earlier table.</span></span>

# <a name="macos"></a>[<span data-ttu-id="bfcf6-165">macOS</span><span class="sxs-lookup"><span data-stu-id="bfcf6-165">macOS</span></span>](#tab/macos)

<span data-ttu-id="bfcf6-166">Mac 上では、SDK とランタイムを別々に削除する必要があります。そのためには、該当するバージョンを含むディレクトリを削除します。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-166">On Mac, you must remove the SDKs and runtimes separately, by removing the directory that contains that version.</span></span> <span data-ttu-id="bfcf6-167">たとえば、1.0.1 SDK とランタイムを削除するには、次の bash コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-167">For example, to remove the 1.0.1 SDK and runtime, you would use the following bash commands:</span></span>

```bash
sudo rm -rf /usr/local/share/dotnet/sdk/1.0.1
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.NETCore.App/1.0.1
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.AspNetCore.App/1.0.1
sudo rm -rf /usr/local/share/dotnet/host/fxr/1.0.1
```

<span data-ttu-id="bfcf6-168">上記の表に示したように、SDK とランタイムの親ディレクトリは、`dotnet --list-sdks` コマンドおよび `dotnet --list-runtimes` コマンドからの出力に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-168">The parent directories for the SDK and runtime are listed in the output from the `dotnet --list-sdks` and `dotnet --list-runtimes` command, as shown in the earlier table.</span></span>

---

## <a name="net-core-uninstall-tool"></a><span data-ttu-id="bfcf6-169">.NET Core アンインストール ツール</span><span class="sxs-lookup"><span data-stu-id="bfcf6-169">.NET Core Uninstall Tool</span></span>

<span data-ttu-id="bfcf6-170">[.NET Core アンインストール ツール](../additional-tools/uninstall-tool.md) (`dotnet-core-uninstall`) を使用すると、.NET Core SDK とランタイムをシステムから削除できます。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-170">The [.NET Core Uninstall Tool](../additional-tools/uninstall-tool.md) (`dotnet-core-uninstall`) lets you remove .NET Core SDKs and runtimes from a system.</span></span> <span data-ttu-id="bfcf6-171">一連のオプションを使用して、アンインストールするバージョンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-171">A collection of options is available to specify which versions should be uninstalled.</span></span>

## <a name="visual-studio-dependency-on-net-core-sdk-versions"></a><span data-ttu-id="bfcf6-172">.NET Core SDK バージョンに対する Visual Studio の依存関係</span><span class="sxs-lookup"><span data-stu-id="bfcf6-172">Visual Studio dependency on .NET Core SDK versions</span></span>

<span data-ttu-id="bfcf6-173">Visual Studio 2019 バージョン 16.3 より前では、Visual Studio インストーラーはスタンドアロンの .NET Core SDK インストーラーを呼び出しました。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-173">Before Visual Studio 2019 version 16.3, Visual Studio installers called the standalone .NET Core SDK installer.</span></span> <span data-ttu-id="bfcf6-174">その結果、Windows の **[プログラムの追加と削除]** ダイアログに SDK のバージョンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-174">As a result, the SDK versions appear in the Windows **Add/Remove Programs** dialog.</span></span> <span data-ttu-id="bfcf6-175">スタンドアロン インストーラーを使用して Visual Studio によってインストールされた .NET Core SDK を削除すると、Visual Studio が破損する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-175">Removing .NET Core SDKs that were installed by Visual Studio using the standalone installer may break Visual Studio.</span></span> <span data-ttu-id="bfcf6-176">SDK をアンインストールした後に Visual Studio で問題が発生した場合は、その特定のバージョンの Visual Studio で [修復] を実行します。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-176">If Visual Studio has problems after you uninstall SDKs, run Repair on that specific version of Visual Studio.</span></span> <span data-ttu-id="bfcf6-177">次の表に、.NET Core SDK バージョンに対する Visual Studio の依存関係の一部を示します。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-177">The following table shows some of the Visual Studio dependencies on .NET Core SDK versions:</span></span>

| <span data-ttu-id="bfcf6-178">Visual Studio のバージョン</span><span class="sxs-lookup"><span data-stu-id="bfcf6-178">Visual Studio version</span></span> | <span data-ttu-id="bfcf6-179">.NET Core SDK のバージョン</span><span class="sxs-lookup"><span data-stu-id="bfcf6-179">.NET Core SDK version</span></span> |
| -- | -- |
| <span data-ttu-id="bfcf6-180">Visual Studio 2019 バージョン 16.2</span><span class="sxs-lookup"><span data-stu-id="bfcf6-180">Visual Studio 2019 version 16.2</span></span> | <span data-ttu-id="bfcf6-181">.NET Core SDK 2.2.4xx、2.1.8xx</span><span class="sxs-lookup"><span data-stu-id="bfcf6-181">.NET Core SDK 2.2.4xx, 2.1.8xx</span></span> |
| <span data-ttu-id="bfcf6-182">Visual Studio 2019 バージョン 16.1</span><span class="sxs-lookup"><span data-stu-id="bfcf6-182">Visual Studio 2019 version 16.1</span></span> | <span data-ttu-id="bfcf6-183">.NET Core SDK 2.2.3xx、2.1.7xx</span><span class="sxs-lookup"><span data-stu-id="bfcf6-183">.NET Core SDK 2.2.3xx, 2.1.7xx</span></span> |
| <span data-ttu-id="bfcf6-184">Visual Studio 2019 バージョン 16.0</span><span class="sxs-lookup"><span data-stu-id="bfcf6-184">Visual Studio 2019 version 16.0</span></span> | <span data-ttu-id="bfcf6-185">.NET Core SDK 2.2.2xx、2.1.6xx</span><span class="sxs-lookup"><span data-stu-id="bfcf6-185">.NET Core SDK 2.2.2xx, 2.1.6xx</span></span> |
| <span data-ttu-id="bfcf6-186">Visual Studio 2017 バージョン 15.9</span><span class="sxs-lookup"><span data-stu-id="bfcf6-186">Visual Studio 2017 version 15.9</span></span> | <span data-ttu-id="bfcf6-187">.NET Core SDK 2.2.1xx、2.1.5xx</span><span class="sxs-lookup"><span data-stu-id="bfcf6-187">.NET Core SDK 2.2.1xx, 2.1.5xx</span></span> |
| <span data-ttu-id="bfcf6-188">Visual Studio 2017 バージョン 15.8</span><span class="sxs-lookup"><span data-stu-id="bfcf6-188">Visual Studio 2017 version 15.8</span></span> | <span data-ttu-id="bfcf6-189">.NET Core SDK 2.1.4xx</span><span class="sxs-lookup"><span data-stu-id="bfcf6-189">.NET Core SDK 2.1.4xx</span></span> |

<span data-ttu-id="bfcf6-190">Visual Studio 2019 バージョン 16.3 以降では、Visual Studio によって .NET Core SDK の独自のコピーが管理されます。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-190">Starting with Visual Studio 2019 version 16.3, Visual Studio is in charge of its own copy of the .NET Core SDK.</span></span> <span data-ttu-id="bfcf6-191">そのため、 **[プログラムの追加と削除]** ダイアログにこれらの SDK バージョンが表示されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-191">For that reason, you no longer see those SDK versions in the **Add/Remove Programs** dialog.</span></span>

## <a name="remove-the-nuget-fallback-folder"></a><span data-ttu-id="bfcf6-192">NuGet フォールバック フォルダーの削除</span><span class="sxs-lookup"><span data-stu-id="bfcf6-192">Remove the NuGet fallback folder</span></span>

<span data-ttu-id="bfcf6-193">.NET Core 3.0 SDK より前では、.NET Core SDK インストーラーは *NuGetFallbackFolder* を使用して、NuGet パッケージのキャッシュを格納していました。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-193">Before .NET Core 3.0 SDK, the .NET Core SDK installers used the *NuGetFallbackFolder* to store a cache of NuGet packages.</span></span> <span data-ttu-id="bfcf6-194">このキャッシュは、`dotnet restore` や `dotnet build /t:Restore` などの操作中に使用されました。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-194">This cache was used during operations such as `dotnet restore` or `dotnet build /t:Restore`.</span></span> <span data-ttu-id="bfcf6-195">`NuGetFallbackFolder` は、Windows では *C:\Program Files\dotnet\sdk* に、macOS では */usr/local/share/dotnet/sdk* にあります。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-195">The `NuGetFallbackFolder` is located at *C:\Program Files\dotnet\sdk* on Windows and at */usr/local/share/dotnet/sdk* on macOS.</span></span>

<span data-ttu-id="bfcf6-196">次の場合は、このフォルダーを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-196">You may want to remove this folder, if:</span></span>

* <span data-ttu-id="bfcf6-197">.NET Core 3.0 SDK 以降のバージョンのみを使用して開発している。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-197">You're only developing using .NET Core 3.0 SDK or later versions.</span></span>
* <span data-ttu-id="bfcf6-198">3\.0 より前の .NET Core SDK のバージョンを使用して開発しているが、オンラインで作業することができ、処理が遅くなることがある。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-198">You're developing using .NET Core SDK versions earlier than 3.0, but you can work online and things can be slower once.</span></span>

<span data-ttu-id="bfcf6-199">NuGet フォールバック フォルダーを削除する場合は、管理者特権が必要になります。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-199">If you want to remove the NuGet fallback folder, you can delete it, but you'll need admin privileges to do so.</span></span>

<span data-ttu-id="bfcf6-200">*dotnet* フォルダーの削除はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-200">It's not recommended to delete the *dotnet* folder.</span></span> <span data-ttu-id="bfcf6-201">これを行うと、以前にインストールしたグローバル ツールがすべて削除されます。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-201">Doing so would remove any global tools you've previously installed.</span></span> <span data-ttu-id="bfcf6-202">また、Windows の場合は、次のことが発生します。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-202">Also, on Windows:</span></span>

- <span data-ttu-id="bfcf6-203">Visual Studio 2019 バージョン 16.3 以降のバージョンが破損します。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-203">You'll break Visual Studio 2019 version 16.3 and later versions.</span></span> <span data-ttu-id="bfcf6-204">**[修復]** を実行して回復できます。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-204">You can run **Repair** to recover.</span></span>
- <span data-ttu-id="bfcf6-205">**[プログラムの追加と削除]** ダイアログに .NET Core SDK エントリがある場合、それらは孤立状態になります。</span><span class="sxs-lookup"><span data-stu-id="bfcf6-205">If there are .NET Core SDK entries in the **Add/Remove Programs** dialog, they'll be orphaned.</span></span>
