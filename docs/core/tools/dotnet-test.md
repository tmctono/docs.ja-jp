---
title: dotnet test コマンド
description: dotnet test コマンドは、指定されたプロジェクトで単体テストを実行する場合に使用されます。
ms.date: 02/27/2020
ms.openlocfilehash: 359e4522b26e2b59092d55eea3fca575d2afaf1f
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121038"
---
# <a name="dotnet-test"></a><span data-ttu-id="55e7c-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="55e7c-103">dotnet test</span></span>

<span data-ttu-id="55e7c-104">**この記事の対象:** ✔️ .NET Core 2.1 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="55e7c-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="55e7c-105">名前</span><span class="sxs-lookup"><span data-stu-id="55e7c-105">Name</span></span>

<span data-ttu-id="55e7c-106">`dotnet test` - 単体テストを実行するために使用される .NET テスト ドライバー。</span><span class="sxs-lookup"><span data-stu-id="55e7c-106">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="55e7c-107">構文</span><span class="sxs-lookup"><span data-stu-id="55e7c-107">Synopsis</span></span>

```dotnetcli
dotnet test [<PROJECT> | <SOLUTION>]
    [-a|--test-adapter-path] [--blame] [-c|--configuration]
    [--collect] [-d|--diag] [-f|--framework] [--filter]
    [--interactive] [-l|--logger] [--no-build] [--nologo]
    [--no-restore] [-o|--output] [-r|--results-directory]
    [--runtime] [-s|--settings] [-t|--list-tests]
    [-v|--verbosity] [[--] <RunSettings arguments>]

dotnet test [-h|--help]
```

## <a name="description"></a><span data-ttu-id="55e7c-108">説明</span><span class="sxs-lookup"><span data-stu-id="55e7c-108">Description</span></span>

<span data-ttu-id="55e7c-109">`dotnet test` コマンドは、指定されたプロジェクトで単体テストを実行する場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="55e7c-109">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="55e7c-110">`dotnet test` コマンドは、プロジェクト用に指定されたテスト ランナーのコンソール アプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="55e7c-110">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="55e7c-111">テスト ランナーでは、単体テスト フレームワーク (MSTest、NUnit、xUnit など) 用に定義されたテストを実行し、各テストの成功または失敗をレポートします。</span><span class="sxs-lookup"><span data-stu-id="55e7c-111">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="55e7c-112">すべてのテストが成功した場合、テスト ランナーは 0 の終了コードを返します。それ以外の、いずれかのテストに失敗した場合は、1 を返します。</span><span class="sxs-lookup"><span data-stu-id="55e7c-112">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span> <span data-ttu-id="55e7c-113">テスト ランナーと単体テスト ライブラリは、NuGet パッケージとしてパッケージ化され、プロジェクトの通常の依存関係として復元されます。</span><span class="sxs-lookup"><span data-stu-id="55e7c-113">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="55e7c-114">テスト プロジェクトでは、通常の `<PackageReference>` 要素を使用してテスト ランナーを指定します。次のサンプル プロジェクト ファイルのようになります。</span><span class="sxs-lookup"><span data-stu-id="55e7c-114">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="55e7c-115">引数</span><span class="sxs-lookup"><span data-stu-id="55e7c-115">Arguments</span></span>

- **`PROJECT | SOLUTION`**

  <span data-ttu-id="55e7c-116">テスト プロジェクトまたはソリューションへのパス。</span><span class="sxs-lookup"><span data-stu-id="55e7c-116">Path to the test project or solution.</span></span> <span data-ttu-id="55e7c-117">指定しない場合は、既定で現在のディレクトリに設定されます。</span><span class="sxs-lookup"><span data-stu-id="55e7c-117">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="55e7c-118">オプション</span><span class="sxs-lookup"><span data-stu-id="55e7c-118">Options</span></span>

- **`a|--test-adapter-path <PATH_TO_ADAPTER>`**

  <span data-ttu-id="55e7c-119">テスト実行で指定されたパスからカスタムのテスト アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="55e7c-119">Use the custom test adapters from the specified path in the test run.</span></span>

- **`--blame`**

  <span data-ttu-id="55e7c-120">変更履歴モードでテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="55e7c-120">Runs the tests in blame mode.</span></span> <span data-ttu-id="55e7c-121">このオプションは、テスト ホストがクラッシュする原因となる問題のあるテストを分離するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="55e7c-121">This option is helpful in isolating problematic tests that cause the test host to crash.</span></span> <span data-ttu-id="55e7c-122">これは、現在のディレクトリ内に出力ファイルを *Sequence.xml* として作成します。このファイルは、クラッシュ前にテストの実行順序をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="55e7c-122">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

