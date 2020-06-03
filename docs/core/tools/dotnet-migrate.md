---
title: dotnet migrate コマンド
description: dotnet migrate コマンドは、プロジェクトとそのすべての依存関係を移行します。
ms.date: 02/14/2020
ms.openlocfilehash: 2e7f9ae5a1d11c54280d914b04df761f0d5aff99
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84284093"
---
# <a name="dotnet-migrate"></a><span data-ttu-id="51285-103">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="51285-103">dotnet migrate</span></span>

<span data-ttu-id="51285-104">**この記事の対象:** ✔️ .NET Core 2.x SDK</span><span class="sxs-lookup"><span data-stu-id="51285-104">**This article applies to:** ✔️ .NET Core 2.x SDK</span></span>

## <a name="name"></a><span data-ttu-id="51285-105">名前</span><span class="sxs-lookup"><span data-stu-id="51285-105">Name</span></span>

<span data-ttu-id="51285-106">`dotnet migrate` - Preview 2 .NET Core プロジェクトを .NET Core SDK スタイルのプロジェクトに移行します。</span><span class="sxs-lookup"><span data-stu-id="51285-106">`dotnet migrate` - Migrates a Preview 2 .NET Core project to a .NET Core SDK-style project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="51285-107">構文</span><span class="sxs-lookup"><span data-stu-id="51285-107">Synopsis</span></span>

```dotnetcli
dotnet migrate [<SOLUTION_FILE|PROJECT_DIR>] [--format-report-file-json <REPORT_FILE>]
    [-r|--report-file <REPORT_FILE>] [-s|--skip-project-references [Debug|Release]]
    [--skip-backup] [-t|--template-file <TEMPLATE_FILE>] [-v|--sdk-package-version]
    [-x|--xproj-file]

dotnet migrate -h|--help
```

## <a name="description"></a><span data-ttu-id="51285-108">説明</span><span class="sxs-lookup"><span data-stu-id="51285-108">Description</span></span>

<span data-ttu-id="51285-109">このコマンドは非推奨です。</span><span class="sxs-lookup"><span data-stu-id="51285-109">This command is deprecated.</span></span> <span data-ttu-id="51285-110">`dotnet migrate` コマンドは、.NET Core 3.0 SDK 以降では使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="51285-110">The `dotnet migrate` command is no longer available starting with .NET Core 3.0 SDK.</span></span> <span data-ttu-id="51285-111">これは、Preview 2 .NET Core プロジェクトを 1.x .NET Core プロジェクト (サポート対象外) にしか移行できません。</span><span class="sxs-lookup"><span data-stu-id="51285-111">It can only migrate a Preview 2 .NET Core project to a 1.x .NET Core project, which is out of support.</span></span>

<span data-ttu-id="51285-112">既定では、このコマンドは、ルート プロジェクトとルート プロジェクトに含まれるすべてのプロジェクト参照を移行します。</span><span class="sxs-lookup"><span data-stu-id="51285-112">By default, the command migrates the root project and any project references that the root project contains.</span></span> <span data-ttu-id="51285-113">この動作は、実行時に `--skip-project-references` オプションを使って、無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="51285-113">This behavior is disabled using the `--skip-project-references` option at run time.</span></span>

<span data-ttu-id="51285-114">移行は次のアセットで実行できます。</span><span class="sxs-lookup"><span data-stu-id="51285-114">Migration can be performed on the following assets:</span></span>

* <span data-ttu-id="51285-115">1 つのプロジェクト。移行する *project.json* ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="51285-115">A single project by specifying the *project.json* file to migrate.</span></span>
* <span data-ttu-id="51285-116">*global.json* ファイルで指定されているすべてのディレクトリ。*global.json* ファイルへのパスを渡します。</span><span class="sxs-lookup"><span data-stu-id="51285-116">All of the directories specified in the *global.json* file by passing in a path to the *global.json* file.</span></span>
* <span data-ttu-id="51285-117">*solution.sln* ファイル。ソリューションで参照されているプロジェクトを移行します。</span><span class="sxs-lookup"><span data-stu-id="51285-117">A *solution.sln* file, where it migrates the projects referenced in the solution.</span></span>
* <span data-ttu-id="51285-118">特定のディレクトリのすべてのサブディレクトリ (再帰的)。</span><span class="sxs-lookup"><span data-stu-id="51285-118">On all subdirectories of the given directory recursively.</span></span>

