---
title: dotnet msbuild コマンド
description: dotnet msbuild コマンドは、MSBuild コマンド ラインへのアクセスを提供します。
ms.date: 02/14/2020
ms.openlocfilehash: 9739fe782e17db3955db087ca1781ad4280cd491
ms.sourcegitcommit: 1eae045421d9ea2bfc82aaccfa5b1ff1b8c9e0e4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "84803169"
---
# <a name="dotnet-msbuild"></a><span data-ttu-id="c7c93-103">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="c7c93-103">dotnet msbuild</span></span>

<span data-ttu-id="c7c93-104">**この記事の対象:** ✔️ .NET Core 2.x SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="c7c93-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="c7c93-105">名前</span><span class="sxs-lookup"><span data-stu-id="c7c93-105">Name</span></span>

<span data-ttu-id="c7c93-106">`dotnet msbuild` - プロジェクトとそのすべての依存関係をビルドします。</span><span class="sxs-lookup"><span data-stu-id="c7c93-106">`dotnet msbuild` - Builds a project and all of its dependencies.</span></span> <span data-ttu-id="c7c93-107">メモ:複数存在するとき、ソリューションまたはプロジェクト ファイルを場合によっては指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7c93-107">Note: A solution or project file may need to be specified if there are multiple.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c7c93-108">構文</span><span class="sxs-lookup"><span data-stu-id="c7c93-108">Synopsis</span></span>

```dotnetcli
dotnet msbuild <MSBUILD_ARGUMENTS>

dotnet msbuild -h
```

## <a name="description"></a><span data-ttu-id="c7c93-109">説明</span><span class="sxs-lookup"><span data-stu-id="c7c93-109">Description</span></span>

<span data-ttu-id="c7c93-110">`dotnet msbuild` コマンドでは、完全に機能する MSBuild へのアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="c7c93-110">The `dotnet msbuild` command allows access to a fully functional MSBuild.</span></span>

<span data-ttu-id="c7c93-111">このコマンドには、SDK スタイルのプロジェクトに対してのみ、既存の MSBuild コマンド ライン クライアントとまったく同じ機能があります。</span><span class="sxs-lookup"><span data-stu-id="c7c93-111">The command has the exact same capabilities as the existing MSBuild command-line client for SDK-style projects only.</span></span> <span data-ttu-id="c7c93-112">オプションはすべて同じです。</span><span class="sxs-lookup"><span data-stu-id="c7c93-112">The options are all the same.</span></span> <span data-ttu-id="c7c93-113">使用可能なオプションの詳細については、「[MSBuild コマンド ライン リファレンス](/visualstudio/msbuild/msbuild-command-line-reference)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7c93-113">For more information about the available options, see the [MSBuild command-line reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span>

<span data-ttu-id="c7c93-114">[dotnet build](dotnet-build.md) コマンドは、`dotnet msbuild -restore` に相当します。</span><span class="sxs-lookup"><span data-stu-id="c7c93-114">The [dotnet build](dotnet-build.md) command is equivalent to `dotnet msbuild -restore`.</span></span> <span data-ttu-id="c7c93-115">プロジェクトをビルドしないが、特定のターゲットを実行する場合、`dotnet build` または `dotnet msbuild` を使用し、ターゲットを指定します。</span><span class="sxs-lookup"><span data-stu-id="c7c93-115">When you don't want to build the project and you have a specific target you want to run, use `dotnet build` or `dotnet msbuild` and specify the target.</span></span>

## <a name="examples"></a><span data-ttu-id="c7c93-116">使用例</span><span class="sxs-lookup"><span data-stu-id="c7c93-116">Examples</span></span>

- <span data-ttu-id="c7c93-117">プロジェクトとその依存関係をビルドします。</span><span class="sxs-lookup"><span data-stu-id="c7c93-117">Build a project and its dependencies:</span></span>

  ```dotnetcli
  dotnet msbuild
  ```

- <span data-ttu-id="c7c93-118">リリース構成を使用して、プロジェクトとその依存関係をビルドします。</span><span class="sxs-lookup"><span data-stu-id="c7c93-118">Build a project and its dependencies using Release configuration:</span></span>

  ```dotnetcli
  dotnet msbuild -property:Configuration=Release
  ```

- <span data-ttu-id="c7c93-119">発行先を実行して、RID `osx.10.11-x64` に発行します。</span><span class="sxs-lookup"><span data-stu-id="c7c93-119">Run the publish target and publish for the `osx.10.11-x64` RID:</span></span>

  ```dotnetcli
  dotnet msbuild -target:Publish -property:RuntimeIdentifiers=osx.10.11-x64
  ```

- <span data-ttu-id="c7c93-120">プロジェクト全体と SDK に付属するすべてのターゲットをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c7c93-120">See the whole project with all targets included by the SDK:</span></span>

  ```dotnetcli
  dotnet msbuild -preprocess
  dotnet msbuild -preprocess:<fileName>.xml
  ```