- **`c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="55e7c-123">ビルド構成を定義します。</span><span class="sxs-lookup"><span data-stu-id="55e7c-123">Defines the build configuration.</span></span> <span data-ttu-id="55e7c-124">既定値は `Debug` ですが、プロジェクトの構成がこの既定の SDK 設定をオーバーライドする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="55e7c-124">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

- **`-collect <DATA_COLLECTOR_FRIENDLY_NAME>`**

  <span data-ttu-id="55e7c-125">テストの実行のためのデータ コレクターを有効にします。</span><span class="sxs-lookup"><span data-stu-id="55e7c-125">Enables data collector for the test run.</span></span> <span data-ttu-id="55e7c-126">詳細については、[「Monitor and analyze test run」](https://aka.ms/vstest-collect) (テストの実行のモニターと分析) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55e7c-126">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

- **`d|--diag <PATH_TO_DIAGNOSTICS_FILE>`**

  <span data-ttu-id="55e7c-127">テスト プラットフォームの診断モードを有効にし、指定したファイルに診断メッセージを出力します。</span><span class="sxs-lookup"><span data-stu-id="55e7c-127">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

- **`f|--framework <FRAMEWORK>`**

  <span data-ttu-id="55e7c-128">特定の[フレームワーク](../../standard/frameworks.md)のテスト バイナリを検索します。</span><span class="sxs-lookup"><span data-stu-id="55e7c-128">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

- **`--filter <EXPRESSION>`**

  <span data-ttu-id="55e7c-129">指定された式を使用して、現在のプロジェクト内のテストを除外します。</span><span class="sxs-lookup"><span data-stu-id="55e7c-129">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="55e7c-130">詳細については、「[フィルター オプションの詳細](#filter-option-details)」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="55e7c-130">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="55e7c-131">選択的単体テストのフィルター処理の使用方法に関する詳細と例については、「[選択的単体テストの実行](../testing/selective-unit-tests.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="55e7c-131">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

- **`h|--help`**

  <span data-ttu-id="55e7c-132">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="55e7c-132">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="55e7c-133">コマンドを停止して、ユーザーの入力または操作のために待機させることができます。</span><span class="sxs-lookup"><span data-stu-id="55e7c-133">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="55e7c-134">たとえば、認証を完了する場合があります。</span><span class="sxs-lookup"><span data-stu-id="55e7c-134">For example, to complete authentication.</span></span> <span data-ttu-id="55e7c-135">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="55e7c-135">Available since .NET Core 3.0 SDK.</span></span>

- **`l|--logger <LoggerUri/FriendlyName>`**

  <span data-ttu-id="55e7c-136">テスト結果のロガーを指定します。</span><span class="sxs-lookup"><span data-stu-id="55e7c-136">Specifies a logger for test results.</span></span> <span data-ttu-id="55e7c-137">MSBuild とは異なり、dotnet テストでは省略形は受け入れられません。`-l "console;v=d"` ではなく `-l "console;verbosity=detailed"` を使用してください。</span><span class="sxs-lookup"><span data-stu-id="55e7c-137">Unlike MSBuild, dotnet test doesn't accept abbreviations: instead of `-l "console;v=d"` use `-l "console;verbosity=detailed"`.</span></span>

- **`--no-build`**

  <span data-ttu-id="55e7c-138">実行前にテスト プロジェクトをビルドしません。</span><span class="sxs-lookup"><span data-stu-id="55e7c-138">Doesn't build the test project before running it.</span></span> <span data-ttu-id="55e7c-139">また、- `--no-restore` フラグが暗黙的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="55e7c-139">It also implicitly sets the - `--no-restore` flag.</span></span>

- **`--nologo`**

  <span data-ttu-id="55e7c-140">Microsoft TestPlatform バナーを表示せずにテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="55e7c-140">Run tests without displaying the Microsoft TestPlatform banner.</span></span> <span data-ttu-id="55e7c-141">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="55e7c-141">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-restore`**

  <span data-ttu-id="55e7c-142">コマンドを実行するときに、暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="55e7c-142">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="55e7c-143">実行するバイナリを検索するディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="55e7c-143">Directory in which to find the binaries to run.</span></span>

- **`-r|--results-directory <PATH>`**

  <span data-ttu-id="55e7c-144">テスト結果が配置されるディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="55e7c-144">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="55e7c-145">指定されたディレクトリが存在しない場合は、作成されます。</span><span class="sxs-lookup"><span data-stu-id="55e7c-145">If the specified directory doesn't exist, it's created.</span></span>

