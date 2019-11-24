---
title: CLI を使用して .NET Core アプリを展開する
description: .NET Core SDK のコマンド ライン インターフェイス (CLI) ツールを使用して .NET Core アプリを公開する方法を説明します。
author: thraka
ms.author: adegeo
ms.date: 01/16/2019
dev_langs:
- csharp
- vb
ms.custom: seodec18
ms.openlocfilehash: 41af1c708a264833f1f7217529b5c0206d405449
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428914"
---
# <a name="publish-net-core-apps-with-the-cli"></a><span data-ttu-id="7eb9e-103">CLI を使用して .NET Core アプリを展開する</span><span class="sxs-lookup"><span data-stu-id="7eb9e-103">Publish .NET Core apps with the CLI</span></span>

<span data-ttu-id="7eb9e-104">この記事では、コマンド ラインから .NET Core アプリケーションを公開する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-104">This article demonstrates how you can publish your .NET Core application from the command line.</span></span> <span data-ttu-id="7eb9e-105">.NET Core では、アプリケーションを公開する方法が 3 つ用意されています。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-105">.NET Core provides three ways to publish your applications.</span></span> <span data-ttu-id="7eb9e-106">フレームワークに依存する展開では、ローカル環境にインストールされている .NET Core ランタイムを使用するクロス プラットフォームの .dll ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-106">Framework-dependent deployment produces a cross-platform .dll file that uses the locally installed .NET Core runtime.</span></span> <span data-ttu-id="7eb9e-107">フレームワークに依存する実行可能ファイルでは、ローカル環境にインストールされている .NET Core ランタイムを使用するプラットフォーム固有の実行可能ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-107">Framework-dependent executable produces a platform-specific executable that uses the locally installed .NET Core runtime.</span></span> <span data-ttu-id="7eb9e-108">自己完結型の実行可能ファイルでは、プラットフォーム固有の実行可能ファイルが生成されて、.NET Core ランタイムのローカル コピーが組み込まれます。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-108">Self-contained executable produces a platform-specific executable and includes a local copy of the .NET Core runtime.</span></span>

