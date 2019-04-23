---
title: dotnet list package コマンド
description: "\"dotnet list package\" コマンドでは、プロジェクトまたはソリューションのパッケージ参照を列挙する便利なオプションが提供されています。"
ms.date: 04/09/2019
ms.openlocfilehash: bc38b94201f85ed4b22e11722ef5cabcb6fbf040
ms.sourcegitcommit: 859b2ba0c74a1a5a4ad0d59a3c3af23450995981
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/11/2019
ms.locfileid: "59481574"
---
# <a name="dotnet-list-package"></a><span data-ttu-id="bdbeb-103">dotnet list package</span><span class="sxs-lookup"><span data-stu-id="bdbeb-103">dotnet list package</span></span>

[!INCLUDE [topic-appliesto-net-core-22plus](../../../includes/topic-appliesto-net-core-22plus.md)]

## <a name="name"></a><span data-ttu-id="bdbeb-104">name</span><span class="sxs-lookup"><span data-stu-id="bdbeb-104">Name</span></span>

`dotnet list package` <span data-ttu-id="bdbeb-105">- プロジェクトまたはソリューションのパッケージ参照を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="bdbeb-105">- Lists the package references for a project or solution.</span></span>

## <a name="synopsis"></a><span data-ttu-id="bdbeb-106">構文</span><span class="sxs-lookup"><span data-stu-id="bdbeb-106">Synopsis</span></span>

```
dotnet list [<PROJECT | SOLUTION>] package [--config] [--framework] [--highest-minor] [--highest-patch] 
   [--include-prerelease] [--include-transitive] [--outdated] [--source]
dotnet list package [-h|--help]
```

## <a name="description"></a><span data-ttu-id="bdbeb-107">説明</span><span class="sxs-lookup"><span data-stu-id="bdbeb-107">Description</span></span>

<span data-ttu-id="bdbeb-108">`dotnet list package` コマンドでは、特定のプロジェクトまたはソリューションのすべての NuGet パッケージ参照を列挙する便利なオプションが提供されています。</span><span class="sxs-lookup"><span data-stu-id="bdbeb-108">The `dotnet list package` command provides a convenient option to list all NuGet package references for a specific project or a solution.</span></span> <span data-ttu-id="bdbeb-109">このコマンドで処理するために必要なアセットを用意するには、最初にプロジェクトをビルドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bdbeb-109">You first need to build the project in order to have the assets needed for this command to process.</span></span> <span data-ttu-id="bdbeb-110">次の例では、[SentimentAnalysis](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) プロジェクトに対する `dotnet list package` コマンドの出力を示します。</span><span class="sxs-lookup"><span data-stu-id="bdbeb-110">The following example shows the output of the `dotnet list package` command for the [SentimentAnalysis](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) project:</span></span>

```output
Project 'SentimentAnalysis' has the following package references
   [netcoreapp2.1]:
   Top-level Package               Requested   Resolved
   > Microsoft.ML                  0.11.0      0.11.0
   > Microsoft.NETCore.App   (A)   [2.1.0, )   2.1.0

(A) : Auto-referenced package.
```

