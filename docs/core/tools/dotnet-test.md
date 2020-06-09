---
title: dotnet test コマンド
description: dotnet test コマンドは、指定されたプロジェクトで単体テストを実行する場合に使用されます。
ms.date: 04/29/2020
ms.openlocfilehash: 1190ecb75e83c9930c60726e7cd83203b11928cb
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84283937"
---
# <a name="dotnet-test"></a><span data-ttu-id="8c0da-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="8c0da-103">dotnet test</span></span>

<span data-ttu-id="8c0da-104">**この記事の対象:** ✔️ .NET Core 2.1 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="8c0da-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="8c0da-105">名前</span><span class="sxs-lookup"><span data-stu-id="8c0da-105">Name</span></span>

<span data-ttu-id="8c0da-106">`dotnet test` - 単体テストを実行するために使用される .NET テスト ドライバー。</span><span class="sxs-lookup"><span data-stu-id="8c0da-106">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="8c0da-107">構文</span><span class="sxs-lookup"><span data-stu-id="8c0da-107">Synopsis</span></span>

```dotnetcli
dotnet test [<PROJECT> | <SOLUTION> | <DIRECTORY> | <DLL>]
    [-a|--test-adapter-path <PATH_TO_ADAPTER>] [--blame]
    [-c|--configuration <CONFIGURATION>]
    [--collect <DATA_COLLECTOR_FRIENDLY_NAME>]
    [-d|--diag <PATH_TO_DIAGNOSTICS_FILE>] [-f|--framework <FRAMEWORK>]
    [--filter <EXPRESSION>] [--interactive]
    [-l|--logger <LOGGER_URI/FRIENDLY_NAME>] [--no-build]
    [--nologo] [--no-restore] [-o|--output <OUTPUT_DIRECTORY>]
    [-r|--results-directory <PATH>] [--runtime <RUNTIME_IDENTIFIER>]
    [-s|--settings <SETTINGS_FILE>] [-t|--list-tests]
    [-v|--verbosity <LEVEL>] [[--] <RunSettings arguments>]

dotnet test -h|--help
```

## <a name="description"></a><span data-ttu-id="8c0da-108">説明</span><span class="sxs-lookup"><span data-stu-id="8c0da-108">Description</span></span>

<span data-ttu-id="8c0da-109">`dotnet test` コマンドは、指定されたソリューションで単体テストを実行する場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="8c0da-109">The `dotnet test` command is used to execute unit tests in a given solution.</span></span> <span data-ttu-id="8c0da-110">`dotnet test` コマンドを実行すると、ソリューションがビルドされ、ソリューション内の各テスト プロジェクトのテスト ホスト アプリケーションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="8c0da-110">The `dotnet test` command builds the solution and runs a test host application for each test project in the solution.</span></span> <span data-ttu-id="8c0da-111">テスト ホストは、指定されたプロジェクトで、テスト フレームワークを使用してテストを実行します。たとえば、MSTest、NUnit、xUnit などです。そして、各テストの成功または失敗を報告します。</span><span class="sxs-lookup"><span data-stu-id="8c0da-111">The test host executes tests in the given project using a test framework, for example: MSTest, NUnit, or xUnit, and reports the success or failure of each test.</span></span> <span data-ttu-id="8c0da-112">すべてのテストが成功した場合、テスト ランナーは 0 の終了コードを返します。それ以外の、いずれかのテストに失敗した場合は、1 を返します。</span><span class="sxs-lookup"><span data-stu-id="8c0da-112">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span>

