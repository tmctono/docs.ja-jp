---
title: dotnet vstest コマンド
description: dotnet vstest コマンドは、プロジェクトとそのすべての依存関係をビルドします。
ms.date: 02/27/2020
ms.openlocfilehash: 88e5b6a8966d78d0746f9ea5ccbccab142a2e0f6
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156934"
---
# <a name="dotnet-vstest"></a><span data-ttu-id="cecea-103">dotnet vstest</span><span class="sxs-lookup"><span data-stu-id="cecea-103">dotnet vstest</span></span>

<span data-ttu-id="cecea-104">**この記事の対象:** ✔️ .NET Core 2.1 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="cecea-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="cecea-105">名前</span><span class="sxs-lookup"><span data-stu-id="cecea-105">Name</span></span>

<span data-ttu-id="cecea-106">`dotnet-vstest` - 指定されたファイルからテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="cecea-106">`dotnet-vstest` - Runs tests from the specified files.</span></span>

## <a name="synopsis"></a><span data-ttu-id="cecea-107">構文</span><span class="sxs-lookup"><span data-stu-id="cecea-107">Synopsis</span></span>

```dotnetcli
dotnet vstest [<TEST_FILE_NAMES>] [--Settings] [--Tests]
    [--TestAdapterPath] [--Platform] [--Framework] [--Parallel]
    [--TestCaseFilter] [--logger] [-lt|--ListTests]
    [--ParentProcessId] [--Port] [--Diag] [--Blame]
    [--InIsolation] [[--] <args>...]] [-?|--Help]
```

## <a name="description"></a><span data-ttu-id="cecea-108">説明</span><span class="sxs-lookup"><span data-stu-id="cecea-108">Description</span></span>

<span data-ttu-id="cecea-109">`dotnet-vstest` コマンドでは、`VSTest.Console` コマンド ライン アプリケーションが実行されて、自動単体テストが実行されます。</span><span class="sxs-lookup"><span data-stu-id="cecea-109">The `dotnet-vstest` command runs the `VSTest.Console` command-line application to run automated unit tests.</span></span>

## <a name="arguments"></a><span data-ttu-id="cecea-110">引数</span><span class="sxs-lookup"><span data-stu-id="cecea-110">Arguments</span></span>

- **`TEST_FILE_NAMES`**

  <span data-ttu-id="cecea-111">指定されたアセンブリからテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="cecea-111">Run tests from the specified assemblies.</span></span> <span data-ttu-id="cecea-112">複数のテスト アセンブリ名を指定するときは、空白で区切ります。</span><span class="sxs-lookup"><span data-stu-id="cecea-112">Separate multiple test assembly names with spaces.</span></span> <span data-ttu-id="cecea-113">ワイルドカードを利用できます。</span><span class="sxs-lookup"><span data-stu-id="cecea-113">Wildcards are supported.</span></span>

## <a name="options"></a><span data-ttu-id="cecea-114">オプション</span><span class="sxs-lookup"><span data-stu-id="cecea-114">Options</span></span>

- **`--Settings <Settings File>`**

  <span data-ttu-id="cecea-115">テストの実行時に使用される設定です。</span><span class="sxs-lookup"><span data-stu-id="cecea-115">Settings to use when running tests.</span></span>

- **`--Tests <Test Names>`**

  <span data-ttu-id="cecea-116">指定した値に一致する名前のテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="cecea-116">Run tests with names that match the provided values.</span></span> <span data-ttu-id="cecea-117">複数の値を指定するときは、コンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="cecea-117">Separate multiple values with commas.</span></span>

- **`--TestAdapterPath`**

  <span data-ttu-id="cecea-118">テストの実行では、指定されたパス (存在する場合) からカスタム テスト アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="cecea-118">Use custom test adapters from a given path (if any) in the test run.</span></span>

- **`--Platform <Platform type>`**

  <span data-ttu-id="cecea-119">テストの実行に使用する対象のプラットフォーム アーキテクチャです。</span><span class="sxs-lookup"><span data-stu-id="cecea-119">Target platform architecture used for test execution.</span></span> <span data-ttu-id="cecea-120">有効な値は `x86`、`x64`、`ARM` です。</span><span class="sxs-lookup"><span data-stu-id="cecea-120">Valid values are `x86`, `x64`, and `ARM`.</span></span>

