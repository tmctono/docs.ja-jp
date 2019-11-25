---
title: dotnet sln コマンド
description: dotnet-sln コマンドは、ソリューション ファイルでプロジェクトを追加、削除、一覧表示するための便利なオプションを提供します。
ms.date: 10/29/2019
ms.openlocfilehash: 18702c7638798117bd04d5c6a829d64cc6bf18a8
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2019
ms.locfileid: "73191822"
---
# <a name="dotnet-sln"></a><span data-ttu-id="52ddf-103">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="52ddf-103">dotnet sln</span></span>

<span data-ttu-id="52ddf-104">**この記事の対象: ✓** .NET Core 1.x SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="52ddf-104">**This article applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="52ddf-105">name</span><span class="sxs-lookup"><span data-stu-id="52ddf-105">Name</span></span>

<span data-ttu-id="52ddf-106">`dotnet sln` - .NET Core ソリューション ファイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="52ddf-106">`dotnet sln` - Modifies a .NET Core solution file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="52ddf-107">構文</span><span class="sxs-lookup"><span data-stu-id="52ddf-107">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] [command] [-h|--help]
```

## <a name="description"></a><span data-ttu-id="52ddf-108">説明</span><span class="sxs-lookup"><span data-stu-id="52ddf-108">Description</span></span>

<span data-ttu-id="52ddf-109">`dotnet sln` コマンドは、ソリューション ファイルでプロジェクトを追加、削除、一覧表示するための便利な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="52ddf-109">The `dotnet sln` command provides a convenient way to add, remove, and list projects in a solution file.</span></span>

<span data-ttu-id="52ddf-110">`dotnet sln` コマンドを使用するには、ソリューション ファイルが既に存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="52ddf-110">To use the `dotnet sln` command, the solution file must already exist.</span></span> <span data-ttu-id="52ddf-111">作成する必要がある場合、下の例のように [dotnet new](dotnet-new.md) コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="52ddf-111">If you need to create one, use the [dotnet new](dotnet-new.md) command, like in the following example:</span></span>

```dotnetcli
dotnet new sln
```

## <a name="arguments"></a><span data-ttu-id="52ddf-112">引数</span><span class="sxs-lookup"><span data-stu-id="52ddf-112">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="52ddf-113">使用するソリューション ファイル。</span><span class="sxs-lookup"><span data-stu-id="52ddf-113">The solution file to use.</span></span> <span data-ttu-id="52ddf-114">指定されていない場合、現在のディレクトリで検索されます。</span><span class="sxs-lookup"><span data-stu-id="52ddf-114">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="52ddf-115">ディレクトリに複数のソリューション ファイルがある場合、1 つを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52ddf-115">If there are multiple solution files in the directory, one must be specified.</span></span>

## <a name="options"></a><span data-ttu-id="52ddf-116">オプション</span><span class="sxs-lookup"><span data-stu-id="52ddf-116">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="52ddf-117">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="52ddf-117">Prints out a short help for the command.</span></span>

## <a name="commands"></a><span data-ttu-id="52ddf-118">コマンド</span><span class="sxs-lookup"><span data-stu-id="52ddf-118">Commands</span></span>

### `add`

<span data-ttu-id="52ddf-119">ソリューション ファイルに 1 つまたは複数のプロジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="52ddf-119">Adds a project or multiple projects to the solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="52ddf-120">構文</span><span class="sxs-lookup"><span data-stu-id="52ddf-120">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] add [--in-root] [-s|--solution-folder] <PROJECT_PATH>
dotnet sln add [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="52ddf-121">引数</span><span class="sxs-lookup"><span data-stu-id="52ddf-121">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="52ddf-122">使用するソリューション ファイル。</span><span class="sxs-lookup"><span data-stu-id="52ddf-122">The solution file to use.</span></span> <span data-ttu-id="52ddf-123">指定されていない場合、現在のディレクトリで検索されます。</span><span class="sxs-lookup"><span data-stu-id="52ddf-123">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="52ddf-124">ディレクトリに複数のソリューション ファイルがある場合、1 つを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52ddf-124">If there are multiple solution files in the directory, one must be specified.</span></span>

- **`PROJECT_PATH`**

  <span data-ttu-id="52ddf-125">ソリューションに追加するプロジェクトへのパス。</span><span class="sxs-lookup"><span data-stu-id="52ddf-125">The path to the project to add to the solution.</span></span> <span data-ttu-id="52ddf-126">複数のプロジェクトを追加するには、それぞれをスペースで区切って順に追加します。</span><span class="sxs-lookup"><span data-stu-id="52ddf-126">Add multiple projects by adding one after the other separated by spaces.</span></span> <span data-ttu-id="52ddf-127">Unix/Linux シェルの[glob パターン](https://en.wikipedia.org/wiki/Glob_(programming))拡張機能は、`dotnet sln`コマンドで正しく処理されます。</span><span class="sxs-lookup"><span data-stu-id="52ddf-127">Unix/Linux shell [globbing pattern](https://en.wikipedia.org/wiki/Glob_(programming)) expansions are processed correctly by the `dotnet sln` command.</span></span>

#### <a name="options"></a><span data-ttu-id="52ddf-128">オプション</span><span class="sxs-lookup"><span data-stu-id="52ddf-128">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="52ddf-129">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="52ddf-129">Prints out a short help for the command.</span></span>

- **`--in-root`**

  <span data-ttu-id="52ddf-130">ソリューション フォルダーを作成するのではなく、プロジェクトをソリューションのルートに配置します。</span><span class="sxs-lookup"><span data-stu-id="52ddf-130">Places the projects in the root of the solution, rather than creating a solution folder.</span></span> <span data-ttu-id="52ddf-131">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="52ddf-131">Available since .NET Core 3.0 SDK.</span></span>

- **`-s|--solution-folder`**

  <span data-ttu-id="52ddf-132">プロジェクトの追加先のソリューション フォルダーのパス。</span><span class="sxs-lookup"><span data-stu-id="52ddf-132">The destination solution folder path to add the projects to.</span></span> <span data-ttu-id="52ddf-133">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="52ddf-133">Available since .NET Core 3.0 SDK.</span></span>

### `remove`

<span data-ttu-id="52ddf-134">ソリューション ファイルから 1 つまたは複数のプロジェクトを削除します。</span><span class="sxs-lookup"><span data-stu-id="52ddf-134">Removes a project or multiple projects from the solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="52ddf-135">構文</span><span class="sxs-lookup"><span data-stu-id="52ddf-135">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] remove <PROJECT_PATH>
dotnet sln [<SOLUTION_FILE>] remove [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="52ddf-136">引数</span><span class="sxs-lookup"><span data-stu-id="52ddf-136">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="52ddf-137">使用するソリューション ファイル。</span><span class="sxs-lookup"><span data-stu-id="52ddf-137">The solution file to use.</span></span> <span data-ttu-id="52ddf-138">指定されていない場合、現在のディレクトリで検索されます。</span><span class="sxs-lookup"><span data-stu-id="52ddf-138">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="52ddf-139">ディレクトリに複数のソリューション ファイルがある場合、1 つを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52ddf-139">If there are multiple solution files in the directory, one must be specified.</span></span>

- **`PROJECT_PATH`**

  <span data-ttu-id="52ddf-140">ソリューションから削除するプロジェクトへのパス。</span><span class="sxs-lookup"><span data-stu-id="52ddf-140">The path to the project to remove from the solution.</span></span> <span data-ttu-id="52ddf-141">複数のプロジェクトを削除するには、それぞれをスペースで区切って順に追加します。</span><span class="sxs-lookup"><span data-stu-id="52ddf-141">Remove multiple projects by adding one after the other separated by spaces.</span></span> <span data-ttu-id="52ddf-142">Unix/Linux シェルの[glob パターン](https://en.wikipedia.org/wiki/Glob_(programming))拡張機能は、`dotnet sln`コマンドで正しく処理されます。</span><span class="sxs-lookup"><span data-stu-id="52ddf-142">Unix/Linux shell [globbing pattern](https://en.wikipedia.org/wiki/Glob_(programming)) expansions are processed correctly by the `dotnet sln` command.</span></span>

#### <a name="options"></a><span data-ttu-id="52ddf-143">オプション</span><span class="sxs-lookup"><span data-stu-id="52ddf-143">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="52ddf-144">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="52ddf-144">Prints out a short help for the command.</span></span>

### `list`

<span data-ttu-id="52ddf-145">ソリューション ファイルのすべてのプロジェクトを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="52ddf-145">Lists all projects in a solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="52ddf-146">構文</span><span class="sxs-lookup"><span data-stu-id="52ddf-146">Synopsis</span></span>

```dotnetcli
dotnet sln list [-h|--help]
```
  
#### <a name="arguments"></a><span data-ttu-id="52ddf-147">引数</span><span class="sxs-lookup"><span data-stu-id="52ddf-147">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="52ddf-148">使用するソリューション ファイル。</span><span class="sxs-lookup"><span data-stu-id="52ddf-148">The solution file to use.</span></span> <span data-ttu-id="52ddf-149">指定されていない場合、現在のディレクトリで検索されます。</span><span class="sxs-lookup"><span data-stu-id="52ddf-149">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="52ddf-150">ディレクトリに複数のソリューション ファイルがある場合、1 つを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52ddf-150">If there are multiple solution files in the directory, one must be specified.</span></span>

#### <a name="options"></a><span data-ttu-id="52ddf-151">オプション</span><span class="sxs-lookup"><span data-stu-id="52ddf-151">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="52ddf-152">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="52ddf-152">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="52ddf-153">使用例</span><span class="sxs-lookup"><span data-stu-id="52ddf-153">Examples</span></span>

<span data-ttu-id="52ddf-154">ソリューションに 1 つの C# プロジェクトを追加する:</span><span class="sxs-lookup"><span data-stu-id="52ddf-154">Add a C# project to a solution:</span></span>

```dotnetcli
dotnet sln todo.sln add todo-app/todo-app.csproj
```

<span data-ttu-id="52ddf-155">ソリューションから 1 つの C# プロジェクトを削除する:</span><span class="sxs-lookup"><span data-stu-id="52ddf-155">Remove a C# project from a solution:</span></span>

```dotnetcli
dotnet sln todo.sln remove todo-app/todo-app.csproj
```

<span data-ttu-id="52ddf-156">ソリューションに複数の C# プロジェクトを追加する:</span><span class="sxs-lookup"><span data-stu-id="52ddf-156">Add multiple C# projects to a solution:</span></span>

```dotnetcli
dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj
```

<span data-ttu-id="52ddf-157">ソリューションから複数の C# プロジェクトを削除する:</span><span class="sxs-lookup"><span data-stu-id="52ddf-157">Remove multiple C# projects from a solution:</span></span>

```dotnetcli
dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj
```

<span data-ttu-id="52ddf-158">glob パターンを使用して、ソリューションに複数の C# プロジェクトを追加する (Unix/Linux のみ):</span><span class="sxs-lookup"><span data-stu-id="52ddf-158">Add multiple C# projects to a solution using a globbing pattern (Unix/Linux only):</span></span>

```dotnetcli
dotnet sln todo.sln add **/*.csproj
```

<span data-ttu-id="52ddf-159">glob パターンを使用して、ソリューションから複数の C# プロジェクトを削除する (Unix/Linux のみ):</span><span class="sxs-lookup"><span data-stu-id="52ddf-159">Remove multiple C# projects from a solution using a globbing pattern (Unix/Linux only):</span></span>

```dotnetcli
dotnet sln todo.sln remove **/*.csproj
```
