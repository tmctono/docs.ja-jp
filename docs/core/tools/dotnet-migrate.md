---
title: dotnet migrate コマンド
description: dotnet migrate コマンドは、プロジェクトとそのすべての依存関係を移行します。
ms.date: 06/26/2019
ms.openlocfilehash: 3304f666d15d9188cdae76a401747d91791f817f
ms.sourcegitcommit: b5c59eaaf8bf48ef3ec259f228cb328d6d4c0ceb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2019
ms.locfileid: "67539396"
---
# <a name="dotnet-migrate"></a><span data-ttu-id="34482-103">dotnet の移行</span><span class="sxs-lookup"><span data-stu-id="34482-103">dotnet migrate</span></span>

<span data-ttu-id="34482-104">**このトピックの対象: ✓** .NET Core 1.x SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="34482-104">**This topic applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="34482-105">name</span><span class="sxs-lookup"><span data-stu-id="34482-105">Name</span></span>

<span data-ttu-id="34482-106">`dotnet migrate` - Preview 2 .NET Core プロジェクトを .NET Core SDK スタイルのプロジェクトに移行します。</span><span class="sxs-lookup"><span data-stu-id="34482-106">`dotnet migrate` - Migrates a Preview 2 .NET Core project to a .NET Core SDK-style project.</span></span>

> [!NOTE]
> <span data-ttu-id="34482-107">次のプレビュー リリースでは、`dotnet migrate` が .NET Core 3.0 SDK から削除されます。</span><span class="sxs-lookup"><span data-stu-id="34482-107">`dotnet migrate` will be removed from the .NET Core 3.0 SDK in the next preview release.</span></span>

## <a name="synopsis"></a><span data-ttu-id="34482-108">構文</span><span class="sxs-lookup"><span data-stu-id="34482-108">Synopsis</span></span>

```
dotnet migrate [<SOLUTION_FILE|PROJECT_DIR>] [--format-report-file-json] [-r|--report-file] [-s|--skip-project-references] [--skip-backup] [-t|--template-file] [-v|--sdk-package-version] [-x|--xproj-file]
dotnet migrate [-h|--help]
```

## <a name="description"></a><span data-ttu-id="34482-109">説明</span><span class="sxs-lookup"><span data-stu-id="34482-109">Description</span></span>

<span data-ttu-id="34482-110">`dotnet migrate` コマンドは、有効な Preview 2 *project.json* ベースのプロジェクトを有効な .NET Core SDK スタイルの *csproj* プロジェクトに移行します。</span><span class="sxs-lookup"><span data-stu-id="34482-110">The `dotnet migrate` command migrates a valid Preview 2 *project.json*-based project to a valid .NET Core SDK-style *csproj* project.</span></span>

<span data-ttu-id="34482-111">既定では、このコマンドは、ルート プロジェクトとルート プロジェクトに含まれるすべてのプロジェクト参照を移行します。</span><span class="sxs-lookup"><span data-stu-id="34482-111">By default, the command migrates the root project and any project references that the root project contains.</span></span> <span data-ttu-id="34482-112">この動作は、実行時に `--skip-project-references` オプションを使って、無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="34482-112">This behavior is disabled using the `--skip-project-references` option at runtime.</span></span>

<span data-ttu-id="34482-113">移行は次のアセットで実行できます。</span><span class="sxs-lookup"><span data-stu-id="34482-113">Migration can be performed on the following assets:</span></span>

* <span data-ttu-id="34482-114">1 つのプロジェクト。移行する *project.json* ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="34482-114">A single project by specifying the *project.json* file to migrate.</span></span>
* <span data-ttu-id="34482-115">*global.json* ファイルで指定されているすべてのディレクトリ。*global.json* ファイルへのパスを渡します。</span><span class="sxs-lookup"><span data-stu-id="34482-115">All of the directories specified in the *global.json* file by passing in a path to the *global.json* file.</span></span>
* <span data-ttu-id="34482-116">*solution.sln* ファイル。ソリューションで参照されているプロジェクトを移行します。</span><span class="sxs-lookup"><span data-stu-id="34482-116">A *solution.sln* file, where it migrates the projects referenced in the solution.</span></span>
* <span data-ttu-id="34482-117">特定のディレクトリのすべてのサブディレクトリ (再帰的)。</span><span class="sxs-lookup"><span data-stu-id="34482-117">On all subdirectories of the given directory recursively.</span></span>