- **`--Framework <Framework Version>`**

  <span data-ttu-id="cecea-121">テストの実行に使用する対象の .NET Framework バージョンです。</span><span class="sxs-lookup"><span data-stu-id="cecea-121">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="cecea-122">有効な値の例としては、`.NETFramework,Version=v4.6` や `.NETCoreApp,Version=v1.0` などがあります。</span><span class="sxs-lookup"><span data-stu-id="cecea-122">Examples of valid values are `.NETFramework,Version=v4.6` or `.NETCoreApp,Version=v1.0`.</span></span> <span data-ttu-id="cecea-123">サポートされるその他の値は、`Framework40`、`Framework45`、`FrameworkCore10`、および `FrameworkUap10` です。</span><span class="sxs-lookup"><span data-stu-id="cecea-123">Other supported values are `Framework40`, `Framework45`, `FrameworkCore10`, and `FrameworkUap10`.</span></span>

- **`--Parallel`**

  <span data-ttu-id="cecea-124">テストを並列で実行します。</span><span class="sxs-lookup"><span data-stu-id="cecea-124">Run tests in parallel.</span></span> <span data-ttu-id="cecea-125">既定では、コンピューター上のすべての使用可能なコアを使用できます。</span><span class="sxs-lookup"><span data-stu-id="cecea-125">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="cecea-126">*runsettings* ファイルの `RunConfiguration` ノードの下に `MaxCpuCount` プロパティを設定して、明示的なコア数を指定します。</span><span class="sxs-lookup"><span data-stu-id="cecea-126">Specify an explicit number of cores by setting the `MaxCpuCount` property under the `RunConfiguration` node in the *runsettings* file.</span></span>

- **`--TestCaseFilter <Expression>`**

  <span data-ttu-id="cecea-127">指定した式に一致するテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="cecea-127">Run tests that match the given expression.</span></span> <span data-ttu-id="cecea-128">`<Expression>` の形式は `<property>Operator<value>[|&<Expression>]` です。この場合の演算子は `=`、`!=`、または `~` のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="cecea-128">`<Expression>` is of the format `<property>Operator<value>[|&<Expression>]`, where Operator is one of `=`, `!=`, or `~`.</span></span> <span data-ttu-id="cecea-129">演算子 `~` は 'contains' セマンティクスを持ち、`DisplayName` などの文字列プロパティに適用できます。</span><span class="sxs-lookup"><span data-stu-id="cecea-129">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="cecea-130">サブ式をグループ化するにはかっこ `()` を使用します。</span><span class="sxs-lookup"><span data-stu-id="cecea-130">Parenthesis `()` are used to group subexpressions.</span></span>

- **`-?|--Help`**

  <span data-ttu-id="cecea-131">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="cecea-131">Prints out a short help for the command.</span></span>

- **`--logger <Logger Uri/FriendlyName>`**

  <span data-ttu-id="cecea-132">テスト結果のロガーを指定します。</span><span class="sxs-lookup"><span data-stu-id="cecea-132">Specify a logger for test results.</span></span>

  - <span data-ttu-id="cecea-133">Team Foundation Server にテスト結果を発行するには、次のように `TfsPublisher` ロガー プロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="cecea-133">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

    ```console
    /logger:TfsPublisher;
        Collection=<team project collection url>;
        BuildName=<build name>;
        TeamProject=<team project name>
        [;Platform=<Defaults to "Any CPU">]
        [;Flavor=<Defaults to "Debug">]
        [;RunTitle=<title>]
    ```

  - <span data-ttu-id="cecea-134">Visual Studio テスト結果ファイル (TRX) に結果のログを書き込むには、`trx` ロガー プロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="cecea-134">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="cecea-135">このように切り替えることで、テスト結果ディレクトリに指定のログ ファイル名でファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="cecea-135">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="cecea-136">`LogFileName` が指定されていない場合は、テスト結果を保持するために一意のファイル名が作成されます。</span><span class="sxs-lookup"><span data-stu-id="cecea-136">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

    ```console
    /logger:trx [;LogFileName=<Defaults to unique file name>]
    ```

