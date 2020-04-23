---
title: dotnet vstest コマンド
description: dotnet vstest コマンドは、プロジェクトとそのすべての依存関係をビルドします。
ms.date: 02/27/2020
ms.openlocfilehash: e8fa94cf12ca2fe5fb99c6e3c1dcdb52185798c0
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463281"
---
# <a name="dotnet-vstest"></a><span data-ttu-id="fadf6-103">dotnet vstest</span><span class="sxs-lookup"><span data-stu-id="fadf6-103">dotnet vstest</span></span>

<span data-ttu-id="fadf6-104">**この記事の対象:** ✔️ .NET Core 2.1 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="fadf6-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="fadf6-105">名前</span><span class="sxs-lookup"><span data-stu-id="fadf6-105">Name</span></span>

<span data-ttu-id="fadf6-106">`dotnet-vstest` - 指定されたファイルからテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="fadf6-106">`dotnet-vstest` - Runs tests from the specified files.</span></span>

## <a name="synopsis"></a><span data-ttu-id="fadf6-107">構文</span><span class="sxs-lookup"><span data-stu-id="fadf6-107">Synopsis</span></span>

```dotnetcli
dotnet vstest [<TEST_FILE_NAMES>] [--Blame] [--Diag <PATH_TO_LOG_FILE>]
    [--Framework <FRAMEWORK>] [--InIsolation] [-lt|--ListTests <FILE_NAME>]
    [--logger <LOGGER_URI/FRIENDLY_NAME>] [--Parallel]
    [--ParentProcessId <PROCESS_ID>] [--Platform] <PLATFORM_TYPE>
    [--Port <PORT>] [--ResultsDirectory<PATH>] [--Settings <SETTINGS_FILE>]
    [--TestAdapterPath <PATH>] [--TestCaseFilter <EXPRESSION>]
    [--Tests <TEST_NAMES>] [[--] <args>...]]

dotnet vstest -?|--Help
```

## <a name="description"></a><span data-ttu-id="fadf6-108">説明</span><span class="sxs-lookup"><span data-stu-id="fadf6-108">Description</span></span>

<span data-ttu-id="fadf6-109">`dotnet-vstest` コマンドでは、`VSTest.Console` コマンド ライン アプリケーションが実行されて、自動単体テストが実行されます。</span><span class="sxs-lookup"><span data-stu-id="fadf6-109">The `dotnet-vstest` command runs the `VSTest.Console` command-line application to run automated unit tests.</span></span>

## <a name="arguments"></a><span data-ttu-id="fadf6-110">引数</span><span class="sxs-lookup"><span data-stu-id="fadf6-110">Arguments</span></span>

- **`TEST_FILE_NAMES`**

  <span data-ttu-id="fadf6-111">指定されたアセンブリからテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="fadf6-111">Run tests from the specified assemblies.</span></span> <span data-ttu-id="fadf6-112">複数のテスト アセンブリ名を指定するときは、空白で区切ります。</span><span class="sxs-lookup"><span data-stu-id="fadf6-112">Separate multiple test assembly names with spaces.</span></span> <span data-ttu-id="fadf6-113">ワイルドカードを利用できます。</span><span class="sxs-lookup"><span data-stu-id="fadf6-113">Wildcards are supported.</span></span>

## <a name="options"></a><span data-ttu-id="fadf6-114">オプション</span><span class="sxs-lookup"><span data-stu-id="fadf6-114">Options</span></span>

- **`--Blame`**

  <span data-ttu-id="fadf6-115">変更履歴モードでテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="fadf6-115">Runs the tests in blame mode.</span></span> <span data-ttu-id="fadf6-116">このオプションは、テスト ホストのクラッシュを引き起こす問題のあるテストを分離するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fadf6-116">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="fadf6-117">これは、現在のディレクトリ内に出力ファイルを *Sequence.xml* として作成します。このファイルは、クラッシュ前にテストの実行順序をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="fadf6-117">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

- **`--Diag <PATH_TO_LOG_FILE>`**

  <span data-ttu-id="fadf6-118">テスト プラットフォームの詳細ログを有効にします。</span><span class="sxs-lookup"><span data-stu-id="fadf6-118">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="fadf6-119">指定されたファイルにログが書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="fadf6-119">Logs are written to the provided file.</span></span>

- **`--Framework <FRAMEWORK>`**

  <span data-ttu-id="fadf6-120">テストの実行に使用する対象の .NET Framework バージョンです。</span><span class="sxs-lookup"><span data-stu-id="fadf6-120">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="fadf6-121">有効な値の例としては、`.NETFramework,Version=v4.6` や `.NETCoreApp,Version=v1.0` などがあります。</span><span class="sxs-lookup"><span data-stu-id="fadf6-121">Examples of valid values are `.NETFramework,Version=v4.6` or `.NETCoreApp,Version=v1.0`.</span></span> <span data-ttu-id="fadf6-122">サポートされるその他の値は、`Framework40`、`Framework45`、`FrameworkCore10`、および `FrameworkUap10` です。</span><span class="sxs-lookup"><span data-stu-id="fadf6-122">Other supported values are `Framework40`, `Framework45`, `FrameworkCore10`, and `FrameworkUap10`.</span></span>