<span data-ttu-id="51285-119">`dotnet migrate` コマンドは、`backup` ディレクトリ内に移行された *project.json* ファイルを保持します。ディレクトリが存在しない場合は作成されます。</span><span class="sxs-lookup"><span data-stu-id="51285-119">The `dotnet migrate` command keeps the migrated *project.json* file inside a `backup` directory, which it creates if the directory doesn't exist.</span></span> <span data-ttu-id="51285-120">この動作は、`--skip-backup` オプションを使ってオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="51285-120">This behavior is overridden using the `--skip-backup` option.</span></span>

<span data-ttu-id="51285-121">既定では、移行操作は、標準出力 (STDOUT) に移行プロセスの状態を出力します。</span><span class="sxs-lookup"><span data-stu-id="51285-121">By default, the migration operation outputs the state of the migration process to standard output (STDOUT).</span></span> <span data-ttu-id="51285-122">`--report-file <REPORT_FILE>` オプションを使うと、指定したファイルに出力が保存を指定します。</span><span class="sxs-lookup"><span data-stu-id="51285-122">If you use the `--report-file <REPORT_FILE>` option, the output is saved to the file specify.</span></span>

<span data-ttu-id="51285-123">`dotnet migrate` コマンドは、有効な Preview 2 *project.json* ベースのプロジェクトのみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="51285-123">The `dotnet migrate` command only supports valid Preview 2 *project.json*-based projects.</span></span> <span data-ttu-id="51285-124">つまり、DNX または Preview 1 の *project.json* ベースのプロジェクトを MSBuild/csproj プロジェクトに直接移行するためには使えません。</span><span class="sxs-lookup"><span data-stu-id="51285-124">This means that you cannot use it to migrate DNX or Preview 1 *project.json*-based projects directly to MSBuild/csproj projects.</span></span> <span data-ttu-id="51285-125">最初にプロジェクトを Preview 2 *project.json* ベースのプロジェクトに手動で移行し、その後で `dotnet migrate` コマンドを使ってプロジェクトを移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51285-125">You first need to manually migrate the project to a Preview 2 *project.json*-based project and then use the `dotnet migrate` command to migrate the project.</span></span>

## <a name="arguments"></a><span data-ttu-id="51285-126">引数</span><span class="sxs-lookup"><span data-stu-id="51285-126">Arguments</span></span>

`PROJECT_JSON/GLOBAL_JSON/SOLUTION_FILE/PROJECT_DIR`

<span data-ttu-id="51285-127">次のいずれかへのパスです。</span><span class="sxs-lookup"><span data-stu-id="51285-127">The path to one of the following:</span></span>

* <span data-ttu-id="51285-128">移行する *project.json* ファイル。</span><span class="sxs-lookup"><span data-stu-id="51285-128">a *project.json* file to migrate.</span></span>
* <span data-ttu-id="51285-129">*global.json* ファイル: *global.json* で指定されているフォルダーを移行します。</span><span class="sxs-lookup"><span data-stu-id="51285-129">a *global.json* file: the folders specified in *global.json* are migrated.</span></span>
* <span data-ttu-id="51285-130">*solution.sln* ファイル: ソリューションで参照されているプロジェクトを移行します。</span><span class="sxs-lookup"><span data-stu-id="51285-130">a *solution.sln* file: the projects referenced in the solution are migrated.</span></span>
* <span data-ttu-id="51285-131">移行するディレクトリ: 移行する *project.json* ファイルを再帰的に検索して、指定したディレクトリ内に移行します。</span><span class="sxs-lookup"><span data-stu-id="51285-131">a directory to migrate: recursively searches for *project.json* files to migrate inside the specified directory.</span></span>

<span data-ttu-id="51285-132">何も指定しない場合の既定値は現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="51285-132">Defaults to current directory if nothing is specified.</span></span>

## <a name="options"></a><span data-ttu-id="51285-133">オプション</span><span class="sxs-lookup"><span data-stu-id="51285-133">Options</span></span>

