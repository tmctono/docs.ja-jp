---
title: dotnet migrate コマンド
description: dotnet migrate コマンドは、プロジェクトとそのすべての依存関係を移行します。
ms.date: 08/08/2019
ms.openlocfilehash: afc16161761d151e743e53a8572a6564add43517
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117689"
---
# <a name="dotnet-migrate"></a><span data-ttu-id="3c89a-103">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="3c89a-103">dotnet migrate</span></span>

<span data-ttu-id="3c89a-104">**この記事の対象: ✓** .NET Core 1.x SDK **✓** .NET Core 2.x SDK</span><span class="sxs-lookup"><span data-stu-id="3c89a-104">**This article applies to: ✓** .NET Core 1.x SDK **✓** .NET Core 2.x SDK</span></span>

## <a name="name"></a><span data-ttu-id="3c89a-105">name</span><span class="sxs-lookup"><span data-stu-id="3c89a-105">Name</span></span>

<span data-ttu-id="3c89a-106">`dotnet migrate` - Preview 2 .NET Core プロジェクトを .NET Core SDK スタイルのプロジェクトに移行します。</span><span class="sxs-lookup"><span data-stu-id="3c89a-106">`dotnet migrate` - Migrates a Preview 2 .NET Core project to a .NET Core SDK-style project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="3c89a-107">構文</span><span class="sxs-lookup"><span data-stu-id="3c89a-107">Synopsis</span></span>

```dotnetcli
dotnet migrate [<SOLUTION_FILE|PROJECT_DIR>] [--format-report-file-json] [-r|--report-file] [-s|--skip-project-references] [--skip-backup] [-t|--template-file] [-v|--sdk-package-version] [-x|--xproj-file]
dotnet migrate [-h|--help]
```

## <a name="description"></a><span data-ttu-id="3c89a-108">説明</span><span class="sxs-lookup"><span data-stu-id="3c89a-108">Description</span></span>

<span data-ttu-id="3c89a-109">`dotnet migrate` コマンドは、有効な Preview 2 *project.json* ベースのプロジェクトを有効な .NET Core SDK スタイルの *csproj* プロジェクトに移行します。</span><span class="sxs-lookup"><span data-stu-id="3c89a-109">The `dotnet migrate` command migrates a valid Preview 2 *project.json*-based project to a valid .NET Core SDK-style *csproj* project.</span></span>

<span data-ttu-id="3c89a-110">既定では、このコマンドは、ルート プロジェクトとルート プロジェクトに含まれるすべてのプロジェクト参照を移行します。</span><span class="sxs-lookup"><span data-stu-id="3c89a-110">By default, the command migrates the root project and any project references that the root project contains.</span></span> <span data-ttu-id="3c89a-111">この動作は、実行時に `--skip-project-references` オプションを使って、無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="3c89a-111">This behavior is disabled using the `--skip-project-references` option at runtime.</span></span>

<span data-ttu-id="3c89a-112">移行は次のアセットで実行できます。</span><span class="sxs-lookup"><span data-stu-id="3c89a-112">Migration can be performed on the following assets:</span></span>

* <span data-ttu-id="3c89a-113">1 つのプロジェクト。移行する *project.json* ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="3c89a-113">A single project by specifying the *project.json* file to migrate.</span></span>
* <span data-ttu-id="3c89a-114">*global.json* ファイルで指定されているすべてのディレクトリ。*global.json* ファイルへのパスを渡します。</span><span class="sxs-lookup"><span data-stu-id="3c89a-114">All of the directories specified in the *global.json* file by passing in a path to the *global.json* file.</span></span>
* <span data-ttu-id="3c89a-115">*solution.sln* ファイル。ソリューションで参照されているプロジェクトを移行します。</span><span class="sxs-lookup"><span data-stu-id="3c89a-115">A *solution.sln* file, where it migrates the projects referenced in the solution.</span></span>
* <span data-ttu-id="3c89a-116">特定のディレクトリのすべてのサブディレクトリ (再帰的)。</span><span class="sxs-lookup"><span data-stu-id="3c89a-116">On all subdirectories of the given directory recursively.</span></span>

