---
title: dotnet sln コマンド
description: dotnet-sln コマンドは、ソリューション ファイルでプロジェクトを追加、削除、一覧表示するための便利なオプションを提供します。
ms.date: 02/14/2020
ms.openlocfilehash: 231287477d986f9ec4a5404cc5278e76c297faa4
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463399"
---
# <a name="dotnet-sln"></a><span data-ttu-id="231b0-103">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="231b0-103">dotnet sln</span></span>

<span data-ttu-id="231b0-104">**この記事の対象:** ✔️ .NET Core 2.x SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="231b0-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="231b0-105">名前</span><span class="sxs-lookup"><span data-stu-id="231b0-105">Name</span></span>

<span data-ttu-id="231b0-106">`dotnet sln` - .NET Core ソリューション ファイル内のプロジェクトを一覧表示または変更します。</span><span class="sxs-lookup"><span data-stu-id="231b0-106">`dotnet sln` - Lists or modifies the projects in a .NET Core solution file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="231b0-107">構文</span><span class="sxs-lookup"><span data-stu-id="231b0-107">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] [command]

dotnet sln [command] -h|--help
```

## <a name="description"></a><span data-ttu-id="231b0-108">説明</span><span class="sxs-lookup"><span data-stu-id="231b0-108">Description</span></span>

<span data-ttu-id="231b0-109">`dotnet sln` コマンドでは、ソリューション ファイル内のプロジェクトを一覧表示および変更するための便利な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="231b0-109">The `dotnet sln` command provides a convenient way to list and modify projects in a solution file.</span></span>

<span data-ttu-id="231b0-110">`dotnet sln` コマンドを使用するには、ソリューション ファイルが既に存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="231b0-110">To use the `dotnet sln` command, the solution file must already exist.</span></span> <span data-ttu-id="231b0-111">作成する必要がある場合、以下の例のように [dotnet new](dotnet-new.md) コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="231b0-111">If you need to create one, use the [dotnet new](dotnet-new.md) command, as in the following example:</span></span>

```dotnetcli
dotnet new sln
```

## <a name="arguments"></a><span data-ttu-id="231b0-112">引数</span><span class="sxs-lookup"><span data-stu-id="231b0-112">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="231b0-113">使用するソリューション ファイル。</span><span class="sxs-lookup"><span data-stu-id="231b0-113">The solution file to use.</span></span> <span data-ttu-id="231b0-114">この引数が省略された場合、コマンドでは、現在のディレクトリでの検索を行います。</span><span class="sxs-lookup"><span data-stu-id="231b0-114">If this argument is omitted, the command searches the current directory for one.</span></span> <span data-ttu-id="231b0-115">ソリューション ファイルが見つからない場合、または複数のソリューション ファイルが見つかった場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="231b0-115">If it finds no solution file or multiple solution files, the command fails.</span></span>

## <a name="options"></a><span data-ttu-id="231b0-116">オプション</span><span class="sxs-lookup"><span data-stu-id="231b0-116">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="231b0-117">コマンドの使用方法を示した説明を出力します。</span><span class="sxs-lookup"><span data-stu-id="231b0-117">Prints out a description of how to use the command.</span></span>

## <a name="commands"></a><span data-ttu-id="231b0-118">コマンド</span><span class="sxs-lookup"><span data-stu-id="231b0-118">Commands</span></span>

### `list`

<span data-ttu-id="231b0-119">ソリューション ファイルのすべてのプロジェクトを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="231b0-119">Lists all projects in a solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="231b0-120">構文</span><span class="sxs-lookup"><span data-stu-id="231b0-120">Synopsis</span></span>

```dotnetcli
dotnet sln list [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="231b0-121">引数</span><span class="sxs-lookup"><span data-stu-id="231b0-121">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="231b0-122">使用するソリューション ファイル。</span><span class="sxs-lookup"><span data-stu-id="231b0-122">The solution file to use.</span></span> <span data-ttu-id="231b0-123">この引数が省略された場合、コマンドでは、現在のディレクトリでの検索を行います。</span><span class="sxs-lookup"><span data-stu-id="231b0-123">If this argument is omitted, the command searches the current directory for one.</span></span> <span data-ttu-id="231b0-124">ソリューション ファイルが見つからない場合、または複数のソリューション ファイルが見つかった場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="231b0-124">If it finds no solution file or multiple solution files, the command fails.</span></span>

#### <a name="options"></a><span data-ttu-id="231b0-125">オプション</span><span class="sxs-lookup"><span data-stu-id="231b0-125">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="231b0-126">コマンドの使用方法を示した説明を出力します。</span><span class="sxs-lookup"><span data-stu-id="231b0-126">Prints out a description of how to use the command.</span></span>
  
### `add`

<span data-ttu-id="231b0-127">1 つ以上のプロジェクトをソリューション ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="231b0-127">Adds one or more projects to the solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="231b0-128">構文</span><span class="sxs-lookup"><span data-stu-id="231b0-128">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] add [--in-root] [-s|--solution-folder <PATH>] <PROJECT_PATH> [<PROJECT_PATH>...]
dotnet sln add [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="231b0-129">引数</span><span class="sxs-lookup"><span data-stu-id="231b0-129">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="231b0-130">使用するソリューション ファイル。</span><span class="sxs-lookup"><span data-stu-id="231b0-130">The solution file to use.</span></span> <span data-ttu-id="231b0-131">指定されていない場合、コマンドでは、現在のディレクトリでの検索を行います。複数のソリューション ファイルがある場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="231b0-131">If it is unspecified, the command searches the current directory for one and fails if there are multiple solution files.</span></span>

- **`PROJECT_PATH`**

  <span data-ttu-id="231b0-132">ソリューションに追加する 1 つ以上のプロジェクトへのパス。</span><span class="sxs-lookup"><span data-stu-id="231b0-132">The path to the project or projects to add to the solution.</span></span> <span data-ttu-id="231b0-133">Unix/Linux シェルの[glob パターン](https://en.wikipedia.org/wiki/Glob_(programming))拡張機能は、`dotnet sln`コマンドで正しく処理されます。</span><span class="sxs-lookup"><span data-stu-id="231b0-133">Unix/Linux shell [globbing pattern](https://en.wikipedia.org/wiki/Glob_(programming)) expansions are processed correctly by the `dotnet sln` command.</span></span>

#### <a name="options"></a><span data-ttu-id="231b0-134">オプション</span><span class="sxs-lookup"><span data-stu-id="231b0-134">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="231b0-135">コマンドの使用方法を示した説明を出力します。</span><span class="sxs-lookup"><span data-stu-id="231b0-135">Prints out a description of how to use the command.</span></span>

- **`--in-root`**

  <span data-ttu-id="231b0-136">ソリューション フォルダーを作成するのではなく、プロジェクトをソリューションのルートに配置します。</span><span class="sxs-lookup"><span data-stu-id="231b0-136">Places the projects in the root of the solution, rather than creating a solution folder.</span></span> <span data-ttu-id="231b0-137">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="231b0-137">Available since .NET Core 3.0 SDK.</span></span>

- **`-s|--solution-folder <PATH>`**

  <span data-ttu-id="231b0-138">プロジェクトの追加先のソリューション フォルダーのパス。</span><span class="sxs-lookup"><span data-stu-id="231b0-138">The destination solution folder path to add the projects to.</span></span> <span data-ttu-id="231b0-139">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="231b0-139">Available since .NET Core 3.0 SDK.</span></span>

### `remove`

<span data-ttu-id="231b0-140">ソリューション ファイルから 1 つまたは複数のプロジェクトを削除します。</span><span class="sxs-lookup"><span data-stu-id="231b0-140">Removes a project or multiple projects from the solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="231b0-141">構文</span><span class="sxs-lookup"><span data-stu-id="231b0-141">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] remove <PROJECT_PATH> [<PROJECT_PATH>...]
dotnet sln [<SOLUTION_FILE>] remove [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="231b0-142">引数</span><span class="sxs-lookup"><span data-stu-id="231b0-142">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="231b0-143">使用するソリューション ファイル。</span><span class="sxs-lookup"><span data-stu-id="231b0-143">The solution file to use.</span></span> <span data-ttu-id="231b0-144">指定されていない場合、コマンドでは、現在のディレクトリでの検索を行います。複数のソリューション ファイルがある場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="231b0-144">If is left unspecified, the command searches the current directory for one and fails if there are multiple solution files.</span></span>

- **`PROJECT_PATH`**

  <span data-ttu-id="231b0-145">ソリューションに追加する 1 つ以上のプロジェクトへのパス。</span><span class="sxs-lookup"><span data-stu-id="231b0-145">The path to the project or projects to add to the solution.</span></span> <span data-ttu-id="231b0-146">Unix/Linux シェルの[glob パターン](https://en.wikipedia.org/wiki/Glob_(programming))拡張機能は、`dotnet sln`コマンドで正しく処理されます。</span><span class="sxs-lookup"><span data-stu-id="231b0-146">Unix/Linux shell [globbing pattern](https://en.wikipedia.org/wiki/Glob_(programming)) expansions are processed correctly by the `dotnet sln` command.</span></span>

#### <a name="options"></a><span data-ttu-id="231b0-147">オプション</span><span class="sxs-lookup"><span data-stu-id="231b0-147">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="231b0-148">コマンドの使用方法を示した説明を出力します。</span><span class="sxs-lookup"><span data-stu-id="231b0-148">Prints out a description of how to use the command.</span></span>

## <a name="examples"></a><span data-ttu-id="231b0-149">使用例</span><span class="sxs-lookup"><span data-stu-id="231b0-149">Examples</span></span>

- <span data-ttu-id="231b0-150">ソリューション内のプロジェクトを一覧表示する:</span><span class="sxs-lookup"><span data-stu-id="231b0-150">List the projects in a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln list
  ```

- <span data-ttu-id="231b0-151">ソリューションに 1 つの C# プロジェクトを追加する:</span><span class="sxs-lookup"><span data-stu-id="231b0-151">Add a C# project to a solution:</span></span>

  ```dotnetcli
  dotnet sln add todo-app/todo-app.csproj
  ```

- <span data-ttu-id="231b0-152">ソリューションから 1 つの C# プロジェクトを削除する:</span><span class="sxs-lookup"><span data-stu-id="231b0-152">Remove a C# project from a solution:</span></span>

  ```dotnetcli
  dotnet sln remove todo-app/todo-app.csproj
  ```

- <span data-ttu-id="231b0-153">ソリューションのルートに複数の C# プロジェクトを追加する:</span><span class="sxs-lookup"><span data-stu-id="231b0-153">Add multiple C# projects to the root of a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj --in-root
  ```

- <span data-ttu-id="231b0-154">ソリューションに複数の C# プロジェクトを追加する:</span><span class="sxs-lookup"><span data-stu-id="231b0-154">Add multiple C# projects to a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj
  ```

- <span data-ttu-id="231b0-155">ソリューションから複数の C# プロジェクトを削除する:</span><span class="sxs-lookup"><span data-stu-id="231b0-155">Remove multiple C# projects from a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj
  ```

- <span data-ttu-id="231b0-156">glob パターンを使用して、ソリューションに複数の C# プロジェクトを追加する (Unix/Linux のみ):</span><span class="sxs-lookup"><span data-stu-id="231b0-156">Add multiple C# projects to a solution using a globbing pattern (Unix/Linux only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln add **/*.csproj
  ```

- <span data-ttu-id="231b0-157">glob パターンを使用して、ソリューションに複数の C# プロジェクトを追加する (Windows PowerShell のみ):</span><span class="sxs-lookup"><span data-stu-id="231b0-157">Add multiple C# projects to a solution using a globbing pattern (Windows PowerShell only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln add (ls **/*.csproj)
  ```

- <span data-ttu-id="231b0-158">glob パターンを使用して、ソリューションから複数の C# プロジェクトを削除する (Unix/Linux のみ):</span><span class="sxs-lookup"><span data-stu-id="231b0-158">Remove multiple C# projects from a solution using a globbing pattern (Unix/Linux only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln remove **/*.csproj
  ```

- <span data-ttu-id="231b0-159">glob パターンを使用して、ソリューションから複数の C# プロジェクトを削除する (Windows PowerShell のみ):</span><span class="sxs-lookup"><span data-stu-id="231b0-159">Remove multiple C# projects from a solution using a globbing pattern (Windows PowerShell only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln remove (ls **/*.csproj)
  ```
