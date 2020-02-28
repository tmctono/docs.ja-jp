---
title: dotnet store コマンド
description: "'dotnet store' コマンドは、指定したアセンブリをランタイム パッケージ ストアに格納します。"
ms.date: 02/14/2020
ms.openlocfilehash: da1d132b2b873ff55ec104b5bb092d0194889bdc
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503584"
---
# <a name="dotnet-store"></a><span data-ttu-id="e8b50-103">dotnet store</span><span class="sxs-lookup"><span data-stu-id="e8b50-103">dotnet store</span></span>

<span data-ttu-id="e8b50-104">**この記事の対象:** ✔️ .NET Core 2.x SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="e8b50-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="e8b50-105">名前</span><span class="sxs-lookup"><span data-stu-id="e8b50-105">Name</span></span>

<span data-ttu-id="e8b50-106">`dotnet store` - 指定したアセンブリを[ランタイム パッケージ ストア](../deploying/runtime-store.md)に格納します。</span><span class="sxs-lookup"><span data-stu-id="e8b50-106">`dotnet store` - Stores the specified assemblies in the [runtime package store](../deploying/runtime-store.md).</span></span>

## <a name="synopsis"></a><span data-ttu-id="e8b50-107">構文</span><span class="sxs-lookup"><span data-stu-id="e8b50-107">Synopsis</span></span>

```dotnetcli
dotnet store -m|--manifest -f|--framework -r|--runtime  [--framework-version] [-h|--help] [--output] [--skip-optimization] [--skip-symbols] [-v|--verbosity] [--working-dir]
```

## <a name="description"></a><span data-ttu-id="e8b50-108">説明</span><span class="sxs-lookup"><span data-stu-id="e8b50-108">Description</span></span>

