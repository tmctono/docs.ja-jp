---
title: dotnet add package コマンド
description: "'dotnet add package' コマンドは、NuGet パッケージ参照をプロジェクトに追加する便利なオプションを提供します。"
ms.date: 06/26/2019
ms.openlocfilehash: 50a352be66f2b4bd4498d79f61dc01f56d4b00c5
ms.sourcegitcommit: 4a3c95e91289d16c38979575a245a4f76b0da147
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2019
ms.locfileid: "67569513"
---
# <a name="dotnet-add-package"></a><span data-ttu-id="d5901-103">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="d5901-103">dotnet add package</span></span>

<span data-ttu-id="d5901-104">**この記事の対象: ✓** .NET Core 1.x SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="d5901-104">**This article applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="d5901-105">name</span><span class="sxs-lookup"><span data-stu-id="d5901-105">Name</span></span>

<span data-ttu-id="d5901-106">`dotnet add package` - プロジェクト ファイルにパッケージ参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="d5901-106">`dotnet add package` - Adds a package reference to a project file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d5901-107">構文</span><span class="sxs-lookup"><span data-stu-id="d5901-107">Synopsis</span></span>

`dotnet add [<PROJECT>] package <PACKAGE_NAME> [-h|--help] [-f|--framework] [--interactive] [-n|--no-restore] [--package-directory] [-s|--source] [-v|--version]`

## <a name="description"></a><span data-ttu-id="d5901-108">説明</span><span class="sxs-lookup"><span data-stu-id="d5901-108">Description</span></span>

<span data-ttu-id="d5901-109">`dotnet add package` コマンドは、プロジェクト ファイルにパッケージ参照を追加する便利なオプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="d5901-109">The `dotnet add package` command provides a convenient option to add a package reference to a project file.</span></span> <span data-ttu-id="d5901-110">このコマンドの実行後に、パッケージがプロジェクト内のフレームワークと互換性があることを確認する互換性チェックがあります。</span><span class="sxs-lookup"><span data-stu-id="d5901-110">After running the command, there's a compatibility check to ensure the package is compatible with the frameworks in the project.</span></span> <span data-ttu-id="d5901-111">互換性チェックに合格すると、`<PackageReference>` 要素がプロジェクト ファイルに追加されて、[dotnet restore](dotnet-restore.md) が実行されます。</span><span class="sxs-lookup"><span data-stu-id="d5901-111">If the check passes, a `<PackageReference>` element is added to the project file and [dotnet restore](dotnet-restore.md) is run.</span></span>

[!INCLUDE[DotNet Restore Note](../../../includes/dotnet-restore-note.md)]

<span data-ttu-id="d5901-112">たとえば、`Newtonsoft.Json` を *ToDo.csproj* に追加すると、次のような出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="d5901-112">For example, adding `Newtonsoft.Json` to *ToDo.csproj* produces output similar to the following example:</span></span>

```console
  Writing C:\Users\mairaw\AppData\Local\Temp\tmp95A8.tmp
info : Adding PackageReference for package 'Newtonsoft.Json' into project 'C:\projects\ToDo\ToDo.csproj'.
log  : Restoring packages for C:\Temp\projects\consoleproj\consoleproj.csproj...
info :   GET https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json
info :   OK https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json 79ms
info :   GET https://api.nuget.org/v3-flatcontainer/newtonsoft.json/12.0.1/newtonsoft.json.12.0.1.nupkg
info :   OK https://api.nuget.org/v3-flatcontainer/newtonsoft.json/12.0.1/newtonsoft.json.12.0.1.nupkg 232ms
log  : Installing Newtonsoft.Json 12.0.1.
info : Package 'Newtonsoft.Json' is compatible with all the specified frameworks in project 'C:\projects\ToDo\ToDo.csproj'.
info : PackageReference for package 'Newtonsoft.Json' version '12.0.1' added to file 'C:\projects\ToDo\ToDo.csproj'.
```

<span data-ttu-id="d5901-113">この *ToDo.csproj* ファイルには、参照されるパッケージの [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) 要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d5901-113">The *ToDo.csproj* file now contains a [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) element for the referenced package.</span></span>

```xml
<PackageReference Include="Newtonsoft.Json" Version="12.0.1" />
```

## <a name="arguments"></a><span data-ttu-id="d5901-114">引数</span><span class="sxs-lookup"><span data-stu-id="d5901-114">Arguments</span></span>

* **`PROJECT`**

  <span data-ttu-id="d5901-115">プロジェクト ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="d5901-115">Specifies the project file.</span></span> <span data-ttu-id="d5901-116">指定されていない場合、現在のディレクトリで検索されます。</span><span class="sxs-lookup"><span data-stu-id="d5901-116">If not specified, the command searches the current directory for one.</span></span>

* **`PACKAGE_NAME`**

  <span data-ttu-id="d5901-117">追加するパッケージ参照。</span><span class="sxs-lookup"><span data-stu-id="d5901-117">The package reference to add.</span></span>