<span data-ttu-id="8c0da-113">複数の対象を持つプロジェクトでは、対象となる各フレームワークに対してテストが実行されます。</span><span class="sxs-lookup"><span data-stu-id="8c0da-113">For multi-targeted projects, tests are run for each targeted framework.</span></span> <span data-ttu-id="8c0da-114">テスト ホストと単体テスト フレームワークは、NuGet パッケージとしてパッケージ化され、プロジェクトの通常の依存関係として復元されます。</span><span class="sxs-lookup"><span data-stu-id="8c0da-114">The test host and the unit test framework are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="8c0da-115">テスト プロジェクトでは、通常の `<PackageReference>` 要素を使用してテスト ランナーを指定します。次のサンプル プロジェクト ファイルのようになります。</span><span class="sxs-lookup"><span data-stu-id="8c0da-115">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

<span data-ttu-id="8c0da-116">`Microsoft.NET.Test.Sdk` がテスト ホストの場合、`xunit` はテスト フレームワークです。</span><span class="sxs-lookup"><span data-stu-id="8c0da-116">Where `Microsoft.NET.Test.Sdk` is the test host, `xunit` is the test framework.</span></span> <span data-ttu-id="8c0da-117">また、`xunit.runner.visualstudio` はテスト アダプターであり、xUnit フレームワークはテスト ホストと連携できます。</span><span class="sxs-lookup"><span data-stu-id="8c0da-117">And `xunit.runner.visualstudio` is a test adapter, which allows the xUnit framework to work with the test host.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="8c0da-118">暗黙的な復元</span><span class="sxs-lookup"><span data-stu-id="8c0da-118">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="8c0da-119">引数</span><span class="sxs-lookup"><span data-stu-id="8c0da-119">Arguments</span></span>

- **`PROJECT | SOLUTION | DIRECTORY | DLL`**

  - <span data-ttu-id="8c0da-120">テスト プロジェクトへのパス。</span><span class="sxs-lookup"><span data-stu-id="8c0da-120">Path to the test project.</span></span>
  - <span data-ttu-id="8c0da-121">ソリューションへのパス。</span><span class="sxs-lookup"><span data-stu-id="8c0da-121">Path to the solution.</span></span>
  - <span data-ttu-id="8c0da-122">プロジェクトまたはソリューションを含むディレクトリへのパス。</span><span class="sxs-lookup"><span data-stu-id="8c0da-122">Path to a directory that contains a project or a solution.</span></span>
  - <span data-ttu-id="8c0da-123">テスト プロジェクト " *.dll*" ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="8c0da-123">Path to a test project *.dll* file.</span></span>

  <span data-ttu-id="8c0da-124">指定されていない場合、プロジェクトまたはソリューションが現在のディレクトリで検索されます。</span><span class="sxs-lookup"><span data-stu-id="8c0da-124">If not specified, it searches for a project or a solution in the current directory.</span></span>

## <a name="options"></a><span data-ttu-id="8c0da-125">オプション</span><span class="sxs-lookup"><span data-stu-id="8c0da-125">Options</span></span>

- **`-a|--test-adapter-path <PATH_TO_ADAPTER>`**

  <span data-ttu-id="8c0da-126">追加のテスト アダプターを検索するディレクトリへのパス。</span><span class="sxs-lookup"><span data-stu-id="8c0da-126">Path to a directory to be searched for additional test adapters.</span></span> <span data-ttu-id="8c0da-127">サフィックス `.TestAdapter.dll` を持つ " *.dll*" ファイルのみが検査されます。</span><span class="sxs-lookup"><span data-stu-id="8c0da-127">Only *.dll* files with suffix `.TestAdapter.dll` are inspected.</span></span> <span data-ttu-id="8c0da-128">指定しない場合、テスト " *.dll*" のディレクトリが検索されます。</span><span class="sxs-lookup"><span data-stu-id="8c0da-128">If not specified, the directory of the test *.dll* is searched.</span></span>

