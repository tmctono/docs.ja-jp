---
title: dotnet msbuild コマンド
description: dotnet msbuild コマンドは、MSBuild コマンド ラインへのアクセスを提供します。
ms.date: 12/03/2018
ms.openlocfilehash: dae1e9f0ca355166d41c11fbafb80c7c9fb29748
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733203"
---
# <a name="dotnet-msbuild"></a><span data-ttu-id="0b984-103">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="0b984-103">dotnet msbuild</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="0b984-104">名前</span><span class="sxs-lookup"><span data-stu-id="0b984-104">Name</span></span>

<span data-ttu-id="0b984-105">`dotnet msbuild` - プロジェクトとそのすべての依存関係をビルドします。</span><span class="sxs-lookup"><span data-stu-id="0b984-105">`dotnet msbuild` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="0b984-106">構文</span><span class="sxs-lookup"><span data-stu-id="0b984-106">Synopsis</span></span>

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a><span data-ttu-id="0b984-107">説明</span><span class="sxs-lookup"><span data-stu-id="0b984-107">Description</span></span>

<span data-ttu-id="0b984-108">`dotnet msbuild` コマンドでは、完全に機能する MSBuild へのアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="0b984-108">The `dotnet msbuild` command allows access to a fully functional MSBuild.</span></span>

<span data-ttu-id="0b984-109">このコマンドには、SDK スタイルのプロジェクトに対してのみ、既存の MSBuild コマンド ライン クライアントとまったく同じ機能があります。</span><span class="sxs-lookup"><span data-stu-id="0b984-109">The command has the exact same capabilities as the existing MSBuild command-line client for SDK-style projects only.</span></span> <span data-ttu-id="0b984-110">オプションはすべて同じです。</span><span class="sxs-lookup"><span data-stu-id="0b984-110">The options are all the same.</span></span> <span data-ttu-id="0b984-111">使用可能なオプションの詳細については、「[MSBuild コマンド ライン リファレンス](/visualstudio/msbuild/msbuild-command-line-reference)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b984-111">For more information about the available options, see the [MSBuild command-line reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span>

<span data-ttu-id="0b984-112">[dotnet build](dotnet-build.md) コマンドは、`dotnet msbuild -restore -target:Build` に相当します。</span><span class="sxs-lookup"><span data-stu-id="0b984-112">The [dotnet build](dotnet-build.md) command is equivalent to `dotnet msbuild -restore -target:Build`.</span></span> <span data-ttu-id="0b984-113">[dotnet ビルド](dotnet-build.md)は、プロジェクトのビルドによく使用されますが、ビルド ターゲットを常に実行するため、プロジェクトをビルドしなくてもよい場合は `dotnet msbuild` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0b984-113">[dotnet build](dotnet-build.md) is more commonly used for building projects, but because it always runs the build target, you can use `dotnet msbuild` when you don't want to build the project.</span></span> <span data-ttu-id="0b984-114">たとえば、プロジェクトをビルドせずに実行したい特定のターゲットがある場合は、`dotnet msbuild` を使用してターゲットを指定します。</span><span class="sxs-lookup"><span data-stu-id="0b984-114">For example, if you have a specific target you want to run without building the project, use `dotnet msbuild` and specify the target.</span></span>

## <a name="examples"></a><span data-ttu-id="0b984-115">使用例</span><span class="sxs-lookup"><span data-stu-id="0b984-115">Examples</span></span>

* <span data-ttu-id="0b984-116">プロジェクトとその依存関係をビルドします。</span><span class="sxs-lookup"><span data-stu-id="0b984-116">Build a project and its dependencies:</span></span>

  ```dotnetcli
  dotnet msbuild
  ```

* <span data-ttu-id="0b984-117">リリース構成を使用して、プロジェクトとその依存関係をビルドします。</span><span class="sxs-lookup"><span data-stu-id="0b984-117">Build a project and its dependencies using Release configuration:</span></span>

  ```dotnetcli
  dotnet msbuild -property:Configuration=Release
  ```

* <span data-ttu-id="0b984-118">発行先を実行して、RID `osx.10.11-x64` に発行します。</span><span class="sxs-lookup"><span data-stu-id="0b984-118">Run the publish target and publish for the `osx.10.11-x64` RID:</span></span>

  ```dotnetcli
  dotnet msbuild -target:Publish -property:RuntimeIdentifiers=osx.10.11-x64
  ```

* <span data-ttu-id="0b984-119">プロジェクト全体と SDK に付属するすべてのターゲットをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0b984-119">See the whole project with all targets included by the SDK:</span></span>

  ```dotnetcli
  dotnet msbuild -preprocess
  ```