<span data-ttu-id="e8b50-109">`dotnet store` - 指定したアセンブリを[ランタイム パッケージ ストア](../deploying/runtime-store.md)に格納します。</span><span class="sxs-lookup"><span data-stu-id="e8b50-109">`dotnet store` stores the specified assemblies in the [runtime package store](../deploying/runtime-store.md).</span></span> <span data-ttu-id="e8b50-110">既定では、アセンブリは、ターゲット ランタイムとフレームワークに合わせて最適化されます。</span><span class="sxs-lookup"><span data-stu-id="e8b50-110">By default, assemblies are optimized for the target runtime and framework.</span></span> <span data-ttu-id="e8b50-111">詳細については、[「ランタイム パッケージ ストア」](../deploying/runtime-store.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8b50-111">For more information, see the [runtime package store](../deploying/runtime-store.md) topic.</span></span>

## <a name="required-options"></a><span data-ttu-id="e8b50-112">必須オプション</span><span class="sxs-lookup"><span data-stu-id="e8b50-112">Required options</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e8b50-113">[ターゲット フレームワーク](../../standard/frameworks.md)を指定します。</span><span class="sxs-lookup"><span data-stu-id="e8b50-113">Specifies the [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="e8b50-114">ターゲット フレームワークはプロジェクト ファイルに指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8b50-114">The target framework has to be specified in the project file.</span></span>

- **`-m|--manifest <PATH_TO_MANIFEST_FILE>`**

  <span data-ttu-id="e8b50-115">"*パッケージ ストア マニフェスト ファイル*" は、格納するパッケージの一覧を含む XML ファイルです。</span><span class="sxs-lookup"><span data-stu-id="e8b50-115">The *package store manifest file* is an XML file that contains the list of packages to store.</span></span> <span data-ttu-id="e8b50-116">マニフェスト ファイルの形式は、SDK スタイル プロジェクト形式と互換性があります。</span><span class="sxs-lookup"><span data-stu-id="e8b50-116">The format of the manifest file is compatible with the SDK-style project format.</span></span> <span data-ttu-id="e8b50-117">そのため、必要なパッケージを参照するプロジェクト ファイルを `-m|--manifest` オプションと使用することで、ランタイム パッケージ ストアにアセンブリを格納することができます。</span><span class="sxs-lookup"><span data-stu-id="e8b50-117">So, a project file that references the desired packages can be used with the `-m|--manifest` option to store assemblies in the runtime package store.</span></span> <span data-ttu-id="e8b50-118">複数のマニフェスト ファイルを指定するには、ファイルごとにオプションとパスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="e8b50-118">To specify multiple manifest files, repeat the option and path for each file.</span></span> <span data-ttu-id="e8b50-119">たとえば、`--manifest packages1.csproj --manifest packages2.csproj` のように指定します。</span><span class="sxs-lookup"><span data-stu-id="e8b50-119">For example: `--manifest packages1.csproj --manifest packages2.csproj`.</span></span>

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="e8b50-120">ターゲットとする[ランタイム識別子](../rid-catalog.md)。</span><span class="sxs-lookup"><span data-stu-id="e8b50-120">The [runtime identifier](../rid-catalog.md) to target.</span></span>

## <a name="optional-options"></a><span data-ttu-id="e8b50-121">省略可能なオプション</span><span class="sxs-lookup"><span data-stu-id="e8b50-121">Optional options</span></span>

- **`--framework-version <FRAMEWORK_VERSION>`**

  <span data-ttu-id="e8b50-122">.NET Core SDK のバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="e8b50-122">Specifies the .NET Core SDK version.</span></span> <span data-ttu-id="e8b50-123">このオプションでは、`-f|--framework` オプションで指定したフレームワーク以降の特定のフレームワーク バージョンを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="e8b50-123">This option enables you to select a specific framework version beyond the framework specified by the `-f|--framework` option.</span></span>

- **`-h|--help`**

  <span data-ttu-id="e8b50-124">ヘルプ情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="e8b50-124">Shows help information.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="e8b50-125">ランタイム パッケージ ストアへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="e8b50-125">Specifies the path to the runtime package store.</span></span> <span data-ttu-id="e8b50-126">指定しない場合、ユーザー プロファイル .NET Core インストール ディレクトリのサブディレクトリ *store* が既定値となります。</span><span class="sxs-lookup"><span data-stu-id="e8b50-126">If not specified, it defaults to the *store* subdirectory of the user profile .NET Core installation directory.</span></span>

- **`--skip-optimization`**

  <span data-ttu-id="e8b50-127">最適化フェーズをスキップします。</span><span class="sxs-lookup"><span data-stu-id="e8b50-127">Skips the optimization phase.</span></span>

- **`--skip-symbols`**

  <span data-ttu-id="e8b50-128">シンボルの生成をスキップします。</span><span class="sxs-lookup"><span data-stu-id="e8b50-128">Skips symbol generation.</span></span> <span data-ttu-id="e8b50-129">現時点では、Windows と Linux 上でのみシンボルを生成することができます。</span><span class="sxs-lookup"><span data-stu-id="e8b50-129">Currently, you can only generate symbols on Windows and Linux.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="e8b50-130">コマンドの詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="e8b50-130">Sets the verbosity level of the command.</span></span> <span data-ttu-id="e8b50-131">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="e8b50-131">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

- **`-w|--working-dir <WORKING_DIRECTORY>`**

  <span data-ttu-id="e8b50-132">コマンドで使用される作業ディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="e8b50-132">The working directory used by the command.</span></span> <span data-ttu-id="e8b50-133">指定しない場合、現在のディレクトリの *obj* サブディレクトリが使用されます。</span><span class="sxs-lookup"><span data-stu-id="e8b50-133">If not specified, it uses the *obj* subdirectory of the current directory.</span></span>

## <a name="examples"></a><span data-ttu-id="e8b50-134">使用例</span><span class="sxs-lookup"><span data-stu-id="e8b50-134">Examples</span></span>

- <span data-ttu-id="e8b50-135">.NET Core 2.0.0 の *packages.csproj* プロジェクト ファイルで指定されたパッケージを格納します。</span><span class="sxs-lookup"><span data-stu-id="e8b50-135">Store the packages specified in the *packages.csproj* project file for .NET Core 2.0.0:</span></span>

  ```dotnetcli
  dotnet store --manifest packages.csproj --framework-version 2.0.0
  ```

- <span data-ttu-id="e8b50-136">*packages.csproj* で指定されたパッケージを最適化なしで格納します。</span><span class="sxs-lookup"><span data-stu-id="e8b50-136">Store the packages specified in the *packages.csproj* without optimization:</span></span>

  ```dotnetcli
  dotnet store --manifest packages.csproj --skip-optimization
  ```

## <a name="see-also"></a><span data-ttu-id="e8b50-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="e8b50-137">See also</span></span>

- [<span data-ttu-id="e8b50-138">ランタイム パッケージ ストア</span><span class="sxs-lookup"><span data-stu-id="e8b50-138">Runtime package store</span></span>](../deploying/runtime-store.md)
