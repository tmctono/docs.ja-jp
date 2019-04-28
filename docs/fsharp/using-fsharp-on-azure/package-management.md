---
title: パッケージの管理を使用してF#for Azure
description: パケットを作成または Nuget を使用して管理するF#Azure の依存関係
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: fd9c4a15ab0741d44d6d5cf909b7219d310affb0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756534"
---
# <a name="package-management-for-f-azure-dependencies"></a><span data-ttu-id="23cdc-103">F# の Azure の依存関係のためのパッケージ管理</span><span class="sxs-lookup"><span data-stu-id="23cdc-103">Package Management for F# Azure Dependencies</span></span>

<span data-ttu-id="23cdc-104">パッケージ マネージャーを使用すると、Azure 向け開発用のパッケージを取得することは簡単です。</span><span class="sxs-lookup"><span data-stu-id="23cdc-104">Obtaining packages for Azure development is easy when you use a package manager.</span></span> <span data-ttu-id="23cdc-105">2 つのオプションは[パケット](https://fsprojects.github.io/Paket/)と[NuGet](https://www.nuget.org/)します。</span><span class="sxs-lookup"><span data-stu-id="23cdc-105">The two options are [Paket](https://fsprojects.github.io/Paket/) and [NuGet](https://www.nuget.org/).</span></span>

## <a name="using-paket"></a><span data-ttu-id="23cdc-106">パケットを使用します。</span><span class="sxs-lookup"><span data-stu-id="23cdc-106">Using Paket</span></span>

<span data-ttu-id="23cdc-107">使用している場合[パケット](https://fsprojects.github.io/Paket/)の依存関係マネージャーとして使用することができます、 `paket.exe` Azure の依存関係を追加するツール。</span><span class="sxs-lookup"><span data-stu-id="23cdc-107">If you're using [Paket](https://fsprojects.github.io/Paket/) as your dependency manager, you can use the `paket.exe` tool to add Azure dependencies.</span></span> <span data-ttu-id="23cdc-108">例えば:</span><span class="sxs-lookup"><span data-stu-id="23cdc-108">For example:</span></span>

    > paket add nuget WindowsAzure.Storage

<span data-ttu-id="23cdc-109">または、使用している[Mono](https://www.mono-project.com/)クロスプラット フォーム対応 .NET 開発。</span><span class="sxs-lookup"><span data-stu-id="23cdc-109">Or, if you're using [Mono](https://www.mono-project.com/) for cross-platform .NET development:</span></span>

    > mono paket.exe add nuget WindowsAzure.Storage

<span data-ttu-id="23cdc-110">これが追加されます`WindowsAzure.Storage`、現在のディレクトリでプロジェクトのパッケージの依存関係のセット、変更、`paket.dependencies`ファイルを開き、パッケージをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="23cdc-110">This will add `WindowsAzure.Storage` to your set of package dependencies for the project in the current directory, modify the `paket.dependencies` file, and download the package.</span></span> <span data-ttu-id="23cdc-111">依存関係を設定したが、依存関係が設定されていない他の開発者がプロジェクトを使用するか、解決およびローカルのような依存関係をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="23cdc-111">If you have previously set up dependencies, or are working with a project where dependencies have been set up by another developer, you can resolve and install dependencies locally like this:</span></span>

    > paket install

<span data-ttu-id="23cdc-112">または、Mono の開発。</span><span class="sxs-lookup"><span data-stu-id="23cdc-112">Or, for Mono development:</span></span>

    > mono paket.exe install

<span data-ttu-id="23cdc-113">すべてのパッケージ依存関係は、このような最新バージョンに更新できます。</span><span class="sxs-lookup"><span data-stu-id="23cdc-113">You can update all your package dependencies to the latest version like this:</span></span>

    > paket update

<span data-ttu-id="23cdc-114">または、Mono の開発。</span><span class="sxs-lookup"><span data-stu-id="23cdc-114">Or, for Mono development:</span></span>

    > mono paket.exe update

## <a name="using-nuget"></a><span data-ttu-id="23cdc-115">Nuget を使用してください。</span><span class="sxs-lookup"><span data-stu-id="23cdc-115">Using Nuget</span></span>

<span data-ttu-id="23cdc-116">使用している場合[NuGet](https://www.nuget.org/)の依存関係マネージャーとして使用することができます、 `nuget.exe` Azure の依存関係を追加するツール。</span><span class="sxs-lookup"><span data-stu-id="23cdc-116">If you're using [NuGet](https://www.nuget.org/) as your dependency manager, you can use the `nuget.exe` tool to add Azure dependencies.</span></span> <span data-ttu-id="23cdc-117">例:</span><span class="sxs-lookup"><span data-stu-id="23cdc-117">For example:</span></span>

    > nuget install WindowsAzure.Storage -ExcludeVersion

<span data-ttu-id="23cdc-118">または、Mono の開発。</span><span class="sxs-lookup"><span data-stu-id="23cdc-118">Or, for Mono development:</span></span>

    > mono nuget.exe install WindowsAzure.Storage -ExcludeVersion

<span data-ttu-id="23cdc-119">これは追加`WindowsAzure.Storage`を現在のディレクトリ、およびダウンロード パッケージにプロジェクトのパッケージの依存関係のセットにします。</span><span class="sxs-lookup"><span data-stu-id="23cdc-119">This will add `WindowsAzure.Storage` to your set of package dependencies for the project in the current directory, and download the package.</span></span> <span data-ttu-id="23cdc-120">依存関係を設定したが、依存関係が設定されていない他の開発者がプロジェクトを使用するか、解決およびローカルのような依存関係をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="23cdc-120">If you have previously set up dependencies, or are working with a project where dependencies have been set up by another developer, you can resolve and install dependencies locally like this:</span></span>

    > nuget restore 

<span data-ttu-id="23cdc-121">または、Mono の開発。</span><span class="sxs-lookup"><span data-stu-id="23cdc-121">Or, for Mono development:</span></span>

    > mono nuget.exe restore

<span data-ttu-id="23cdc-122">すべてのパッケージ依存関係は、このような最新バージョンに更新できます。</span><span class="sxs-lookup"><span data-stu-id="23cdc-122">You can update all your package dependencies to the latest version like this:</span></span>

    > nuget update

<span data-ttu-id="23cdc-123">または、Mono の開発。</span><span class="sxs-lookup"><span data-stu-id="23cdc-123">Or, for Mono development:</span></span>

    > mono nuget.exe update

## <a name="referencing-assemblies"></a><span data-ttu-id="23cdc-124">参照元のアセンブリ</span><span class="sxs-lookup"><span data-stu-id="23cdc-124">Referencing Assemblies</span></span>

<span data-ttu-id="23cdc-125">パッケージを使用するには、 F# 、スクリプトを使用してパッケージに含まれるアセンブリを参照する必要があります、`#r`ディレクティブ。</span><span class="sxs-lookup"><span data-stu-id="23cdc-125">In order to use your packages in your F# script, you need to reference the assemblies included in the packages using a `#r` directive.</span></span> <span data-ttu-id="23cdc-126">例えば:</span><span class="sxs-lookup"><span data-stu-id="23cdc-126">For example:</span></span>

    > #r "packages/WindowsAzure.Storage/lib/net40/Microsoft.WindowsAzure.Storage.dll"

<span data-ttu-id="23cdc-127">ご覧のように、DLL と完全の DLL の名前は必ずしも厳密パッケージ名と同じ相対パスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23cdc-127">As you can see, you'll need to specify the relative path to the DLL and the full DLL name, which may not be exactly the same as the package name.</span></span> <span data-ttu-id="23cdc-128">パスには、framework のバージョンやパッケージのバージョン番号が含まれます。</span><span class="sxs-lookup"><span data-stu-id="23cdc-128">The path will include a framework version and possibly a package version number.</span></span> <span data-ttu-id="23cdc-129">インストールされているすべてのアセンブリを見つけるには、Windows コマンド ラインでこのようなものを使用できます。</span><span class="sxs-lookup"><span data-stu-id="23cdc-129">To find all the installed assemblies, you can use something like this on a Windows command line:</span></span>

    > cd packages/WindowsAzure.Storage
    > dir /s/b *.dll

<span data-ttu-id="23cdc-130">または、Unix シェルのような処理。</span><span class="sxs-lookup"><span data-stu-id="23cdc-130">Or in a Unix shell, something like this:</span></span>

    > find packages/WindowsAzure.Storage -name "*.dll"

<span data-ttu-id="23cdc-131">こうパスにインストールされているアセンブリ。</span><span class="sxs-lookup"><span data-stu-id="23cdc-131">This will give you the paths to the installed assemblies.</span></span> <span data-ttu-id="23cdc-132">そこから、フレームワークのバージョンの正しいパスを選択できます。</span><span class="sxs-lookup"><span data-stu-id="23cdc-132">From there, you can select the correct path for your framework version.</span></span>
