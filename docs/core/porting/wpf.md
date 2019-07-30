---
title: WPF アプリを .NET Core 3.0 に移植する
description: .NET Framework Windows Presentation Foundation アプリケーションを .NET Core 3.0 for Windows に移植する方法について説明します。
author: Thraka
ms.author: adegeo
ms.date: 03/27/2019
ms.custom: ''
ms.openlocfilehash: 9885f666e68b795b9b6aba9cf31f9750e30fd170
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512281"
---
# <a name="how-to-port-a-wpf-desktop-app-to-net-core"></a><span data-ttu-id="a0040-103">方法: WPF デスクトップ アプリを .NET Core に移植する</span><span class="sxs-lookup"><span data-stu-id="a0040-103">How to: Port a WPF desktop app to .NET Core</span></span>

<span data-ttu-id="a0040-104">この記事では、Windows Presentation Foundation (WPF) ベースのデスクトップ アプリを .NET Framework から .NET Core 3.0 に移植する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a0040-104">This article describes how to port your Windows Presentation Foundation-based (WPF) desktop app from .NET Framework to .NET Core 3.0.</span></span> <span data-ttu-id="a0040-105">.NET Core 3.0 SDK には、WPF アプリケーションのサポートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a0040-105">The .NET Core 3.0 SDK includes support for WPF applications.</span></span> <span data-ttu-id="a0040-106">WPF は、まだ Windows 専用のフレームワークであるため、Windows 上でのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="a0040-106">WPF is still a Windows-only framework and only runs on Windows.</span></span> <span data-ttu-id="a0040-107">この例では、.NET Core CLI を使用して、プロジェクトの作成と管理を行います。</span><span class="sxs-lookup"><span data-stu-id="a0040-107">This example uses the .NET Core SDK CLI to create and manage your project.</span></span>

<span data-ttu-id="a0040-108">この記事では、さまざまな名前が使用して、移行で使用されるファイルの種類を識別しています。</span><span class="sxs-lookup"><span data-stu-id="a0040-108">In this article, various names are used to identify types of files used for migration.</span></span> <span data-ttu-id="a0040-109">実際のファイルの名前とは異なっているため、自分のプロジェクトを移行するときは、次の一覧の名前に置き換えて説明をお読みください。</span><span class="sxs-lookup"><span data-stu-id="a0040-109">When migrating your project, your files will be named differently, so mentally match them to the ones listed below:</span></span>

| <span data-ttu-id="a0040-110">ファイル</span><span class="sxs-lookup"><span data-stu-id="a0040-110">File</span></span> | <span data-ttu-id="a0040-111">説明</span><span class="sxs-lookup"><span data-stu-id="a0040-111">Description</span></span> |
| ---- | ----------- |
| <span data-ttu-id="a0040-112">**MyApps.sln**</span><span class="sxs-lookup"><span data-stu-id="a0040-112">**MyApps.sln**</span></span> | <span data-ttu-id="a0040-113">ソリューション ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="a0040-113">The name of the solution file.</span></span> |
| <span data-ttu-id="a0040-114">**MyWPF.csproj**</span><span class="sxs-lookup"><span data-stu-id="a0040-114">**MyWPF.csproj**</span></span> | <span data-ttu-id="a0040-115">移植する .NET Framework WPF プロジェクトの名前。</span><span class="sxs-lookup"><span data-stu-id="a0040-115">The name of the .NET Framework WPF project to port.</span></span> |
| <span data-ttu-id="a0040-116">**MyWPFCore.csproj**</span><span class="sxs-lookup"><span data-stu-id="a0040-116">**MyWPFCore.csproj**</span></span> | <span data-ttu-id="a0040-117">作成する新しい .NET Core プロジェクトの名前。</span><span class="sxs-lookup"><span data-stu-id="a0040-117">The name of the new .NET Core project you create.</span></span> |
| <span data-ttu-id="a0040-118">**MyAppCore.exe**</span><span class="sxs-lookup"><span data-stu-id="a0040-118">**MyAppCore.exe**</span></span> | <span data-ttu-id="a0040-119">.NET Core WPF アプリの実行可能ファイル。</span><span class="sxs-lookup"><span data-stu-id="a0040-119">The .NET Core WPF app executable.</span></span> |

