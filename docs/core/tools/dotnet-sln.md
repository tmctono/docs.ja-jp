---
title: dotnet sln コマンド
description: dotnet-sln コマンドは、ソリューション ファイルでプロジェクトを追加、削除、一覧表示するための便利なオプションを提供します。
ms.date: 06/13/2018
ms.openlocfilehash: 84508aaefff61b31e2965576ebc2daaae7331951
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117592"
---
# <a name="dotnet-sln"></a><span data-ttu-id="92811-103">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="92811-103">dotnet sln</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="92811-104">name</span><span class="sxs-lookup"><span data-stu-id="92811-104">Name</span></span>

<span data-ttu-id="92811-105">`dotnet sln` - .NET Core ソリューション ファイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="92811-105">`dotnet sln` - Modifies a .NET Core solution file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="92811-106">構文</span><span class="sxs-lookup"><span data-stu-id="92811-106">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_NAME>] add <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] add <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] remove <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] remove <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] list
dotnet sln [-h|--help]
```

## <a name="description"></a><span data-ttu-id="92811-107">説明</span><span class="sxs-lookup"><span data-stu-id="92811-107">Description</span></span>

<span data-ttu-id="92811-108">`dotnet sln` コマンドは、ソリューション ファイルでプロジェクトを追加、削除、一覧表示するための便利な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="92811-108">The `dotnet sln` command provides a convenient way to add, remove, and list projects in a solution file.</span></span>

<span data-ttu-id="92811-109">`dotnet sln` コマンドを使用するには、ソリューション ファイルが既に存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="92811-109">To use the `dotnet sln` command, the solution file must already exist.</span></span> <span data-ttu-id="92811-110">作成する必要がある場合、下の例のように [dotnet new](dotnet-new.md) コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="92811-110">If you need to create one, use the [dotnet new](dotnet-new.md) command, like in the following example:</span></span>

```dotnetcli
dotnet new sln
```

## <a name="commands"></a><span data-ttu-id="92811-111">コマンド</span><span class="sxs-lookup"><span data-stu-id="92811-111">Commands</span></span>

`add <PROJECT> ...`

`add <GLOBBING_PATTERN>`

<span data-ttu-id="92811-112">ソリューション ファイルに 1 つまたは複数のプロジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="92811-112">Adds a project or multiple projects to the solution file.</span></span> <span data-ttu-id="92811-113">[Glob パターン](https://en.wikipedia.org/wiki/Glob_(programming))は Unix/Linux ベースの端末でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="92811-113">[Globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

`remove <PROJECT> ...`

`remove <GLOBBING_PATTERN>`

<span data-ttu-id="92811-114">ソリューション ファイルから 1 つまたは複数のプロジェクトを削除します。</span><span class="sxs-lookup"><span data-stu-id="92811-114">Removes a project or multiple projects from the solution file.</span></span> <span data-ttu-id="92811-115">[Glob パターン](https://en.wikipedia.org/wiki/Glob_(programming))は Unix/Linux ベースの端末でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="92811-115">[Globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

`list`

<span data-ttu-id="92811-116">ソリューション ファイルのすべてのプロジェクトを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="92811-116">Lists all projects in a solution file.</span></span>

## <a name="arguments"></a><span data-ttu-id="92811-117">引数</span><span class="sxs-lookup"><span data-stu-id="92811-117">Arguments</span></span>

`SOLUTION_NAME`

<span data-ttu-id="92811-118">使用するソリューション ファイル。</span><span class="sxs-lookup"><span data-stu-id="92811-118">Solution file to use.</span></span> <span data-ttu-id="92811-119">指定されていない場合、現在のディレクトリで検索されます。</span><span class="sxs-lookup"><span data-stu-id="92811-119">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="92811-120">ディレクトリに複数のソリューション ファイルがある場合、1 つを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92811-120">If there are multiple solution files in the directory, one must be specified.</span></span>

## <a name="options"></a><span data-ttu-id="92811-121">オプション</span><span class="sxs-lookup"><span data-stu-id="92811-121">Options</span></span>

`-h|--help`

<span data-ttu-id="92811-122">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="92811-122">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="92811-123">使用例</span><span class="sxs-lookup"><span data-stu-id="92811-123">Examples</span></span>

<span data-ttu-id="92811-124">ソリューションに 1 つの C# プロジェクトを追加する:</span><span class="sxs-lookup"><span data-stu-id="92811-124">Add a C# project to a solution:</span></span>

`dotnet sln todo.sln add todo-app/todo-app.csproj`

<span data-ttu-id="92811-125">ソリューションから 1 つの C# プロジェクトを削除する:</span><span class="sxs-lookup"><span data-stu-id="92811-125">Remove a C# project from a solution:</span></span>

`dotnet sln todo.sln remove todo-app/todo-app.csproj`

<span data-ttu-id="92811-126">ソリューションに複数の C# プロジェクトを追加する:</span><span class="sxs-lookup"><span data-stu-id="92811-126">Add multiple C# projects to a solution:</span></span>

`dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj`

<span data-ttu-id="92811-127">ソリューションから複数の C# プロジェクトを削除する:</span><span class="sxs-lookup"><span data-stu-id="92811-127">Remove multiple C# projects from a solution:</span></span>

`dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj`

<span data-ttu-id="92811-128">glob パターンを使用して、C# ソリューションに複数のプロジェクトを追加する:</span><span class="sxs-lookup"><span data-stu-id="92811-128">Add multiple C# projects to a solution using a globbing pattern:</span></span>

`dotnet sln todo.sln add **/*.csproj`

<span data-ttu-id="92811-129">glob パターンを使用して、C# ソリューションから複数のプロジェクトを削除する:</span><span class="sxs-lookup"><span data-stu-id="92811-129">Remove multiple C# projects from a solution using a globbing pattern:</span></span>

`dotnet sln todo.sln remove **/*.csproj`

> [!NOTE]
> <span data-ttu-id="92811-130">グロビングは CLI 機能ではなく、コマンド シェルの機能です。</span><span class="sxs-lookup"><span data-stu-id="92811-130">Globbing is not a CLI feature but rather a feature of the command shell.</span></span> <span data-ttu-id="92811-131">ファイルを正常に展開するには、グロビングをサポートするシェルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92811-131">To successfully expand the files, you must use a shell that supports globbing.</span></span> <span data-ttu-id="92811-132">グロビングの詳細については、[Wikipedia](https://en.wikipedia.org/wiki/Glob_(programming)) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92811-132">For more information about globbing, see [Wikipedia](https://en.wikipedia.org/wiki/Glob_(programming)).</span></span>
