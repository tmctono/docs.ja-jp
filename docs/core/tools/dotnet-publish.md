---
title: dotnet publish コマンド
description: dotnet publish コマンドを実行すると、.NET Core プロジェクトまたはソリューションをディレクトリに発行できます。
ms.date: 02/24/2020
ms.openlocfilehash: cf41ee09244faad03feb8ccda19135b8c7780106
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157000"
---
# <a name="dotnet-publish"></a><span data-ttu-id="192f0-103">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="192f0-103">dotnet publish</span></span>

<span data-ttu-id="192f0-104">**この記事の対象:** ✔️ .NET Core 2.1 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="192f0-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="192f0-105">名前</span><span class="sxs-lookup"><span data-stu-id="192f0-105">Name</span></span>

<span data-ttu-id="192f0-106">`dotnet publish` - ホスティング システムへの展開のため、アプリケーションとその依存関係をフォルダーに発行します。</span><span class="sxs-lookup"><span data-stu-id="192f0-106">`dotnet publish` - Publishes the application and its dependencies to a folder for deployment to a hosting system.</span></span>

## <a name="synopsis"></a><span data-ttu-id="192f0-107">構文</span><span class="sxs-lookup"><span data-stu-id="192f0-107">Synopsis</span></span>

```dotnetcli
dotnet publish [<PROJECT>|<SOLUTION>] [-c|--configuration] 
    [-f|--framework] [--force] [--interactive] [--manifest]
    [--no-build] [--no-dependencies] [--no-restore] [--nologo]
    [-o|--output] [-r|--runtime] [--self-contained]
    [--no-self-contained] [-v|--verbosity] [--version-suffix]

dotnet publish [-h|--help]
```

## <a name="description"></a><span data-ttu-id="192f0-108">説明</span><span class="sxs-lookup"><span data-stu-id="192f0-108">Description</span></span>

<span data-ttu-id="192f0-109">`dotnet publish` はアプリケーションをコンパイルし、プロジェクト ファイルに指定されたその依存関係を読み取り、結果のファイル セットをディレクトリに発行します。</span><span class="sxs-lookup"><span data-stu-id="192f0-109">`dotnet publish` compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="192f0-110">出力には次のアセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="192f0-110">The output includes the following assets:</span></span>

- <span data-ttu-id="192f0-111">アセンブリの中間言語 (IL) コード (*dll* 拡張子)。</span><span class="sxs-lookup"><span data-stu-id="192f0-111">Intermediate Language (IL) code in an assembly with a *dll* extension.</span></span>
- <span data-ttu-id="192f0-112">*.deps.json* ファイル。プロジェクトのすべての依存関係が含まれます。</span><span class="sxs-lookup"><span data-stu-id="192f0-112">A *.deps.json* file that includes all of the dependencies of the project.</span></span>
- <span data-ttu-id="192f0-113">*.runtimeconfig.json* ファイル。アプリケーションが想定する共有ランタイムと、ランタイム用の他の構成オプション (ガベージ コレクションの種類など) を指定します。</span><span class="sxs-lookup"><span data-stu-id="192f0-113">A *.runtimeconfig.json* file that specifies the shared runtime that the application expects, as well as other configuration options for the runtime (for example, garbage collection type).</span></span>
- <span data-ttu-id="192f0-114">アプリケーションの依存関係。NuGet キャッシュから出力フォルダーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="192f0-114">The application's dependencies, which are copied from the NuGet cache into the output folder.</span></span>

<span data-ttu-id="192f0-115">`dotnet publish` コマンドの出力は、実行のためにホスト システム (サーバー、PC、Mac、ラップトップなど) にすぐに展開できます。</span><span class="sxs-lookup"><span data-stu-id="192f0-115">The `dotnet publish` command's output is ready for deployment to a hosting system (for example, a server, PC, Mac, laptop) for execution.</span></span> <span data-ttu-id="192f0-116">これは、アプリケーションの展開を準備するための正式にサポートされている唯一の方法です。</span><span class="sxs-lookup"><span data-stu-id="192f0-116">It's the only officially supported way to prepare the application for deployment.</span></span> <span data-ttu-id="192f0-117">プロジェクトに指定されている展開の種類によっては、ホスティング システムに .NET Core 共有ランタイムがインストールされている場合とされていない場合があります。</span><span class="sxs-lookup"><span data-stu-id="192f0-117">Depending on the type of deployment that the project specifies, the hosting system may or may not have the .NET Core shared runtime installed on it.</span></span>

## <a name="arguments"></a><span data-ttu-id="192f0-118">引数</span><span class="sxs-lookup"><span data-stu-id="192f0-118">Arguments</span></span>

