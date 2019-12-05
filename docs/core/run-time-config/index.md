---
title: ランタイムの構成
description: ランタイム構成設定を使用して .NET Core アプリケーションを構成する方法について説明します。
ms.date: 11/13/2019
ms.openlocfilehash: 2665026347e94d26026821beb2bfcf8441f755f6
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/04/2019
ms.locfileid: "74801920"
---
# <a name="net-core-run-time-configuration-settings"></a><span data-ttu-id="acbdb-103">.NET Core ランタイム構成設定</span><span class="sxs-lookup"><span data-stu-id="acbdb-103">.NET Core run-time configuration settings</span></span>

<span data-ttu-id="acbdb-104">.NET Core では、実行時に .NET Core アプリケーションの動作を構成するために、構成ファイルと環境変数の使用がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="acbdb-104">.NET Core supports the use of configuration files and environment variables to configure the behavior of .NET Core applications at run time.</span></span> <span data-ttu-id="acbdb-105">ランタイムの構成は、次の場合に適しています。</span><span class="sxs-lookup"><span data-stu-id="acbdb-105">Run-time configuration is an attractive option if:</span></span>

- <span data-ttu-id="acbdb-106">アプリケーションのソースコードを所有または制御していないため、プログラムで構成することができない。</span><span class="sxs-lookup"><span data-stu-id="acbdb-106">You don't own or control the source code for an application and therefore are unable to configure it programmatically.</span></span>

- <span data-ttu-id="acbdb-107">アプリケーションの複数のインスタンスが 1 つのシステムで同時に実行され、最適なパフォーマンスを実現するために各インスタンスを構成する必要がある。</span><span class="sxs-lookup"><span data-stu-id="acbdb-107">Multiple instances of your application run at the same time on a single system, and you want to configure each for optimum performance.</span></span>

> [!NOTE]
> <span data-ttu-id="acbdb-108">このドキュメントは現在作成中です。</span><span class="sxs-lookup"><span data-stu-id="acbdb-108">This documentation is a work in progress.</span></span> <span data-ttu-id="acbdb-109">ここに記載されている情報が不完全であるか、不正確であることがわかった場合は、[イシューを作成](https://github.com/dotnet/docs/issues)してお知らせになるか、[pull request を送信](https://github.com/dotnet/docs/pulls)してイシューに対処してください。</span><span class="sxs-lookup"><span data-stu-id="acbdb-109">If you notice that the information presented here is either incomplete or inaccurate, either [open an issue](https://github.com/dotnet/docs/issues) to let us know about it, or [submit a pull request](https://github.com/dotnet/docs/pulls) to address the issue.</span></span> <span data-ttu-id="acbdb-110">dotnet/docs リポジトリに対する pull request の送信については、[共同作成者のガイド](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="acbdb-110">For information on submitting pull requests for the dotnet/docs repository, see the [contributor's guide](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).</span></span>

<span data-ttu-id="acbdb-111">.NET Core には、実行時にアプリケーションを構成するための次のメカニズムが用意されています。</span><span class="sxs-lookup"><span data-stu-id="acbdb-111">.NET Core provides the following mechanisms for configuring applications at run time:</span></span>

- <span data-ttu-id="acbdb-112">[runtimeconfig.json ファイル](#runtimeconfigjson)</span><span class="sxs-lookup"><span data-stu-id="acbdb-112">The [runtimeconfig.json file](#runtimeconfigjson)</span></span>

- [<span data-ttu-id="acbdb-113">環境変数</span><span class="sxs-lookup"><span data-stu-id="acbdb-113">Environment variables</span></span>](#environment-variables)

<span data-ttu-id="acbdb-114">ドキュメントのこのセクションの記事は、デバッグやガベージ コレクションなどのカテゴリ別に分類されています。</span><span class="sxs-lookup"><span data-stu-id="acbdb-114">The articles in this section of the documentation include are organized by category, for example, debugging and garbage collection.</span></span> <span data-ttu-id="acbdb-115">必要に応じて、*runtimeconfig. json* (.NET Core のみ)、*app.config* (.NET Framework のみ)、および環境変数の構成オプションが示されています。</span><span class="sxs-lookup"><span data-stu-id="acbdb-115">Where applicable, configuration options are shown for *runtimeconfig.json* (.NET Core only), *app.config* (.NET Framework only), and environment variables.</span></span>

## <a name="runtimeconfigjson"></a><span data-ttu-id="acbdb-116">runtimeconfig.json</span><span class="sxs-lookup"><span data-stu-id="acbdb-116">runtimeconfig.json</span></span>

<span data-ttu-id="acbdb-117">アプリの *runtimeconfig.json* ファイルの **configProperties** セクションで、ランタイム構成オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="acbdb-117">Specify run-time configuration options in the **configProperties** section of the app's *runtimeconfig.json* file.</span></span> <span data-ttu-id="acbdb-118">このセクションには次の形式が含まれます。</span><span class="sxs-lookup"><span data-stu-id="acbdb-118">This section has the form:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "config-property-name1": "config-value1",
         "config-property-name2": "config-value2"
      }
   }
}
```

<span data-ttu-id="acbdb-119">ファイルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="acbdb-119">Here is an example file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": true,
         "System.GC.RetainVM": true,
         "System.Threading.ThreadPool.MinThreads": "4",
         "System.Threading.ThreadPool.MaxThreads": "25"
      }
   }
}
```

