---
title: dotnet clean コマンド
description: dotnet clean コマンドは現在のディレクトリを消去します。
ms.date: 06/26/2019
ms.openlocfilehash: 736c0bba5d156e919534f1ad811641e815b3ffac
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734253"
---
# <a name="dotnet-clean"></a><span data-ttu-id="38b3c-103">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="38b3c-103">dotnet clean</span></span>

<span data-ttu-id="38b3c-104">**この記事の対象:** ✔️ .NET Core 1.x SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="38b3c-104">**This article applies to:** ✔️ .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="38b3c-105">名前</span><span class="sxs-lookup"><span data-stu-id="38b3c-105">Name</span></span>

<span data-ttu-id="38b3c-106">`dotnet clean` - プロジェクトの出力を消去します。</span><span class="sxs-lookup"><span data-stu-id="38b3c-106">`dotnet clean` - Cleans the output of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="38b3c-107">構文</span><span class="sxs-lookup"><span data-stu-id="38b3c-107">Synopsis</span></span>

```dotnetcli
dotnet clean [<PROJECT>|<SOLUTION>] [-c|--configuration] [-f|--framework] [--interactive]
    [--nologo] [-o|--output] [-r|--runtime] [-v|--verbosity]
dotnet clean [-h|--help]
```

## <a name="description"></a><span data-ttu-id="38b3c-108">説明</span><span class="sxs-lookup"><span data-stu-id="38b3c-108">Description</span></span>

<span data-ttu-id="38b3c-109">`dotnet clean` コマンドは、以前のビルドの出力を消去します。</span><span class="sxs-lookup"><span data-stu-id="38b3c-109">The `dotnet clean` command cleans the output of the previous build.</span></span> <span data-ttu-id="38b3c-110">[MSBuild ターゲット](/visualstudio/msbuild/msbuild-targets)として実装されます。そのため、コマンドの実行時にプロジェクトが評価されます。</span><span class="sxs-lookup"><span data-stu-id="38b3c-110">It's implemented as an [MSBuild target](/visualstudio/msbuild/msbuild-targets), so the project is evaluated when the command is run.</span></span> <span data-ttu-id="38b3c-111">ビルド中に作成された出力のみが消去されます。</span><span class="sxs-lookup"><span data-stu-id="38b3c-111">Only the outputs created during the build are cleaned.</span></span> <span data-ttu-id="38b3c-112">中間 (*obj*) と最終出力 (*bin*) フォルダーの両方が消去されます。</span><span class="sxs-lookup"><span data-stu-id="38b3c-112">Both intermediate (*obj*) and final output (*bin*) folders are cleaned.</span></span>

## <a name="arguments"></a><span data-ttu-id="38b3c-113">引数</span><span class="sxs-lookup"><span data-stu-id="38b3c-113">Arguments</span></span>

`PROJECT | SOLUTION`

<span data-ttu-id="38b3c-114">クリーンにする MSBuild プロジェクトまたはソリューション。</span><span class="sxs-lookup"><span data-stu-id="38b3c-114">The MSBuild project or solution to clean.</span></span> <span data-ttu-id="38b3c-115">プロジェクトまたはソリューションのファイルを指定しない場合、MSBuild は、現在の作業ディレクトリから *proj* または *sln* のどちらかで終わるファイル拡張子を持つファイルを検索して、そのファイルを使います。</span><span class="sxs-lookup"><span data-stu-id="38b3c-115">If a project or solution file is not specified, MSBuild searches the current working directory for a file that has a file extension that ends in *proj* or *sln*, and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="38b3c-116">オプション</span><span class="sxs-lookup"><span data-stu-id="38b3c-116">Options</span></span>

* **`-c|--configuration {Debug|Release}`**

  <span data-ttu-id="38b3c-117">ビルド構成を定義します。</span><span class="sxs-lookup"><span data-stu-id="38b3c-117">Defines the build configuration.</span></span> <span data-ttu-id="38b3c-118">既定値は `Debug` です。</span><span class="sxs-lookup"><span data-stu-id="38b3c-118">The default value is `Debug`.</span></span> <span data-ttu-id="38b3c-119">このオプションは、ビルド時に指定した場合にのみ、消去時にも必要です。</span><span class="sxs-lookup"><span data-stu-id="38b3c-119">This option is only required when cleaning if you specified it during build time.</span></span>