<span data-ttu-id="7eb9e-109">これらの公開モードの概要については、「[.NET Core アプリケーションの展開](index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-109">For an overview of these publishing modes, see [.NET Core Application Deployment](index.md).</span></span>

<span data-ttu-id="7eb9e-110">CLI の使用方法について簡単にわかるヘルプをお探しですか。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-110">Looking for some quick help on using the CLI?</span></span> <span data-ttu-id="7eb9e-111">次の表では、アプリの公開方法についての例を示します。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-111">The following table shows some examples of how to publish your app.</span></span> <span data-ttu-id="7eb9e-112">ターゲット フレームワークは、`-f <TFM>` パラメーターを使用するか、プロジェクト ファイルを編集して、指定することができます。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-112">You can specify the target framework with the `-f <TFM>` parameter or by editing the project file.</span></span> <span data-ttu-id="7eb9e-113">詳細については、「[公開の基礎](#publishing-basics)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-113">For more information, see [Publishing basics](#publishing-basics).</span></span>

| <span data-ttu-id="7eb9e-114">公開モード</span><span class="sxs-lookup"><span data-stu-id="7eb9e-114">Publish Mode</span></span> | <span data-ttu-id="7eb9e-115">SDK のバージョン</span><span class="sxs-lookup"><span data-stu-id="7eb9e-115">SDK Version</span></span> | <span data-ttu-id="7eb9e-116">コマンド</span><span class="sxs-lookup"><span data-stu-id="7eb9e-116">Command</span></span> |
| ------------ | ----------- | ------- |
| <span data-ttu-id="7eb9e-117">フレームワークに依存する展開</span><span class="sxs-lookup"><span data-stu-id="7eb9e-117">Framework-dependent deployment</span></span> | <span data-ttu-id="7eb9e-118">2.x</span><span class="sxs-lookup"><span data-stu-id="7eb9e-118">2.x</span></span> | `dotnet publish -c Release` |
| <span data-ttu-id="7eb9e-119">フレームワークに依存する実行可能ファイル</span><span class="sxs-lookup"><span data-stu-id="7eb9e-119">Framework-dependent executable</span></span> | <span data-ttu-id="7eb9e-120">2.2</span><span class="sxs-lookup"><span data-stu-id="7eb9e-120">2.2</span></span> | `dotnet publish -c Release -r <RID> --self-contained false` |
|                                | <span data-ttu-id="7eb9e-121">3.0</span><span class="sxs-lookup"><span data-stu-id="7eb9e-121">3.0</span></span> | `dotnet publish -c Release -r <RID> --self-contained false` |
|                                | <span data-ttu-id="7eb9e-122">3.0\*</span><span class="sxs-lookup"><span data-stu-id="7eb9e-122">3.0\*</span></span> | `dotnet publish -c Release` |
| <span data-ttu-id="7eb9e-123">自己完結型の展開</span><span class="sxs-lookup"><span data-stu-id="7eb9e-123">Self-contained deployment</span></span>      | <span data-ttu-id="7eb9e-124">2.1</span><span class="sxs-lookup"><span data-stu-id="7eb9e-124">2.1</span></span> | `dotnet publish -c Release -r <RID> --self-contained true` |
|                                | <span data-ttu-id="7eb9e-125">2.2</span><span class="sxs-lookup"><span data-stu-id="7eb9e-125">2.2</span></span> | `dotnet publish -c Release -r <RID> --self-contained true` |
|                                | <span data-ttu-id="7eb9e-126">3.0</span><span class="sxs-lookup"><span data-stu-id="7eb9e-126">3.0</span></span> | `dotnet publish -c Release -r <RID> --self-contained true` |

<span data-ttu-id="7eb9e-127">\* SDK バージョン 3.0 を使用する場合、基本的な `dotnet publish` コマンドを実行するときは、フレームワークに依存する実行可能ファイルが既定の公開モードです。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-127">\* When using SDK version 3.0, framework-dependent executable is the default publishing mode when running the basic `dotnet publish` command.</span></span> <span data-ttu-id="7eb9e-128">これは、プロジェクトのターゲットが **.NET Core 2.1** または **.NET Core 3.0** である場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-128">This only applies when the project targets either **.NET Core 2.1** or **.NET Core 3.0**.</span></span>

## <a name="publishing-basics"></a><span data-ttu-id="7eb9e-129">公開の基礎</span><span class="sxs-lookup"><span data-stu-id="7eb9e-129">Publishing basics</span></span>

<span data-ttu-id="7eb9e-130">アプリを公開するときは、プロジェクト ファイルの設定 `<TargetFramework>` で既定のターゲット フレームワークを指定します。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-130">The `<TargetFramework>` setting of the project file specifies the default target framework when you publish your app.</span></span> <span data-ttu-id="7eb9e-131">任意の有効な[ターゲット フレームワーク モニカー (TFM)](../../standard/frameworks.md) にターゲット フレームワークを変更できます。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-131">You can change the target framework to any valid [Target Framework Moniker (TFM)](../../standard/frameworks.md).</span></span> <span data-ttu-id="7eb9e-132">たとえば、プロジェクトで `<TargetFramework>netcoreapp2.2</TargetFramework>` を使用している場合は、.NET Core 2.2 をターゲットとするバイナリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-132">For example, if your project uses `<TargetFramework>netcoreapp2.2</TargetFramework>`, a binary that targets .NET Core 2.2 is created.</span></span> <span data-ttu-id="7eb9e-133">この設定で指定されている TFM が、[`dotnet publish`](../tools/dotnet-publish.md) コマンドで使用される既定のターゲットになります。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-133">The TFM specified in this setting is the default target used by the [`dotnet publish`](../tools/dotnet-publish.md) command.</span></span>

<span data-ttu-id="7eb9e-134">複数のフレームワークをターゲットにしたい場合は、セミコロンで区切ることにより設定 `<TargetFrameworks>` で複数の TFM 値を設定できます。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-134">If you want to target more than one framework, you can set the `<TargetFrameworks>` setting to more than one TFM value separated by a semicolon.</span></span> <span data-ttu-id="7eb9e-135">`dotnet publish -f <TFM>` コマンドではフレームワークの 1 つを公開できます。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-135">You can publish one of the frameworks with the `dotnet publish -f <TFM>` command.</span></span> <span data-ttu-id="7eb9e-136">たとえば、`<TargetFrameworks>netcoreapp2.1;netcoreapp2.2</TargetFrameworks>` と設定して `dotnet publish -f netcoreapp2.1` を実行すると、.NET Core 2.1 をターゲットとするバイナリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-136">For example, if you have `<TargetFrameworks>netcoreapp2.1;netcoreapp2.2</TargetFrameworks>` and run `dotnet publish -f netcoreapp2.1`, a binary that targets .NET Core 2.1 is created.</span></span>

<span data-ttu-id="7eb9e-137">他の値を設定しない限り、[`dotnet publish`](../tools/dotnet-publish.md) コマンドの出力ディレクトリは `./bin/<BUILD-CONFIGURATION>/<TFM>/publish/` です。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-137">Unless otherwise set, the output directory of the [`dotnet publish`](../tools/dotnet-publish.md) command is `./bin/<BUILD-CONFIGURATION>/<TFM>/publish/`.</span></span> <span data-ttu-id="7eb9e-138">`-c` パラメーターで変更しない限り、**BUILD-CONFIGURATION** の既定のモードは **Debug** です。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-138">The default **BUILD-CONFIGURATION** mode is **Debug** unless changed with the `-c` parameter.</span></span> <span data-ttu-id="7eb9e-139">たとえば、`dotnet publish -c Release -f netcoreapp2.1` と指定すると、`myfolder/bin/Release/netcoreapp2.1/publish/` に公開されます。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-139">For example, `dotnet publish -c Release -f netcoreapp2.1` publishes to `myfolder/bin/Release/netcoreapp2.1/publish/`.</span></span>

<span data-ttu-id="7eb9e-140">.NET Core SDK 3.0 を使用する場合、.NET Core バージョン 2.1、2.2、または 3.0 をターゲットとするアプリの既定の公開モードは、フレームワークに依存する実行可能ファイルです。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-140">If you use .NET Core SDK 3.0, the default publish mode for apps that target .NET Core versions 2.1, 2.2, or 3.0 is framework-dependent executable.</span></span>

<span data-ttu-id="7eb9e-141">.NET Core SDK 2.1 を使用する場合、.NET Core バージョン 2.1 または 2.2 をターゲットとするアプリの既定の公開モードは、フレームワークに依存する展開です。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-141">If you use .NET Core SDK 2.1, the default publish mode for apps that target .NET Core versions 2.1, 2.2 is framework-dependent deployment.</span></span>

### <a name="native-dependencies"></a><span data-ttu-id="7eb9e-142">ネイティブの依存関係</span><span class="sxs-lookup"><span data-stu-id="7eb9e-142">Native dependencies</span></span>

<span data-ttu-id="7eb9e-143">アプリにネイティブの依存関係がある場合、別のオペレーティング システムではアプリが実行されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-143">If your app has native dependencies, it may not run on a different operating system.</span></span> <span data-ttu-id="7eb9e-144">たとえば、ネイティブの Windows API を使用しているアプリは、macOS または Linux では実行されません。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-144">For example, if your app uses the native Windows API, it won't run on macOS or Linux.</span></span> <span data-ttu-id="7eb9e-145">プラットフォーム固有のコードを提供し、プラットフォームごとに実行可能ファイルをコンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-145">You would need to provide platform-specific code and compile an executable for each platform.</span></span>

<span data-ttu-id="7eb9e-146">また、参照しているライブラリにネイティブの依存関係がある場合、すべてのプラットフォームではアプリを実行できない可能性があることも考慮してください。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-146">Consider also, if a library you referenced has a native dependency, your app may not run on every platform.</span></span> <span data-ttu-id="7eb9e-147">ただし、参照している NuGet パッケージには、必要なネイティブの依存関係を処理するためにプラットフォーム固有のバージョンが含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-147">However, it's possible a NuGet package you're referencing has included platform-specific versions to handle the required native dependencies for you.</span></span>

<span data-ttu-id="7eb9e-148">ネイティブの依存関係があるアプリを配布するときは、`dotnet publish -r <RID>` スイッチを使用して、公開対象のターゲット プラットフォームを指定することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-148">When distributing an app with native dependencies, you may need to use the `dotnet publish -r <RID>` switch to specify the target platform you want to publish for.</span></span> <span data-ttu-id="7eb9e-149">ランタイム識別子の一覧については、[ランタイム識別子 (RID) のカタログ](../rid-catalog.md)に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-149">For a list of runtime identifiers, see [Runtime Identifier (RID) catalog](../rid-catalog.md).</span></span>

<span data-ttu-id="7eb9e-150">プラットフォーム固有のバイナリの詳細については、「[フレームワークに依存する実行可能ファイル](#framework-dependent-executable)」および「[自己完結型の展開](#self-contained-deployment)」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-150">More information about platform-specific binaries is covered in the [Framework-dependent executable](#framework-dependent-executable) and [Self-contained deployment](#self-contained-deployment) sections.</span></span>

## <a name="sample-app"></a><span data-ttu-id="7eb9e-151">サンプル アプリ</span><span class="sxs-lookup"><span data-stu-id="7eb9e-151">Sample app</span></span>

<span data-ttu-id="7eb9e-152">次のアプリを使用して、公開コマンドを確認できます。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-152">You can use the following app to explore the publishing commands.</span></span> <span data-ttu-id="7eb9e-153">ターミナルで次のコマンドを実行すると、アプリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-153">The app is created by running the following commands in your terminal:</span></span>

```dotnetcli
mkdir apptest1
cd apptest1
dotnet new console
dotnet add package Figgle
```

<span data-ttu-id="7eb9e-154">コンソール テンプレートによって生成される `Program.cs` または `Program.vb` ファイルを、次のように変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-154">The `Program.cs` or `Program.vb` file that is generated by the console template needs to be changed to the following:</span></span>

```csharp
using System;

namespace apptest1
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine(Figgle.FiggleFonts.Standard.Render("Hello, World!"));
        }
    }
}
```

```vb
Module Program
    Sub Main(args As String())
        Console.WriteLine(Figgle.FiggleFonts.Standard.Render("Hello, World!"))
    End Sub
End Module
```

<span data-ttu-id="7eb9e-155">アプリを実行すると ([`dotnet run`](../tools/dotnet-run.md))、次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-155">When you run the app ([`dotnet run`](../tools/dotnet-run.md)), the following output is displayed:</span></span>

```terminal
  _   _      _ _         __        __         _     _ _
 | | | | ___| | | ___    \ \      / /__  _ __| | __| | |
 | |_| |/ _ \ | |/ _ \    \ \ /\ / / _ \| '__| |/ _` | |
 |  _  |  __/ | | (_) |    \ V  V / (_) | |  | | (_| |_|
 |_| |_|\___|_|_|\___( )    \_/\_/ \___/|_|  |_|\__,_(_)
                     |/
```

## <a name="framework-dependent-deployment"></a><span data-ttu-id="7eb9e-156">フレームワークに依存する展開</span><span class="sxs-lookup"><span data-stu-id="7eb9e-156">Framework-dependent deployment</span></span>

<span data-ttu-id="7eb9e-157">.NET Core SDK 2.x の CLI では、フレームワークに依存する展開 (FDD) が、基本的な `dotnet publish` コマンドの既定のモードです。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-157">For the .NET Core SDK 2.x CLI, framework-dependent deployment (FDD) is the default mode for the basic `dotnet publish` command.</span></span>

<span data-ttu-id="7eb9e-158">FDD としてアプリを公開すると、`./bin/<BUILD-CONFIGURATION>/<TFM>/publish/` フォルダーに`<PROJECT-NAME>.dll` ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-158">When you publish your app as an FDD, a `<PROJECT-NAME>.dll` file is created in the `./bin/<BUILD-CONFIGURATION>/<TFM>/publish/` folder.</span></span> <span data-ttu-id="7eb9e-159">アプリを実行するには、出力フォルダーに移動して、`dotnet <PROJECT-NAME>.dll` コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-159">To run your app, navigate to the output folder and use the `dotnet <PROJECT-NAME>.dll` command.</span></span>

<span data-ttu-id="7eb9e-160">アプリは、特定のバージョンの .NET Core をターゲットにするように構成されます。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-160">Your app is configured to target a specific version of .NET Core.</span></span> <span data-ttu-id="7eb9e-161">アプリを実行するコンピューターには、そのターゲットの .NET Core ランタイムが存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-161">That targeted .NET Core runtime is required to be on the machine where you want to run your app.</span></span> <span data-ttu-id="7eb9e-162">たとえば、アプリのターゲットが .NET Core 2.2 である場合、アプリを実行するコンピューターには、.NET Core 2.2 ランタイムがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-162">For example, if your app targets .NET Core 2.2, any machine that your app runs on must have the .NET Core 2.2 runtime installed.</span></span> <span data-ttu-id="7eb9e-163">「[公開の基礎](#publishing-basics)」セクションで説明したように、プロジェクト ファイルを編集することで、既定のターゲット フレームワークを変更したり、複数のフレームワークをターゲットにしたりできます。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-163">As stated in the [Publishing basics](#publishing-basics) section, you can edit your project file to change the default target framework or to target more than one framework.</span></span>

<span data-ttu-id="7eb9e-164">FDD の公開では、アプリが実行されるシステムで使用できる最新の .NET Core セキュリティ更新プログラムまで自動的にロールフォワードするアプリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-164">Publishing an FDD creates an app that automatically rolls-forward to the latest .NET Core security patch available on the system that runs the app.</span></span> <span data-ttu-id="7eb9e-165">コンパイル時のバージョンのバインドの詳細については、「[使用する .NET Core のバージョンを選択する](../versions/selection.md#framework-dependent-apps-roll-forward)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-165">For more information on version binding at compile time, see [Select the .NET Core version to use](../versions/selection.md#framework-dependent-apps-roll-forward).</span></span>

## <a name="framework-dependent-executable"></a><span data-ttu-id="7eb9e-166">フレームワークに依存する実行可能ファイル</span><span class="sxs-lookup"><span data-stu-id="7eb9e-166">Framework-dependent executable</span></span>

<span data-ttu-id="7eb9e-167">.NET Core SDK 3.x の CLI では、フレームワークに依存する実行可能ファイル (FDE) が、基本的な `dotnet publish` コマンドの既定のモードです。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-167">For the .NET Core SDK 3.x CLI, framework-dependent executable (FDE) is the default mode for the basic `dotnet publish` command.</span></span> <span data-ttu-id="7eb9e-168">現在のオペレーティング システムをターゲットにする限り、他のパラメーターを指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-168">You don't need to specify any other parameters as long as you want to target the current operating system.</span></span>

<span data-ttu-id="7eb9e-169">このモードでは、クロスプラットフォーム アプリをホストするために、プラットフォームに固有の実行可能なホストが作成されます。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-169">In this mode, a platform-specific executable host is created to host your cross-platform app.</span></span> <span data-ttu-id="7eb9e-170">FDD では `dotnet` コマンドの形式でホストを要求するので、このモードは FDD と似ています。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-170">This mode is similar to FDD as FDD requires a host in the form of the `dotnet` command.</span></span> <span data-ttu-id="7eb9e-171">ホストの実行可能ファイル名はプラットフォームごとに異なり、`<PROJECT-FILE>.exe` のような名前になります。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-171">The host executable filename varies per platform, and is named something similar to `<PROJECT-FILE>.exe`.</span></span> <span data-ttu-id="7eb9e-172">この実行可能ファイルを直接実行することができ、`dotnet <PROJECT-FILE>.dll` を呼び出す代わりに使用できますが、このコマンドもアプリの実行手段として同じように使用できます。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-172">You can run this executable directly instead of calling `dotnet <PROJECT-FILE>.dll` which is still an acceptable way to run the app.</span></span>

<span data-ttu-id="7eb9e-173">アプリは、特定のバージョンの .NET Core をターゲットにするように構成されます。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-173">Your app is configured to target a specific version of .NET Core.</span></span> <span data-ttu-id="7eb9e-174">アプリを実行するコンピューターには、そのターゲットの .NET Core ランタイムが存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-174">That targeted .NET Core runtime is required to be on the machine where you want to run your app.</span></span> <span data-ttu-id="7eb9e-175">たとえば、アプリのターゲットが .NET Core 2.2 である場合、アプリを実行するコンピューターには、.NET Core 2.2 ランタイムがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-175">For example, if your app targets .NET Core 2.2, any machine that your app runs on must have the .NET Core 2.2 runtime installed.</span></span> <span data-ttu-id="7eb9e-176">「[公開の基礎](#publishing-basics)」セクションで説明したように、プロジェクト ファイルを編集することで、既定のターゲット フレームワークを変更したり、複数のフレームワークをターゲットにしたりできます。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-176">As stated in the [Publishing basics](#publishing-basics) section, you can edit your project file to change the default target framework or to target more than one framework.</span></span>

<span data-ttu-id="7eb9e-177">FDE の公開では、アプリが実行されるシステムで使用できる最新の .NET Core セキュリティ更新プログラムまで自動的にロールフォワードするアプリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-177">Publishing an FDE creates an app that automatically rolls-forward to the latest .NET Core security patch available on the system that runs the app.</span></span> <span data-ttu-id="7eb9e-178">コンパイル時のバージョンのバインドの詳細については、「[使用する .NET Core のバージョンを選択する](../versions/selection.md#framework-dependent-apps-roll-forward)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-178">For more information on version binding at compile time, see [Select the .NET Core version to use](../versions/selection.md#framework-dependent-apps-roll-forward).</span></span>

<span data-ttu-id="7eb9e-179">`dotnet publish` コマンドで次のスイッチを使用して、FDE を公開する必要があります (現在のプラットフォームをターゲットにするときの .NET Core 3.x を除きます)。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-179">You must (except for .NET Core 3.x when you target the current platform) use the following switches with the `dotnet publish` command to publish an FDE:</span></span>

- <span data-ttu-id="7eb9e-180">`-r <RID>` このスイッチでは、識別子 (RID) を使用してターゲット プラットフォームを指定します。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-180">`-r <RID>` This switch uses an identifier (RID) to specify the target platform.</span></span> <span data-ttu-id="7eb9e-181">ランタイム識別子の一覧については、[ランタイム識別子 (RID) のカタログ](../rid-catalog.md)に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-181">For a list of runtime identifiers, see [Runtime Identifier (RID) catalog](../rid-catalog.md).</span></span>

- <span data-ttu-id="7eb9e-182">`--self-contained false` このスイッチでは、識別子 (RID) を使用してターゲット プラットフォームを指定します。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-182">`--self-contained false` This switch tells the .NET Core SDK to create an executable as an FDE.</span></span>

<span data-ttu-id="7eb9e-183">`-r` スイッチを使用すると常に、出力フォルダーのパスが `./bin/<BUILD-CONFIGURATION>/<TFM>/<RID>/publish/` に変わります</span><span class="sxs-lookup"><span data-stu-id="7eb9e-183">Whenever you use the `-r` switch, the output folder path changes to: `./bin/<BUILD-CONFIGURATION>/<TFM>/<RID>/publish/`</span></span>

<span data-ttu-id="7eb9e-184">[アプリの例](#sample-app)を使用する場合は、`dotnet publish -f netcoreapp2.2 -r win10-x64 --self-contained false` を実行します。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-184">If you use the [example app](#sample-app), run `dotnet publish -f netcoreapp2.2 -r win10-x64 --self-contained false`.</span></span> <span data-ttu-id="7eb9e-185">このコマンドでは、実行可能ファイル `./bin/Debug/netcoreapp2.2/win10-x64/publish/apptest1.exe` が作成されます</span><span class="sxs-lookup"><span data-stu-id="7eb9e-185">This command creates the following executable: `./bin/Debug/netcoreapp2.2/win10-x64/publish/apptest1.exe`</span></span>

> [!NOTE]
> <span data-ttu-id="7eb9e-186">**グローバリゼーション インバリアント モード**を有効にすることで、展開の合計サイズを小さくすることができます。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-186">You can reduce the total size of your deployment by enabling **globalization invariant mode**.</span></span> <span data-ttu-id="7eb9e-187">このモードは、全世界を意識するものではなく、[インバリアント カルチャ](xref:System.Globalization.CultureInfo.InvariantCulture)の書式設定規則、大文字/小文字の区別規則、文字列比較、並べ替え順序を使用できるアプリケーションにとって便利です。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-187">This mode is useful for applications that are not globally aware and that can use the formatting conventions, casing conventions, and string comparison and sort order of the [invariant culture](xref:System.Globalization.CultureInfo.InvariantCulture).</span></span> <span data-ttu-id="7eb9e-188">**グローバリゼーション インバリアント モード**の詳細と、それを有効にする方法については、「[.NET Core Globalization Invariant Mode](https://github.com/dotnet/corefx/blob/master/Documentation/architecture/globalization-invariant-mode.md)」(.NET Core のグローバリゼーション インバリアント モード) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-188">For more information about **globalization invariant mode** and how to enable it, see [.NET Core Globalization Invariant Mode](https://github.com/dotnet/corefx/blob/master/Documentation/architecture/globalization-invariant-mode.md).</span></span>

## <a name="self-contained-deployment"></a><span data-ttu-id="7eb9e-189">自己完結型の展開</span><span class="sxs-lookup"><span data-stu-id="7eb9e-189">Self-contained deployment</span></span>

<span data-ttu-id="7eb9e-190">自己完結型の展開 (SCD) を公開すると、.NET Core SDK によってプラットフォーム固有の実行可能ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-190">When you publish a self-contained deployment (SCD), the .NET Core SDK creates a platform-specific executable.</span></span> <span data-ttu-id="7eb9e-191">SCD の公開には、アプリの実行に必要なすべての .NET Core ファイルが含まれますが、[.NET Core のネイティブの依存関係](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md)は含まれません。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-191">Publishing an SCD includes all required .NET Core files to run your app but it doesn't include the [native dependencies of .NET Core](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span></span> <span data-ttu-id="7eb9e-192">これらの依存関係は、アプリを実行する前に、システムに存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-192">These dependencies must be present on the system before the app runs.</span></span>

<span data-ttu-id="7eb9e-193">SCD の公開で作成されるアプリでは、使用可能な最新の .NET Core セキュリティ更新プログラムへのロールフォワードは行われません。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-193">Publishing an SCD creates an app that doesn't roll-forward to the latest available .NET Core security patch.</span></span> <span data-ttu-id="7eb9e-194">コンパイル時のバージョンのバインドの詳細については、「[使用する .NET Core のバージョンを選択する](../versions/selection.md#self-contained-deployments-include-the-selected-runtime)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-194">For more information on version binding at compile time, see [Select the .NET Core version to use](../versions/selection.md#self-contained-deployments-include-the-selected-runtime).</span></span>

<span data-ttu-id="7eb9e-195">`dotnet publish` コマンドで次のスイッチを使用して、SCD を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-195">You must use the following switches with the `dotnet publish` command to publish an SCD:</span></span>

- <span data-ttu-id="7eb9e-196">`-r <RID>` このスイッチでは、識別子 (RID) を使用してターゲット プラットフォームを指定します。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-196">`-r <RID>` This switch uses an identifier (RID) to specify the target platform.</span></span> <span data-ttu-id="7eb9e-197">ランタイム識別子の一覧については、[ランタイム識別子 (RID) のカタログ](../rid-catalog.md)に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-197">For a list of runtime identifiers, see [Runtime Identifier (RID) catalog](../rid-catalog.md).</span></span>

- <span data-ttu-id="7eb9e-198">`--self-contained true` このスイッチでは、SCD として実行可能ファイルを作成するよう .NET Core SDK に指示されます。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-198">`--self-contained true` This switch tells the .NET Core SDK to create an executable as an SCD.</span></span>

> [!NOTE]
> <span data-ttu-id="7eb9e-199">**グローバリゼーション インバリアント モード**を有効にすることで、展開の合計サイズを小さくすることができます。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-199">You can reduce the total size of your deployment by enabling **globalization invariant mode**.</span></span> <span data-ttu-id="7eb9e-200">このモードは、全世界を意識するものではなく、[インバリアント カルチャ](xref:System.Globalization.CultureInfo.InvariantCulture)の書式設定規則、大文字/小文字の区別規則、文字列比較、並べ替え順序を使用できるアプリケーションにとって便利です。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-200">This mode is useful for applications that are not globally aware and that can use the formatting conventions, casing conventions, and string comparison and sort order of the [invariant culture](xref:System.Globalization.CultureInfo.InvariantCulture).</span></span> <span data-ttu-id="7eb9e-201">**グローバリゼーション インバリアント モード**の詳細と、それを有効にする方法については、「[.NET Core Globalization Invariant Mode](https://github.com/dotnet/corefx/blob/master/Documentation/architecture/globalization-invariant-mode.md)」(.NET Core のグローバリゼーション インバリアント モード) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7eb9e-201">For more information about **globalization invariant mode** and how to enable it, see [.NET Core Globalization Invariant Mode](https://github.com/dotnet/corefx/blob/master/Documentation/architecture/globalization-invariant-mode.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7eb9e-202">関連項目</span><span class="sxs-lookup"><span data-stu-id="7eb9e-202">See also</span></span>

- [<span data-ttu-id="7eb9e-203">.NET Core アプリケーションの展開の概要</span><span class="sxs-lookup"><span data-stu-id="7eb9e-203">.NET Core Application Deployment Overview</span></span>](index.md)
- [<span data-ttu-id="7eb9e-204">.NET Core のランタイム識別子 (RID) のカタログ</span><span class="sxs-lookup"><span data-stu-id="7eb9e-204">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
