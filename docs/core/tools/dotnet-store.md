---
title: dotnet store コマンド
description: "'dotnet store' コマンドは、指定したアセンブリをランタイム パッケージ ストアに格納します。"
ms.date: 05/29/2018
ms.openlocfilehash: cc5b4b6160ba296e1529f006c15e238746d9e08a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733054"
---
# <a name="dotnet-store"></a><span data-ttu-id="42863-103">dotnet store</span><span class="sxs-lookup"><span data-stu-id="42863-103">dotnet store</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]

## <a name="name"></a><span data-ttu-id="42863-104">名前</span><span class="sxs-lookup"><span data-stu-id="42863-104">Name</span></span>

<span data-ttu-id="42863-105">`dotnet store` - 指定したアセンブリを[ランタイム パッケージ ストア](../deploying/runtime-store.md)に格納します。</span><span class="sxs-lookup"><span data-stu-id="42863-105">`dotnet store` - Stores the specified assemblies in the [runtime package store](../deploying/runtime-store.md).</span></span>

## <a name="synopsis"></a><span data-ttu-id="42863-106">構文</span><span class="sxs-lookup"><span data-stu-id="42863-106">Synopsis</span></span>

`dotnet store -m|--manifest -f|--framework -r|--runtime  [--framework-version] [-h|--help] [--output] [--skip-optimization] [--skip-symbols] [-v|--verbosity] [--working-dir]`

## <a name="description"></a><span data-ttu-id="42863-107">説明</span><span class="sxs-lookup"><span data-stu-id="42863-107">Description</span></span>

