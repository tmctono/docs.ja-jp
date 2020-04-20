---
title: dotnet msbuild コマンド
description: dotnet msbuild コマンドは、MSBuild コマンド ラインへのアクセスを提供します。
ms.date: 02/14/2020
ms.openlocfilehash: 88e85868e2d7de564b2e4c90ce6e78bde4cb350e
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463620"
---
# <a name="dotnet-msbuild"></a><span data-ttu-id="b860f-103">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="b860f-103">dotnet msbuild</span></span>

<span data-ttu-id="b860f-104">**この記事の対象:** ✔️ .NET Core 2.x SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="b860f-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="b860f-105">name</span><span class="sxs-lookup"><span data-stu-id="b860f-105">Name</span></span>

<span data-ttu-id="b860f-106">`dotnet msbuild` - プロジェクトとそのすべての依存関係をビルドします。</span><span class="sxs-lookup"><span data-stu-id="b860f-106">`dotnet msbuild` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b860f-107">構文</span><span class="sxs-lookup"><span data-stu-id="b860f-107">Synopsis</span></span>

```dotnetcli
dotnet msbuild <MSBUILD_ARGUMENTS>

dotnet msbuild -h
```

## <a name="description"></a><span data-ttu-id="b860f-108">[説明]</span><span class="sxs-lookup"><span data-stu-id="b860f-108">Description</span></span>

<span data-ttu-id="b860f-109">`dotnet msbuild` コマンドでは、完全に機能する MSBuild へのアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="b860f-109">The `dotnet msbuild` command allows access to a fully functional MSBuild.</span></span>

<span data-ttu-id="b860f-110">このコマンドには、SDK スタイルのプロジェクトに対してのみ、既存の MSBuild コマンド ライン クライアントとまったく同じ機能があります。</span><span class="sxs-lookup"><span data-stu-id="b860f-110">The command has the exact same capabilities as the existing MSBuild command-line client for SDK-style projects only.</span></span> <span data-ttu-id="b860f-111">オプションはすべて同じです。</span><span class="sxs-lookup"><span data-stu-id="b860f-111">The options are all the same.</span></span> <span data-ttu-id="b860f-112">使用可能なオプションの詳細については、「[MSBuild コマンド ライン リファレンス](/visualstudio/msbuild/msbuild-command-line-reference)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b860f-112">For more information about the available options, see the [MSBuild command-line reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span>

<span data-ttu-id="b860f-113">[dotnet build](dotnet-build.md) コマンドは、`dotnet msbuild -restore -target:Build` に相当します。</span><span class="sxs-lookup"><span data-stu-id="b860f-113">The [dotnet build](dotnet-build.md) command is equivalent to `dotnet msbuild -restore -target:Build`.</span></span> <span data-ttu-id="b860f-114">[dotnet ビルド](dotnet-build.md)は、プロジェクトのビルドによく使用されますが、ビルド ターゲットを常に実行するため、プロジェクトをビルドしなくてもよい場合は `dotnet msbuild` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b860f-114">[dotnet build](dotnet-build.md) is more commonly used for building projects, but because it always runs the build target, you can use `dotnet msbuild` when you don't want to build the project.</span></span> <span data-ttu-id="b860f-115">たとえば、プロジェクトをビルドせずに実行したい特定のターゲットがある場合は、`dotnet msbuild` を使用してターゲットを指定します。</span><span class="sxs-lookup"><span data-stu-id="b860f-115">For example, if you have a specific target you want to run without building the project, use `dotnet msbuild` and specify the target.</span></span>

## <a name="examples"></a><span data-ttu-id="b860f-116">例</span><span class="sxs-lookup"><span data-stu-id="b860f-116">Examples</span></span>

- <span data-ttu-id="b860f-117">プロジェクトとその依存関係をビルドします。</span><span class="sxs-lookup"><span data-stu-id="b860f-117">Build a project and its dependencies:</span></span>

  ```dotnetcli
  dotnet msbuild
  ```

- <span data-ttu-id="b860f-118">リリース構成を使用して、プロジェクトとその依存関係をビルドします。</span><span class="sxs-lookup"><span data-stu-id="b860f-118">Build a project and its dependencies using Release configuration:</span></span>

  ```dotnetcli
  dotnet msbuild -property:Configuration=Release
  ```

- <span data-ttu-id="b860f-119">発行先を実行して、RID `osx.10.11-x64` に発行します。</span><span class="sxs-lookup"><span data-stu-id="b860f-119">Run the publish target and publish for the `osx.10.11-x64` RID:</span></span>

  ```dotnetcli
  dotnet msbuild -target:Publish -property:RuntimeIdentifiers=osx.10.11-x64
  ```

- <span data-ttu-id="b860f-120">プロジェクト全体と SDK に付属するすべてのターゲットをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b860f-120">See the whole project with all targets included by the SDK:</span></span>

  ```dotnetcli
  dotnet msbuild -preprocess
  ```