- **`--blame`**

  <span data-ttu-id="8c0da-129">変更履歴モードでテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="8c0da-129">Runs the tests in blame mode.</span></span> <span data-ttu-id="8c0da-130">このオプションは、テスト ホストがクラッシュする原因となる問題のあるテストを分離するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8c0da-130">This option is helpful in isolating problematic tests that cause the test host to crash.</span></span> <span data-ttu-id="8c0da-131">クラッシュが検出されると、クラッシュ前に実行されたテストの順序をキャプチャするシーケンス ファイルが `TestResults/<Guid>/<Guid>_Sequence.xml` に作成されます。</span><span class="sxs-lookup"><span data-stu-id="8c0da-131">When a crash is detected, it creates a sequence file in `TestResults/<Guid>/<Guid>_Sequence.xml` that captures the order of tests that were run before the crash.</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="8c0da-132">ビルド構成を定義します。</span><span class="sxs-lookup"><span data-stu-id="8c0da-132">Defines the build configuration.</span></span> <span data-ttu-id="8c0da-133">既定値は `Debug` ですが、プロジェクトの構成がこの既定の SDK 設定をオーバーライドする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8c0da-133">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

- **`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`**

  <span data-ttu-id="8c0da-134">テストの実行のためのデータ コレクターを有効にします。</span><span class="sxs-lookup"><span data-stu-id="8c0da-134">Enables data collector for the test run.</span></span> <span data-ttu-id="8c0da-135">詳細については、[「Monitor and analyze test run」](https://aka.ms/vstest-collect) (テストの実行のモニターと分析) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c0da-135">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>
  
  <span data-ttu-id="8c0da-136">.NET Core でサポートされている任意のプラットフォーム上のコード カバレッジを収集するには、[Coverlet](https://github.com/coverlet-coverage/coverlet/blob/master/README.md) をインストールし、`--collect:"XPlat Code Coverage"` オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="8c0da-136">To collect code coverage on any platform that is supported by .NET Core, install [Coverlet](https://github.com/coverlet-coverage/coverlet/blob/master/README.md) and use the `--collect:"XPlat Code Coverage"` option.</span></span>

  <span data-ttu-id="8c0da-137">Windows では、`--collect "Code Coverage"` オプションを使用してコード カバレッジを収集できます。</span><span class="sxs-lookup"><span data-stu-id="8c0da-137">On Windows, you can collect code coverage by using the `--collect "Code Coverage"` option.</span></span> <span data-ttu-id="8c0da-138">このオプションを選択すると、 *.coverage* ファイルが生成されます。このファイルは、Visual Studio 2019 Enterprise で開くことができます。</span><span class="sxs-lookup"><span data-stu-id="8c0da-138">This option generates a *.coverage* file, which can be opened in Visual Studio 2019 Enterprise.</span></span> <span data-ttu-id="8c0da-139">詳細については、[コード カバレッジの使用](/visualstudio/test/using-code-coverage-to-determine-how-much-code-is-being-tested)に関するページと「[コード カバレッジ分析のカスタマイズ](/visualstudio/test/customizing-code-coverage-analysis)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c0da-139">For more information, see [Use code coverage](/visualstudio/test/using-code-coverage-to-determine-how-much-code-is-being-tested) and [Customize code coverage analysis](/visualstudio/test/customizing-code-coverage-analysis).</span></span>

- **`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`**

  <span data-ttu-id="8c0da-140">テスト プラットフォームの診断モードを有効にし、指定したファイルとそれ以降のファイルに診断メッセージを出力します。</span><span class="sxs-lookup"><span data-stu-id="8c0da-140">Enables diagnostic mode for the test platform and writes diagnostic messages to the specified file and to files next to it.</span></span> <span data-ttu-id="8c0da-141">メッセージをログに記録するプロセスによって、テスト ホスト ログの `*.host_<date>.txt` やデータ コレクター ログの `*.datacollector_<date>.txt` などの、作成されるファイルが決まります。</span><span class="sxs-lookup"><span data-stu-id="8c0da-141">The process that is logging the messages determines which files are created, such as `*.host_<date>.txt` for test host log, and `*.datacollector_<date>.txt` for data collector log.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="8c0da-142">テスト バイナリに `dotnet` または .NET Framework テスト ホストを強制的に使用します。</span><span class="sxs-lookup"><span data-stu-id="8c0da-142">Forces the use of `dotnet` or .NET Framework test host for the test binaries.</span></span> <span data-ttu-id="8c0da-143">このオプションでは、使用するホストの種類のみが決定されます。</span><span class="sxs-lookup"><span data-stu-id="8c0da-143">This option only determines which type of host to use.</span></span> <span data-ttu-id="8c0da-144">実際に使用されるフレームワークのバージョンは、テスト プロジェクトの "*runtimeconfig. json*" によって決まります。</span><span class="sxs-lookup"><span data-stu-id="8c0da-144">The actual framework version to be used is determined by the *runtimeconfig.json* of the test project.</span></span> <span data-ttu-id="8c0da-145">指定しない場合、[TargetFramework アセンブリ属性](/dotnet/api/system.runtime.versioning.targetframeworkattribute) を使用してホストの種類が決定されます。</span><span class="sxs-lookup"><span data-stu-id="8c0da-145">When not specified, the [TargetFramework assembly attribute](/dotnet/api/system.runtime.versioning.targetframeworkattribute) is used to determine the type of host.</span></span> <span data-ttu-id="8c0da-146">その属性が " *.dll*" から削除されると、.NET Framework ホストが使用されます。</span><span class="sxs-lookup"><span data-stu-id="8c0da-146">When that attribute is stripped from the *.dll*, the .NET Framework host is used.</span></span>

- **`--filter <EXPRESSION>`**

  <span data-ttu-id="8c0da-147">指定された式を使用して、現在のプロジェクト内のテストを除外します。</span><span class="sxs-lookup"><span data-stu-id="8c0da-147">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="8c0da-148">詳細については、「[フィルター オプションの詳細](#filter-option-details)」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8c0da-148">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="8c0da-149">選択的単体テストのフィルター処理の使用方法に関する詳細と例については、「[選択的単体テストの実行](../testing/selective-unit-tests.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8c0da-149">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

- **`-h|--help`**

  <span data-ttu-id="8c0da-150">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="8c0da-150">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="8c0da-151">コマンドを停止して、ユーザーの入力または操作のために待機させることができます。</span><span class="sxs-lookup"><span data-stu-id="8c0da-151">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="8c0da-152">たとえば、認証を完了する場合があります。</span><span class="sxs-lookup"><span data-stu-id="8c0da-152">For example, to complete authentication.</span></span> <span data-ttu-id="8c0da-153">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="8c0da-153">Available since .NET Core 3.0 SDK.</span></span>

- **`-l|--logger <LOGGER_URI/FRIENDLY_NAME>`**

  <span data-ttu-id="8c0da-154">テスト結果のロガーを指定します。</span><span class="sxs-lookup"><span data-stu-id="8c0da-154">Specifies a logger for test results.</span></span> <span data-ttu-id="8c0da-155">MSBuild とは異なり、dotnet テストでは省略形は受け入れられません。`-l "console;v=d"` ではなく `-l "console;verbosity=detailed"` を使用してください。</span><span class="sxs-lookup"><span data-stu-id="8c0da-155">Unlike MSBuild, dotnet test doesn't accept abbreviations: instead of `-l "console;v=d"` use `-l "console;verbosity=detailed"`.</span></span>

- **`--no-build`**

  <span data-ttu-id="8c0da-156">実行前にテスト プロジェクトをビルドしません。</span><span class="sxs-lookup"><span data-stu-id="8c0da-156">Doesn't build the test project before running it.</span></span> <span data-ttu-id="8c0da-157">また、- `--no-restore` フラグが暗黙的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="8c0da-157">It also implicitly sets the - `--no-restore` flag.</span></span>

- **`--nologo`**

  <span data-ttu-id="8c0da-158">Microsoft TestPlatform バナーを表示せずにテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="8c0da-158">Run tests without displaying the Microsoft TestPlatform banner.</span></span> <span data-ttu-id="8c0da-159">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="8c0da-159">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-restore`**

  <span data-ttu-id="8c0da-160">コマンドを実行するときに、暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="8c0da-160">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="8c0da-161">実行するバイナリを検索するディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="8c0da-161">Directory in which to find the binaries to run.</span></span> <span data-ttu-id="8c0da-162">指定しない場合、既定のパスは `./bin/<configuration>/<framework>/` になります。</span><span class="sxs-lookup"><span data-stu-id="8c0da-162">If not specified, the default path is `./bin/<configuration>/<framework>/`.</span></span>  <span data-ttu-id="8c0da-163">(`TargetFrameworks` プロパティを使用した) ターゲット フレームワークが複数あるプロジェクトの場合は、このオプションを指定するときに `--framework` も定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c0da-163">For projects with multiple target frameworks (via the `TargetFrameworks` property), you also need to define `--framework` when you specify this option.</span></span> <span data-ttu-id="8c0da-164">`dotnet test` では常に、出力ディレクトリからテストが実行されます。</span><span class="sxs-lookup"><span data-stu-id="8c0da-164">`dotnet test` always runs tests from the output directory.</span></span> <span data-ttu-id="8c0da-165"><xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType> を使用して、出力ディレクトリ内のテスト資産を使用できます。</span><span class="sxs-lookup"><span data-stu-id="8c0da-165">You can use <xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType> to consume test assets in the output directory.</span></span>

- **`-r|--results-directory <PATH>`**

  <span data-ttu-id="8c0da-166">テスト結果が配置されるディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="8c0da-166">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="8c0da-167">指定されたディレクトリが存在しない場合は、作成されます。</span><span class="sxs-lookup"><span data-stu-id="8c0da-167">If the specified directory doesn't exist, it's created.</span></span> <span data-ttu-id="8c0da-168">既定値は、プロジェクト ファイルが含まれるディレクトリの `TestResults` です。</span><span class="sxs-lookup"><span data-stu-id="8c0da-168">The default is `TestResults` in the directory that contains the project file.</span></span>

- **`--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="8c0da-169">テスト対象のターゲット ランタイム。</span><span class="sxs-lookup"><span data-stu-id="8c0da-169">The target runtime to test for.</span></span>

- **`-s|--settings <SETTINGS_FILE>`**

  <span data-ttu-id="8c0da-170">テストの実行に使用する `.runsettings` ファイルです。</span><span class="sxs-lookup"><span data-stu-id="8c0da-170">The `.runsettings` file to use for running the tests.</span></span> <span data-ttu-id="8c0da-171">`TargetPlatform` 要素 (x86|x64) は `dotnet test` には影響しません。</span><span class="sxs-lookup"><span data-stu-id="8c0da-171">The `TargetPlatform` element (x86|x64) has no effect for `dotnet test`.</span></span> <span data-ttu-id="8c0da-172">x86 を対象とするテストを実行するには、x86 バージョンの .NET Core をインストールします。</span><span class="sxs-lookup"><span data-stu-id="8c0da-172">To run tests that target x86, install the x86 version of .NET Core.</span></span> <span data-ttu-id="8c0da-173">パスにある *dotnet.exe* のビットは、テストを実行するために使用されるものです。</span><span class="sxs-lookup"><span data-stu-id="8c0da-173">The bitness of the *dotnet.exe* that is on the path is what will be used for running tests.</span></span> <span data-ttu-id="8c0da-174">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c0da-174">For more information, see the following resources:</span></span>

  - [<span data-ttu-id="8c0da-175">`.runsettings` ファイルを使用して単体テストを構成します。</span><span class="sxs-lookup"><span data-stu-id="8c0da-175">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)
  - [<span data-ttu-id="8c0da-176">テスト実行を構成する</span><span class="sxs-lookup"><span data-stu-id="8c0da-176">Configure a test run</span></span>](https://github.com/Microsoft/vstest-docs/blob/master/docs/configure.md)

- **`-t|--list-tests`**

  <span data-ttu-id="8c0da-177">現在のプロジェクトで検出されたすべてのテストを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="8c0da-177">List all of the discovered tests in the current project.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="8c0da-178">コマンドの詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="8c0da-178">Sets the verbosity level of the command.</span></span> <span data-ttu-id="8c0da-179">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="8c0da-179">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="8c0da-180">既定値は、`minimal` です。</span><span class="sxs-lookup"><span data-stu-id="8c0da-180">The default is `minimal`.</span></span> <span data-ttu-id="8c0da-181">詳細については、「<xref:Microsoft.Build.Framework.LoggerVerbosity>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c0da-181">For more information, see <xref:Microsoft.Build.Framework.LoggerVerbosity>.</span></span>

- <span data-ttu-id="8c0da-182">**`RunSettings`** 引数</span><span class="sxs-lookup"><span data-stu-id="8c0da-182">**`RunSettings`** arguments</span></span>

 <span data-ttu-id="8c0da-183">インラインの `RunSettings` は、コマンド ラインの最後の引数として "-- " の後に渡されます (-- の後のスペースに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="8c0da-183">Inline `RunSettings` are passed as the last arguments on the command line after "-- " (note the space after --).</span></span> <span data-ttu-id="8c0da-184">インラインの `RunSettings` は `[name]=[value]` のペアとして指定されます。</span><span class="sxs-lookup"><span data-stu-id="8c0da-184">Inline `RunSettings` are specified as `[name]=[value]` pairs.</span></span> <span data-ttu-id="8c0da-185">複数の `[name]=[value]` のペアを区切るにはスペースを使用します。</span><span class="sxs-lookup"><span data-stu-id="8c0da-185">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

  <span data-ttu-id="8c0da-186">例 : `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="8c0da-186">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

  <span data-ttu-id="8c0da-187">詳しくは、「[コマンド ラインで RunSettings 引数を渡す](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8c0da-187">For more information, see [Passing RunSettings arguments through command line](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

## <a name="examples"></a><span data-ttu-id="8c0da-188">使用例</span><span class="sxs-lookup"><span data-stu-id="8c0da-188">Examples</span></span>

- <span data-ttu-id="8c0da-189">現在のディレクトリのプロジェクトでテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="8c0da-189">Run the tests in the project in the current directory:</span></span>

  ```dotnetcli
  dotnet test
  ```

- <span data-ttu-id="8c0da-190">`test1` プロジェクトでテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="8c0da-190">Run the tests in the `test1` project:</span></span>

  ```dotnetcli
  dotnet test ~/projects/test1/test1.csproj
  ```

- <span data-ttu-id="8c0da-191">現在のディレクトリでプロジェクトのテストを実行し、trx 形式でテスト結果ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="8c0da-191">Run the tests in the project in the current directory, and generate a test results file in the trx format:</span></span>

  ```dotnetcli
  dotnet test --logger trx
  ```

- <span data-ttu-id="8c0da-192">現在のディレクトリでプロジェクトのテストを実行し、([Coverlet](https://github.com/tonerdo/coverlet/blob/master/README.md) をインストールした後) コード カバレッジ ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="8c0da-192">Run the tests in the project in the current directory, and generate a code coverage file (after installing [Coverlet](https://github.com/tonerdo/coverlet/blob/master/README.md)):</span></span>

  ```dotnetcli
  dotnet test --collect:"XPlat Code Coverage"
  ```

- <span data-ttu-id="8c0da-193">現在のディレクトリでプロジェクトのテストを実行し、コード カバレッジ ファイルを生成します (Windows のみ)。</span><span class="sxs-lookup"><span data-stu-id="8c0da-193">Run the tests in the project in the current directory, and generate a code coverage file (Windows only):</span></span>

  ```dotnetcli
  dotnet test --collect "Code Coverage"
  ```

- <span data-ttu-id="8c0da-194">現在のディレクトリでプロジェクトのテストを実行し、詳細をコンソールに記録します。</span><span class="sxs-lookup"><span data-stu-id="8c0da-194">Run the tests in the project in the current directory, and log with detailed verbosity to the console:</span></span>

  ```dotnetcli
  dotnet test --logger "console;verbosity=detailed"
  ```
  
  - <span data-ttu-id="8c0da-195">現在のディレクトリのプロジェクトでテストを実行し、テスト ホストがクラッシュしたときに実行されていたテストを報告します。</span><span class="sxs-lookup"><span data-stu-id="8c0da-195">Run the tests in the project in the current directory, and report tests that were in progress when the test host crashed:</span></span>

  ```dotnetcli
  dotnet test --blame
  ```

## <a name="filter-option-details"></a><span data-ttu-id="8c0da-196">フィルター オプションの詳細</span><span class="sxs-lookup"><span data-stu-id="8c0da-196">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="8c0da-197">`<Expression>` の形式は `<property><operator><value>[|&<Expression>]` です。</span><span class="sxs-lookup"><span data-stu-id="8c0da-197">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="8c0da-198">`<property>` は `Test Case` の属性です。</span><span class="sxs-lookup"><span data-stu-id="8c0da-198">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="8c0da-199">よく利用される単体テスト フレームワークでサポートされるプロパティは以下の通りです。</span><span class="sxs-lookup"><span data-stu-id="8c0da-199">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="8c0da-200">テスト フレームワーク</span><span class="sxs-lookup"><span data-stu-id="8c0da-200">Test Framework</span></span> | <span data-ttu-id="8c0da-201">サポートされるプロパティ</span><span class="sxs-lookup"><span data-stu-id="8c0da-201">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="8c0da-202">MSTest</span><span class="sxs-lookup"><span data-stu-id="8c0da-202">MSTest</span></span>         | <ul><li><span data-ttu-id="8c0da-203">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="8c0da-203">FullyQualifiedName</span></span></li><li><span data-ttu-id="8c0da-204">名前</span><span class="sxs-lookup"><span data-stu-id="8c0da-204">Name</span></span></li><li><span data-ttu-id="8c0da-205">ClassName</span><span class="sxs-lookup"><span data-stu-id="8c0da-205">ClassName</span></span></li><li><span data-ttu-id="8c0da-206">優先度</span><span class="sxs-lookup"><span data-stu-id="8c0da-206">Priority</span></span></li><li><span data-ttu-id="8c0da-207">TestCategory</span><span class="sxs-lookup"><span data-stu-id="8c0da-207">TestCategory</span></span></li></ul> |
| <span data-ttu-id="8c0da-208">xUnit</span><span class="sxs-lookup"><span data-stu-id="8c0da-208">xUnit</span></span>          | <ul><li><span data-ttu-id="8c0da-209">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="8c0da-209">FullyQualifiedName</span></span></li><li><span data-ttu-id="8c0da-210">DisplayName</span><span class="sxs-lookup"><span data-stu-id="8c0da-210">DisplayName</span></span></li><li><span data-ttu-id="8c0da-211">Traits</span><span class="sxs-lookup"><span data-stu-id="8c0da-211">Traits</span></span></li></ul>                                   |
| <span data-ttu-id="8c0da-212">NUnit</span><span class="sxs-lookup"><span data-stu-id="8c0da-212">NUnit</span></span>          | <ul><li><span data-ttu-id="8c0da-213">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="8c0da-213">FullyQualifiedName</span></span></li><li><span data-ttu-id="8c0da-214">名前</span><span class="sxs-lookup"><span data-stu-id="8c0da-214">Name</span></span></li><li><span data-ttu-id="8c0da-215">TestCategory</span><span class="sxs-lookup"><span data-stu-id="8c0da-215">TestCategory</span></span></li><li><span data-ttu-id="8c0da-216">優先度</span><span class="sxs-lookup"><span data-stu-id="8c0da-216">Priority</span></span></li></ul>                                   |

<span data-ttu-id="8c0da-217">`<operator>` は、プロパティと値の関係を示します。</span><span class="sxs-lookup"><span data-stu-id="8c0da-217">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="8c0da-218">演算子</span><span class="sxs-lookup"><span data-stu-id="8c0da-218">Operator</span></span> | <span data-ttu-id="8c0da-219">関数</span><span class="sxs-lookup"><span data-stu-id="8c0da-219">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="8c0da-220">完全一致</span><span class="sxs-lookup"><span data-stu-id="8c0da-220">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="8c0da-221">完全一致ではない</span><span class="sxs-lookup"><span data-stu-id="8c0da-221">Not exact match</span></span> |
| `~`      | <span data-ttu-id="8c0da-222">内容</span><span class="sxs-lookup"><span data-stu-id="8c0da-222">Contains</span></span>        |
| `!~`     | <span data-ttu-id="8c0da-223">含まない</span><span class="sxs-lookup"><span data-stu-id="8c0da-223">Not contains</span></span>    |

<span data-ttu-id="8c0da-224">`<value>` は文字列です。</span><span class="sxs-lookup"><span data-stu-id="8c0da-224">`<value>` is a string.</span></span> <span data-ttu-id="8c0da-225">すべての参照で大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="8c0da-225">All the lookups are case insensitive.</span></span>

<span data-ttu-id="8c0da-226">`<operator>` を含まない式は、自動的に `FullyQualifiedName` プロパティの `contains` とみなされます (たとえば、`dotnet test --filter xyz` は `dotnet test --filter FullyQualifiedName~xyz` と同じです)。</span><span class="sxs-lookup"><span data-stu-id="8c0da-226">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="8c0da-227">式は条件演算子を使用して結合できます。</span><span class="sxs-lookup"><span data-stu-id="8c0da-227">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="8c0da-228">演算子</span><span class="sxs-lookup"><span data-stu-id="8c0da-228">Operator</span></span>            | <span data-ttu-id="8c0da-229">関数</span><span class="sxs-lookup"><span data-stu-id="8c0da-229">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="8c0da-230">OR</span><span class="sxs-lookup"><span data-stu-id="8c0da-230">OR</span></span>       |
| `&`                 | <span data-ttu-id="8c0da-231">AND</span><span class="sxs-lookup"><span data-stu-id="8c0da-231">AND</span></span>      |

<span data-ttu-id="8c0da-232">条件演算子を使用する場合は、式をかっこで囲みます (例: `(Name~TestMethod1) | (Name~TestMethod2)`)。</span><span class="sxs-lookup"><span data-stu-id="8c0da-232">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="8c0da-233">選択的単体テストのフィルター処理の使用方法に関する詳細と例については、「[選択的単体テストの実行](../testing/selective-unit-tests.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8c0da-233">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8c0da-234">関連項目</span><span class="sxs-lookup"><span data-stu-id="8c0da-234">See also</span></span>

- [<span data-ttu-id="8c0da-235">フレームワークとターゲット</span><span class="sxs-lookup"><span data-stu-id="8c0da-235">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="8c0da-236">.NET Core のランタイム識別子 (RID) のカタログ</span><span class="sxs-lookup"><span data-stu-id="8c0da-236">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
- [<span data-ttu-id="8c0da-237">コマンドラインを使用して runsettings 引数を渡す</span><span class="sxs-lookup"><span data-stu-id="8c0da-237">Passing runsettings arguments through commandline</span></span>](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)