>[!IMPORTANT]
><span data-ttu-id="a0040-120">この記事では C# をターゲット言語として使用しますが、VB.NET でも手順は同じです。ただし、VB.NET では、 *.csproj* ファイルと *.cs* ファイルの代わりに、それぞれ *.vbproj* ファイルと *.vb* ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="a0040-120">Even though this article uses C# as the target language, the steps are the same for VB.NET, except that VB.NET uses *.vbproj* and *.vb* files instead of *.csproj* and *.cs* files, respectively.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a0040-121">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a0040-121">Prerequisites</span></span>

- <span data-ttu-id="a0040-122">実行したいデザイナー作業用の [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)。</span><span class="sxs-lookup"><span data-stu-id="a0040-122">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) for any designer work you want to do.</span></span>

  <span data-ttu-id="a0040-123">次の Visual Studio ワークロードをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a0040-123">Install the following Visual Studio workloads:</span></span>
  - <span data-ttu-id="a0040-124">.NET デスクトップ開発</span><span class="sxs-lookup"><span data-stu-id="a0040-124">.NET desktop development</span></span>
  - <span data-ttu-id="a0040-125">.NET クロスプラットフォーム開発</span><span class="sxs-lookup"><span data-stu-id="a0040-125">.NET cross-platform development</span></span>