<span data-ttu-id="3c89a-117">`dotnet migrate` コマンドは、`backup` ディレクトリ内に移行された *project.json* ファイルを保持します。ディレクトリが存在しない場合は作成されます。</span><span class="sxs-lookup"><span data-stu-id="3c89a-117">The `dotnet migrate` command keeps the migrated *project.json* file inside a `backup` directory, which it creates if the directory doesn't exist.</span></span> <span data-ttu-id="3c89a-118">この動作は、`--skip-backup` オプションを使ってオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="3c89a-118">This behavior is overridden using the `--skip-backup` option.</span></span>

<span data-ttu-id="3c89a-119">既定では、移行操作は、標準出力 (STDOUT) に移行プロセスの状態を出力します。</span><span class="sxs-lookup"><span data-stu-id="3c89a-119">By default, the migration operation outputs the state of the migration process to standard output (STDOUT).</span></span> <span data-ttu-id="3c89a-120">`--report-file <REPORT_FILE>` オプションを使うと、指定したファイルに出力が保存を指定します。</span><span class="sxs-lookup"><span data-stu-id="3c89a-120">If you use the `--report-file <REPORT_FILE>` option, the output is saved to the file specify.</span></span>

<span data-ttu-id="3c89a-121">`dotnet migrate` コマンドは、有効な Preview 2 *project.json* ベースのプロジェクトのみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="3c89a-121">The `dotnet migrate` command only supports valid Preview 2 *project.json*-based projects.</span></span> <span data-ttu-id="3c89a-122">つまり、DNX または Preview 1 の *project.json* ベースのプロジェクトを MSBuild/csproj プロジェクトに直接移行するためには使えません。</span><span class="sxs-lookup"><span data-stu-id="3c89a-122">This means that you cannot use it to migrate DNX or Preview 1 *project.json*-based projects directly to MSBuild/csproj projects.</span></span> <span data-ttu-id="3c89a-123">最初にプロジェクトを Preview 2 *project.json* ベースのプロジェクトに手動で移行し、その後で `dotnet migrate` コマンドを使ってプロジェクトを移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c89a-123">You first need to manually migrate the project to a Preview 2 *project.json*-based project and then use the `dotnet migrate` command to migrate the project.</span></span>

<span data-ttu-id="3c89a-124">`dotnet migrate` コマンドは、.NET Core 3.0 SDK 以降では使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="3c89a-124">The `dotnet migrate` command is no longer available starting with .NET Core 3.0 SDK.</span></span>

## <a name="arguments"></a><span data-ttu-id="3c89a-125">引数</span><span class="sxs-lookup"><span data-stu-id="3c89a-125">Arguments</span></span>

`PROJECT_JSON/GLOBAL_JSON/SOLUTION_FILE/PROJECT_DIR`

<span data-ttu-id="3c89a-126">次のいずれかへのパスです。</span><span class="sxs-lookup"><span data-stu-id="3c89a-126">The path to one of the following:</span></span>

* <span data-ttu-id="3c89a-127">移行する *project.json* ファイル。</span><span class="sxs-lookup"><span data-stu-id="3c89a-127">a *project.json* file to migrate.</span></span>
* <span data-ttu-id="3c89a-128">*global.json* ファイル: *global.json* で指定されているフォルダーを移行します。</span><span class="sxs-lookup"><span data-stu-id="3c89a-128">a *global.json* file: the folders specified in *global.json* are migrated.</span></span>
* <span data-ttu-id="3c89a-129">*solution.sln* ファイル: ソリューションで参照されているプロジェクトを移行します。</span><span class="sxs-lookup"><span data-stu-id="3c89a-129">a *solution.sln* file: the projects referenced in the solution are migrated.</span></span>
* <span data-ttu-id="3c89a-130">移行するディレクトリ: 移行する *project.json* ファイルを再帰的に検索して、指定したディレクトリ内に移行します。</span><span class="sxs-lookup"><span data-stu-id="3c89a-130">a directory to migrate: recursively searches for *project.json* files to migrate inside the specified directory.</span></span>

<span data-ttu-id="3c89a-131">何も指定しない場合の既定値は現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="3c89a-131">Defaults to current directory if nothing is specified.</span></span>

## <a name="options"></a><span data-ttu-id="3c89a-132">オプション</span><span class="sxs-lookup"><span data-stu-id="3c89a-132">Options</span></span>

`--format-report-file-json <REPORT_FILE>`

