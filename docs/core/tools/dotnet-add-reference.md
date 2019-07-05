---
title: dotnet-add reference コマンド
description: dotnet add 参照コマンドは、プロジェクト間参照を追加する便利なオプションを提供します。
ms.date: 06/26/2019
ms.openlocfilehash: 6e0ca40e701b62dcc18147f9de83cafa6aa2f50f
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2019
ms.locfileid: "67422004"
---
# <a name="dotnet-add-reference"></a><span data-ttu-id="f7635-103">dotnet-add 参照</span><span class="sxs-lookup"><span data-stu-id="f7635-103">dotnet-add reference</span></span>

<span data-ttu-id="f7635-104">**この記事の対象: ✓** .NET Core 1.x SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="f7635-104">**This article applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="f7635-105">name</span><span class="sxs-lookup"><span data-stu-id="f7635-105">Name</span></span>

<span data-ttu-id="f7635-106">`dotnet add reference` - プロジェクト間 (P2P) 参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="f7635-106">`dotnet add reference` - Adds project-to-project (P2P) references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="f7635-107">構文</span><span class="sxs-lookup"><span data-stu-id="f7635-107">Synopsis</span></span>

`dotnet add [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help] [--interactive]`

## <a name="description"></a><span data-ttu-id="f7635-108">説明</span><span class="sxs-lookup"><span data-stu-id="f7635-108">Description</span></span>

<span data-ttu-id="f7635-109">`dotnet add reference` コマンドは、プロジェクトにプロジェクト参照を追加する便利なオプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="f7635-109">The `dotnet add reference` command provides a convenient option to add project references to a project.</span></span> <span data-ttu-id="f7635-110">このコマンドを実行すると、[`<ProjectReference>`](/visualstudio/msbuild/common-msbuild-project-items) 要素がプロジェクト ファイルに追加されます。</span><span class="sxs-lookup"><span data-stu-id="f7635-110">After running the command, the [`<ProjectReference>`](/visualstudio/msbuild/common-msbuild-project-items) elements are added to the project file.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a><span data-ttu-id="f7635-111">引数</span><span class="sxs-lookup"><span data-stu-id="f7635-111">Arguments</span></span>

* **`PROJECT`**

  <span data-ttu-id="f7635-112">プロジェクト ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="f7635-112">Specifies the project file.</span></span> <span data-ttu-id="f7635-113">指定されていない場合、現在のディレクトリで検索されます。</span><span class="sxs-lookup"><span data-stu-id="f7635-113">If not specified, the command searches the current directory for one.</span></span>

* **`PROJECT_REFERENCES`**

  <span data-ttu-id="f7635-114">追加するプロジェクト間参照 (P2P) です。</span><span class="sxs-lookup"><span data-stu-id="f7635-114">Project-to-project (P2P) references to add.</span></span> <span data-ttu-id="f7635-115">1 つ以上のプロジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="f7635-115">Specify one or more projects.</span></span> <span data-ttu-id="f7635-116">[glob パターン](https://en.wikipedia.org/wiki/Glob_(programming))は Unix/Linux ベースのシステムで利用できます。</span><span class="sxs-lookup"><span data-stu-id="f7635-116">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux-based systems.</span></span>

## <a name="options"></a><span data-ttu-id="f7635-117">オプション</span><span class="sxs-lookup"><span data-stu-id="f7635-117">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="f7635-118">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="f7635-118">Prints out a short help for the command.</span></span>

* **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="f7635-119">特定の[フレームワーク](../../standard/frameworks.md)を対象にしている場合にのみ、プロジェクト参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="f7635-119">Adds project references only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

* **`--interactive`**

  <span data-ttu-id="f7635-120">コマンドを停止して、ユーザーの入力または操作のために待機させることができます (たとえば、認証を完了する場合)。</span><span class="sxs-lookup"><span data-stu-id="f7635-120">Allows the command to stop and wait for user input or action (for example, to complete authentication).</span></span> <span data-ttu-id="f7635-121">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="f7635-121">Available since .NET Core 3.0 SDK.</span></span>

## <a name="examples"></a><span data-ttu-id="f7635-122">使用例</span><span class="sxs-lookup"><span data-stu-id="f7635-122">Examples</span></span>

* <span data-ttu-id="f7635-123">プロジェクト参照を追加する:</span><span class="sxs-lookup"><span data-stu-id="f7635-123">Add a project reference:</span></span>

  ```console
  dotnet add app/app.csproj reference lib/lib.csproj
  ```

* <span data-ttu-id="f7635-124">現在のディレクトリのプロジェクトに複数のプロジェクト参照を追加する:</span><span class="sxs-lookup"><span data-stu-id="f7635-124">Add multiple project references to the project in the current directory:</span></span>

  ```console
  dotnet add reference lib1/lib1.csproj lib2/lib2.csproj
  ```

* <span data-ttu-id="f7635-125">Linux/Unix で glob パターンを使って複数のプロジェクト参照を追加する:</span><span class="sxs-lookup"><span data-stu-id="f7635-125">Add multiple project references using a globbing pattern on Linux/Unix:</span></span>

  ```console
  dotnet add app/app.csproj reference **/*.csproj
  ```