<span data-ttu-id="bdbeb-111">**[Requested]** 列は、プロジェクト ファイルで指定されているパッケージのバージョンを示し、範囲で示されることもあります。</span><span class="sxs-lookup"><span data-stu-id="bdbeb-111">The **Requested** column refers to the package version specified in the project file and can be a range.</span></span> <span data-ttu-id="bdbeb-112">**[Resolved]** 列には、プロジェクトで現在使用されているバージョンが一覧表示され、常に単一の値です。</span><span class="sxs-lookup"><span data-stu-id="bdbeb-112">The **Resolved** column lists the version that the project is currently using and is always a single value.</span></span> <span data-ttu-id="bdbeb-113">名前の隣に `(A)` と表示されているパッケージは、プロジェクトの設定から推論される[暗黙的なパッケージ参照](csproj.md#implicit-package-references)を表します (`Sdk` 型、`<TargetFramework>` プロパティ、`<TargetFrameworks>` プロパティなど)。</span><span class="sxs-lookup"><span data-stu-id="bdbeb-113">The packages displaying an `(A)` right next to their names represent [implicit package references](csproj.md#implicit-package-references) that are inferred from your project settings (`Sdk` type, `<TargetFramework>` or `<TargetFrameworks>` property, etc.)</span></span>

<span data-ttu-id="bdbeb-114">プロジェクトで使用されているパッケージのさらに新しいバージョンを利用可能かどうかを調べるには、`--outdated` オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="bdbeb-114">Use the `--outdated` option to find out if there are newer versions available of the packages you're using in your projects.</span></span> <span data-ttu-id="bdbeb-115">既定では、解決済みのバージョンがプレリリース バージョンでもある場合を除き、`--outdated` では最新の安定したパッケージが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="bdbeb-115">By default, `--outdated` lists the latest stable packages unless the resolved version is also a prerelease version.</span></span> <span data-ttu-id="bdbeb-116">新しいバージョンを一覧表示するときにプレリリース版を含めるには、`--include-prerelease` オプションも指定します。</span><span class="sxs-lookup"><span data-stu-id="bdbeb-116">To include prerelease versions when listing newer versions, also specify the `--include-prerelease` option.</span></span> <span data-ttu-id="bdbeb-117">次の例では、前の例と同じプロジェクトに対する `dotnet list package --outdated --include-prerelease` コマンドの出力を示します。</span><span class="sxs-lookup"><span data-stu-id="bdbeb-117">The following examples shows the output of the `dotnet list package --outdated --include-prerelease` command for the same project as the previous example:</span></span>

```output
The following sources were used:
   https://api.nuget.org/v3/index.json

Project `SentimentAnalysis` has the following updates to its packages
   [netcoreapp2.1]:
   Top-level Package      Requested   Resolved   Latest
   > Microsoft.ML         0.11.0      0.11.0     1.0.0-preview
```

<span data-ttu-id="bdbeb-118">プロジェクトに推移的依存関係があるかどうかを確認する必要がある場合は、`--include-transitive` オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="bdbeb-118">If you need to find out whether your project has transitive dependencies, use the `--include-transitive` option.</span></span> <span data-ttu-id="bdbeb-119">推移的依存関係は、プロジェクトに追加したパッケージがさらに別のパッケージに依存している場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="bdbeb-119">Transitive dependencies occur when you add a package to your project that in turn relies on another package.</span></span> <span data-ttu-id="bdbeb-120">次の例では、[HelloPlugin](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin/HelloPlugin) プロジェクトに対して `dotnet list package --include-transitive` コマンドを実行した出力を示します、最上位のパッケージと、それらが依存しているパッケージが表示されています。</span><span class="sxs-lookup"><span data-stu-id="bdbeb-120">The following example shows the output from running the `dotnet list package --include-transitive` command for the [HelloPlugin](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin/HelloPlugin) project, which displays top-level packages and the packages they depend on:</span></span>

```output
Project 'HelloPlugin' has the following package references
   [netcoreapp3.0]:
   Top-level Package                      Requested                    Resolved
   > Microsoft.NETCore.Platforms    (A)   [3.0.0-preview3.19128.7, )   3.0.0-preview3.19128.7
   > Microsoft.WindowsDesktop.App   (A)   [3.0.0-preview3-27504-2, )   3.0.0-preview3-27504-2

   Transitive Package               Resolved
   > Microsoft.NETCore.Targets      2.0.0
   > PluginBase                     1.0.0

(A) : Auto-referenced package.
```

## <a name="arguments"></a><span data-ttu-id="bdbeb-121">引数</span><span class="sxs-lookup"><span data-stu-id="bdbeb-121">Arguments</span></span>

`PROJECT | SOLUTION`

<span data-ttu-id="bdbeb-122">対象のプロジェクトまたはソリューションのファイル。</span><span class="sxs-lookup"><span data-stu-id="bdbeb-122">The project or solution file to operate on.</span></span> <span data-ttu-id="bdbeb-123">指定されていない場合、現在のディレクトリで検索されます。</span><span class="sxs-lookup"><span data-stu-id="bdbeb-123">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="bdbeb-124">複数のソリューションまたはプロジェクトが見つかった場合は、エラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="bdbeb-124">If more than one solution or project is found, an error is thrown.</span></span>

## <a name="options"></a><span data-ttu-id="bdbeb-125">オプション</span><span class="sxs-lookup"><span data-stu-id="bdbeb-125">Options</span></span>

* **`--config <SOURCE>`**

  <span data-ttu-id="bdbeb-126">より新しいパッケージを検索するときに使用する NuGet ソース。</span><span class="sxs-lookup"><span data-stu-id="bdbeb-126">The NuGet sources to use when searching for newer packages.</span></span> <span data-ttu-id="bdbeb-127">`--outdated` オプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="bdbeb-127">Requires the `--outdated` option.</span></span>

* **`--framework <FRAMEWORK>`**

  <span data-ttu-id="bdbeb-128">指定した[ターゲット フレームワーク](../../standard/frameworks.md)に該当するパッケージのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="bdbeb-128">Displays only the packages applicable for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="bdbeb-129">複数のフレームワークを指定するには、オプションを複数回繰り返します。</span><span class="sxs-lookup"><span data-stu-id="bdbeb-129">To specify multiple frameworks, repeat the option multiple times.</span></span> <span data-ttu-id="bdbeb-130">たとえば、`--framework netcoreapp2.2 --framework netstandard2.0` のように指定します。</span><span class="sxs-lookup"><span data-stu-id="bdbeb-130">For example: `--framework netcoreapp2.2 --framework netstandard2.0`.</span></span>

* **`-h|--help`**

  <span data-ttu-id="bdbeb-131">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="bdbeb-131">Prints out a short help for the command.</span></span>

* **`--highest-minor`**

  <span data-ttu-id="bdbeb-132">新しいパッケージを検索するときに、メジャー バージョン番号が一致するパッケージのみを考慮します。</span><span class="sxs-lookup"><span data-stu-id="bdbeb-132">Considers only the packages with a matching major version number when searching for newer packages.</span></span> <span data-ttu-id="bdbeb-133">`--outdated` オプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="bdbeb-133">Requires the `--outdated` option.</span></span>

* **`--highest-patch`**

  <span data-ttu-id="bdbeb-134">新しいパッケージを検索するときに、メジャー バージョン番号とマイナー バージョン番号が一致するパッケージのみを考慮します。</span><span class="sxs-lookup"><span data-stu-id="bdbeb-134">Considers only the packages with a matching major and minor version numbers when searching for newer packages.</span></span> <span data-ttu-id="bdbeb-135">`--outdated` オプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="bdbeb-135">Requires the `--outdated` option.</span></span>

* **`--include-prerelease`**

  <span data-ttu-id="bdbeb-136">新しいパッケージを検索するときに、プレリリース バージョンのパッケージを考慮します。</span><span class="sxs-lookup"><span data-stu-id="bdbeb-136">Considers packages with prerelease versions when searching for newer packages.</span></span> <span data-ttu-id="bdbeb-137">`--outdated` オプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="bdbeb-137">Requires the `--outdated` option.</span></span>

* **`--include-transitive`**

  <span data-ttu-id="bdbeb-138">最上位のパッケージに加えて、推移的なパッケージを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="bdbeb-138">Lists transitive packages, in addition to the top-level packages.</span></span> <span data-ttu-id="bdbeb-139">このオプションを指定すると、最上位のパッケージが依存しているパッケージの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bdbeb-139">When specifying this option, you get a list of packages that the top-level packages depend on.</span></span>

* **`--outdated`**

  <span data-ttu-id="bdbeb-140">より新しいバージョンを使用できるパッケージを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="bdbeb-140">Lists packages that have newer versions available.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="bdbeb-141">より新しいパッケージを検索するときに使用する NuGet ソース。</span><span class="sxs-lookup"><span data-stu-id="bdbeb-141">The NuGet sources to use when searching for newer packages.</span></span> <span data-ttu-id="bdbeb-142">`--outdated` オプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="bdbeb-142">Requires the `--outdated` option.</span></span>

## <a name="examples"></a><span data-ttu-id="bdbeb-143">使用例</span><span class="sxs-lookup"><span data-stu-id="bdbeb-143">Examples</span></span>

* <span data-ttu-id="bdbeb-144">特定のプロジェクトのパッケージ参照を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="bdbeb-144">List package references of a specific project:</span></span>

  ```console
  dotnet list SentimentAnalysis.csproj package
  ```

* <span data-ttu-id="bdbeb-145">プレリリース バージョンを含め、さらに新しいバージョンを使用できるパッケージ参照を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="bdbeb-145">List package references that have newer versions available, including prerelease versions:</span></span>

  ```console
  dotnet list package --outdated --include-prerelease
  ```

* <span data-ttu-id="bdbeb-146">特定のターゲット フレームワークのパッケージ参照を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="bdbeb-146">List package references for a specific target framework:</span></span>

  ```console
  dotnet list package --framework netcoreapp3.0
  ```