<span data-ttu-id="34482-118">`dotnet migrate` コマンドは、`backup` ディレクトリ内に移行された *project.json* ファイルを保持します。ディレクトリが存在しない場合は作成されます。</span><span class="sxs-lookup"><span data-stu-id="34482-118">The `dotnet migrate` command keeps the migrated *project.json* file inside a `backup` directory, which it creates if the directory doesn't exist.</span></span> <span data-ttu-id="34482-119">この動作は、`--skip-backup` オプションを使ってオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="34482-119">This behavior is overridden using the `--skip-backup` option.</span></span>

<span data-ttu-id="34482-120">既定では、移行操作は、標準出力 (STDOUT) に移行プロセスの状態を出力します。</span><span class="sxs-lookup"><span data-stu-id="34482-120">By default, the migration operation outputs the state of the migration process to standard output (STDOUT).</span></span> <span data-ttu-id="34482-121">`--report-file <REPORT_FILE>` オプションを使うと、指定したファイルに出力が保存を指定します。</span><span class="sxs-lookup"><span data-stu-id="34482-121">If you use the `--report-file <REPORT_FILE>` option, the output is saved to the file specify.</span></span>

<span data-ttu-id="34482-122">`dotnet migrate` コマンドは、有効な Preview 2 *project.json* ベースのプロジェクトのみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="34482-122">The `dotnet migrate` command only supports valid Preview 2 *project.json*-based projects.</span></span> <span data-ttu-id="34482-123">つまり、DNX または Preview 1 の *project.json* ベースのプロジェクトを MSBuild/csproj プロジェクトに直接移行するためには使えません。</span><span class="sxs-lookup"><span data-stu-id="34482-123">This means that you cannot use it to migrate DNX or Preview 1 *project.json*-based projects directly to MSBuild/csproj projects.</span></span> <span data-ttu-id="34482-124">最初にプロジェクトを Preview 2 *project.json* ベースのプロジェクトに手動で移行し、その後で `dotnet migrate` コマンドを使ってプロジェクトを移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34482-124">You first need to manually migrate the project to a Preview 2 *project.json*-based project and then use the `dotnet migrate` command to migrate the project.</span></span>

## <a name="arguments"></a><span data-ttu-id="34482-125">引数</span><span class="sxs-lookup"><span data-stu-id="34482-125">Arguments</span></span>

`PROJECT_JSON/GLOBAL_JSON/SOLUTION_FILE/PROJECT_DIR`

<span data-ttu-id="34482-126">次のいずれかへのパスです。</span><span class="sxs-lookup"><span data-stu-id="34482-126">The path to one of the following:</span></span>

* <span data-ttu-id="34482-127">移行する *project.json* ファイル。</span><span class="sxs-lookup"><span data-stu-id="34482-127">a *project.json* file to migrate.</span></span>
* <span data-ttu-id="34482-128">*global.json* ファイル: *global.json* で指定されているフォルダーを移行します。</span><span class="sxs-lookup"><span data-stu-id="34482-128">a *global.json* file: the folders specified in *global.json* are migrated.</span></span>
* <span data-ttu-id="34482-129">*solution.sln* ファイル: ソリューションで参照されているプロジェクトを移行します。</span><span class="sxs-lookup"><span data-stu-id="34482-129">a *solution.sln* file: the projects referenced in the solution are migrated.</span></span>
* <span data-ttu-id="34482-130">移行するディレクトリ: 移行する *project.json* ファイルを再帰的に検索して、指定したディレクトリ内に移行します。</span><span class="sxs-lookup"><span data-stu-id="34482-130">a directory to migrate: recursively searches for *project.json* files to migrate inside the specified directory.</span></span>

<span data-ttu-id="34482-131">何も指定しない場合の既定値は現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="34482-131">Defaults to current directory if nothing is specified.</span></span>

## <a name="options"></a><span data-ttu-id="34482-132">オプション</span><span class="sxs-lookup"><span data-stu-id="34482-132">Options</span></span>