`--format-report-file-json <REPORT_FILE>`

<span data-ttu-id="51285-134">ユーザー メッセージではなく、JSON として移行レポート ファイルを出力します。</span><span class="sxs-lookup"><span data-stu-id="51285-134">Output migration report file as JSON rather than user messages.</span></span>

`-h|--help`

<span data-ttu-id="51285-135">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="51285-135">Prints out a short help for the command.</span></span>

`-r|--report-file <REPORT_FILE>`

<span data-ttu-id="51285-136">移行レポートをコンソールだけでなく、ファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="51285-136">Output migration report to a file in addition to the console.</span></span>

`-s|--skip-project-references [Debug|Release]`

<span data-ttu-id="51285-137">プロジェクト参照の移行をスキップします。</span><span class="sxs-lookup"><span data-stu-id="51285-137">Skip migrating project references.</span></span> <span data-ttu-id="51285-138">既定では、プロジェクト参照は再帰的に移行されます。</span><span class="sxs-lookup"><span data-stu-id="51285-138">By default, project references are migrated recursively.</span></span>

`--skip-backup`

<span data-ttu-id="51285-139">移行が成功した後、*project.json*、*global.json*、および *\*.xproj* の `backup` ディレクトリへの移動をスキップします。</span><span class="sxs-lookup"><span data-stu-id="51285-139">Skip moving *project.json*, *global.json*, and *\*.xproj* to a `backup` directory after successful migration.</span></span>

`-t|--template-file <TEMPLATE_FILE>`

<span data-ttu-id="51285-140">移行に使用するテンプレートの csproj ファイル。</span><span class="sxs-lookup"><span data-stu-id="51285-140">Template csproj file to use for migration.</span></span> <span data-ttu-id="51285-141">既定では、`dotnet new console` によってドロップされるテンプレートと同じテンプレートが使用されます。</span><span class="sxs-lookup"><span data-stu-id="51285-141">By default, the same template as the one dropped by `dotnet new console` is used.</span></span>

`-v|--sdk-package-version <VERSION>`

<span data-ttu-id="51285-142">移行されたアプリで参照される sdk パッケージのバージョンです。</span><span class="sxs-lookup"><span data-stu-id="51285-142">The version of the sdk package that's referenced in the migrated app.</span></span> <span data-ttu-id="51285-143">既定値は、`dotnet new` 内の SDK のバージョンです。</span><span class="sxs-lookup"><span data-stu-id="51285-143">The default is the version of the SDK in `dotnet new`.</span></span>

`-x|--xproj-file <FILE>`

<span data-ttu-id="51285-144">使用する xproj ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="51285-144">The path to the xproj file to use.</span></span> <span data-ttu-id="51285-145">プロジェクト ディレクトリに複数の xproj がある場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="51285-145">Required when there is more than one xproj in a project directory.</span></span>

## <a name="examples"></a><span data-ttu-id="51285-146">使用例</span><span class="sxs-lookup"><span data-stu-id="51285-146">Examples</span></span>

<span data-ttu-id="51285-147">現在のディレクトリのプロジェクトとそのプロジェクト間の依存関係をすべて移行します。</span><span class="sxs-lookup"><span data-stu-id="51285-147">Migrate a project in the current directory and all of its project-to-project dependencies:</span></span>

`dotnet migrate`

<span data-ttu-id="51285-148">*global.json* ファイルに含まれるすべてのプロジェクトを移行します。</span><span class="sxs-lookup"><span data-stu-id="51285-148">Migrate all projects that *global.json* file includes:</span></span>

`dotnet migrate path/to/global.json`

<span data-ttu-id="51285-149">現在のプロジェクトのみを移行し、プロジェクト間 (P2P) の依存関係は移行しません。</span><span class="sxs-lookup"><span data-stu-id="51285-149">Migrate only the current project and no project-to-project (P2P) dependencies.</span></span> <span data-ttu-id="51285-150">また、特定の SDK バージョンを使います。</span><span class="sxs-lookup"><span data-stu-id="51285-150">Also, use a specific SDK version:</span></span>

`dotnet migrate -s -v 1.0.0-preview4`
