---
title: 'Azure での F # での Package Management の使用'
description: 'パケットまたは NuGet を使用して F # Azure の依存関係を管理する'
author: sylvanc
ms.date: 09/20/2016
ms.custom: devx-track-fsharp
ms.openlocfilehash: 7816c82e87db113a35fef967886c8c3e27959332
ms.sourcegitcommit: a8a205034eeffc7c3e1bdd6f506a75b0f7099ebf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2020
ms.locfileid: "91756235"
---
# <a name="package-management-for-f-azure-dependencies"></a><span data-ttu-id="4780d-103">F# の Azure の依存関係のためのパッケージ管理</span><span class="sxs-lookup"><span data-stu-id="4780d-103">Package Management for F# Azure Dependencies</span></span>

<span data-ttu-id="4780d-104">パッケージマネージャーを使用すると、Azure 開発用のパッケージを簡単に取得できます。</span><span class="sxs-lookup"><span data-stu-id="4780d-104">Obtaining packages for Azure development is easy when you use a package manager.</span></span> <span data-ttu-id="4780d-105">[パケット](https://fsprojects.github.io/Paket/)と[NuGet](https://www.nuget.org/)の2つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="4780d-105">The two options are [Paket](https://fsprojects.github.io/Paket/) and [NuGet](https://www.nuget.org/).</span></span>

## <a name="using-paket"></a><span data-ttu-id="4780d-106">パケットの使用</span><span class="sxs-lookup"><span data-stu-id="4780d-106">Using Paket</span></span>

<span data-ttu-id="4780d-107">[パケット](https://fsprojects.github.io/Paket/)を dependency manager として使用している場合は、ツールを使用して `paket.exe` Azure の依存関係を追加できます。</span><span class="sxs-lookup"><span data-stu-id="4780d-107">If you're using [Paket](https://fsprojects.github.io/Paket/) as your dependency manager, you can use the `paket.exe` tool to add Azure dependencies.</span></span> <span data-ttu-id="4780d-108">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4780d-108">For example:</span></span>

```console
> paket add nuget WindowsAzure.Storage
```

<span data-ttu-id="4780d-109">または、クロスプラットフォームの .NET 開発に [Mono](https://www.mono-project.com/) を使用している場合は、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="4780d-109">Or, if you're using [Mono](https://www.mono-project.com/) for cross-platform .NET development:</span></span>

```console
> mono paket.exe add nuget WindowsAzure.Storage
```

<span data-ttu-id="4780d-110">これにより、 `WindowsAzure.Storage` 現在のディレクトリ内のプロジェクトに対するパッケージの依存関係のセットが追加され、ファイルが変更され、 `paket.dependencies` パッケージがダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="4780d-110">This will add `WindowsAzure.Storage` to your set of package dependencies for the project in the current directory, modify the `paket.dependencies` file, and download the package.</span></span> <span data-ttu-id="4780d-111">以前に依存関係を設定している場合、または他の開発者によって依存関係が設定されているプロジェクトを操作している場合は、次のようにローカルに依存関係を解決してインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="4780d-111">If you have previously set up dependencies, or are working with a project where dependencies have been set up by another developer, you can resolve and install dependencies locally like this:</span></span>

```console
> paket install
```

<span data-ttu-id="4780d-112">または、Mono 開発の場合:</span><span class="sxs-lookup"><span data-stu-id="4780d-112">Or, for Mono development:</span></span>

```console
> mono paket.exe install
```

<span data-ttu-id="4780d-113">次のように、すべてのパッケージの依存関係を最新バージョンに更新できます。</span><span class="sxs-lookup"><span data-stu-id="4780d-113">You can update all your package dependencies to the latest version like this:</span></span>

```console
> paket update
```

<span data-ttu-id="4780d-114">または、Mono 開発の場合:</span><span class="sxs-lookup"><span data-stu-id="4780d-114">Or, for Mono development:</span></span>

```console
> mono paket.exe update
```

## <a name="using-nuget"></a><span data-ttu-id="4780d-115">NuGet の使用</span><span class="sxs-lookup"><span data-stu-id="4780d-115">Using NuGet</span></span>

<span data-ttu-id="4780d-116">依存関係マネージャーとして [NuGet](https://www.nuget.org/) を使用している場合は、ツールを使用して `nuget.exe` Azure の依存関係を追加できます。</span><span class="sxs-lookup"><span data-stu-id="4780d-116">If you're using [NuGet](https://www.nuget.org/) as your dependency manager, you can use the `nuget.exe` tool to add Azure dependencies.</span></span> <span data-ttu-id="4780d-117">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4780d-117">For example:</span></span>

```console
> nuget install WindowsAzure.Storage -ExcludeVersion
```

<span data-ttu-id="4780d-118">または、Mono 開発の場合:</span><span class="sxs-lookup"><span data-stu-id="4780d-118">Or, for Mono development:</span></span>

```console
> mono nuget.exe install WindowsAzure.Storage -ExcludeVersion
```

<span data-ttu-id="4780d-119">これにより、 `WindowsAzure.Storage` 現在のディレクトリ内のプロジェクトに対するパッケージの依存関係のセットが追加され、パッケージがダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="4780d-119">This will add `WindowsAzure.Storage` to your set of package dependencies for the project in the current directory, and download the package.</span></span> <span data-ttu-id="4780d-120">以前に依存関係を設定している場合、または他の開発者によって依存関係が設定されているプロジェクトを操作している場合は、次のようにローカルに依存関係を解決してインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="4780d-120">If you have previously set up dependencies, or are working with a project where dependencies have been set up by another developer, you can resolve and install dependencies locally like this:</span></span>

```console
> nuget restore
```

<span data-ttu-id="4780d-121">または、Mono 開発の場合:</span><span class="sxs-lookup"><span data-stu-id="4780d-121">Or, for Mono development:</span></span>

```console
> mono nuget.exe restore
```

<span data-ttu-id="4780d-122">次のように、すべてのパッケージの依存関係を最新バージョンに更新できます。</span><span class="sxs-lookup"><span data-stu-id="4780d-122">You can update all your package dependencies to the latest version like this:</span></span>

```console
> nuget update
```

<span data-ttu-id="4780d-123">または、Mono 開発の場合:</span><span class="sxs-lookup"><span data-stu-id="4780d-123">Or, for Mono development:</span></span>

```console
> mono nuget.exe update
```

## <a name="referencing-assemblies"></a><span data-ttu-id="4780d-124">参照元のアセンブリ</span><span class="sxs-lookup"><span data-stu-id="4780d-124">Referencing Assemblies</span></span>

<span data-ttu-id="4780d-125">F # スクリプトでパッケージを使用するには、ディレクティブを使用して、パッケージに含まれているアセンブリを参照する必要があり `#r` ます。</span><span class="sxs-lookup"><span data-stu-id="4780d-125">In order to use your packages in your F# script, you need to reference the assemblies included in the packages using a `#r` directive.</span></span> <span data-ttu-id="4780d-126">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4780d-126">For example:</span></span>

```fsharp
> #r "packages/WindowsAzure.Storage/lib/net40/Microsoft.WindowsAzure.Storage.dll"
```

<span data-ttu-id="4780d-127">ご覧のとおり、DLL への相対パスと完全な DLL 名を指定する必要があります。これは、パッケージ名とまったく同じではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4780d-127">As you can see, you'll need to specify the relative path to the DLL and the full DLL name, which may not be exactly the same as the package name.</span></span> <span data-ttu-id="4780d-128">このパスには、フレームワークのバージョンと、場合によってはパッケージのバージョン番号が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4780d-128">The path will include a framework version and possibly a package version number.</span></span> <span data-ttu-id="4780d-129">インストールされているすべてのアセンブリを検索するには、Windows のコマンドラインで次のように使用します。</span><span class="sxs-lookup"><span data-stu-id="4780d-129">To find all the installed assemblies, you can use something like this on a Windows command line:</span></span>

```console
> cd packages/WindowsAzure.Storage
> dir /s/b *.dll
```

<span data-ttu-id="4780d-130">Unix シェルでは、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="4780d-130">Or in a Unix shell, something like this:</span></span>

```console
> find packages/WindowsAzure.Storage -name "*.dll"
```

<span data-ttu-id="4780d-131">これにより、インストールされているアセンブリへのパスが得られます。</span><span class="sxs-lookup"><span data-stu-id="4780d-131">This will give you the paths to the installed assemblies.</span></span> <span data-ttu-id="4780d-132">そこから、フレームワークのバージョンに適したパスを選択できます。</span><span class="sxs-lookup"><span data-stu-id="4780d-132">From there, you can select the correct path for your framework version.</span></span>
