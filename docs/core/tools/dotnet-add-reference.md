---
title: dotnet add reference コマンド
description: dotnet add 参照コマンドは、プロジェクト間参照を追加する便利なオプションを提供します。
ms.date: 02/14/2020
ms.openlocfilehash: f2bd67d181784c4858b8971d05053d196df7818e
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463745"
---
# <a name="dotnet-add-reference"></a><span data-ttu-id="8f811-103">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="8f811-103">dotnet add reference</span></span>

<span data-ttu-id="8f811-104">**この記事の対象:** ✔️ .NET Core 2.x SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="8f811-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="8f811-105">名前</span><span class="sxs-lookup"><span data-stu-id="8f811-105">Name</span></span>

<span data-ttu-id="8f811-106">`dotnet add reference` - プロジェクト間 (P2P) 参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="8f811-106">`dotnet add reference` - Adds project-to-project (P2P) references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="8f811-107">構文</span><span class="sxs-lookup"><span data-stu-id="8f811-107">Synopsis</span></span>

```dotnetcli
dotnet add [<PROJECT>] reference [-f|--framework <FRAMEWORK>]
     [--interactive] <PROJECT_REFERENCES>

dotnet add reference -h|--help
```

## <a name="description"></a><span data-ttu-id="8f811-108">説明</span><span class="sxs-lookup"><span data-stu-id="8f811-108">Description</span></span>

<span data-ttu-id="8f811-109">`dotnet add reference` コマンドは、プロジェクトにプロジェクト参照を追加する便利なオプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="8f811-109">The `dotnet add reference` command provides a convenient option to add project references to a project.</span></span> <span data-ttu-id="8f811-110">このコマンドを実行すると、`<ProjectReference>` 要素がプロジェクト ファイルに追加されます。</span><span class="sxs-lookup"><span data-stu-id="8f811-110">After running the command, the `<ProjectReference>` elements are added to the project file.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a><span data-ttu-id="8f811-111">引数</span><span class="sxs-lookup"><span data-stu-id="8f811-111">Arguments</span></span>

- **`PROJECT`**

  <span data-ttu-id="8f811-112">プロジェクト ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="8f811-112">Specifies the project file.</span></span> <span data-ttu-id="8f811-113">指定されていない場合、現在のディレクトリで検索されます。</span><span class="sxs-lookup"><span data-stu-id="8f811-113">If not specified, the command searches the current directory for one.</span></span>

- **`PROJECT_REFERENCES`**

  <span data-ttu-id="8f811-114">追加するプロジェクト間参照 (P2P) です。</span><span class="sxs-lookup"><span data-stu-id="8f811-114">Project-to-project (P2P) references to add.</span></span> <span data-ttu-id="8f811-115">1 つ以上のプロジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="8f811-115">Specify one or more projects.</span></span> <span data-ttu-id="8f811-116">[glob パターン](https://en.wikipedia.org/wiki/Glob_(programming))は Unix/Linux ベースのシステムで利用できます。</span><span class="sxs-lookup"><span data-stu-id="8f811-116">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux-based systems.</span></span>

## <a name="options"></a><span data-ttu-id="8f811-117">オプション</span><span class="sxs-lookup"><span data-stu-id="8f811-117">Options</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="8f811-118">特定の[フレームワーク](../../standard/frameworks.md)を対象にしている場合にのみ、プロジェクト参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="8f811-118">Adds project references only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

- **`-h|--help`**

  <span data-ttu-id="8f811-119">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="8f811-119">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="8f811-120">コマンドを停止して、ユーザーの入力または操作のために待機させることができます (たとえば、認証を完了する場合)。</span><span class="sxs-lookup"><span data-stu-id="8f811-120">Allows the command to stop and wait for user input or action (for example, to complete authentication).</span></span> <span data-ttu-id="8f811-121">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="8f811-121">Available since .NET Core 3.0 SDK.</span></span>

## <a name="examples"></a><span data-ttu-id="8f811-122">使用例</span><span class="sxs-lookup"><span data-stu-id="8f811-122">Examples</span></span>

- <span data-ttu-id="8f811-123">プロジェクト参照を追加する:</span><span class="sxs-lookup"><span data-stu-id="8f811-123">Add a project reference:</span></span>

  ```dotnetcli
  dotnet add app/app.csproj reference lib/lib.csproj
  ```

- <span data-ttu-id="8f811-124">現在のディレクトリのプロジェクトに複数のプロジェクト参照を追加する:</span><span class="sxs-lookup"><span data-stu-id="8f811-124">Add multiple project references to the project in the current directory:</span></span>

  ```dotnetcli
  dotnet add reference lib1/lib1.csproj lib2/lib2.csproj
  ```

- <span data-ttu-id="8f811-125">Linux/Unix で glob パターンを使って複数のプロジェクト参照を追加する:</span><span class="sxs-lookup"><span data-stu-id="8f811-125">Add multiple project references using a globbing pattern on Linux/Unix:</span></span>

  ```dotnetcli
  dotnet add app/app.csproj reference **/*.csproj
  ```
