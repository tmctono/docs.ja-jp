---
title: dotnet msbuild コマンド
description: dotnet msbuild コマンドは、MSBuild コマンド ラインへのアクセスを提供します。
ms.date: 12/03/2018
ms.openlocfilehash: 983fae6f4ecf875da0b155a668009984b5df50de
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632028"
---
# <a name="dotnet-msbuild"></a><span data-ttu-id="3d379-103">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="3d379-103">dotnet msbuild</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="3d379-104">name</span><span class="sxs-lookup"><span data-stu-id="3d379-104">Name</span></span>

<span data-ttu-id="3d379-105">`dotnet msbuild` - プロジェクトとそのすべての依存関係をビルドします。</span><span class="sxs-lookup"><span data-stu-id="3d379-105">`dotnet msbuild` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="3d379-106">構文</span><span class="sxs-lookup"><span data-stu-id="3d379-106">Synopsis</span></span>

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a><span data-ttu-id="3d379-107">説明</span><span class="sxs-lookup"><span data-stu-id="3d379-107">Description</span></span>

<span data-ttu-id="3d379-108">`dotnet msbuild` コマンドでは、完全に機能する MSBuild へのアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="3d379-108">The `dotnet msbuild` command allows access to a fully functional MSBuild.</span></span>

<span data-ttu-id="3d379-109">このコマンドには、SDK スタイルのプロジェクトに対してのみ、既存の MSBuild コマンド ライン クライアントとまったく同じ機能があります。</span><span class="sxs-lookup"><span data-stu-id="3d379-109">The command has the exact same capabilities as the existing MSBuild command-line client for SDK-style project only.</span></span> <span data-ttu-id="3d379-110">オプションはすべて同じです。</span><span class="sxs-lookup"><span data-stu-id="3d379-110">The options are all the same.</span></span> <span data-ttu-id="3d379-111">使用可能なオプションの詳細については、「[MSBuild コマンド ライン リファレンス](/visualstudio/msbuild/msbuild-command-line-reference)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d379-111">For more information about the available options, see the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span>

<span data-ttu-id="3d379-112">[dotnet build](dotnet-build.md) コマンドは、`dotnet msbuild -restore -target:Build` に相当します。</span><span class="sxs-lookup"><span data-stu-id="3d379-112">The [dotnet build](dotnet-build.md) command is equivalent to `dotnet msbuild -restore -target:Build`.</span></span> <span data-ttu-id="3d379-113">プロジェクトの構築では `dotnet build` のほうが一般的に使用されますが、`dotnet msbuild` のほうが細かい制御を実行できます。</span><span class="sxs-lookup"><span data-stu-id="3d379-113">`dotnet build` is more commonly used for building projects, but `dotnet msbuild` gives you more control.</span></span> <span data-ttu-id="3d379-114">たとえば、実行したい特定のターゲットがあるが、ビルドしたターゲットを実行したくない場合は、`dotnet msbuild` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3d379-114">For example, if you have a specific target you want to run (without running the build target), you probably want to use `dotnet msbuild`.</span></span>

## <a name="examples"></a><span data-ttu-id="3d379-115">使用例</span><span class="sxs-lookup"><span data-stu-id="3d379-115">Examples</span></span>

* <span data-ttu-id="3d379-116">プロジェクトとその依存関係をビルドします。</span><span class="sxs-lookup"><span data-stu-id="3d379-116">Build a project and its dependencies:</span></span>

  ```console
  dotnet msbuild
  ```

* <span data-ttu-id="3d379-117">リリース構成を使用して、プロジェクトとその依存関係をビルドします。</span><span class="sxs-lookup"><span data-stu-id="3d379-117">Build a project and its dependencies using Release configuration:</span></span>

  ```console
  dotnet msbuild -p:Configuration=Release
  ```

* <span data-ttu-id="3d379-118">発行先を実行して、RID `osx.10.11-x64` に発行します。</span><span class="sxs-lookup"><span data-stu-id="3d379-118">Run the publish target and publish for the `osx.10.11-x64` RID:</span></span>

  ```console
  dotnet msbuild -t:Publish -p:RuntimeIdentifiers=osx.10.11-x64
  ```

* <span data-ttu-id="3d379-119">プロジェクト全体と SDK に付属するすべてのターゲットをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3d379-119">See the whole project with all targets included by the SDK:</span></span>

  ```console
  dotnet msbuild -pp
  ```