- **`--InIsolation`**

  <span data-ttu-id="fadf6-123">分離プロセスでテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="fadf6-123">Runs the tests in an isolated process.</span></span> <span data-ttu-id="fadf6-124">これにより、テストでエラーが発生しても *vstest.console.exe* プロセスが停止することは少なくなりますが、テストの実行速度は低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fadf6-124">This makes *vstest.console.exe* process less likely to be stopped on an error in the tests, but tests may run slower.</span></span>

- **`-lt|--ListTests <FILE_NAME>`**

  <span data-ttu-id="fadf6-125">指定されたテスト コンテナーから探索されたテストをすべて一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="fadf6-125">Lists all discovered tests from the given test container.</span></span>

- **`--logger <LOGGER_URI/FRIENDLY_NAME>`**

  <span data-ttu-id="fadf6-126">テスト結果のロガーを指定します。</span><span class="sxs-lookup"><span data-stu-id="fadf6-126">Specify a logger for test results.</span></span>

  - <span data-ttu-id="fadf6-127">Team Foundation Server にテスト結果を発行するには、次のように `TfsPublisher` ロガー プロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="fadf6-127">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

    ```console
    /logger:TfsPublisher;
        Collection=<team project collection url>;
        BuildName=<build name>;
        TeamProject=<team project name>
        [;Platform=<Defaults to "Any CPU">]
        [;Flavor=<Defaults to "Debug">]
        [;RunTitle=<title>]
    ```

  - <span data-ttu-id="fadf6-128">Visual Studio テスト結果ファイル (TRX) に結果のログを書き込むには、`trx` ロガー プロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="fadf6-128">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="fadf6-129">このように切り替えることで、テスト結果ディレクトリに指定のログ ファイル名でファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="fadf6-129">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="fadf6-130">`LogFileName` が指定されていない場合は、テスト結果を保持するために一意のファイル名が作成されます。</span><span class="sxs-lookup"><span data-stu-id="fadf6-130">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

    ```console
    /logger:trx [;LogFileName=<Defaults to unique file name>]
    ```

- **`--Parallel`**

  <span data-ttu-id="fadf6-131">テストを並列で実行します。</span><span class="sxs-lookup"><span data-stu-id="fadf6-131">Run tests in parallel.</span></span> <span data-ttu-id="fadf6-132">既定では、コンピューター上のすべての使用可能なコアを使用できます。</span><span class="sxs-lookup"><span data-stu-id="fadf6-132">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="fadf6-133">*runsettings* ファイルの `RunConfiguration` ノードの下に `MaxCpuCount` プロパティを設定して、明示的なコア数を指定します。</span><span class="sxs-lookup"><span data-stu-id="fadf6-133">Specify an explicit number of cores by setting the `MaxCpuCount` property under the `RunConfiguration` node in the *runsettings* file.</span></span>

- **`--ParentProcessId <PROCESS_ID>`**

  <span data-ttu-id="fadf6-134">現在のプロセスを起動する親プロセスのプロセス ID です。</span><span class="sxs-lookup"><span data-stu-id="fadf6-134">Process ID of the parent process responsible for launching the current process.</span></span>

- **`--Platform <PLATFORM_TYPE>`**

  <span data-ttu-id="fadf6-135">テストの実行に使用する対象のプラットフォーム アーキテクチャです。</span><span class="sxs-lookup"><span data-stu-id="fadf6-135">Target platform architecture used for test execution.</span></span> <span data-ttu-id="fadf6-136">有効な値は `x86`、`x64`、`ARM` です。</span><span class="sxs-lookup"><span data-stu-id="fadf6-136">Valid values are `x86`, `x64`, and `ARM`.</span></span>

- **`--Port <PORT>`**

  <span data-ttu-id="fadf6-137">ソケット接続およびイベント メッセージの受信用のポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="fadf6-137">Specifies the port for the socket connection and receiving the event messages.</span></span>

- **`--ResultsDirectory:<PATH>`**

  <span data-ttu-id="fadf6-138">テスト結果ディレクトリが存在しない場合、指定されたパスに作成されます。</span><span class="sxs-lookup"><span data-stu-id="fadf6-138">Test results directory will be created in specified path if not exists.</span></span>

- **`--Settings <SETTINGS_FILE>`**

  <span data-ttu-id="fadf6-139">テストの実行時に使用される設定です。</span><span class="sxs-lookup"><span data-stu-id="fadf6-139">Settings to use when running tests.</span></span>