- **`--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="55e7c-146">テスト対象のターゲット ランタイム。</span><span class="sxs-lookup"><span data-stu-id="55e7c-146">The target runtime to test for.</span></span>

- **`-s|--settings <SETTINGS_FILE>`**

  <span data-ttu-id="55e7c-147">テストの実行に使用する `.runsettings` ファイルです。</span><span class="sxs-lookup"><span data-stu-id="55e7c-147">The `.runsettings` file to use for running the tests.</span></span> [<span data-ttu-id="55e7c-148">`.runsettings` ファイルを使用して単体テストを構成します。</span><span class="sxs-lookup"><span data-stu-id="55e7c-148">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)

- **`-t|--list-tests`**

  <span data-ttu-id="55e7c-149">現在のプロジェクトで検出されたすべてのテストを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="55e7c-149">List all of the discovered tests in the current project.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="55e7c-150">コマンドの詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="55e7c-150">Sets the verbosity level of the command.</span></span> <span data-ttu-id="55e7c-151">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="55e7c-151">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="55e7c-152">既定値は、`minimal` です。</span><span class="sxs-lookup"><span data-stu-id="55e7c-152">The default is `minimal`.</span></span> <span data-ttu-id="55e7c-153">詳細については、「<xref:Microsoft.Build.Framework.LoggerVerbosity>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55e7c-153">For more information, see <xref:Microsoft.Build.Framework.LoggerVerbosity>.</span></span>

- <span data-ttu-id="55e7c-154">`RunSettings` 引数</span><span class="sxs-lookup"><span data-stu-id="55e7c-154">`RunSettings` arguments</span></span>

  <span data-ttu-id="55e7c-155">引数は、テストの `RunSettings` 構成として渡されます。</span><span class="sxs-lookup"><span data-stu-id="55e7c-155">Arguments are passed as `RunSettings` configurations for the test.</span></span> <span data-ttu-id="55e7c-156">引数は、"-- " に続く `[name]=[value]` のペアとして指定されます (-- の後ろのスペースに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="55e7c-156">Arguments are specified as `[name]=[value]` pairs after "-- " (note the space after --).</span></span> <span data-ttu-id="55e7c-157">複数の `[name]=[value]` のペアを区切るにはスペースを使用します。</span><span class="sxs-lookup"><span data-stu-id="55e7c-157">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

  <span data-ttu-id="55e7c-158">例 : `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="55e7c-158">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

  <span data-ttu-id="55e7c-159">詳細については、[vstest.console.exe の RunSettings 引数渡し](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="55e7c-159">For more information, see [vstest.console.exe: Passing RunSettings args](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

## <a name="examples"></a><span data-ttu-id="55e7c-160">使用例</span><span class="sxs-lookup"><span data-stu-id="55e7c-160">Examples</span></span>

- <span data-ttu-id="55e7c-161">現在のディレクトリのプロジェクトでテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="55e7c-161">Run the tests in the project in the current directory:</span></span>

  ```dotnetcli
  dotnet test
  ```

- <span data-ttu-id="55e7c-162">`test1` プロジェクトでテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="55e7c-162">Run the tests in the `test1` project:</span></span>

  ```dotnetcli
  dotnet test ~/projects/test1/test1.csproj
  ```

- <span data-ttu-id="55e7c-163">現在のディレクトリでプロジェクトのテストを実行し、trx 形式でテスト結果ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="55e7c-163">Run the tests in the project in the current directory, and generate a test results file in the trx format:</span></span>

  ```dotnetcli
  dotnet test --logger trx
  ```

- <span data-ttu-id="55e7c-164">現在のディレクトリでプロジェクトのテストを実行し、詳細をコンソールに記録します。</span><span class="sxs-lookup"><span data-stu-id="55e7c-164">Run the tests in the project in the current directory, and log with detailed verbosity to the console:</span></span>

  ```dotnetcli
  dotnet test --logger "console;verbosity=detailed"
  ```

## <a name="filter-option-details"></a><span data-ttu-id="55e7c-165">フィルター オプションの詳細</span><span class="sxs-lookup"><span data-stu-id="55e7c-165">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="55e7c-166">`<Expression>` の形式は `<property><operator><value>[|&<Expression>]` です。</span><span class="sxs-lookup"><span data-stu-id="55e7c-166">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="55e7c-167">`<property>` は `Test Case` の属性です。</span><span class="sxs-lookup"><span data-stu-id="55e7c-167">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="55e7c-168">よく利用される単体テスト フレームワークでサポートされるプロパティは以下の通りです。</span><span class="sxs-lookup"><span data-stu-id="55e7c-168">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="55e7c-169">テスト フレームワーク</span><span class="sxs-lookup"><span data-stu-id="55e7c-169">Test Framework</span></span> | <span data-ttu-id="55e7c-170">サポートされるプロパティ</span><span class="sxs-lookup"><span data-stu-id="55e7c-170">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="55e7c-171">MSTest</span><span class="sxs-lookup"><span data-stu-id="55e7c-171">MSTest</span></span>         | <ul><li><span data-ttu-id="55e7c-172">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="55e7c-172">FullyQualifiedName</span></span></li><li><span data-ttu-id="55e7c-173">名前</span><span class="sxs-lookup"><span data-stu-id="55e7c-173">Name</span></span></li><li><span data-ttu-id="55e7c-174">ClassName</span><span class="sxs-lookup"><span data-stu-id="55e7c-174">ClassName</span></span></li><li><span data-ttu-id="55e7c-175">優先度</span><span class="sxs-lookup"><span data-stu-id="55e7c-175">Priority</span></span></li><li><span data-ttu-id="55e7c-176">TestCategory</span><span class="sxs-lookup"><span data-stu-id="55e7c-176">TestCategory</span></span></li></ul> |
| <span data-ttu-id="55e7c-177">xUnit</span><span class="sxs-lookup"><span data-stu-id="55e7c-177">xUnit</span></span>          | <ul><li><span data-ttu-id="55e7c-178">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="55e7c-178">FullyQualifiedName</span></span></li><li><span data-ttu-id="55e7c-179">DisplayName</span><span class="sxs-lookup"><span data-stu-id="55e7c-179">DisplayName</span></span></li><li><span data-ttu-id="55e7c-180">Traits</span><span class="sxs-lookup"><span data-stu-id="55e7c-180">Traits</span></span></li></ul>                                   |

<span data-ttu-id="55e7c-181">`<operator>` は、プロパティと値の関係を示します。</span><span class="sxs-lookup"><span data-stu-id="55e7c-181">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="55e7c-182">演算子</span><span class="sxs-lookup"><span data-stu-id="55e7c-182">Operator</span></span> | <span data-ttu-id="55e7c-183">関数</span><span class="sxs-lookup"><span data-stu-id="55e7c-183">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="55e7c-184">完全一致</span><span class="sxs-lookup"><span data-stu-id="55e7c-184">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="55e7c-185">完全一致ではない</span><span class="sxs-lookup"><span data-stu-id="55e7c-185">Not exact match</span></span> |
| `~`      | <span data-ttu-id="55e7c-186">内容</span><span class="sxs-lookup"><span data-stu-id="55e7c-186">Contains</span></span>        |
| `!~`     | <span data-ttu-id="55e7c-187">含まない</span><span class="sxs-lookup"><span data-stu-id="55e7c-187">Not contains</span></span>    |

<span data-ttu-id="55e7c-188">`<value>` は文字列です。</span><span class="sxs-lookup"><span data-stu-id="55e7c-188">`<value>` is a string.</span></span> <span data-ttu-id="55e7c-189">すべての参照で大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="55e7c-189">All the lookups are case insensitive.</span></span>

<span data-ttu-id="55e7c-190">`<operator>` を含まない式は、自動的に `FullyQualifiedName` プロパティの `contains` とみなされます (たとえば、`dotnet test --filter xyz` は `dotnet test --filter FullyQualifiedName~xyz` と同じです)。</span><span class="sxs-lookup"><span data-stu-id="55e7c-190">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="55e7c-191">式は条件演算子を使用して結合できます。</span><span class="sxs-lookup"><span data-stu-id="55e7c-191">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="55e7c-192">演算子</span><span class="sxs-lookup"><span data-stu-id="55e7c-192">Operator</span></span>            | <span data-ttu-id="55e7c-193">関数</span><span class="sxs-lookup"><span data-stu-id="55e7c-193">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="55e7c-194">OR</span><span class="sxs-lookup"><span data-stu-id="55e7c-194">OR</span></span>       |
| `&`                 | <span data-ttu-id="55e7c-195">AND</span><span class="sxs-lookup"><span data-stu-id="55e7c-195">AND</span></span>      |

<span data-ttu-id="55e7c-196">条件演算子を使用する場合は、式をかっこで囲みます (例: `(Name~TestMethod1) | (Name~TestMethod2)`)。</span><span class="sxs-lookup"><span data-stu-id="55e7c-196">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="55e7c-197">選択的単体テストのフィルター処理の使用方法に関する詳細と例については、「[選択的単体テストの実行](../testing/selective-unit-tests.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="55e7c-197">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="55e7c-198">関連項目</span><span class="sxs-lookup"><span data-stu-id="55e7c-198">See also</span></span>

- [<span data-ttu-id="55e7c-199">フレームワークとターゲット</span><span class="sxs-lookup"><span data-stu-id="55e7c-199">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="55e7c-200">.NET Core のランタイム識別子 (RID) のカタログ</span><span class="sxs-lookup"><span data-stu-id="55e7c-200">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
- [<span data-ttu-id="55e7c-201">コマンドラインを使用して runsettings 引数を渡す</span><span class="sxs-lookup"><span data-stu-id="55e7c-201">Passing runsettings arguments through commandline</span></span>](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)