## <a name="options"></a><span data-ttu-id="d5901-118">オプション</span><span class="sxs-lookup"><span data-stu-id="d5901-118">Options</span></span>

* **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="d5901-119">特定の[フレームワーク](../../standard/frameworks.md)を対象にしている場合にのみ、パッケージ参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="d5901-119">Adds a package reference only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

* **`-h|--help`**

  <span data-ttu-id="d5901-120">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="d5901-120">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="d5901-121">コマンドを停止して、ユーザーの入力または操作のために待機させることができます (たとえば、認証を完了する場合)。</span><span class="sxs-lookup"><span data-stu-id="d5901-121">Allows the command to stop and wait for user input or action (for example, to complete authentication).</span></span> <span data-ttu-id="d5901-122">.NET Core 2.1 SDK バージョン 2.1.400 以降で使用可能です。</span><span class="sxs-lookup"><span data-stu-id="d5901-122">Available since .NET Core 2.1 SDK, version 2.1.400 or later.</span></span>

* **`-n|--no-restore`**

  <span data-ttu-id="d5901-123">復元のプレビューと互換性チェックを実行せずにパッケージ参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="d5901-123">Adds a package reference without performing a restore preview and compatibility check.</span></span>

* **`--package-directory <PACKAGE_DIRECTORY>`**

  <span data-ttu-id="d5901-124">パッケージの復元先となるディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="d5901-124">The directory where to restore the packages.</span></span> <span data-ttu-id="d5901-125">既定のパッケージ復元場所は、Windows の場合は `%userprofile%\.nuget\packages`、macOS と Linux の場合は `~/.nuget/packages` です。</span><span class="sxs-lookup"><span data-stu-id="d5901-125">The default package restore location is `%userprofile%\.nuget\packages` on Windows and `~/.nuget/packages` on macOS and Linux.</span></span> <span data-ttu-id="d5901-126">詳細については、[NuGet でのグローバル パッケージ、キャッシュ、および一時フォルダーの管理](https://docs.microsoft.com/nuget/consume-packages/managing-the-global-packages-and-cache-folders)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5901-126">For more information, see [Managing the global packages, cache, and temp folders in NuGet](https://docs.microsoft.com/nuget/consume-packages/managing-the-global-packages-and-cache-folders).</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="d5901-127">復元操作時に使用する NuGet パッケージのソース。</span><span class="sxs-lookup"><span data-stu-id="d5901-127">The NuGet package source to use during the restore operation.</span></span>

* **`-v|--version <VERSION>`**

  <span data-ttu-id="d5901-128">パッケージのバージョン。</span><span class="sxs-lookup"><span data-stu-id="d5901-128">Version of the package.</span></span> <span data-ttu-id="d5901-129">[NuGet パッケージのバージョン管理](https://docs.microsoft.com/nuget/reference/package-versioning)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5901-129">See [NuGet package versioning](https://docs.microsoft.com/nuget/reference/package-versioning).</span></span>

## <a name="examples"></a><span data-ttu-id="d5901-130">使用例</span><span class="sxs-lookup"><span data-stu-id="d5901-130">Examples</span></span>

* <span data-ttu-id="d5901-131">`Newtonsoft.Json` NuGet パッケージをプロジェクトに追加する:</span><span class="sxs-lookup"><span data-stu-id="d5901-131">Add `Newtonsoft.Json` NuGet package to a project:</span></span>

  ```console
  dotnet add package Newtonsoft.Json
  ```

* <span data-ttu-id="d5901-132">特定バージョンのパッケージをプロジェクトに追加する:</span><span class="sxs-lookup"><span data-stu-id="d5901-132">Add a specific version of a package to a project:</span></span>

  ```console
  dotnet add ToDo.csproj package Microsoft.Azure.DocumentDB.Core -v 1.0.0
  ```

* <span data-ttu-id="d5901-133">特定の NuGet ソースを使用してパッケージを追加する:</span><span class="sxs-lookup"><span data-stu-id="d5901-133">Add a package using a specific NuGet source:</span></span>

  ```console
  dotnet add package Microsoft.AspNetCore.StaticFiles -s https://dotnet.myget.org/F/dotnet-core/api/v3/index.json
  ```

## <a name="see-also"></a><span data-ttu-id="d5901-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="d5901-134">See also</span></span>

- [<span data-ttu-id="d5901-135">NuGet でグローバル パッケージ、キャッシュ、および一時フォルダーを管理する</span><span class="sxs-lookup"><span data-stu-id="d5901-135">Managing the global packages, cache, and temp folders in NuGet</span></span>](https://docs.microsoft.com/nuget/consume-packages/managing-the-global-packages-and-cache-folders)
- [<span data-ttu-id="d5901-136">NuGet パッケージのバージョン管理</span><span class="sxs-lookup"><span data-stu-id="d5901-136">NuGet package versioning</span></span>](https://docs.microsoft.com/nuget/reference/package-versioning)