<span data-ttu-id="acbdb-120">*runtimeconfig. json* ファイルは、[dotnet build](../tools/dotnet-build.md) コマンドによってビルド ディレクトリに自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="acbdb-120">The *runtimeconfig.json* file is automatically created in the build directory by the [dotnet build](../tools/dotnet-build.md) command.</span></span> <span data-ttu-id="acbdb-121">また、Visual Studio で **[ビルド]** メニュー オプションを選択したときにも作成されます。</span><span class="sxs-lookup"><span data-stu-id="acbdb-121">It's also created when you select the **Build** menu option in Visual Studio.</span></span> <span data-ttu-id="acbdb-122">ファイルが作成されたら、編集できます。</span><span class="sxs-lookup"><span data-stu-id="acbdb-122">You can then edit the file once it's created.</span></span>

<span data-ttu-id="acbdb-123">一部の構成値は、<xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> メソッドを呼び出すことによって、プログラムで設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="acbdb-123">Some configuration values can also be set programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

## <a name="environment-variables"></a><span data-ttu-id="acbdb-124">環境変数</span><span class="sxs-lookup"><span data-stu-id="acbdb-124">Environment variables</span></span>

<span data-ttu-id="acbdb-125">環境変数を使用すると、ランタイムの構成情報を指定できます。</span><span class="sxs-lookup"><span data-stu-id="acbdb-125">Environment variables can be used to supply some run-time configuration information.</span></span> <span data-ttu-id="acbdb-126">環境変数として指定された構成ノブには、一般に **COMPlus_** のプレフィックスが付いています。</span><span class="sxs-lookup"><span data-stu-id="acbdb-126">Configuration knobs specified as environment variables generally have the prefix **COMPlus_**.</span></span>

<span data-ttu-id="acbdb-127">環境変数は、Windows のコントロール パネル、コマンド ライン、または Windows と Unix ベースのシステムの両方で <xref:System.Environment.SetEnvironmentVariable(System.String,System.String)?displayProperty=nameWithType> メソッドを呼び出すことによって、プログラムで定義できます。</span><span class="sxs-lookup"><span data-stu-id="acbdb-127">You can define environment variables from the Windows Control Panel, at the command line, or programmatically by calling the <xref:System.Environment.SetEnvironmentVariable(System.String,System.String)?displayProperty=nameWithType> method on both Windows and Unix-based systems.</span></span>

<span data-ttu-id="acbdb-128">次の例は、コマンド ラインで環境変数を設定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="acbdb-128">The following examples show how to set an environment variable at the command line:</span></span>

```shell
# Windows
set COMPlus_GCRetainVM=1

# Powershell
$env:COMPlus_GCRetainVM="1"

# Unix
export COMPlus_GCRetainVM=1
```