- **`PROJECT|SOLUTION`**

  <span data-ttu-id="192f0-119">発行するプロジェクトまたはソリューション。</span><span class="sxs-lookup"><span data-stu-id="192f0-119">The project or solution to publish.</span></span>
  
  * <span data-ttu-id="192f0-120">`PROJECT` は、[C#](csproj.md)、F#、または Visual Basic のプロジェクト ファイルのパスおよびファイル名か、C#、F#、または Visual Basic のプロジェクト ファイルを含むディレクトリへのパスです。</span><span class="sxs-lookup"><span data-stu-id="192f0-120">`PROJECT` is the path and filename of a [C#](csproj.md), F#, or Visual Basic project file, or the path to a directory that contains a C#, F#, or Visual Basic project file.</span></span> <span data-ttu-id="192f0-121">ディレクトリが指定されていない場合は、既定で現在のディレクトリに設定されます。</span><span class="sxs-lookup"><span data-stu-id="192f0-121">If the directory is not specified, it defaults to the current directory.</span></span>

  * <span data-ttu-id="192f0-122">`SOLUTION` は、ソリューション ファイルのパスとファイル名 ( *.sln* 拡張子)、またはソリューション ファイルを含むディレクトリのパスです。</span><span class="sxs-lookup"><span data-stu-id="192f0-122">`SOLUTION` is the path and filename of a solution file (*.sln* extension), or the path to a directory that contains a solution file.</span></span> <span data-ttu-id="192f0-123">ディレクトリが指定されていない場合は、既定で現在のディレクトリに設定されます。</span><span class="sxs-lookup"><span data-stu-id="192f0-123">If the directory is not specified, it defaults to the current directory.</span></span> <span data-ttu-id="192f0-124">**.NET Core 3.0 SDK 以降で使用できます。**</span><span class="sxs-lookup"><span data-stu-id="192f0-124">**Available starting with .NET Core 3.0 SDK.**</span></span> 

## <a name="options"></a><span data-ttu-id="192f0-125">オプション</span><span class="sxs-lookup"><span data-stu-id="192f0-125">Options</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="192f0-126">ビルド構成を定義します。</span><span class="sxs-lookup"><span data-stu-id="192f0-126">Defines the build configuration.</span></span> <span data-ttu-id="192f0-127">ほとんどのプロジェクトの既定値は `Debug` ですが、プロジェクトでビルド構成設定をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="192f0-127">The default for most projects is `Debug`, but you can override the build configuration settings in your project.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="192f0-128">指定した[ターゲット フレームワーク](../../standard/frameworks.md)のアプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="192f0-128">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="192f0-129">ターゲット フレームワークはプロジェクト ファイルで指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="192f0-129">You must specify the target framework in the project file.</span></span>

- **`--force`**

  <span data-ttu-id="192f0-130">最後の復元が成功した場合でも、すべての依存関係が強制的に解決されます。</span><span class="sxs-lookup"><span data-stu-id="192f0-130">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="192f0-131">このフラグを指定することは、*project.assets.json* ファイルを削除することと同じです。</span><span class="sxs-lookup"><span data-stu-id="192f0-131">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

- **`-h|--help`**

  <span data-ttu-id="192f0-132">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="192f0-132">Prints out a short help for the command.</span></span>

- <span data-ttu-id="192f0-133">**`--interactive`** **.NET Core 3.0 SDK 以降で使用できます。**</span><span class="sxs-lookup"><span data-stu-id="192f0-133">**`--interactive`** **Available starting with .NET Core 3.0 SDK.**</span></span>

  <span data-ttu-id="192f0-134">コマンドを停止して、ユーザーの入力または操作のために待機させることができます。</span><span class="sxs-lookup"><span data-stu-id="192f0-134">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="192f0-135">たとえば、認証を完了する場合があります。</span><span class="sxs-lookup"><span data-stu-id="192f0-135">For example, to complete authentication.</span></span> 

- **`--manifest <PATH_TO_MANIFEST_FILE>`**

  <span data-ttu-id="192f0-136">アプリによって公開された一連のパッケージをトリミングするために使用する[ターゲット マニフェスト](../deploying/runtime-store.md)を 1 つまたは複数指定します。</span><span class="sxs-lookup"><span data-stu-id="192f0-136">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="192f0-137">マニフェスト ファイルは、[`dotnet store` コマンド](dotnet-store.md)の出力の一部です。</span><span class="sxs-lookup"><span data-stu-id="192f0-137">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="192f0-138">複数のマニフェストを指定するには、マニフェストごとに `--manifest` を追加します。</span><span class="sxs-lookup"><span data-stu-id="192f0-138">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span>

- **`--no-build`**

  <span data-ttu-id="192f0-139">発行の前にプロジェクトをビルドしません。</span><span class="sxs-lookup"><span data-stu-id="192f0-139">Doesn't build the project before publishing.</span></span> <span data-ttu-id="192f0-140">また、`--no-restore` フラグが暗黙的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="192f0-140">It also implicitly sets the `--no-restore` flag.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="192f0-141">プロジェクト間参照を無視し、ルート プロジェクトのみを復元します。</span><span class="sxs-lookup"><span data-stu-id="192f0-141">Ignores project-to-project references and only restores the root project.</span></span>

- <span data-ttu-id="192f0-142">**`--nologo`** **.NET Core 3.0 SDK 以降で使用できます。**</span><span class="sxs-lookup"><span data-stu-id="192f0-142">**`--nologo`** **Available starting with .NET Core 3.0 SDK.**</span></span>

  <span data-ttu-id="192f0-143">著作権情報を表示しません。</span><span class="sxs-lookup"><span data-stu-id="192f0-143">Doesn't display the startup banner or the copyright message.</span></span> 

- **`--no-restore`**

  <span data-ttu-id="192f0-144">コマンドを実行するときに、暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="192f0-144">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="192f0-145">出力ディレクトリのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="192f0-145">Specifies the path for the output directory.</span></span> <span data-ttu-id="192f0-146">指定しない場合、ランタイムに依存する実行可能ファイルおよびクロスプラットフォーム バイナリの既定値は *./bin/[configuration]/[framework]/publish/* に設定されます。</span><span class="sxs-lookup"><span data-stu-id="192f0-146">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a runtime-dependent executable and cross-platform binaries.</span></span> <span data-ttu-id="192f0-147">自己完結型の実行可能ファイルの場合、既定値は *./bin/[configuration]/[framework]/[runtime]/publish/* です。</span><span class="sxs-lookup"><span data-stu-id="192f0-147">It defaults to *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained executable.</span></span>

  <span data-ttu-id="192f0-148">パスが相対的である場合、生成された出力ディレクトリは、現在の作業ディレクトリではなく、プロジェクト ファイルの場所に相対的なパスとなります。</span><span class="sxs-lookup"><span data-stu-id="192f0-148">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

- **`--self-contained [true|false]`**

  <span data-ttu-id="192f0-149">アプリケーションと一緒に .NET Core ランタイムを発行します。これにより、ランタイムをターゲット コンピューターにインストールする必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="192f0-149">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="192f0-150">ランタイム識別子が指定されている場合、既定値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="192f0-150">Default is `true` if a runtime identifier is specified.</span></span> <span data-ttu-id="192f0-151">詳細については、[.NET Core アプリケーションの発行](../deploying/index.md)に関する記事と「[.NET Core CLI を使用して .NET Core アプリを発行する](../deploying/deploy-with-cli.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="192f0-151">For more information, see [.NET Core application publishing](../deploying/index.md) and [Publish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md).</span></span>

- <span data-ttu-id="192f0-152">**`--no-self-contained`** **.NET Core 3.0 SDK 以降で使用できます。**</span><span class="sxs-lookup"><span data-stu-id="192f0-152">**`--no-self-contained`**  **Available starting with .NET Core 3.0 SDK.**</span></span>

  <span data-ttu-id="192f0-153">これは、`--self-contained false` に相当します。</span><span class="sxs-lookup"><span data-stu-id="192f0-153">Equivalent to `--self-contained false`.</span></span>

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="192f0-154">指定されたランタイムのアプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="192f0-154">Publishes the application for a given runtime.</span></span> <span data-ttu-id="192f0-155">ランタイム ID (RID) の一覧については、[RID カタログ](../rid-catalog.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="192f0-155">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="192f0-156">詳細については、[.NET Core アプリケーションの発行](../deploying/index.md)に関する記事と「[.NET Core CLI を使用して .NET Core アプリを発行する](../deploying/deploy-with-cli.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="192f0-156">For more information, see [.NET Core application publishing](../deploying/index.md) and [Publish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md).</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="192f0-157">コマンドの詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="192f0-157">Sets the verbosity level of the command.</span></span> <span data-ttu-id="192f0-158">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="192f0-158">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

- **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="192f0-159">プロジェクト ファイルのバージョン フィールドでアスタリスク (`*`) を置き換えるバージョン サフィックスを定義します。</span><span class="sxs-lookup"><span data-stu-id="192f0-159">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

## <a name="examples"></a><span data-ttu-id="192f0-160">使用例</span><span class="sxs-lookup"><span data-stu-id="192f0-160">Examples</span></span>

- <span data-ttu-id="192f0-161">現在のディレクトリ内にプロジェクト用の[ランタイムに依存するクロスプラットフォーム バイナリ](../deploying/index.md#produce-a-cross-platform-binary)を作成します。</span><span class="sxs-lookup"><span data-stu-id="192f0-161">Create a [runtime-dependent cross-platform binary](../deploying/index.md#produce-a-cross-platform-binary) for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet publish
  ```

  <span data-ttu-id="192f0-162">.NET Core 3.0 SDK 以降の場合、この例では、現在のプラットフォーム用の[ランタイムに依存する実行可能ファイル](../deploying/index.md#publish-runtime-dependent)も作成されます。</span><span class="sxs-lookup"><span data-stu-id="192f0-162">Starting with .NET Core 3.0 SDK, this example also creates a [runtime-dependent executable](../deploying/index.md#publish-runtime-dependent) for the current platform.</span></span>

- <span data-ttu-id="192f0-163">特定のランタイムに対して、現在のディレクトリ内にプロジェクト用の[自己完結型の実行可能ファイル](../deploying/index.md#publish-self-contained)を作成します。</span><span class="sxs-lookup"><span data-stu-id="192f0-163">Create a [self-contained executable](../deploying/index.md#publish-self-contained) for the project in the current directory, for a specific runtime:</span></span>

  ```dotnetcli
  dotnet publish --runtime osx.10.11-x64
  ```

  <span data-ttu-id="192f0-164">RID をプロジェクト ファイルに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="192f0-164">The RID must be in the project file.</span></span>

- <span data-ttu-id="192f0-165">特定のプラットフォーム用に、プロジェクト用の[ランタイムに依存する実行可能ファイル](../deploying/index.md#publish-runtime-dependent)を現在のディレクトリに作成します。</span><span class="sxs-lookup"><span data-stu-id="192f0-165">Create a [runtime-dependent executable](../deploying/index.md#publish-runtime-dependent) for the project in the current directory, for a specific platform:</span></span>

  ```dotnetcli
  dotnet publish --runtime osx.10.11-x64 --self-contained false
  ```

  <span data-ttu-id="192f0-166">RID をプロジェクト ファイルに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="192f0-166">The RID must be in the project file.</span></span> <span data-ttu-id="192f0-167">この例は、.NET Core 3.0 SDK 以降のバージョンに適用されます。</span><span class="sxs-lookup"><span data-stu-id="192f0-167">This example applies to .NET Core 3.0 SDK and later versions.</span></span>

- <span data-ttu-id="192f0-168">特定のランタイムとターゲット フレームワーク用に、現在のディレクトリのプロジェクトを発行します。</span><span class="sxs-lookup"><span data-stu-id="192f0-168">Publish the project in the current directory, for a specific runtime and target framework:</span></span>

  ```dotnetcli
  dotnet publish --framework netcoreapp3.1 --runtime osx.10.11-x64
  ```

- <span data-ttu-id="192f0-169">指定されたプロジェクト ファイルを発行します。</span><span class="sxs-lookup"><span data-stu-id="192f0-169">Publish the specified project file:</span></span>

  ```dotnetcli
  dotnet publish ~/projects/app1/app1.csproj
  ```

- <span data-ttu-id="192f0-170">現在のアプリケーションを発行します。ただし、復元操作中はルート プロジェクトのみを復元し、プロジェクト間 (P2P) 参照は復元しないでください。</span><span class="sxs-lookup"><span data-stu-id="192f0-170">Publish the current application but don't restore project-to-project (P2P) references, just the root project during the restore operation:</span></span>

  ```dotnetcli
  dotnet publish --no-dependencies
  ```

## <a name="see-also"></a><span data-ttu-id="192f0-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="192f0-171">See also</span></span>

- [<span data-ttu-id="192f0-172">.NET Core アプリケーションの発行の概要</span><span class="sxs-lookup"><span data-stu-id="192f0-172">.NET Core application publishing overview</span></span>](../deploying/index.md)
- [<span data-ttu-id="192f0-173">.NET Core CLI を使用して .NET Core アプリを発行する</span><span class="sxs-lookup"><span data-stu-id="192f0-173">Publish .NET Core apps with the .NET Core CLI</span></span>](../deploying/deploy-with-cli.md)
- [<span data-ttu-id="192f0-174">ターゲット フレームワーク</span><span class="sxs-lookup"><span data-stu-id="192f0-174">Target frameworks</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="192f0-175">ランタイム識別子 (RID) のカタログ</span><span class="sxs-lookup"><span data-stu-id="192f0-175">Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
- <span data-ttu-id="192f0-176">[macOS Catalina の公証に対応する](../install/macos-notarization-issues.md) 詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="192f0-176">[Working with macOS Catalina Notarization](../install/macos-notarization-issues.md) For more information, see he following resources:</span></span>
- [<span data-ttu-id="192f0-177">発行されたアプリケーションのディレクトリ構造</span><span class="sxs-lookup"><span data-stu-id="192f0-177">Directory structure of a published application</span></span>](/aspnet/core/hosting/directory-structure)
