---
title: dotnet clean コマンド
description: dotnet clean コマンドは現在のディレクトリを消去します。
ms.date: 02/14/2020
ms.openlocfilehash: 186f1ea07718a8e178f88c3d079cf6e2f1f8660b
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503752"
---
# <a name="dotnet-clean"></a><span data-ttu-id="19a40-103">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="19a40-103">dotnet clean</span></span>

<span data-ttu-id="19a40-104">**この記事の対象:** ✔️ .NET Core 2.x SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="19a40-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="19a40-105">名前</span><span class="sxs-lookup"><span data-stu-id="19a40-105">Name</span></span>

<span data-ttu-id="19a40-106">`dotnet clean` - プロジェクトの出力を消去します。</span><span class="sxs-lookup"><span data-stu-id="19a40-106">`dotnet clean` - Cleans the output of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="19a40-107">構文</span><span class="sxs-lookup"><span data-stu-id="19a40-107">Synopsis</span></span>

```dotnetcli
dotnet clean [<PROJECT>|<SOLUTION>] [-c|--configuration] [-f|--framework] [--interactive]
    [--nologo] [-o|--output] [-r|--runtime] [-v|--verbosity]
dotnet clean [-h|--help]
```

## <a name="description"></a><span data-ttu-id="19a40-108">説明</span><span class="sxs-lookup"><span data-stu-id="19a40-108">Description</span></span>

<span data-ttu-id="19a40-109">`dotnet clean` コマンドは、以前のビルドの出力を消去します。</span><span class="sxs-lookup"><span data-stu-id="19a40-109">The `dotnet clean` command cleans the output of the previous build.</span></span> <span data-ttu-id="19a40-110">[MSBuild ターゲット](/visualstudio/msbuild/msbuild-targets)として実装されます。そのため、コマンドの実行時にプロジェクトが評価されます。</span><span class="sxs-lookup"><span data-stu-id="19a40-110">It's implemented as an [MSBuild target](/visualstudio/msbuild/msbuild-targets), so the project is evaluated when the command is run.</span></span> <span data-ttu-id="19a40-111">ビルド中に作成された出力のみが消去されます。</span><span class="sxs-lookup"><span data-stu-id="19a40-111">Only the outputs created during the build are cleaned.</span></span> <span data-ttu-id="19a40-112">中間 (*obj*) と最終出力 (*bin*) フォルダーの両方が消去されます。</span><span class="sxs-lookup"><span data-stu-id="19a40-112">Both intermediate (*obj*) and final output (*bin*) folders are cleaned.</span></span>

## <a name="arguments"></a><span data-ttu-id="19a40-113">引数</span><span class="sxs-lookup"><span data-stu-id="19a40-113">Arguments</span></span>

`PROJECT | SOLUTION`

<span data-ttu-id="19a40-114">クリーンにする MSBuild プロジェクトまたはソリューション。</span><span class="sxs-lookup"><span data-stu-id="19a40-114">The MSBuild project or solution to clean.</span></span> <span data-ttu-id="19a40-115">プロジェクトまたはソリューションのファイルを指定しない場合、MSBuild は、現在の作業ディレクトリから *proj* または *sln* のどちらかで終わるファイル拡張子を持つファイルを検索して、そのファイルを使います。</span><span class="sxs-lookup"><span data-stu-id="19a40-115">If a project or solution file is not specified, MSBuild searches the current working directory for a file that has a file extension that ends in *proj* or *sln*, and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="19a40-116">オプション</span><span class="sxs-lookup"><span data-stu-id="19a40-116">Options</span></span>

* **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="19a40-117">ビルド構成を定義します。</span><span class="sxs-lookup"><span data-stu-id="19a40-117">Defines the build configuration.</span></span> <span data-ttu-id="19a40-118">ほとんどのプロジェクトの既定値は `Debug` ですが、プロジェクトでビルド構成設定をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="19a40-118">The default for most projects is `Debug`, but you can override the build configuration settings in your project.</span></span> <span data-ttu-id="19a40-119">このオプションは、ビルド時に指定した場合にのみ、消去時にも必要です。</span><span class="sxs-lookup"><span data-stu-id="19a40-119">This option is only required when cleaning if you specified it during build time.</span></span>

* **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="19a40-120">ビルド時に指定された[フレームワーク](../../standard/frameworks.md)です。</span><span class="sxs-lookup"><span data-stu-id="19a40-120">The [framework](../../standard/frameworks.md) that was specified at build time.</span></span> <span data-ttu-id="19a40-121">フレームワークは、[プロジェクト ファイル](csproj.md)で定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19a40-121">The framework must be defined in the [project file](csproj.md).</span></span> <span data-ttu-id="19a40-122">ビルド時にフレームワークを指定した場合は、消去時にフレームワークを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19a40-122">If you specified the framework at build time, you must specify the framework when cleaning.</span></span>

* **`-h|--help`**

  <span data-ttu-id="19a40-123">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="19a40-123">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="19a40-124">コマンドを停止して、ユーザーの入力または操作のために待機させることができます。</span><span class="sxs-lookup"><span data-stu-id="19a40-124">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="19a40-125">たとえば、認証を完了する場合があります。</span><span class="sxs-lookup"><span data-stu-id="19a40-125">For example, to complete authentication.</span></span> <span data-ttu-id="19a40-126">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="19a40-126">Available since .NET Core 3.0 SDK.</span></span>

* **`--nologo`**

  <span data-ttu-id="19a40-127">著作権情報を表示しません。</span><span class="sxs-lookup"><span data-stu-id="19a40-127">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="19a40-128">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="19a40-128">Available since .NET Core 3.0 SDK.</span></span>

* **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="19a40-129">クリーンにするビルド成果物を含むディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="19a40-129">The directory that contains the build artifacts to clean.</span></span> <span data-ttu-id="19a40-130">プロジェクトのビルド時にフレームワークを指定した場合、出力ディレクトリ スイッチと共に `-f|--framework <FRAMEWORK>` スイッチを指定します。</span><span class="sxs-lookup"><span data-stu-id="19a40-130">Specify the `-f|--framework <FRAMEWORK>` switch with the output directory switch if you specified the framework when the project was built.</span></span>

* **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="19a40-131">指定したランタイムの出力フォルダーをクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="19a40-131">Cleans the output folder of the specified runtime.</span></span> <span data-ttu-id="19a40-132">これは、[自己完結型の展開](../deploying/index.md#publish-self-contained)が作成された場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="19a40-132">This is used when a [self-contained deployment](../deploying/index.md#publish-self-contained) was created.</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="19a40-133">MSBuild の詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="19a40-133">Sets the MSBuild verbosity level.</span></span> <span data-ttu-id="19a40-134">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="19a40-134">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="19a40-135">既定値は、`normal` です。</span><span class="sxs-lookup"><span data-stu-id="19a40-135">The default is `normal`.</span></span>

## <a name="examples"></a><span data-ttu-id="19a40-136">使用例</span><span class="sxs-lookup"><span data-stu-id="19a40-136">Examples</span></span>

* <span data-ttu-id="19a40-137">プロジェクトの既定のビルドを消去します。</span><span class="sxs-lookup"><span data-stu-id="19a40-137">Clean a default build of the project:</span></span>

  ```dotnetcli
  dotnet clean
  ```

* <span data-ttu-id="19a40-138">リリース構成を使用してビルドされたプロジェクトを消去します。</span><span class="sxs-lookup"><span data-stu-id="19a40-138">Clean a project built using the Release configuration:</span></span>

  ```dotnetcli
  dotnet clean --configuration Release
  ```