- **`--TestAdapterPath <PATH>`**

  <span data-ttu-id="fadf6-140">テストの実行では、指定されたパス (存在する場合) からカスタム テスト アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="fadf6-140">Use custom test adapters from a given path (if any) in the test run.</span></span>

- **`--TestCaseFilter <EXPRESSION>`**

  <span data-ttu-id="fadf6-141">指定した式に一致するテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="fadf6-141">Run tests that match the given expression.</span></span> <span data-ttu-id="fadf6-142">`<EXPRESSION>` の形式は `<property>Operator<value>[|&<EXPRESSION>]` です。この場合の演算子は `=`、`!=`、または `~` のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="fadf6-142">`<EXPRESSION>` is of the format `<property>Operator<value>[|&<EXPRESSION>]`, where Operator is one of `=`, `!=`, or `~`.</span></span> <span data-ttu-id="fadf6-143">演算子 `~` は 'contains' セマンティクスを持ち、`DisplayName` などの文字列プロパティに適用できます。</span><span class="sxs-lookup"><span data-stu-id="fadf6-143">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="fadf6-144">サブ式のグループ化には、かっこ `()` を使用します。</span><span class="sxs-lookup"><span data-stu-id="fadf6-144">Parentheses `()` are used to group subexpressions.</span></span> <span data-ttu-id="fadf6-145">詳細については、[TestCase フィルター](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fadf6-145">For more information, see [TestCase filter](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).</span></span>

- **`--Tests <TEST_NAMES>`**

  <span data-ttu-id="fadf6-146">指定した値に一致する名前のテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="fadf6-146">Run tests with names that match the provided values.</span></span> <span data-ttu-id="fadf6-147">複数の値を指定するときは、コンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="fadf6-147">Separate multiple values with commas.</span></span>

- **`-?|--Help`**

  <span data-ttu-id="fadf6-148">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="fadf6-148">Prints out a short help for the command.</span></span>

- **`@<file>`**

  <span data-ttu-id="fadf6-149">応答ファイルを読み込んで、オプションを追加します。</span><span class="sxs-lookup"><span data-stu-id="fadf6-149">Reads response file for more options.</span></span>

- **`args`**

  <span data-ttu-id="fadf6-150">アダプターに渡す追加の引数を指定します。</span><span class="sxs-lookup"><span data-stu-id="fadf6-150">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="fadf6-151">引数は `<n>=<v>` 形式の名前と値のペアとして指定されます。この場合の `<n>` は引数名、`<v>` は引数値です。</span><span class="sxs-lookup"><span data-stu-id="fadf6-151">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="fadf6-152">複数の引数を指定する場合は、空白で区切ります。</span><span class="sxs-lookup"><span data-stu-id="fadf6-152">Use a space to separate multiple arguments.</span></span>

## <a name="examples"></a><span data-ttu-id="fadf6-153">使用例</span><span class="sxs-lookup"><span data-stu-id="fadf6-153">Examples</span></span>

<span data-ttu-id="fadf6-154">*mytestproject.dll* でテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="fadf6-154">Run tests in *mytestproject.dll*:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll
```

<span data-ttu-id="fadf6-155">*mytestproject.dll* でテストを実行し、カスタム名を指定してカスタム フォルダーにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="fadf6-155">Run tests in *mytestproject.dll*, exporting to custom folder with custom name:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll --logger:"trx;LogFileName=custom_file_name.trx" --ResultsDirectory:custom/file/path
```

<span data-ttu-id="fadf6-156">*mytestproject.dll* と *myothertestproject.exe* でテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="fadf6-156">Run tests in *mytestproject.dll* and *myothertestproject.exe*:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll myothertestproject.exe
```

<span data-ttu-id="fadf6-157">`TestMethod1` テストを実行する:</span><span class="sxs-lookup"><span data-stu-id="fadf6-157">Run `TestMethod1` tests:</span></span>

```dotnetcli
dotnet vstest /Tests:TestMethod1
```

<span data-ttu-id="fadf6-158">`TestMethod1` および `TestMethod2` テストを実行する:</span><span class="sxs-lookup"><span data-stu-id="fadf6-158">Run `TestMethod1` and `TestMethod2` tests:</span></span>

```dotnetcli
dotnet vstest /Tests:TestMethod1,TestMethod2
```

## <a name="see-also"></a><span data-ttu-id="fadf6-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="fadf6-159">See also</span></span>

- [<span data-ttu-id="fadf6-160">VSTest.Console.exe のコマンド ライン オプション</span><span class="sxs-lookup"><span data-stu-id="fadf6-160">VSTest.Console.exe command-line options</span></span>](/visualstudio/test/vstest-console-options)