`--format-report-file-json <REPORT_FILE>`

<span data-ttu-id="34482-133">ユーザー メッセージではなく、JSON として移行レポート ファイルを出力します。</span><span class="sxs-lookup"><span data-stu-id="34482-133">Output migration report file as JSON rather than user messages.</span></span>

`-h|--help`

<span data-ttu-id="34482-134">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="34482-134">Prints out a short help for the command.</span></span>

`-r|--report-file <REPORT_FILE>`

<span data-ttu-id="34482-135">移行レポートをコンソールだけでなく、ファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="34482-135">Output migration report to a file in addition to the console.</span></span>

`-s|--skip-project-references [Debug|Release]`

<span data-ttu-id="34482-136">プロジェクト参照の移行をスキップします。</span><span class="sxs-lookup"><span data-stu-id="34482-136">Skip migrating project references.</span></span> <span data-ttu-id="34482-137">既定では、プロジェクト参照は再帰的に移行されます。</span><span class="sxs-lookup"><span data-stu-id="34482-137">By default, project references are migrated recursively.</span></span>

`--skip-backup`

<span data-ttu-id="34482-138">移行が成功した後、*project.json*、*global.json*、および *\*.xproj* の `backup` ディレクトリへの移動をスキップします。</span><span class="sxs-lookup"><span data-stu-id="34482-138">Skip moving *project.json*, *global.json*, and *\*.xproj* to a `backup` directory after successful migration.</span></span>

`-t|--template-file <TEMPLATE_FILE>`

<span data-ttu-id="34482-139">移行に使用するテンプレートの csproj ファイル。</span><span class="sxs-lookup"><span data-stu-id="34482-139">Template csproj file to use for migration.</span></span> <span data-ttu-id="34482-140">既定では、`dotnet new console` によってドロップされるテンプレートと同じテンプレートが使用されます。</span><span class="sxs-lookup"><span data-stu-id="34482-140">By default, the same template as the one dropped by `dotnet new console` is used.</span></span>

`-v|--sdk-package-version <VERSION>`

<span data-ttu-id="34482-141">移行されたアプリで参照される sdk パッケージのバージョンです。</span><span class="sxs-lookup"><span data-stu-id="34482-141">The version of the sdk package that's referenced in the migrated app.</span></span> <span data-ttu-id="34482-142">既定値は、`dotnet new` 内の SDK のバージョンです。</span><span class="sxs-lookup"><span data-stu-id="34482-142">The default is the version of the SDK in `dotnet new`.</span></span>

`-x|--xproj-file <FILE>`

<span data-ttu-id="34482-143">使用する xproj ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="34482-143">The path to the xproj file to use.</span></span> <span data-ttu-id="34482-144">プロジェクト ディレクトリに複数の xproj がある場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="34482-144">Required when there is more than one xproj in a project directory.</span></span>

## <a name="examples"></a><span data-ttu-id="34482-145">使用例</span><span class="sxs-lookup"><span data-stu-id="34482-145">Examples</span></span>

<span data-ttu-id="34482-146">現在のディレクトリのプロジェクトとそのプロジェクト間の依存関係をすべて移行します。</span><span class="sxs-lookup"><span data-stu-id="34482-146">Migrate a project in the current directory and all of its project-to-project dependencies:</span></span>

`dotnet migrate`

<span data-ttu-id="34482-147">*global.json* ファイルに含まれるすべてのプロジェクトを移行します。</span><span class="sxs-lookup"><span data-stu-id="34482-147">Migrate all projects that *global.json* file includes:</span></span>

`dotnet migrate path/to/global.json`

<span data-ttu-id="34482-148">現在のプロジェクトのみを移行し、プロジェクト間 (P2P) の依存関係は移行しません。</span><span class="sxs-lookup"><span data-stu-id="34482-148">Migrate only the current project and no project-to-project (P2P) dependencies.</span></span> <span data-ttu-id="34482-149">また、特定の SDK バージョンを使います。</span><span class="sxs-lookup"><span data-stu-id="34482-149">Also, use a specific SDK version:</span></span>

`dotnet migrate -s -v 1.0.0-preview4`