<span data-ttu-id="42863-108">`dotnet store` - 指定したアセンブリを[ランタイム パッケージ ストア](../deploying/runtime-store.md)に格納します。</span><span class="sxs-lookup"><span data-stu-id="42863-108">`dotnet store` stores the specified assemblies in the [runtime package store](../deploying/runtime-store.md).</span></span> <span data-ttu-id="42863-109">既定では、アセンブリは、ターゲット ランタイムとフレームワークに合わせて最適化されます。</span><span class="sxs-lookup"><span data-stu-id="42863-109">By default, assemblies are optimized for the target runtime and framework.</span></span> <span data-ttu-id="42863-110">詳細については、[「ランタイム パッケージ ストア」](../deploying/runtime-store.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42863-110">For more information, see the [runtime package store](../deploying/runtime-store.md) topic.</span></span>

## <a name="required-options"></a><span data-ttu-id="42863-111">必須オプション</span><span class="sxs-lookup"><span data-stu-id="42863-111">Required options</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="42863-112">[ターゲット フレームワーク](../../standard/frameworks.md)を指定します。</span><span class="sxs-lookup"><span data-stu-id="42863-112">Specifies the [target framework](../../standard/frameworks.md).</span></span>

`-m|--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="42863-113">"*パッケージ ストア マニフェスト ファイル*" は、格納するパッケージの一覧を含む XML ファイルです。</span><span class="sxs-lookup"><span data-stu-id="42863-113">The *package store manifest file* is an XML file that contains the list of packages to store.</span></span> <span data-ttu-id="42863-114">マニフェスト ファイルの形式は、SDK スタイル プロジェクト形式と互換性があります。</span><span class="sxs-lookup"><span data-stu-id="42863-114">The format of the manifest file is compatible with the SDK-style project format.</span></span> <span data-ttu-id="42863-115">そのため、必要なパッケージを参照するプロジェクト ファイルを `-m|--manifest` オプションと使用することで、ランタイム パッケージ ストアにアセンブリを格納することができます。</span><span class="sxs-lookup"><span data-stu-id="42863-115">So, a project file that references the desired packages can be used with the `-m|--manifest` option to store assemblies in the runtime package store.</span></span> <span data-ttu-id="42863-116">複数のマニフェスト ファイルを指定するには、ファイルごとにオプションとパスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="42863-116">To specify multiple manifest files, repeat the option and path for each file.</span></span> <span data-ttu-id="42863-117">たとえば、`--manifest packages1.csproj --manifest packages2.csproj` のように指定します。</span><span class="sxs-lookup"><span data-stu-id="42863-117">For example: `--manifest packages1.csproj --manifest packages2.csproj`.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="42863-118">ターゲットとする[ランタイム識別子](../rid-catalog.md)。</span><span class="sxs-lookup"><span data-stu-id="42863-118">The [runtime identifier](../rid-catalog.md) to target.</span></span>

## <a name="optional-options"></a><span data-ttu-id="42863-119">省略可能なオプション</span><span class="sxs-lookup"><span data-stu-id="42863-119">Optional options</span></span>

`--framework-version <FRAMEWORK_VERSION>`

<span data-ttu-id="42863-120">.NET Core SDK のバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="42863-120">Specifies the .NET Core SDK version.</span></span> <span data-ttu-id="42863-121">このオプションでは、`-f|--framework` オプションで指定したフレームワーク以降の特定のフレームワーク バージョンを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="42863-121">This option enables you to select a specific framework version beyond the framework specified by the `-f|--framework` option.</span></span>

`-h|--help`

<span data-ttu-id="42863-122">ヘルプ情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="42863-122">Shows help information.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="42863-123">ランタイム パッケージ ストアへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="42863-123">Specifies the path to the runtime package store.</span></span> <span data-ttu-id="42863-124">指定しない場合、ユーザー プロファイル .NET Core インストール ディレクトリのサブディレクトリ *store* が既定値となります。</span><span class="sxs-lookup"><span data-stu-id="42863-124">If not specified, it defaults to the *store* subdirectory of the user profile .NET Core installation directory.</span></span>

`--skip-optimization`

<span data-ttu-id="42863-125">最適化フェーズをスキップします。</span><span class="sxs-lookup"><span data-stu-id="42863-125">Skips the optimization phase.</span></span>

`--skip-symbols`

<span data-ttu-id="42863-126">シンボルの生成をスキップします。</span><span class="sxs-lookup"><span data-stu-id="42863-126">Skips symbol generation.</span></span> <span data-ttu-id="42863-127">現時点では、Windows と Linux 上でのみシンボルを生成することができます。</span><span class="sxs-lookup"><span data-stu-id="42863-127">Currently, you can only generate symbols on Windows and Linux.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="42863-128">コマンドの詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="42863-128">Sets the verbosity level of the command.</span></span> <span data-ttu-id="42863-129">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="42863-129">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`-w|--working-dir <INTERMEDIATE_WORKING_DIRECTORY>`

<span data-ttu-id="42863-130">コマンドで使用される作業ディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="42863-130">The working directory used by the command.</span></span> <span data-ttu-id="42863-131">指定しない場合、現在のディレクトリの *obj* サブディレクトリが使用されます。</span><span class="sxs-lookup"><span data-stu-id="42863-131">If not specified, it uses the *obj* subdirectory of the current directory.</span></span>

## <a name="examples"></a><span data-ttu-id="42863-132">使用例</span><span class="sxs-lookup"><span data-stu-id="42863-132">Examples</span></span>

<span data-ttu-id="42863-133">.NET Core 2.0.0 の *packages.csproj* プロジェクト ファイルで指定されたパッケージを格納します。</span><span class="sxs-lookup"><span data-stu-id="42863-133">Store the packages specified in the *packages.csproj* project file for .NET Core 2.0.0:</span></span>

`dotnet store --manifest packages.csproj --framework-version 2.0.0`

<span data-ttu-id="42863-134">*packages.csproj* で指定されたパッケージを最適化なしで格納します。</span><span class="sxs-lookup"><span data-stu-id="42863-134">Store the packages specified in the *packages.csproj* without optimization:</span></span>

`dotnet store --manifest packages.csproj --skip-optimization`

## <a name="see-also"></a><span data-ttu-id="42863-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="42863-135">See also</span></span>

- [<span data-ttu-id="42863-136">ランタイム パッケージ ストア</span><span class="sxs-lookup"><span data-stu-id="42863-136">Runtime package store</span></span>](../deploying/runtime-store.md)
