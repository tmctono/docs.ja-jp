---
title: ランタイムの構成オプション
description: ランタイム構成設定を使用して .NET Core アプリケーションを構成する方法について説明します。
ms.date: 01/21/2020
ms.openlocfilehash: ddf68c30e620a06856f65e71bd050e1b77618f20
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "79397612"
---
# <a name="net-core-run-time-configuration-settings"></a><span data-ttu-id="71008-103">.NET Core ランタイム構成設定</span><span class="sxs-lookup"><span data-stu-id="71008-103">.NET Core run-time configuration settings</span></span>

<span data-ttu-id="71008-104">.NET Core では、実行時に .NET Core アプリケーションの動作を構成するために、構成ファイルと環境変数の使用がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="71008-104">.NET Core supports the use of configuration files and environment variables to configure the behavior of .NET Core applications at run time.</span></span> <span data-ttu-id="71008-105">ランタイムの構成は、次の場合に適しています。</span><span class="sxs-lookup"><span data-stu-id="71008-105">Run-time configuration is an attractive option if:</span></span>

- <span data-ttu-id="71008-106">アプリケーションのソースコードを所有または制御していないため、プログラムで構成することができない。</span><span class="sxs-lookup"><span data-stu-id="71008-106">You don't own or control the source code for an application and therefore are unable to configure it programmatically.</span></span>

- <span data-ttu-id="71008-107">アプリケーションの複数のインスタンスが 1 つのシステムで同時に実行され、最適なパフォーマンスを実現するために各インスタンスを構成する必要がある。</span><span class="sxs-lookup"><span data-stu-id="71008-107">Multiple instances of your application run at the same time on a single system, and you want to configure each for optimum performance.</span></span>

