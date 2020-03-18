---
title: .NET Core コマンドライン ツールのアーキテクチャ
description: .NET Core ツール レイヤーと最近のバージョンの変更内容について説明します。
ms.date: 03/06/2017
ms.openlocfilehash: fde1a0acb6af9dd65aa3466b4ea37473b2eab6fb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "77092916"
---
# <a name="high-level-overview-of-changes-in-the-net-core-tools"></a><span data-ttu-id="d5e88-103">.NET Core ツールの変更の概要</span><span class="sxs-lookup"><span data-stu-id="d5e88-103">High-level overview of changes in the .NET Core tools</span></span>

<span data-ttu-id="d5e88-104">このドキュメントでは、*project.json* から MSBuild への移行に関連する変更について、および *csproj* プロジェクト システムについて、.NET Core ツールのレイヤー化と CLI コマンド実装の変更に関する情報と共に説明します。</span><span class="sxs-lookup"><span data-stu-id="d5e88-104">This document describes the changes associated with moving from *project.json* to MSBuild and the *csproj* project system with information on the changes to the layering of the .NET Core tooling and the implementation of the CLI commands.</span></span> <span data-ttu-id="d5e88-105">これらの変更は、2017 年 3 月 7 日の .NET Core SDK 1.0 および Visual Studio 2017 のリリース ([アナウンス](https://devblogs.microsoft.com/dotnet/announcing-net-core-tools-1-0/)をご覧ください) に伴って発生しましたが、.NET Core SDK Preview 3 のリリースで初めて実装されました。</span><span class="sxs-lookup"><span data-stu-id="d5e88-105">These changes occurred with the release of .NET Core SDK 1.0 and Visual Studio 2017 on March 7, 2017 (see the [announcement](https://devblogs.microsoft.com/dotnet/announcing-net-core-tools-1-0/)) but were initially implemented with the release of the .NET Core SDK Preview 3.</span></span>

## <a name="moving-away-from-projectjson"></a><span data-ttu-id="d5e88-106">project.json から移行する</span><span class="sxs-lookup"><span data-stu-id="d5e88-106">Moving away from project.json</span></span>

<span data-ttu-id="d5e88-107">.NET Core のツールの最大の違いは、プロジェクト システムが [project.json から csproj に移行](https://devblogs.microsoft.com/dotnet/changes-to-project-json/)されることです。</span><span class="sxs-lookup"><span data-stu-id="d5e88-107">The biggest change in the tooling for .NET Core is certainly the [move away from project.json to csproj](https://devblogs.microsoft.com/dotnet/changes-to-project-json/) as the project system.</span></span> <span data-ttu-id="d5e88-108">最新バージョンのコマンドライン ツールは *project.json* ファイルをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d5e88-108">The latest versions of the command-line tools don't support *project.json* files.</span></span> <span data-ttu-id="d5e88-109">これは、project.json ベースのアプリケーションやライブラリをビルド、実行、発行できないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="d5e88-109">That means that it cannot be used to build, run, or publish project.json based applications and libraries.</span></span> <span data-ttu-id="d5e88-110">このバージョンのツールを使用するには、既存のプロジェクトを移行するか、新しいプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d5e88-110">To use this version of the tools, migrate your existing projects or start new ones.</span></span>

<span data-ttu-id="d5e88-111">この移行の一環として、project.json プロジェクトの構築用に開発されたカスタム ビルド エンジンが、[MSBuild](https://github.com/Microsoft/msbuild) と呼ばれる、成熟した完全な機能を持つビルド エンジンに置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="d5e88-111">As part of this move, the custom build engine that was developed to build project.json projects was replaced with a mature and fully capable build engine called [MSBuild](https://github.com/Microsoft/msbuild).</span></span> <span data-ttu-id="d5e88-112">MSBuild は、.NET コミュニティでよく知られているエンジンです。</span><span class="sxs-lookup"><span data-stu-id="d5e88-112">MSBuild is a well-known engine in the .NET community.</span></span> <span data-ttu-id="d5e88-113">これはプラットフォームの最初のリリース以来の重要なテクノロジです。</span><span class="sxs-lookup"><span data-stu-id="d5e88-113">It has been a key technology since the platform's first release.</span></span> <span data-ttu-id="d5e88-114">MSBuild では .NET Core アプリケーションをビルドする必要があるため、MSBuild は .NET Core に移植されており、.NET Core が動作するすべてのプラットフォームで使用できます。</span><span class="sxs-lookup"><span data-stu-id="d5e88-114">Because it needs to build .NET Core applications, MSBuild has been ported to .NET Core and can be used on any platform that .NET Core runs on.</span></span> <span data-ttu-id="d5e88-115">.NET Core の最大の保証の 1 つは、これがクロスプラット フォームの開発スタックであるということです。この動きによってこれは保証され続けるように努めました。</span><span class="sxs-lookup"><span data-stu-id="d5e88-115">One of the main promises of .NET Core is that of a cross-platform development stack, and we have made sure that this move does not break that promise.</span></span>

> [!TIP]
> <span data-ttu-id="d5e88-116">MSBuild を初めて使用する際に詳細を学習するには、まず、「[MSBuild の概念](/visualstudio/msbuild/msbuild-concepts)」という記事をお読みください。</span><span class="sxs-lookup"><span data-stu-id="d5e88-116">If you are new to MSBuild and would like to learn more about it, you can start by reading the [MSBuild concepts](/visualstudio/msbuild/msbuild-concepts) article.</span></span>

## <a name="the-tooling-layers"></a><span data-ttu-id="d5e88-117">ツールの階層</span><span class="sxs-lookup"><span data-stu-id="d5e88-117">The tooling layers</span></span>

<span data-ttu-id="d5e88-118">ビルド エンジンにおける変更と既存のプロジェクト システムからの移行に伴い、当然ながらいくつかの疑問が生じます。</span><span class="sxs-lookup"><span data-stu-id="d5e88-118">With the change in build engine and the move away from the existing project system, some questions naturally follow.</span></span> <span data-ttu-id="d5e88-119">これらの変更によって .NET Core ツールのエコシステム全体の "レイヤー" に変更はあるのでしょうか?</span><span class="sxs-lookup"><span data-stu-id="d5e88-119">Do any of these changes change the overall "layering" of the .NET Core tooling ecosystem?</span></span> <span data-ttu-id="d5e88-120">小さなものからコンポーネントまで、新しいものはありますか?</span><span class="sxs-lookup"><span data-stu-id="d5e88-120">Are there new bits and components?</span></span>

<span data-ttu-id="d5e88-121">次の図で Preview 2 のレイヤーを簡単に再確認してみましょう。</span><span class="sxs-lookup"><span data-stu-id="d5e88-121">Let's start with a quick refresher on Preview 2 layering as shown in the following picture:</span></span>

![Preview 2 のツールの概要](media/cli-msbuild-architecture/p2-arch.png)

<span data-ttu-id="d5e88-123">Preview 2 ではツールのレイヤーは簡単です。</span><span class="sxs-lookup"><span data-stu-id="d5e88-123">The layering of the tools in Preview 2 is straightforward.</span></span> <span data-ttu-id="d5e88-124">下部にある基盤は .NET Core CLI です。</span><span class="sxs-lookup"><span data-stu-id="d5e88-124">At the bottom, the foundation is the .NET Core CLI.</span></span> <span data-ttu-id="d5e88-125">Visual Studio または Visual Studio Code などのその他すべての上位レベルのツールは、プロジェクトのビルドや依存関係の復元などで CLI に依存しています。</span><span class="sxs-lookup"><span data-stu-id="d5e88-125">All other, higher-level tools, such as Visual Studio or Visual Studio Code, depend and rely on the CLI to build projects, restore dependencies, and so on.</span></span> <span data-ttu-id="d5e88-126">たとえば Visual Studio で復元操作を行う場合、CLI の `dotnet restore` ([注を参照](#dotnet-restore-note)) コマンドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d5e88-126">For example, if Visual Studio wanted to perform a restore operation, it would call into the `dotnet restore` ([see note](#dotnet-restore-note)) command in the CLI.</span></span>

<span data-ttu-id="d5e88-127">新しいプロジェクト システムに移行すると、前の図は以下のように変わります。</span><span class="sxs-lookup"><span data-stu-id="d5e88-127">With the move to the new project system, the previous diagram changes:</span></span>

![.NET Core SDK 1.0.0 のアーキテクチャの概要](media/cli-msbuild-architecture/p3-arch.png)

<span data-ttu-id="d5e88-129">主な違いは、CLI が基本的なレイヤーではなくなり、この役割が "共有 SDK コンポーネント" に置き換えられたことです。</span><span class="sxs-lookup"><span data-stu-id="d5e88-129">The main difference is that the CLI is not the foundational layer anymore; this role is now filled by the "shared SDK component".</span></span> <span data-ttu-id="d5e88-130">この共有 SDK コンポーネントは、一連のターゲットとそれに関連付けられている、コードのコンパイル、コードの発行、NuGet パッケージの作成などを担うタスクです。</span><span class="sxs-lookup"><span data-stu-id="d5e88-130">This shared SDK component is a set of targets and associated tasks that are responsible for compiling code, publishing it, packing NuGet packages, and so on.</span></span> <span data-ttu-id="d5e88-131">.NET Core SDK はオープン ソースであり、GitHub の [SDK リポジトリ](https://github.com/dotnet/sdk)から入手できます。</span><span class="sxs-lookup"><span data-stu-id="d5e88-131">The .NET Core SDK is open-source and is available on GitHub on the [SDK repo](https://github.com/dotnet/sdk).</span></span>

> [!NOTE]
> <span data-ttu-id="d5e88-132">"ターゲット" とは、MSBuild が呼び出すことのできる名前付きの操作を意味する MSBuild の用語です。</span><span class="sxs-lookup"><span data-stu-id="d5e88-132">A "target" is an MSBuild term that indicates a named operation that MSBuild can invoke.</span></span> <span data-ttu-id="d5e88-133">これは、通常ターゲットが行うことを期待されているいくつかのロジックを実行する 1 つ以上のタスクと連結されています。</span><span class="sxs-lookup"><span data-stu-id="d5e88-133">It is usually coupled with one or more tasks that execute some logic that the target is supposed to do.</span></span> <span data-ttu-id="d5e88-134">MSBuild では、`Copy` や `Execute` などの多数の既製ターゲットをサポートしています。また、ユーザーがマネージド コードを使用して、独自のタスクを記述し、それらのタスクをターゲットに実行させるよう定義することも可能です。</span><span class="sxs-lookup"><span data-stu-id="d5e88-134">MSBuild supports many ready-made targets such as `Copy` or `Execute`; it also allows users to write their own tasks using managed code and define targets to execute those tasks.</span></span> <span data-ttu-id="d5e88-135">詳細については、「[MSBuild タスク](/visualstudio/msbuild/msbuild-tasks)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5e88-135">For more information, see [MSBuild tasks](/visualstudio/msbuild/msbuild-tasks).</span></span>

<span data-ttu-id="d5e88-136">すべてのツールセットは、CLI を含む、共有 SDK コンポーネントとそのターゲットを消費します。</span><span class="sxs-lookup"><span data-stu-id="d5e88-136">All the toolsets now consume the shared SDK component and its targets, CLI included.</span></span> <span data-ttu-id="d5e88-137">たとえば、Visual Studio 2019 では、.NET Core プロジェクトの依存関係を復元するために `dotnet restore` ([注を参照](#dotnet-restore-note)) コマンドは呼び出されません。</span><span class="sxs-lookup"><span data-stu-id="d5e88-137">For example, Visual Studio 2019 doesn't call into the `dotnet restore` ([see note](#dotnet-restore-note)) command to restore dependencies for .NET Core projects.</span></span> <span data-ttu-id="d5e88-138">代わりに、"復元" のターゲットを直接使用します。</span><span class="sxs-lookup"><span data-stu-id="d5e88-138">Instead, it uses the "Restore" target directly.</span></span> <span data-ttu-id="d5e88-139">これらは MSBuild のターゲットであるため、これらの実行に未加工の MSBuild の [dotnet msbuild](dotnet-msbuild.md) コマンドを使用することも可能です。</span><span class="sxs-lookup"><span data-stu-id="d5e88-139">Since these are MSBuild targets, you can also use raw MSBuild to execute them using the [dotnet msbuild](dotnet-msbuild.md) command.</span></span>

### <a name="cli-commands"></a><span data-ttu-id="d5e88-140">CLI コマンド</span><span class="sxs-lookup"><span data-stu-id="d5e88-140">CLI commands</span></span>

<span data-ttu-id="d5e88-141">共有 SDK コンポーネントとは、大多数の既存の CLI コマンドが MSBuild のタスクやターゲットとして再実装されたものです。</span><span class="sxs-lookup"><span data-stu-id="d5e88-141">The shared SDK component means that the majority of existing CLI commands have been reimplemented as MSBuild tasks and targets.</span></span> <span data-ttu-id="d5e88-142">これは CLI コマンドやツールセットの使用にどのような意味があるのでしょうか?</span><span class="sxs-lookup"><span data-stu-id="d5e88-142">What does this mean for the CLI commands and your usage of the toolset?</span></span>

<span data-ttu-id="d5e88-143">使用の観点からは、CLI の使用方法には変わりはありません。</span><span class="sxs-lookup"><span data-stu-id="d5e88-143">From a usage perspective, it doesn't change the way you use the CLI.</span></span> <span data-ttu-id="d5e88-144">CLI には、.NET Core 1.0 Preview 2 リリースに存在していた主要なコマンドがまだあります。</span><span class="sxs-lookup"><span data-stu-id="d5e88-144">The CLI still has the core commands that existed in the .NET Core 1.0 Preview 2 release:</span></span>

- `new`
- `restore`
- `run`
- `build`
- `publish`
- `test`
- `pack`

<span data-ttu-id="d5e88-145">引き続きこれらのコマンドを使用して、目的の動作 (新しいプロジェクトの作成、ビルド、発行、パッケージ作成など) を実行できます。</span><span class="sxs-lookup"><span data-stu-id="d5e88-145">These commands still do what you expect them to do (new up a project, build it, publish it, pack it, and so on).</span></span> <span data-ttu-id="d5e88-146">コマンドのヘルプ画面 (`dotnet <command> --help`を使用) またはこのサイトのドキュメントを参照して、それらの動作を理解することができます。</span><span class="sxs-lookup"><span data-stu-id="d5e88-146">You can consult either the command's help screen (using `dotnet <command> --help`) or documentation on this site to get familiar with their behavior.</span></span>

<span data-ttu-id="d5e88-147">実行の観点からは、CLI コマンドにパラメーターを渡すと、必要なプロパティを設定して目的のターゲットを実行する "生" の MSBuild への呼び出しが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d5e88-147">From an execution perspective, the CLI commands take their parameters and construct a call to "raw" MSBuild that sets the needed properties and runs the desired target.</span></span> <span data-ttu-id="d5e88-148">次の図でこれを分かりやすく説明します。</span><span class="sxs-lookup"><span data-stu-id="d5e88-148">To better illustrate this, consider the following command:</span></span>

   ```dotnetcli
   dotnet publish -o pub -c Release
   ```

<span data-ttu-id="d5e88-149">このコマンドで、"Release" 構成を使用してアプリケーションを `pub` フォルダーに発行します。</span><span class="sxs-lookup"><span data-stu-id="d5e88-149">This command publishes an application into a `pub` folder using the "Release" configuration.</span></span> <span data-ttu-id="d5e88-150">このコマンドは、内部では次の MSBuild の呼び出しに変換されます。</span><span class="sxs-lookup"><span data-stu-id="d5e88-150">Internally, this command gets translated into the following MSBuild invocation:</span></span>

   ```dotnetcli
   dotnet msbuild -t:Publish -p:OutputPath=pub -p:Configuration=Release
   ```

<span data-ttu-id="d5e88-151">この規則の注目すべき例外は、`new` コマンドと `run` のコマンドです。</span><span class="sxs-lookup"><span data-stu-id="d5e88-151">Notable exceptions to this rule are the `new` and `run` commands.</span></span> <span data-ttu-id="d5e88-152">それらは MSBuild ターゲットとして実装されていません。</span><span class="sxs-lookup"><span data-stu-id="d5e88-152">They have not been implemented as MSBuild targets.</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