* **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="38b3c-120">ビルド時に指定された[フレームワーク](../../standard/frameworks.md)です。</span><span class="sxs-lookup"><span data-stu-id="38b3c-120">The [framework](../../standard/frameworks.md) that was specified at build time.</span></span> <span data-ttu-id="38b3c-121">フレームワークは、[プロジェクト ファイル](csproj.md)で定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="38b3c-121">The framework must be defined in the [project file](csproj.md).</span></span> <span data-ttu-id="38b3c-122">ビルド時にフレームワークを指定した場合は、消去時にフレームワークを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="38b3c-122">If you specified the framework at build time, you must specify the framework when cleaning.</span></span>

* **`-h|--help`**

  <span data-ttu-id="38b3c-123">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="38b3c-123">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="38b3c-124">コマンドを停止して、ユーザーの入力または操作のために待機させることができます。</span><span class="sxs-lookup"><span data-stu-id="38b3c-124">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="38b3c-125">たとえば、認証を完了する場合があります。</span><span class="sxs-lookup"><span data-stu-id="38b3c-125">For example, to complete authentication.</span></span> <span data-ttu-id="38b3c-126">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="38b3c-126">Available since .NET Core 3.0 SDK.</span></span>

* **`--nologo`**

  <span data-ttu-id="38b3c-127">著作権情報を表示しません。</span><span class="sxs-lookup"><span data-stu-id="38b3c-127">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="38b3c-128">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="38b3c-128">Available since .NET Core 3.0 SDK.</span></span>

* **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="38b3c-129">クリーンにするビルド成果物を含むディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="38b3c-129">The directory that contains the build artifacts to clean.</span></span> <span data-ttu-id="38b3c-130">プロジェクトのビルド時にフレームワークを指定した場合、出力ディレクトリ スイッチと共に `-f|--framework <FRAMEWORK>` スイッチを指定します。</span><span class="sxs-lookup"><span data-stu-id="38b3c-130">Specify the `-f|--framework <FRAMEWORK>` switch with the output directory switch if you specified the framework when the project was built.</span></span>

* **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="38b3c-131">指定したランタイムの出力フォルダーをクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="38b3c-131">Cleans the output folder of the specified runtime.</span></span> <span data-ttu-id="38b3c-132">これは、[自己完結型の展開](../deploying/index.md#self-contained-deployments-scd)が作成された場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="38b3c-132">This is used when a [self-contained deployment](../deploying/index.md#self-contained-deployments-scd) was created.</span></span> <span data-ttu-id="38b3c-133">.NET Core 2.0 SDK 以降、使用できるオプションです。</span><span class="sxs-lookup"><span data-stu-id="38b3c-133">Option available since .NET Core 2.0 SDK.</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="38b3c-134">MSBuild の詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="38b3c-134">Sets the MSBuild verbosity level.</span></span> <span data-ttu-id="38b3c-135">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="38b3c-135">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="38b3c-136">既定値は、`normal` です。</span><span class="sxs-lookup"><span data-stu-id="38b3c-136">The default is `normal`.</span></span>

## <a name="examples"></a><span data-ttu-id="38b3c-137">使用例</span><span class="sxs-lookup"><span data-stu-id="38b3c-137">Examples</span></span>

* <span data-ttu-id="38b3c-138">プロジェクトの既定のビルドを消去します。</span><span class="sxs-lookup"><span data-stu-id="38b3c-138">Clean a default build of the project:</span></span>

  ```dotnetcli
  dotnet clean
  ```

* <span data-ttu-id="38b3c-139">リリース構成を使用してビルドされたプロジェクトを消去します。</span><span class="sxs-lookup"><span data-stu-id="38b3c-139">Clean a project built using the Release configuration:</span></span>

  ```dotnetcli
  dotnet clean --configuration Release
  ```