> [!NOTE]
> <span data-ttu-id="71008-108">このドキュメントは現在作成中です。</span><span class="sxs-lookup"><span data-stu-id="71008-108">This documentation is a work in progress.</span></span> <span data-ttu-id="71008-109">ここに記載されている情報が不完全であるか、不正確であることがわかった場合は、[イシューを作成](https://github.com/dotnet/docs/issues)してお知らせになるか、[pull request を送信](https://github.com/dotnet/docs/pulls)してイシューに対処してください。</span><span class="sxs-lookup"><span data-stu-id="71008-109">If you notice that the information presented here is either incomplete or inaccurate, either [open an issue](https://github.com/dotnet/docs/issues) to let us know about it, or [submit a pull request](https://github.com/dotnet/docs/pulls) to address the issue.</span></span> <span data-ttu-id="71008-110">dotnet/docs リポジトリに対する pull request の送信については、[共同作成者のガイド](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md)のページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="71008-110">For information about submitting pull requests for the dotnet/docs repository, see the [contributor's guide](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).</span></span>

<span data-ttu-id="71008-111">.NET Core には、実行時にアプリケーションを構成する次のメカニズムがあります。</span><span class="sxs-lookup"><span data-stu-id="71008-111">.NET Core provides the following mechanisms for configuring run-time application behavior:</span></span>

- <span data-ttu-id="71008-112">[runtimeconfig.json ファイル](#runtimeconfigjson)</span><span class="sxs-lookup"><span data-stu-id="71008-112">The [runtimeconfig.json file](#runtimeconfigjson)</span></span>

- [<span data-ttu-id="71008-113">MSBuild プロパティ</span><span class="sxs-lookup"><span data-stu-id="71008-113">MSBuild properties</span></span>](#msbuild-properties)

- [<span data-ttu-id="71008-114">環境変数</span><span class="sxs-lookup"><span data-stu-id="71008-114">Environment variables</span></span>](#environment-variables)

<span data-ttu-id="71008-115">一部の構成値は、<xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> メソッドを呼び出すことによって、プログラムで設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="71008-115">Some configuration values can also be set programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="71008-116">ドキュメントのこのセクションの記事は、[デバッグ](debugging-profiling.md)や[ガベージ コレクション](garbage-collector.md)などのカテゴリに分類されています。</span><span class="sxs-lookup"><span data-stu-id="71008-116">The articles in this section of the documentation are organized by category, for example, [debugging](debugging-profiling.md) and [garbage collection](garbage-collector.md).</span></span> <span data-ttu-id="71008-117">必要に応じて、*runtimeconfig.json* ファイル、MSBuild のプロパティ、環境変数用の構成オプションを示しています。また相互参照用に .NET Framework プロジェクトの *app.config* ファイルも示しています。</span><span class="sxs-lookup"><span data-stu-id="71008-117">Where applicable, configuration options are shown for *runtimeconfig.json* files, MSBuild properties, environment variables, and, for cross-reference, *app.config* files for .NET Framework projects.</span></span>

## <a name="runtimeconfigjson"></a><span data-ttu-id="71008-118">runtimeconfig.json</span><span class="sxs-lookup"><span data-stu-id="71008-118">runtimeconfig.json</span></span>

<span data-ttu-id="71008-119">プロジェクトが[ビルドされた](../tools/dotnet-build.md)場合、出力ディレクトリに *[appname].runtimeconfig.json* ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="71008-119">When a project is [built](../tools/dotnet-build.md), an *[appname].runtimeconfig.json* file is generated in the output directory.</span></span> <span data-ttu-id="71008-120">*runtimeconfig.template.json* ファイルがプロジェクト ファイルと同じフォルダーにある場合、それに設定されているすべてのオプションは *[appname].runtimeconfig.json* ファイルにマージされます。</span><span class="sxs-lookup"><span data-stu-id="71008-120">If a *runtimeconfig.template.json* file exists in the same folder as the project file, any configuration options it contains are merged into the *[appname].runtimeconfig.json* file.</span></span> <span data-ttu-id="71008-121">そのアプリをご自分でビルドする場合は、構成オプションはすべて *runtimeconfig.template.json* ファイルに追加してください。</span><span class="sxs-lookup"><span data-stu-id="71008-121">If you're building the app yourself, put any configuration options in the *runtimeconfig.template.json* file.</span></span> <span data-ttu-id="71008-122">そのアプリを実行しているだけの場合は、 *[appname].runtimeconfig.json* ファイルに直接挿入します。</span><span class="sxs-lookup"><span data-stu-id="71008-122">If you're just running the app, insert them directly into the *[appname].runtimeconfig.json* file.</span></span>

> [!NOTE]
> <span data-ttu-id="71008-123">この *[appname].runtimeconfig.json* ファイルは、以降のビルドで上書きされます。</span><span class="sxs-lookup"><span data-stu-id="71008-123">The *[appname].runtimeconfig.json* file will get overwritten on subsequent builds.</span></span>

<span data-ttu-id="71008-124">**runtimeconfig.json** ファイルの *configProperties* セクションに、ランタイム構成オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="71008-124">Specify run-time configuration options in the **configProperties** section of the *runtimeconfig.json* files.</span></span> <span data-ttu-id="71008-125">このセクションには次の形式が含まれます。</span><span class="sxs-lookup"><span data-stu-id="71008-125">This section has the form:</span></span>

```json
"configProperties": {
  "config-property-name1": "config-value1",
  "config-property-name2": "config-value2"
}
```

### <a name="example-appnameruntimeconfigjson-file"></a><span data-ttu-id="71008-126">[appname].runtimeconfig.json ファイルの例</span><span class="sxs-lookup"><span data-stu-id="71008-126">Example [appname].runtimeconfig.json file</span></span>

<span data-ttu-id="71008-127">このオプションを出力 JSON ファイルに入力する場合、`runtimeOptions` プロパティの下に入れます。</span><span class="sxs-lookup"><span data-stu-id="71008-127">If you're placing the options in the output JSON file, nest them under the `runtimeOptions` property.</span></span>

```json
{
  "runtimeOptions": {
    "tfm": "netcoreapp3.1",
    "framework": {
      "name": "Microsoft.NETCore.App",
      "version": "3.1.0"
    },
    "configProperties": {
      "System.GC.Concurrent": false,
      "System.Threading.ThreadPool.MinThreads": 4,
      "System.Threading.ThreadPool.MaxThreads": 25
    }
  }
}
```

### <a name="example-runtimeconfigtemplatejson-file"></a><span data-ttu-id="71008-128">runtimeconfig.template.json ファイルの例</span><span class="sxs-lookup"><span data-stu-id="71008-128">Example runtimeconfig.template.json file</span></span>

<span data-ttu-id="71008-129">このオプションをテンプレート JSON ファイルに入力する場合、`runtimeOptions` プロパティを省略します。</span><span class="sxs-lookup"><span data-stu-id="71008-129">If you're placing the options in the template JSON file, omit the `runtimeOptions` property.</span></span>

```json
{
  "configProperties": {
    "System.GC.Concurrent": false,
    "System.Threading.ThreadPool.MinThreads": "4",
    "System.Threading.ThreadPool.MaxThreads": "25"
  }
}
```

## <a name="msbuild-properties"></a><span data-ttu-id="71008-130">MSBuild プロパティ</span><span class="sxs-lookup"><span data-stu-id="71008-130">MSBuild properties</span></span>

<span data-ttu-id="71008-131">一部の実行構成オプションは、 *.csproj* の MSBuild のプロパティ、または SDK 形式の .NET Core プロジェクトの *.vbproj* ファイルを使用して設定できます。</span><span class="sxs-lookup"><span data-stu-id="71008-131">Some run-time configuration options can be set using MSBuild properties in the *.csproj* or *.vbproj* file of SDK-style .NET Core projects.</span></span> <span data-ttu-id="71008-132">MSBuild のプロパティは、*runtimeconfig.template.json* ファイルで設定されているオプションよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="71008-132">MSBuild properties take precedence over options set in the *runtimeconfig.template.json* file.</span></span> <span data-ttu-id="71008-133">また、 *[appname].runtimeconfig.json* ファイルに設定されているすべてのオプションもビルド時に上書きします。</span><span class="sxs-lookup"><span data-stu-id="71008-133">They also overwrite any options you set in the *[appname].runtimeconfig.json* file at build time.</span></span>

<span data-ttu-id="71008-134">次に、ランタイム動作を構成する MSBuild のプロパティがある SDK 形式のプロジェクト ファイルの例を示します。</span><span class="sxs-lookup"><span data-stu-id="71008-134">Here is an example SDK-style project file with MSBuild properties for configuring run-time behavior:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
    <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
    <ThreadPoolMaxThreads>25</ThreadPoolMaxThreads>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="71008-135">実行時の動作を構成する MSBuild プロパティについては、[ガベージ コレクション](garbage-collector.md)に関するページなど、各領域の個々の記事に記載されています。</span><span class="sxs-lookup"><span data-stu-id="71008-135">MSBuild properties for configuring run-time behavior are noted in the individual articles for each area, for example, [garbage collection](garbage-collector.md).</span></span>

## <a name="environment-variables"></a><span data-ttu-id="71008-136">環境変数</span><span class="sxs-lookup"><span data-stu-id="71008-136">Environment variables</span></span>

<span data-ttu-id="71008-137">環境変数を使用すると、ランタイムの構成情報を指定できます。</span><span class="sxs-lookup"><span data-stu-id="71008-137">Environment variables can be used to supply some run-time configuration information.</span></span> <span data-ttu-id="71008-138">環境変数として指定された構成ノブには、一般に **COMPlus_** のプレフィックスが付いています。</span><span class="sxs-lookup"><span data-stu-id="71008-138">Configuration knobs specified as environment variables generally have the prefix **COMPlus_**.</span></span>

<span data-ttu-id="71008-139">環境変数は、Windows のコントロール パネル、コマンド ライン、または Windows と Unix ベースのシステムの両方で <xref:System.Environment.SetEnvironmentVariable(System.String,System.String)?displayProperty=nameWithType> メソッドを呼び出すことによって、プログラムで定義できます。</span><span class="sxs-lookup"><span data-stu-id="71008-139">You can define environment variables from the Windows Control Panel, at the command line, or programmatically by calling the <xref:System.Environment.SetEnvironmentVariable(System.String,System.String)?displayProperty=nameWithType> method on both Windows and Unix-based systems.</span></span>

<span data-ttu-id="71008-140">次の例は、コマンド ラインで環境変数を設定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="71008-140">The following examples show how to set an environment variable at the command line:</span></span>

```shell
# Windows
set COMPlus_GCRetainVM=1

# Powershell
$env:COMPlus_GCRetainVM="1"

# Unix
export COMPlus_GCRetainVM=1
```