<span data-ttu-id="3c89a-133">ユーザー メッセージではなく、JSON として移行レポート ファイルを出力します。</span><span class="sxs-lookup"><span data-stu-id="3c89a-133">Output migration report file as JSON rather than user messages.</span></span>

`-h|--help`

<span data-ttu-id="3c89a-134">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="3c89a-134">Prints out a short help for the command.</span></span>

`-r|--report-file <REPORT_FILE>`

<span data-ttu-id="3c89a-135">移行レポートをコンソールだけでなく、ファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="3c89a-135">Output migration report to a file in addition to the console.</span></span>

`-s|--skip-project-references [Debug|Release]`

<span data-ttu-id="3c89a-136">プロジェクト参照の移行をスキップします。</span><span class="sxs-lookup"><span data-stu-id="3c89a-136">Skip migrating project references.</span></span> <span data-ttu-id="3c89a-137">既定では、プロジェクト参照は再帰的に移行されます。</span><span class="sxs-lookup"><span data-stu-id="3c89a-137">By default, project references are migrated recursively.</span></span>

`--skip-backup`

<span data-ttu-id="3c89a-138">移行が成功した後、*project.json*、*global.json*、および *\*.xproj* の `backup` ディレクトリへの移動をスキップします。</span><span class="sxs-lookup"><span data-stu-id="3c89a-138">Skip moving *project.json*, *global.json*, and *\*.xproj* to a `backup` directory after successful migration.</span></span>

`-t|--template-file <TEMPLATE_FILE>`

<span data-ttu-id="3c89a-139">移行に使用するテンプレートの csproj ファイル。</span><span class="sxs-lookup"><span data-stu-id="3c89a-139">Template csproj file to use for migration.</span></span> <span data-ttu-id="3c89a-140">既定では、`dotnet new console` によってドロップされるテンプレートと同じテンプレートが使用されます。</span><span class="sxs-lookup"><span data-stu-id="3c89a-140">By default, the same template as the one dropped by `dotnet new console` is used.</span></span>

`-v|--sdk-package-version <VERSION>`

<span data-ttu-id="3c89a-141">移行されたアプリで参照される sdk パッケージのバージョンです。</span><span class="sxs-lookup"><span data-stu-id="3c89a-141">The version of the sdk package that's referenced in the migrated app.</span></span> <span data-ttu-id="3c89a-142">既定値は、`dotnet new` 内の SDK のバージョンです。</span><span class="sxs-lookup"><span data-stu-id="3c89a-142">The default is the version of the SDK in `dotnet new`.</span></span>

`-x|--xproj-file <FILE>`

<span data-ttu-id="3c89a-143">使用する xproj ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="3c89a-143">The path to the xproj file to use.</span></span> <span data-ttu-id="3c89a-144">プロジェクト ディレクトリに複数の xproj がある場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="3c89a-144">Required when there is more than one xproj in a project directory.</span></span>

## <a name="examples"></a><span data-ttu-id="3c89a-145">使用例</span><span class="sxs-lookup"><span data-stu-id="3c89a-145">Examples</span></span>

<span data-ttu-id="3c89a-146">現在のディレクトリのプロジェクトとそのプロジェクト間の依存関係をすべて移行します。</span><span class="sxs-lookup"><span data-stu-id="3c89a-146">Migrate a project in the current directory and all of its project-to-project dependencies:</span></span>

`dotnet migrate`

<span data-ttu-id="3c89a-147">*global.json* ファイルに含まれるすべてのプロジェクトを移行します。</span><span class="sxs-lookup"><span data-stu-id="3c89a-147">Migrate all projects that *global.json* file includes:</span></span>

`dotnet migrate path/to/global.json`

<span data-ttu-id="3c89a-148">現在のプロジェクトのみを移行し、プロジェクト間 (P2P) の依存関係は移行しません。</span><span class="sxs-lookup"><span data-stu-id="3c89a-148">Migrate only the current project and no project-to-project (P2P) dependencies.</span></span> <span data-ttu-id="3c89a-149">また、特定の SDK バージョンを使います。</span><span class="sxs-lookup"><span data-stu-id="3c89a-149">Also, use a specific SDK version:</span></span>

`dotnet migrate -s -v 1.0.0-preview4`