- <span data-ttu-id="a0040-126">問題なくビルドされて実行されているソリューション内の作業用 WPF プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="a0040-126">A working WPF project in a solution that builds and runs without issue.</span></span>
- <span data-ttu-id="a0040-127">最新の [.NET Core 3.0](https://aka.ms/netcore3download) のプレビューをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a0040-127">Install the latest [.NET Core 3.0](https://aka.ms/netcore3download) preview.</span></span>

>[!NOTE]
><span data-ttu-id="a0040-128">**Visual Studio 2017** では、.NET Core 3.0 プロジェクトはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a0040-128">**Visual Studio 2017** doesn't support .NET Core 3.0 projects.</span></span> <span data-ttu-id="a0040-129">**Visual Studio 2019** では .NET Core 3.0 プロジェクトがサポートされますが、.NET Core WPF ビジュアル デザイナーのサポートは制限されています。</span><span class="sxs-lookup"><span data-stu-id="a0040-129">**Visual Studio 2019** supports .NET Core 3.0 projects but has limited support for the .NET Core WPF visual designer.</span></span> <span data-ttu-id="a0040-130">完全にサポートされるビジュアル デザイナーを使用するには、.NET Core プロジェクトとそのファイルを共有するソリューション内に .NET Framework WPF プロジェクトが必要です。</span><span class="sxs-lookup"><span data-stu-id="a0040-130">To use a fully-supported visual designer, you must have a .NET Framework WPF project in your solution that shares its files with the .NET Core project.</span></span>

### <a name="consider"></a><span data-ttu-id="a0040-131">次の例を考えてみましょう</span><span class="sxs-lookup"><span data-stu-id="a0040-131">Consider</span></span>

<span data-ttu-id="a0040-132">.NET Framework WPF アプリケーションを移植するときは、いくつかの点を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0040-132">When porting a .NET Framework WPF application, there are a few things you must consider.</span></span>

01. <span data-ttu-id="a0040-133">アプリケーションが移行に適した候補であることを確認する。</span><span class="sxs-lookup"><span data-stu-id="a0040-133">Check that your application is a good candidate for migration.</span></span>

    <span data-ttu-id="a0040-134">[.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) を使用して、プロジェクトを .NET Core 3.0 に移行できるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="a0040-134">Use the [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) to determine if your project will migrate to .NET Core 3.0.</span></span> <span data-ttu-id="a0040-135">プロジェクトが .NET Core 3.0 では問題が発生する場合は、アナライザーによってこれらの問題を特定できます。</span><span class="sxs-lookup"><span data-stu-id="a0040-135">If your project has issues with .NET Core 3.0, the analyzer helps you identify those problems.</span></span>

01. <span data-ttu-id="a0040-136">WPF の別のバージョンを使用している。</span><span class="sxs-lookup"><span data-stu-id="a0040-136">You're using a different version of WPF.</span></span>

    <span data-ttu-id="a0040-137">.NET Core 3.0 プレビュー 1 がリリースされたときに、WPF は GitHub でオープン ソースになりました。</span><span class="sxs-lookup"><span data-stu-id="a0040-137">When .NET Core 3.0 Preview 1 was released, WPF went open-source on GitHub.</span></span> <span data-ttu-id="a0040-138">.NET Core WPF のコードは、.NET Framework WPF コード ベースの 1 つの分岐です。</span><span class="sxs-lookup"><span data-stu-id="a0040-138">The code for .NET Core WPF is a fork of the .NET Framework WPF code base.</span></span> <span data-ttu-id="a0040-139">違いの存在によって、アプリが移植されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a0040-139">It's possible some differences exist and your app won't port.</span></span>

01. <span data-ttu-id="a0040-140">[Windows 互換機能パック][compat-pack]が移行に役立つ可能性がある。</span><span class="sxs-lookup"><span data-stu-id="a0040-140">The [Windows Compatibility Pack][compat-pack] may help you migrate.</span></span>

    <span data-ttu-id="a0040-141">.NET Framework で利用できる一部の API は、.NET Core 3.0 では利用できません。</span><span class="sxs-lookup"><span data-stu-id="a0040-141">Some APIs that are available in .NET Framework aren't available in .NET Core 3.0.</span></span> <span data-ttu-id="a0040-142">[Windows 互換機能パック][compat-pack]によってその多くの API が追加され、WPF アプリに .NET Core との互換性を持たせるために役立つ可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a0040-142">The [Windows Compatibility Pack][compat-pack] adds many of these APIs and may help your WPF app become compatible with .NET Core.</span></span>

01. <span data-ttu-id="a0040-143">自分のプロジェクトで使用されている NuGet パッケージを更新する。</span><span class="sxs-lookup"><span data-stu-id="a0040-143">Update the NuGet packages used by your project.</span></span>

    <span data-ttu-id="a0040-144">移行する前に、常に NuGet パッケージの最新バージョンを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a0040-144">It's always a good practice to use the latest versions of NuGet packages before any migration.</span></span> <span data-ttu-id="a0040-145">アプリケーションで NuGet パッケージを参照している場合は、最新バージョンに更新してください。</span><span class="sxs-lookup"><span data-stu-id="a0040-145">If your application is referencing any NuGet packages, update them to the latest version.</span></span> <span data-ttu-id="a0040-146">アプリケーションが正常にビルドされることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a0040-146">Ensure your application builds successfully.</span></span> <span data-ttu-id="a0040-147">アップグレード後にパッケージ エラーが発生した場合は、コードを壊さない最新のバージョンにパッケージをダウングレードします。</span><span class="sxs-lookup"><span data-stu-id="a0040-147">After upgrading, if there are any package errors, downgrade the package to the latest version that doesn't break your code.</span></span>

01. <span data-ttu-id="a0040-148">Visual Studio 2019 では、.NET Core 3.0 用の WPF デザイナーはまだサポートされていない</span><span class="sxs-lookup"><span data-stu-id="a0040-148">Visual Studio 2019 doesn't yet support the WPF Designer for .NET Core 3.0</span></span>

    <span data-ttu-id="a0040-149">現時点では、Visual Studio の WPF デザイナーを使用する場合は、既存の .NET Framework WPF プロジェクト ファイルを保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0040-149">Currently, you need to keep your existing .NET Framework WPF project file if you want to use the WPF Designer from Visual Studio.</span></span>

## <a name="create-a-new-sdk-project"></a><span data-ttu-id="a0040-150">新しい SDK プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="a0040-150">Create a new SDK project</span></span>

<span data-ttu-id="a0040-151">作成する新しい .NET Core 3.0 プロジェクトは、.NET Framework プロジェクトとは別のディレクトリに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0040-151">The new .NET Core 3.0 project you create must be in a different directory from your .NET Framework project.</span></span> <span data-ttu-id="a0040-152">両方が同じディレクトリに配置されている場合は、**obj** ディレクトリ内に生成されているファイルと競合する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a0040-152">If they're both in the same directory, you may run into conflicts with the files that are generated in the **obj** directory.</span></span> <span data-ttu-id="a0040-153">この例では、**SolutionFolder** ディレクトリに **MyWPFAppCore** という名前のディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="a0040-153">In this example, you'll create a directory named **MyWPFAppCore** in the **SolutionFolder** directory:</span></span>

```
SolutionFolder
├───MyApps.sln
├───MyWPFApp
│   └───MyWPF.csproj
└───MyWPFAppCore      <--- New folder for core project
```

<span data-ttu-id="a0040-154">次に、**MyWPFAppCore** ディレクトリに **MyWPFCore.csproj** プロジェクトを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0040-154">Next, you need to create the **MyWPFCore.csproj** project in the **MyWPFAppCore** directory.</span></span> <span data-ttu-id="a0040-155">このファイルは、任意のテキスト エディターを使用して手動で作成できます。</span><span class="sxs-lookup"><span data-stu-id="a0040-155">You can create this file manually by using the text editor of choice.</span></span> <span data-ttu-id="a0040-156">次の XML に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="a0040-156">Paste in the following XML:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="a0040-157">プロジェクト ファイルを手動で作成しない場合は、Visual Studio または .NET Core SDK を使用して生成できます。</span><span class="sxs-lookup"><span data-stu-id="a0040-157">If you don't want to create the project file manually, you can use Visual Studio or the .NET Core SDK to generate the project.</span></span> <span data-ttu-id="a0040-158">ただし、プロジェクト ファイル以外のプロジェクト テンプレートによって生成されるすべてのファイルを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0040-158">However, you must delete all other files generated by the project template except for the project file.</span></span> <span data-ttu-id="a0040-159">SDK を使用するには、次のコマンドを **SolutionFolder** ディレクトリから実行します。</span><span class="sxs-lookup"><span data-stu-id="a0040-159">To use the SDK, run the following command from the **SolutionFolder** directory:</span></span>

```cli
dotnet new wpf -o MyWPFAppCore -n MyWPFCore
```

<span data-ttu-id="a0040-160">**MyWPFCore.csproj** を作成した後、ディレクトリ構造は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="a0040-160">After you create the **MyWPFCore.csproj**, your directory structure should look like the following:</span></span>

```
SolutionFolder
├───MyApps.sln
├───MyWPFApp
│   └───MyWPF.csproj
└───MyWPFAppCore
    └───MyWPFCore.csproj
```

<span data-ttu-id="a0040-161">**SolutionFolder** ディレクトリから Visual Studio または .NET Core CLI を使用して、**MyWPFCore.csproj** プロジェクトを **MyApps.sln** に追加できます。</span><span class="sxs-lookup"><span data-stu-id="a0040-161">You'll want to add the **MyWPFCore.csproj** project to **MyApps.sln** with either Visual Studio or the .NET Core CLI from the **SolutionFolder** directory:</span></span>

```cli
dotnet sln add .\MyWPFAppCore\MyWPFCore.csproj
```

## <a name="fix-assembly-info-generation"></a><span data-ttu-id="a0040-162">アセンブリ情報の生成を修正する</span><span class="sxs-lookup"><span data-stu-id="a0040-162">Fix assembly info generation</span></span>

<span data-ttu-id="a0040-163">.NET Framework で作成された Windows Presentation Foundation プロジェクトには、生成されるアセンブリのバージョンなどのアセンブリの属性を格納する `AssemblyInfo.cs` ファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a0040-163">Windows Presentation Foundation projects that were created with .NET Framework include an `AssemblyInfo.cs` file, which contains assembly attributes such as the version of the assembly to be generated.</span></span> <span data-ttu-id="a0040-164">SDK スタイルのプロジェクトでは、SDK プロジェクト ファイルに基づいて、この情報が自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="a0040-164">SDK-style projects automatically generate this information for you based on the SDK project file.</span></span> <span data-ttu-id="a0040-165">両方の種類の "アセンブリ情報" があると、競合が発生します。</span><span class="sxs-lookup"><span data-stu-id="a0040-165">Having both types of "assembly info" creates a conflict.</span></span> <span data-ttu-id="a0040-166">この問題は、自動生成を無効にして、既存の `AssemblyInfo.cs` ファイルをプロジェクトに強制的に使用させることで解決します。</span><span class="sxs-lookup"><span data-stu-id="a0040-166">Resolve this problem by disabling automatic generation, which forces the project to use your existing `AssemblyInfo.cs` file.</span></span>

<span data-ttu-id="a0040-167">メインの `<PropertyGroup>` ノードに追加する 3 つの設定があります。</span><span class="sxs-lookup"><span data-stu-id="a0040-167">There are three settings to add to the main `<PropertyGroup>` node.</span></span> 

- <span data-ttu-id="a0040-168">**GenerateAssemblyInfo**</span><span class="sxs-lookup"><span data-stu-id="a0040-168">**GenerateAssemblyInfo**</span></span>\
<span data-ttu-id="a0040-169">このプロパティを `false` に設定すると、アセンブリ属性が生成されなくなります。</span><span class="sxs-lookup"><span data-stu-id="a0040-169">When you set this property to `false`, it won't generate the assembly attributes.</span></span> <span data-ttu-id="a0040-170">これにより、.NET Framework プロジェクトからの既存の `AssemblyInfo.cs` ファイルとの競合を回避できます。</span><span class="sxs-lookup"><span data-stu-id="a0040-170">This avoids the conflict with the existing `AssemblyInfo.cs` file from the .NET Framework project.</span></span>

- <span data-ttu-id="a0040-171">**AssemblyName**</span><span class="sxs-lookup"><span data-stu-id="a0040-171">**AssemblyName**</span></span>\
<span data-ttu-id="a0040-172">このプロパティの値は、コンパイル時に作成される出力バイナリです。</span><span class="sxs-lookup"><span data-stu-id="a0040-172">The value of this property is the output binary created when you compile.</span></span> <span data-ttu-id="a0040-173">名前には、拡張子を追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a0040-173">The name doesn't need an extension added to it.</span></span> <span data-ttu-id="a0040-174">たとえば、`MyCoreApp` を使用すると、`MyCoreApp.exe` が作成されます。</span><span class="sxs-lookup"><span data-stu-id="a0040-174">For example, using `MyCoreApp` produces `MyCoreApp.exe`.</span></span>

- <span data-ttu-id="a0040-175">**RootNamespace**</span><span class="sxs-lookup"><span data-stu-id="a0040-175">**RootNamespace**</span></span>\
<span data-ttu-id="a0040-176">プロジェクトで使用される既定の名前空間。</span><span class="sxs-lookup"><span data-stu-id="a0040-176">The default namespace used by your project.</span></span> <span data-ttu-id="a0040-177">これは、.NET Framework プロジェクトの既定の名前空間と一致させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0040-177">This should match the default namespace of the .NET Framework project.</span></span>

<span data-ttu-id="a0040-178">これら 3 つの要素を、`MyWPFCore.csproj` ファイルの `<PropertyGroup>` ノードに追加します。</span><span class="sxs-lookup"><span data-stu-id="a0040-178">Add these three elements to the `<PropertyGroup>` node in the `MyWPFCore.csproj` file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWPF>true</UseWPF>

    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    <AssemblyName>MyCoreApp</AssemblyName>
    <RootNamespace>MyWPF</RootNamespace>
  </PropertyGroup>

</Project>
```

## <a name="add-source-code"></a><span data-ttu-id="a0040-179">ソース コードを追加する</span><span class="sxs-lookup"><span data-stu-id="a0040-179">Add source code</span></span>
<span data-ttu-id="a0040-180">現時点では、**MyWPFCore.csproj** プロジェクトには、コンパイルされるコードはありません。</span><span class="sxs-lookup"><span data-stu-id="a0040-180">Right now, the **MyWPFCore.csproj** project doesn't compile any code.</span></span> <span data-ttu-id="a0040-181">既定では、.NET Core プロジェクトには、現在のディレクトリとすべての子ディレクトリ内のすべてのソース コードが自動的に含まれます。</span><span class="sxs-lookup"><span data-stu-id="a0040-181">By default, .NET Core projects automatically include all source code in the current directory and any child directories.</span></span> <span data-ttu-id="a0040-182">相対パスを使用して、.NET Framework プロジェクトのコードが含まれるようにプロジェクトを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0040-182">You must configure the project to include code from the .NET Framework project using a relative path.</span></span> <span data-ttu-id="a0040-183">.NET Framework プロジェクトで、ウィンドウとコントロールのアイコンとリソース用の **.resx** ファイルが使用されている場合は、それらも含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0040-183">If your .NET Framework project used **.resx** files for icons and resources for your windows and controls, you'll need to include those too.</span></span> 

<span data-ttu-id="a0040-184">プロジェクトに追加する必要がある最初の `<ItemGroup>` ノードには、アプリで使用されるスタートアップ構成とリソースを表す **App.xaml** ファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="a0040-184">The first `<ItemGroup>` node you need to add to your project includes the **App.xaml** file that represents the startup config and resources your app uses.</span></span> <span data-ttu-id="a0040-185">**App.xaml** ファイルには **App.xaml.cs** ファイルも付随しますが、それは別の `<ItemGroup>` に自動的に入ります。</span><span class="sxs-lookup"><span data-stu-id="a0040-185">The **App.xaml** file also has an accompanying **App.xaml.cs** file, but it will be automatically included in a different `<ItemGroup>`.</span></span>

```xml
  <ItemGroup>
    <ApplicationDefinition Include="..\MyWPFApp\App.xaml">
      <Generator>MSBuild:Compile</Generator>
    </ApplicationDefinition>
  </ItemGroup>
```

<span data-ttu-id="a0040-186">次に、次の `<ItemGroup>` コードをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="a0040-186">Next, add the following `<ItemGroup>` node to your project.</span></span> <span data-ttu-id="a0040-187">各ステートメントには、子ディレクトリを含むファイルの glob パターンが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a0040-187">Each statement includes a file glob pattern that includes child directories.</span></span> <span data-ttu-id="a0040-188">これには、プロジェクトのソース コード、設定ファイル、リソースが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a0040-188">It includes the source code for your project, any settings files, and any resources.</span></span> <span data-ttu-id="a0040-189">**obj** ディレクトリは明示的に除外されます。</span><span class="sxs-lookup"><span data-stu-id="a0040-189">The **obj** directory is explicitly excluded.</span></span>

```xml
  <ItemGroup>
    <Compile Include="..\MyWPFApp\**\*.cs" Exclude="..\MyWPFApp\obj\**" />
    <None Include="..\MyWPFApp\**\*.settings" />
    <EmbeddedResource Include="..\MyWPFApp\**\*.resx" />
  </ItemGroup>
```

<span data-ttu-id="a0040-190">次に、**App.xaml** ファイルを除くすべての **xaml** ファイルの `<Page>` エントリが含まれる別の `<ItemGroup>` ノードをプロジェクトに含めます。</span><span class="sxs-lookup"><span data-stu-id="a0040-190">Next, include another `<ItemGroup>` node that contains a `<Page>` entry for every **xaml** file in your project except the **App.xaml** file.</span></span> <span data-ttu-id="a0040-191">これには、**xaml** 形式のすべてのウィンドウ、ページ、リソースが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a0040-191">These contain all of the windows, pages, and resources that are in **xaml** format.</span></span> <span data-ttu-id="a0040-192">ここでは glob パターンを使用できません。ファイルごとにエントリを追加し、使用されている `<Generator>` を示す必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0040-192">You cannot use a glob pattern here and must add an entry for every file and indicate the `<Generator>` used.</span></span>

```xml
  <ItemGroup>
    <Page Include="..\MyWPFApp\MainWindow.xaml">
      <Generator>MSBuild:Compile</Generator>
    </Page>
  </ItemGroup>
```

## <a name="add-nuget-packages"></a><span data-ttu-id="a0040-193">NuGet パッケージを追加する</span><span class="sxs-lookup"><span data-stu-id="a0040-193">Add NuGet packages</span></span>

<span data-ttu-id="a0040-194">.NET Framework プロジェクトによって参照される各 NuGet パッケージを.NET Core プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="a0040-194">Add each NuGet package referenced by the .NET Framework project to the .NET Core project.</span></span> 

<span data-ttu-id="a0040-195">ほとんどの場合、.NET Framework WPF アプリには、**packages.config** プロジェクトによって参照されるすべての NuGet パッケージの一覧を含むファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="a0040-195">Most likely your .NET Framework WPF app has a **packages.config** file that contains a list of all of the NuGet packages that are referenced by your project.</span></span> <span data-ttu-id="a0040-196">この一覧を調べて、.NET Core プロジェクトに追加する NuGet パッケージを決定できます。</span><span class="sxs-lookup"><span data-stu-id="a0040-196">You can look at this list to determine which NuGet packages to add to the .NET Core project.</span></span> <span data-ttu-id="a0040-197">たとえば、.NET Framework プロジェクトで `MahApps.Metro` NuGet パッケージが参照される場合、Visual Studio でそれをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="a0040-197">For example, if the .NET Framework project references the `MahApps.Metro` NuGet package, add it to the project with Visual Studio.</span></span> <span data-ttu-id="a0040-198">**SolutionFolder** ディレクトリから .NET Core CLI を使用してパッケージ参照を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="a0040-198">You can also add the package reference with the .NET Core CLI from the **SolutionFolder** directory:</span></span>

```cli
dotnet add .\MyWPFAppCore\MyWPFCore.csproj package MahApps.Metro -v 2.0.0-alpha0262
```

<span data-ttu-id="a0040-199">上のコマンドによって、次の NuGet 参照が **MyWPFCore.csproj** プロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="a0040-199">The previous command would add the following NuGet reference to the **MyWPFCore.csproj** project:</span></span>

```xml
  <ItemGroup>
    <PackageReference Include="MahApps.Metro" Version="2.0.0-alpha0262" />
  </ItemGroup>
```

## <a name="problems-compiling"></a><span data-ttu-id="a0040-200">コンパイルの問題</span><span class="sxs-lookup"><span data-stu-id="a0040-200">Problems compiling</span></span>

<span data-ttu-id="a0040-201">プロジェクトのコンパイルで問題が発生した場合は、.NET Framework では使用できるが .NET Core では使用できない Windows 専用 API が使用されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a0040-201">If you have problems compiling your projects, you may be using some Windows-only APIs that are available in .NET Framework but not available in .NET Core.</span></span> <span data-ttu-id="a0040-202">[Windows 互換機能パック][compat-pack] NuGet パッケージのプロジェクトへの追加を試すことができます。</span><span class="sxs-lookup"><span data-stu-id="a0040-202">You can try adding the [Windows Compatibility Pack][compat-pack] NuGet package to your project.</span></span> <span data-ttu-id="a0040-203">このパッケージは Windows でのみ実行され、約 20,000 の Windows API を .NET Core と .NET Standard プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="a0040-203">This package only runs on Windows and adds about 20,000 Windows APIs to .NET Core and .NET Standard projects.</span></span>

```cli
dotnet add .\MyWPFAppCore\MyWPFCore.csproj package Microsoft.Windows.Compatibility
```

<span data-ttu-id="a0040-204">前のコマンドにより、以下が **MyWPFCore.csproj** プロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="a0040-204">The previous command adds the following to the **MyWPFCore.csproj** project:</span></span>

```xml
  <ItemGroup>
    <PackageReference Include="Microsoft.Windows.Compatibility" Version="2.0.1" />
  </ItemGroup>
```

## <a name="wpf-designer"></a><span data-ttu-id="a0040-205">WPF デザイナー</span><span class="sxs-lookup"><span data-stu-id="a0040-205">WPF Designer</span></span>

<span data-ttu-id="a0040-206">この記事で説明したように、Visual Studio 2019 では、.NET Framework プロジェクトでのみ WPF デザイナーがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="a0040-206">As detailed in this article, Visual Studio 2019 only supports the WPF Designer in .NET Framework projects.</span></span> <span data-ttu-id="a0040-207">サイドバイサイドの .NET Core プロジェクトを作成することで、.NET Framework プロジェクトを使用してフォームをデザインしながら、.NET Core でプロジェクトをテストできます。</span><span class="sxs-lookup"><span data-stu-id="a0040-207">By creating a side-by-side .NET Core project, you can test your project with .NET Core while you use the .NET Framework project to design forms.</span></span> <span data-ttu-id="a0040-208">ソリューション ファイルには、.NET Framework と .NET Core の両方のプロジェクトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a0040-208">Your solution file includes both the .NET Framework and .NET Core projects.</span></span> <span data-ttu-id="a0040-209">.NET Framework プロジェクトにフォームとコントロールを追加してデザインし、.NET Core プロジェクトに追加されたファイルの glob パターンに基づいて、新しいファイルまたは変更されたファイルが、.NET Core プロジェクトに自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="a0040-209">Add and design your forms and controls in the .NET Framework project, and based on the file glob patterns we added to the .NET Core projects, any new or changed files will automatically be included in the .NET Core projects.</span></span>

<span data-ttu-id="a0040-210">Visual Studio 2019 で WPF デザイナーがサポートされるようになったら、.NET Core プロジェクト ファイルの内容を .NET Framework プロジェクト ファイルにコピーして貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="a0040-210">Once Visual Studio 2019 supports the WPF Designer, you can copy/paste the content of your .NET Core project file into the .NET Framework project file.</span></span> <span data-ttu-id="a0040-211">その後、`<Source>` と `<EmbeddedResource>` 項目を使用して追加されたファイルの glob パターンを削除します。</span><span class="sxs-lookup"><span data-stu-id="a0040-211">Then delete the file glob patterns added with the `<Source>` and `<EmbeddedResource>` items.</span></span> <span data-ttu-id="a0040-212">アプリで使用されるすべてのプロジェクト参照のパスを修正します。</span><span class="sxs-lookup"><span data-stu-id="a0040-212">Fix the paths to any project reference used by your app.</span></span> <span data-ttu-id="a0040-213">これにより、.NET Framework プロジェクトが .NET Core プロジェクトに効率的にアップグレードされます。</span><span class="sxs-lookup"><span data-stu-id="a0040-213">This effectively upgrades the .NET Framework project to a .NET Core project.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a0040-214">次の手順</span><span class="sxs-lookup"><span data-stu-id="a0040-214">Next steps</span></span>

- <span data-ttu-id="a0040-215">[Windows 互換機能パック][compat-pack]の詳細を確認する。</span><span class="sxs-lookup"><span data-stu-id="a0040-215">Read more about the [Windows Compatibility Pack][compat-pack].</span></span>
- <span data-ttu-id="a0040-216">.NET Framework WPF プロジェクトの .NET Core への[移植に関するビデオ](https://www.youtube.com/watch?v=5MomsgkWkVw&list=PLS__JrkRveTMiWxG-Lv4cBwYfMQ6m2gmt)を視聴する。</span><span class="sxs-lookup"><span data-stu-id="a0040-216">Watch a [video on porting](https://www.youtube.com/watch?v=5MomsgkWkVw&list=PLS__JrkRveTMiWxG-Lv4cBwYfMQ6m2gmt) your .NET Framework WPF project to .NET Core.</span></span>

[compat-pack]: windows-compat-pack.md