- **`-lt|--ListTests <File Name>`**

  <span data-ttu-id="cecea-137">指定されたテスト コンテナーから探索されたテストをすべて一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="cecea-137">Lists all discovered tests from the given test container.</span></span>

- **`--ParentProcessId <ParentProcessId>`**

  <span data-ttu-id="cecea-138">現在のプロセスを起動する親プロセスのプロセス ID です。</span><span class="sxs-lookup"><span data-stu-id="cecea-138">Process ID of the parent process responsible for launching the current process.</span></span>

- **`--Port <Port>`**

  <span data-ttu-id="cecea-139">ソケット接続およびイベント メッセージの受信用のポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="cecea-139">Specifies the port for the socket connection and receiving the event messages.</span></span>

- **`--Diag <Path to log file>`**

  <span data-ttu-id="cecea-140">テスト プラットフォームの詳細ログを有効にします。</span><span class="sxs-lookup"><span data-stu-id="cecea-140">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="cecea-141">指定されたファイルにログが書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="cecea-141">Logs are written to the provided file.</span></span>

- **`--Blame`**

  <span data-ttu-id="cecea-142">変更履歴モードでテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="cecea-142">Runs the tests in blame mode.</span></span> <span data-ttu-id="cecea-143">このオプションは、テスト ホストのクラッシュを引き起こす問題のあるテストを分離するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="cecea-143">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="cecea-144">これは、現在のディレクトリ内に出力ファイルを *Sequence.xml* として作成します。このファイルは、クラッシュ前にテストの実行順序をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="cecea-144">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

- **`--InIsolation`**

  <span data-ttu-id="cecea-145">分離プロセスでテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="cecea-145">Runs the tests in an isolated process.</span></span> <span data-ttu-id="cecea-146">これにより、テストでエラーが発生しても *vstest.console.exe* プロセスが停止することは少なくなりますが、テストの実行速度は低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cecea-146">This makes *vstest.console.exe* process less likely to be stopped on an error in the tests, but tests may run slower.</span></span>

- **`@<file>`**

  <span data-ttu-id="cecea-147">応答ファイルを読み込んで、オプションを追加します。</span><span class="sxs-lookup"><span data-stu-id="cecea-147">Reads response file for more options.</span></span>

- **`args`**

  <span data-ttu-id="cecea-148">アダプターに渡す追加の引数を指定します。</span><span class="sxs-lookup"><span data-stu-id="cecea-148">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="cecea-149">引数は `<n>=<v>` 形式の名前と値のペアとして指定されます。この場合の `<n>` は引数名、`<v>` は引数値です。</span><span class="sxs-lookup"><span data-stu-id="cecea-149">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="cecea-150">複数の引数を指定する場合は、空白で区切ります。</span><span class="sxs-lookup"><span data-stu-id="cecea-150">Use a space to separate multiple arguments.</span></span>

## <a name="examples"></a><span data-ttu-id="cecea-151">使用例</span><span class="sxs-lookup"><span data-stu-id="cecea-151">Examples</span></span>

<span data-ttu-id="cecea-152">*mytestproject.dll* でテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="cecea-152">Run tests in *mytestproject.dll*:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll
```

<span data-ttu-id="cecea-153">*mytestproject.dll* でテストを実行し、カスタム名を指定してカスタム フォルダーにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="cecea-153">Run tests in *mytestproject.dll*, exporting to custom folder with custom name:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll --logger:"trx;LogFileName=custom_file_name.trx" --ResultsDirectory:custom/file/path
```

<span data-ttu-id="cecea-154">*mytestproject.dll* と *myothertestproject.exe* でテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="cecea-154">Run tests in *mytestproject.dll* and *myothertestproject.exe*:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll myothertestproject.exe
```

<span data-ttu-id="cecea-155">`TestMethod1` テストを実行する:</span><span class="sxs-lookup"><span data-stu-id="cecea-155">Run `TestMethod1` tests:</span></span>

```dotnetcli
dotnet vstest /Tests:TestMethod1
```

<span data-ttu-id="cecea-156">`TestMethod1` および `TestMethod2` テストを実行する:</span><span class="sxs-lookup"><span data-stu-id="cecea-156">Run `TestMethod1` and `TestMethod2` tests:</span></span>

```dotnetcli
dotnet vstest /Tests:TestMethod1,TestMethod2
```
